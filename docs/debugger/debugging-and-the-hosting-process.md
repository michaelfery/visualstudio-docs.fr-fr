---
title: Débogage et processus d’hébergement | Microsoft Docs
ms.date: 08/01/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], hosting process
- hosting process
ms.assetid: d0f0b9a6-2a6e-463d-b6ea-9518ee727933
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: af0d57e39fa8d1312032bacbbd9af95d44449ca1
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57525828"
---
# <a name="debugging-and-the-hosting-process"></a>Débogage et processus d'hébergement
Le processus d'hébergement Visual Studio améliore la performance de débogueur et active de nouvelles fonctions de débogage, telles que le débogage de confiance partielle et l'évaluation d'une expression au moment du design. Vous pouvez désactiver le processus d’hébergement, le cas échéant. Les sections suivantes décrivent certaines des différences entre le débogage avec et sans le processus d’hébergement.

> [!NOTE]
> À partir de Visual Studio 2017, l’option au débogage en utilisant le processus d’hébergement n’est plus nécessaire et a été supprimée. Pour plus d’informations, consultez [débogage : Visual Studio 2017 vise à vitesse de votre moins favori travail](https://vslive.com/Blogs/News-and-Tips/2017/02/Debugging-Visual-Studio-2017-aims-to-speed-up-your-least-favorite-job.aspx).

## <a name="partial-trust-debugging-and-click-once-security"></a>Débogage de confiance partielle et sécurité ClickOnce
 Le débogage de confiance partielle requiert le processus d'hébergement. Si vous désactivez le processus d’hébergement, le débogage de confiance partielle ne fonctionnera pas, même si la sécurité de confiance partielle est activée dans la page **Sécurité** de **Propriétés du projet**. Pour plus d’informations, consultez [Comment : déboguer une Application de confiance partielle](/visualstudio/debugger/debugger-security).

## <a name="design-time-expression-evaluation"></a>Évaluation de l’expression au moment du design
 L'expression au moment du design utilise toujours le processus d'hébergement. La désactivation du processus d'hébergement dans **Propriétés du projet** désactive l'évaluation d'une expression au moment du design pour les projets Bibliothèque de classes. Pour d'autres types de projet, l'évaluation d'une expression au moment du design n'est pas désactivée. À la place, Visual Studio démarre le fichier exécutable réel et l'utilise pour l'évaluation au moment du design sans le processus d'hébergement. Cette différence peut produire des résultats différents.

## <a name="appdomaincurrentdomainfriendlyname-differences"></a>Différences AppDomain.CurrentDomain.FriendlyName
 `AppDomain.CurrentDomain.FriendlyName` retourne des résultats différents selon que le processus d'hébergement est activé ou non. Si vous appelez `AppDomain.CurrentDomain.FriendlyName` avec le processus d’hébergement activé, il retourne *nom_application*`.vhost.exe`. Si vous l’appelez avec le processus d’hébergement désactivé, il retourne *nom_application*`.exe`.

## <a name="assemblygetcallingassemblyfullname-differences"></a>Différences Assembly.GetCallingAssembly().FullName
 `Assembly.GetCallingAssembly().FullName` retourne des résultats différents selon que le processus d'hébergement est activé ou non. Si vous appelez `Assembly.GetCallingAssembly().FullName` avec le processus d’hébergement activé, il retourne `mscorlib`. Si vous appelez `Assembly.GetCallingAssembly().FullName` avec le processus d’hébergement désactivé, il retourne le nom d’application.

## <a name="see-also"></a>Voir aussi

- [Guide pratique pour déboguer une application de confiance partielle](/visualstudio/debugger/debugger-security)