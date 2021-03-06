---
title: IDispatchEx::GetNextDispID | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispatchEx.GetNextDispID
apilocation:
- scrobj.dll
helpviewer_keywords:
- GetNextDispID method
ms.assetid: 8263d441-85ee-47f4-bdba-fbf2ad07e85f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d964a8744f1f0a28704dd0a1d5e0fd2e67aab1c
ms.sourcegitcommit: 05d104a14ff357d599ff274f97cd59d464ee4a46
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2019
ms.locfileid: "58897671"
---
# <a name="idispatchexgetnextdispid"></a>IDispatchEx::GetNextDispID

Énumère les membres de l’objet.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetNextDispID(
   DWORD grfdex,
   DISPID id,
   DISPID *pid
);
```

## <a name="parameters"></a>Paramètres

`grfdex`\
Détermine quel jeu d’éléments sont à énumérer. Cela peut être une combinaison des valeurs suivantes :

|Value|Signification|
|-----------|-------------|
|fdexEnumDefault|Demande que l’objet énumère les éléments par défaut. L’objet est autorisé à énumérer n’importe quel jeu d’éléments.|
|fdexEnumAll|Demande que l’objet énumère tous les éléments. L’objet est autorisé à énumérer n’importe quel jeu d’éléments.|

`id`\
Identifie le membre actuel. GetNextDispID récupère l’élément dans l’énumération après celui-ci. Utilise GetDispID ou un appel précédent à GetNextDispID pour obtenir cet identificateur. Utilise la valeur DISPID_STARTENUM pour obtenir le premier identificateur du premier élément.

`pid`\
Adresse d’une variable DISPID qui reçoit l’identificateur de l’élément suivant dans l’énumération.

Si un membre est supprimé par `DeleteMemberByName` ou `DeleteMemberByDispID`, le `DISPID` doit rester valide pour `GetNextDispID`.

## <a name="return-value"></a>Valeur de retour

Retourne une des valeurs suivantes :

|||
|-|-|
|`S_OK`|Opération réussie.|
|`S_FALSE`|L’énumération est effectuée.|

## <a name="example"></a>Exemple

```cpp
   HRESULT hr;
   BSTR bstrName;
   DISPID dispid;
   IDispatchEx *pdex;

   // Assign to pdex
   hr = pdex->GetNextDispID(fdexEnumAll, DISPID_STARTENUM, &dispid);
   while (hr == NOERROR)
   {
      hr = pdex->GetMemberName(dispid, &bstrName);
      if (!wcscmp(bstrName, OLESTR("Bar")))
      {
         SysFreeString(bstrName);
         return TRUE;
      }
      SysFreeString(bstrName);
      hr = pdex->GetNextDispID(fdexEnumAll, dispid, &dispid);
   }
```

## <a name="see-also"></a>Voir aussi

- [IDispatchEx, interface](../../winscript/reference/idispatchex-interface.md)
- [IDispatchEx::GetDispID](../../winscript/reference/idispatchex-getdispid.md)
- [IDispatchEx::DeleteMemberByName](../../winscript/reference/idispatchex-deletememberbyname.md)
- [IDispatchEx::DeleteMemberByDispID](../../winscript/reference/idispatchex-deletememberbydispid.md)