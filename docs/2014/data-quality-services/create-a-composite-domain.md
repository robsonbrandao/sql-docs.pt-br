---
title: Criar um domínio de composição | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.createcd.f1
- sql12.dqs.dm.cdproperties.f1
ms.assetid: c7f0bd84-a02e-4a81-885d-985e6415c499
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 3cfaf75851b97a8b13856fa8f65aca0bde7e10d1
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2019
ms.locfileid: "56034087"
---
# <a name="create-a-composite-domain"></a>Criar um domínio composto
  Este tópico descreve como criar um domínio composto em uma base de dados de conhecimento no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS). Um domínio composto consiste em um ou mais domínios únicos que se aplicam a um campo de dados único. Para obter mais informações sobre domínios de composição, consulte [Gerenciando um domínio de composição](../../2014/data-quality-services/managing-a-composite-domain.md).  
  
 Há duas maneiras de criar um novo domínio composto. A primeira é durante a etapa Mapear da atividade de descoberta da base de dados de conhecimento, quando você está no processo de analisar um exemplo de dados para adicionar conhecimento a uma base de dados de conhecimento nova ou existente. A segunda é durante a atividade de gerenciamento de domínio, quando, em vez de alterar um domínio existente, você cria um novo domínio. Para criar um domínio composto, você já deve ter criado pelo menos dois domínios únicos para adicionar ao domínio composto. Somente os domínios únicos que já foram criados e não foram adicionados a um domínio composto existente estão disponíveis quando você cria um novo domínio composto. Um domínio único não pode ser adicionado a mais de um domínio composto e um domínio composto não pode ser adicionado a outro domínio composto.  
  
 Depois de criar um domínio composto, você pode alterar as propriedades do domínio composto, associar um serviço de dados de referência ao domínio, criar as regras de domínio cruzado ou criar relações de valor. Para fazer isso, selecione o domínio composto na lista **Domínio** da página **Gerenciamento de Domínio** e selecione a guia apropriada.  
  
##  <a name="BeforeYouBegin"></a> Antes de começar  
  
###  <a name="Prerequisites"></a> Pré-requisitos  
 Para criar um domínio composto, você já deve ter criado e aberto uma base de dados de conhecimento e deve ter criado pelo menos dois domínios únicos para adicionar ao domínio composto.  
  
###  <a name="Security"></a> Segurança  
  
####  <a name="Permissions"></a> Permissões  
 Você deve ter a função dqs_kb_editor ou dqs_administrator no banco de dados DQS_MAIN para criar um domínio composto.  
  
##  <a name="ParsingKnowledgeDiscoveryActivity"></a> Criar um domínio composto na atividade Descoberta da Base de Dados de Conhecimento  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)] [Executar o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).  
  
2.  Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Abrir base de dados de conhecimento** e selecione uma base de dados de conhecimento ou clique em **Nova base de dados de conhecimento** e insira propriedades para a nova base de dados de conhecimento.  
  
3.  Selecione **Descoberta da Base de Dados de Conhecimento** como a atividade e clique em **Criar** para criar a nova base de dados de conhecimento ou em **Abrir** para abrir uma base de dados de conhecimento existente.  
  
4.  Na página **Mapa** , especifique uma conexão com a fonte de dados. Para obter mais informações, consulte [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md).  
  
5.  Na tabela **Mapeamentos** , selecione uma coluna de origem na lista suspensa da coluna **Coluna de Origem** de uma linha vazia. Verifique se a coluna de origem contém o domínio composto endereçado por dois domínios únicos existentes. Se não existir nenhum domínio único correspondente, clique no ícone **Criar um Domínio** .  
  
6.  Na tabela **Mapeamentos** , selecione uma coluna de origem na lista suspensa da coluna **Coluna de Origem** de uma linha vazia. Verifique se a coluna de origem contém as partes do domínio composto que são endereçadas por dois domínios únicos existentes. Se não existir nenhum domínio único correspondente, clique no ícone **Criar um Domínio** para criá-los. Para obter mais informações, consulte [Criar um domínio](../../2014/data-quality-services/create-a-domain.md).  
  
7.  Clique no ícone **Criar um Domínio Composto** .  
  
##  <a name="DomainManagementActivity"></a> Criar um domínio composto na atividade Gerenciamento de Domínio  
  
1.  Na home page do cliente Data Quality Services, clique em **Abrir base de dados de conhecimento** e selecione uma base de dados de conhecimento ou clique em **Nova base de dados de conhecimento** e insira propriedades para a nova base de dados de conhecimento.  
  
2.  Selecione **Gerenciamento de Domínio** como a atividade e clique em **Criar** para criar a nova base de dados de conhecimento ou em **Abrir** para abrir uma base de dados de conhecimento existente.  
  
3.  Verifique se existem dois ou mais domínios únicos necessários para o domínio composto. Se não existirem, clique no ícone **Criar um Domínio** e crie-os. Para obter mais informações, consulte [Criar um domínio](../../2014/data-quality-services/create-a-domain.md).  
  
4.  Na página **Gerenciamento de Domínio** , clique no ícone **Criar um Domínio Composto** acima da lista de domínios.  
  
5.  Insira um nome que seja exclusivo para a base de dados de conhecimento e uma descrição com até 256 caracteres.  
  
6.  Na **Lista de Domínios**, selecione os domínios que farão parte do domínio composto e clique na seta para direita para movê-los para a tabela **Domínios no Domínio Composto** .  
  
7.  Clique em **OK**.  
  
##  <a name="CompositeDomainProperties"></a> Definir as propriedades do domínio composto  
  
1.  Na caixa de diálogo **Criar um Domínio Composto** , insira um nome que seja exclusivo para a base de dados de conhecimento e uma descrição com até 256 caracteres.  
  
2.  Na **Lista de Domínios**, selecione os domínios que farão parte do domínio composto e clique na seta para direita para movê-los para a tabela **Domínios no Domínio Composto** . Esta é uma lista de domínios únicos que estão disponíveis para adição ao domínio composto que você está criando. Somente os domínios únicos que já foram criados e não foram adicionados a um domínio composto existente estão disponíveis. Um domínio único não pode ser adicionado a mais de um domínio composto na base de dados de conhecimento e um domínio composto não pode ser adicionado a outro domínio composto.  
  
3.  Clique em **Avançado**.  
  
4.  Selecione uma das seguintes opções como o **Método de Análise**:  
  
    -   **Dados de referência**: Analise os valores do campo acordo com como os dados são formatados pelo serviço de dados de referência (RDS). O Data Quality Services enviará os valores no domínio composto ao RDS e o RDS retornará os dados corrigidos e analisados de acordo com o domínio no domínio composto.  
  
    -   **Em ordem**: Analise os valores do campo de acordo com a ordem dos domínios no domínio composto. O primeiro valor será incluído no primeiro domínio, o segundo valor no segundo domínio etc.  
  
    -   **Delimitadores**: Analise os valores do campo com base no delimitador selecionado dentre os botões de opção exibidos quando delimitadores estão selecionados. Esses podem ser: **Guia**, **Ponto-e-vírgula**, **Vírgula**, **Espaço**ou **Outro**. Se **Outro**, insira o valor que atuará como o delimitador.  
  
5.  Se você selecionou **Delimitadores** como o método de análise, também poderá selecionar **Usar Análise da Base de Dados de Conhecimento**. Para obter mais informações, consulte [Knowledge-Based Parsing](#KnowledgeBaseParsing).  
  
6.  Clique em **Concluir** para concluir a atividade de gerenciamento de domínio, conforme descrito em [Terminar a atividade Gerenciamento de Domínio](../../2014/data-quality-services/end-the-domain-management-activity.md).  
  
##  <a name="FollowUp"></a> Acompanhamento: Depois de criar um domínio composto  
 Depois que você criar um domínio composto, poderá executar outras tarefas de gerenciamento de domínio, poderá executar a descoberta da base de dados de conhecimento para adicionar conhecimento ao domínio ou poderá adicionar uma política de correspondência ao domínio. Para obter mais informações, consulte [Executar a descoberta de conhecimento](../../2014/data-quality-services/perform-knowledge-discovery.md), [Gerenciando um domínio](../../2014/data-quality-services/managing-a-domain.md) ou [Criar uma política de conciliação](../../2014/data-quality-services/create-a-matching-policy.md).  
  
##  <a name="KnowledgeBaseParsing"></a> Knowledge-Based Parsing  
 O Data Quality Services permite que você analise os dados com base no conhecimento, não apenas no delimitador ou na ordem. A análise baseada em conhecimento é usada quando fontes de dados complexas são mapeadas para um domínio composto e você não está usando serviços de dados de referência. Você pode usar a análise baseada em conhecimento para analisar os dados a partir da fonte de dados nos domínios únicos relevantes. Com a análise baseada em conhecimento, o DQS primeiro tentará usar o conhecimento para analisar os dados complexos em domínios únicos. Se possível, ela identificará partes da cadeia de caracteres como em um ou mais domínios e analisará a cadeia de caracteres em seus vários domínios. Por exemplo, suponha que tem "John B. Doe" como valores complexos em um campo de nome completo representado por um domínio composto de Nome Completo. Se o DQS identificar "John" como no domínio Nome e "Doe" como no domínio Sobrenome e o DQS adicionará "B." ao domínio de Segundo Nome com base no conhecimento do domínio.  
  
 Você poderá usar a análise baseada em conhecimento somente se também selecionar a análise baseada no delimitador. A análise baseada em conhecimento não substitui a análise baseada no delimitador, mas a aprimora. Somente se não houver nenhum conhecimento para fazer isso é que o DQS usará um delimitador para realizar a análise. Em algumas instâncias, o DQS poderá determinar parte da análise executando a análise baseada no conhecimento e depois determinar outra análise pela análise baseada no delimitador.  
  
 A análise baseada no conhecimento pode ser usada quando o domínio composto abrange domínios de cadeia de caracteres ou quando o domínio composto abrange uma combinação de tipos diferentes de domínios (int, date, time etc). Se a fonte de dados abranger tipos de dados diferentes, a análise deverá ser feita primeiro para os tipos de dados não de cadeias de caracteres e, em seguida, conforme descrito acima com base no conhecimento do domínio do restante dos dados.  
  
 Quando você está usando a análise baseada em conhecimento e há menos valores na fonte de dados do que domínios no domínio composto, o DQS coloca um valor nulo no domínio ausente. Quando há mais valores na fonte de dados do que domínios no domínio composto, o DQS adicionará os dados extras a uma das colunas. Se dois ou mais domínios contiverem os mesmos valores, a fonte de dados será analisada como o primeiro domínio correspondente.  
  
  
