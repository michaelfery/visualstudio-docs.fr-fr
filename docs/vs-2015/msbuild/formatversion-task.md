---
title: FormatVersion, tâche | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 96e692f6-b581-46ca-8cc9-441a1861e371
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7fbd03676d69dde5f9a6d169739a25e7b5e1b82e
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2019
ms.locfileid: "54755123"
---
# <a name="formatversion-task"></a>Tâche FormatVersion
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Ajoute le numéro de révision au numéro de version.  
  
-   Cas #1 : Input: Version=\<undefined>;  Revision=\<peu importe>;   Output: OutputVersion="1.0.0.0"  
  
-   Cas #2 : Input: Version="1.0.0.*"  Revision="5"  Output: OutputVersion="1.0.0.5"  
  
-   Cas #3 : Input: Version="1.0.0.0"  Revision=\<peu importe>;  Output: OutputVersion="1.0.0.0"  
  
## <a name="parameters"></a>Paramètres  
 Le tableau ci-dessous décrit les paramètres de la tâche `FormatVersion` .  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`FormatType`|Paramètre `String` facultatif.<br /><br /> Spécifie le type de format.<br /><br /> -   "Version" = version.<br />-   "Path" = remplacez "." par "_";|  
|`OutputVersion`|Paramètre de sortie `String` facultatif.<br /><br /> Spécifie la version de la sortie qui inclut le numéro de révision.|  
|`Revision`|Paramètre `Int32` facultatif.<br /><br /> Spécifie la révision à ajouter à la version.|  
|`Version`|Paramètre `String` facultatif.<br /><br /> Spécifie la chaîne de numéro de version à mettre en forme.|  
  
## <a name="remarks"></a>Remarques  
 En plus des paramètres répertoriés dans le tableau, cette tâche comprend des paramètres qu’elle hérite de la classe <xref:Microsoft.Build.Tasks.TaskExtension>, qui elle-même hérite de la classe <xref:Microsoft.Build.Utilities.Task>. Pour obtenir la liste de ces paramètres supplémentaires et leurs descriptions, consultez [TaskExtension Base Class](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Tâches](../msbuild/msbuild-tasks.md)   
 [Task Reference (Informations de référence sur les tâches MSBuild)](../msbuild/msbuild-task-reference.md)
