---
title: MSpeer_lsns (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSpeer_lsns
- MSpeer_lsns_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSpeer_lsns system table
ms.assetid: 0ba33907-601b-4c3d-8099-2663f680a161
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 08926758b2d217bde6f858405ebde1c2b38b4d66
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52796168"
---
# <a name="mspeerlsns-transact-sql"></a>MSpeer_lsns (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  O **Mspeer_lsns** tabela é usada para mapear cada transação para uma assinatura em uma topologia de replicação ponto a ponto. Essa tabela é armazenada em cada banco de dados de publicação em uma topologia de replicação ponto a ponto, e no banco de dados de assinatura de todos os Assinantes de uma publicação ponto a ponto. Para obter mais informações sobre esse tipo de topologia de replicação transacional, consulte [a replicação transacional ponto a ponto](../../relational-databases/replication/transactional/peer-to-peer-transactional-replication.md). Essa tabela é armazenada no banco de dados de publicação.  
  
## <a name="definition"></a>Definição  
  
|Nome da coluna|Tipo de dados|Descrição|  
|-----------------|---------------|-----------------|  
|**id**|**int**|Identifica um LSN ponto a ponto.|  
|**last_updated**|**datetime**|O **datetime** no qual foi feita a última atualização de linha.|  
|**originator**|**sysname**|O nome do Publicador que originou a transação.|  
|**originator_db**|**sysname**|O nome do banco de dados de origem da transação.|  
|**originator_publication**|**sysname**|O nome da publicação de origem da transação.|  
|**originator_publication_id**|**int**|O identificador da publicação de origem da transação.|  
|**originator_db_version**|**int**|Identifica o número da versão do banco de dados de origem.|  
|**originator_lsn**|**int**|Identifica o LSN na publicação de origem.|  
|**originator_version**|**int**|Identifica o número da versão do Publicador.|  
|**originator_id**|**smallint**|Identifica cada nó na topologia com a finalidade de detecção de conflito. Para obter mais informações, consulte [Conflict Detection in Peer-to-Peer Replication](../../relational-databases/replication/transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md).|  
  
## <a name="see-also"></a>Consulte também  
 [Tabelas de replicação &#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Exibições de replicação &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
