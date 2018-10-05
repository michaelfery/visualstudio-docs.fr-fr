---
title: '&lt;assembly&gt; , élément (déploiement ClickOnce) | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assembly> element [ClickOnce deployment manifest]
ms.assetid: b8e3362a-f821-4696-b98d-571d4bbfe431
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 96978ec8329ddf31b2cc641bf02d2b38a9e98f4a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47495514"
---
# <a name="ltassemblygt-element-clickonce-deployment"></a>&lt;assembly&gt; , élément (déploiement ClickOnce)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [ &lt;assembly&gt; , élément (déploiement ClickOnce)](https://docs.microsoft.com/visualstudio/deployment/assembly-element-clickonce-deployment).  
  
Élément de niveau supérieur pour le manifeste de déploiement.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      <assembly    
   manifestVersion  
/>  
```  
  
## <a name="elements-and-attributes"></a>Éléments et attributs  
 Le `assembly` élément est l’élément racine et est obligatoire. Le premier élément de relation contenant-contenu doit être un `assemblyIdentity` élément. Les éléments du manifeste doivent être dans les espaces de noms suivants : `urn:schemas-microsoft-com:asm.v1`, `urn:schemas-microsoft-com:asm.v2`, et `http://www.w3.org/2000/09/xmldsig#`. Les éléments enfants de l’assembly doivent également être dans ces espaces de noms, par héritage ou par balisage.  
  
 Le `assembly` élément a l’attribut suivant.  
  
|Attribut|Description|  
|---------------|-----------------|  
|`manifestVersion`|Obligatoire. Cet attribut doit être défini `1.0`.|  
  
## <a name="example"></a>Exemple  
 L’exemple de code suivant illustre un `assembly` élément dans un manifeste de déploiement d’une application déployée à l’aide de [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]. Cet exemple de code fait partie d’un exemple plus complet fourni pour le [du manifeste de déploiement ClickOnce](../deployment/clickonce-deployment-manifest.md) rubrique.  
  
```  
<asmv1:assembly   
  xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd"  
  manifestVersion="1.0"  
  xmlns:asmv3="urn:schemas-microsoft-com:asm.v3"  
  xmlns:dsig=http://www.w3.org/2000/09/xmldsig#  
  xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1"  
  xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2"  
  xmlns="urn:schemas-microsoft-com:asm.v2"  
  xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"  
  xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"  
  xmlns:xrml="urn:mpeg:mpeg21:2003:01-REL-R-NS"  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Manifeste de déploiement ClickOnce](../deployment/clickonce-deployment-manifest.md)   
 [\<assembly > élément](../deployment/assembly-element-clickonce-application.md)


