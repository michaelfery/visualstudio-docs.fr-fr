---
title: IDiaSession::findChildren | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findChildren method
ms.assetid: 5d19046f-f668-4aa9-8788-95cda9a98997
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c5759d810bf9180522508a6be54e5c94ffcfadb3
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56643078"
---
# <a name="idiasessionfindchildren"></a>IDiaSession::findChildren
Récupère tous les enfants d’un identificateur du parent spécifié qui correspondent au type de nom et le symbole.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT findChildren ( 
   IDiaSymbol*       parent,
   SymTagEnum        symtag,
   LPCOLESTR         name,
   DWORD             compareFlags,
   IDiaEnumSymbols** ppResult
);
```

#### <a name="parameters"></a>Paramètres
 `parent`

[in] Un [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) objet représentant le parent. Si ce symbole parent est une fonction, un module ou un bloc, ses enfants lexicales sont retournées dans `ppResult`. Si le symbole de parent est un type, ses enfants de la classe sont retournées. Si ce paramètre est `NULL`, puis `symtag` doit être définie sur `SymTagExe` ou `SymTagNull`, qui retourne la portée globale (fichier .exe).

 `symtag`

[in] Spécifie la balise de symbole des enfants à récupérer. Les valeurs sont extraites à partir de la [SymTagEnum (énumération)](../../debugger/debug-interface-access/symtagenum.md) énumération. La valeur `SymTagNull` pour récupérer tous les enfants.

 `name`

[in] Spécifie le nom des enfants à récupérer. La valeur `NULL` pour tous les enfants doivent être récupérées.

 `compareFlags`

[in] Spécifie les options de comparaison appliquées à la correspondance de noms. Les valeurs de la [NameSearchOptions (énumération)](../../debugger/debug-interface-access/namesearchoptions.md) énumération peut être utilisée seul ou combiné.

 `ppResult`

[out] Retourne un [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) de récupérer l’objet qui contient la liste des symboles de l’enfant.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.

## <a name="example"></a>Exemple
 L’exemple suivant montre comment rechercher des variables locales de fonction `pFunc` ce nom de la correspondance `szVarName`.

```C++
IDiaEnumSymbols* pEnum;
pSession->findChildren( pFunc, SymTagData, szVarName, nsCaseSensitive, &pEnum );
```

## <a name="see-also"></a>Voir aussi
- [Vue d’ensemble](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [NameSearchOptions, énumération](../../debugger/debug-interface-access/namesearchoptions.md)
- [SymTagEnum, énumération](../../debugger/debug-interface-access/symtagenum.md)