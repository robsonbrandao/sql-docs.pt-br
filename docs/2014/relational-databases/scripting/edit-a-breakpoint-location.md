---
title: Editar um local de ponto de interrupção | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint location
ms.assetid: 5c28e411-0377-4210-a7ce-2a5c13dcdf74
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 36833c6eb5fc588edb2d12716ba439140b8a1cbe
ms.sourcegitcommit: 40c3b86793d91531a919f598dd312f7e572171ec
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "53327327"
---
# <a name="edit-a-breakpoint-location"></a>Editar um local de ponto de interrupção
  O local do ponto de interrupção especifica a linha e o caractere em que o ponto de interrupção reside em um arquivo de script [!INCLUDE[tsql](../../includes/tsql-md.md)] . Você pode editar o local do ponto de interrupção para movê-lo para outro local no script ou para outro script.  
  
## <a name="editing-a-location"></a>Editando um local  
 Quando você edita um local de ponto de interrupção, ele se move para o novo local, levando consigo todas as propriedades existentes, como contagem de ocorrências ou condição.  
  
#### <a name="to-edit-a-breakpoint-location"></a>Para editar um local de ponto de interrupção  
  
1.  Na janela do editor, clique com o botão direito do mouse no glifo do ponto de interrupção e clique em **Local** no menu de atalho.  
  
     -ou-  
  
     Na janela **Pontos de Interrupção** , clique com o botão direito do mouse no glifo do ponto de interrupção e clique em **Local** no menu de atalho.  
  
2.  Na caixa de diálogo **Ponto de Interrupção de Arquivo** , edite **Arquivo** para especificar um novo arquivo, **Linha** para especificar uma nova linha ou **Caractere** para especificar um novo local na linha. Se o novo arquivo especificado já estiver aberto em uma janela do editor de consulta, o ponto de interrupção será movido para essa janela do editor. Se o arquivo não estiver aberto, uma nova janela do editor será aberta, o arquivo será carregado nela e o ponto de interrupção será movido para o novo local.  
  
     A opção **Permitir que o código-fonte seja diferente da versão original** não tem efeito durante a depuração de [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
## <a name="see-also"></a>Consulte também  
 [Especificar uma contagem de ocorrências](specify-a-hit-count.md)   
 [Especificar uma ação de ponto de interrupção](specify-a-breakpoint-action.md)   
 [Especificar uma condição de ponto de interrupção](specify-a-breakpoint-condition.md)   
 [Especificar um filtro de ponto de interrupção](specify-a-breakpoint-filter.md)  
