---
title: 'Tarefa 8: Criar uma regra de domínio composto | Microsoft Docs'
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- data-quality-services
- integration-services
- master-data-services
ms.topic: conceptual
ms.assetid: cff3b662-7876-4445-9bdd-96be35b3ca0c
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 19b4922446f564435970fbb7f0422a3c98de48df
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48151956"
---
# <a name="task-8-creating-a-composite-domain-rule"></a>Tarefa 8: Criando uma regra de domínio composto
  Nesta tarefa, você pode criar uma regra para o **Address Validation** domínio composto. Defina uma regra de domínio cruzado: se **Cidade** é **Los Angeles**, **estado** deve ser **CA** onde **Cidade** e **estado** são dois domínios.  
  
1.  No painel direito, alterne para o **regras do CD** guia.  
  
2.  Clique em **adicionar uma nova regra de domínio** na barra de ferramentas.  
  
3.  Tipo de **City-State Rule** para **nome** e pressione **ENTER**.  
  
4.  No **uma regra de compilação** painel, selecione **Cidade** na lista de domínios e selecione a condição **valor é igual a** e digite **Los Angeles** para o valor.  
  
5.  No **, em seguida,** painel, selecione **estado** na lista de domínios e selecione **valor é igual a**, tipo **CA** para o valor e pressione **Guia**.  
  
     ![Regra de domínio composto](../../2014/tutorials/media/et-creatingacompositedomainrule.jpg "regra de domínio composto")  
  
6.  Clique em **fechar** botão na parte inferior da página para alternar para a página principal do cliente do DQS. Você publicará a base de dados de conhecimento na próxima lição. Observe que a base de dados de conhecimento está no estado bloqueado (ícone de bloqueio).  
  
## <a name="next-step"></a>Próxima etapa  
 [Tarefa 9: Configurando um serviço de dados de referência](../../2014/tutorials/task-9-configuring-a-reference-data-service.md)  
  
  
