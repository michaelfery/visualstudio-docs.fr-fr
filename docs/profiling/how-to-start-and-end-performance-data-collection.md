---
title: 'Procédure : Démarrer et terminer la collecte des données de performances | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.wizard.summarypage
helpviewer_keywords:
- profiling tools, launching sessions
- performance sessions, launching
- performance sessions, ending
- profiling tools, ending sessions
ms.assetid: 9f6eb0d5-d9e9-4bec-b627-445065610bce
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 798ae2e577d56abbe4cd2619ea40c7fc729d2406
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56622538"
---
# <a name="how-to-start-and-end-performance-data-collection"></a>Procédure : Démarrer et terminer la collecte des données de performances
Vous devez ajouter le fichier binaire cible à profiler à la session de performance avant de démarrer le profilage. Pour ajouter une cible, cliquez avec le bouton droit sur **Cibles** dans l’**Explorateur de performances**, puis cliquez sur **Ajouter un fichier binaire cible**. Dans la boîte de dialogue **Ajouter un fichier binaire cible**, sélectionnez le nom du fichier, puis cliquez sur **Ouvrir**. Un nouveau fichier binaire est ajouté.

### <a name="to-start-profiling"></a>Pour démarrer le profilage

1.  Cliquez avec le bouton droit sur le nom de la session de performance dans la fenêtre **Explorateur de performances**, puis choisissez l’une des options suivantes :

    -   **Démarrer avec le profilage** : démarre l’application et commence immédiatement le profilage.

    -   **Démarrer avec le profilage suspendu** : démarre l’application sans commencer le profilage. Pour commencer le profilage, sélectionnez **Reprendre la collecte** dans la fenêtre **Contrôle de collecte de données**. Pour plus d'informations, voir [Procédure : Suspendre et reprendre la collecte de données de performances](../profiling/how-to-pause-and-resume-performance-data-collection.md).

### <a name="to-end-profiling"></a>Pour terminer le profilage

-   Pour terminer une session de profilage, il est recommandé de quitter l’application. Pour arrêter immédiatement le profilage, dans la barre d’outils de l’**Explorateur de performances**, cliquez sur **Arrêter**.

## <a name="see-also"></a>Voir aussi
- [Contrôler la collecte des données](../profiling/controlling-data-collection.md)
- [Guide pratique pour suspendre et reprendre la collecte de données de performances](../profiling/how-to-pause-and-resume-performance-data-collection.md)