---
title: IDebugReference2::GetDerivedMostReference | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugReference2::GetDerivedMostReference
helpviewer_keywords:
- IDebugReference2::GetDerivedMostReference
ms.assetid: 07253b74-7d39-48e0-8e85-ac8dfd919f6e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: cfa0e6b6755ea884b6dd9b6ba0409a614e80e290
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31119198"
---
# <a name="idebugreference2getderivedmostreference"></a>IDebugReference2::GetDerivedMostReference
Obtém a referência mais derivado de uma referência. Reservado para uso futuro.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetDerivedMostReference(   
   IDebugReference2** ppDerivedMost  
);  
```  
  
```csharp  
int GetDerivedMostReference(   
   out IDebugReference2 ppDerivedMost  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `ppDerivedMost`  
 [out] Retorna um [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objeto que representa a propriedade mais derivado.  
  
## <a name="return-value"></a>Valor de retorno  
 Sempre retorna `E_NOTIMPL`.  
  
## <a name="remarks"></a>Comentários  
 Por exemplo, se esta propriedade descreve um objeto que implementa `ClassRoot` , mas que é realmente uma instanciação de `ClassDerived` que é derivado de `ClassRoot`, em seguida, esse método retorna um [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objeto que representa uma referência para o `ClassDerived` objeto.  
  
## <a name="see-also"></a>Consulte também  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)