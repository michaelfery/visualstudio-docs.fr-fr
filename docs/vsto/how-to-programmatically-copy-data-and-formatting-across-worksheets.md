---
title: 'Procédure : Copier des données et la mise en forme entre feuilles de calcul par programmation'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, copying data
- formatting [Office development in Visual Studio]
- data [Office development in Visual Studio], copying across worksheets
- copying data, Office development in Visual Studio
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 77feefe7a2d274403e483dbaa3167f53f72ae168
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56608264"
---
# <a name="how-to-programmatically-copy-data-and-formatting-across-worksheets"></a>Procédure : Copier des données et la mise en forme entre feuilles de calcul par programmation
  Vous pouvez copier des données à partir d’une plage d’une feuille à toutes les autres feuilles dans un classeur à l’aide de la <xref:Microsoft.Office.Interop.Excel.Worksheets.FillAcrossSheets%2A> (méthode). Spécifier une plage, et si vous souhaitez copier des données, la mise en forme ou les deux.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="example"></a>Exemple
 [!code-csharp[Trin_VstcoreExcelAutomation#44](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#44)]
 [!code-vb[Trin_VstcoreExcelAutomation#44](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#44)]

## <a name="compile-the-code"></a>Compiler le code
 Cet exemple requiert une plage nommée `rangeData` dans une feuille de calcul.

## <a name="see-also"></a>Voir aussi
- [Travailler avec des feuilles de calcul](../vsto/working-with-worksheets.md)
- [Guide pratique pour Ajouter par programmation des feuilles de calcul à des classeurs](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)
- [Guide pratique pour Modifier la mise en forme dans les lignes de feuille de calcul contenant des cellules sélectionnées par programmation](../vsto/how-to-programmatically-change-formatting-in-worksheet-rows-containing-selected-cells.md)
- [Paramètres optionnels dans les solutions Office](../vsto/optional-parameters-in-office-solutions.md)
