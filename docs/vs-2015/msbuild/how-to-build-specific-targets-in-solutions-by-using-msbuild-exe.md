---
title: 'Comment : générer des cibles spécifiques dans des solutions en utilisant MSBuild.exe | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, building specific targets in a solution
- msbuild.exe, building specific targets in a solution
- MSBuild, msbuild.exe
ms.assetid: f46feb9b-4c16-4fec-b6e1-36a959692ba3
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 85c8f3dcb9364c2837cd4d10f163de3795821ce7
ms.sourcegitcommit: 4d9c54f689416bf1dc4ace058919592482d02e36
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58194228"
---
# <a name="how-to-build-specific-targets-in-solutions-by-using-msbuildexe"></a>Comment : générer des cibles spécifiques dans des solutions en utilisant MSBuild.exe
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Vous pouvez utiliser MSBuild.exe pour générer des cibles spécifiques de certains projets d’une solution.  
  
### <a name="to-build-a-specific-target-of-a-specific-project-in-a-solution"></a>Pour générer une cible spécifique d’un projet particulier d’une solution  
  
1.  Dans la ligne de commande, tapez `MSBuild.exe <SolutionName>.sln`, où `<SolutionName>` correspond au nom de fichier de la solution qui contient la cible à exécuter.  
  
2.  Spécifiez la cible après le commutateur **/t** en respectant le format *nom_projet*:*nom_cible*.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant exécute la cible `Rebuild` du projet `NotInSlnFolder`, puis exécute la cible `Clean` du projet `InSolutionFolder`, qui se trouve dans le dossier de solution `NewFolder`.  
  
```  
msbuild SlnFolders.sln /t:NotInSlnfolder:Rebuild;NewFolder\InSolutionFolder:Clean  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Command-Line Reference (Référence de ligne de commande MSBuild)](../msbuild/msbuild-command-line-reference.md)   
 [Référence MSBuild](../msbuild/msbuild-reference.md)   
 [MSBuild](msbuild.md)  
 [Concepts MSBuild](../msbuild/msbuild-concepts.md)
