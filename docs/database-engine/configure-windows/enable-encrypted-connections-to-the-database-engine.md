---
title: Habilitar conexões criptografadas com o Mecanismo de Banco de Dados | Microsoft Docs
ms.custom: ''
ms.date: 12/21/2017
ms.prod: sql
ms.prod_service: high-availability
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], encrypted
- SSL [SQL Server]
- Secure Sockets Layer (SSL)
- encryption [SQL Server], connections
- cryptography [SQL Server], connections
- certificates [SQL Server], installing
- requesting encrypted connections
- installing certificates
- security [SQL Server], encryption
ms.assetid: e1e55519-97ec-4404-81ef-881da3b42006
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 6fd3c164b539c8c6fc2dcce24f8ea1ad479ddee6
ms.sourcegitcommit: b51edbe07a0a2fdb5f74b5874771042400baf919
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/28/2019
ms.locfileid: "55087685"
---
# <a name="enable-encrypted-connections-to-the-database-engine"></a>Habilitar conexões criptografadas com o Mecanismo de Banco de Dados
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

  Este tópico descreve como habilitar conexões criptografadas para uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] especificando um certificado para o [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager. O computador servidor deve ter um certificado configurado e a máquina cliente deve estar configurada para confiar na autoridade raiz do certificado. Provisionamento é o processo de instalar um certificado importando-o para o Windows.  
  
 O certificado deve ser emitido para **Autenticação do Servidor**. O nome do certificado deve ser o FQDN (nome de domínio totalmente qualificado) do computador.  
  
 Os certificados são armazenados localmente para os usuários no computador. Para instalar um certificado para uso do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], é necessário executar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager com uma conta que tem privilégios de administrador local.
 
  
 O cliente deve poder verificar a propriedade do certificado usado pelo servidor. Se o cliente tiver o certificado de chave pública da autoridade de certificação que assinou o certificado de servidor, nenhuma outra configuração será necessária. [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows inclui os certificados de chave pública de muitas autoridades de certificação. Se o certificado do servidor foi assinado por uma autoridade de certificação pública ou privada para a qual o cliente não tem o certificado de chave pública, será necessário instalar o certificado de chave pública da autoridade de certificação que assinou o certificado do servidor.  
  
> [!NOTE]  
>  Para usar critografia com um cluster de failover, você deve instalar o certificado de servidor com o nome DNS completamente qualificado do servidor virtual em todos os nós no cluster de failover. Por exemplo, se você tiver um cluster de dois nós, com os nós chamados test1.*\<your company>*.com e test2.*\<your company>*.com e um servidor virtual chamado virtsql, precisará instalar um certificado para virtsql.*\<your company>*.com em ambos os nós. É possível definir o valor da opção **ForceEncryption** como **Sim**.  

> [!NOTE]
> Ao criar conexões criptografadas para um indexador do Azure Search para o SQL Server em uma VM do Azure, consulte [Configurar uma conexão de um indexador do Azure Search para SQL Server em uma VM do Azure](https://azure.microsoft.com/documentation/articles/search-howto-connecting-azure-sql-iaas-to-azure-search-using-indexers/). 
  
 
##  <a name="Provision"></a> Para instalar um certificado no servidor  

>[!NOTE]
>Consulte [Gerenciamento de certificado (SQL Server Configuration Manager)](https://docs.microsoft.com/sql/database-engine/configure-windows/manage-certificates.md) para adicionar um certificado em um único servidor.
  
1.  No menu **Iniciar** , clique em **Executar**e na caixa **Abrir** , digite **MMC** e clique em **OK**.  
  
2.  No console do MMC, no menu **Arquivo** , clique em **Adicionar/Remover Snap-in**.  
  
3.  Na caixa de diálogo **Adicionar/Remover Snap-in** , clique em **Adicionar**.  
  
4.  Na caixa de diálogo **Adicionar Snap-in Autônomo** , clique em **Certificados**e em **Adicionar**.  
  
5.  Na caixa de diálogo **Snap-in de certificados** , clique em **Conta de computador**e em **Concluir**.  
  
6.  Na caixa de diálogo **Adicionar Snap-in Autônomo** , clique em **Fechar.**  
  
7.  Na caixa de diálogo **Adicionar/Remover Snap-in** , clique em **OK**.  
  
8.  No snap-in de **Certificados** , expanda **Certificados**, expanda **Pessoal**, clique com o botão direito do mouse em **Certificados**, aponte para **Todas as Tarefas**e clique em **Importar**.  

9. Clique com o botão direito do mouse no certificado importado, aponte para **Todas as Tarefas**e clique em **Gerenciar Chaves Privadas**. Na caixa de diálogo **Segurança** , adicione a permissão de leitura para a conta de usuário usada pela conta de serviço do SQL Server.  
  
10. Complete o **Assistente para Importação de Certificados**, para adicionar um certificado ao computador e feche o console MMC. Para obter mais informações sobre como adicionar um certificado a um computador, consulte sua documentação do Windows.  
  
## <a name="to-provision-install-a-certificate-across-multiple-servers"></a>Para provisionar (instalar) um certificado em vários servidores

Consulte [Gerenciamento de certificado (SQL Server Configuration Manager)](https://docs.microsoft.com/sql/database-engine/configure-windows/manage-certificates.md) para adicionar um certificado entre vários servidores.

##  <a name="Export"></a> Para exportar o certificado de servidor  
  
1.  No snap-in de **Certificados** , localize o certificado na pasta **Certificados** / **Pessoal** , clique com o botão direito do mouse em **Certificado**, aponte para **Todas as Tarefas**e clique em **Exportar**.  
  
2.  Complete o **Assistente para Exportação de Certificados**armazenando o arquivo de certificado em um local conveniente.  
  
##  <a name="ConfigureServerConnections"></a> Para configurar o servidor para forçar conexões criptografadas  
  
1.  No **SQL Server Configuration Manager**, expanda **Configuração de Rede do SQL Server**, clique com o botão direito do mouse em **Protocolos de** _\<server instance>_ e, depois, selecione **Propriedades**.  
  
2.  Na caixa de diálogo **Propriedades** de **Protocolos de**  _\<instance name>_, na guia **Certificado**, selecione o certificado desejado na lista suspensa da caixa **Certificado** e, depois, clique em **OK**.  
  
3.  Na guia **Sinalizadores** , na caixa **ForceEncryption** , selecione **Sim**e clique em **OK** para fechar a caixa de diálogo.  
  
4.  Reinicie o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  


> [!NOTE]
> Para garantir a conectividade segura entre o cliente e o servidor, configure o cliente para solicitar conexões criptografadas. Mais detalhes são explicados [mais adiante neste artigo](#client-request-encrypt-connect-23h).

### <a name="wildcard-certificates"></a>Certificados curinga  
A partir do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2008, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client dão suporte a certificados curinga. Outros clientes podem não dar suporte a certificados curinga. Para obter mais informações, consulte a documentação do cliente. O certificado curinga não pode ser selecionado usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager. Para usar um certificado curinga, é necessário editar a chave do Registro `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQLServer\SuperSocketNetLib` e inserir a impressão digital do certificado, sem espaços, no valor **Certificado**.  

> [!WARNING]  
> [!INCLUDE[ssnoteregistry_md](../../includes/ssnoteregistry-md.md)]  

<a name="client-request-encrypt-connect-23h"/></a>

## <a name="ConfigureClientConnections"></a> Para configurar o cliente para solicitar conexões criptografadas  
  
1.  Copie o certificado original ou o arquivo de certificado exportado no computador cliente.  
  
2.  No computador cliente, use o snap-in de **Certificados** para instalar o certificado raiz ou o arquivo do certificado exportado.  
  
3.  No painel de console, clique com o botão direito do mouse em **Configuração do SQL Server Native Client**e clique em **Propriedades**.  
  
4.  Na página **Sinalizadores** , na caixa **Forçar criptografia de protocolo** , clique em **Sim**.  
  
## <a name="EncryptConnection"></a> Para criptografar uma conexão do SQL Server Management Studio  
  
1.  Na barra de ferramentas do Pesquisador de Objetos, clique em **Conectar**e clique em **Mecanismo de Banco de Dados**.  
  
2.  Na caixa de diálogo **Conectar ao Servidor** , complete as informações de conexão e clique em **Opções**.  
  
3.  Na guia **Propriedades de Conexão** , clique em **Criptografar conexão**.  
  
## <a name="see-also"></a>Consulte Também

[Suporte a TLS 1.2 para o Microsoft SQL Server](https://support.microsoft.com/kb/3135244)  

