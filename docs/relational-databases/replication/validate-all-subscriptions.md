---
title: Validar Todas as Assinaturas | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql13.rep.validate.allsubscriptions.f1
helpviewer_keywords:
- Validate All Subscriptions dialog box
ms.assetid: 32e31469-36e4-42d9-a57a-12388bfd229d
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 849bd9e2d6c76f58e38b8f854d31686cef0ccfec
ms.sourcegitcommit: 7aa6beaaf64daf01b0e98e6c63cc22906a77ed04
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54134886"
---
# <a name="validate-all-subscriptions"></a>Validar Todas as Assinaturas
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Use a caixa de diálogo **Validar Todas as Assinaturas** para especificar que todas as assinaturas em uma publicação de mesclagem devem ser validadas na próxima execução do Merge Agent. Os resultados de validação são exibidos no Replication Monitor. Para obter mais informações, consulte [Validate Data at the Subscriber](../../relational-databases/replication/validate-data-at-the-subscriber.md).  
  
 Também é possível validar uma única assinatura clicando com o botão direito em uma assinatura no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e clicando em **Validar Assinatura**.  
  
## <a name="options"></a>Opções  
 **Verificar as contagens de linhas somente**  
 Selecione para validar se a tabela no Assinante tem o mesmo número de linhas que a tabela no Publicador. Esse método não valida que o conteúdo de correspondências de linhas. A validação de número de linhas fornece uma abordagem superficial à validação que pode alertá-lo sobre problemas com seus dados.  
  
 **Verificar as contagens de linhas e comparar as somas de verificação para verificar os dados da linha**  
 Além de contar o número de linhas no Publicador e no Assinante, uma soma de verificação de todos os dados é calculada usando o algoritmo de soma de verificação binária. Se a contagem de linhas falhar, a soma de verificação não será executada. Essa opção não é válida para [!INCLUDE[ssEW](../../includes/ssew-md.md)].  
  
## <a name="see-also"></a>Consulte Também  
 [Validar os dados replicados](../../relational-databases/replication/validate-data-at-the-subscriber.md)  
  
  
