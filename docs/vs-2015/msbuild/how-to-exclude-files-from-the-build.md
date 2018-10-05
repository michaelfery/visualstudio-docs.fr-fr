---
title: 'Comment : exclure des fichiers de la génération | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSBuild, wildcards
- MSBuild, excluding files
- wildcards, MSBuild
ms.assetid: 1be36e45-01da-451c-972d-f9fc0e7d663c
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c4527e6381a893a7ba7396199980de0bf62ae0a7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47508159"
---
# <a name="how-to-exclude-files-from-the-build"></a>Comment : exclure des fichiers de la build
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [Comment : exclure des fichiers de la Build](https://docs.microsoft.com/visualstudio/msbuild/how-to-exclude-files-from-the-build).  
  
  
Dans un fichier projet, vous pouvez utiliser des caractères génériques pour inclure tous les fichiers d’un répertoire ou un ensemble imbriqué de répertoires comme des entrées d’une génération. Toutefois, il se peut que vous ne souhaitiez pas inclure un fichier du répertoire ou un répertoire d’un ensemble imbriqué de répertoires comme entrée d’une génération. Vous pouvez explicitement exclure ce fichier ou ce répertoire de la liste d’entrées. Il peut également s’agir d’un fichier d’un projet que vous ne souhaitez inclure que dans certaines conditions. Vous pouvez déclarer explicitement les conditions dans lesquelles un fichier est inclus dans une génération.  
  
## <a name="excluding-a-file-or-directory-from-the-inputs-for-a-build"></a>Exclusion d’un fichier ou d’un répertoire des entrées d’une génération  
 Les listes d’éléments constituent les fichiers d’entrée d’une génération. Les éléments que vous souhaitez inclure sont déclarés séparément ou en tant que groupe à l’aide de l’attribut `Include`. Exemple :  
  
```  
<CSFile Include="Form1.cs"/>  
<CSFile Include ="File1.cs;File2.cs"/>  
<CSFile Include="*.cs"/>  
<JPGFile Include="Images\**\*.jpg"/>  
```  
  
 Si vous avez utilisé des caractères génériques pour inclure tous les fichiers d’un répertoire ou un ensemble imbriqué de répertoires comme entrées d’une génération, il se peut que vous ne vouliez pas inclure un ou plusieurs fichiers du répertoire ou un répertoire de l’ensemble imbriqué des répertoires. Pour exclure un élément de la liste d’éléments, utilisez l’attribut `Exclude`.  
  
#### <a name="to-include-all-cs-or-vb-files-except-form2"></a>Pour inclure tous les fichiers .cs ou .vb à l’exception de Form2  
  
-   Utilisez l’un des attributs `Include` et `Exclude` suivants :  
  
    ```  
    <CSFile Include="*.cs" Exclude="Form2.cs"/>  
    ```  
  
     - ou  
  
    ```  
    <VBFile Include="*.vb" Exclude="Form2.vb"/>  
    ```  
  
#### <a name="to-include-all-cs-or-vb-files-except-form2-and-form3"></a>Pour inclure tous les fichiers .cs ou .vb à l’exception de Form2 et de Form3  
  
-   Utilisez l’un des attributs `Include` et `Exclude` suivants :  
  
    ```  
    <CSFile Include="*.cs" Exclude="Form2.cs;Form3.cs"/>  
    ```  
  
     - ou  
  
    ```  
    <VBFile Include="*.vb" Exclude="Form2.vb;Form3.vb"/>  
    ```  
  
#### <a name="to-include-all-jpg-files-in-subdirectories-of-the-images-directory-except-those-in-the-version2-directory"></a>Pour inclure tous les fichiers .jpg des sous-répertoires du répertoire Images, à l’exception de ceux du répertoire Version2  
  
-   Utilisez les attributs `Include` et `Exclude` suivants :  
  
    ```  
    <JPGFile  
        Include="Images\**\*.jpg"  
        Exclude = "Images\**\Version2\*.jpg"/>  
    ```  
  
    > [!NOTE]
    >  Vous devez spécifier le chemin d’accès pour les deux attributs. Si vous utilisez un chemin d’accès absolu pour spécifier les emplacements des fichiers dans l’attribut `Include`, vous devez également utiliser un chemin d’accès absolu dans l’attribut `Exclude` ; si vous utilisez un chemin d’accès relatif dans l’attribut `Include`, vous devez également utiliser un chemin d’accès relatif dans l’attribut `Exclude`.  
  
## <a name="using-conditions-to-exclude-a-file-or-directory-from-the-inputs-for-a-build"></a>Utilisation de conditions pour exclure un fichier ou un répertoire des entrées d’une génération  
 Si vous souhaitez inclure des éléments, par exemple, dans une version Debug, mais pas dans une version Release, vous pouvez utiliser l’attribut `Condition` pour spécifier les conditions dans lesquelles inclure l’élément.  
  
#### <a name="to-include-the-file-formulavb-only-in-release-builds"></a>Pour inclure le fichier Formula.vb uniquement dans les versions Release  
  
-   Utilisez un attribut `Condition` semblable à ce qui suit :  
  
    ```  
    <Compile  
        Include="Formula.vb"  
        Condition=" '$(Configuration)' == 'Release' " />  
    ```  
  
## <a name="example"></a>Exemple  
 L’exemple de code suivant génère un projet avec l’ensemble des fichiers .cs du répertoire à l’exception du fichier Form2.cs.  
  
```  
<Project DefaultTargets="Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <PropertyGroup>  
        <builtdir>built</builtdir>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <CSFile Include="*.cs Exclude="Form2.cs"/>  
  
        <Reference Include="System.dll"/>  
        <Reference Include="System.Data.dll"/>  
        <Reference Include="System.Drawing.dll"/>  
        <Reference Include="System.Windows.Forms.dll"/>  
        <Reference Include="System.XML.dll"/>  
    </ItemGroup>  
  
    <Target Name="PreBuild">  
        <Exec Command="if not exist $(builtdir) md $(builtdir)"/>  
    </Target>  
  
    <Target Name="Compile" DependsOnTargets="PreBuild">  
        <Csc Sources="@(CSFile)"  
            References="@(Reference)"  
            OutputAssembly="$(builtdir)\$(MSBuildProjectName).exe"  
            TargetType="exe" />  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Éléments](../msbuild/msbuild-items.md)   
 [MSBuild](msbuild.md) [Guide pratique pour sélectionner des fichiers dans une build](../msbuild/how-to-select-the-files-to-build.md)

