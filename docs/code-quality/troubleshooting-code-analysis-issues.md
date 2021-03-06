---
title: Résolution des problèmes liés à l'analyse du code
ms.date: 11/04/2016
ms.topic: troubleshooting
ms.assetid: 61c7e44d-2780-4df5-9bcb-49e40c1152fc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e309015eda874e73213e78e90e953862d23fbe61
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55956244"
---
# <a name="troubleshooting-code-analysis-issues"></a>Résolution des problèmes liés à l'analyse du code
Cette rubrique contient des informations de résolution des problèmes suivants liés à l’analyse du code Visual Studio.

-   [Des modifications apportées à un ensemble de règles de Visual Studio 2010 ne sont pas répercutées dans les versions antérieures de Visual Studio](#ChildRuleSetChangesInPreviousVersions)

##  <a name="ChildRuleSetChangesInPreviousVersions"></a> Des modifications apportées à un ensemble de règles de Visual Studio 2010 ne sont pas répercutées dans les versions antérieures de Visual Studio
 Quand vous créez un ensemble de règles dans [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] qui contient un ensemble de règles enfant, une modification de cet ensemble de règles peut ne pas être appliquée dans les exécutions de l’analyse du code sur des ordinateurs qui utilisent une version antérieure de Visual Studio. Pour résoudre ce problème, vous devez forcer une réécriture de l’ensemble de règles parent, qui est l’ensemble de règles contenant l’ensemble de règles enfant.

1. Ouvrez l’ensemble de règles parent dans [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)].

2. Faites une modification, comme ajouter ou supprimer une règle, puis enregistrez l’ensemble de règles.

3. Rouvrez l’ensemble de règles, annulez la modification, puis réenregistrez l’ensemble de règles.

## <a name="see-also"></a>Voir aussi

- [Analyse de la qualité des applications](../code-quality/code-analysis-for-managed-code-overview.md)
- [Analyse de la qualité d’un code managé](../code-quality/code-analysis-for-managed-code-overview.md)
- [Utilisation d’ensembles de règles pour regrouper des règles d’analyse du code](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)