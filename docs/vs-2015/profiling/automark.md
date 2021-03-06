---
title: AutoMark | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: c4de965e-0364-4f78-9936-1f509e85df74
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4fb849b43e21010d9183f53e31ccf6bbc70736b6
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2019
ms.locfileid: "54753464"
---
# <a name="automark"></a>AutoMark
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

L’option **AutoMark** spécifie le nombre de millisecondes écoulées entre les collectes des événements des compteurs de performances logiciels Windows. Les compteurs de performances Windows sont spécifiés dans l’option **WinCounter**.  
  
 Vous ne pouvez spécifier qu’une seule option **AutoMark** sur la ligne de commande. Notez que l’intervalle d’échantillonnage de **WinCounter** spécifié par **AutoMark** est indépendant de l’intervalle d’échantillonnage principal.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Start:Method /WinCounter:Path /AutoMark:Milliseconds  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Milliseconds`  
 Spécifie le nombre de millisecondes écoulées entre les collectes des événements des compteurs de performances Windows.  
  
## <a name="required-options"></a>Options obligatoires  
 **WinCounter:** `Path`  
 Spécifie le compteur de performances Windows à collecter. Quand vous utilisez la méthode d’instrumentation, vous pouvez spécifier plusieurs compteurs Windows. Quand vous utilisez la méthode d’échantillonnage, vous ne pouvez spécifier qu’un seul compteur Windows. L’option **WinCounter** doit être spécifiée dans une ligne de commande qui contient l’option **Start**.  
  
## <a name="example"></a>Exemple  
 Dans cet exemple, un intervalle d’échantillonnage de 1 000 millisecondes est défini pour deux compteurs de performances Windows.  
  
```  
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /WinCounter:"\Process(*)\% Processor Time" /WinCounter:"\ASP.NET\Pages/sec" /AutoMark:1000  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>Voir aussi  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilage d’applications autonomes](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilage d’applications web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilage de services](../profiling/command-line-profiling-of-services.md)
