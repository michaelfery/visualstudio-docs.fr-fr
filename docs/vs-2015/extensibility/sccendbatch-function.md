---
title: Fonction SccEndBatch | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccEndBatch
helpviewer_keywords:
- SccEndBatch function
ms.assetid: 100e7833-fe0a-45c0-9fca-3e61fd1165b7
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 075e661976062d2de985fa52110ea87840c2ab21
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47495110"
---
# <a name="sccendbatch-function"></a>Fonction SccEndBatch
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [fonction SccEndBatch](https://docs.microsoft.com/visualstudio/extensibility/sccendbatch-function).  
  
Cette fonction termine un lot d’opérations de contrôle de code source. Ces lots ne peuvent pas être imbriqués.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
SCCRTN SccEndBatch(void);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Aucun.  
  
## <a name="return-value"></a>Valeur de retour  
 L’implémentation de plug-in de contrôle de source de cette fonction est censée retourner l’une des valeurs suivantes :  
  
|Value|Description|  
|-----------|-----------------|  
|SCC_OK|Lot d’opérations conclu avec succès.|  
|SCC_E_UNKNOWNERROR|Erreur non spécifique.|  
  
## <a name="remarks"></a>Notes  
 Lots de contrôle source sont utilisés pour exécuter les mêmes opérations de contrôle de source entre plusieurs projets ou de plusieurs contextes. Lots peuvent être utilisés pour éliminer les boîtes de dialogue redondante à partir de l’expérience utilisateur lors d’une opération par lot. Le [SccBeginBatch](../extensibility/sccbeginbatch-function.md) et `SccEndBatch` (fonction) sont utilisés en tant que paire pour indiquer le début et la fin d’une opération. Ils ne peuvent pas être imbriquées.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions d’API de plug-in de contrôle de source](../extensibility/source-control-plug-in-api-functions.md)   
 [SccBeginBatch](../extensibility/sccbeginbatch-function.md)
