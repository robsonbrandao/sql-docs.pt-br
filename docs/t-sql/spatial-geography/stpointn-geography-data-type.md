---
title: STPointN (tipo de dados geography) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- STPointN_TSQL
- STPointN (geography Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- STPointN method
ms.assetid: 47670feb-b9e0-4b4b-af83-b9bba7da66ac
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 23f5b2e7333873f861165bc7bbf19fbbd56ca733
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47836614"
---
# <a name="stpointn-geography-data-type"></a>STPointN (tipo de dados geography)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retorna o ponto especificado em uma instância de **geography**.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
.STPointN ( expression )  
```  
  
## <a name="arguments"></a>Argumentos  
 *expressão*  
 É uma expressão **int** entre 1 e o número de pontos na instância de **geography**.  
  
## <a name="return-types"></a>Tipos de retorno  
 Tipo de retorno do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **geography**  
  
 Tipo de retorno do CLR: **SqlGeography**  
  
 Tipo do OGC (Open Geospatial Consortium): **Point**  
  
## <a name="remarks"></a>Remarks  
 Se uma instância de **geography** for criada pelo usuário, STPointN() retornará o ponto especificado pela *expressão* ordenando os pontos pela ordem de entrada original.  
  
 Se uma instância de **geography** for construída pelo sistema, STPointN() retornará o ponto especificado pela *expressão* ordenando os pontos na mesma ordem em que eles seriam emitidos: primeiro pela instância de **geography**, depois pelo anel na instância (se apropriado) e, em seguida, pelo ponto dentro do anel. Essa ordem é determinística.  
  
 Se esse método for chamado com um valor menor que 1, ele gerará uma **ArgumentOutOfRangeException**.  
  
 Se esse método for chamado com um valor maior que o número de pontos na instância, retornará nulo.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir cria uma instância `LineString` e usa `STPointN()` para recuperar o segundo o ponto na descrição da instância.  
  
```  
DECLARE @g geography;  
SET @g = geography::STGeomFromText('LINESTRING(-122.360 47.656, -122.343 47.656)', 4326);  
SELECT @g.STPointN(2).ToString();  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Métodos OGC em instâncias geography](../../t-sql/spatial-geography/ogc-methods-on-geography-instances.md)  
  
  
