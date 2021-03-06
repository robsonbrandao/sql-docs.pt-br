---
title: Funções (Driver ODBC do Visual FoxPro) da cadeia de caracteres | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- ODBC string functions [ODBC]
- string functions [ODBC]
- Visual FoxPro ODBC driver [ODBC], string functions
- FoxPro ODBC driver [ODBC], string functions
ms.assetid: 1974fd26-ef0d-45d5-860b-298917c8e9c3
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 1a9e1c94eec150cc24522cd6e4c57eb35b4a2126
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47854824"
---
# <a name="string-functions-visual-foxpro-odbc-driver"></a>Funções de cadeia de caracteres (Driver ODBC do Visual FoxPro)
A tabela a seguir lista funções de manipulação de cadeia de caracteres ODBC com suporte pelo Driver de ODBC Visual FoxPro; Quando a gramática do Visual FoxPro para a mesma função difere da sintaxe ODBC, o Visual FoxPro equivalente é listado.  
  
|Gramática ODBC|Gramática do Visual FoxPro|  
|------------------|---------------------------|  
|ASCII *(string_exp)*|ASC *(string_exp)*|  
|CHAR *(código)*|CHR *(string_exp)*|  
|CONCAT *(string_exp2 com string_exp1)*|*string_exp1 + string_exp2 com*|  
|DIFERENÇA *(string_exp2 com string_exp1)*||  
|Inserir *(string_exp1, início, comprimento, string_exp2 com)*|COISAS *(string_exp1, início, comprimento, string_exp2 com)*|  
|LCASE *(string_exp)*|INFERIOR *(string_exp)*|  
|ESQUERDA *(string_exp, contagem)*||  
|COMPRIMENTO *(string_exp)*|LEN *(string_exp)*|  
|LTRIM *(string_exp)*||  
|REPITA *(string_exp, contagem)*|REPLICAR *(string_exp, contagem)*|  
|Substitua *(string_exp1, string_exp2 com, string_exp3)*|STRTRAN *(string_exp1, string_exp2 com, string_exp3)*|  
|DIREITA *(string_exp, contagem)*||  
|RTRIM *(string_exp)*||  
|SOUNDEX *(string_exp)*||  
|ESPAÇO *(contagem)*||  
|Subcadeia de caracteres *(string_exp, início, comprimento)*|SUBSTR *(string_exp, início, comprimento)*|  
|UCASE *(string_exp)*|SUPERIOR *(string_exp)*|
