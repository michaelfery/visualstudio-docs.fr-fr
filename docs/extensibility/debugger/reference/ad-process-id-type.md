---
title: AD_PROCESS_ID_TYPE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AD_PROCESS_ID_TYPE
helpviewer_keywords:
- AD_PROCESS_ID_TYPE enumeration
ms.assetid: 0aab80e9-285a-4697-94ac-c864d42a6aaa
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 405d11b0c685017d59251ba83126a73fe1a96db2
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56708964"
---
# <a name="adprocessidtype"></a>AD_PROCESS_ID_TYPE
Spécifie comment interpréter un ID de processus dans le [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) structure.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_AD_PROCESS_ID {
    AD_PROCESS_ID_SYSTEM = 0,
    AD_PROCESS_ID_GUID   = 1
};
typedef DWORD AD_PROCESS_ID_TYPE;
```

```csharp
public enum enum_AD_PROCESS_ID {
    AD_PROCESS_ID_SYSTEM = 0,
    AD_PROCESS_ID_GUID   = 1
};
```

## <a name="members"></a>Membres
ID de processus AD_PROCESS_ID_SYSTEM est un identificateur de système. Utilisez le `ProcessId.dwProcessId` champ la [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) structure.

ID de processus AD_PROCESS_ID_GUID est un GUID. Utilisez le `ProcessId.guidProcessId` champ la `AD_PROCESS_ID` structure.

## <a name="remarks"></a>Notes
Utilisé pour le `ProcessIdType` membre de la [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) structure pour identifier le type d’ID de processus qui est contenue dans la structure. Détermine comment interpréter le `ProcessId` union dans la structure.

## <a name="requirements"></a>Spécifications
En-tête : msdbg.h

Espace de noms : Microsoft.VisualStudio.Debugger.Interop

Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Énumérations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)
