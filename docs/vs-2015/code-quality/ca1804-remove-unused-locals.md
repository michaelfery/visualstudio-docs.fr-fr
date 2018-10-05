---
title: 'CA1804 : Supprimez les variables locales inutilisées | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1804
- RemoveUnusedLocals
helpviewer_keywords:
- RemoveUnusedLocals
- CA1804
ms.assetid: cc332e67-6543-4813-bd8a-6f6fc75bf22a
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b2d54383061d9d033ad368b05121e794f761f219
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47588135"
---
# <a name="ca1804-remove-unused-locals"></a>CA1804 : Supprimez les variables locales inutilisées
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [CA1804 : supprimez les variables locales inutilisées](https://docs.microsoft.com/visualstudio/code-quality/ca1804-remove-unused-locals).

|||
|-|-|
|TypeName|RemoveUnusedLocals|
|CheckId|CA1804|
|Category|Microsoft.Performance|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Une méthode déclare une variable locale, mais n’utilise pas la variable sauf éventuellement en tant que le destinataire d’une instruction d’assignation. Pour l’analyse par cette règle, l’assembly testé doit être généré avec les informations de débogage et le fichier de base de données (.pdb) du programme associé doit être disponible.

## <a name="rule-description"></a>Description de la règle
 Les variables locales inutilisées et les assignations inutiles augmentent la taille d'un assembly et font baisser les performances.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, supprimez ou utilisez la variable locale. Notez que le compilateur c# qui est inclus avec [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)] supprime les variables locales inutilisées lorsque le `optimize` est activée.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Supprimez un avertissement de cette règle si la variable a été émise par un compilateur. Il est également recommandé de supprimer un avertissement de cette règle, ou pour désactiver la règle, si les performances et maintenance du code ne sont pas des préoccupations.

## <a name="example"></a>Exemple
 L’exemple suivant montre plusieurs variables locales inutilisées.

 [!code-csharp[FxCop.Performance.UnusedLocals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.UnusedLocals/cs/FxCop.Performance.UnusedLocals.cs#1)]
 [!code-vb[FxCop.Performance.UnusedLocals#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.UnusedLocals/vb/FxCop.Performance.UnusedLocals.vb#1)]

## <a name="related-rules"></a>Règles associées
 [CA1809 : Évitez le surplus de variables locales](../code-quality/ca1809-avoid-excessive-locals.md)

 [CA1811 : Évitez le recours à du code privé non appelé](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1812 : Évitez les classes internes non instanciées](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1801 : Passez en revue les paramètres inutilisés](../code-quality/ca1801-review-unused-parameters.md)


