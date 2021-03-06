---
title: Outils de données pour C++
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CPP
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
- cplusplus
ms.openlocfilehash: 5157f1d6a851e0784e79dfbfe5b94aef0490a026
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55930556"
---
# <a name="visual-studio-data-tools-for-c"></a>Outils de données Visual Studio pour C++

C++ natif peuvent souvent offrir les meilleures performances lorsque vous accédez à des sources de données. Toutefois, les données des outils pour les applications C++ dans Visual Studio ne sont pas aussi riches car il s’agit pour les applications .NET. Par exemple, le **des Sources de données** fenêtre ne peut pas être utilisée pour glisser- déposer des sources de données sur une aire de conception de C++. Si vous avez besoin d’une couche objet-relationnel, vous devrez écrire votre propre, ou utiliser un produit tiers. Vaut pour les fonctionnalités de liaison de données, bien que les applications qui utilisent la bibliothèque Microsoft Foundation Class peuvent utiliser des classes de base de données, ainsi que des documents et vues, pour stocker les données en mémoire et les afficher à l’utilisateur. Pour plus d’informations, consultez [accès aux données dans Visual C++](/cpp/data/data-access-in-cpp).

Pour vous connecter aux bases de données SQL, les applications C++ natives peuvent utiliser les pilotes ODBC et OLE DB et le fournisseur ADO qui sont inclus avec Windows. Ceux-ci peuvent se connecter aux bases de données qui prend en charge ces interfaces. Le pilote ODBC est la norme. OLE DB est fourni pour la compatibilité descendante. Pour plus d’informations sur ces technologies de données, consultez [Windows Data Access Components](/previous-versions/windows/desktop/ms692897(v=vs.85)).

Pour tirer parti des fonctionnalités personnalisées dans SQL Server 2005 et version ultérieure, utilisez le [SQL Server natif client](/sql/relational-databases/native-client/sql-server-native-client). Le client natif contient également le pilote ODBC de SQL Server et le fournisseur OLE DB pour SQL Server dans une bibliothèque de liens dynamiques (DLL). Il prend en charge des applications à l’aide des API en code natif (ODBC, OLE DB et ADO) pour Microsoft SQL Server. SQL Server Native Client est installé avec SQL Server Data Tools. Le guide de programmation est ici : [programmation du client natif SQL Server](/sql/relational-databases/native-client/sql-server-native-client-programming).

## <a name="to-connect-to-localdb-through-odbc-and-sql-native-client-from-a-c-application"></a>Se connecter à la base de données locale via ODBC et SQL Native Client à partir d’une application C++

1. Installez SQL Server Data Tools.

2. Si vous avez besoin d’une base de données exemple SQL pour vous connecter à, téléchargez la base de données Northwind et décompressez-le dans un nouvel emplacement.

3. Utiliser SQL Server Management Studio pour attacher le décompressé *Northwind.mdf* fichier à la base de données locale. Au démarrage de SQL Server Management Studio, connectez-vous à (localdb) \MSSQLLocalDB.

   ![Boîte de dialogue de connexion de SSMS](../data-tools/media/raddata-ssms-connect-dialog.png)

   Avec le bouton droit sur le nœud de base de données locale dans le volet gauche, puis choisissez **attacher**.

   ![SSMS attacher la base de données](../data-tools/media/raddata-ssms-attach-database.png)

4. Téléchargez l’exemple de kit de développement logiciel Windows ODBC et décompressez-le dans un nouvel emplacement. Cet exemple montre les commandes ODBC de base qui sont utilisés pour se connecter à une base de données et émettre des requêtes et commandes. Vous pouvez en savoir plus sur ces fonctions dans le [Microsoft Open Database Connectivity (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc). Lorsque vous chargez tout d’abord la solution (il s’agit dans le dossier C++), Visual Studio propose de mettre à niveau de la solution vers la version actuelle de Visual Studio. Cliquez sur **Oui**.

5. Pour utiliser le client natif, vous devez son *en-tête* fichier et *lib* fichier. Ces fichiers contiennent des fonctions et des définitions spécifiques à SQL Server, au-delà des fonctions ODBC définies dans sql.h. Dans **projet** > **propriétés** > **répertoires VC ++**, ajoutez le répertoire include de ce qui suit :

   **%ProgramFiles%\Microsoft SQL Server\110\SDK\Include**

   Et ce répertoire de la bibliothèque :

   **%ProgramFiles%\Microsoft SQL Server\110\SDK\Lib**

6. Ajoutez ces lignes dans *odbcsql.cpp*. Le #define empêche des définitions de OLE DB non pertinentes à partir d’en cours de compilation.

   ```cpp
   #define _SQLNCLI_ODBC_
   #include <sqlncli.h>
   ```

    Notez que l’exemple ne pas réellement utilise toute la fonctionnalité de client natif, les étapes précédentes sont donc pas nécessaires compiler et exécuter. Mais le projet est maintenant configuré pour pouvoir utiliser cette fonctionnalité. Pour plus d’informations, consultez [Programmation de SQL Server Native Client](/sql/relational-databases/native-client/sql-server-native-client).

7. Spécifiez le pilote à utiliser dans le sous-système ODBC. L’exemple passe l’attribut de chaîne de connexion de pilote dans comme un argument de ligne de commande. Dans **projet** > **propriétés** > **débogage**, ajoutez l’argument de commande suivant :

   ```cpp
   DRIVER="SQL Server Native Client 11.0"
   ```

8. Appuyez sur **F5** pour générer et exécuter l’application. Vous devez voir une boîte de dialogue à partir du pilote qui vous invite à entrer une base de données. Entrez `(localdb)\MSSQLLocalDB`et vérifiez **utiliser la connexion approuvée**. Appuyez sur **OK**. Vous devez voir une console avec les messages qui indiquent une connexion réussie. Vous devriez également voir une invite de commandes où vous pouvez taper une instruction SQL. L’écran suivant montre un exemple de requête et les résultats :

   ![Sortie de requête d’exemple ODBC](../data-tools/media/raddata-odbc-sample-query-output.png)

## <a name="see-also"></a>Voir aussi

- [Accès aux données dans Visual Studio](../data-tools/accessing-data-in-visual-studio.md)