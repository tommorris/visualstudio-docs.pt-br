---
title: Visão geral da interface de usuário das Ferramentas de Linguagem Específica do Domínio
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.dsldesigner.editor
helpviewer_keywords:
- Domain-Specific Language Tools, user interface
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 8ab473e4835e4ba6467a9af83e69bfabc43e8236
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748719"
---
# <a name="overview-of-the-domain-specific-language-tools-user-interface"></a>Visão geral da interface de usuário das Ferramentas de Linguagem Específica do Domínio
Quando você abre uma solução de ferramentas de linguagem específica de domínio (ferramentas de DSL) em [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], a interface do usuário será semelhante a figura a seguir.

 ![designer de DSL](../modeling/media/dsl_designer.png)

 A tabela a seguir explica como as partes da interface do usuário são usadas.

|**Elemento**|**Definição**|
|-----------------|--------------------|
|Diagrama|O diagrama exibe o modelo de domínio.<br /><br /> O diagrama tem dois lados. Um lado define os tipos de elementos em seus modelos. O outro lado define como seus modelos aparecerá na tela.|
|Caixa de Ferramentas|Arraste as ferramentas da caixa de ferramentas para adicionar classes de domínio e tipos ao diagrama de forma. Para adicionar relações, conectores e mapas de formas, a ferramenta, clique o nó de origem no diagrama e, em seguida, o nó de destino.|
|DSL Explorer|**Gerenciador de DSL** aparece quando uma definição de DSL é a janela ativa. Ele mostra o DSL como uma árvore. DSL Explorer permite editar os recursos do modelo que não são exibidos no diagrama. Por exemplo, você pode adicionar itens da caixa de ferramentas e alternar o processo de validação usando o **DSL Explorer**.|
|Janela detalhes DSL|O **DSL detalhes** janela mostra propriedades do domínio elementos do modelo que permitem controlar como os elementos são exibidos e como os elementos são copiados e excluídos.<br /><br /> -Por padrão, o **DSL detalhes** janela aparece ao lado de **lista de erros** e **saída** windows.|

## <a name="the-domain-model-diagram"></a>O diagrama de modelo de domínio
 O diagrama de modelo de domínio é dividido em duas partes. Um lado do diagrama mostra os elementos e as relações no modelo. O outro lado mostra como o modelo é exibido e inclui as formas que são usadas para exibir os elementos e as propriedades do diagrama de modelo. A figura a seguir mostra os elementos do diagrama.

 ![designer de DSL com swimlane](../modeling/media/dsl_desinger.png)

 A tabela a seguir explica alguns dos elementos do diagrama de modelo de domínio.

|**Termo**|**Definição**|
|--------------|--------------------|
|Classe de domínio|Classes de domínio são os tipos de elementos em seus modelos.<br /><br /> Uma classe de domínio pode aparecer mais de uma vez em um diagrama, se ele é o destino de mais de uma relação.<br /><br /> Para adicionar uma classe de domínio, arraste a ferramenta de classe de domínio do **caixa de ferramentas** para o **Classes e relacionamentos** lado do diagrama.|
|Relacionamento de domínio|Relações de domínio são os tipos de links entre elementos nos seus modelos.<br /><br /> Um *relacionamento de incorporação* indica que o elemento de destino é de propriedade ou contido no elemento de origem e aparece como uma linha sólida. Cada elemento em um modelo deve ser o destino de um relacionamento de incorporação, para que o modelo de uma árvore de formulários. Um *relação de referência* indica um link geral entre elementos de modelo e aparece como uma linha tracejada. Qualquer elemento pode ter qualquer número de links de referência.<br /><br /> Criar uma relação clicando na ferramenta sobre o **caixa de ferramentas**, clicando na classe de domínio de origem e, em seguida, clicando na classe de destino.|
|Formas e Conectores|Formas de especificam como os elementos de modelo devem ser exibidos em um diagrama DSL., conectores Especifique linhas em um diagrama DSL que pode ser usado para exibir relações.<br /><br /> Para criar um conector ou forma, arraste a ferramenta de **elementos de diagrama** lado do diagrama.|
|Mapas de formas|Um mapa de formas aparece como o diagrama de modelo de domínio, uma forma de vinculação para a classe de domínio que ele exibe, ou um conector para o relacionamento de domínio que ele exibe uma linha.|

## <a name="see-also"></a>Consulte também

- [Visão geral das Ferramentas de Linguagem Específica de Domínio](../modeling/overview-of-domain-specific-language-tools.md)
- [Glossário de ferramentas de linguagem específica de domínio](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
- [Personalizando e estendendo uma linguagem específica de domínio](../modeling/customizing-and-extending-a-domain-specific-language.md)