---
title: Fonctionnalités disponibles par type d’application et de projet Office
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application-level add-ins [Office development in Visual Studio]
- Office development in Visual Studio, features
- Ribbon [Office development in Visual Studio]
- Office applications [Office development in Visual Studio], features available
- document-level customizations [Office development in Visual Studio]
- Office projects [Office development in Visual Studio], features available
- add-ins [Office development in Visual Studio]
- form regions [Office development in Visual Studio], features available
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2cff118e31a10780a4573608a6516ddea9e4f73a
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56626750"
---
# <a name="features-available-by-office-application-and-project-type"></a>Fonctionnalités disponibles par type d’application et de projet Office
  Visual Studio possède plusieurs types de modèles de projet qui prennent en charge différents scénarios professionnels pour les applications Microsoft Office, y compris les types suivants :

- Personnalisations au niveau du document

- Compléments VSTO

  Toutes les applications ne peuvent pas utiliser chaque type de projet. Par exemple, les projets au niveau du document sont uniquement disponibles pour Microsoft Office Word et Microsoft Office Excel. De même, certaines fonctionnalités sont uniquement disponibles pour certains types de projets ou d'applications. Par exemple, le volet Actions est uniquement disponible dans les projets au niveau du document, et les extensions Ruban sont uniquement disponibles pour certaines applications. Pour plus d’informations sur les différents types de projets, consultez [présentation du développement de solutions Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).

> [!NOTE]
>  Les modèles de projet Office sont uniquement disponibles dans certaines éditions de [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Pour plus d’informations, consultez [configurer un ordinateur pour développer des solutions Office](../vsto/configuring-a-computer-to-develop-office-solutions.md).

## <a name="project-types-available-for-different-microsoft-office-applications"></a>Types de projets disponibles pour différentes applications Microsoft Office
 Le tableau suivant montre les applications que vous pouvez utiliser avec chaque type de projet.

|Types de projet|Application Microsoft Office|
|-------------------|----------------------------------|
|Personnalisations au niveau du document|Excel<br /><br /> Word|
|Compléments VSTO|Excel<br /><br /> InfoPath (InfoPath 2013 et InfoPath 2010 uniquement)<br /><br /> Outlook<br /><br /> PowerPoint<br /><br /> Projet<br /><br /> Visio<br /><br /> Word<br /><br /> Excel|

## <a name="features-available-in-different-project-types"></a>Fonctionnalités disponibles dans différents types de projets
 Le tableau suivant montre quels types de projet proposent chaque fonctionnalité.

|Fonctionnalité|Types de projets proposant la fonctionnalité|Informations supplémentaires|
|-------------|--------------------------------------------|---------------------|
|Volet Actions|Projets au niveau du document.|[Vue d’ensemble du volet Actions](../vsto/actions-pane-overview.md)|
|Déploiement ClickOnce|Projets VS et au niveau du document|[Déployer une solution Office](../vsto/deploying-an-office-solution.md)|
|Volets de tâches personnalisés|Projets de complément VSTO pour les applications suivantes :<br /><br /> -   Excel<br />-InfoPath (InfoPath 2013 et InfoPath 2010 uniquement)<br />-   Outlook<br />-   PowerPoint<br />-   Word|[Volets Office personnalisés](../vsto/custom-task-panes.md)|
|Parties XML personnalisées|Projets au niveau du document.<br /><br /> Projets de niveau application pour les applications suivantes :<br /><br /> -   Excel<br />-   PowerPoint<br />-   Word|[Vue d’ensemble de parties XML personnalisée](../vsto/custom-xml-parts-overview.md)|
|Cache de données|Projets au niveau du document.|[Données mises en cache dans les personnalisations au niveau du document](../vsto/cached-data-in-document-level-customizations.md)|
|Exposer un objet dans un complément VSTO à d’autres solutions Microsoft Office.|Projets de complément VSTO|[Appeler du code dans des Compléments VSTO à partir d’autres solutions Office](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md)|
|Contrôles hôtes suivants :<br /><br /> -Graphique<br />-   ListObject<br />-   NamedRange<br />-Contrôles de contenu<br />-Signet|Projets au niveau du document.<br /><br /> Projets de complément VSTO pour Word et Excel.|[Éléments hôtes et la vue d’ensemble des contrôles hôtes](../vsto/host-items-and-host-controls-overview.md)|
|Contrôles hôtes suivants :<br /><br /> -   XMLMappedRange<br />-   XMLNode<br />-   XMLNodes|Projets au niveau du document.|[Éléments hôtes et la vue d’ensemble des contrôles hôtes](../vsto/host-items-and-host-controls-overview.md)|
|Déploiement de plusieurs projet|Projets au niveau du document.<br /><br /> Projets de complément VSTO|[Procédure pas à pas : Déployer plusieurs solutions Office dans un seul programme d’installation ClickOnce](https://msdn.microsoft.com/051223c0-4082-4799-b78b-a4763a9def55)|
|Zones de formulaire Outlook|Projets de complément VSTO pour Outlook.|[Créer des zones de formulaire Outlook](../vsto/creating-outlook-form-regions.md)|
|Actions de post-déploiement|Projets au niveau du document.<br /><br /> Projets de complément VSTO|[Procédure pas à pas : Copier un document à l’ordinateur de l’utilisateur final après une installation ClickOnce](https://msdn.microsoft.com/100090f7-bc63-4152-b3e1-19b48bc27466)|
|Personnalisations du ruban|Projets au niveau du document.<br /><br /> Projets de complément VSTO pour les applications suivantes :<br /><br /> -   Excel<br />-InfoPath (InfoPath 2013 et InfoPath 2010 uniquement)<br />-   Outlook<br />-   PowerPoint<br />-   Project<br />-   Visio<br />-   Word|[Vue d’ensemble du ruban](../vsto/ribbon-overview.md)|
|Concepteur visuel de documents|Projets au niveau du document.|[Projets Office dans l’environnement Visual Studio](../vsto/office-projects-in-the-visual-studio-environment.md)|

## <a name="see-also"></a>Voir aussi
- [Prise en main &#40;développement Office dans Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
- [Vue d’ensemble du développement de solutions Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)
- [Vue d’ensemble du volet Actions](../vsto/actions-pane-overview.md)
- [Vue d’ensemble du ruban](../vsto/ribbon-overview.md)
- [Créer des zones de formulaire Outlook](../vsto/creating-outlook-form-regions.md)
- [Éléments hôtes et la vue d’ensemble des contrôles hôtes](../vsto/host-items-and-host-controls-overview.md)
- [Données mises en cache dans les personnalisations au niveau du document](../vsto/cached-data-in-document-level-customizations.md)
- [Déployer une solution Office](../vsto/deploying-an-office-solution.md)
