---
title: Extensões específicas do SQL Server em processo para o ADO.NET | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- data access [CLR integration]
- ADO.NET [CLR integration]
- common language runtime [SQL Server], ADO.NET
- database objects [CLR integration], in-process extensions
- in-process data access providers [CLR integration]
- extensions [CLR integration]
ms.assetid: 781b812e-eb14-472a-85fa-aa4cdb929bee
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 9c5e98bebb99192c7245db3e2c255a36af751c0c
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47683154"
---
# <a name="sql-server-in-process-specific-extensions-to-adonet"></a>Extensões específicas em processo do SQL Server para o ADO.NET
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Há quatro extensões funcionais principais para o ADO.NET que se destinam especificamente ao uso em processo. Os tópicos a seguir abrangem essas extensões detalhadamente.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Objeto SqlContext](../../relational-databases/clr-integration-data-access-in-process-ado-net/sqlcontext-object.md)  
 Esta classe fornece acesso às outras extensões abstraindo o contexto de um chamador de uma rotina do SQL Server que executa código gerenciado em processo.  
  
 [Objeto SqlPipe](../../relational-databases/clr-integration-data-access-in-process-ado-net/sqlpipe-object.md)  
 Esta classe contém rotinas para enviar mensagens e resultados tabulares ao cliente.  
  
 [Objeto SqlTriggerContext](../../relational-databases/clr-integration-data-access-in-process-ado-net/sqltriggercontext-object.md)  
 Esta classe fornece informações sobre o contexto no qual um gatilho é executado.  
  
 [Objeto SqlDataRecord](../../relational-databases/clr-integration-data-access-in-process-ado-net/sqldatarecord-object.md)  
 A classe SqlDataRecord representa uma única linha de dados, juntamente com seus metadados relacionados, e permite que procedimentos armazenados retornem conjuntos de resultados personalizados ao cliente.  
  
  
