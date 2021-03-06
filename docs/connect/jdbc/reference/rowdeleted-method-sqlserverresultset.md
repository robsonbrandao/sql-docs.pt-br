---
title: Método rowDeleted (SQLServerResultSet) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.rowDeleted
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 9c6db315-e614-4604-b020-41af6a214cc1
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: b99e2f6f7bc289e123c36e3a528ec937e0f5f7ec
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47605604"
---
# <a name="rowdeleted-method-sqlserverresultset"></a>Método rowDeleted (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera se uma linha foi excluída.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public boolean rowDeleted()  
```  
  
## <a name="return-value"></a>Valor retornado  
 **True** se uma linha foi excluída e as exclusões forem detectadas. Caso contrário, **false**.  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Esse método rowDeleted é especificado pelo método rowDeleted na interface do resultset.  
  
 Uma linha excluída pode deixar um buraco visível em um conjunto de resultados. Esse método pode ser usado para detectar buracos em um conjunto de resultados. O valor retornado dependerá da capacidade do objeto [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) de detectar exclusões.  
  
> [!NOTE]  
>  O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] detecta linhas excluídas de todos os tipos de cursores atualizáveis, embora a detecção seja transitória para cursores dinâmicos e de avanço.  
  
## <a name="see-also"></a>Consulte Também  
 [Membros de SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Classe SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
