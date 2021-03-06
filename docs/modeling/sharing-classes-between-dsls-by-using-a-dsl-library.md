---
title: Compartilhando classes entre DSLs por meio de uma biblioteca de DSLs
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 5a48ba42982ea8f190fca2e13d714cb99cb01490
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31949453"
---
# <a name="sharing-classes-between-dsls-by-using-a-dsl-library"></a>Compartilhando classes entre DSLs por meio de uma biblioteca de DSLs
No [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] visualização e modelagem SDK, você pode criar uma definição de DSL incompleto que você pode importar para outro DSL. Isso lhe permite fatores partes comuns de modelos semelhantes.

## <a name="creating-and-using-dsl-libraries"></a>Criando e usando bibliotecas de DSL

#### <a name="to-create-a-dsl-library"></a>Para criar uma biblioteca de DSL

1.  Criar um novo projeto DSL e escolha o modelo de solução de biblioteca de DSL.

     Um único projeto DSL será criado com um modelo vazio.

2.  Você pode adicionar classes de domínio, relações, formas e assim por diante.

     Os elementos na biblioteca não é necessário que formar uma única árvore de incorporação.

     Para definir uma relação que podem usar importadores, crie duas classes de domínio e criar a relação entre eles.

     É recomendável configurar o **modificador de herança** das classes de domínio para `Abstract`.

3.  Você pode adicionar elementos que você definir no Explorer DSL, como construtores de Conexão.

4.  Você pode adicionar personalizações que exigem o código adicional, como restrições de validação.

5.  Clique em **transformar todos os modelos**.

6.  Compile o projeto.

7.  Quando você distribui DSL para outros usuários, você deve fornecer o assembly (DLL) e o arquivo `DslDefinition.dsl`. Você pode encontrar o assembly compilado em uma pasta sob `Dsl\bin\*`

#### <a name="to-import-a-dsl-library"></a>Para importar uma biblioteca de DSL

1.  Em outra definição de DSL em **DSL Explorer**, clique com botão direito a classe raiz do DSL e, em seguida, clique em **adicionar nova importação DslLibrary**.

2.  Na janela Propriedades, defina o **caminho do arquivo** da biblioteca. Você pode usar um caminho absoluto ou relativo.

     A biblioteca importada aparece no Gerenciador de DSL, no modo somente leitura.

3.  Você pode usar as classes importadas como classes base. Criar uma classe de domínio em que a importação DSL e nas propriedades da janela, defina **classe Base** para uma classe importada.

4.  Clique em transformar todos os modelos.

5.  Adicione ao projeto DSL uma referência ao assembly (DLL) que foi compilado pelo projeto biblioteca DSL.

6.  Compile a solução.

 Uma biblioteca de DSL pode importar outras bibliotecas. Quando você importa uma biblioteca, suas importações aparecem automaticamente no Explorer de DSL.

## <a name="see-also"></a>Consulte também

- [Como definir uma linguagem específica de domínio](../modeling/how-to-define-a-domain-specific-language.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
