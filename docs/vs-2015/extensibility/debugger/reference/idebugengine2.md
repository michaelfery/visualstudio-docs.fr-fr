---
title: IDebugEngine2 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEngine2
helpviewer_keywords:
- IDebugEngine2 interface
ms.assetid: 1f0e9ac0-6dfb-461a-976c-888d82144cdb
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0c011a530bbd4323546257a40334a4b8a0f57bdb
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58952339"
---
# <a name="idebugengine2"></a>IDebugEngine2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Cette interface représente un moteur de débogage (dé). Il est utilisé pour gérer différents aspects d’une session de débogage, à partir de la création de points d’arrêt pour sélectionner et désélectionner des exceptions.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugEngine2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs  
 Cette interface est implémentée par un DE personnalisée pour gérer le débogage des programmes. Cette interface doit être implémentée par l’Allemagne.  
  
## <a name="notes-for-callers"></a>Notes de publication pour les appelants  
 Cette interface est appelée par le Gestionnaire de session de débogage (SDM) pour gérer la session de débogage, y compris la gestion des exceptions, la création des points d’arrêt et la réponse aux événements synchrones envoyés par le DE.  
  
## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable  
 Le tableau suivant présente les méthodes de `IDebugEngine2`.  
  
|Méthode|Description|  
|------------|-----------------|  
|[EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md)|Crée un énumérateur pour tous les programmes en cours de débogage par un DE.|  
|[Attacher](../../../extensibility/debugger/reference/idebugengine2-attach.md)|Attache un dé à un programme.|  
|[CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)|Crée un point d’arrêt en attente dans le DE.|  
|[SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)|Spécifie la façon dont le DE doit gérer une exception donnée.|  
|[RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)|Supprime l’exception spécifiée, donc il n’est n’est plus géré par le moteur de débogage.|  
|[RemoveAllSetExceptions](../../../extensibility/debugger/reference/idebugengine2-removeallsetexceptions.md)|Supprime la liste des exceptions, que l’IDE a définie pour une architecture d’exécution particulière ou une langue.|  
|[GetEngineID](../../../extensibility/debugger/reference/idebugengine2-getengineid.md)|Obtient le GUID de l’Allemagne.|  
|[DestroyProgram](../../../extensibility/debugger/reference/idebugengine2-destroyprogram.md)|Informe un dé que le programme spécifié a été arrêté anormalement et que l’Allemagne doit nettoyer toutes les références au programme et envoyer un programme détruire l’événement.|  
|[ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)|Appelé par le SDM pour indiquer qu’un événement de débogage synchrone, précédemment envoyé par le DE pour le SDM, a été reçu et traité.|  
|[SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md)|Définit les paramètres régionaux de l’Allemagne.|  
|[SetRegistryRoot](../../../extensibility/debugger/reference/idebugengine2-setregistryroot.md)|Définit la racine de Registre actuellement en cours d’utilisation par l’Allemagne.|  
|[SetMetric](../../../extensibility/debugger/reference/idebugengine2-setmetric.md)|Définit une mesure.|  
|[CauseBreak](../../../extensibility/debugger/reference/idebugengine2-causebreak.md)|Demande que tous les programmes en cours de débogage par cette D’arrête l’exécution de la prochaine fois qu’un de ses threads tente de s’exécuter.|  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : Msdbg.h  
  
 Espace de noms : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Événement](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [GetEngine](../../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md)
