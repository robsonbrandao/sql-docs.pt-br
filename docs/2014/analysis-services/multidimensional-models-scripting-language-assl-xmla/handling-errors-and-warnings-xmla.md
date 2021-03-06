---
title: Tratamento de erros e avisos (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- errors [XML for Analysis]
- inline errors [XMLA]
- SOAP faults [XML for Analysis]
- XML for Analysis, errors
- faults [XML for Analysis]
- messages [XML for Analysis]
- XMLA, errors
- warnings [XML for Analysis]
- inline warnings [XMLA]
ms.assetid: ab895282-098d-468e-9460-032598961f45
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 5a41e9cedf8a2a19aea0cf8a374bc71f520ff52f
ms.sourcegitcommit: 7fe14c61083684dc576d88377e32e2fc315b7107
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/26/2018
ms.locfileid: "50147741"
---
# <a name="handling-errors-and-warnings-xmla"></a>Manipulando erros e avisos (XMLA)
  Tratamento de erros é necessário quando um XML for Analysis (XMLA) [Discover](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) ou [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) chamada de método não é executado, é executado com êxito, mas gera erros ou avisos, ou seja executado com êxito, mas retorna resultados que contêm erros.  
  
|Erro|Relatório|  
|-----------|---------------|  
|A chamada de método XMLA não é executada|[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Retorna uma mensagem de falha SOAP que contém os detalhes da falha.<br /><br /> Para obter mais informações, consulte a seção [tratamento de falhas de SOAP](#handling_soap_faults).|  
|Erros ou avisos em uma chamada de método com êxito|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] inclui um [erro](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/error-element-xmla) ou [aviso](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/warning-element-xmla) elemento para cada erro ou aviso, respectivamente, no [mensagens](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla) propriedade do [raiz](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/root-element-xmla) elemento que contém os resultados da chamada de método.<br /><br /> Para obter mais informações, consulte a seção [Handling Errors and Warnings](#handling_errors_and_warnings).|  
|Erros no resultado de uma chamada de método com êxito|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] inclui um embutido `error` ou `warning` elemento para o erro ou aviso, respectivamente, com um intervalo apropriado [célula](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) ou [linha](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/row-element-xmla) elemento dos resultados da chamada de método.<br /><br /> Para obter mais informações, consulte a seção [tratamento de erros e avisos embutidos](#handling_inline_errors_and_warnings).|  
  
##  <a name="handling_soap_faults"></a> Tratamento de falhas de SOAP  
 O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retorna uma falha SOAP quando ocorrem as seguintes situações:  
  
-   A mensagem SOAP que contém o método XMLA não foi bem formada ou não pôde ser validada pela instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].  
  
-   Houve um erro de comunicação ou outro erro envolvendo a mensagem SOAP que contém o método XMLA.  
  
-   O método XMLA não foi executado na instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].  
  
 Os códigos de falha SOAP para XMLstartA começam com "XMLForAnalysis", seguido por um ponto e o código de resultado hexadecimal HRESULT. Por exemplo, um código de erro "`0x80000005`" é formatado como "`XMLForAnalysis.0x80000005`". Para obter mais informações sobre o formato de falha SOAP, consulte Falha Soap no protocolo SOAP 1.1 do W3C.  
  
### <a name="fault-code-information"></a>Informações de código de falha  
 A tabela a seguir mostra as informações de código de falha XMLA contidas na sessão de detalhe da resposta SOAP. As colunas são os atributos de um erro na seção de detalhe de uma falha SOAP.  
  
|Nome da coluna|Tipo|Description|Nulo permitido<sup>1</sup>|  
|-----------------|----------|-----------------|------------------------------|  
|`ErrorCode`|`UnsignedInt`|Código de retorno que indica o êxito ou a falha do método. O valor hexadecimal deve ser convertido para um valor `UnsignedInt`.|não|  
|`WarningCode`|`UnsignedInt`|Código de retorno que indica uma condição de aviso. O valor hexadecimal deve ser convertido para um valor `UnsignedInt`.|Sim|  
|`Description`|`String`|Texto e descrição de erro ou de aviso retornadas pelo componente que gerou o erro.|Sim|  
|`Source`|`String`|Nome do componente que gerou o erro ou o aviso.|Sim|  
|`HelpFile`|`String`|Caminho ou URL para o arquivo de Ajuda ou tópico que descreve o erro ou o aviso.|Sim|  
  
 <sup>1</sup> indica se os dados é obrigatório e devem ser retornados, ou se os dados são opcionais e uma cadeia de caracteres nula será permitida se a coluna não se aplica.  
  
 A seguir, um exemplo de uma falha SOAP ocorrida quando uma chamada de método falhou:  
  
```  
<?xml version="1.0"?>  
   <SOAP-ENV:Envelope  
   xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
   SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
      <SOAP-ENV:Fault>  
         <faultcode>XMLAnalysisError.0x80000005</faultcode>  
         <faultstring>The XML for Analysis provider encountered an error.</faultstring>  
         <faultactor>XML for Analysis Provider</faultactor>  
         <detail>  
<Error  
ErrorCode="2147483653"  
Description="An unexpected error has occurred."  
Source="XML for Analysis Provider"  
HelpFile="" />  
         </detail>  
      </SOAP-ENV:Fault>  
</SOAP-ENV:Envelope>  
```  
  
##  <a name="handling_errors_and_warnings"></a> Tratamento de erros e avisos  
 O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retornará a propriedade `Messages` no elemento `root` para um comando se as situações a seguir ocorrerem após a execução do comando:  
  
-   O próprio método não falhou, mas houve uma falha na instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] após o êxito da chamada de método.  
  
-   A instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retorna um aviso quando o comando tem êxito.  
  
 A propriedade `Messages` segue todas as outras propriedades contidas pelo elemento `root` e pode conter um ou mais elementos `Message`. Por sua vez, cada elemento `Message` pode conter um único elemento `error` ou `warning` descrevendo erros ou avisos, respectivamente, ocorridos para o comando especificado.  
  
 Para obter mais informações sobre erros e avisos estão contidos na `Messages` propriedade, consulte [mensagens elemento &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla).  
  
### <a name="handling-errors-during-serialization"></a>Manipulando erros durante a serialização  
 Se ocorrer um erro após o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instância já tiver começado a serializar a saída de um comando executado com êxito, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retorna um [exceção](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/exception-element-xmla) elemento em um namespace diferente no ponto do erro. A instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fechará todos os elementos abertos para que o documento XML enviado ao cliente seja um documento válido. A instância também retornará um elemento `Messages` com a descrição do erro.  
  
##  <a name="handling_inline_errors_and_warnings"></a> Tratamento de erros e avisos embutidos  
 O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retornará um `error` ou `warning` embutido para um comando se o próprio método XMLA não tenha falhado, mas houve um erro específico de um elemento de dados nos resultados retornados pelo método na instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] após o êxito da chamada de método XMLA.  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Fornece embutido `error` e `warning` elementos se problemas específicos para uma célula ou outros dados que são contidos em um `root` elemento usando o [MDDataSet](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/mddataset-data-type-xmla) ocorra de tipo de dados, como uma segurança erro ou a formatação Erro de uma célula. Nesses casos, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retorna um elemento `error` ou `warning` no elemento `Cell` ou `row` que contém o erro ou o aviso, respectivamente.  
  
 O exemplo a seguir ilustra um conjunto de resultados que contém um erro no conjunto de linhas retornado de uma `Execute` usando o método de [instrução](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) comando.  
  
```  
<return>  
   ...  
   <root>  
      ...  
      <CellData>  
      ...  
         <Cell CellOrdinal="10">  
            <Value>  
               <Error>  
                  <ErrorCode>2148497527</ErrorCode>   
                  <Description>Security Error.</Description>   
               </Error>  
            </Value>  
         </Cell>  
      </CellData>  
      ...  
   </root>  
   ...  
</return>  
```  
  
## <a name="see-also"></a>Consulte também  
 [Desenvolvendo com XMLA no Analysis Services](developing-with-xmla-in-analysis-services.md)  
  
  
