---
title: Notas de versão (OLE DB Driver para SQL Server) | Microsoft Docs
ms.date: 02/12/2019
ms.prod: sql
ms.technology: connectivity
ms.topic: conceptual
author: David-Engel
ms.author: v-daveng
ms.openlocfilehash: 36dc1b7325265da6231b75e9f4db46854b0b219f
ms.sourcegitcommit: 958cffe9288cfe281280544b763c542ca4025684
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 02/23/2019
ms.locfileid: "56744356"
---
# <a name="release-notes-for-the-microsoft-ole-db-driver-for-sql-server"></a>Notas de versão do Driver do Microsoft OLE DB para SQL Server
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

[!INCLUDE[Driver_OLEDB_Download](../../includes/driver_oledb_download.md)]

Esta página discute o que foi adicionado em cada versão do Driver da Microsoft OLE DB para SQL Server.

## <a name="whats-new-in-version-1821"></a>Novidades da versão 18.2.1

**Recursos adicionados:**

* Suporte para codificação do servidor UTF-8. Para obter mais informações, consulte: [suporte a UTF-8 no Driver do OLE DB para SQL Server](features/utf-8-support-in-oledb-driver-for-sql-server.md).
* Suporte para autenticação do Azure Active Directory. Para saber mais, confira [Usar o Azure Active Directory](features/using-azure-active-directory.md).

## <a name="whats-new-in-version-1810"></a>Novidades da versão 18.1.0

**Recursos adicionados:**

* Suporte para `UseFMTONLY` palavra-chave de cadeia de caracteres de conexão e `SSPROP_INIT_USEFMTONLY` propriedade de inicialização.
`UseFMTONLY` Controla como os metadados são recuperados ao se conectar ao [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] e mais recente.  
Para obter mais informações, consulte:
  * [Uso de palavras-chave de cadeia de conexão com o Driver do OLE DB para SQL Server](applications/using-connection-string-keywords-with-oledb-driver-for-sql-server.md)

**Bugs corrigidos:**

* Fixo versão incorreta do arquivo de formato BCP. O 18.0 do Driver de banco de dados OLE incorretamente define a versão do arquivo de formato BCP para 18.0 em vez de 11.0. Arquivos de formato gerados pelo 18.0 do Driver de banco de dados OLE não podem ser lido pelo 18.1 do Driver de banco de dados OLE. Se você precisar usar arquivos de formato gerados pela versão anterior do driver com o novo driver, você pode editar manualmente os arquivos para alterar a versão 11.0.

## <a name="whats-new-in-version-1802"></a>Novidades da versão 18.0.2

**Recursos adicionados**:

* Suporte para `MultiSubnetFailover` palavra-chave de cadeia de caracteres de conexão e `SSPROP_INIT_MULTISUBNETFAILOVER` propriedade de inicialização.  
Para obter mais informações, consulte:  
  * [Suporte ao Driver do OLE DB para SQL Server para alta disponibilidade e recuperação de desastre](features/oledb-driver-for-sql-server-support-for-high-availability-disaster-recovery.md)  
  * [Uso de palavras-chave de cadeia de conexão com o Driver do OLE DB para SQL Server](applications/using-connection-string-keywords-with-oledb-driver-for-sql-server.md)

## <a name="see-also"></a>Confira também
[Driver do Microsoft OLE DB para SQL Server](oledb-driver-for-sql-server.md)
