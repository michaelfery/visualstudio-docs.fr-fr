---
title: '&lt;publisherIdentity&gt; , élément (déploiement ClickOnce) | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publisherIdentity Element [ClickOnce deployment manifest], introduction
- required element for signed manifests [ClickOnce], publisherIdentity Element
- publisherIdentity Element [ClickOnce deployment manifest], syntax, elements, and attributes
ms.assetid: 34c579db-d2f2-4b66-b9c8-47207f33d950
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 995b002784c1e76ceed36e51edb1ae893448f448
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56628440"
---
# <a name="ltpublisheridentitygt-element-clickonce-deployment"></a>&lt;publisherIdentity&gt; , élément (déploiement ClickOnce)
Contient des informations sur l'éditeur qui a signé ce manifeste de déploiement.

## <a name="syntax"></a>Syntaxe

```xml
<publisherIdentity
   name
   issuerKeyHash
/>
```

## <a name="elements-and-attributes"></a>Éléments et attributs
 Le `publisherIdentity` élément est requis pour les manifestes signés. Le tableau suivant montre les attributs que le `publisherIdentity` élément prend en charge.

|Attribut|Description|
|---------------|-----------------|
|`name`|Obligatoire. Décrit l’identité du tiers qui a publié cette application.|
|`issuerKeyHash`|Obligatoire. Contient le hachage SHA-1 de la clé publique de l’émetteur du certificat.|

#### <a name="parameters"></a>Paramètres

## <a name="property-valuereturn-value"></a>Valeur de propriété/valeur de retour

## <a name="exceptions"></a>Exceptions

## <a name="remarks"></a>Remarques

## <a name="requirements"></a>Spécifications

## <a name="subhead"></a>Sous-titre