---
title: Método setIntegratedSecurity (SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDataSource.setIntegratedSecurity
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 4c968ee4-b041-424a-bf69-cc2c4a4f51c6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: b5919545e08b2de0578080e7dbc538ea2581f587
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47690904"
---
# <a name="setintegratedsecurity-method-sqlserverdatasource"></a>Método setIntegratedSecurity (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Define um valor **booliano** que indica se a propriedade integratedSecurity está habilitada.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public void setIntegratedSecurity(boolean enable)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *enable*  
  
 **True** se integratedSecurity está habilitada. Caso contrário, **false**.  
  
## <a name="remarks"></a>Remarks  
 Defina como "**true**" para indicar que as credenciais do Windows serão usadas pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para autenticar o usuário do aplicativo. Se "**true**", o [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] pesquisará no cache de credenciais do computador local as credenciais que já foram fornecidas quando foi feito logon no computador ou na rede. Se "**false**", o nome de usuário e a senha deverão ser fornecidos.  
  
> [!NOTE]  
>  Essa propriedade só é compatível nos sistemas operacionais [!INCLUDE[msCoName](../../../includes/msconame_md.md)] Windows.  
  
 Para obter mais informações sobre como usar a autenticação integrada, consulte [construindo a URL de Conexão](../../../connect/jdbc/building-the-connection-url.md).  
  
## <a name="see-also"></a>Consulte Também  
 [Membros de SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Classe SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
