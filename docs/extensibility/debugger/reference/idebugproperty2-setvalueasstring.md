---
title: IDebugProperty2::SetValueAsString | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::SetValueAsString
helpviewer_keywords:
- IDebugProperty2::SetValueAsString
ms.assetid: 9e6a5054-41b7-4223-b509-b93689d366a5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6acc3c0c0ec271793832783b2fb7eb9f2ff2309a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686481"
---
# <a name="idebugproperty2setvalueasstring"></a>IDebugProperty2::SetValueAsString
Définit la valeur d’une propriété à partir d’une chaîne donnée.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetValueAsString ( 
   LPCOLESTR pszValue,
   UINT      nRadix,
   DWORD     dwTimeout
);
```

```csharp
int SetValueAsString ( 
   string pszValue,
   uint   nRadix,
   uint   dwTimeout
);
```

#### <a name="parameters"></a>Paramètres
 `pszValue`

 [in] Chaîne contenant la valeur à définir.

 `nRadix`

 [in] Une base pour être utilisées pour interpréter toutes les informations numériques. Cela peut être 0 pour tenter de déterminer la base automatiquement.

 `dwTimeout`

 [in] Spécifie la durée maximale, en millisecondes, à attendre avant de retourner à partir de cette méthode. Utilisez `INFINITE` pour attendre indéfiniment.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon retourne le code d’erreur. Le tableau suivant présente les autres valeurs possibles.

|Value|Description|
|-----------|-----------------|
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|La chaîne n’a pas pu être convertie en une valeur de propriété, ou la valeur de propriété pas pu être définie.|
|`E_SETVALUE_VALUE_IS_READONLY`|La propriété doit être en lecture seule.|

## <a name="see-also"></a>Voir aussi
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)