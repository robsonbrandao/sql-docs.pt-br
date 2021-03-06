---
title: Processar dados (SSAS Tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
ms.assetid: d88f2dc9-2933-4be5-9bf3-48ffbc2d0a1a
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: c3f47ddcfab5df43104d3998822fdaf8bd504946
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48048426"
---
# <a name="process-data-ssas-tabular"></a>Processar dados (SSAS tabular)
  Ao importar dados para um modelo de tabela, no modo Cache, você está capturando um instantâneo desses dados no momento da importação. Em alguns casos, esses dados podem nunca serem alterados e não precisam ser atualizados no modelo. Porém, é mais provável que os dados de que você está importando sejam alterados regularmente. Para que seu modelo reflita os dados mais recentes das fontes de dados, é necessário processar (atualizar) os dados e recalcular os dados calculados. Para atualizar os dados em seu modelo, você executa uma ação de processo em todas as tabelas, em uma tabela individual, por uma partição, ou por uma conexão da fonte de dados.  
  
 Ao criar seu projeto de modelo, inicie as ações de processamento manualmente no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]. Após a implantação de um modelo, as operações de processamento podem ser executadas usando o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ou programadas usando um script. As tarefas descritas aqui todas pertencem a ações de processo que você pode fazer durante a criação do modelo no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]. Para obter mais informações sobre ações de processo para um modelo implantado, consulte [Process Database, Table, or Partition](tabular-models/process-database-table-or-partition-analysis-services.md).  
  
## <a name="related-tasks"></a>Related Tasks  
  
|Tópico|Description|  
|-----------|-----------------|  
|[Processar manualmente dados de &#40;Tabular do SSAS&#41;](manually-process-data-ssas-tabular.md)|Descreve como processar manualmente dados de espaço de trabalho modelo.|  
|[Solucionar problemas de dados de processo &#40;Tabular do SSAS&#41;](troubleshoot-process-data-ssas-tabular.md)|Descreve como solucionar problemas de operações de processo.|  
  
  
