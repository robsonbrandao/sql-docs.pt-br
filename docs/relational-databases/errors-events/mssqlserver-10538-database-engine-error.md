---
title: MSSQLSERVER_10538 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 10538 (Database Engine error)
ms.assetid: 284d19b4-4979-4cbe-a9be-ac1104433c69
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 163dd6e764f061e936f32fd530ca4c1b5a13421d
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47619654"
---
# <a name="mssqlserver10538"></a>MSSQLSERVER_10538
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|10538|  
|Origem do evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|PG_INVALID_PLANGUIDE_HANDLE|  
|Texto da mensagem|Não foi possível encontrar o guia de plano porque a ID do guia de plano especificada é NULL ou inválida ou você não tem permissão no objeto referenciado pelo guia de plano. Verifique se a ID do guia de plano é válida, se a sessão atual está definida com o contexto de banco de dados correto e se você tem a permissão ALTER DATABASE ou ALTER no objeto referenciado pelo guia de plano.|  
  
## <a name="explanation"></a>Explicação  
A ID do plano de guia especificado é NULL ou inválida ou você não tem permissão no objeto referenciado pelo guia de plano.  
  
## <a name="user-action"></a>Ação do usuário  
Verifique se a ID do guia de plano é válida, se a sessão atual está definida com o contexto de banco de dados correto e se você tem a permissão ALTER DATABASE ou ALTER no objeto referenciado pelo guia de plano.  
  
## <a name="see-also"></a>Consulte Também  
[sp_create_plan_guide &#40;Transact-SQL&#41;](~/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql.md)  
[Guias de plano](~/relational-databases/performance/plan-guides.md)  
[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](~/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql.md)  
  
