---
description: na
keywords: na
pagetitle: Operations for Your Azure Rights Management Tenant Key
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1284d0ee-0a72-45ba-a64c-3dcb25846c3d
---
# 你的 Azure 权限管理租户密钥的操作
实现 Microsoft Azure Rights Management (Azure RMS) 租户密钥之后，你可对该密钥进行不同级别的控制并承担相应责任，具体取决于你的租户密钥拓扑（由 Microsoft 管理或由客户管理）。

这种自行管理租户密钥的方式通常称为“自带密钥”(BYOK)。 有关此方案以及如何在两种租户密钥拓扑之间进行选择的详细信息，请参阅[计划和实现你的 Azure 权限管理租户密钥](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md)。

下表介绍了你可以执行的操作，具体取决于你为 Azure RMS 租户密钥选择的拓扑。

|生命周期操作|由 Microsoft 管理（默认）|由客户管理 (BYOK)|
|----------|----------------------|----------------|
|撤消你的租户密钥|否（自动）|否（自动）|
|更新你的租户密钥|是|是|
|备份和恢复你的租户密钥|否|是|
|导出你的租户密钥|是|否|
|对违规行为做出响应|是|是|
在你确定实现了哪一种拓扑之后，请阅读以下某个部分，获取有关 Azure RMS 租户密钥的这些操作的详细信息。

## <a name="BKMK_MSManagedOperations"></a>由 Microsoft 管理：租户密钥生命周期操作
如果由 Microsoft 管理你的 Azure 权限管理租户密钥（默认），请阅读以下部分，获取有关此拓扑的相关生命周期操作的详细信息：

-   [Revoke your tenant key](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSRevoke)

-   [Re-key your tenant key](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSRekey)

-   [Backup and recover your tenant key](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSBackup)

-   [Export your tenant key](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSExport)

-   [Respond to a breach](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSBreach)

### <a name="BKMK_MSRevoke"></a>撤消你的租户密钥
当你取消订阅 Azure RMS 时，Azure RMS 将停止使用你的租户密钥，无需你执行任何操作。

### <a name="BKMK_MSRekey"></a>更新你的租户密钥
更新密钥也称为滚动密钥。 不要更新你的租户密钥，除非在真正必要的情况下。 旧版客户端（例如 Office 2010）无法适当处理密钥更改。 在这种情况下，你必须通过使用组策略或同等机制，清除计算机上的 RMS 状态。 但是，某些法律事件可能迫使你更新租户密钥。 例如：

-   你的公司拆分为两家或更多公司。 当你更新你的租户密钥时，新公司将无法访问你的员工发布的新内容。 如果有旧租户密钥的副本，他们可以访问旧内容。

-   你认为租户密钥的主副本（你掌握的副本）已泄漏。

你可以通过呼叫 Microsoft 客户支持服务部门 (CSS) 并证明你是租户管理员来更新你的租户密钥。

当你更新租户密钥时，新内容将使用新租户密钥来保护。 这个过程是分阶段进行的，因此在一段时间内，有些新内容仍将使用旧租户密钥来保护。 以前受到保护的内容仍将使用旧租户密钥来保护。 为了支持此种方案，Azure RMS 保留你的旧密钥，使得它能够发布旧内容的许可证。

### <a name="BKMK_MSBackup"></a>备份和恢复你的租户密钥
Microsoft 负责备份你的租户密钥，无需你进行任何操作。

### <a name="BKMK_MSExport"></a>导出你的租户密钥
你可以按照以下三个步骤的说明，导出 Azure RMS 配置和租户密钥：

##### 步骤 1：启动导出

-   若要执行此操作，请联系 Microsoft 客户服务支持 (CSS)。 你必须证明自己是 Azure RMS 租户管理员。

##### 步骤 2：等待验证

-   Microsoft 将验证你请求发放你的 RMS 租户密钥是否合法。 此过程最多可能需要 3 周时间。

##### 步骤 3：接收来自 CSS 的密钥说明

-   Microsoftp 客户支持服务 (CSS) 将你的 Azure RMS 配置和租户密钥发送给你，在一个文件扩展名为 .tpd 的受密码保护文件中加密。 执行此操作时，CSS 首先通过电子邮件向你（即启动导出的人员）发送一个工具。 你必须从命令提示符处运行该工具，如下所示：

    ```
    AadrmTpd.exe -createkey
    ```
    这样可以生成 RSA 密钥对，并将公有部分和私有部分保存为当前文件夹中的文件。 例如：**PublicKey-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt** 和 **PrivateKey-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt**。

    回复来自 CSS 的电子邮件，附加名称以 **PublicKey** 开头的文件。 CSS 随后将向你发送一个作为 .xml 文件的 TPD 文件，该文件使用你的 RSA 密钥进行加密。 将此文件复制到与你最初运行 AadrmTpd 工具时的相同文件夹，并使用以 **PrivateKey** 开头的文件和 CSS 中的文件重新运行该工具。 例如：

    ```
    AadrmTpd.exe -key PrivateKey-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt -target TPD-77172C7B-8E21-48B7-9854-7A4CEAC474D0.xml
    ```
    此命令的输出应该是两个文件：一个文件包含受密码保护的 TPD 的明文密码，另一个文件则是受密码保护的 TPD 本身。 为了进行交叉引用，两个文件都应具有与运行 AadrmTpd.exe -createkey 时的公钥和私钥文件相同的 GUID：

    -   Password-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt

    -   ExportedTPD-FA29D0FE-5049-4C8E-931B-96C6152B0441.xml

    备份这些文件并将其安全存储，以确保你能够继续解密使用此租户密钥保护的内容。 此外，如果你要迁移到 AD RMS，可将此 TPD 文件（以 **ExportedTDP** 开头的文件）导入到 AD RMS 服务器。

##### 步骤 4：日常：保护你的租户密钥。

-   在收到你的租户密钥后，对其进行良好的保护，因为如果有人得到了它，他们将可以解密由该密钥保护的所有文档。

    如果你导出租户密钥的原因是不想再使用 Azure RMS，则最好的做法是马上禁用你的 RMS 租户。 不要拖延到收到租户密钥后再做此事，因为此预防措施可以帮助你将不该得到你的租户密钥的人得到它后导致的后果降至最低。 有关说明，请参阅[解除 Azure Rights Management 授权和停用 Azure Rights Management](../Topic/Decommissioning_and_Deactivating_Azure_Rights_Management.md)。

### <a name="BKMK_MSBreach"></a>对违规行为做出响应
如果没有违规响应流程，无论如何强大的安全系统都是不完整的。 你的租户密钥可能泄漏或失窃。 即便它得到了很好的保护，在当前这代的 HSM 技术或当前的密钥长度和算法方面也可以找到一些漏洞。

Microsoft 拥有一个专业团队，负责响应其产品和服务中的安全事件。 当收到某个事件的可信报告时，该团队将参与调查事件的范围、根本原因和缓解办法。 如果该事件影响到你的资产，则 Microsoft 将使用你在订阅时提供的地址，通过电子邮件通知你的 Azure RMS 租户管理员。

如果你发现了安全违规行为，则你或 Microsoft 能够采取的最佳行动取决于安全违规的范围；Microsoft 将与你共同完成这个过程。 下表显示了一些典型情况以及可能的响应，但具体的响应要取决于在调查过程中揭示的所有信息。

|事件描述|可能的响应|
|--------|---------|
|你的租户密钥泄露。|更新你的租户密钥。 参阅本主题中的[Re-key your tenant key](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSRekey)部分。|
|未经授权的个人或恶意软件获取了使用你的租户密钥的权限，但密钥本身并未泄露。|更新你的租户密钥在这种情况下并不奏效，需要进行根源分析。 如果进程或软件 Bug 是导致未经授权的个人获得访问权限的原因，则必须解决这一问题。|
|在 RSA 算法、密钥长度或暴力攻击方面发现的漏洞可能被利用。|Microsoft 必须更新 Azure RMS，以支持新的算法和具有弹性的更长密钥长度，并指示所有客户更新他们的租户密钥。|

## <a name="BKMK_BYOKManagedOperations"></a>由客户管理：租户密钥生命周期操作
如果由你自行管理 Azure 权限管理租户密钥（自带密钥方案，简称 BYOK 方案），请阅读以下部分，获取有关此拓扑的相关生命周期操作的详细信息：

-   [Revoke your tenant key](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKRevoke)

-   [Re-key your tenant key](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKRekey)

-   [Backup and recover your tenant key](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKBackup)

-   [Export your tenant key](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKExport)

-   [Respond to a breach](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKBreach)

### <a name="BKMK_BYOKRevoke"></a>撤消你的租户密钥
当你取消订阅 Azure RMS 时，Azure RMS 将停止使用你的租户密钥，无需你执行任何操作。

### <a name="BKMK_BYOKRekey"></a>更新你的租户密钥
更新密钥也称为滚动密钥。 不要更新你的租户密钥，除非在真正必要的情况下。 旧版客户端（例如 Office 2010）无法适当处理密钥更改。 在这种情况下，你必须通过使用组策略或同等机制，清除计算机上的 RMS 状态。 但是，某些法律事件可能迫使你更新租户密钥。 例如：

-   你的公司拆分为两家或更多公司。 当你更新你的租户密钥时，新公司将无法访问你的员工发布的新内容。 如果有旧租户密钥的副本，他们可以访问旧内容。

-   你认为租户密钥的主副本（你掌握的副本）已泄漏。

当你更新租户密钥时，新内容将使用新租户密钥来保护。 这个过程是分阶段进行的，因此在一段时间内，有些新内容仍将使用旧租户密钥来保护。 以前受到保护的内容仍将使用旧租户密钥来保护。 为了支持此种方案，Azure RMS 保留你的旧密钥，使得它能够发布旧内容的许可证。

若要更新你的租户密钥，可使用[Implementing bring your own key (BYOK)](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_ImplementBYOK)主题的[计划和实现你的 Azure 权限管理租户密钥](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md)一节中的过程通过 Internet 生成并创建一个新密钥，也可以亲自前往 Microsoft 的相关部门。

### <a name="BKMK_BYOKBackup"></a>备份和恢复你的租户密钥
你负责备份自己的租户密钥。 如果你在 Thales HSM 中生成租户密钥，若要备份该密钥，只需备份标记化密钥文件、安全体系文件和管理员卡即可。

如果你按照[Implementing bring your own key (BYOK)](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_ImplementBYOK)主题的[计划和实现你的 Azure 权限管理租户密钥](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md)部分中的程序传输密钥，则 Azure RMS 将保留标记化密钥文件，以防任何 Azure RMS 节点出现故障。 但是，不要将它作为完全备份。 例如，如果你需要密钥的明文副本在 Thales HSM 外部使用，则 Azure RMS 将无法为你检索该副本，因为它仅有不可恢复的副本。

### <a name="BKMK_BYOKExport"></a>导出你的租户密钥
如果使用自带密钥，则你无法从 Azure RMS 导出租户密钥。 Azure RMS 中的副本是不可恢复的。 如果你想要删除此密钥以使其不再可用，请与 Microsoft 客户服务支持 (CSS) 联系。

### <a name="BKMK_BYOKBreach"></a>对违规行为做出响应
如果没有违规响应流程，无论如何强大的安全系统都是不完整的。 你的租户密钥可能泄漏或失窃。 即便它得到了很好的保护，在当前这代的 HSM 技术或当前的密钥长度和算法方面也可以找到一些漏洞。

Microsoft 拥有一个专业团队，负责响应其产品和服务中的安全事件。 当收到某个事件的可信报告时，该团队将参与调查事件的范围、根本原因和缓解办法。 如果该事件影响到你的资产，则 Microsoft 将使用你在订阅时提供的地址，通过电子邮件通知你的 Azure RMS 租户管理员。

如果你发现了安全违规行为，你或 Microsoft 能够采取的最佳行动取决于安全违规的范围；Microsoft 将与你共同完成这个过程。 下表显示了一些典型情况以及可能的响应，但具体的响应要取决于在调查过程中揭示的所有信息。

|事件描述|可能的响应|
|--------|---------|
|你的租户密钥泄露。|更新你的租户密钥。 参阅本主题中的[Re-key your tenant key](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKRekey)部分。|
|未经授权的个人或恶意软件获取了使用你的租户密钥的权限，但密钥本身并未泄露。|更新你的租户密钥在这种情况下并不奏效，需要进行根源分析。 如果进程或软件 Bug 是导致未经授权的个人获得访问权限的原因，则必须解决这一问题。|
|在当前这代 HSM 技术中发现的漏洞。|Microsoft 必须更新 HSM。 如果有理由认为这些漏洞泄露了密钥，则 Microsoft 将指示所有客户更新他们的租户密钥。|
|在 RSA 算法、密钥长度或暴力攻击方面发现的漏洞可能被利用。|Microsoft 必须更新 Azure RMS，以支持新的算法和具有弹性的更长密钥长度，并指示所有客户更新他们的租户密钥。|

## 请参阅
[使用 Azure 权限管理](../Topic/Using_Azure_Rights_Management.md)

