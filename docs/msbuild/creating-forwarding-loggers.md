---
title: Criando agentes de log de encaminhamento | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, forwarding loggers
- MSBuild, logging
ms.assetid: 3aebf9c8-b62c-4cb2-b2d6-8cdfcd369a24
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d18e84e6c3637fb5d40dfcef14e8dd6a06dc47ce
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39179197"
---
# <a name="create-forwarding-loggers"></a>Criar agentes de encaminhamento
Agentes de encaminhamento melhoram a eficiência de log, permitindo que você escolha os eventos que deseja monitorar ao compilar projetos em um sistema com vários processadores. Ao habilitar agentes de encaminhamento, você pode impedir que eventos indesejados sobrecarreguem o agente central, diminuindo o tempo de build e desorganizando o log.  
  
 Para criar um agente de encaminhamento, você pode implementar a interface <xref:Microsoft.Build.Framework.IForwardingLogger> e, em seguida, implementar seus métodos manualmente ou usar a classe <xref:Microsoft.Build.BuildEngine.ConfigurableForwardingLogger> e seus métodos pré-configurados. (O último será suficiente para a maioria dos aplicativos.)  
  
## <a name="register-events-and-respond-to-them"></a>Registrar eventos e responder a eles  
 Um agente de encaminhamento reúne informações sobre eventos de build à medida que são relatados pelo mecanismo de build secundária, que é um processo de trabalho criado pelo processo de build principal durante um build em um sistema com vários processadores. Em seguida, o agente de encaminhamento seleciona eventos para encaminhar para o agente central, com base nas instruções que você atribuiu a ele.  
  
 Você deve registrar os agentes de encaminhamento para manipular os eventos que deseja monitorar. Para registrar-se para eventos, os agentes devem substituir o método <xref:Microsoft.Build.Utilities.Logger.Initialize%2A>. Este método agora inclui um parâmetro opcional, `nodecount`, que pode ser definido como o número de processadores no sistema. (Por padrão, o valor é 1.)  
  
 Alguns exemplos de eventos que você pode monitorar são <xref:Microsoft.Build.Framework.IEventSource.TargetStarted>, <xref:Microsoft.Build.Framework.IEventSource.ProjectStarted> e <xref:Microsoft.Build.Framework.IEventSource.ProjectFinished>.  
  
 Em um ambiente com vários processadores, mensagens de evento, provavelmente, serão recebidas fora de ordem. Portanto, você deve avaliar os eventos usando o manipulador de eventos no agente de encaminhamento e programá-lo para determinar quais eventos passar para o redirecionador para serem encaminhados para o agente central. Para fazer isso, você pode usar a classe <xref:Microsoft.Build.Framework.BuildEventContext>, que está anexada a cada mensagem, para ajudar a identificar eventos que deseja encaminhar e, em seguida, transmitir os nomes de eventos para a classe <xref:Microsoft.Build.BuildEngine.ConfigurableForwardingLogger> (ou uma subclasse dela). Quando você usa esse método, nenhuma outra codificação específica é necessária para encaminhar eventos.  
  
## <a name="specify-a-forwarding-logger"></a>Especificar um agente de encaminhamento  
 Depois que o agente de encaminhamento tiver sido compilado em um assembly, você deve informar o [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] para usá-lo durante builds. Para fazer isso, use as opções `/FileLogger`, `/FileLoggerParameters` e `/DistributedFileLogger` junto com *MSBuild.exe*. A opção `/FileLogger` informa ao *MSBuild.exe* de que o agente está diretamente anexado. A opção `/DistributedFileLogger` significa que há um arquivo de log por nó. Para definir parâmetros no agente de encaminhamento, use a opção `/FileLoggerParameters`. Para obter mais informações sobre essas e outras opções do *MSBuild.exe*, confira [Referência de linha de comando](../msbuild/msbuild-command-line-reference.md).  
  
## <a name="multi-processor-aware-loggers"></a>Agentes com reconhecimento de multiprocessador  
 Quando você cria um projeto em um sistema com vários processadores, as mensagens de build de cada processador não são intercaladas automaticamente em uma sequência unificada. Em vez disso, você deve estabelecer uma prioridade de agrupamento de mensagens usando a classe <xref:Microsoft.Build.Framework.BuildEventContext> que está anexada a cada mensagem. Para obter mais informações sobre o build de multiprocessador, confira [Registrando em log em um ambiente multiprocessador](../msbuild/logging-in-a-multi-processor-environment.md).  
  
## <a name="see-also"></a>Consulte também  
 [Obter logs de build](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [Agentes de build](../msbuild/build-loggers.md)   
 [Registrando em log em um ambiente multiprocessador](../msbuild/logging-in-a-multi-processor-environment.md)