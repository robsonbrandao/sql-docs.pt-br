---
title: Adicionar um mapa personalizado a um relatório móvel do Reporting Services | Microsoft Docs
ms.date: 03/01/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: mobile-reports
ms.topic: conceptual
ms.assetid: fd259b95-bb58-4eb1-a436-6aa12fc6f5f2
author: markingmyname
ms.author: maghan
ms.openlocfilehash: eef1a8c7ca2d1a7aaff29e04455f17a7cc236b78
ms.sourcegitcommit: 31800ba0bb0af09476e38f6b4d155b136764c06c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56291254"
---
# <a name="add-a-custom-map-to-a-reporting-services-mobile-report"></a>Adicionar um mapa personalizado a um relatório móvel do Reporting Services
Os mapas personalizados exigem dois arquivos:  
* Um arquivo .SHP para geometrias de forma  
* Um arquivo .DBF para metadados  
  
Leia mais sobre [mapas personalizados nos relatórios móveis do Reporting Services](../../reporting-services/mobile-reports/custom-maps-in-reporting-services-mobile-reports.md).  
  
Armazene os dois arquivos na mesma pasta. Os nomes dos dois arquivos devem corresponder (por exemplo, canada.shp e canada.dbf). Os metadados (arquivos DBF) devem incluir o campo "NOME" com o valor do nome da forma correspondente (chave) a ser usada quando o mapa for populado com dados.   
  
## <a name="load-a-custom-map"></a>Carregar um mapa personalizado  
  
1. Na guia **Layout**, selecione um tipo de mapa: **Mapa de Calor de Gradiente**, **Mapa de Calor de Interrupção de Intervalo**ou **Mapa de Bolhas**, arraste-o para a superfície de design e coloque-o no tamanho desejado.  
  
   ![SSMRP_MapsGallery](../../reporting-services/mobile-reports/media/ssmrp-mapsgallery.png)  
  
2. No modo de exibição **layout** > no painel **Propriedades Visuais** > **Mapa**, escolha **Personalizar Mapa a partir do Arquivo**.   
  
   ![SSMRP_SelectCustomMap](../../reporting-services/mobile-reports/media/ssmrp-selectcustommap.png)  
  
3. Na caixa de diálogo **Abrir** , navegue até o local dos arquivos SHP e DBF e selecione os dois.   
  
   ![SSMRP_SelectDBFandSHP](../../reporting-services/mobile-reports/media/ssmrp-selectdbfandshp.png)  
  
## <a name="connect-data-to-a-custom-map"></a>Conectar os dados a um mapa personalizado  
Quando você adiciona primeiro o mapa personalizado ao relatório, o [!INCLUDE[SS_MobileReptPub_Short](../../includes/ss-mobilereptpub-short.md)] preenche-o com dados de geografia simulada.  
  
![SSMRP_MapsData](../../reporting-services/mobile-reports/media/ssmrp-mapsdata.png)  
  
Exibir dados reais em seu mapa personalizado é o mesmo que exibir dados nos mapas internos. Siga as etapas em [Mapas nos relatórios móveis do Reporting Services](../../reporting-services/mobile-reports/maps-in-reporting-services-mobile-reports.md) para exibir seus dados.  
  
### <a name="see-also"></a>Confira também  
- [Custom maps in Reporting Services mobile reports](../../reporting-services/mobile-reports/custom-maps-in-reporting-services-mobile-reports.md)  
- [Mapas nos relatórios móveis do Reporting Services](../../reporting-services/mobile-reports/maps-in-reporting-services-mobile-reports.md)  
- [Criar e publicar relatórios móveis com o Publicador de Relatórios Móveis do SQL Server](../../reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher.md)   
  
  
  
  
