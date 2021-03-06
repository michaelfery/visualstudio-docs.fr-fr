---
title: Créer une application de plateforme Windows universelle (UWP) avec Visual Studio et C#
description: Créer une application UWP dans Visual Studio avec XAML et C#
titleSuffix: ''
ms.custom: seodec18, get-started
ms.date: 03/23/2019
ms.technology: vs-ide-general
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 3ea8cc58e5afa6f98bbe07e2b75323449e637f25
ms.sourcegitcommit: 8d453b345c72339c37b489a140dad00b244e6ba4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2019
ms.locfileid: "58475940"
---
# <a name="tutorial-create-your-first-universal-windows-platform-application-in-visual-studio-with-xaml-and-c35"></a>Tutoriel : Créer votre première application de plateforme Windows universelle dans Visual Studio avec XAML et C&#35;

Dans cette présentation de l’environnement de développement intégré (IDE) Visual Studio, vous allez créer une application « Hello World » qui s’exécute sur n’importe quel appareil Windows 10. Pour ce faire, vous allez utiliser un modèle de projet de plateforme Windows universelle (UWP), le langage XAML (Extensible Application Markup Language) et le langage de programmation C#.

::: moniker range="vs-2017"
Si vous n’avez pas encore installé Visual Studio, accédez à la page [Téléchargements Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) pour l’installer gratuitement.
::: moniker-end
::: moniker range="vs-2019"
Si vous n’avez pas encore installé Visual Studio, accédez à la page [Téléchargements Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+rc) pour l’installer gratuitement.
::: moniker-end

## <a name="create-a-project"></a>Créer un projet

Créez tout d’abord un projet de plateforme Windows universelle. Le type de projet inclut tous les fichiers de modèle dont vous avez besoin au départ.

::: moniker range="vs-2017"
1. Ouvrez Visual Studio.

1. Dans la barre de menus supérieure, choisissez **Fichier** > **Nouveau** > **Projet**.

1. Dans le volet gauche de la boîte de dialogue **Nouveau projet**, développez **Visual C#**, puis choisissez **Windows universel**. Dans le volet central, choisissez **Application vide (Windows universel)**. Ensuite, nommez le projet *HelloWorld* et choisissez **OK**.

   ![Modèle de projet Windows universel dans la boîte de dialogue Nouveau projet dans l’IDE Visual Studio](media/new-project-csharp-uwp-helloworld.png)

   > [!NOTE]
   > Si vous ne voyez pas le modèle de projet **Application vide (Windows universel)**, cliquez sur le lien **Ouvrir le programme d’installation de Visual Studio** dans le volet gauche de la boîte de dialogue **Nouveau projet**.<br><br>![Cliquer sur le lien Ouvrir le programme d’installation de Visual Studio dans la boîte de dialogue Nouveau projet](../../ide/media/vb-open-visual-studio-installer-hello-world.png)<br><br>Visual Studio Installer est lancé. Choisissez la charge de travail **Développement pour la plateforme Windows universelle**, puis **Modifier**.<br><br>![Charge de travail Développement pour la plateforme Windows universelle dans le programme d’installation de Visual Studio](media/uwp-dev-workload.png)

1. Acceptez les paramètres par défaut pour **Version cible** et **Version minimale** dans la boîte de dialogue **Nouveau projet de plateforme Windows universelle**.

   ![Accepter les paramètres par défaut pour Version cible et Version minimale dans la boîte de dialogue Nouveau projet de plateforme Windows universelle](media/new-uwp-project-target-minver-dialog.png)
::: moniker-end

::: moniker range=">=vs-2019"
1. Ouvrez Visual Studio puis, dans la fenêtre de démarrage, choisissez **Créer un projet**.

1. Sur l’écran **Créer un projet**, entrez *Windows universel* dans la zone de recherche, choisissez le modèle C# pour **Application vide (Windows universel)**, puis choisissez **Suivant**.

   ![Capture d’écran de l’écran Créer un projet](media/vs-2019/uwp-create-new-project.png)

   > [!NOTE]
   > Si vous ne voyez pas le modèle de projet **Application vide (Windows universel)**, cliquez sur le lient **Installer plus d’outils et de fonctionnalités**.<br><br>![Cliquer sur le lien Installer plus d’outils et de fonctionnalités](media/vs-2019/uwp-not-finding.png)<br><br>Visual Studio Installer est lancé. Choisissez la charge de travail **Développement pour la plateforme Windows universelle**, puis **Modifier**.<br><br>![Charge de travail Développement pour la plateforme Windows universelle dans le programme d’installation de Visual Studio](media/uwp-dev-workload.png)

1. Acceptez les paramètres par défaut pour **Version cible** et **Version minimale** dans la boîte de dialogue **Nouveau projet de plateforme Windows universelle**.

   ![Accepter les paramètres par défaut pour Version cible et Version minimale dans la boîte de dialogue Nouveau projet de plateforme Windows universelle](media/vs-2019/new-uwp-project-target-minver-dialog.png)
::: moniker-end

   > [!NOTE]
   > S’il s’agit de la première fois que vous avez utilisé Visual Studio pour créer une application UWP, une boîte de dialogue **Paramètres** peut s’afficher. Choisissez **Mode développeur**, puis **Oui**.<br><br>
   ![Activer le mode développeur dans la boîte de dialogue Paramètres du projet UWP](media/enable-developer-mode.png)<br><br>Visual Studio installe un autre package en mode développeur pour vous. Une fois l’installation du package terminée, fermez la boîte de dialogue **Paramètres**.

## <a name="create-the-application"></a>Créer l’application

Il est temps de commencer à développer. Vous allez ajouter un contrôle bouton, ajouter une action au bouton, puis démarrer l’application « Hello World » pour voir à quoi elle ressemble.

### <a name="add-a-button-to-the-design-canvas"></a>Ajouter un bouton à la zone de conception

1. Dans **l’Explorateur de solutions**, double-cliquez sur *MainPage.xaml* pour ouvrir un mode fractionné.

   ::: moniker range="vs-2017"
   ![Ouvrir MainPage.xaml à partir de l’Explorateur de solutions ](media/uwp-solution-explorer-MainPage-xaml.png)
   ::: moniker-end
   ::: moniker range=">=vs-2019"
   ![Ouvrir MainPage.xaml à partir de l’Explorateur de solutions](media/vs-2019/uwp-solution-explorer-mainpage-xaml.png)
   ::: moniker-end

   Il existe deux volets : le **concepteur XAML**, qui comprend une zone de conception et l’**éditeur XAML** où vous pouvez ajouter et modifier le code.

   ![Volet du concepteur XAML dans l’éditeur XAML](media/uwp-xaml-editor.png)

1. Choisissez **Boîte à outils** pour ouvrir la fenêtre volante Boîte à outils.

   ![Cliquer sur Boîte à outils pour ouvrir la fenêtre volante Boîte à outils](media/uwp-toolbox.png)

   (Si vous ne voyez pas l’option **Boîte à outils**, ouvrez-la à partir de la barre de menus. Pour ce faire, choisissez **Affichage** > **Barre d’outils**. Vous pouvez aussi appuyer sur **Ctrl**+**Alt**+**X**.)

1. Cliquez sur l’icône **Épingler** pour ancrer la fenêtre Boîte à outils.

   ![Cliquer sur l’icône Épingler pour ancrer la fenêtre Boîte à outils](media/uwp-toolbox-autohide.png)

1. Cliquez sur le contrôle **Button**, puis faites-le glisser dans la zone de conception.

   ![Cliquer sur le contrôle Button, puis le faire glisser dans la zone de conception](media/uwp-toolbox-add-button-control.png)

   Si vous examinez le code dans **l’éditeur XAML**, vous verrez que le contrôle Button y a aussi été ajouté :

   ![Cliquer sur le contrôle Button, puis le faire glisser dans la zone de conception](media/uwp-xaml-control-code-window.png)

### <a name="add-a-label-to-the-button"></a>Ajouter une étiquette au bouton

1. Dans **l’éditeur XAML**, remplacez la valeur de Button Content « Button » par « Hello World! ».

   ![Remplacer la valeur de Button Content par Hello World](media/uwp-change-button-text-in-xaml-code-window.png)

1. Notez que le bouton dans le **Concepteur XAML** change également.

   ![Le bouton devient Hello World dans la zone de conception](media/uwp-button-text-change-in-design-canvas.png)

### <a name="add-an-event-handler"></a>Ajouter un gestionnaire d’événements

Un « gestionnaire d’événements » semble compliqué, mais il s’agit simplement d’un autre nom pour le code qui est appelé quand un événement se produit. Dans ce cas, il ajoute une action au bouton « Hello World! » disproportionnée.

1. Double-cliquez sur le contrôle bouton dans la zone de conception.

1. Modifiez le code de gestionnaire d’événements dans *MainPage.xaml.cs*, la page code-behind.

   C’est ici que les choses deviennent intéressantes. Voici à quoi ressemble le gestionnaire d’événements par défaut :

   ![Gestionnaire d’événements Button_Click par défaut ](media/uwp-button-click-code.png)

   Modifions-le afin qu’il ressemble à ceci :

   ![Nouveau gestionnaire d’événements Button_Click asynchrone ](media/uwp-add-hello-world-async-code.png)

   Voici le code à copier et coller :

   ```C#
   private async void Button_Click(object sender, RoutedEventArgs e)
         {
             MediaElement mediaElement = new MediaElement();
             var synth = new Windows.Media.SpeechSynthesis.SpeechSynthesizer();
             Windows.Media.SpeechSynthesis.SpeechSynthesisStream stream = await synth.SynthesizeTextToStreamAsync("Hello, World!");
             mediaElement.SetSource(stream, stream.ContentType);
             mediaElement.Play();
         }
   ```

#### <a name="what-did-we-just-do"></a>Que venons-nous de faire ?

Le code utilise des API Windows pour créer un objet de synthèse vocale, puis lui donne du texte à dire. (Pour plus d’informations sur l’utilisation de `SpeechSynthesis`, consultez <xref:System.Speech.Synthesis>.)

## <a name="run-the-application"></a>Exécuter l'application

Il est temps de générer, déployer et lancer l’application UWP « Hello World » pour voir à quoi elle ressemble. Voici comment procéder.

1. Utilisez le bouton Lecture (il contient le texte **Ordinateur local**) pour démarrer l’application sur l’ordinateur local.

   ![Cliquer sur Ordinateur local pour démarrer et déboguer votre application UWP](media/uwp-start-or-debug.png)

   (Vous pouvez également choisir **Déboguer** > **Démarrer le débogage** dans la barre de menus ou appuyer sur F5 pour démarrer votre application.)

1. Examinez votre application, qui apparaît vite après la disparition d’un écran de démarrage. L’application doit ressembler à ceci :

   ![Application UWP « Hello World »](media/uwp-hello-world-app.png)

1. Cliquez sur le bouton **Hello World**.

   Votre appareil Windows 10 dira littéralement « Hello, World ! »

1. Pour fermer l’application, cliquez sur le bouton **Arrêter le débogage** dans la barre d’outils. (Vous pouvez également choisir **Déboguer** > **Arrêter le débogage** dans la barre de menus ou appuyer sur Maj+F5.)

## <a name="next-steps"></a>Étapes suivantes

Félicitations ! Vous avez terminé ce didacticiel. Nous espérons que vous avez appris quelques principes fondamentaux sur UWP et l’IDE Visual Studio. Pour en savoir plus, passez au tutoriel suivant :

> [!div class="nextstepaction"]
> [Créer une interface utilisateur](/windows/uwp/design/basics/xaml-basics-ui)