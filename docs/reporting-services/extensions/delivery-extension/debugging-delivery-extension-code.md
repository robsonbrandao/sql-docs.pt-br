---
title: Depurando o código de extensão de entrega | Microsoft Docs
ms.date: 03/16/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: extensions
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], debugging
- debugging delivery extensions [Reporting Services]
- troubleshooting [Reporting Services], delivery extensions
ms.assetid: a7d959da-5005-4a50-aca7-2cef36aa9947
author: markingmyname
ms.author: maghan
ms.openlocfilehash: c6a7bb7b306b3e00d0ed45aa03d42cf4637c4708
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47709030"
---
# <a name="debugging-delivery-extension-code"></a>Depurando o código de extensão de entrega
  O [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] fornece várias ferramentas de depuração que podem ajudar você a analisar seu código de extensão de entrega e localizar erros nele. A ferramenta mais adequada dependerá do que você está tentando realizar. Este exemplo usa o [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].  
  
#### <a name="to-debug-your-delivery-extension-code"></a>Para depurar seu código de extensão de entrega  
  
1.  Inicie o [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] e abra o projeto de extensão de entrega.  
  
2.  Crie o projeto e implante o seu assembly de extensão de entrega e o arquivo .pdb que o acompanha no servidor de relatório e no Gerenciador de Relatórios. Para obter mais informações sobre a implantação, consulte [Implantando uma extensão de entrega](../../../reporting-services/extensions/delivery-extension/deploying-a-delivery-extension.md).  
  
3.  Se você escreveu uma interface do usuário de assinatura para estender o Gerenciador de Relatórios, abra o Internet Explorer e navegue até o Gerenciador de Relatórios deixando o seu código de extensão de entrega aberto no [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]. Se você não possui uma interface do usuário de assinatura implantada para o Gerenciador de Relatórios, basta abrir o aplicativo cliente, de onde chamará a sua extensão de entrega usando a API SOAP.  
  
4.  Navegue até o [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] e até o seu projeto de extensão de entrega e defina alguns pontos de quebra em seu código.  
  
5.  Com o projeto de extensão de entrega ainda na janela ativa, clique em **Anexar ao Processo** no menu **Depurar**.  
  
     A caixa de diálogo **Anexar ao Processo** será aberta.  
  
6.  Na lista de processos, selecione o processo aspnet_wp.exe (ou w3wp.exe, se o aplicativo tiver sido implantado no IIS 6.0) e clique em **Anexar**.  
  
7.  Defina uma assinatura nova usando a sua extensão de entrega. É bem provável que você use o Gerenciador de Relatórios ou a API SOAP. Isso deve chamar o depurador e executar o código correspondente a seus pontos de quebra.  
  
8.  Percorra o código usando a tecla **F11**. Para obter mais informações sobre como usar o [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] para depuração, consulte a documentação do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
## <a name="see-also"></a>Consulte Também  
 [Implementando uma extensão de entrega](../../../reporting-services/extensions/delivery-extension/implementing-a-delivery-extension.md)   
 [Biblioteca de extensões do Reporting Services](../../../reporting-services/extensions/reporting-services-extension-library.md)  
  
  
