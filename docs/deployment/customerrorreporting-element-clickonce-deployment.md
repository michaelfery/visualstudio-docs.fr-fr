---
title: '&lt;customErrorReporting&gt; , élément (déploiement ClickOnce) | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <customErrorReporting> element [ClickOnce deployment manifest]
ms.assetid: 7d31816e-c692-46b5-9cc9-753284b3bcda
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6d42bd1f7304d9f50b6334d9ac8ddd4f626605d2
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56629454"
---
# <a name="ltcustomerrorreportinggt-element-clickonce-deployment"></a>&lt;customErrorReporting&gt; , élément (déploiement ClickOnce)
Spécifie un URI à afficher en cas d'erreur.

## <a name="syntax"></a>Syntaxe

```xml
<customErrorReporting
   uri
/>
```

## <a name="remarks"></a>Remarques
 Cet élément est facultatif. Sans cela, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] affiche une boîte de dialogue d’erreur indiquant la pile d’exception. Si le `customErrorReporting` élément est présent, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] affiche l’URI indiqué par le `uri` paramètre. L’URI cible inclut la classe d’exception externe, la classe d’exception interne et le message d’exception interne en tant que paramètres.

 Utilisez cet élément pour ajouter le rapport d’erreurs des fonctionnalités à votre application. Étant donné que l’URI généré inclut des informations sur le type d’erreur, votre site Web peut analyser ces informations et afficher, par exemple, un écran de dépannage approprié.

## <a name="example"></a>Exemple
 L’extrait de code suivant montre le `customErrorReporting` élément, ainsi que l’URI généré qu’il peut produire.

```xml
<customErrorReporting uri=http://www.contoso.com/applications/error.asp />

Example Generated Error:
http://www.contoso.com/applications/error.asp? outer=System.Deployment.Application.InvalidDeploymentException&&inner=System.Deployment.Application.InvalidDeploymentException&&msg=The%20application%20manifest%20is%20signed,%20but%20the%20deployment%20manifest%20is%20unsigned.%20Both%20manifests%20must%20be%20either%20signed%20or%20unsigned.
```

## <a name="see-also"></a>Voir aussi
- [Manifeste de déploiement ClickOnce](../deployment/clickonce-deployment-manifest.md)