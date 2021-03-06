---
title: Package GUID des fonctionnalités de Visual Studio 2015 | Microsoft Docs
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio shell, isolated mode%2C package GUIDs
ms.assetid: f56f0356-f3ac-48bc-9674-94259e29a4df
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 8601b4f072c206ab19fdcb4a7248e79784af934a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58949920"
---
# <a name="package-guids-of-visual-studio-features"></a>GUID du package de fonctionnalités de Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez utiliser les GUID suivants dans le fichier .pkgundef de votre application de shell isolé à exclure des packages spécifiques de l’application.

## <a name="package-guids"></a>GUID du package

|Domaine de fonctionnalités|Nom du Package brutes|GUID du package|
|------------------|----------------------|------------------|
|Core IDE|Annuler le Package|{1D76B2E0-F11B-11D2-AFC3-00105A9991EF}|
||Package d’environnement Visual Studio|{DA9FB551-C724-11d0-AE1F-00A0C90FFFC3}|
||Package de définition de commandes de Visual Studio|{44E07B02-29A5-11D3-B882-00C04F79F802}|
||Package de liste de répertoire de Visual Studio|{5010C52F-44AB-4051-8CE1-D36C20D989B4}|
||Package IDE courantes de Visual Studio|{6E87CFAD-6C05-4ADF-9CD7-3B7943875B7C}|
||Package de Menu environnement Visual Studio|{715F10EB-9E99-11D2-BFC2-00C04F990235}|
||Package du Gestionnaire de bibliothèque Visual Studio COM +|{ED8979BC-B02F-4dA9-A667-D3256C36220A}|
||Package de l’intégration de contrôle de code Source Visual Studio|{53544C4D-E3F8-4AA0-8195-8A8D16019423}|
||Package de Build de Solution Visual Studio|{282BD676-8B5B-11D0-8A34-00A0C91E2ACD}|
||Package de gestion de texte|{F5E7E720-1401-11d1-883B-0000F87579D2}|
||Package de VsSettings Visual Studio|{F74C5077-D848-4630-80C9-B00E68A1CA0C}|
|Help|Package d’aide de Visual Studio|{4A791146-19E4-11D3-B86B-00C04F79F802}|
|Liste des tâches, liste d’erreurs|ErrorListPackage|{4A9B7E50-AA16-11D0-A8C5-00A0C921A4D2}|
|Structure de la classe|Classe structure du Package|{21AF45B0-FFA5-11D0-G63F-00A0C922E851}|
|Programme d’installation des contrôles de boîte à outils|Package de programme d’installation de contrôles de boîte à outils|{2C298B35-07DA-45F1-96A3-BE55D91C8d7A}|
|Projets web|Microsoft.VisualStudio.Web|{349C5850-65DF-11DA-9384-00065B846F21}|
||Package de système de projet Visual Web Developer|{39C9C826-8EF8-4079-8C95-428F5B1C323F}|
||Package de persistance du projet Visual Web Developer|{8FF02D1A-C177-4AC8-A62F-88FC6EA65F57}|
||Package de Migration de Visual Web Developer Web|{C1DAB116-2D63-493A-B970-10D7DD0B476E}|
||Visual Web Developer Web Package|{E7f851C8-6267-4794-B0FE-7BCAB6DACBB4}|
||Visual Web Developer Web|{DC7F691A-91FC-4F7B-923E-FE829C3A18DC}|
|Éditeur HTML|Package de l’éditeur Visual Studio HTM|{1B437D20-F8FE-11D2-A6AE-00104BCC7269}|
||Package de l’éditeur de Source HTML de Visual Web Developer|{BFCC0C3C-6F87-4285-A6C8-BB616061800D}|
|éditeur CSS|Package de modification de CSS de Visual Studio|{A764E895-518D-11d2-9A89-00C04F79EFC3}|
|Éditeur XML|Package de l’éditeur XML de Visual Studio|{87569308-4813-40A0-9CD0-D7A30838CA3F}|
|Navigateur web|Package de navigateur Web de Visual Studio|{E8B06F41-6D01-11D2-AA7D-00C04F990343}|
||Fabrique de projet Application Web, pour afficher les fonctionnalités de navigateur|{349C5851-65DF-11DA-9384-00065B846F21}|
|éditeur binaire|Package de l’éditeur binaire Visual Studio|{5B98C2C0-CD7B-11D0-92DF-00A0C9138C45}|
|Concepteur Windows Forms|Package d’hébergement Concepteur Windows Forms|{68939055-38E0-4D17-92CB-8909710D8178}|
||Package de concepteur Windows Forms|{7494682B-37A0-11D2-A273-00C04F8EF4FF}|
||Package de ressources du Concepteur Windows Forms|{7B5D447B-0B12-41EA-A84E-C822034422D4}|
||Package de Configuration Application Windows Forms|{80C7728B-70A6-4528-8669-73E02D1B9C41}|
||Package du Concepteur de ElementHost|{7EAB3C71-59FF-4571-A5F3-643F255FC2E6}|
|Interface utilisateur du débogueur|Débogueur Visual Studio|{C9DD4A57-47FB-11D2-83E7-00C04F9902C1}|
|Database Tools|Package d’outils de base de données Visual|{220A4C17-7E7C-4663-BBCC-5E607C6543CD}|
||Concepteurs d’outils de base de données de Visual Studio|{EF828E39-70F5-4b8e-A3A0-4C0ECD28A69A}|
||Concepteurs de données Visual Studio|{D6C919AA-1217-41E2-a13B-9B92E1866305}|
||Package de données de Visual Studio|{E1AA7737-69BE-43d0-A425-E3097651E192}|
||Package d’extensibilité du Concepteur de données de Visual Studio|{A8F602E2-40CE-4dAF-AE82-A457A91728B9}|
||Explorateurs de Visual Studio et les concepteurs Package|{8D8529D3-625D-4496-8354-3DAD630ECC1B}|
||Concepteur de rapports de Microsoft|{F3A96850-E2AE-4E00-9278-8FE23F225A0D}|
|Runtime DSL|CommonModelingPackage|{D1091694-EA72-4BDD-8918-78324CC25448}|
||Microsoft.VisualStudio.TextTemplating|{A9696DE6-E209-414D-BBEC-A0506fb0E924}|
|Prise en charge de SourceSafe|Package de fournisseur de Visual SourceSafe|{AA8EB8CD-7A51-11D0-92C3-00A0C9138C45}|
||Package de Stub de fournisseur de Visual SourceSafe|{53544C4D-B03D-4209-A7D0-D9DD13A4019B}|
|Concepteur WPF|WPFFlavor.WPFPackage|{B3BAE735-386C-4030-8329-EF48EEDA4036}|
||XamlDesignerPackage|{512be089-83ec-4cc6-8483-cf16565ae209}|
||XamlLanguagePackage|{2ef1ec52-c8bf-4fe0-8ece-ba9c0d5d1603}|
||XamlDiagnosticsPackage|{8291c340-36b8-4c91-8c40-cce75398ff75}|
|Extraits de code|Package d’extraits de Code de Visual Studio|{0B680757-2C29-4531-80FA-535A5178AA98}|
|Prise en charge du projet de langage managé|Énumérateur de composant de Visual Studio|{588205E0-66e0-11D3-8600-00C04F6123B3}|
||Paramètres de Visual Studio et Package de concepteurs de projet|{67909B06-91E9-4F3E-AB50-495046BE9A9A}|
|Exporter le modèle...|Exporter un Package de modèle|{F1E4CFCA-4573-4345-8718-7BDE2b1F0BE8}|

 Certains packages ne doivent jamais être supprimés, car de nombreuses autres fonctionnalités prennent de dépendances sur ces derniers. Par exemple, celles répertoriées sous « Core IDE » ne doivent jamais être supprimés.

 Certaines fonctionnalités ne peut pas être complètement supprimées. Par exemple, il n’existe aucun package qui peut être désinscrit pour supprimer **affichage de classes** et ses menus associés, options et les services. Le **affichage de classes** fenêtre est fournie par le Package d’environnement Visual Studio, qui permet également d’autres fonctionnalités clées de l’IDE. Si vous souhaitez supprimer **affichage de classes**, vous devez également supprimer **rechercher et remplacer**, l’environnement **Options** pages, le **la fenêtre de commande**et le **sortie** fenêtre.
