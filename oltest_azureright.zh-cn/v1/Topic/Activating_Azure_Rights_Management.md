---
description: na
keywords: na
pagetitle: Activating Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f8707e01-b239-4d1a-a1ea-0d1cf9a8d214
---
# 激活 Azure 权限管理
激活 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] (Azure RMS) 后，你的组织便可以开始使用支持此信息保护解决方案的应用程序和服务保护重要数据了。 管理员还可以管理和监视你的组织拥有的受保护文件和电子邮件。 能够开始在 Office、SharePoint 和 Exchange 中使用信息权限管理 (IRM) 功能保护任何敏感或机密文件之前，你必须启用[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]。

如果你要在激活该服务之前了解有关 Azure 权限管理的详细信息（例如，它解决了哪些业务问题、一些典型用例以及它的工作原理），请参阅[什么是 Azure 权限管理？](../Topic/What_is_Azure_Rights_Management_.md)

> [!IMPORTANT]
> 在激活 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 之前，请确保你的组织具有包含 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 服务的服务计划。 如果没有，你将不能激活 Azure RMS。
> 
> 有关详细信息，请参阅[Azure 权限管理要求](../Topic/Requirements_for_Azure_Rights_Management.md)主题中的[支持 Azure RMS 的云订阅](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions)部分。

激活 Azure RMS 后，你的组织中的所有用户将可以对其文件应用信息保护，并且所有用户均可打开（使用）受 Azure RMS 保护的文件。 但是，如果你愿意，可以通过对分阶段部署使用加入控制来限制哪些人员可以应用信息保护。 有关详细信息，请参阅本主题中的[为分阶段部署配置加入控制](../Topic/Activating_Azure_Rights_Management.md#BKMK_OnboardingControls)部分。

## 激活权限管理
使用以下某一个过程来激活 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]。

> [!TIP]
> 也可以使用 Windows PowerShell cmdlet [Enable-Aadrm](http://msdn.microsoft.com/library/windowsazure/dn629412.aspx) 来激活 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]。

#### 从 Office 365 管理中心激活权限管理

1.  在注册包含 Rights Management 的 Office 365 计划后，[使用你的工作或学校帐户登录到 Office 365](https://portal.office.com/)，该帐户应是 Office 365 部署的管理员。

2.  如果未自动显示 Office 365 管理中心，请选择左上方的应用程序启动程序图标，然后选择“管理”。 “管理”磁贴只会向 Office 365 管理员显示。

    > [!TIP]
    > 有关管理中心的帮助，请参阅[关于 Office 365 管理中心 - 管理员帮助](https://support.office.com/article/About-the-Office-365-admin-center-Admin-Help-58537702-d421-4d02-8141-e128e3703547)。

3.  在左窗格中，单击“服务设置”。

4.  单击“Rights Management”。

    > [!NOTE]
    > 如果你没有看到此选项，原因可能是你的服务计划或产品版本无法支持权限管理，或者尚未经过升级以支持权限管理。
    > 
    > 请使用[Azure 权限管理要求](../Topic/Requirements_for_Azure_Rights_Management.md)主题中[支持 Azure RMS 的云订阅](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions)部分的信息来确认是否支持。 如果支持你的服务计划或产品版本，但你却没有看到“权限管理”选项，则原因可能是服务尚未升级。 若要获取有关此问题的帮助，请发送电子邮件至 [askipteam](mailto:askipteam@microsoft.com?subject=I%20cannot%20activate%20RMS)。

5.  在“Rights Management”页上，单击“管理”。

6.  在“权限管理”页上，单击“激活”。

7.  当提示**“是否要激活权限管理?”**时，请单击**“激活”**。

现在，应会显示“Rights Management 已激活”和用于停用的选项。

#### 从 Azure 经典门户激活 Rights Management

1.  注册 Azure 帐户后，[登录到 Azure 经典门户](http://go.microsoft.com/fwlink/p/?LinkID=275081)。

2.  在左窗格中，单击“ACTIVE DIRECTORY”。

3.  在“Active Directory”页中，单击“Rights Management”。

4.  选择要进行[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]的待管理目录，单击**“激活”**，然后确认你的操作。

    > [!NOTE]
    > 如果看到激活错误，则原因可能是你的服务计划或产品版本不支持 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]。
    > 
    > 请使用 [Azure 权限管理要求](../Topic/Requirements_for_Azure_Rights_Management.md)主题中[支持 Azure RMS 的云订阅](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions)部分的信息来确认是否提供 RMS 支持。 若要获取有关此问题的帮助，请发送电子邮件至 [askipteam](mailto:askipteam?subject=I%20cannot%20activate%20RMS)。

**“权限管理状态”**现在应该显示**“活动”**，而**“激活”**选项将替换为**“停用”**。

### Azure 经典门户中的 Rights Management 状态值和说明
除了“活动”状态（该状态指示 Rights Management 服务已启用并可供使用）外，你可能还会看到“非活动”、“不可用”或“未授权”。

|状态值|说明|
|-------|------|
|**活动**|[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 已启用并可供使用。|
|**非活动**|[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 已禁用，必须先将其激活，然后组织才能保护文件。|
|**Unavailable**|[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 服务已关闭。 请稍后重试。|
|**未授权**|你无权查看 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 服务的状态。 例如，你的帐户已被锁定，或者你不是所选租户的全局管理员。|

## <a name="BKMK_OnboardingControls"></a>为分阶段部署配置加入控制
如果你不希望所有用户都能立即使用 Azure RMS 保护文件，则可以使用 [Set-AadrmOnboardingControlPolicy](http://msdn.microsoft.com/library/azure/dn857521.aspx) Windows PowerShell 命令来配置用户加入控制。 在激活 Azure RMS 之前或之后，你可以运行此命令。

> [!IMPORTANT]
> 若要使用此命令，你必须安装至少 **2.1.0.0** 版的 [Azure RMS Windows PowerShell 模块](http://go.microsoft.com/fwlink/?LinkId=257721)。
> 
> 若要查看已安装的版本，请运行：**(Get-Module aadrm –ListAvailable).Version**

例如，如果出于测试目的，你最初只想让“IT 部门”组（具有对象 ID fbb99ded-32a0-45f1-b038-38b519009503）中的管理员能够保护内容，请使用以下命令：

```
Set-AadrmOnboardingControlPolicy – SecurityGroupObjectId fbb99ded-32a0-45f1-b038-38b519009503
```
请注意：对于此配置选项，必须指定组，不能指定单个用户。

或者，如果你要确保只有正确获得使用 Azure RMS 的许可的用户可以保护内容，请使用以下命令：

```
Set-AadrmOnboardingControlPolicy -UseRmsUserLicense $true
```
使用这些加入控制时，组织中的所有用户始终可以使用由用户的子集保护的受保护内容，但他们自身将不能从客户端应用程序应用信息保护。 例如，他们将在其 Office 客户端中看不到激活 Azure RMS 时自动发布的默认模板，也看不到你可能会配置的自定义模板。  服务器端应用程序（如 Exchange）可以为 RMS 集成实现自己的每用户控制，以获得相同的结果。

## 后续步骤
为组织激活 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]之后，向用户和管理员推出 [Azure 权限管理部署路线图](../Topic/Azure_Rights_Management_Deployment_Roadmap.md)之前，你可以使用 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]来检查是否还需要执行其他配置步骤。 例如，你可能需要使用[自定义模板](http://technet.microsoft.com/library/dn642472.aspx)使用户更方便地向文件应用信息保护，通过安装 [RMS 连接器](http://technet.microsoft.com/library/dn375964.aspx)来连接本地服务器以使用 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]，以及部署 [Rights Management](http://technet.microsoft.com/library/jj585031.aspx) 共享应用程序，以便对所有设备上的所有文件类型进行保护。 Exchange Online 和 SharePoint Online 等 Office 服务需要进行其他配置，然后才能使用其信息权限管理 (IRM) 功能。 但是，如果不需要执行其他配置步骤，请参阅[使用 Azure 权限管理](../Topic/Using_Azure_Rights_Management.md)以获取操作指导，帮助你的组织成功完成部署。

有关应用程序如何与 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]配合工作的信息，请参阅[应用程序如何支持 Azure 权限管理](../Topic/How_Applications_Support_Azure_Rights_Management.md)。

## 请参阅
[配置 Azure 权限管理](../Topic/Configuring_Azure_Rights_Management.md)

