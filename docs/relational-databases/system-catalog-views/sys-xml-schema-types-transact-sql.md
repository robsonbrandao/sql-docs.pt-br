---
title: sys.xml_schema_types (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.xml_schema_types_TSQL
- xml_schema_types_TSQL
- sys.xml_schema_types
- xml_schema_types
dev_langs:
- TSQL
helpviewer_keywords:
- sys.xml_schema_types catalog view
ms.assetid: 441ba49d-f778-4fa1-98c4-ced375a01a34
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: ea20d8e326d006e1a405adffcf73fae6ca1e4473
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47715945"
---
# <a name="sysxmlschematypes-transact-sql"></a>sys.xml_schema_types (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retorna uma linha por componente de esquema XML que é um tipo **symbol_space** dos **T**.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**\<herdado colunas >**||Herda colunas de [xml_schema_components](../../relational-databases/system-catalog-views/sys-xml-schema-components-transact-sql.md).|  
|**is_abstract**|**bit**|1 = O tipo é abstrato. Todas as instâncias de um elemento desse tipo devem usar **xsi: Type** para indicar um tipo derivado que não é abstrato.<br /><br /> 0 = O tipo não é abstrato. (padrão)|  
|**allows_mixed_content**|**bit**|1 = É permitido conteúdo misturado<br /><br /> 0 = Não é permitido conteúdo misturado (padrão)|  
|**is_extension_blocked**|**bit**|1 = substituição com uma extensão do tipo está bloqueada nas instâncias quando o bloco de atributo de **complexType** definição ou o **blockDefault** atributo do ancestral \<esquema > item de informação do elemento é definido como "extension" ou "#all".<br /><br /> 0 = A substituição pela extensão não está bloqueada.|  
|**is_restriction_blocked**|**bit**|1 = substituição com uma restrição de tipo está bloqueada nas instâncias quando o bloco de atributo de **complexType** definição ou o **blockDefault** atributo do ancestral \<esquema > item de informação do elemento é definido como "restriction" ou "#all".<br /><br /> 0 = A substituição pela restrição não está bloqueada. (padrão)|  
|**is_final_extension**|**bit**|1 = a derivação pela extensão do tipo é bloqueada quando o atributo final na **complexType** definição ou o **finalDefault** atributo do ancestral \<esquema > informações sobre o elemento item é definido como "extension" ou "#all".<br /><br /> 0 = A extensão é permitida. (padrão)|  
|**is_final_restriction**|**bit**|1 = a derivação por restrição do tipo é bloqueada quando o atributo final em simples ou **complexType** definição ou o **finalDefault** atributo do ancestral \<esquema > elemento item de informação é definido como "restriction" ou "#all".<br /><br /> 0 = A restrição é permitida. (padrão)|  
|**is_final_list_member**|**bit**|1 = Esse tipo simples não pode ser usado como o tipo de item em uma lista.<br /><br /> 0 = Esse é um tipo complexo ou pode ser usado como tipo de item de lista. (padrão)|  
|**is_final_union_member**|**bit**|1 = Esse tipo simples não pode ser usado como o tipo de membro de um tipo de união.<br /><br /> 0 = É um tipo complexo ou pode ser usado como tipo de membro de união. (padrão)|  
  
## <a name="permissions"></a>Permissões  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Para obter mais informações, consulte [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Consulte também  
 [Exibições de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Esquemas XML &#40;sistema de tipo XML&#41; exibições do catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/xml-schemas-xml-type-system-catalog-views-transact-sql.md)  
  
  
