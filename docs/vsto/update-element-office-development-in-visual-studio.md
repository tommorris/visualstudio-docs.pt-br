---
title: '&lt;atualizar&gt; elemento (desenvolvimento do Office no Visual Studio)'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- update element
- <update> element
- application manifests [Office development in Visual Studio], <update> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c51a7f79165d421f080d05088418d02a48680b66
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767602"
---
# <a name="ltupdategt-element-office-development-in-visual-studio"></a>&lt;atualizar&gt; elemento (desenvolvimento do Office no Visual Studio)
  O `update` elemento Especifica o intervalo no qual a solução irá verificar atualizações.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<update  
  enabled>  
  <expiration  
    maximumAge  
    unit  
  />  
</update>  
```  
  
## <a name="elements-and-attributes"></a>Elementos e atributos  
 O `update` elemento é necessário e está no `vstav3` namespace.  
  
 O `update` elemento tem os seguintes atributos.  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|`enabled`|Necessário. Defina habilitado como um dos valores a seguir:<br /><br /> -   **True** para verificar se há atualizações.<br />-   **False** para evitar a verificação de atualizações.|  
  
 O `update` elemento tem os seguintes elementos filho.  
  
### <a name="expiration"></a>expiração  
 O `expiration` elemento é necessário e está no `vstav3` namespace. Este elemento Especifica o intervalo no qual a solução verifica as atualizações.  
  
 O `expiration` elemento tem os seguintes atributos.  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|`maximumAge`|   Necessário. Defina isso como um número inteiro.|  
|`unit`|Necessário. Definir `unit` para um dos seguintes valores:<br /><br /> -   **Horas**<br />-   **Dias**<br />-   **Semanas**|  
  
## <a name="example-of-always-checking-for-updates"></a>Exemplo de sempre verificar atualizações  
  
### <a name="description"></a>Descrição  
 O exemplo de código a seguir ilustra um `update` elemento que é definido como sempre verifique se há atualizações em soluções do Office.  
  
### <a name="code"></a>Código  
  
```xml  
<vstav3:update enabled="true" />  
```  
  
## <a name="example-of-setting-a-default-update-interval"></a>Exemplo de definição de um intervalo de atualização padrão  
  
### <a name="description"></a>Descrição  
 O exemplo de código a seguir ilustra um `update` elemento em um manifesto de aplicativo para soluções do Office. Este exemplo de código é parte de um exemplo maior fornecido em [manifestos de aplicativo para soluções do Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Código  
  
```xml  
<vstav3:update enabled="true">  
    <vstav3:expiration maximumAge="7" unit="days" />  
</vstav3:update>  
```  
  
## <a name="see-also"></a>Consulte também  
 [Implantar uma solução do Office usando ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Manifestos de aplicativo para soluções do Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifestos de implantação para soluções do Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [Manifesto do aplicativo ClickOnce](/visualstudio/deployment/clickonce-application-manifest)  
  
  