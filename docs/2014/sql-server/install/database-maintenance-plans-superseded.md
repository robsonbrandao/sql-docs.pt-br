---
title: Planos de manutenção substituídos de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- suspended database maintenance plans
- database maintenance plans [SQL Server Agent]
- maintenance plans [SQL Server Agent]
ms.assetid: efac127c-6c81-4c7a-a6c4-9aae5d15545d
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 769bc3ad8b330afd81b14aed1340a67c1d7812ef
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48181436"
---
# <a name="database-maintenance-plans-superseded"></a>Planos de manutenção de banco de dados substituídos
    
## <a name="component"></a>Componente  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent  
  
## <a name="description"></a>Description  
 Os planos de manutenção de banco de dados são atualizados e continuam a funcionar. Porém, você não poderá criar novos planos de manutenção de banco de dados usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]. Para exibir os planos de manutenção no Pesquisador de Objetos, expanda Gerenciamento e, em seguida, Herdado. Você pode migrar planos de manutenção de banco de dados existente para o novo formato, selecionando **Migrate** no menu de contexto para qualquer plano de manutenção de banco de dados. Como o novo recurso de plano de manutenção não é uma substituição direta para os planos de manutenção de banco de dados, existe a possibilidade de perder algumas funcionalidades após a migração. A migração de um plano de manutenção de banco de dados não exclui o plano anterior, portanto você pode testar sua funcionalidade como um plano de manutenção antes de remover o plano anterior.  
  
 Não há mais suporte para os seguintes recursos dentro dos planos de manutenção de banco de dados:  
  
-   Envio de logs  
  
-   O **tentar reparar problemas menores** opção do **verificação de integridade do banco de dados** tarefa  
  
## <a name="corrective-action"></a>Ação corretiva  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] impede que o envio de logs seja incluído em um plano de manutenção do banco de dados. Para obter mais informações, consulte o tópico ‘Envio de logs’ nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
  
