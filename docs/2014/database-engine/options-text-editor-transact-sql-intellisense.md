---
title: Opções (Editor de texto-Transact-SQL – IntelliSense) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.SQL.Advanced
- VS.ToolsOptionsPages.Text_Editor.SQL_Server_Tools.Advanced
dev_langs:
- TSQL
ms.assetid: 1855d916-5bf9-4d94-b0fb-9f9bb05ff950
author: craigg-msft
ms.author: craigg
manager: craigg
ms.openlocfilehash: 5472e7d0c910c03f49425c263293fd721320eba9
ms.sourcegitcommit: 31c8f9eab00914e056e9219093dbed1b0b4542a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2019
ms.locfileid: "55484625"
---
# <a name="options-text-editor-transact-sql-intellisense"></a>Opções (Editor de texto-Transact-SQL – IntelliSense)
  A caixa de diálogo **Opções** permite que você altere as configurações do IntelliSense para o Editor de Consultas [!INCLUDE[ssDE](../includes/ssde-md.md)]. Essas configurações estão disponíveis quando, no menu **Ferramentas**, você clica em **Opções**, expande a pasta **Editor de Texto**, expande a pasta **Transact-SQL** e, em seguida, clica em **Avançado**.  
  
## <a name="transact-sql-intellisense-settings"></a>Configurações do IntelliSense do Transact-SQL  
 Especifica as opções do IntelliSense para o Editor de Consultas [!INCLUDE[ssDE](../includes/ssde-md.md)].  
  
### <a name="enable-intellisense"></a>Habilitar o IntelliSense  
 Habilita os recursos do IntelliSense. Quando esta caixa não estiver selecionada, as opções do IntelliSense específicas ficarão indisponíveis. Por padrão, esta caixa é selecionada.  
  
 **Sublinhar erros**  
 Identifica erros de sintaxe e de semântica em instruções [!INCLUDE[tsql](../includes/tsql-md.md)] na janela de consulta. Todos os erros e avisos aparecem em vermelho. Só há suporte para erros e avisos nas instruções [!INCLUDE[tsql](../includes/tsql-md.md)] para as quais o IntelliSense foi implementado. Por padrão, esta caixa é selecionada.  
  
 **Estrutura de tópicos de instruções**  
 Habilita o recurso de estrutura de tópicos quando um arquivo é aberto. Isso cria blocos recolhíveis de código [!INCLUDE[tsql](../includes/tsql-md.md)] . Por padrão, esta caixa é selecionada.  
  
 **Tamanho máximo de script**  
 Especifica o tamanho no qual a funcionalidade IntelliSense é desabilitada. Se um script exceder o tamanho especificado, uma mensagem de aviso será emitida. Todos os recursos do IntelliSense, exceto a codificação de cor, são desabilitados nessa janela do editor. O IntelliSense é habilitado novamente quando texto suficiente é excluído para reduzir o tamanho de script para o limite. A habilitação do IntelliSense para tamanhos de script grandes pode prejudicar o desempenho em computadores lentos. Os tamanhos permitidos são 100 KB, 500 KB, 1 MB, 2 MB e Ilimitado. O padrão é 1 MB.  
  
 **Uso de maiusculas e minúsculas para nomes de funções internas**  
 Especifica se os nomes das funções internas do [!INCLUDE[tsql](../includes/tsql-md.md)] incluídos nas listas de conclusão usam letras maiúsculas, como DATEADD, ou minúsculas, como dateadd. Selecione a opção que atende melhor às convenções de codificação do [!INCLUDE[tsql](../includes/tsql-md.md)] em uso.  
  
## <a name="see-also"></a>Consulte também  
 [Solucionando problemas do IntelliSense &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/troubleshooting-intellisense.md)  
  
  
