---
title: Installer des frameworks de tests unitaires tierces | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47893b70-46f8-49dc-84bd-ec820178f683
caps.latest.revision: 12
ms.author: gewarren
manager: douge
ms.openlocfilehash: 8a0f17f4c49c88b341c6ccc7583f7069c8b5142a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47508606"
---
# <a name="install-third-party-unit-test-frameworks"></a>Installer des frameworks de tests unitaires tierces
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [installer des infrastructures de tests unitaires de tiers](https://docs.microsoft.com/visualstudio/test/install-third-party-unit-test-frameworks).  
  
L'Explorateur de tests Visual Studio peut exécuter n'importe quel framework de tests unitaires ayant développé une interface d'adaptateur pour l'Explorateur. Le programme d'installation du framework installe les fichiers binaires et ajoute des modèles de projet Visual Studio pour les langages qu'il prend en charge. Lorsque vous créez un projet avec le modèle, le framework est inscrit avec l'Explorateur de tests. Une solution Visual Studio peut contenir des projets de test unitaire qui utilisent des frameworks différents et qui sont destinés à des langages différents. L'Explorateur de tests les exécute tous.  
  
 **Spécifications**  
  
-   Visual Studio Enterprise, Visual Studio Professional  
  
## <a name="acquiring-third-party-frameworks"></a>Obtention de frameworks tiers  
 Vous pouvez télécharger et installer plusieurs frameworks de test unitaire tiers à l'aide du gestionnaire d'extensions de Visual Studio ou à partir de la galerie Visual Studio sur le site web MSDN. Il est également possible de télécharger des frameworks à partir d'autres sites tels que le site web du framework.  
  
### <a name="installing-from-visual-studio"></a>Installation à partir de Visual Studio  
  
1.  Choisissez **Outils** dans le menu standard, puis choisissez **Extensions et mises à jour**.  
  
2.  Développez **En ligne**, **Galerie Visual Studio**, **Outils**. Choisissez **Test**.  
  
3.  Parcourez la liste pour rechercher le framework.  
  
4.  Sélectionnez le framework, puis choisissez **Télécharger**.  
  
 Pour plus d’informations, consultez [Recherche et utilisation des extensions Visual Studio](../ide/finding-and-using-visual-studio-extensions.md).  
  
### <a name="installing-from-the-web"></a>Installation à partir du web  
 Si vous savez quel framework vous intéresse :  
  
1.  Ouvrez [la galerie Visual Studio](http://go.microsoft.com/fwlink/?LinkId=236267) sur le site web MSDN.  
  
2.  Tapez le nom du framework dans la zone **Rechercher**.  
  
3.  Choisissez le framework dans la liste des résultats pour accéder à la page de la galerie Visual Studio correspondant à l'outil.  
  
 Pour parcourir la liste des frameworks ainsi que d'autres outils de test :  
  
1.  Ouvrez [la galerie Visual Studio](http://go.microsoft.com/fwlink/?LinkId=236267) sur le site web MSDN.  
  
2.  Choisissez **Parcourir**.  
  
3.  Dans la liste **Catégorie**, développez le nœud **Outils**, puis choisissez **Test**.  
  
4.  Choisissez un framework dans la liste des résultats pour accéder à une page de la galerie Visual Studio correspondant à l'outil.  
  
## <a name="see-also"></a>Voir aussi  
 [Tests unitaires sur votre code](../test/unit-test-your-code.md)


