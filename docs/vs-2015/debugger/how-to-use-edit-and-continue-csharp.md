---
title: 'Procédure : Utiliser Modifier & Continuer (C#) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Edit and Continue [C#], about Edit and Continue
ms.assetid: 40e136d8-a08c-43bd-b313-fb821c55eb3c
caps.latest.revision: 22
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c52540c8e639adcd8ceec6b4da79fb87cff18386
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58949999"
---
# <a name="how-to-use-edit-and-continue-c"></a>Procédure : Utiliser Modifier & Continuer (C#)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Avec Modifier &amp; Continuer pour C#, vous pouvez modifier votre code en mode arrêt pendant le débogage. Les modifications peuvent être appliquées sans qu'il soit nécessaire d'arrêter et de redémarrer la session de débogage.  
  
 Modifier & Continuer est appelé automatiquement lorsque vous apportez des modifications en mode arrêt, puis choisissez une débogueur, l’exécution commande, telles que **continuer**, **étape**, ou **définir l’instruction suivante**, ou évaluez une fonction dans une fenêtre du débogueur.  
  
> [!NOTE]
>  Modifier & Continuer n’est pas pris en charge lorsque le Compact Framework, le code optimisé, le débogage mixte natif/managé ou code de l’intégration SQL Server common language runtime (CLR). Si vous essayez d’appliquer les modifications du code dans un de ces scénarios, le débogueur affiche une boîte de dialogue expliquant que Modifier & Continuer n’est pas compatible.  
  
### <a name="to-invoke-edit-and-continue-automatically"></a>Pour appeler modifier et continuer automatiquement  
  
1.  En mode arrêt, apportez une modification à votre code source.  
  
2.  À partir de la **déboguer** menu, cliquez sur **continuer**, **étape**, ou **définir l’instruction suivante** ou évaluez une fonction dans une fenêtre du débogueur.  
  
     Le nouveau code est compilé et le débogage se poursuit avec le nouveau code. Certaines modifications ne sont pas pris en charge par Modifier & Continuer. Pour plus d’informations, consultez [les modifications de Code prises en charge (C#)](../debugger/supported-code-changes-csharp.md).  
  
### <a name="to-enabledisable-edit-and-continue"></a>Pour activer ou désactiver Modifier &amp; Continuer  
  
1.  Dans le menu **Outils**, cliquez sur **Options**.  
  
2.  Dans le **Options** boîte de dialogue, développez le **débogage** nœud, puis sélectionnez **Modifier & Continuer**.  
  
3.  Dans le **Options** boîte de dialogue **Modifier & Continuer** page, activez ou désactivez le **Activer Modifier & Continuer** case à cocher.  
  
     Le paramètre prend effet lorsque vous redémarrez la session de débogage.  
  
## <a name="see-also"></a>Voir aussi  
 [Modifier & Continuer (Visual C#)](../debugger/edit-and-continue-visual-csharp.md)   
 [Modifications de Code prises en charge (C#)](../debugger/supported-code-changes-csharp.md)   
 [Erreurs et avertissements de Modifier & Continuer (C#)](../misc/edit-and-continue-errors-and-warnings-csharp.md)
