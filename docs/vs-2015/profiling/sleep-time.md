---
title: Durée de veille | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.sleep
helpviewer_keywords:
- Concurrency Visualizer, Sleep Time
ms.assetid: 3ddb96f9-9bda-4a68-ad4d-ef488a0a68dc
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 8a79bbca9f6275f115105cc2ba6b001ac0ca7d44
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2019
ms.locfileid: "54774618"
---
# <a name="sleep-time"></a>Durée de veille
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ces segments de la chronologie sont associés au temps de blocage catégorisé comme Veille. La catégorie Veille implique qu’un thread a volontairement abandonné son cœur logique et n’effectue aucun travail. Pendant cette période, un thread a été bloqué dans une API que le visualiseur concurrentiel considère comme étant de la veille. Les API comme `Sleep()` et `SwitchToThread()` appartiennent à ce groupe.  
  
## <a name="see-also"></a>Voir aussi  
 [vue Threads](../profiling/threads-view-parallel-performance.md)
