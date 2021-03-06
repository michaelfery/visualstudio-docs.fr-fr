---
title: IDebugPortEvents2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortEvents2
helpviewer_keywords:
- IDebugPortEvents2 interface
ms.assetid: 2c017094-3ba2-4067-83f9-147df1d96bce
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fb6a13b47013153de284ad1997a484efb3be1c98
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56712461"
---
# <a name="idebugportevents2"></a>IDebugPortEvents2
Cette interface indique à un écouteur (en général, le débogage Gestionnaire de session [SDM] ou un moteur de débogage) de la création de processus et un programme et de destruction sur un port particulier. Ces informations peuvent être utilisées pour présenter une vue en temps réel des processus et des programmes en cours d’exécution sur le port.

## <a name="syntax"></a>Syntaxe

```
IDebugPortEvents2 : IUnknown
```

## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs
 En général, Visual Studio implémente cette interface pour recevoir des notifications sur la création du programme et la destruction. Un moteur de débogage peut également implémenter cette interface pour écouter ces événements de port.

## <a name="notes-for-callers"></a>Notes de publication pour les appelants
 Tous les [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) interfaces peuvent être interrogées pour une <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> interface. Le <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer.FindConnectionPoint%2A> méthode pour `IDebugPortEvents2` est appelée le <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> interface permettant d’obtenir un <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> interface. Enfin, le <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint.Advise%2A> méthode dans le <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> interface est appelée pour envoyer des événements via le [événement](../../../extensibility/debugger/reference/idebugportevents2-event.md) (méthode).

## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable
 Le tableau suivant présente la méthode de `IDebugPortEvents2`.

|Méthode|Description|
|------------|-----------------|
|[Event](../../../extensibility/debugger/reference/idebugportevents2-event.md)|Envoie les événements qui décrivent la création et la destruction des processus et des programmes sur le port.|

## <a name="remarks"></a>Notes
 `IDebugPortEvents2` est également utilisé par le SDM pour déboguer des programmes qui s’exécutent dans un processus déjà en cours de débogage.

 Événements de port sont passés au SDM par cette interface.

## <a name="requirements"></a>Spécifications
 En-tête : msdbg.h

 Espace de noms : Microsoft.VisualStudio.Debugger.Interop

 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Interfaces de base](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)