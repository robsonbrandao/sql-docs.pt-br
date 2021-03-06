---
title: dbo.sysdac_instances (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dbo.sysdac_instances_TSQL
- sysdac_instances
- sysdac_instances_TSQL
- dbo.sysdac_instances
dev_langs:
- TSQL
helpviewer_keywords:
- dbo.sysdac_instances
- sysdac_instances
ms.assetid: 28285f3d-3889-439f-8b24-3bdef08e46b4
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 049f3d0201957cfee5d7bc88301c6af97c0b6dcb
ms.sourcegitcommit: 9c6a37175296144464ffea815f371c024fce7032
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51660676"
---
# <a name="data-tier-application-views---dbosysdacinstances"></a>Exibições de aplicativo da camada de dados - dbo.sysdac_instances
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

  Exibe uma linha para cada instância do DAC (Aplicativo da Camada de Dados) implantada a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)]. sysdac_instances pertence ao esquema dbo no banco de dados msdb. A tabela a seguir descreve as colunas na exibição de sysdac_instances.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|instance_id|**uniqueidentifier**|Identificador da instância do DAC.|  
|instance_name|**sysname**|Nome da instância do DAC especificada quando o DAC foi implantado.|  
|type_name|**sysname**|Nome do DAC especificado quando o pacote do DAC foi criado.|  
|type_version|**nvarchar(64)**|Versão do DAC especificado quando o pacote do DAC foi criado.|  
|descrição|**nvarchar(4000)**|Uma descrição do DAC escrita quando o pacote do DAC foi criado.|  
|type_stream|**varbinary(max)**|Fluxo que contém uma representação codificada dos objetos lógicos, como tabelas e exibições, contidos no DAC.|  
|date_created|**datetime**|Data e hora em que a instância do DAC foi criada.|  
|created_by|**sysname**|Logon que criou a instância do DAC.|  
|database_name|**sysname**|Nome do banco de dados criado para a instância do DAC.|  
  
## <a name="remarks"></a>Comentários  
 Um DAC inclui um tipo de DAC que é uma definição dos objetos da camada de dados lógicos usados por um aplicativo, como tabelas e exibições. Um pacote do DAC é um arquivo usado para implantar um DAC. O pacote do DAC contém uma representação de todos os objetos lógicos contidos no tipo do DAC. O pacote do DAC pode ser usado para implantar uma ou mais cópias, ou instâncias, do DAC em uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)]. Cada instância do DAC implantada a partir do mesmo pacote do DAC compartilha o mesmo tipo, mas é atribuída a um nome e identificador de instância exclusivos.  
  
## <a name="permissions"></a>Permissões  
 Requer associação na função de servidor fixa sysadmin para exibir todas as colunas. Os membros da função pública podem exibir as colunas instance_name, description e type_version.  
  
## <a name="see-also"></a>Consulte também  
 [Aplicativos da Camada de Dados](../../relational-databases/data-tier-applications/data-tier-applications.md)   
 [Exibições de aplicativo da camada de dados &#40;Transact-SQL&#41;](https://msdn.microsoft.com/library/0de01328-d7a6-4677-b7a0-dcd3098c23d4)  
  
  
