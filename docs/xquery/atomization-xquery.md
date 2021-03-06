---
title: Atomização (XQuery) | Microsoft Docs
ms.custom: ''
ms.date: 08/01/2016
ms.prod: sql
ms.prod_service: sql
ms.reviewer: ''
ms.technology: xml
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- XQuery, atomization
- atomization [XQuery]
ms.assetid: e3d7cf2f-c6fb-43c2-8538-4470a6375af5
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: bddb70c6c79ab983d1931bb17c741ff0dd531857
ms.sourcegitcommit: 9c6a37175296144464ffea815f371c024fce7032
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51657265"
---
# <a name="atomization-xquery"></a>Atomização (XQuery)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  A atomização é o processo de extrair o valor digitado de um item. Esse processo está implícito em determinadas circunstâncias. Alguns dos operadores XQuery, como operadores de aritmética e de comparação, dependem desse processo. Por exemplo, quando você aplica operadores aritméticos diretamente a nós, o valor digitado de um nó é recuperado primeiro invocando implicitamente a [função dados](../xquery/data-accessor-functions-data-xquery.md). Isso passa o valor atômico como um operando para o operador aritmético.  
  
 Por exemplo, a consulta a seguir retorna o total dos atributos LaborHours. Nesse caso, **Data ()** é aplicado implicitamente a nós de atributo.  
  
```  
declare @x xml  
set @x='<ROOT><Location LID="1" SetupTime="1.1" LaborHours="3.3" />  
<Location LID="2" SetupTime="1.0" LaborHours="5" />  
<Location LID="3" SetupTime="2.1" LaborHours="4" />  
</ROOT>'  
-- data() implicitly applied to the attribute node sequence.  
SELECT @x.query('sum(/ROOT/Location/@LaborHours)')  
```  
  
 Embora não seja necessário, você também pode especificar explicitamente o **Data ()** função:  
  
```  
SELECT @x.query('sum(data(ROOT/Location/@LaborHours))')  
```  
  
 Outro exemplo de atomização implícita é quando você usa operadores aritméticos. O **+** operador requer valores atômicos, e **Data ()** é aplicado implicitamente para recuperar o valor atômico do atributo LaborHours. A consulta é especificada na coluna Instructions do **xml** tipo na tabela ProductModel. A consulta a seguir retorna o atributo LaborHours três vezes. Na consulta, observe o seguinte:  
  
-   Na construção do atributo OriginalLaborHours, a atomização é aplicada implicitamente à sequência de singleton retornada por (`$WC/@LaborHours`). O valor digitado do atributo LaborHours é atribuído a OriginalLaborHours.  
  
-   Na construção do atributo UpdatedLaborHoursV1, o operador aritmético requer valores atômicos. Portanto, **Data ()** é aplicado implicitamente ao atributo LaborHours retornado por (`$WC/@LaborHours`). O valor atômico 1 é então adicionado a ele. A construção do atributo UpdatedLaborHoursV2 mostra o aplicativo explícito de **Data ()**, mas não é necessário.  
  
```  
SELECT Instructions.query('  
     declare namespace AWMI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
for $WC in /AWMI:root/AWMI:Location[1]  
        return  
            <WC OriginalLaborHours = "{ $WC/@LaborHours }"  
                UpdatedLaborHoursV1 = "{ $WC/@LaborHours + 1 }"   
                UpdatedLaborHoursV2 = "{ data($WC/@LaborHours) + 1 }" >  
            </WC>') as Result  
FROM Production.ProductModel  
where ProductModelID=7  
```  
  
 Este é o resultado:  
  
```  
<WC OriginalLaborHours="2.5"   
    UpdatedLaborHoursV1="3.5"   
    UpdatedLaborHoursV2="3.5" />  
```  
  
 A atomização resulta em uma instância de um tipo simples, um conjunto vazio ou um erro de tipo estático.  
  
 Atomização também ocorre em parâmetros de expressão de comparação passados para funções, valores retornados pelas funções, **cast ()** expressões e expressões de ordenação passadas na ordem por cláusula.  
  
## <a name="see-also"></a>Consulte também  
 [Fundamentos de XQuery](../xquery/xquery-basics.md)   
 [Expressões de comparação &#40;XQuery&#41;](../xquery/comparison-expressions-xquery.md)   
 [Funções XQuery em Tipos de Dados XML](../xquery/xquery-functions-against-the-xml-data-type.md)  
  
  
