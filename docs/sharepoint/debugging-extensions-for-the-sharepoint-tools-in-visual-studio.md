---
title: "Debugging Extensions for the SharePoint Tools in Visual Studio | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "SharePoint development in Visual Studio, debugging extensions"
ms.assetid: 7cee8ce0-d07b-41f6-8ce1-b18e4be3b50c
caps.latest.revision: 26
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Debugging Extensions for the SharePoint Tools in Visual Studio
  You can debug SharePoint tools extensions in the experimental instance or the regular instance of Visual Studio. If you need to troubleshoot the behavior of an extension, you can also modify registry values to display additional error information and to configure how Visual Studio executes SharePoint commands.  
  
## Debugging Extensions in the Experimental Instance of Visual Studio  
 To safeguard your Visual Studio development environment from accidental corruption by untested extensions, the Visual Studio SDK provides an alternative Visual Studio instance, called the *experimental instance*, that you can use to install and test extensions. You develop new extensions by using the regular instance of Visual Studio, but you debug and run them in the experimental instance. For more information, see [The Experimental Instance](/visual-studio/extensibility/the-experimental-instance).  
  
 If you use a VSIX project to deploy your extension, and the VSIX project is the startup project in your solution, Visual Studio automatically installs and runs the extension in the experimental instance when you debug your solution. The startup project is the project that starts when you debug a solution that contains multiple projects. For more information about using a VSIX project to deploy your extension, see [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md). For more information about startup projects, see [NIB How to: Set Startup Projects](http://msdn.microsoft.com/en-us/31465836-0911-48db-a5d9-e456b635e970).  
  
 For examples that demonstrate how to debug various types of extensions in the experimental instance of Visual Studio, see the following walkthroughs:  
  
-   [Walkthrough: Extending a SharePoint Project Item Type](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)  
  
-   [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)  
  
-   [Walkthrough: Creating a Custom Deployment Step for SharePoint Projects](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)  
  
-   [Walkthrough: Extending Server Explorer to Display Web Parts](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)  
  
-   [Walkthrough: Calling into the SharePoint Client Object Model in a Server Explorer Extension](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md)  
  
## Debugging Extensions in the Regular Instance of Visual Studio  
 If you want to debug your extension project in the regular instance of Visual Studio, first install the extension in the regular instance. Then, attach the debugger to a second Visual Studio process. After you are finished, you can remove the extension so that it no longer loads on the development computer.  
  
#### To install the extension  
  
1.  Close all instances of Visual Studio.  
  
2.  In the build output folder for the extension project, open the .vsix file either by double-clicking it or by opening its shortcut menu and then choosing **Open**:  
  
3.  In the **Visual Studio Extension Installer** dialog box, choose the edition of Visual Studio to which you want to install the extension, and then choose the **Install** button.  
  
     Visual Studio installs the extension files to %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0\Extensions\\*author name*\\*extension name*\\*version*. The last three folders in this path are constructed from the `Author`, `Name`, and `Version` elements in the extension.vsixmanifest file for the extension.  
  
4.  After Visual Studio installs the extension, choose the **Close** button.  
  
#### To debug the extension  
  
1.  Start Visual Studio with administrator privileges and open the extension project. The following steps refer to this instance of Visual Studio as the *first instance*.  
  
2.  Start another instance of Visual Studio with administrator privileges. The following steps refer to this instance of Visual Studio as the *second instance*.  
  
3.  Switch to the first instance of Visual Studio.  
  
4.  On the menu bar, choose **Debug**, **Attach to Process**.  
  
5.  In the **Available Processes** list, choose devenv.exe. This entry refers to the second instance of Visual Studio; this is the instance you want to debug your project extension in.  
  
6.  Choose the **Attach** button.  
  
     Visual Studio runs the extension project in debug mode.  
  
7.  Switch to the second instance of Visual Studio.  
  
8.  Create a new SharePoint project that loads your extension. For example, if you are debugging an extension for list definition project items, create a **List Definition** project.  
  
9. Perform whatever steps are required to test your extension code.  
  
10. When you are finished debugging the extension, close the second instance of Visual Studio.  
  
#### To remove the extension  
  
1.  In Visual Studio, on the menu bar, choose **Tools**, **Extensions and Updates**.  
  
     The **Extensions and Updates** dialog box opens.  
  
2.  In the list of extensions, choose the name of the extension, and then choose the **Uninstall** button.  
  
3.  In the dialog box that appears, choose the **Yes** button to confirm that you want to uninstall the extension.  
  
4.  Choose the **Restart Now** button to complete the uninstallation.  
  
## Debugging SharePoint Commands  
 If you want to debug a SharePoint command that is part of a SharePoint tools extension, you must attach the debugger to the vssphost4.exe process. This is the 64-bit host process that executes SharePoint commands. For more information about SharePoint commands and vssphost4.exe, see [Calling into the SharePoint Object Models](../sharepoint/calling-into-the-sharepoint-object-models.md).  
  
#### To attach the debugger to the vssphost4.exe process  
  
1.  Start debugging your extension in the experimental instance of Visual Studio or the regular instance of Visual Studio by following the instructions above.  
  
2.  In the instance of Visual Studio in which you are running the debugger, on the menu bar, choose **Debug**, **Attach to Process**.  
  
3.  In the **Available Processes** list, choose vssphost.exe.  
  
    > [!NOTE]  
    >  If vssphost.exe does not appear in the list, you must start the vssphost4.exe process in the instance of Visual Studio in which you are running the extension. Typically, you do this by performing an action that causes Visual Studio to connect to the SharePoint site on the development computer. For example, Visual Studio starts vssphost4.exe when you expand a site connection node (a node that displays a site URL) under the **SharePoint Connections** node in the **Server Explorer** window, or when you add certain SharePoint project items, such as **List Instance** or **Event Receiver** items, to a SharePoint project.  
  
4.  Choose the **Attach** button.  
  
5.  In the instance of Visual Studio that is being debugged, perform the steps that are required to execute your command.  
  
## Modifying Registry Values to Help Debug SharePoint Tools Extensions  
 When you debug an extension of the SharePoint tools in Visual Studio, you can modify values in the registry to help you troubleshoot the extension. The values exist under the HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\11.0\SharePointTools key. These values do not exist by default.  
  
 To help troubleshoot any extension of the SharePoint tools, you can create and set the EnableDiagnostics value. The following table describes this value.  
  
|Value|Description|  
|-----------|-----------------|  
|EnableDiagnostics|REG_DWORD that specifies whether diagnostic messages are displayed in the **Output** window.<br /><br /> To display diagnostic messages, set this value to 1. To stop displaying messages, set this value to 0 or delete this value.<br /><br /> To write messages to the **Output** window from a SharePoint tools extension, use the SharePoint project service. For more information, see [Using the SharePoint Project Service](../sharepoint/using-the-sharepoint-project-service.md).|  
  
 If your extension includes a SharePoint command, you can create and set additional values to help troubleshoot the command. The following table describes these values.  
  
|Value|Description|  
|-----------|-----------------|  
|AttachDebuggerToHostProcess|REG_DWORD that specifies whether to display a dialog box that enables you to attach the debugger to vssphost4.exe as soon as it starts. This is useful if the command that you want to debug is executed by vssphost.exe immediately after it starts, and there is not enough time to manually attach the debugger before the command is executed. To display the dialog box, vssphost4.exe calls the <xref:System.Diagnostics.Debugger.Break%2A> method when it starts.<br /><br /> To enable this behavior, set this value to 1. To turn off this behavior, set this value to 0 or delete this value.<br /><br /> If you set this value to 1, you may also want to increase the HostProcessStartupTimeout value to give yourself enough time to attach the debugger before Visual Studio expects vssphost4.exe to signal that it started successfully.|  
|ChannelOperationTimeout|REG_DWORD that specifies the time, in seconds, that Visual Studio waits for a SharePoint command to execute. If the command does not execute in time, a <xref:Microsoft.VisualStudio.SharePoint.SharePointConnectionException> is thrown.<br /><br /> The default is 120 seconds.|  
|HostProcessStartupTimeout|REG_DWORD that specifies the time, in seconds, that Visual Studio waits for vssphost4.exe to signal that it started successfully. If vssphost4.exe does not signal a successful start in time, a <xref:Microsoft.VisualStudio.SharePoint.SharePointConnectionException> is thrown.<br /><br /> The default is 60 seconds.|  
|MaxReceivedMessageSize|REG_DWORD that specifies the maximum allowed size, in bytes, of WCF messages that are passed between Visual Studio and vssphost4.exe.<br /><br /> The default is 1,048,576 bytes (1 MB).|  
|MaxStringContentLength|REG_DWORD that specifies the maximum allowed size, in bytes, of strings that are passed between Visual Studio and vssphost4.exe.<br /><br /> The default is 1,048,576 bytes (1 MB).|  
  
## See Also  
 [Extending the SharePoint Tools in Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)   
 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
  