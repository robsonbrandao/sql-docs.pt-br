---
title: Compreender as diferenças entre execução local e remota | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
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
ms.openlocfilehash: 0fd5a3c554f9b7621b1acfad2ce16cd638195a50
ms.sourcegitcommit: 334cae1925fa5ac6c140e0b2c38c844c477e3ffb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "53351077"
---
# <a name="understanding-the-differences-between-local-and-remote-execution"></a>Compreendendo as diferenças entre execução local e remota
  Desenvolvedores e administradores de pacotes devem ficar atentos às restrições relacionadas ao local de execução de um pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
-   **Um pacote é executado no mesmo computador que o programa que o inicia**. Mesmo quando um programa carrega um pacote que é armazenado remotamente em outro servidor, o pacote é executado no computador local.  
  
-   **Você só pode executar um pacote fora do ambiente de desenvolvimento em um computador que tem o Integration Services instalado**. Você não pode executar pacotes fora do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] em um computador cliente que não tenha o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] instalado, e os termos do seu licenciamento do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] talvez não permitam que você instale o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] em computadores adicionais. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] O [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] é um componente de servidor e não é redistribuível a computadores cliente. Para executar pacotes de um computador cliente, procure iniciá-los de forma a garantir a execução dos pacotes no servidor.  
  
 Para obter mais informações sobre como carregar e executar um pacote salvo, consulte:  
  
-   [Carregar e executar um pacote local programaticamente](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md)  
  
-   [Carregar e executar um pacote remoto programaticamente](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)  
  
 Para obter mais informações sobre como executar um pacote e carregar sua saída em um programa personalizado, consulte:  
  
-   [Carregar a saída de um pacote local](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
![Ícone do Integration Services (pequeno)](../media/dts-16.gif "ícone do Integration Services (pequeno)")**mantenha-se para cima até o momento com o Integration Services**<br /> Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:<br /><br /> [Visite a página do Integration Services no MSDN](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.  
  
## <a name="see-also"></a>Consulte também  
 [Carregando e executando um pacote local de forma programática](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md)   
 [Carregar e executar um pacote remoto programaticamente](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)   
 [Carregar a saída de um pacote local](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
