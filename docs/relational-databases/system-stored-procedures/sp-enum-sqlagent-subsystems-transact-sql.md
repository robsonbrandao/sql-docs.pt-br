---
title: sp_enum_sqlagent_subsystems (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_enum_sqlagent_subsystems
- sp_enum_sqlagent_subsystems_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_enum_sqlagent_subsystems
ms.assetid: 019a3c9d-bac3-495b-a70a-2c19f1d2e20e
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 5aac3e1471f969ea324008c03f97b9b26c05c4ec
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47790204"
---
# <a name="spenumsqlagentsubsystems-transact-sql"></a>sp_enum_sqlagent_subsystems (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Lista os subsistemas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_enum_sqlagent_subsystems  
```  
  
## <a name="arguments"></a>Argumentos  
 None  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**subsystem**|**nvarchar(40)**|Nome do subsistema.|  
|**Descrição**|**nvarchar(512)**|Descrição do subsistema.|  
|**subsystem_dll**|**nvarchar(510)**|Módulo DLL que contém o subsistema.|  
|**agent_exe**|**nvarchar(510)**|Módulo executável usado pelo subsistema.|  
|**start_entry_point**|**nvarchar(30)**|Procedimento que o SQL Server Agent chama durante a execução da etapa de trabalho.|  
|**event_entry_point**|**nvarchar(30)**|Procedimento que o SQL Server Agent chama durante a execução da etapa de trabalho.|  
|**stop_entry_point**|**nvarchar(30)**|Procedimento que o SQL Server Agent chama durante a execução da etapa de trabalho.|  
|**max_worker_threads**|**int**|Número de máximo de threads que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent iniciará para este subsistema.|  
|**subsystem_id**|**int**|Identificador do subsistema.|  
  
## <a name="remarks"></a>Comentários  
 Este procedimento lista os subsistemas disponíveis na instância.  
  
## <a name="permissions"></a>Permissões  
 Por padrão, os membros da função de servidor fixa **sysadmin** podem executar este procedimento armazenado. Deve ser concedida a outros usuários a função de banco de dados fixa **SQLAgentOperatorRole** no banco de dados **msdb** .  
  
 Para obter detalhes sobre **SQLAgentOperatorRole**, consulte [funções de banco de dados fixas do SQL Server Agent](../../ssms/agent/sql-server-agent-fixed-database-roles.md).  
  
## <a name="see-also"></a>Consulte também  
 [Implementar a segurança do SQL Server Agent](../../ssms/agent/implement-sql-server-agent-security.md)   
 [sp_add_jobstep &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql.md)  
  
  
