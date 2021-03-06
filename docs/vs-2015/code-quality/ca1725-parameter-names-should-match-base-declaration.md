---
title: 'CA1725 : Les noms de paramètre doivent correspondre à la déclaration de base | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ParameterNamesShouldMatchBaseDeclaration
- CA1725
helpviewer_keywords:
- CA1725
- ParameterNamesShouldMatchBaseDeclaration
ms.assetid: 9b657ab0-fe81-4f4c-9481-ba746988c922
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e97431b46640fb8241d6bde80d09d38084650be8
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58952947"
---
# <a name="ca1725-parameter-names-should-match-base-declaration"></a>CA1725 : Les noms des paramètres doivent correspondre à la déclaration de base
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ParameterNamesShouldMatchBaseDeclaration|
|CheckId|CA1725|
|Category|Microsoft.Naming|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Le nom d’un paramètre dans une substitution de méthode visible de l’extérieur ne correspond pas au nom du paramètre dans la déclaration de base de la méthode ou le nom du paramètre dans la déclaration d’interface de la méthode.

## <a name="rule-description"></a>Description de la règle
 La désignation cohérente des paramètres dans une hiérarchie de substitution augmente la facilité d'utilisation des substitutions de méthode. Un nom de paramètre dans une méthode dérivée qui diffère du nom dans la déclaration de base peut créer une confusion pour déterminer si la méthode est une substitution de la méthode de base ou une nouvelle surcharge de la méthode.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, renommez le paramètre pour correspondre à la déclaration de base. Le correctif est une modification avec rupture pour les méthodes visibles par COM.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez pas un avertissement de cette règle à l’exception des méthodes visibles par COM dans les bibliothèques fournies antérieurement.
