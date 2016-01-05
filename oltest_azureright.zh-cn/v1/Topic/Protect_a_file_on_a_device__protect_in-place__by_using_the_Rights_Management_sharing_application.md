---
description: na
keywords: na
pagetitle: Protect a file on a device (protect in-place) by using the Rights Management sharing application
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 33920329-5247-4f6c-8651-6227afb4a1fa
---
# 使用 Rights Management 共享应用程序保护设备上的文件（就地保护）。
当你就地保护文件时，它将替换未受保护的原始文件。 然后，你可以将文件保留在原来位置、将其复制到其他文件夹或设备，或共享其所在的文件夹，同时该文件将仍处于受保护状态。 你还可以将受保护文件附加到电子邮件，虽然我们建议直接从文件资源管理器或 Office 应用程序（请参阅 [使用权限管理共享应用程序保护通过电子邮件进行共享的文件](../Topic/Protect_a_file_that_you_share_by_email_by_using_the_Rights_Management_sharing_application.md)）通过电子邮件共享受保护文件。

> [!TIP]
> 当你尝试保护文件时看到任何错误，请参阅[适用于 Windows 的 Microsoft Rights Management 共享应用程序的常见问题](http://go.microsoft.com/fwlink/?LinkId=303971)。

## 保护设备上的文件（就地保护）

1.  选择文件资源管理器中要保护的文件。 右键单击该文件，依次选择“使用 RMS 保护”、“就地保护”。 例如：

    ![](../Image/ADRMS_MSRMSApp_SP_CompanyDefined.png)

    > [!NOTE]
    > 如果没有看到“使用 RMS 保护”选项，可能是计算机上没有安装 RMS 共享应用程序，或者是必须重新启动计算机以完成安装。 有关如何安装 RMS 共享应用程序的详细信息，请参阅[下载和安装 Rights Management 共享应用程序](../Topic/Download_and_install_the_Rights_Management_sharing_application.md)。

2.  执行以下操作之一：

    -   选择策略模板：一般而言，它们是将访问权限和使用限制给你的组织成员的预定义权限。 例如，如果组织名称为“Contoso, Ltd”，你可能会看到“Contoso, Ltd - 机密，仅供查阅”。 如果这是你首次在此电脑上保护文件，将需要首先选择“公司定义的保护”以下载模板。

        下次单击“就地保护”选项时，你会看到多达 10 个可供选择的模板。 如果可用模板超过 10 个，但没有显示你所需要的模板，则可单击“公司定义的保护”以下载和查看所有模板。

        选择策略模板时，也可以保护多个文件和某个文件夹。 选择某个文件夹时，将自动选择该文件夹中的所有文件进行保护，但不会自动保护在该文件夹中创建的新文件。

    -   选择“自定义权限”：如果模板没有提供所需的保护级别，或你想要自己显式设置保护选项，请选择此选项。 在[添加保护对话框](http://technet.microsoft.com/library/dn574738.aspx)中指定此文件所需的选项，然后单击“应用”。

3.  你可能很快就会看到一个对话框，告诉你文件处于受保护状态，然后焦点返回到文件资源管理器。 现在，所选文件处于受保护状态。 在某些情况下（添加的保护更改了文件扩展名时），文件资源管理器中的原始文件将为具有 Rights Management 保护锁状图标的新文件所替代。 例如：

    ![](../Image/ADRMS_MSRMSApp_Pfile.png)

如果你以后需要删除文件保护，请参阅 [使用 Rights Management 共享应用程序移除对文件的保护](../Topic/Remove_protection_from_a_file_by_using_the_Rights_Management_sharing_application.md)。

## 示例和其他说明
有关如何使用 Rights Management 共享应用程序以及操作说明的示例，请参阅以下 Rights Management 共享应用程序用户指南部分：

-   [使用 RMS 共享应用程序的示例](../Topic/Rights_Management_sharing_application_user_guide.md#BKMK_SharingExamples)

-   [要执行什么操作？](../Topic/Rights_Management_sharing_application_user_guide.md#BKMK_SharingInstructions)

## 请参阅
[权限管理共享应用程序用户指南](../Topic/Rights_Management_sharing_application_user_guide.md)

