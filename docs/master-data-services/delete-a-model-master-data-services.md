---
title: Excluir um modelo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting models [Master Data Services]
- models [Master Data Services], deleting models
ms.assetid: f0ad3cc4-aed7-47c8-94bc-2971fe9fe871
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: c7ae7bce17aad06bf17c8d78d976cdd0ef518bad
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52796409"
---
# <a name="delete-a-model-master-data-services"></a>Excluir um modelo (Master Data Services)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  Exclua um modelo para removê-lo juntamente com todos os seus dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].  
  
> [!NOTE]  
>  Quando esse procedimento estiver concluído, todos os objetos e dados de todas as versões do modelo serão excluídos permanentemente.  
  
## <a name="prerequisites"></a>Prerequisites  
 Para executar esse procedimento:  
  
-   Você deve ter permissão para acessar a área funcional **Administração do Sistema** .  
  
-   Você deve ser um administrador de modelo. Para obter mais informações, veja [Administradores &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
### <a name="to-delete-a-model"></a>Para excluir um modelo  
  
1.  No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.  
  
2.  Na página **Exibição de Modelo** , na barra de menus, aponte para **Gerenciar** e clique em **Modelos**.  
  
3.  Na página **Gerenciar Modelos** , na grade, selecione a linha do modelo que você deseja excluir.  
  
4.  Clique em **Excluir**.  
  
5.  Na caixa de diálogo de confirmação, clique em **OK**.  
  
6.  Na caixa de diálogo de confirmação adicional, clique em **OK**.  
  
 A coluna **Status** na grade mostra o status da operação no modelo. Quando você clica no botão **Salvar modelo**, a imagem ![Atualizando](../master-data-services/media/mds-model-status-updating.png "Atualizando") é exibida, indicando que o modelo está sendo atualizando. Se houver erros ao criar ou editar um modelo, a imagem ![Erro](../master-data-services/media/mds-model-status-error.png "Erro") será exibida. Caso contrário, o status será OK e a imagem ![OK](../master-data-services/media/mds-model-status-ok.png "OK") será exibida.  
  
## <a name="see-also"></a>Consulte Também  
 [Modelos &#40;Master Data Services&#41;](../master-data-services/models-master-data-services.md)   
 [Criar um modelo &#40;Master Data Services&#41;](../master-data-services/create-a-model-master-data-services.md)  
  
  
