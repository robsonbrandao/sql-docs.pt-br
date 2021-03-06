---
title: Executar trabalhos do Spark no Kit de ferramentas do Azure para IntelliJ em Cluster grande de dados do SQL Server
titleSuffix: SQL Server Big Data Clusters
description: Envie trabalhos do Spark em Big Data Clusters do SQL Server no Kit de ferramentas do Azure para IntelliJ.
author: jejiang
ms.author: jejiang
ms.reviewer: jroth
ms.date: 02/28/2019
ms.topic: conceptual
ms.openlocfilehash: 06ce1d325caa0835381fd6f9ecd5428d2bbb6f66
ms.sourcegitcommit: 2533383a7baa03b62430018a006a339c0bd69af2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57018472"
---
# <a name="submit-spark-jobs-on-sql-server-big-data-clusters-in-intellij"></a>Enviar trabalhos do Spark em Big Data Clusters do SQL Server no IntelliJ

Um dos principais cenários para Clusters grandes de dados do SQL Server é a capacidade de enviar trabalhos do Spark. O recurso de envio de trabalho do Spark permite que você envie arquivos Jar ou Py locais com referências a Clusters grandes de dados do SQL Server. Ele também permite que você execute um arquivos Jar ou Py, que já estão localizados no sistema de arquivos HDFS. 

## <a name="prerequisites"></a>Prerequisites

- Cluster de Big Data do SQL Server.
- Oracle Java Development Kit. Você pode instalá-lo partir o [site da Oracle](https://aka.ms/azure-jdks).
- IDEA do IntelliJ. Você pode instalá-lo partir o [site do JetBrains](https://www.jetbrains.com/idea/download/).
- Kit de ferramentas do Azure para IntelliJ extensão. Para obter instruções de instalação, consulte [instalar o Azure Toolkit for IntelliJ](https://docs.microsoft.com/azure/azure-toolkit-for-intellij-installation).

## <a name="link-sql-server-big-data-cluster"></a>Cluster de Big Data do link SQL Server
1. Abra a ferramenta de IntelliJ IDEA.

2. Se você estiver usando um certificado autoassinado, desabilite a validação de certificado SSL do **ferramentas** menu, selecione **Azure**, **Validar certificado SSL do Spark para Cluster**, em seguida, **Desabilitar**.

    ![vincular um Cluster grande de dados do SQL Server – desabilitar o SSL](./media/spark-submit-job-intellij-tool-plugin/link-ariscluster-disableSSL.png)

3. Abra o Explorer do Azure do **modo de exibição** menu, selecione **ferramenta Windows**e, em seguida, selecione **Azure Explorer**.
4. Clique com botão direito **Cluster grande de dados do SQL Server**, selecione **Cluster de Big Data do Link de SQL Server**. Insira o **Server**, **nome de usuário**, e **senha**, em seguida, clique em **Okey**.

    ![vincular o cluster de Big Data - caixa de diálogo](./media/spark-submit-job-intellij-tool-plugin/link-ariscluster-dialog.png)

5. Quando for exibida a caixa de diálogo de certificado do servidor não confiável, clique em **Accept**. Você pode gerenciar o certificado mais tarde, consulte [certificados de servidor](https://www.jetbrains.com/help/idea/settings-tools-server-certificates.html).

6. O cluster vinculado lista sob **Cluster grande de dados do SQL Server**. Você pode monitorar o trabalho do spark abrindo o histórico do spark da interface do usuário e a IU do Yarn, você pode desvincular também, pelo clique com o botão direito no cluster.

    ![vincular o cluster de Big Data - menu de contexto](./media/spark-submit-job-intellij-tool-plugin/link-ariscluster-contextmenu.png)

## <a name="create-a-spark-scala-application-from-hdinsight-template"></a>Criar um aplicativo Scala Spark do HDInsight modelo

1. Inicie o IntelliJ IDEA e, em seguida, crie um projeto. No **novo projeto** caixa de diálogo, siga as etapas abaixo: 

   a. Selecione **Spark do Azure/HDInsight** > **Spark projeto com exemplos (Scala)**.

   b. No **ferramenta de compilação** , selecione qualquer uma das seguintes opções, de acordo com suas necessidades:

      * **Maven**, para suporte ao Assistente de criação do projeto de Scala
      * **SBT**, para gerenciar as dependências e compilar o projeto de Scala

    ![A caixa de diálogo Novo projeto](./media/spark-submit-job-intellij-tool-plugin/create-hdi-scala-app.png)

2. Selecione **Avançar**.

3. O Assistente de criação de projetos Scala detecta automaticamente se você instalou o plug-in Scala. Selecione **Instalar**.

   ![Seleção de plug-in scala](./media/spark-submit-job-intellij-tool-plugin/Scala-Plugin-check-Reminder.PNG) 

4. Para baixar o plug-in Scala, selecione **Okey**. Siga as instruções para reiniciar o IntelliJ. 

   ![A caixa de diálogo de instalação de plug-in Scala](./media/spark-submit-job-intellij-tool-plugin/Choose-Scala-Plugin.PNG)

5. No **novo projeto** janela, faça o seguinte:  

    ![Selecionando o SDK do Spark](./media/spark-submit-job-intellij-tool-plugin/hdi-new-project.png)

   a. Insira um nome de projeto e local.

   b. No **SDK do projeto** lista suspensa, selecione **Java 1.8** para o cluster Spark 2.x ou selecione **Java 1.7** para o cluster Spark 1.x.

   c. No **versão do Spark** lista suspensa, o Assistente de criação de projeto Scala integra a versão apropriada para SDK do Spark e o SDK do Scala. Se a versão de cluster do Spark for inferior a 2.0, selecione **Spark 1.x**. Caso contrário, selecione **Spark2.x**. Este exemplo usa **Spark 2.0.2 (Scala 2.11.8)**.

6. Selecione **Concluir**.

7. O projeto do Spark cria automaticamente um artefato para você. Para exibir o artefato, faça o seguinte:

   a. Sobre o **arquivo** menu, selecione **estrutura do projeto**.

   b. No **estrutura do projeto** caixa de diálogo, selecione **artefatos** para exibir o artefato padrão criado. Você também pode criar seu próprio artefato selecionando o sinal de adição (**+**).

      ![Informações de artefato na caixa de diálogo](./media/spark-submit-job-intellij-tool-plugin/default-artifact.png)
      

## <a name="submit-application-to-sql-server-big-data-cluster"></a>Enviar o aplicativo para o Cluster grande de dados do SQL Server
Depois de vincular um Cluster grande de dados do SQL Server, você pode enviar o aplicativo nele.

1. Defina a configuração no **executar/depurar configurações** janela, clique em + ->**Apache Spark no SQL Server**, selecione guia **executar remotamente em Cluster**, defina os parâmetros como a seguir, em seguida, clique em Okey.

    ![Console interativo de adicionar a entrada de configuração](./media/spark-submit-job-intellij-tool-plugin/interactive-console-add-config-entry.png)

    ![vincular o cluster de Big Data - config](./media/spark-submit-job-intellij-tool-plugin/link-ariscluster-config.png)

    * Para **(somente Linux) de clusters do Spark**, selecione o cluster no qual você deseja executar o aplicativo.

    * Selecione um artefato do projeto IntelliJ ou selecionar uma na unidade de disco rígido.

    * **Nome da classe principal** campo: O valor padrão é a classe principal do arquivo selecionado. Você pode alterar a classe selecionando as reticências (**...** ) e escolhendo outra classe.   

    * **As configurações de trabalho** campo:  Os valores padrão são definidos como imagem mostrada acima. Você pode alterar o valor ou adicionar nova chave/valor para o envio do trabalho. Para obter mais informações, consulte: [Apache Livy API REST](http://livy.incubator.apache.org./docs/latest/rest-api.html)

      ![O significado de configuração do envio do Spark caixa de diálogo caixa trabalho](./media/spark-submit-job-intellij-tool-plugin/submit-job-configurations.png)

    * **Argumentos de linha de comando** campo: Você pode inserir os valores de argumentos dividido pelo espaço para a classe principal, se necessário.

    * **Referenciado Jars** e **arquivos referenciados** campos: Você pode inserir os caminhos para os Jars referenciados e arquivos, se houver. Para obter mais informações, consulte: [Configuração do Apache Spark](https://spark.apache.org/docs/latest/configuration.html#runtime-environment) 

      ![Os arquivos jar do caixa da caixa de diálogo de envio do Spark ou seja](./media/spark-submit-job-intellij-tool-plugin/jar-files-meaning.png)

       > [!NOTE]  
       > Para carregar seus referenciado JARs e os arquivos referenciados, consulte: [Como carregar recursos de cluster](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)
                         
    * **Caminho de carregamento**: Você pode indicar o local de armazenamento para o envio de recursos de projeto Jar ou Scala. Há vários tipos de armazenamento com suporte: **Use a sessão interativa do Spark para carregar** e **WebHDFS de uso para carregar**
    
2. Clique em **SparkJobRun** para enviar seu projeto para o cluster selecionado. O **trabalho remoto do Spark no Cluster** guia exibe o progresso da execução de trabalho na parte inferior. Você pode interromper o aplicativo clicando no botão vermelho.  

    ![cluster de Big Data Link - execute](./media/spark-submit-job-intellij-tool-plugin/link-ariscluster-run.png)

## <a name="next-steps"></a>Próximas etapas
Para obter mais informações sobre o Cluster grande de dados do SQL Server e cenários relacionados, consulte [quais são os clusters do SQL Server 2019 grandes dados](big-data-cluster-overview.md)?
