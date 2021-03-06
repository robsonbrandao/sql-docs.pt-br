---
title: CREATE EVENT SESSION (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- CREATE EVENT SESSION
- SESSION
- EVENT SESSION
- SESSION_TSQL
- EVENT_SESSION_TSQL
- CREATE_EVENT_SESSION_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- event sessions [SQL Server]
- CREATE EVENT SESSION statement
ms.assetid: 67683027-2b0f-47aa-b223-604731af8b4d
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: c2335efbd97872975fd6779081e7a5a693266e02
ms.sourcegitcommit: a192814756570bcbce3b1dbbb05acb24a79d1530
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54457669"
---
# <a name="create-event-session-transact-sql"></a>CREATE EVENT SESSION (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Cria uma sessão de Eventos Estendidos que identifica a origem dos eventos, os destinos da sessão de evento e as opções da sessão de evento.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md).  
  
## <a name="syntax"></a>Sintaxe  
  
```    
CREATE EVENT SESSION event_session_name  
ON SERVER  
{  
    <event_definition> [ ,...n]  
    [ <event_target_definition> [ ,...n] ]  
    [ WITH ( <event_session_options> [ ,...n] ) ]  
}  
;  
  
<event_definition>::=  
{  
    ADD EVENT [event_module_guid].event_package_name.event_name   
         [ ( {   
                 [ SET { event_customizable_attribute = <value> [ ,...n] } ]  
                 [ ACTION ( { [event_module_guid].event_package_name.action_name [ ,...n] } ) ]  
                 [ WHERE <predicate_expression> ]  
        } ) ]  
}  
  
<predicate_expression> ::=   
{  
    [ NOT ] <predicate_factor> | {( <predicate_expression> ) }   
    [ { AND | OR } [ NOT ] { <predicate_factor> | ( <predicate_expression> ) } ]   
    [ ,...n ]  
}  
  
<predicate_factor>::=   
{  
    <predicate_leaf> | ( <predicate_expression> )  
}  
  
<predicate_leaf>::=  
{  
      <predicate_source_declaration> { = | < > | ! = | > | > = | < | < = } <value>   
    | [event_module_guid].event_package_name.predicate_compare_name ( <predicate_source_declaration>, <value> )   
}  
  
<predicate_source_declaration>::=   
{  
    event_field_name | ( [event_module_guid].event_package_name.predicate_source_name )  
}  
  
<value>::=   
{  
    number | 'string'  
}  
  
<event_target_definition>::=  
{  
    ADD TARGET [event_module_guid].event_package_name.target_name  
        [ ( SET { target_parameter_name = <value> [ ,...n] } ) ]  
}  
  
<event_session_options>::=  
{  
    [    MAX_MEMORY = size [ KB | MB ] ]  
    [ [,] EVENT_RETENTION_MODE = { ALLOW_SINGLE_EVENT_LOSS | ALLOW_MULTIPLE_EVENT_LOSS | NO_EVENT_LOSS } ]  
    [ [,] MAX_DISPATCH_LATENCY = { seconds SECONDS | INFINITE } ]  
    [ [,] MAX_EVENT_SIZE = size [ KB | MB ] ]  
    [ [,] MEMORY_PARTITION_MODE = { NONE | PER_NODE | PER_CPU } ]  
    [ [,] TRACK_CAUSALITY = { ON | OFF } ]  
    [ [,] STARTUP_STATE = { ON | OFF } ]  
}  
```  
  
## <a name="arguments"></a>Argumentos  
 *event_session_name*  
 É o nome definido pelo usuário para a sessão de evento. *event_session_name* é alfanumérico, pode ter até 128 caracteres, deve ser exclusivo em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e deve obedecer às regras de [Identificadores](../../relational-databases/databases/database-identifiers.md).  
  
 ADD EVENT [ *event_module_guid* ].*event_package_name*.*event_name*  
 É o evento a ser associado com a sessão de evento, onde:  
  
-   *event_module_guid* é o GUID do módulo que contém o evento.  
  
-   *event_package_name* é o pacote que contém o objeto de ação.  
  
-   *event_name* é o objeto de evento.  
  
 Eventos aparecem na exibição sys.dm_xe_objects como object_type “evento”.  
  
 SET { *event_customizable_attribute*= \<value> [ ,...*n*] }  
 Permite atributos personalizáveis para o evento a ser definido. Os atributos personalizáveis são mostrados na exibição sys.dm_xe_object_columns como column_type 'personalizável' e object_name = *event_name*.  
  
 ACTION ( { [*event_module_guid*].*event_package_name*.*action_name* [ **,**...*n*] })  
 É a ação a ser associada à sessão de evento, onde:  
  
-   *event_module_guid* é o GUID do módulo que contém o evento.  
  
-   *event_package_name* é o pacote que contém o objeto de ação.  
  
-   *action_name* é o objeto de ação.  
  
 Ações aparecem na exibição sys.dm_xe_objects como object_type “ação”.  
  
 WHERE \<predicate_expression> Especifica a expressão de predicado usada para determinar se um evento deve ser processado. Se \<predicate_expression> for verdadeira, o evento será processado mais detalhadamente pelas ações e pelos destinos da sessão. Se \<predicate_expression> for falsa, o evento será removido pela sessão antes de ser processado pelas ações e pelos destinos da sessão. As expressões de predicado são limitadas a 3.000 caracteres, o que limita os argumentos de cadeia de caracteres. 
  
 *event_field_name*  
 É o nome do campo de evento que identifica a origem do predicado.  
  
 [*event_module_guid*].*event_package_name*.*predicate_source_name*  
 É o nome da origem do predicado global onde:  
  
-   *event_module_guid* é o GUID do módulo que contém o evento.  
  
-   *event_package_name* é o pacote que contém o objeto de predicado.  
  
-   *predicate_source_name* é definido na exibição sys.dm_xe_objects como object_type 'pred_source'.  
  
 [*event_module_guid*].*event_package_name*.*predicate_compare_name*  
 É o nome do objeto de predicado a ser associado à sessão de evento, onde:  
  
-   *event_module_guid* é o GUID do módulo que contém o evento.  
  
-   *event_package_name* é o pacote que contém o objeto de predicado.  
  
-   *predicate_compare_name* é uma origem global definida na exibição sys.dm_xe_objects como object_type 'pred_compare'.  
  
 *number*  
 É qualquer tipo numérico, incluindo **decimal**. Limitações são a falta de memória física disponível ou um número que é muito grande para ser representado como um inteiro de 64 bits.  
  
 '*string*'  
 Uma cadeia de caracteres ANSI ou Unicode, conforme requerido pela comparação de predicado. Nenhuma conversão de tipo de cadeia de caracteres implícita é executada para as funções de comparação de predicado. A transferência do tipo incorreto resulta em um erro.  
  
 ADD TARGET [*event_module_guid*].*event_package_name*.*target_name*  
 É o destino a ser associado à sessão de evento, onde:  
  
-   *event_module_guid* é o GUID do módulo que contém o evento.  
  
-   *event_package_name* é o pacote que contém o objeto de ação.  
  
-   *target_name* é o destino. Os destinos aparecem na exibição sys.dm_xe_objects como object_type ‘destino’.  
  
 SET { *target_parameter_name*= \<value> [, ...*n*] }  
 Define um parâmetro de destino. Os parâmetros de destino são mostrados na exibição sys.dm_xe_object_columns como column_type 'personalizável' e object_name = *target_name*.  
  
> [!IMPORTANT]  
>  Se você estiver usando o destino de buffer de anel, recomendamos definir o parâmetro de destino max_memory como 2.048 KB (kilobytes) para ajudar a evitar um possível truncamento de dados da saída XML. Para obter mais informações sobre como usar os diferentes tipos de destino, consulte [Destinos de eventos estendidos do SQL Server](https://msdn.microsoft.com/library/e281684c-40d1-4cf9-a0d4-7ea1ecffa384).  
  
 WITH ( \<event_session_options> [ ,...*n*] ) Especifica as opções a serem usadas com a sessão de evento.  
  
 MAX_MEMORY =*size* [ KB | **MB** ]  
 Especifica a quantidade máxima de memória a ser alocada à sessão para buffer de evento. O padrão é 4 MB. *size* é um número inteiro e pode ser um valor de KB (kilobyte) ou MB (megabyte). A quantidade máxima não pode exceder 2 GB (menos de 2048 MB). No entanto, não é recomendável usar valores de memória na faixa de GB.
  
 EVENT_RETENTION_MODE = { **ALLOW_SINGLE_EVENT_LOSS** | ALLOW_MULTIPLE_EVENT_LOSS | NO_EVENT_LOSS }  
 Especifica o modo de retenção do evento para usar em tratamento de perda de evento.  
  
 **ALLOW_SINGLE_EVENT_LOSS**  
 Um evento pode ser perdido da sessão. Um único evento será descartado somente quando todos os buffers de evento estiverem cheios. A perda de um único evento quando os buffers de evento estão cheios permite características de desempenho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aceitáveis, enquanto minimiza a perda de dados no fluxo de evento processado.  
  
 ALLOW_MULTIPLE_EVENT_LOSS  
 Buffers de evento cheios que contêm vários eventos podem ser perdidos da sessão. A quantidade de eventos perdidos depende do tamanho de memória alocado à sessão, do particionamento da memória e do tamanho dos eventos no buffer. Essa opção minimiza o impacto do desempenho no servidor quando buffers de evento são rapidamente enchidos, mas grandes números de eventos podem ser perdidos da sessão.  
  
 NO_EVENT_LOSS  
 Nenhuma perda de evento é permitida. Essa opção assegura que todos os eventos gerados sejam retidos. O uso dessa opção força todas as tarefas que acionam eventos a esperar até que haja espaço disponível em um buffer de evento. Isso pode causar problemas de desempenho detectáveis enquanto a sessão de evento está ativa. As conexões de usuário poderão parar enquanto esperam a liberação de eventos do buffer.  
  
 MAX_DISPATCH_LATENCY = { *seconds* SECONDS | **INFINITE** }  
 Especifica a quantidade de tempo em que haverá buffer de eventos na memória antes que sejam enviados para destinos de sessão de evento. Por padrão, este valor é definido como 30 segundos.  
  
 *seconds* SECONDS  
 O tempo, em segundos, a esperar antes de liberar buffers para os destinos. *seconds* é um número inteiro. O valor mínimo de latência é 1 segundo. No entanto, o valor 0 pode ser usado para especificar a latência INFINITE.  
  
 **INFINITE**  
 Libera buffers para os destinos somente quando eles estão cheios ou quando a sessão de evento é fechada.  
  
> [!NOTE]  
>  MAX_DISPATCH_LATENCY = 0 SECONDS é equivalente a MAX_DISPATCH_LATENCY = INFINITE.  
  
 MAX_EVENT_SIZE =*size* [ KB | **MB** ]  
 Especifica o tamanho máximo permitido para eventos. MAX_EVENT_SIZE deverá ser definido apenas para permitir eventos únicos maiores que MAX_MEMORY; sua definição como menos que MAX_MEMORY irá gerar um erro. *size* é um número inteiro e pode ser um valor de KB (kilobyte) ou MB (megabyte). Se *size* for especificado em kilobytes, o tamanho mínimo permitido será de 64 KB. Quando MAX_EVENT_SIZE é definido, dois buffers de *size* são criados, além de MAX_MEMORY. Isso significa que a memória total usada para buffer de evento é MAX_MEMORY + 2 * MAX_EVENT_SIZE.  
  
 MEMORY_PARTITION_MODE = { **NONE** | PER_NODE | PER_CPU }  
 Especifica o local onde buffers de evento são criados.  
  
 **NONE**  
 Um único conjunto de buffers é criado na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 PER_NODE  
 Um conjunto de buffers é criado para cada nó NUMA.  
  
 PER_CPU  
 Um conjunto de buffers é criado para cada CPU.  
  
 TRACK_CAUSALITY = { ON | **OFF** }  
 Especifica se a causalidade deve ou não ser controlada. Se habilitada, a causalidade permitirá que eventos relacionados em conexões de servidor diferentes sejam correlacionados.  
  
 STARTUP_STATE = { ON | **OFF** }  
 Especifica se essa sessão de evento deve ser iniciada automaticamente quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inicia.  
  
> [!NOTE]  
> Se `STARTUP_STATE = ON`, a sessão de evento somente será iniciada se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for parado e, em seguida, reiniciado.  
  
 ON  
 A sessão de evento é iniciada na inicialização.  
  
 **OFF**  
 A sessão de evento não é iniciada na inicialização.  
  
## <a name="remarks"></a>Remarks  
A ordem de precedência para operadores lógicos é `NOT` (mais alto), seguido por `AND`, seguido por `OR`.  
  
## <a name="permissions"></a>Permissões  
Requer a permissão `ALTER ANY EVENT SESSION`.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir mostra como criar uma sessão de evento denominada `test_session`. Esse exemplo adiciona dois eventos e usa o destino Rastreamento de Eventos do Windows.  
  
```sql  
IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='test_session')  
    DROP EVENT session test_session ON SERVER;  
GO  
CREATE EVENT SESSION test_session  
ON SERVER  
    ADD EVENT sqlos.async_io_requested,  
    ADD EVENT sqlserver.lock_acquired  
    ADD TARGET package0.etw_classic_sync_target   
        (SET default_etw_session_logfile_path = N'C:\demo\traces\sqletw.etl' )  
    WITH (MAX_MEMORY=4MB, MAX_EVENT_SIZE=4MB);  
GO  
```  
  
## <a name="see-also"></a>Consulte Também  
 [ALTER EVENT SESSION &#40;Transact-SQL&#41;](../../t-sql/statements/alter-event-session-transact-sql.md)   
 [DROP EVENT SESSION &#40;Transact-SQL&#41;](../../t-sql/statements/drop-event-session-transact-sql.md)   
 [sys.server_event_sessions &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-server-event-sessions-transact-sql.md)   
 [sys.dm_xe_objects &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql.md)   
 [sys.dm_xe_object_columns &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-xe-object-columns-transact-sql.md)  
  
  

