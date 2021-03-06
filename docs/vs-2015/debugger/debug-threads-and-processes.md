---
title: Depurar Threads e processos | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- multiprocess debugging
- threading [Visual Studio], debugging
- processes, debugging
- debugging threads
- debugging [Visual Studio], threads
ms.assetid: 9f0c8505-b6b2-452b-adfd-076db14d8115
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6bda70d9f99b4b97623d5d9f03ca440721f9a728
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47460596"
---
# <a name="debug-threads-and-processes"></a>Depurar threads e processos
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [depurar Threads e processos](https://docs.microsoft.com/visualstudio/debugger/debug-threads-and-processes).  
  
Threads * e *processos* são conceitos relacionados em ciência da computação. Ambos representam sequências de instruções que devem executar em uma ordem específica. Instruções em threads ou processos separados, entretanto, podem ser executados em paralelo.  
  
 Os processos existem no sistema operacional e correspondem ao que os usuários veem como programas ou aplicativos. Um thread, por outro lado, existe dentro de um processo. Por esse motivo, threads são às vezes chamados de *processos leves*. Cada processo consiste em um ou mais threads.  
  
 A existência de vários processos permite que um computador execute mais de uma tarefa de cada vez. A existência de vários threads permite que um processo separe o trabalho a ser executado paralelamente. Em um computador com multiprocessadores, os processos ou threads podem ser executados em processadores diferentes. Isso permite o verdadeiro processamento paralelo.  
  
 O processamento paralelo perfeito não é sempre possível. Às vezes os threads devem ser sincronizados. Um thread pode ter que aguardar um resultado de outro thread, ou um thread pode precisar de acesso exclusivo a um recurso que outro thread está usando. Problemas de sincronização são uma causa comum de erro em aplicativos com multithreads. Em alguns casos, os threads podem interromper espera de um recurso que nunca fica disponível. Isso resulta em uma condição chamada *deadlock*.  
  
 O depurador do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] fornece ferramentas avançadas e mas fáceis de usar para depurar threads e processos.  
  
## <a name="tools-for-debugging-threads-and-processes-in-visual-studio"></a>Ferramentas para depurar threads e processos no Visual Studio  
 As principais ferramentas para trabalhar com processos no [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] são os **anexar ao processo** caixa de diálogo, o **processos** janela e o **local de depuração** barra de ferramentas. As ferramentas principais para depurar threads são a **Threads** janela, marcadores de thread em janelas de origem e o **local de depuração** barra de ferramentas.  
  
 As ferramentas principais para depurar aplicativos multissegmentados são as **pilhas paralelas** e **tarefas paralelas**, **inspeção paralela**, e **ThreadsdaGPU** windows.  
  
 A tabela a seguir mostra as informações disponíveis e as ações que você pode executar em cada um desses locais:  
  
|Interface do Usuário|Informação disponível|Ações que você pode executar|  
|--------------------|---------------------------|-----------------------------|  
|**Anexar ao processo** caixa de diálogo|Processos disponíveis você pode anexar:<br /><br /> -Nome do processo (.exe)<br />-Número de ID processo<br />-Título barra de menus<br />-Tipo (v4.0 gerenciado; V2.0 gerenciado, v1.1, v1.0; x86; x64; IA64)<br />-O nome de usuário (nome de conta)<br />-Número sessão|Selecione um processo anexar.<br /><br /> Selecione um computador remoto<br /><br /> Altere o tipo de transporte para se conectar a computadores remotos|  
|**Processos** janela|Processos anexados:<br /><br /> -Nome do processo<br />-Número de ID processo<br />-Path para processar .exe<br />-Título barra de menus<br />-Estado (interrupção. em execução)<br />-Depuração (nativo, gerenciado e assim por diante).<br />-(Padrão, nativo sem autenticação) do tipo de transporte<br />-Qualificador de transporte (computador remoto)|Ferramentas:<br /><br /> -Anexar<br />-Desanexar<br />-Encerrar<br /><br /> O menu de atalho:<br /><br /> -Anexar<br />-Desanexar<br />-Desanexe quando a depuração for interrompida<br />-Encerrar|  
|**Threads** janela|Threads durante o processo atual:<br /><br /> -ID do thread<br />-ID gerenciada<br />-Categoria (thread principal, thread de interface, manipulador de chamada de procedimento remoto ou thread de trabalho)<br />-Nome do thread<br />-Local onde o thread é criado<br />-Prioridade<br />-Máscara de afinidade<br />-Contagem suspensa<br />-Nome do processo<br />-Indicador de sinalização<br />-Indicador suspenso|Ferramentas:<br /><br /> -Pesquisa<br />-Pesquisar pilha de chamadas<br />-Sinalizar apenas meu código<br />-O sinalizador seleção de módulo personalizada<br />-Group by<br />-Columns<br />-Expandir/recolher pilhas de chamadas<br />-Expandir/recolher grupos<br />-Congelar/descongelar Threads<br /><br /> O menu de atalho:<br /><br /> -Mostrar threads na origem<br />-Alternar para um thread<br />-Congelar um thread em execução<br />-Descongelar um thread congelado<br />-Sinalizar um thread para estudos adicionais<br />-Remover sinalização de um thread<br />-Renomeie um thread<br />-Mostrar e ocultar threads<br /><br /> Outras ações:<br /><br /> -Exibir a pilha de chamadas para um thread em um DataTip|  
|Janela de origem|Indexadores de threads na medianiz esquerda indicam um ou vários segmentos (desativado por padrão, ativado usando o menu de atalho **Threads** janela)|O menu de atalho:<br /><br /> -Alternar para um thread<br />-Sinalizar um thread para estudos adicionais<br />-Remover sinalização de um thread|  
|**Local de depuração** barra de ferramentas|-Processo atual<br />-Suspender o aplicativo<br />-Retomar o aplicativo<br />-Suspenda e feche o aplicativo<br />-Thread atual<br />-Ativar/desativar estado atual do sinalizador de thread<br />-Mostrar somente threads sinalizados<br />-Mostrar somente o processo atual<br />-Quadro de pilhas atual|-Alternar para outro processo<br />-Suspender, continuar ou desligar o aplicativo<br />-Mudar para outro thread no processo atual<br />-Alternar para outro quadro de pilha no thread atual<br />-Sinalizar ou Remover sinalização de threads atuais<br />-Mostrar somente threads sinalizados<br />-Mostrar somente o processo atual|  
|**Pilhas paralelas** janela|-Pilhas de chamadas para vários threads em uma janela.<br />-Quadro de pilha Active Directory para cada thread.<br />-Os chamadores e receptores de qualquer método.|-Remover threads especificados<br />-Alternar para modo de exibição de tarefas paralelas<br />-Sinalizar ou Remover sinalização de um thread<br />-Zoom|  
|**Tarefas paralelas** janela|-Exibir informações sobre <xref:System.Threading.Tasks.Task> objetos, incluindo a ID da tarefa, status da tarefa (agendada, executando, em espera, em deadlock), e qual thread é atribuído à tarefa.<br />-Local atual na pilha de chamadas.<br />-Delegate é passado para a tarefa no momento da criação|-Alternar para a tarefa atual<br />-Sinalizar ou Remover sinalização de uma tarefa<br />-Congelar ou descongelar uma tarefa|  
|**Inspeção paralela** janela|-A coluna do sinalizador, na qual você pode marcar um thread que você deseja prestar atenção especial ao.<br />-A coluna do quadro, em que uma seta indica o quadro selecionado.<br />-Uma coluna configurável que pode exibir o computador, processo, lado a lado, tarefas e thread.|-Sinalizar ou Remover sinalização de um thread<br />-Exibir somente threads sinalizados<br />-Quadros chave<br />-Classificar uma coluna<br />-Threads grupo<br />-Congelar ou descongelar threads<br />-Exportar os dados na janela Inspeção paralela|  
|**Threads da GPU** janela|-A coluna do sinalizador, na qual você pode marcar um thread que você deseja prestar atenção especial ao.<br />-A coluna thread ativo, em que uma seta amarela indica um thread ativo. Uma seta indica um thread onde a execução interrompe no depurador.<br />-A **contagem de threads** coluna, que exibe o número de threads no mesmo local.<br />-A **linha** coluna, que exibe a linha de código em que cada grupo de threads está localizado.<br />-A **endereço** coluna, que exibe o endereço da instrução onde cada grupo de threads está localizado.<br />-A **local** coluna, que é o local no código do endereço.<br />-A **Status** coluna, que mostra se o thread está ativo ou bloqueado.<br />-A **bloco** coluna, que mostra o índice do bloco para os segmentos na linha.|-Alterar para um thread ativo diferente<br />-Exibe um bloco específico e um thread<br />-Exibir ou ocultar uma coluna<br />-Classificação por coluna<br />-Threads grupo<br />-Congelar ou descongelar threads<br />-Sinalizar ou Remover sinalização de um thread<br />-Exibir somente threads sinalizados|  
  
## <a name="see-also"></a>Consulte também  
 [Anexar a processos em execução](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Depurar aplicativos multithread](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Depurando código de GPU](../debugger/debugging-gpu-code.md)



