---
title: Envoi des événements requis | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], required events
ms.assetid: 08319157-43fb-44a9-9a63-50b919fe1377
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 1ec13cffddda09b51a6d674f9263e4eab24444fa
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58938310"
---
# <a name="sending-the-required-events"></a>Envoi des événements nécessaires
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Utilisez cette procédure pour l’envoi des événements requis.  
  
## <a name="process-for-sending-required-events"></a>Processus d’envoi d’événements requis  
 Les événements suivants sont requis, dans cet ordre, lors de la création d’un débogage du moteur de (dé) et en l’attachant à un programme :  
  
1.  Envoyer un [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) objet d’événement pour le Gestionnaire de session de débogage (SDM) lors de l’Allemagne est initialisé pour un ou plusieurs programmes dans un processus de débogage.  
  
2.  Lorsque le programme à déboguer est attaché au, envoyer un [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) objet d’événement pour le SDM. Cet événement peut être un événement d’arrêt en cours, en fonction de votre conception de moteur.  
  
3.  Si le programme est attaché au lorsque le processus est lancé, envoyez un [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) objet d’événement pour le SDM pour notifier l’IDE du nouveau thread. Cet événement peut être un événement d’arrêt en cours, en fonction de votre conception de moteur.  
  
4.  Envoyer un [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) objet d’événement pour le SDM quand le programme en cours de débogage est terminé le chargement ou lorsque l’attacher au programme est terminée. Cet événement doit être un événement d’arrêt.  
  
5.  Si l’application à déboguer est lancée, envoyer un [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) objet d’événement pour le SDM lors de la première instruction du code dans l’architecture de l’exécution est sur le point d’être exécutée. Cet événement est toujours un arrêt. Lors de l’exécution pas à pas dans la session de débogage, l’IDE s’arrête sur cet événement.  
  
> [!NOTE]
>  De nombreux langages utilisent des initialiseurs globaux ou les fonctions externes précompilées (à partir de la bibliothèque CRT ou le _Main) au début de leur code. Si la langue du programme que vous déboguez contient un de ces types d’éléments avant le point d’entrée initial, ce code est exécuté, puis l’événement de point d’entrée est envoyé lorsque l’utilisateur point d’entrée, tel que **principal** ou `WinMain`, est atteinte.  
  
## <a name="see-also"></a>Voir aussi  
 [Activation d’un programme à déboguer](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)
