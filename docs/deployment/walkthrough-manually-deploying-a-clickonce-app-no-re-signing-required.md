---
title: 'Passo a passo: Implantando manualmente um aplicativo ClickOnce que não requer nova assinatura e que preserva informações de identidade Visual | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- branding
- preserved branding information
- ClickOnce deployment, manually
- multiple ClickOnce deployment and branding
- ClickOnce deployment, SDK tools
- customer deployments
- manual ClickOnce deployments
- manifests [ClickOnce]
- ClickOnce applications, deployed by others
ms.assetid: c21822fb-d4ee-42e4-b72d-41ee9786efe5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b23d7da819a0403366260b240fa095defd0f120a
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2018
ms.locfileid: "39511403"
---
# <a name="walkthrough-manually-deploy-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information"></a>Passo a passo: Implantar manualmente um aplicativo ClickOnce que não requer nova assinatura e que preserva informações de identidade Visual
Quando você cria um [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplicativo e, em seguida, dê a ele a um cliente para publicar e implantar, o cliente teve tradicionalmente atualizar o manifesto de implantação e assine-o novamente. Enquanto ainda é o método preferencial na maioria dos casos, o .NET Framework 3.5 permite que você crie [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] implantações que podem ser implantadas por clientes sem precisar regenerar um novo manifesto de implantação. Para obter mais informações, consulte [ClickOnce implantar aplicativos para servidores de teste e produção sem assinar novamente](../deployment/deploying-clickonce-applications-for-testing-and-production-without-resigning.md).  
  
 Quando você cria um [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplicativo e, em seguida, dê a ele a um cliente para publicar e implantar, o aplicativo pode usar a identidade visual do cliente ou pode preservar a sua identidade visual. Por exemplo, se o aplicativo for um aplicativo proprietário único, você talvez queira preservar sua identidade visual. Se o aplicativo é altamente personalizado para cada cliente, você talvez queira usar a identidade visual do cliente. O .NET Framework 3.5 permite que você preserve sua identidade visual, informações do publicador e assinatura de segurança quando você der um aplicativo como uma organização para implantar. Para obter mais informações, consulte [ClickOnce criar aplicativos para que outros possam implantar](../deployment/creating-clickonce-applications-for-others-to-deploy.md).  
  
> [!NOTE]
>  Neste passo a passo é cria implantações manualmente usando a ferramenta de linha de comando *Mage.exe* ou a ferramenta gráfica *MageUI.exe*. Para obter mais informações sobre implantações manuais, consulte [instruções passo a passo: implantar manualmente um aplicativo ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
## <a name="prerequisites"></a>Pré-requisitos  
 Para executar as etapas neste passo a passo, você precisa do seguinte:  
  
-   Um aplicativo de formulários do Windows que você está pronto para implantar. Este aplicativo será referenciado como *WindowsFormsApp1*.  
  
-   Visual Studio ou o SDK do Windows.  
  
### <a name="to-deploy-a-clickonce-application-with-multiple-deployment-and-branding-support-using-mageexe"></a>Para implantar um aplicativo ClickOnce com vários implantação e suporte de identidade visual usando Mage.exe  
  
1.  Abra um prompt de comando do Visual Studio ou um [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] prompt de comando e altere o diretório no qual você armazenará seus [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] arquivos.  
  
2.  Crie um diretório chamado depois da versão atual da sua implantação. Se essa for a primeira vez que você está implantando o aplicativo, você deverá escolher provavelmente **1.0.0.0**.  
  
    > [!NOTE]
    >  A versão da sua implantação pode ser diferente do que a versão dos arquivos do aplicativo.  
  
3.  Criar um subdiretório chamado **bin** e copie todos os arquivos do aplicativo aqui, incluindo arquivos executáveis, assemblies, recursos e arquivos de dados.  
  
4.  Gere o manifesto do aplicativo com uma chamada para Mage.exe.  
  
    ```cmd  
    mage -New Application -ToFile 1.0.0.0\WindowsFormsApp1.exe.manifest -Name "Windows Forms App 1" -Version 1.0.0.0 -FromDirectory 1.0.0.0\bin -UseManifestForTrust true -Publisher "A. Datum Corporation"  
    ```  
  
5.  Assinar o manifesto de aplicativo com o certificado digital.  
  
    ```cmd  
    mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx  
    ```  
  
6.  Gere o manifesto de implantação com uma chamada para *Mage.exe*. Por padrão, *Mage.exe* marcará sua [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] implantação como um aplicativo instalado, para que ele pode ser executado tanto online e offline. Para disponibilizar o aplicativo somente quando o usuário está online, use o `-i` argumento com um valor de `f`. Uma vez que esse aplicativo aproveitará as vantagens do recurso de implantação de várias, exclua o `-providerUrl` argumento para *Mage.exe*. (Nas versões do .NET Framework anteriores à versão 3.5, exceto `-providerUrl` para um aplicativo offline resultará em erro.)  
  
    ```cmd  
    mage -New Deployment -ToFile WindowsFormsApp1.application -Name "Windows Forms App 1" -Version 1.0.0.0 -AppManifest 1.0.0.0\WindowsFormsApp1.manifest   
    ```  
  
7.  Não assinar o manifesto de implantação.  
  
8.  Forneça todos os arquivos para o cliente, que vai implantar o aplicativo em sua rede.  
  
9. Neste ponto, o cliente deve assinar o manifesto de implantação com seu próprio certificado gerado automaticamente. Por exemplo, se o cliente trabalha para uma empresa chamada Adventure Works, ele pode gerar um certificado autoassinado usando o *MakeCert.exe* ferramenta. Em seguida, use o *Pvk2pfx.exe* ferramenta para combinar os arquivos criados pelo *MakeCert.exe* em um arquivo PFX que pode ser passado para *Mage.exe*.  
  
    ```cmd  
    makecert -r -pe -n "CN=Adventure Works" -sv MyCert.pvk MyCert.cer  
    pvk2pfx.exe -pvk MyCert.pvk -spc MyCert.cer -pfx MyCert.pfx  
    ```  
  
10. Em seguida, o cliente usa esse certificado para assinar o manifesto de implantação.  
  
    ```cmd  
    mage -Sign WindowsFormsApp1.application -CertFile MyCert.pfx  
    ```  
  
11. O cliente implanta o aplicativo para seus usuários.  
  
### <a name="to-deploy-a-clickonce-application-with-multiple-deployment-and-branding-support-using-mageuiexe"></a>Para implantar um aplicativo ClickOnce com vários implantação e suporte de identidade visual usando MageUI.exe  
  
1.  Abra um prompt de comando do Visual Studio ou um [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] prompt de comando e navegue até o diretório no qual você armazenará seus [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] arquivos.  
  
2.  Criar um subdiretório chamado **bin** e copie todos os arquivos do aplicativo aqui, incluindo arquivos executáveis, assemblies, recursos e arquivos de dados.  
  
3.  Crie um subdiretório chamado depois da versão atual da sua implantação. Se essa for a primeira vez que você está implantando o aplicativo, você deverá escolher provavelmente **1.0.0.0**.  
  
    > [!NOTE]
    >  A versão da sua implantação pode ser diferente do que a versão dos arquivos do aplicativo.  
  
4.  Mover o \\ **bin** diretório para o diretório que você criou na etapa 2.  
  
5.  Inicie a ferramenta gráfica *MageUI.exe*.  
  
    ```cmd  
    MageUI.exe  
    ```  
  
6.  Criar um novo manifesto de aplicativo, selecionando **arquivo**, **New**, **manifesto do aplicativo** no menu.  
  
7.  No padrão **nome** , insira o número de versão e o nome dessa implantação. Além disso, forneça um valor para **publicador**, que será usado como o nome da pasta para o link de atalho do aplicativo no menu Iniciar quando ele é implantado.  
  
8.  Selecione o **opções de aplicativo** guia e clique em **uso manifesto do aplicativo para obter informações de confiança**. Isso permitirá que outros fornecedores de identidade visual para este [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplicativo.  
  
9. Selecione o **arquivos** guia e clique no **procurar** lado de **diretório de aplicativo** caixa de texto.  
  
10. Selecione o diretório que contém os arquivos de aplicativo que você criou na etapa 2 e, em seguida, clique em **Okey** na caixa de diálogo de seleção de pasta.  
  
11. Clique o **popular** botão para adicionar todos os arquivos de aplicativo à lista de arquivos. Se seu aplicativo contiver mais de um arquivo executável, marcar o arquivo executável principal para essa implantação como o aplicativo de inicialização, selecionando **ponto de entrada** da **tipo de arquivo** lista suspensa. (Se seu aplicativo contém um arquivo executável, apenas *MageUI.exe* marcará para você.)  
  
12. Selecione o **permissões necessárias** guia e selecione o nível de confiança, você precisa declarar seu aplicativo. O padrão é **confiança total**, que será apropriado para a maioria dos aplicativos.  
  
13. Selecione **arquivo**, **salvar** no menu e salve o manifesto do aplicativo. Você será solicitado para assinar o manifesto do aplicativo quando você salvá-lo.  
  
14. Se você tiver um certificado armazenado como um arquivo em seu sistema de arquivos, use o **sinal como arquivo de certificado** opção e, em seguida, selecione o certificado do sistema de arquivos usando o botão de reticências (**...** ) botão.  
  
     -ou-  
  
     Se seu certificado é mantido em um repositório de certificados que pode ser acessado do computador, selecione o **entrar com a opção de certificado armazenadas**e selecione o certificado na lista fornecida.  
  
15. Selecione **arquivo**, **New**, **manifesto de implantação** no menu para criar o manifesto de implantação e, em seguida, no **nome** guia, forneça um nome e número de versão (**1.0.0.0** neste exemplo).  
  
16. Alterne para o **atualizar** guia e, em seguida, especifique a frequência com que você deseja que este aplicativo para atualizar. Se seu aplicativo usa o [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] API de implantação para verificar se há atualizações em si, desmarque a caixa de seleção rotulada **esse aplicativo deve verificar por atualizações**.  
  
17. Alterne para o **referência de aplicativo** guia. Você pode preencher previamente os todos os valores nesta guia clicando o **selecionar manifesto** botão e selecionando o manifesto do aplicativo que você criou nas etapas anteriores.  
  
18. Escolher **salvar** e salve o manifesto de implantação para o disco. Você será solicitado para assinar o manifesto do aplicativo quando você salvá-lo. Clique em **Cancelar** para salvar o manifesto sem assiná-lo.  
  
19. Forneça todos os arquivos de aplicativo para o cliente.  
  
20. Neste ponto, o cliente deve assinar o manifesto de implantação com seu próprio certificado gerado automaticamente. Por exemplo, se o cliente trabalha para uma empresa chamada Adventure Works, ele pode gerar um certificado autoassinado usando o *MakeCert.exe* ferramenta. Em seguida, use o *Pvk2pfx.exe* ferramenta para combinar os arquivos criados pelo *MakeCert.exe* em um arquivo PFX que pode ser passado para *MageUI.exe*.  
  
    ```cmd  
    makecert -r -pe -n "CN=Adventure Works" -sv MyCert.pvk MyCert.cer  
    pvk2pfx.exe -pvk MyCert.pvk -spc MyCert.cer -pfx MyCert.pfx  
    ```  
  
21. Com o certificado gerado, o cliente agora assina o manifesto de implantação, abrindo o manifesto de implantação no *MageUI.exe*e, em seguida, salvá-lo. Quando for exibida a caixa de diálogo de assinatura, o cliente seleciona **sinal como arquivo de certificado** opção e escolhe o arquivo PFX que ele foi salvo em disco.  
  
22. O cliente implanta o aplicativo para seus usuários.  
  
## <a name="see-also"></a>Consulte também  
 [Mage.exe (Manifest Generation and Editing Tool)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (Manifest Generation and Editing Tool, Cliente Gráfico)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [MakeCert](/windows/desktop/SecCrypto/makecert)