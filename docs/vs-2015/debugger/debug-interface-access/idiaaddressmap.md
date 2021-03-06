---
title: IDiaAddressMap | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap interface
ms.assetid: e6467529-508c-4328-85d7-89444ae4d1c1
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 012d6b1ca06b06f56239048fee712d898a79efa9
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58950824"
---
# <a name="idiaaddressmap"></a>IDiaAddressMap
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Permet de contrôler comment le SDK DIA calcule les adresses virtuelles virtuels et relatifs pour les objets de débogage.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaAddressMap : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable  
 Le tableau suivant présente les méthodes de `IDiaAddressMap`.  
  
|Méthode|Description|  
|------------|-----------------|  
|[IDiaAddressMap::get_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)|Indique si un mappage d’adresse a été établi pour une session particulière.|  
|[IDiaAddressMap::put_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)|Spécifie si le mappage d’adresses doit être utilisé pour traduire les adresses de symbole.|  
|[IDiaAddressMap::get_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)|Indique si le calcul et l’utilisation d’adresses virtuelles relatives est activé.|  
|[IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)|Permet au client activer ou désactiver le calcul d’adresses virtuelles relatives.|  
|[IDiaAddressMap::get_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)|Récupère l’alignement de l’image actuelle.|  
|[IDiaAddressMap::put_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-put-imagealign.md)|Définit l’alignement de l’image.|  
|[IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)|Définit l’image en-têtes pour la traduction d’adresses virtuelles relatives.|  
|[IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)|Fournit un mappage d’adresses pour prendre en charge les traductions de disposition d’image.|  
  
## <a name="remarks"></a>Notes  
 Le contrôle fourni par cette interface est encapsulé dans deux jeux de données que vous fournissez : en-têtes de l’image et de mappages d’adresses. La plupart des clients utilisent le [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) méthode pour rechercher les informations de débogage appropriées pour une image et la méthode peuvent découvrir généralement toutes les données les en-têtes et les mappages nécessaires lui-même. Toutefois, certains clients implémentent spécialisées de traitement et de recherche de données. Ces clients utilisent les méthodes de la `IDiaAddressMap` interface pour fournir le DIA SDK avec les résultats de recherche.  
  
## <a name="notes-for-callers"></a>Notes de publication pour les appelants  
 Cette interface est disponible à partir de l’objet de session DIA. Le client appelle le `QueryInterface` méthode sur DIA objet interface de session, généralement [IDiaSession](../../debugger/debug-interface-access/idiasession.md), pour récupérer le `IDiaAddressMap` interface.  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : Dia2.h  
  
 Bibliothèque : diaguids.lib  
  
 DLL : msdia80.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces (Kit SDK Debug Interface Access)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
