---
title: Opções (página Designers – Designers de Tabela e Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Designers.Table_Designer
ms.assetid: b43f4b97-17b9-4004-a824-f77b9e145741
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: fbf35f72721cee361d62ad5b5ac2b6b09c9c58df
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47823134"
---
# <a name="options-designers---table-and-database-designers-page"></a>Opções (Designers – página de Designers de Tabela e Banco de Dados)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
Use esta página para determinar o comportamento padrão do designer. Para acessar as configurações, no menu **Ferramentas** , clique em **Opções**, expanda  a pasta **Designers** e clique em **Designer de Tabela**.  
  
## <a name="uielement-list"></a>Lista de elementos de interface do usuário  
**Substituir valor de tempo limite da cadeia de caracteres da conexão para atualizações do designer de tabela**  
Permite que um novo valor de tempo limite seja definido para ações no designer de tabela. Isso pode ser útil quando o designer de tabela afetar uma tabela grande e requerer tempo extra para concluir a modificação da tabela.  
  
**Tempo limite de transação após**  
Define um valor de tempo limite para o designer de tabela.  
  
**Gerar scripts de alteração automaticamente**  
Cria, automaticamente, um script para implementar as alterações definidas no designer de tabela.  
  
**Avisar sobre chaves primárias nulas**  
Fornece uma caixa de diálogo de aviso quando um campo que é selecionado para uma chave primária puder conter valores nulos.  
  
**Aviso sobre detecção de diferença**  
Se você selecionar esta caixa, uma caixa de mensagens listará qualquer conflito entre suas alterações e as feitas por outro usuário ao salvar alterações.  
  
**Avisar sobre tabelas afetadas**  
Fornece uma caixa de diálogo de aviso que lista as tabelas que serão afetadas pela ação e solicita confirmação.  
  
**Evitar salvar alterações que exijam recriação de tabela**  
Impede um usuário de fazer alterações que requerem recriação de tabela. As ações seguintes poderiam exigir a recriação de uma tabela:  
  
-   Adição de uma nova coluna no meio da tabela  
  
-   Descarte de uma coluna  
  
-   Alteração da nulidade da coluna  
  
-   Alteração da ordem das colunas  
  
-   Alteração do tipo de dados de uma coluna  
  
**Exibição de tabela padrão**  
Selecione o modo que você deseja ver tabelas no designer:  
  
-   **Standard**  
  
    Mostra o cabeçalho, todos os nomes das colunas, os tipos de dados e a configuração Permitir Nulos da tabela.  
  
-   **Nomes de coluna**  
  
    Mostra os nomes das colunas.  
  
-   **Chave**  
  
    Mostra o cabeçalho de tabela e as colunas de chave primária.  
  
-   **Apenas nome**  
  
    Mostra apenas o cabeçalho da tabela com seu nome.  
  
-   **Personalizar**  
  
    Permite que você escolha quais colunas deseja exibir.  
  
**Iniciar diálogo de adição de tabela no novo diagrama**  
Abre automaticamente a caixa de diálogo **Adicionar Tabela** quando os designers são abertos.  
  
