---
title: 'Tarefa 7: Criar um domínio composto | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: ae778647-1df0-4952-9a69-0ef6177eea9c
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: c48144ca3720565c3c745ffd8aa39b0896e1fb66
ms.sourcegitcommit: dfb1e6deaa4919a0f4e654af57252cfb09613dd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2019
ms.locfileid: "56013787"
---
# <a name="task-7-creating-a-composite-domain"></a>Tarefa 7: Criando um domínio composto
  Nesta tarefa, você criará um domínio composto, **Address Validation**, que inclui **Address Line**, **Cidade**, **estado**e  **ZIP** domínios. Um domínio composto permite definir uma regra entre domínios que envolve vários domínios em uma regra. Há outras vantagens para um domínio composto, como analisar um valor de campo em vários domínios.  Por exemplo, um valor para um campo Nome Completo pode ser analisado em domínios separados de Nome, Nome do Meio e Sobrenome. Neste tutorial, você define apenas uma regra entre domínios. Ver [Gerenciando um domínio composto](https://msdn.microsoft.com/library/hh510399.aspx) para obter mais detalhes.  
  
1.  No painel esquerdo, clique em **criar um domínio composto** na barra de ferramentas.  
  
     ![Criar um botão de barra de ferramentas do domínio composto](../../2014/tutorials/media/et-creatingacompositedomain-01.jpg "criar um botão de barra de ferramentas do domínio composto")  
  
2.  Insira **validação de endereço** para o **nome de domínio composto**.  
  
     ![Validação de domínio composto de endereço](../../2014/tutorials/media/et-creatingacompositedomain-02.jpg "domínio composto de validação de endereço")  
  
3.  Selecione a lista de domínio **Address Line**, **City**, **estado**, e **Zip** e clique em **seta para a direita** para adicioná-los para o **domínios no domínio composto** lista.  
  
4.  Clique em **OK** para fechar a caixa de diálogo.  
  
## <a name="next-step"></a>Próxima etapa  
 [Tarefa 8: Criando uma regra de domínio composto](../../2014/tutorials/task-8-creating-a-composite-domain-rule.md)  
  
  
