---
title: Objeto CubeDef (ADO MD) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- CubeDef
helpviewer_keywords:
- CubeDef object [ADO MD]
ms.assetid: feb2581c-fc41-471c-bb69-29f8a55fda70
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d1027fc76cb09f7b846e1b8edad52a3cb5dbf2bc
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47694046"
---
# <a name="cubedef-object-ado-md"></a>Objeto CubeDef (ADO MD)
Representa um cubo de um esquema multidimensional, que contém um conjunto de dimensões relacionadas.  
  
## <a name="remarks"></a>Comentários  
 Com as coleções e propriedades de um **CubeDef** do objeto, você pode fazer o seguinte:  
  
-   Identificar uma **CubeDef** com o [nome](../../../ado/reference/ado-md-api/name-property-ado-md.md) propriedade.  
  
-   Retornar uma cadeia de caracteres que descreve o cubo com o [descrição](../../../ado/reference/ado-md-api/description-property-ado-md.md) propriedade.  
  
-   Retornar as dimensões que compõem o cubo com o [dimensões](../../../ado/reference/ado-md-api/dimensions-collection-ado-md.md) coleção.  
  
-   Obter informações adicionais sobre o **CubeDef** com o padrão ADO [propriedades](../../../ado/reference/ado-api/properties-collection-ado.md) coleção.  
  
 O **propriedades** coleção contém propriedades fornecidos pelo provedor. A tabela a seguir lista as propriedades que podem estar disponíveis. A lista de propriedades reais pode diferir dependendo após a implementação do provedor. Consulte a documentação do seu provedor para obter uma lista completa de propriedades disponíveis.  
  
|Nome|Description|  
|----------|-----------------|  
|CatalogName|O nome do catálogo ao qual pertence este cubo.|  
|CreatedOn|Data e hora da criação do cubo.|  
|CubeGUID|GUID do cubo.|  
|CubeName|O nome do cubo.|  
|CubeType|O tipo do cubo.|  
|DataUpdatedBy|ID de usuário da pessoa que faz a última atualização de dados.|  
|Description|Uma descrição significativa do cubo.|  
|LastSchemaUpdate|Data e hora da última atualização de esquema.|  
|SchemaName|O nome do esquema ao qual pertence este cubo.|  
|SchemaUpdatedBy|ID de usuário da pessoa que faz a última atualização de esquema.|  
  
 Esta seção contém o tópico a seguir.  
  
-   [Propriedades, métodos e eventos](../../../ado/reference/ado-md-api/cubedef-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo CubeDef (VBScript)](../../../ado/reference/ado-md-api/cubedef-example-vbscript.md)   
 [Objeto de catálogo (ADO MD)](../../../ado/reference/ado-md-api/catalog-object-ado-md.md)   
 [Coleção CubeDefs (ADO MD)](../../../ado/reference/ado-md-api/cubedefs-collection-ado-md.md)   
 [Coleção de dimensões (ADO MD)](../../../ado/reference/ado-md-api/dimensions-collection-ado-md.md)   
 [Coleção Properties (ADO)](../../../ado/reference/ado-api/properties-collection-ado.md)
