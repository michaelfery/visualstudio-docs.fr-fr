---
title: 'Procédure : Empêcher Outlook d’afficher une zone de formulaire'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], canceling display
- canceling form region display
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ad17041650324e597fb76925f521bb7fc2e9ce93
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56629181"
---
# <a name="how-to-prevent-outlook-from-displaying-a-form-region"></a>Procédure : Empêcher Outlook d’afficher une zone de formulaire
  Il peut arriver dans lequel vous ne souhaitez pas que Microsoft Office Outlook pour afficher une zone de formulaire pour un élément particulier. Par exemple, si un élément de contact ne contient pas une adresse professionnelle, vous pouvez empêcher une zone de formulaire qui affiche l’emplacement de l’entreprise dans un mappage d’apparaître.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="to-prevent-outlook-from-displaying-a-form-region"></a>Pour empêcher Outlook d’afficher une zone de formulaire

1. Ouvrez le fichier de code pour la zone de formulaire que vous souhaitez modifier.

2. Développez le **fabrique de zones de formulaire** région de code.

3. Ajouter du code pour le `FormRegionInitializing` Gestionnaire d’événements qui définit le <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propriété de la <xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs> classe **true**.

   Dans cet exemple, si l’élément de contact ne contient pas d’adresse, le <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propriété est définie sur **true**, et la zone de formulaire n’apparaît pas.

## <a name="example"></a>Exemple
 [!code-csharp[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Separate_O12/MapIt.cs#1)]
 [!code-vb[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Separate_O12/MapIt.vb#1)]

## <a name="see-also"></a>Voir aussi
- [Créer des zones de formulaire Outlook](../vsto/creating-outlook-form-regions.md)
- [Procédure pas à pas : Concevoir une zone de formulaire Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)
- [Guide pratique pour Ajouter une zone de formulaire à un projet de complément Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)
- [Procédure pas à pas : Concevoir une zone de formulaire Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)
- [Procédure pas à pas : Importer une zone de formulaire conçue dans Outlook](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)
