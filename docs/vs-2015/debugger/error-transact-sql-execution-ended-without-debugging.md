---
title: 'Erreur : L’exécution de Transact-SQL s’est terminée sans débogage | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.sqlde_sql_executed_but_not_debugged
dev_langs:
- FSharp
- VB
- CSharp
- C++
- SQL
ms.assetid: 7a4d4999-3973-4339-ba6a-f0d19bcb1d4a
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7de8aaba3abf4ef7c767ed549b5454b1599e808d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47508077"
---
# <a name="error-transact-sql-execution-ended-without-debugging"></a>Erreur : L'exécution de Transact-SQL s'est terminée sans débogage
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [erreur : l’exécution de Transact-SQL s’est terminée sans débogage](https://docs.microsoft.com/visualstudio/debugger/error-transact-sql-execution-ended-without-debugging).  
  
Cette erreur se produit lorsque vous essayez de déboguer une procédure Transact-SQL ou SQLCLR et que le débogueur ne reçoit pas de messages de débogage de SQL Server.  
  
 Cela peut être dû à des problèmes liés au réseau ou à SQL Server, mais plus probablement à un problème d'autorisation.  
  
 Deux comptes sont concernés :  
  
-   Le compte d'application est le compte utilisateur qu'utilise [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] pour s'exécuter.  
  
-   Le compte de connexion est l'identité utilisée pour établir la connexion à SQL Server. Il ne s'agit pas nécessairement du compte sous lequel Visual Studio est exécuté si la connexion utilise l'authentification SQL.  
  
 Le débogage SQL requiert que le compte d'application corresponde au compte de connexion ou soit administrateur système.  
  
 Si vous utilisez un nom d'utilisateur SQL comme sa, le compte d'application doit être configuré sur le SQL Server comme un administrateur système. Par défaut, les administrateurs de l'ordinateur sur lequel SQL Server est exécuté sont des administrateurs système SQL Server.  
  
 Pour corriger cette erreur, vous pouvez avoir besoin de :  
  
-   Vérifier vos paramètres d'autorisation. Pour plus d’informations, consultez [Comment : définir des autorisations SQL Server pour le débogage](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414).  
  
-   Vérifier que le débogage SQL est correctement configuré.  
  
-   Consulter votre administrateur réseau ou de base de données.  
  
## <a name="see-also"></a>Voir aussi  
 [Configuration du débogage SQL](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3)   
 [Comment : définir des autorisations SQL Server pour le débogage](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414)   
 [Paramètres et préparation du débogueur](../debugger/debugger-settings-and-preparation.md)   
 [Débogage à distance](../debugger/remote-debugging.md)


