---
title: IDiaStackWalkFrame | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame interface
ms.assetid: 42d82845-d6f6-4846-9ecd-9dd169216077
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c525d2c19f3bc4ab7ea540ac129931583064db01
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47460944"
---
# <a name="idiastackwalkframe"></a>IDiaStackWalkFrame
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [IDiaStackWalkFrame](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackwalkframe).  
  
Mantém o contexto de pilha entre invocações da [idiaframedata:: execute](../../debugger/debug-interface-access/idiaframedata-execute.md) método.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
IDiaStackWalkFrame : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Métodos na ordem de Vtable  
 A tabela a seguir mostra os métodos de `IDiaStackWalkFrame`.  
  
|Método|Descrição|  
|------------|-----------------|  
|[IDiaStackWalkFrame::get_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-get-registervalue.md)|Recupera o valor de um registro.|  
|[IDiaStackWalkFrame::put_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-put-registervalue.md)|Define o valor de um registro.|  
|[IDiaStackWalkFrame::readMemory](../../debugger/debug-interface-access/idiastackwalkframe-readmemory.md)|Lê a memória da imagem.|  
|[IDiaStackWalkFrame::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddress.md)|Pesquisa o quadro de pilha especificada para o endereço de retorno de função mais próximo.|  
|[IDiaStackWalkFrame::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddressstart.md)|Pesquisa o quadro de pilha especificada para um endereço de retorno em ou próximo o endereço especificado.|  
  
## <a name="remarks"></a>Comentários  
 Essa interface é usada durante a execução do programa para ler e gravar registros, bem como acessar a memória e localizar endereços de retornados.  
  
## <a name="notes-for-callers"></a>Observações para chamadores  
 O aplicativo cliente implementa essa interface e passa uma instância da interface para o [idiaframedata:: execute](../../debugger/debug-interface-access/idiaframedata-execute.md) método. A mesma instância dessa interface é usada várias vezes para manter o estado dos registros durante cada chamada a `execute` método. O `execute` método também usa essa interface para determinar o endereço de retorno.  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: Dia2.h  
  
 Biblioteca: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Consulte também  
 [Interfaces (SDK de acesso à Interface de depuração)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaFrameData::execute](../../debugger/debug-interface-access/idiaframedata-execute.md)



