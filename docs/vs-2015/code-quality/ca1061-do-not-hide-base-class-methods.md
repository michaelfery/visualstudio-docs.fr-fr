---
title: 'CA1061 : Ne pas masquer les méthodes de classe de base | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1061
- DoNotHideBaseClassMethods
helpviewer_keywords:
- DoNotHideBaseClassMethods
- CA1061
ms.assetid: 0bda9dc8-87b4-4038-ab9d-563298387466
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e932b2c948493c4703e8edd5edb37818e80f0253
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58951558"
---
# <a name="ca1061-do-not-hide-base-class-methods"></a>CA1061 : Ne pas masquer les méthodes de la classe de base
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotHideBaseClassMethods|
|CheckId|CA1061|
|Category|Microsoft.Design|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Un type dérivé déclare une méthode portant le même nom et avec le même nombre de paramètres qu’une de ses méthodes de base ; un ou plusieurs des paramètres sont un type de base du paramètre correspondant dans la méthode de base ; et tous les paramètres restants ont des types qui sont identiques aux paramètres correspondants dans la méthode de base.

## <a name="rule-description"></a>Description de la règle
 Une méthode dans un type de base est masquée par une méthode portant le même nommée dans un type dérivé lorsque la signature de paramètre de la méthode dérivée diffère uniquement par les types qui sont dérivés plus faiblement que les types correspondants dans la signature de paramètre de la méthode de base.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, supprimer ou renommer la méthode ou modifiez la signature de paramètre afin que la méthode ne masque pas la méthode de base.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="example"></a>Exemple
 L’exemple suivant montre une méthode qui enfreint la règle.

 [!code-csharp[FxCop.Design.HideBaseMethod#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.HideBaseMethod/cs/FxCop.Design.HideBaseMethod.cs#1)]
