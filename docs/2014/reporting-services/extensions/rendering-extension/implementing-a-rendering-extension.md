---
title: Implementando uma extensão de renderização | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.topic: reference
helpviewer_keywords:
- rendering extensions [Reporting Services]
- custom rendering extensions [Reporting Services]
- transformations [Reporting Services]
- extensions [Reporting Services], rendering
- rendering extensions [Reporting Services], implementing
ms.assetid: 4a5c64f5-2391-4597-ba3f-81d265b23703
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 5efb71a33e1b840eecd4503f47e64d3d661c0101
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2019
ms.locfileid: "56036307"
---
# <a name="implementing-a-rendering-extension"></a>Implementando uma extensão de renderização
  Uma extensão de renderização é um componente ou um módulo de um servidor de relatório que transforma dados de relatório e informações de layout para um formato específico do dispositivo. SQL Server Reporting Services inclui seis extensões de renderização: HTML, Excel, Word, CSV ou texto, XML, imagem e PDF. Você pode criar extensões de renderização adicionais para gerar relatórios em outros formatos.  
  
> [!NOTE]  
>  Para determinar quais extensões de renderização estão disponíveis, exiba a lista das extensões instaladas no arquivo RSReportServer.config.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Visão geral das extensões de renderização](rendering-extensions-overview.md)  
 Introduz como escrever uma extensão de renderização personalizada para o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].  
  
 [Implementar a interface IRenderingExtension](implementing-the-irenderingextension-interface.md)  
 Descreve os atributos de uma extensão de renderização.  
  
 [Implantando uma extensão de renderização](deploying-a-rendering-extension.md)  
 Descreve como implantar uma extensão de renderização em um servidor de relatório.  
  
 [Remover uma extensão de renderização](removing-a-rendering-extension.md)  
 Descreve como remover uma extensão de renderização de um servidor de relatório.  
  
## <a name="see-also"></a>Consulte também  
 [Extensões do Reporting Services](../reporting-services-extensions.md)   
 [Biblioteca de extensões do Reporting Services](../reporting-services-extension-library.md)  
  
  
