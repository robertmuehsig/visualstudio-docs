---
title: "BuildProjectOnLoad (Visual Studio Templates) | Microsoft Docs"
ms.custom: ""
ms.date: "2018-06-30"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#BuildOnLoad"
helpviewer_keywords: 
  - "<BuildOnLoad> element [Visual Studio Templates]"
  - "BuildOnLoad element [Visual Studio Templates]"
ms.assetid: 950f5fc1-d041-4090-9a5c-60844768a4cc
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# BuildProjectOnLoad (Visual Studio Templates)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

The latest version of this topic can be found at [BuildProjectOnLoad (Visual Studio Templates)](https://docs.microsoft.com/visualstudio/extensibility/buildprojectonload-visual-studio-templates).  
  
Specifies whether to build the project immediately after it's created.  
  
 \<VSTemplate>  
 \<TemplateData>  
 \<BuildProjectOnLoad>  
  
## Syntax  
  
```  
<BuildProjectOnLoad> true/false </BuildProjectOnLoad>  
```  
  
## Attributes and Elements  
 The following sections describe attributes, child elements, and parent elements.  
  
### Attributes  
 None.  
  
### Child Elements  
 None.  
  
### Parent Elements  
  
|Element|Description|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Categorizes the template and defines how it displays in either the **New Project** or the **Add New Item** dialog box.|  
  
## Text Value  
 A text value is required.  
  
 The text must be either `true` or `false`, indicating whether to build the project immediately after it's created.  
  
## Remarks  
 `BuildProjectOnLoad` is an optional attribute. The default value is `false`.  
  
## Example  
 The following example illustrates the metadata for a [!INCLUDE[csprcs](../includes/csprcs-md.md)] template.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <BuildProjectOnload>true</BuildProjectOnLoad>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## See Also  
 [TemplateContent Element (Visual Studio Templates)](../extensibility/templatecontent-element-visual-studio-templates.md)   
 [Creating Project and Item Templates](../ide/creating-project-and-item-templates.md)   
 [Visual Studio Template Schema Reference](../extensibility/visual-studio-template-schema-reference.md)

