---
title: 'Etapa 2: Inicializar a caixa de listagem principal | Microsoft Docs'
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
ms.assetid: a1454493-1c86-46c2-ada8-d3c6fcdaf3c1
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 90b7d50d6cb0a6fd8c0814d1b4bcbb631e5e8376
ms.sourcegitcommit: 6443f9a281904af93f0f5b78760b1c68901b7b8d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53206415"
---
# <a name="step-2-initialize-the-main-list-box"></a>Etapa 2: Inicializar a caixa de listagem principal
Para declarar objetos globais de registro e o conjunto de registros, insira o código a seguir (geral) (declarações) para Form1:  
  
```  
Option Explicit  
Dim grec As Record  
Dim grs As Recordset  
```  
  
 Esse código declara referências de objeto global para objetos de registro e o conjunto de registros que serão usados mais tarde neste cenário.  
  
## <a name="to-connect-to-a-url-and-populate-lstmain"></a>Para se conectar a uma URL e popular lstMain  
 Insira o seguinte código no manipulador de eventos de carregamento de formulário para Form1:  
  
```  
Private Sub Form_Load()  
    Set grec = New Record  
    Set grs = New Recordset  
    grec.Open "", "URL=https://servername/foldername/", , _  
        adOpenIfExists Or adCreateCollection  
    Set grs = grec.GetChildren  
    While Not grs.EOF  
        lstMain.AddItem grs(0)  
        grs.MoveNext  
    Wend  
End Sub  
```  
  
 Esse código instancia os objetos globais de registro e o conjunto de registros. O objeto de registro, `grec`, é aberta com uma URL especificada como o ActiveConnection. Se a URL existir, ele é aberto; Se ele ainda não existir, ele será criado. Observe que você deve substituir "<https://servername/foldername/>" com uma URL válida do seu ambiente.  
  
 O objeto de conjunto de registros `grs`, é aberta nos filhos do registro, `grec`. Em seguida, `lstMain` é preenchida com os nomes de arquivo dos recursos publicados para a URL.  
  
## <a name="see-also"></a>Consulte também  
 [Cenário de publicação na Internet](../../../ado/guide/data/internet-publishing-scenario.md)   
 [Etapa 1: Configurar o projeto do Visual Basic](../../../ado/guide/data/step-1-set-up-the-visual-basic-project.md)   
 [Etapa 3: Preencha a caixa de lista de campos](../../../ado/guide/data/step-3-populate-the-fields-list-box.md)
