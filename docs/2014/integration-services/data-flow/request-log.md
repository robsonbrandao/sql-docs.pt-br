---
title: Log de solicitações | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 165d3833-0493-490c-9f63-8a134a7fafb8
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 958a2990fe3bde49898451c9fefaee74b1b335f8
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52750208"
---
# <a name="request-log"></a>Log de solicitações
  Use a caixa de diálogo **Log de Solicitações** para exibir os eventos que são registrados em log durante a solicitação que é feita no sistema SAP Netweaver BW para dados de exemplo. Essas informações podem ser úteis se você precisar solucionar problemas da configuração da origem do SAP BW.  
  
 Para saber mais sobre o componente de origem do SAP BW do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 para SAP BW, consulte [Origem SAP BW](sap-bw-source.md).  
  
> [!IMPORTANT]  
>  A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW. Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.  
  
> [!IMPORTANT]  
>  A extração de dados do SAP Netweaver BW exige licenciamento SAP adicional. Verifique esses requisitos com a SAP.  
  
 **Para abrir a caixa de diálogo Log de Solicitações**  
  
1.  No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém a origem SAP BW.  
  
2.  Na guia **Fluxo de Dados** , clique duas vezes na fonte SAP BW.  
  
3.  No **Editor de Origem SAP BW**, clique em **Gerenciador de Conexões** para abrir a página **Gerenciador de Conexões** do editor.  
  
4.  Depois de configurar a origem do SAP BW, clique em **Visualizar** para visualizar os eventos na caixa de diálogo **Log de Solicitações** .  
  
    > [!NOTE]  
    >  Clicar em **Visualizar** também abre a caixa de diálogo **Visualizar** . Para obter mais informações sobre essa caixa de diálogo, consulte [Preview](preview.md).  
  
## <a name="options"></a>Opções  
 **Time**  
 Exibe a hora em que o evento foi registrado em log.  
  
 **Tipo**  
 Exibe o tipo do evento que foi registrado em log. A tabela seguinte lista os possíveis tipos de evento.  
  
|Valor|Descrição|  
|-----------|-----------------|  
|P|Mensagem de êxito.|  
|E|Mensagem de erro|  
|L|Mensagem de aviso.|  
|I|Mensagem informativa.|  
|Um|A operação foi anulada.|  
  
 **Mensagem**  
 Exibe o texto da mensagem associada ao evento de log.  
  
## <a name="see-also"></a>Consulte também  
 [Editor de Origem SAP BW &#40;Página Gerenciador de Conexões&#41;](sap-bw-source-editor-connection-manager-page.md)   
 [Ajuda F1 do Microsoft Connector 1.1 para SAP BW](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
