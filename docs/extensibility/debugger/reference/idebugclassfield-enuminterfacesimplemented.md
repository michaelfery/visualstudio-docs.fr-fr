---
title: IDebugClassField::EnumInterfacesImplemented | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField::EnumInterfacesImplemented
helpviewer_keywords:
- IDebugClassField::EnumInterfacesImplemented method
ms.assetid: e5523e45-d350-491e-a92c-fe0ca97d2052
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bffae40f1e5212132c89b6b71b7fc83cca6ebb42
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56702133"
---
# <a name="idebugclassfieldenuminterfacesimplemented"></a>IDebugClassField::EnumInterfacesImplemented
Crée un énumérateur pour les interfaces implémentées par cette classe.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT EnumInterfacesImplemented( 
   IEnumDebugFields** ppEnum
);
```

```csharp
int EnumInterfacesImplemented(
   out IEnumDebugFields ppEnum
);
```

#### <a name="parameters"></a>Paramètres
 `ppEnum`

 [out] Retourne un [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objet représentant la liste des interfaces implémentées. Retourne une valeur null si aucune interface.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne S_OK, ou retourne S_FALSE s’il n’existe aucune interface implémenté sur cette classe. Sinon, retourne un code d'erreur.

## <a name="remarks"></a>Notes
 Chaque élément de l’énumération est un [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) objet décrivant une interface. Notez que non gérés [!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)] code n’utilise pas les interfaces en tant qu’entité discrète donc cette méthode retourne toujours une valeur null pour unmanaged [!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)] code.

## <a name="see-also"></a>Voir aussi
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)