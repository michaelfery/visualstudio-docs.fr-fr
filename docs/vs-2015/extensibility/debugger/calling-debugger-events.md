---
title: Appel des événements de débogueur | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: b3440ac3-80af-40c6-bef4-cbf00fa67885
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 86c48d072baa53cf3f8ba0a6d903021e6c396afa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47502169"
---
# <a name="calling-debugger-events"></a>Événements d’appel du débogueur
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [appelant les événements de débogueur](https://docs.microsoft.com/visualstudio/extensibility/debugger/calling-debugger-events).  
  
Dans les sessions de débogage se produisent dans un ordre spécifique.  
  
## <a name="discussion"></a>Discussion  
 Pour comprendre le modèle d’appels entre le moteur de débogage (dé) et le Gestionnaire de session de débogage (SDM), ce qui suit représente l’ordre d’appel des événements qui se produisent dans une session de débogage classique :  
  
1.  [Attachement et détachement d’un programme](../../extensibility/debugger/attaching-and-detaching-to-a-program.md)  
  
2.  [Lancement du débogueur](../../extensibility/debugger/launching-the-debugger.md)  
  
3.  [Arrêt d’un programme](../../extensibility/debugger/terminating-a-program.md)  
  
4.  [Création d’un point d’arrêt](../../extensibility/debugger/creating-a-breakpoint.md)  
  
5.  [Quand un point d’arrêt est lié ou devient indépendant](../../extensibility/debugger/when-a-breakpoint-binds-or-becomes-unbound.md)  
  
6.  [Erreurs de point d’arrêt](../../extensibility/debugger/breakpoint-errors.md)  
  
7.  [Atteindre un point d’arrêt](../../extensibility/debugger/hitting-a-breakpoint.md)  
  
8.  [Suppression d’un point d’arrêt](../../extensibility/debugger/deleting-a-breakpoint.md)  
  
9. [Passage en mode arrêt](../../extensibility/debugger/entering-break-mode.md)  
  
10. [Exécution pas à pas en mode arrêt](../../extensibility/debugger/stepping-in-break-mode.md)  
  
11. [Évaluation de l’expression en mode arrêt](../../extensibility/debugger/expression-evaluation-in-break-mode.md)  
  
12. [Gestion des exceptions](../../extensibility/debugger/exception-handling-visual-studio-sdk.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Création d’un moteur de débogage personnalisé](../../extensibility/debugger/creating-a-custom-debug-engine.md)
