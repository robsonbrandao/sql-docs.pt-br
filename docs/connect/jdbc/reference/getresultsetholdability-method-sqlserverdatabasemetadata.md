---
title: Método getResultSetHoldability (SQLServerDatabaseMetaData) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDatabaseMetaData,getResultSetHoldability
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: f0bd6283-83ab-4a0a-b825-ec4cdccf03e1
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: fd044a5ea530a1b932561fcd1fe60d52b108ad09
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47793744"
---
# <a name="getresultsetholdability-method-sqlserverdatabasemetadata"></a>Método getResultSetHoldability (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera a capacidade de colocação em espera padrão dos conjuntos de resultados do banco de dados em questão.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public int getResultSetHoldability()  
```  
  
## <a name="return-value"></a>Valor retornado  
 Um **int** que indica a suspensão padrão.  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Esse método getResultSetHoldability é especificado pelo método getResultSetHoldability na interface DatabaseMetadata.  
  
 Durante o uso do [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] com um banco de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], esse método retorna 1, que equivale à constante ResultSet.HOLD_CURSORS_OVER_COMMIT.  
  
## <a name="see-also"></a>Consulte Também  
 [Métodos SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [Membros SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [Classe SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
