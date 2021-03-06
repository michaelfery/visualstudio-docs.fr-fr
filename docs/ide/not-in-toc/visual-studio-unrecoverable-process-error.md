---
title: Un processus a rencontré une erreur irrécupérable
ms.date: 06/22/2018
ms.topic: troubleshooting
helpviewer_keywords:
- unrecoverable error
- error, process
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 11605b9477397bb217bc2799feb622cb9d5bce37
ms.sourcegitcommit: 87d7123c09812534b7b08743de4d11d6433eaa13
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57223631"
---
# <a name="visual-studio-unrecoverable-process-error"></a>Erreur de processus irrécupérable Visual Studio

Visual Studio utilise plusieurs processus hors processus pour exécuter des tâches d’arrière-plan obligatoires, telles que des tests unitaires en direct, des analyseurs de code, et bien plus encore. Grâce à l’exécution hors processus de ces processus, les performances de Visual Studio sont améliorées ; par exemple, Visual Studio répond plus rapidement pendant l’exécution de tâches gourmandes en ressources et de longue durée. En outre, Visual Studio étant un processus 32 bits, l’exécution de processus hors processus met un espace de mémoire plus grand à la disposition des travaux gourmands en mémoire.

Si le processus *ServiceHub.RoslynCodeAnalysisService.exe* ou *ServiceHub.RoslynCodeAnalysisService32.exe* se termine pour une raison quelconque, une barre d’information contextuelle s’affiche avec le message suivant :

**« Malheureusement, un processus utilisé par Visual Studio a rencontré une erreur irrécupérable. Nous vous recommandons d’enregistrer votre travail, puis de fermer et redémarrer Visual Studio. »**

Si vous voyez ce message, vous devez enregistrer votre travail, puis fermer et redémarrer Visual Studio.

## <a name="list-of-processes"></a>Liste de processus

Voici une liste des processus hors processus utilisés par Visual Studio. Cette liste comprend les processus qui démarrent dans des scénarios ou des flux de travail spécifiques. Par conséquent, dans la plupart des cas ils ne s’exécutent pas tous en même temps.

- Microsoft.Alm.Shared.Remoting.RemoteContainer.dll
- Microsoft.CodeAnalysis.LiveUnitTesting.EntryPoint
- PerfWatson2.exe
- ServiceHub.Host.Node.x86.exe
- ServiceHub.IdentityHost.exe
- ServiceHub.VSDetouredHost.exe
- ServiceHub.SettingsHost.exe
- ServiceHub.Host.CLR.x86.exe
- ServiceHub.RoslynCodeAnalysisService32.exe
- ServiceHub.RoslynCodeAnalysisService.exe
- WindowsAzureGuestAgent.exe
- WindowsAzureTelemetryService.exe
- WaAppAgent.exe

Si l’un de ces processus s’arrête de façon inattendue, certaines fonctionnalités dans Visual Studio cessent de fonctionner. Pour certains processus, la perte de fonctionnalité peut être négligeable. Pour d’autres, la stabilité de Visual Studio est affectée et un message d’erreur s’affiche.