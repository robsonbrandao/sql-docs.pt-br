---
title: Compreender as diferenças entre execução local e remota | Microsoft Docs
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, running
- packages [Integration Services], running
- packages [Integration Services], troubleshooting
ms.assetid: 610ee7d9-4fea-4aba-9395-57add826923b
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: a63be8a6f21ca969ccbeca9576ed3d29b2ec3277
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47843264"
---
# <a name="understanding-the-differences-between-local-and-remote-execution"></a>Compreendendo as diferenças entre execução local e remota
  Desenvolvedores e administradores de pacotes devem ficar atentos às restrições relacionadas ao local de execução de um pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
-   **Um pacote é executado no mesmo computador que o programa que o inicia**. Mesmo quando um programa carrega um pacote que é armazenado remotamente em outro servidor, o pacote é executado no computador local.  
  
-   **Você só pode executar um pacote fora do ambiente de desenvolvimento em um computador que tem o Integration Services instalado**. Você não pode executar pacotes fora do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] em um computador cliente que não tenha o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] instalado, e os termos do seu licenciamento do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] talvez não permitam que você instale o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] em computadores adicionais. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] O [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] é um componente de servidor e não é redistribuível a computadores cliente. Para executar pacotes de um computador cliente, procure iniciá-los de forma a garantir a execução dos pacotes no servidor.  
  
 Para obter mais informações sobre como carregar e executar um pacote salvo, consulte:  
  
-   [Carregar e executar um pacote local programaticamente](../../integration-services/run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md)  
  
-   [Carregar e executar um pacote remoto programaticamente](../../integration-services/run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)  
  
 Para obter mais informações sobre como executar um pacote e carregar sua saída em um programa personalizado, consulte:  
  
-   [Carregar a saída de um pacote local](../../integration-services/run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Carregando e executando um pacote local de forma programática](../../integration-services/run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md)   
 [Carregar e executar um pacote remoto programaticamente](../../integration-services/run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)   
 [Carregar a saída de um pacote local](../../integration-services/run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
