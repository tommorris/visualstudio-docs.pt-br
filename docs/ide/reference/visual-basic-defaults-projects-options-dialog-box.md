---
title: Caixa de diálogo Padrões do Visual Basic, Projetos, Opções
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Projects.VBDefaults
helpviewer_keywords:
- Option Explicit statement, setting in the IDE
- Option Compare statement, setting in the IDE
- Option Strict statement, setting in the IDE
ms.assetid: 2465cd9d-18b6-4c4a-b1ea-86dbab23fc79
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d211b69a4fb8ce988298a39310f103574b563721
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31945864"
---
# <a name="visual-basic-defaults-projects-options-dialog-box"></a>Caixa de diálogo Padrões do Visual Basic, Projetos, Opções
Especifica as configurações padrão para opções de projeto do Visual Basic. Quando um novo projeto é criado, as instruções da opção especificada serão adicionadas ao cabeçalho do projeto no Editor de Códigos. As opções se aplicam a todos os projetos do Visual Basic.

 Para acessar essa caixa de diálogo, no menu **Ferramentas**, clique em **Opções**, expanda a pasta **Projetos e Soluções** e clique em **Padrões de VB**.

 **Opção Explícita**

 Define o padrão do compilador para que declarações explícitas de variáveis sejam necessárias. Por padrão, **Opção Explicit** fica definido como **Ativado**. Para obter mais informações, consulte [/optionexplicit](/dotnet/visual-basic/reference/command-line-compiler/optionexplicit).

 **Opção Estrita**

 Define o padrão do compilador para que as conversões de estreitamento explícitas sejam obrigatórias e as associações tardias não sejam permitidas. Por padrão, **Opção Strict** fica definido como **Desativado**. Para obter mais informações, veja [/optionstrict](/dotnet/visual-basic/reference/command-line-compiler/optionstrict).

 **Opção Comparar**

 Define o padrão do compilador para comparações de cadeia de caracteres: binário (diferencia maiúsculas de minúsculas) ou texto (não diferencia maiúsculas de minúsculas). Por padrão, **Opção Compare** fica definido como **Binário**. Para obter mais informações, consulte [/optioncompare](/dotnet/visual-basic/reference/command-line-compiler/optioncompare).

 **Opção Inferir**

 Define o padrão do compilador para inferência de tipo de variável local. Por padrão, **Opção Infer** é definido como **Ativado** para projetos criados recentemente e como **Desativado** para projetos migrados criados em versões anteriores do Visual Basic. Para obter mais informações, consulte [/optioninfer](/dotnet/visual-basic/reference/command-line-compiler/optioninfer).

## <a name="see-also"></a>Consulte também

- [Soluções e projetos](../../ide/solutions-and-projects-in-visual-studio.md)