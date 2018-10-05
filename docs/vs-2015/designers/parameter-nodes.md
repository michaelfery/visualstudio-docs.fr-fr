---
title: Nœuds de paramètre | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da54db0b-3a3d-48dc-858c-7ac43aa04b13
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bed941a35af21b78ea5159a218ccd36d2ff5f1e9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47516778"
---
# <a name="parameter-nodes"></a>Nœuds de paramètre
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [les nœuds de paramètre](https://docs.microsoft.com/visualstudio/designers/parameter-nodes).  
  
Dans le concepteur de nuanceur, les nœuds de paramètre représentent les entrées dans le nuanceur qui sont sous le contrôle de l’application dessin par dessin, par exemple, les propriétés de matériau, les lumières directionnelles et la position de la caméra. Comme vous pouvez modifier ces paramètres à chaque appel de dessin, vous pouvez utiliser le même nuanceur pour attribuer différentes apparences à un objet.  
  
## <a name="parameter-node-reference"></a>Informations de référence des nœuds de paramètre  
  
|Nœud|Détails|Properties|  
|----------|-------------|----------------|  
|**Position universelle de la caméra**|Position de l'appareil photo dans l'espace universel.<br /><br /> **Sortie :**<br /><br /> `Output`: `float4`<br /> Position de la caméra.|Aucun.|  
|**Direction de la lumière**|Vecteur qui définit la direction dans laquelle la lumière est diffusée depuis une source de lumière dans l’espace universel.<br /><br /> Vous pouvez l’utiliser pour calculer les contributions spéculaires et d’éclairage dans l’espace universel.<br /><br /> **Sortie :**<br /><br /> `Output`: `float3`<br /> Vecteur du pixel actuel à une source de lumière.|Aucun.|  
|**Matériau ambiant**|Contribution de couleur diffuse du pixel actuel qui est attribuée à l’éclairage indirect.<br /><br /> La couleur diffuse d’un pixel simule l’interaction de l’éclairage avec des surfaces rugueuses. Vous pouvez utiliser le paramètre Matériau ambiant pour estimer la contribution de l’éclairage indirect à l’apparence d’un objet dans le monde réel.<br /><br /> **Sortie :**<br /><br /> `Output`: `float4`<br /> Couleur diffuse du pixel actuel qui est due à l’éclairage indirect, c’est-à-dire à la lumière ambiante.|**Accès**<br /> **Public** pour que la propriété puisse être définie dans l’éditeur de modèle. **Privé** dans le cas contraire.<br /><br /> **Valeur**<br /> Couleur diffuse du pixel actuel qui est due à l’éclairage indirect, c’est-à-dire à la lumière ambiante.|  
|**Matériau diffus**|Couleur qui décrit la manière dont le pixel actuel diffuse la lumière directe.<br /><br /> La couleur diffuse d’un pixel simule l’interaction de l’éclairage avec des surfaces rugueuses. Vous pouvez utiliser le paramètre Matériau diffus pour modifier la façon dont le pixel actuel diffuse la lumière directe, c’est-à-dire les lumières directionnelles, ponctuelles et projetées.<br /><br /> **Sortie :**<br /><br /> `Output`: `float4`<br /> Couleur qui décrit la manière dont le pixel actuel diffuse la lumière directe.|**Accès**<br /> **Public** pour que la propriété puisse être définie dans l’éditeur de modèle. **Privé** dans le cas contraire.<br /><br /> **Valeur**<br /> Couleur qui décrit la manière dont le pixel actuel diffuse la lumière directe.|  
|**Matériau émissif**|Contribution de couleur du pixel actuel qui est attribuée à son éclairage propre.<br /><br /> Vous pouvez l’utiliser pour simuler un objet lumineux, autrement dit, un objet qui fournit sa propre lumière. Cette lumière n’affecte pas les autres objets.<br /><br /> **Sortie :**<br /><br /> `Output`: `float4`<br /> Contribution de couleur du pixel actuel, basée sur l’auto-éclairage.|**Accès**<br /> **Public** pour que la propriété puisse être définie dans l’éditeur de modèle. **Privé** dans le cas contraire.<br /><br /> **Valeur**<br /> Contribution de couleur du pixel actuel, basée sur l’auto-éclairage.|  
|**Matériau spéculaire**|Couleur qui décrit la manière dont le pixel actuel reflète la lumière directe.<br /><br /> La couleur spéculaire d’un pixel simule l’interaction de l’éclairage avec des surfaces lisses, de type miroir. Vous pouvez utiliser le paramètre Matériau spéculaire pour modifier la façon dont le pixel actuel reflète la lumière directe, c’est-à-dire les lumières directionnelles, ponctuelles et projetées.<br /><br /> **Sortie :**<br /><br /> `Output`: `float4`<br /> Couleur qui décrit la manière dont le pixel actuel reflète la lumière directe.|**Accès**<br /> **Public** pour que la propriété puisse être définie dans l’éditeur de modèle. **Privé** dans le cas contraire.<br /><br /> **Valeur**<br /> Couleur qui décrit la manière dont le pixel actuel reflète la lumière directe.|  
|**Puissance spéculaire du matériau**|Valeur scalaire qui décrit l'intensité des surbrillances spéculaires.<br /><br /> L’intensité et la portée des surbrillances spéculaires sont proportionnelles à la puissance spéculaire.<br /><br /> **Sortie :**<br /><br /> `Output`: `float`<br /> Terme exponentiel qui décrit l’intensité des surbrillances spéculaires sur le pixel actuel.|**Accès**<br /> **Public** pour que la propriété puisse être définie dans l’éditeur de modèle. **Privé** dans le cas contraire.<br /><br /> **Valeur**<br /> Exposant qui définit l’intensité des surbrillances spéculaires sur le pixel actuel.|  
|**Heure normalisée**|Durée en secondes, normalisée dans la plage [0, 1] de sorte que lorsque la durée atteint 1, elle est réinitialisée sur 0.<br /><br /> Vous pouvez l’utiliser en tant que paramètre dans les calculs du nuanceur, par exemple pour animer les coordonnées de la texture, les valeurs de couleur ou d’autres attributs.<br /><br /> **Sortie :**<br /><br /> `Output`: `float`<br /> Heure normalisée, en secondes.|Aucun.|  
|**Heure**|La durée en secondes.<br /><br /> Vous pouvez l’utiliser en tant que paramètre dans les calculs du nuanceur, par exemple pour animer les coordonnées de la texture, les valeurs de couleur ou d’autres attributs.<br /><br /> **Sortie :**<br /><br /> `Output`: `float`<br /> Durée en secondes.|Aucun.|


