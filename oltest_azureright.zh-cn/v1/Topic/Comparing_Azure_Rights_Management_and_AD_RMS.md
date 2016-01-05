---
description: na
keywords: na
pagetitle: Comparing Azure Rights Management and AD RMS
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8123bd62-1814-4d79-b306-e20c1a00e264
---
# 比较 Azure 权限管理和 AD RMS
如果你了解或以前部署过 Active Directory Rights Management Services (AD RMS)，你可能想知道 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] (Azure RMS) 在功能和要求方面与它相比有何差别。 我们使用以下表格，对 Azure RMS 和 AD RMS 的功能和优势进行了并排比较。 如果你有安全方面的比较问题，请参阅本主题中的[对签名和加密的加密控制](../Topic/Comparing_Azure_Rights_Management_and_AD_RMS.md#BKMK_CryptographicControls)部分。

> [!NOTE]
> 为了简化这种比较，本文重复了[Azure 权限管理要求](../Topic/Requirements_for_Azure_Rights_Management.md)中的一些信息。 使用该主题可获取有关 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]的更加具体的支持和版本信息。

|[!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] (Azure RMS)|Active Directory 权限管理服务 (AD RMS)|
|-----------------------------------------------------------------------------------------|------------------------------------|
|支持 Microsoft Online Services（例如  Exchange Online 和 SharePoint Online 以及 Office 365）中的信息权限管理 (IRM) 功能。<br /><br />还支持本地 Microsoft 服务器产品，例如 Exchange Server、SharePoint Server 以及运行 Windows Server 和文件分类基础结构 (FCI) 的文件服务器。|支持本地 Microsoft 服务器产品，例如 Exchange Server、SharePoint Server 以及运行 Windows Server 和文件分类基础结构 (FCI) 的文件服务器。|
|实现组织之间和任何组织内用户之间的隐式信任。 这意味着在用户使用 [!INCLUDE[o365_1](../Token/o365_1_md.md)]、[!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 的情况下，或在用户注册了个人 RMS 的情况下，受保护内容可在同一组织或不同组织的用户之间共享。|信任必须在两个组织间以直接点对点的关系显式定义，方法是使用受信任用户域 (TUD) 或使用 Active Directory 联合身份验证服务 (AD FS) 创建的联合信任。|
|提供两个默认权限策略模板，将内容的访问权限仅限于自己的组织范围内；一个模板提供受保护内容的只读查看，另一个模板提供受保护内容的写入或修改权限。<br /><br />你还可以创建自己的自定义模板，其中包括只对用户的子集可见的部门模板。 有关详细信息，请参阅[为 Azure 权限管理配置自定义模板](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md)。<br /><br />此外，如果模板不能满足需求，用户可以定义自己的一组权限。|没有默认权限策略模板；必须创建这些模板，然后分发它们。 有关详细信息，请参阅 [AD RMS 策略模板注意事项](http://go.microsoft.com/fwlink/?LinkId=154765)。<br /><br />此外，如果模板不能满足需求，用户可以定义自己的一组权限。|
|支持的 Microsoft Office 最低版本为 Office 2010，它需要 [RMS 共享应用程序](http://technet.microsoft.com/library/dn339006.aspx)。<br /><br />Microsoft Office for Mac：<br /><br />-   Microsoft Office for Mac 2016：支持<br />-   Microsoft Office for Mac 2011：不支持|支持的 Microsoft Office 最低版本为 Office 2007。<br /><br />Microsoft Office for Mac：<br /><br />-   Microsoft Office for Mac 2016：支持<br />-   Microsoft Office for Mac 2011：支持|
|支持适用于 Windows、Mac 计算机和移动设备的 [RMS 共享应用程序](https://technet.microsoft.com/library/dn919648%28v=ws.10%29.aspx)。<br /><br />此外，RMS 共享应用程序支持以下内容：<br /><br />-   与其他组织的用户共享。<br />-   电子邮件通知，让发件人知道有人尝试打开受保护附件。<br />-   适用于用户的文档跟踪站点，包括撤消文档的功能。|支持适用于 Windows、Mac 计算机和移动设备的 [RMS 共享应用程序](https://technet.microsoft.com/library/dn919648%28v=ws.10%29.aspx)。 但是，共享不支持与其他组织的用户共享、电子邮件通知、或文档跟踪站点以及用户撤消文档的功能。|
|可以[在使用 RMS 共享应用程序时，通过本机保护或一般性保护](https://technet.microsoft.com/library/dn339003%28v=ws.10%29.aspx)，保护所有文件类型。<br /><br />对于其他应用程序，请查看[客户端功能表](https://technet.microsoft.com/library/dn655136.aspx)。|可以[在使用 RMS 共享应用程序时，通过本机保护或一般性保护](https://technet.microsoft.com/library/dn339003%28v=ws.10%29.aspx)，保护所有文件类型。<br /><br />对于其他应用程序，请查看[客户端功能表](https://technet.microsoft.com/library/dn655136.aspx)。|
|支持的 Windows 客户端最低版本为 Windows 7。|支持的 Windows 客户端最低版本为 Windows Vista Service Pack 2。|
|移动设备支持包括 Windows Phone、Android、iOS 和 Windows RT。<br /><br />在支持 Exchange ActiveSync IRM 协议的所有移动设备平台上，也支持使用该协议管理电子邮件。|移动设备支持包括 Windows Phone、Android、iOS 和 Windows RT，并需要 [Active Directory Rights Management 服务移动设备扩展](http://technet.microsoft.com/library/a69ead9d-7dd3-4b38-9830-4728e9757341)。<br /><br />在支持 Exchange ActiveSync IRM 协议的所有移动设备平台上，支持使用 Exchange ActiveSync IRM 管理电子邮件。|
|支持适用于计算机和移动设备的多因素身份验证 (MFA)。<br /><br />有关详细信息，请参阅[多因素身份验证 (MFA) 和 Azure RMS](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_MFA)主题中的[Azure 权限管理要求](../Topic/Requirements_for_Azure_Rights_Management.md)部分。|如果将 IIS 配置为请求证书，将支持智能卡身份验证。|
|支持加密模式 2，而无需额外配置，该模式针对各种密钥长度和加密算法提供更强大的安全性。<br /><br />有关详细信息，请参阅本主题中的[对签名和加密的加密控制](../Topic/Comparing_Azure_Rights_Management_and_AD_RMS.md#BKMK_CryptographicControls)部分以及 [AD RMS 加密模式](http://go.microsoft.com/fwlink/?LinkId=266659)。|默认情况下支持加密模式 1，需要额外配置才能支持加密算法 2，以提供更强大的安全性。<br /><br />有关详细信息，请参阅本主题中的[对签名和加密的加密控制](../Topic/Comparing_Azure_Rights_Management_and_AD_RMS.md#BKMK_CryptographicControls)部分以及 [AD RMS 加密模式](http://go.microsoft.com/fwlink/?LinkId=266659)。|
|支持从 AD RMS 迁移，如果需要，支持迁移到 AD RMS：<br /><br />-   [从 AD RMS 迁移到 Azure 权限管理](../Topic/Migrating_from_AD_RMS_to_Azure_Rights_Management.md)<br />-   [解除 Azure Rights Management 授权和停用 Azure Rights Management](../Topic/Decommissioning_and_Deactivating_Azure_Rights_Management.md)|支持从 Azure RMS 迁移和迁移到 Azure RMS：<br /><br />-   [解除 Azure Rights Management 授权和停用 Azure Rights Management](../Topic/Decommissioning_and_Deactivating_Azure_Rights_Management.md)<br />-   [从 AD RMS 迁移到 Azure 权限管理](../Topic/Migrating_from_AD_RMS_to_Azure_Rights_Management.md)|
|需要 RMS 许可证才能保护内容。 无需 RMS 许可证即可使用已受 Azure RMS（包括另一个组织的用户）保护的内容。<br /><br />有关详细信息，请参阅[Azure 权限管理要求](../Topic/Requirements_for_Azure_Rights_Management.md)中的[支持 Azure RMS 的云订阅](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions)部分。|需要 RMS 许可证才能保护内容，以及使用已受 AD RMS 保护的内容。<br /><br />有关 AD RMS 授权的详细信息，如果是一般信息，请参阅[客户端访问许可证和管理许可证](https://www.microsoft.com/en-us/Licensing/product-licensing/client-access-license.aspx)，如果是特定信息，请联系 Microsoft 合作伙伴或 Microsoft 代表。|

## <a name="BKMK_CryptographicControls"></a>对签名和加密的加密控制
[!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 始终将 RSA 2048 用于所有公钥加密，将 SHA 256 用于签名操作。 相比之下，AD RMS 支持 RSA 1024 和 RSA 2048，还将 SHA 1 或 SHA 256 用于签名操作。

[!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 和 AD RMS 都将 AES 128 用于对称加密。

如果创建了租户密钥并由 Microsoft 管理（默认），或者如果你管理自己的租户密钥（称为 BYOK），[!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 将遵守 FIPS 140-2。 有关管理租户密钥的详细信息，请参阅[计划和实现你的 Azure 权限管理租户密钥](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md)。

## 请参阅
[Azure 权限管理入门](../Topic/Getting_Started_with_Azure_Rights_Management.md)

