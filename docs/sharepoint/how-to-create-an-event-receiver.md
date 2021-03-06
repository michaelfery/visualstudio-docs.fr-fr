---
title: 'Procédure : Créer un récepteur d’événements | Microsoft Docs'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.SPE.EventReceiver
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, event receivers
- event receivers [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 395fc5976f31fb2d465c57f036b3e5369aaa0c07
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54865097"
---
# <a name="how-to-create-an-event-receiver"></a>Procédure : Créer un récepteur d’événements
  En créant *récepteurs d’événements*, vous pouvez répondre lorsqu’un utilisateur interagit avec les éléments de SharePoint telles que les listes ou éléments de liste. Par exemple, le code dans un récepteur d’événements peut être déclenché lorsqu’un utilisateur modifie le calendrier ou supprime un nom d’une liste de contacts. En suivant cette rubrique, vous pouvez apprendre à ajouter un récepteur d’événements à une instance de liste.

 Pour effectuer ces étapes, vous devez avoir installé [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] et éditions de Windows et SharePoint prises en charge. Étant donné que cet exemple requiert un projet SharePoint, vous également devez avoir terminé la procédure décrite dans la rubrique [procédure pas à pas : Créer une colonne de site, le type de contenu et la liste pour SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md).

## <a name="adding-an-event-receiver"></a>Ajout d’un récepteur d’événements
 Le projet que vous avez créé dans [procédure pas à pas : Créer une colonne de site, le type de contenu et la liste pour SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md) inclut des colonnes de site personnalisées, une liste personnalisée et un type de contenu. Dans la procédure suivante, vous allez développer ce projet en ajoutant un gestionnaire d’événements simple (un récepteur d’événements) à une instance de liste pour montrer comment gérer les événements qui se produisent dans les éléments tels que des listes SharePoint.

#### <a name="to-add-an-event-receiver-to-the-list-instance"></a>Pour ajouter un récepteur d’événements à l’instance de liste

1.  Ouvrez le projet que vous avez créé dans [procédure pas à pas : Créer une colonne de site, le type de contenu et la liste pour SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md).

2.  Dans **l’Explorateur de solutions**, choisissez le nœud de projet SharePoint, qui est nommé **clinique**.

3.  Dans la barre de menus, choisissez **Projet** > **Ajouter un nouvel élément**.

4.  Sous **Visual C#** ou **Visual Basic**, développez le **SharePoint** nœud, puis choisissez le **2010** élément.

5.  Dans le **modèles** volet, choisissez **récepteur d’événements**, nommez-le **TestEventReceiver1**, puis choisissez le **OK** bouton.

     Le **Assistant Personnalisation de SharePoint** s’affiche.

6.  Dans le **quel type de récepteur d’événements voulez-vous ?** , choisissez **événements d’élément de liste**.

7.  Dans le **quel élément doit être la source d’événements ?** , choisissez **Patients (Clinic\Patients)**.

8.  Dans le **gérer les événements suivants** , sélectionnez la case à cocher à côté **un élément a été ajouté**, puis choisissez le **Terminer** bouton.

     Le fichier de code pour le récepteur d’événements contient une méthode unique nommée `ItemAdded`. Dans l’étape suivante, vous ajouterez du code à cette méthode afin que chaque contact sera nommé Scott Brown par défaut.

9. Remplacer la `ItemAdded` méthode par le code suivant de code, puis choisissez le **F5** clé :

     [!code-csharp[SP_EventReceiver#1](../sharepoint/codesnippet/CSharp/CustomField1/TestEventReceiver1/TestEventReceiver1.cs#1)]
     [!code-vb[SP_EventReceiver#1](../sharepoint/codesnippet/VisualBasic/CustomField1_VB/EventReceiver1/EventReceiver1.vb#1)]

     Le code est exécuté et le site s’affiche dans le navigateur web de SharePoint.

10. Dans la barre de lancement rapide, choisissez le **Patients** lier, puis choisissez le **ajouter un nouvel élément** lien.

     Le formulaire d’entrée pour les nouveaux éléments s’ouvre.

11. Entrez des données dans les champs, puis choisissez le **enregistrer** bouton.

     Après avoir choisi le **enregistrer** bouton, le **nom du Patient** colonne met automatiquement à jour le nom Scott Brown.

## <a name="see-also"></a>Voir aussi

- [Développer des solutions SharePoint](../sharepoint/developing-sharepoint-solutions.md)