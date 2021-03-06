---
title: Cursores dinâmicos | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- cursors [ADO], dynamic
- dynamic cursors [ADO]
ms.assetid: 00460f30-8cf7-494e-82df-41012f40ae51
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: f0d7a19476a00fb88e0b2195c761993f91b7a5d4
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47838324"
---
# <a name="dynamic-cursors"></a>Cursores dinâmicos
Cursores dinâmicos detectam todas as alterações feitas nas linhas no conjunto de resultados, independentemente se ocorrerem as alterações de dentro do cursor ou por outros usuários fora do cursor. Todos os insert, update e as instruções delete feitas por todos os usuários são visíveis pelo cursor. O cursor dinâmico pode detectar todas as alterações feitas a linhas, a ordem e a valores no conjunto de resultados depois que o cursor é aberto. As atualizações feitas fora do cursor não são visíveis até serem confirmadas (a menos que o nível de isolamento da transação de cursor é definido como "não confirmado").  
  
 Por exemplo, suponha que um cursor dinâmico busca duas linhas e o outro aplicativo e, em seguida, atualiza uma dessas linhas e exclui a outra. Se o cursor dinâmico, em seguida, busca essas linhas, ele não localizará a linha excluída, mas ele exibirá os novos valores para a linha atualizada.  
  
 O cursor dinâmico é uma boa opção se seu aplicativo deve detectar todas as atualizações simultâneas feitas por outros usuários. Use o **adOpenDynamic CursorTypeEnum** para indicar que você deseja usar um cursor dinâmico no ADO.  
  
## <a name="see-also"></a>Consulte também  
 [Cursores de somente avanço](../../../ado/guide/data/forward-only-cursors.md)   
 [Cursores estáticos](../../../ado/guide/data/static-cursors.md)   
 [Cursores do conjunto de chaves](../../../ado/guide/data/keyset-cursors.md)
