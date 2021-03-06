---
title: Ajouter des paramètres d’exécution à un test de charge
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, run settings, adding
- load tests, run settings
ms.assetid: 257d2a24-d582-4cfe-8b2b-51f51ba9cc84
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: bd5a7183589255d246fd299b9ec628330d948dcf
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55917543"
---
# <a name="how-to-add-additional-run-settings-to-a-load-test"></a>Procédure : ajouter des paramètres d’exécution supplémentaires à un test de charge

Les paramètres d'exécution d'un test de charge déterminent d'autres paramètres. Ceux-ci incluent la durée du test, le niveau de détail de la collection des résultats et les ensembles de compteurs collectés pendant l'exécution des tests. Vous pouvez créer et stocker plusieurs paramètres d'exécution pour chaque test de charge, puis sélectionner un paramètre particulier à utiliser lors de l'exécution du test. Un paramètre d’exécution initial est ajouté à votre test de charge lors de la création de ce dernier à l’aide de **l’Assistant Nouveau test de charge**.

Vous pouvez ajouter davantage de paramètres d'exécution à votre test de charge avec divers paramètres de propriété afin de pouvoir exécuter le test de charge dans différentes conditions, par exemple, vous pouvez ajouter un nouveau paramètre de test et utiliser un taux d'échantillonnage distinct, ou vous pouvez spécifier une plus longue durée d'exécution. Vous ne pouvez utiliser qu'un seul paramètre d'exécution à la fois et vous devez spécifier le paramètre d'exécution à utiliser en le marquant comme actif.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-add-another-run-setting"></a>Pour ajouter un autre paramètre d'exécution

1.  Ouvrez un test de charge.

2.  (Facultatif) Développez le dossier **Paramètres d’exécution**.

3.  Cliquez avec le bouton droit sur le dossier **Paramètres d’exécution**, puis sélectionnez **Ajouter un paramètre d’exécution**.

     Un nouveau paramètre d’exécution est ajouté au dossier **Paramètres d’exécution**.

4.  Dans le menu **Affichage**, choisissez **Fenêtre Propriétés**.

     La fenêtre **Propriétés** s’affiche avec les propriétés du paramètre d’exécution sélectionné.

5.  Dans la fenêtre **Propriétés**, utilisez la zone de texte de la propriété **Nom** pour donner au nouveau paramètre d’exécution un nom qui décrit sa finalité (par exemple, **Paramètre d’exécution : exécution de cinq minutes**).

6.  Utilisez la fenêtre **Propriétés** pour modifier les paramètres d’exécution. Par exemple, remplacez la durée d’exécution par **00:05:00** pour exécuter votre test pendant cinq minutes.

    > [!NOTE]
    > Pour obtenir la liste complète des propriétés des paramètres et leur description, voir [Propriétés des paramètres de série de tests de charge](../test/load-test-run-settings-properties.md).

     Vous pouvez maintenant indiquer que vous souhaitez utiliser le paramètre d'exécution ajouté en l'activant. Pour plus d'informations, voir [Procédure : sélectionner le paramètre d’exécution active d’un test de charge](../test/how-to-select-the-active-run-setting-for-a-load-test.md).

## <a name="see-also"></a>Voir aussi

- [Configurer les paramètres d’exécution des tests de charge](../test/configure-load-test-run-settings.md)
- [Spécifier les ensembles de compteurs et les règles de seuil des ordinateurs dans un test de charge](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)