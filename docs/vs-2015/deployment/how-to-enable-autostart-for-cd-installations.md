---
title: 'Procédure : Activer le démarrage automatique pour les Installations de CD | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, AutoStart
- ClickOnce deployment, installation on CD or DVD
- deploying applications [ClickOnce], installation on CD or DVD
ms.assetid: caaec619-900c-4790-90e3-8c91f5347635
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6266f487e2e0c66e532297c3fdae3fd3e5498052
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58950500"
---
# <a name="how-to-enable-autostart-for-cd-installations"></a>Procédure : Activer le démarrage automatique pour les installations depuis un CD-ROM
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Lorsque vous déployez un [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] application au moyen de supports amovibles tels que des CD-ROM ou DVD-ROM, vous pouvez activer `AutoStart` afin que le [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] application est lancée automatiquement lorsque le média est inséré.  
  
 `AutoStart` peut être activé sur le **publier** page de la **Concepteur de projet**.  
  
### <a name="to-enable-autostart"></a>Pour activer le démarrage automatique  
  
1.  Après avoir sélectionné un projet dans l’ **Explorateur de solutions**, dans le menu **Projet** , cliquez sur **Propriétés**.  
  
2.  Cliquez sur l’onglet **Publier**.  
  
3.  Cliquez sur le bouton **Options**.  
  
     Le **Options de publication** boîte de dialogue s’affiche.  
  
4.  Cliquez sur **déploiement**.  
  
5.  Sélectionnez le **installations pour CD-ROM, démarrer automatiquement l’installation lorsque le CD est inséré** case à cocher.  
  
     Un fichier Autorun.inf sera copié à l’emplacement de publication lorsque l’application est publiée.  
  
## <a name="see-also"></a>Voir aussi  
 [Publication d’applications ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Guide pratique pour publier une application ClickOnce à l’aide de l’Assistant Publication](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
