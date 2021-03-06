---
title: Mover ou excluir um item (Gerenciador de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- moving items
- items [Reporting Services], moving
ms.assetid: 980a66c7-a18b-4af7-8954-45726fa517d6
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 03107ceb9c09cd3a48a0d547882b02b951d4d3c2
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2019
ms.locfileid: "56020147"
---
# <a name="move-or-delete-an-item-report-manager"></a>Mover ou excluir um item (Gerenciador de Relatórios)
  Relatórios e itens de relatório que você publica em um servidor de relatório são armazenados em pastas. Você pode mover itens para uma pasta diferente e as referências a esses itens são mantidas automaticamente pelo servidor de relatório. Antes de excluir um item, verifique se outros itens dependem dele.  
  
## <a name="move-an-item"></a>Mover um item  
 Você pode mover itens do servidor de relatório para locais de pasta diferentes na hierarquia de pastas do servidor de relatório. Quando você move um item, todas as propriedades (inclusive configurações de segurança) são movidas com o item para o novo local. Ao mover uma pasta, todos os itens na pasta são movidos juntos.  
  
 No Gerenciador de Relatórios, os itens que podem ser movidos estão indicados na hierarquia de pasta. A tabela a seguir mostra o ícone para cada item móvel.  
  
|Ícone|Item móvel|  
|----------|-------------------|  
|![Ícone Relatório](../media/hlp-16doc.gif "Ícone Relatório")|Relatório|  
|![Ícone Relatório vinculado](../media/hlp-16linked.gif "Ícone Relatório vinculado")|Relatório vinculado|  
|![Ícone Pasta](../media/hlp-16folder.gif "Ícone Pasta")|Pasta|  
|![Ícone Recurso genérico](../media/hlp-16file.gif "Ícone Recurso genérico")|Recurso genérico|  
|![Ícone Fonte de dados compartilhada](../media/hlp-16datasource.png "Ícone Fonte de dados compartilhada")|Fonte de dados compartilhada|  
||Conjunto de dados compartilhado|  
  
 Nem todos os itens com os quais você trabalha podem ser movidos. Não é possível mover itens associados a um relatório, como assinaturas ou histórico de relatório. Esses itens são movidos com os seus relatórios associados. De maneira semelhante, não é possível mover itens, como agendas compartilhadas, que existem fora da hierarquia de pasta. Não é possível mover itens sem a devida permissão. Permissão para mover um item é concedida quando as tarefas a seguir são selecionadas na atribuição de função para o item em questão: "Gerenciar relatórios," "Gerenciar modelos", "Gerenciam pastas" e "Gerenciar fontes de dados".  
  
#### <a name="to-move-an-item-from-within-the-contents-page"></a>Para mover um item de dentro da página Conteúdo  
  
1.  Iniciar [Gerenciador de relatórios &#40;modo nativo do SSRS&#41;]... / relatório-manager-ssrs-native-mode.md).  
  
2.  No Gerenciador de Relatórios, navegue até a página **Conteúdo** e localize o item que você deseja mover.  
  
3.  Focalize o item e clique na seta do menu suspenso.  
  
4.  No menu suspenso, clique em **Mover**.  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  Para **Localização**, especifique a pasta para a qual você deseja mover o item. É possível digitar o nome de pasta totalmente qualificado ou usar o controle de árvore para navegar até a pasta.  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 Como alternativa, navegue até o objeto que você deseja mover, clique em **Propriedades**e clique em **Mover** na parte superior da página.  
  
## <a name="delete-an-item"></a>Excluir um item  
 Antes de excluir um item, determine se ele é usado por outros itens. Por exemplo, se você excluir uma fonte de dados compartilhada, relatórios e modelos que usam essa fonte de dados não serão mais executados. Se um relatório for excluído, as assinaturas e o histórico de relatórios associados também são excluídos. Para localizar itens dependentes para um item, consulte [página itens dependentes &#40;Gerenciador de relatórios&#41;]... / dependente-itens-página-relatório-manager.md).  
  
#### <a name="to-delete-a-report-or-item"></a>Para excluir um relatório ou item  
  
1.  Iniciar [Gerenciador de relatórios &#40;modo nativo do SSRS&#41;]... / relatório-manager-ssrs-native-mode.md).  
  
2.  No Gerenciador de Relatórios, navegue até a página **Conteúdo** e localize o item que você deseja excluir.  
  
3.  Focalize o item e clique na seta do menu suspenso.  
  
4.  No menu suspenso, clique em **Excluir**.  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 [Página de conteúdo &#40;Gerenciador de relatórios&#41;]... / conteúdo-página de relatório manager.md)   
 [Localizando, exibindo e gerenciando relatórios &#40;Construtor de Relatórios e SSRS&#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
