---
title: Créer une Installation hors connexion | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-install
ms.topic: conceptual
f1_keywords:
- offline installation
- offline install
- ISO
ms.assetid: 85d65709-42be-449f-9663-914bf1045089
caps.latest.revision: 22
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: 297c35b7c42287613bdbc567631ddb6b1c1d9dba
ms.sourcegitcommit: b7f25ae08e45fcaa84a84276b588cf6799cc7620
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57567232"
---
# <a name="create-an-offline-installation-of-visual-studio"></a>Créer une installation hors connexion de Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pour la documentation la plus récente pour Visual Studio 2017, consultez [installer Visual Studio 2017 sur faible bande passante ou des environnements réseau non fiables](https://docs.microsoft.com/visualstudio/install/install-vs-inconsistent-quality-network), ou [créer une installation réseau de Visual Studio 2017](https://docs.microsoft.com/visualstudio/install/create-a-network-installation-of-visual-studio) et [Considérations particulières pour installer Visual Studio 2017 dans un environnement hors connexion](https://docs.microsoft.com/visualstudio/install/install-visual-studio-in-offline-environment).

Cette page décrit comment installer Visual Studio 2015 lorsque vous n’êtes pas connecté à Internet. Toutefois, pour effectuer une installation « déconnectée », vous devez d’abord créer une disposition d’installation hors connexion à l’aide d’un ordinateur qui est connecté à Internet. Voici comment faire.

> [!IMPORTANT]
>  Si votre ordinateur en mode hors connexion est en cours d’exécution Windows 7 SP1 ou Windows Server 2008 R2, consultez les instructions spéciales dans le [dépannage d’une installation hors connexion](#BKMK_tshoot) section de cette rubrique.  Vous devez suivre ces instructions *avant* vous installez Visual Studio 2015.

##  <a name="BKMK_Offline"></a> L’installation en créant une installation hors connexion

#### <a name="to-create-an-offline-installation-layout"></a>Pour créer une disposition d’installation hors connexion

1.  Choisissez l’édition de Visual Studio que vous souhaitez installer à partir de la [My.VisualStudio.com](https://my.visualstudio.com/downloads?q=visual%20studio%20Enterprise%202015) page de téléchargement.

2.  Après avoir téléchargé le programme d’installation vers un emplacement sur votre système de fichiers, exécutez «\<nom exécutable >/Layout ».

     Par exemple, exécutez : `vs_enterprise.exe /layout D:\VisualStudio2015`

     À l’aide de la `/layout` commutateur, vous pouvez télécharger presque tous les packages d’installation, pas seulement ceux qui s’appliquent à l’ordinateur de téléchargement. Cette approche vous offre les fichiers dont vous avez besoin pour exécuter ce programme d’installation de n’importe où, et il peut être utile si vous souhaitez installer les composants qui n’ont pas été installés à l’origine.

3.  Après avoir exécuté cette commande, une boîte de dialogue s’affiche qui vous permet de modifier le dossier où vous souhaitez la disposition d’installation hors connexion réside.   Ensuite, cliquez sur le **télécharger** bouton.

     Lorsque le téléchargement du package ne réussit pas, vous devez voir un message indiquant que **installation réussie ! Tous les composants spécifiés ont été correctement acquis.**

4.  Recherchez le dossier que vous avez spécifié précédemment. (Par exemple, recherchez D:\VisualStudio2015.) Ce dossier contient tout ce que vous devez copier vers un emplacement partagé ou le média d’installation.

    > [!CAUTION]
    >  Actuellement, le kit SDK Android ne prend pas en charge les installations hors connexion. Si vous installez des éléments de l’installation du kit SDK Android sur un ordinateur qui n’est pas connecté à internet, l’installation peut échouer. Pour plus d’informations, consultez la section « Résolution des problèmes d’une installation hors connexion » dans cette rubrique.

5.  Exécutez l’installation à partir de l’emplacement du fichier ou à partir du support d’installation.

## <a name="updating-an-offline-installation"></a>La mise à jour une installation hors connexion
 Microsoft a publié plusieurs mises à jour pour Visual Studio 2015. Pour mettre à jour votre installation de Visual Studio, il suffit de télécharger l’édition souhaitée de l’à partir de la [My.VisualStudio.com](https://my.visualstudio.com/downloads?q=visual%20studio%20Enterprise%202015) page de téléchargement. Ensuite, suivez les étapes décrites dans cette rubrique pour créer une nouvelle disposition d’installation hors connexion et l’utiliser pour mettre à jour votre copie de Visual Studio 2015.

##  <a name="BKMK_tshoot"></a> Dépannage d’une installation hors connexion
 Quand vous effectuez une installation hors connexion à partir de votre cache d’installation hors connexion, des messages d’avertissement peuvent s’afficher pour vous indiquer l’impossibilité d’installer certains composants et packages. Le tableau suivant présente les solutions possibles à ces scénarios.


|                                                                                       Composant ou package                                                                                       |                                                                                                                                                                                                                                                                                                                                                                                                   Solution                                                                                                                                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dotfuscator et Analytique Community Edition 5.19.1 (pour les éditions Community, Professional et Enterprise de Visual Studio, comme étant installée dans **Windows 7 SP1** et **Windows Server 2008 R2**) |                                                                                                                                       Si votre ordinateur en mode hors connexion est en cours d’exécution **Windows 7 SP1** ou **Windows Server 2008 R2**, vous devez effectuer les étapes suivantes avant d’installer Visual Studio 2015 :<br /><br /> 1.  Configurer un serveur de fichiers ou web pour télécharger les fichiers CTL.<br /><br /> 2.    Rediriger l’URL de mise à jour automatique de Microsoft pour un environnement déconnecté.<br /><br /> Pour plus d’informations, consultez le [configurer des racines de confiance et certificats non autorisés](https://technet.microsoft.com/library/dn265983.aspx) page sur le site Microsoft TechNet.                                                                                                                                       |
|                                                                                  Installation du SDK Android (Niveau API)                                                                                   |                                                                        Vous devez avoir une connexion Internet pour installer les packages du SDK Android (niveau API). Si vous êtes sur un réseau limité, vous devez autoriser l’accès aux URL suivantes quand vous installez Visual Studio :<br /><br /> -   http://dl.google.com:443<br />-   http://dl-ssl.google.com:443<br />-   https://dl-ssl.google.com/android/repository/*<br /> <br />Pour plus d’informations sur la résolution des éventuels problèmes avec les paramètres de proxy, consultez le billet de blog [Visual Studio 2015 install failures (Android SDK Setup) behind a Proxy](https://blogs.msdn.microsoft.com/peterhauge/2016/09/22/visual-studio-2015-install-failures-android-sdk-setup-behind-a-proxy/).                                                                         |
|                             Modèles d’élément d’extensibilité Visual Studio<br /><br /> Extension GitHub pour Visual Studio<br /><br /> Outils PowerShell pour Visual Studio                             | Si vous n’avez pas d’une connexion internet lorsque vous installez Visual Studio 2015, vous pouvez utiliser un spécial flux hors connexion pour générer la disposition d’installation hors connexion. **Remarque :** ce flux spécial inclut les mises à jour plus récente de Visual Studio 2015. <br /><br /> Pour créer des flux hors connexion spéciale, exécutez la commande suivante : / Layout *lecteur :* \VisualStudio2015 /overridefeeduri *URL aux flux xml*<br /><br /> Par exemple, pour un langue anglaise spécial flux hors connexion de Visual Studio 2015 Enterprise, exécutez :<br /><br /> `vs_enterprise_ENU.exe /layout D:\VisualStudio2015 /overridefeeduri "http://go.microsoft.com/fwlink/?LinkID=785882&clcid0x409"`<br /><br /> Pour obtenir une liste complète des URL que vous pouvez utiliser pour créer un flux hors connexion de spécial dans le langage de votre choix, consultez le tableau ci-dessous. |

 Utilisez les URL suivantes pour créer un flux hors connexion spécial spécifique à la langue, comme décrit dans le tableau ci-dessus.


|       Langue        |                            URL                            |
|-----------------------|-----------------------------------------------------------|
| Chinois (simplifié)  | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x804 |
| Chinois (traditionnel) | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x404 |
|         Tchèque         | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x405 |
|        Allemand         | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x407 |
|        Anglais        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x409 |
|        Espagnol        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0xC0A |
|        Français         | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x40C |
|        Italien        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x410 |
|       Japonais        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x411 |
|        Coréen         | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x412 |
|        Polonais         | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x415 |
|      Portugais       | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x416 |
|        Russe        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x419 |
|        Turc        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x41F |

## <a name="see-also"></a>Voir aussi
 [Installer Visual Studio](install-visual-studio-2015.md)