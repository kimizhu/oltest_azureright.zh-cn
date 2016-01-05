---
description: na
keywords: na
pagetitle: Azure Rights Management Deployment Roadmap
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 086600c2-c5d8-47ec-a4c0-c782e1797486
---
# Azure 权限管理部署路线图
使用以下步骤为你的组织准备、实现和管理 Azure Rights Management (Azure RMS)。

不过，如果你只是想要自己大致试用一下 Azure RMS，请不是将它部署在生产环境中，具体请参阅 [Azure Rights Management 快速入门教程](../Topic/Quick_Start_Tutorial_for_Azure_Rights_Management.md)。

> [!IMPORTANT]
> 在执行以下步骤之前，请确保已查看 [Azure 权限管理要求](../Topic/Requirements_for_Azure_Rights_Management.md)。

## 步骤 1：确认你有一个包含 Azure Rights Management 的订阅
有多种类型的订阅包含 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]。 请参阅 [Azure 权限管理要求](../Topic/Requirements_for_Azure_Rights_Management.md)主题中的[支持 Azure RMS 的云订阅](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions)，并参考 [Rights Management 服务 (RMS) 产品比较](https://technet.microsoft.com/dn858608)中的表格，检查订阅是否包含你要在组织中使用的功能。

## 步骤 2：准备你的租户帐户以便使用权限管理
开始使用 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 之前，请进行以下准备工作：

1.  确保 Azure 或 Office 365 租户包含 Azure RMS 用来对你组织中的用户进行身份验证的用户帐户和组。 如有必要，请创建这些帐户和组，或者从本地目录同步这些帐户和组。 有关详细信息，请参阅[准备 Azure 权限管理](../Topic/Preparing_for_Azure_Rights_Management.md)。

2.  决定你是希望 Microsoft 管理你的租户密钥（默认设置），还是自行生成和管理你的租户密钥（也称为“自带密钥”，简称 BYOK）。 请注意，如果你当前使用了 Exchange Online，则不能使用 BYOK。 有关详细信息，请参阅[计划和实现你的 Azure 权限管理租户密钥](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md)。

3.  至少在一台可以访问 Internet 的计算机上安装适用于 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 的 Windows PowerShell 模块。 你可以立即执行此步骤，也可以稍后执行。 有关详细信息，请参阅[安装适用于 Azure 权限管理的 Windows PowerShell](../Topic/Installing_Windows_PowerShell_for_Azure_Rights_Management.md)。

4.  如果你目前正在使用本地权限管理服务，则必须执行以下操作：执行迁移操作以将密钥、模板和 URL 移到云中。 有关详细信息，请参阅[从 AD RMS 迁移到 Azure 权限管理](../Topic/Migrating_from_AD_RMS_to_Azure_Rights_Management.md)。

5.  激活权限管理，然后即可使用该服务。 如果需要分阶段部署，请配置用户载入控件以将其使用限于特定用户。 有关详细信息，请参阅[激活 Azure 权限管理](../Topic/Activating_Azure_Rights_Management.md)。

（可选）考虑进行以下配置：

-   自定义模板，前提是默认权限策略模式不足以满足你组织的要求。 你可以立即执行此步骤，也可以稍后执行。 有关详细信息，请参阅[为 Azure 权限管理配置自定义模板](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md)。

-   使用日志记录，以便你能够监控你组织使用权限管理的情况。 你可以立即执行此步骤，也可以稍后执行。 有关详细信息，请参阅[记录和分析 Azure 权限管理使用情况](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md)。

## 步骤 3：配置要运行 Rights Management 的应用程序和服务
配置应用程序的过程可能包括安装权限管理共享应用程序、在 SharePoint Online 或 Exchange Online 中启用对信息权限管理 (IRM) 功能的支持。 有关详细信息，请参阅[为 Azure 权限管理配置应用程序](../Topic/Configuring_Applications_for_Azure_Rights_Management.md)。

如果你的现有 IT 服务（例如数据泄漏防护 (DLP) 解决方案、内容加密网关 (CEG) 和反恶意软件产品）需要检查 Azure RMS 将要保护的文件，请将服务帐户配置为 Azure RMS 的超级用户。 有关详细信息，请参阅[为 Azure Rights Management 和发现服务或数据恢复配置超级用户](../Topic/Configuring_Super_Users_for_Azure_Rights_Management_and_Discovery_Services_or_Data_Recovery.md)。

如果你希望将 Azure 权限管理用于本地服务，请安装和配置权限管理连接器。 有关详细信息，请参阅[部署 Azure 权限管理连接器](../Topic/Deploying_the_Azure_Rights_Management_Connector.md)。

## 步骤 4：发布和使用受权限保护的内容
现在，你可以发布和使用受保护的内容，并记录公司如何使用 Rights Management。 有关详细信息，请参阅[使用 Azure 权限管理](../Topic/Using_Azure_Rights_Management.md)。

## 步骤 5：根据需要管理租户帐户的权限管理
开始使用 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 时，你可能发现适用于 Windows PowerShell 的 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 模块可以帮助你编写脚本或自动执行管理更改。 有关详细信息，请参阅[使用 Windows PowerShell 管理 Azure 权限管理](../Topic/Administering_Azure_Rights_Management_by_Using_Windows_PowerShell.md)。

## 请参阅
[配置 Azure 权限管理](../Topic/Configuring_Azure_Rights_Management.md)

