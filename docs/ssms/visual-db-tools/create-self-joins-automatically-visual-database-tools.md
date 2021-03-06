---
title: Criar autojunções automaticamente (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- automatic joins
- self-joins
- joins [SQL Server], self
ms.assetid: f9ec90e8-3aad-415c-a5c4-8dfa9540e37f
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 0f1d7bdeca1202eb46bf2926d2ddc86855bd5f71
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47652505"
---
# <a name="create-self-joins-automatically-visual-database-tools"></a>Criar autojunções automaticamente (Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
Se uma tabela tiver uma relação reflexiva no banco de dados, a autojunção poderá ocorrer automaticamente.  
  
### <a name="to-create-a-self-join-automatically"></a>Para criar uma autojunção automaticamente  
  
1.  Adicione ao [painel Diagrama](../../ssms/visual-db-tools/diagram-pane-visual-database-tools.md) a tabela com a qual deseja trabalhar.  
  
2.  Adicione a mesma tabela novamente, de forma que seja exibida a mesma tabela duas vezes no painel Diagrama.  
  
    O [Designer de Consulta e Exibição](../../ssms/visual-db-tools/query-and-view-designer-tools-visual-database-tools.md) atribui um alias à segunda instância adicionando um número sequencial ao nome da tabela. Além disso, o Designer de Consulta e Exibição cria uma linha de junção entre os dois retângulos representando dois modos diferentes de participação da tabela na consulta.  
  
## <a name="see-also"></a>Consulte Também  
[Consultar com junções &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/query-with-joins-visual-database-tools.md)  
  
