---
title: SQLEndTran (biblioteca de cursores) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLEndTran function [ODBC], Cursor Library
ms.assetid: 92340b87-9084-4838-a509-e9ca22d5fd5c
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: e2e218035473d1ebb980aa5f44da8cc7b8ef843d
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47827034"
---
# <a name="sqlendtran-cursor-library"></a>SQLEndTran (Biblioteca de cursores)
> [!IMPORTANT]  
>  Este recurso será removido em uma versão futura do Windows. Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que usam esse recurso atualmente. A Microsoft recomenda usar a funcionalidade de cursor do driver.  
  
 Este tópico discute o uso do **SQLEndTran** função na biblioteca de cursor. Para obter informações gerais sobre **SQLEndTran**, consulte [função SQLEndTran](../../../odbc/reference/syntax/sqlendtran-function.md).  
  
 A biblioteca de cursores não oferece suporte a transações e passa a chamadas para **SQLEndTran** diretamente para o driver. No entanto, a biblioteca de cursores dá suporte os comportamentos de confirmação e reversão do cursor conforme retornado pela fonte de dados com os tipos de informações SQL_CURSOR_ROLLBACK_BEHAVIOR e SQL_CURSOR_COMMIT_BEHAVIOR:  
  
-   Para fontes de dados que preservam os cursores em transações, as alterações que são revertidas na fonte de dados não são revertidas no cache da biblioteca de cursor. Para fazer com que o cache corresponderem aos dados na fonte de dados, o aplicativo feche e reabra o cursor.  
  
-   Para fontes de dados que fechar cursores em limites de transação, a biblioteca de cursores fechará os cursores e exclui os caches para todas as instruções sobre a conexão.  
  
-   Para fontes de dados que excluir instruções preparadas nos limites da transação, o aplicativo deve reprepare todas as instruções preparadas sobre a conexão antes de sê-los.
