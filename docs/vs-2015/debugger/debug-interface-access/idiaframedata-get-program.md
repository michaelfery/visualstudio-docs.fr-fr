---
title: IDiaFrameData::get_program | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_program method
ms.assetid: 9201409e-b4b1-4e2e-a9f8-d17678ac538b
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6daf5262552d056a6ac2d46a092fe94ec7510b15
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47505416"
---
# <a name="idiaframedatagetprogram"></a>IDiaFrameData::get_program
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [IDiaFrameData::get_program](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaframedata-get-program).  
  
Récupère la chaîne de programme qui est utilisée pour calculer le Registre défini avant l’appel à la fonction active.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_program (   
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pRetVal`  
 [out] Retourne la chaîne de programme.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`. Retourne `S_FALSE` si cette propriété n’est pas pris en charge. Sinon, retourne un code d'erreur.  
  
## <a name="remarks"></a>Notes  
 La chaîne de programme est une séquence de macros est interprétée afin d’établir le prologue. Par exemple, un frame de pile classique peut utiliser la chaîne de programme `"$T0 $ebp = $eip $T0 4 + ^ = $ebp $T0 ^ = $esp $T0 8 + ="`. Le format est la notation polonaise inverse, où les opérateurs suivent les opérandes. `T0` représente une variable temporaire sur la pile. Cet exemple effectue les étapes suivantes :  
  
1.  Déplacer le contenu du Registre `ebp` à `T0`.  
  
2.  Ajouter `4` à la valeur de `T0` pour produire une adresse, obtenir la valeur de cette adresse et stockez la valeur de Registre `eip`.  
  
3.  Obtenir la valeur de l’adresse stockée dans `T0` et stocker cette valeur dans le Registre `ebp`.  
  
4.  Ajouter `8` à la valeur de `T0` et stocker cette valeur dans le Registre `esp`.  
  
 Notez que la chaîne de programme est spécifique au processeur et à la convention d’appel défini pour la fonction représentée par le frame de pile actuel.  
  
## <a name="see-also"></a>Voir aussi  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)


