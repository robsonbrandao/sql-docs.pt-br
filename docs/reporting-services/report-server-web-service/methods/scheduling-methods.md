---
title: "Métodos de agendamento | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- schedules [Reporting Services], methods
- reports [Reporting Services], scheduling
- shared schedules [Reporting Services], methods
- methods [Reporting Services], scheduling
ms.assetid: 68ae13f9-d91e-4572-a82a-8fa42001569e
caps.latest.revision: 35
author: sabotta
ms.author: carlasab
manager: erikre
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: 3c7360e28e7dd59f258fd43aa0440866528b9e32
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017

---
# <a name="scheduling-methods"></a>Métodos de agendamento
  É possível usar esses métodos para criar e gerenciar agendas compartilhadas para execução e entrega de relatório e para planos de atualização do cache utilizados pelo servidor de relatório.  
  
|Método|Ação|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateCacheRefreshPlan%2A>|Cria um plano de atualização do cache para um item.|  
|<xref:ReportService2010.ReportingService2010.CreateSchedule%2A>|Cria uma nova agenda compartilhada.|  
|<xref:ReportService2010.ReportingService2010.DeleteCacheRefreshPlan%2A>|Exclui um plano de atualização do cache.|  
|<xref:ReportService2010.ReportingService2010.DeleteSchedule%2A>|Exclui uma agenda compartilhada com base em uma ID de agenda específica.|  
|<xref:ReportService2010.ReportingService2010.GetCacheRefreshPlanProperties%2A>|Retorna as propriedades do plano de atualização do cache especificado.|  
|<xref:ReportService2010.ReportingService2010.GetScheduleProperties%2A>|Retorna os valores de propriedades de uma agenda compartilhada.|  
|<xref:ReportService2010.ReportingService2010.ListCacheRefreshPlans%2A>|Retorna uma lista dos planos de atualização do cache associados a um item do catálogo.|  
|<xref:ReportService2010.ReportingService2010.ListScheduledItems%2A>|Retorna uma lista de itens associados a uma agenda compartilhada.|  
|<xref:ReportService2010.ReportingService2010.ListSchedules%2A>|Retorna uma lista de todas as agendas compartilhadas no servidor de relatório ou no site do SharePoint.|  
|<xref:ReportService2010.ReportingService2010.ListScheduleStates%2A>|Retorna uma lista de estados de agenda com suporte.|  
|<xref:ReportService2010.ReportingService2010.PauseSchedule%2A>|Pausa a execução de uma determinada agenda.|  
|<xref:ReportService2010.ReportingService2010.ResumeSchedule%2A>|Retoma uma agenda compartilhada que foi pausada.|  
|<xref:ReportService2010.ReportingService2010.SetCacheRefreshPlanProperties%2A>|Define as propriedades de um plano de atualização do cache.|  
|<xref:ReportService2010.ReportingService2010.SetScheduleProperties%2A>|Define o valor de propriedades de uma agenda compartilhada.|  
  
## <a name="see-also"></a>Consulte também  
 [Criando aplicativos que usam o serviço Web e o .NET Framework](../../../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)   
 [Serviço Web servidor de relatório](../../../reporting-services/report-server-web-service/report-server-web-service.md)   
 [Métodos de Web do serviço do servidor de relatório](../../../reporting-services/report-server-web-service/methods/report-server-web-service-methods.md)   
 [Referência técnica &#40; SSRS &#41;](../../../reporting-services/technical-reference-ssrs.md)  
  
  