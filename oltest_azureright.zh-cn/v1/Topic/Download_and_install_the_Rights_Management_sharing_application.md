---
description: na
keywords: na
pagetitle: Download and install the Rights Management sharing application
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2bf09690-9dba-43b7-9e0a-0110915d4081
---
# 下载和安装 Rights Management 共享应用程序
你无需是本地管理员就能安装 RMS 共享应用程序。 但是，如果你不是本地管理员而使用 Office 2010，就会有一些限制。 有关详细信息，请参阅本主题中的[如果你不是本地管理员，而且使用 Office 2010](#BKMK_SetupOffice2010)部分。

### 下载并安装权限管理共享应用程序

1.  转到 Microsoft 网站上的 [Microsoft 权限管理](http://go.microsoft.com/fwlink/?LinkId=303970)页。

2.  在“计算机”部分中，单击“适用于 Windows 的 RMS 应用”图标，并保存用于安装 Microsoft Rights Management 共享应用程序的 **Setup.exe** 文件。

3.  双双击已下载的 Setup.exe 文件。 如果系统提示你继续，请单击**“是”**。

4.  在**“安装 Microsoft RMS”**页上，单击**“下一步”**，然后等待安装完成。

    > [!NOTE]
    > RMS 共享应用程序需要 Microsoft .NET Framework（最低版本 4.0）。 安装程序会进行检查以查看是否安装了此组件，如果未安装，你将看到一封包含安装链接的邮件。

5.  安装完成后，请单击**“重启”**以重新启动计算机并完成安装。 或者，单击“关闭”，在稍后重启计算机以完成安装。

现在，你可以随时开始保护你的文件或阅读其他人保护的文件。

## <a name="BKMK_SetupOffice2010"></a>如果你不是本地管理员，而且使用 Office 2010
如果你登录到计算机而没有本地管理权限，并且安装程序检测到你已安装 Office 2010，就会显示一条警告消息，指出某些方案将不适用于此配置。 这些方案包括：

-   如果你组织使用 Azure RMS 而不是本地版本的 RMS：

    -   Office 的信息权限管理 (IRM) 功能将不可用。 例如，电子邮件的“不转发”选项，以及可以从 Word 和 Excel 中的“文件”菜单设置的“限制访问”权限。 你可以使用功能区中的“共享保护项”选项，以及文件资源管理器中的右键单击选项。

-   如果你组织使用本地版本的 RMS 而不是 Azure RMS：

    -   你将无法读取另一个组织中的人员发送给你的使用 Azure RMS 保护的文档。

如果你不是本地管理员而使用 Office 365 或 Office 2013，你将不会看到此消息，并且支持这些方案。

你可以继续安装并接受这些已知限制。 也可以停止安装，在步骤 3 中运行 Setup.exe 时使用“以管理员身份运行”选项重新运行它或请管理员为你安装。 管理员可以为你[编写此安装的脚本](https://technet.microsoft.com/library/dn339003.aspx)，使它可以自动安装。

## 示例和其他说明
有关如何使用 Rights Management 共享应用程序以及操作说明的示例，请参阅以下 Rights Management 共享应用程序用户指南部分：

-   [使用 RMS 共享应用程序的示例](../Topic/Rights_Management_sharing_application_user_guide.md#BKMK_SharingExamples)

-   [要执行什么操作？](../Topic/Rights_Management_sharing_application_user_guide.md#BKMK_SharingInstructions)

## 请参阅
[权限管理共享应用程序用户指南](../Topic/Rights_Management_sharing_application_user_guide.md)

