---
description: na
keywords: na
pagetitle: Active Directory Rights Management Services Mobile Device Extension
search: na
ms.date: na
ms.tgt_pltfrm: na
ms.assetid: a69ead9d-7dd3-4b38-9830-4728e9757341
robots: noindex,nofollow
---
# Active Directory Rights Management Services 移动设备扩展
Active Directory Rights Management Services (AD RMS) 移动设备扩展运行在现有 AD RMS 部署之上。这使得具有移动设备的用户可以保护和使用敏感数据（如果其设备支持最新 RMS 客户端并使用支持 RMS 的应用）。例如，这些设备上的用户可以执行以下操作：

-   通过 RMS 共享应用使用采用不同格式保护的文本文件（包括 .txt、.csv 和 .xml）。

-   通过 RMS 共享应用使用受保护的图像文件（包括 .jpg、.gif 和 .tif）。

-   使用 RMS 共享应用打开任何受常规保护的文件（.pfile 格式）。

-   使用 RMS 共享应用保护设备上的图像文件。

-   使用适用于移动设备且支持 RMS 的 PDF 查看器打开 PDF 文件，这些文件受适用于 Windows 的 RMS 共享应用程序或其他支持 RMS 的应用程序保护。

-   使用来自软件供应商（提供支持 RMS 的应用）的其他应用，这些应用所支持的文件类型本身支持 RMS。

-   使用通过 RMS SDK 编写的内部开发的支持 RMS 的应用。

> [!NOTE]
> 你可以从 Microsoft 网站上的 [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970) 页面下载 RMS 共享应用。
> 
> 有关 RMS 支持的不同文件类型的详细信息，请参阅 Rights Management 共享应用程序管理员指南中的[支持的文件类型和文件扩展名](http://technet.microsoft.com/library/dn339003.aspx)部分。

如果设备使用支持 Exchange ActiveSync IRM 的邮件应用程序，则无需通过移动设备扩展在设备上使用或编写受保护的电子邮件。Exchange 2010 Service Pack 1 中引入了这种对 RMS 和移动设备的本机支持。

使用以下部分部署 Active Directory Rights Management Services (AD RMS) 移动设备扩展：

-   [AD RMS 移动设备扩展的先决条件](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_Preqs)

    -   [为 AD RMS 移动设备扩展配置 AD FS](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_ADFS)

    -   [为 AD RMS 移动设备扩展配置 AD FS](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_ADFS)

-   [为 AD RMS 移动设备扩展指定 DNS SRV 记录](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_SRV)

-   [部署 AD RMS 移动设备扩展](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_Deploy)

## <a name="BKMK_Preqs"></a>AD RMS 移动设备扩展的先决条件
在安装 AD RMS 移动设备扩展之前，请确保这些依赖项已就位。

|要求|详细信息|
|------|--------|
|Windows Server 2012 R2 或 Windows Server 2012 上的现有 AD RMS 部署。 **Note:** AD RMS 必须在单独的服务器上使用完全基于 Microsoft SQL Server 的数据库，而不是通常用于在同一服务器上进行测试的 Windows 内部数据库。|有关 AD RMS 的文档，请参阅 Windows Server 库中的 [Active Directory Rights Management Services](http://technet.microsoft.com/library/hh831364.aspx)。|
|在 Windows Server 2012 R2 上部署的 AD FS|有关 AD FS 的文档，请参阅 Windows Server 库中的 [Windows Server 2012 R2 AD FS 部署指南](http://technet.microsoft.com/library/dn486820.aspx)。<br /><br />必须为移动设备扩展配置 AD FS。有关说明，请参阅本主题中的[为 AD RMS 移动设备扩展配置 AD FS](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_ADFS)部分。|
|DNS 中的 SRV 记录|在一个或多个公司域中创建一条或多条 SRV 记录：<br /><br />-   一条记录用于用户将要使用的每一个电子邮件域后缀<br />-   一条记录用于你的 RMS 群集为保护内容而使用的每一个 FQDN<br /><br />当用户通过其移动设备提供电子邮件地址时，域后缀用于确定其应使用 AD RMS 基础结构还是 Azure RMS。找到 SRV 记录后，客户端将重定向到对应于该 URL 的 AD RMS 服务器。<br /><br />当用户通过移动设备使用受保护的内容时，客户端应用程序在 DNS 中查找与群集（用于保护内容）的 URL 中的 FQDN 相匹配的记录。然后，设备定向到在 DNS 记录中指定的 AD RMS 群集并获取许可证以打开该内容。在大多数情况下，RMS 群集将会是用于保护内容的同一 RMS 群集。<br /><br />有关如何指定 SRV 记录的信息，请参阅本主题中的[为 AD RMS 移动设备扩展指定 DNS SRV 记录](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_SRV)部分。|
|当前支持的客户端：<br /><br />-   使用最新版适用于 Android 的 RMS 共享应用的 Android 设备|最低版本为 Android 4.0.3。<br /><br />从 [Microsoft Connect 站点](https://connect.microsoft.com/site1170/Downloads)下载适用于 Android 的 RMS 共享应用并将其旁加载到设备上。|

### <a name="BKMK_ADFS"></a>为 AD RMS 移动设备扩展配置 AD FS
首先必须配置 AD FS，然后再对适用于 Android 的 RMS 共享应用进行授权。

##### 步骤 1：配置 AD FS

-   可以运行 Windows PowerShell 脚本自动配置 AD FS 以支持 AD RMS 移动设备扩展，也可以手动指定配置选项和值：

    -   若要自动配置 AD FS，请将以下内容复制并粘贴到 Windows PowerShell 脚本文件中，然后运行它：

        ```
        # This Script Configures the Microsoft Rights Management Mobile Device Extension and Claims used in the ADFS Server

        # Check if Microsoft Rights Management Mobile Device Extension is configured on the Server 
        $CheckifConfigured = Get-AdfsRelyingPartyTrust -Identifier "api.rms.rest.com"
        if ($CheckifConfigured)
        {
        Write-Host "api.rms.rest.com Identifer used for Microsoft Rights Management Mobile Device Extension is already configured on this Server"
        Write-Host $CheckifConfigured 
        }
        else
        {
        Write-Host "Configuring  Microsoft Rights Management Mobile Device Extension "

        # TransformaRules used by Microsoft Rights Management Mobile Device Extension
        # Claims: E-mail, UPN and ProxyAddresses
        $TransformRules = @"
        @RuleTemplate = "LdapClaims"
        @RuleName = "Jwt Token"
        c:[Type ==
        "http://schemas.microsoft.com/ws/2008/06/identity/claims/windowsaccountname",
        Issuer == "AD AUTHORITY"]
         => issue(store = "Active Directory", types =
        ("http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress",
        "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/upn",
        "http://schemas.xmlsoap.org/claims/ProxyAddresses"), query =
        ";mail,userPrincipalName,proxyAddresses;{0}", param = c.Value);

        @RuleTemplate = "PassThroughClaims"
        @RuleName = "JWT pass through"
        c:[Type == "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress"]
         => issue(claim = c);

        @RuleTemplate = "PassThroughClaims"
        @RuleName = "JWT pass through"
        c:[Type == "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/upn"]
         => issue(claim = c);

        @RuleTemplate = "PassThroughClaims"
        @RuleName = "JWT pass through Proxy addresses"
        c:[Type == "http://schemas.xmlsoap.org/claims/ProxyAddresses"]
         => issue(claim = c);
        "@

        # AuthorizationRules used by Microsoft Rights Management Mobile Device Extension
        # Allow All users
        $AuthorizationRules = @"
        @RuleTemplate = "AllowAllAuthzRule"
         => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit",
        Value = "true");
        "@

        # Add a Relying Part Truest with Name -"Microsoft Rights Management Mobile Device Extension" Identifier "api.rms.rest.com"
        Add-ADFSRelyingPartyTrust -Name "Microsoft Rights Management Mobile Device Extension" -Identifier "api.rms.rest.com" -IssuanceTransformRules $TransformRules -IssuanceAuthorizationRules  $AuthorizationRules

        Write-Host "Microsoft Rights Management Mobile Device Extension Configured"
        }
        ```

    -   若要手动配置 AD FS，请使用以下设置：

        |配置|值|
        |------|-----|
        |**信赖方信任**|api.rms.rest.com|
        |**声明规则**|属性存储：Active Directory<br /><br />电子邮件地址：电子邮件地址<br /><br />用户主体名称：UPN<br /><br />代理地址：https://schemas.xmlsoap.org/claims/ProxyAddresses|

##### 步骤 2：对适用于 Android 的 RMS 共享应用进行授权

-   运行以下 Windows PowerShell 命令添加对 Android 设备的支持：

    ```
    Add-AdfsClient -Name "RMSsharingAndroid" -ClientId "com.microsoft.ipviewer" -RedirectUri @("com.microsoft.ipviewer://authorize")
    ```

### <a name="BKMK_SRV"></a>为 AD RMS 移动设备扩展指定 DNS SRV 记录
必须为你的用户所使用的每个电子邮件域创建 DNS SRV 记录。如果你的所有用户都使用来自单个父域的子域，并且此连续命名空间中的所有用户都使用相同的 RMS 群集，则可以在父域中仅使用一条 SRV 记录，而 RMS 将会找到相应的 DNS 记录。

SRV 记录具有以下格式：_rmsdisco._http._tcp. *&lt;emailsuffix&gt;**&lt;portnumber&gt;**&lt;RMSClusterFQDN&gt;*

例如，如果你的组织具有使用以下电子邮件地址的用户：

-   user@contoso.com

-   user@sales.contoso.com

-   user@fabrikam.com

- 并且 contoso.com 的其他任何子域都不使用除名为“rmsserver.contoso.com”的 RMS 群集以外的其他 RMS 群集，则创建具有以下值的两条 DNS SRV 记录：

-   _rmsdisco._http._tcp.contoso.com 443 rmsserver.contoso.com

-   _rmsdisco._http._tcp.fabrikam.com 443 rmsserver.contoso.com

除了这些用于电子邮件域的 DNS SRV 记录以外，你还必须在用户域中创建另一条 DNS SRV 记录。此记录必须指定保护内容的 RMS 群集的 URL。RMS 所保护的每个文件都包含指向保护该文件的群集的 URL。移动设备使用 DNS SRV 记录和记录中指定的 URL FQDN 查找可支持移动设备的相应 RMS 群集。

例如，如果你的 RMS 群集为“rmsserver.contoso.com”，则创建一条具有以下值的 DNS SRV 记录：**_rmsdisco._http._tcp.rmsserver.contoso.com 443 rmsserver.contoso.com**

## <a name="BKMK_Deploy"></a>部署 AD RMS 移动设备扩展
在安装 AD RMS 移动设备扩展之前，请确保上一部分中的先决条件已先满足，并确保你知道 AD FS 服务器的 URL。然后执行以下操作：

1.  从 [Microsoft Connect 站点](http://go.microsoft.com/fwlink/?LinkId=397245)下载 AD RMS 移动设备扩展。

2.  运行 Setup.exe，启动 Active Directory Rights Management Services 移动设备扩展安装向导。

3.  出现提示时，输入之前配置的 AD FS 服务器的 URL。

4.  完成向导。

在 RMS 群集中的所有节点上运行此向导。

