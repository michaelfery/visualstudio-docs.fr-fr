---
title: Nœuds de texture | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7df5ef3-dd4f-4964-9d96-34e0e180515e
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 05bf4ecfcdd41815345c9f8ed6a5293723af799d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47506598"
---
# <a name="texture-nodes"></a>Nœuds de texture
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [nœuds de Texture](https://docs.microsoft.com/visualstudio/designers/texture-nodes).  
  
Dans le concepteur de nuanceur, les nœuds de texture échantillonnent différents types de texture ainsi que des géométries, et produisent ou transforment des coordonnées de texture. Les textures apportent des détails de couleur et d’éclairage aux objets.  
  
## <a name="texture-node-reference"></a>Informations de référence des nœuds de texture  
  
|Nœud|Détails|Properties|  
|----------|-------------|----------------|  
|**Cubemap Sample (Exemple de carte cubique)**|Extrait un échantillon de couleur d’une carte cubique aux coordonnées spécifiées.<br /><br /> Vous pouvez utiliser une carte cubique pour fournir un détail de couleur pour les effets de réflexion ou pour appliquer à un objet sphérique une texture avec moins de distorsion qu’une texture 2D.<br /><br /> **Entrée :**<br /><br /> `UVW`: `float3`<br /> Vecteur qui spécifie l’emplacement de l’extraction de l’échantillon sur le cube de texture. L’échantillon est prélevé à l’intersection de ce vecteur et du cube.<br /><br /> **Sortie :**<br /><br /> `Output`: `float4`<br /> Échantillon de couleur.|**Texture**<br /> Registre de texture associé à l’échantillonneur.|  
|**Normal Map Sample (Exemple de carte de normales)**|Extrait un échantillon de normale d’une carte de normales 2D aux coordonnées spécifiées.<br /><br /> Vous pouvez utiliser une carte de normales pour simuler l’apparence de détails géométriques supplémentaires sur la surface d’un objet. Les cartes de normales contiennent des données compressées qui représentent un vecteur unitaire et non des données de couleur.<br /><br /> **Entrée :**<br /><br /> `UV`: `float2`<br /> Coordonnées de l’emplacement auquel l’échantillon est prélevé.<br /><br /> **Sortie :**<br /><br /> `Output`: `float3`<br /> Échantillon de normale.|**Axis Adjustment (Ajustement d’un axe)**<br /> Facteur utilisé pour ajuster la latéralisation gauche/droite de l’échantillon de carte de normales.<br /><br /> **Texture**<br /> Registre de texture associé à l’échantillonneur.|  
|**UV Panoramique**|Effectue un panoramique des coordonnées de texture spécifiées en tant que fonction du temps.<br /><br /> Vous pouvez l’utiliser pour déplacer une carte de textures ou de normales sur la surface d’un objet.<br /><br /> **Entrée :**<br /><br /> `UV`: `float2`<br /> Coordonnées sur lesquelles effectuer un panoramique.<br /><br /> `Time`: `float`<br /> Durée du panoramique, en secondes.<br /><br /> **Sortie :**<br /><br /> `Output`: `float2`<br /> Coordonnées auxquelles est appliqué un panoramique.|**Vitesse X**<br /> Nombre de texels panoramiqués le long de l'axe des abcisses, par seconde.<br /><br /> **Vitesse Y**<br /> Nombre de texels panoramiqués le long de l'axe des ordonnées, par seconde.|  
|**UV Parallaxe**|Déplace les coordonnées de texture spécifiées en tant que fonction de la hauteur et de l’angle de visualisation.<br /><br /> L’effet créé est appelé *mappage parallaxe* ou mappage de déplacement virtuel. Vous pouvez l’utiliser pour créer une illusion de profondeur sur une surface plane.<br /><br /> **Entrée :**<br /><br /> `UV`: `float2`<br /> Coordonnées à déplacer.<br /><br /> `Height`: `float`<br /> Valeur de la carte du relief qui est associée aux coordonnées `UV`.<br /><br /> **Sortie :**<br /><br /> `Output`: `float2`<br /> Coordonnées déplacées.|**Plan de profondeur**<br /> Profondeur de référence de l’effet parallaxe. Par défaut, sa valeur est égale à 0,5. Des valeurs plus petites soulèvent la texture, tandis que des valeurs supérieures l’enfoncent dans la surface.<br /><br /> **Échelle de profondeur**<br /> Échelle de l’effet parallaxe. La profondeur apparente est ainsi rendue plus ou moins prononcée. Les valeurs standard sont inscrites dans la plage s’étendant de 0,02 à 0,1.|  
|**Faire pivoter UV**|Effectue une rotation des coordonnées de texture spécifiées autour d’un point central en tant que fonction du temps.<br /><br /> Vous pouvez l’utiliser pour faire tourner une carte de textures ou de normales sur la surface d’un objet.<br /><br /> **Entrée :**<br /><br /> `UV`: `float2`<br /> Coordonnées à faire pivoter.<br /><br /> `Time`: `float`<br /> Durée du panoramique, en secondes.<br /><br /> **Sortie :**<br /><br /> `Output`: `float2`<br /> Coordonnées ayant subi une rotation.|**Centrer X**<br /> Coordonnée x qui définit le centre de rotation.<br /><br /> **Centrer Y**<br /> Coordonnée y qui définit le centre de rotation.<br /><br /> **Vitesse**<br /> Angle, en radians, en fonction duquel la texture pivote chaque seconde.|  
|**Coordonnée de texture**|Coordonnées de texture du pixel actuel.<br /><br /> Les coordonnées de texture sont déterminées par interpolation entre les attributs de coordonnées de texture des sommets voisins. Vous pouvez considérer cela comme position du pixel actuel dans l’espace de texture.<br /><br /> **Sortie :**<br /><br /> `Output`: `float2`<br /> Coordonnées de texture.|Aucun.|  
|**Dimensions de la texture**|Génère la largeur et la hauteur d’une carte de textures 2D.<br /><br /> Vous pouvez utiliser les dimensions de texture pour prendre en compte la largeur et la hauteur de la texture dans un nuanceur.<br /><br /> **Sortie :**<br /><br /> `Output`: `float2`<br /> Largeur et hauteur de la texture, exprimées en tant que vecteur. La largeur est stockée dans le premier élément du vecteur. La hauteur est stockée dans le second élément.|**Texture**<br /> Registre de texture associé aux dimensions de la texture.|  
|**Différentiel d’élément de texture**|Génère le différentiel (la distance) entre les éléments de texture d’une carte de textures 2D.<br /><br /> Vous pouvez utiliser le différentiel d’élément de texture pour échantillonner des valeurs d’éléments de texture voisins dans un nuanceur.<br /><br /> **Sortie :**<br /><br /> `Output`: `float2`<br /> Différentiel (distance) d’un élément de texture à l’élément de texture suivant (déplacement en diagonale dans le sens positif), exprimé sous la forme d’un vecteur dans un espace de texture normalisé. Vous pouvez dériver les positions de tous les éléments de texture voisins en ignorant ou en inversant de manière sélective les coordonnées U ou V du différentiel.|**Texture**<br /> Registre de texture associé au différentiel d’élément de texture.|  
|**Échantillon de texture**|Extrait un échantillon de couleur d’une carte de textures 2D aux coordonnées spécifiées.<br /><br /> Vous pouvez utiliser une carte de textures pour ajouter un détail de couleur à la surface d’un objet.<br /><br /> **Entrée :**<br /><br /> `UV`: `float2`<br /> Coordonnées de l’emplacement auquel l’échantillon est prélevé.<br /><br /> **Sortie :**<br /><br /> `Output`: `float4`<br /> Échantillon de couleur.|**Texture**<br /> Registre de texture associé à l’échantillonneur.|


