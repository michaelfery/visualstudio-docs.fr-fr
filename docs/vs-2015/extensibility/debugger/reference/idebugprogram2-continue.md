---
title: IDebugProgram2::Continue | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProgram2::Continue
helpviewer_keywords:
- IDebugProgram2::Continue
ms.assetid: e5a6e02a-d21b-4a03-a034-e8de1f71ce2e
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c8e40b21f84aa5c244b7904331373b3120e0b4df
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58948248"
---
# <a name="idebugprogram2continue"></a>IDebugProgram2::Continue
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Continue de s’exécuter ce programme à partir d’un état arrêté. N’importe quel état de l’exécution précédente (par exemple, une étape) est conservé, et le programme commence à s’exécuter à nouveau.  
  
> [!NOTE]
>  Cette méthode est dépréciée. Utilisez le [continuer](../../../extensibility/debugger/reference/idebugprocess3-continue.md) méthode à la place.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Continue(   
   IDebugThread2* pThread  
);  
```  
  
```csharp  
int Continue(   
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pThread`  
 [in] Un [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objet qui représente le thread.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="remarks"></a>Notes  
 Cette méthode est appelée sur ce programme, quel que soit le nombre de programmes est en cours de débogage, ou le programme qui a généré l’événement de l’arrêt. L’implémentation doit conserver l’état de l’exécution précédente (par exemple, une étape) et poursuivre l’exécution comme s’il n’avait jamais arrêté avant la fin de sa précédente exécution. Autrement dit, si un thread dans ce programme a été effectuant une opération de pas à pas principal, a été arrêté, car un autre programme est arrêté, et ensuite cette méthode a été appelée, le programme doit effectuer l’opération de pas à pas principal d’origine.  
  
> [!WARNING]
>  Ne pas envoyer un événement d’arrêt ou un événement (synchrone) immédiat [événement](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) lors du traitement de cet appel ; sinon, le débogueur peut se bloquer.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
