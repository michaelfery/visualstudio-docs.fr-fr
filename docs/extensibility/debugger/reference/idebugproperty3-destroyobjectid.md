---
title: IDebugProperty3::DestroyObjectID | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty3::DestroyObjectID
helpviewer_keywords:
- IDebugProperty3::DestroyObjectID
ms.assetid: bd08f356-cc67-4717-98c9-c3d00cad2040
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 540427286306999b25fba99a2efbd17013740d90
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56708990"
---
# <a name="idebugproperty3destroyobjectid"></a>IDebugProperty3::DestroyObjectID
Détruit l’ID unique associé à cette propriété, indiquant que l’appelant n’a plus besoin d’identifier cette propriété identifie de façon unique à partir de toutes les autres propriétés.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT DestroyObjectID(
   void
);
```

```csharp
int DestroyObjectID();
```

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.

## <a name="remarks"></a>Notes
 Si le moteur de débogage n’a pas besoin prendre en charge des ID uniques pour une propriété (car il déjà suit les identifie de façon unique en interne), il peut simplement retourner `E_NOTIMPL` pour cette méthode.

 ID uniques est créés avec un appel à la [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md) méthode lorsque l’appelant veut s’assurer que cette propriété est identifiée de manière unique parmi toutes les autres propriétés.

## <a name="see-also"></a>Voir aussi
- [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)
- [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)