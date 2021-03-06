---
title: Administração do DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- dqs administration
- administration
- dqs,adminstration
ms.assetid: 9940ef5d-f6f6-4dec-9414-1077a4d7f12b
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 6ff50e59daa241d64bbe878d6bd134c4efdea619
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2019
ms.locfileid: "56032777"
---
# <a name="dqs-administration"></a>administração do dqs
  O DQS ([!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] ) permite administrar e gerenciar várias atividades de DQS executadas no [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], configurar propriedades do nível de servidor relacionadas a atividades de DQS, definir as configurações de Serviço de Dados de Referência e definir configurações de log de DQS. Estas coisas são feitas pelo recurso **Administração** no [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]. Dependendo de seu acesso de segurança (função) no DQS, você recebe acesso ou tem o acesso negado a determinadas funcionalidades nesta área.  
  
 Além destas atividades de administração, este tópico também fornece informações sobre uma atividade de administração, fazendo backup e restaurando bancos de dados do DQS que não são executados usando o [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].  
  
 O recurso de administração no [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] tem os seguintes benefícios:  
  
-   Permite que administradores de dados monitorem várias atividades do DQS em um [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] de um [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].  
  
-   Permite que os administradores do DQS monitorem as atividades do DQS em um [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] de um [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]e *finalizem* uma atividade em execução ou *parem* um processo em execução dentro de uma atividade, se for preciso.  
  
-   Defina as configurações de serviço de dados de referência como configurar conectividade com o Windows Azure Marketplace e gerenciar provedores de serviços de dados de referências de terceiros.  
  
-   Configure valores de limites para atividades de limpeza e correspondência.  
  
-   Habilite/desabilite notificações no [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].  
  
-   Configure log com base no nível de severidade dos eventos.  
  
##  <a name="AdminUsingClent"></a> Atividades de administração usando Cliente Data Quality  
 Estas atividades são executadas usando o recurso **Administração** no [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].  
  
### <a name="activity-monitoring"></a>Monitoramento de Atividades  
 A tela **Monitoramento de Atividade** no [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] exibe informações detalhadas sobre cada atividade executada em um [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]. Essa tela será usada principalmente pelo administrador de dados para executar um monitoramento de alto nível de todas as atividades executadas no [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] com o qual o aplicativo do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] está conectado. Essa tela não fornece nenhum monitoramento em nível do sistema. Além disso, esta tela também permite os administradores do DQS controlem uma atividade ou um processo dentro de uma atividade finalizando uma atividade em execução ou parando um processo em execução dentro de uma atividade, se for preciso. Os dados são exibidos para descoberta da base de dados de conhecimento, gerenciamento de domínio, política de correspondência, limpeza, correspondência e limpeza baseada no SSIS (SQL Server Integration Services).  
  
### <a name="configuration"></a>Configuração  
 A tela **Configuração** no [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] permite que o administrador do DQS faça o seguinte:  
  
-   **Dados de referência**: Configure provedores de serviços de dados de referência: Windows Azure Marketplace ou provedores de serviço de dados de referência direto. Depois de configurar os provedores de serviço de dados de referência, você pode mapear um domínio ou domínio composto com os dados de referência durante a atividade de gerenciamento de domínio em uma base de dados de conhecimento e, em seguida, usar a mesma base de dados de conhecimento para a atividade de limpeza em um projeto de qualidade de dados. Isso também permite que você especifique as configurações de proxy para conectar-se à Internet para usar o Windows Azure Marketplace.  
  
-   **Configurações gerais**: Especifique os valores de limite para limpeza e correspondência de dados e se é para habilitar as notificações de criação de perfil em [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]. Estes valores de limite são usados pelo DQS durante a limpeza por computador e atividades correspondentes em um projeto de qualidade de dados.  
  
-   **Configurações de log**: Os arquivos de log no DQS registram as atividades executadas no DQS e são úteis para rastrear problemas operacionais durante a manutenção e solução de problemas. Você pode filtrar as mensagens que quiser que sejam registradas em log para vários recursos do DQS (gerenciamento de domínio, descoberta da base de dados de conhecimento, limpeza, correspondência e serviços de dados de referência) e módulos do DQS com base no nível de severidade dos eventos.  
  
> [!NOTE]  
>  A tela **Configuração** só estará disponível para os usuários que tiverem a função dqs_administrator no banco de dados DQS_MAIN.  
  
##  <a name="AdminOutsideClient"></a> Atividades de administração fora do Cliente Data Quality  
 As atividades são executadas fora do Cliente Data Quality:  
  
-   **Fazer backup e restaurar bancos de dados DQS**: O backup e restauração de bancos de dados DQS é o mesmo que fazer backup e restaurar qualquer banco de dados do SQL Server com algumas considerações que são específicas do DQS.  
  
-   **Desanexar e anexar bancos de dados DQS**: As etapas para desanexar e anexar bancos de dados DQS é o mesmo que desanexar e anexar qualquer banco de dados do SQL Server com algumas considerações que são específicas do DQS.  
  
 Para obter mais informações, consulte [Manage DQS Databases](../../2014/data-quality-services/manage-dqs-databases.md).  
  
## <a name="related-tasks"></a>Related Tasks  
  
|Descrição da tarefa|Tópico|  
|----------------------|-----------|  
|Descreve como monitorar atividades no DQS.|[Monitorar atividade do DQS](../../2014/data-quality-services/monitor-dqs-activities.md)|  
|Descreve como definir configurações de dados de referência no DQS.|[Configurar DQS para usar dados de referência](../../2014/data-quality-services/configure-dqs-to-use-reference-data.md)|  
|Descreve como configurar valores de limites para atividades de limpeza e correspondência.|[Configurar valores de limite para limpeza e correspondência](../../2014/data-quality-services/configure-threshold-values-for-cleansing-and-matching.md)|  
|Descreve como habilitar ou desabilitar as notificações no DQS.|[Habilitar ou desabilitar notificações de criação de perfil no DQS](../../2014/data-quality-services/enable-or-disable-profiling-notifications-in-dqs.md)|  
|Descreve como configurar log do DQS com base no nível de severidade dos eventos.|[Configurar níveis de severidade para arquivos de log do DQS](../../2014/data-quality-services/configure-severity-levels-for-dqs-log-files.md)|  
|Descreve como definir configurações avançadas para log do DQS.|[Definir configurações avançadas para arquivos de log do DQS](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md)|  
|Descreve como fazer backup e restaurar bancos de dados do DQS.|[Fazer backup e restaurar banco de dados do DQS](../../2014/data-quality-services/backing-up-and-restoring-dqs-databases.md)|  
|Descreve como desanexar e anexar bancos de dados DQS.|[Desanexar e anexar bancos de dados do DQS](../../2014/data-quality-services/detaching-and-attaching-dqs-databases.md)|  
  
## <a name="see-also"></a>Consulte também  
 [Serviços de Dados de Referência no DQS](../../2014/data-quality-services/reference-data-services-in-dqs.md)   
 [Gerenciar arquivos de log do DQS](../../2014/data-quality-services/manage-dqs-log-files.md)   
 [Gerenciar bancos de dados do DQS](../../2014/data-quality-services/manage-dqs-databases.md)  
  
  
