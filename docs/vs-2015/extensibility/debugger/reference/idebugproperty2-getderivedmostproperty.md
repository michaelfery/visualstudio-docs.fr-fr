---
title: IDebugProperty2::GetDerivedMostProperty | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProperty2::GetDerivedMostProperty
helpviewer_keywords:
- IDebugProperty2::GetDerivedMostProperty
ms.assetid: cc86b461-62d1-4340-8209-c65037fd8b02
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 32581e352b3f3862da326638e1645c2ad117f5ad
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47508537"
---
# <a name="idebugproperty2getderivedmostproperty"></a>IDebugProperty2::GetDerivedMostProperty
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [IDebugProperty2::GetDerivedMostProperty](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugproperty2-getderivedmostproperty).  
  
Obtient la propriété plus dérivé d’une propriété.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetDerivedMostProperty (   
   IDebugProperty2** ppDerivedMost  
);  
```  
  
```csharp  
int GetDerivedMostProperty (   
   out IDebugProperty2 ppDerivedMost  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `ppDerivedMost`  
 [out] Retourne un [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objet qui représente la propriété la plus dérivée.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon retourne le code d’erreur. Retourne `S_GETDERIVEDMOST_NO_DERIVED_MOST` s’il n’existe aucune propriété plus dérivé à récupérer.  
  
## <a name="remarks"></a>Notes  
 Par exemple, si cette propriété décrit un objet qui implémente `ClassRoot` mais qui est en fait une instanciation de `ClassDerived` qui est dérivée de `ClassRoot`, cette méthode retourne un [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objet décrivant la `ClassDerived` objet.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
