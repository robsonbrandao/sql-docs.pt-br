---
title: Conectar-se a fontes de dados | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- connections [ADO]
ms.assetid: 82770486-37bd-4c90-885f-6817a7c77ad7
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 1fb066b2d75efd1ea1d5974c92ea5c524165f2e7
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47635304"
---
# <a name="connecting-to-data-sources"></a>Conectando-se a fontes de dados
ADO **Conexão** objeto representa uma sessão exclusiva com uma fonte de dados, incluindo um arquivo de texto delimitado por vírgula, um armazenamento de arquivos ou um DBMS. No caso de um sistema de banco de dados cliente/servidor, a conexão ADO pode ser uma conexão de rede reais para o servidor.  
  
 O **Conexão** objeto oferece suporte a vários [propriedades e métodos](../../../ado/reference/ado-api/connection-object-properties-methods-and-events.md) para especificar as configurações de conexão, abrindo e fechando conexões, criar e executar comandos na fonte de dados e fornecendo informações sobre o design de fonte de dados na forma de conjuntos de linhas de esquema, etc. Dependendo da funcionalidade compatível com o provedor, algumas coleções, métodos ou propriedades de um **Conexão** objeto pode não estar disponível.  
  
 Você pode se conectar a uma fonte de dados usando um **Conexão** do objeto ou usando uma **Recordset** objeto.  
  
 Esta seção contém os tópicos a seguir.  
  
-   [Usando um objeto Connection](../../../ado/guide/data/using-a-connection-object.md)  
  
-   [Usando um objeto Recordset](../../../ado/guide/data/using-a-recordset-object.md)  
  
-   [Criando uma cadeia de conexão](../../../ado/guide/data/creating-a-connection-string.md)  
  
-   [Especificando propriedades de conexão](../../../ado/guide/data/specifying-connection-properties.md)  
  
-   [Controlar transações](../../../ado/guide/data/controlling-transactions-ado.md)
