---
title: Création d’une Extension avec une fenêtre outil | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: 585b0a3a-f85b-4f92-81bb-9ca499bb8a89
caps.latest.revision: 6
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f07cb45d6b77fc554475558fddba34792c0d8a55
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58949894"
---
# <a name="creating-an-extension-with-a-tool-window"></a>Création d’une extension avec une fenêtre d’outil
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dans cette procédure, vous allez apprendre à utiliser le modèle de projet VSIX et le **fenêtre d’outil personnalisé** modèle d’élément pour créer une extension avec une fenêtre outil.  
  
## <a name="prerequisites"></a>Prérequis  
 À partir de Visual Studio 2015, vous n’installez pas le Kit de développement logiciel Visual Studio à partir du centre de téléchargement. Il est inclus comme fonctionnalité facultative dans le programme d’installation de Visual Studio. Vous pouvez également installer le kit SDK VS par la suite. Pour plus d’informations, consultez [l’installation de Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
### <a name="creating-a-tool-window"></a>Création d’une fenêtre outil  
  
1.  Créez un projet VSIX nommé **FirstWindow**. Vous pouvez trouver le modèle de projet VSIX dans le **nouveau projet** boîte de dialogue sous **Visual C# / extensibilité**.  
  
2.  Quand le projet s’ouvre, ajoutez un modèle d’élément de fenêtre outil nommé **FirstWindow**. Dans le **l’Explorateur de solutions**, cliquez sur le nœud du projet et sélectionnez **Ajouter / nouvel élément**. Dans le **ajouter un nouvel élément** boîte de dialogue, accédez à **Visual C# / extensibilité** et sélectionnez **fenêtre d’outil personnalisé**. Dans le **nom** en bas de la fenêtre, modifiez le nom de fichier de fenêtre outil à **FirstWindow.cs**.  
  
3.  Générez le projet et commencez le débogage.  
  
     L’instance expérimentale de Visual Studio s’affiche. Pour plus d’informations sur l’instance expérimentale, consultez [l’Instance expérimentale](../extensibility/the-experimental-instance.md).  
  
4.  Dans l’instance expérimentale, accédez à **vue / autres Windows**.  
  
     Vous devez voir un élément de menu pour **FirstWindow**. Cliquez dessus.  
  
     Vous devez voir une fenêtre outil avec le titre **FirstWindow** et un message de bouton **Click Me !.**
