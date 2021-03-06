---
title: PROVIDER_PROCESS_DATA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- PROVIDER_PROCESS_DATA
helpviewer_keywords:
- PROVIDER_PROCESS_DATA structure
ms.assetid: ec2362ed-4a0c-4a09-9d66-8ff04e4f41ee
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 61b1b5d67faea0ce5c1c2a56b3f411cd4f947067
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126668"
---
# <a name="providerprocessdata"></a>PROVIDER_PROCESS_DATA
Essa estrutura fornece informações sobre os processos em execução em um computador.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
typedef struct tagPROVIDER_PROCESS_DATA {  
   PROVIDER_FIELDS    Fields;  
   PROGRAM_NODE_ARRAY ProgramNodes;  
   BOOL               fIsDebuggerPresent;  
} PROVIDER_PROCESS_DATA;  
```  
  
```csharp  
public struct PROVIDER_PROCESS_DATA {  
   public uint               Fields;  
   public PROGRAM_NODE_ARRAY ProgramNodes;  
   public int                fIsDebuggerPresent;  
}  
```  
  
## <a name="members"></a>Membros  
 Campos  
 Uma combinação de sinalizadores do [PROVIDER_FIELDS](../../../extensibility/debugger/reference/provider-fields.md) enumeração, que indica quais campos são preenchidos.  
  
 ProgramNodes  
 Um [PROGRAM_NODE_ARRAY](../../../extensibility/debugger/reference/program-node-array.md) estrutura que contém uma matriz de nós de programa.  
  
 fIsDebuggerPresent  
 Diferente de zero (`TRUE`) se o [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] depurador está em execução, zero (`FALSE`) se não for.  
  
## <a name="remarks"></a>Comentários  
 Essa estrutura é passada para o [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md) método em que ele é preenchido.  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte também  
 [Estruturas e uniões](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [PROVIDER_FIELDS](../../../extensibility/debugger/reference/provider-fields.md)   
 [PROGRAM_NODE_ARRAY](../../../extensibility/debugger/reference/program-node-array.md)   
 [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)