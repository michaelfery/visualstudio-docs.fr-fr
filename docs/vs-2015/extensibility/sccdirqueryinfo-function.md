---
title: Fonction SccDirQueryInfo | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccDirQueryInfo
helpviewer_keywords:
- SccDirQueryInfo function
ms.assetid: 459e2d99-573d-47c4-b834-6d82c5e14162
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b86ac7c701f96d467f0c059fc7e4b732699b1da5
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58947196"
---
# <a name="sccdirqueryinfo-function"></a>Fonction SccDirQueryInfo
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cette fonction examine une liste de répertoires complets pour leur état actuel.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
SCCRTN SccDirQueryInfo(  
LPVOID  pContext,  
LONG    nDirs,  
LPCSTR* lpDirNames,  
LPLONG  lpStatus  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 pContext  
 [in] La structure de contexte de plug-in de contrôle de source.  
  
 nDirs  
 [in] Le nombre de répertoires sélectionnés à interroger.  
  
 lpDirNames  
 [in] Un tableau des chemins qualifiés complets des répertoires à interroger.  
  
 lpStatus  
 [in, out] Une structure de tableau pour le plug-in pour retourner les indicateurs d’état de contrôle de code source (consultez [Code d’état Directory](../extensibility/directory-status-code-enumerator.md) pour plus d’informations).  
  
## <a name="return-value"></a>Valeur de retour  
 L’implémentation de plug-in de contrôle de source de cette fonction est censée retourner l’une des valeurs suivantes :  
  
|Value|Description|  
|-----------|-----------------|  
|SCC_OK|La requête a réussi.|  
|SCC_E_OPNOTSUPPORTED|Le système de contrôle de code source ne prend pas en charge cette opération.|  
|SCC_E_ACCESSFAILURE|Impossible d’accéder au système de contrôle source, probablement en raison de problèmes réseau ou de contention. Une nouvelle tentative est recommandée.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Erreur non spécifique.|  
  
## <a name="remarks"></a>Notes  
 La fonction remplit le tableau de résultats avec un masque de bits de bits à partir de la `SCC_DIRSTATUS` famille (consultez [Code d’état Directory](../extensibility/directory-status-code-enumerator.md)), une entrée pour chaque répertoire donné. Le tableau de statut est alloué par l’appelant.  
  
 L’IDE utilise cette fonction avant qu’un répertoire est renommé pour vérifier si le répertoire est sous contrôle de code source en interrogeant si elle possède un projet correspondant. Si le répertoire n’est pas sous contrôle de code source, l’IDE peut fournir l’avertissement approprié à l’utilisateur.  
  
> [!NOTE]
>  Si un plug-in de contrôle de code source choisit de n'implémenter pas une ou plusieurs valeurs d’état, non implémentées bits doivent être définis sur zéro.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions d’API de plug-in de contrôle de source](../extensibility/source-control-plug-in-api-functions.md)   
 [Code d’état de répertoire](../extensibility/directory-status-code-enumerator.md)
