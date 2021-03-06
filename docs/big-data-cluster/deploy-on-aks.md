---
title: Configurar o serviço de Kubernetes do Azure
titleSuffix: SQL Server 2019 big data clusters
description: Saiba como configurar o serviço de Kubernetes do Azure (AKS) para implantações de cluster (versão prévia) do SQL Server 2019 big data.
author: rothja
ms.author: jroth
manager: craigg
ms.date: 02/28/2019
ms.topic: conceptual
ms.prod: sql
ms.technology: big-data-cluster
ms.custom: seodec18
ms.openlocfilehash: ae8a8b2869a46a9157c805edcb8c6d74ca49e3d0
ms.sourcegitcommit: 2533383a7baa03b62430018a006a339c0bd69af2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57017992"
---
# <a name="configure-azure-kubernetes-service-for-sql-server-2019-big-data-cluster-preview-deployments"></a>Configurar o serviço Kubernetes do Azure para implantações de cluster (versão prévia) do SQL Server 2019 big data

Este artigo descreve como configurar o serviço de Kubernetes do Azure (AKS) para implantações de cluster (versão prévia) do SQL Server 2019 big data.

AKS torna simples a criar, configurar e gerenciar um cluster de máquinas virtuais que são pré-configuradas com um cluster Kubernetes para executar aplicativos em contêineres. Isso permite que você use suas habilidades existentes ou explore um grande e crescente Conhecimento da comunidade, para implantar e gerenciar aplicativos baseados em contêiner no Microsoft Azure.

Este artigo descreve as etapas para implantar o Kubernetes no AKS usando a CLI do Azure. Se você não tiver uma assinatura do Azure, crie uma conta gratuita, antes de começar.

> [!TIP] 
> Para um script de python de exemplo que implanta o cluster de big data do AKS e o SQL Server, consulte [guia de início rápido: Implantar o SQL Server no serviço de Kubernetes do Azure (AKS) de cluster de big data](quickstart-big-data-cluster-deploy.md).

## <a name="prerequisites"></a>Prerequisites

- [Implantar as ferramentas de big data do SQL Server 2019](deploy-big-data-tools.md):
   - **Kubectl**
   - **Azure Data Studio**
   - **Extensão do SQL Server de 2019**
   - **CLI do Azure**

- Versão mínima 1.10 para o servidor de Kubernetes. Para o AKS, você precisará usar `--kubernetes-version` parâmetro para especificar uma versão diferente do padrão.

- Para obter uma experiência ideal ao validar cenários básicos de AKS, use:
   - Mínimo de 3 VMs do agente
   - 4 vCPUs por VM
   - 32 GB de memória por VM

   > [!TIP]
   > Infraestrutura do Azure oferece várias opções de tamanho para VMs, consulte [aqui](https://docs.microsoft.com/azure/virtual-machines/windows/sizes) para seleções na região em que você planeja implantar.

## <a name="create-a-resource-group"></a>Criar um grupo de recursos

Um grupo de recursos do Azure é um grupo lógico no qual Azure recursos são implantados e gerenciados. As etapas a seguir entrar no Azure e criar um grupo de recursos para o cluster do AKS.

1. No prompt de comando, execute o seguinte comando e siga os prompts para fazer logon em sua assinatura do Azure:

    ```azurecli
    az login
    ```

1. Se você tiver várias assinaturas, você pode exibir todas as suas assinaturas, executando o seguinte comando:

   ```azurecli
   az account list
   ```

1. Se você quiser alterar para uma assinatura diferente, você pode executar este comando:

   ```azurecli
   az account set --subscription <subscription id>
   ```

1. Criar um grupo de recursos com o **criar grupo de az** comando. O exemplo a seguir cria um grupo de recursos denominado `sqlbigdatagroup` no `westus2` local.

   ```azurecli
   az group create --name sqlbigdatagroup --location westus2
   ```

## <a name="create-a-kubernetes-cluster"></a>Criar um cluster Kubernetes

1. Criar um cluster Kubernetes no AKS com o [criar az aks](https://docs.microsoft.com/cli/azure/aks) comando. O exemplo a seguir cria um cluster Kubernetes chamado *kubcluster* com três nós de agente do Linux. Certifique-se de que criar o cluster do AKS no mesmo grupo de recursos que você usou nas seções anteriores.

    ```azurecli
   az aks create --name kubcluster \
    --resource-group sqlbigdatagroup \
    --generate-ssh-keys \
    --node-vm-size Standard_L4s \
    --node-count 3 \
    --kubernetes-version 1.10.9
    ```

   Você pode aumentar ou diminuir o número de nós de agente do Kubernetes, alterando a `--node-count <n>` onde `<n>` é o número de nós de agente que você deseja usar. Isso não inclui o nó mestre do Kubernetes, que é gerenciado pelo AKS em segundo plano. Portanto, no exemplo acima, há **3** VMs de tamanho **Standard_L4s** usadas para os nós de agente do cluster do AKS.

   Após alguns minutos, o comando for concluído e retorna informações formatadas em JSON sobre o cluster.

1. Salve a saída JSON do comando anterior para uso posterior.

## <a name="connect-to-the-cluster"></a>Conectar-se ao cluster

1. Para configurar o kubectil para conectar-se ao cluster Kubernetes, execute as [az aks get-credentials](https://docs.microsoft.com/cli/azure/aks?view=azure-cli-latest#az-aks-get-credentials) comando. Esta etapa baixa credenciais e configura o kubectl CLI para usá-los.

   ```azurecli
   az aks get-credentials --resource-group=sqlbigdatagroup --name kubcluster
   ```

1. Para verificar a conexão ao seu cluster, use o [kubectl get](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands) comando para retornar uma lista de nós do cluster.  O exemplo a seguir mostra a saída se você tem 1 mestre e nós de agente 3.

   ```
   kubectl get nodes
   ```

## <a name="next-steps"></a>Próximas etapas

As etapas neste artigo configurado um cluster Kubernetes no AKS. A próxima etapa é implantar o SQL Server 2019 grandes dados ao cluster. Para obter mais informações sobre como implantar clusters de big data, consulte o artigo a seguir:

[Como implantar clusters de grandes dados do SQL Server no Kubernetes](deployment-guidance.md)
