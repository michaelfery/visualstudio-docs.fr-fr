---
title: Ajout de projet et modèles d’élément de projet | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], adding
- project items [Visual Studio], adding
ms.assetid: 8c59217f-56e5-4540-a73b-cd10de189373
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4b68c9f4bbaed73603c46fc0beab77a308b8933d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58951680"
---
# <a name="adding-project-and-project-item-templates"></a>Ajout d’un projet et de modèles d’élément de projet
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Lorsque vous créez vos propres types de projet, vous devez fournir la prise en charge pour l’ajout de nouveaux projets et éléments de projet à l’aide de la norme [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] intégrées des boîtes de dialogue de l’environnement (IDE) de développement. Les rubriques suivantes traitent des différentes techniques pour l’ajout de projets et éléments de projet.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Contexte de projet](../../extensibility/internals/project-context.md)  
 Explique que le projet fournit la plupart des informations de contexte pour ce qui se passe réellement dans l’environnement.  
  
 [Priorité de projet](../../extensibility/internals/project-priority.md)  
 Explique qu’un élément de projet est généralement un membre d’un projet pour aider à éviter toute ambiguïté sur lequel le projet est utilisé pour ouvrir l’élément.  
  
 [Projet Fichiers divers](../../extensibility/internals/miscellaneous-files-project.md)  
 Fournit des informations sur les deux types d’éditeurs qui peuvent être utilisées pour ouvrir des fichiers dans un projet et le rôle de la lecture du projet pour déterminer quel éditeur à utiliser lors de l’ouverture d’un élément de projet.  
  
 [Inscription de modèles de projet et d’élément](../../extensibility/internals/registering-project-and-item-templates.md)  
 Explique ce qui se produit lorsqu’un [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] projet est créé.  
  
 [Ajout d’éléments aux boîtes de dialogue Ajouter un élément](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)  
 Explique le processus d’ajout d’éléments à la **ajouter un nouvel élément** boîte de dialogue.  
  
 [Ajout de répertoires à la boîte de dialogue Nouveau projet](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)  
 Fournit un exemple de l’inscription d’un répertoire qui contient les modèles personnalisés mis à disposition par un VSPackage.  
  
 [Ajout de répertoires à la boîte de dialogue Ajouter un élément](../../extensibility/internals/adding-directories-to-the-add-new-item-dialog-box.md)  
 Fournit un exemple de l’inscription d’un nouvel ensemble de répertoires pour les **ajouter un nouvel élément** boîte de dialogue.  
  
 [Commandes définies par l’IDE pour l’extension des systèmes de projet](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)  
 Répertorie les différents types d’éléments de commande utilisés pour l’extension des systèmes de projet.  
  
 [CATID des objets qui sont généralement utilisés pour étendre des projets](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)  
 Répertorie le CATID pour les objets qui sont utilisés pour étendre [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)], [!INCLUDE[csprcs](../../includes/csprcs-md.md)], et [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] systèmes de projet.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [Guide pratique pour Ouvrez éditeurs spécifiques du projet](../../extensibility/how-to-open-project-specific-editors.md)  
 Fournit des instructions détaillées pour l’ouverture d’un élément intrinsèquement lié à un éditeur spécifique pour un projet.  
  
 [Guide pratique pour Ouvrir des éditeurs Standard](../../extensibility/how-to-open-standard-editors.md)  
 Fournit des instructions détaillées pour l’ouverture d’un éditeur standard.  
  
 [Sous-types de projets](../../extensibility/internals/project-subtypes.md)  
 Fournit des liens vers des rubriques conceptuelles de sous-type de projet. Étendent les sous-types de projet existant [!INCLUDE[csprcs](../../includes/csprcs-md.md)] et [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] projets.  
  
 [Types de projets](../../extensibility/internals/project-types.md)  
 Fournit des liens vers des rubriques supplémentaires qui offrent des informations sur la façon de concevoir de nouveaux types de projet.
