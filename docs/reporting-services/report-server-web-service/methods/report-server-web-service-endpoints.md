---
title: "Relatórios de pontos de extremidade de serviço do servidor Web | Microsoft Docs"
ms.custom: 
ms.date: 03/03/2017
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
- management endpoints [Reporting Services]
- Web service [Reporting Services], endpoints
- endpoints [Reporting Services]
- execution endpoints [Reporting Services]
- Report Server Web service, endpoints
ms.assetid: f3f5d85f-9359-4508-bc5a-7f78a3cf7421
caps.latest.revision: 26
author: sabotta
ms.author: carlasab
manager: erikre
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: 2a0c98cd0c45fc7121a93a51e623dcd2bf36d8bf
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017

---
# <a name="report-server-web-service-endpoints"></a>Pontos de extremidade do serviço Web Servidor de Relatórios
  O serviço Web Servidor de Relatórios fornece vários pontos de extremidade para gerenciar um servidor de relatório como também executar relatórios e navegar neles.  
  
## <a name="the-management-endpoints"></a>Pontos de extremidade de gerenciamento  
 Existem três pontos de extremidade disponíveis para o gerenciamento de objetos em um servidor de relatório: <xref:ReportService2005>, <xref:ReportService2006> e <xref:ReportService2010>. O ponto de extremidade <xref:ReportService2005> é usado para gerenciar objetos em um servidor de relatório que está configurado para o modo nativo. O ponto de extremidade <xref:ReportService2006> é usado para gerenciar objetos em um servidor de relatório que está configurado para o modo integrado do SharePoint. O ponto de extremidade <xref:ReportService2010> mescla as funcionalidades do <xref:ReportService2005> e do <xref:ReportService2006> e pode gerenciar objetos em um servidor de relatório configurado para modo nativo ou integrado do SharePoint.  
  
> [!IMPORTANT]  
>  Quando um servidor de relatório está configurado para modo integrado do SharePoint, o <xref:ReportService2005> APIs retornarão um **rsOperationNotSupportedSharePointMode** erro. Se o servidor de relatório estiver configurado para modo nativo, o <xref:ReportService2006> APIs retornarão um **rsOperationNotSupportedNativeMode** erro. Da mesma forma, quando APIs específicas ao modo no <xref:ReportService2010> forem usadas em modos sem finalidade, as APIs retornarão os respectivos erros.  
  
> [!NOTE]  
>  Os pontos de extremidade <xref:ReportService2005> e <xref:ReportService2006> foram preteridos no [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)]. O ponto de extremidade <xref:ReportService2010> inclui as funcionalidades dos dois pontos de extremidade e contém recursos de gerenciamento adicionais.  
  
 Se o servidor de relatório estiver configurado para o modo nativo ou o modo integrado do SharePoint, o WSDL do ponto de extremidade de gerenciamento poderá ser acessado por meio de uma das seguintes URLs:  
  
```  
http://<Server Name>/ReportServer/ReportService2010.asmx?wsdl  
```  
  
 Para obter mais informações, consulte [acessando a API SOAP](../../../reporting-services/report-server-web-service/accessing-the-soap-api.md).  
  
## <a name="the-execution-endpoint"></a>Ponto de extremidade de execução  
 O ponto de extremidade do <xref:ReportExecution2005> permite que os desenvolvedores personalizem o processamento e a renderização do relatório de forma mais fácil em um servidor de relatório tanto no modo nativo como no integrado do SharePoint. O ponto de extremidade inclui classes e métodos que existiram em versões anteriores do serviço Web Servidor de Relatórios. Além disso, muitas classes e métodos novos foram adicionados ao serviço Web Servidor de Relatórios que foram expostos por meio do ponto de extremidade de execução.  
  
 O WSDL para o ponto de extremidade de gerenciamento pode ser acessado através desta URL:  
  
```  
http://<Server Name>/ReportServer/ReportExecution2005.asmx?wsdl  
```  
  
 Se o servidor de relatório for configurado para o modo de integração do SharePoint, o WSDL poderá ser acessado por meio da URL a seguir:  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportExecution2005.asmx?wsdl  
```  
  
 Para obter mais informações, consulte [acessando a API SOAP](../../../reporting-services/report-server-web-service/accessing-the-soap-api.md).  
  
## <a name="sharepoint-proxy-endpoints"></a>Pontos de extremidade de proxy do SharePoint  
 Quando um servidor de relatório for configurado para o modo integrado do SharePoint e o Suplemento [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] tiver sido instalado, um conjunto de pontos de extremidade de proxy será instalado no servidor do SharePoint. Os pontos de extremidade de proxy são a API primária para desenvolver soluções de relatório quando um servidor de relatório é configurado para o modo integrado do SharePoint. Quando você estiver desenvolvendo soluções nos pontos de extremidade de proxy, o Suplemento [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] gerenciará a troca de credenciais entre o SharePoint Server e o servidor de relatório no modo de autenticação de conta confiável. Quando você estiver desenvolvendo soluções nos pontos de extremidade do servidor de relatório, o aplicativo de chamada terá que gerenciar a troca de credencial no modo de autenticação de conta confiável. A tabela a seguir lista os pontos de extremidade que são instalados com o Suplemento [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].  
  
|Ponto de extremidade de proxy|Description|  
|--------------------|-----------------|  
|<xref:ReportService2006>|Fornece as APIs para gerenciar um servidor de relatório que é configurado para o modo de integração do SharePoint.<br /><br /> Observação: Esse ponto de extremidade foi preterido no [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)].|  
|<xref:ReportService2010>|Fornece as APIs para gerenciamento de um servidor de relatório configurado para o modo nativo ou o modo integrado do SharePoint.|  
|<xref:ReportExecution2005>|Fornece as APIs para executar relatórios e navegar neles.|  
|<xref:ReportServiceAuthentication>|Fornece as APIs para autenticar os usuários de um servidor de relatório quando o aplicativo Web do SharePoint é configurado para autenticação de formulários.|  
  
 A seguir são apresentadas URLs de exemplo para referenciar os pontos de extremidade de proxy em um site do SharePoint.  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportService2010.asmx  
```  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportExecution2005.asmx  
```  
  
```  
http://<Server Name>/<Site Name>/_vti_bin/ReportServer/ReportServiceAuthentication.asmx  
```  
  
## <a name="see-also"></a>Consulte também  
 [Criando aplicativos que usam o serviço Web e o .NET Framework](../../../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  