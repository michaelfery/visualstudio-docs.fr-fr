---
title: Propriétés d’éléments des diagrammes de composants UML | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
f1_keywords:
- vs.teamarch.componentdiagram.shapes.properties
helpviewer_keywords:
- component diagrams, properties
- UML, element properties
ms.assetid: fa0a9460-6675-4642-aa00-50f8719a892d
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f5fc99de05ef040db8c4560f9f6623081018a556
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58951401"
---
# <a name="properties-of-elements-on-uml-component-diagrams"></a>Propriétés des éléments dans les diagrammes de composants UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dans un diagramme de composant UML, chaque élément du diagramme possède des propriétés. Pour afficher les propriétés d’un élément, cliquez sur l’élément sur le diagramme ou dans **Explorateur de modèles UML** puis cliquez sur **propriétés**. Les propriétés s’affichent dans le **propriétés** fenêtre.  
  
> [!NOTE]
>  Cette rubrique traite des propriétés d'éléments dans les diagrammes de composants UML. Pour plus d’informations sur la lecture des diagrammes de composants UML, consultez [diagrammes de composants UML : Référence](../modeling/uml-component-diagrams-reference.md). Pour plus d’informations sur la façon de dessiner des diagrammes de composants UML, consultez [diagrammes de composants UML : Les instructions](../modeling/uml-component-diagrams-guidelines.md).  
  
## <a name="properties-of-elements"></a>Propriétés des éléments  
  
|Propriété|Par défaut|Élément|Description|  
|--------------|-------------|-------------|-----------------|  
|**Name**|Nom par défaut|Tous|Identifie l'élément.|  
|**Nom qualifié**|Namespace :: Nom|Tous|Identifie l'élément de manière unique.<br /><br /> Le nom d'un composant ou d'un type a pour préfixe le nom qualifié du package qui le contient.<br /><br /> Le nom d'une partie ou d'un port a pour préfixe le nom qualifié du composant qui le possède.|  
|**Éléments de travail**|{0} associé|Tous|Nombre d'éléments de travail associés à cet élément. Pour associer des éléments de travail, consultez [lier des éléments de modèle et des éléments de travail](../modeling/link-model-elements-and-work-items.md).|  
|**Description**|(aucune)|Tous|Vous pouvez consigner des remarques générales concernant l'élément.|  
|**Color**|(valeur par défaut pour le type)|Composant, élément, délégation, assembly d'élément|Couleur de la forme. Contrairement aux autres propriétés, c'est la couleur de la forme plutôt que l'élément de modèle que la forme affiche.|  
|**Is Indirectly Instantiated**|True|Composant|Le composant existe uniquement en tant qu'un artefact de conception. Au moment de l'exécution, seuls ses éléments existent.|  
|**Est abstrait**|False|Composant|La définition du composant peut être utilisée uniquement comme une généralisation à partir de laquelle d'autres composants peuvent être spécialisés.|  
|**Visibilité**|Public|Composant, élément, port|**Public** : visible globalement.<br /><br /> **Package** : visible dans le package.<br /><br /> **Privé** : visible dans le composant propriétaire.<br /><br /> **Protégé** : visible aux composants dérivés du propriétaire.|  
|**Type**|Type à la création|Élément<br /><br /> Port|Le type d'un élément est un composant ou une classe.<br /><br /> Le type d'un port est une interface.|  
|**Multiplicité**|1|Élément<br /><br /> Port|Indique le nombre d'instances du type spécifié faisant partie du composant parent.<br /><br /> `1` : exactement un.<br /><br /> `0..1` : un ou aucun.<br /><br /> `*` : collection d'un nombre quelconque.<br /><br /> `n..m` : collection d'instances de n à m.|  
|**Est le comportement**|False|Port|Si la valeur est True, les messages envoyés à ce port sont contrôlés par des activités ou des opérations qui sont décrites dans le cadre du composant, et non dans ses éléments.|  
|**Est le Service**|False|Port|Si la valeur est True, ce port fait partie de l'interface publiée de ce composant.|  
|**LinkedPackage**|Modèle|Diagramme|Espace de noms par défaut pour les éléments ajoutés à ce diagramme.|  
  
## <a name="see-also"></a>Voir aussi  
 [Diagrammes de cas d’usage UML : Référence](../modeling/uml-use-case-diagrams-reference.md)   
 [Diagrammes de cas d’usage UML : Recommandations](../modeling/uml-use-case-diagrams-guidelines.md)
