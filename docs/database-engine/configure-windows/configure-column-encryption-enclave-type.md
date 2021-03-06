---
title: Opção de Configuração do Servidor column encryption enclave type | Microsoft Docs
ms.custom: ''
ms.date: 09/24/2018
ms.prod: sql
ms.prod_service: security
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
author: jaszymas
ms.author: jaszymas
manager: craigg
monikerRange: '>= sql-server-ver15 || = sqlallproducts-allversions'
ms.openlocfilehash: 961cf4a634f134f3bd41858a8157db0e8f6cb45f
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47782384"
---
# <a name="column-encryption-enclave-type-server-configuration-option"></a>Opção de Configuração do Servidor column encryption enclave type
[!INCLUDE[tsql-appliesto-ssver15-xxxx-xxxx-xxx](../../includes/tsql-appliesto-ssver15-xxxx-xxxx-xxx.md)]

  Use a opção **column encryption enclave type** para habilitar ou desabilitar um enclave seguro para Always Encrypted.  Para obter mais informações, consulte [Always Encrypted com enclaves seguros](../../relational-databases/security/encryption/always-encrypted-enclaves.md).

 A tabela a seguir lista os valores possíveis de **column encryption enclave type**:  
  
|Valor|Descrição|  
|-------------------|-----------------|  
|0|**Nenhum enclave seguro**. O [!INCLUDE[ssDE](../../includes/ssde-md.md)] não inicializará o enclave seguro para o Always Encrypted. Como resultado, a funcionalidade do Always Encrypted com enclaves seguros não estará disponível.|  
|1|**VBS (segurança baseada em virtualização)**. O [!INCLUDE[ssDE](../../includes/ssde-md.md)] inicializará o enclave seguro (um enclave de memória seguro de VBS) para o Always Encrypted.|    

> [!IMPORTANT]
> Alterações de **column encryption enclave type** não terão efeito até que você reinicie a instância de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].
  
   
## <a name="examples"></a>Exemplos  
 O exemplo a seguir habilita o enclave seguro:  

```sql  
sp_configure 'column encryption enclave type', 1;  
GO  
RECONFIGURE;  
GO  
```  

O exemplo a seguir desabilita o enclave seguro:  

```sql  
sp_configure 'column encryption enclave type', 0;  
GO  
RECONFIGURE;  
GO  
```  

## <a name="see-also"></a>Consulte Também  
 [sp_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)   
 [RECONFIGURE &#40;Transact-SQL&#41;](../../t-sql/language-elements/reconfigure-transact-sql.md)   
 [Opções de configuração do servidor &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md)  
  
  
