---
title: "LIB Task | Microsoft Docs"
ms.custom: ""
ms.date: "2018-06-30"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLibrarianTool.Name"
  - "VC.Project.VCLibrarianTool.TreatLibWarningsAsErrors"
  - "VC.Project.VCLibrarianTool.Verbose"
  - "vc.task.lib"
  - "VC.Project.VCLibrarianTool.ErrorReporting"
  - "VC.Project.VCLibrarianTool.LinkLibraryDependencies"
  - "VC.Project.VCLibrarianTool.LinkTimeCodeGeneration"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
  - "C++"
helpviewer_keywords: 
  - "MSBuild (Visual C++), LIB task"
  - "LIB task (MSBuild (Visual C++))"
ms.assetid: e062c7f9-cc69-4a83-9361-1bb5355e5fe8
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: "ghogen"
---
# LIB Task
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

The latest version of this topic can be found at [LIB Task](https://docs.microsoft.com/visualstudio/msbuild/lib-task).  
  
  
Wraps the Microsoft 32-Bit Library Manager tool, lib.exe. The Library Manager creates and manages a library of Common Object File Format (COFF) object files. The Library Manager can also create export files and import libraries to reference exported definitions. For more information, see [LIB Reference](http://msdn.microsoft.com/library/ecc7f643-bbd4-47a3-8dc6-b360f880db91) and [Running LIB](http://msdn.microsoft.com/library/d54f5c81-7147-4b2c-a8db-68ce6eb1eabd).  
  
## Parameters  
 The following table describes the parameters of the **LIB** task. Most task parameters correspond to a command-line option.  
  
|Parameter|Description|  
|---------------|-----------------|  
|**AdditionalDependencies**|Optional **String[]** parameter.<br /><br /> Specifies additional items to add to the command line.|  
|**AdditionalLibraryDirectories**|Optional **String[]** parameter.<br /><br /> Overrides the environment library path. Specify a directory name.<br /><br /> For more information, see [/LIBPATH (Additional Libpath)](http://msdn.microsoft.com/library/7240af0b-9a3d-4d53-8169-2a92cd6958ba).|  
|**AdditionalOptions**|Optional **String** parameter.<br /><br /> A list of lib.exe options as specified on the command line. For example, **"_/option1 /option2 /option#_". Use this parameter to specify lib.exe options that are not represented by any other **LIB** task parameter.<br /><br /> For more information, see [Running LIB](http://msdn.microsoft.com/library/d54f5c81-7147-4b2c-a8db-68ce6eb1eabd).|  
|**DisplayLibrary**|Optional **String** parameter.<br /><br /> Displays information about the output library. Specify a file name to redirect the information to a file. Specify "CON" or nothing to redirect the information to the console.<br /><br /> This parameter corresponds to the **/LIST** option of lib.exe.|  
|**ErrorReporting**|Optional **String** parameter.<br /><br /> Specifies how to send internal error information to Microsoft if lib.exe fails at runtime.<br /><br /> Specify one of the following values, each of which corresponds to a command-line option.<br /><br /> -   **NoErrorReport** - **/ERRORREPORT:NONE**<br />-   **PromptImmediately** - **/ERRORREPORT:PROMPT**<br />-   **QueueForNextLogin** - **/ERRORREPORT:QUEUE**<br />-   **SendErrorReport** - **/ERRORREPORT:SEND**<br /><br /> For more information, see the **/ERRORREPORT** command-line option at [Running LIB](http://msdn.microsoft.com/library/d54f5c81-7147-4b2c-a8db-68ce6eb1eabd).|  
|**ExportNamedFunctions**|Optional **String[]** parameter.<br /><br /> Specifies one or more functions to export.<br /><br /> This parameter corresponds to the **/EXPORT:** option of lib.exe.|  
|**ForceSymbolReferences**|Optional **String** parameter.<br /><br /> Forces lib.exe to include a reference to the specified symbol.<br /><br /> This parameter corresponds to the **/INCLUDE:** option of lib.exe.|  
|**IgnoreAllDefaultLibraries**|Optional `Boolean` parameter.<br /><br /> If `true`, removes all default libraries from the list of libraries that lib.exe searches when it resolves external references.<br /><br /> This parameter corresponds to the parameter-less form of the **/NODEFAULTLIB** option of lib.exe.|  
|**IgnoreSpecificDefaultLibraries**|Optional **String[]** parameter.<br /><br /> Removes the specified libraries from the list of libraries that lib.exe searches when it resolves external references.<br /><br /> This parameter corresponds to the **/NODEFAULTLIB** option of lib.exe that takes a `library` argument.|  
|**LinkLibraryDependencies**|Optional `Boolean` parameter.<br /><br /> If `true`, specifies that library outputs from project dependencies are automatically linked in.|  
|**LinkTimeCodeGeneration**|Optional `Boolean` parameter.<br /><br /> If `true`, specifies link-time code generation.<br /><br /> This parameter corresponds to the **/LCTG** option of lib.exe.|  
|**MinimumRequiredVersion**|Optional **String** parameter.<br /><br /> Specifies the minimum required version of the subsystem. Specify a comma-delimited list of decimal numbers in the range 0 through 65535.|  
|**ModuleDefinitionFile**|Optional **String** parameter.<br /><br /> Specifies the name of the module-definition file (.def).<br /><br /> This parameter corresponds to the **/DEF** option of lib.exe that takes a `filename` argument.|  
|**Name**|Optional **String** parameter.<br /><br /> When an import library is built, specifies the name of the DLL for which the import library is being built.<br /><br /> This parameter corresponds to the **/NAME** option of lib.exe that takes a `filename` argument.|  
|**OutputFile**|Optional **String** parameter.<br /><br /> Overrides the default name and location of the program that lib.exe creates.<br /><br /> This parameter corresponds to the **/OUT** option of lib.exe that takes a `filename` argument.|  
|**RemoveObjects**|Optional **String[]** parameter.<br /><br /> Omits the specified object from the output library. Lib.exe creates an output library by combining all objects (whether in object files or libraries), and then deleting any objects  that are specified by this option.<br /><br /> This parameter corresponds to the **/REMOVE** option of lib.exe that takes a `membername` argument.|  
|**Sources**|Required `ITaskItem[]` parameter.<br /><br /> Specifies a list of source files separated by spaces.|  
|**SubSystem**|Optional **String** parameter.<br /><br /> Specifies the environment for the executable. The choice of subsystem affects the entry point symbol or entry point function.<br /><br /> Specify one of the following values, each of which corresponds to a command-line option.<br /><br /> -   **Console** - **/SUBSYSTEM:CONSOLE**<br />-   **Windows** - **/SUBSYSTEM:WINDOWS**<br />-   **Native** - **/SUBSYSTEM:NATIVE**<br />-   **EFI Application** - **/SUBSYSTEM:EFI_APPLICATION**<br />-   **EFI Boot Service Driver** - **/SUBSYSTEM:EFI_BOOT_SERVICE_DRIVER**<br />-   **EFI ROM** - **/SUBSYSTEM:EFI_ROM**<br />-   **EFI Runtime** - **/SUBSYSTEM:EFI_RUNTIME_DRIVER**<br />-   **WindowsCE** - **/SUBSYSTEM:WINDOWSCE**ReplaceThisText<br />-   **POSIX** - **/SUBSYSTEM:POSIX**<br /><br /> For more information, see [/SUBSYSTEM (Specify Subsystem)](http://msdn.microsoft.com/library/d7b133cf-cf22-4da8-ab46-6552702c0b9b).|  
|**SuppressStartupBanner**|Optional **Boolean** parameter.<br /><br /> If `true`, prevents the display of the copyright and version number message when the task starts.<br /><br /> For more information, see the **/NOLOGO** option at [Running LIB](http://msdn.microsoft.com/library/d54f5c81-7147-4b2c-a8db-68ce6eb1eabd).|  
|**TargetMachine**|Optional **String** parameter.<br /><br /> Specifies the target platform for the program or DLL.<br /><br /> Specify one of the following values, each of which corresponds to a command-line option.<br /><br /> -   **MachineARM** - **/MACHINE:ARM**<br />-   **MachineEBC** - **/MACHINE:EBC**<br />-   **MachineIA64** - **/MACHINE:IA64**<br />-   **MachineMIPS** - **/MACHINE:MIPS**<br />-   **MachineMIPS16** - **/MACHINE:MIPS16**<br />-   **MachineMIPSFPU** -**/MACHINE:MIPSFPU**<br />-   **MachineMIPSFPU16** - **/MACHINE:MIPSFPU16**<br />-   **MachineSH4** - **/MACHINE:SH4**<br />-   **MachineTHUMB** - **/MACHINE:THUMB**<br />-   **MachineX64** - **/MACHINE:X64**<br />-   **MachineX86** - **/MACHINE:X86**<br /><br /> For more information, see [/MACHINE (Specify Target Platform)](http://msdn.microsoft.com/library/8d41bf4b-7e53-4ab9-9085-d852b08d31c2).|  
|**TrackerLogDirectory**|Optional **String** parameter.<br /><br /> Specifies the directory of the tracker log.|  
|**TreatLibWarningAsErrors**|Optional **Boolean** parameter.<br /><br /> If `true`, causes the **LIB** task to not generate an output file if lib.exe generates a warning. If `false`, an output file is generated.<br /><br /> For more information, see the **/WX** option at [Running LIB](http://msdn.microsoft.com/library/d54f5c81-7147-4b2c-a8db-68ce6eb1eabd).|  
|**UseUnicodeResponseFiles**|Optional **Boolean** parameter.<br /><br /> If `true`, instructs the project system to generate UNICODE response files when the librarian is spawned. Specify `true` when files in the project have UNICODE paths.|  
|**Verbose**|Optional **Boolean** parameter.<br /><br /> If `true`, displays details about the progress of the session; this includes names of the .obj files being added. The information is sent to standard output and can be redirected to a file.<br /><br /> For more information, see the **/VERBOSE** option in [Running LIB](http://msdn.microsoft.com/library/d54f5c81-7147-4b2c-a8db-68ce6eb1eabd).|  
  
## Remarks  
  
## See Also  
 [Task Reference](../msbuild/msbuild-task-reference.md)



