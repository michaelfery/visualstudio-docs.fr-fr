---
title: 'Procédure pas à pas : Capture d’informations graphiques | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48f12f6e-57b4-48ec-a145-89fa71a42424
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: de553729d37bb82d1b30c6a142f7e65c983bb1c1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47494786"
---
# <a name="walkthrough-capturing-graphics-information"></a>Procédure pas à pas : capture d'informations Graphics
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [procédure pas à pas : capture d’informations graphiques](https://docs.microsoft.com/visualstudio/debugger/graphics/walkthrough-capturing-graphics-information).  
  
Cette procédure pas à pas montre comment utiliser le [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Graphics Diagnostics pour capturer manuellement les informations graphiques d’une application Direct3D.  
  
 Cette procédure pas à pas décrit les tâches suivantes :  
  
-   Raccordement de Graphics Diagnostics à votre application  
  
-   Capture d'informations graphiques  
  
## <a name="capturing-graphics-information"></a>Capture d'informations graphiques  
 Pour utiliser les outils Graphics Diagnostics, vous devez d'abord capturer les informations graphiques dont ils ont besoin. Pour activer la capture, utilisez la commande **Démarrer les diagnostics** pour raccorder Graphics Diagnostics à votre application lors de son démarrage.  
  
#### <a name="to-enable-the-capture-of-graphics-information-after-a-project-or-solution-is-loaded"></a>Pour activer la capture des informations graphiques après le chargement d’un projet ou d’une solution  
  
1.  Dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], charger un fichier projet ou solution pour l’application que vous souhaitez capturer les informations graphiques.  
  
2.  Dans la barre d’outils Graphics Diagnostics, choisissez **Démarrer les diagnostics**.  
  
#### <a name="to-enable-the-capture-of-graphics-information-without-loading-a-project-or-solution"></a>Pour activer la capture des informations graphiques sans charger de projet ou solution  
  
1.  Dans la barre de menus, choisissez **Fichier**, **Ouvrir**, **Projet/Solution**. La boîte de dialogue **Ouvrir un projet** s’affiche.  
  
2.  Au lieu d’un fichier projet ou solution, spécifiez le fichier exécutable de l’application dont vous voulez capturer les informations graphiques, puis choisissez **Ouvrir**.  
  
3.  Dans la barre de menus, choisissez **Déboguer**, **Graphiques**, **Démarrer les diagnostics**.  
  
 Après le démarrage de l’application et l’affichage des frames, vous pouvez commencer la capture des informations graphiques.  
  
#### <a name="to-capture-graphics-information"></a>Pour capturer des informations graphiques  
  
-   Dans la barre d’outils Graphics Diagnostics, choisissez le bouton **Capturer** . ![Icône de bouton de capture de Graphics](../debugger/media/debuggingdirectxgraphics.png "DebuggingDirectXGraphics")  
  
     - ou -  
  
     Quand l’application a le focus, appuyez sur **Impr. écran**.  
  
 Chaque fois que vous capturez des informations sur un frame, Graphics Diagnostics enregistre les événements Direct3D et leur état associé, puis ajoute ces données dans un journal de graphisme. Un nouveau journal de graphisme est créé pour chaque session Graphics Diagnostics. Pour plus d’informations sur les journaux de graphisme, consultez [vue d’ensemble](../debugger/overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="next-steps"></a>Étapes suivantes  
 Cette procédure pas à pas vous a montré comment capturer manuellement des informations graphiques. Pour franchir une étape supplémentaire, envisagez cette possibilité :  
  
-   Découvrez comment analyser les informations graphiques capturées à l’aide des outils Graphics Diagnostics. Consultez [vue d’ensemble](../debugger/overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Capture d’informations graphiques](../debugger/capturing-graphics-information.md)


