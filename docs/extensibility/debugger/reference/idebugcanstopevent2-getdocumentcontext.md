---
title: IDebugCanStopEvent2::GetDocumentContext | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCanStopEvent2::GetDocumentContext
helpviewer_keywords:
- IDebugCanStopEvent2::GetDocumentContext
ms.assetid: 936a6c4e-30c5-4c7e-9ad5-910cc605a4b5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0e5b9bbd5127ac3cf7aef70744fc80ebc8372dfb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31106238"
---
# <a name="idebugcanstopevent2getdocumentcontext"></a>IDebugCanStopEvent2::GetDocumentContext
Obtém o contexto de documento que descreve o local desse evento.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetDocumentContext (   
   IDebugDocumentContext2** ppDocCxt  
);  
```  
  
```csharp  
int GetDocumentContext (   
   out IDebugDocumentContext2 ppDocCxt  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `ppDocCxt`  
 [out] Retorna o [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) interface que representa uma posição em um documento do arquivo de origem correspondente para o local atual do código.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, retorna `S_OK`; caso contrário, retorna um código de erro.  
  
## <a name="remarks"></a>Comentários  
 Em geral, o contexto do documento pode ser pensado como uma posição em um arquivo de origem.  
  
 Para obter o contexto de código, que é orientado para instruções de código, chame o [GetCodeContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getcodecontext.md) método.  
  
## <a name="see-also"></a>Consulte também  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getcodecontext.md)