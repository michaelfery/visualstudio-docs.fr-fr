---
title: 'CA2229 : Implémentez des constructeurs de sérialisation | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2229
- ImplementSerializationConstructors
helpviewer_keywords:
- CA2229
- ImplementSerializationConstructors
ms.assetid: 8e04d5fe-dfad-445a-972e-0648324fac45
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ee283e2e25958d497e00dad245bb69841196c65c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58938663"
---
# <a name="ca2229-implement-serialization-constructors"></a>CA2229 : Implémentez des constructeurs de sérialisation
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ImplementSerializationConstructors|
|CheckId|CA2229|
|Category|Microsoft.Usage|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Le type implémente le <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> interface, n’est pas un délégué ou une interface, et une des conditions suivantes est remplie :

-   Le type n’a pas de constructeur qui accepte un <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> objet et un <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> objet (la signature du constructeur de sérialisation).

-   Le type est non scellé, et le modificateur d’accès pour son constructeur de sérialisation n’est pas protégé (famille).

-   Le type est sealed et le modificateur d’accès pour son constructeur de sérialisation n’est pas privé.

## <a name="rule-description"></a>Description de la règle
 Cette règle s’applique aux types qui prennent en charge la sérialisation personnalisée. Un type prend en charge la sérialisation personnalisée s’il implémente la <xref:System.Runtime.Serialization.ISerializable> interface. Le constructeur de sérialisation est requis pour désérialiser ou recréer des objets qui ont été sérialisés à l’aide de la <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> (méthode).

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, implémentez le constructeur de sérialisation. Dans le cas d'une classe sealed, rendez le constructeur privé ; sinon, attribuez-lui l'état protégé.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez pas une violation de la règle. Le type ne sera pas désérialisable et ne fonctionnera pas dans de nombreux scénarios.

## <a name="example"></a>Exemple
 L’exemple suivant illustre un type qui satisfait la règle.

 [!code-csharp[FxCop.Usage.ISerializableCtor#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.ISerializableCtor/cs/FxCop.Usage.ISerializableCtor.cs#1)]

## <a name="related-rules"></a>Règles associées
 [CA2237 : Marquer les types ISerializable avec SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

## <a name="see-also"></a>Voir aussi
 <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>
 <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>
