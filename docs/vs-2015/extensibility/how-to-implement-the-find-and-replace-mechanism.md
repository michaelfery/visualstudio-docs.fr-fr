---
title: 'Procédure : Implémenter la rechercher et remplacer le mécanisme | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - find and replace
ms.assetid: bbd348db-3d19-42eb-99a2-3e808528c0ca
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a42df69a7c51b7eb7ef44cf137d8449cf1421ae2
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58951474"
---
# <a name="how-to-implement-the-find-and-replace-mechanism"></a>Procédure : Implémenter la rechercher et remplacer le mécanisme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio fournit deux méthodes d’implémentation de rechercher/remplacer. Une façon consiste à passer d’une image de texte à l’interpréteur de commandes et qu’il traite de la recherche, la mise en surbrillance et le texte en remplaçant. Cela permet aux utilisateurs de spécifier plusieurs étendues de texte. Vous pouvez également votre VSPackage peut contrôler cette fonctionnalité lui-même. Dans les deux cas, vous devez informer l’interpréteur de commandes sur la cible actuelle et les cibles pour tous les documents ouverts.  
  
### <a name="to-implement-findreplace"></a>Pour implémenter les rechercher/remplacer.  
  
1.  Implémentez le <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget> interface sur l’un des objets retournés par les propriétés de frame <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID> ou <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>. Si vous créez un éditeur personnalisé, vous devez implémenter cette interface dans le cadre de la classe d’éditeur personnalisé.  
  
2.  Utilisez le <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetCapabilities%2A> méthode pour spécifier les options qui prend en charge de votre éditeur et pour indiquer si elle implémente la recherche de texte image.  
  
     Si votre éditeur prend en charge la recherche de texte image, implémenter <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>.  
  
     Sinon, implémenter <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> et <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>.  
  
3.  Si vous implémentez le <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> et <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A> méthodes, vous pouvez simplifier vos tâches de recherche en appelant le <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper> interface.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>
