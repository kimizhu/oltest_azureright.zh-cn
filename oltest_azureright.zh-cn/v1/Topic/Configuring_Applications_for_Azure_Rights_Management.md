---
description: na
keywords: na
pagetitle: Configuring Applications for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ea09cbc5-b98b-444e-8b60-5bc3cb199c36
---
# 为 Azure 权限管理配置应用程序
> [!NOTE]
> 此信息适用于已部署了 Azure 权限管理的 IT 管理员和顾问。 如果你要寻找有关如何针对特定应用程序使用 Rights Management，或者如何打开权限保护文件的用户帮助和信息，请使用你的应用程序附带的帮助和指南。
> 
> 例如，对于 Office 应用程序，请单击帮助图标并输入搜索词，例如 **Rights Management** 或 **IRM**。 有关适用于 Windows 的 RMS 共享应用程序，请参阅[权限管理共享应用程序用户指南](http://technet.microsoft.com/library/dn339006.aspx)。

在为组织部署 Azure Rights Management (RMS) 之后，请使用以下信息配置应用程序和服务以支持 Azure RMS。 其中包括 Word 2013 和 Word 2010 等 Office 应用程序，以及 Exchange Online（传输规则、数据丢失预防、请勿转发和消息加密）与 SharePoint Online（受保护库）等服务。 有关这些应用程序和服务如何支持 Rights Management 的信息，请参阅[应用程序如何支持 Azure 权限管理](../Topic/How_Applications_Support_Azure_Rights_Management.md)。

> [!IMPORTANT]
> 有关支持版本和其他要求的信息，请参阅[Azure 权限管理要求](../Topic/Requirements_for_Azure_Rights_Management.md)。

-   [Office 365：客户端和联机服务的配置](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_O365)

    -   [Exchange Online：IRM 配置](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_ExchangeOnline)

    -   [SharePoint Online 和 OneDrive for Business:IRM 配置](#BKMK_SharePointOnline)

-   [Office 2016 和 Office 2013：客户端配置](#BKMK_Office2013Configuration)

-   [Office 2010：客户端配置](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_Office2010Configuration)

-   [权限管理共享应用程序：客户端安装和配置](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharingApp)

    -   [适用于 Windows 的 RMS 共享应用程序：安装和配置](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharingAppforWindows)

    -   [适用于移动平台的 RMS 共享应用程序：安装](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharingAppMovileDevices)

-   [支持 RMS API 的其他应用程序：安装和配置](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_RMSAPIs)

若要配置本地服务器，例如 Exchange Server 和 SharePoint Server，请参阅[部署 Azure 权限管理连接器](../Topic/Deploying_the_Azure_Rights_Management_Connector.md)。

> [!TIP]
> 有关配置为使用 Azure RMS 的应用程序的高级示例和屏幕截图，请参阅[什么是 Azure 权限管理？](../Topic/What_is_Azure_Rights_Management_.md)主题中的[运行中的 Azure RMS：管理员和用户看到的内容](../Topic/What_is_Azure_Rights_Management_.md#BKMK_RMSpictures)部分。

## <a name="BKMK_O365"></a>Office 365：客户端和联机服务的配置
由于 Office 365 以本机方式支持 Azure RMS，因此无需客户端计算机配置即可支持各个应用程序（例如 Word、Excel、PowerPoint、Outlook 和 Outlook Web App）的信息权限管理 (IRM) 功能。 用户只需使用他们的 [!INCLUDE[o365_1](../Token/o365_1_md.md)] 凭据登录 Office 应用程序，即可保护文件和电子邮件，并可使用其他人保护的文件和电子邮件。

但是，我们建议你使用 Rights Management 共享应用程序，为这些应用程序提供补充，使得用户能够发挥 Office 加载项的优势。 有关详细信息，请参阅本主题中的[权限管理共享应用程序：客户端安装和配置](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharingApp)部分。

### <a name="BKMK_ExchangeOnline"></a>Exchange Online：IRM 配置
若要配置 Exchange Online 以支持 Azure RMS，你必须为 Exchange Online 配置信息权限管理 (IRM) 服务。 为此，你可以使用 Windows PowerShell（无需安装单独的模块）并运行[适用于 Exchange Online 的 PowerShell 命令](https://technet.microsoft.com/library/jj200677.aspx)。

> [!NOTE]
> 如果你对 Azure RMS 使用客户管理的租户密钥 (BYOK)，而不是默认配置（即 Microsoft 管理的租户密钥），则当前不能将 Exchange Online 配置为支持 Azure RMS。 有关详细信息，请参阅[BYOK 定价和限制](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_Pricing)主题中的[计划和实现你的 Azure 权限管理租户密钥](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md)部分。
> 
> 如果你尝试在 Azure RMS 使用 BYOK 时配置 Exchange Online，则导入密钥命令（下面过程中的步骤 5）将失败并显示错误消息 **[FailureCategory=Cmdlet-FailedToGetTrustedPublishingDomainFromRmsOnlineException]**。

以下步骤提供了一组典型的命令，你可以运行这些命令以允许 Exchange Online 使用 Azure RMS：

1.  如果这是你第一次在计算机上使用 Windows PowerShell for Exchange Online，必须配置 Windows PowerShell 以运行签名的脚本。 使用“以管理员身份运行”选项启动 Windows PowerShell 会话，然后键入：

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

2.  在 Windows PowerShell 会话中，使用为远程 Shell 访问启用的帐户登录到 Exchange Online。 默认情况下，将允许在 Exchange Online 中创建的所有帐户进行远程 Shell 访问，但可以使用 [Set-User &lt;UserIdentity&gt; -RemotePowerShellEnabled](https://technet.microsoft.com/library/jj984292%28v=exchg.160%29.aspx) 命令将此项禁用（和启用）。

    若要登录，请键入：

    ```
    $Cred = Get-Credential
    ```
    在“Windows PowerShell 凭据请求”对话框中，提供你的 Office 365 用户名和密码。

3.  通过运行以下两个命令连接到 Exchange Online 服务：

    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell/ -Credential $Cred -Authentication Basic –AllowRedirection
    ```

    ```
    Import-PSSession $Session
    ```

4.  根据你所在区域，指定 Azure RMS 租户密钥的位置：

    适用于北美（以及政府订阅）：

    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```
    适用于欧洲：

    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc"
    ```
    适用于亚洲：

    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc"
    ```
    适用于南美：

    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

5.  以受信任的发布域 (TPD) 的形式从 Azure RMS 将配置数据导入到 Exchange Online。 这包括 Azure RMS 租户密钥和 Azure RMS 模板：

    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -name "RMS Online"
    ```
    在此命令中，我们将 **RMS Online** 的名称用作 Exchange Online 中 Azure RMS 的 TPD 的基名称。 导入 TPD 后，它将在 Exchange Online 中名为 **RMS Online - 1**。

6.  启用 Azure RMS 功能，以便 IRM 功能可用于 Exchange Online：

    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```
    运行此命令后，将自动为 Outlook 客户端、Outlook Web 应用和 Exchange Active Sync 启用 Rights Management。

7.  （可选）使用以下命令测试此配置是否成功：

    ```
    Test-IRMConfiguration -Sender <user email address>
    ```
    例如：**Test-IRMConfiguration -Sender  adams@contoso.com**

    此命令将运行一系列检查，包括验证与服务的连接，检索配置，检索 URI、许可证和任何模板。 在 Windows PowerShell 会话中，你将看到每一项的结果并在结束时看到是否所有内容均已通过这些检查：**总体结果：通过**

8.  与远程 PowerShell 会话断开连接：

    ```
    Remove-PSSession $Session
    ```

现在用户可以使用 Azure RMS 来保护其电子邮件。 例如，在 Outlook Web App 中，从扩展菜单 (**...**) 中选择“设置权限”，然后选择“不转发”或可用模板之一，以便将信息保护应用于电子邮件和任何附件。 但是，由于 Outlook Web App 将缓存 UI 一天时间，请在运行这些配置命令后并在尝试将信息保护应用于电子邮件前，等待经过这段时间。 在 UI 更新以反映新配置之前，你将在“设置权限”菜单中看不到任何选项。

> [!IMPORTANT]
> 如果你为 Azure RMS 创建了新的[自定义模板](https://technet.microsoft.com/library/dn642472.aspx)或更新了这些模板，则每次都必须运行以下 Exchange Online PowerShell 命令（如有必要，请先运行步骤 2 和步骤 3）来将这些更改同步到 Exchange Online：`Import-RMSTrustedPublishingDomain -Name "RMS Online - 1" -RefreshTemplates –RMSOnline`

作为 Exchange 管理员，你现在可以配置自动应用信息保护的功能，如[传输规则](https://technet.microsoft.com/library/dd302432.aspx)、[数据丢失防护 (DLP) 策略](https://technet.microsoft.com/library/jj150527%28v=exchg.150%29.aspx)和[受保护的语音邮件](https://technet.microsoft.com/library/dn198211%28v=exchg.150%29.aspx)（统一消息传送）。

有关配置 Exchange Online 以启用 IRM 功能的详细说明，请参阅 Exchange 库中的文档。 例如：

-   [使用远程 PowerShell 连接到 Exchange Online](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)

-   [将 IRM 配置为使用 Azure Rights Management](https://technet.microsoft.com/library/dn151475%28v=exchg.150%29.aspx)

#### Office 365 消息加密
运行前一部分中所述的相同步骤，但如果你不希望显示模板，请在步骤 6 之前运行以下命令，以防止在 Outlook Web 应用和 Outlook 客户端中提供 IRM 模板：`Set-IRMConfiguration -ClientAccessServerEnabled $false`

然后，你便可以将[传输规则](https://technet.microsoft.com/library/dd302432.aspx)配置为在收件人位于组织外部时自动修改消息安全性，并选择“应用 Office 365 消息加密”选项。

有关消息加密的详细信息，请参阅 Exchange 库中的 [Office 365 中的加密](https://technet.microsoft.com/library/dn569286.aspx)。

### <a name="BKMK_SharePointOnline"></a>SharePoint Online 和 OneDrive for Business:IRM 配置
若要配置 SharePoint Online 和 OneDrive for Business 以支持 Azure RMS，你必须先通过使用 SharePoint 管理中心，为 SharePoint Online 启用信息权限管理 (IRM) 服务。 然后，站点所有者可以使用 IRM 保护其 SharePoint 列表和文档库，用户可以使用 IRM 保护其 OneDrive for Business 库，以便在该处保存并与其他人共享的文档自动由 Azure RMS 保护。

若要为 SharePoint Online 启用信息权限管理 (IRM) 服务，请参阅 Office 网站中的以下说明：

-   [在 SharePoint 管理中心设置信息权限管理 (IRM)](http://office.microsoft.com/office365-sharepoint-online-enterprise-help/set-up-information-rights-management-irm-insharepoint-online-HA102895193.aspx)

由 Office 365 管理员进行此配置。

#### 为库和列表配置 IRM
在你为 SharePoint 启用 IRM 服务后，站点所有者可以使用 IRM 保护其 SharePoint 文档库和列表。 有关说明，请参阅 Office 网站中的以下内容：

-   [将信息权限管理应用于列表或库](http://office.microsoft.com/sharepoint-help/apply-information-rights-management-to-a-list-or-library-HA102891460.aspx)

由 SharePoint 站点管理员进行此配置。

#### <a name="BKMK_OneDrive"></a>为 OneDrive for Business 配置 IRM
在你为 SharePoint Online 启用 IRM 服务之后，可以配置用户的 OneDrive for Business 文档库以进行 Rights Management 保护。  用户可以使用其 OneDrive 中的“设置”图标为自己配置此项。 虽然管理员不能使用 SharePoint 管理中心为用户的 OneDrive for Business 配置 Rights Management，但是你可以使用 Windows PowerShell 执行此操作。

> [!NOTE]
> 有关配置 OneDrive for Business 的详细信息，请参阅 Office 文档[在 Office 365 中设置 OneDrive for Business](https://support.office.com/article/Set-up-OneDrive-for-Business-in-Office-365-3e21f8f0-e0a1-43be-aa3e-8c0236bf11bb)。

##### 用户配置
为用户提供这些说明，以便他们可以配置其 OneDrive for Business 并使用 IRM 保护其业务文件。

1.  在 OneDrive 中，单击“设置”图标，以打开“设置”菜单，然后单击“网站内容”。

2.  将鼠标指针悬停在“文档”磁贴上，选择省略号 (**...**)，然后单击“设置”。

3.  在“设置”页上的“权限和管理”部分中，单击“信息权限管理”。

4.  在“信息权限管理设置”页上，选择“下载时限制对此库的权限”复选框，为权限指定你选择的名称和描述，然后可以选择单击“显示选项”以配置可选配置，然后单击“确定”。

    有关配置选项的详细信息，请参阅 Office 文档中[将信息权限管理应用于列表或库](https://support.office.com/article/Apply-Information-Rights-Management-to-a-list-or-library-3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1)中的说明。

由于此配置依赖于用户（而不是管理员）使用 IRM 保护其 OneDrive for Business 库，因此请让用户了解保护其文件的好处以及如何执行此操作。 例如，说明当用户从 OneDrive for Business 共享某个文档时，只有他们授权的人员可以访问该文档并具有他们可以配置的任何限制，即使该文件被重命名并复制其他位置，也是如此。

##### 管理员配置
虽然你不能使用 SharePoint 管理中心为用户的 OneDrive for Business 配置 IRM，但是你可以使用 Windows PowerShell 执行此操作。 若要为这些库启用 IRM，请执行以下步骤：

1.  下载并安装 [SharePoint Online 客户端组件 SDK](http://www.microsoft.com/en-us/download/details.aspx?id=42038)。

2.  下载并安装 [SharePoint Online 命令行管理程序](http://www.microsoft.com/en-us/download/details.aspx?id=35588)。

3.  在计算机上复制以下脚本的内容，并将文件命名为 Set-IRMOnOneDriveForBusiness.ps1。

    *&#42;&#42;免责声明&#42;&#42;*：此示例脚本在任何 Microsoft 标准支持计划或服务下均不受支持。 此示例脚本按原样提供，不提供任何形式的保证。

    ```
    # Requires Windows PowerShell version 3 <# Description: Configures IRM policy settings for OneDrive for Business and can also be used for SharePoint Online libraries and lists Script Installation Requirements: SharePoint Online Client Components SDK http://www.microsoft.com/en-us/download/details.aspx?id=42038 SharePoint Online Management Shell http://www.microsoft.com/en-us/download/details.aspx?id=35588 ====== #> # URL will be in the format https://<tenant-name>-admin.sharepoint.com $sharepointAdminCenterUrl = "https://contoso-admin.sharepoint.com" $tenantAdmin = "admin@contoso.com" $webUrls = @("https://contoso-my.sharepoint.com/personal/user1_contoso_com", "https://contoso-my.sharepoint.com/personal/user2_contoso_com", "https://contoso-my.sharepoint.com/personal/user3_contoso_com") <# As an alternative to specifying the URLs as an array, you can import them from a CSV file (no header, single value per row). Then, use: $webUrls = Get-Content -Path "File_path_and_name.csv" #> $listTitle = "Documents" function Load-SharePointOnlineClientComponentAssemblies { [cmdletbinding()] param() process { # assembly location: C:\Program Files\Common Files\microsoft shared\Web Server Extensions\16\ISAPI try { Write-Verbose "Loading Assembly: Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null return $true } catch { if($_.Exception.Message -match "Could not load file or assembly") { Write-Error -Message "Unable to load the SharePoint Server 2013 Client Components.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=42038" } else { Write-Error -Exception $_.Exception } return $false } } } function Load-SharePointOnlineModule { [cmdletbinding()] param() process { do { # Installation location: C:\Program Files\SharePoint Online Management Shell\Microsoft.Online.SharePoint.PowerShell $spoModule = Get-Module -Name Microsoft.Online.SharePoint.PowerShell -ErrorAction SilentlyContinue if(-not $spoModule) { try { Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking return $true } catch { if($_.Exception.Message -match "Could not load file or assembly") { Write-Error -Message "Unable to load the SharePoint Online Management Shell.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=35588" } else { Write-Error -Exception $_.Exception } return $false } } else { return $true } } while(-not $spoModule) } } function Set-IrmConfiguration { [cmdletbinding()] param( [parameter(Mandatory=$true)][Microsoft.SharePoint.Client.List]$List, [parameter(Mandatory=$true)][string]$PolicyTitle, [parameter(Mandatory=$true)][string]$PolicyDescription, [parameter(Mandatory=$false)][switch]$IrmReject, [parameter(Mandatory=$false)][DateTime]$ProtectionExpirationDate, [parameter(Mandatory=$false)][switch]$DisableDocumentBrowserView, [parameter(Mandatory=$false)][switch]$AllowPrint, [parameter(Mandatory=$false)][switch]$AllowScript, [parameter(Mandatory=$false)][switch]$AllowWriteCopy, [parameter(Mandatory=$false)][int]$DocumentAccessExpireDays, [parameter(Mandatory=$false)][int]$LicenseCacheExpireDays, [parameter(Mandatory=$false)][string]$GroupName ) process { Write-Verbose "Applying IRM Configuration on '$($List.Title)'" # reset the value to the default settings $list.InformationRightsManagementSettings.Reset() $list.IrmEnabled = $true # IRM Policy title and description $list.InformationRightsManagementSettings.PolicyTitle       = $PolicyTitle $list.InformationRightsManagementSettings.PolicyDescription = $PolicyDescription # Set additional IRM library settings # Do not allow users to upload documents that do not support IRM $list.IrmReject = $IrmReject.IsPresent $parsedDate = Get-Date if([DateTime]::TryParse($ProtectionExpirationDate, [ref]$parsedDate)) { # Stop restricting access to the library at <date> $list.IrmExpire = $true $list.InformationRightsManagementSettings.DocumentLibraryProtectionExpireDate = $ProtectionExpirationDate } # Prevent opening documents in the browser for this Document Library $list.InformationRightsManagementSettings.DisableDocumentBrowserView = $DisableDocumentBrowserView.IsPresent # Configure document access rights # Allow viewers to print $list.InformationRightsManagementSettings.AllowPrint = $AllowPrint.IsPresent # Allow viewers to run script and screen reader to function on downloaded documents $list.InformationRightsManagementSettings.AllowScript = $AllowScript.IsPresent # Allow viewers to write on a copy of the downloaded document $list.InformationRightsManagementSettings.AllowWriteCopy = $AllowWriteCopy.IsPresent if($DocumentAccessExpireDays) { # After download, document access rights will expire after these number of days (1-365) $list.InformationRightsManagementSettings.EnableDocumentAccessExpire = $true $list.InformationRightsManagementSettings.DocumentAccessExpireDays   = $DocumentAccessExpireDays } # Set group protection and credentials interval if($LicenseCacheExpireDays) { # Users must verify their credentials using this interval (days) $list.InformationRightsManagementSettings.EnableLicenseCacheExpire = $true $list.InformationRightsManagementSettings.LicenseCacheExpireDays   = $LicenseCacheExpireDays } if($GroupName) { # Allow group protection. Default group: $list.InformationRightsManagementSettings.EnableGroupProtection = $true $list.InformationRightsManagementSettings.GroupName             = $GroupName } } end { if($list) { Write-Verbose "Committing IRM configuration settings on '$($list.Title)'" $list.InformationRightsManagementSettings.Update() $list.Update() $script:clientContext.Load($list) $script:clientContext.ExecuteQuery() } } } function Get-CredentialFromCredentialCache { [cmdletbinding()] param([string]$CredentialName) #if( Test-Path variable:\global:CredentialCache ) if( Get-Variable O365TenantAdminCredentialCache -Scope Global -ErrorAction SilentlyContinue ) { if($global:O365TenantAdminCredentialCache.ContainsKey($CredentialName)) { Write-Verbose "Credential Cache Hit: $CredentialName" return $global:O365TenantAdminCredentialCache[$CredentialName] } } Write-Verbose "Credential Cache Miss: $CredentialName" return $null } function Add-CredentialToCredentialCache { [cmdletbinding()] param([System.Management.Automation.PSCredential]$Credential) if(-not (Get-Variable CredentialCache -Scope Global -ErrorAction SilentlyContinue)) { Write-Verbose "Initializing the Credential Cache" $global:O365TenantAdminCredentialCache = @{} } Write-Verbose "Adding Credential to the Credential Cache" $global:O365TenantAdminCredentialCache[$Credential.UserName] = $Credential } # load the required assemblies and Windows PowerShell modules if(-not ((Load-SharePointOnlineClientComponentAssemblies) -and (Load-SharePointOnlineModule)) ) { return } # Add the credentials to the client context and SharePoint Online service connection # check for cached credentials to use $o365TenantAdminCredential = Get-CredentialFromCredentialCache -CredentialName $tenantAdmin if(-not $o365TenantAdminCredential) { # when credentials are not cached, prompt for the tenant admin credentials $o365TenantAdminCredential = Get-Credential -UserName $tenantAdmin -Message "Enter the password for the Office 365 admin" if(-not $o365TenantAdminCredential -or -not $o365TenantAdminCredential.UserName -or $o365TenantAdminCredential.Password.Length -eq 0 ) { Write-Error -Message "Could not validate the supplied tenant admin credentials" return } # add the credentials to the cache Add-CredentialToCredentialCache -Credential $o365TenantAdminCredential } # connect to Office365 first, required for SharePoint Online cmdlets to run Connect-SPOService -Url $sharepointAdminCenterUrl -Credential $o365TenantAdminCredential # enumerate each of the specified site URLs foreach($webUrl in $webUrls) { $grantedSiteCollectionAdmin = $false try { # establish the client context and set the credentials to connect to the site $script:clientContext = New-Object Microsoft.SharePoint.Client.ClientContext($webUrl) $script:clientContext.Credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($o365TenantAdminCredential.UserName, $o365TenantAdminCredential.Password) # initialize the site and web context $script:clientContext.Load($script:clientContext.Site) $script:clientContext.Load($script:clientContext.Web) $script:clientContext.ExecuteQuery() # load and ensure the tenant admin user account if present on the target SharePoint site $tenantAdminUser = $script:clientContext.Web.EnsureUser($o365TenantAdminCredential.UserName) $script:clientContext.Load($tenantAdminUser) $script:clientContext.ExecuteQuery() # check if the tenant admin is a site admin if( -not $tenantAdminUser.IsSiteAdmin ) { try { # grant the tenant admin temporary admin rights to the site collection Set-SPOUser -Site $script:clientContext.Site.Url -LoginName $o365TenantAdminCredential.UserName -IsSiteCollectionAdmin $true | Out-Null $grantedSiteCollectionAdmin = $true } catch { Write-Error $_.Exception return } } try { # load the list orlibrary using CSOM $list = $null $list = $script:clientContext.Web.Lists.GetByTitle($listTitle) $script:clientContext.Load($list) $script:clientContext.ExecuteQuery() # **************  ADMIN INSTRUCTIONS  ************** # If necessary, modify the following Set-IrmConfiguration parameters to match your required values # The supplied options and values are for example only # Example that shows the Set-IrmConfiguration command with all parameters: Set-IrmConfiguration -List $list -PolicyTitle "Protected Files" -PolicyDescription "This policy restricts access to authorized users" -IrmReject -ProtectionExpirationDate $(Get-Date).AddDays(180) -DisableDocumentBrowserView -AllowPrint -AllowScript -AllowWriteCopy -LicenseCacheExpireDays 25 -DocumentAccessExpireDays 90 Set-IrmConfiguration -List $list -PolicyTitle "Protected Files" -PolicyDescription "This policy restricts access to authorized users" } catch { Write-Error -Message "Error setting IRM configuration on site: $webUrl.`nError Details: $($_.Exception.ToString())" } } finally { if($grantedSiteCollectionAdmin) { # remove the temporary admin rights to the site collection Set-SPOUser -Site $script:clientContext.Site.Url -LoginName $o365TenantAdminCredential.UserName -IsSiteCollectionAdmin $false | Out-Null } } } Disconnect-SPOService -ErrorAction SilentlyContinue
    ```

4.  查看脚本，然后进行以下更改：

    1.  搜索 `$sharepointAdminCenterUrl` 并将示例值替换为你自己的 SharePoint 管理中心 URL。

        当你进入 SharePoint 管理中心，你会发现此值作为基 URL 并且具有以下格式：https://*&lt;tenant_name&gt;*-admin.sharepoint.com

        例如，如果租户名称为“contoso”，则会指定：**https://contoso-admin.sharepoint.com**

    2.  搜索 `$tenantAdmin` 并将示例值替换为你自己的 Office 365 完全限定全局管理员帐户。

        此值与你用来以全局管理员身份登录到 Office 365 管理门户的帐户相同，并具有以下格式：user_name@*&lt;tenant domain name&gt;*.com

        例如，如果对于“contoso.com”租户域，Office 365 全局管理员用户名是“admin”，则会指定：**admin@contoso.com**

    3.  搜索 `$webUrls` 并将示例值替换为用户的 OneDrive for Business Web URL，根据需要添加或删除任意数量的条目。

        或者，请参见脚本中有关如何通过导入包含需要配置的所有 URL 的 .CSV 文件来替换此数组的注释。  我们提供了另一个示例脚本，用于自动搜索并提取 URL 以填充此 .CSV 文件。 当你准备好执行此操作时，请在这些步骤后展开 [用于将所有 OneDrive for Business URL 输出到 .CSV 文件的附加脚本](#BKMK_Script_OD4B_URLS) 节。

        用户的 OneDrive for Business 的 Web URL 采用以下格式：https://*&lt;tenant name&gt;*-my.sharepoint.com/personal/*&lt;user_name&gt;*_*&lt;tenant name&gt;*_com

        例如，如果用户在 contoso 租户中的用户名为“rsimone”，你会指定：**https://contoso-my.sharepoint.com/personal/rsimone_contoso_com**

    4.  由于我们使用脚本来配置 OneDrive for Business，因此请不要更改 `$listTitle` 变量的 **Documents** 值。

    5.  搜索 `ADMIN INSTRUCTIONS`。 如果你没有更改此节，则将为 IRM 配置用户的 OneDrive for Business，其中策略标题为“受保护的文件”，说明为“此策略限制授权用户的访问权限”。  将不会设置任何其他 IRM 选项，这可能适用于大多数环境。 然而，你可以更改建议的策略标题和说明，也可以添加适合你的环境的任何其他 IRM 选项。 参见脚本中注释的示例可帮助你构造你自己的一组 Set-IrmConfiguration 命令参数。

5.  保存该脚本并为其签名。 如果你未为脚本签名（更安全），则必须在计算机上配置 Windows PowerShell 才能运行未签名的脚本。 为此，请使用“以管理员身份运行”选项运行 Windows PowerShell 会话，然后键入：**Set-ExecutionPolicy Unrestricted**。 但是，此配置将允许所有未签名的脚本运行（较不安全）。

    有关为 Windows PowerShell 脚本签名的详细信息，请参阅 PowerShell 文档库中的 [about_Signing](https://technet.microsoft.com/library/hh847874.aspx)。

6.  运行该脚本，如果系统提示，请提供 Office 365 管理员帐户的密码。 如果你修改了脚本，然后在同一个 Windows PowerShell 会话中运行该脚本，则不会提示你输入凭据。

> [!TIP]
> 你还可以使用此脚本为 SharePoint Online 库配置 IRM。 对于此配置，你可能希望启用附加选项“不允许用户上载不支持 IRM 的文档”，以确保库只包含受保护的文档。    为此，请将 `-IrmReject` 参数添加到脚本中的 Set-IrmConfiguration 命令。
> 
> 你还需要修改 `$webUrls` 变量（例如，**https://contoso.sharepoint.com**）和 `$listTitle` 变量（例如，**$Reports**）。

如果你需要为用户的 OneDrive for Business 库禁用 IRM，请展开 [用于为 OneDrive for Business 禁用 IRM 的脚本](#BKMK_Script_OD4B_DisableIRM) 节。

###### <a name="BKMK_Script_OD4B_URLS"></a>用于将所有 OneDrive for Business URL 输出到 .CSV 文件的附加脚本
对于上面的步骤 4c，你可以使用以下 Windows PowerShell 脚本提取所有用户的 OneDrive for Business 库的 URL，然后可以对其进行检查、编辑（如果有必要），然后将其导入到主脚本中。

此脚本还需要 [SharePoint Online 客户端组件 SDK](http://www.microsoft.com/en-us/download/details.aspx?id=42038) 和 [SharePoint Online 命令行管理程序](http://www.microsoft.com/en-us/download/details.aspx?id=35588)。 按照相同的说明复制并粘贴它，在本地保存文件（例如，“Report-OneDriveForBusinessSiteInfo.ps1”），和前面一样修改 `$sharepointAdminCenterUrl` 和 `$tenantAdmin` 值，然后运行该脚本。

*&#42;&#42;免责声明&#42;&#42;*：此示例脚本在任何 Microsoft 标准支持计划或服务下均不受支持。 此示例脚本按原样提供，不提供任何形式的保证。

```
# Requires Windows PowerShell version 3 <# Description: Queries the search service of an Office 365 tenant to retrieve all OneDrive for Business sites. Details of the discovered sites are written to a .CSV file (by default,"OneDriveForBusinessSiteInfo_<date>.csv"). Script Installation Requirements: SharePoint Online Client Components SDK http://www.microsoft.com/en-us/download/details.aspx?id=42038 SharePoint Online Management Shell http://www.microsoft.com/en-us/download/details.aspx?id=35588 ====== #> # URL will be in the format https://<tenant-name>-admin.sharepoint.com $sharepointAdminCenterUrl = "https://contoso-admin.sharepoint.com" $tenantAdmin = "admin@contoso.onmicrosoft.com" $reportName = "OneDriveForBusinessSiteInfo_$((Get-Date).ToString("yyyy-MM-dd_hh.mm.ss")).csv" $oneDriveForBusinessSiteUrls= @() $resultsProcessed = 0 function Load-SharePointOnlineClientComponentAssemblies { [cmdletbinding()] param() process { # assembly location: C:\Program Files\Common Files\microsoft shared\Web Server Extensions\16\ISAPI try { Write-Verbose "Loading Assembly: Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null return $true } catch { if($_.Exception.Message -match "Could not load file or assembly") { Write-Error -Message "Unable to load the SharePoint Server 2013 Client Components.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=42038" } else { Write-Error -Exception $_.Exception } return $false } } } function Load-SharePointOnlineModule { [cmdletbinding()] param() process { do { # Installation location: C:\Program Files\SharePoint Online Management Shell\Microsoft.Online.SharePoint.PowerShell $spoModule = Get-Module -Name Microsoft.Online.SharePoint.PowerShell -ErrorAction SilentlyContinue if(-not $spoModule) { try { Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking return $true } catch { if($_.Exception.Message -match "Could not load file or assembly") { Write-Error -Message "Unable to load the SharePoint Online Management Shell.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=35588" } else { Write-Error -Exception $_.Exception } return $false } } else { return $true } } while(-not $spoModule) } } function Get-CredentialFromCredentialCache { [cmdletbinding()] param([string]$CredentialName) #if( Test-Path variable:\global:CredentialCache ) if( Get-Variable O365TenantAdminCredentialCache -Scope Global -ErrorAction SilentlyContinue ) { if($global:O365TenantAdminCredentialCache.ContainsKey($CredentialName)) { Write-Verbose "Credential Cache Hit: $CredentialName" return $global:O365TenantAdminCredentialCache[$CredentialName] } } Write-Verbose "Credential Cache Miss: $CredentialName" return $null } function Add-CredentialToCredentialCache { [cmdletbinding()] param([System.Management.Automation.PSCredential]$Credential) if(-not (Get-Variable CredentialCache -Scope Global -ErrorAction SilentlyContinue)) { Write-Verbose "Initializing the Credential Cache" $global:O365TenantAdminCredentialCache = @{} } Write-Verbose "Adding Credential to the Credential Cache" $global:O365TenantAdminCredentialCache[$Credential.UserName] = $Credential } # load the required assemblies and Windows PowerShell modules if(-not ((Load-SharePointOnlineClientComponentAssemblies) -and (Load-SharePointOnlineModule)) ) { return } # Add the credentials to the client context and SharePoint Online service connection # check for cached credentials to use $o365TenantAdminCredential = Get-CredentialFromCredentialCache -CredentialName $tenantAdmin if(-not $o365TenantAdminCredential) { # when credentials are not cached, prompt for the tenant admin credentials $o365TenantAdminCredential = Get-Credential -UserName $tenantAdmin -Message "Enter the password for the Office 365 admin" if(-not $o365TenantAdminCredential -or -not $o365TenantAdminCredential.UserName -or $o365TenantAdminCredential.Password.Length -eq 0 ) { Write-Error -Message "Could not validate the supplied tenant admin credentials" return } # add the credentials to the cache Add-CredentialToCredentialCache -Credential $o365TenantAdminCredential } # establish the client context and set the credentials to connect to the site $clientContext = New-Object Microsoft.SharePoint.Client.ClientContext($sharepointAdminCenterUrl) $clientContext.Credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($o365TenantAdminCredential.UserName, $o365TenantAdminCredential.Password) # run a query against the Office 365 tenant search service to retrieve all OneDrive for Business URLs do { # build the query object $query = New-Object Microsoft.SharePoint.Client.Search.Query.KeywordQuery($clientContext) $query.TrimDuplicates        = $false $query.RowLimit              = 500 $query.QueryText             = "SPSiteUrl:'/personal/' AND contentclass:STS_Site" $query.StartRow              = $resultsProcessed $query.TotalRowsExactMinimum = 500000 # run the query $searchExecutor = New-Object Microsoft.SharePoint.Client.Search.Query.SearchExecutor($clientContext) $queryResults = $searchExecutor.ExecuteQuery($query) $clientContext.ExecuteQuery() # enumerate the search results and store the site URLs $queryResults.Value[0].ResultRows | % { $oneDriveForBusinessSiteUrls += $_.Path $resultsProcessed++ } } while($resultsProcessed -lt $queryResults.Value.TotalRows) $oneDriveForBusinessSiteUrls | Out-File -FilePath $reportName
```

###### <a name="BKMK_Script_OD4B_DisableIRM"></a>用于为 OneDrive for Business 禁用 IRM 的脚本
如果你需要为用户的 OneDrive for Business 禁用 IRM，请使用以下示例脚本。

此脚本还需要 [SharePoint Online 客户端组件 SDK](http://www.microsoft.com/en-us/download/details.aspx?id=42038) 和 [SharePoint Online 命令行管理程序](http://www.microsoft.com/en-us/download/details.aspx?id=35588)。 复制并粘贴内容，在本地保存文件（例如，“Disable-IRMOnOneDriveForBusiness.ps1”），并修改 `$sharepointAdminCenterUrl` 和 `$tenantAdmin` 值。 手动指定 OneDrive for Business URL，或者使用上一节中的脚本以便可以导入这些 URL，然后运行该脚本。

*&#42;&#42;免责声明&#42;&#42;*：此示例脚本在任何 Microsoft 标准支持计划或服务下均不受支持。 此示例脚本按原样提供，不提供任何形式的保证。

```
# Requires Windows PowerShell version 3 <# Description: Disables IRM for OneDrive for Business and can also be used for SharePoint Online libraries and lists Script Installation Requirements: SharePoint Online Client Components SDK http://www.microsoft.com/en-us/download/details.aspx?id=42038 SharePoint Online Management Shell http://www.microsoft.com/en-us/download/details.aspx?id=35588 ====== #> $sharepointAdminCenterUrl = "https://contoso-admin.sharepoint.com" $tenantAdmin = "admin@contoso.com" $webUrls = @("https://contoso-my.sharepoint.com/personal/user1_contoso_com", "https://contoso-my.sharepoint.com/personal/user2_contoso_com", "https://contoso-my.sharepoint.com/personal/person3_contoso_com") <# As an alternative to specifying the URLs as an array, you can import them from a CSV file (no header, single value per row). Then, use: $webUrls = Get-Content -Path "File_path_and_name.csv" #> $listTitle = "Documents" function Load-SharePointOnlineClientComponentAssemblies { [cmdletbinding()] param() process { # assembly location: C:\Program Files\Common Files\microsoft shared\Web Server Extensions\16\ISAPI try { Write-Verbose "Loading Assembly: Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null return $true } catch { if($_.Exception.Message -match "Could not load file or assembly") { Write-Error -Message "Unable to load the SharePoint Server 2013 Client Components.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=42038" } else { Write-Error -Exception $_.Exception } return $false } } } function Load-SharePointOnlineModule { [cmdletbinding()] param() process { do { # Installation location: C:\Program Files\SharePoint Online Management Shell\Microsoft.Online.SharePoint.PowerShell $spoModule = Get-Module -Name Microsoft.Online.SharePoint.PowerShell -ErrorAction SilentlyContinue if(-not $spoModule) { try { Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking return $true } catch { if($_.Exception.Message -match "Could not load file or assembly") { Write-Error -Message "Unable to load the SharePoint Online Management Shell.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=35588" } else { Write-Error -Exception $_.Exception } return $false } } else { return $true } } while(-not $spoModule) } } function Remove-IrmConfiguration { [cmdletbinding()] param( [parameter(Mandatory=$true)][Microsoft.SharePoint.Client.List]$List ) process { Write-Verbose "Disabling IRM Configuration on '$($List.Title)'" $List.IrmEnabled = $false $List.IrmExpire  = $false $List.IrmReject  = $false $List.InformationRightsManagementSettings.Reset() } end { if($List) { Write-Verbose "Committing IRM configuration settings on '$($list.Title)'" $list.InformationRightsManagementSettings.Update() $list.Update() $script:clientContext.Load($list) $script:clientContext.ExecuteQuery() } } } function Get-CredentialFromCredentialCache { [cmdletbinding()] param([string]$CredentialName) #if( Test-Path variable:\global:CredentialCache ) if( Get-Variable O365TenantAdminCredentialCache -Scope Global -ErrorAction SilentlyContinue ) { if($global:O365TenantAdminCredentialCache.ContainsKey($CredentialName)) { Write-Verbose "Credential Cache Hit: $CredentialName" return $global:O365TenantAdminCredentialCache[$CredentialName] } } Write-Verbose "Credential Cache Miss: $CredentialName" return $null } function Add-CredentialToCredentialCache { [cmdletbinding()] param([System.Management.Automation.PSCredential]$Credential) if(-not (Get-Variable CredentialCache -Scope Global -ErrorAction SilentlyContinue)) { Write-Verbose "Initializing the Credential Cache" $global:O365TenantAdminCredentialCache = @{} } Write-Verbose "Adding Credential to the Credential Cache" $global:O365TenantAdminCredentialCache[$Credential.UserName] = $Credential } # load the required assemblies and Windows PowerShell modules if(-not ((Load-SharePointOnlineClientComponentAssemblies) -and (Load-SharePointOnlineModule)) ) { return } # Add the credentials to the client context and SharePoint Online service connection # check for cached credentials to use $o365TenantAdminCredential = Get-CredentialFromCredentialCache -CredentialName $tenantAdmin if(-not $o365TenantAdminCredential) { # when credentials are not cached, prompt for the tenant admin credentials $o365TenantAdminCredential = Get-Credential -UserName $tenantAdmin -Message "Enter the password for the Office 365 admin" if(-not $o365TenantAdminCredential -or -not $o365TenantAdminCredential.UserName -or $o365TenantAdminCredential.Password.Length -eq 0 ) { Write-Error -Message "Could not validate the supplied tenant admin credentials" return } # add the credentials to the cache Add-CredentialToCredentialCache -Credential $o365TenantAdminCredential } # connect to Office365 first, required for SharePoint Online cmdlets to run Connect-SPOService -Url $sharepointAdminCenterUrl -Credential $o365TenantAdminCredential # enumerate each of the specified site URLs foreach($webUrl in $webUrls) { $grantedSiteCollectionAdmin = $false try { # establish the client context and set the credentials to connect to the site $script:clientContext = New-Object Microsoft.SharePoint.Client.ClientContext($webUrl) $script:clientContext.Credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($o365TenantAdminCredential.UserName, $o365TenantAdminCredential.Password) # initialize the site and web context $script:clientContext.Load($script:clientContext.Site) $script:clientContext.Load($script:clientContext.Web) $script:clientContext.ExecuteQuery() # load and ensure the tenant admin user account if present on the target SharePoint site $tenantAdminUser = $script:clientContext.Web.EnsureUser($o365TenantAdminCredential.UserName) $script:clientContext.Load($tenantAdminUser) $script:clientContext.ExecuteQuery() # check if the tenant admin is a site admin if( -not $tenantAdminUser.IsSiteAdmin ) { try { # grant the tenant admin temporary admin rights to the site collection Set-SPOUser -Site $script:clientContext.Site.Url -LoginName $o365TenantAdminCredential.UserName -IsSiteCollectionAdmin $true | Out-Null $grantedSiteCollectionAdmin = $true } catch { Write-Error $_.Exception return } } try { # load the list orlibrary using CSOM $list = $null $list = $script:clientContext.Web.Lists.GetByTitle($listTitle) $script:clientContext.Load($list) $script:clientContext.ExecuteQuery() Remove-IrmConfiguration -List $list } catch { Write-Error -Message "Error setting IRM configuration on site: $webUrl.`nError Details: $($_.Exception.ToString())" } } finally { if($grantedSiteCollectionAdmin) { # remove the temporary admin rights to the site collection Set-SPOUser -Site $script:clientContext.Site.Url -LoginName $o365TenantAdminCredential.UserName -IsSiteCollectionAdmin $false | Out-Null } } } Disconnect-SPOService -ErrorAction SilentlyContinue
```

## <a name="BKMK_Office2013Configuration"></a>Office 2016 和 Office 2013：客户端配置
由于 Office 的这些更高版本以本机方式支持 Azure RMS，因此无需客户端计算机配置即可支持各个应用程序（例如 Word、Excel、PowerPoint、Outlook 和 Outlook Web App）的信息权限管理 (IRM) 功能。 用户只需使用他们的 [!INCLUDE[o365_1](../Token/o365_1_md.md)] 凭据登录 Office 应用程序，即可保护文件和电子邮件，并可使用其他人保护的文件和电子邮件。

但是，我们建议你使用 Rights Management 共享应用程序，为这些应用程序提供补充，使得用户能够发挥 Office 加载项的优势。 有关详细信息，请参阅本主题中的[权限管理共享应用程序：客户端安装和配置](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharingApp)部分。

## <a name="BKMK_Office2010Configuration"></a>Office 2010：客户端配置
对于要将 Azure RMS 用于 Office 2010 的客户端计算机，它们必须安装适用于 Windows 的权限管理共享应用程序。 用户必须使用他们的 [!INCLUDE[o365_1](../Token/o365_1_md.md)] 凭据登录才能保护文件并使用其他用户保护的文件，此外不再需要更多配置。

有关 Rights Management 共享应用程序的详细信息，请参阅本主题中的[权限管理共享应用程序：客户端安装和配置](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharingApp)部分。

## <a name="BKMK_SharingApp"></a>权限管理共享应用程序：客户端安装和配置
客户端计算机需要权限管理 (RMS) 共享应用程序，才能将 Azure RMS 用于 Office 2010，建议在支持 Azure RMS 的所有计算机和移动设备上使用该应用程序。 通过安装 Office 加载项，RMS 共享应用程序可与 Office 应用程序集成在一起，使得用户能够轻松地从功能区直接保护文件和电子邮件。 RMS 共享应用程序还针对 Azure RMS 无法以本机方式支持的文件类型提供常规保护，以保护所有文件类型；此外，它提供一个文档跟踪站点，让用户跟踪他们保护的文件和撤消保护。

### <a name="BKMK_SharingAppforWindows"></a>适用于 Windows 的 RMS 共享应用程序：安装和配置
若要为企业部署安装和配置适用于 Windows 的 RMS 共享应用程序，请参阅 [Rights Management 共享应用程序管理员指南](http://technet.microsoft.com/library/dn339003.aspx)。

> [!TIP]
> 如果你希望为单个计算机快速安装和测试 RMS 共享应用程序，请参阅 [Rights Management 共享应用程序用户指南](http://technet.microsoft.com/library/dn339006.aspx)中的[下载和安装 Rights Management 共享应用程序](http://technet.microsoft.com/library/dn574734.aspx)。

### <a name="BKMK_SharingAppMovileDevices"></a>适用于移动平台的 RMS 共享应用程序：安装
若要安装适用于移动平台的 RMS 共享应用程序，请使用 [Microsoft Rights Management 页](http://go.microsoft.com/fwlink/?LinkId=303970)上的链接下载相关应用程序。 无需任何配置即可将 Azure RMS 用于此应用。

## <a name="BKMK_RMSAPIs"></a>支持 RMS API 的其他应用程序：安装和配置
此类别包括使用 RMS SDK 内部编写的业务线应用程序，以及来自软件供应商的使用 RMS SDK 编写的应用程序。 对于这些应用程序，请按照应用程序随附的说明操作。

## 后续步骤
将应用程序配置为支持 Azure Rights Management 后，向用户和管理员推出 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 之前，你可以使用 [Azure 权限管理部署路线图](../Topic/Azure_Rights_Management_Deployment_Roadmap.md)来检查是否还需要执行其他配置步骤。 如果不需要执行，请参阅[使用 Azure 权限管理](../Topic/Using_Azure_Rights_Management.md) 以了解后续步骤。

## 请参阅
[配置 Azure 权限管理](../Topic/Configuring_Azure_Rights_Management.md)

