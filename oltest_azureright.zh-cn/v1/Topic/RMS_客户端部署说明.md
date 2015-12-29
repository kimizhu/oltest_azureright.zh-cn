---
description: na
keywords: na
pagetitle: RMS 客户端部署说明
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 03cc8c6f-3b63-4794-8d92-a5df4cdf598f
---
# RMS 客户端部署说明
Rights Management 服务客户端（RMS 客户端）版本 2 也称为 MSIPC 客户端。 它是在 Windows 计算机上安装的软件，可用来与本地或云中的 Microsoft Rights Management 服务通信，以帮助保护对流经应用程序和设备的信息的访问和使用，无论这些信息是在组织边界的内部还是受管边界的外部。 除了随附[适用于 Windows 的 Rights Management 共享应用程序](https://technet.microsoft.com/library/dn919648.aspx)以外，RMS 客户端还可作为[可选下载产品](http://www.microsoft.com/download/details.aspx?id=38396)获取，在确认和接受其许可协议的情况下，客户可以通过第三方软件自由地分发它，使客户端能够保护和使用受 Rights Management 服务保护的内容。

本主题包含以下各节：

-   [Redistributing the RMS Client](#BKMK_RedistributeInstaller)

-   [Installing the RMS Client](#BKMK_InstallClient)

-   [Questions and Answers about the RMS Client](#BKMK_QA)

-   [RMS Client Settings](#BKMK_Settings)

-   [AD RMS Only: Limiting the RMS Client to Use Trusted AD RMS Servers](#BKMK_UsingTrustedServers)

-   [RMS Service Discovery](#BKMK_ServiceDiscovery)

## <a name="BKMK_RedistributeInstaller"></a>重新分发 RMS 客户端
可以通过其他应用程序和 IT 解决方案自由地重新分发和捆绑 RMS 客户端。 如果你是应用程序开发人员或解决方案提供商，并想要重新分发 RMS 客户端，可以使用两个选项：

-   建议：在应用程序安装过程中嵌入 RMS 客户端安装程序，然后在静默模式下运行（下一部分详述的 **/quiet** 开关）。

-   使 RMS 客户端成为应用程序的必备组件。 如果采用此方法，则可能需要先向用户提供有关如何获取、安装以及更新计算机以使用该客户端的其他说明，然后用户才能使用你的应用程序。

## <a name="BKMK_InstallClient"></a>安装 RMS 客户端
RMS 客户端包含在名为 **setup_msipc_***&lt;arch&gt;***.exe** 的安装程序可执行文件中，其中 *&lt;arch&gt;* 是 **x86**（对于 32 位客户端计算机）或 **x64**（对于 64 位客户端计算机）。 64 位 (x64) 安装程序包将同时安装 32 位运行时组件（以与在 64 位操作系统安装上运行的 32 位应用程序兼容）以及 64 位运行时组件（以支持本机 64 位应用程序）。 32 位 (x86) 安装程序将不会在 64 位 Windows 安装上运行。

> [!NOTE]
> 若要安装 RMS 客户端，你需要有提升的权限，例如，是本地计算机上管理员组的成员。

可以使用以下安装方法之一来安装 RMS 客户端：

-   **静默模式。** 通过使用作为命令行选项的一部分的 **/quiet** 开关，可以以静默方式在客户端计算机上安装 RMS 客户端。 以下示例命令演示了以静默模式在 64 位客户端计算机上安装 RMS 客户端：

    ```
    setup_msipc_x64.exe /quiet
    ```

-   **交互模式。** 或者，你可以使用由 RMS 客户端安装向导提供的基于 GUI 的交互式安装程序，来安装 RMS 客户端。 为此，请双击 RMS 客户端安装程序包 (**setup_msipc_***&lt;arch&gt;***.exe**)，该安装程序包位于在本地计算机上复制或下载它时所在的文件夹中。

## <a name="BKMK_QA"></a>有关 RMS 客户端的问题和解答
以下部分包含有关 RMS 客户端的常见问题及其解答。

### 哪些操作系统支持 RMS 客户端？
以下操作系统支持 RMS 客户端：

|Windows Server 操作系统|Windows 客户端操作系统|
|-----------------------|-------------------|
|Windows Server 2012 R2|Windows 8.1|
|Windows Server 2012|Windows 8|
|Windows Server 2008 R2|Windows 7（最少装有 SP1）|
|Windows Server 2008（仅限 AD RMS）|Windows Vista（最少装有 SP2，仅限 AD RMS）|

### 哪些处理器或平台支持 RMS 客户端？
x86 和 x64 计算平台支持 RMS 客户端。

### RMS 客户端安装在哪个位置？
默认情况下，RMS 客户端安装在 %ProgramFiles%\Active Directory Rights Management Services Client 2.&lt;次要版本号&gt; 中。

### 与 RMS 客户端软件关联的文件有哪些？
以下文件将连同 RMS 客户端软件一起安装：

-   Msipc.dll

-   Ipcsecproc.dll

-   Ipcsecproc_ssp.dll

-   MSIPCEvents.man

除了上述文件外，RMS 客户端还将安装使用 44 种语言的多语言用户界面 (MUI) 支持文件。 若要验证支持的语言，请运行 RMS 客户端安装，然后在安装完成后，查看默认路径下的多语言支持文件夹中的内容。

### 在我安装受支持的操作系统时，是否默认包含 RMS 客户端？
不能。 此版本的 RMS 客户端是作为可选下载产品交付的，可在运行受支持 Microsoft Windows 操作系统版本的计算机上单独安装。

### Microsoft Update 是否会自动更新 RMS 客户端？
如果此 RMS 客户端是使用静默安装选项安装的，则 RMS 客户端将继承当前的 Microsoft Update 设置。 如果 RMS 客户端是使用基于 GUI 的安装程序安装的，则 RMS 客户端安装向导将提示你启用 Microsoft Update。

## <a name="BKMK_Settings"></a>RMS 客户端设置
以下部分包含有关 RMS 客户端的设置信息。 如果使用 RMS 客户端的应用程序或服务出现问题，这些信息可能很有帮助。

> [!NOTE]
> 某些设置取决于启用 RMS 的应用程序是作为客户端模式应用程序运行（如 Microsoft Word 和 Outlook，或 RMS 共享应用程序），还是作为服务器模式应用程序运行（如 SharePoint 和 Exchange）。  在下表中，这些设置分别标识为**客户端模式**和**服务器模式**。

### RMS 客户端将许可证存储在客户端计算机上的哪个位置？
RMS 客户端将许可证存储在本地磁盘上，并且还在 Windows 注册表中缓存一些信息。

|说明|客户端模式路径|服务器模式路径|
|------|-----------|-----------|
|许可证存储位置|%localappdata%\Microsoft\MSIPC|%allusersprofile%\Microsoft\MSIPC\Server\*&lt;SID&gt;*\|
|模板存储位置|%localappdata%\Microsoft\MSIPC\Templates|%allusersprofile%\Microsoft\MSIPC\Server\Templates\*&lt;SID&gt;*\|
|注册表位置|HKEY_CURRENT_USER<br /> \Software<br /> \Classes<br /> \Local Settings<br /> \Software<br /> \Microsoft<br /> \MSIPC|HKEY_CURRENT_USER<br /> \Software<br /> \Microsoft<br /> \MSIPC<br /> \Server<br /> \*&lt;SID&gt;*|
> [!NOTE]
> *&lt;SID&gt;* 是用于运行服务器应用程序的帐户的安全标识符 (SID)。 例如，如果应用程序在内置的网络服务帐户下运行，请使用该帐户的已知 SID 的值 (S-1-5-20) 替换 *&lt;SID&gt;*。

### RMS 客户端的 Windows 注册表设置
你可以使用 Windows 注册表项设置或修改 RMS 客户端配置。 例如，作为已启用 RMS、要与 AD RMS 服务器通信的应用程序的管理员，你可能想要根据客户端计算机在 Active Directory 拓扑内的当前位置，更新企业服务位置（即，替代当前选择发布的 AD RMS 服务器）。 或者，你可能想要在客户端计算机上启用 AD RMS 跟踪，以帮助排查启用 RMS 的应用程序的问题。 使用下表来了解可针对 RMS 客户端更改的注册表设置。

|任务|设置|
|------|------|
|仅限 AD RMS：更新客户端计算机的企业服务位置|更新以下注册表项：<br /><br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\EnterpriseCertification<br />    REG_SZ：default<br />    **值：**&lt;http 或 https&gt;:// *RMS_Cluster_Name*/_wmcs/Certification<br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\EnterprisePublishing<br />    REG_SZ：default<br />    **值：**&lt;http 或 https&gt;:// *RMS_Cluster_Name*/_wmcs/Licensing|
|启用和禁用跟踪|更新以下注册表项：<br /><br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC<br />    REG_DWORD：Trace<br />    **Value：**1 表示启用跟踪，0 表示禁用跟踪（默认）|
|更改模板刷新的频率（以天为单位）|以下注册表值指定当未设置 TemplateUpdateFrequencyInSeconds 值时，在用户计算机上刷新模板的频率。  如果这两个值都未设置，则应用程序使用 RMS 客户端（版本 1.0.1784.0）下载模板所遵循的默认刷新间隔为 1 天。 在低于此版本的版本中，默认刷新间隔值为 7 天。<br /><br />**客户端模式：**<br /><br />-   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC<br />    REG_DWORD：TemplateUpdateFrequency<br />    **Value：**指定下载间隔天数的整数值（最小为 1）。<br /><br />**服务器模式：**<br /><br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\Server\*&lt;SID&gt;*<br />    REG_DWORD：TemplateUpdateFrequency<br />    **Value：**指定下载间隔天数的整数值（最小为 1）。|
|更改模板刷新的频率（以秒为单位） **Important:** 如果指定此值，将忽略以天为单位的模板刷新频率值。 指定其中一项，而不要同时指定两项。|以下注册表值指定在用户计算机上刷新模板的频率。 如果未设置此值或者用于更改以天为单位的频率的值 (TemplateUpdateFrequency)，则应用程序使用 RMS 客户端（版本 1.0.1784.0）下载模板所遵循的默认刷新间隔为 1 天。 在低于此版本的版本中，默认刷新间隔值为 7 天。<br /><br />**客户端模式：**<br /><br />-   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC<br />    REG_DWORD：TemplateUpdateFrequencyInSeconds<br />    **Value：**指定下载间隔秒数的整数值（最小为 1）。<br /><br />**服务器模式：**<br /><br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\Server\*&lt;SID&gt;*<br />    REG_DWORD：TemplateUpdateFrequencyInSeconds<br />    **Value：**指定下载间隔秒数的整数值（最小为 1）。|
|仅限 AD RMS：在下一次发布请求时立即下载模板|在测试和评估期间，你可能希望 RMS 客户端尽快下载模板。 为此，可以删除以下注册表项，使 RMS 客户端在下一次发布请求时立即下载模板，而不是按 TemplateUpdateFrequency 注册表设置指定的时间等待：<br /><br />-   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC\&lt;Server Name&gt;\Template **Note:** &lt;Server Name&gt; 可以同时具有外部 (corprights.contoso.com) 和内部 (corprights) URL，因此可能具有两个不同项。|
|仅限 AD RMS：启用联合身份验证支持|如果 RMS 客户端使用联合信任连接到 AD RMS 群集，则你必须配置联合主领域。<br /><br />-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\Federation<br />    REG_SZ：FederationHomeRealm<br />    **Value：**此注册表项的值是联合身份验证服务的统一资源标识符 (URI)（例如，“https://fs-01.contoso.com”）。|
|仅限 AD RMS：支持需要对用户输入进行基于窗体的身份验证的合作伙伴联合身份验证服务器|默认情况下，RMS 客户端在静默模式下运行，并且不需要用户输入。 但是，合作伙伴联合身份验证服务器可能会配置为需要用户输入，例如通过基于窗体的身份验证等方式。 在这种情况下，RMS 客户端必须配置为忽略静默模式，以便联合身份验证表单显示在浏览器窗口中，并提示用户进行身份验证。<br /><br />-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\Federation<br />    REG_DWORD：EnableBrowser **Note:** 如果联合身份验证服务器配置为使用基于窗体的身份验证，则此项是必需的。 如果联合身份验证服务器配置为使用 Windows 集成身份验证，则此项不是必需的。|
|仅限 AD RMS：阻止 ILS 服务使用|默认情况下，RMS 客户端支持使用受 ILS 服务保护的内容，但是可以通过设置以下注册表项对它进行配置以阻止此行为。 如果此注册表项设置为阻止 ILS 服务，则对受 ILS 服务保护内容的任何打开和使用尝试都将返回以下错误：<br />HRESULT_FROM_WIN32(ERROR_ACCESS_DISABLED_BY_POLICY)<br /><br />-   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC<br />    REG_DWORD：**DisablePassportCertification**<br />    **Value：**1 表示阻止 ILS 使用，0 表示允许 ILS 使用（默认）|

### 管理 RMS 客户端的模板分发
用户和管理员可以使用模板快速轻松地应用 Rights Management 保护，RMS 客户端将自动从其 RMS 服务器或服务下载模板。如果你将模板放置在以下文件夹位置，RMS 客户端将不会从其默认位置下载任何模板，而是下载你放入此文件夹中的模板。 RMS 客户端可能会继续从其他可用 RMS 服务器下载模板。

**客户端模式：**%localappdata%\Microsoft\MSIPC\UnmanagedTemplates

**服务器模式：**%allusersprofile%\Microsoft\MSIPC\Server\UnmanagedTemplates\*&lt;SID&gt;*

如果你使用此文件夹，则除了模板应由 AD RMS 服务器发布，并且应使用 .xml 文件扩展名以外，没有其他必须遵循的特殊命名约定。 例如，Contoso-Confidential.xml 或 Contoso-ReadOnly.xml 是有效的名称。

## <a name="BKMK_UsingTrustedServers"></a>仅限 AD RMS：将 RMS 客户端限制为仅使用受信任的 AD RMS 服务器
可以通过对本地计算机上的 Windows 注册表做出以下更改，将 RMS 客户端限制为仅使用受信任的特定 AD RMS 服务器。

**将 RMS 客户端限制为仅使用受信任的 AD RMS 服务器**

-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\TrustedServers\
    REG_DWORD：AllowTrustedServersOnly

    **Value：**如果指定一个非零值，RMS 客户端将只信任 TrustedServers 列表中配置的特定服务器以及 Azure Rights Management 服务。

**将成员添加到受信任的 AD RMS 服务器列表**

-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\TrustedServers\
    REG_SZ：*&lt;URL_or_HostName&gt;*

    **Value：**在此注册表项位置中添加的字符串值可以是 DNS 域名格式（例如 **adrms.contoso.com**），也可以是指向受信任 AD RMS 服务器的完整 URL（例如 **https://adrms.contoso.com**）。 如果指定的 URL 以 **https://** 开头，RMS 客户端将使用 SSL 或 TLS 来联系指定的 AD RMS 服务器。

## <a name="BKMK_ServiceDiscovery"></a>RMS 服务发现
RMS 服务发现可让 RMS 客户端在保护内容之前检查要与哪个 RMS 服务器或服务通信。 当 RMS 客户端使用受保护的内容时，也可能会发生服务发现，不过，这种情况很少出现，附加到内容的策略包含首选的 RMS 服务器或服务，仅当该策略的执行不成功时，客户端才会运行服务发现。

服务发现首先查找 Rights Management (AD RMS) 的本地版本。 如果此操作不成功，服务发现将自动查找 Rights Management (Azure RMS) 的云版本。

为了对本地部署执行服务发现，RMS 客户端将检查以下各项：

1.  本地计算机上的 Windows 注册表：如果注册表中配置了服务发现设置，则先尝试这些设置。  默认情况下，注册表中不会配置这些设置。

2.  Active Directory 域服务：已加入域的计算机将在 Active Directory 中查询服务连接点 (SCP)。 如果注册了一个 SCP，则会将 RMS 服务器的 URL 返回给 RMS 客户端使用。

### 仅限 AD RMS：使用 Active Directory 启用服务器端服务发现
如果你的帐户具有足够的权限（AD RMS 服务器的企业管理员和本地管理员），则你可以在安装 AD RMS 根群集服务器时自动注册服务连接点 (SCP)。 如果 SCP 已存在于林中，则你必须先删除现有的 SCP，然后才能注册新的 SCP。

你可以在安装 AD RMS 后，使用以下过程注册和删除 SCP。 在开始之前，请确保你的帐户具有所需的权限 （AD RMS 服务器的企业管理员和本地管理员）。

##### 通过在 Active Directory 中注册 SCP 启用 AD RMS 服务发现

1.  在 AD RMS 服务器上打开 Active Directory Management Services 控制台：

    -   如果你使用的是 Windows Server 2008 R2 或 Windows Server 2008，请依次单击“开始”、“管理工具”、“Active Directory Rights Management Services”。

    -   如果你使用的是 Windows Server 2012 R2 或 Windows Server 2012，请在服务器管理器中，依次单击“工具”、“Active Directory Rights Management Services”。

2.  在 AD RMS 控制台中，右键单击 AD RMS 群集，然后单击“属性”。

3.  单击“SCP”选项卡。

4.  选中“更改 SCP”复选框。

5.  选择“将 SCP 设置为当前证书群集”选项，然后单击“确定”。

### 使用 Windows 注册表启用客户端服务发现
使用 SCP 或 SCP 不存在时的替代方法是：配置客户端计算机上的注册表，使 RMS 客户端能够找到其 AD RMS 服务器。

##### 使用 Windows 注册表启用客户端 AD RMS 服务发现

1.  执行 Regedit.exe 打开 Windows 注册表编辑器：

    -   在客户端计算机上的“运行”窗口中，键入 **regedit**，然后按 Enter 打开注册表编辑器。

2.  在注册表编辑器中，导航到 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC**。

    > [!IMPORTANT]
    > 如果你是在 64 位计算机上运行 32 位应用程序，则路径如下：
    > **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC**

3.  若要创建 ServiceLocation 子项，请右键单击“MSIPC”、指向“新建”、单击“项”，然后键入 **ServiceLocation**。

4.  若要创建 EnterpriseCertification 子项，请右键单击“ServiceLocation”、指向“新建”、单击“项”，然后键入 **EnterpriseCertification**。

5.  若要设置企业认证 URL，请在“EnterpriseCertification”子项下双击“(默认值)”值，并在“编辑字符串”对话框出现时，为“值数据”键入 &lt;http or https&gt;://*AD RMS_cluster_name*/_wmcs/Certification，然后单击“确定”。

6.  若要创建 EnterprisePublishing 子项，请右键单击“ServiceLocation”、指向“新建”、单击“项”，然后键入 EnterprisePublishing。

7.  若要设置企业发布 URL，请在“EnterprisePublishing”子项下双击“(默认值)”值，并在“编辑字符串”对话框出现时，为“值数据”键入以下 &lt;http or https&gt;://*AD RMS_cluster_name*/_wmcs/Licensing，然后单击“确定”。

8.  关闭注册表编辑器。

如果 RMS 客户端无法通过查询 Active Directory 找到 SCP 并且注册表中未配置 SCP，则对 AD RMS 的服务发现调用将会失败。

### 重定向授权服务器流量
在某些情况下，你可能需要在服务发现期间重定向流量，例如当两个组织合并后，一个组织中的旧授权服务器已停用，而客户端需要重定向到新的授权服务器。 或者，你要从 AD RMS 迁移到 Azure RMS。 若要启用授权重定向，请使用以下过程。

##### 使用 Windows 注册表启用 AD RMS 授权重定向

1.  执行 Regedit.exe 打开 Windows 注册表编辑器：

    -   在客户端计算机上的“运行”窗口中，键入 **regedit**，然后按 Enter 打开注册表编辑器。

2.  在注册表编辑器中，导航到以下项之一：

    -   对于 x64 平台上的 64 位版本 Office：HKLM\SOFTWARE\Microsoft\MSIPC\Servicelocation

    -   对于 x64 平台上的 32 位版本 Office：HKLM\SOFTWARE\Wow6432Node\Microsoft\MSIPC\Servicelocation

3.  通过右键单击“Servicelocation”、指向“新建”、单击“项”，然后键入 **LicensingRedirection**，创建一个 LicensingRedirection 子项。

4.  若要设置授权重定向，请右键单击“LicensingRedirection”子项、选择“新建”，然后选择“字符串值”。  对于“名称”，请指定以前的服务器授权 URL；对于“值”，请指定新的服务器授权 URL。

    例如，若要将授权从位于 Contoso.com 的服务器重定向到位于 Fabrikam.com 的服务器，你可以输入以下值：

    **名称：**`https://contoso.com/_wmcs/licensing`

    **值：**`https://fabrikam.com/_wmcs/licensing`

    > [!NOTE]
    > 如果旧的授权服务器同时指定了 Intranet URL 和 Extranet URL，则必须在 LicensingRedirection 项下同时为这两个 URL 设置新的名称/值映射。

5.  为所有需要重定向的服务器重复上一步。

6.  关闭注册表编辑器。

