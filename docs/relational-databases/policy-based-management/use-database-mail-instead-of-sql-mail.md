---
title: Usando o Database Mail em vez do SQL Mail | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: b08df7be-d8be-4184-a661-38ec0ac85cd1
author: VanMSFT
ms.author: vanto
manager: craigg
ms.openlocfilehash: 6cba711740695f692f6c5bbca20c19353ef35c5f
ms.sourcegitcommit: ef6e3ec273b0521e7c79d5c2a4cb4dcba1744e67
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51512641"
---
# <a name="use-database-mail-instead-of-sql-mail"></a>Usando o Database Mail em vez do SQL Mail
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Esta regra verifica a exibição do catálogo sys.configurations para determinar se a opção de configuração do servidor do SQL Mail XPs está definida como ON.  
  
## <a name="best-practices-recommendations"></a>Práticas Recomendadas  
 O SQL Mail será removido em uma versão futura do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam. Para enviar email, use o Database Mail.  
  
 O SQL Mail é executado em processo de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Se o SQL Mail ficar inoperante, o servidor também ficará. O Database Mail é executado fora do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em um processo separado, é escalável e não requer a instalação de componentes de cliente MAPI estendido no servidor de produção.  
  
## <a name="for-more-information"></a>Para obter mais informações  
 [Database Mail](../../relational-databases/database-mail/database-mail.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Monitorar e impor práticas recomendadas usando o Gerenciamento Baseado em Políticas](../../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
