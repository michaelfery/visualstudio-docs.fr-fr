---
title: Options, Éditeur de texte, Basic (VB), Avancé
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Visual_Basic.Editor
- VS.ToolsOptionsPages.Text_Editor.Basic.Editor
- VS.ToolsOptionsPages.Visual_Basic_Editor.Editor
- VS.ToolsOptionsPages.Text_Editor.Basic.SimplifiedEditorPage
- VS.ToolsOptionsPages.Text_Editor.Basic
- VS.ToolsOptionsPages.Text_Editor.Basic.Advanced
- VS.ToolsOptionsPages.Text_Editor.Basic.VB_Specific
helpviewer_keywords:
- Basic Text Editor Options dialog box
ms.assetid: 5a8cafca-f7b4-4a2d-92ce-6894a7673d00
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8a7ea9c2efd6a204932e24de0ef250ba143b8b34
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55925460"
---
# <a name="options-text-editor-basic-visual-basic-advanced"></a>Option, Éditeur de texte, Basic (Visual Basic), Avancé
La page de propriétés **Spécifique à VB**, accessible par le biais du menu **Outils**, dans la boîte de dialogue **Options**, puis dans le dossier **Éditeur de texte** et son dossier **De base**, contient les propriétés suivantes :

## <a name="analysis"></a>Analyse

- Activer l’analyse complète de la solution

   Active l’analyse du code sur tous les fichiers dans la solution, pas simplement les fichiers de code ouverts. Pour plus d’informations, consultez [Analyse complète de la solution](../../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md).

## <a name="using-directives"></a>Directives Using

- Placer les directives « System » en premier lors du tri des usings

   Quand elle est sélectionnée, la commande **Supprimer et trier les instructions using** du menu contextuel trie les directives `using` et place les espaces de noms « System » en haut de la liste.

- Séparer les groupes de directives using

   La commande **Supprimer et trier les instructions using** du menu contextuel sépare les directives `using` en insérant une ligne vide entre les groupes de directives qui ont le même espace de noms racine.

- Suggérer des usings pour les types dans les assemblys de référence
- Suggérer des usings pour les types dans les packages NuGet

   Quand ces options sont sélectionnées, une [Action rapide](../quick-actions.md) est disponible pour installer un package NuGet et ajouter une directive `using` pour les types non référencés.

   ![Action rapide pour installer un package NuGet dans Visual Studio](media/nuget-lightbulb.png)


## <a name="highlighting"></a>Highlighting

 **Activer la mise en surbrillance des références et des mots clés**

L’éditeur de texte peut mettre en surbrillance toutes les instances d’un symbole ou tous les mots clés dans une clause, par exemple `If..Then`, `While...End While` ou `Try...Catch...Finally`. Vous pouvez naviguer entre les références ou les mots clés surlignés en appuyant sur **Ctrl** + **Maj** + **Flèche vers le bas** ou **Ctrl** + **Maj** + **Flèche vers le haut**.

## <a name="outlining"></a>mode Plan

**Activer le mode Plan**

Quand vous ouvrez un fichier dans l’éditeur de code, vous pouvez afficher le document en mode Plan. Pour plus d’informations, consultez [Mode Plan](../../ide/outlining.md). Quand cette option est sélectionnée, la fonctionnalité mode Plan est activée à l’ouverture d’un fichier.

**Afficher les séparateurs de ligne de procédure**

L’éditeur de texte indique la portée visuelle des procédures. Une ligne est tracée dans les fichiers sources *.vb* de votre projet, aux emplacements présentés dans le tableau suivant :

|Emplacement dans le fichier source .vb|Exemple d’emplacement de la ligne|
|---------------------------------|------------------------------|
|Après la fermeture d’une construction de déclaration de bloc|-   À la fin d’une classe, d’une structure, d’un module, d’une interface ou d’un enum<br />-   Après une propriété, une fonction ou un sub<br />-   Pas entre les clauses get et set d’une propriété|
|Après un ensemble de constructions de lignes uniques|-   Après les instructions import, avant une définition de type dans un fichier de classe<br />-   Après les variables déclarées dans une classe, avant toute procédure|
|Après les déclarations de lignes uniques (déclarations pas au niveau des blocs)|-   À la suite des instructions import et inherits, des déclarations de variables, des déclarations event et delegate, et des instructions declare de DLL|

## <a name="block-structure-guides"></a>Repères de structure de bloc

Quand cette option est sélectionnée, des lignes verticales alignées avec les blocs de code structurés sont affichées dans l’éditeur, ce qui vous permet d’identifier facilement les différents blocs de code. Par exemple, vous voyez une ligne entre `Sub` et `EndSub` dans une instruction `Sub`.

## <a name="editor-help"></a>Aide de l'éditeur

**Listing en mode Pretty (remise en forme) du code** L’éditeur de texte remet en forme votre code comme il convient. Quand cette option est sélectionnée, l’éditeur de code effectue les opérations suivantes :

-   Aligner votre code sur la tabulation correcte

-   Appliquer la casse correcte aux mots clés, variables et objets

-   Ajouter un élément `Then` manquant à une instruction `If...Then`

-   Ajouter des parenthèses aux appels de fonctions

-   Ajouter les guillemets fermants manquants aux chaînes

-   Remettre en forme la notation exponentielle

-   Remettre en forme les dates

**Insertion automatique des constructions de fin**

Par exemple, quand vous tapez la première ligne d’une déclaration de procédure, `Sub Main`, et que vous appuyez sur **Entrée**, l’éditeur de texte ajoute une ligne `End Sub` correspondante. De même, si vous ajoutez une boucle [For](/dotnet/visual-basic/language-reference/statements/for-next-statement), l’éditeur de texte ajoute une instruction `Next` correspondante. Quand cette option est sélectionnée, l’éditeur de code ajoute automatiquement la construction de fin.

**Insertion automatique des membres Interface et MustOverride**

Quand vous validez une instruction `Implements` ou `Inherits` pour une classe, l’éditeur de texte insère des prototypes pour les membres qui doivent être implémentés ou substitués, respectivement.

**Activer les suggestions de correction d’erreurs**

L’éditeur de texte peut suggérer des solutions aux erreurs courantes et vous permettre de sélectionner la correction appropriée, qui est appliquée ensuite à votre code.

## <a name="see-also"></a>Voir aussi

- [Général, Environnement, boîte de dialogue Options](../../ide/reference/general-environment-options-dialog-box.md)
- [Options, Éditeur de texte, Tous les langages, Onglets](../../ide/reference/options-text-editor-all-languages-tabs.md)
