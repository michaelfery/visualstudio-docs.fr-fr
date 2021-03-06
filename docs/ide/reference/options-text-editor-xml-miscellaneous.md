---
title: Options, Éditeur de texte, XML, Divers
ms.date: 10/29/2018
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XML.Miscellaneous
ms.assetid: b6538cbe-badd-4313-a1fb-39e906736bbe
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d3421580251a6a871adba311fd609e881e088ebd
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57525080"
---
# <a name="options-text-editor-xml-miscellaneous"></a>Options, Éditeur de texte, XML, Divers

Utilisez la page d’options **Divers** pour modifier les paramètres de saisie semi-automatique et de schéma pour l’éditeur XML. Pour accéder aux options XML diverses, choisissez **Outils** > **Options** > **Éditeur de texte** > **XML**, puis **Divers**.

## <a name="auto-insert"></a>Insertion automatique

**Balises de fermeture**

L’éditeur de texte ajoute des balises de fermeture lors de la création des éléments XML. Si une balise de début d’un élément est sélectionnée, l’éditeur insère la balise de fermeture correspondante, avec un préfixe d’espace de noms correspondant. Elle est activée par défaut.

**Guillemets d’attribut**

Quand vous créez des attributs XML, l’éditeur insère les caractères `="` et `"`, et place le caret (**^**) à l’intérieur des guillemets doubles. Elle est activée par défaut.

**Déclarations d’espaces de noms**

L'éditeur insère automatiquement des déclarations d'espaces de noms chaque fois qu'elles sont nécessaires. Elle est activée par défaut.

**Autre balisage (commentaires, CDATA)**

Les commentaires, CDATA, DOCTYPE, les instructions de traitement et les autres éléments de balisages sont complétés automatiquement. Elle est activée par défaut.

## <a name="network"></a>Réseau

**Télécharger automatiquement les DTD et les schémas**

Les schémas et les DTD (définitions de type de document) sont automatiquement téléchargés à partir d'emplacements HTTP. Cette fonctionnalité utilise System.Net avec la détection automatique de serveur proxy activée. Elle est activée par défaut.

## <a name="outlining"></a>mode Plan

**Passer en mode Plan à l’ouverture des fichiers**

Active le mode plan à l'ouverture d'un fichier. Elle est activée par défaut.

## <a name="caching"></a>Mise en cache

**Schémas**

Spécifie l'emplacement du cache de schéma. Le bouton **Parcourir** permet d’ouvrir l’emplacement du cache de schéma actuel dans une nouvelle fenêtre. L’emplacement par défaut est *%VsInstallDir%\xml\Schemas*.

## <a name="see-also"></a>Voir aussi

- [Options XML - Mise en forme](options-text-editor-xml-formatting.md)
- [Outils XML dans Visual Studio](../../xml-tools/xml-tools-in-visual-studio.md)