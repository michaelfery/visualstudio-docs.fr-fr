---
title: Enregistrer des données dans une base de données (plusieurs tables)
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- updating datasets, walkthroughs
- data [Visual Studio], saving
- saving data, walkthroughs
- data [Visual Studio], updating
ms.assetid: 7ebe03da-ce8c-4cbc-bac0-a2fde4ae4d07
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: b5f2296e7dbd6c40327ed516f4da2bf51b8dd4cd
ms.sourcegitcommit: 5af29226aef0a3b4a506b69a08a97cfd21049521
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 03/20/2019
ms.locfileid: "58268562"
---
# <a name="save-data-to-a-database-multiple-tables"></a>Enregistrer des données dans une base de données (plusieurs tables)

L'un des scénarios les plus courants dans le développement d'applications consiste à afficher des données dans un formulaire d'une application Windows, à modifier ces données, puis à renvoyer les données mises à jour à la base de données. Cette procédure pas à pas crée un formulaire affichant les données de deux tables associées et indique comment modifier les enregistrements et enregistrer les modifications dans la base de données. Cet exemple utilise les tables `Customers` et `Orders` de l'exemple de base de données Northwind.

Vous pouvez enregistrer des données de votre application dans la base de données en appelant la méthode `Update` d'un TableAdapter. Lorsque vous faites glisser les tables à partir de la **des Sources de données** fenêtre sur un formulaire, le code qui est nécessaire pour enregistrer les données est automatiquement ajoutée. Toutes les tables supplémentaires qui sont ajoutés à un formulaire requièrent l’ajout manuel de ce code. Cette procédure pas à pas indique comment ajouter du code pour enregistrer les mises à jour de plusieurs tables.

Cette procédure pas à pas décrit notamment les tâches suivantes :

-  Création et configuration d’une source de données dans votre application avec le [Assistant de Configuration de Source de données](../data-tools/media/data-source-configuration-wizard.png).

-  Définition des contrôles des éléments dans le [fenêtre Sources de données](add-new-data-sources.md#data-sources-window). Pour plus d’informations, consultez [définir le contrôle à créer lors du déplacement de la fenêtre Sources de données](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).

-  Création de contrôles liés aux données en faisant glisser des éléments depuis la fenêtre **Sources de données** vers votre formulaire.

-  Modification des enregistrements dans chaque table dans le jeu de données.

-  Modification du code pour renvoyer les données mises à jour dans le dataset à la base de données.

## <a name="prerequisites"></a>Prérequis

Cette procédure pas à pas utilise SQL Server Express LocalDB et la base de données Northwind.

1. Si vous n’avez pas SQL Server Express LocalDB, installez-le à partir de la [page de téléchargement de SQL Server Express](https://www.microsoft.com/sql-server/sql-server-editions-express), ou via le **le programme d’installation de Visual Studio**. Dans le **le programme d’installation de Visual Studio**, vous pouvez installer SQL Server Express LocalDB dans le cadre de la **stockage de données et de traitement** charge de travail, ou comme un composant individuel.

2. Installer la base de données Northwind en suivant ces étapes :

    1. Dans Visual Studio, ouvrez le **Explorateur d’objets SQL Server** fenêtre. (Explorateur d’objets SQL Server est installé dans le cadre de la **stockage de données et de traitement** charge de travail dans Visual Studio Installer.) Développez le **SQL Server** nœud. Avec le bouton droit sur votre instance de base de données locale et sélectionnez **nouvelle requête**.

       Une fenêtre d’éditeur de requête s’ouvre.

    2. Copie le [script Transact-SQL de Northwind](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) dans votre Presse-papiers. Ce script T-SQL crée la base de données Northwind à partir de zéro et la remplit avec des données.

    3. Collez le script T-SQL dans l’éditeur de requête, puis choisissez le **Execute** bouton.

       Après une courte période, la requête est terminée en cours d’exécution et la base de données Northwind est créé.

## <a name="create-the-windows-forms-application"></a>Créer l’application Windows Forms

Créer un nouveau **Windows Forms application** projet pour soit C# ou Visual Basic. Attribuez le nom **UpdateMultipleTablesWalkthrough** au projet.

## <a name="create-the-data-source"></a>Créer la source de données

Cette étape crée une source de données à partir de la base de données Northwind à l’aide de l’**Assistant Configuration de source de données**. Vous devez avoir accès à l'exemple de base de données Northwind pour créer la connexion. Pour plus d’informations sur la configuration de la base de données Northwind, consultez [Comment : installer les bases de données exemple](../data-tools/installing-database-systems-tools-and-samples.md).

1. Sur le **données** menu, sélectionnez **afficher les Sources de données**.

   La fenêtre **Sources de données** s’ouvre.

2. Dans la fenêtre **Sources de données**, sélectionnez **Ajouter une nouvelle source de données** pour démarrer l’**Assistant Configuration de source de données**.

3. Sur le **choisir un Type de Source de données** s’affiche, sélectionnez **base de données**, puis sélectionnez **suivant**.

4. Sur le **choisir votre connexion de données** , effectuez une des opérations suivantes :

    - Si une connexion de données à l’exemple de base de données Northwind est disponible dans la liste déroulante, sélectionnez-la.

         - ou -

    - Sélectionnez **Nouvelle connexion** pour ouvrir la boîte de dialogue **Ajouter/Modifier la connexion**.

5. Si votre base de données requiert un mot de passe, sélectionnez l’option pour inclure les données sensibles, puis sélectionnez **suivant**.

6. Sur le **enregistrer la chaîne de connexion dans le fichier de Configuration de l’Application**, sélectionnez **suivant**.

7. Sur le **choisir vos objets de base de données** écran, développez le **Tables** nœud.

8. Sélectionnez le **clients** et **commandes** tables, puis sélectionnez **Terminer**.

     **NorthwindDataSet** est ajouté à votre projet et les tables apparaissent dans la fenêtre **Sources de données**.

## <a name="set-the-controls-to-be-created"></a>Définir les contrôles à créer

Pour cette procédure pas à pas, les données dans le `Customers` table se trouve dans un **détails** où les données sont affichées dans des contrôles individuels. Les données à partir de la `Orders` table se trouve dans un **grille** mise en page qui s’affiche dans un <xref:System.Windows.Forms.DataGridView> contrôle.

### <a name="to-set-the-drop-type-for-the-items-in-the-data-sources-window"></a>Pour définir le type de déplacement des éléments de la fenêtre Sources de données

1. Dans le **des Sources de données** fenêtre, développez le **clients** nœud.

2. Sur le **clients** nœud, sélectionnez **détails** à partir de la liste de contrôle pour modifier le contrôle de la **clients** table par des contrôles individuels. Pour plus d’informations, consultez [définir le contrôle à créer lors du déplacement de la fenêtre Sources de données](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).

## <a name="create-the-data-bound-form"></a>Création d’un formulaire lié aux données

Pour créer des contrôles liés aux données, vous pouvez faire glisser des éléments depuis la fenêtre **Sources de données** vers votre formulaire.

1. Faites glisser le nœud **Customers** depuis la fenêtre **Sources de données** vers **Form1**.

     Les contrôles liés aux données assortis d'étiquettes descriptives apparaissent dans le formulaire, ainsi qu'une barre d'outils (<xref:System.Windows.Forms.BindingNavigator>) pour parcourir les enregistrements. Un [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), `CustomersTableAdapter`, <xref:System.Windows.Forms.BindingSource>, et <xref:System.Windows.Forms.BindingNavigator> s’affichent dans la barre d’état du composant.

2. Faites glisser le nœud **Orders** associé depuis la fenêtre **Sources de données** vers **Form1**.

    > [!NOTE]
    > Le nœud **Orders** associé est situé sous la colonne **Fax** et constitue un nœud enfant du nœud **Customers**.

     Un contrôle <xref:System.Windows.Forms.DataGridView> et une barre d'outils (<xref:System.Windows.Forms.BindingNavigator>) pour parcourir les enregistrements apparaissent dans le formulaire. Un `OrdersTableAdapter` et <xref:System.Windows.Forms.BindingSource> s’affichent dans la barre d’état du composant.

## <a name="add-code-to-update-the-database"></a>Ajouter du code pour mettre à jour de la base de données

Vous pouvez mettre à jour la base de données en appelant les méthodes `Update` des TableAdapters **Customers** et **Orders**. Par défaut, un gestionnaire d’événements pour le **enregistrer** bouton de la<xref:System.Windows.Forms.BindingNavigator> est ajouté au code du formulaire pour envoyer des mises à jour à la base de données. Cette procédure modifie le code pour envoyer des mises à jour dans le bon ordre. Cela élimine le risque de lever des erreurs d’intégrité référentielle. Le code implémente également la gestion des erreurs en enveloppant l'appel de mise à jour dans un bloc try-catch. Vous pouvez modifier le code pour répondre aux besoins de votre application.

> [!NOTE]
> Pour plus de clarté, cette procédure pas à pas n’utilise pas une transaction. Toutefois, si vous mettez à jour deux ou plusieurs tables connexes, inclure toute la logique de mise à jour dans une transaction. Une transaction est un processus qui garantit que toutes les modifications associées à une base de données sont réussies avant que toutes les modifications soient validées. Pour plus d’informations, consultez [Transactions et la concurrence](/dotnet/framework/data/adonet/transactions-and-concurrency).

### <a name="to-add-update-logic-to-the-application"></a>Pour ajouter une logique de mise à jour à l'application

1. Sélectionnez le **enregistrer** situé dans le <xref:System.Windows.Forms.BindingNavigator>. Cette opération ouvre l’éditeur de Code pour le `bindingNavigatorSaveItem_Click` Gestionnaire d’événements.

2. Remplacez le code dans le gestionnaire d'événements pour appeler les méthodes `Update` des TableAdapters associés. Le code suivant crée d'abord trois tables de données temporaires pour contenir les informations mises à jour pour chaque <xref:System.Data.DataRowState> (<xref:System.Data.DataRowState.Deleted>, <xref:System.Data.DataRowState.Added> et <xref:System.Data.DataRowState.Modified>). Les mises à jour sont exécutées dans l’ordre approprié. Le code doit se présenter comme suit :

     [!code-vb[VbRaddataSaving#10](../data-tools/codesnippet/VisualBasic/save-data-to-a-database-multiple-tables_1.vb)]
     [!code-csharp[VbRaddataSaving#10](../data-tools/codesnippet/CSharp/save-data-to-a-database-multiple-tables_1.cs)]

## <a name="test-the-application"></a>Tester l’application

1. Appuyez sur **F5**.

2. Apportez quelques modifications aux données d'un ou plusieurs enregistrements dans chaque table.

3. Sélectionnez le bouton **Enregistrer**.

4. Vérifiez les valeurs figurant dans la base de données pour confirmer que les modifications ont bien été enregistrées.

## <a name="see-also"></a>Voir aussi

- [Enregistrer les données dans la base de données](../data-tools/save-data-back-to-the-database.md)