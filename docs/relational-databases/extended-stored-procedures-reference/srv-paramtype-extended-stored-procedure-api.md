---
title: srv_paramtype (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
apiname:
- srv_paramtype
apilocation:
- opends60.dll
apitype: DLLExport
dev_langs:
- C++
helpviewer_keywords:
- srv_paramtype
ms.assetid: badc6d36-8a87-42b5-b28c-9c4f5ded8552
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 073cc3f3e93bfcbce1b8914bbf3061dc7fde161d
ms.sourcegitcommit: edf7372cb674179f03a330de5e674824a8b4118f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53246665"
---
# <a name="srvparamtype-extended-stored-procedure-api"></a>srv_paramtype (API de procedimento armazenado estendido)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Em vez disso, use a Integração CLR.  
  
 Retorna o tipo de dados de um parâmetro de chamada de procedimento armazenado remoto.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
int srv_paramtype (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
```  
  
## <a name="arguments"></a>Argumentos  
 *srvproc*  
 É um ponteiro para a estrutura SRV_PROC que identifica uma conexão de cliente específica (nesse caso, o identificador que recebeu a chamada do procedimento armazenado remoto). A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.  
  
 *n*  
 Indica o número do parâmetro. O primeiro parâmetro é 1.  
  
## <a name="returns"></a>Retorna  
 Um valor de token para o tipo de dados do parâmetro. Para obter informações sobre tipos de dados, consulte [Tipos de dados &#40;API de Procedimento Armazenado Estendido&#41;](../../relational-databases/extended-stored-procedures-reference/data-types-extended-stored-procedure-api.md). Se não houver *n*-ésimo parâmetro nem procedimento armazenado remoto, o valor retornado será -1.  
  
 Essa função retornará os valores a seguir se o parâmetro for um dos tipos de dados do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].  
  
|Novos tipos de dados|Valor retornado|  
|--------------------|------------------|  
|**BITN**|SRVBIT|  
|**BIGVARCHAR**|VARCHAR|  
|**BIGCHAR**|CHAR|  
|**BIGBINARY**|BINARY|  
|**BIGVARBINARY**|VARBINARY|  
|**NCHAR**|CHAR|  
|**NVARCHAR**|VARCHAR|  
|**NTEXT**|-1|  
  
## <a name="remarks"></a>Remarks  
 Quando uma chamada de procedimento armazenado remoto é feita com parâmetros, os parâmetros podem ser passados pelo nome ou pela posição (sem-nome). Se a chamada de procedimento armazenado remoto for feita com alguns parâmetros transmitidos pelo nome e outros pela posição, ocorrerá um erro. O manipulador SRV_RPC ainda O manipulador SRV_RPC ainda é chamado, mas aparece como se não houvesse parâmetros e **srv_rpcparams** retorna 0.  
  
> [!IMPORTANT]  
>  Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção. Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://www.microsoft.com/en-us/msrc?rtc=1).  
  
## <a name="see-also"></a>Consulte Também  
 [srv_paraminfo &#40;API de Procedimento Armazenado Estendido&#41;](../../relational-databases/extended-stored-procedures-reference/srv-paraminfo-extended-stored-procedure-api.md)   
 [srv_rpcparams &#40;API de Procedimento Armazenado Estendido&#41;](../../relational-databases/extended-stored-procedures-reference/srv-rpcparams-extended-stored-procedure-api.md)  
  
  
