---
title: 'Erreur : Vous n’êtes pas autorisé à inspecter le processus&#39;identité de s | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: troubleshooting
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 25d0a0be957cc06be75e48432a96357146671926
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56688080"
---
# <a name="error-you-do-not-have-permission-to-inspect-the-process39s-identity"></a>Erreur : Vous n’êtes pas autorisé à inspecter le processus&#39;identité de s
Vous n'êtes pas autorisé à inspecter l'identité du processus. Cela peut être dû à la configuration de votre système.

 Le débogueur n'a pas pu inspecter l'identité du processus, qui contient des informations nécessaires au débogage. La cause la plus probable est la désactivation des services Terminal Server. Les services Terminal Server sont activés par défaut. Pour les réactiver, procédez comme suit.

### <a name="to-enable-terminal-services"></a>Pour activer les services Terminal Server

1.  Cliquez sur **Démarrer**, puis choisissez **Panneau de configuration**.

2.  Dans le Panneau de configuration, sélectionnez si nécessaire **Basculer vers l’affichage classique**, puis double-cliquez sur **Outils d’administration**.

3.  Dans la fenêtre **Outils d’administration**, double-cliquez sur **Gestion de l’ordinateur**.

4.  Dans la fenêtre Gestion de l’ordinateur, développez le nœud **Services et applications**.

5.  Sous **Services et applications**, cliquez sur **Services**.

     Une liste de services apparaît dans le volet droit.

6.  Dans la liste **Services**, cliquez avec le bouton droit sur **Services Terminal Server**, puis choisissez **Propriétés**.

7.  Dans le **propriétés des Services Terminal Server** fenêtre, accédez à la **général** onglet et définissez **type de démarrage** à **manuel**.

8.  Cliquez sur **OK**.

9. Redémarrez l'ordinateur.

     Cette procédure n'active pas automatiquement le Bureau à distance. Pour activer le Bureau à distance sur votre ordinateur, effectuez la procédure supplémentaire suivante.

### <a name="to-enable-remote-desktop"></a>Pour activer le Bureau à distance

1.  Cliquez sur **Démarrer**, puis cliquez avec le bouton droit sur **Poste de travail**.

2.  Choisissez **Propriétés**.

     La fenêtre **Propriétés système** s’affiche.

3.  Cliquez sur **À distance**.

4.  Sous **Bureau à distance**, sélectionnez **Autoriser les utilisateurs à se connecter à distance à cet ordinateur**.

5.  Cliquez sur **OK**.

## <a name="see-also"></a>Voir aussi
- [Erreurs et résolution des problèmes du débogage distant](../debugger/remote-debugging-errors-and-troubleshooting.md)