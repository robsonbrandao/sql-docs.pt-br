---
title: Propriedade ParentRow (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- ADORecordConstruction::put_ParentRow
- ADORecordConstruction::ParentRow
- ADORecordConstruction::putParentRow
helpviewer_keywords:
- ParentRow property [ADO]
ms.assetid: 5ea8029b-eda4-490b-ae84-2ad036fb582f
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 9ea31baf4b215a6a516c13b438b526b8e9d8b612
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47606574"
---
# <a name="parentrow-property-ado"></a>Propriedade ParentRow (ADO)
Define o contêiner de um banco de dados OLE **linha** do objeto em um **ADORecordConstruction** objeto, de modo que o pai da linha é transformado em ADO **registro** objeto.  
  
 Somente gravação.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT put_ParentRow([in] IUnknown* pParent);  
```  
  
## <a name="parameters"></a>Parâmetros  
 *pParent*  
 Um contêiner de uma linha.  
  
## <a name="return-values"></a>Valores de retorno  
 Esse método de propriedade retorna os valores HRESULT padrão, incluindo S_OK e E_FAIL.  
  
## <a name="applies-to"></a>Aplica-se a  
 [Interface ADORecordConstruction](../../../ado/reference/ado-api/adorecordconstruction-interface.md)
