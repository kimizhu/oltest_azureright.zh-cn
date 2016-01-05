---
description: na
keywords: na
pagetitle: Logging and Analyzing Azure Rights Management Usage
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a735f3f7-6eb2-4901-9084-8c3cd3a9087e
---
# 记录和分析 Azure 权限管理使用情况
使用本主题中的信息可以帮助你了解如何使用 Azure Rights Management (Azure RMS) 的使用日志记录功能。 Azure Rights Management 服务能够记录它为你组织发出的所有请求，包括来自用户的请求、你组织中的 Rights Management 管理员执行的操作、Microsoft 操作人员为了支持你的 Azure Rights Management 部署执行的操作。

然后，你可以使用这些 Azure Rights Management 日志来支持以下业务方案：

-   分析信息以获得业务见解。

    Azure Rights Management 采用 W3C 扩展日志格式，将日志写入你提供的 Azure 存储帐户。 然后，你可将这些日志发送到你选择的存储库（例如数据库、联机分析处理 (OLAP) 系统或 map-reduce 系统），以便分析信息并生成报告。 例如，你可以看出谁在访问你的 RMS 保护数据。 你还可以确定用户访问了哪些 RMS 保护数据、从哪些设备访问、从何处访问。 你可以了解用户是否能够成功读取受保护内容。 你还可以看出哪些用户阅读了某个受保护的重要文档。

-   监控滥用行为。

    你可以近乎实时地访问 Azure Rights Management 日志记录信息，从而持续监控你公司使用 Rights Management 的情况。 99.9% 的日志可在 RMS 启动操作后 15 分钟之内访问。

    例如，如果在正常工作时间之外读取 RMS 保护数据的用户迅猛增加，可能意味着恶意用户正在收集信息并企图售卖给你的竞争对手，你希望在出现这种情况时收到警报。 或者，如果同一用户在很短时间内显然是从两个不同 IP 地址访问数据，则可能意味着该用户帐户已泄漏。

-   执行取证分析。

    如果遇到信息泄露，安全人员很可能向你询问最近谁访问了特定文档，以及可疑人员最近访问了哪些信息。 当你使用 Azure Rights Management 和日志记录时，你就能够回答这些类型的问题，因为使用受保护内容的用户始终必须获取 Rights Management 许可证才能打开受 Azure Rights Management 保护的文档和图片，即便这些文件已移动（通过电子邮件）或复制到 U 盘或其他存储设备也是如此。 这意味着在通过 Azure Rights Management 保护数据时，你能够使用 Azure Rights Management 日志作为确定性信息源进行取证分析。

> [!NOTE]
> 如果你只希望记录 Azure Rights Management 的管理任务，而不希望跟踪用户如何使用 Rights Management，则可使用适用于 Azure Rights Management 的 [Get-AadrmAdminLog](https://msdn.microsoft.com/library/azure/dn629430.aspx) Windows PowerShell cmdlet。
> 
> 你还可以使用 Azure 经典门户获取高级使用情况报告，包括“RMS 使用情况”、“最活跃的 RMS 用户”、“RMS 设备使用情况”和“已启用 RMS 的应用程序使用情况”。 若要从 Azure 经典门户访问这些报告，请单击“Active Directory”，选择并打开一个目录，然后单击“报告”。

有关 Azure Rights Management 使用日志记录的详细信息，请参阅以下部分。

-   [如何启用 Azure Rights Management 使用日志记录](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_EnableRMSLogging)

-   [如何访问和使用 Azure Rights Management 使用日志](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_AccesAndUseLogs)

-   [如何管理 Azure Rights Management 日志存储](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_ManageStorage)

-   [如何委托对 Azure Rights Management 使用日志的访问权限](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_Delegate)

-   [如何解释 Azure Rights Management 使用日志](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_Interpret)

-   [Windows PowerShell 参考](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_PowerShell)

## <a name="BKMK_EnableRMSLogging"></a>如何启用 Azure Rights Management 使用日志记录
Azure Rights Management 使用日志记录是可选的，因此如果你希望使用该功能，则必须执行特定步骤。 当你使用 Azure Rights Management 使用日志记录时，Rights Management 的工作方式没有变化，日志记录流程本身是免费的。 但是，你必须提供用于日志的 Azure 存储帐户，此存储服务收取费用。

开始之前，请确保你符合使用 Azure Rights Management 使用日志记录的以下先决条件：

|要求|更多信息|
|------|--------|
|包含 Azure Rights Management 的由 IT 人员管理的订阅|你必须拥有由你组织管理的 Microsoft Azure Rights Management 订阅。 使用个人 RMS 的组织不能使用 Azure Rights Management 使用日志记录。<br /><br />如果你组织有用户使用个人 RMS，则 Azure Rights Management 使用日志记录提供了一个非常具有说服力的业务理由，促使你组织将个人 RMS 转换为 Microsoft Azure Rights Management 订阅。<br /><br />有关包含 Azure RMS 的订阅的详细信息，请参阅 [Azure 权限管理要求](../Topic/Requirements_for_Azure_Rights_Management.md)主题中的[支持 Azure RMS 的云订阅](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions)部分。<br /><br />有关个人 RMS 的详细信息，请参阅[个人 RMS 和 Azure 权限管理](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md)|
|Azure 订阅|你必须具有 Azure 订阅，还需要在 Azure 上具有足够的存储空间，用于存储 Azure Rights Management 日志。|
|适用于 Azure Rights Management 的 Windows PowerShell|如果你尚未这样做，请下载并安装适用于 Azure Rights Management 的 Windows PowerShell 模块。 你将使用 Windows PowerShell cmdlet 来配置和管理 Azure Rights Management 使用日志。<br /><br />有关详细信息，请参阅[安装适用于 Azure 权限管理的 Windows PowerShell](../Topic/Installing_Windows_PowerShell_for_Azure_Rights_Management.md)。|
使用以下过程可以启用 Azure Rights Management 使用日志记录，此过程包括创建 Azure 存储帐户，并将 Azure 配置为使用此存储帐户来存储 Rights Management 日志。

> [!NOTE]
> 此过程假定你有 Azure 帐户。 Azure Rights Management 使用日志记录支持个人帐户，但最好使用工作或学校帐户。 此外，我们建议你为 Rights Management 日志创建一个专用存储帐户。 你必须与 Azure Rights Management 共享存储访问密钥，如果其他人也希望使用日志文件，你可能还需要与他们共享。
> 
> 有关 Azure 存储空间的详细信息，请参阅 [Azure 存储空间文档](http://azure.microsoft.com/documentation/services/storage/)。

#### 如何创建存储帐户并启用 Azure Rights Management 使用日志记录

1.  登录到 [Azure 门户](https://portal.azure.com/)。

2.  在“中心”菜单上，选择“新建”-&gt;“数据 + 存储”-&gt;“存储帐户”。

    > [!TIP]
    > 如果看不到此选项，请检查除了 Rights Management 的订阅以外，你是否还拥有 Azure 订阅。

3.  保留默认部署模型（即**经典**），然后单击“创建”。

    指定存储帐户的名称，如有必要，更改**定价层**、**资源组**、**订阅**的所选选项，以及是否要**固定到仪表板**。 然后单击“创建”。 等待“创建存储帐户”活动完成。

4.  单击新创建的存储帐户，然后单击“设置”。

5.  在“设置”边栏选项卡中，请单击“密钥”图标。

6.  在“管理密钥”边栏选项卡中，复制**主访问密钥**的值，然后关闭边栏选项卡。

7.  使用“以管理员身份运行”选项启动 Windows PowerShell。 运行 [Connect-AadrmService](https://msdn.microsoft.com/library/azure/dn629415.aspx) 命令以连接到 Azure Rights Management 服务：

    ```
    Connect-AadrmService
    ```

8.  使用 [Set-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629426.aspx) 命令指定需要存储 Azure Rights Management 使用日志的位置，将 *&lt;Access_Key&gt;* 替换为你在步骤 6 中复制的主访问密钥，并将 *&lt;StorageAccount&gt;* 替换为你在步骤 3 中创建的存储帐户的名称：

    ```
    $accesskey = convertto-securestring -asplaintext -force –string <Access_Key> Set-AadrmUsageLogStorageAccount -AccessKey $accesskey -StorageAccount <StorageAccount>
    ```

9. 使用 [Enable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629421.aspx) 命令启用 Azure Rights Management 使用日志记录：

    ```
    Enable-AadrmUsageLogFeature
    ```
    你应该看到以下消息：**为权限管理服务启用了使用日志记录功能。**

现在，使用日志记录功能已启用，Azure Rights Management 开始记录你组织的所有操作，并将这些信息保存到你的存储帐户。 日志记录信息在此之前不可用。

有关如何创建存储帐户的详细信息，请参阅 Azure 文档的[关于 Azure 存储帐户](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/)中的[创建存储帐户](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/)部分。

## <a name="BKMK_AccesAndUseLogs"></a>如何访问和使用 Azure Rights Management 使用日志
Azure Rights Management 将日志作为一系列 Blob 写入你的 Azure 存储帐户。 每个 Blob 包含一条或多条日志记录，采用 W3C 扩展日志格式。 Blob 名称为数字，按创建顺序排列。 本文档后面的[如何解释 Azure Rights Management 使用日志](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_Interpret)部分包含了有关日志内容及其创建情况的更多信息。

在 Azure Rights Management 操作之后，日志需要一段时间才能显示在你的存储帐户中。 大多数日志在 15 分钟之内显示。

你为 Azure Rights Management 使用日志创建的存储帐户类似于邮箱，支持从存储帐户直接读取，但这并非最佳使用方式。 相反，为了达到最佳性能并帮助降低成本，我们建议你将日志下载到本地存储，例如本地文件夹、数据库或 map-reduce 存储库。

你可通过两种方式下载使用日志：

-   使用 Windows PowerShell cmdlet [Get-AadrmUsageLog](https://msdn.microsoft.com/library/azure/dn629401.aspx)。

    这是访问使用日志的最简单方式。 此 cmdlet 可将日志下载到你的计算机，将每个 Blob 作为文件下载到你指定的位置。

-   使用 [Azure 存储空间 SDK](http://www.windowsazure.com/en-us/develop/net/) 编写你自己的自定义应用程序以下载日志。

    自定义应用程序能够提供比 Get-AadrmUsageLogs cmdlet 更高的灵活性。 例如，你可能希望将日志下载操作委托给其他人或不能使用 Azure Rights Management 管理凭据的进程。 你也可能希望实时轮询日志，因为你要监控滥用情况。

#### 使用 PowerShell 下载使用日志

-   使用“以管理员身份运行”选项启动 Windows PowerShell，然后运行 **Get-AadrmUsageLog –Path &lt;location&gt;**。 例如，在 E 盘上创建名为 **logs** 的文件夹之后：

    -   将所有可用日志下载到 E:\logs 文件夹：`Get-AadrmUsageLog -Path "e:\logs"`

    -   下载特定范围的 Blob：`Get-AadrmUsageLog –Path "e:\logs" –FromCounter 1024 –ToCounter 2047`

当你运行这些 cmdlet 时，Windows PowerShell 会显示下载的上一个 Blob 的名称。 你可将此名称分配给变量，让你能够在循环或计划作业中运行 Get-AadrmUsageLog，每次仅下载新增日志。

例如：

**PS C:\&gt; $LastBlobName = Get-AadrmUsageLog –Path "e:\logs"**

**1527**

**PS C:\&gt; $LastBlobName**

**1527**

> [!TIP]
> 你可以使用 [Microsoft 的 Log Parser](http://www.microsoft.com/download/details.aspx?id=24659)（一种在各种常见日志格式之间进行转换的工具），将所有已下载日志文件整合为 CSV 格式。 你还能够使用该工具将数据转换为 SYSLOG 格式，或者将其导入到数据库。 安装该工具之后，请运行 **LogParser.exe /?** 以获得此工具的使用帮助和信息。 例如，你可以运行以下命令，将所有信息导出为 .log 文件格式：**logparser –i:w3c –o:csv “SELECT &#42; INTO AllLogs.csv FROM &#42;.log”**。

你可以暂停和恢复使用日志记录。 当你暂停日志记录时，Azure Rights Management 将保留你的存储帐户信息，使得你能够轻松地重新恢复日志记录。

#### 暂停和恢复使用日志记录

-   若要暂停日志记录，请使用以下 cmdlet：[Disable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629404.aspx)

-   若要恢复日志记录，请使用以下 cmdlet：[Enable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629421.aspx)

-   若要检查日志记录是处于启用还是禁用状态，请使用以下 cmdlet：[Get-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629425.aspx)

    如果值为 **True**，则表示 Azure Rights Management 使用日志记录处于启用状态，如果值为 **False**，则表示使用日志记录处于禁用状态。

## <a name="BKMK_ManageStorage"></a>如何管理 Azure Rights Management 日志存储
你要负责管理用于保存你的 Azure Rights Management 日志的存储空间。

Azure Rights Management 不自动管理使用日志文件。 如果你没有执行任何操作，日志将保留在你的存储帐户中。 但是，为了节省空间和降低存储成本，你可能希望在下载日志之后删除日志。 或者，你也可以选择要删除哪些文件。 由于 Azure Rights Management 不使用这些日志文件，因此也不限制你何时可以删除它们，但有一个文件例外。

你不能删除（或修改）的这个文件的名称为 **metadata**，位于 **rms-metadata** 容器中。 Azure Rights Management 使用这个 Blob 来跟踪使用的上一个 Blob 编号。 如果此文件被删除，Azure Rights Management 将为日志启动一个新容器，其 Blob 编号从 1 开始，今后使用 Get-AadrmUsageLog cmdlet 进行的所有下载都将使用这个新容器来下载日志文件。 因此，原有容器中的所有日志都会保留，但却是孤立的。 下载这些孤立日志的唯一方法是使用 Azure 存储 SDK。

> [!TIP]
> 你无需自行管理 Azure Rights Management 日志存储，而是可以通过共享你的存储帐户名和访问密钥，将这项管理职能委托给另一家公司。 有关详细信息，请参阅本主题后面的[如何委托对 Azure Rights Management 使用日志的访问权限](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_Delegate)部分。

某些情况下，你可能希望重新生成存储访问密钥。 例如：

-   你更改了管理 Azure Rights Management 使用日志的公司。

-   你怀疑你的存储访问密钥已泄漏。

如果发生这种情况，你可以使用辅助访问密钥（假定你以前使用主访问密钥）以确保服务连续性。 当你重新生成以前没有使用的访问密钥时，请将 Azure Rights Management 配置为使用新密钥。 请使用以下过程重新生成辅助访问密钥，然后将 Azure Rights Management 配置为使用该密钥：

#### 重新生成辅助访问密钥

1.  登录到 [Azure 门户](https://portal.azure.com/)。

2.  单击“全部资源”，然后通过在文本框中键入存储名称来搜索你的存储。

3.  选择你的存储，然后单击“设置”。

4.  单击“密钥”图标。

5.  在“管理密钥”部分中，单击“重新生成辅助密钥”，单击“是”以确认要重新生成辅助访问密钥，并将新的辅助访问密钥复制到剪贴板。

    请不要关闭 Azure 门户。

6.  使用“以管理员身份运行”选项启动 Windows PowerShell，并使用 [Set-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629426.aspx) cmdlet 将 Azure Rights Management 配置为使用这个新访问密钥，将 *&lt;StorageAccount&gt;* 替换为你的存储帐户名称，将 *&lt;Access_Key&gt;* 替换为你刚才复制的重新生成的辅助访问密钥：

    ```
    Set-AadrmUsageLogStorageAccount -StorageAccount <StorageAccount>-AccessKey <Access_Key>
    ```
    > [!WARNING]
    > 虽然你可以在运行此命令时切换到其他存储帐户，但此操作会孤立你以前的日志，导致 Set-AadrmUsageLogStorageAccount cmdlet 或类似管理命令和功能无法再访问这些日志。

7.  回到 Azure 门户中的“管理密钥”部分，重新生成你的主访问密钥。

有关如何管理存储访问密钥的详细信息，请参阅 Azure 文档的[关于 Azure 存储帐户](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/)中的[管理存储访问密钥](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/)部分。

## <a name="BKMK_Delegate"></a>如何委托对 Azure Rights Management 使用日志的访问权限
你可以通过共享存储帐户名称和访问密钥，委托对 RMS 日志的访问权限。 你可能希望将访问权限委托给另一位管理员用户、组织内部开发人员或独立软件供应商 (ISV)。 由于他们没有你的 RMS 管理员凭据，因此无法使用 Get-AardrmUsageLog cmdlet 来下载 RMS 日志。 他们只能使用 Windows 存储 SDK 来下载日志。 此外，他们也可以编写一个应用程序，用于直接从 Azure 存储空间读取日志。

在将存储帐户专用于你的 RMS 日志时，通过这种方式共享你的存储帐户名称和访问密钥是安全的。 虽然其他人拥有你的访问密钥，但他们无法使用该密钥来访问其他任何存储帐户，也无法使用你的 RMS 租户帐户。

## <a name="BKMK_Interpret"></a>如何解释 Azure Rights Management 使用日志
使用以下信息可帮助你解释 Azure Rights Management 使用日志。

### 存储帐户布局
当 Azure Rights Management 第一次将日志写入你的存储帐户时，它会创建以下两个容器：

-   **Rms-metadata**：此容器为 Azure Rights Management 保留。 不要修改或删除此容器。

-   **Rms-logs-&lt;guid&gt;**：Azure Rights Management 在此容器中创建和保存日志。 如果你不再需要此容器包含的日志记录信息，可以安全地删除其中的任何文件。

随着时间推移，Azure Rights Management 可能创建更多 **Rms-logs-&lt;guid&gt;** 容器。 例如，如果 **Rms-metadata** 容器被破坏或意外删除，Azure Rights Management 将重置其内容，并创建新的 **Rms-logs-&lt;guid&gt;** 容器，用于存储今后的所有日志。 旧容器中的旧日志不会被删除，但会被孤立。

### 日志序列
Azure Rights Management 将日志作为一系列 Blob 写入。 每个 Blob 包含一条或多条日志记录，采用 W3C 扩展日志格式。

每个 Blob 的名称是数字。 在每个日志容器内，第一个 Blob 命名为 000000001。 每个 Blob 按创建顺序依次命名。 每个 Blob 包含一条或多条日志记录。 每条日志记录具有一个 UTC 时间戳，指示 Azure Rights Management 何时处理相应请求。

> [!IMPORTANT]
> Azure Rights Management 日志记录系统经过优化，可快速为你提供日志，而不必严格遵循顺序。 Blob 的顺序以及 Blob 内部日志记录的顺序可能不符合时间顺序。 按顺序命名 Blob 的唯一原因是让你能够以增量方式高效下载它们。
> 
> 可能的日志序列结果的两个示例：
> 
> -   Blob 000000004 中的日志记录可能与 Blob 000000003 中的日志记录在时间上重叠。 在极端情况下，Blob 000000004 中的所有日志记录可能已在 Blob 000000003 中的所有日志记录之前生成。
> -   Blob 中的第二个日志记录可能在第一个日志记录之前生成，但按照相反顺序写入存储。

在分析 Azure Rights Management 使用日志之前，建议你将日志下载和导入到存储库，并可以在存储库中按时间戳对日志进行排序。 有关如何下载日志的详细信息，请参阅本主题中的[如何访问和使用 Azure Rights Management 使用日志](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_AccesAndUseLogs)部分。

虽然日志并非一定遵循时间顺序，但大多数日志在请求后 15 分钟内写入，因此在使用时间戳识别所需的日志时，请将你感兴趣的日志的时间加上 15 分钟， 然后再下载这些日志。 这种策略会确保你获取几乎所有日志。

另外请记住，每条日志记录上的时间戳是处理请求的 Azure Rights Management 服务的本地时间。 由于 Azure Rights Management 在跨多个数据中心的多个服务器上运行，有时日志即使是按时间戳排序，也似乎并不符合时间顺序。 不过这种差异很小，通常在一分钟之内。 大多数情况下，这不会为日志分析带来麻烦。

### Blob 格式
所有 Blob 都采用 W3C 扩展日志格式。 开头是以下两行：

**#Software:RMS**

**#Version:1.1**

第一行标识这些是 Azure Rights Management 日志。 第二行标识 Blob 的剩余部分遵循版本 1.1 规范。 我们建议，用于解析这些日志的任何应用程序都应先验证这两行，然后再继续解析 Blob 的剩余部分。

第三行枚举字段名称列表，以制表符分隔：

**#字段：date            time            row-id        request-type           user-id       result          correlation-id          content-id                owner-email           issuer                     template-id             file-name                  date-published      c-info         c-ip**

后面的每行都是日志记录。 这些字段的值与前一行具有相同的顺序，并且以制表符分隔。 请使用下表分析这些字段。

|字段名称|W3C 数据类型|说明|示例值|
|--------|------------|------|-------|
|date|日期|为请求提供服务时的 UTC 日期。<br /><br />源是为请求提供服务的服务器上的本地时钟。|2013-06-25|
|time|时间|为请求提供服务时的 UTC 时间（24 小时格式）。<br /><br />源是为请求提供服务的服务器上的本地时钟。|21:59:28|
|row-id|文本|此日志记录的唯一 GUID。<br /><br />在你整合日志或将日志复制为其他格式时，这个值是有用的。|1c3fe7a9-d9e0-4654-97b7-14fafa72ea63|
|request-type|Name|所请求的 RMS API 的名称。|AcquireLicense|
|user-id|String|发出请求的用户。<br /><br />该值包括在单引号中。 有些请求类型是匿名的，在这种情况下，该值为 ”。|‘joe@contoso.com’|
|result|String|如果成功地为请求提供服务，则为‘Success’。<br /><br />如果为请求提供服务失败，则在单引号中显示错误类型。|‘Success’|
|correlation-id|文本|在 RMS 客户端日志和服务器日志之间通用的针对给定请求的 GUID。<br /><br />此值有助于你解决客户端问题。|cab52088-8925-4371-be34-4b71a3112356|
|content-id|文本|包括在大括号中的 GUID，标识受保护内容（例如某个文档）。<br /><br />只有当 request-type 为 AcquireLicense 时，此字段才具有值，对于其他所有请求类型，此字段都为空。|{bb4af47b-cfed-4719-831d-71b98191a4f2}|
|owner-email|String|文档所有者的电子邮件地址。|alice@contoso.com|
|issuer|String|文档发布者的电子邮件地址。|alice@contoso.com（或）FederatedEmail.4c1f4d-93bf-00a95fa1e042@contoso.onmicrosoft.com'|
|Template-id|String|用于保护文档的模板的 ID。|{6d9371a6-4e2d-4e97-9a38-202233fed26e}|
|File-name|String|已保护的文档的文件名。|TopSecretDocument.docx|
|Date-published|日期|保护文档时的日期。|2015-10-15T21:37:00|
|c-info|String|有关发出请求的客户端平台的信息。<br /><br />特定字符串各不相同，具体取决于应用程序（例如操作系统或浏览器）。|'MSIPC;version=1.0.623.47;AppName=WINWORD.EXE;AppVersion=15.0.4753.1000;AppArch=x86;OSName=Windows;OSVersion=6.1.7601;OSArch=amd64'|
|c-ip|Address|发出请求的客户端的 IP 地址。|64.51.202.144|

#### user-id 字段的例外
虽然 user-id 字段通常指示发出请求的用户，但在两种例外情况下，该值不映射到真正用户：

-   值 **'microsoftrmsonline@&lt;YourTenantID&gt;.rms.&lt;region&gt;.aadrm.com'**。

    它指示 Office 365 服务（例如 Exchange Online 或 Sharepoint Online）正在发出请求。 在字符串中，*&lt;YourTenantID&gt;* 是你租户的 GUID，*&lt;region&gt;* 是你租户注册的区域。 例如，**na** 代表北美，**eu** 代表欧洲，**ap** 代表亚洲。

-   如果你使用 RMS 连接器。

    此连接器发出的请求将使用服务主体名称来进行记录，该名称是 RMS 在你安装 RMS 连接器时自动生成的。

#### 典型请求类型
Azure Rights Management 中有很多请求类型，但下表列出了其中一些最常用的请求类型。

|请求类型|说明|
|--------|------|
|AcquireLicense|基于 Windows 的计算机上的客户端为受 RMS 保护的内容请求许可证。|
|AcquirePreLicense|客户端代表用户为受 RMS 保护的内容请求许可证。|
|AcquireTemplates|进行调用以基于模板 ID 获取模板|
|AcquireTemplateInformation|进行调用以从服务获取模板的 ID。|
|AddTemplate|从 Azure 经典门户进行调用以添加模板。|
|BECreateEndUserLicenseV1|从移动设备进行调用以创建最终用户许可证。|
|BEGetAllTemplatesV1|从移动设备（后端）进行调用以获取所有模板。|
|Certify|客户端正在认证要保护的内容。|
|Decrypt|客户端正在尝试解密受 RMS 保护的内容。|
|DeleteTemplateById|从 Azure 经典门户进行调用以按模板 ID 删除模板。|
|ExportTemplateById|从 Azure 经典门户进行调用以基于模板 ID 导出模板。|
|FECreateEndUserLicenseV1|类似于 AcquireLicense 请求，但来自移动设备。|
|FECreatePublishingLicenseV1|与 Certify 和 GetClientLicensorCert 组合请求相同，来自移动客户端。|
|FEGetAllTemplates|从移动设备（前端）进行调用以获取模板。|
|GetAllTemplates|从 Azure 经典门户进行调用以获取所有模板。|
|GetClientLicensorCert|客户端正在从基于 Windows 的计算机请求发布证书（随后用于保护内容）。|
|GetConfiguration|调用 Azure PowerShell cmdlet 以获取 Azure RMS 租户的配置。|
|GetConnectorAuthorizations|从 RMS 连接器进行调用以从云中获取其配置。|
|GetTenantFunctionalState|Azure 经典门户检查是否已激活 Azure RMS。|
|GetTemplateById|从 Azure 经典门户进行调用以通过指定模板 ID 来获取模板。|
|ExportTemplateById|从 Azure 经典门户进行调用以通过指定模板 ID 来导出模板。|
|FindServiceLocationsForUser|进行调用以查询 URL，使用该项来调用 Certify 或 AcquireLicense。|
|ImportTemplate|从 Azure 经典门户进行调用以导入模板。|
|ServerCertify|从已启用 RMS 的客户端（如 SharePoint）进行调用以认证服务器。|
|SetUsageLogFeatureState|进行调用以启用使用日志记录。|
|SetUsageLogStorageAccount|进行调用以指定 Azure RMS 日志的位置。|
|SignDigest|在密钥用于签名目的时进行调用。 通常是针对每个 AcquireLicence（或 FECreateEndUserLicenseV1）、Certify 和 GetClientLicensorCert（或 FECreatePublishingLicenseV1）请求调用一次此项。|
|UpdateTemplate|从 Azure 经典门户进行调用以更新现有模板。|

## <a name="BKMK_PowerShell"></a>Windows PowerShell 参考
使用以下 Windows PowerShell cmdlet 帮助你配置和使用 Azure Rights Management 使用日志记录：

-   [Disable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629404.aspx)

-   [Enable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629421.aspx)

-   [Get-AadrmUsageLog](https://msdn.microsoft.com/library/azure/dn629401.aspx)

-   [Get-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629425.aspx)

-   [Get-AadrmUsageLogLastCounterValue](https://msdn.microsoft.com/library/azure/dn629423.aspx)

-   [Get-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629419.aspx)

-   [Set-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629426.aspx)

有关使用适用于 Azure Rights Management 的 Windows PowerShell 的详细信息，请参阅[使用 Windows PowerShell 管理 Azure 权限管理](../Topic/Administering_Azure_Rights_Management_by_Using_Windows_PowerShell.md)。

## 请参阅
[使用 Azure 权限管理](../Topic/Using_Azure_Rights_Management.md)

