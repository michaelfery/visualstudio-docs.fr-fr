---
title: IEnumDebugCustomAttributes::Clone | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEnumCustomAttributes::Clone
helpviewer_keywords:
- IEnumDebugCustomAttributes::Clone
ms.assetid: e6825000-e195-42b4-b296-bfe1e533d79b
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a0cabc640329ffd6cb070cdd7550b88119185692
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58950993"
---
# <a name="ienumdebugcustomattributesclone"></a>IEnumDebugCustomAttributes::Clone
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Crée un énumérateur qui contient le même état d’énumération que l’énumérateur en cours.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Clone (   
   IEnumCustomAttributes** ppEnum  
);  
```  
  
```csharp  
int Clone(  
   out IEnumDebugCustomAttributes ppEnum  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 ppEnum  
 [out] Retourne une copie de cette énumération en tant qu’objet distinct.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="remarks"></a>Notes  
 La copie de l’énumération a le même état que l’original au moment de que cette méthode est appelée. Toutefois, les États de la copie et la version d’origine sont distincts et peuvent être modifiées individuellement.  
  
## <a name="see-also"></a>Voir aussi  
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)
