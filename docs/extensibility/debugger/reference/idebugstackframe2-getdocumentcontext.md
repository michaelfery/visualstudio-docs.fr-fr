---
title: IDebugStackFrame2::GetDocumentContext | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetDocumentContext
helpviewer_keywords:
- IDebugStackFrame2::GetDocumentContext
ms.assetid: 69e81439-1238-4f18-9028-6fd1c1ba5e4a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f4fecae2fe2398f1814b0948fd6639f234353390
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56703810"
---
# <a name="idebugstackframe2getdocumentcontext"></a>IDebugStackFrame2::GetDocumentContext
Obtient le contexte de document pour ce frame de pile.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetDocumentContext ( 
   IDebugDocumentContext2** ppCxt
);
```

```csharp
int GetDocumentContext ( 
   out IDebugDocumentContext2 ppCxt
);
```

#### <a name="parameters"></a>Paramètres
 `ppCxt`

 [out] Retourne un [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) objet qui représente la position actuelle dans un document source.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.

## <a name="remarks"></a>Notes
 Cette méthode est plus rapide que l’appel le [GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md) (méthode), puis en appelant le [GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md) méthode sur le contexte de code. Toutefois, il n’est pas garanti que chaque moteur de débogage (dé) implémente cette méthode.

## <a name="see-also"></a>Voir aussi
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
- [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)
- [GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md)
- [GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)