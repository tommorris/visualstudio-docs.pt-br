---
title: 'CA2202: não descartar objetos várias vezes'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2202
- Do not dispose objects multiple times
- DoNotDisposeObjectsMultipleTimes
helpviewer_keywords:
- CA2202
ms.assetid: fa85349a-cf1e-42c8-a86b-eacae1f8bd96
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4e805cb76ebe4c216b456f65ea3264f8f25561cc
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45548594"
---
# <a name="ca2202-do-not-dispose-objects-multiple-times"></a>CA2202: não descartar objetos várias vezes

|||
|-|-|
|NomeDoTipo|DoNotDisposeObjectsMultipleTimes|
|CheckId|CA2202|
|Categoria|Microsoft.Usage|
|Alteração Significativa|Não separável|

## <a name="cause"></a>Causa

Uma implementação do método contém caminhos de código que poderiam causar várias chamadas para <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> ou um equivalente de Dispose, como um método Close () em alguns tipos, no mesmo objeto.

## <a name="rule-description"></a>Descrição da regra

Um implementado corretamente <xref:System.IDisposable.Dispose%2A> método pode ser chamado várias vezes sem lançar uma exceção. No entanto, isso não é garantido e para evitar a geração de um <xref:System.ObjectDisposedException?displayProperty=fullName> você não deve chamar <xref:System.IDisposable.Dispose%2A> mais de uma vez em um objeto.

## <a name="related-rules"></a>Regras relacionadas

- [CA2000: descartar objetos antes de perder o escopo](../code-quality/ca2000-dispose-objects-before-losing-scope.md)

## <a name="how-to-fix-violations"></a>Como corrigir violações

Para corrigir uma violação dessa regra, altere a implementação assim que independentemente do caminho do código, <xref:System.IDisposable.Dispose%2A> é chamado apenas uma vez para o objeto.

## <a name="when-to-suppress-warnings"></a>Quando suprimir avisos

Não suprima um aviso nessa regra. Mesmo se <xref:System.IDisposable.Dispose%2A> para o objeto é conhecido por ser com segurança que pode ser chamado várias vezes, a implementação pode ser alterado no futuro.

## <a name="example"></a>Exemplo

Aninhado `using` instruções (`Using` no Visual Basic) pode causar violações do aviso CA2202. Se o recurso de IDisposable de aninhada interna `using` declaração contém o recurso de externo `using` instrução, o `Dispose` método do recurso aninhado libera o recurso contido. Quando essa situação ocorre, o `Dispose` método de externo `using` declaração tenta descartar seu recurso para uma segunda vez.

No exemplo a seguir, uma <xref:System.IO.Stream> objeto que é criado em um externa usando a instrução é liberado no final do interno usando a instrução no método Dispose do <xref:System.IO.StreamWriter> objeto que contém o `stream` objeto. No final do externo `using` instrução, o `stream` o objeto é liberado uma segunda vez. A segunda versão é uma violação da CA2202.

```csharp
using (Stream stream = new FileStream("file.txt", FileMode.OpenOrCreate))
{
    using (StreamWriter writer = new StreamWriter(stream))
    {
        // Use the writer object...
    }
}
```

## <a name="example"></a>Exemplo

Para resolver esse problema, use uma `try` / `finally` bloco, em vez de externa `using` instrução. No `finally` bloquear, certifique-se de que o `stream` recurso não for nulo.

```csharp
Stream stream = null;
try
{
    stream = new FileStream("file.txt", FileMode.OpenOrCreate);
    using (StreamWriter writer = new StreamWriter(stream))
    {
        stream = null;
        // Use the writer object...
    }
}
finally
{
    if(stream != null)
        stream.Dispose();
}
```

## <a name="see-also"></a>Consulte também

- <xref:System.IDisposable?displayProperty=fullName>
- [Padrão de descarte](/dotnet/standard/design-guidelines/dispose-pattern)