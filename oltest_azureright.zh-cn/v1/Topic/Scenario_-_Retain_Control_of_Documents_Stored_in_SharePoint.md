---
description: na
keywords: na
pagetitle: Scenario - Retain Control of Documents Stored in SharePoint
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1b6244c7-5ab9-4881-bc8f-6fa960390d89
---
# 应用场景 - 保留对 SharePoint 中所存储文档的控制
本部分包含管理员说明以及有关用户说明的指导。在通知用户有关此配置的事宜之前，必须先阅读针对管理员的说明。

## 管理员的指令
![](../Image/AzRMS_AdminBanner.png)

按这些说明操作，以确保使用受保护的库让存储在 SharePoint 中的 Office 文档保持受你的控制。例如，文档会自动防范由用户意外或有意泄露，并且即使在下载或同步后，你也可以阻止对内容的访问。你想要保护的文件可能是来在设计文档或计划上进行协作的，或者是用于交付的。为 SharePoint 配置受保护的库时，在其中存储的 Office 文件将由 Azure 权限管理来保护。

这些指令适用于下面一组情况：

-   员工共享 Office 文档并用这些文档进行协作。

-   文档包含非公共信息，但这些信息也并非必须专供内部使用。

-   员工不需要设置或更改管理员在库级别设置的权限。

## 本方案的要求
要让此应用场景成立，必须做好以下准备：

|Check|要求|需要更多信息|
|---------|------|----------|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|已准备好 Office 365 或 Azure Active Directory 的帐户和组|[准备 Azure 权限管理](https://technet.microsoft.com/library/jj585029.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|已激活 Azure Rights Management|[激活 Azure 权限管理](https://technet.microsoft.com/library/jj658941.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|如果使用 SharePoint Server：部署 RMS 连接器并针对 SharePoint 进行配置|[部署 Azure 权限管理连接器](https://technet.microsoft.com/library/dn375964.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|为 IRM 和受保护的库配置 SharePoint|[在 SharePoint 管理中心设置信息权限管理 (IRM)](https://support.office.com/en-us/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239ce6eb-4e81-42db-bf86-a01362fed65c)<br /><br />[将信息权限管理应用于列表或库](http://office.microsoft.com/sharepoint-help/apply-information-rights-management-to-a-list-or-library-HA102891460.aspx)|

## 用户指令
本应用场景没有针对用户的特别说明，因为受保护的库不需要用户采取任何特殊操作。根据 SharePoint 管理员为站点设置的权限，文档会自动受到保护。但是，你可能需要通知用户和技术支持哪些库会受到保护以及保护措施会对他们使用文档有哪些限制。例如，由于当前限制，这些文档可以查看但不能在移动设备上进行编辑。

下面的示例可作为将 SharePoint 库配置为使用 Azure RMS 后给相关部门或团队的标准电子邮件通信。

### 示例用户文档
![](../Image/AzRMS_ExampleBanner.png)

##### IT 公告：对“销售预测和报告”站点的更改

-   SharePoint 站点**销售预测和报告**现已进行了安全协作配置。从现在起，必须直接编辑存储在此站点中的电子表格和 Word 文档 — 例如，不能将它们保存到其他位置以后再编辑或者用电子邮件将它们发送给其他人。可以使用移动设备查看它们，但必须使用 Windows 计算机对其进行编辑。

**需要帮助吗?**

-   请联系技术支持：helpdesk@vanarsdelltd.com

