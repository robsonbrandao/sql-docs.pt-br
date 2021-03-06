---
title: sp_helpfilegroup (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_helpfilegroup_TSQL
- sp_helpfilegroup
dev_langs:
- TSQL
helpviewer_keywords:
- sp_helpfilegroup
ms.assetid: 619716b5-95dc-4538-82ae-4b90b9da8ebc
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 1d6e7c28e628254fd33269ab4ee200fee0067870
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47741044"
---
# <a name="sphelpfilegroup-transact-sql"></a>sp_helpfilegroup (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retorna os nomes e os atributos de grupos de arquivos associados ao banco de dados atual.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_helpfilegroup [ [ @filegroupname = ] 'name' ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@filegroupname =** ] **'***nome***'**  
 É o nome lógico de qualquer grupo de arquivos no banco de dados atual. *nome da* está **sysname**, com um padrão NULL. Se *nome* não for especificado, todos os grupos de arquivos no banco de dados atual são listados e somente o primeiro conjunto de resultados mostrado na seção conjuntos de resultados é exibido.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 0 (êxito) ou 1 (falha)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**groupname**|**sysname**|Nome do grupo de arquivos.|  
|**groupid**|**smallint**|Identificador de grupo de arquivos numérico.|  
|**filecount**|**int**|Número de arquivos no grupo de arquivos.|  
  
 Se *nome* é uma linha para cada arquivo no grupo de arquivos especificado, será retornada.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**file_in_group**|**sysname**|Nome lógico do arquivo no grupo de arquivos.|  
|**fileid**|**smallint**|Identificador de arquivos numérico.|  
|**filename**|**nchar(260)**|O nome  físico do arquivo que inclui o caminho de diretório.|  
|**size**|**nvarchar(15)**|Tamanho do arquivo em kilobytes.|  
|**tamanho máximo**|**nvarchar(15)**|Tamanho máximo do arquivo.<br /><br /> É o tamanho máximo até o qual o arquivo pode crescer. Um valor UNLIMITED neste campo indica que o arquivo cresce até o disco ficar cheio.|  
|**growth**|**nvarchar(15)**|Incremento de crescimento do arquivo. Isso indica a quantidade de espaço adicionada ao arquivo sempre que um novo espaço é necessário.<br /><br /> 0 = Arquivo tem um tamanho fixo e não crescerá.|  
  
## <a name="permissions"></a>Permissões  
 Requer associação à função **pública** .  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-returning-all-filegroups-in-a-database"></a>A. Retornando todos os grupos de arquivos de um banco de dados  
 O exemplo a seguir retorna informações sobre os grupos de arquivos no banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_helpfilegroup;  
GO  
```  
  
### <a name="b-returning-all-files-in-a-filegroup"></a>B. Retornando todos os arquivos de um grupo de arquivos  
 O exemplo a seguir retorna informações para todos os arquivos no grupo de arquivos `PRIMARY` do banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_helpfilegroup 'PRIMARY';  
GO  
```  
  
## <a name="see-also"></a>Consulte também  
 [Procedimentos armazenados do mecanismo de banco de dados &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/database-engine-stored-procedures-transact-sql.md)   
 [sp_helpfile &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-helpfile-transact-sql.md)   
 [sys.database_files &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-database-files-transact-sql.md)   
 [sys.master_files &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-master-files-transact-sql.md)   
 [sys.filegroups &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-filegroups-transact-sql.md)   
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [Arquivos e grupos de arquivos do banco de dados](../../relational-databases/databases/database-files-and-filegroups.md)  
  
  
