---
title: " Página de opções do SQL Server ‒ Ambiente ‒ Inicialização | Microsoft Docs"
ms.date: 11/05/2018
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 87de35c23a89e49f376b41676462dd275f676871
ms.sourcegitcommit: a2be75158491535c9a59583c51890e3457dc75d6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2018
ms.locfileid: "51269460"
---
# <a name="options-environment---startup-page"></a>Opções (Ambiente – página de Inicialização)

[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

Use a caixa de diálogo **Opções** para configurar ações de inicialização do [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], opções gerais de gerenciamento de janelas e outras configurações gerais. No menu **Ferramentas**, clique em **Opções**, expanda a pasta **Ambiente** e clique em **Inicialização**.

## <a name="uielement-list"></a>Lista de elementos de interface do usuário

**Na inicialização**

Selecione a ação a ser executada pelo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] quando for iniciado. As opções são:

- **Abrir Pesquisador de Objetos** solicita uma conexão e abre o Pesquisador de Objetos.

- **Abrir nova janela de consulta** solicita uma conexão e abre o Editor de Consultas SQL.

- **Abrir Pesquisador de Objetos e janela de consulta** solicita uma conexão e, depois, abre o Pesquisador de Objetos e o Editor de Consultas SQL com essa conexão.

- **Abrir Pesquisador de Objetos e Monitor de Atividade**

- **Abrir ambiente vazio** abre o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] sem uma janela do Editor de Consultas SQL e sem conectar o Pesquisador de Objetos com um servidor.

**Ocultar objetos do sistema no Pesquisador de Objetos**

Marque essa caixa de seleção para remover os bancos de dados, tabelas e exibições do sistema e os procedimentos armazenados do sistema da exibição em árvore no Pesquisador de Objetos. As funções e tipos de dados do sistema não são ocultos. Essa opção só se aplica a instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e não afeta servidores já conectados no Pesquisador de Objetos.

## <a name="see-also"></a>Confira também

- [Ajuda de F1 das caixas de diálogo opções](options-dialog-boxes-f1-help.md)
- [Opções (Ambiente – página Geral)](options-environment-general-page.md)
