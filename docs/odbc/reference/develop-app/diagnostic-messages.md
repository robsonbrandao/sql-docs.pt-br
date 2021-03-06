---
title: Mensagens de diagnóstico | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- diagnostic information [ODBC], diagnostic messages messages
- error messages [ODBC], diagnostic messages
- diagnostic messages [ODBC]
ms.assetid: 98027871-9901-476e-a722-ee58b7723c1f
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 883cd29d8628f1e9270ae95a772c4d116b896710
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47767624"
---
# <a name="diagnostic-messages"></a>Mensagens de diagnóstico
Uma mensagem de diagnóstico será retornada com cada SQLSTATE. O SQLSTATE mesmo frequentemente é retornado com um número de mensagens diferentes. Por exemplo, o SQLSTATE 42000 (sintaxe ou violação de acesso) é retornado para a maioria dos erros de sintaxe SQL. No entanto, cada erro de sintaxe é a probabilidade de ser descrito por uma mensagem diferente.  
  
 Mensagens de diagnóstico de exemplo são listadas na coluna de erro na tabela de SQLSTATEs no Apêndice A e em cada função. Embora drivers podem retornar essas mensagens, eles são mais prováveis de retornar qualquer mensagem é passada a eles pela fonte de dados.  
  
 Aplicativos geralmente exibem mensagens de diagnóstico para o usuário, junto com o SQLSTATE e o código de erro nativo. Isso ajuda o usuário e equipe de suporte determinar a causa de quaisquer problemas. As informações de componente inseridas na mensagem são particularmente útil ao fazer isso.  
  
 Mensagens de diagnóstico provenientes de fontes de dados e componentes em uma conexão ODBC, como drivers, gateways e o Gerenciador de Driver. Normalmente, fontes de dados não suportam diretamente ODBC. Consequentemente, se um componente em uma conexão ODBC recebe uma mensagem de uma fonte de dados, ele deverá identificar a fonte de dados como a origem da mensagem. Ele também deve identificar em si como o componente que recebeu a mensagem.  
  
 Se a fonte de um erro ou aviso é um componente em si, a mensagem de diagnóstico deve explicar isso. Portanto, o texto de mensagens tem dois formatos diferentes. Para erros e avisos que não ocorram em uma fonte de dados, a mensagem de diagnóstico deve usar este formato:  
  
 **[** *identificador de fornecedor* **] [** *identificador de componente de ODBC* **]** *texto fornecido pelo componente*  
  
 Para erros e avisos que ocorrem em uma fonte de dados, a mensagem de diagnóstico deve usar este formato:  
  
 **[** *identificador de fornecedor* **] [** *identificador de componente de ODBC* **] [** *identificador da fonte de dados*  **]** *dados--fornecido-texto de origem*  
  
 A tabela a seguir mostra o significado de cada elemento.  
  
|Elemento|Significado|  
|-------------|-------------|  
|*Identificador de fornecedor*|Identifica o fornecedor do componente no qual ocorreu o erro ou aviso ou que recebeu o erro ou aviso diretamente da fonte de dados.|  
|*Identificador do componente de ODBC*|Identifica o componente no qual ocorreu o erro ou aviso ou que recebeu o erro ou aviso diretamente da fonte de dados.|  
|*Identificador da fonte de dados*|Identifica a fonte de dados. Para drivers baseados em arquivo, isso normalmente é um formato de arquivo, como drivers baseados em DBMS para Xbase [1], isso é o produto do DBMS.|  
|*texto fornecido pelo componente*|Gerado pelo componente do ODBC.|  
|*dados de origem-fornecido-texto*|Gerado pela fonte de dados.|  
  
 [1] nesse caso, o driver está atuando como o driver e a fonte de dados.  
  
 Colchetes (**[]**) deve ser incluído na mensagem e não indicam itens opcionais.
