---
title: Guide pratique pour exclure ou inclure les fonctions courtes de l’instrumentation | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, instrument events
- profiling tools, include short functions
- profiling tools, exclude short functions
ms.assetid: eaeead79-aafe-4490-86ff-6ed4cad9c15f
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d37984b6535e353053ba6ee71090797e4ce119d3
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54801659"
---
# <a name="how-to-exclude-or-include-short-functions-from-instrumentation"></a>Guide pratique pour exclure ou inclure les fonctions courtes de l’instrumentation
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Par défaut, les outils de profilage excluent les *petites fonctions* de l’instrumentation. Les petites fonctions sont des fonctions courtes qui n’effectuent pas d’appels de fonction. L’exclusion de ces petites fonctions permet de réduire la surcharge d’instrumentation, et donc d’accélérer la vitesse d’instrumentation. L’exclusion des petites fonctions a également pour effet de réduire la taille du fichier de données de profilage de performances (.vsp) et de raccourcir le temps nécessaire à l’analyse. Si les petites fonctions sont exclues, le temps qui leur est consacré sera soustrait du temps exclusif et inclusif de leurs fonctions parents. Les petites fonctions peuvent être exclues ou incluses dans l’instrumentation, comme le décrit la procédure suivante.  
  
### <a name="to-exclude-or-include-short-functions-from-instrumentation"></a>Pour exclure ou inclure les fonctions courtes de l’instrumentation  
  
1.  Dans l’**Explorateur de performances**, sélectionnez **Session de performance**, puis cliquez avec le bouton droit et sélectionnez **Propriétés**.  
  
     La boîte de dialogue **Pages de propriétés** s’affiche.  
  
2.  Dans les **Pages de propriétés**, cliquez sur les propriétés **Instrumentation**.  
  
3.  Pour exclure les fonctions courtes de l’instrumentation, sélectionnez **Exclure les petites fonctions de l’instrumentation**. Il s'agit du paramètre par défaut.  
  
     - ou -  
  
     Pour inclure les fonctions courtes dans l’instrumentation, décochez la case **Exclure les petites fonctions de l’instrumentation**.  
  
4.  Cliquez sur **OK**.  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de la collecte de données](../profiling/controlling-data-collection.md)   
 [Propriétés d’une session de performance](../profiling/performance-session-properties.md)
