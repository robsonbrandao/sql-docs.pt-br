---
title: Exibir relatórios de caso de teste (SybaseToSQL) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Tester Component,Test Case Reports
ms.assetid: cb75d281-43ef-4f4a-b754-2c4ee3b62ae7
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: 840f73d0732d0789d378c6f1bceb100c58e01bb6
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "47624457"
---
# <a name="viewing-test-case-reports-sybasetosql"></a>Exibir relatórios de caso de teste (SybaseToSQL)
O relatório de caso de teste mostra os resultados da verificação de teste e as informações de teste geral. Em caso de falha de teste, informações sobre todos os dados incompatíveis em objetos verificados também são exibidas.  
  
## <a name="report-structure"></a>Estrutura de relatório  
A parte superior do relatório mostra essas estatísticas:  
  
-   O número total de objetos testados e o número de objetos para o qual o teste foi bem-sucedido.  
  
-   O número total de tabelas verificadas e chaves estrangeiras e o número de tabelas e chaves estrangeiras combinadas com sucesso.  
  
-   A hora de início, hora de término do caso de teste e o tempo total decorrido para execução.  
  
O restante do relatório mostra informações em quatro categorias:  
  
**Erros de pré-requisitos**  
Mostra os erros que ocorreram na **pré-requisitos** etapa. Normalmente, ele será ignorado.  
  
**Inicialização**  
Mostra o status de execução como **sucesso** ou **falha**.  
  
**Objetos de resultado do teste**  
Uma comparação dos resultados (êxito ou falha) e a incompatibilidade com o SSMA testador detectado em caso de falha.  
  
**Finalização**  
Mostra o status de execução como **sucesso** ou **falha**.  
  
## <a name="see-also"></a>Consulte também  
[Executar casos de teste &#40;SybaseToSQL&#41;](../../ssma/sybase/running-test-cases-sybasetosql.md)  
[Testar objetos de banco de dados migrados &#40;SybaseToSQL&#41;](../../ssma/sybase/testing-migrated-database-objects-sybasetosql.md)  
  
