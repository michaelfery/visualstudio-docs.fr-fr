---
title: 'CA1003 : Utiliser des instances du Gestionnaire d’événements génériques | Microsoft Docs'
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
- UseGenericEventHandlerInstances
- CA1003
helpviewer_keywords:
- CA1003
- UseGenericEventHandlerInstances
ms.assetid: 402101b6-555d-4cf7-b223-1d9fdfaaf1cd
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 4e6a2a3f3d2684c4de49d02dfb19c4654a76eda9
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47589631"
---
# <a name="ca1003-use-generic-event-handler-instances"></a>CA1003 : Utiliser les instances du gestionnaire d'événements génériques
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [CA1003 : utiliser des instances du Gestionnaire d’événements génériques](https://docs.microsoft.com/visualstudio/code-quality/ca1003-use-generic-event-handler-instances).

|||
|-|-|
|TypeName|UseGenericEventHandlerInstances|
|CheckId|CA1003|
|Category|Microsoft.Design|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Un type contienne un délégué qui retourne void, dont la signature contient deux paramètres (le premier est un objet et le second est un type pouvant être assigné à EventArgs) et l’assembly conteneur cible [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)].

## <a name="rule-description"></a>Description de la règle
 Avant de [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)], afin de passer des informations personnalisées au gestionnaire d’événements, un nouveau délégué devait être déclaré qui a spécifié une classe qui était dérivée de la <xref:System.EventArgs?displayProperty=fullName> classe. Ce n’est plus vrai dans [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)], qui a introduit le <xref:System.EventHandler%601?displayProperty=fullName> déléguer. Ce délégué générique permet à n’importe quelle classe dérivée de <xref:System.EventArgs> pour être utilisée avec le Gestionnaire d’événements.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, supprimez le délégué et remplacez son utilisation à l’aide de la <xref:System.EventHandler%601?displayProperty=fullName> déléguer. Si le délégué est généré automatiquement par le [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] compilateur, modifiez la syntaxe de la déclaration d’événement à utiliser le <xref:System.EventHandler%601?displayProperty=fullName> déléguer.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="example"></a>Exemple
 L’exemple suivant montre un délégué qui enfreint la règle. Dans le [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] exemple, commentaires expliquent comment modifier l’exemple pour satisfaire à la règle. Pour l’exemple c#, un exemple qui suit présente le code modifié.

 [!code-csharp[FxCop.Design.CustomEventHandler#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.CustomEventHandler/cs/FxCop.Design.CustomEventHandler.cs#1)]
 [!code-vb[FxCop.Design.CustomEventHandler#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.CustomEventHandler/vb/FxCop.Design.CustomEventHandler.vb#1)]

## <a name="example"></a>Exemple
 L’exemple suivant supprime la déclaration du délégué de l’exemple précédent, ce qui satisfait à la règle et remplace son utilisation dans le `ClassThatRaisesEvent` et `ClassThatHandlesEvent` méthodes aide le <xref:System.EventHandler%601?displayProperty=fullName> déléguer.

 [!code-csharp[FxCop.Design.GenericEventHandler#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.GenericEventHandler/cs/FxCop.Design.GenericEventHandler.cs#1)]

## <a name="related-rules"></a>Règles associées
 [CA1005 : Évitez trop de paramètres sur les types génériques](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010 : Les collections doivent implémenter une interface générique](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000 : Ne déclarez pas de membres statiques sur les types génériques](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002 : N’exposez pas de listes génériques](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006 : Ne pas imbriquer les types génériques dans les signatures de membre](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004 : Les méthodes génériques doivent fournir un paramètre de type](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1007 : Utiliser des méthodes génériques lorsque cela est approprié](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>Voir aussi
 [Génériques](http://msdn.microsoft.com/library/75ea8509-a4ea-4e7a-a2b3-cf72482e9282)


