---
title: Adicionar assinante não SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.addnonsqlsubscriber.f1
ms.assetid: 21beeaa0-4b9e-48da-be63-1b9ff14e03d2
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: cc291a9677efe2acf875f5b5a37d9153fcb3eee3
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52771998"
---
# <a name="add-non-sql-server-subscriber"></a>Adicionar Assinante não SQL Server
  A replicação oferece suporte à criação de assinaturas push para publicações de instantâneo e transacionais para Assinantes Oracle e IBM DB2.  
  
## <a name="options"></a>Opções  
 **Tipo de Assinante a adicionar**  
 Selecione um Assinante Oracle ou um Assinante IBM DB2. Para obter mais informações sobre o suporte para esses Assinantes, consulte [Assinantes não SQL Server](non-sql/non-sql-server-subscribers.md).  
  
 **Nome da fonte de dados**  
 O nome usado para localizar o banco de dados em uma rede. A replicação produz uma sequência de conexão para o banco de dados usando o nome da fonte de dados, combinando com o logon, senha e qualquer opção de conexão especificada na página **Segurança do Agente de Distribuição** neste assistente.  
  
> [!NOTE]  
>  The data source name and connection string are not validated by [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] until the Distribution Agent attempts to initialize the subscription.  
  
## <a name="see-also"></a>Consulte também  
 [Criar uma assinatura para um assinante não SQL Server](create-a-subscription-for-a-non-sql-server-subscriber.md)   
 [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md)   
 [Assinar publicações](subscribe-to-publications.md)  
  
  
