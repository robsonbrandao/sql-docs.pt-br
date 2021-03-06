---
title: Método setHostNameInCertificate (SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- setHostNameInCertificate Method (SQLServerDataSource)
apilocation:
- setHostNameInCertificate Method (SQLServerDataSource)
apitype: Assembly
ms.assetid: 2bcf4f2e-a103-4374-abc4-ffad4ce8e3c0
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 012073c9d1f8f3646c9bea5fd35cb12e0e0343c8
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47601774"
---
# <a name="sethostnameincertificate-method-sqlserverdatasource"></a>Método setHostNameInCertificate (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Define o nome do host a ser usado ao validar o certificado SSL (Secure Sockets Layer) do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public void setHostNameInCertificate(java.lang.String hostNameInCertificate)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *hostNameInCertificate*  
  
 Uma **String** que contém o nome do host.  
  
## <a name="remarks"></a>Remarks  
 O valor de hostNameInCertificate valor é usado para validar o certificado SSL do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quando a camada de comunicação é criptografada com SSL. O valor padrão é nulo.  
  
 Se a propriedade hostNameInCertificate for definida como nula ou não for especificada, o [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] usará o valor da propriedade serverName para validar em relação ao certificado SSL do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Se a propriedade hostNameInCertificate for definida como uma cadeia de caracteres ou uma cadeia de caracteres vazia "", o driver usará esse valor para validar o certificado SSL do servidor.  
  
## <a name="see-also"></a>Consulte Também  
 [Membros de SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Classe SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
