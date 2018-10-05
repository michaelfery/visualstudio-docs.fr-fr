---
title: 'CA2106 : Sécurisez les assertions | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2106
- SecureAsserts
helpviewer_keywords:
- CA2106
- SecureAsserts
ms.assetid: 91feb36e-6e2c-436c-8272-5aee31f77e98
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 67d1228b7684b2ba00a7e64f3755fb107fa0e75b
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47589975"
---
# <a name="ca2106-secure-asserts"></a>CA2106 : Assertions sécurisées
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [CA2106 : assertions sécurisées](https://docs.microsoft.com/visualstudio/code-quality/ca2106-secure-asserts).

|||
|-|-|
|TypeName|SecureAsserts|
|CheckId|CA2106|
|Category|Microsoft.Security|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Une méthode déclare une autorisation et aucune vérification de sécurité n’est exécutée sur l’appelant.

## <a name="rule-description"></a>Description de la règle
 L'assertion d'une autorisation de sécurité effectuée sans vérification de sécurité peut rendre votre code vulnérable et facile à exploiter. Un parcours de pile de sécurité s’arrête lorsqu’une autorisation de sécurité est déclarée. Si vous déclarez une autorisation sans effectuer de n’importe quel contrôle sur l’appelant, l’appelant indirectement pourrait exécuter du code à l’aide de vos autorisations. Assertions effectuées sans contrôles de sécurité sont autorisées uniquement si vous êtes certain que l’assertion ne peut pas être utilisée de façon préjudiciable. Une assertion est sans conséquence si le code que vous appelez ne présente aucun danger ou que les utilisateurs ne peuvent pas transmettre des informations arbitraires au code que vous appelez.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, ajoutez une demande de sécurité à la méthode ou son type déclarant.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Supprimer un avertissement de cette règle uniquement après un examen minutieux de la sécurité.

## <a name="see-also"></a>Voir aussi
 <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName> [Instructions de codage sécurisé](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)


