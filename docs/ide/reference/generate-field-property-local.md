---
title: Gerar um campo, uma propriedade ou uma variável local no Visual Studio
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 4cff83eb490f8012e8679dbd0b2c6a65d27f8e14
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31945084"
---
# <a name="generate-a-field-property-or-local-variable-in-visual-studio"></a>Gerar um campo, uma propriedade ou uma variável local no Visual Studio

Esta geração de código aplica-se a:

- C#

- Visual Basic

**O quê:** permite gerar imediatamente o código para um campo, propriedade ou local não declarada anteriormente.

**Quando:** você introduz um novo campo, propriedade ou local durante a digitação e quer declará-la correta e automaticamente.

**Por quê:** você poderia declarar o campo, propriedade ou local antes de usá-lo; no entanto, esse recurso gerará a declaração ou o tipo automaticamente.

## <a name="how-to"></a>Como fazer

1. Coloque o cursor na linha em que há um rabisco vermelho. O rabisco vermelho indica um campo, um local ou uma propriedade que ainda não existe.

   - C#:

    ![Código em C# realçado](media/field-highlight-cs.png)

   - Visual Basic:

    ![Código em VB realçado](media/field-highlight-vb.png)

1. Depois, siga um destes procedimentos:

   - **Teclado**
     - Pressione **Ctrl**+**.** para acionar o menu **Ações e Refatorações Rápidas**.
   - **Mouse**
     - Clique com o botão direito do mouse e selecione o menu **Ações Rápidas e Refatorações**.
     - Passe o mouse sobre o rabisco vermelho e clique no ícone de ![Lâmpada](media/bulb-cs.png) que aparece.
     - Clique no ícone de ![Lâmpada](media/bulb-cs.png) que aparece na margem esquerda se o cursor de texto já estiver na linha com o rabisco vermelho.

    ![Visualização da geração de campo/propriedade/local](media/field-preview-cs.png)

1. Selecione uma das opções de geração no menu suspenso.

   > [!TIP]
   > Use o link **Visualizar alterações** na parte inferior da janela de visualização [para ver todas as alterações](../../ide/preview-changes.md) que serão feitas antes de fazer sua seleção.

   O campo, a propriedade ou o local é criado, com o tipo inferido de seu uso.

   - C#:

      ![Gerar o resultado do método C#](media/field-result-cs.png)

   - Visual Basic:

      ![Gerar o resultado do método VB](media/field-result-vb.png)

## <a name="see-also"></a>Consulte também

- [Geração de código](../code-generation-in-visual-studio.md)
- [Visualizar alterações](../../ide/preview-changes.md)