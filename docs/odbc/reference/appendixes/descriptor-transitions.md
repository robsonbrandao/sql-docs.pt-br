---
title: Transições de descritor | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- state transitions [ODBC], descriptor
- transitioning states [ODBC], descriptor
- descriptor transitions [ODBC]
ms.assetid: 0cf24fe6-5e3c-45fa-81b8-4f52ddf8501d
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 027b711c5c1a2cb2d35e65efdc2b00f441841d8c
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47718014"
---
# <a name="descriptor-transitions"></a>Transições de descritor
Descritores ODBC tem três estados.  
  
|Estado|Description|  
|-----------|-----------------|  
|D0|Descritor não alocado|  
|D1i|Descritor implicitamente alocado|  
|D1e|Descritor alocado explicitamente|  
  
 As tabelas a seguir mostram como cada função ODBC afeta o estado do descritor.  
  
## <a name="sqlallochandle"></a>Falha de SQLAllocHandle  
  
|D0<br /><br /> Não alocado|D1i<br /><br /> Implícito|D1e<br /><br /> Explícito|  
|------------------------|----------------------|----------------------|  
|D1i [1]|--|--|  
|D1e [2]|--|--|  
  
 [1] essa linha mostra as transições quando *HandleType* foi SQL_HANDLE_STMT.  
  
 [2] essa linha mostra as transições quando *HandleType* foi SQL_HANDLE_DESC.  
  
## <a name="sqlcopydesc"></a>SQLCopyDesc  
  
|D0<br /><br /> Não alocado|D1i<br /><br /> Implícito|D1e<br /><br /> Explícito|  
|------------------------|----------------------|----------------------|  
|(IH)|--|--|  
  
## <a name="sqlfreehandle"></a>SQLFreeHandle  
  
|D0<br /><br /> Não alocado|D1i<br /><br /> Implícito|D1e<br /><br /> Explícito|  
|------------------------|----------------------|----------------------|  
|--[1]|D0|--|  
|(IH) [2]|(HY017)|D0|  
  
 [1] essa linha mostra as transições quando *HandleType* foi SQL_HANDLE_STMT.  
  
 [2] essa linha mostra as transições quando *HandleType* foi SQL_HANDLE_DESC.  
  
## <a name="sqlgetdescfield-and-sqlgetdescrec"></a>SQLGetDescField e SQLGetDescRec  
  
|D0<br /><br /> Não alocado|D1i<br /><br /> Implícito|D1e<br /><br /> Explícito|  
|------------------------|----------------------|----------------------|  
|(IH)|--|--|  
  
## <a name="sqlsetdescfield-and-sqlsetdescrec"></a>SQLSetDescField e SQLSetDescRec  
  
|D0<br /><br /> Não alocado|D1i<br /><br /> Implícito|D1e<br /><br /> Explícito|  
|------------------------|----------------------|----------------------|  
|(IH) [1]|--|--|  
  
 [1] essa linha mostra as transições quando *DescriptorHandle* era o identificador de APD, descartar ou IPD, ou (para **SQLSetDescField**) quando *DescriptorHandle* era o identificador de um IRD e *FieldIdentifier* era SQL_DESC_ARRAY_STATUS_PTR ou SQL_DESC_ROWS_PROCESSED_PTR.  
  
## <a name="all-other-odbc-functions"></a>Todas as outras funções ODBC  
  
|D0<br /><br /> Não alocado|D1i<br /><br /> Implícito|D1e<br /><br /> Explícito|  
|------------------------|----------------------|----------------------|  
|--|--|--|
