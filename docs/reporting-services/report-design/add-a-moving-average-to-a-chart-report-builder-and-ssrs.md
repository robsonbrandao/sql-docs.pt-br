---
title: Adicionar uma média móvel a um gráfico (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.date: 03/03/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.technology: report-design
ms.topic: conceptual
ms.assetid: 166cf9c1-0750-4866-8381-542e4fbfe65a
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 7131bbd8f325deea3ef34c0f7e45bebfb7f3688a
ms.sourcegitcommit: 31800ba0bb0af09476e38f6b4d155b136764c06c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56298375"
---
# <a name="add-a-moving-average-to-a-chart-report-builder-and-ssrs"></a>Adicionar uma média móvel a um gráfico (Construtor de Relatórios e SSRS)
Uma média móvel é uma média dos dados na série, calculada em um período de tempo definido. Em relatórios paginados do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , a média móvel pode ser mostrada no gráfico para identificar tendências significativas.  

![report-builder-column-chart-tutorial](../../reporting-services/media/report-builder-column-chart-tutorial.png)
  
 A fórmula Média Móvel é o indicador de preço mais popular usado em análises técnicas. Muitas outras fórmulas, incluindo desvio médio, mediano e padrão, também podem ser derivadas de uma série no gráfico. Ao especificar uma média móvel, cada fórmula pode ter um ou mais parâmetros que devem ser especificados.  
 
 O [Tutorial: Adicionar um gráfico de colunas ao relatório (Construtor de Relatórios)](Tutorial:%20Add%20a%20Column%20Chart%20to%20Your%20Report%20\(Report%20Builder\).md) orienta sobre a adição de uma média móvel a um gráfico, caso você deseje testá-lo com os dados de exemplo.
  
 Quando uma fórmula de média móvel é adicionada em Modo de design, a série de linhas adicionada é apenas um espaço reservado visual. O gráfico calcula os pontos de dados de cada fórmula durante o processamento de relatório.  
  
 O suporte interno para linhas de tendência não está disponível no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="to-add-a-calculated-moving-average-to-a-series-on-the-chart"></a>Para adicionar uma média móvel calculada a uma série no gráfico  
  
1.  Clique com o botão direito do mouse na área **Valores** e clique em **Adicionar Série Calculada**. A caixa de diálogo **Propriedades da Série Calculada** é exibida.  
  
2.  Selecione a opção **Média Móvel** na lista suspensa **Fórmula** .  
  
3.  Especifique um valor inteiro para o **Período** que representa o período da média móvel.  
  
    > [!NOTE]  
    >  O período é o número de dias usado para calcular uma média móvel. Se os valores de data/hora não forem especificados no eixo x, o período será representado pelo número de pontos de dados usados para calcular uma média móvel. Se houver apenas um ponto de dados, a fórmula da média móvel não será calculada. A média móvel é calculada a partir do segundo ponto. Se a opção **Iniciar no primeiro ponto** estiver especificada, o gráfico iniciará a média móvel no primeiro ponto. Se houver apenas um ponto de dados, o ponto na média móvel calculada será idêntico ao primeiro ponto na série original.  
  
## <a name="see-also"></a>Consulte Também  
* [Tutorial: Adicionar um gráfico de colunas ao relatório (Construtor de Relatórios)](Tutorial:%20Add%20a%20Column%20Chart%20to%20Your%20Report%20\(Report%20Builder\).md)
*  [Formatar um gráfico &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/formatting-a-chart-report-builder-and-ssrs.md)   
*  [Gráficos &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)   
*  [Adicionar pontos vazios a um gráfico &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/add-empty-points-to-a-chart-report-builder-and-ssrs.md)  
  
  
