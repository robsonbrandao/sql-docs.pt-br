---
title: sys.external_libraries (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2019
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- external_libraries
- external_libraries_TSQL
- sys.external_libraries
- sys.external_libraries_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.external_libraries catalog view
author: dphansen
ms.author: davidph
manager: cgronlun
monikerRange: '>=sql-server-2017||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 3a2f83d703566ae5a60fd027ff7f186205a0c404
ms.sourcegitcommit: 2533383a7baa03b62430018a006a339c0bd69af2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57017532"
---
# <a name="sysexternallibraries-transact-sql"></a>sys.external_libraries (Transact-SQL)  
[!INCLUDE[tsql-appliesto-ss2017-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2017-xxxx-xxxx-xxx-md.md)]

Dá suporte ao gerenciamento de bibliotecas de pacotes relacionados a tempos de execução externos, como R, Python e Java.

> [!NOTE]
> No SQL Server 2017, a linguagem R e a plataforma do Windows têm suporte. R, Python e Java na plataforma do Windows têm suporte no SQL Server de 2019 CTP 2.3. Suporte para Linux está planejado para uma versão posterior.

## <a name="sysexternallibraries"></a>sys.external_libraries

O sys.external_libraries do modo de exibição de catálogo lista uma linha para cada biblioteca externa que tenha sido carregada no banco de dados.

|Nome da coluna |Tipo de dados | Descrição|
|------|------|------|
|external_library_id |INT | ID do objeto de biblioteca externa. |
|nome |sysname |Nome da biblioteca externa. É exclusivo no banco de dados por proprietário.|
|principal_id |INT |ID da entidade de segurança que possui essa biblioteca externa. |
|language | sysname | Nome do idioma ou tempo de execução que dá suporte a biblioteca externa. Valores válidos são 'R', 'Python' e 'Java'. Tempos de execução adicionais podem ser adicionados no futuro.|
|escopo |INT |0 para um escopo público; 1 para o escopo particular |  
|scope_desc |varchar(7) |Indica se o pacote é pública ou privada|

## <a name="see-also"></a>Confira também  

+ [sys.external_library_files](sys-external-library-files-transact-sql.md)  
+ [CRIAR A BIBLIOTECA EXTERNA](../../t-sql/statements/create-external-library-transact-sql.md)  
+ [Instalar os novos pacotes R no SQL Server](../../advanced-analytics/r/install-additional-r-packages-on-sql-server.md)  
+ [Instalar os novos pacotes Python no SQL Server](../../advanced-analytics/python/install-additional-python-packages-on-sql-server.md)  