---
title: AD_PROCESS_ID_TYPE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- AD_PROCESS_ID_TYPE
helpviewer_keywords:
- AD_PROCESS_ID_TYPE enumeration
ms.assetid: 0aab80e9-285a-4697-94ac-c864d42a6aaa
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f8318efdc64adf9792e44ccf2f4ad4aa9f74dd67
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31098281"
---
# <a name="adprocessidtype"></a>AD_PROCESS_ID_TYPE
Especifica como interpretar uma ID de processo de [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) estrutura.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
enum enum_AD_PROCESS_ID {  
   AD_PROCESS_ID_SYSTEM = 0,  
   AD_PROCESS_ID_GUID   = 1  
};  
typedef DWORD AD_PROCESS_ID_TYPE;  
```  
  
```csharp  
public enum enum_AD_PROCESS_ID {  
   AD_PROCESS_ID_SYSTEM = 0,  
   AD_PROCESS_ID_GUID   = 1  
};  
```  
  
## <a name="members"></a>Membros  
 AD_PROCESS_ID_SYSTEM  
 ID do processo é um identificador de sistema. Use o `ProcessId.dwProcessId` campo o [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) estrutura.  
  
 AD_PROCESS_ID_GUID  
 ID do processo é um GUID. Use o `ProcessId.guidProcessId` campo o `AD_PROCESS_ID` estrutura.  
  
## <a name="remarks"></a>Comentários  
 Usado para o `ProcessIdType` membro o [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) estrutura para identificar o tipo de ID de processo que está contido na estrutura. Determina como interpretar o `ProcessId` union na estrutura.  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte também  
 [Enumerações](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)