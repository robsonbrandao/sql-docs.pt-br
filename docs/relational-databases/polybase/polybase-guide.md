---
title: O que é o PolyBase? | Microsoft Docs
ms.date: 09/24/2018
ms.prod: sql
ms.reviewer: ''
ms.custom: ''
ms.technology: polybase
ms.topic: overview
f1_keywords:
- PolyBase
- PolyBase, guide
helpviewer_keywords:
- PolyBase
- PolyBase, overview
- Hadoop import
- Hadoop export
- Hadoop export, PolyBase overview
- Hadoop import, PolyBase overview
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: e91afc38ec7cfa4d37217a3152ca731d3c8dac39
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47844604"
---
# <a name="what-is-polybase"></a>O que é o PolyBase?

[!INCLUDE[appliesto-ss-xxxx-asdw-pdw-md-winonly](../../includes/appliesto-ss-xxxx-asdw-pdw-md-winonly.md)]

<!--SQL Server 2016/2017-->
::: moniker range="= sql-server-2016 || = sql-server-2017"

O PolyBase permite que a instância do SQL Server 2016 processar consultas Transact-SQL que leem dados do Hadoop. A mesma consulta também pode acessar tabelas relacionais no SQL Server. O PolyBase permite que a mesma consulta também unir os dados do Hadoop e do SQL Server. No SQL Server, um [tabela externa](../../t-sql/statements/create-external-table-transact-sql.md) ou [fonte de dados externa](../../t-sql/statements/create-external-data-source-transact-sql.md) fornece a conexão para o Hadoop.

![PolyBase lógico](../../relational-databases/polybase/media/polybase-logical.png "PolyBase lógico")

O PolyBase envia alguns cálculos para o nó de Hadoop para otimizar a consulta geral. No entanto, o acesso externo do PolyBase não é limitado ao Hadoop. Outras tabelas relacionais não estruturadas também são suportadas, como arquivos de texto delimitado.

> [!TIP]
> O SQL Server 2019 CTP 2.0 introduz novos conectores para o PolyBase, incluindo o SQL Server, Oracle, Teradata e MongoDB. Para obter mais informações, confira a [Documentação do PolyBase para SQL Server 2019 CTP 2.0](polybase-guide.md?view=sql-server-ver15)

::: moniker-end
<!--SQL Server 2019-->
::: moniker range=">= sql-server-ver15 || =sqlallproducts-allversions"

O PolyBase permite que a instância do SQL Server processe consultas Transact-SQL que leem dados de fontes de dados externas. O SQL Server 2016 e versões posteriores podem acessar dados externos no Hadoop e Armazenamento de Blobs do Azure. No SQL Server 2019 CTP 2.0, agora você pode usar o PolyBase para acessar dados externos no [SQL Server](polybase-configure-sql-server.md), [Oracle](polybase-configure-oracle.md), [Teradata](polybase-configure-teradata.md) e [MongoDB](polybase-configure-mongodb.md).

As mesmas consultas que acessam dados externos também podem ser direcionadas a tabelas relacionais na sua instância do SQL Server. Isso permite que você combine dados de fontes externas com os dados relacionais de alto valor no seu banco de dados. No SQL Server, um [tabela externa](../../t-sql/statements/create-external-table-transact-sql.md) ou [fonte de dados externa](../../t-sql/statements/create-external-data-source-transact-sql.md) fornece a conexão para o Hadoop.

O PolyBase envia alguns cálculos para o nó de Hadoop para otimizar a consulta geral. No entanto, o acesso externo do PolyBase não é limitado ao Hadoop. Outras tabelas relacionais não estruturadas também são suportadas, como arquivos de texto delimitado.

::: moniker-end

### <a name="supported-sql-products-and-services"></a>Produtos e serviços SQL compatíveis

O PolyBase fornece essas mesmas funcionalidades para os seguintes produtos SQL da Microsoft:

- SQL Server 2016 e verões posteriores (somente Windows)
- O Analytics Platform System (anteriormente conhecido como Parallel Data Warehouse)
- Azure SQL Data Warehouse

### <a name="azure-integration"></a>Integração do Azure

Com a Ajuda subjacente do PolyBase, consultas T-SQL também podem importar e exportar dados do Armazenamento de Blobs do Azure. Além disso, o PolyBase permite que o SQL Data Warehouse do Azure importe/exporte dados do Armazenamento de Blobs do Azure e do Azure Data Lake Store.

## <a name="why-use-polybase"></a>Por que usar o PolyBase?

No passado, era mais difícil unir os dados do SQL Server com dados externos. Você tinha estas duas opções desagradáveis:

- Transferir metade os dados para que todos os seus dados ficassem em um formato ou em outro.
- Consultar ambas as fontes de dados, então escrever lógica de consulta personalizada para ingressar e integrar os dados no nível do cliente.

O PolyBase evita essas opções desagradáveis usando o T-SQL para unir os dados.

Para simplificar, o PolyBase não exige instalação de software adicional no ambiente do Hadoop. Você pode consultar dados externos usando a mesma sintaxe do T-SQL usada para consultar uma tabela de banco de dados. As ações de suporte implementadas pelo PolyBase todos ocorrem de maneira transparente. O autor da consulta não precisa de nenhum conhecimento sobre o Hadoop.

### <a name="polybase-uses"></a>Usos do PolyBase

O PolyBase habilita os seguintes cenários no SQL Server:

- **Consultar dados armazenados no Hadoop do SQL Server ou do PDW.** Os usuários estão armazenando dados em sistemas escalonáveis e distribuídos mais econômicos, como o Hadoop. O PolyBase facilita a consulta dos dados com T-SQL.

- **Consulte os dados armazenados no Armazenamento de Blobs do Azure.** O armazenamento de blobs do Azure é um local conveniente para armazenar dados para uso dos serviços do Azure.  O PolyBase facilita o acesso aos dados com T-SQL.

- **Importe dados do Hadoop, do Armazenamento de Blobs do Azure ou do Azure Data Lake Store.** Aproveite a velocidade das funcionalidades de análise e tecnologia de columnstore do Microsoft SQL, com a importação de dados do Hadoop, do Armazenamento de Blobs do Azure ou do Azure Data Lake Store em tabelas relacionais. Não é necessário ter uma ferramenta separada de ETL ou importação.

- **Exporte dados para o Hadoop, o Armazenamento de Blobs do Azure ou o Azure Data Lake Store.** Arquive dados no Hadoop, no Armazenamento de Blobs do Azure ou no Azure Data Lake Store para obter um armazenamento econômico e mantê-los online para fácil acesso.

- **Integre com ferramentas de BI.** Use o PolyBase com a business intelligence e a pilha de análise da Microsoft ou use as ferramentas de terceiros compatíveis com o SQL Server.

## <a name="performance"></a>Desempenho

- **Enviar por push de computação para Hadoop.** O otimizador de consulta faz uma decisão baseada em custo para enviar por push computação para Hadoop, quando então será melhorar desempenho da consulta.  Ele usa as estatísticas de tabelas externas para tomar a decisão baseada em custo. O envio por push do cálculo cria trabalhos MapReduce e aproveita os recursos computacionais distribuídos do Hadoop.

- **Escale os recursos de computação.** Para melhorar o desempenho da consulta, é possível usar os [grupos de escala horizontal do PolyBase](../../relational-databases/polybase/polybase-scale-out-groups.md)do SQL Server. Isso permite a transferência de dados em paralelo entre as instâncias do SQL Server e os nós do Hadoop, além de adicionar recursos de computação para operação em dados externos.

## <a name="next-steps"></a>Próximas etapas

Antes de usar o PolyBase, é preciso [instalar o recurso do PolyBase](polybase-installation.md). Em seguida, confira os guias de configuração a seguir, dependendo da sua fonte de dados:

<!--SQL Server 2016/2017-->
::: moniker range="= sql-server-2016 || = sql-server-2017"

- [Hadoop](polybase-configure-hadoop.md)
- [Armazenamento de Blobs do Azure](polybase-configure-azure-blob-storage.md)

::: moniker-end
<!--SQL Server 2019-->
::: moniker range=">= sql-server-ver15 || =sqlallproducts-allversions"

- [Hadoop](polybase-configure-hadoop.md)
- [Armazenamento de Blobs do Azure](polybase-configure-azure-blob-storage.md)
- [SQL Server](polybase-configure-sql-server.md)
- [Oracle](polybase-configure-oracle.md)
- [Teradata](polybase-configure-teradata.md)
- [MongoDB](polybase-configure-mongodb.md)

::: moniker-end
