---
title: Como exportar um sombreador
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 0bd48bf4-9792-4456-a545-e462a2be668d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1eb69a4662521c08fc8d2df34bbbfa41a5d1d7ea
ms.sourcegitcommit: db680e8fa8066f905e7f9240342ece7ab9259308
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2018
ms.locfileid: "37924073"
---
# <a name="how-to-export-a-shader"></a>Como exportar um sombreador
Este documento demonstra como usar o Designer de Sombreador para exportar um sombreador da DGSL (Directed Graph Shader Language) para poder usá-lo em seu aplicativo.

 Este documento demonstra esta atividade:

-   Exportar um sombreador

## <a name="exporting-a-shader"></a>Exportar um sombreador
 Depois de criar um sombreador usando o Designer de Sombreador é necessário exportá-lo em um formato que seja compreendido pela API de gráficos antes de usá-lo em seu aplicativo. Você pode exportar um sombreador de maneiras diferentes para atender a necessidades diferentes.

### <a name="to-export-a-shader"></a>Para exportar um sombreador

1.  No [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], abra uma arquivo do **Visual Shader Graph (.dgsl)**.

     Se você não tiver um arquivo **Visual Shader Graph (.dgsl)** para abrir, crie um conforme a descrição em [Como criar um sombreador de cor básico](../designers/how-to-create-a-basic-color-shader.md).

2.  Na barra de ferramentas **Designer de Sombreador**, escolha **Avançado** > **Exportar** > **Exportar Como**. A caixa de diálogo **Exportar Sombreador** é exibida.

3.  Na lista suspensa **Salvar como tipo**, escolha o formato que você deseja exportar.

     Aqui estão os formatos que você pode escolher:

     **Sombreador de Pixel HLSL (\*.hlsl)** Exporta o sombreador como código-fonte HLSL (High Level Shader Language). Essa opção possibilita modificar o sombreador posteriormente, mesmo depois que ele for implantado em um aplicativo. Isso pode tornar mais fácil depurar e corrigir o código com base em problemas de usuários finais, mas também torna mais fácil para um usuário modificar o sombreador de formas indesejáveis, por exemplo, para obter uma vantagem injusta em um jogo de competição. Isso também pode aumentar o tempo de carregamento do sombreador.

     **Sombreador de Pixel Compilado (\*.cso)** Exporta o sombreador como um código de bytes HLSL. Essa opção possibilita modificar o sombreador posteriormente, mesmo depois que ele for implantado em um aplicativo. Isso pode tornar mais fácil depurar e corrigir o código com base em problemas de usuários finais, mas como o sombreador é pré-compilado, ele não incorre em sobrecarga adicional de tempo de execução quando o sombreador é carregado pelo aplicativo. Usuários suficientemente habilidosos ainda podem modificar o sombreador de formas indesejáveis, mas a compilação do sombreador torna isso muito mais difícil.

     **Cabeçalho C++ (\*.h)** Exporta o sombreador como um cabeçalho de estilo C que define uma matriz de bytes que contém o código de bytes HLSL. Essa opção pode fazer com que a depuração e correção do código com base em problemas do usuário final se tornem mais demoradas porque o aplicativo tem que ser recompilado para testar a correção. No entanto, como esta opção torna difícil, mas não impossível, a modificação do sombreador depois de ser implantado em um aplicativo, ela apresenta maior dificuldade para um usuário que deseja modificar o sombreador de formas indesejáveis.

4.  Na caixa de combinação **Nome de arquivo**, especifique um nome para o sombreador exportado e, em seguida, escolha o botão **Salvar**.

## <a name="see-also"></a>Consulte também

- [Como criar um sombreador de cor básico](../designers/how-to-create-a-basic-color-shader.md)
- [Designer de Sombreador](../designers/shader-designer.md)