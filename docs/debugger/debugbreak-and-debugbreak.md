---
title: DebugBreak et __debugbreak | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DebugBreak
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], DebugBreak function
- DebugBreak function
- breakpoints, DebugBreak function
ms.assetid: 9787c795-df94-4f48-bc8d-3bf899b67421
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b6c4b9d780caf7589eecdc709cbede577dd7a6fd
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686156"
---
# <a name="debugbreak-and-debugbreak"></a>DebugBreak et __debugbreak
Vous pouvez appeler la fonction Win32 DebugBreak ou l’objet intrinsèque [__debugbreak](/cpp/intrinsics/debugbreak) à n’importe quel endroit de votre code. `DebugBreak` et `__debugbreak` reviennent à définir un point d'arrêt à cet emplacement.

 Étant donné que `DebugBreak` est un appel à une fonction système, les symboles de débogage de système doivent être installés pour vérifier que les informations de pile des appels correctes sont affichées après l’arrêt. À défaut, les informations de la pile des appels affichées par le débogueur peuvent être décalées d'un frame. Si vous utilisez `__debugbreak`, les symboles ne sont pas requis.

## <a name="see-also"></a>Voir aussi
- [compilateur, fonctions intrinsèques](/cpp/intrinsics/compiler-intrinsics)
- [Sécurité du débogueur](../debugger/debugger-security.md)
- [Débogage du code natif](../debugger/debugging-native-code.md)
- [Spécifier les fichiers de symbole (.pdb) et les fichiers sources](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)