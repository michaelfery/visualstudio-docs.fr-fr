---
title: BP_FLAGS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_FLAGS
helpviewer_keywords:
- BP_FLAGS enumeration
ms.assetid: c45dfc74-5e7f-4f1e-a147-ab2a55dccbd0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fe346d708110cf16b85e84d61aeb25ee335c0e96
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56688431"
---
# <a name="bpflags"></a>BP_FLAGS
Fournit des indicateurs facultatifs qui peuvent être utilisées pour spécifier des informations supplémentaires lors de la définition d’un point d’arrêt.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_BP_FLAGS {
    BP_FLAG_NONE            = 0x0000,
    BP_FLAG_MAP_DOCPOSITION = 0x0001,
    BP_FLAG_DONT_STOP       = 0x0002
};
typedef DWORD BP_FLAGS;
```

```csharp
public enum enum_BP_FLAGS {
    BP_FLAG_NONE            = 0x0000,
    BP_FLAG_MAP_DOCPOSITION = 0x0001,
    BP_FLAG_DONT_STOP       = 0x0002
};
```

## <a name="members"></a>Membres
BP_FLAG_NONE ne spécifie aucun indicateur de point d’arrêt.

BP_FLAG_MAP_DOCPOSITION Spécifie que le moteur de débogage (dé) doit mapper le point d’arrêt à l’aide de la position du document. Cela s’applique uniquement aux points d’arrêt définis dans les fichiers source orienté sur le script Active Server Pages (ASP).

BP_FLAG_DONT_STOP Spécifie que le point d’arrêt doit être traité par le moteur de débogage, mais que le moteur de débogage en fin de compte ne doit pas arrêter il (autrement dit, un [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) objet d’événement ne doit pas être envoyé). Cet indicateur est conçu pour être principalement utilisé avec des points de trace.

## <a name="remarks"></a>Notes
Utilisé pour le `dwFlags` membre de la [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) et [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) structures.

Ces valeurs peuvent être combinées avec un opérateur de bits `OR`.

## <a name="requirements"></a>Spécifications
En-tête : msdbg.h

Espace de noms : Microsoft.VisualStudio.Debugger.Interop

Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Énumérations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)
- [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)
- [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)
