---
title: Importar do Analysis Services (SSAS Tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
ms.assetid: b9a21b23-3a06-4ef8-bc06-9c79cdc54870
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 8a698ddb598c4de51d4c30dde717176027f67e6d
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48130488"
---
# <a name="import-from-analysis-services-ssas-tabular"></a>Importar do Analysis Services (SSAS tabular)
  Este tópico descreve como você pode criar um novo projeto de modelo de tabela importando os metadados de um modelo de tabela existente usando o modelo de projeto Importar do Servidor no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].  
  
## <a name="create-a-new-model-by-importing-metadata-from-an-existing-model-in-analysis-services"></a>Criar um novo modelo com a importação de metadados de um modelo existente no Analysis Services  
 Use o modelo de projeto Importar de Servidor para criar um novo projeto de modelo tabular copiando os metadados de um modelo tabular existente em um servidor do Analysis Services. O novo projeto será criado com as mesmas conexões da fonte de dados, tabelas, relações, medidas, KPIs, funções, hierarquias, perspectivas e partições como o modelo do qual foi importado. Porém, os dados não são copiados do modelo existente para o novo espaço de trabalho modelo. Quando o processo de importação tiver sido concluído, e o novo projeto de modelo criado, você deverá executar um Processar Tudo (Atualizar Tudo) para carregar os dados das fontes de dados no novo banco de dados do espaço de trabalho do projeto do modelo.  
  
#### <a name="to-create-a-new-model-by-importing-metadata-from-an-existing-model"></a>Para criar um novo modelo com a importação de metadados de um modelo existente  
  
1.  No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], no menu **Arquivo** , clique em **Novo**e, em seguida, em **Projeto**.  
  
2.  Na caixa de diálogo **Novo Projeto** , em **Modelos Instalados**, clique em **Business Intelligence**e clique em **Importar de Servidor**.  
  
3.  Em **Nome**, digite um nome para o projeto e especifique um local e um nome para a solução e clique em **OK**.  
  
4.  Na caixa de diálogo **Importar do Analysis Services** , em **Nome do Servidor**, especifique o nome do servidor do Analysis Services que contém os metadados modelo que você deseja importar.  
  
5.  Em **Nome do Banco de Dados**, selecione o banco de dados modelo de tabela que contém os metadados de modelo que você deseja importar e clique em **OK**.  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades do projeto &#40;Tabular do SSAS&#41;](properties-ssas-tabular.md)  
  
  
