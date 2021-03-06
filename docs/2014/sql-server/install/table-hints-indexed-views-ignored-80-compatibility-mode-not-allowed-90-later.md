---
title: Indexado de dicas de tabela na exibição de definições são ignoradas no modo de compatibilidade 80 e não são permitidas no modo 90 ou posterior | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- query hints [SQL Server]
- indexed views [SQL Server], query hints
ms.assetid: 405dfcff-a3a6-4e6d-a53a-ed77bbacdd13
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: bf4f8e5c3ea23b1ab52199c884c2980bf52bc983
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48160046"
---
# <a name="table-hints-in-indexed-view-definitions-are-ignored-in-80-compatibility-mode-and-are-not-allowed-in-90-mode-or-later"></a>Dicas de tabelas em definições de exibição indexada são ignoradas no modo de compatibilidade 80 e não são permitidas no modo de compatibilidade 90 ou posterior
  As dicas de tabelas presentes em definições de exibição indexadas não são permitidas no modo de compatibilidade 90 ou posterior. Para obter mais informações, consulte os seguintes tópicos nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: ‘Projetando exibições indexadas’, ‘Criando exibições indexadas’ e ‘Dica de consulta ([!INCLUDE[tsql](../../includes/tsql-md.md)])’.  
  
## <a name="component"></a>Componente  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a>Ação corretiva  
 As dicas de tabelas devem ser removidas das definições de exibição indexadas. Independentemente do modo de compatibilidade usado, recomendamos que você teste o aplicativo. Ao fazer isso, você se certifica de que ele está executando de forma adequada durante a criação, a atualização e o acesso a exibições indexadas, inclusive quando há correspondência entre exibições indexadas e consultas.  
  
## <a name="see-also"></a>Consulte também  
 [Problemas de atualização de mecanismo de banco de dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md)   
 [Supervisor de atualização do SQL Server 2014 &#91;novo&#93;](/sql/2014/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
