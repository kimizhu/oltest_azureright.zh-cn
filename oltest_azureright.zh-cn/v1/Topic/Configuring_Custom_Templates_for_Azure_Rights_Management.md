---
description: na
keywords: na
pagetitle: Configuring Custom Templates for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1775d8d0-9a59-42c8-914f-ce285b71ac1c
---
# 为 Azure 权限管理配置自定义模板
在你激活 Azure Rights Management (Azure RMS) 之后，用户就能够自动使用两个默认模板，这些模板让他们能够轻松地将策略应用于在组织中限制访问授权用户的敏感文件。 这两个模板具有以下权限策略限制：

-   受保护内容的只读查看

    -   显示名称：**&lt;组织名称&gt; - 机密，仅供查阅**

    -   特定权限：查看内容

-   受保护内容的读取或修改权限

    -   显示名称：**&lt;组织名称&gt; - 机密**

    -   特定权限：查看内容、保存文件、编辑内容、查看分配的权限、允许宏、转发、答复、全部答复

此外，[RMS 共享应用程序](http://technet.microsoft.com/library/dn339006.aspx)让用户能够定义他们自己的一组权限。 对于 Outlook 客户端和 Outlook Web Access，用户可为电子邮件选择“不要转发”选项。

对于很多组织，默认模板可能足以满足他们的需求。 但如果你希望创建自己的自定义权限策略模板，也可以这样做。 创建自定义模板有以下原因：

-   你希望模板仅向组织内的一部分用户授权，而不是向所有用户授权。

-   你希望只有用户的子集能够在应用程序中查看和选择模板（部门模板），而不是组织中的所有用户都可以查看和选择模板。

-   你希望为模板定义一种自定义权限，例如查看和编辑，而不是复制和打印。

-   你希望在模板中配置更多选项，包括过期日期，以及是否能够在没有 Internet 连接的情况下访问内容。

要让用户能够选择包含此类设置的自定义模板，你必须首先创建一个自定义模板，对其进行配置，然后发布该模板。

使用以下部分可帮助你配置和使用自定义模板：

-   [如何创建、配置和发布自定义模板](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md#BKMK_HowToConfigureCustomTemplates)

-   [如何复制模板](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md#BKMK_HowToCopyTemplates)

-   [如何删除（存档）模板](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md#BKMK_HowToArchiveTemplates)

-   [为用户刷新模板](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md#BKMK_RefreshingTemplates)

-   [Windows PowerShell 参考](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md#BKMK_PowerShellTemplates)

## <a name="BKMK_HowToConfigureCustomTemplates"></a>如何创建、配置和发布自定义模板
你可以在 Azure 经典门户中创建和管理自定义模板。 可以直接从 Azure 经典门户执行这些操作，也可以登录到 Office 365 管理中心，并选择 Rights Management 的“高级功能”，它会将你重定向至 Azure 经典门户。

请使用以下过程为权限管理创建、配置和发布自定义模板。

#### 创建自定义模板

1.  根据你是登录到 Office 365 管理中心还是登录到 Azure 经典门户，执行以下操作之一：

    -   从 [Office 365 管理中心](https://portal.office.com/)：

        1.  在左窗格中，单击“服务设置”。

        2.  在“服务设置”页中，单击“Rights Management”。

        3.  在“保护你的信息”部分中，单击“管理”。

        4.  在“Rights Management”部分中，单击“高级功能”。

            > [!NOTE]
            > 如果你尚未激活 Rights Management，请首先单击“激活”并确认你的操作。 有关详细信息，请参阅[激活 Azure 权限管理](../Topic/Activating_Azure_Rights_Management.md)。
            > 
            > 如果你之前未单击“高级功能”，请在激活 Rights Management 后，按照屏幕上的说明获取免费的 Azure 订阅，需要该订阅才能访问 Azure 经典门户。

            单击“高级功能”即可加载 Azure 经典门户，你可以在该门户中针对组织的 Azure Active Directory 管理 **RIGHTS MANAGEMENT**。

    -   从 [Azure 经典门户](http://go.microsoft.com/fwlink/p/?LinkID=275081)：

        1.  在左窗格中，单击“ACTIVE DIRECTORY”。

        2.  在**“Active Directory”**页中，单击**“权限管理”**。

        3.  为权限管理选择要管理的目录。

        4.  如果你尚未激活 Rights Management，请单击“激活”并确认你的操作。

            > [!NOTE]
            > 有关详细信息，请参阅[激活 Azure 权限管理](../Topic/Activating_Azure_Rights_Management.md)。

2.  创建新模板：

    -   在 Azure 经典门户的“开始使用 Rights Management”快速启动页中，单击“创建新的权限策略模板”。

        如果你在按照 Office 365 的说明进行操作后没有立刻看到此页，请按上面的 Azure 经典门户导航说明进行操作。

3.  在“添加新的权限策略模板”页上，选择输入用户将看到的模板名称和说明所用的语言（你可以随后添加更多语言）。 然后键入唯一名称和说明，并单击“完成”按钮。

在“开始使用 Rights Management”快速启动页中，现在可单击“管理你的权限策略模板”。 你将看到新创建的模板已添加到模板列表中，其状态为“已存档”。 在这个阶段，模板已创建但尚未配置，对用户是不可见的。

#### 配置和发布自定义模板

1.  在 Azure 经典门户的“模板”页中选择你新创建的模板。

2.  在“你的模板已添加”快速启动页上，依次单击步骤 1 的“开始使用”、“配置用户和组权限”、“立即开始使用”或“添加”，然后选择将有权使用受新模板保护内容的用户和组。

    > [!NOTE]
    > 你选择的用户或组必须有电子邮件地址。 在生产环境中，他们几乎都有电子邮件地址，但在简单的测试环境中，你可能需要为用户帐户或组添加电子邮件地址。

    最佳做法是使用组而不是用户，这样可以简化模板的管理。 如果你具有本地 Active Directory 并同步到 Azure AD，可以使用已启用邮件的安全组或通讯组。 但是，如果你要向组织中的所有用户授予权限，则复制一个默认模板将比指定多个组更有效率。 有关详细信息，请参阅本主题中的[如何复制模板](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md#BKMK_HowToCopyTemplates)部分。

    > [!TIP]
    > 你可以稍后通过[适用于 Azure Rights Management 的 Windows PowerShell 模块](https://technet.microsoft.com/library/jj585012.aspx)以及下述方法之一将不属于你组织的用户添加到模板中：
    > 
    > -   **使用权限定义对象更新模板**：  在权限定义对象中指定外部电子邮件地址及其权限，然后使用这些地址和权限更新模板。 指定权限定义对象时，可使用 [New-AadrmRightsDefinition](https://msdn.microsoft.com/library/azure/dn727080.aspx) cmdlet 来创建一个变量，然后将该变量提供给 -RightsDefinition 参数，并可使用 [Set-AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727076.aspx) cmdlet 来修改现有模板。 但是，如果你是将这些用户添加到现有模板中，则还需要在模板中为现有组定义权限定义对象，不仅仅只需为新的外部用户进行此类操作。
    > -   **导出、编辑和导入已更新的模板**：使用 [Export-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727078.aspx) cmdlet 将模板导出到一个文件中，然后即可对该文件进行编辑，将这些用户的外部电子邮件地址及其权限添加到现有组和权限。 然后，使用 [Import-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727077.aspx) cmdlet 将所做的更改导回到 Azure RMS 中。

3.  单击“下一步”按钮，然后为你选择的用户和组分配所列的某一种权限。

    有关每个权限（以及自定义权限）的详细信息，请使用显示的说明。 有关详细信息，请查看 [为 Azure 权限管理配置使用权限](../Topic/Configuring_Usage_Rights_for_Azure_Rights_Management.md)。 但是，支持 RMS 的应用程序可能在实现这些权限的方式方面有所不同。 请查阅其文档，并在为用户部署模板之前，对用户使用的应用程序执行自己的测试以检查其行为。 要使此模板只对此测试的管理员可见，请将此模板设为部门模板（步骤 6）。

4.  如果你选择了“自定义”，请单击“下一步”按钮，然后选择这些自定义权限。

    虽然你可以使用各种可用权限的任意组合，但在某些应用程序中，有些权限可能与其他各种权限存在依赖关系。 在这种情况下，会自动为你选择依赖权限。

    > [!TIP]
    > 请考虑添加“复制和提取内容”权限，并向选定管理员或其他拥有信息恢复职责的角色授予此权限。 授予此权限后，他们便能够根据需要删除对将使用此模板提供保护的文件和电子邮件的保护。 通过这种可以取消模板级保护的功能，将可以提供比使用超级用户功能更为精细的控制。

5.  单击“完成”按钮。

6.  如果你希望只有用户的子集在应用程序中查看模板列表时可以看到此模板：请单击“作用域”，将此模板配置为部门模板，然后单击“立即开始使用”。 否则，请转到步骤 9。

    有关部门模板的详细信息：默认情况下，Azure 目录中的所有用户都可看到所有已发布的模板，然后他们在要保护内容时可以从应用程序中选择这些模板。 如果你希望仅特定用户可以看到某些已发布的模板，则必须将这些模板的作用域设为这些用户。 然后，将只有这些用户能够选择这些模板。 你未指定的其他用户将看不到这些模板，因此，无法选择这些模板。 此技术使用户可以更轻松地选择合适的模板，尤其是当你创建的模板是专为供特定组或部门使用而设计的时候。 然后，用户将只看到专为他们设计的模板。

    例如，你为人力资源部门创建了一个模板，该模板对财务部门的成员应用了只读权限。 因此在使用权限管理共享应用程序时，只有人力资源部门的成员能够应用该模板，你将该模板的作用域设为名为 HumanResources 的已启用电子邮件的组。 然后，只有此组的成员能够查看和应用该模板。

7.  在“模板可见性”页上，选择能够在启用 RMS 的应用程序中查看和选择该模板的用户和组。 与前面一样，最佳做法是使用组而不是使用用户，并且你选择的组或用户必须具有电子邮件地址。

8.  单击“下一步”按钮，确定是否需要为部门模板配置应用程序兼容性。 如果需要，请单击“应用程序兼容性”，选中该复选框，然后单击“完成”。

    为什么你可能需要配置应用程序兼容性？ 并非所有应用程序都可以支持部门模板。 为此，应用程序必须先使用 RMS 服务进行身份验证，然后再下载这些模板。 如果未执行身份验证过程，默认情况下，将无法下载部门模板。 可以通过指定应该下载所有部门模板来覆盖此行为，方法是配置应用程序兼容性，并选中“在应用程序不支持用户标识时，向所有用户显示此模板”复选框。

    例如，如果你在人力资源示例中未为部门模板配置应用程序兼容性，则在使用 RMS 共享应用程序时，将只有人力资源部门中的用户可以看到部门模板，但是在他们从 Exchange Server 2013 使用 Outlook Web Access (OWA) 时，将没有用户可以看到部门模板，因为 Exchange OWA 和 Exchange ActiveSync 目前不支持部门模板。 如果通过配置应用程序兼容性覆盖此默认行为，在使用 RMS 共享应用程序时，将只有人力资源部门中的用户可以看到部门模板，但在使用 Outlook Web Access (OWA) 时，所有用户都可看到部门模板。 如果用户从 Exchange Online 使用 OWA 或 Exchange ActiveSync，则要么所有用户都将看到部门模板，要么没有用户将看到部门模板，具体取决于 Exchange Online 中的模板状态（存档还是已发布）。

    Office 2016 原生支持部门模板，装有最新 Office 更新 ([KB 3054853](https://support.microsoft.com/kb/3054853)) 的 Office 2013 也提供此支持。

    > [!NOTE]
    > 如果你的应用程序本身尚不支持部门模板，则可以使用自定义的 RMS 模板下载脚本或其他工具，将这些模板部署到本地 RMS 客户端文件夹。 然后，这些应用程序将正确地只向为模板作用域选择的用户和组显示这些部门模板：
    > 
    > -   Office 2010 的客户端文件夹是 **%localappdata%\Microsoft\DRM\Templates**。
    > -   你可以从已下载所有模板的客户端计算机复制模板文件，然后将这些文件粘贴到其他计算机。
    > 
    > 你可以[从 Microsoft Connect 站点下载自定义的 RMS 模板脚本](http://go.microsoft.com/fwlink/?LinkId=524506)。 如果你在单击此链接时看到错误，则很可能尚未在 Microsoft Connect 中注册。   若要注册，请执行以下操作：
    > 
    > 1.  转到 [Microsoft Connect 站点](http://www.connect.microsoft.com)，并使用 Microsoft 帐户登录。
    > 2.  单击“目录”，并选择“查看当前不接受反馈的 Connect 产品”类别。
    > 3.  搜索 **Rights Management Services**，对于“Microsoft RMS 企业功能”计划，单击“加入”。

9. 单击**“配置”**并添加用户使用的其他语言，以及使用该语言的模板名称和说明。 具有多语言用户时，应添加他们使用的每一种语言，并使用该语言提供模板名称和说明，这一点非常重要。 用户随后看到的模板名称和说明将使用与他们的客户端操作系统相同的语言，这样可以确保他们理解应用程序于文档或电子邮件的策略。 如果语言与用户的客户端操作系统不匹配，则他们看到的名称和说明将恢复为你最初创建模板时定义的语言。

    然后确认你是否要对以下设置进行任何更改：

    |Setting|更多信息|
    |-----------|--------|
    |**内容过期时间**|为此模板定义一个日期或天数，受模板保护的文件在到达此日期或经历这些天数后就会打不开。 你可以指定一个日期，也可以指定对文件应用程序保护后所经历的天数。<br /><br />如果你指定一个日期，它将在你当前时区的午夜生效。|
    |**脱机访问**|如果用户必须能够在没有 Internet 连接时打开受保护文件，则使用此设置可以平衡针对这种情况的任何安全要求。<br /><br />如果你指定内容在没有 Internet 连接的情况下不可用，或者指定内容仅在指定天数内可用，则在到达该阈值时，用户必须重新进行身份验证，他们的访问也将被记录。 发生这种情况时，如果他们的凭据不缓存，用户会收到登录后才能打开文件的提示。<br /><br />除了重新进行身份验证之外，还会重新评估策略和用户组成员身份。 这意味着，如果策略或组成员身份相比用户上一次访问文件时发生变化，则他们可能获得与上一次访问相同文件时不同的访问结果。|

10. 当你确信已经为用户正确配置了模板时，请单击“发布”，使得用户能够看到该模板，然后单击“保存”。

11. 单击经典门户中的“返回”按钮，返回到“模板”页，其中的模板的状态现已更新为“已发布”。

若要对模板进行任何更改，请选择模板，然后重新使用快速启动步骤。 或者选择以下选项之一：

-   添加更多用户和组，并为这些用户和组定义权限：单击“权限”，然后单击“添加”。

-   删除你先前选择的用户或组：单击“权限”，从列表中选择用户或组，然后单击“删除”。

-   若要更改哪些用户可以看到这些模板以便从应用程序中选择它们，请执行以下操作：单击“作用域”，然后单击“添加”或“删除”，或“应用程序兼容性”。

-   若要让模板不再对所有用户可见，请执行以下操作：依次单击“配置”、“存档”、“保存”。

-   进行其他配置更改：单击“配置”，进行更改，然后单击“保存”。

> [!WARNING]
> 当你对以前保存的模板进行更改时，客户端将不会看到对模板的这些更改，直至这些模板在它们的计算机上刷新。 有关详细信息，请参阅本主题中的[为用户刷新模板](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md#BKMK_RefreshingTemplates)部分。

## <a name="BKMK_HowToCopyTemplates"></a>如何复制模板
如果你需要创建一个新模板，它具有与现有模板非常相似的设置，请在“模板”页上选择原始模板，单击“复制”，指定唯一名称，然后进行所需的更改。

> [!IMPORTANT]
> 当你复制模板时，“已发布”或“已存档”状态也将被复制。 因此，如果你复制了已发布模板，则其即时状态也将为已发布，除非你更改该状态。

你可以复制自定义模板和默认模板。 如果你想要模板向组织中的所有用户授予权限，最佳做法是，复制默认模板之一而不是创建新的自定义模板。 此方法意味着，你不必创建或选择多个组即可指定所有用户。 但是，在此方案中，请务必为针对其他语言复制的模板指定新名称和说明。

## <a name="BKMK_HowToArchiveTemplates"></a>如何删除（存档）模板
无法删除默认模板，但可以将它们存档，这样用户就不会看到它们。

同样，如果你发布了一个自定义模板，但不再希望用户能够看到它，则可编辑该模板，并在“配置”页中选择“存档”和“保存”。 或者，你可从“模板”页中选择该模板，然后选择“存档”。

由于你无法编辑默认模板，因此若要将这些模板存档，必须使用“模板”页中的“存档”选项。 你无法将 Outlook 的“不要转发”选项存档。

#### 删除默认模板

-   在“模板”页中，选择默认模板，然后单击“存档”。

状态从“已发布”更改为“已存档”。 如果你改变了主意，请选择该模板并单击“发布”。

## <a name="BKMK_RefreshingTemplates"></a>为用户刷新模板
当你使用 Azure RMS 时，模板会自动下载到客户端计算机，因而用户能够从他们的应用程序选择这些模板。 但是，如果你对模板进行了更改，可能还需要执行附加步骤：

|应用程序或服务|如何在更改后刷新模板|
|-----------|--------------|
|Exchange Online|需要手动配置来刷新模板。<br /><br />有关配置步骤，请参阅展开部分：[仅适用于 Exchange Online：如何将 Exchange 配置为下载已更改的自定义模板](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md#BKMK_ExchangeOnlineTemplatesUpdate)。|
|Office 365|自动刷新 – 无需额外的步骤。|
|Office 2016 和 Office 2013<br /><br />适用于 Windows 的 RMS 共享应用程序|自动刷新 – 按计划刷新：<br /><br />-   对于这些更高版本的 Office：默认刷新间隔是 7 天。<br />-   对于适用于 Windows 的 RMS 共享应用程序：从版本 1.0.1784.0 开始，默认刷新间隔是 1 天。 以前版本的默认刷新间隔为 7 天。<br /><br />若要强制执行比此计划更快的刷新，请展开以下部分：[适用于 Windows 的 Office 2016、Office 2013 和 RMS 共享应用程序：如何强制执行针对已更改自定义模板的刷新](#BKMK_Office2013ForceUpdate)。|
|Office 2010|当用户登录时刷新。<br /><br />若要强制执行刷新，应要求或强制用户注销和重新登录。 或者，请参阅以下部分：[仅适用于 Office 2010：如何强制执行针对已更改自定义模板的刷新](#BKMK_Office2010ForceUpdate)。|
对于使用 RMS 共享应用程序的移动设备，模板会自动下载（必要时还会刷新），而无需其他配置。

### <a name="BKMK_ExchangeOnlineTemplatesUpdate"></a>仅适用于 Exchange Online：如何将 Exchange 配置为下载已更改的自定义模板
如果你已经为 Exchange Online 配置了信息权限管理 (IRM)，则不会为用户下载自定义模板，除非你使用 Windows PowerShell 在 Exchange Online 中进行了下列更改：

> [!NOTE]
> 有关如何在 Exchange Online 中使用 Windows PowerShell 的详细信息，请参阅[在 Exchange Online 中使用 PowerShell](https://technet.microsoft.com/library/jj200677%28v=exchg.160%29.aspx)。

每次更改模板时，你必须执行此过程。

##### 为 Exchange Online 更新模板

1.  在 Exchange Online 中使用 Windows PowerShell 连接到服务：

    1.  提供你的 Office 365 用户名和密码：

        ```
        $Cred = Get-Credential
        ```

    2.  通过运行以下两个命令连接到 Exchange Online 服务：

        ```
        $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell/ -Credential $Cred -Authentication Basic –AllowRedirection
        ```

        ```
        Import-PSSession $Session
        ```

2.  使用 [Import-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/jj200724%28v=exchg.160%29.aspx) cmdlet，从 Azure RMS 重新导入你的受信任发布域 (TPD)：

    ```
    Import-RMSTrustedPublishingDomain -Name "<TPD name>" -RefreshTemplates -RMSOnline
    ```
    例如，如果 TPD 名为 **RMS Online - 1**（很多组织的典型名称），请输入：**Import-RMSTrustedPublishingDomain -Name "RMS Online - 1" -RefreshTemplates -RMSOnline**

    > [!NOTE]
    > 若要验证你的 TPD 名称，可以使用 [Get-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/jj200707%28v=exchg.160%29.aspx) cmdlet。

3.  若要确认模板已经成功导入，请等候几分钟，然后运行 [Get-RMSTemplate](http://technet.microsoft.com/library/dd297960%28v=exchg.160%29.aspx) cmdlet 并将 Type 设为 All。 例如：

    ```
    Get-RMSTemplate -TrustedPublishingDomain "RMS Online - 1" -Type All
    ```
    > [!TIP]
    > 保留输出的副本很有用，这样，如果你以后将模板存档，可以轻松地复制模板名称或 GUID。

4.  对于需要在 Outlook Web App 中使用的每个已导入的模板，你必须使用 [Set-RMSTemplate](http://technet.microsoft.com/library/hh529923%28v=exchg.160%29.aspx) cmdlet 并将 Type 设置为 Distributed：

    ```
    Set-RMSTemplate -Identity "<name  or GUID of the template>" -Type Distributed
    ```
    由于 Outlook Web Access 缓存 UI 24 小时，用户可能最长在一天之内都看不到新模板。

此外，如果你存档一个模板（自定义或默认），并将 Exchange Online 和 Office 365 配合使用，则如果用户使用 Outlook Web App 或运行 Exchange ActiveSync 协议的移动设备，他们仍然可以看到存档的模板。

因此用户再也看不到这些模板，这种情况下，请使用 Exchange Online 中的 Windows PowerShell 连接到服务，然后通过运行以下命令来使用 [Set-RMSTemplate](http://technet.microsoft.com/library/hh529923%28v=exchg.160%29.aspx) cmdlet：

```
Set-RMSTemplate -Identity "<name or GUID of the template>" -Type Archived
```

### <a name="BKMK_Office2013ForceUpdate"></a>适用于 Windows 的 Office 2016、Office 2013 和 RMS 共享应用程序：如何强制执行针对已更改自定义模板的刷新
通过编辑运行 Office 2016、Office 2013 或适用于 Windows 的 Rights Management (RMS) 共享应用程序的计算机上的注册表，你可以更改自动计划，以便更改的模板在计算机上的刷新频率比其默认值更频繁。 你还可以通过删除注册表值中的现有数据，强制执行即时刷新。

> [!WARNING]
> 如果你没有正确使用注册表编辑器，则可能导致严重问题，需要你重新安装操作系统。 Microsoft 无法保证你能够解决由于错误使用注册表编辑器而导致的问题。 你自行承担使用注册表编辑器的风险。

##### 更改自动计划

1.  使用注册表编辑器，创建并设置以下注册表值中的某一个：

    -   设置以天为单位的更新频率（最少为 1 天）：创建名为“TemplateUpdateFrequency”的新注册表值，并为该数据定义整数值，该值将指定向已下载模板下载任何更改的频率（以天为单位）。 使用下表查找创建此新注册表值的注册表路径。

        |注册表路径|类型|值|
        |---------|------|-----|
        |HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC|REG_DWORD|TemplateUpdateFrequency|

    -   设置以秒为单位的更新频率（最少为 1 秒）：创建名为“TemplateUpdateFrequencyInSeconds”的新注册表值，并为该数据定义整数值，该值将指定向已下载模板下载任何更改的频率（以秒为单位）。 使用下表查找创建此新注册表值的注册表路径。

        |注册表路径|类型|值|
        |---------|------|-----|
        |HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC|REG_DWORD|TemplateUpdateFrequencyInSeconds|

    请确保你创建并设置这两个注册表值中的其中一个，而不是对这两个注册表值都执行此操作。 如果两者均存在，将忽略 **TemplateUpdateFrequency**。

2.  如果你想要强制即时刷新模板，请转到下一个过程。 否则，请立即重启 Office 应用程序和文件资源管理器实例。

##### 强制执行即时刷新

1.  使用注册表编辑器，删除“LastUpdatedTime”值的数据。 例如，数据可能显示“2015-04-20T15:52”；删除 2015-04-20T15:52，使得数据不会显示。 使用下表查找删除此注册表值数据的注册表路径。

    |注册表路径|类型|值|
    |---------|------|-----|
    |HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC\&lt;MicrosoftRMS_FQDN&gt;\Template|REG_SZ|LastUpdatedTime|
    > [!TIP]
    > 在注册表路径中，*&lt;MicrosoftRMS_FQDN&gt;* 是指 Microsoft RMS 服务 FQDN。 如果你想要验证此值：
    > 
    > 1.  对 Azure RMS 运行 [Get-AadrmConfiguration](https://msdn.microsoft.com/library/windowsazure/dn629410.aspx) cmdlet。 如果你尚未安装适用于 Azure RMS 的 Windows PowerShell 模块，请参阅[安装适用于 Azure 权限管理的 Windows PowerShell](../Topic/Installing_Windows_PowerShell_for_Azure_Rights_Management.md)。
    > 2.  在输出中找到 **LicensingIntranetDistributionPointUrl** 值。
    > 
    >     例如：**LicensingIntranetDistributionPointUrl：https://5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com/_wmcs/licensing**
    > 3.  在该值中，将“https://”和“/_wmcs/licensing”从字符串中删除。 剩下的值就是 Microsoft RMS 服务 FQDN。 在我们的示例中，Microsoft RMS 服务 FQDN 会是以下值：
    > 
    >     **5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com**

2.  删除以下文件夹及其包含的所有文件：**%localappdata%\Microsoft\MSIPC\Templates**

3.  请重启 Office 应用程序和文件资源管理器实例。

### <a name="BKMK_Office2010ForceUpdate"></a>仅适用于 Office 2010：如何强制执行针对已更改自定义模板的刷新
通过编辑运行 Office 2010 的计算机上的注册表，你可以设置值，使得更改的模板在计算机上无需等待用户注销后又重新打开即可刷新。 你还可以通过删除注册表值中的现有数据，强制执行即时刷新。

> [!WARNING]
> 如果你没有正确使用注册表编辑器，则可能导致严重问题，需要你重新安装操作系统。 Microsoft 无法保证你能够解决由于错误使用注册表编辑器而导致的问题。 你自行承担使用注册表编辑器的风险。

##### 更改更新频率

1.  使用注册表编辑器，创建名为“UpdateFrequency”的新注册表值，并为该数据定义整数值，该值将指定向已下载模板下载任何更改的频率（以天为单位）。 使用下表查找创建此新注册表值的注册表路径。

    |注册表路径|类型|值|
    |---------|------|-----|
    |HKEY_CURRENT_USER\Software\Microsoft\MSDRM\TemplateManagement|REG_DWORD|UpdateFrequency|

2.  如果你想要强制即时刷新模板，请转到下一个过程。 否则，请立即重新启动 Office 应用程序。

##### 强制执行即时刷新

1.  使用注册表编辑器，删除“LastUpdatedTime”值的数据。 例如，数据可能显示“2015-04-20T15:52”；删除 2015-04-20T15:52，使得数据不会显示。 使用下表查找删除此注册表值数据的注册表路径。

    |注册表路径|类型|值|
    |---------|------|-----|
    |HKEY_CURRENT_USER\Software\Microsoft\MSDRM\TemplateManagement|REG_SZ|lastUpdatedTime|

2.  删除以下文件夹及其包含的所有文件：**%localappdata%\Microsoft\MSIPC\Templates**

3.  重新启动 Office 应用程序。

## <a name="BKMK_PowerShellTemplates"></a>Windows PowerShell 参考
在 Azure 经典门户中创建和管理模板所需执行的操作均可使用 Windows PowerShell 从命令行执行。 此外，你还能够导出和导入模板，因此能够在租户之间复制模板，或者在模板中执行对复杂属性（例如多语言名称和描述）的批量编辑。

你还可以使用导出和导入来备份和还原自定义模板，最好是经常备份你的自定义模板，这样一来，如果你发现所做的更改不是你想要的，即可轻松还原到以前的版本。

> [!IMPORTANT]
> 若要使用 Windows PowerShell 来创建和管理 Azure RMS 权限策略模板，必须安装至少 2.0.0.0 版的[适用于 Azure RMS 的 Windows PowerShell 模块](http://go.microsoft.com/fwlink/?LinkId=257721)。
> 
> 如果你已经安装了此 Windows PowerShell 模块，请在 PowerShell 窗口中运行以下命令以检查版本号：`(Get-Module aadrm -ListAvailable).Version`

有关安装说明，请参阅[安装适用于 Azure 权限管理的 Windows PowerShell](../Topic/Installing_Windows_PowerShell_for_Azure_Rights_Management.md)。

支持创建和管理模板的 cmdlet：

-   [Add-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727075.aspx)

-   [Export-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727078.aspx)

-   [Get-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727079.aspx)

-   [Get-AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727081.aspx)

-   [Import-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727077.aspx)

-   [New-AadrmRightsDefinition](https://msdn.microsoft.com/library/azure/dn727080.aspx)

-   [Remove-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727082.aspx)

-   [Set-AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727076.aspx)

## 后续步骤
为 Azure Rights Management 配置自定义模板后，向用户和管理员推出 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]之前，你可以使用 [Azure 权限管理部署路线图](../Topic/Azure_Rights_Management_Deployment_Roadmap.md)来检查是否还需要执行其他配置步骤。 如果不需要执行其他配置步骤，请参阅[使用 Azure 权限管理](../Topic/Using_Azure_Rights_Management.md) 以获取操作指导，帮助你的组织成功完成部署。

## 请参阅
[配置 Azure 权限管理](../Topic/Configuring_Azure_Rights_Management.md)

