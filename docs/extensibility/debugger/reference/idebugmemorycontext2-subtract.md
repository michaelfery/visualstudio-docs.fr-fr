---
title: IDebugMemoryContext2::Subtract | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMemoryContext2::Subtract
helpviewer_keywords:
- Subtract method
- IDebugMemoryContext2::Subtract method
ms.assetid: 63df14c7-8d7e-47c1-afa7-5a1ab5d8eaba
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6bc84d1658fe71131f75825fa4b8b50d8aa9e31b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56723654"
---
# <a name="idebugmemorycontext2subtract"></a>IDebugMemoryContext2::Subtract
Soustrait la valeur spécifiée à partir du contexte actuel et retourne un nouveau contexte.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Subtract( 
   UINT64                 dwCount,
   IDebugMemoryContext2** ppMemCxt
);
```

```csharp
int Subtract(
   ulong                    dwCount,
   out IDebugMemoryContext2 ppMemCxt
);
```

#### <a name="parameters"></a>Paramètres
 `dwCount`

 [in] Le nombre d’octets de mémoire à décrémenter.

 `ppMemCxt`

 [out] Retourne un nouvel [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objet.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.

## <a name="remarks"></a>Notes
 Un contexte de mémoire étant une adresse, en soustrayant une valeur à partir d’une adresse génère une nouvelle adresse qui requiert une nouvelle interface de contexte.

 Cette méthode doit produire toujours un nouveau contexte, même si l’adresse obtenue est en dehors de l’espace de mémoire associé à ce contexte. La seule exception est si aucune mémoire ne pouvant être allouée pour le nouveau contexte ou si `ppMemCxt` est une valeur null (qui est une erreur).

## <a name="see-also"></a>Voir aussi
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)