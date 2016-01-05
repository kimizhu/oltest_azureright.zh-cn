---
description: na
keywords: na
pagetitle: RMS for Individuals and Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2efcb440-fefd-45e9-872b-f471573aadf2
---
# 个人 RMS 和 Azure 权限管理
个人 RMS 是供组织内的用户使用的一种免费自助服务订阅，用户在下列情况下可以使用：用户收到了受 Microsoft Azure Rights Management (Azure RMS) 保护的敏感文件，但他们无法进行身份验证，因为 IT 部门不会管理他们的 Azure 帐户。 例如，IT 部门没有 Office 365 或不使用 Azure 服务。

这些用户可以注册免费的工作或学校帐户来使用 Azure RMS，以及下载并安装 Rights Management 共享应用程序。 因此，这些用户现在可以进行身份验证以证明他们就是接收受保护文件的人，然后在计算机或移动设备上读取受保护文件。

在 Windows 计算机上使用 Rights Management 共享应用程序，这些用户还可以就地保护文件或者通过电子邮件将受保护文件发送给其组织内外的人员。 如果这些电子邮件收件人的组织也没有管理 Azure 用户帐户，他们也可以注册个人 RMS 帐户以读取受保护的电子邮件附件。

> [!IMPORTANT]
> 此免费订阅确保经授权的人员始终可以阅读受保护的文件。 目前，你还可以使用此免费订阅保护文档和创建新的受保护电子邮件，但创作新的受保护内容的功能仅供试用，并可能会在将来删除。 有关使用个人 RMS 来保护内容的详细信息及任何变更，请参阅 [Microsoft Rights Management 服务条款](https://portal.aadrm.com/Legal/Service)。

有关如何使用免费的权限管理共享应用程序来保护文件的详细信息，请参阅[权限管理共享应用程序用户指南](http://technet.microsoft.com/library/dn339006.aspx)。

个人 RMS 是一个 Azure Active Directory 支持的自助注册示例。 有关工作原理，请参阅 Microsoft Azure 文档中的[什么是 Azure 自助注册？](https://azure.microsoft.com/documentation/articles/active-directory-self-service-signup/)。 使用以下部分，获取特定于个人 RMS 的详细信息：

-   [用户如何注册个人 RMS](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md#BKMK_SignUp)

    -   [技术概述](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md#BKMK_TechnicalOverview)

-   [管理员如何才能控制为个人 RMS 创建的帐户](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md#BKMK_TakeControlofAccounts)

-   [如何发现你的用户注册了个人 RMS？](#BKMK_Detect)

## <a name="BKMK_SignUp"></a>用户如何注册个人 RMS
若要注册这种免费帐户，你可以通过访问 [Microsoft Rights Management 页](https://portal.aadrm.com/)发出请求，并提供你的工作或学校电子邮件地址。 将你导向此注册页面的最常见方式是接收带有受保护附件的电子邮件，这包含有关如何注册的说明。 你将收到 Microsoft 的回应电子邮件，然后完成注册过程，方法是输入详细信息来创建帐户。 当你接收到 Microsoft 的电子邮件确认时，此最终电子邮件会将你带到可以下载适用于不同设备的共享应用程序页面以及指向用户指南的链接。

#### 注册个人 RMS

1.  使用 Windows 或 Mac 计算机，访问 [Microsoft Rights Management 页](https://portal.aadrm.com)。

2.  键入你用作组织电子邮件的电子邮件地址，例如 **janetm@contoso.com** 或 **p.dover@fabrikam.com**。

    > [!IMPORTANT]
    > 不支持个人电子邮件地址，因此请不要输入 Microsoft 帐户（以前称为 Microsoft Live ID 帐户）或可能在家使用的由 Internet 服务提供商提供的其他个人帐户。

3.  单击**“开始使用”**。

    Microsoft 使用电子邮件地址检查你的组织是否已经具有[包括 Azure RMS 在内的付费订阅](https://technet.microsoft.com/library/dn655136.aspx)。 如果是这种情况，你无需使用个人 RMS，因此可以立即登录并且个人 RMS 的自助注册将取消。 如果没有找到 Azure RMS 的付费订阅，你将继续到下一步。

4.  等待确认电子邮件发送至你提供的地址。 该电子邮件的发件人为 Microsoft (DoNotReply@microsoft.com)，主题为“Microsoft RMS”。

5.  当你收到电子邮件时，请单击说明中的链接完成注册过程。

6.  链接会带你访问新的 **Microsoft 权限管理**页，你可以在该页提供有关帐户的详细信息。 键入你的名字、姓氏、输入并确认所选密码、从下拉列表中选择国家/地区（如果没有列出你的国家/地区，则选择最近的国家/地区），然后单击“创建”。

7.  等待 Microsoft 发送另一封电子邮件，该邮件现在会确认你的帐户可以随时使用。

8.  收到电子邮件后，请单击登录链接并阅读说明以下载和安装共享应用程序，或者单击“帮助”链接以阅读共享应用程序用户指南。

现在你的帐户已经创建，你可以随时开始保护文件并读取其他人保护的文件。 当提示登录以便保护文件或读取受保护文件时，请输入你用于创建个人 RMS 帐户的电子邮件地址和密码。

### <a name="BKMK_TechnicalOverview"></a>技术概述
个人 RMS 使用自助注册过程，该过程也可由其他使用 Microsoft 基于云的技术对用户进行身份验证的服务使用。

以下是用户注册个人 RMS 但其组织没有 Office 365 订阅或 Azure 订阅，因此 Azure 中没有目录可对用户进行身份验证时后台发生的情况：

1.  当组织的第一位用户请求个人 RMS 订阅时，系统会检查其电子邮件地址中提供的域名，查看该域名是否已与某个 Azure 租户相关联。 如果不存在现有租户，将自动为组织创建新租户和 Azure 目录，这包含此首位用户的帐户。 与 Azure 的付费订阅不同，此第一个帐户不是全局管理员，而是标准用户。 新帐户使用用户提供的电子邮件地址和密码。

    > [!NOTE]
    > 某些域名不能用于创建目录，因此不能用于个人 RMS。 可以从此 JavaScript 对象表示法文件中查看阻止的域名的列表：[http://portal.aadrm.com/content/blocked_domains.json](http://portal.aadrm.com/content/blocked_domains.json)

    如果找到了现有租户，将对其进行检查以查看它是否具有 Azure RMS 订阅。 当没有找到订阅时，可以添加免费的个人 RMS 订阅。

2.  将授予组织个人 RMS 订阅。 现在，此用户可使用 Azure 进行身份验证，然后可以使用 Azure Rights Management 来保护文件并读取其他人保护的文件。 若要保护文件和读取受保护文件，用户必须具有启用 RMS 的应用程序，如[免费的 Rights Management 共享应用程序](https://technet.microsoft.com/library/dn919648.aspx)。

3.  当同一个组织的第二个用户请求个人 RMS 订阅时，将使用该组织的个人 RMS 订阅将一个新用户帐户添加到前面创建的 Azure 目录。 这第二个用户能够执行第一个用户能够执行的所有操作（保护文件和读取受保护文件），但除此之外，这两位用户现在还能够更加轻松地安全协作，因为他们可以快速将默认模板应用于文件，以仅允许其组织的 Azure 目录中的帐户访问这些文件。

4.  来自同一个组织的后续用户遵循相同的模式，向该组织的 Azure 目录添加用户帐户（当新用户注册时）。 添加到目录的帐户越多，能够与同事和合作伙伴进行安全协作的用户就越多，此外还能更加轻松地防止未授权人员读取他们没有访问权限的文件。

在这整个过程中，不会向组织收取任何费用，也不需要 IT 部门做任何工作。 但是，IT 部门可以选择采用以下某种管理方式：

-   **管理帐户和注册过程**：IT 管理员可以获得 Azure 中自动创建的目录和帐户的所有权。 然后，他们就可以通过实现密码同步和单一登录等目录集成解决方案来管理帐户。 或者，他们可以阻止用户创建帐户或注册个人 RMS。

    有关详细信息，请参阅以下部分[管理员如何才能控制为个人 RMS 创建的帐户](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md#BKMK_TakeControlofAccounts)。

-   **管理 Rights Management**：IT 管理员可以将组织的个人 RMS 订阅转换为包括 Azure 权限管理的付费订阅。 当他们执行此操作时，现有 Azure 目录和帐户将会保留，以便使用个人 RMS 的现有用户能够进行无缝转换。 用户以前保护的所有文件仍将使用相同策略进行保护，他们向其授予文件使用权限的人员仍将能够通过相同方式使用文件。

    当你执行此操作过程时，你的组织能够将权限管理集成到其工作流、服务和数据存储并从中受益。 此外，你现在还能够管理权限管理，因为你控制了组织的 Azure 权限管理租户密钥。 你现在可以执行以下操作：

    -   配置 Exchange 和 SharePoint 以支持 Azure 权限管理，即便它们在本地运行也能做到。 本机支持 Exchange 和 SharePoint 以实现联机服务，通过本地服务器的连接器为它们提供支持。 有关详细信息，请参阅以下内容：

        -   [为 Azure 权限管理配置应用程序](../Topic/Configuring_Applications_for_Azure_Rights_Management.md)主题的 [Office 365：客户端和联机服务的配置](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_O365)中的“Exchange Online”和“SharePoint Online”部分

        -   [部署 Azure 权限管理连接器](../Topic/Deploying_the_Azure_Rights_Management_Connector.md)

    -   对公司拥有的数据执行电子发现，如果需要，还可解密使用权限管理保护的文件。 有关详细信息，请参阅[为 Azure Rights Management 和发现服务或数据恢复配置超级用户](../Topic/Configuring_Super_Users_for_Azure_Rights_Management_and_Discovery_Services_or_Data_Recovery.md)。

    -   记录在组织中使用的所有权限管理活动。 这是一项非常强大的功能，因为你不仅能够监视哪些文件受到保护，哪些用户成功访问了那些受保护文件，还能够识别试图访问受保护文件的未授权用户的潜在可疑行为。 有关详细信息，请参阅[记录和分析 Azure 权限管理使用情况](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md)。

    -   如果这些 [Azure RMS 订阅](https://technet.microsoft.com/dn858608)支持这些功能，请提供用户跟踪和撤销其受保护的文档的功能。 有关详细信息，请参阅 [RMS 共享应用程序用户指南](https://technet.microsoft.com/library/dn339006.aspx)中的[跟踪和撤消文件](https://technet.microsoft.com/library/dn986611.aspx)。

    -   实现“自带密钥”解决方案 (BYOK)，以便能够根据你的 IT 策略，在本地生成 Azure 权限管理的租户密钥，并使用硬件安全模块 (HSM) 将该密钥安全传输到 Microsoft。 有关详细信息，请参阅[计划和实现你的 Azure 权限管理租户密钥](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md)。

## <a name="BKMK_TakeControlofAccounts"></a>管理员如何才能控制为个人 RMS 创建的帐户
如果你不希望将组织的个人 RMS 订阅转换为付费订阅，你仍然可以通过下列方式，控制为组织创建的 Azure 目录中的用户帐户：

-   实现 Azure Active Directory 和 Active Directory 域服务基础结构的目录集成解决方案。 你可以同步帐户和密码，使得用户无需创建新帐户即可使用权限管理，你的本地密码策略将应用于新的 Azure 用户帐户。 你还可以同步密码，使得用户无需为了使用权限管理而记忆不同密码。

-   你可以阻止用户注册使用 Azure Rights Management 和个人 RMS 订阅。 大多数情况下，这种做法没有什么好处，因为用户在不受保护的情况下共享文件可能会让公司承担风险，用户还可能会使用其他文件保护机制，导致 IT 部门不能访问数据。 但是，如果你希望阻止用户注册使用个人 RMS，请在取得组织的 Azure 目录的所有权后执行以下操作之一：

    -   阻止所有用户注册包括个人 RMS 的自助订阅。  目前，你无法通过服务设置此内容；该设置适用于所有使用自助过程的 Azure 订阅。 为此，请使用 Azure Active Directory 的 Windows PowerShell 模块中的 [Set-MsolCompanySettings](http://technet.microsoft.com/library/dn194127.aspx) cmdlet，将 **AllowAdHocSubscriptions** 参数设置为 false。 例如：**Set-MsolCompanySettings -AllowAdHocSubscriptions $false**

    -   阻止用户在 Azure 中创建新帐户，这意味着仅已经具有 Azure 帐户的用户可以注册包括个人 RMS 的自助订阅。  为此，请使用 Azure Active Directory 的 Windows PowerShell 模块中的 [Set-MsolCompanySettings](http://technet.microsoft.com/library/dn194127.aspx) cmdlet，将 **AllowEmailVerifiedUsers** 参数设置为 false。 例如：**Set-MsolCompanySettings -AllowEmailVerifiedUsers $false -AllowAdHocSubscriptions $true**

    -   将 Active Directory 域服务基础结构与 Azure Active Directory 同步。 此操作可以在用户注册自助订阅（如个人 RMS）阻止创建新帐户，并且你还可以删除或禁用以前在 Azure 目录中创建的帐户。

若要控制 Azure 目录中的用户帐户，或者阻止用户注册个人 RMS，你必须具有 Azure 订阅并拥有该目录。 如果没有 Azure 订阅，你可以免费获取一个订阅。 如果在自助过程期间自动为你创建了目录，请获取用于创建该目录的域的所有权。 如果你在 Azure 中已经拥有目录，但用户指定了在组织中使用的新的域，请将该域合并到现有目录中。 有关详细信息，请参阅[什么是 Azure 自助注册？](https://azure.microsoft.com/documentation/articles/active-directory-self-service-signup/)中的说明。

## <a name="BKMK_Detect"></a>如何发现你的用户注册了个人 RMS？
作为管理员，你如何知道用户是否注册了个人 RMS？ 你可以使用以下任意一种方法，或者结合使用多种方法：

-   询问用户如何保护高度机密文件，特别是在与组织外部人员协作时。

-   如果你拥有组织的 Azure 订阅，请使用 [Get-MsolAccountSku](https://msdn.microsoft.com/library/azure/dn194118.aspx) cmdlet 查看 **RIGHTSMANAGEMENT_ADHOC** 是否返回为订阅之一。 如果是，这是授予该组织的个人订阅 RMS，提供有可供用户使用自助服务注册过程的活动单元池。

-   使用 System Center Configuration Manager 等系统管理解决方案来清点已安装软件和在用软件。 Rights Management 共享应用程序是通过使用 **ipviewer.exe** 程序运行的，你可以免费[下载和安装该应用程序](http://go.microsoft.com/fwlink/?LinkId=303970)，以了解有关此应用程序的其他特征，然后将其用于软件清单。

-   请注意权限管理共享应用程序创建的文件扩展名。 .pfile 和 .ppdf 文件扩展名是最明显的示例，但是也有一些其他文件在原本就受 Rights Management 保护时会更改其文件扩展名。 有关详细信息，请参阅[权限管理共享应用程序管理员指南](http://technet.microsoft.com/library/dn339003.aspx)中的[支持的文件类型和文件扩展名](http://technet.microsoft.com/library/dn339003.aspx)部分。

## 请参阅
[Azure 权限管理入门](../Topic/Getting_Started_with_Azure_Rights_Management.md)

