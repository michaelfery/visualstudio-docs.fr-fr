---
title: CreateCSharpManifestResourceName, tâche | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CreateCSharpManifestResourceName task
- CreateCSharpManifestResourceName task [MSBuild]
ms.assetid: 2ace88c1-d757-40a7-8158-c1d3f5ff0511
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 05028dabe3ca5c6cff8838a1f4ac69b0cf70bce0
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2019
ms.locfileid: "54773055"
---
# <a name="createcsharpmanifestresourcename-task"></a>CreateCSharpManifestResourceName, tâche
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Crée un nom de manifeste de style [!INCLUDE[csprcs](../includes/csprcs-md.md)] à partir d’un nom de fichier .resx donné ou d’une autre ressource.  
  
## <a name="parameters"></a>Paramètres  
 Le tableau suivant décrit les paramètres de la [tâche reateCSharpManifestResourceName](../msbuild/createcsharpmanifestresourcename-task.md).  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`ManifestResourceNames`|Paramètre de sortie <xref:Microsoft.Build.Framework.ITaskItem> `[]` en lecture seule.<br /><br /> Noms des manifestes résultants.|  
|`ResourceFiles`|Paramètre `String` requis.<br /><br /> Nom du fichier de ressources à partir duquel créer le nom du manifeste [!INCLUDE[csprcs](../includes/csprcs-md.md)].|  
|`RootNamespace`|Paramètre `String` facultatif.<br /><br /> Espace de noms racine du fichier de ressources, qui provient généralement du fichier projet. Peut avoir la valeur `null`.|  
|`PrependCultureAsDirectory`|Paramètre `Boolean` facultatif.<br /><br /> Si `true`, le nom de culture est ajouté comme nom de répertoire juste avant le nom de ressource de manifeste. La valeur par défaut est `true`.|  
|`ResourceFilesWithManifestResourceNames`|Paramètre de sortie `String` en lecture seule facultatif.<br /><br /> Retourne le nom du fichier de ressources qui inclut maintenant le nom de ressource de manifeste.|  
  
## <a name="remarks"></a>Remarques  
 La [tâche CreateVisualBasicManifestResourceName](../msbuild/createvisualbasicmanifestresourcename-task.md) détermine le nom de ressource de manifeste approprié à assigner à un fichier .resx ou autre fichier de ressources donné. La tâche fournit un nom logique à un fichier de ressources, puis l’attache à un paramètre de sortie en tant que métadonnées.  
  
 En plus des paramètres énumérés ci-dessus, cette tâche hérite des paramètres de la classe <xref:Microsoft.Build.Tasks.TaskExtension>, qui elle-même hérite de la classe <xref:Microsoft.Build.Utilities.Task>. Pour obtenir la liste de ces paramètres supplémentaires et leurs descriptions, consultez [TaskExtension Base Class](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Tâches](../msbuild/msbuild-tasks.md)   
 [Task Reference (Informations de référence sur les tâches MSBuild)](../msbuild/msbuild-task-reference.md)
