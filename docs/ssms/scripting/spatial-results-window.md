---
title: Janela Resultados Espaciais | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.technology: scripting
ms.reviewer: ''
ms.topic: conceptual
ms.assetid: c2d5a477-6496-4d01-adee-7322ebdfadf3
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 422114f2a753327f34b105c4c6893b7c3f8d3c2b
ms.sourcegitcommit: 0638b228980998de9056b177c83ed14494b9ad74
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2018
ms.locfileid: "51642585"
---
# <a name="spatial-results-window"></a>Janela Resultados Espaciais
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
  A janela **Resultados espaciais** fornece ferramentas de mapeamento visuais para exibição de dados espaciais. Para exibir resultados espaciais, os resultados da consulta devem incluir uma coluna espacial com dados de geometria ou de geografia.  
  
> [!NOTE]  
>  A janela **Resultados espaciais** estará disponível apenas se os resultados forem retornados para uma grade na janela **Resultados** . Se você especificar que os resultados são retornados como texto, essa janela não estará disponível.  
  
## <a name="options"></a>Opções  
 **Selecionar coluna espacial**  
 Especifique a coluna espacial que você deseja exibir das colunas espaciais dos resultados da consulta. Apenas uma coluna pode ser selecionada por vez.  
  
 **Selecionar coluna de rótulo**  
 Especifique a coluna não espacial das colunas retornadas nos resultados da consulta para rotular os dados espaciais. Apenas uma coluna pode ser selecionada por vez.  
  
 Essa opção não estará disponível quando apenas instâncias de ponto forem retornadas em uma consulta.  
  
 **Selecionar projeção**  
 Exiba dados de geografia em uma de quatro projeções: Cilíndrica equidistante, Mercator, Robinson ou Bonne.  
  
 Essa opção não está disponível para dados de geometria.  
  
 **Zoom**  
 Ajuste a exibição do mapa em uma escala exponencial.  
  
 **Mostrar linhas de grade**  
 Ative ou desative as linhas de grade das coordenadas.  
  
 Para formas de polígono, o rótulo é exibido apenas quando a forma for grande o suficiente para manter o texto do rótulo. Para exibir rótulos para formas pequenas, ajuste o zoom.  
  
> [!NOTE]  
>  Instâncias de ponto não podem ser rotuladas.  
  
## <a name="see-also"></a>Consulte Também  
 [Exibir dados espaciais no Pesquisador de Objetos](../../relational-databases/scripting/view-spatial-data-in-object-explorer.md)   
 [Dados espaciais &#40;SQL Server&#41;](../../relational-databases/spatial/spatial-data-sql-server.md)   
 [Editor de Consultas do Mecanismo de Banco de Dados &#40;SQL Server Management Studio&#41;](../../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md)   
 [Editores de consultas e de texto &#40;SQL Server Management Studio&#41;](../../relational-databases/scripting/query-and-text-editors-sql-server-management-studio.md)  
  
  
