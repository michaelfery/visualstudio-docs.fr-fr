---
title: IDebugDocumentPositionOffset2 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentPositionOffset2 interface
ms.assetid: f1b05db3-50d8-453f-a72f-e68b239236a4
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c1f30c3a465d4803e5c91f14ee45ad582e76d986
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58938101"
---
# <a name="idebugdocumentpositionoffset2"></a>IDebugDocumentPositionOffset2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Représente une position dans un fichier source par un offset de caractère.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugDocumentPositionOffset2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs  
 Implémentée par l’IDE et utilisée par les moteurs de débogage.  
  
## <a name="methods"></a>Méthodes  
 Le tableau suivant présente les méthodes de `IDebugDocumentPositionOffset2`.  
  
|Méthode|Description|  
|------------|-----------------|  
|[GetRange](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2-getrange.md)|Récupère la plage pour la position actuelle du document.|  
  
## <a name="remarks"></a>Notes  
 Cela retourne les mêmes informations que [GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md) mais, dans `char` offsets à partir du début du document. Cela pose le document comme il existe sur un disque, autrement dit, un tableau unidimensionnel de caractères, plutôt que les informations de ligne et la colonne est retournée normalement.  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : Msdbg.h  
  
 Espace de noms : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)
