---
title: sys.dm_xe_object_columns (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_xe_object_columns
- sys.dm_xe_object_columns_TSQL
- dm_xe_object_columns_TSQL
- dm_xe_object_columns
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_xe_object_columns dynamic management view
- extended events [SQL Server], views
ms.assetid: d96a14f3-4284-45ff-b1fe-4858e540a013
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 21b97ab3eaae8399fbc0bf37905b2b61b608948c
ms.sourcegitcommit: f46fd79fd32a894c8174a5cb246d9d34db75e5df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/26/2018
ms.locfileid: "53785777"
---
# <a name="sysdmxeobjectcolumns-transact-sql"></a>sys.dm_xe_object_columns (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retorna as informações de esquema de todos os objetos.  
  
> [!NOTE]  
>  Os objetos de evento expõem esquemas fixos para dados somente leitura e de leitura e gravação.  
  
|Nome da coluna|Tipo de dados|Descrição|  
|-----------------|---------------|-----------------|  
|nome|**nvarchar(256)**|O nome da coluna. nome é exclusivo dentro do objeto. Não permite valor nulo.|  
|column_id|**int**|O identificador da coluna. column_id é exclusivo dentro do objeto quando usado com column_type. Não permite valor nulo.|  
|object_name|**nvarchar(256)**|O nome do objeto ao qual a coluna pertence. Há uma relação muitos para um com sys.dm_xe_packages.package_id. Não permite valor nulo.|  
|object_package_guid|**uniqueidentifier**|O GUID do pacote que contém o objeto. Não permite valor nulo.|  
|type_name|**nvarchar(256)**|O nome do tipo desta coluna. Não permite valor nulo.|  
|type_package_guid|**uniqueidentifier**|O GUID do pacote que contém o tipo de dados de coluna. Não permite valor nulo.|  
|column_type|**nvarchar(60)**|Indica como essa coluna é usada. Não permite valor nulo. column_type pode ser uma das seguintes opções:<br /><br /> readonly. A coluna contém um valor estático que não pode ser alterado.<br /><br /> data. A coluna contém dados de tempo de execução mostrados pelo objeto.<br /><br /> customizable. A coluna contém um valor que pode ser alterado.<br /><br /> Observação: Alterar este valor pode modificar o comportamento do objeto.|  
|column_value|**nvarchar(256)**|Exibe valores estáticos associados à coluna de objeto. Permite valor nulo.|  
|funcionalidades|**int**|Um bitmap que descreve as capacidades desta coluna. Permite valor nulo.|  
|capabilities_desc|**nvarchar(256)**|Uma descrição dos recursos desta coluna de objeto. Este valor pode ser um dos seguintes:<br /><br /> Mandatory. O valor deve ser definido ao associar o objeto pai a uma sessão de evento.<br /><br /> Permite valor nulo.|  
|descrição|**nvarchar(3072)**|A descrição desta coluna de objeto. Permite valor nulo.|  
  
## <a name="permissions"></a>Permissões  
 , é necessário ter permissão VIEW SERVER STATE no servidor.  
  
### <a name="relationship-cardinalities"></a>Cardinalidades de relações  
  
|De|Para|Relação|  
|----------|--------|------------------|  
|sys.dm_xe_object_columns.object_name, sys.dm_xe_object_columns.object_package_guid|sys.dm_xe_objects.name,<br /><br /> sys.dm_xe_objects.package_guid|Muitos para um|  
|sys.dm_xe_object_columns.type_name<br /><br /> sys.dm_xe_object_columns.type_package_guid|sys.dm_xe_objects.name<br /><br /> sys.dm_xe_objects.package_guid|Muitos para um|  
  
## <a name="see-also"></a>Consulte também  
 [Exibições e funções de gerenciamento dinâmico &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)  
  
  

