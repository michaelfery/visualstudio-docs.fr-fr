---
title: 'Procédure : Publier une Application ClickOnce à l’aide de l’Assistant Publication | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, publishing
- deploying applications [ClickOnce], Publish wizard
- Windows applications, ClickOnce deployments
- publishing, ClickOnce
ms.assetid: 2e4aa67c-4445-4f7b-9e03-9acb95829127
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 45ca2bd23c6da7d86b65cc05c0b0dee670e2718f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58949992"
---
# <a name="how-to-publish-a-clickonce-application-using-the-publish-wizard"></a>Procédure : Publier une application ClickOnce à l’aide de l’Assistant Publication
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pour mettre une application ClickOnce à la disposition des utilisateurs, vous devez la publier sur un partage de fichiers ou un chemin d'accès, un serveur FTP ou un média amovible. Vous pouvez publier cette application à l’aide de l’Assistant Publication. Vous trouverez des propriétés supplémentaires liées à la publication sur la page **Publier** du **Concepteur de projet**. Pour plus d’informations, consultez [publication d’Applications ClickOnce](../deployment/publishing-clickonce-applications.md).  
  
 Avant d'exécuter l'Assistant Publication, vous devez correctement définir les propriétés de publication. Par exemple, vous pouvez spécifier une clé pour signer votre application ClickOnce dans la page **Signature** du **Concepteur de projet**. Pour plus d’informations, consultez [Sécurisation des applications ClickOnce](../deployment/securing-clickonce-applications.md).  
  
> [!NOTE]
>  Quand vous installez plusieurs versions d'une application via ClickOnce, l'installation déplace les versions antérieures de cette application dans un dossier nommé Archive, à l'emplacement de publication que vous avez spécifié. Cet archivage permet d’éviter la présence de dossiers de la version précédente dans le répertoire d’installation.  
  
> [!NOTE]
>  Selon vos paramètres actifs ou votre édition, les boîtes de dialogue et les commandes de menu affichées peuvent différer de celles qui sont décrites dans l'aide. Pour modifier ces paramètres, cliquez sur **Importation et exportation de paramètres** dans le menu **Outils** . Pour plus d’informations, consultez [Personnalisation des paramètres de développement dans Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-publish-to-a-file-share-or-path"></a>Pour publier vers un partage de fichiers ou un chemin d'accès  
  
1. Dans l’**Explorateur de solutions**, sélectionnez le projet d’application.  
  
2. Sur le **Build** menu, cliquez sur **publier**`Projectname`.  
  
    L'Assistant Publication apparaît.  
  
3. Dans la page **Où voulez-vous publier l’application ?**, entrez une adresse de serveur FTP valide ou un chemin de fichier valide dans un des formats indiqués, puis cliquez sur **Suivant**.  
  
4. Dans la page **Comment les utilisateurs installeront-ils l’application ?**, sélectionnez l’emplacement auquel les utilisateurs devront accéder pour installer l’application :  
  
   -   Si les utilisateurs effectuent l’installation à partir d’un site web, cliquez sur **À partir d’un site web**, puis entrez une URL qui correspond au chemin de fichier entré à l’étape précédente. Cliquez sur **Suivant**. (Cette option est généralement utilisée quand vous spécifiez une adresse FTP comme emplacement de publication. Le téléchargement direct à partir de FTP n'est pas pris en charge. Vous devez donc entrer une URL ici.)   
  
   -   Si les utilisateurs installent directement l’application à partir du partage de fichiers, cliquez sur **À partir d’un chemin UNC ou d’un partage de fichiers**, puis cliquez sur **Suivant**. (Il s’agit de la publication des emplacements de la forme c:\deploy\myapp ou \\\server\myapp.)  
  
   -   Si les utilisateurs installent l’application à partir d’un média amovible, cliquez sur **À partir d’un CD-ROM ou DVD-ROM**, puis cliquez sur **Suivant**.  
  
5. Dans la page **L’application sera-t-elle disponible hors connexion ?**, cliquez sur l’option appropriée :  
  
   - Si vous voulez permettre à l’application de s’exécuter quand l’utilisateur est déconnecté du réseau, cliquez sur **Oui, cette application est disponible en ligne ou hors connexion**. Un raccourci est créé dans le menu **Démarrer** pour l’application.  
  
   - Pour exécuter directement l’application depuis l’emplacement de publication, cliquez sur **Non, cette application est uniquement disponible en ligne**. Aucun raccourci n’est alors créé dans le menu **Démarrer**.  
  
     Cliquez sur **Suivant** pour continuer.  
  
6. Cliquez sur **Terminer** pour publier l’application.  
  
    L'état de publication s'affiche dans la zone de notification d'état.  
  
### <a name="to-publish-to-a-cd-rom-or-dvd-rom"></a>Pour publier sur un CD-ROM ou DVD-ROM  
  
1. Dans l’**Explorateur de solutions**, cliquez avec le bouton droit sur le projet d’application, puis cliquez sur **Propriétés**.  
  
    Le **Concepteur de projet** s’affiche.  
  
2. Cliquez sur l’onglet **Publier** pour ouvrir la page **Publier** du **Concepteur de projet**, puis cliquez sur le bouton **Assistant Publication**.  
  
    L'Assistant Publication apparaît.  
  
3. Dans le **où voulez-vous publier l’application ?** , entrez le chemin d’accès de fichier ou l’emplacement de FTP où l’application sera publiée, par exemple d:\deploy. Cliquez ensuite sur **Suivant** pour continuer.  
  
4. Dans la page **Comment les utilisateurs installeront-ils l’application ?**, cliquez sur **À partir d’un CD-ROM ou DVD-ROM**, puis cliquez sur **Suivant**.  
  
   > [!NOTE]
   >  Si vous voulez que l’installation s’exécute automatiquement quand le CD-ROM est inséré dans le lecteur, ouvrez la page **Publier** dans le **Concepteur de projet**, puis cliquez sur le bouton **Options** puis, dans l’Assistant **Options de publication**, sélectionnez **Pour les installations depuis un CD-ROM, démarrer automatiquement l’installation dès l’insertion du CD-ROM**.  
  
5. Si vous distribuez votre application sur CD-ROM, vous souhaitez peut-être fournir des mises à jour à partir d'un site web. Dans la page **Où l’application doit-elle vérifier la disponibilité de mises à jour ?**, choisissez une option de mise à jour :  
  
   - Si l’application doit vérifier les mises à jour, cliquez sur **L’application va vérifier la disponibilité de mises à jour à partir de l’emplacement suivant**, puis entrez l’emplacement où les mises à jour seront publiées. Il peut s'agir d'un emplacement de fichier, d'un site web ou d'un serveur FTP.  
  
   - Si l’application ne doit pas vérifier les mises à jour, cliquez sur **L’application ne vérifiera pas la disponibilité de mises à jour**.  
  
     Cliquez sur **Suivant** pour continuer.  
  
6. Cliquez sur **Terminer** pour publier l’application.  
  
    L'état de publication s'affiche dans la zone de notification d'état.  
  
   > [!NOTE]
   >  Une fois la publication terminée, vous devez utiliser un graveur de CD ou de DVD pour copier les fichiers depuis l'emplacement spécifié à l'étape 3 sur le CD-ROM ou DVD-ROM.  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité et déploiement ClickOnce](../deployment/clickonce-security-and-deployment.md)   
 [Sécurisation des applications ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Déploiement d’une solution Office à l’aide de ClickOnce](http://msdn.microsoft.com/library/feb516b3-5e4d-449a-9fd2-347d08d90252)
