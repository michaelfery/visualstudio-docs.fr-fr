---
title: Guide pratique pour spécifier le fichier binaire à démarrer | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.itemlaunch
helpviewer_keywords:
- profiling tools, launching
- performance tools, launching
- performance sessions, launching
ms.assetid: ba77fcf4-8d78-49f1-b8f3-7dd0acf84306
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 45b5e3ba98c526ffea1ab63f58ef9193a3eaae75
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54759891"
---
# <a name="how-to-specify-the-binary-to-start"></a>Guide pratique pour spécifier le fichier binaire à démarrer
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pour profiler des fichiers binaires, tels que les DLL, vous devez entrer des informations dans la boîte de dialogue **Pages de propriétés de \<Cible>**. Ces informations indiquent où le projet DLL peut trouver l’application appelante.  
  
 **Spécifications**  
  
-   [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
### <a name="to-specify-the-executable-to-start"></a>Pour spécifier l’exécutable à démarrer  
  
1.  Dans l’**Explorateur de performances**, cliquez avec le bouton droit sur le fichier binaire cible, puis cliquez sur **Propriétés**.  
  
2.  Dans la boîte de dialogue **Pages de propriétés**, cliquez sur les propriétés **Lancer**.  
  
3.  Cochez la case **Remplacer les paramètres du projet**.  
  
4.  Dans la zone de texte **Exécutable à lancer**, spécifiez l’emplacement du fichier.  
  
5.  Dans la zone de texte **Arguments**, spécifiez les arguments nécessaires pour démarrer l’application.  
  
6.  Dans la zone de texte **Répertoire de travail**, spécifiez l’emplacement du répertoire.  
  
7.  Cliquez sur **OK**.  
  
## <a name="see-also"></a>Voir aussi  
 [Configuration de sessions de performances](../profiling/configuring-performance-sessions.md)
