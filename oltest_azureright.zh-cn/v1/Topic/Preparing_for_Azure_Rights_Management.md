---
description: na
keywords: na
pagetitle: Preparing for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: afbca2d6-32a7-4bda-8aaf-9f93f5da5abc
---
# 准备 Azure 权限管理
在你注册云订阅并创建组织的 [!INCLUDE[o365_1](../Token/o365_1_md.md)] 或 Azure Active Directory 帐户之后，即可随时启用 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 服务。

但是，在执行此操作之前，请确保已准备好以下项：

-   在云中手动或自动创建的已从 Active Directory 域服务 (AD DS) 同步的用户帐户和组。

    当你同步本地帐户和组时，并非所有属性都需要同步。 有关必须为 Azure RMS 同步的属性的列表，请参阅 Azure Active Directory 文档中的此 [Azure RMS 部分](https://azure.microsoft.com/documentation/articles/active-directory-aadconnectsync-attributes-synchronized/)。 为了便于部署，我们建议你使用 [Azure AD Connect](http://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) 将本地目录连接到 Azure Active Directory，但你可以使用任何目录同步方法实现相同的结果。

-   云中支持邮件的组，将用于权限管理。 这些组可以是内置组或手动创建的组，其中包含将使用权限管理的用户。

    如果你有 Exchange Online，则可以使用 Exchange 管理中心创建和使用支持邮件的组。 如果你有 AD DS 并要同步到 Azure AD，则可以创建和使用支持邮件的组（安全组或通讯组）。

## 启用权限管理
默认情况下，在你注册 [!INCLUDE[o365_2](../Token/o365_2_md.md)] 或 Azure AD 帐户时，[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 处于禁用状态。 若要为组织启用 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]，你必须激活服务。 有关详细信息，请参阅[激活 Azure 权限管理](../Topic/Activating_Azure_Rights_Management.md)。

## 请参阅
[配置 Azure 权限管理](../Topic/Configuring_Azure_Rights_Management.md)

