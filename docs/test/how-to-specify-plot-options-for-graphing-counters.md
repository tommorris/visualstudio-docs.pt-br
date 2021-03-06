---
title: Opções de plotagem para gráficos de contadores de testes de carga no Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, graphing counters
ms.assetid: 1969c20b-e0eb-48f6-a49f-a9090cd86008
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 5df33a8cf05e4ad73b1643e2948392e49a32356e
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2018
ms.locfileid: "39382315"
---
# <a name="how-to-specify-plot-options-for-graphing-counters"></a>Como especificar opções de gráfico para contadores de representação gráfica

A caixa de diálogo **Opções de Plotagem** permite alterar a cor e o estilo de linha de um contador plotado em um gráfico. Você também pode corrigir o intervalo em um valor específico ou definir o intervalo para ser ajustado automaticamente com base nos dados da amostra.

![Caixa de diálogo Opções de Plotagem](../test/media/ltest_plotoptions.png)

## <a name="to-specify-plotting-options-for-graphs"></a>Para especificar opções de plotagem para gráficos

1.  No **Analisador de Teste de Carga**, escolha **Grafos** na barra de ferramentas.

     Isso exibe os resultados do teste de carga na exibição de grafo.

2.  Na legenda ou no grafo, clique com o botão direito do mouse na linha ou na linha de plotagem atual do contador de desempenho cuja opção de plotagem deseja alterar e, em seguida, selecione **Opções de Gráfico**.

     A caixa de diálogo **Opções de Plotagem** é exibida.

3.  Use a lista suspensa **Cor** e selecione a cor que deseja usar para plotar o contador de desempenho.

4.  Use a lista suspensa **Estilo** e selecione o estilo que deseja usar para plotar o contador de desempenho.

5.  Realize um dos seguintes procedimentos:

     Selecione **Ajustar automaticamente o intervalo** (padrão)

     \- ou -

     Desmarque **Ajustar automaticamente o intervalo** e use a lista suspensa **Intervalo** para especificar o intervalo que deseja usar na plotagem do contador de desempenho.

6.  Escolha **OK**.

     O contador de desempenho cujas opções você alterou é exibido no gráfico com as alterações que você especificou.

## <a name="see-also"></a>Consulte também

- [Analisar resultados do teste de carga na exibição Grafos](../test/analyze-load-test-results-in-the-graphs-view.md)
- [Como criar gráficos personalizados](../test/how-to-create-custom-graphs-in-load-test-results.md)
