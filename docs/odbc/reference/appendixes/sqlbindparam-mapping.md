---
title: Mapeamento SQLBindParam | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLBindparam function [ODBC], mapping
- mapping deprecated functions [ODBC], SQLBindParam
ms.assetid: 375f8f24-36de-4946-916e-c75abc6f070d
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 57e0fe66d76f91c8cea35710e9d0245db7619628
ms.sourcegitcommit: 2429fbcdb751211313bd655a4825ffb33354bda3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "52544432"
---
# <a name="sqlbindparam-mapping"></a>Mapeamento SQLBindParam
**SQLBindParam** não pode realmente ser chamado preterido porque nunca foi lá em ODBC; no entanto, ela ainda representa funções duplicadas – precisa exportá-lo porque o ISO e abra grupo compatível com aplicativos usará o Gerenciador de Driver. Porque **SQLBindParameter** contém toda a funcionalidade dos **SQLBindParam**, **SQLBindParam** serão mapeados na parte superior da **SQLBindParameter** (quando o driver subjacente é um ODBC 3 *. x* driver). Um ODBC 3 *. x* driver não precisa implementar **SQLBindParam**.  
  
## <a name="remarks"></a>Comentários  
 Quando esta chamada para **SQLBindParam** é feita:  
  
```  
SQLBindParam(   StatementHandle,    ParameterNumber,    ValueType,    ParameterType,    ColumnSize,    DecimalDigits,    ParameterValuePtr,    StrLen_or_IndPtr)  
```  
  
 as chamadas de Gerenciador de Driver **SQLBindParameter** no driver da seguinte maneira:  
  
```  
SQLBindParameter(   StatementHandle,    ParameterNumber,    SQL_PARAM_INPUT,    ValueType,    ParameterType,    ColumnSize,    DecimalDigits,    ParameterValuePtr,    BufferLength,    StrLen_or_IndPtr)  
```  
  
 Ver [informações de ODBC 64-Bit](../../../odbc/reference/odbc-64-bit-information.md), se o aplicativo será executado em um sistema operacional de 64 bits.  
  
## <a name="see-also"></a>Consulte também  
 [Funções preteridas de mapeamento](../../../odbc/reference/appendixes/mapping-deprecated-functions.md)
