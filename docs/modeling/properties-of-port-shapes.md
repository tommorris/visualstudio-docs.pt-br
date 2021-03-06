---
title: Propriedades de formas de porta
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.port
helpviewer_keywords:
- Domain-Specific Language, port shape
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: f070d9c8c7283542dc9f2af921698245a2075f66
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31951239"
---
# <a name="properties-of-port-shapes"></a>Propriedades de formas de porta
Você pode usar formas de porta para representar as classes de domínio no designer de gerado.

 Para obter mais informações, consulte [como definir uma linguagem específica do domínio](../modeling/how-to-define-a-domain-specific-language.md). Para obter mais informações sobre como usar essas propriedades, consulte [personalizar e estender uma linguagem específica do domínio](../modeling/customizing-and-extending-a-domain-specific-language.md).

 Formas de porta tem as propriedades que são listadas na tabela a seguir.

|Propriedade|Descrição|Padrão|
|--------------|-----------------|-------------|
|Cor de preenchimento|A cor de preenchimento dessa forma.|Branco|
|Preencher o modo de gradiente|O modo de preenchimento a gradação dessa forma.|Horizontal|
|Geometry|A geometria dessa forma (retângulo, retângulo arredondado, elipse ou círculo).|Retângulo|
|Tem pontos de Conexão padrão|Se `True`, a forma usará superior, inferior, esquerda e pontos de conexão à direita no designer de gerado.|False|
|Cor do contorno|A cor do contorno dessa forma.|Preto|
|Estilo do tracejado da estrutura de tópicos|O estilo de traço da estrutura de tópicos desta forma (sólido, tracejado, ponto, Traçoponto, Traçopontoponto ou personalizado).|Sólido|
|Espessura da estrutura de tópicos|A espessura da estrutura de tópicos dessa forma.|0.03125|
|Cor do texto|A cor que é usada para decoradores de texto que estão associados esta forma.|Preto|
|Modificador de acesso|O nível de acesso da classe (`public` ou `internal`).|Público|
|Atributos personalizados|Usado para adicionar atributos para a classe do código fonte que é gerada a partir dessa forma.|\<Nenhum >|
|Gera dois derivado|Se `True`, uma classe base e uma classe parcial (para dar suporte a personalização por meio de substituições) será gerada. Para obter mais informações, consulte [substituir e estender as Classes geradas](../modeling/overriding-and-extending-the-generated-classes.md)|False|
|Tem um construtor personalizado|Se `True`, será fornecido um construtor personalizado no código-fonte. Para obter mais informações, consulte [substituir e estender as Classes geradas pelo](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Modificador de herança|Descreve o tipo de herança da classe de código fonte que é gerada a partir da porta (`none`, `abstract` ou `sealed`).|nenhum|
|Porta de base|A classe base dessa forma.|(nenhum)|
|Nome|O nome dessa forma.|Nome atual|
|Namespace|O namespace que é associado a esta forma.|Namespace atual|
|Tipo de dica de ferramenta|Como a dica de ferramenta é definida (fixo, variável ou nenhum). Se for resolvido, em seguida, o valor da `Fixed Tooltip Text` propriedade é usada como a dica de ferramenta; se a variável, em seguida, a dica de ferramenta é definida no código personalizado.|nenhum|
|Observações|Anotações informais que estão associadas esta forma.|\<Nenhum >|
|Altura inicial|A altura inicial dessa forma, em polegadas.|1|
|Largura inicial|A largura inicial dessa forma, em polegadas.|1.5|
|Cor de preenchimento exposto como propriedade<br /><br /> Modo de gradação de preenchimento exposto<br /><br /> Exposto a cor do contorno como propriedade<br /><br /> Exposto estilo do tracejado da estrutura de tópicos como propriedade<br /><br /> Exposto a espessura da estrutura de tópicos como propriedade<br /><br /> Expõe a cor do texto|Se `True`, o usuário pode definir a propriedade declarada de uma forma. Para definir isso, a definição de forma de mouse e clique em **adicionar expostos**.|False|
|Descrição|Usado para documentar o designer gerado.|\<Nenhum >|
|Nome de Exibição|O nome que será exibido no designer gerado para esta forma.|\<Nenhum >|
|Texto da dica de ferramenta fixa|O texto que é usado para uma dica de ferramenta fixa.|\<Nenhum >|
|Palavra-chave de ajuda|A palavra-chave que é usada para indexar a Ajuda de F1 para esta forma.|\<Nenhum >|

## <a name="see-also"></a>Consulte também

- [Glossário de ferramentas de linguagem específica de domínio](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)