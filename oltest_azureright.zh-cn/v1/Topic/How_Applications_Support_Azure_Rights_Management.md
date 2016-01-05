---
description: na
keywords: na
pagetitle: How Applications Support Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2cdc7bde-4044-4021-b887-11476f99afd9
---
# 应用程序如何支持 Azure 权限管理
使用以下信息可以帮助你了解最终用户应用程序（例如 Office 应用程序，包括 Word、Excel、PowerPoint 和 Outlook）和服务（例如 Exchange 和 SharePoint）如何才能使用 Microsoft [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 来帮助保护组织的数据：

-   [Windows 和移动平台的 RMS 共享应用程序](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_SharingAppIntro)

-   [Office 应用程序：Word、Excel、PowerPoint、Outlook](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_OfficeAppsIntro)

    -   [Exchange Online 和 Exchange Server](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_ExchangeIntro)

    -   [SharePoint Online 和 SharePoint Server](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_SharePointIntro)

-   [运行 Windows Server 和使用文件分类基础结构 (FCI) 的文件服务器](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_FCIIntro)

-   [支持 RMS API 的其他应用程序](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_APIAppsIntro)

> [!NOTE]
> 若要确认 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] (Azure RMS) 支持的应用程序和版本，请参阅 [Azure 权限管理要求](../Topic/Requirements_for_Azure_Rights_Management.md)。

某些情况下，将根据你配置的策略来自动应用信息保护。 例如，SharePoint 库、分类文件和 Exchange 传输规则就属于此种情况。 在其他情况下，用户必须自动通过应用程序（不管是通过选择模板还是通过选择特定选项）来应用信息保护。 例如，用户可通过电子邮件来共享文件，或者通过将访问权限和使用权限限制给选定用户或组织外部用户来保护现有文件。

利用模板，用户（以及配置策略的管理员）能够更加轻松地应用正确级别的保护，并将访问权限限制给组织内部人员。 虽然 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 附带了两个默认模板，但你可能还希望创建自定义模板，以减少使用模板指定各个选项所需的时间。 有关详细信息，请参阅[为 Azure 权限管理配置自定义模板](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md)。

对于用户必须自行应用信息保护的情况，请务必为他们提供有关信息保护应用方式和时机的说明和指导。 这些说明应该专门针对他们使用的特定应用程序和版本及其使用方式，有关信息保护应用时机和方式的指导应该适用于你的企业。 有关详细信息，请参阅[帮助用户使用 Azure 权限管理保护文件](../Topic/Helping_Users_to_Protect_Files_by_Using_Azure_Rights_Management.md)。

有关如何为 Azure RMS 配置 这些应用程序的信息，请参阅[为 Azure 权限管理配置应用程序](../Topic/Configuring_Applications_for_Azure_Rights_Management.md)。

> [!TIP]
> 有关使用 Azure RMS 的应用程序的示例和屏幕截图，请参阅[什么是 Azure 权限管理？](../Topic/What_is_Azure_Rights_Management_.md)主题中的[运行中的 Azure RMS：管理员和用户看到的内容](../Topic/What_is_Azure_Rights_Management_.md#BKMK_RMSpictures)部分。

## <a name="BKMK_SharingAppIntro"></a>Windows 和移动平台的 RMS 共享应用程序
RMS 共享应用程序是支持 Office 2010 所必需的免费可下载应用程序，但我们也建议将其用于 Windows 计算机、Mac 计算机和移动设备。 它的一大优点是能够为无法以本机方式支持 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 的应用程序和文件提供通用保护，这意味着所有文件都能得到保护。 有关不同保护级别的详细信息，请参阅 [Rights Management 共享应用程序管理员指南](http://technet.microsoft.com/library/dn339003.aspx)中的[保护级别 – 本机和常规](http://technet.microsoft.com/library/dn339003.aspx)部分。

当用户通过使用 RMS 共享应用程序保护其文件时，他们还可以跟踪他们保护的文档，如有必要，撤消对这些文档的访问权限。 他们通过使用[文档跟踪站点](http://go.microsoft.com/fwlink/?LinkId=529562)来执行此操作。

对于 Windows 计算机，RMS 共享应用程序可与用户已在使用的应用程序轻松集成，并且增强这些应用程序的功能：

-   安装 Word、Excel、PowerPoint 和 Outlook 的 Office 加载项。 这样可在功能区上为用户提供“共享保护内容”按钮，该按钮可以调用一个易于使用的对话框，其中包含用于保护要通过电子邮件发送的文件的最常用设置。 此按钮还提供了用于访问文档跟踪站点的快捷方式。

-   文件资源管理器的全新右键单击选项。 它可在功能区上为用户提供“就地保护”选项，该选项可以调用一个易于使用的对话框，其中包含用于保护存储在磁盘上的文件的最常用设置。

-   一个查看器，用于打开受 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 保护的文件。 当没有其他已安装的应用程序可以打开受保护文件时，将自动调用此查看器。

-   Office 2010 的后端配置，让此套件的 Word、Excel、PowerPoint 和 Outlook 能够与 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 无缝集成。

虽然可通过使用 [Microsoft Rights Management 页](http://go.microsoft.com/fwlink/?LinkId=303970)为单台计算机下载和安装适用于 Windows 的 RMS 共享应用程序，但它也支持企业部署的静默安装和自定义配置。 有关详细信息，请参阅下列资源：

-   [权限管理共享应用程序管理员指南](http://technet.microsoft.com/library/dn339003.aspx)

-   [权限管理共享应用程序用户指南](http://technet.microsoft.com/library/dn339006.aspx)

适用于移动设备的 RMS 共享应用程序支持最常用的移动设备，例如 iPad 和 iPhone、Android、Windows Phone 和 Windows RT。 用户可以从相关应用商店下载此应用，[Microsoft 权限管理页](http://go.microsoft.com/fwlink/?LinkId=303970)提供这些应用商店的链接。

## <a name="BKMK_OfficeAppsIntro"></a>Office 应用程序：Word、Excel、PowerPoint、Outlook
这些应用程序通过使用信息权限管理 (IRM) 以本机方式支持权限管理，让用户能够将保护应用于已保存文档，或者应用于要发送的电子邮件。 用户可以应用模板或选择针对访问、权限和使用限制的高度自定义设置。 例如，用户可以通过配置文件仅允许组织内人员访问该文件，还可以控制是否允许编辑该文件、是否将其限制为只读，以及是否禁止打印该文件。 对于时间敏感型文件，可以配置一个过期时间（直接由用户配置，或者应用模板进行配置），在过期之后无法再访问该文件。 对于 Outlook，用户还可以选择“不要转发”选项来帮助防止数据泄漏。

### <a name="BKMK_ExchangeIntro"></a>Exchange Online 和 Exchange Server
使用 Exchange Online 或 Exchange Server 时，你可以使用信息权限管理 (IRM) 集成，它提供更多信息保护解决方案：

-   **Exchange ActiveSync IRM**，让移动设备能够保护和使用受保护的电子邮件。

-   **Outlook Web 应用**的 RMS 支持，其实施方法与 Outlook 客户端类似，让用户能够通过模板或指定各个选项来保护电子邮件，用户能够阅读和使用发送给他们的受保护电子邮件。

-   适用于 Outlook 客户端的**保护规则**，管理员能够配置这些规则，以便自动将 RMS 模板应用于发送给指定收件人的电子邮件。 例如，在将内部电子邮件发送至法律部门时，只允许法律部门成员阅读这些邮件，而且不能转发。 在发送电子邮件之前，用户可以看到应用于电子邮件的保护，而默认情况下，如果他们确定该电子邮件不是必须发送的，则可将其删除。 电子邮件在发送之前进行了加密。 有关详细信息，请参阅 Exchange 库中的 [Outlook 保护规则](http://technet.microsoft.com/library/dd638178%28v=exchg.150%29.aspx)和[创建 Outlook 保护规则](http://technet.microsoft.com/library/dd638196%28v=exchg.150%29.aspx)。

-   **传输规则**，管理员能够配置这些规则，根据各种属性（例如发件人、收件人、邮件主题和内容），自动将 RMS 模板应用于电子邮件。 这些规则在概念上类似于保护规则，但不允许用户取消保护；这些规则可以应用于 Outlook Web Access 和通过移动设备发送的电子邮件；在从客户端发送电子邮件之前，这些规则不对其进行加密。 有关详细信息，请参阅 Exchange 库中的[创建传输保护规则](http://technet.microsoft.com/library/dd302432.aspx)。

-   **数据丢失预防 (DLP) 策略**，包含一系列筛选邮件的条件，有助于防止机密或敏感内容（例如个人信息或信用卡信息）的数据丢失。 检测到敏感数据时，可以使用策略提示，根据电子邮件中的内容，警告用户他们可能需要应用信息保护。 有关详细信息，请参阅 Exchange 库中的[数据丢失预防](http://technet.microsoft.com/library/jj150527%28v=exchg.150%29.aspx)。

-   **Office 365 邮件加密**，使用传输规则将加密电子邮件发送到公司外部人员，该电子邮件在浏览器中阅读，浏览器界面与 Outlook Web App 相似。 你可以在公司的加密电子邮件中自定义免责声明文本和标题文本，甚至添加你公司的徽标。 有关详细信息，请参阅 Office 网站上的 [Office 365 邮件加密](http://office.microsoft.com/o365-message-encryption-FX104179182.aspx)。

如果使用 Exchange Server，则可以通过部署 RMS 连接器，将其用作内部部署服务器和 RMS 云服务之间的中继，从而利用 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 的信息保护功能。 有关详细信息，请参阅[部署 Azure 权限管理连接器](../Topic/Deploying_the_Azure_Rights_Management_Connector.md)。

### <a name="BKMK_SharePointIntro"></a>SharePoint Online 和 SharePoint Server
使用 SharePoint Online 或 SharePoint Server 时，你可以使用信息权限管理 (IRM) 集成，让管理员保护列表或库，这样当用户签出文档时，文件将会受到保护，只有授权人员能够根据你指定的信息保护策略来查看和使用文件。 例如，文件可能是只读的，可能会禁用文本复制，可能会阻止保存本地副本，可能会阻止打印文件。

对于列表和库，始终由管理员（永远不会由最终用户）应用信息保护。 对于该容器中的所有文档，信息保护是在列表或库级别上应用的，而不是在单独文件级别上应用。  如果你使用 SharePoint Online，用户还可以对其 OneDrive for Business 库应用 IRM。

必须首先为 SharePoint 启用 IRM 服务。 然后，为库指定信息权限管理。 对于 SharePoint Online 和 OneDrive for Business，用户还可以为其 OneDrive for Business 库指定信息权限管理。 SharePoint 不使用权限策略模板，虽然你可以选择的 SharePoint 配置设置非常匹配你可以在模板中指定的设置。

如果使用 SharePoint Server，则可以通过部署 RMS 连接器，将其用作内部部署服务器和 RMS 云服务之间的中继，从而利用 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]的信息保护功能。 有关详细信息，请参阅[部署 Azure 权限管理连接器](../Topic/Deploying_the_Azure_Rights_Management_Connector.md)。

> [!NOTE]
> 目前，将 IRM 用于 SharePoint 时有一些限制：
> 
> -   不能使用在 Azure 经典门户中管理的默认模板或自定义模板。
> -   不支持带 .PPDF 文件扩展名的受保护 PDF 文件。 当你使用本机支持 RMS 的 PDF 阅读器时时，支持带 PDF 文件扩展名的文件以及受 RMS 本机保护的文件。
> -   由于移动设备上的 Office 尚不支持 RMS，因此这些设备必须使用浏览器来查看已使用 RMS 保护的文件，并且这些文件是只读的。

Azure RMS 会在从 SharePoint 下载文档时为文档应用使用限制和数据加密，而不是在 SharePoint 中首次创建文档或将其上载到库中时进行此类操作。 有关如何在下载文档前对其进行保护的信息，请参阅 SharePoint 文档中的 [OneDrive for Business 和 SharePoint Online 中的数据加密](https://technet.microsoft.com/library/dn905447.aspx)。

有关在 SharePoint 中使用 Azure RMS 的详细信息，请参阅 Office 博客中的以下文章：[SharePoint 和 SharePoint 中的信息权限管理的新增功能](http://blogs.office.com/2012/11/09/whats-new-with-information-rights-management-in-sharepoint-and-sharepoint-online/)

## <a name="BKMK_FCIIntro"></a>运行 Windows Server 和使用文件分类基础结构 (FCI) 的文件服务器
当你将 Windows Server 配置为使用文件分类基础结构时，此文件服务器资源管理器功能可以扫描本地文件，并确定它们是否包含敏感数据。 对于满足此条件的文件，可以使用管理员定义的分类属性，对其进行标记。 然后，文件分类基础结构可根据分类执行自动操作。 其中一种操作是使用 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 来应用信息保护，并部署 Rights Management 连接器（也称为 RMS 连接器）。 然后，由 Azure RMS 自动保护 Office 文件。

若要保护所有文件类型，将不使用 RMS 连接器，而是改为使用 [RMS 保护工具](https://www.microsoft.com/en-us/download/details.aspx?id=47256)中提供的 cmdlet 运行 Windows PowerShell 脚本。

分类策略是完全可以配置的，并且具有高度的可扩展性，因此你可以防止未授权和已授权用户可能发生的数据泄漏。 它甚至有助于降低网络管理员的数据泄漏风险，因为你可以配置不要求这些管理员具有文件访问权限的策略。

有关为 Office 文件部署和配置 RMS 连接器的说明，请参阅 [部署 Azure 权限管理连接器](../Topic/Deploying_the_Azure_Rights_Management_Connector.md)。

有关对所有文件类型使用 Windows PowerShell 脚本的说明，请参阅 [使用 Windows Server 文件分类基础结构 &#40;FCI&#41; 的 RMS 保护](../Topic/RMS_Protection_with_Windows_Server_File_Classification_Infrastructure__FCI_.md)。

## <a name="BKMK_APIAppsIntro"></a>支持 RMS API 的其他应用程序
使用 RMS SDK，内部开发人员可以编写业务线应用程序，以本机方式支持 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]。 信息保护与这些应用程序的集成方式取决于编写应用程序的方式。 例如，这种集成可以是自动应用的，只需很少的用户交互，或者为了提供更多自定义体验，可能会提示用户配置相关设置，以便对文件应用信息保护。 有关 SDK 的详细信息，请参阅 [Microsoft Rights Management SDK](http://msdn.microsoft.com/library/hh552972%28v=vs.85%29.aspx)。

同样，很多软件供应商提供各种应用程序作为信息保护解决方案，也称为企业权限管理 (ERM) 产品。 常见的例子是支持特定平台的 [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] 的 PDF 阅读器。 可以使用 [Azure 权限管理要求](../Topic/Requirements_for_Azure_Rights_Management.md) 主题的 [客户端设备功能](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_ClientCapabilities) 部分中的表来确定支持 RMS 的应用程序（启用 RMS 的应用程序），然后使用 web 搜索购买或下载应用程序。

> [!TIP]
> 对于新发布的应用程序，请查看在 [Azure 权限管理的信息和支持](../Topic/Information_and_Support_for_Azure_Rights_Management.md)中列出的 RMS 社区频道。

## 请参阅
[Azure 权限管理入门](../Topic/Getting_Started_with_Azure_Rights_Management.md)

