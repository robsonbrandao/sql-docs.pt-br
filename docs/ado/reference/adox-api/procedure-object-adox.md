---
title: Objeto Procedure (ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Procedure
helpviewer_keywords:
- Procedure object [ADOX]
ms.assetid: 927bcf3e-32f5-4a80-98d3-600779f0732e
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 41d8e640d5b85f8adc32e0ce69801accacdc602d
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47692714"
---
# <a name="procedure-object-adox"></a>Objeto Procedure (ADOX)
Representa um procedimento armazenado. Quando usado em conjunto com o ADO [comando](../../../ado/reference/ado-api/command-object-ado.md) objeto, o **procedimento** objeto pode ser usado para adicionar, excluir ou modificar procedimentos armazenados.  
  
## <a name="remarks"></a>Comentários  
 O **procedimento** objeto permite que você crie um procedimento armazenado sem precisar saber ou usar a sintaxe de "CREATE PROCEDURE" do provedor.  
  
 Com as propriedades de um **procedimento** do objeto, você pode:  
  
-   Identificar o procedimento com o [nome](../../../ado/reference/adox-api/name-property-adox.md) propriedade.  
  
-   Especifique o ADO **comando** objeto que pode ser usado para criar ou executar o procedimento com o [comando](../../../ado/reference/adox-api/command-property-adox.md) propriedade.  
  
-   Retornar informações de data com o [DateCreated](../../../ado/reference/adox-api/datecreated-property-adox.md) e [DateModified](../../../ado/reference/adox-api/datemodified-property-adox.md) propriedades.  
  
 Esta seção contém o tópico a seguir.  
  
-   [Propriedades, Métodos e Eventos do objeto Procedure](../../../ado/reference/adox-api/procedure-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo Command e CommandText propriedades (VB)](../../../ado/reference/adox-api/command-and-commandtext-properties-example-vb.md)   
 [Coleção de parâmetros de exemplo da propriedade Command (VB)](../../../ado/reference/adox-api/parameters-collection-command-property-example-vb.md)   
 [Append de procedimentos de exemplo do método (VB)](../../../ado/reference/adox-api/procedures-append-method-example-vb.md)   
 [Delete de procedimentos de exemplo do método (VB)](../../../ado/reference/adox-api/procedures-delete-method-example-vb.md)   
 [Coleção Procedures (ADOX)](../../../ado/reference/adox-api/procedures-collection-adox.md)
