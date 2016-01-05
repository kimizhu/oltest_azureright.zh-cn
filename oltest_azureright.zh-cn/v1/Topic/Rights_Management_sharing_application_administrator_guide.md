---
description: na
keywords: na
pagetitle: Rights Management sharing application administrator guide
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d9992e30-f3d1-48d5-aedc-4e721f7d7c25
---
# 权限管理共享应用程序管理员指南
如果你负责企业网络上的 Microsoft Rights Management 共享应用程序，或者如果你希望获得除了 [权限管理共享应用程序用户指南](../Topic/Rights_Management_sharing_application_user_guide.md)或[适用于 Windows 的 Microsoft Rights Management 共享应用程序常见问题](http://go.microsoft.com/fwlink/?LinkId=303971)以外的更多技术信息，请使用以下信息：

-   [自动部署 Microsoft Rights Management 共享应用程序](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_ScriptedInstall)

    -   [验证安装是否成功](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted)

    -   [卸载命令](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_uninstallscripted)

    -   [禁止自动更新](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_SuppressAutomaticUpdates)

    -   [仅限 Azure RMS：配置文档跟踪](#BKMK_DocumentTracking)

    -   [仅限 AD RMS：在组织中支持多个电子邮件域](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_FederatedDomains)

-   [Microsoft Rights Management 共享应用程序技术概述](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_AdminOverview)

    -   [保护级别 – 本机和常规](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_LevelsofProtection)

    -   [支持的文件类型和文件扩展名](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_SupportFileTypes)

    -   [更改文件的默认保护级别](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_ChangeDefaultProtection)

> [!TIP]
> 如果你是 RMS 共享应用程序的新手，或想要查找更多信息，请参阅 [RMS 如何通过使用 RMS 共享应用保护所有文件类型](https://curah.microsoft.com/191031/how-rms-protects-all-file-types-by-using-the-rms-sharing-app)。

RMS 共享应用程序最适合与 Azure RMS 配合使用，因为这种部署配置支持向另一组织中的用户发送受保护的附件，并提供电子邮件通知、文档跟踪和撤消等选项。  不过，它也能够与本地版本的 AD RMS 配合使用，只是存在一些限制。 有关 Azure RMS 和 AD RMS 支持的功能的全面比较，请参阅[比较 Azure Rights Management 和 AD RMS](https://technet.microsoft.com/library/jj739831.aspx)。 如果你安装了 AD RMS 并想要迁移到 Azure RMS，请参阅[从 AD RMS 迁移到 Azure Rights Management](https://technet.microsoft.com/library/dn858447.aspx)。

## <a name="BKMK_ScriptedInstall"></a>自动部署 Microsoft Rights Management 共享应用程序
Windows 版 RMS 共享应用程序支持脚本化安装，因此适合企业部署。

安装的唯一先决条件是，计算机运行最低版本的 Windows 7 Service Pack 1 且已安装 Microsoft Framework（最低版本为 4.0）。 如果你需要安装 Microsoft.NET Framework 4.0，可以[从 Microsoft 下载中心下载并安装](http://www.microsoft.com/download/details.aspx?id=17718)。

#### 下载要自动部署的 RMS 共享应用程序

1.  在 Microsoft 下载中心转到[适用于 Windows 的 Rights Management 共享应用程序](http://www.microsoft.com/download/details.aspx?id=40857)页，然后单击“下载”。

2.  选择并下载所需的文件。 选择并下载所需文件。有两个客户端安装包：一个适用于 64 位 Windows (Microsoft Rights Management sharing application x64.zip)，另一个适用于 32 位 Windows (Microsoft Rights Management sharing application x86.zip)。

3.  从压缩的安装包中提取文件，例如双击它们。 然后，将提取的文件复制到客户端计算机可以访问的网络位置。

RMS 共享应用程序的安装包支持不同的部署方案，包括以下方案：

|说明|部署方案|
|------|--------|
|Microsoft Online 登录助手|对于以下方案是必需的：<br /><br />-   Office 2010 和 Azure RMS<br />-   Office 2013 和 Azure RMS（如果你尚未安装 [Office 2013 2015 年 6 月 9 日更新](https://support.microsoft.com/kb/3054853) (KB3054853)|
|Office 修补程序 (KB 2596501)|对于以下方案是必需的：<br /><br />-   Office 2010 和 Azure RMS<br />-   Office 2010 和 Active Directory RMS|
|用于启用 AD RMS 客户端 1.0 以与 Azure RMS 配合工作的修补程序 (KB 2843630)|对于以下方案是必需的：<br /><br />-   Office 2010 和 Azure RMS<br />-   Office 2010 和 Active Directory RMS|
|AD RMS 客户端和 RMS 共享应用程序|对于以下方案是必需的：<br /><br />-   Office 2016 或 Office 2013，以及 Azure RMS 或 Active Directory RMS<br />-   Office 2010 和 Azure RMS<br />-   Office 2010 和 Active Directory RMS<br />-   仅 RMS 共享应用程序和 Office 加载项|
|功能区的 Office 加载项|对于以下方案是必需的：<br /><br />-   Office 2016 或 Office 2013，以及 Azure RMS 或 Active Directory RMS<br />-   Office 2010 和 Azure RMS<br />-   Office 2010 和 Active Directory RMS<br />-   仅 RMS 共享应用程序和 Office 加载项|
|Azure Active Directory Rights Management 准备工具|对于以下方案是必需的：<br /><br />-   Office 2010 和 Azure RMS|
使用以下过程来确定为这些部署方案部署 RMS 共享应用程序所需的命令：

-   **Office 2016 或 Office 2013，以及 Azure RMS 或 Active Directory RMS**

    你的用户运行的是 Office 2016 或 Office 2013、你的组织使用的是 Azure RMS 或 Active Directory RMS，并且用户与使用 Azure RMS 或 Active Directory RMS 的其他组织进行协作。

-   **Office 2010 和 Azure RMS**

    你的用户运行的是 Office 2010、你的组织使用的是 Azure RMS，并且用户与使用 Azure RMS 或 Active Directory RMS 的其他组织进行协作。

-   **Office 2010 和 Active Directory RMS**

    你的用户运行的是 Office 2010、你的组织使用的是 AD RMS，并且用户与使用 Azure RMS 的其他组织进行协作。

-   **仅 RMS 共享应用程序和 Office 加载项**

    你的用户运行的是 Office 2016、Office 2013 或 Office 2010、你的组织使用的是 AD RMS，并且用户无需与使用 Azure RMS 的其他组织进行协作。 此安装仅允许你安装共享应用程序和 Office 加载项。

> [!NOTE]
> 在上述方案中，如果你的组织运行的是 AD RMS，则用户可以从使用 Azure RMS 的其他组织接收受保护内容，但他们无法将受保护的内容发送给使用 Azure RMS 的组织中的用户。 但是，如果你的组织运行的是 Azure RMS，则用户可以发送和接收来自其他组织的受保护内容。

若要针对每个步骤完成安装，必须重新启动计算机。 可以使用类似于 shutdown /i 的命令实现自动重新启动。

#### 为 Office 2016 或 Office 2013 和 Azure RMS 或 Active Directory RMS 部署 RMS 共享应用程序

-   在要安装 RMS 共享应用程序及相关组件的每台计算机上，使用提升的权限运行以下命令：

    ```
    setup.exe /s
    ```

若要验证是否成功，请参阅本主题中的[验证安装是否成功](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted)部分。

#### 为 Office 2010 和 Azure RMS 部署 RMS 共享应用程序

1.  你必须是 Office 365 或 Azure Active Directory 租户的全局管理员，才能通过运行 Azure Active Directory Rights Management 准备工具获取组织的证书服务 URL。 在单台计算机上，只需运行此工具一次。 在每台计算机上安装 RMS 共享应用程序时，你将使用证书服务 URL：

    1.  使用本地管理员帐户登录到计算机。

    2.  在该计算机上，[下载并安装 Microsoft Online 登录助手](http://www.microsoft.com/download/details.aspx?id=28177)。

    3.  运行以下命令以查看显示在屏幕上的证书服务 URL，然后可以复制并保存该 URL 以供下一步使用：

        -   对于 64 位 Windows 8.1 和 Windows 8：

            ```
            x64\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        -   对于 32 位 Windows 8.1 和 Windows 8：

            ```
            X86\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        -   对于 64 位 Windows 7：

            ```
            x64\win7\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        > [!NOTE]
        > 此命令可能会提示你输入 Azure 的凭据。 如果计算机未加入域，系统将会提示你加入。 如果计算机已加入域，该工具也许可以使用缓存的凭据。

2.  在要安装 RMS 共享应用程序的每台计算机上，使用提升的权限运行以下命令：

    ```
    setup.exe /s /configureO2010Admin /certificationUrl <certification_url>
    ```

3.  在要安装 RMS 共享应用程序的每台计算机上，用户必须运行以下命令（不需要使用提升的权限）。 可通过不同的方式来实现此目的，包括要求用户运行该命令（例如，在电子邮件中提供一个链接，或者在技术支持门户上提供一个链接），或者在用户的登录脚本中添加该命令：

    ```
    bin\RMSSetup.exe /configureO2010Only
    ```

若要验证是否成功，请参阅本主题中的[验证安装是否成功](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted)部分。

#### 为 Office 2010 和 Active Directory RMS 部署 RMS 共享应用程序

1.  在要安装 RMS 共享应用程序的每台计算机上，使用提升的权限运行以下命令：

    ```
    setup.exe /s /configureO2010Admin
    ```

2.  在要安装 RMS 共享应用程序的每台计算机上，用户必须运行以下命令（不需要使用提升的权限）。 可通过不同的方式来实现此目的，包括要求用户运行该命令（例如，在电子邮件中提供一个链接，或者在技术支持门户上提供一个链接），或者在用户的登录脚本中添加该命令：

    -   对于 64 位 Windows 10、Windows 8.1 和 Windows 8：

        ```
        x64\aadrmprep.exe /configureO2010
        ```

    -   对于 32 位 Windows 10、Windows 8.1 和 Windows 8：

        ```
        X86\aadrmprep.exe /configureO2010
        ```

    -   对于 64 位 Windows 7：

        ```
        x64\win7\aadrmpep.exe /configureO2010
        ```

若要验证是否成功，请参阅本主题中的[验证安装是否成功](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted)部分。

#### 仅安装 RMS 共享应用程序和 Office 加载项

1.  使用以下命令安装 AD RMS 客户端和 RMS 共享应用程序：

    -   对于 64 位 Windows：

        ```
        x64\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "<log file path and name>"
        ```

    -   对于 32 位 Windows：

        ```
        X86\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "<log file path and name>"
        ```

    例如：`\\server5\apps\rms\x64\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "C:\Log files\ipviewerinstall.log"`

2.  使用以下命令安装 Office 加载项：

    -   对于 64 位版本的 Office：

        ```
        msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x64\Setup64.msi" /L*v "<log file path and name>"
        ```

    -   对于 32 位版本的 Office：

        ```
        msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x86\Setup.msi" /L*v "<log file path and name>"
        ```

    例如：`\\server5\apps\rms\msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x64\Setup64.msi" /L*v "C:\Log files\rmsofficeinstall.log"`

若要验证是否成功，请参阅本主题中的[验证安装是否成功](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted)部分。

### <a name="BKMK_verifyscripted"></a>验证安装是否成功
可以使用安装日志文件来验证安装是否成功。

##### 验证是否为 Office 2016 或 Office 2013 和 Azure RMS 或 Active Directory RMS 成功安装 RMS 共享应用程序

-   若要验证 Setup.exe 命令是否成功运行，请在每台计算机上的 *%temp%\RMS_installer_&lt;guid&gt;* 文件夹中搜索安装日志文件 **RMInstaller.log**，然后查看退出代码。

    如果退出代码为 0，则表示安装成功；如果退出代码为其他任何数字，则表示安装失败。

    示例日志文件名：**C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0\RMInstaller.log**

##### 验证是否为 Office 2010 和 Azure RMS 成功安装 RMS 共享应用程序

1.  若要验证 Setup.exe 命令是否成功运行，请在每台计算机上的 *%temp%\RMS_installer_&lt;guid&gt;* 文件夹中搜索安装日志文件 **RMInstaller.log**，然后查看退出代码。

    如果退出代码为 0，则表示安装成功；如果退出代码为其他任何数字，则表示安装失败。

    示例日志文件名：**C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0**

2.  若要验证 RMSSetup.exe 命令是否成功运行，用户应在其 *%localappdata%\microsoft\drm* 文件夹中创建以下文件：

    -   CERT-Machine-2048.drm

    -   CERT-Machine.drm

    -   CLC-&#42;.drm

    -   GIC-&#42;.drm

    CLC-&#42;.drm 文件示例：

    **CLC-alice@isvtenant999.onmicrosoft.com-{1b9cfccf;k5b11;k4a10;kac15;k29b2b6980f4c}.drm**

##### 验证是否为 Office 2010 和 Active Directory RMS 成功安装 RMS 共享应用程序

1.  若要验证 Setup.exe 命令是否成功运行，请在每台计算机上的 *%temp%\RMS_installer_&lt;guid&gt;* 文件夹中搜索安装日志文件，然后查看退出代码。

    如果退出代码为 0，则表示安装成功；如果退出代码为其他任何数字，则表示安装失败。

    示例日志文件名：**C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0**

2.  若要验证 aadrmprep.exe 命令是否成功运行，请在安装日志文件中搜索以下文本：**aadrmprep.exe exited with status SUCCESS**

    > [!NOTE]
    > 有时，此安装可能会运行两次；第一次安装是失败的，第二次安装是成功的。

    如果你想要手动检查此工具所做的注册表更改，更改内容如下：

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\Federation]

        "FederationHomeRealm"="urn:HostedRmsOnlineService:Certification"

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSDRM\Federation]

        "FederationHomeRealm"="urn:HostedRmsOnlineService:Certification"

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSDRM\ServiceLocation\Activation]

        @="&lt;certification url&gt;"

    -   [HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\14.0\Common\DRM]

        DefaultUser="&lt;default_user&gt;"

##### 验证仅安装 RMS 共享应用程序和 Office 加载项是否成功

1.  若要验证 Setup_ipviewer.exe 命令是否成功运行，请在安装日志文件中搜索以下文本：**Installation success or error status:0**

    成功安装时包含的示例行：

    **MSI (s) (F0:B8) [14:19:57:854]:Product:Active Directory Rights Management Services Client 2.1 -- Installation completed successfully.**

    **MSI (s) (F0:B8) [14:19:57:854]:Windows Installer installed the product. Product Name:Active Directory Rights Management Services Client 2.1. Product Version:1.0.1179.1. Product Language:1033. 制造商:Microsoft Corporation. 安装成功或错误状态：0.**

2.  若要验证 Office 加载项是否成功安装，请在每台计算机的安装日志文件中搜索以下文本：**Installation success or error status:0**

    成功安装时包含的示例行：

    **MSI (s) (9C:88) [18:49:04:007]:Product:Microsoft RMS Office Addins -- Installation completed successfully.**

    **MSI (s) (9C:88) [18:49:04:007]:Windows Installer installed the product. Product Name:Microsoft RMS Office Addins. Product Version:1.0.7. Product Language:1033. 制造商:Microsoft. Installation success or error status:0.**

### <a name="BKMK_uninstallscripted"></a>卸载命令
并非这些部署所需的所有安装命令都支持卸载命令。 你可以卸载 AD RMS 客户端和共享应用程序，也可以卸载 Office 加载项。 请使用以下命令卸载这些元素。

##### 卸载 AD RMS 客户端和 RMS 共享应用程序

-   使用以下命令：

    -   对于 64 位 Windows：

        ```
        x64\setup_ipviewer.exe /uninstall /quiet
        ```

    -   对于 32 位 Windows：

        ```
        x86\setup_ipviewer.exe /uninstall /quiet
        ```

##### 卸载 Office 加载项

-   使用以下命令：

    -   对于 64 位版本的 Office：

        ```
        msiexec /x \x64\Setup[64].msi /quiet
        ```

    -   对于 32 位版本的 Office：

        ```
        msiexec /x \x86\Setup.msi /quiet
        ```

### <a name="BKMK_SuppressAutomaticUpdates"></a>禁止自动更新
默认情况下，当出现较新版本的 RMS 共享应用程序时，系统将通知用户并提示他们下载该应用程序。 你可以对注册表进行以下编辑来取消显示此通知：

1.  导航到 **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC**，如果它尚不存在，请创建名为 **RmsSharingApp** 的新注册表项。

2.  选择 **RmsSharingApp**，创建一个新的 DWORD 值 **AllowUpdatePrompt**，并将该值设置为 **0**。

由于 WSUS 不支持 RMS 共享应用程序，你可以先使用以下技术测试所有新版本的 RMS 共享应用程序，然后再将其部署到所有用户：

1.  在所有用户的计算机上，运行一个脚本来禁止自动更新。 在管理员用于测试新版本的计算机上，请不要运行此脚本。

2.  当新版本可用时，管理员将下载它并对其进行测试。

3.  在测试完成且解决了所有问题之后，使用本指南中的自动部署说明将最新版本部署到所有用户。

### <a name="BKMK_DocumentTracking"></a>仅限 Azure RMS：配置文档跟踪
如果的[订阅支持文档跟踪](https://technet.microsoft.com/en-us/dn858608)，则默认情况下，已经为你组织中的所有用户启用了文档跟踪站点。文档跟踪会显示尝试访问用户共享的受保护文档的人员的电子邮件地址、其尝试访问这些文档的时间以及他们所在的位置。如果你的组织出于隐私要求而要禁止显示此类信息，你可以使用 [Disable-AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623032) cmdlet

 来禁用对文档跟踪站点的访问。你随时可以使用 [Enable-AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623037) 来重新启用对该站点的访问，并可以使用 [Get-AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623037).

 来查看当前是已启用还是已禁用这种访问 若要运行这些 cmdlet，你必须安装至少 **2.3.0.0** 版的适用于 Windows PowerShell 的 Azure RMS 模块。有关安装说明，请参阅[安装适用于 Azure Rights Management 的 Windows PowerShell](https://technet.microsoft.com/library/jj585012.aspx)。

> [!TIP]
> 如果你以前下载并安装了该模块，可通过运行以下命令检查版本号：`(Get-Module aadrm –ListAvailable).Version`

以下 URL 用于文档跟踪，你必须允许访问这些 URL（例如，如果你使用具有增强安全性的 Internet Explorer，请将这些 URL 添加到“受信任的站点”）：

-   https://&#42;.azurerms.com

-   https://ecn.dev.virtualearth.net

    > [!NOTE]
    > 此 URL 用于必应地图。

-   https://&#42;.microsoftonline.com

-   https://&#42;.microsoftonline-p.com

### <a name="BKMK_FederatedDomains"></a>仅限 AD RMS：在组织中支持多个电子邮件域
如果你使用 AD RMS 且你所在组织中的用户具有多个电子邮件域（可能由于组织的合并或收购而引起），则必须对注册表进行以下编辑：

1.  导航到 **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC**，如果它尚不存在，请创建名为 **RmsSharingApp** 的新注册表项。

2.  选择 **RmsSharingApp**，创建一个名为 **FederatedDomains** 的新多字符串值，然后添加组织使用的域和所有子域。 不支持使用通配符。

    例如：Coho Vineyard &amp; Winery 公司拥有标准的电子邮件域 **cohovineyardandwinery.com**，但由于合并，它们也使用电子邮件域 **cohowinery.com**、**eastcoast.cohowinery.com** 和 **cohovineyard**。 对于 **FederatedDomains** 值数据，管理员可输入：**cohowinery.com; eastcoast.cohowinery.com; cohovineyard**

如果未对该注册表进行更改，则用户可能无法使用由所在组织中的其他用户所保护的内容。 如果你使用 Azure RMS，则不需要编辑该注册表。

## <a name="BKMK_AdminOverview"></a>Microsoft Rights Management 共享应用程序技术概述
Microsoft Rights Management 共享应用程序是一个可选且可下载的适用于 Microsoft Windows 和其他平台的应用程序，它提供以下功能：

-   单个文件保护、多个文件的批量保护以及对某个选定文件夹内所有文件的保护。

-   完全支持对任意类型文件的保护，并提供一个内置的查看器用于查看常用文本文件和图像文件类型。

-   对不支持 RMS 保护的文件的常规保护。

-   与使用 Office 信息权限管理 (IRM) 保护的文件的完全互操作性。

-   与使用 SharePoint、FCI 和支持的 PDF 创作工具保护的 PDF 文件的完全互操作性。

Microsoft Rights Management 共享应用程序使用新的 [AD RMS 客户端 2.1 运行时](http://www.microsoft.com/download/details.aspx?id=38396)。 通过使用 AD RMS 2.1 的功能，Microsoft Rights Management 共享应用程序为最终用户提供了简单的保护和使用体验。

借助 2013 年 10 月版的 RMS，你可以使用 Office 2010 本机保护文档，还可以将这些文档发送给其他公司的用户，这样他们便可以通过 Azure RMS 使用这些文档。 此外，在此版本中，如果你在加密模式 2 中使用 AD RMS，则可以使用面向个人的 RMS，并可以使用其他公司中使用 Azure RMS 的用户提供的内容。 有关加密模式 2 的详细信息，请参阅 [AD RMS 加密模式](http://technet.microsoft.com/library/hh867439%28v=ws.10%29.aspx)。

### <a name="BKMK_LevelsofProtection"></a>保护级别 – 本机和常规
Microsoft Rights Management 共享应用程序支持两个不同级别的保护，如下表中所述。

|保护类型|本机|泛型|
|--------|------|------|
|说明|对于文本、图像、Microsoft Office（Word、Excel、PowerPoint）文件、.pdf 文件和其他支持 AD RMS 的应用程序文件类型，本机保护提供了同时包括权限的加密和强制执行的强保护级别。|对于其他所有应用程序和文件类型，常规保护提供了一种保护级别，该保护级别既包括使用 .pfile 文件类型的文件封装，又包括用于验证用户是否有权打开该文件的身份验证。|
|保护|对文件进行完全加密，并采用以下方式强制执行保护：<br /><br />-   必须在通过电子邮件接收文件的用户或通过文件被授予访问权限或共享权限的用户成功通过身份验证之后，才能呈现受保护的内容。<br />-   此外，无论是使用 IP 查看器（适用于受保护的文本和图像文件）还是关联的应用程序（适用于其他所有受支持的文件类型）呈现内容，都会完全执行内容所有者在文件处于受保护状态时所设置的使用权限和策略。|通过以下方式强制执行文件保护：<br /><br />-   必须在经授权可打开文件的用户或被授予访问权限的用户成功通过身份验证之后，才能呈现受保护的内容。 如果授权失败，则文件不会打开。<br />-   将显示由内容所有者设置的使用权限和策略，以向授权用户通知预期使用策略。<br />-   将出现授权用户打开和访问文件的审核日志记录，但是，不支持的应用程序不强制执行任何使用权限。|
|文件类型默认值|这是以下文件类型的默认保护级别：<br /><br />-   文本和图像文件<br />-   Microsoft Office（Word、Excel、PowerPoint）文件<br />-   可移植文档格式 (.pdf)<br /><br />有关详细信息，请参阅以下部分：[支持的文件类型和文件扩展名](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_SupportFileTypes)。|这是针对不受完整保护支持的其他所有文件类型（例如 .vsdx、.rtf 等）的默认保护。|
可以更改 RMS 共享应用程序所应用的默认保护级别。 可以将默认级别从本机更改为常规，从常规更改为本机，甚至可以禁止 RMS 共享应用程序应用保护。 有关详细信息，请参阅本主题中的[更改文件的默认保护级别](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_ChangeDefaultProtection)部分。

### <a name="BKMK_SupportFileTypes"></a>支持的文件类型和文件扩展名
下表列出了本身受 Microsoft Rights Management 共享应用程序支持的文件类型。 对于这些文件类型，原始文件扩展名将在应用本机保护时发生变化，并且这些文件将变为只读形式。

此外，当 RMS 共享应用程序通过共享从本机保护受用户保护的 Word、Excel 或 PowerPoint 文件时，此操作将自动创建另一个文件，该文件是与原始文件同名的副本，但其文件扩展名¹为 **.ppdf**。 此版本的文件可确保安装 RMS 共享应用程序的接收方始终可以打开已应用本机保护的文件。

对于以常规形式进行保护的文件，原始文件扩展名将始终更改为 .pfile。

> [!WARNING]
> 如果你拥有可根据文件扩展名检查并采取操作的防火墙、Web 代理或者安全软件，你可能需要重新配置它们以支持这些新的文件扩展名。

|原始文件扩展名|受 RMS 保护的文件扩展名|
|-----------|------------------|
|.txt|.ptxt|
|.xml|.pxml|
|.jpg|.pjpg|
|.jpeg|.ppng|
|.pdf|.ppdf|
|.png|.ppng|
|.tiff|.ptiff|
|.bmp|.pbmp|
|.gif|.pgif|
|.giff|.pgiff|
|.jpe|.pjpe|
|.jfif|.pjfif|
|.jif|.pjif|
|.jt|.pjt|
¹ 由 Foxit 提供技术支持的 PDF Rendering。 Foxit Corporation 版权所有 © 2003–2014。

下表列出了 Microsoft Rights Management 共享应用程序本身在 Microsoft Office 2016、Office 2013 和 Office 2010 中支持的文件类型。 对于这些文件，在文件受 RMS 保护后，文件扩展名仍保持不变。

|Office 支持的文件类型|Office 支持的文件类型|
|------------------|------------------|
|.doc<br /><br />.docm<br /><br />.docx<br /><br />.dot<br /><br />.dotm<br /><br />.dotx<br /><br />.potm<br /><br />.potx<br /><br />.pps<br /><br />.ppsm<br /><br />.ppsx<br /><br />.ppt<br /><br />.pptm|.pptx<br /><br />.thmx<br /><br />.xla<br /><br />.xlam<br /><br />.xls<br /><br />.xlsb<br /><br />.xlt<br /><br />.xlsm<br /><br />.xlsx<br /><br />.xltm<br /><br />.xltx<br /><br />.xps|

### <a name="BKMK_ChangeDefaultProtection"></a>更改文件的默认保护级别
你可以通过编辑注册表来更改 RMS 共享应用程序保护文件的方式。 例如，你可以强制使支持本机保护的文件由 RMS 共享应用程序进行常规保护。

可能要执行此操作的原因是：

-   为了确保所有用户都能从其移动设备打开该文件。

-   为了确保所有用户都可以在没有支持本机保护的应用程序的情况下打开该文件。

-   为了适应根据文件扩展名对文件采取操作的安全系统，可将其重新配置为适应 .pfile 文件扩展名，但无法将其重新配置为适应已应用本机保护的多个文件扩展名。

同样，你也可以强制使 RMS 共享应用程序将本机保护应用到默认已应用常规保护的文件。 这在你具有支持 RMS API 的应用程序（例如，由内部开发人员编写的业务线应用程序或从独立软件供应商 (ISV) 处购买的应用程序）时可能正合适。

也可以强制使 RMS 共享应用程序阻止文件保护（而不是应用本机保护或常规保护）。 例如，如果你具有一个必须能够打开特定文件才能处理其内容的自动应用程序或服务，这可能是必需的。 当你阻止保护某一文件类型时，用户无法使用 RMS 共享应用程序保护具有该文件类型的文件。 他们将在尝试保护此类文件时看到一条消息，提示管理员已阻止保护，并且他们必须取消保护该文件的操作。

若要将 RMS 共享应用程序配置为将常规保护应用于默认已应用本机保护的所有文件，请对注册表进行以下编辑：

1.  **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection**：创建一个名为 **&#42;** 的新项。

    此设置表示文件可具有任意文件扩展名。

2.  在新添加的项 **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\&#42;** 中，创建一个名为 **Encryption**、数据值为 **Pfile** 的新字符串值 (REG_SZ)。

    此设置会导致 RMS 共享应用程序应用常规保护。

这两个设置会导致 RMS 共享应用程序将常规保护应用于具有某一文件扩展名的所有文件。 如果这是你的目标，则无需进行任何进一步的配置。 但是，你可以为特定文件类型定义例外，以便它们仍受本机保护。 为此，你必须针对每个文件类型对注册表执行三个额外的编辑操作：

1.  **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection**：添加一个具有该文件扩展名的新项（不带前面的句点）。

    例如，对于文件扩展名为 .docx 的文件，创建一个名为 **DOCX** 的项。

2.  在新添加的文件类型项（例如 **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\DOCX**）中，创建一个名为 **AllowPFILEEncryption**、值为 **0** 的新 DWORD 值。

3.  在新添加的文件类型项（例如 **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\DOCX**）中，创建一个名为 **Encryption**、值为 **Native** 的新 DWORD 值。

应用这些设置后，所有文件均受常规保护，但文件扩展名为 .docx 的文件除外，因为它们本身受 RMS 共享应用程序保护。

对于要将其定义为例外的其他文件类型重复这三个步骤，因为它们支持本机保护，而你不希望它们由 RMS 共享应用程序进行常规保护。

通过更改支持以下值的 **Encryption** 字符串的值，你可以在其他情况下进行类似的注册表编辑：

-   **Pfile**:一般性保护

-   **Native**：本机保护

-   **Off**：阻止保护

## 请参阅
[权限管理共享应用程序用户指南](../Topic/Rights_Management_sharing_application_user_guide.md)

