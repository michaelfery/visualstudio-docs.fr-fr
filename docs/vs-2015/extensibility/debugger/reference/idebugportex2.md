---
title: IDebugPortEx2 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugPortEx2
helpviewer_keywords:
- IDebugPortEx2 interface
ms.assetid: 144724d0-38ee-4c9b-87ca-8a504371182b
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 35a1acf88acda7a96dffc10706b8467253ae816d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58950710"
---
# <a name="idebugportex2"></a>IDebugPortEx2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Cette interface permet à la session de débogage manager (SDM) contrôle les programmes et les processus en cours d’exécution sur un port.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPortEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs  
 Un fournisseur de port personnalisé implémente cette interface sur le même objet qui implémente [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md).  
  
## <a name="notes-for-callers"></a>Notes de publication pour les appelants  
 Les appels SDM [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) sur la `IDebugPort2` interface pour obtenir cette interface.  
  
## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable  
 Le tableau suivant présente les méthodes de `IDebugPortEx2`.  
  
|Méthode|Description|  
|------------|-----------------|  
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)|Lance un fichier exécutable.|  
|[ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md)|Reprend l’exécution d’un processus.|  
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugportex2-canterminateprocess.md)|Détermine si un processus peut être arrêté.|  
|[TerminateProcess](../../../extensibility/debugger/reference/idebugportex2-terminateprocess.md)|Arrête un processus.|  
|[GetPortProcessId](../../../extensibility/debugger/reference/idebugportex2-getportprocessid.md)|Obtient l’ID de processus du port lui-même.|  
|[GetProgram](../../../extensibility/debugger/reference/idebugportex2-getprogram.md)|Obtient un programme associé à un nœud de programme.|  
  
## <a name="remarks"></a>Notes  
 Cette interface est normalement privée entre le SDM et le fournisseur de port personnalisé.  
  
 Si vous le souhaitez, un moteur de débogage (dé) peut rechercher pour cette interface sur le [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) interface transmise au [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) et utiliser [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md) pour lancer le programme. Cela n’est pas obligatoire, toutefois, et un DE faire tout ce qui est nécessaire pour lancer le programme de la demande.  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : portpriv.h  
  
 Espace de noms : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces principales](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)
