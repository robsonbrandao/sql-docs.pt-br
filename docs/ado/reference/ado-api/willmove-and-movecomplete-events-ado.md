---
title: Eventos WillMove e Movecomplete (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset::MoveComplete
- WillMove
- MoveComplete
- Recordset::WillMove
helpviewer_keywords:
- MoveComplete event [ADO]
- WillMove event [ADO]
ms.assetid: 1a3d1042-4f30-4526-a0c7-853c242496db
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 47040adf2ce7be17d0540755f7fa972d7a76266f
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47772544"
---
# <a name="willmove-and-movecomplete-events-ado"></a>Eventos WillMove e MoveComplete (ADO)
O **eventos WillMove** evento é chamado antes de uma operação pendente altera a posição atual na [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md). O **MoveComplete** eventos é chamado após a posição atual na **Recordset** alterações.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
WillMove adReason, adStatus, pRecordset  
MoveComplete adReason, pError, adStatus, pRecordset  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *adReason*  
 Uma [EventReasonEnum](../../../ado/reference/ado-api/eventreasonenum.md) valor que especifica o motivo para esse evento. Seu valor pode ser **adRsnMoveFirst**, **adRsnMoveLast**, **adRsnMoveNext**, **adRsnMovePrevious**, **adRsnMove** , ou **adRsnRequery**.  
  
 *pError*  
 Uma [erro](../../../ado/reference/ado-api/error-object.md) objeto. Ele descreve o erro ocorrido se o valor de *adStatus* é **adStatusErrorsOccurred**; caso contrário, o parâmetro não for definido.  
  
 *adStatus*  
 Uma [EventStatusEnum](../../../ado/reference/ado-api/eventstatusenum.md) valor de status.  
  
 Quando **eventos WillMove** é chamado, esse parâmetro é definido como **adStatusOK** se a operação que causou o evento foi bem-sucedida. Ele é definido como **adStatusCantDeny** se esse evento não é possível solicitar o cancelamento da operação pendente.  
  
 Quando **MoveComplete** é chamado, esse parâmetro é definido como **adStatusOK** se a operação que causou o evento foi bem-sucedida, ou ao **adStatusErrorsOccurred** se a Falha na operação.  
  
 Antes de **eventos WillMove** retorna, defina esse parâmetro como **adStatusCancel** para solicitar o cancelamento da operação pendente ou definir esse parâmetro como **adStatusUnwantedEvent** Para evitar notificações subsequentes.  
  
 Antes de **MoveComplete** retorna, defina esse parâmetro como **adStatusUnwantedEvent** para evitar notificações subsequentes.  
  
 *pRecordset*  
 Um [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) objeto. O **Recordset** para que esse evento ocorreu.  
  
## <a name="remarks"></a>Comentários  
 Um **eventos WillMove** ou **MoveComplete** evento pode ocorrer devido ao seguinte **conjunto de registros** operações: [abrir](../../../ado/reference/ado-api/open-method-ado-recordset.md), [mover](../../../ado/reference/ado-api/move-method-ado.md), [MoveFirst](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md), [MoveLast](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md), [MoveNext](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md), [MovePrevious](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md), [AddNew](../../../ado/reference/ado-api/addnew-method-ado.md), e [Requery](../../../ado/reference/ado-api/requery-method.md). Esses eventos podem ocorrer devido às seguintes propriedades: [filtro](../../../ado/reference/ado-api/filter-property.md), [índice](../../../ado/reference/ado-api/index-property.md), [indicador](../../../ado/reference/ado-api/bookmark-property-ado.md), [AbsolutePage](../../../ado/reference/ado-api/absolutepage-property-ado.md)e [AbsolutePosition](../../../ado/reference/ado-api/absoluteposition-property-ado.md). Esses eventos também ocorrem se alguma criança **conjunto de registros** tem **conjunto de registros** eventos conectados e o pai **Recordset** é movido.  
  
 Você deve definir a *adStatus* parâmetro **adStatusUnwantedEvent** para cada possível *adReason* valor para interromper completamente a notificação de eventos para qualquer evento que inclui um *adReason* parâmetro.  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo de modelo de eventos ADO (VC + +)](../../../ado/reference/ado-api/ado-events-model-example-vc.md)   
 [Resumo do manipulador de eventos ADO](../../../ado/guide/data/ado-event-handler-summary.md)   
 [Objeto Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)
