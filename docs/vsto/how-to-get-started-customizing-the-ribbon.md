---
title: 'Procédure : Commencer la personnalisation du ruban'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom Ribbon, adding Ribbon to project
- Ribbon [Office development in Visual Studio], adding
- Ribbon [Office development in Visual Studio], customizing
- customizing the Ribbon, adding Ribbon to project
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 14c4ff1e8bf443351f835d74d44b49bbb61e0321
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56640114"
---
# <a name="how-to-get-started-customizing-the-ribbon"></a>Procédure : Commencer la personnalisation du ruban
  Pour personnaliser le ruban d’une application Microsoft Office, ajoutez un **ruban (Concepteur visuel)** ou **ruban (XML)** élément à un projet Office.

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

### <a name="to-add-a-ribbon-to-a-project"></a>Pour ajouter un ruban à un projet

1. Sur le **projet** Menu, cliquez sur **ajouter un nouvel élément**.

2. Dans le **ajouter un nouvel élément** boîte de dialogue, sélectionnez **ruban (Concepteur visuel)** ou **ruban (XML)**. Pour plus d’informations sur ces modèles, consultez [vue d’ensemble du ruban](../vsto/ribbon-overview.md).

3. Dans le **nom** , tapez un nom pour l’élément de ruban.

    Les noms ne peut pas contenir les caractères suivants :

   -   Signe dièse (#)

   -   Pourcentage (%)

   -   Esperluette (&)

   -   astérisque (*)

   -   barre verticale (|)

   -   Barre oblique inverse (\\)

   -   Signe deux-points ( :))

   -   Guillemet double (")

   -   Inférieur à (\<)

   -   Supérieur à (>)

   -   point d'interrogation (?)

   -   Oblique (/)

   -   Espaces à gauche ou (' ')

   -   Noms réservés à Windows ou à MS-DOS comme (« nul », « aux », « con », « com1 », « lpt1 » et ainsi de suite)

4. Cliquez sur **OK**.

   L’élément de ruban s’affiche dans **l’Explorateur de solutions**. Pour plus d’informations sur les étapes, consultez [vue d’ensemble du ruban](../vsto/ribbon-overview.md).

## <a name="see-also"></a>Voir aussi
- [Accéder au ruban lors de l’exécution](../vsto/accessing-the-ribbon-at-run-time.md)
- [Concepteur de ruban](../vsto/ribbon-designer.md)
- [Ribbon XML](../vsto/ribbon-xml.md)
- [Procédure pas à pas : Créer un onglet personnalisé à l’aide du Concepteur de ruban](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
- [Procédure pas à pas : Créer un onglet personnalisé à l’aide de XML du ruban](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)
