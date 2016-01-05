---
description: na
keywords: na
pagetitle: Frequently Asked Questions for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 71ce491f-41c1-4d15-9646-455a6eaa157d
---
# Azure 权限管理常见问题解答
Microsoft [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]（也称为 Azure RMS）的某些常见问题：

## 部署 Azure RMS 需要做好哪些准备，如何能够顺利完成部署？
首先，请查看 [Azure 权限管理要求](../Topic/Requirements_for_Azure_Rights_Management.md)，其中包含了有关云订阅选项、如何将本地服务器与 Azure RMS 配合使用、当前不支持的部署方案以及哪些设备、应用程序支持 Azure RMS 的信息以及你需要的防火墙和代理服务器的 IP 地址和域名列表链接。 你还可能需要查看 [Azure 权限管理入门](../Topic/Getting_Started_with_Azure_Rights_Management.md)部分中的其他主题，以基本了解 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 如何帮助保护组织的数据、如何与应用程序配合工作、它与 Active Directory Rights Management 的本地版本比起来如何，并了解特定于 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 的术语和缩写。

然后，便可以自行测试 Azure RMS，或者为组织部署 Azure RMS。请使用 [Azure 权限管理部署路线图](../Topic/Azure_Rights_Management_Deployment_Roadmap.md)来获取步骤列表，以及用于了解详细信息和操作说明的链接。

如果需要更多信息、资源和支持选项，请参阅 [Azure 权限管理的信息和支持](../Topic/Information_and_Support_for_Azure_Rights_Management.md)。

## 可以将 Azure RMS 与我的本地服务器集成吗？
适用。 Azure RMS 可以与你的本地服务器集成，如 Exchange Server、SharePoint 和 Windows 文件服务器。 为此，你需要使用 [Rights Management 连接器](https://technet.microsoft.com/library/dn375964.aspx)。 或者，如果你只想对 Windows Server 使用文件分类基础结构 (FC)，则可使用 [RMS 保护 cmdlet](https://technet.microsoft.com/library/mt601315%28v=ws.10%29.aspx)。 你还可以使用 [Azure AD Connect](http://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)，将 Active Directory 域控制器与 Azure AD 同步和联合，为用户提供更为契合的身份验证体验。

Azure RMS 将根据需要自动生成并管理 XrML 证书，因此它不使用本地 PKI。 有关 Azure RMS 如何使用证书的详细信息，请参阅[什么是 Azure 权限管理？](../Topic/What_is_Azure_Rights_Management_.md)主题中的[Azure RMS 工作原理演练：首次使用、内容保护、内容使用](../Topic/What_is_Azure_Rights_Management_.md#BKMK_Walthrough)部分。

## 我对 Exchange 采用混合部署：Exchange Online 上存在一些用户，而其他用户则在 Exchange Server 上。Azure RMS 支持这种部署吗？
绝对支持，而且很棒的是，用户将受到无缝保护，并可以在两种 Exchange 部署上使用受保护的电子邮件和附件。 对于此配置，[激活 Azure RMS](https://technet.microsoft.com/library/jj658941.aspx) 并[启用适用于 Exchange Online 的 IRM](https://technet.microsoft.com/library/dn151475%28v=exchg.150%29.aspx)，然后[部署并配置适用于 Exchange Server 的 RMS 连接器](https://technet.microsoft.com/library/dn375964.aspx)。

## 如果我在生产中部署 Azure RMS，我的公司是否就只能使用该解决方案？或者是否存在无法访问由 Azure RMS 进行保护的内容的风险？
不会，数据始终由你控制，并可以继续访问，即使你决定不再使用 Azure RMS 也是如此。 有关详细信息，请参阅[解除 Azure Rights Management 授权和停用 Azure Rights Management](../Topic/Decommissioning_and_Deactivating_Azure_Rights_Management.md)。

但是，在你解除 Azure RMS 部署授权前，我们希望倾听你的意见，了解你为什么做出这个决定。 如果 Azure RMS 未能满足你的业务要求，请与我们取得联系，或许在不久的将来会计划新功能或存在替代方法。 将电子邮件发送到 [AskIPTeam@Microsoft.com](mailto:askipteam@microsoft.com?subject=Planning%20to%20decommission%20Azure%20RMS)，我们将很高兴讨论你的技术和商业要求。

## 是否可以控制哪些用户能够使用 Azure RMS 来保护内容？
可以，Azure RMS 针对这种情况提供了用户登记控制功能。 有关详细信息，请参阅[激活 Azure 权限管理](../Topic/Activating_Azure_Rights_Management.md)主题中的[为分阶段部署配置加入控制](../Topic/Activating_Azure_Rights_Management.md#BKMK_OnboardingControls)部分。

## 是否可以防止用户与特定的组织共享受保护文档？
Azure RMS 的最大优势之一在于，它支持企业与企业的协作，同时，你无需为每个合作伙伴组织配置显式信任关系，因为 Azure AD 会代你处理好身份验证。

我们未提供相应的管理选项来防止用户与特定的组织安全共享文档。 例如，你想要阻止某家你不信任的或者竞争的组织。 防止 Azure RMS 向该组织的用户发送受保护文档没有任何意义，因为你的用户到时还是会共享未保护的文档，而这也许是你最终希望发生的事情！ 例如，你无法识别谁在与这些组织的用户共享公司机密文档，但是，如果文档（或电子邮件）受 Azure RMS 的保护，则你可以识别。

## 如果我与公司之外的用户共享受保护文档，该用户如何进行身份验证。
Azure RMS 始终使用 Azure Active Directory 帐户和关联的电子邮件地址进行用户身份验证，这为管理员将企业间的协作变得天衣无缝。 如果其他组织使用 Azure 服务，用户将具有 Azure Active Directory 帐户，即使这些帐户是在本地创建和进行管理，然后同步到 Azure。  如果组织具有 Office 365，此服务在后台还会将 Azure Active Directory 用于用户帐户。  如果用户的组织不具有托管的 Azure 帐户，用户可以注册[个人 RMS](https://technet.microsoft.com/library/dn592127.aspx)，这将为组织创建非托管的 Azure 租户和目录，并为用户创建帐户，因此，此用户可以进行 Azure RMS 身份验证。

这些帐户的身份验证方法各不相同，具体取决于其他组织中的管理员如何配置 Azure Active Directory 帐户。 例如，他们可以使用为这些帐户、多重身份验证 (MFA)、联合身份验证创建的密码，或在 Active Directory 域服务中创建、然后同步到 Azure Active Directory 的密码。

## 我可以将公司之外的用户添加到自定义模板吗？
适用。  创建最终用户（和管理员）可以从应用程序中选择的自定义模板，可使用户使用你指定的预定义策略应用信息保护变得简单快捷。 该模板中的设置之一是哪些用户能够访问内容，而且你可以指定组织中的用户和组以及组织之外的用户。

若要指定不属于组织的用户，请使用[适用于 Azure Rights Management 的 Windows PowerShell 模块](https://technet.microsoft.com/library/jj585012.aspx)：

-   **使用权限定义对象创建或更新模板**。    在权限定义对象中指定外部电子邮件地址及其权限，然后你将使用该地址创建或更新模板。 指定权限定义对象时，可使用 [New-AadrmRightsDefinition](https://msdn.microsoft.com/library/azure/dn727080.aspx) cmdlet 来创建一个变量，然后将该变量提供给 -RightsDefinition 参数，并可使用 [Add-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727075.aspx) cmdlet（如果是新模板）或 [Set-AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727076.aspx) cmdlet（如果需要修改现有模板）。 但是，如果你是将这些用户添加到现有模板中，则需要在模板中为现有组定义权限定义对象，不仅仅只需为外部用户进行此类操作。

有关自定义模板的详细信息，请参阅[为 Azure 权限管理配置自定义模板](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md)。

## Azure RMS 支持哪些设备和哪种文件类型？
有关支持的设备列表，请参阅[Azure 权限管理要求](../Topic/Requirements_for_Azure_Rights_Management.md)主题中的[支持 Azure RMS 的客户端设备](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedDevices)部分。 由于并非所有受支持的设备目前都能支持所有 RMS 功能，因此，还请务必查看该主题中的[客户端设备功能](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_ClientCapabilities)表。

Azure RMS 能够支持所有文件类型。 对于文字、图像、Microsoft Office (Word、Excel、PowerPoint) 文件、.pdf 文件和一些其他应用程序文件类型，Azure RMS 提供的本地保护包括对权利（权限）的加密和执行。 对于其他应用程序和文件类型，通用保护提供文件封装和验证以确认用户是否授权打开文件。

对于 Azure RMS 以本机方式支持的文件扩展名列表，请参阅 [Rights Management 共享应用程序管理员指南](http://technet.microsoft.com/library/dn339003.aspx)中的[支持的文件类型和文件扩展名](http://technet.microsoft.com/library/dn339003.aspx)部分。 未列出的文件扩展名支持使用 RMS 共享应用程序，可自动提供通用保护保护这些文件。

## 你们何时支持从 AD RMS 迁移？
最初，Azure RMS 不支持从本地部署的权限管理（如 AD RMS）迁移。 但是，现在支持这种迁移。

有关详细信息，请参阅[从 AD RMS 迁移到 Azure 权限管理](../Topic/Migrating_from_AD_RMS_to_Azure_Rights_Management.md)。

## 我们很想将 BYOK 和 Azure RMS 一起使用，但却了解到这与 Exchange Online 不兼容，你有什么建议呢？
不要让此当前限制延迟 Azure RMS 部署。 如果你具有 Exchange Online 并想要使用自带密钥 (BYOK)，我们建议你暂时以默认密钥管理模式部署 Azure RMS，即由 Microsoft 生成和管理你的密钥。 如此一来，你现在可以获取保护重要文件和电子邮件的所有好处，并可以选择以后移动到 BYOK（例如，当 Exchange Online 不支持 BYOK 时）。

但是，如果你的公司策略要求你使用硬件安全模块 (HSM)，但这将阻止你的 Azure RMS 部署，可以另作选择，将 Azure RMS 和 BYOK 一起部署，只不过 Exchange 的 RMS 功能会减弱。 有关详细信息，请参阅[计划和实现你的 Azure 权限管理租户密钥](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md)主题中的[BYOK 定价和限制](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_Pricing)部分。

## 我正在寻找的一项功能看起来不适用于 SharePoint 保护的库。是否计划了针对此功能的支持？
当前，SharePoint 通过使用 IRM 保护的库，支持 RMS 保护的文档，但不支持自定义模板、文档跟踪和一些其他功能。  有关详细信息，请展开[应用程序如何支持 Azure 权限管理](../Topic/How_Applications_Support_Azure_Rights_Management.md)主题中的 [SharePoint Online 和 OneDrive for Business:IRM 配置](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharePointOnline)部分。

如果你对当前不支持的某项特定功能感兴趣，请务必关注 [RMS 团队博客](http://blogs.technet.com/b/rms/)上的公告。

## 如何在 SharePoint Online 中配置 OneDrive for Business，以便用户可以安全地与公司内外的人员共享他们的文件？
默认情况下，作为 Office 365 管理员，你不用执行此配置，用户会进行配置。

正如 SharePoint 站点管理员为其拥有的 SharePoint 库启用并配置 IRM 一样，根据 OneDrive for Business 的设计，用户也需要为自己的 OneDrive for Business 库启用并配置 IRM。  不过，你可以使用 PowerShell 为他们执行此类操作。 若需说明，请参阅[为 Azure 权限管理配置应用程序](../Topic/Configuring_Applications_for_Azure_Rights_Management.md)文章中的 [SharePoint Online 和 OneDrive for Business:IRM 配置](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharePointOnline)部分。

## 是否能够提供有关成功部署 RMS 的任何诀窍或技巧？
在考察大量的部署并聆听客户、合作伙伴、顾问和支持工程师的意见后，结合自身的经验，我们很乐意与你分享下面这个极其有效的诀窃：**设计并部署简单的权限策略**。

由于 Azure RMS 支持与任何人安全共享，因此，你完全有理由相信自己的信息保护措施的覆盖面。 但是，对权限策略应持保守态度。 对于许多组织而言，对业务产生的最大影响来自于通过应用默认权限策略模板防止数据泄漏，将其访问权限限制给组织中的人员。 当然，你可以根据需要采取粒度级比这高得多的措施 - 例如，防止人员打印、编辑，等等。但是，对于确实需要高级安全性的文档，请将更高粒度级的限制保留为例外措施，并且不要一开始就实施这些限制性更强的策略，而是计划采取分阶段的实施方案。

## 哪些功能可以或不可以用于 Azure RMS 的不同订阅？
对于支持 Azure RMS 的付费订阅（Office 365、Azure RMS Premium 和 Enterprise Mobility Suite），在支持的 RMS 功能方面存在一些差异。 有关列表，请参阅 [Rights Management 服务 (RMS) 产品比较](http://technet.microsoft.com/dn858608)。

支持 Azure RMS（个人 RMS）的免费订阅支持使用受 Azure RMS 保护的内容。 有关详细信息，请参阅[个人 RMS 和 Azure 权限管理](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md)。

## 我在哪里可以获取有关 Azure RMS（个人 RMS）免费订阅的技术信息 — 例如它的工作原理、如何控制帐户、哪些域名不可用？
你可以在[个人 RMS 和 Azure 权限管理](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md)主题中找到这些问题的答案。

## 我们如何重新获取对由已离职员工保护的文件的访问权限？
使用 Azure RMS 的超级用户功能，它可以让授权用户对组织的 RMS 租户授予的所有使用许可证行使所有者权限。 根据需要，此相同功能可以让授权服务编写文件索引和检查文件。

有关详细信息，请参阅[为 Azure Rights Management 和发现服务或数据恢复配置超级用户](../Topic/Configuring_Super_Users_for_Azure_Rights_Management_and_Discovery_Services_or_Data_Recovery.md)。

## Rights Management 可以防止屏幕截图吗？
Rights Management 能够阻止大多数常用屏幕截图工具进行屏幕截图，这样可以防止因意外或疏忽而泄露机密信息或敏感信息。 不过，用户可以通过多种方式来共享显示在屏幕上的数据，进行屏幕截图只是其中一种方法。 例如，如果想要共享所显示的信息，用户可以使用带相机的手机拍照，可以重新键入相关数据，还可以直接通过口头方式将其传达给某人。

这些示例表明，单纯通过技术手段并不总能阻止用户共享不应共享的数据。 虽然 Rights Management 可以通过授权和使用策略的方式来确保重要数据的安全性，但在使用企业权限管理解决方案时还应加入其他控制手段。 例如，可以实施物理安全措施，可以仔细盘查和监视有权访问组织数据的人员，还可以进行用户教育，让用户了解哪些数据是不应共享的。

## 我在何处可以找到 Azure RMS 的支持信息，例如法律、合规性和 SLA？
Azure RMS 支持其他服务，也依赖于其他服务。 如果你寻找的信息与 Azure RMS 相关，但与如何使用 Azure RMS 服务无关，请查看以下资源：

**法律和隐私：**

-   对于 Microsoft Azure 协议信息：[Microsoft Azure 协议](http://azure.microsoft.com/support/legal/subscription-agreement/)

-   对于 Microsoft Azure 隐私信息：[Microsoft Azure 隐私声明](http://azure.microsoft.com/support/legal/privacy-statement/)

**安全、相容性和审核：**

请参阅[什么是 Azure 权限管理？](../Topic/What_is_Azure_Rights_Management_.md)主题中的[安全、合规性和法规要求](../Topic/What_is_Azure_Rights_Management_.md#BKMK_RMScompliance)部分。 此外：

-   对于 Azure RMS 的外部认证：[Microsoft Azure 信任中心](http://azure.microsoft.com/support/trust-center/)

-   对于 FIPS 140 信息：[FIPS 140 验证](https://technet.microsoft.com/library/security/cc750357.aspx)

**服务级别协议：**

-   Azure RMS 的服务级别协议（按所选国家/地区列出）：[服务级别协议](http://microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37)

-   Azure Active Directory 的服务级别协议：[服务级别协议](http://azure.microsoft.com/support/legal/sla/)

**文档：**

-   Azure Active Directory 文档站点：[Azure Active Directory](http://azure.microsoft.com/documentation/services/active-directory/)

-   Azure Active Directory 库：[Azure Active Directory](http://msdn.microsoft.com/library/azure/jj673460.aspx)

-   Office 365 库：[Office 365](http://technet.microsoft.com/library/dn127064%28v=office.14%29.aspx)

## 如果我的问题不在这里，我该如何操作？
使用 [Azure 权限管理的信息和支持](../Topic/Information_and_Support_for_Azure_Rights_Management.md)中列出的链接和资源。

此外，我们还为最终用户制作了常见问题解答：

-   [适用于 Windows 的 Rights Management 共享应用程序常见问题](https://technet.microsoft.com/dn467883)

-   [适用于移动平台和 Mac 平台的 Rights Management 共享应用程序的常见问题](https://technet.microsoft.com/dn451248)

-   [文档跟踪常见问题](http://go.microsoft.com/fwlink/?LinkId=523977)

此常见问题页将定期更新，其中新添加的内容将在 [Microsoft 权限管理 (RMS) 团队](http://blogs.technet.com/b/rms/)博客上的每月文档更新公告中列出。

> [!TIP]
> 可以使用该博客上的[文档标记](http://blogs.technet.com/b/rms/archive/tags/docs/)更轻松地找到这些文档公告。

## 请参阅
[Azure 权限管理入门](../Topic/Getting_Started_with_Azure_Rights_Management.md)

