---
title: 'DA0503 : Jeu de travail moyen en octets pour le processus en cours de profilage | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.503
- vs.performance.DA0503
- vs.performance.rules.DA0503
ms.assetid: 9047a494-eaaf-4679-b422-c64e8bde77a4
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e71d7e630505d44392610ab5ba94c19b3928f7f9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47501114"
---
# <a name="da0503-average-working-set-in-bytes-for-the-process-being-profiled"></a>DA0503 : jeu de travail moyen, en octets, pour le processus en cours de profilage
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [DA0503 : jeu de travail moyen en octets pour le processus profilé](https://docs.microsoft.com/visualstudio/profiling/da0503-average-working-set-in-bytes-for-the-process-being-profiled).  
  
Id de règle | DA0503 |  
| Catégorie | Surveillance des ressources |  
| Méthode de profilage | Tous les |  
| Message | À titre d’information uniquement. Le compteur Jeu de travail de processus mesure l’utilisation de la mémoire physique par le processus en cours de profilage. La valeur signalée correspond à la moyenne de tous les intervalles de mesure. |  
| Type de règle | Informations |  
  
 Lorsque vous effectuez un profilage à l’aide de la méthode d’échantillonnage, de mémoire .NET ou de conflit des ressources, vous devez collecter au moins 10 échantillons pour déclencher cette règle.  
  
## <a name="rule-description"></a>Description de la règle  
 Ce message signale la quantité moyenne de mémoire physique que le processus utilise actuellement, en octets (le jeu de travail). Le jeu de travail du processus comprend les pages de l’espace d’adressage de processus qui résident actuellement dans la mémoire physique.  
  
 La valeur signalée comprend les pages résidant dans les segments de mémoire partagée que le processus a référencées. Les DLL partagées que le processus référence sont incluses dans les segments de mémoire partagée qui sont comptabilisés. La valeur du jeu de travail du processus peut être supérieure à la quantité de mémoire virtuelle que le processus a allouée, en raison des segments de mémoire partagée.  
  
 La valeur signalée correspond à la moyenne de tous les intervalles de mesure pendant lesquels le processus profilé était actif.  
  
 La taille du jeu de travail du processus correspond à la mémoire virtuelle que le processus utilise activement. Elle est également affectée par la quantité de mémoire physique (ou RAM) disponible pour exécuter l’application, et par les conflits entre cette mémoire physique et d’autres processus en cours d’exécution. Si la mémoire physique est limitée, la valeur du jeu de travail de processus peut varier considérablement lorsque les systèmes d’exploitation tentent d’équilibrer l’utilisation de la mémoire entre les processus actifs en supprimant périodiquement les pages relativement inactives des jeux de travail de processus.  
  
 Pour plus d’informations sur les jeux de travail de processus, consultez [Jeu de travail](http://go.microsoft.com/fwlink/?LinkId=177830) dans la documentation MSDN relative à la gestion de la mémoire dans Windows.  
  
## <a name="how-to-use-rule-data"></a>Comment utiliser des données de règle  
 Utilisez la valeur de la règle pour comparer les performances des différentes versions du programme ou pour comprendre les performances de l’application dans différents scénarios de profilage.  
  
 Double-cliquez sur le message dans la fenêtre Liste d’erreurs pour accéder à la vue [Marques](../profiling/marks-view.md) des données de profilage. Accédez aux colonnes **Processus\Jeu de travail** et **Mémoire\Pages/s**. Comparez les deux colonnes et déterminez si des phases de l’exécution du programme ont connu une augmentation de l’activité d’E/S de pagination.


