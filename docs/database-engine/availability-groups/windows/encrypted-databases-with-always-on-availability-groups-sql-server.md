---
title: Adicionar um banco de dados criptografado a um grupo de disponibilidade
description: Etapas para adicionar um banco de dados criptografado (ou recentemente descriptografado) a um grupo de disponibilidade Always On.
ms.custom: seodec18
ms.date: 05/17/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Transparent Data Encryption, AlwaysOn Availability Groups
- TDE, AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 09eb6ebc-3051-4fff-86a5-93524507b1fc
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: bf22a6a15d85f3e5ad6ffc24a9ce371f43b34206
ms.sourcegitcommit: 6443f9a281904af93f0f5b78760b1c68901b7b8d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53215482"
---
# <a name="add-an-encrypted-database-to-an-always-on-availability-group"></a>Adicionar um banco de dados criptografado em um grupo de disponibilidade Always On
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

  Este tópico contém informações sobre como o usar bancos de dados atualmente criptografados ou recentemente descriptografados com o [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].  
  
 **Neste tópico:**  
  
-   [Limitações e restrições](#Restrictions)  
  
-   [Tarefas relacionadas](#RelatedTasks)  
  
##  <a name="Restrictions"></a> Limitações e Restrições  
  
-   Se um banco de dados estiver criptografado ou contiver até mesmo uma DEK (chave de criptografia de banco de dados), você não poderá usar o [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] nem o [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] para adicionar um grupo de disponibilidade. Mesmo se um banco de dados criptografado for descriptografado, seus backups de log poderão conter dados criptografados. Nesse caso, a total sincronização inicial de dados poderia falhar no banco de dados. Isso é porque a operação de log de restauração pode exigir o certificado que foi usado pelas DEKs (chaves de criptografia de banco de dados), e esse certificado pode não estar disponível.  
  
     Para tornar um banco de dados descriptografado elegível para adição a um grupo de disponibilidade usando o assistente:  
  
    1.  Crie um backup de log do banco de dados primário.  
  
    2.  Crie um backup completo do banco de dados primário.  
  
    3.  Restaure o backup do banco de dados na instância de servidor que hospeda a réplica secundária.  
  
    4.  Crie um novo backup de log a partir do banco de dados primário.  
  
    5.  Restaure esse backup de log no banco de dados secundário.  
  
##  <a name="RelatedTasks"></a> Tarefas relacionadas  
  
-   [Preparar um banco de dados secundário manualmente para um grupo de disponibilidade &#40;SQL Server&#41;](../../../database-engine/availability-groups/windows/manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [Usar o Assistente de Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [Usar o Assistente para Adicionar Banco de Dados ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Visão geral dos grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](../../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [TDE &#40;Transparent Data Encryption&#41;](../../../relational-databases/security/encryption/transparent-data-encryption.md)  
  
  
