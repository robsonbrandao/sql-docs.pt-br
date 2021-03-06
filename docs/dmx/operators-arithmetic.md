---
title: Operadores aritméticos (DMX) | Microsoft Docs
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: edbe8a3404217f330b5b62a9d433c7d560b28656
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "37989649"
---
# <a name="operators---arithmetic"></a>Operadores – aritméticos
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Você pode usar operadores aritméticos em extensões DMX (Data Mining) para computações aritméticas no [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], incluindo adição, subtração, multiplicação e divisão.  
  
 A tabela a seguir identifica os operadores aritméticos aos quais a DMX oferece suporte.  
  
|Operador|Description|  
|--------------|-----------------|  
|[+ &#40;Adicionar&#41; &#40;DMX&#41;](../dmx/add-dmx.md)|Soma dois números.|  
|[- &#40;Subtrair&#41; &#40;DMX&#41;](../dmx/subtract-dmx.md)|Subtrai um número de outro.|  
|[&#42;&#40;Multiplicar&#41; &#40;DMX&#41;](../dmx/multiply-dmx.md)|Multiplica um número por outro.|  
|[&#40;Dividir&#41; &#40;DMX&#41;](../dmx/divide-dmx.md)|Divide um número pelo outro.|  
  
 As regras a seguir determinam a ordem de prioridade para operadores aritméticos em uma expressão DMX:  
  
-   Quando houver mais de um operador aritmético em uma expressão, a multiplicação e a divisão serão calculadas primeiramente, seguidas da subtração e da adição.  
  
-   Quando todos os operadores aritméticos em uma expressão tiverem o mesmo nível de prioridade, a ordem de execução será da esquerda para a direita.  
  
-   Expressões entre parênteses têm prioridade sobre todas as outras operações.  
  
## <a name="see-also"></a>Consulte também  
 [Extensões de mineração de dados &#40;DMX&#41; referência](../dmx/data-mining-extensions-dmx-reference.md)   
 [Extensões de mineração de dados &#40;DMX&#41; referência de função](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Extensões de mineração de dados &#40;DMX&#41; referência de operador](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [Extensões de mineração de dados &#40;DMX&#41; referência de instrução](../dmx/data-mining-extensions-dmx-statements.md)   
 [Extensões de mineração de dados &#40;DMX&#41; convenções de sintaxe](../dmx/data-mining-extensions-dmx-syntax-conventions.md)   
 [Extensões de mineração de dados &#40;DMX&#41; elementos de sintaxe](../dmx/data-mining-extensions-dmx-syntax-elements.md)   
 [Expressões &#40;DMX&#41;](../dmx/expressions-dmx.md)   
 [Funções de previsão gerais &#40;DMX&#41;](../dmx/general-prediction-functions-dmx.md)   
 [Operadores &#40;DMX&#41;](../dmx/operators-dmx.md)   
 [Estrutura e uso de consultas de previsão DMX](../dmx/structure-and-usage-of-dmx-prediction-queries.md)   
 [Compreendendo a instrução DMX Select](../dmx/understanding-the-dmx-select-statement.md)  
  
  
