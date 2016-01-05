---
description: na
keywords: na
pagetitle: Rights Management sharing application: Version release history
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6751bd90-959f-4eba-91ed-6588ac983762
---
# 权限管理共享应用程序：版本发行历史记录
Rights Management 团队定期更新 Rights Management 共享应用程序，以提供修补程序和新功能。 使用以下信息查看版本中的新增内容或更改的内容。 最新版本会最先列出。

不会列出 2015 年 1 月 1 日之前的版本。

> [!NOTE]
> 如果你有关于 RMS 共享应用程序的反馈或问题，请发送电子邮件到 [AskIPTeam](mailto:AskIPTeam@microsoft.com?subject=RMS%20sharing%20app:%20Feedback%20or%20question)。

## 版本 1.0.2004.0
**发布日期**：12/11/2015

**修补程序**：

-   错误消息改进（准确性和清晰性）。

-   加密和解密内容的性能改进。

**新增功能**：

-   支持非管理员安装，使标准用户可以安装 RMS 共享应用程序。

    对运行 Office 2010 的标准用户有一些限制。 有关详细信息，请参阅[下载和安装 Rights Management 共享应用程序](../Topic/Download_and_install_the_Rights_Management_sharing_application.md)用户说明中的[如果你不是本地管理员，而且使用 Office 2010](../Topic/Download_and_install_the_Rights_Management_sharing_application.md#BKMK_SetupOffice2010)部分。

## 版本 1.0.1908.0
**发布日期**：2015/9/16

**修补程序**：

-   对 Azure RMS 的 Multi-Factor Authentication (MFA) 的支持也将删除 Microsoft 登录助手（使用新式身份验证）的依赖关系。

    有关详细信息，请参阅[Azure 权限管理要求](../Topic/Requirements_for_Azure_Rights_Management.md)中的[多因素身份验证 (MFA) 和 Azure RMS](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_MFA) 部分。

## 版本 1.0.1784.0
**发布日期**：2015/7/30

**修补程序**：

-   权限策略模板的默认刷新间隔从 7 天减少到 1 天。

-   少量的回归测试和较小的 Bug。

## 版本 1.0.1770.0
**发布日期**：2015/4/25

**修补程序**：

-   现在，只有所有者和共同所有者可以删除保护。 合著者不能删除保护。

-   现在可以保护网络共享上的文件。

**新增功能**：

-   支持文档跟踪和撤消。 有关详细信息，请参阅[使用 RMS 共享应用程序跟踪和撤销文档](../Topic/Track_and_revoke_your_documents_when_you_use_the_RMS_sharing_application.md)。

-   选择“共享保护”时的模板支持：

    -   你现在可以选择模板。

    -   你看到的不是滑块，而是包含模板和自定义权限的列表框。

    -   你将不会再看到“允许在所有设备上使用”和“强制实施使用限制”选项。 相反，根据文件类型，将自动选择“一般性保护”。

    有关详细信息，请参阅[权限管理共享应用程序的的对话框选项](../Topic/Dialog_box_options_for_the_Rights_Management_sharing_application.md)。

## 版本 1.0.1667.0
**发布日期**：2015/1/19

**修补程序**：

-   RMS 共享应用 PPDF 查看器中的中文字体支持。

-   改进的错误处理和消息传送。

-   更高版本的应用可用于下载时，对于自动更新通知问题的修复。

**新增功能**：

-   **对于你的组织中的多个电子邮件域的支持**：如果你使用 AD RMS，并且组织中的用户具有多个电子邮件域，此更新可让你的用户使用其他域中的组织用户保护的内容。 有关详细信息，请参阅[权限管理共享应用程序管理员指南](../Topic/Rights_Management_sharing_application_administrator_guide.md)中的[仅限 AD RMS：在组织中支持多个电子邮件域](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_FederatedDomains)部分。

