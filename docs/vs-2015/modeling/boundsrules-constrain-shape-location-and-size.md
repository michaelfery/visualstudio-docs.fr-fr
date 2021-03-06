---
title: Emplacement de la forme et la taille de contrainte par BoundsRules | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, events
ms.assetid: 4d08e541-fc67-4e68-bf31-30d346aa2aa0
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d09be82be084767bfb2d300a1877e95456a957b4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58950649"
---
# <a name="boundsrules-constrain-shape-location-and-size"></a>Définition de l'emplacement et de la taille de la forme par la classe BoundsRules
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Un *règle de limites* est une classe qui définit les limites de la taille et l’emplacement d’une forme. Il fournit une méthode qui est appelée à plusieurs reprises pendant que l’utilisateur fait glisser une forme ou angles ou sur les côtés d’une forme.  
  
 L’exemple suivant force une forme rectangulaire à une barre de taille fixe, horizontale ou verticale. Lorsque l’utilisateur fait glisser les angles ou sur les côtés, le contour renverse entre les deux configurations autorisées de hauteur et largeur.  
  
 Les limites de règle est une classe dérivée de <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>. Une instance de la règle est créée dans la forme :  
  
```  
using Microsoft.VisualStudio.Modeling.Diagrams; ...  
public partial class BarShape  
{  
  /// <summary>  
  /// Rule invoked when the user is resizing a shape.  
  /// </summary>  
  public override BoundsRules BoundsRules  
  { get { return new BarBoundsRule(); } }  
}  
/// <summary>  
/// Rule invoked when the user is changing a shape's outline.  
/// Provides real-time mouse rubber-band feedback, so must work fast.  
/// </summary>  
public class BarBoundsRule: BoundsRules  
{   
  public override RectangleD GetCompliantBounds   
     (ShapeElement shape, RectangleD proposedBounds)  
  {  
    double thickness = 0.1;  
    if (proposedBounds.Height > proposedBounds.Width)  
    {  
      // There is a minimum width for a shape; the width  
      // will actually be set to the lesser of   
      // thickness and that minimum.  
      return new RectangleD(proposedBounds.Location,   
            new SizeD(thickness, proposedBounds.Height));  
    }  
    else  
    {  
      // There is a minimum height for a shape; the   
      // height will actually be set to the lesser of   
      // thickness and that minimum.  
      return new RectangleD(proposedBounds.Location,   
         new SizeD(proposedBounds.Width, thickness));  
} } }  
```  
  
 Notez que l’emplacement et la taille peuvent être contraint si vous le souhaitez.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>   
 [Propagation et réponse aux modifications](../modeling/responding-to-and-propagating-changes.md)
