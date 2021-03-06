---
title: bcp_collen | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_collen
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_collen function
ms.assetid: faaf1f7a-81f2-4852-a178-56602c33673a
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: a66a88a61a581dff262fb8585b5cf32830f8eeed
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48137962"
---
# <a name="bcpcollen"></a>bcp_collen
  Define o comprimento de dados na variável de programa para a cópia em massa atual no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
RETCODE bcp_collen (  
HDBC   
hdbc  
,  
DBINT   
cbData  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a>Argumentos  
 *HDBC*  
 É o identificador de conexão ODBC habilitado para cópia em massa.  
  
 *cbData*  
 É o comprimento dos dados na variável de programa, não incluindo o comprimento dos indicadores ou terminadores de comprimento. A definição de *cbData* como SQL_NULL_DATA indica que todas as linhas copiadas no servidor contêm um valor NULL na coluna. Defini-lo como SQL_VARLEN_DATA indica que um terminador da cadeia de caracteres ou outro método é usado para determinar o comprimento dos dados copiados. Se um indicador de comprimento e um terminador existirem, o sistema usará o que resultar em menos cópia de dados.  
  
 *idxServerCol*  
 É a posição ordinal da coluna na tabela na qual os dados são copiados. A primeira coluna é 1. A posição ordinal de uma coluna é relatada por [SQLColumns](../native-client-odbc-api/sqlcolumns.md).  
  
## <a name="returns"></a>Retorna  
 SUCCEED ou FAIL.  
  
## <a name="remarks"></a>Comentários  
 A função **bcp_collen** permite que você altere o comprimento de dados na variável do programa para uma coluna específica quando copiar dados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com [bcp_sendrow](bcp-sendrow.md).  
  
 Inicialmente, o comprimento de dados é determinado quando [bcp_bind](bcp-bind.md) é chamado. Se o comprimento de dados for alterado entre as chamadas para **bcp_sendrow** e nenhum prefixo de comprimento ou terminador for usado, você poderá chamar **bcp_collen** para redefinir o comprimento. A próxima chamada para **bcp_sendrow** usará o comprimento definido pela chamada para **bcp_collen**.  
  
 Você deve chamar **bcp_collen** uma vez para cada coluna na tabela cujo comprimento de dados deseje modificar.  
  
## <a name="see-also"></a>Consulte também  
 [Funções de cópia em massa](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
