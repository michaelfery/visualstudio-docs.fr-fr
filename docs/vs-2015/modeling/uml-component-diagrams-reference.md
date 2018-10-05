---
title: 'Diagrammes de composants UML : Référence | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.teamarch.componentdiagram.diagram
- vs.teamarch.componentdiagram.toolbox
- vs.teamarch.UMLModelExplorer.componentdiagram
helpviewer_keywords:
- UML diagrams, component
- diagrams - modeling, component
- diagrams - modeling, UML component
- UML, component diagrams
- component diagrams
ms.assetid: 5eddff6a-892a-4c3c-9278-687ac1eccc50
caps.latest.revision: 38
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: f628ebfa84246c6d991543352f4de36a51cc7fbf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47507268"
---
# <a name="uml-component-diagrams-reference"></a>Diagrammes de composants UML : référence
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [diagrammes de composants UML : référence](https://docs.microsoft.com/visualstudio/modeling/uml-component-diagrams-reference).  
  
Dans Visual Studio, un *diagramme de composant* montre les parties d’une conception pour un système logiciel. Un diagramme de composant vous aide à visualiser la structure globale du système et le comportement de service que ces parties fournissent et consomment via des interfaces. Pour créer un diagramme de composant UML, dans le **Architecture** menu, cliquez sur **nouveau UML ou diagramme de couche**.  
  
 Pour connaître les versions de Visual Studio qui prennent en charge cette fonctionnalité, consultez [Prise en charge des versions pour les outils d'architecture et de modélisation](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Vous pouvez utiliser un diagramme de composant pour décrire une conception implémentée dans n'importe quel langage ou style. Il est uniquement nécessaire d'identifier les parties de la conception qui interagissent avec d'autres parties de la conception via un ensemble restreint d'entrées et de sorties. L'échelle des composants importe peu et ceux-ci peuvent être interconnectés de n'importe quelle manière.  
  
 Pour plus d’informations sur l’utilisation des diagrammes de composants en cours de conception, consultez [modéliser l’architecture de votre application](../modeling/model-your-app-s-architecture.md).  
  
> [!NOTE]
>  Cette rubrique décrit les éléments que vous pouvez utiliser dans les diagrammes de composants. Pour plus d’informations sur la façon de dessiner des diagrammes de composants, consultez [diagrammes de composants UML : indications](../modeling/uml-component-diagrams-guidelines.md). Pour plus d’informations sur la façon de dessiner des diagrammes de modélisation en général, consultez [modèles et diagrammes UML modifier](../modeling/edit-uml-models-and-diagrams.md).  
  
## <a name="reading-component-diagrams"></a>Lecture de diagrammes de composants  
 Le tableau suivant décrit les éléments que vous pouvez utiliser sur un diagramme de composant, ainsi que leurs principales propriétés. Pour obtenir une liste complète des propriétés des éléments, consultez [propriétés d’éléments des diagrammes de composants UML](../modeling/properties-of-elements-on-uml-component-diagrams.md).  
  
 ![Éléments utilisés sur les diagrammes de composants](../modeling/media/uml-compovreading.png "UML_CompOvReading")  
  
|**Forme**|**Élément**|**Description et principales propriétés**|  
|---------------|-----------------|-----------------------------------------|  
|1|**Composant**|Partie réutilisable de fonctionnalité système. Un composant fournit et consomme un comportement via des interfaces et il peut utiliser d'autres composants.<br /><br /> Vous pouvez masquer ou afficher les éléments internes d'un composant à l'aide du contrôle de développement/réduction (9).<br /><br /> Un composant est un genre de classe.<br /><br /> -   **Is Indirectly Instantiated**. Si la valeur est true, le composant existe uniquement en tant qu'artefact de conception. Au moment de l'exécution, seules ses parties existent.|  
|2|**Port d’Interface fourni**|Représente un groupe de messages ou d'appels qu'un composant implémente et que d'autres composants ou systèmes externes peuvent utiliser. Un port est une propriété d'un composant qui a une interface comme type.|  
|3|**Port d’Interface requis**|Représente un groupe de messages ou d'appels que le composant envoie à d'autres composants ou systèmes externes. Le composant est conçu pour être couplé à des composants qui fournissent au moins ces opérations. Le port a une interface comme type.|  
|4|**dépendance**|Peut être utilisé pour indiquer qu'une Interface requise sur un composant peut être satisfaite par une Interface fournie sur un autre.<br /><br /> Vous pouvez aussi utiliser des dépendances de manière plus générale entre des éléments de modèle, pour montrer qu'une conception de l'un dépend de la conception de l'autre.|  
|5|**Partie**|Attribut d'un composant, dont le type est généralement un autre composant. Une partie est utilisée dans la conception interne de son composant parent. Les parties sont affichées graphiquement, imbriquées dans le composant parent.<br /><br /> Pour créer une partie d'un type de composant existant, faites glisser le composant de l'Explorateur de modèles UML vers le composant propriétaire.<br /><br /> Pour créer une partie d’un nouveau type, cliquez sur le **composant** outil, puis cliquez sur le composant propriétaire.<br /><br /> Par exemple, un composant `Car` a des parties `engine:CarEngine`, `backLeft:Wheel`, `frontRight:Wheel`, et ainsi de suite.<br /><br /> Plusieurs parties peuvent avoir le même type et différents composants peuvent avoir des parties du même type.<br /><br /> -   **Type**. Type de la partie, qui est défini ailleurs dans le modèle. En règle générale, le type est un autre composant.<br />-   **Multiplicité**. La valeur par défaut est 1. Vous pouvez le définir sur **valeur 0.. 1** pour indiquer que la partie peut avoir la valeur **null**, **\*** pour indiquer que la partie est une collection d’instances du type donné, ou Pour toute expression qui peut être évaluée à une plage de nombres.|  
|6|**Assembly d’élément**|Connexion entre les ports d'interfaces requises d'une partie et les ports d'interfaces fournies d'une autre. L'implémentation d'un assembly de partie peut varier d'un composant à un autre. Les parties connectées doivent avoir le même composant parent.|  
|7|**Délégation**|Lie un port à une interface de l'une des parties du composant. Indique que les messages envoyés au composant sont traités par la partie ou que les messages envoyés par la partie sont envoyés à partir du composant parent.|  
|(non affiché)|**Généralisation**|Indique qu'un composant hérite d'un autre composant. Les parties et les interfaces sont héritées.|  
|9|Contrôle Réduire/Développer|Permet de masquer ou d'afficher les parties internes d'un composant.|  
|(non affiché)|**Commentaire**|Pour des remarques supplémentaires. Vous pouvez lier un commentaire à n’importe quel nombre d’éléments dans le diagramme à l’aide de la **connecteur** outil.|  
  
## <a name="see-also"></a>Voir aussi  
 [Modifier des modèles UML et des diagrammes](../modeling/edit-uml-models-and-diagrams.md)   
 [Diagrammes de composants UML : indications](../modeling/uml-component-diagrams-guidelines.md)   
 [Valider votre système pendant le développement](../modeling/validate-your-system-during-development.md)   
 [Diagrammes de cas d’usage UML : référence](../modeling/uml-use-case-diagrams-reference.md)   
 [Diagrammes de classes UML : référence](../modeling/uml-class-diagrams-reference.md)   
 [Diagrammes d’activités UML : référence](../modeling/uml-activity-diagrams-reference.md)   
 [Informations de référence sur les diagrammes de séquence UML](../modeling/uml-sequence-diagrams-reference.md)


