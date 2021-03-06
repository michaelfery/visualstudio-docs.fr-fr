---
title: 'Procédure : Recherchez les mises à jour de l’Application par programmation à l’aide de l’API du déploiement ClickOnce | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, updates
- application updates
ms.assetid: 1a886310-67c8-44e5-a382-c2f0454f887d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ac7a5665b287f51e59d99d21802acc252a55a99a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58952678"
---
# <a name="how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api"></a>Procédure : Recherchez les mises à jour de l’Application par programmation à l’aide de l’API du déploiement ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ClickOnce fournit deux façons de mettre à jour une application après son déploiement. Dans la première méthode, vous pouvez configurer le déploiement ClickOnce pour vérifier automatiquement les mises à jour à intervalles réguliers. Dans la deuxième méthode, vous pouvez écrire du code qui utilise le <xref:System.Deployment.Application.ApplicationDeployment> class à vérifier les mises à jour basée sur un événement, telle qu’une demande utilisateur.  
  
 Les procédures suivantes montrent du code pour effectuer une mise à jour par programme et indiquent également comment configurer votre déploiement de ClickOnce pour activer les vérifications de mise à jour par programmation.  
  
 Pour mettre à jour une application ClickOnce par programme, vous devez spécifier un emplacement pour les mises à jour. Cela est parfois appelé un fournisseur de déploiement. Pour plus d’informations sur la définition de cette propriété, consultez [choix d’une stratégie de mise à jour ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md).  
  
> [!NOTE]
>  Vous pouvez également utiliser la technique décrite ci-dessous pour déployer votre application à partir d’un emplacement, mais mettre à jour à partir d’un autre. Pour plus d'informations, voir [Procédure : Spécifiez un autre emplacement pour le déploiement des mises à jour](../deployment/how-to-specify-an-alternate-location-for-deployment-updates.md).  
  
### <a name="to-check-for-updates-programmatically"></a>Pour vérifier les mises à jour par programmation  
  
1.  Créer une nouvelle application Windows Forms à l’aide de vos outils de ligne de commande ou visual préférés.  
  
2.  Créer le bouton, l’élément de menu, ou autre élément d’interface utilisateur vous souhaitez que vos utilisateurs à sélectionner pour rechercher les mises à jour. À partir du Gestionnaire d’événements de cet élément, appelez la méthode suivante pour vérifier et installer les mises à jour.  
  
     [!code-cpp[ClickOnceAPI#6](../snippets/cpp/VS_Snippets_Winforms/ClickOnceAPI/cpp/form1.cpp#6)]
     [!code-csharp[ClickOnceAPI#6](../snippets/csharp/VS_Snippets_Winforms/ClickOnceAPI/CS/Form1.cs#6)]
     [!code-vb[ClickOnceAPI#6](../snippets/visualbasic/VS_Snippets_Winforms/ClickOnceAPI/VB/Form1.vb#6)]  
  
3.  Compilez votre application.  
  
### <a name="using-mageexe-to-deploy-an-application-that-checks-for-updates-programmatically"></a>À l’aide de Mage.exe pour déployer une application qui vérifie les mises à jour par programmation  
  
-   Suivez les instructions pour le déploiement de votre application à l’aide de Mage.exe comme expliqué dans [procédure pas à pas : déploiement manuel d’une application ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Lorsque vous appelez Mage.exe pour générer le manifeste de déploiement, vérifiez que vous utilisez le commutateur de ligne de commande `providerUrl`et pour spécifier l’URL où ClickOnce doit rechercher des mises à jour. Si votre application met à jour à partir de [ http://www.adatum.com/MyApp ](http://www.adatum.com/MyApp), par exemple, votre appel pour générer le manifeste de déploiement peut ressembler à ceci :  
  
    ```  
    mage -New Deployment -ToFile WindowsFormsApp1.application -Name "My App 1.0" -Version 1.0.0.0 -AppManifest 1.0.0.0\MyApp.manifest -providerUrl http://www.adatum.com/MyApp/MyApp.application  
    ```  
  
### <a name="using-mageuiexe-to-deploy-an-application-that-checks-for-updates-programmatically"></a>À l’aide de MageUI.exe pour déployer une application qui vérifie les mises à jour par programmation  
  
-   Suivez les instructions pour le déploiement de votre application à l’aide de Mage.exe comme expliqué dans [procédure pas à pas : déploiement manuel d’une application ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Sur le **Options de déploiement** onglet, définissez la **Start Location** champ au manifeste d’application ClickOnce doit rechercher des mises à jour. Sur le **les Options de mise à jour** onglet, désactivez le **cette application doit rechercher les mises à jour** case à cocher.  
  
## <a name="net-framework-security"></a>Sécurité .NET Framework  
 Votre application doit avoir des autorisations de confiance totale pour utiliser la mise à jour par programmation.  
  
## <a name="see-also"></a>Voir aussi  
 [Guide pratique pour Spécifiez un autre emplacement pour le déploiement des mises à jour](../deployment/how-to-specify-an-alternate-location-for-deployment-updates.md)   
 [Choix d’une stratégie de mise à jour ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md)   
 [Publication d’applications ClickOnce](../deployment/publishing-clickonce-applications.md)
