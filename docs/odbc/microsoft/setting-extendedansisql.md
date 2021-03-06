---
title: Configurando o ExtendedAnsiSQL | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- extendedANSISQL [ODBC], setting
ms.assetid: 37b775d1-65ac-45ac-8572-454bc4e3c1a2
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: c9b8999e229e8a6ed4804b2f06a4072d139ae93a
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47818136"
---
# <a name="setting-extendedansisql"></a>Configurar o ExtendedAnsiSQL
O atributo pode ser controlado na cadeia de conexão, adicionando o atributo ExtendedAnsiSQL:  
  
|Valor|Description|  
|-----------|-----------------|  
|ExtendedAnsiSQL = 0 (padrão)|Essa configuração não permite os novos recursos.|  
|ExtendedAnsiSQL = 1|Essa configuração permite que os novos recursos.|  
  
 O atributo também pode ser definido em um DSN por meio de **opções avançadas de** ao configurar um DSN por meio do painel de controle de caixa de diálogo.  
  
 Configurar o atributo para 0 desabilita os novos recursos. Configurando-a como 1 habilita os recursos novos.  
  
 O atributo também pode ser definido usando SQLSetConnectAttr(). O valor do atributo é 65501 e é definido como um valor de sqlinteger que contém de 1 ou 0, conforme documentado na tabela anterior. Ele pode ser chamado antes ou depois de se conectar, mas é melhor para chamá-lo após a conexão devido à ordem na qual os processos de driver em cache os atributos de conexão e cadeias de caracteres de conexão.
