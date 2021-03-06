---
title: Alterar as tabelas de captura de dados (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: a4372d0b-50ca-4e58-80f6-2ed3cb52a84a
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: d977843f6fdbe59f382b6dbb39da017453265c5e
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47692694"
---
# <a name="change-data-capture-tables-transact-sql"></a>tabelas Change Data Capture (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  O Change Data Capture habilita o rastreamento de alterações em tabelas, de modo que as alterações de DML (linguagem de manipulação de dados) e de DDL (linguagem de definição de dados) feitas nas tabelas podem ser carregadas de forma incremental no data warehouse. Os tópicos desta seção descrevem as tabelas do sistema que armazenam informações usadas pelas operações do Change Data Capture.  
  
## <a name="in-this-section"></a>Nesta seção  
 [cdc.<capture_instance>_CT](../../relational-databases/system-tables/cdc-capture-instance-ct-transact-sql.md)  
 Retorna uma linha para cada alteração feita em uma coluna capturada na tabela de origem associada.  
  
 [cdc.captured_columns](../../relational-databases/system-tables/cdc-captured-columns-transact-sql.md)  
 Retorna uma linha para cada coluna rastreada em uma instância de captura.  
  
 [cdc.change_tables](../../relational-databases/system-tables/cdc-change-tables-transact-sql.md)  
 Retorna uma linha para cada tabela de alteração do banco de dados.  
  
 [cdc.ddl_history](../../relational-databases/system-tables/cdc-ddl-history-transact-sql.md)  
 Retorna uma linha para cada alteração de linguagem de definição de dados (DDL) feita nas tabelas que estão habilitadas para captura de dados de alteração.  
  
 [cdc.lsn_time_mapping](../../relational-databases/system-tables/cdc-lsn-time-mapping-transact-sql.md)  
 Retorna uma linha para cada transação que tem linhas em uma tabela de alteração. Esta tabela é usada para mapear entre os valores confirmados de LSN (número de sequência de log) e a hora em que a transação foi confirmada.  
  
 [cdc.index_columns](../../relational-databases/system-tables/cdc-index-columns-transact-sql.md)  
 Retorna uma linha para cada coluna de índice associada a uma tabela de alteração.  
  
 [cdc_jobs &#40;Transact-SQL&#41;](../../relational-databases/system-tables/dbo-cdc-jobs-transact-sql.md)  
 Retorna os parâmetros de configuração para trabalhos de agente Change Data Capture.  
  
## <a name="see-also"></a>Consulte também  
 [Procedimentos armazenados de captura de dados de alterações &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/change-data-capture-stored-procedures-transact-sql.md)   
 [Alterar funções de captura de dados &#40;Transact-SQL&#41;](../../relational-databases/system-functions/change-data-capture-functions-transact-sql.md)  
  
  
