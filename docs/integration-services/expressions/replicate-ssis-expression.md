---
title: REPLICATE (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- REPLICATE function
ms.assetid: e7a37b93-6d1d-42d5-9a65-de1790abf6a5
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 8dc9024d0c68b4ed992215417dc40c0438877701
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47840754"
---
# <a name="replicate-ssis-expression"></a>REPLICATE (Expressão SSIS)
  Retorna uma expressão de caractere que é replicada várias vezes. O argumento *times* deve ser avaliado como um inteiro.  
  
> [!NOTE]  
>  A função REPLICATE usa com frequência cadeias longas e, portanto, é mais provável de incorrer o limite de 4.000 caracteres no tamanho da expressão. Se o resultado da avaliação de uma expressão tiver o tipo de dados DT_WSTR ou DT_STR do Integration Services, a expressão truncará em 4.000 caracteres. Se o tipo de resultado de uma subexpressão for DT_STR ou DT_WSTR, essa subexpressão será truncada em 4.000 caracteres, independentemente do tipo de resultado da expressão geral. As consequências do truncamento podem ser controladas muito bem ou causam um aviso ou um erro. Para obter mais informações, consulte [Sintaxe &#40;SSIS&#41;](../../integration-services/expressions/syntax-ssis.md).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
REPLICATE(character_expression,times)  
```  
  
## <a name="arguments"></a>Argumentos  
 *character_expression*  
 É uma expressão de caractere a ser replicada.  
  
 *times*  
 É uma expressão de inteiro que especifica o número de vezes que *character_expression* é replicado.  
  
## <a name="result-types"></a>Tipos de resultado  
 DT_WSTR  
  
## <a name="remarks"></a>Remarks  
 Se *times* for zero, a função retornará uma cadeia de comprimento zero.  
  
 Se *times* for um número negativo, a função retornará um erro.  
  
 O argumento *times* também pode usar variáveis e colunas.  
  
 REPLICATE só funciona com o tipo de dados DT_WSTR. Um argumento *character_expression* que é um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR é implicitamente convertido para o tipo de dados DT_WSTR antes que REPLICATE execute sua operação. Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR. Para obter mais informações, consulte [Tipos de dados do Integration Services](../../integration-services/data-flow/integration-services-data-types.md) e [Cast &#40;Expressão SSIS&#41;](../../integration-services/expressions/cast-ssis-expression.md).  
  
 REPLICATE retornará um resultado nulo se o argumento for nulo.  
  
## <a name="expression-examples"></a>Exemplos de expressões  
 Esse exemplo replica um literal de cadeia três vezes. O resultado de retorno é "Mountain BikeMountain BikeMountain Bike".  
  
```  
REPLICATE("Mountain Bike", 3)  
```  
  
 Esse exemplo replica os valores na coluna **Nome** pelo valor na variável **Vezes** . Se **Vezes** for 3 e **Nome** for Roda Dianteira de Passeio, o resultado de retorno será Roda Dianteira de PasseioRoda Dianteira de PasseioRoda Dianteira de Passeio.  
  
```  
REPLICATE(Name, @Times)  
```  
  
 Esse exemplo replica o valor na variável **Nome** pelo valor na coluna **Vezes** . **Times** tem um tipo de dados não Integer e a expressão inclui uma conversão explícita para um tipo de dados Integer. Se **Nome** contiver Capacete e **Vezes** for 2, o resultado de retorno será "CapaceteCapacete".  
  
```  
REPLICATE(@Name, (DT_I4(Times))  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Funções &#40;Expressão do SSIS&#41;](../../integration-services/expressions/functions-ssis-expression.md)  
  
  
