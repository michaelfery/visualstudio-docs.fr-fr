---
title: IDebugProperty2::SetValueAsReference | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProperty2::SetValueAsReference
helpviewer_keywords:
- IDebugProperty2::SetValueAsReference method
ms.assetid: 341b1b89-4ab8-4e1c-abe2-fb955df5c6b0
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a94e3767ee05e39e847af27dc5999fa8bbbe2d44
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58948932"
---
# <a name="idebugproperty2setvalueasreference"></a>IDebugProperty2::SetValueAsReference
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Définit la valeur de cette propriété à la valeur de la référence donnée.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT SetValueAsReference(  
   IDebugReference2** rgpArgs,  
   DWORD              dwArgCount,  
   IDebugReference2*  pValue,  
   DWORD              dwTimeout  
);  
```  
  
```csharp  
int SetValueAsReference(  
   IDebugReference2[] rgpArgs,  
   uint               dwArgCount,  
   IDebugReference2   pValue,  
   uint               dwTimeout  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `rgpArgs`  
 [in] Tableau d’arguments à passer à l’accesseur de propriété de code managé. Si la méthode setter de propriété ne prend pas d’arguments ou si cette [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objet ne fait pas référence à cet un accesseur Set de propriété, `rgpArgs` doit être une valeur null. Ce paramètre est généralement une valeur null.  
  
 `dwArgCount`  
 [in] Le nombre d’arguments dans le `rgpArgs` tableau.  
  
 `pValue`  
 [in] Une référence, sous la forme d’un [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objet, à la valeur à utiliser pour définir cette propriété.  
  
 `dwTimeout`  
 [in] Combien de temps à suivre pour définir la valeur, en millisecondes. Une valeur typique est `INFINITE`. Cela affecte la durée pendant laquelle toute évaluation possible peut prendre.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne une erreur de code, généralement une des opérations suivantes :  
  
|Error|Description|  
|-----------|-----------------|  
|`E_SETVALUEASREFERENCE_NOTSUPPORTED`|Définition de la valeur à partir d’une référence n’est pas pris en charge.|  
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|Impossible de définir la valeur que cette propriété fait référence à une méthode.|  
|`E_SETVALUE_VALUE_IS_READONLY`|La valeur est en lecture seule et ne peut pas être définie.|  
|`E_NOTIMPL`|La méthode n’est pas implémentée.|  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
