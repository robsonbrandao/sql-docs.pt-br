---
title: Propriedade DataMember | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset20::DataMember
helpviewer_keywords:
- DataMember property
ms.assetid: 2c8fb09e-10ad-49b5-ab41-2603771780d9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: b7a1bb2d55fbf4e8d2030c612a1d000b93ca1110
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47603704"
---
# <a name="datamember-property"></a>Propriedade DataMember
Indica o nome do membro de dados que será recuperado do [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md) referenciado pelo [DataSource](../../../ado/reference/ado-api/datasource-property-ado.md) propriedade.  
  
## <a name="settings-and-return-values"></a>As configurações e valores de retorno  
 Define ou retorna um **cadeia de caracteres** valor. O nome não diferencia maiusculas de minúsculas.  
  
## <a name="remarks"></a>Comentários  
 Essa propriedade é usada para criar controles associados a dados com o ambiente de dados. O ambiente de dados mantém a chamada de coleções de dados (fontes de dados) que contém objetos (membros de dados) que serão representados como uma [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) objeto.  
  
 O **DataMember** e **DataSource** propriedades devem ser usadas juntas.  
  
 O **DataMember** propriedade determina qual objeto especificado pelo **DataSource** propriedade será representada como um **Recordset** objeto. O **Recordset** objeto deve ser fechado antes que essa propriedade é definida. Um erro será gerado se o **DataMember** não está definida antes do **DataSource** propriedade, ou se o **DataMember** nome não é reconhecido pelo objeto especificado no **Fonte de dados** propriedade.  
  
## <a name="usage"></a>Uso  
  
```  
Dim rs as New ADODB.Recordset  
rs.DataMember = "Command"     'Name of the rowset to bind to  
Set rs.DataSource = myDE      'Name of the object containing an IRowset  
```  
  
## <a name="applies-to"></a>Aplica-se a  
 [Objeto Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>Consulte também  
 [Propriedade DataSource (ADO)](../../../ado/reference/ado-api/datasource-property-ado.md)
