---
title: Função local-name (XQuery) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: sql
ms.reviewer: ''
ms.technology: xml
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- fn:local-name function
- local-name function
ms.assetid: c901ef5d-89c5-482a-bf64-3eefbcf3098d
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 93f289ed165742ae8fdf8d49732186161a4a8b5d
ms.sourcegitcommit: 9c6a37175296144464ffea815f371c024fce7032
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51666985"
---
# <a name="functions-on-nodes---local-name"></a>Funções em Nós – local-name
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Retorna a parte local do nome da *$arg* como xs: String que será a cadeia de caracteres de comprimento zero ou terá a forma léxica de um xs: NCName. Se o argumento não for fornecido, o padrão será o nó de contexto.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
fn:local-name() as xs:string  
fn:local-name($arg as node()?) as xs:string  
```  
  
## <a name="arguments"></a>Argumentos  
 *$arg*  
 Nome de nó cuja parte local-name será recuperada.  
  
## <a name="remarks"></a>Comentários  
  
-   No SQL Server **fn:local-name()** sem um argumento só pode ser usado no contexto de um predicado dependente de contexto. Mais precisamente, ele só pode ser usado entre parênteses (`[ ]`).  
  
-   Se o argumento for fornecido e a sequência for vazia, a função retornará a cadeia de caracteres de comprimento zero.  
  
-   Se o nó designado não tiver nome, por ser um nó de documento, um comentário ou um nó de texto, a função retornará a cadeia de caracteres de comprimento zero.  
  
## <a name="examples"></a>Exemplos  
 Este tópico fornece exemplos de XQuery contra instâncias XML armazenadas em várias **xml** colunas de tipo de banco de dados AdventureWorks.  
  
### <a name="a-retrieve-local-name-of-a-specific-node"></a>A. Recuperar o nome local de um nó específico  
 A consulta a seguir é especificada em uma instância XML não digitada. A expressão de consulta, `local-name(/ROOT[1])`, recupera a parte do nome local do nó especificado.  
  
```  
declare @x xml  
set @x='<ROOT><a>111</a></ROOT>'  
SELECT @x.query('local-name(/ROOT[1])')  
-- result = ROOT  
```  
  
 A consulta a seguir é especificada contra a coluna Instructions, uma coluna xml digitada, da tabela ProductModel. A expressão, `local-name(/AWMI:root[1]/AWMI:Location[1])`, retorna o nome local, `Location`, do nó especificado.  
  
```  
SELECT Instructions.query('  
declare namespace AWMI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions" ;  
     local-name(/AWMI:root[1]/AWMI:Location[1])') as Result  
FROM Production.ProductModel  
WHERE ProductModelID=7  
-- result = Location  
```  
  
### <a name="b-using-local-name-without-argument-in-a-predicate"></a>B. Usando o local-name sem argumento em um predicado  
 A consulta a seguir é especificada na coluna Instructions, digitado **xml** coluna da tabela ProductModel. A expressão retorna todos os filhos do elemento do elemento <`root`> cuja parte do nome local do QName é "Location". O **example** função é especificada no predicado e não tem nenhum argumento, o nó de contexto é usado pela função.  
  
```  
SELECT Instructions.query('  
declare namespace AWMI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions" ;  
  /AWMI:root//*[local-name() = "Location"]') as Result  
FROM Production.ProductModel  
WHERE ProductModelID=7  
```  
  
 A consulta retorna todos os filhos do elemento <`Location`> do elemento <`root`>.  
  
## <a name="see-also"></a>Consulte também  
 [Funções em nós](https://msdn.microsoft.com/library/09a8affa-3341-4f50-aebc-fdf529e00c08)   
 [Função namespace-uri &#40;XQuery&#41;](../xquery/functions-on-nodes-namespace-uri.md)  
  
  
