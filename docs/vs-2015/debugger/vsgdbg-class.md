---
title: Vsgdbg, classe | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6722263c-ccef-40c7-a0ae-87a863fbab00
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 927990cb8fb21dfeaf25a681cfb0a222ecc3c8ed
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47492902"
---
# <a name="vsgdbg-class"></a>VsgDbg, classe
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [vsgdbg, classe](https://docs.microsoft.com/visualstudio/debugger/graphics/vsgdbg-class).  
  
Représente une interface pour un contrôle par programmation du composant dans l’application de graphics diagnostics.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
class VsgDbg;  
```  
  
## <a name="members"></a>Membres  
 Le `VsgDbg` classe prend en charge les membres suivants.  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[VsgDbg::VsgDbg, constructeur](../debugger/vsgdbg-vsgdbg-constructor.md)|Construit une instance de la `VsgDbg` classe et prépare éventuellement le composant dans l’application de graphics diagnostics activement capturer et enregistrer des informations graphiques.|  
|[VsgDbg::~VsgDbg, destructeur](../debugger/vsgdbg-tilde-vsgdbg-destructor.md)|Détruit une instance de la `VsgDbg` classe.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[AddMessage](../debugger/addmessage.md)|Ajoute un message personnalisé pour les diagnostics graphiques HUD (Head-Up Display).|  
|[BeginCapture](../debugger/begincapture.md)|Commence un intervalle de capture s’achèvera par `EndCapture`.|  
|[CaptureCurrentFrame](../debugger/capturecurrentframe.md)|Capture le reste de l’image actuelle dans le fichier journal de graphiques.|  
|[Copier (capture par programmation)](../debugger/copy-programmatic-capture.md)|Copie le contenu du fichier journal (.vsglog) tracé actif dans un nouveau fichier.|  
|[EndCapture](../debugger/endcapture.md)|Met fin à un intervalle de capture a été démarré avec `BeginCapture`.|  
|[Init](../debugger/init.md)|Prépare le composant dans l’application de graphics diagnostics activement capturer et enregistrer des informations graphiques.|  
|[ToggleHUD](../debugger/togglehud.md)|Active ou désactive le segment de recouvrement graphics diagnostics HUD activé ou désactivé.|  
|[UnInit](../debugger/uninit.md)|Finalise le fichier journal de graphisme, il ferme et libère les ressources qui ont été utilisés pendant que l’application a été enregistre activement les informations graphiques.|  
  
## <a name="remarks"></a>Notes  
 Le `VsgDbg` classe représente une interface qui vous permettent de contrôler par programme les fonctionnalités graphics diagnostics. Vous pouvez utiliser certaines fonctionnalités même lorsque vous n’êtes pas activement capturer et enregistrer les informations graphiques ; Cela inclut la `AddMessage` fonction membre et `ToggleHUD` fonction membre. Les autres fonctions membres de préparer le composant dans l’application de graphics diagnostics pour démarrer ou arrêter la capture des informations graphiques actifs ou doivent être appelées pendant que l’application est activement capturer et enregistrer des informations graphiques dans un fichier journal de graphisme.


