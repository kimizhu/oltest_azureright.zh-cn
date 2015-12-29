---
description: na
keywords: na
pagetitle: 为 Azure Rights Management 和发现服务或数据恢复配置超级用户
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: acb4c00b-d3a9-4d74-94fe-91eeb481f7e3
---
# 为 Azure Rights Management 和发现服务或数据恢复配置超级用户
Microsoft [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] (Azure RMS) 的超级用户功能确保已获授权的用户与服务始终可以阅读和检查 Azure RMS 为你的组织保护的数据。 如有需要，超级用户可以删除保护，或者更改以前应用的保护。 超级用户始终对组织的 RMS 租户授予的所有使用许可证拥有完整所有者权限。 这种功能有时称为“数据推理”，是保持对组织数据进行控制的关键所在。 例如，对于以下任何情况，你可以使用此功能：

-   某位员工离职，你需要阅读其保护的文件。

-   IT 管理员需要删除当前针对文件配置的保护策略，并应用新的保护策略。

-   Exchange Server 需要为邮箱编制索引以执行搜索操作。

-   数据丢失防护 (DLP) 解决方案、内容加密网关 (CEG) 和反恶意软件产品的现有 IT 服务需要检查已受保护的文件。

-   出于审核、法律或其他合规性原因，你需要批量解密文件。

默认情况下，超级用户功能未启用，并且没有向任何用户分配此角色。 如果你为 Exchange 配置了 Rights Management 连接器，则会自动启用超级用户功能，对于运行 Exchange Online、SharePoint Online 或 SharePoint Server 的标准服务，不需要该功能。

如果需要手动启用超级用户功能，请使用 Windows PowerShell cmdlet [Enable-AadrmSuperUserFeature](https://msdn.microsoft.com/library/azure/dn629400.aspx)，然后根据需要使用 [Add-AadrmSuperUser](https://msdn.microsoft.com/library/azure/dn629411.aspx) cmdlet 分配用户（或服务帐户）。 可以为组织配置一个或多个超级用户，但必须添加个人用户；不支持组。

> [!NOTE]
> 如果你尚未安装适用于 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]的 Windows PowerShell 模块，请参阅[安装适用于 Azure 权限管理的 Windows PowerShell](../Topic/Installing_Windows_PowerShell_for_Azure_Rights_Management.md)。

超级用户功能的最佳安全做法：

-   使用 [Add-AadrmRoleBasedAdministrator](https://msdn.microsoft.com/library/azure/dn629417.aspx) cmdlet 限制和监视分配为 Office 365 或 Azure RMS 租户全局管理员或获得了 GlobalAdministrator 角色的管理员。 这些用户可以启用超级用户功能并将用户（包括其自己）分配为超级用户，并且可能解密组织保护的所有文件。

-   若要查看已将哪些用户和服务帐户分配为超级用户，请使用 [Get-AadrmSuperUser cmdlet](https://msdn.microsoft.com/library/azure/dn629408.aspx)。  与所有管理操作一样，对于启用或禁用超级功能，以及添加或删除超级用户操作，将会加以记录，并且可使用 [Get-AadrmAdminLog](https://msdn.microsoft.com/library/azure/dn629430.aspx) 进行审核。 超级用户解密文件时，会记录此操作，并且可使用[使用情况日志记录](https://technet.microsoft.com/library/dn529121.aspx)进行审核。

-   如果你不需要日常服务的超级用户功能，仅在需要时启用该功能，并使用 [Disable-AadrmSuperUserFeature](https://msdn.microsoft.com/library/azure/dn629428.aspx) cmdlet 再次禁用。

下面的日志提取中显示使用 Get-AadrmAdminLog cmdlet 的一些示例条目。 在此示例中，Contoso Ltd 的管理员确认超级用户功能禁用用、将 Richard Simone 添加为超级用户、检查是否将 Richard 配置为 Azure RMS 唯一的超级用户，然后启用超级用户功能，以便 Richard 现在可以解密现在已离开公司的员工保护的某些文件。

`2015-08-01T18:58:20	admin@contoso.com	GetSuperUserFeatureState	Passed	Disabled`
`2015-08-01T18:59:44	admin@contoso.com	AddSuperUser -id rsimone@contoso.com	Passed	True`
`2015-08-01T19:00:51	admin@contoso.com	GetSuperUser	Passed	rsimone@contoso.com`
`2015-08-01T19:01:45	admin@contoso.com	SetSuperUserFeatureState -state Enabled	Passed	True`

## <a name="BKMK_RMSProtectionModule"></a>超级用户的脚本选项
分配为 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 超级用户的某人将需要删除对位于多个位置的多个文件的保护。 尽管可以手动执行此操作，但使用脚本会提高效率（并且通常更可靠）。 为此，请[下载 RMS 保护工具](http://www.microsoft.com/en-us/download/details.aspx?id=47256)。 然后，根据需要使用 [Unprotect-RMSFile](https://msdn.microsoft.com/library/azure/mt433200.aspx) cmdlet 和 [Protect-RMSFile](https://msdn.microsoft.com/library/azure/mt433201.aspx) cmdlet。

> [!IMPORTANT]
> 尽管 RMS 保护工具专为超级用户批量取消保护文件以进行恢复而设计，但该工具的当前版本不支持 Azure RMS 用户身份验证。 在解决此限制之前，必须先使用服务主体帐户向 Azure RMS 进行身份验证，然后才可删除对文件的保护。  有关更多信息和说明，请参阅 [about_RMSProtection_AzureRMS](https://msdn.microsoft.com/library/azure/mt433202.aspx)。

有关使用这些 cmdlet 的详细信息，请参阅 [RMS 保护 Cmdlet](https://msdn.microsoft.com/library/azure/mt433195.aspx)。

> [!NOTE]
> RMS 保护工具随附的 RMSProtection Windows PowerShell 模块不同于主要的[适用于 Azure Rights Management 的 Windows PowerShell 模块](https://technet.microsoft.com/library/jj585027.aspx)，前者为后者做了补充。 它支持 Azure RMS 和 AD RMS。

## 请参阅
[配置 Azure 权限管理](../Topic/Configuring_Azure_Rights_Management.md)

