---
title: '&lt;Planifications&gt; élément (programme d’amorçage) | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <Schedules> element [bootstrapper]
ms.assetid: 28d094cf-64f5-42b1-bd8a-3697082aab4f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a2f6e4ae90dbd36dab4f4df7f72d5ecf57ee04b1
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56639425"
---
# <a name="ltschedulesgt-element-bootstrapper"></a>&lt;Planifications&gt; élément (programme d’amorçage)
Le `Schedules` élément contient `Schedule` éléments qui définissent des heures spécifiques commandes définies par le `Command` élément doit être exécuté.

## <a name="syntax"></a>Syntaxe

```xml
<Schedules>
    <Schedule
        Name
    >
        <BuildList />
        <BeforePackage />
        <AfterPackage />
    </Schedule>
</Schedules>
```

## <a name="elements-and-attributes"></a>Éléments et attributs
 Le `Schedules` élément est un enfant de le `Product` élément. Chaque `Product` élément peut avoir au maximum un `Schedules` élément. L’élément `Schedules` ne comporte pas d’attributs.

## <a name="schedule"></a>Planification
 Le `Schedule` élément est un enfant de le `Schedules` élément. Un `Schedules` élément doit avoir au moins un `Schedule` élément.

 `Schedule` a l’attribut suivant.

|Attribut|Description|
|---------------|-----------------|
|`Name`|Obligatoire. Le nom de l’élément de planification. Cela correspond à la `ScheduleName` propriété de la `Command` élément. Quand un `Command` fait référence à la planification nommée, elle est exécutée uniquement à l’heure indiquée par cette `Schedule` élément. Les planifications peuvent également être associées la `FailIf` et `BypassIf` éléments, qui limitent ces tests conditionnels visant l’exécution à la planification spécifiée. Pour plus d’informations, consultez [ \<commandes > élément](../deployment/commands-element-bootstrapper.md).|

 A compte tenu de `Schedule` élément peut-être posséder exactement un des enfants suivants.

## <a name="buildlist"></a>BuildList
 Le `BuildList` élément indique le programme d’installation pour exécuter une commande immédiatement après le démarrage de l’application d’amorçage.

## <a name="beforepackage"></a>BeforePackage
 Le `BeforePackage` élément indique le programme d’installation pour exécuter une commande avant l’installation du package spécifié.

## <a name="afterpackage"></a>AfterPackage
 Le `AfterPackage` élément indique le programme d’installation pour exécuter une commande après avoir installé le package spécifié.

## <a name="see-also"></a>Voir aussi
- [\<Produit > élément](../deployment/product-element-bootstrapper.md)
- [Informations de référence sur le schéma de produit et de package](../deployment/product-and-package-schema-reference.md)