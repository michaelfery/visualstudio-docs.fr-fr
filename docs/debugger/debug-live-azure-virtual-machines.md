---
title: Déboguer des machines virtuelles et des groupes de machines virtuelles identiques Azure ASP.NET en production
description: Découvrez comment définir des snappoints et afficher des instantanés avec le Débogueur de capture instantanée.
ms.custom: ''
ms.date: 02/06/2019
ms.topic: conceptual
helpviewer_keywords:
- debugger
author: poppastring
ms.author: madownie
manager: andster
monikerRange: '>= vs-2019'
ms.workload:
- aspnet
- azure
ms.openlocfilehash: 0bbe7d081e15fdf81308218f2bb4b54e7623b333
ms.sourcegitcommit: 509fc3a324b7748f96a072d0023572f8a645bffc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58856954"
---
# <a name="debug-live-aspnet-apps-on-azure-virtual-machines-and-azure-virtual-machine-scale-sets-using-the-snapshot-debugger"></a>Déboguer des applications ASP.NET en production sur des machines virtuelles Azure et des groupes de machines virtuelles identiques Azure à l’aide du Débogueur de capture instantanée

Le Débogueur de capture instantanée prend une capture instantanée de vos applications en production au moment de l’exécution du code qui vous intéresse. Pour indiquer au débogueur de prendre une capture instantanée, vous définissez des points d’ancrage et des points de journalisation dans votre code. Dans le débogueur, vous pouvez voir précisément à quel endroit le code ne s’est pas exécuté correctement, sans que cela impacte le trafic de votre application en production. Snapshot Debugger peut vous aider à résoudre beaucoup plus vite les problèmes rencontrés dans les environnements de production.

Les snappoints et les logpoints sont similaires aux points d’arrêt, mais contrairement à ceux-ci, les snappoints n’arrêtent pas l’application lorsqu’ils sont atteints. En règle générale, la capture d’un instantané sur un snappoint prend entre 10 et 20 millisecondes.

Dans ce didacticiel, vous allez effectuer les actions suivantes :

> [!div class="checklist"]
> * Démarrer le Débogueur de capture instantanée
> * Définir un snappoint et afficher un instantané
> * Définir un logpoint

## <a name="prerequisites"></a>Prérequis

* Le Débogueur de capture instantanée pour les machines virtuelles Azure et les groupes de machines virtuelles identiques Azure est uniquement disponible pour Visual Studio 2019 Enterprise préversion ou version ultérieure avec la **charge de travail de développement Azure**. (Sous l’onglet **Composants individuels**, vous le trouverez sous **Débogage et test** > **Débogueur de capture instantanée**.)

    S’il n’est pas déjà installé, installez [Visual Studio 2019 Enterprise préversion](https://visualstudio.microsoft.com/vs/preview/).

* La collecte de capture instantanée est disponible pour les applications web Azure VM/VMSS suivantes :
  * Applications ASP.NET exécutées sur .NET Framework version 4.6.1 ou ultérieure.
  * Applications ASP.NET Core exécutées sur .NET Core version 2.0 ou ultérieure sur Windows.

## <a name="open-your-project-and-start-the-snapshot-debugger"></a>Ouvrir votre projet et démarrer le Débogueur de capture instantanée

1. Ouvrez le projet pour lequel vous souhaitez exécuter le débogage d’instantané.

    > [!IMPORTANT]
    > Pour le débogage d’instantané, vous devez ouvrir la *même version de code source* que celle publiée dans votre service Azure VM/VMSS.

1. Choisissez **Déboguer > Joindre le Débogueur de capture instantanée...**. Sélectionnez le service Azure VM/VMSS sur lequel votre application web est déployée et un compte de stockage Azure, puis cliquez sur **Joindre**.

      ![Lancer le Débogueur de capture instantanée à partir du menu Déboguer](../debugger/media/snapshot-debug-menu-attach.png)

      ![Sélectionner une ressource Azure](../debugger/media/snapshot-select-azure-resource-vm.png) 

    > [!IMPORTANT]
    > La première fois que vous sélectionnez **Joindre le Débogueur de capture instantanée** pour votre machine virtuelle, IIS est redémarré automatiquement.
    > La première fois que vous sélectionnez **Joindre le Débogueur de capture instantanée** pour votre VMSS, la mise à niveau manuelle de chaque instance de VMSS est requise.

    Les métadonnées pour les **Modules** ne sont pas initialement activées, accédez à l’application web et le bouton **Démarrer la collecte** devient actif. Visual Studio est maintenant en mode Débogage de capture instantanée.

   ![Mode Débogage de capture instantanée](../debugger/media/snapshot-message.png)

    > [!NOTE]
    > L’extension de site Application Insights prend également en charge le débogage de capture instantanée. Si un message d’erreur du type « extension de site obsolète » apparaît, voir [Conseils de résolution des problèmes et problèmes connus pour le débogage de capture instantanée](../debugger/debug-live-azure-apps-troubleshooting.md) pour effectuer une mise à niveau.
    > Pour VMSS, l’utilisateur doit mettre à niveau manuellement les instances dans VMSS après avoir joint le Débogueur de capture instantanée pour la première fois.

   La fenêtre **Modules** indique que tous les modules sont chargés pour Azure VM/VMSS (choisissez **Déboguer > Fenêtres > Modules** pour l’ouvrir).

   ![Consulter la fenêtre Modules](../debugger/media/snapshot-modules.png)

## <a name="set-a-snappoint"></a>Définir un snappoint

1. Dans l’éditeur de code, cliquez sur la marge gauche à côté de la ligne de code qui vous intéresse pour définir un snappoint. Vérifiez que ce code pourra s’exécuter.

   ![Définir un snappoint](../debugger/media/snapshot-set-snappoint.png)

1. Cliquez sur **Lancer la collecte** pour activer le snappoint.

   ![Activer le snappoint](../debugger/media/snapshot-start-collection.png)

    > [!TIP]
    > L’exécution pas à pas n’est pas possible à l’affichage d’une capture instantanée, mais vous pouvez placer plusieurs snappoints dans votre code pour suivre l’exécution sur différentes lignes de code. Si le code comporte plusieurs snappoints, le Débogueur de capture instantanée s’assure que les captures instantanées correspondantes proviennent de la même session d’utilisateur final, même si de nombreux utilisateurs accèdent à l’application.

## <a name="take-a-snapshot"></a>Prendre un instantané

Lorsqu’un snappoint est activé, il prend une capture instantanée chaque fois à chaque exécution de la ligne de code correspondante. Cette exécution peut être provoquée par une demande réelle sur le serveur. Pour forcer l’activation du snappoint, accédez à la vue dans le navigateur de votre site web et effectuez l’une des actions correspondant à ce snappoint.

## <a name="inspect-snapshot-data"></a>Inspecter les données de capture instantanée

1. Lorsque le snappoint est atteint, une capture instantanée apparaît dans la fenêtre Outils de diagnostic. Pour ouvrir cette fenêtre, choisissez **Déboguer > Fenêtres > Afficher les Outils de diagnostic**.

   ![Ouvrir un snappoint](../debugger/media/snapshot-diagsession-window.png)

1. Double-cliquez sur le snappoint pour ouvrir la capture instantanée dans l’éditeur de code.

   ![Inspecter les données de capture instantanée](../debugger/media/snapshot-inspect-data.png)

   Dans cette vue, vous pouvez pointer sur les variables pour afficher les DataTips, utilisez les fenêtres **Variables locales**, **Suivi**, et **Pile des appels**, et évaluer des expressions.

    Le site web lui-même est toujours en ligne ; les utilisateurs finaux ne sont pas affectés. Par défaut, le snappoint ne prend qu’une capture instantanée : dès que c’est fait, ce dernier se désactive. Si vous souhaitez prendre une autre capture instantanée sur le snappoint, vous pouvez le réactiver en cliquant sur **Mettre à jour la collecte**.

Vous pouvez également ajouter d’autres snappoints à votre application et les activer avec le bouton **Mettre à jour la collecte**.

**Vous avez besoin d'aide ?** Voir les pages [Résolution des problèmes et problèmes connus](../debugger/debug-live-azure-apps-troubleshooting.md) et [FAQ du débogage de captures instantanées](../debugger/debug-live-azure-apps-faq.md).

## <a name="set-a-conditional-snappoint"></a>Définir un snappoint conditionnel

S’il vous est difficile de recréer un état particulier de votre application, vous pouvez utiliser un snappoint conditionnel. Les snappoints conditionnels évitent d’avoir à prendre une capture instantanée tant que l’application n’est pas passée à l’état souhaité, par exemple lorsqu’une variable prend une valeur que vous souhaitez inspecter. Les conditions sont définies à l’aide d’expressions, de filtres ou d’un nombre d’accès.

#### <a name="to-create-a-conditional-snappoint"></a>Créer un snappoint conditionnel

1. Cliquez avec le bouton droit sur une icône de snappoint (sphère) et choisissez **Paramètres**.

   ![Choisir des paramètres](../debugger/media/snapshot-snappoint-settings.png)

1. Dans la fenêtre des paramètres du snappoint, tapez une expression.

   ![Taper une expression](../debugger/media/snapshot-snappoint-conditions.png)

   Dans l’illustration précédente, la capture instantanée n’est pas prise pour le snappoint que si `visitor.FirstName == "Dan"`.

## <a name="set-a-logpoint"></a>Définir un logpoint

Nous avons vu comment prendre une capture instantanée lorsqu’un snappoint est atteint. Il est également possible de configurer un snappoint de sorte qu’il consigne un message (autrement dit, qu’il crée un logpoint). Il n’est pas nécessaire pour cela de redéployer l’application. Les logpoints sont exécutés virtuellement, sans impact ou ni effet secondaire sur l’application en cours d’exécution.

#### <a name="to-create-a-logpoint"></a>Créer un logpoint

1. Cliquez avec le bouton droit sur une icône de snappoint (hexagone bleu) et choisissez **Paramètres**.

1. Dans la fenêtre des paramètres du snappoint, sélectionnez **Actions**.

    ![Créer un logpoint](../debugger/media/snapshot-logpoint.png)

1. Dans le champ **Message**, entrez le nouveau message de journal à consigner. Vous pouvez également évaluer des variables dans votre message de journal en les plaçant entre accolades.

    Si **Envoyer dans la fenêtre Sortie** est sélectionné, le message s’affiche dans la fenêtre Outils de diagnostic lorsque le logpoint est atteint.

    ![Données de logpoint dans la fenêtre Outils de diagnostic](../debugger/media/snapshot-logpoint-output.png)

    Si **Envoyer au journal des applications** est sélectionné, le message s’affiche partout où apparaissent les messages de `System.Diagnostics.Trace` (ou `ILogger` dans .NET Core), par exemple [App Insights](/azure/application-insights/app-insights-asp-net-trace-logs), lorsque le logpoint est atteint.

## <a name="next-steps"></a>Étapes suivantes

Dans ce tutoriel, vous avez appris comment utiliser le Débogueur de capture instantanée pour les machines virtuelles Azure et les groupes de machines virtuelles identiques Azure. Peut-être souhaitez-vous en savoir plus sur cette fonctionnalité.

> [!div class="nextstepaction"]
> [Questions fréquentes (FAQ) sur le débogage d’instantané](../debugger/debug-live-azure-apps-faq.md)