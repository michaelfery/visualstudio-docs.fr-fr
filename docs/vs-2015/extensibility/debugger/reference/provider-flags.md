---
title: PROVIDER_FLAGS | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- PROVIDER_FLAGS
helpviewer_keywords:
- PROVIDER_FLAGS enumeration
ms.assetid: 8cbd2312-ed2f-4477-b192-c3f25c6098c3
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c39aa316308f313bf23ef2c5680671585636f0a5
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58948491"
---
# <a name="providerflags"></a>PROVIDER_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Spécifie les propriétés souhaitées doivent être obtenues à partir d’un fournisseur de programme.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_PROVIDER_FLAGS {  
   PFLAG_NONE                    = 0x00,  
   PFLAG_REMOTE_PORT             = 0x01,  
   PFLAG_DEBUGGEE                = 0x02,  
   PFLAG_ATTACHED_TO_DEBUGGEE    = 0x04,  
   PFLAG_REASON_WATCH            = 0x08,  
   PFLAG_GET_PROGRAM_NODES       = 0x10,  
   PFLAG_GET_IS_DEBUGGER_PRESENT = 0x20  
};  
typedef DWORD PROVIDER_FLAGS;  
```  
  
```csharp  
public enum enum_PROVIDER_FLAGS {  
   PFLAG_NONE                    = 0x00,  
   PFLAG_REMOTE_PORT             = 0x01,  
   PFLAG_DEBUGGEE                = 0x02,  
   PFLAG_ATTACHED_TO_DEBUGGEE    = 0x04,  
   PFLAG_REASON_WATCH            = 0x08,  
   PFLAG_GET_PROGRAM_NODES       = 0x10,  
   PFLAG_GET_IS_DEBUGGER_PRESENT = 0x20  
};  
```  
  
## <a name="members"></a>Membres  
 PFLAG_NONE  
 Aucun indicateur n’est spécifié.  
  
 PFLAG_REMOTE_PORT  
 L’appelant veut une liste des programmes sur un ordinateur différent de celui [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
 PFLAG_DEBUGGEE  
 Le processus est en cours de débogage par cette instance de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
 PFLAG_ATTACH_TODEBUGGEE  
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] n’est attaché au programme en cours de débogage, mais ne la démarre pas.  
  
 PFLAG_REASON_WATCH  
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] surveille les événements.  
  
 PFLAG_GET_PROGRAM_NODES  
 L’appelant veut le `ProgramNodes` champ la [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md) structure.  
  
 PFLAG_GET_IS_DEBUGGER_PRESENT  
 L’appelant veut le `fIsTheDebuggerPresent` champ la `PROVIDER_PROCESS_DATA` structure.  
  
## <a name="remarks"></a>Notes  
 Ces indicateurs sont passées aux méthodes suivantes :  
  
- [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)  
  
- [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)  
  
- [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)  
  
  Ces valeurs peuvent être combinées avec un opérateur de bits `OR`.  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : msdbg.h  
  
 Espace de noms : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Énumérations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md)   
 [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)   
 [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)   
 [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)
