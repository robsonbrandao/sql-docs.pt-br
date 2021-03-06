---
title: Configurando o SQL Server Managed Backup to Windows Azure para grupos de disponibilidade | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 0c4553cd-d8e4-4691-963a-4e414cc0f1ba
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 6a67b2331959dbc3087f6282be05de90b42443c5
ms.sourcegitcommit: 1ab115a906117966c07d89cc2becb1bf690e8c78
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/27/2018
ms.locfileid: "52416827"
---
# <a name="setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups"></a>Configurando o Backup Gerenciado do SQL Server para Windows Azure para Grupos de Disponibilidade
  Este tópico é um tutorial sobre como configurar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para bancos de dados que fazem parte dos Grupos de Disponibilidade AlwaysOn.  
  
## <a name="availability-group-configurations"></a>Configurações de grupo de disponibilidade  
 O [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] tem suporte para bancos de dados do Grupo de Disponibilidade, estejam as réplicas configuradas no local ou inteiramente no Windows Azure, ou em uma implementação Híbrida entre local ou em uma ou mais máquinas virtuais do Windows Azure. No entanto, talvez você precise considerar o seguinte para uma ou mais implementações:  
  
-   Frequência de backup de log: A frequência de backup de log é o crescimento de tempo e de log. Por exemplo, o backup de log é feito uma vez a cada 2 horas, a menos que o espaço de log usado nesse período de duas horas seja de 5 MB ou mais. Isso se aplica a todas as implementações, locais, em nuvem ou Híbrida.  
  
-   Largura de banda de rede: Ela se aplica a implementações nas quais as réplicas estão localizadas em diferentes locais físicos, como uma nuvem híbrida ou entre regiões diferentes do Microsoft Azure em uma configuração somente em nuvem. A largura de banda de rede pode afetar a latência dos secundários e se os secundários forem definidos como replicação síncrona, então isso poderá causar aumento de log no primário. Se os secundários forem definidos para replicação síncrona, não poderão prosseguir devido à latência de rede, o que poderá resultar em perda de dados no caso de um failover na réplica secundária.  
  
### <a name="configuring-includesssmartbackupincludesss-smartbackup-mdmd-for-availability-databases"></a>Configurando o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para bancos de dados de disponibilidade.  
 **Permissões:**  
  
-   Requer associação na **db_backupoperator** função de banco de dados com **ALTER ANY CREDENTIAL** permissões, e `EXECUTE` permissões em **sp_delete_backuphistory**procedimento armazenado.  
  
-   Requer permissões **SELECT** na função **smart_admin.fn_get_current_xevent_settings**.  
  
-   Requer `EXECUTE` permissões de **sp_get_backup_diagnostics** procedimento armazenado. Além disso, requer permissões `VIEW SERVER STATE`, pois chama internamente outros objetos do sistema que exigem essa permissão.  
  
-   Requer `EXECUTE` permissões de `smart_admin.sp_set_instance_backup` e `smart_admin.sp_backup_master_switch` procedimentos armazenados.  
  
 Estas são as etapas básicas para configurar um Grupo de disponibilidade AlwaysOn com o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]. Um tutorial passo a passo detalhado será descrito mais adiante neste tópico.  
  
1.  Depois que você criar Grupo de Disponibilidade, configure a réplica de backup preferencial. Essa configuração para o Grupo de Disponibilidade também é usada pelo [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para determinar qual réplica deve ser usada para o backup. Para obter instruções passo a passo sobre como configurar a preferência de backup, consulte [Configurar Backup em réplicas de disponibilidade &#40;SQL Server&#41;](availability-groups/windows/configure-backup-on-availability-replicas-sql-server.md).  Se você estiver criando um novo grupo de disponibilidade AlwaysOn, consulte [Introdução aos grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](availability-groups/windows/getting-started-with-always-on-availability-groups-sql-server.md).  
  
2.  Configure o acesso de conexão somente leitura às réplicas secundárias. Para instruções passo a passo sobre como configurar o acesso somente leitura, consulte [configurar o acesso de somente leitura em uma réplica de disponibilidade &#40;SQL Server&#41;](availability-groups/windows/configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
3.  Especifique a réplica de Backup. A configuração de réplica de backup preferencial é usada pelo [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para determinar o banco de dados a ser usado para agendar backups.  Para determinar se a réplica atual é a réplica de backup preferencial, use o [sys. fn_hadr_backup_is_preferred_replica &#40;Transact-SQL&#41; ](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql) função.  
  
4.  Em cada réplica, execute [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configuração do banco de dados usando o **inteligente admin.sp_set_db_backup** procedimento armazenado.  
  
     **[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] comportamento após um failover:** [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] continuarão funcionando e mantendo cópias de backup e capacidade de recuperação após um evento de failover. Nenhuma ação específica é necessária depois de um failover.  
  
#### <a name="considerations-and-requirements"></a>Considerações e requisitos:  
 Configurar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para os bancos de dados que participam do Grupo de Disponibilidade AlwaysOn exige considerações e requisitos específicos. Esta é uma lista de considerações e requisitos:  
  
-   Os parâmetros de configuração do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] devem ser os mesmos para todos os bancos de dados em todos os nós do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que participam no mesmo Grupo de Disponibilidade. Você pode obter isso definindo as mesmas configurações do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para todas as réplicas primárias e no nível do banco de dados ou definindo as mesmas configurações padrão do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] em todos os nós participantes dos Grupos de Disponibilidade. É recomendável definir o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] no banco de dados, pois configurar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] no nível do banco de dados permite isolar as configurações nos bancos de dados, e as alterações nas configurações padrão afetam todos os outros bancos de dados na instâncias.  
  
-   Especifique a réplica de Backup. A configuração da réplica de backup preferencial é usada pelo [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para agendar os backups. Para determinar se a réplica atual é a réplica de backup preferencial, use o [sys. fn_hadr_backup_is_preferred_replica &#40;Transact-SQL&#41; ](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql) função.  
  
-   Se a réplica secundária estiver configurada como a réplica preferencial, ela deverá ser configurada para ter pelo menos acesso de conexão somente leitura. Não há suporte para grupos de disponibilidade que não têm nenhum acesso de conexão com os bancos de dados secundários.  Para obter mais informações, veja [Configurar o acesso somente leitura em uma réplica de disponibilidade &#40;SQL Server&#41;](availability-groups/windows/configure-read-only-access-on-an-availability-replica-sql-server.md).  
  
-   Se você estiver configurando o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] depois de configurar o Grupo de Disponibilidade, o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] tentará copiar todos os backups existentes e os copiará no contêiner de armazenamento.  Se o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] não conseguir localizar ou acessar os backup existentes, ele agendará um backup completo do banco de dados. Isso é feito especificamente para otimizar as operações de backup de bancos de dados do Grupo de Disponibilidade.  
  
-   Você talvez queira considerar desabilitar as configurações de nível de instância, se você estiver criando um novo banco de dados de disponibilidade, e você não pretende aplicar as configurações de nível de instância para o banco de dados  
  
-   Ao usar criptografia, use o mesmo certificado em todas as réplicas. Isso facilita as operações de backup e contínuas ininterruptas no caso de um failover ou de restaurações em uma réplica diferente.  
  
#### <a name="enable-and-configure-includesssmartbackupincludesss-smartbackup-mdmd-for-an-availability-database"></a>Habilitar e configurar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para um Banco de Dados de Disponibilidade  
 Este tutorial descreve as etapas de habilitação e configuração do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para um banco de dados (AGTestDB) nos computadores Node1 e Node2, seguidas pelas etapas de habilitação do monitoramento do status de integridade do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].  
  
1.  **Crie uma conta de armazenamento do Windows Azure:** Os backups são armazenados no serviço de armazenamento de Blob do Microsoft Azure. Primeiro, você deverá criar uma conta de armazenamento do Windows Azure, se ainda não tiver uma. Para obter mais informações, consulte [Criando uma conta de armazenamento do Windows Azure](http://www.windowsazure.com/manage/services/storage/how-to-create-a-storage-account/). Anote o nome da conta de armazenamento, as chaves de acesso e a URL da conta de armazenamento. O nome da conta de armazenamento e as informações de chave de acesso são usados para criar uma Credencial SQL. A Credencial do SQL é usada pelo [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] durante operações de backup para autenticação para a conta de armazenamento.  
  
2.  **Crie uma credencial SQL:** Crie uma Credencial do SQL usando o nome da conta de armazenamento como a Identidade e a chave de acesso de armazenamento como a senha.  
  
3.  **Verifique se o serviço SQL Server Agent é iniciado e em execução:** Inicie o SQL Server Agent se ele ainda não estiver em execução. [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] requer que o SQL Server Agent esteja em execução na instância para executar operações de backup.  Talvez seja necessário definir o SQL Agent para ser executado automaticamente para garantir que as operações de backup ocorram regularmente.  
  
4.  **Determine o período de retenção:** Determine o período de retenção que você deseja para os arquivos de backup. O período de retenção é especificado em dias e pode variar de 1 a 30. O período de retenção determina o tempo de recuperação do banco de dados.  
  
5.  **Crie uma certificado ou chave assimétrica para usar para a criptografia durante o:** Criar o certificado no primeiro nó Node1 e, em seguida, exportá-lo em um arquivo usando [certificado de BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql)... No Nó 2, crie um certificado usando o arquivo exportado do Nó 1. Para obter mais informações sobre como criar um certificado de um arquivo, consulte o exemplo na [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).  
  
6.  **Habilitar e configurar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para AGTestDB no Node1:** Inicie o SQL Server Management Studio e conecte-se à instância em Node1 na qual o banco de dados de disponibilidade está instalado. Na janela de consulta, execute a seguinte instrução após modificar os valores do nome do banco de dados, a URL de armazenamento, a Credencial SQL e o período de retenção de acordo com seus requisitos:  
  
    ```  
    Use msdb;  
    GO  
    EXEC smart_admin.sp_set_db_backup   
                    @database_name='AGTestDB'   
                    ,@retention_days=30   
                    ,@credential_name='MyCredential'  
                    ,@encryption_algorithm ='AES_128'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert'  
                    ,@enable_backup=1;  
    GO  
  
    ```  
  
     Para obter mais informações sobre como criar um certificado para criptografia, consulte a etapa **Criar um certificado de backup** em [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).  
  
7.  **Habilitar e configurar [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para AGTestDB no Node2:** Inicie o SQL Server Management Studio e conecte-se à instância em Node2 na qual o banco de dados de disponibilidade está instalado. Na janela de consulta, execute a seguinte instrução após modificar os valores do nome do banco de dados, a URL de armazenamento, a Credencial SQL e o período de retenção de acordo com seus requisitos:  
  
    ```  
    Use msdb;  
    GO  
    EXEC smart_admin.sp_set_db_backup   
                    @database_name='AGTestDB'   
                    ,@retention_days=30   
                    ,@credential_name='MyCredential'  
                    ,@encryption_algorithm ='AES_128'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert'  
                    ,@enable_backup=1;  
    GO  
  
    ```  
  
     [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] está habilitado no banco de dados que você especificou. Podem ser necessários até 15 minutos para que as operações de backup no banco de dados comecem a ser executadas. O backup ocorrerá na réplica de backup preferencial.  
  
8.  **Examine a configuração padrão do evento estendido:**  Analise a configuração de evento estendido executando a seguinte instrução transact-SQL na réplica que [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] está usando para agendar os backups. Em geral, essa é a configuração da réplica de backup preferencial para um Grupo de Disponibilidade ao qual o banco de dados pertence.  
  
    ```  
    SELECT * FROM smart_admin.fn_get_current_xevent_settings()  
    ```  
  
     Você verá que os eventos de canal Admin, Operacional e Analítico estão habilitados por padrão e não podem ser desabilitados. Isso deve ser suficiente para monitorar os eventos que requerem intervenção manual.  Você pode habilitar os eventos de depuração, mas esses canais incluem eventos informativos e de depuração que usa o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para detectar problemas e resolvê-los. Para obter mais informações, consulte [Monitor de SQL Server Managed Backup to Windows Azure](../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md).  
  
9. **Habilitar e configurar a notificação do status de integridade:** [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] tem um procedimento armazenado que cria um trabalho de agente para enviar notificações por email sobre erros ou avisos que possam exigir atenção.  Para receber essas notificações, você deve habilitar a execução do procedimento armazenado que cria um Trabalho do SQL Server Agent. As etapas a seguir descrevem o processo para habilitar e configurar notificações por email:  
  
    1.  Configure o Database Mail se ele ainda não estiver habilitado na instância. Para obter mais informações, consulte [Configure Database Mail](../relational-databases/database-mail/configure-database-mail.md).  
  
    2.  Configure o SQL Server Agent Notification para usar o Database Mail. Para obter mais informações, consulte [Configurar o SQL Server Agent Mail para usar o Database Mail](../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).  
  
    3.  **Habilite notificações por email receber avisos e erros de backup:** Na janela de consulta, execute as seguintes instruções Transact-SQL:  
  
        ```  
        EXEC msdb.smart_admin.sp_set_parameter  
        @parameter_name = 'SSMBackup2WANotificationEmailIds',  
        @parameter_value = '<email>'  
  
        ```  
  
         Para obter mais informações e um script de exemplo completo, consulte [Monitor de SQL Server Managed Backup to Windows Azure](../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md).  
  
10. **Exibir arquivos de backup na conta de armazenamento do Windows Azure:** Conecte-se à conta de armazenamento do SQL Server Management Studio ou do Portal de Gerenciamento do Azure. Você verá um contêiner para a instância do SQL Server que hospeda o banco de dados que configurou para usar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]. Você também poderá consultar um banco de dados e um backup de log 15 minutos depois de habilitar o [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] para o banco de dados.  
  
11. **Monitore o Status de integridade:**  Você pode monitorar por meio de notificações de email que configurou antes ou monitorar ativamente os eventos registrados. Estes são alguns exemplos de instruções Transact-SQL usados para exibir os eventos:  
  
    ```  
    --  view all admin events  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    DECLARE @eventresult TABLE  
    (event_type nvarchar(512),  
    event varchar (512),  
    timestamp datetime  
    )  
  
    INSERT INTO @eventresult  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek  
  
    SELECT * from @eventresult  
    WHERE event_type LIKE '%admin%'  
  
    ```  
  
    ```  
    -- to enable debug events  
    Use msdb;  
    Go  
             EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
  
    ```  
  
    ```  
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;  
  
    ```  
  
 As etapas descritas nesta seção destinam-se especificamente à configuração do [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] pela primeira vez no banco de dados. Você pode modificar as configurações existentes usando o mesmo procedimento armazenado do sistema **smart_admin.sp_set_db_backup** e fornecer os novos valores. Para obter mais informações, consulte [SQL Server Managed Backup to Windows Azure - Retention and Storage Settings](../../2014/database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md).  
  
### <a name="considerations-when-removing-a-database-from-alwayson-availability-group-configuration"></a>Considerações ao remover um banco de dados de configuração do Grupo de Disponibilidade AlwaysOn  
 Se um banco de dados é removido da configuração do grupo de disponibilidade AlwaysOn e agora é um banco de dados autônomo, é recomendável fazer backup usando [smart_admin.sp_backup_on_demand &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/managed-backup-sp-backup-on-demand-transact-sql). Quando você cria um backup de banco de dados dessa maneira, ele estabelece uma nova cadeia de backup, e o arquivo será colocado no contêiner específico da instância, e não no contêiner de disponibilidade do contêiner em que os backups foram armazenados quando o banco de dados fazia parte do Grupo de Disponibilidade.  
  
> [!WARNING]  
>  A capacidade de recuperação do banco de dados nesse cenário, desde os backups anteriores até a alteração do status do Grupo de Disponibilidade, não é garantida.  
  
  
