---
title: Collecte de données concurrentielles pour un service en utilisant la ligne de commande du profileur | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 275aacba-b2af-4d34-8931-ee30d777a256
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8ca716b092d8d184313da65bffa6f66839c7254e
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56615375"
---
# <a name="collect-concurrency-data-for-a-service-by-using-the-profiler-command-line"></a>Collecter des données de concurrence pour un service en utilisant la ligne de commande du profileur
La méthode d’accès concurrentiel des outils de profilage [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] permet de collecter des données de conflit de ressources et des données d’activité de thread montrant l’utilisation du processeur, les conflits de threads, la migration des threads, les délais de synchronisation, les zones d’E/S avec chevauchement, et autres événements système.

> [!NOTE]
>  Les fonctionnalités de sécurité renforcée de Windows 8 et Windows Server 2012 ont imposé des changements importants dans la façon dont le profileur Visual Studio collecte les données sur ces plateformes. Les applications UWP nécessitent aussi de nouvelles techniques de collecte. Consultez [Outils d’analyse des performances sur les applications Windows 8 et Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

## <a name="common-tasks"></a>Tâches courantes

|Tâche|Contenu associé|
|----------|---------------------|
|**Attacher le profileur à un service .NET en cours d’exécution**|-   [Guide pratique pour attacher le profileur à un service .NET pour collecter des données concurrentielles](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-concurrency-data-by-using-the-command-line.md)|
|**Ajouter des interactions de couche**|-   [Collecter les données d’interaction de couche](../profiling/adding-tier-interaction-data-from-the-command-line.md)|
|**Attacher le profileur à un service C/C++ en cours d’exécution**|-   [Guide pratique pour attacher le profileur à un service natif pour collecter des données concurrentielles](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line.md)|

## <a name="related-tasks"></a>Tâches connexes

### <a name="profile-windows-services"></a>Profiler des services Windows

|Tâche|Contenu associé|
|----------|---------------------|
|**Profiler à l’aide de la méthode d’échantillonnage**|-   [Collecter des statistiques d’applications en utilisant l’échantillonnage](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|
|**Profiler à l’aide de la méthode d’instrumentation**|-   [Collecter les données temporelles détaillées à l’aide de l’instrumentation](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method.md)|
|**Profiler l’allocation de mémoire .NET et le garbage collection**|-   [Collecter des données de mémoire .NET](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|

### <a name="profile-concurrency-data"></a>Profiler des données concurrentielles

|Tâche|Contenu associé|
|----------|---------------------|
|**Profiler des applications autonomes**|-   [Collecter des données concurrentielles](../profiling/collecting-concurrency-data-for-stand-alone-applications.md)|
|**Profiler des applications web ASP.NET**|-   [Collecter des données concurrentielles](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md)|

### <a name="analyze-concurrency-data-views-and-reports"></a>Analyser des vues et des rapports de données concurrentielles
- [Vues de données de conflit de ressources](../profiling/resource-contention-data-views.md)

- [Visualiseur concurrentiel](../profiling/concurrency-visualizer.md)

## <a name="reference"></a>Référence
- [Informations de référence sur les outils de profilage de ligne de commande](../profiling/command-line-profiling-tools-reference.md)