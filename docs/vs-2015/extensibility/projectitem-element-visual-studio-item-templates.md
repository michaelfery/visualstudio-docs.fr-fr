---
title: ProjectItem, élément (modèles d’élément Visual Studio) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectItem
helpviewer_keywords:
- <ProjectItem> element [Visual Studio item templates]
- ProjectItem element [Visual Studio item templates]
ms.assetid: 9ed94112-0c38-49df-b728-0dd2d0d1eb47
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 29b65f5cff9e2ffbed3c66c29c61f0a7e9e50f20
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58953439"
---
# <a name="projectitem-element-visual-studio-item-templates"></a>ProjectItem, élément (modèles d'élément Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Spécifie un fichier qui est inclus dans le modèle d’élément.  
  
> [!NOTE]
>  Le `ProjectItem` élément accepte des attributs différents selon que le modèle est pour un projet ou un élément. Cette rubrique explique les `ProjectItem` élément pour l’élément. Pour obtenir une explication de la `ProjectItem` , élément pour les modèles de projet, consultez [ProjectItem, élément (modèles de projet Visual Studio)](../extensibility/projectitem-element-visual-studio-project-templates.md).  
  
 \<VSTemplate>  
 \<TemplateContent>  
 \<ProjectItem>  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ProjectItem  
    SubType="Form/Component/CustomControl/UserControl"  
    CustomTool="string"  
    ItemType="string"  
    ReplaceParameters="true/false"  
    TargetFileName="TargetFileName.ext">  
        FileName.ext  
</ProjectItem>  
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
  
|Attribut|Description|  
|---------------|-----------------|  
|`SubType`|Attribut facultatif.<br /><br /> Spécifie le sous-type d’un élément dans un modèle d’élément multifichier. Cette valeur est utilisée pour déterminer l’éditeur qui [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] utilisera pour ouvrir l’élément.|  
|`CustomTool`|Attribut facultatif.<br /><br /> Définit l’outil personnalisé pour l’élément dans le fichier projet.|  
|`ItemType`|Attribut facultatif.<br /><br /> Définit le ItemType pour l’élément dans le fichier projet.|  
|`ReplaceParameters`|Attribut facultatif.<br /><br /> Valeur booléenne qui spécifie si l’élément a des valeurs de paramètre qui doivent être remplacés lorsqu’un projet est créé à partir du modèle. La valeur par défaut est `false`.|  
|`TargetFileName`|Attribut facultatif.<br /><br /> Spécifie le nom de l’élément qui est créé à partir du modèle. Cet attribut est utile pour l’utilisation de remplacement de paramètres pour créer un nom d’élément.|  
  
### <a name="child-elements"></a>Éléments enfants  
 Aucun.  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Spécifie le contenu du modèle.|  
  
## <a name="text-value"></a>Valeur texte  
 Une valeur texte est requise.  
  
 Un `string` qui représente le nom d’un fichier dans le fichier .zip du modèle.  
  
## <a name="remarks"></a>Notes  
 `ProjectItem` est un enfant facultatif de `TemplateContent`.  
  
 Le `TargetFileName` attribut peut être utilisé pour renommer des fichiers avec des paramètres. Par exemple, si le fichier `MyFile.vb` existe dans le répertoire racine du fichier .zip du modèle, mais vous souhaitez que le fichier se nomme en fonction du nom de fichier fourni par l’utilisateur dans le **ajouter un nouvel élément** boîte de dialogue, vous utiliseriez le code XML suivant :  
  
```  
<ProjectItem TargetFileName="$fileinputname$.vb">MyFile.vb</ProjectItem>  
```  
  
 Lorsqu’un élément est créé à partir de ce modèle, le nom de fichier doit reposer sur le nom de l’utilisateur a entré dans le **ajouter un nouvel élément** boîte de dialogue. Cela est utile lors de la création de modèles d’élément multifichier. Pour plus d'informations, voir [Procédure : Créer des modèles d’élément multifichier](../ide/how-to-create-multi-file-item-templates.md) et [paramètres de modèle](../ide/template-parameters.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant illustre les métadonnées pour le modèle d’élément standard pour une [!INCLUDE[csprcs](../includes/csprcs-md.md)] classe.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <DefaultName>MyClass.cs</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem ReplaceParameters="true">MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Référence du schéma de modèle Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Création de modèles de projet et d’élément](../ide/creating-project-and-item-templates.md)   
 [Guide pratique pour Créer des modèles d’élément multifichier](../ide/how-to-create-multi-file-item-templates.md)   
 [Paramètres de modèle](../ide/template-parameters.md)
