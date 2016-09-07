---
title: "Create a Bootable USB Flash Drive"
ms.custom: na
ms.date: 07/15/2014
ms.prod: windows-server-2012-r2-essentials
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
applies_to: 
  - Windows Server 2012 Essentials
  - Windows Server 2012 R2 Essentials
ms.assetid: 2fe8e35c-69f9-40b3-a270-22e2402510d8
caps.latest.revision: 14
author: DonGill
manager: stevenka
translation.priority.ht: 
  - de-at
  - de-de
  - es-es
  - fr-be
  - fr-fr
  - it-ch
  - it-it
  - ja-jp
  - ko-kr
  - pt-br
  - ru-ru
  - zh-cn
  - zh-hk
  - zh-tw
---
# Create a Bootable USB Flash Drive
You can create a bootable USB flash drive to use to deploy [!INCLUDE[sbs_sbs8web_2](../install/includes/sbs_sbs8web_2_md.md)] . The first step is to prepare the USB flash drive by using DiskPart, which is a command-line utility. For information about DiskPart, see [DiskPart Command-Line Options](http://go.microsoft.com/fwlink/?LinkId=207073).  
  
 For additional scenarios in which you may want to create or use a bootable USB flash drive, see the following topics:  
  
-   [Restore a full system from an existing client computer backup](http://technet.microsoft.com/library/jj713539.aspx#BKMK_CreateBootable)  
  
-   [Restore or repair your server running Windows Server Essentials](http://technet.microsoft.com/library/jj593197.aspx#BKMK_Restore_2)  
  
### To create a bootable USB flash drive  
  
1.  Insert a USB flash drive into a running computer.  
  
2.  Open a Command Prompt window as an administrator.  
  
3.  Type `diskpart`.  
  
4.  In the new command line window that opens, to determine the USB flash drive number or drive letter, at the command prompt, type `list disk`, and then click ENTER. The `list disk` command displays all the disks on the computer. Note the drive number or drive letter of the USB flash drive.  
  
5.  At the command prompt, type `select disk <X>`, where X is the drive number or drive letter of the USB flash drive, and then click ENTER.  
  
6.  Type `clean`, and the click ENTER. This command deletes all data from the USB flash drive.  
  
7.  To create a new primary partition on the USB flash drive, type `create part pri`, and then click ENTER.  
  
8.  To select the partition that you just created, type `select part 1`, and then click ENTER.  
  
9. To format the partition, type `format fs=ntfs quick`, and then click ENTER.  
  
    > [!IMPORTANT]
    >  If your server platform supports Unified Extensible Firmware Interface (UEFI), you should format the USB flash drive as FAT32 rather than as NTFS. To format the partition as FAT32, type `format fs=fat32 quick`, and then click ENTER.  
  
10. Type `active`, and then click ENTER.  
  
11. Type `exit`, and then click ENTER.  
  
12. When you finish preparing your custom image, save it to the root of the USB flash drive.  
  
## See Also  
 [Getting Started with the Windows Server 2012 Essentials ADK](../install/Getting-Started-with-the-Windows-Server-2012-Essentials-ADK.md)   
 [Creating and Customizing the Image](../install/Creating-and-Customizing-the-Image.md)   
 [Additional Customizations](../install/Additional-Customizations.md)   
 [Preparing the Image for Deployment](../install/Preparing-the-Image-for-Deployment.md)   
 [Testing the Customer Experience](../install/Testing-the-Customer-Experience.md)   
 [How can we help you?](http://windows.microsoft.com/windows/support)