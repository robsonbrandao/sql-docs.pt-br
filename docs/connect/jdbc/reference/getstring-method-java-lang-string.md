---
title: Método (lang) getString | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerCallableStatement.getString (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: f67371e0-e879-4188-85fc-ecb85f0be2a9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 208fbad8a728775c8e8d985a6f7f28c7facc865f
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47773484"
---
# <a name="getstring-method-javalangstring"></a>Método getString (java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera o valor do parâmetro designado como uma **String** na linguagem de programação Java, considerando o nome do parâmetro.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public java.lang.String getString(java.lang.String sCol)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *sCol*  
  
 Uma **String** que contém o nome do parâmetro.  
  
## <a name="return-value"></a>Valor retornado  
 Um valor de **String**.  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Esse método getString é especificado pelo método getString na interface java.sql.CallableStatement.  
  
 Todas as colunas no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] podem ser retornadas como uma cadeia de caracteres. Isso significa que uma representação da cadeia de caracteres de todos os tipos baseados em número e em caractere, e uma representação da cadeia de caracteres hexadecimais de colunas binárias, como binary, varbinary, varbinary(max), image, timestamp e uniqueidentifier, podem ser retornadas.  
  
 Os tipos que diferenciam locais, como money, smallmoney, datetime, smalldatetime, float, real, decimal e numeric, retornarão o formato toString() canônico para o valor subjacente do tipo.  
  
 Os tipos definidos pelo usuário são retornados como valores de cadeia de caracteres hexadecimais.  
  
## <a name="see-also"></a>Consulte Também  
 [Método getString &#40;SQLServerCallableStatement&#41;](../../../connect/jdbc/reference/getstring-method-sqlservercallablestatement.md)   
 [Membros SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [Classe SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
