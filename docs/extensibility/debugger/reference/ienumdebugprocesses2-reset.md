---
title: IEnumDebugProcesses2::Reset | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugProcesses2::Reset
helpviewer_keywords:
- IEnumDebugProcesses2::Reset
ms.assetid: 31cbde4f-0bba-497a-9969-d2c342ef4a7b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d40f40ac792eab1c84c3b195d49cd570ec6f83b8
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56708386"
---
# <a name="ienumdebugprocesses2reset"></a>IEnumDebugProcesses2::Reset
Réinitialise l’énumération au premier élément.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Reset(
   void
);
```

```csharp
int Reset();
```

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.

## <a name="remarks"></a>Notes
 Une fois que cette méthode est appelée, l’appel suivant à la [suivant](../../../extensibility/debugger/reference/ienumdebugprocesses2-next.md) méthode retourne le premier élément de l’énumération.

## <a name="see-also"></a>Voir aussi
- [IEnumDebugProcesses2](../../../extensibility/debugger/reference/ienumdebugprocesses2.md)