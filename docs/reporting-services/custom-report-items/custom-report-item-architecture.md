---
title: Arquitetura de item de relatório personalizado | Microsoft Docs
ms.date: 03/03/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: custom-report-items
ms.topic: reference
helpviewer_keywords:
- custom report items, architecture
ms.assetid: 2a88ea46-c9f8-4dd7-aad1-16de11da4f06
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 2c9cf8ad14706b3e344ff6810bfae3ce84af2c32
ms.sourcegitcommit: 1ab115a906117966c07d89cc2becb1bf690e8c78
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/27/2018
ms.locfileid: "52395394"
---
# <a name="custom-report-item-architecture"></a>Arquitetura de item de relatório personalizado
  Um item de relatório personalizado é uma extensão da linguagem RDL que permite que desenvolvedores adicionem funcionalidade que não tem suporte nativo na RDL ou estendam a funcionalidade de controles existentes. Existem dois componentes principais para um item de relatório personalizado: o componente de tempo de execução e o componente tempo de design. Esses componentes são implementados como assemblies [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] e podem ser escritos em qualquer linguagem em conformidade com CLS.  
  
## <a name="the-run-time-component"></a>O componente de tempo de execução  
 O componente de tempo de execução para um item de relatório personalizado é chamado em tempo de execução pelo processador de relatório. O componente de tempo de execução aceita dados passados pelo processador de relatório em tempo de execução, processa seus dados e retorna uma imagem com o item de relatório personalizado renderizado.  
  
 ![Componente de item de relatório personalizado em tempo de execução](../../reporting-services/custom-report-items/media/customreportitemrun-timecomponentarchitecture.gif "Componente de item de relatório personalizado em tempo de execução")  
  
## <a name="the-design-time-component"></a>O componente de tempo de design  
 O componente de tempo de design permite que o item de relatório personalizado seja definido e manipulado na interface do Designer de Relatórios em [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. O componente de tempo de design consiste em vários subcontroles que controlam a aparência e as propriedades do item de relatório personalizado no ambiente de design.  
  
 ![Componente de item de relatório personalizado em tempo de design](../../reporting-services/custom-report-items/media/customreportitemdesign-timecomponentarchitecture.gif "Componente de item de relatório personalizado em tempo de design")  
  
## <a name="see-also"></a>Consulte Também  
 [Criando um componente de item de relatório personalizado em tempo de execução](../../reporting-services/custom-report-items/creating-a-custom-report-item-run-time-component.md)   
 [Criando um componente de item de relatório personalizado em tempo de design](../../reporting-services/custom-report-items/creating-a-custom-report-item-design-time-component.md)   
 [Como implantar um item de relatório personalizado](../../reporting-services/custom-report-items/how-to-deploy-a-custom-report-item.md)  
  
  
