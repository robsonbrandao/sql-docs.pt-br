---
title: Declarando o aplicativo&#39;s ODBC versão | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- declaring ODBC version [ODBC]
- data sources [ODBC], declaring ODBC version
- ODBC drivers [ODBC], declaring ODBC version
- connecting to driver [ODBC], declaring ODBC version
- connecting to data source [ODBC], declaring ODBC version
- version declaration [ODBC]
ms.assetid: 083a1ef5-580a-4979-9cf3-50f4549a080a
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 7c5bb124af74d1fa009a61237edb54a9c8baec74
ms.sourcegitcommit: 37310da0565c2792aae43b3855bd3948fd13e044
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/18/2018
ms.locfileid: "53591540"
---
# <a name="declaring-the-application39s-odbc-version"></a>Declarando o aplicativo&#39;s a versão do ODBC
Antes de um aplicativo aloca uma conexão, ele deve definir o atributo de ambiente SQL_ATTR_ODBC_VERSION. Esse atributo declara que o aplicativo segue o ODBC 2. *x* ou o ODBC 3. *x* especificação ao usar os seguintes itens:  
  
-   **SQLSTATEs**. Muitos valores SQLSTATE são diferentes no ODBC 2. *x* e o ODBC 3. *x*.  
  
-   **Data, hora e identificadores de tipo Timestamp**. A tabela a seguir mostra os identificadores de tipo de data, hora e dados de carimbo de hora no ODBC 2. *x* e o ODBC 3. *x*.  
  
    |ODBC 2. *x*|ODBC 3. *x*|  
    |----------------|----------------|  
    |**Identificadores de tipo SQL**||  
    |SQL_DATE|SQL_TYPE_DATE|  
    |SQL_TIME|SQL_TYPE_TIME|  
    |SQL_TIMESTAMP|SQL_TYPE_TIMESTAMP|  
    |**Identificadores de tipo C**||  
    |SQL_C_DATE|SQL_C_TYPE_DATE|  
    |SQL_C_TIME|SQL_C_TYPE_TIME|  
    |SQL_C_TIMESTAMP|SQL_C_TYPE_TIMESTAMP|  
  
-   _CatalogName_  **argumento em SQLTables**. No ODBC 2. *x*, os caracteres curinga ("%" e "_") nos *CatalogName* argumento são tratados literalmente. Em ODBC 3. *x*, eles são tratados como caracteres curinga. Portanto, um aplicativo que segue o ODBC 2. *x* especificação não é possível usá-los como curinga caracteres e não escapa-las ao usá-los como literais. Um aplicativo que segue o ODBC 3. *x* especificação pode usá-las como caracteres curinga ou escape-los e usá-los como literais. Para obter mais informações, consulte [argumentos em funções de catálogo](../../../odbc/reference/develop-app/arguments-in-catalog-functions.md).  
  
 O ODBC 3 *. x* Gerenciador de Driver e o ODBC 3 *. x* drivers verificar a versão da especificação do ODBC para o qual um aplicativo é escrito e responder de acordo. Por exemplo, se o aplicativo segue o ODBC 2. *x* especificação e chamadas **SQLExecute** antes de chamar **SQLPrepare**, o ODBC 3 *. x* Gerenciador de Driver retornará SQLSTATE S1010 ( Erro de sequência de função). Se o aplicativo segue o ODBC 3 *. x* especificação, o Gerenciador de Driver retornará SQLSTATE HY010 (erro de sequência de função). Para obter mais informações, consulte [compatibilidade com versões anteriores e em conformidade com padrões](../../../odbc/reference/develop-app/backward-compatibility-and-standards-compliance.md).  
  
> [!IMPORTANT]  
>  Aplicativos que seguem o ODBC 3. *x* especificação deve usar o código condicional para evitar o uso de funcionalidade de novo no ODBC 3. *x* ao trabalhar com ODBC 2. *x* drivers. ODBC 2. *x* drivers não dão suporte a funcionalidade de nova no ODBC 3. *x* simplesmente porque o aplicativo declara que ela segue o ODBC 3. *x* especificação. Além disso, o ODBC 3. *x* drivers não deixar de dar suporte à funcionalidade de nova no ODBC 3. *x* simplesmente porque o aplicativo declara que ela segue o ODBC 2. *x* especificação.
