---
title: 'Procédure : Rechercher le nom du processus ASP.NET | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- ASP.NET debugging, ASP.NET process
- ASP.NET process
ms.assetid: 931a7597-b0f0-4a28-931d-46e63344435f
caps.latest.revision: 32
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c403cefee3aa7d45c11cd80cf5fc2dd53a06c1fc
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/24/2019
ms.locfileid: "58947934"
---
# <a name="how-to-find-the-name-of-the-aspnet-process"></a>Procédure : Rechercher le nom du processus ASP.NET
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pour créer un attachement à une application [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] en cours d'exécution, vous devez connaître le nom du processus [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] :  
  
- Si vous exécutez IIS 6.0 ou IIS 7.0, le nom est w3wp.exe.  
  
- Si vous exécutez une version antérieure d'IIS, le nom est aspnet_wp.exe.  
  
  Pour les applications développées à l’aide de [!INCLUDE[vsprvslong](../includes/vsprvslong-md.md)] ou versions ultérieures, le [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] code peut résider sur le système de fichiers et s’exécuter sous le serveur de test WebDev.WebServer.exe. Dans ce cas, vous devez créer un attachement à WebDev.WebServer.exe au lieu du processus [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]. Ce scénario s'applique uniquement au débogage local.  
  
  Les applications antérieures d'ASP s'exécutent à l'intérieur du processus IIS inetinfo.exe lorsqu'elles s'exécutent in-process.  
  
> [!NOTE]
>  Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée. Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** . Pour plus d’informations, consultez [Personnalisation des paramètres de développement dans Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-determine-whether-project-code-resides-on-the-file-system-or-iis"></a>Pour déterminer si le code de projet réside sur le système de fichiers ou IIS  
  
1.  Dans Visual Studio, ouvrez **l’Explorateur de solutions** s’il n’est pas déjà ouvert.  
  
2.  Sélectionnez le nœud supérieur qui contient le nom de l'application.  
  
3.  Si le **propriétés** titre de la fenêtre contient un chemin d’accès de fichier, le code d’application réside sur le système de fichiers.  
  
     Sinon, le **propriétés** titre de la fenêtre contient le nom du site Web.  
  
### <a name="to-determine-the-iis-version-under-which-the-application-is-running"></a>Pour déterminer la version d'IIS sous laquelle l'application s'exécute  
  
1.  Rechercher **outils d’administration** et exécutez-le. Selon votre système d’exploitation, cela peut être une icône à l’intérieur de **le panneau de configuration**, ou une entrée de menu qui s’affiche lorsque vous cliquez sur **Démarrer**.  
  
     Dans Windows XP, **le panneau de configuration** peut se trouver dans l’affichage des catégories ou en affichage classique. Dans l’affichage des catégories, vous devez cliquer sur **basculer vers l’affichage classique** ou **Performance et Maintenance** pour voir les **outils d’administration** icône.  
  
2.  À partir de **outils d’administration**, exécutez Internet Information Services. Une boîte de dialogue MMC apparaît.  
  
3.  Si plusieurs ordinateurs sont répertoriés dans le volet gauche, sélectionnez celui sur lequel réside le code de l'application.  
  
4.  La version d’IIS est dans le **Version** colonne du volet droit.  
  
## <a name="see-also"></a>Voir aussi  
 [Conditions préalables pour le débogage des Applications Web à distance](../debugger/prerequistes-for-remote-debugging-web-applications.md)   
 [Configuration requise](../debugger/aspnet-debugging-system-requirements.md)   
 [Préparation du débogage ASP.NET](../debugger/preparing-to-debug-aspnet.md)   
 [Débogage d’applications et de scripts web](../debugger/debugging-web-applications-and-script.md)
