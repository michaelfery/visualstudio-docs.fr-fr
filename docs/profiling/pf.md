---
title: PF | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: cdc0a094-a986-4629-bd1c-dd5fdca323dc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7815f3b8788ac2fd3eaece89d6e2dbeeb49426d2
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56608355"
---
# <a name="pf"></a>PF
L’option **PF** de *VSPerfCmd.exe* définit l’événement de profilage qui est échantillonné lors des défauts de page. Elle peut changer le nombre de défauts de page dans un intervalle d’échantillonnage (la valeur par défaut est 10).

> [!NOTE]
>  Vous ne pouvez pas utiliser **PF** sur les systèmes 64 bits.

Vous pouvez utiliser **PF** seulement sur une ligne de commande qui contient aussi l’option **Launch** ou **Attach**.

 Par défaut, l’événement d’échantillonnage du profileur est défini sur les cycles d’horloge du processeur hors interruption, et l’intervalle d’échantillonnage est défini sur 10 000 000. Les options **Timer**, **PF**, **Sys** et **Counter** vous permettent de définir l’événement d’échantillonnage et l’intervalle d’échantillonnage. L’option **GC** collecte les données de mémoire .NET à chaque événement d’allocation et de garbage collection. Vous ne pouvez spécifier qu'une seule de ces options sur une ligne de commande.

 Vous pouvez définir l’événement d’échantillonnage et l’intervalle d’échantillonnage seulement sur la première ligne de commande qui contient une option **Launch** ou **Attach**.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe {/Launch:AppName|/Attach:PID} /PF[:Events] [Options]
```

#### <a name="parameters"></a>Paramètres
 `Events` Valeur entière qui spécifie le nombre d’événements de défaut de page dans un intervalle d’échantillonnage. Si `Events` n’est pas spécifié, l’intervalle est défini sur 10.

## <a name="required-options"></a>Options obligatoires
 Vous pouvez spécifier **PF** seulement sur une ligne de commande qui contient une des options suivantes.

 **Launch :** `AppName` Démarre le profileur et l’application spécifiée par AppName.

 **Attach :** `PID` Attache le profileur au processus spécifié par AppName.

## <a name="invalid-options"></a>Options non valides
 Vous ne pouvez pas spécifier les options suivantes sur la même ligne de commande que **PF**.

 **Timer**[**:**`Cycles`] Définit l’événement d’échantillonnage en fonction des cycles d’horloge du processeur et affecte éventuellement à l’intervalle d’échantillonnage la valeur `Cycles`. L’intervalle de Timer par défaut est 10,000,000.

 **Sys**[**:**`Events`] Définit l’événement d’échantillonnage en fonction des appels de l’application profilée au noyau du système d’exploitation (syscalls), et affecte éventuellement à l’intervalle d’échantillonnage la valeur `Events`. L'intervalle Sys par défaut est 10.

 **Counter:** `Name`[`,Reload`[`,FriendlyName`]] Définit l’événement d’échantillonnage en fonction du compteur de performances du CPU spécifié par `Name`, et affecte éventuellement à l’intervalle d’échantillonnage la valeur `Reload`.

 **GC**[**:**{**Allocation**&#124;**Lifetime**}] Collecte les données de mémoire .NET. Par défaut (**Allocation**), les données sont collectées à chaque événement d’allocation mémoire. Quand le paramètre **Lifetime** est spécifié, les données sont aussi collectées à chaque événement de garbage collection.

## <a name="example"></a>Exemple
 Cet exemple montre comment définir l’événement d’échantillonnage du profilage sur les défauts de page, et comment définir l’intervalle d’échantillonnage sur 20 défauts de page.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp
VSPerfCmd.exe /Launch:TestApp.exe /PF:20
```

## <a name="see-also"></a>Voir aussi
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Profiler des applications autonomes](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Profiler des applications web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profiler des services](../profiling/command-line-profiling-of-services.md)