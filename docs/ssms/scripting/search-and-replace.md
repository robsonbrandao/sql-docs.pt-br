---
title: Pesquisar e substituir | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.technology: scripting
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- match case [SQL Server]
- undo operations
- searches [SQL Server Management Studio]
- replacing text
- quick search and replaces [SQL Server Management Studio]
- Query Editor [SQL Server Management Studio], undo
- Query Editor [SQL Server Management Studio], searching
- regular expressions [SQL Server Management Studio]
- finding text [SQL Server Management Studio]
- text [SQL Server], search and replace operations
- finding [SQL Server Management Studio]
- locating text
- Query Editor [SQL Server Management Studio], replacing text
- Find and Replace dialog box
- wildcard options [SQL Server Management Studio]
- match whole word [SQL Server]
- searches [SQL Server Management Studio], replacing
ms.assetid: 3641c7b3-3e3e-4ddd-af82-c15b50004f94
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: d84304f1ba307a55273ddd24aa11686cbd9743e1
ms.sourcegitcommit: 0638b228980998de9056b177c83ed14494b9ad74
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2018
ms.locfileid: "51642572"
---
# <a name="search-and-replace"></a>Pesquisar e substituir
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
  Há vários modos diferentes de localizar e substituir texto. No menu **Editar** , **Localizar e Substituir** oferece quatro opções: **Localização Rápida**, **Substituição Rápida**, **Localizar nos Arquivos**ou **Substituir nos Arquivos**. Cada uma dessas opções abre versões da caixa de diálogo **Localizar e Substituir** . Você também pode pesquisar sem uma caixa de diálogo usando teclas de atalho de teclado de pesquisa incremental. Essas técnicas permitem que você controle o escopo de localização e substituição, e escolha o método de revisão de correspondências e substituições.  
  
 Você deve considerar os itens a seguir ao localizar e substituir texto:  
  
-   As opções definidas na caixa de diálogo **Localizar e Substituir** afetam todas as pesquisas. Essas opções incluem **Corresponder Maiúsculas e Minúsculas**, **Coincidir palavra inteira**, **Pesquisar para cima**, **Pesquisar texto oculto**, **Curingas**, **Expressões Regulares**, **Procurar em Todos os Documentos Abertos**e **Procurar no Projeto Atual**. Nem todas as opções estão disponíveis em todas as versões da caixa de diálogo **Localizar e Substituir** .  
  
-   **Desfazer** só está disponível para documentos deixados abertos após uma operação de substituição.  
  
-   **Desfazer** para uma operação **Substituir Tudo** que englobe mais de um arquivo é considerada uma ação única em massa em todos os arquivos afetados. Isto é, você não pode desfazer a alteração em alguns arquivos e mantê-la em outros.  
  
 Em geral, não é possível pesquisar itens com exibições gráficas.  
  
## <a name="see-also"></a>Consulte Também  
 [Pesquisar um documento ativo de forma incremental](../../relational-databases/scripting/search-an-active-document-incrementally.md)   
 [Pesquisar documentos interativamente](../../relational-databases/scripting/search-documents-interactively.md)   
 [Pesquisar documentos usando listas de resultados](../../relational-databases/scripting/search-documents-using-results-lists.md)   
 [Pesquisar texto com curingas](../../relational-databases/scripting/search-text-with-wildcards.md)   
 [Pesquisar texto com expressões regulares](../../relational-databases/scripting/search-text-with-regular-expressions.md)  
  
  
