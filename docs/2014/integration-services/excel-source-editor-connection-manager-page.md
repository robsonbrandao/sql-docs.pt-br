---
title: Editor de origem do Excel (página Gerenciador de Conexão) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelsourceadapter.connection.f1
helpviewer_keywords:
- Excel Source Editor
ms.assetid: 428e04e0-ad98-45d0-8345-12ec1b67b2eb
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: a247233157dbf83fe29089eff9c67442e00b8809
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48157726"
---
# <a name="excel-source-editor-connection-manager-page"></a>Editor de Origem do Excel (página Gerenciador de Conexões)
  Use o nó **Gerenciador de Conexões** da caixa de diálogo **Editor de Origem do Excel** para selecionar a pasta de trabalho do [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] para a origem que será usada. A origem do Excel lê os dados de uma planilha ou intervalo nomeado em uma pasta de trabalho existente.  
  
> [!NOTE]  
>  O `CommandTimeout` propriedade da origem do Excel não está disponível na **Editor de origem do Excel**, mas pode ser definida usando a **Editor Avançado**. Para obter mais informações sobre esta propriedade, consulte a seção Origem do Excel em [Excel Custom Properties](data-flow/excel-custom-properties.md).  
  
 Para obter mais informações sobre origem do Excel, consulte [Excel Source](data-flow/excel-source.md).  
  
## <a name="static-options"></a>Opções estáticas  
 **Gerenciador de conexões OLE DB**  
 Selecione um gerenciador de conexões do Excel existente na lista ou crie uma nova conexão clicando em **Nova**.  
  
 **Nova**  
 Crie um novo gerenciador de conexões usando a caixa de diálogo **Gerenciador de Conexões do Excel** .  
  
 **Modo de acesso aos dados**  
 Especifique o método para selecionar os dados da origem.  
  
|Valor|Description|  
|-----------|-----------------|  
|Tabela ou exibição|Recupere dados de uma planilha ou intervalo nomeado no arquivo do Excel.|  
|Nome da tabela ou variável do nome de exibição|Especifique a planilha ou o nome do intervalo em uma variável.<br /><br /> **Informações relacionadas:** [Usar variáveis em pacotes](../../2014/integration-services/use-variables-in-packages.md)|  
|Comando SQL|Recupere os dados do arquivo do Excel usando uma consulta SQL. Para obter mais informações sobre a sintaxe da consulta, consulte [Excel Source](data-flow/excel-source.md).|  
|Comando SQL a partir da variável|Especifique o texto da consulta SQL em uma variável.|  
  
 **Visualização**  
 Visualize os resultados usando a caixa de diálogo **Exibição de Dados** . A visualização pode exibir até 200 linhas.  
  
## <a name="data-access-mode-dynamic-options"></a>Opções dinâmicas de modo de acesso aos dados  
  
### <a name="data-access-mode--table-or-view"></a>Modo de acesso aos dados = Tabela ou exibição  
 **Nome da planilha do Excel**  
 Selecione o nome da planilha ou o intervalo nomeado na lista disponível na pasta de trabalho do Excel.  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a>Modo de acesso aos dados = Variável do nome da tabela ou do nome de exibição  
 **Nome da variável**  
 Selecione a variável que contém o nome da planilha ou do intervalo nomeado.  
  
### <a name="data-access-mode--sql-command"></a>Modo de acesso aos dados = Comando SQL  
 **Texto do comando SQL**  
 Insira o texto de uma consulta SQL, crie a consulta clicando em **Construir Consulta**ou procure o arquivo que contém o texto da consulta clicando em **Procurar**.  
  
 **Parâmetros**  
 Se você inseriu uma consulta parametrizada usando ? como um espaço reservado para o parâmetro no texto da consulta, use a caixa de diálogo **Definir Parâmetros da Consulta** para mapear os parâmetros de entrada da consulta para as variáveis do pacote.  
  
 **Build query**  
 Use a caixa de diálogo **Construtor de Consultas** para construir a consulta SQL visualmente.  
  
 **Procurar**  
 Use a caixa de diálogo **Abrir** para localizar o arquivo com contém o texto da consulta SQL.  
  
 **Analisar consulta**  
 Verifique a sintaxe do texto da consulta.  
  
### <a name="data-access-mode--sql-command-from-variable"></a>Modo de acesso aos dados = Comando SQL a partir da variável  
 **Nome da variável**  
 Selecione a variável que contém o texto da consulta SQL.  
  
## <a name="see-also"></a>Consulte também  
 [Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor de origem do Excel &#40;página de colunas&#41;](../../2014/integration-services/excel-source-editor-columns-page.md)   
 [Editor de origem do Excel &#40;página de saída de erro&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md)   
 [Gerenciador de Conexões do Excel](connection-manager/excel-connection-manager.md)   
 [Loop através de arquivos e tabelas do Excel por meio de um contêiner do Loop Foreach](control-flow/foreach-loop-container.md)  
  
  
