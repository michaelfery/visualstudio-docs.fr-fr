---
title: À l’intérieur de l’éditeur principal | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - core editor
ms.assetid: 8265f31c-c45b-4858-882c-6d9f1e3b9083
caps.latest.revision: 22
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a2d9ec83c700f9166dc6b73860547bcacd265a15
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47501471"
---
# <a name="inside-the-core-editor"></a>À l’intérieur de l’éditeur principal
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [à l’intérieur de l’éditeur principal](https://docs.microsoft.com/visualstudio/extensibility/inside-the-core-editor).  
  
Le [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] éditeur principal est un ensemble de plusieurs composants qui vous permettent de modifier et interroger des informations textuelles. Si vous avez personnalisé l’éditeur principal à l’aide de l’API héritée, vous pouvez continuer à utiliser ces personnalisations, qui seront acheminées via les adaptateurs d’éditeur. Il est recommandé, cependant, que vous deviez adapter vos personnalisations vers le nouvel éditeur API.  
  
 Les domaines suivants sont des aspects importants de l’éditeur principal :  
  
-   Mémoire tampon de texte  
  
-   Affichage de texte  
  
-   Fenêtre Code  
  
-   Marqueurs de texte  
  
-   Gestionnaire de texte  
  
-   Intégration avec les services de langage  
  
## <a name="in-this-section"></a>Dans cette section  
 [Instanciation de l’éditeur de base à l’aide de l’API héritée](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)  
 Fournit des instructions détaillées sur l’utilisation <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> pour créer une instance de la base éditeur.  
  
 [Accès à la mémoire tampon de texte à l’aide de l’API héritée](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)  
 Décrit le rôle de la mémoire tampon de texte dans l’éditeur principal, explique les systèmes associés qui sont utilisés pour accéder à la mémoire tampon et fournit une liste des interfaces implémentées par l’objet de mémoire tampon de texte, <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>.  
  
 [Événements de mémoire tampon de texte dans l’API héritée](../extensibility/text-buffer-events-in-the-legacy-api.md)  
 Fournit une liste des interfaces qui sont utilisées pour la notification des événements de mémoire tampon de texte.  
  
 [Guide pratique pour s’inscrire aux événements de mémoire tampon de texte avec l’API héritée](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md)  
 Décrit comment signaler les événements de mémoire tampon de texte.  
  
 [Utilisation du gestionnaire de texte pour superviser les paramètres globaux](../extensibility/using-the-text-manager-to-monitor-global-settings.md)  
 Explique comment le Gestionnaire de texte permet de partager des informations de préférence global avec les principaux composants de l’éditeur et à recevoir des notifications d’événements du Gestionnaire de texte.  
  
 [Accès au mode texte à l’aide de l’API héritée](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)  
 Décrit le rôle de la vue de texte dans l’éditeur principal et répertorie les interfaces implémentées par le <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> objet.  
  
 [Personnalisation des fenêtres Code à l’aide de l’API héritée](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)  
 Fournit des informations sur comment une fenêtre de code est utilisée pour encadrer l’affichage de texte, explique comment le Gestionnaire de fenêtres de code sert à fournir des ornements à la fenêtre de code et fournit une notification de nouveaux affichages.  
  
 [Modification des paramètres d’affichage à l’aide de l’API héritée](../extensibility/changing-view-settings-by-using-the-legacy-api.md)  
 Fournit des instructions détaillées sur comment forcer les paramètres d’affichage et suppression des paramètres forcés.  
  
 [Services de langage et éditeur de base](../extensibility/language-services-and-the-core-editor.md)  
 Décrit l’instanciation d’un service de langage pour les ornements de code de contrôle.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [Procédure pas à pas : création d’un éditeur de base et inscription d’un type de fichier d’éditeur](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)  
 Fournit des instructions détaillées sur la façon de démarrer l’éditeur principal à partir du code managé.  
  
 [Barre déroulante](../extensibility/drop-down-bar.md)  
 Explique comment la barre déroulante est utilisée dans la fenêtre de code et décrit les interfaces qui sont utilisées lorsque vous implémentez une barre déroulante.  
  
 [Utilisation de marqueurs de texte avec l’API héritée](../extensibility/using-text-markers-with-the-legacy-api.md)  
 Explique le concept des marqueurs de texte et comment elles sont utilisées dans l’éditeur principal et répertorie les interfaces qui sont utilisées pour accéder et gérer des marqueurs de texte.  
  
 [Guide pratique pour ajouter des marqueurs de texte standard](../extensibility/how-to-add-standard-text-markers.md)  
 Fournit des instructions détaillées sur la création d’un marqueur de texte et comment ajouter une commande personnalisée à un menu contextuel.  
  
 [Guide pratique pour créer des marqueurs de texte personnalisés](../extensibility/how-to-create-custom-text-markers.md)  
 Fournit des instructions détaillées sur la création d’un marqueur de texte personnalisé et comment fournir le type de marqueur en tant que service.
