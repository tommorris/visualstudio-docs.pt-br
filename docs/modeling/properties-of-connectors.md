---
title: Propriedades de conectores
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, connectors
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: e8954727d7ee38b81ba5993b41e300ef1c6d66fc
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31952725"
---
# <a name="properties-of-connectors"></a>Propriedades de conectores
Conectores de representam relações de domínio em um designer gerado.

 Para obter mais informações, consulte [como definir uma linguagem específica do domínio](../modeling/how-to-define-a-domain-specific-language.md). Para obter mais informações sobre como usar essas propriedades, consulte [personalizar e estender uma linguagem específica do domínio](../modeling/customizing-and-extending-a-domain-specific-language.md).

 Conectores têm as propriedades que são listadas na tabela a seguir.

|Propriedade|Descrição|Padrão|
|--------------|-----------------|-------------|
|Cor|A cor desse conector.|Preto|
|Estilo de traço|O estilo de traço para a linha para este conector (sólido, tracejado, ponto, Traçoponto, Traçopontoponto ou personalizado).|Sólido|
|Estilo de final de origem|O estilo de final de origem para este conector (HollowArrow, EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond ou None).|Nenhum|
|Estilo de final de destino|O estilo de final de destino para este conector (HollowArrow, EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond ou None).|Nenhum|
|Cor do texto|A cor que é usada para decoradores de texto que estão associados este conector.|Preto|
|Espessura|A espessura da linha para esse conector, medida em polegadas.|0.03125|
|Modificador de acesso|O nível de acesso da classe (`public` ou `internal`).|Público|
|Atributos personalizados|Usado para adicionar atributos para a classe do código fonte que é gerada a partir deste conector.|\<Nenhum >|
|Gera dois derivado|Se `True`, uma classe base e uma classe parcial (para dar suporte a personalização por meio de substituições) será gerada. Para obter mais informações, consulte [substituir e estender as Classes geradas pelo](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Tem um construtor personalizado|Se `True`, será fornecido um construtor personalizado no código-fonte. Para obter mais informações, consulte [substituir e estender as Classes geradas pelo](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Modificador de herança|Descreve o tipo de herança da classe de código fonte que é gerada a partir do conector (`none`, `abstract` ou `sealed`).|nenhum|
|Conector de base|A classe base deste conector.|(nenhum)|
|Nome|O nome deste conector.|Nome atual|
|Namespace|O namespace que é associado a esse conector.|Namespace atual|
|Tipo de dica de ferramenta|Como a dica de ferramenta é definida (fixo, variável ou nenhum). Se for resolvido, em seguida, o valor da `Fixed Tooltip Text` propriedade é usada como a dica de ferramenta; se a variável, em seguida, a dica de ferramenta é definida no código personalizado.|\<Nenhum >|
|Observações|Anotações informais que estão associadas este conector.|\<Nenhum >|
|Estilo de roteamento|O estilo que é usado para o conector de roteamento. Um `Rectilinear` conector torna ativa ângulo à direita conforme necessário; um `Straight` conector não.|Retilíneos|
|Cor exposto como propriedade<br /><br /> Estilo do tracejado exposto como propriedade<br /><br /> Espessura exposta como propriedade<br /><br /> Expõe a cor do texto|Se `True`, o usuário pode definir a propriedade declarada de uma forma. Para definir isso, a definição de forma de mouse e clique em **adicionar expostos**.|False|
|Descrição|Usado para documentar o designer gerado.|\<Nenhum >|
|Nome de Exibição|O nome que será exibido no designer gerado para este conector.|\<Nenhum >|
|Texto de dica de ferramenta fixo|O texto que é usado para uma dica de ferramenta fixa.|\<Nenhum >|
|Palavra-chave de ajuda|A palavra-chave que é usada para indexar a Ajuda de F1 para este elemento.|\<Nenhum >|

## <a name="see-also"></a>Consulte também

- [Glossário de ferramentas de linguagem específica de domínio](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)