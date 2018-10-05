---
title: Prise en charge d’Automation pour les Pages Options | Microsoft Docs
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
- Tools Options pages [Visual Studio SDK], automation support
- automation [Visual Studio SDK], creating Tools Options pages
ms.assetid: 0b25b82c-7432-4e0a-9e84-350269ba8260
caps.latest.revision: 30
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9f7a9a9cf13a50cf13817b4c3b12bd1da1e8370b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47495991"
---
# <a name="automation-support-for-options-pages"></a>Prise en charge de l’automatisation pour les pages Options
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [prise en charge d’Automation pour les Pages Options](https://docs.microsoft.com/visualstudio/extensibility/internals/automation-support-for-options-pages).  
  
VSPackages peut fournir une personnalisée **Options** boîtes de dialogue pour le **outils** menu (pages d’Options Outils) dans [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] et vous pouvez les rendre disponibles pour le modèle automation.  
  
## <a name="tools-options-pages"></a>Pages d’Options Outils  
 Pour créer un **Outils/Options** page, un VSPackage doit fournir une implémentation de contrôle utilisateur retournée à l’environnement via l’implémentation du VSPackage de la <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> (méthode), (ou pour le code managé du <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> méthode).  
  
 Il est facultatif, mais il est vivement recommandé d’autoriser l’accès à cette nouvelle page via le modèle automation. Pour cela, les étapes suivantes :  
  
1.  Étendre la <xref:EnvDTE._DTE.Properties%2A> objet via l’implémentation d’un objet dérivé de IDispatch.  
  
2.  Retourner une implémentation de la <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> (méthode) (ou pour le code managé le <xref:Microsoft.VisualStudio.Shell.Package.GetAutomationObject%2A> méthode) à l’objet dérivé de IDispatch.  
  
3.  Lorsqu’un utilisateur d’automation appelle le <xref:EnvDTE._DTE.Properties%2A> méthode sur un personnalisé **Option** page de propriétés, l’environnement utilise le <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> méthode pour obtenir un personnalisé **Outils/Options** automation de la page mise en œuvre.  
  
4.  L’objet automation du VSPackage est ensuite utilisé pour fournir chacune <xref:EnvDTE.Property> retourné par <xref:EnvDTE._DTE.Properties%2A>.  
  
 Pour un exemple d’implémentation d’une page Outils/Options personnalisée, consultez [exemples d’extensibilité Visual Studio](../../misc/vssdk-samples.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Exposition des objets de projet](../../extensibility/internals/exposing-project-objects.md)
