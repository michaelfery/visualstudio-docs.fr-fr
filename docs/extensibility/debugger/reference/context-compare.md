---
title: CONTEXT_COMPARE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CONTEXT_COMPARE
helpviewer_keywords:
- CONTEXT_COMPARE enumeration
ms.assetid: 701ed61c-a320-4c20-a335-0b840024abc0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 21628bda9dc0437672b0b755bb64f1c882b0acbf
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689172"
---
# <a name="contextcompare"></a>CONTEXT_COMPARE
Spécifie les critères pour la comparaison de deux contextes de mémoire.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_CONTEXT_COMPARE {
    CONTEXT_EQUAL                 = 0x0001,
    CONTEXT_LESS_THAN             = 0x0002,
    CONTEXT_GREATER_THAN          = 0x0003,
    CONTEXT_LESS_THAN_OR_EQUAL    = 0x0004,
    CONTEXT_GREATER_THAN_OR_EQUAL = 0x0005,
    CONTEXT_SAME_SCOPE            = 0x0006,
    CONTEXT_SAME_FUNCTION         = 0x0007,
    CONTEXT_SAME_MODULE           = 0x0008,
    CONTEXT_SAME_PROCESS          = 0x0009
};
typedef DWORD CONTEXT_COMPARE;
```

```csharp
public enum enum_CONTEXT_COMPARE {
    CONTEXT_EQUAL                 = 0x0001,
    CONTEXT_LESS_THAN             = 0x0002,
    CONTEXT_GREATER_THAN          = 0x0003,
    CONTEXT_LESS_THAN_OR_EQUAL    = 0x0004,
    CONTEXT_GREATER_THAN_OR_EQUAL = 0x0005,
    CONTEXT_SAME_SCOPE            = 0x0006,
    CONTEXT_SAME_FUNCTION         = 0x0007,
    CONTEXT_SAME_MODULE           = 0x0008,
    CONTEXT_SAME_PROCESS          = 0x0009
};
```

## <a name="members"></a>Membres
CONTEXT_EQUAL recherche le premier contexte de la mémoire dans la liste qui est égale au contexte cible de mémoire.

CONTEXT_LESS_THAN recherche le premier contexte de la mémoire dans la liste qui est inférieur au contexte de la mémoire cible.

CONTEXT_GREATER_THAN recherche le premier contexte de la mémoire dans la liste qui est supérieure dans le contexte de la mémoire cible.

CONTEXT_LESS_THAN_OR_EQUAL recherche le premier contexte de la mémoire dans la liste qui est inférieur ou égal au contexte cible de mémoire.

CONTEXT_GREATER_THAN_OR_EQUAL recherche le premier contexte de la mémoire dans la liste qui est supérieur ou égal au contexte cible de mémoire.

CONTEXT_SAME_SCOPE recherche le premier contexte de la mémoire dans la liste qui se trouve dans la même étendue que le contexte de la mémoire cible.

CONTEXT_SAME_FUNCTION recherche le premier contexte de la mémoire dans la liste qui se trouve dans la même fonction que l’étendue de mémoire cible.

CONTEXT_SAME_MODULE recherche le premier contexte de la mémoire dans la liste qui se trouve dans le même module que le contexte de la mémoire cible.

CONTEXT_SAME_PROCESS recherche le premier contexte de la mémoire dans la liste qui se trouve dans le même processus que le contexte de la mémoire cible.

## <a name="remarks"></a>Notes
Passé en tant qu’argument à la [comparer](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md) (méthode).

Ces valeurs sont utilisées pour rechercher le premier contexte de la mémoire dans une liste qui satisfait aux critères de comparaison spécifiées. Un contexte de mémoire reçoit une liste des contextes de mémoire à comparer lui-même contre via le `IDebugMemoryContext2::Compare` (méthode). Le premier contexte de la mémoire dans la liste pour laquelle l’opérateur de comparaison est `true` est alors retournée.

## <a name="requirements"></a>Spécifications
En-tête : msdbg.h

Espace de noms : Microsoft.VisualStudio.Debugger.Interop

Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Énumérations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [Compare](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)
