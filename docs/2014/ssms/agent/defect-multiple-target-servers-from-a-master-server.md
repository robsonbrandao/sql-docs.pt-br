---
title: Remover vários servidores de destino de um servidor mestre | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], defecting
- SQL Server Agent jobs, master servers
- master servers [SQL Server], defecting target servers
- defecting target servers
- multiple target server defections
ms.assetid: 61a3713b-403a-4806-bfc4-66db72ca1156
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 0123027ac9aa87d616b52ac5cc26f36a20f7e1e3
ms.sourcegitcommit: ceb7e1b9e29e02bb0c6ca400a36e0fa9cf010fca
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2018
ms.locfileid: "52757468"
---
# <a name="defect-multiple-target-servers-from-a-master-server"></a>Defect Multiple Target Servers from a Master Server
  Este tópico descreve como remover vários servidores de destino de uma configuração de administração multisservidor no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]. Execute este procedimento a partir do servidor mestre.  
  
##  <a name="SSMSProcedure"></a> Usando o SQL Server Management Studio  
  
#### <a name="to-defect-multiple-target-servers-from-a-master-server"></a>Para remover vários servidores de destino de um servidor mestre  
  
1.  No **Pesquisador de Objetos**, expanda um servidor que esteja configurado como servidor mestre.  
  
2.  Clique com o botão direito do mouse em **SQL Server Agent**, aponte para **Administração Multisservidor**e clique em **Gerenciar Servidores de Destino**.  
  
3.  Clique em **Postar Instruções**e, na lista **Tipo de instrução** , selecione **Remover**.  
  
4.  Em **Destinatários**, siga um destes procedimentos:  
  
    -   Clique em **Todos os servidores de destino** para remover todos os servidores de destino desse servidor mestre. Use esta opção se quiser desinstalar completamente a configuração de administração multisservidor atual.  
  
    -   Clique em **Estes servidores de destino**e então clique na caixa **Selecionar** correspondente aos servidores de destino que devem ser removidos desse servidor mestre, para remover apenas alguns deles.  
  
## <a name="see-also"></a>Consulte também  
 [Criar um ambiente multisservidor](create-a-multiserver-environment.md)   
 [Administração automatizada em toda a empresa](automated-administration-across-an-enterprise.md)   
 [Defect a Target Server from a Master Server](defect-a-target-server-from-a-master-server.md)  
  
  
