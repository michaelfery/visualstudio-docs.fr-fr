---
title: 'Procédure : Formater le texte par programmation dans des documents'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- formatting [Office development in Visual Studio]
- documents [Office development in Visual Studio], formatting text
- text [Office development in Visual Studio], formatting in documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 66ca84d2246a3335aa3a1bbc0900ca6f48f59f01
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56630689"
---
# <a name="how-to-programmatically-format-text-in-documents"></a>Procédure : Formater le texte par programmation dans des documents
  Vous pouvez utiliser l'objet <xref:Microsoft.Office.Interop.Word.Range> pour mettre en forme le texte dans un document Microsoft Office Word.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

 L'exemple suivant sélectionne le premier paragraphe du document et modifie la taille de la police, le nom de la police et l'alignement. Ensuite, il sélectionne la plage et affiche un message d'interruption avant l'exécution de la section de code suivante. La section suivante appelle la méthode d’annulation de la <xref:Microsoft.Office.Tools.Word.Document> élément hôte (pour une personnalisation au niveau du document) ou la <xref:Microsoft.Office.Interop.Word.Document> classe (pour un complément VSTO) trois fois. Il applique le style Retrait normal et affiche un message permettant de suspendre le code. Puis, le code appelle la méthode <xref:Microsoft.Office.Tools.Word.Document.Undo%2A> une seule fois et affiche un message.

## <a name="document-level-customization-example"></a>Exemple de personnalisation au niveau du document

### <a name="to-format-text-using-a-document-level-customization"></a>Pour mettre en forme un texte à l'aide d'une personnalisation au niveau du document

1.  L'exemple suivant peut être utilisé dans une personnalisation au niveau du document. Pour utiliser ce code, exécutez-le à partir de la classe `ThisDocument` de votre projet.

     [!code-vb[Trin_VstcoreWordAutomation#62](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#62)]
     [!code-csharp[Trin_VstcoreWordAutomation#62](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#62)]

## <a name="vsto-add-in-example"></a>Exemple de complément VSTO

### <a name="to-format-text-using-a-vsto-add-in"></a>Pour mettre en forme du texte avec un complément VSTO

1.  L’exemple suivant peut être utilisé dans un complément VSTO. Cet exemple utilise le document actif. Pour utiliser ce code, exécutez-le à partir de la classe `ThisAddIn` de votre projet.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#62](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#62)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#62](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#62)]

## <a name="see-also"></a>Voir aussi
- [Guide pratique pour Définir et sélectionner des plages dans les documents par programmation](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)
- [Guide pratique pour Insérer du texte dans les documents Word par programmation](../vsto/how-to-programmatically-insert-text-into-word-documents.md)
- [Guide pratique pour Rechercher et remplacer du texte dans les documents par programmation](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)
