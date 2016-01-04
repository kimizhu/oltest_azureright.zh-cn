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
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="zh-CN">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="22662a662dc8c6b7711e70d049524d3b" id="tgt1" class="tgtSentence">使用本主题中的信息可以帮助你了解如何使用 Azure Rights Management (Azure RMS) 的使用日志记录功能。</caps:sentence>
          <caps:sentence sentenceid="7175e4cf114ae559272e83d5d77279ae" id="tgt2" class="tgtSentence"> Azure Rights Management 服务能够记录它为你组织发出的所有请求，包括来自用户的请求、你组织中的 Rights Management 管理员执行的操作、Microsoft 操作人员为了支持你的 Azure Rights Management 部署执行的操作。</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="6e891353c2cf296b4e662ec87649e382" id="tgt3" class="tgtSentence">然后，你可以使用这些 Azure Rights Management 日志来支持以下业务方案：</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <caps:sentence sentenceid="553ff180172154e8028ed6ff2d9351e3" id="tgt4" class="tgtSentence">分析信息以获得业务见解。</caps:sentence>
            </para>
            <para>
              <caps:sentence sentenceid="5874d2c3cd1ecbbc4b200cbd0e8f4043" id="tgt5" class="tgtSentence">Azure Rights Management 采用 W3C 扩展日志格式，将日志写入你提供的 Azure 存储帐户。</caps:sentence>
              <caps:sentence sentenceid="1ae65b531af18298f681545662cf3b6b" id="tgt6" class="tgtSentence"> 然后，你可将这些日志发送到你选择的存储库（例如数据库、联机分析处理 (OLAP) 系统或 map-reduce 系统），以便分析信息并生成报告。</caps:sentence>
              <caps:sentence sentenceid="909a1e3fea32c0a37f22bfe00127820e" id="tgt7" class="tgtSentence"> 例如，你可以看出谁在访问你的 RMS 保护数据。</caps:sentence>
              <caps:sentence sentenceid="929430c45dc7213f067c3b017e1cdc68" id="tgt8" class="tgtSentence"> 你还可以确定用户访问了哪些 RMS 保护数据、从哪些设备访问、从何处访问。</caps:sentence>
              <caps:sentence sentenceid="e9b2481e2c3847564129dfa641ad70f0" id="tgt9" class="tgtSentence"> 你可以了解用户是否能够成功读取受保护内容。</caps:sentence>
              <caps:sentence sentenceid="e2a448d437879096f82118ad9344911d" id="tgt10" class="tgtSentence"> 你还可以看出哪些用户阅读了某个受保护的重要文档。</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence sentenceid="9fd86164ea8ed3ef7fbef244c49b3381" id="tgt11" class="tgtSentence">监控滥用行为。</caps:sentence>
            </para>
            <para>
              <caps:sentence sentenceid="f19fdcf86275351596c6e312e0a9c1ff" id="tgt12" class="tgtSentence">你可以近乎实时地访问 Azure Rights Management 日志记录信息，从而持续监控你公司使用 Rights Management 的情况。</caps:sentence>
              <caps:sentence sentenceid="2ee220a94a479244df88f2e5f4ba5c74" id="tgt13" class="tgtSentence"> 99.9% 的日志可在 RMS 启动操作后 15 分钟之内访问。</caps:sentence>
            </para>
            <para>
              <caps:sentence sentenceid="9a5f200f4798df9885deb4eee9d0f982" id="tgt14" class="tgtSentence">例如，如果在正常工作时间之外读取 RMS 保护数据的用户迅猛增加，可能意味着恶意用户正在收集信息并企图售卖给你的竞争对手，你希望在出现这种情况时收到警报。</caps:sentence>
              <caps:sentence sentenceid="dd6dff482e6f2eb49b2ca9b46083cb1b" id="tgt15" class="tgtSentence"> 或者，如果同一用户在很短时间内显然是从两个不同 IP 地址访问数据，则可能意味着该用户帐户已泄漏。</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence sentenceid="5592ef914ac95bf57f7c7ef51176a529" id="tgt16" class="tgtSentence">执行取证分析。</caps:sentence>
            </para>
            <para>
              <caps:sentence sentenceid="ff0a5cf3b5e54c1a1e76257b6184a839" id="tgt17" class="tgtSentence">如果遇到信息泄露，安全人员很可能向你询问最近谁访问了特定文档，以及可疑人员最近访问了哪些信息。</caps:sentence>
              <caps:sentence sentenceid="331ee877d663f01887452f4ab492ab29" id="tgt18" class="tgtSentence"> 当你使用 Azure Rights Management 和日志记录时，你就能够回答这些类型的问题，因为使用受保护内容的用户始终必须获取 Rights Management 许可证才能打开受 Azure Rights Management 保护的文档和图片，即便这些文件已移动（通过电子邮件）或复制到 U 盘或其他存储设备也是如此。</caps:sentence>
              <caps:sentence sentenceid="e3e1e90d1af46457c638e0f590981760" id="tgt19" class="tgtSentence"> 这意味着在通过 Azure Rights Management 保护数据时，你能够使用 Azure Rights Management 日志作为确定性信息源进行取证分析。</caps:sentence>
            </para>
          </listItem>
        </list>
        <alert class="note">
          <para>
            <caps:sentence sentenceid="815354be460efad4ff3b529539678cc5" id="tgt20" class="tgtSentence">如果你只希望记录 Azure Rights Management 的管理任务，而不希望跟踪用户如何使用 Rights Management，则可使用适用于 Azure Rights Management 的 <externalLink><linkText>Get-AadrmAdminLog</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629430.aspx</linkUri></externalLink> Windows PowerShell cmdlet。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="c5cc60f979fa1b5664fefb1dba55e966" id="tgt21" class="tgtSentence">你还可以使用 Azure 经典门户获取高级使用情况报告，包括“RMS 使用情况”、“最活跃的 RMS 用户”、“RMS 设备使用情况”和“已启用 RMS 的应用程序使用情况”<ui></ui><ui></ui><ui></ui><ui></ui>。</caps:sentence>
            <caps:sentence sentenceid="8f64067cba4365623c3ab5065a4452dc" id="tgt22" class="tgtSentence"> 若要从 Azure 经典门户访问这些报告，请单击“Active Directory”，选择并打开一个目录，然后单击“报告”<ui></ui><ui></ui>。</caps:sentence>
          </para>
        </alert>
        <para>
          <caps:sentence sentenceid="e4c1bc6683cfc7bf9d0c4dea8adcef06" id="tgt23" class="tgtSentence">有关 Azure Rights Management 使用日志记录的详细信息，请参阅以下部分。</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_EnableRMSLogging">How to enable RMS logging</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_AccesAndUseLogs">How to access and use your RMS logs</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_ManageStorage">How to manage your RMS log storage</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_Delegate">How to delegate access to your RMS logs</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_Interpret">How to interpret your RMS logs</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_PowerShell">Windows PowerShell reference</link>
            </para>
          </listItem>
        </list>
      </introduction>
      <section address="BKMK_EnableRMSLogging">
        <title>
          <caps:sentence sentenceid="1f3600c9cd6273f4cb0a7953a78b0671" id="tgt24" class="tgtSentence">如何启用 Azure Rights Management 使用日志记录</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="540481a4317e26b1547221c197352dcb" id="tgt25" class="tgtSentence">Azure Rights Management 使用日志记录是可选的，因此如果你希望使用该功能，则必须执行特定步骤。</caps:sentence>
            <caps:sentence sentenceid="d000f626454a3ae54c070e4cb78c28ca" id="tgt26" class="tgtSentence"> 当你使用 Azure Rights Management 使用日志记录时，Rights Management 的工作方式没有变化，日志记录流程本身是免费的。</caps:sentence>
            <caps:sentence sentenceid="ba96e39b229c65dc703da109c8c8f53c" id="tgt27" class="tgtSentence"> 但是，你必须提供用于日志的 Azure 存储帐户，此存储服务收取费用。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="98c944119b6bd280056311418ed87f7c" id="tgt28" class="tgtSentence">开始之前，请确保你符合使用 Azure Rights Management 使用日志记录的以下先决条件：</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="ba12fb48e2d23bb2bd2819f64d02ec7e" id="tgt29" class="tgtSentence">要求</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="5dc731e46ae38b87ff3e3e2eaf459db2" id="tgt30" class="tgtSentence">更多信息</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="f0c8e0d48a5bfe3d60b027575599e81f" id="tgt31" class="tgtSentence">包含 Azure Rights Management 的由 IT 人员管理的订阅</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="dc69ef9a97237bcc33481df8946cd734" id="tgt32" class="tgtSentence">你必须拥有由你组织管理的 Microsoft Azure Rights Management 订阅。</caps:sentence>
                    <caps:sentence sentenceid="e1201fdcffa570cca1f19bfb89e25942" id="tgt33" class="tgtSentence"> 使用个人 RMS 的组织不能使用 Azure Rights Management 使用日志记录。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="dd6acd3cb9b0e989bf09dc37a989ab01" id="tgt34" class="tgtSentence">如果你组织有用户使用个人 RMS，则 Azure Rights Management 使用日志记录提供了一个非常具有说服力的业务理由，促使你组织将个人 RMS 转换为 Microsoft Azure Rights Management 订阅。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="78f6f45fbb6e41728869b38634a19c84" id="tgt35" class="tgtSentence">有关包含 Azure RMS 的订阅的详细信息，请参阅 <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>主题中的<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link>部分。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="2c68cac55d3d19f5ed96e3e819906777" id="tgt36" class="tgtSentence">有关个人 RMS 的详细信息，请参阅<link xlink:href="2efcb440-fefd-45e9-872b-f471573aadf2">RMS for Individuals and Azure Rights Management</link></caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="e9a958e3a95884bc2b6a17370d017e53" id="tgt37" class="tgtSentence">Azure 订阅</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="e9fab77a2f7f2ea27562640de4c54a0f" id="tgt38" class="tgtSentence">你必须具有 Azure 订阅，还需要在 Azure 上具有足够的存储空间，用于存储 Azure Rights Management 日志。</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="71bc936b1746b15dadaec1b9dfd40f54" id="tgt39" class="tgtSentence">适用于 Azure Rights Management 的 Windows PowerShell</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="98902f3607b0de9e10a56b5a34aeacc7" id="tgt40" class="tgtSentence">如果你尚未这样做，请下载并安装适用于 Azure Rights Management 的 Windows PowerShell 模块。</caps:sentence>
                    <caps:sentence sentenceid="2eec5c1b5506ed7c67273cdabfba7db0" id="tgt41" class="tgtSentence"> 你将使用 Windows PowerShell cmdlet 来配置和管理 Azure Rights Management 使用日志。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="d1aee644e17abda9397214172b7615de" id="tgt42" class="tgtSentence">有关详细信息，请参阅<link xlink:href="0d665ed6-b1de-4d63-854a-bc57c1c49844">Installing Windows PowerShell for Azure Rights Management</link>。</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
          <para>
            <caps:sentence sentenceid="87b36330723a87dd0317636c38a95df3" id="tgt43" class="tgtSentence">使用以下过程可以启用 Azure Rights Management 使用日志记录，此过程包括创建 Azure 存储帐户，并将 Azure 配置为使用此存储帐户来存储 Rights Management 日志。</caps:sentence>
          </para>
          <alert class="note">
            <para>
              <caps:sentence sentenceid="57c6007bcbf6f438841837bbec56e945" id="tgt44" class="tgtSentence">此过程假定你有 Azure 帐户。</caps:sentence>
              <caps:sentence sentenceid="3e3fb8e67bccd8fc678be3c592b9b04e" id="tgt45" class="tgtSentence"> Azure Rights Management 使用日志记录支持个人帐户，但最好使用工作或学校帐户。</caps:sentence>
              <caps:sentence sentenceid="30772583e317300ad595232f1f52dc4f" id="tgt46" class="tgtSentence"> 此外，我们建议你为 Rights Management 日志创建一个专用存储帐户。</caps:sentence>
              <caps:sentence sentenceid="93236b8c8811d2c6d96372a73fbb743d" id="tgt47" class="tgtSentence"> 你必须与 Azure Rights Management 共享存储访问密钥，如果其他人也希望使用日志文件，你可能还需要与他们共享。</caps:sentence>
            </para>
            <para>
              <caps:sentence sentenceid="0f1e4314c029b0c8fcdb4e29ed5a75d9" id="tgt48" class="tgtSentence">有关 Azure 存储空间的详细信息，请参阅 <externalLink><linkText>Azure 存储空间文档</linkText><linkUri>http://azure.microsoft.com/documentation/services/storage/</linkUri></externalLink>。</caps:sentence>
            </para>
          </alert>
          <procedure>
            <title>
              <caps:sentence sentenceid="d8e22cce85bb6f234af129095f1a1980" id="tgt49" class="tgtSentence">如何创建存储帐户并启用 Azure Rights Management 使用日志记录</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="b45e536a8035d15500d48ba4aa04ac22" id="tgt50" class="tgtSentence">登录到 <externalLink><linkText>Azure 门户</linkText><linkUri>https://portal.azure.com/</linkUri></externalLink>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="23a2116d90354810796a81ea828c199f" id="tgt51" class="tgtSentence">在“中心”菜单上，选择“新建”-&gt;“数据 + 存储”-&gt;“存储帐户”<ui></ui><ui></ui><ui></ui>。</caps:sentence>
                  </para>
                  <alert class="tip">
                    <para>
                      <caps:sentence sentenceid="d0ebb82309829aadc91cacaa2b9dbab5" id="tgt52" class="tgtSentence">如果看不到此选项，请检查除了 Rights Management 的订阅以外，你是否还拥有 Azure 订阅。</caps:sentence>
                    </para>
                  </alert>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="b45951efec0a3fab6c0b63226696b384" id="tgt53" class="tgtSentence">保留默认部署模型（即<ui>经典</ui>），然后单击“创建”<ui></ui>。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="fa473074a7fd6998ed52a80d0acbf75e" id="tgt54" class="tgtSentence">指定存储帐户的名称，如有必要，更改<ui>定价层</ui>、<ui>资源组</ui>、<ui>订阅</ui>的所选选项，以及是否要<ui>固定到仪表板</ui>。</caps:sentence>
                    <caps:sentence sentenceid="a44d9fa92ef0c9ce1b26f20489f80969" id="tgt55" class="tgtSentence"> 然后单击“创建”<ui></ui>。</caps:sentence>
                    <caps:sentence sentenceid="3b3ea94fc677e4dfe94c0abf7af04bf5" id="tgt56" class="tgtSentence"> 等待“创建存储帐户”活动完成<ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="28a70ba059e29eb968957420192be8a9" id="tgt57" class="tgtSentence">单击新创建的存储帐户，然后单击“设置”<ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="004dc0ceb5e9b2247446dc0a40f7a169" id="tgt58" class="tgtSentence">在“设置”边栏选项卡中，请单击“密钥”图标<ui></ui><ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="004dc0ceb5e9b2247446dc0a40f7a169" id="tgt59" class="tgtSentence">在“管理密钥”边栏选项卡中，复制<ui>主访问密钥</ui>的值，然后关闭边栏选项卡<ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="a796808f0542040254624a40c5de067c" id="tgt60" class="tgtSentence">使用“以管理员身份运行”选项启动 Windows PowerShell<ui></ui>。</caps:sentence>
                    <caps:sentence sentenceid="5a55dd622556408aded64e9e7cffb4b9" id="tgt61" class="tgtSentence"> 运行 <externalLink><linkText>Connect-AadrmService</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629415.aspx</linkUri></externalLink> 命令以连接到 Azure Rights Management 服务：</caps:sentence>
                  </para>
                  <code>Connect-AadrmService</code>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="16859c9da62799922bc88b1c7de34fc3" id="tgt62" class="tgtSentence">使用 <externalLink><linkText>Set-AadrmUsageLogStorageAccount</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629426.aspx</linkUri></externalLink> 命令指定需要存储 Azure Rights Management 使用日志的位置，将 <placeholder>&lt;Access_Key&gt;</placeholder> 替换为你在步骤 6 中复制的主访问密钥，并将 <placeholder>&lt;StorageAccount&gt;</placeholder> 替换为你在步骤 3 中创建的存储帐户的名称：</caps:sentence>
                  </para>
                  <code>$accesskey = convertto-securestring -asplaintext -force –string <placeholder xmlns="">&lt;Access_Key&gt;</placeholder> Set-AadrmUsageLogStorageAccount -AccessKey $accesskey -StorageAccount <placeholder xmlns="">&lt;StorageAccount&gt;</placeholder></code>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="16859c9da62799922bc88b1c7de34fc3" id="tgt63" class="tgtSentence">使用 <externalLink><linkText>Enable-AadrmUsageLogFeature</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629421.aspx</linkUri></externalLink> 命令启用 Azure Rights Management 使用日志记录：</caps:sentence>
                  </para>
                  <code>Enable-AadrmUsageLogFeature</code>
                  <para>
                    <caps:sentence sentenceid="2d12f6a9d634beeab77a587286df6d7d" id="tgt64" class="tgtSentence">你应该看到以下消息：<ui>为权限管理服务启用了使用日志记录功能。</ui></caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence sentenceid="aab05520a5826f77f5de324537c86146" id="tgt65" class="tgtSentence">现在，使用日志记录功能已启用，Azure Rights Management 开始记录你组织的所有操作，并将这些信息保存到你的存储帐户。</caps:sentence>
                  <caps:sentence sentenceid="3351fff94db1da9be25affb0176f1b36" id="tgt66" class="tgtSentence"> 日志记录信息在此之前不可用。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="bc431a4370dc487d3ac8408891cb29da" id="tgt67" class="tgtSentence">有关如何创建存储帐户的详细信息，请参阅 Azure 文档的<externalLink><linkText>关于 Azure 存储帐户</linkText><linkUri>https://azure.microsoft.com/documentation/articles/storage-create-storage-account/</linkUri></externalLink>中的<externalLink><linkText>创建存储帐户</linkText><linkUri>https://azure.microsoft.com/documentation/articles/storage-create-storage-account/#create-a-storage-account</linkUri></externalLink>部分。</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
        </content>
      </section>
      <section address="BKMK_AccesAndUseLogs">
        <title>
          <caps:sentence sentenceid="dc4a1a28217b1dd3982eaf83276f2c37" id="tgt68" class="tgtSentence">如何访问和使用 Azure Rights Management 使用日志</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="dfaf479d19a1261f9ef0e74dbe9284d4" id="tgt69" class="tgtSentence">Azure Rights Management 将日志作为一系列 Blob 写入你的 Azure 存储帐户。</caps:sentence>
            <caps:sentence sentenceid="30febf2bb481a98bc09a1f40c034a5f0" id="tgt70" class="tgtSentence"> 每个 Blob 包含一条或多条日志记录，采用 W3C 扩展日志格式。</caps:sentence>
            <caps:sentence sentenceid="786c43af7325b1745ee7fde27e09e6e5" id="tgt71" class="tgtSentence"> Blob 名称为数字，按创建顺序排列。</caps:sentence>
            <caps:sentence sentenceid="90adbbe7112a5ab0269194573e650cc6" id="tgt72" class="tgtSentence"> 本文档后面的<link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_Interpret">How to interpret the RMS logs</link>部分包含了有关日志内容及其创建情况的更多信息。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="8749a5358b98f2ba216c5cdd54e4d689" id="tgt73" class="tgtSentence">在 Azure Rights Management 操作之后，日志需要一段时间才能显示在你的存储帐户中。</caps:sentence>
            <caps:sentence sentenceid="1e79717caf4b582029f9085c915956a2" id="tgt74" class="tgtSentence"> 大多数日志在 15 分钟之内显示。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="88df5d64348c0a53bb418f1351cb120c" id="tgt75" class="tgtSentence">你为 Azure Rights Management 使用日志创建的存储帐户类似于邮箱，支持从存储帐户直接读取，但这并非最佳使用方式。</caps:sentence>
            <caps:sentence sentenceid="3fcc555aa2a34edfb985c904dff7721a" id="tgt76" class="tgtSentence"> 相反，为了达到最佳性能并帮助降低成本，我们建议你将日志下载到本地存储，例如本地文件夹、数据库或 map-reduce 存储库。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="349be16b36423dfe5e637b44011b6b29" id="tgt77" class="tgtSentence">你可通过两种方式下载使用日志：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="380738433b0e574f0fcd0aa0fdc634b6" id="tgt78" class="tgtSentence">使用 Windows PowerShell cmdlet <externalLink><linkText>Get-AadrmUsageLog</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629401.aspx</linkUri></externalLink>。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="5641ce03007faebba5d74be6c69fca13" id="tgt79" class="tgtSentence">这是访问使用日志的最简单方式。</caps:sentence>
                <caps:sentence sentenceid="7f4c5f7410e06bde495fe746c2e2fef9" id="tgt80" class="tgtSentence"> 此 cmdlet 可将日志下载到你的计算机，将每个 Blob 作为文件下载到你指定的位置。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="16859c9da62799922bc88b1c7de34fc3" id="tgt81" class="tgtSentence">使用 <externalLink><linkText>Azure 存储空间 SDK</linkText><linkUri>http://www.windowsazure.com/en-us/develop/net/</linkUri></externalLink> 编写你自己的自定义应用程序以下载日志。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="ec6f9840011393a65343fdc6b933c95f" id="tgt82" class="tgtSentence">自定义应用程序能够提供比 Get-AadrmUsageLogs cmdlet 更高的灵活性。</caps:sentence>
                <caps:sentence sentenceid="a07fcd56c121241df8fbee825c5ea8f1" id="tgt83" class="tgtSentence"> 例如，你可能希望将日志下载操作委托给其他人或不能使用 Azure Rights Management 管理凭据的进程。</caps:sentence>
                <caps:sentence sentenceid="0fe3a6aa9bc4eb3aa65567aac1b640fb" id="tgt84" class="tgtSentence"> 你也可能希望实时轮询日志，因为你要监控滥用情况。</caps:sentence>
              </para>
            </listItem>
          </list>
          <procedure>
            <title>
              <caps:sentence sentenceid="cc3565295dee497953e3cd6b0d5a5fc5" id="tgt85" class="tgtSentence">使用 PowerShell 下载使用日志</caps:sentence>
            </title>
            <steps class="bullet">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="a796808f0542040254624a40c5de067c" id="tgt86" class="tgtSentence">使用“以管理员身份运行”选项启动 Windows PowerShell，然后运行 <userInput>Get-AadrmUsageLog –Path &lt;location&gt;</userInput>。<ui></ui></caps:sentence>
                    <caps:sentence sentenceid="1dd32d06672cc7dde1669da42d6f0665" id="tgt87" class="tgtSentence"> 例如，在 E 盘上创建名为 <system>logs</system> 的文件夹之后：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="bb3c91ae410412cc530a7cb4874924e2" id="tgt88" class="tgtSentence">将所有可用日志下载到 E:\logs 文件夹：<codeInline>Get-AadrmUsageLog -Path "e:\logs"</codeInline></caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="7eddee653cf43a5c83adb11aaae79d3a" id="tgt89" class="tgtSentence">下载特定范围的 Blob：<codeInline>Get-AadrmUsageLog –Path "e:\logs" –FromCounter 1024 –ToCounter 2047</codeInline></caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence sentenceid="13a14fd187043a220d91bbdd37ae6f5c" id="tgt90" class="tgtSentence">当你运行这些 cmdlet 时，Windows PowerShell 会显示下载的上一个 Blob 的名称。</caps:sentence>
                  <caps:sentence sentenceid="415ed2d3b4c9a23c6fda12610a4c09e7" id="tgt91" class="tgtSentence"> 你可将此名称分配给变量，让你能够在循环或计划作业中运行 Get-AadrmUsageLog，每次仅下载新增日志。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="a1f6c7d21a6ee4379899b0d1aeea4222" id="tgt92" class="tgtSentence">例如：  </caps:sentence>
                </para>
                <para>
                  <ui>
                    <caps:sentence sentenceid="5b02d996ad89b1565f0208113db9079e" id="tgt93" class="tgtSentence">PS C:\&gt; $LastBlobName = Get-AadrmUsageLog –Path "e:\logs"</caps:sentence>
                  </ui>
                </para>
                <para>
                  <ui>
                    <caps:sentence sentenceid="5cce8dede893813f879b873962fb669f" id="tgt94" class="tgtSentence">1527</caps:sentence>
                  </ui>
                </para>
                <para>
                  <ui>
                    <caps:sentence sentenceid="068eb7e5ccf80b995c139f552153c237" id="tgt95" class="tgtSentence">PS C:\&gt; $LastBlobName</caps:sentence>
                  </ui>
                </para>
                <para>
                  <ui>
                    <caps:sentence sentenceid="5cce8dede893813f879b873962fb669f" id="tgt96" class="tgtSentence">1527</caps:sentence>
                  </ui>
                </para>
              </content>
            </conclusion>
          </procedure>
          <alert class="tip">
            <para>
              <caps:sentence sentenceid="896853f89ee1df593b9a7720781076e0" id="tgt97" class="tgtSentence">你可以使用 <externalLink><linkText>Microsoft 的 Log Parser</linkText><linkUri>http://www.microsoft.com/download/details.aspx?id=24659</linkUri></externalLink>（一种在各种常见日志格式之间进行转换的工具），将所有已下载日志文件整合为 CSV 格式。</caps:sentence>
              <caps:sentence sentenceid="718ae56ff7645b9dbed73d69a36d0aeb" id="tgt98" class="tgtSentence"> 你还能够使用该工具将数据转换为 SYSLOG 格式，或者将其导入到数据库。</caps:sentence>
              <caps:sentence sentenceid="839ef8eef19e7bb80f921a64f5ced952" id="tgt99" class="tgtSentence"> 安装该工具之后，请运行 <userInput>LogParser.exe /?</userInput> 以获得此工具的使用帮助和信息。</caps:sentence>
              <caps:sentence sentenceid="0a73f9d96b3414aef7ce2136f20e80f5" id="tgt100" class="tgtSentence"> 例如，你可以运行以下命令，将所有信息导出为 .log 文件格式：<userInput>logparser –i:w3c –o:csv “SELECT * INTO AllLogs.csv FROM *.log”</userInput>。</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence sentenceid="40bb56c4a978f1782482e5748ef96f15" id="tgt101" class="tgtSentence">你可以暂停和恢复使用日志记录。</caps:sentence>
            <caps:sentence sentenceid="8359951e485e1e039ad71db1e4c358c5" id="tgt102" class="tgtSentence"> 当你暂停日志记录时，Azure Rights Management 将保留你的存储帐户信息，使得你能够轻松地重新恢复日志记录。</caps:sentence>
          </para>
          <procedure>
            <title>
              <caps:sentence sentenceid="6d175252b6d18419e7f44874c2d8868d" id="tgt103" class="tgtSentence">暂停和恢复使用日志记录</caps:sentence>
            </title>
            <steps class="bullet">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="9e94f70e2a4dd41bcece8d71d37a8257" id="tgt104" class="tgtSentence">若要暂停日志记录，请使用以下 cmdlet：<externalLink><linkText>Disable-AadrmUsageLogFeature</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629404.aspx</linkUri></externalLink></caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="0f4d0b353ae72d3a6fb01da8d7fbb873" id="tgt105" class="tgtSentence">若要恢复日志记录，请使用以下 cmdlet：<externalLink><linkText>Enable-AadrmUsageLogFeature</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629421.aspx</linkUri></externalLink></caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="461d7f93178f0dfb9071f5e9625cc2bf" id="tgt106" class="tgtSentence">若要检查日志记录是处于启用还是禁用状态，请使用以下 cmdlet：<externalLink><linkText>Get-AadrmUsageLogFeature</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629425.aspx</linkUri></externalLink></caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="700d5a1c28145abda811777fbbdccd0c" id="tgt107" class="tgtSentence">如果值为 <ui>True</ui>，则表示 Azure Rights Management 使用日志记录处于启用状态，如果值为 <ui>False</ui>，则表示使用日志记录处于禁用状态。</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
          </procedure>
        </content>
      </section>
      <section address="BKMK_ManageStorage">
        <title>
          <caps:sentence sentenceid="9f112ac6900e27d6fc6cdab820ac9eb4" id="tgt108" class="tgtSentence">如何管理 Azure Rights Management 日志存储</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="960afa12e510934f332f9da245e8a906" id="tgt109" class="tgtSentence">你要负责管理用于保存你的 Azure Rights Management 日志的存储空间。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="e371c6c98c798ad7191255b54c6ff10a" id="tgt110" class="tgtSentence">Azure Rights Management 不自动管理使用日志文件。</caps:sentence>
            <caps:sentence sentenceid="d2efcec5b4bd584aa13ff611c2dc05b9" id="tgt111" class="tgtSentence"> 如果你没有执行任何操作，日志将保留在你的存储帐户中。</caps:sentence>
            <caps:sentence sentenceid="3031b7daa55495e350228c8c69bd59cf" id="tgt112" class="tgtSentence"> 但是，为了节省空间和降低存储成本，你可能希望在下载日志之后删除日志。</caps:sentence>
            <caps:sentence sentenceid="ba91c05f3eaeb22e426d0083e542e62f" id="tgt113" class="tgtSentence"> 或者，你也可以选择要删除哪些文件。</caps:sentence>
            <caps:sentence sentenceid="cf073dcb1168338a9d109e5f62664a53" id="tgt114" class="tgtSentence"> 由于 Azure Rights Management 不使用这些日志文件，因此也不限制你何时可以删除它们，但有一个文件例外。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="ab7be43f478f8ec310bb0ac6b0447291" id="tgt115" class="tgtSentence">你不能删除（或修改）的这个文件的名称为 <ui>metadata</ui>，位于 <ui>rms-metadata</ui> 容器中。</caps:sentence>
            <caps:sentence sentenceid="58a4cb03a4cb7778af0ce3c2f3ced5ac" id="tgt116" class="tgtSentence"> Azure Rights Management 使用这个 Blob 来跟踪使用的上一个 Blob 编号。</caps:sentence>
            <caps:sentence sentenceid="044ad7e892af7390100fedc4fbc90831" id="tgt117" class="tgtSentence"> 如果此文件被删除，Azure Rights Management 将为日志启动一个新容器，其 Blob 编号从 1 开始，今后使用 Get-AadrmUsageLog cmdlet 进行的所有下载都将使用这个新容器来下载日志文件。</caps:sentence>
            <caps:sentence sentenceid="3a3cc15659fc6b7fd326afb237f410d3" id="tgt118" class="tgtSentence"> 因此，原有容器中的所有日志都会保留，但却是孤立的。</caps:sentence>
            <caps:sentence sentenceid="a9f2543765cc1678acab822f227ea339" id="tgt119" class="tgtSentence"> 下载这些孤立日志的唯一方法是使用 Azure 存储 SDK。</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence sentenceid="ba9329be7a6cb3e15721c9398f4a4b15" id="tgt120" class="tgtSentence">你无需自行管理 Azure Rights Management 日志存储，而是可以通过共享你的存储帐户名和访问密钥，将这项管理职能委托给另一家公司。</caps:sentence>
              <caps:sentence sentenceid="be021ab36c2c99a549fc25f5fcee238c" id="tgt121" class="tgtSentence"> 有关详细信息，请参阅本主题后面的<link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_Delegate">How to delegate access to your RMS logs</link>部分。</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence sentenceid="5868c659bd0e1da19037fdefcb434a9e" id="tgt122" class="tgtSentence">某些情况下，你可能希望重新生成存储访问密钥。</caps:sentence>
            <caps:sentence sentenceid="4be0bb25039056347740ae85bcda324d" id="tgt123" class="tgtSentence"> 例如：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="30f17a264c68cc899b95976c1e2ddef9" id="tgt124" class="tgtSentence">你更改了管理 Azure Rights Management 使用日志的公司。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="8be77f50e8f00a4e36c7231b8b84d0f7" id="tgt125" class="tgtSentence">你怀疑你的存储访问密钥已泄漏。</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="7c30654f7b0c28b28fb51871bb3d0055" id="tgt126" class="tgtSentence">如果发生这种情况，你可以使用辅助访问密钥（假定你以前使用主访问密钥）以确保服务连续性。</caps:sentence>
            <caps:sentence sentenceid="bda442ba2d89743385762b35632f6efb" id="tgt127" class="tgtSentence"> 当你重新生成以前没有使用的访问密钥时，请将 Azure Rights Management 配置为使用新密钥。</caps:sentence>
            <caps:sentence sentenceid="cb7a47952b8d0a380e54e52ea0230a60" id="tgt128" class="tgtSentence"> 请使用以下过程重新生成辅助访问密钥，然后将 Azure Rights Management 配置为使用该密钥：</caps:sentence>
          </para>
          <procedure>
            <title>
              <caps:sentence sentenceid="7238814bf3d7691da247d2b88d2fa075" id="tgt129" class="tgtSentence">重新生成辅助访问密钥</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="b45e536a8035d15500d48ba4aa04ac22" id="tgt130" class="tgtSentence">登录到 <externalLink><linkText>Azure 门户</linkText><linkUri>https://portal.azure.com/</linkUri></externalLink>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="ccbe2a6c96a5df5e1966988e40064061" id="tgt131" class="tgtSentence">单击“全部资源”，然后通过在文本框中键入存储名称来搜索你的存储<ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="d72d79584a85bef552cfedd54389eb07" id="tgt132" class="tgtSentence">选择你的存储，然后单击“设置”<ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="41ad10da17628099ea69f30e0bc238ba" id="tgt133" class="tgtSentence">单击“密钥”图标<ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="004dc0ceb5e9b2247446dc0a40f7a169" id="tgt134" class="tgtSentence">在“管理密钥”部分中，单击“重新生成辅助密钥”，单击“是”以确认要重新生成辅助访问密钥，并将新的辅助访问密钥复制到剪贴板<ui></ui><ui></ui>。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="b5544643b73914a8e818bde967daba56" id="tgt135" class="tgtSentence">请不要关闭 Azure 门户。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="a796808f0542040254624a40c5de067c" id="tgt136" class="tgtSentence">使用“以管理员身份运行”<ui></ui>选项启动 Windows PowerShell，并使用 <externalLink><linkText>Set-AadrmUsageLogStorageAccount</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629426.aspx</linkUri></externalLink> cmdlet 将 Azure Rights Management 配置为使用这个新访问密钥，将 <placeholder>&lt;StorageAccount&gt;</placeholder> 替换为你的存储帐户名称，将 <placeholder>&lt;Access_Key&gt;</placeholder> 替换为你刚才复制的重新生成的辅助访问密钥：</caps:sentence>
                  </para>
                  <code>Set-AadrmUsageLogStorageAccount -StorageAccount <placeholder xmlns="">&lt;StorageAccount&gt;</placeholder>-AccessKey <placeholder xmlns="">&lt;Access_Key&gt;</placeholder></code>
                  <alert class="warning">
                    <para>
                      <caps:sentence sentenceid="231ffb09152ca251535417d8ce8f28ea" id="tgt137" class="tgtSentence">虽然你可以在运行此命令时切换到其他存储帐户，但此操作会孤立你以前的日志，导致 Set-AadrmUsageLogStorageAccount cmdlet 或类似管理命令和功能无法再访问这些日志。</caps:sentence>
                    </para>
                  </alert>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="fa6ac77c3ddf9d91f172eefcfde3514d" id="tgt138" class="tgtSentence">回到 Azure 门户中的“管理密钥”部分，重新生成你的主访问密钥<ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence sentenceid="b7617a54ccaff11a4e80185715193036" id="tgt139" class="tgtSentence">有关如何管理存储访问密钥的详细信息，请参阅 Azure 文档的<externalLink><linkText>关于 Azure 存储帐户</linkText><linkUri>https://azure.microsoft.com/documentation/articles/storage-create-storage-account/</linkUri></externalLink>中的<externalLink><linkText>管理存储访问密钥</linkText><linkUri>https://azure.microsoft.com/documentation/articles/storage-create-storage-account/#manage-your-storage-access-keys</linkUri></externalLink>部分。</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
        </content>
      </section>
      <section address="BKMK_Delegate">
        <title address="BKMK_DelegateAccess">
          <caps:sentence sentenceid="d77e400fe7fa32738866fdfa1bed1d6c" id="tgt140" class="tgtSentence">如何委托对 Azure Rights Management 使用日志的访问权限</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="f91bfa3fa851c57ca1cd1259b862f993" id="tgt141" class="tgtSentence">你可以通过共享存储帐户名称和访问密钥，委托对 RMS 日志的访问权限。</caps:sentence>
            <caps:sentence sentenceid="9456f4df0aed5e6f524d1c70a5a490cf" id="tgt142" class="tgtSentence"> 你可能希望将访问权限委托给另一位管理员用户、组织内部开发人员或独立软件供应商 (ISV)。</caps:sentence>
            <caps:sentence sentenceid="04b90e7371044b923daac74ce8635f4a" id="tgt143" class="tgtSentence"> 由于他们没有你的 RMS 管理员凭据，因此无法使用 Get-AardrmUsageLog cmdlet 来下载 RMS 日志。</caps:sentence>
            <caps:sentence sentenceid="0556092088db21a8d4e37f57bccb269a" id="tgt144" class="tgtSentence"> 他们只能使用 Windows 存储 SDK 来下载日志。</caps:sentence>
            <caps:sentence sentenceid="e8f76d769c2a47521ca6015932b6303d" id="tgt145" class="tgtSentence"> 此外，他们也可以编写一个应用程序，用于直接从 Azure 存储空间读取日志。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="6238dcfa4b912f02d784b0f73aa40be9" id="tgt146" class="tgtSentence">在将存储帐户专用于你的 RMS 日志时，通过这种方式共享你的存储帐户名称和访问密钥是安全的。</caps:sentence>
            <caps:sentence sentenceid="5ff9e1e0e646a489073469aede84dbb7" id="tgt147" class="tgtSentence"> 虽然其他人拥有你的访问密钥，但他们无法使用该密钥来访问其他任何存储帐户，也无法使用你的 RMS 租户帐户。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_Interpret">
        <title>
          <caps:sentence sentenceid="5c6bb80be89318ffebdcf10299a07402" id="tgt148" class="tgtSentence">如何解释 Azure Rights Management 使用日志</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="59a66176b5102e4c4a74d1c34737270e" id="tgt149" class="tgtSentence">使用以下信息可帮助你解释 Azure Rights Management 使用日志。</caps:sentence>
          </para>
        </content>
        <sections>
          <section>
            <title>
              <caps:sentence sentenceid="fd067266e2e21d97d5167abd3cc00b5b" id="tgt150" class="tgtSentence">存储帐户布局</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="040f720fa0870b0c7f70f0c3f108cbb0" id="tgt151" class="tgtSentence">当 Azure Rights Management 第一次将日志写入你的存储帐户时，它会创建以下两个容器：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="95ad575d3e2eeca8f8e00ac33215e17f" id="tgt152" class="tgtSentence">
                      <ui>Rms-metadata</ui>：此容器为 Azure Rights Management 保留。</caps:sentence>
                    <caps:sentence sentenceid="e3b77c3d43dba43eb30eb4ffda250c6a" id="tgt153" class="tgtSentence"> 不要修改或删除此容器。</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="f18749822c2d3e1bd1f7575616cf8070" id="tgt154" class="tgtSentence">
                      <ui>Rms-logs-&lt;guid&gt;</ui>：Azure Rights Management 在此容器中创建和保存日志。</caps:sentence>
                    <caps:sentence sentenceid="75ec055df7b955189d8087a250f72f01" id="tgt155" class="tgtSentence"> 如果你不再需要此容器包含的日志记录信息，可以安全地删除其中的任何文件。</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence sentenceid="b5a58c3a2d7f271c89779439f3656e36" id="tgt156" class="tgtSentence">随着时间推移，Azure Rights Management 可能创建更多 <ui>Rms-logs-&lt;guid&gt;</ui> 容器。</caps:sentence>
                <caps:sentence sentenceid="74b21dfef0275d0662ae5c1f98eeb848" id="tgt157" class="tgtSentence"> 例如，如果 <ui>Rms-metadata</ui> 容器被破坏或意外删除，Azure Rights Management 将重置其内容，并创建新的 <ui>Rms-logs-&lt;guid&gt;</ui> 容器，用于存储今后的所有日志。</caps:sentence>
                <caps:sentence sentenceid="59d3c2a444df97b01c696fd9a69631ca" id="tgt158" class="tgtSentence"> 旧容器中的旧日志不会被删除，但会被孤立。</caps:sentence>
              </para>
            </content>
          </section>
          <section>
            <title>
              <caps:sentence sentenceid="80430c9a4ac2534726d4e66923ec4edf" id="tgt159" class="tgtSentence">日志序列</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="11176a798c30453cb75c2be6609c6cbd" id="tgt160" class="tgtSentence">Azure Rights Management 将日志作为一系列 Blob 写入。</caps:sentence>
                <caps:sentence sentenceid="849f99dcee9c854baad8567459e0bb57" id="tgt161" class="tgtSentence"> 每个 Blob 包含一条或多条日志记录，采用 W3C 扩展日志格式。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="4be416dbd6b1c6c9fdd6db68cd25891a" id="tgt162" class="tgtSentence">每个 Blob 的名称是数字。</caps:sentence>
                <caps:sentence sentenceid="bab04283fb61bba2066b10e31cbc7125" id="tgt163" class="tgtSentence"> 在每个日志容器内，第一个 Blob 命名为 000000001。</caps:sentence>
                <caps:sentence sentenceid="e295b69afd6e4e42d9c21c89e9431b2b" id="tgt164" class="tgtSentence"> 每个 Blob 按创建顺序依次命名。</caps:sentence>
                <caps:sentence sentenceid="da8bec5b9d6c692b080b65bf366fc392" id="tgt165" class="tgtSentence"> 每个 Blob 包含一条或多条日志记录。</caps:sentence>
                <caps:sentence sentenceid="904e47a34f54f0bf428830e8401017f4" id="tgt166" class="tgtSentence"> 每条日志记录具有一个 UTC 时间戳，指示 Azure Rights Management 何时处理相应请求。</caps:sentence>
              </para>
              <alert class="important">
                <para>
                  <caps:sentence sentenceid="5619bfc871913e3ecb396657c2eafd5e" id="tgt167" class="tgtSentence">Azure Rights Management 日志记录系统经过优化，可快速为你提供日志，而不必严格遵循顺序。</caps:sentence>
                  <caps:sentence sentenceid="f4c6881f9682fee7a503927d15db1337" id="tgt168" class="tgtSentence"> Blob 的顺序以及 Blob 内部日志记录的顺序可能不符合时间顺序。</caps:sentence>
                  <caps:sentence sentenceid="d2c9c82195b2d281352be1db2bdd3b16" id="tgt169" class="tgtSentence"> 按顺序命名 Blob 的唯一原因是让你能够以增量方式高效下载它们。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="99b9220c634dcc8a1ac47d3cf45fde4f" id="tgt170" class="tgtSentence">可能的日志序列结果的两个示例：</caps:sentence>
                </para>
                <list class="bullet">
                  <listItem>
                    <para>
                      <caps:sentence sentenceid="32d327dda5a57377d319815aac313094" id="tgt171" class="tgtSentence">Blob 000000004 中的日志记录可能与 Blob 000000003 中的日志记录在时间上重叠。</caps:sentence>
                      <caps:sentence sentenceid="16adaee22ba7fb49c30415e9524f8809" id="tgt172" class="tgtSentence"> 在极端情况下，Blob 000000004 中的所有日志记录可能已在 Blob 000000003 中的所有日志记录之前生成。</caps:sentence>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence sentenceid="a1c47894a7d84af2504670c499f850ab" id="tgt173" class="tgtSentence">Blob 中的第二个日志记录可能在第一个日志记录之前生成，但按照相反顺序写入存储。</caps:sentence>
                    </para>
                  </listItem>
                </list>
              </alert>
              <para>
                <caps:sentence sentenceid="d20929dce36bf83c8f3f9ed07baadf7d" id="tgt174" class="tgtSentence">在分析 Azure Rights Management 使用日志之前，建议你将日志下载和导入到存储库，并可以在存储库中按时间戳对日志进行排序。</caps:sentence>
                <caps:sentence sentenceid="77347467dd6745402b703834fc0b51d9" id="tgt175" class="tgtSentence"> 有关如何下载日志的详细信息，请参阅本主题中的<link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_AccesAndUseLogs">How to access and use your RMS logs</link>部分。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="0d70986d8572ca17541727a8ad3ef988" id="tgt176" class="tgtSentence">虽然日志并非一定遵循时间顺序，但大多数日志在请求后 15 分钟内写入，因此在使用时间戳识别所需的日志时，请将你感兴趣的日志的时间加上 15 分钟，</caps:sentence>
                <caps:sentence sentenceid="beb7275f545b4fbdf1374a5e606cadef" id="tgt177" class="tgtSentence"> 然后再下载这些日志。</caps:sentence>
                <caps:sentence sentenceid="1f5cfe1809f5fc07cd1f2b6b6ee41564" id="tgt178" class="tgtSentence"> 这种策略会确保你获取几乎所有日志。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="a49c0edb5f6cfe662144b7446c8b5dc1" id="tgt179" class="tgtSentence">另外请记住，每条日志记录上的时间戳是处理请求的 Azure Rights Management 服务的本地时间。</caps:sentence>
                <caps:sentence sentenceid="dfd9efa77e5d10a18367ea08d49e4ce7" id="tgt180" class="tgtSentence"> 由于 Azure Rights Management 在跨多个数据中心的多个服务器上运行，有时日志即使是按时间戳排序，也似乎并不符合时间顺序。</caps:sentence>
                <caps:sentence sentenceid="9f772490464a359c30951736522b13bb" id="tgt181" class="tgtSentence"> 不过这种差异很小，通常在一分钟之内。</caps:sentence>
                <caps:sentence sentenceid="2b14f022b1ea127f004c96605eabe8cd" id="tgt182" class="tgtSentence"> 大多数情况下，这不会为日志分析带来麻烦。</caps:sentence>
              </para>
            </content>
          </section>
          <section>
            <title>
              <caps:sentence sentenceid="b716ed2ff4bbdc28ad05a88c1bd6ef67" id="tgt183" class="tgtSentence">Blob 格式</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="e1ef66cad9113ac795b0758e4bdcb469" id="tgt184" class="tgtSentence">所有 Blob 都采用 W3C 扩展日志格式。</caps:sentence>
                <caps:sentence sentenceid="b6a8e711017a3a12b539d70ad55cfb46" id="tgt185" class="tgtSentence"> 开头是以下两行：</caps:sentence>
              </para>
              <para>
                <ui>
                  <caps:sentence sentenceid="5ad5720222f32901e83d695efdb60fdc" id="tgt186" class="tgtSentence">#Software:RMS</caps:sentence>
                </ui>
              </para>
              <para>
                <ui>
                  <caps:sentence sentenceid="192bc742f8b27706156989e005e0fd25" id="tgt187" class="tgtSentence">#Version:1.1</caps:sentence>
                </ui>
              </para>
              <para>
                <caps:sentence sentenceid="7b95b0a04ea8dc37bef830c98394e714" id="tgt188" class="tgtSentence">第一行标识这些是 Azure Rights Management 日志。</caps:sentence>
                <caps:sentence sentenceid="db31192c1615db5368dcb3847d1bbc05" id="tgt189" class="tgtSentence"> 第二行标识 Blob 的剩余部分遵循版本 1.1 规范。</caps:sentence>
                <caps:sentence sentenceid="9140d350f4ea24befc6eab451f07b3c8" id="tgt190" class="tgtSentence"> 我们建议，用于解析这些日志的任何应用程序都应先验证这两行，然后再继续解析 Blob 的剩余部分。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="a6c667f34d05c92e449cb9aeeec93866" id="tgt191" class="tgtSentence">第三行枚举字段名称列表，以制表符分隔：</caps:sentence>
              </para>
              <para>
                <ui>
                  <caps:sentence sentenceid="5cd553c8da6146368f025e5057f98153" id="tgt192" class="tgtSentence">#字段：date            time            row-id        request-type           user-id       result          correlation-id          content-id                owner-email           issuer                     template-id             file-name                  date-published      c-info         c-ip</caps:sentence>
                </ui>
              </para>
              <para>
                <caps:sentence sentenceid="4d30c7bd9fcb5e1bac3dcb04da02cd2c" id="tgt193" class="tgtSentence">后面的每行都是日志记录。</caps:sentence>
                <caps:sentence sentenceid="fa86655907b6c76ab4396fb8f95d07b0" id="tgt194" class="tgtSentence"> 这些字段的值与前一行具有相同的顺序，并且以制表符分隔。</caps:sentence>
                <caps:sentence sentenceid="fa151854dac81720c6345842152915a9" id="tgt195" class="tgtSentence"> 请使用下表分析这些字段。</caps:sentence>
              </para>
              <table>
                <thead>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="bfaad773361a781112fb325b433d54f7" id="tgt196" class="tgtSentence">字段名称</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="75d51135c88c7a73f17807636b6af548" id="tgt197" class="tgtSentence">W3C 数据类型</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="67daf92c833c41c95db874e18fcb2786" id="tgt198" class="tgtSentence">说明</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="6bad7e8404558aafa56e9b15195bba76" id="tgt199" class="tgtSentence">示例值</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="5fc732311905cb27e82d67f4f6511f7f" id="tgt200" class="tgtSentence">date</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="5fc732311905cb27e82d67f4f6511f7f" id="tgt201" class="tgtSentence">日期</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="290a4432650313b2fd9966ccbf5379a7" id="tgt202" class="tgtSentence">为请求提供服务时的 UTC 日期。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="c894aaf8f5afdd71b59ba77d58800659" id="tgt203" class="tgtSentence">源是为请求提供服务的服务器上的本地时钟。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="c926349b55a58d87d7d5008c349fd1e9" id="tgt204" class="tgtSentence">2013-06-25</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="07cc694b9b3fc636710fa08b6922c42b" id="tgt205" class="tgtSentence">time</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="07cc694b9b3fc636710fa08b6922c42b" id="tgt206" class="tgtSentence">时间</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="fb234cc46d733196ccc085ecb40a14b4" id="tgt207" class="tgtSentence">为请求提供服务时的 UTC 时间（24 小时格式）。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="c894aaf8f5afdd71b59ba77d58800659" id="tgt208" class="tgtSentence">源是为请求提供服务的服务器上的本地时钟。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="f2e1a047ebad38fc058d3858ca0a1fa3" id="tgt209" class="tgtSentence">21:59:28</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="c913fc70fcd84001d9bffc79a03a2895" id="tgt210" class="tgtSentence">row-id</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="1cb251ec0d568de6a929b520c4aed8d1" id="tgt211" class="tgtSentence">文本</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="edfc6e4c10780e0dcb1ce1bd46842611" id="tgt212" class="tgtSentence">此日志记录的唯一 GUID。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="1750772217daf898de93596558b1cd3b" id="tgt213" class="tgtSentence">在你整合日志或将日志复制为其他格式时，这个值是有用的。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="46ba6d7217f80efae3dd3bd6f906c673" id="tgt214" class="tgtSentence">1c3fe7a9-d9e0-4654-97b7-14fafa72ea63</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="e595e7b5d47e2070c3da3cd16bb822d2" id="tgt215" class="tgtSentence">request-type</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="b068931cc450442b63f5b3d276ea4297" id="tgt216" class="tgtSentence">Name</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a03c4131e5a4c3ad0034ede12f427c48" id="tgt217" class="tgtSentence">所请求的 RMS API 的名称。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="96378d61537db78d2fcef81d104db1b0" id="tgt218" class="tgtSentence">AcquireLicense</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="e35c1a36e525c2e4642c43b55246de30" id="tgt219" class="tgtSentence">user-id</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="b45cffe084dd3d20d928bee85e7b0f21" id="tgt220" class="tgtSentence">String</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="ffe3d27ecb9bc4c4507df43f95c61966" id="tgt221" class="tgtSentence">发出请求的用户。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="e908e1289e34b2049c4a49c6dbbb699f" id="tgt222" class="tgtSentence">该值包括在单引号中。</caps:sentence>
                        <caps:sentence sentenceid="f76e0ef479d78d5bdd80c58d7aed7dc2" id="tgt223" class="tgtSentence"> 有些请求类型是匿名的，在这种情况下，该值为 ”。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="df088d1c17ac7e56eb0c7d28294a0234" id="tgt224" class="tgtSentence">‘joe@contoso.com’</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="b4a88417b3d0170d754c647c30b7216a" id="tgt225" class="tgtSentence">result</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="b45cffe084dd3d20d928bee85e7b0f21" id="tgt226" class="tgtSentence">String</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="3996930f607c6e99d8fb0f93244f7012" id="tgt227" class="tgtSentence">如果成功地为请求提供服务，则为‘Success’。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="ce3099faf273786d788f3ed672b17d11" id="tgt228" class="tgtSentence">如果为请求提供服务失败，则在单引号中显示错误类型。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="1cca321971ced8592af906efc27b381e" id="tgt229" class="tgtSentence">‘Success’</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="d5a8a8adae9301f8dbe37316f7789236" id="tgt230" class="tgtSentence">correlation-id</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="1cb251ec0d568de6a929b520c4aed8d1" id="tgt231" class="tgtSentence">文本</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="dfe31c18486351b9c432bebe29d6902d" id="tgt232" class="tgtSentence">在 RMS 客户端日志和服务器日志之间通用的针对给定请求的 GUID。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="687dee56059627a65f0ff294bb224375" id="tgt233" class="tgtSentence">此值有助于你解决客户端问题。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="8a91284e061849269f1e225d9d07565d" id="tgt234" class="tgtSentence">cab52088-8925-4371-be34-4b71a3112356</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="c3ef8a4c2cedff1a4883a1317efb026a" id="tgt235" class="tgtSentence">content-id</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="1cb251ec0d568de6a929b520c4aed8d1" id="tgt236" class="tgtSentence">文本</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="dd369f21803745039f8bff677781ad7d" id="tgt237" class="tgtSentence">包括在大括号中的 GUID，标识受保护内容（例如某个文档）。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="651d7ca32856b7e986e7fb687acd4575" id="tgt238" class="tgtSentence">只有当 request-type 为 AcquireLicense 时，此字段才具有值，对于其他所有请求类型，此字段都为空。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="cc6d3e06881a333d8845146c650c7198" id="tgt239" class="tgtSentence">{bb4af47b-cfed-4719-831d-71b98191a4f2}</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="0969b13c79ef7c7fe184856700ef9f72" id="tgt240" class="tgtSentence">owner-email</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="b45cffe084dd3d20d928bee85e7b0f21" id="tgt241" class="tgtSentence">String</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="6a53cc0ce1f0714291594191a937b7f7" id="tgt242" class="tgtSentence">文档所有者的电子邮件地址。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="d5ec8a4bd7af1123c82fd7c591995a69" id="tgt243" class="tgtSentence">alice@contoso.com</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="3e6c2bc1e7f7e5e8c450394c747a8e9f" id="tgt244" class="tgtSentence">issuer</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="b45cffe084dd3d20d928bee85e7b0f21" id="tgt245" class="tgtSentence">String</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="23464e55e6acca18a2e02c0281fe7d0c" id="tgt246" class="tgtSentence">文档发布者的电子邮件地址。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="5ecfaa04435c6480d9683e1b522d3afc" id="tgt247" class="tgtSentence">alice@contoso.com（或）FederatedEmail.4c1f4d-93bf-00a95fa1e042@contoso.onmicrosoft.com'</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="175e9aa26a4ac89070acf9151c51da1b" id="tgt248" class="tgtSentence">Template-id</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="b45cffe084dd3d20d928bee85e7b0f21" id="tgt249" class="tgtSentence">String</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="3faa3714d667d3ceb4b89663486c5cbc" id="tgt250" class="tgtSentence">用于保护文档的模板的 ID。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="018b4ce624d21e5282fd89091e995591" id="tgt251" class="tgtSentence">{6d9371a6-4e2d-4e97-9a38-202233fed26e}</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="9099dc152ffe017ba299615fe00d04f5" id="tgt252" class="tgtSentence">File-name</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="b45cffe084dd3d20d928bee85e7b0f21" id="tgt253" class="tgtSentence">String</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="4c76f189c2d4d54886e515d53b4e2052" id="tgt254" class="tgtSentence">已保护的文档的文件名。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="37ca0fcfb823fc4504d9848d8a6e89e0" id="tgt255" class="tgtSentence">TopSecretDocument.docx</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="f30a14e3cc27bc057596d0db3f9eb998" id="tgt256" class="tgtSentence">Date-published</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="5fc732311905cb27e82d67f4f6511f7f" id="tgt257" class="tgtSentence">日期</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="682b196208f96dab1e3b9b70c5c6e248" id="tgt258" class="tgtSentence">保护文档时的日期。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a2ba20bd3ab052aab51563792a59f836" id="tgt259" class="tgtSentence">2015-10-15T21:37:00</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="5b6328163b6ef0eea4f1ec530019ad5b" id="tgt260" class="tgtSentence">c-info</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="b45cffe084dd3d20d928bee85e7b0f21" id="tgt261" class="tgtSentence">String</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="a5c61b3f394e463f7ee6a65e982a4766" id="tgt262" class="tgtSentence">有关发出请求的客户端平台的信息。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="c0659eccdf72b83cae1a422cfb8bdc0f" id="tgt263" class="tgtSentence">特定字符串各不相同，具体取决于应用程序（例如操作系统或浏览器）。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="0f2eb0df9729384f4580302df40cda2f" id="tgt264" class="tgtSentence">'MSIPC;version=1.0.623.47;AppName=WINWORD.EXE;AppVersion=15.0.4753.1000;AppArch=x86;OSName=Windows;OSVersion=6.1.7601;OSArch=amd64'</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="1cb4a97a2657ad9a1798614c8bef28e8" id="tgt265" class="tgtSentence">c-ip</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="884d9804999fc47a3c2694e49ad2536a" id="tgt266" class="tgtSentence">Address</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="de22b98c0f158684d0bbc9454badfeb2" id="tgt267" class="tgtSentence">发出请求的客户端的 IP 地址。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="4038d61bb6d2b9a837f87ab3c72c4c16" id="tgt268" class="tgtSentence">64.51.202.144</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </tbody>
              </table>
            </content>
            <sections>
              <section>
                <title>
                  <caps:sentence sentenceid="3cb8dedc51daba8e4a2db1ce25397d8a" id="tgt269" class="tgtSentence">user-id 字段的例外</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence sentenceid="d8868e646ee8ab5943c7bec6fd05dc61" id="tgt270" class="tgtSentence">虽然 user-id 字段通常指示发出请求的用户，但在两种例外情况下，该值不映射到真正用户：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="7201b8b926355623f1e91689e364f1e2" id="tgt271" class="tgtSentence">值 <ui>'microsoftrmsonline@&lt;YourTenantID&gt;.rms.&lt;region&gt;.aadrm.com'</ui>。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="d386a4c6b3a6428c2b7e40ba69c34c03" id="tgt272" class="tgtSentence">它指示 Office 365 服务（例如 Exchange Online 或 Sharepoint Online）正在发出请求。</caps:sentence>
                        <caps:sentence sentenceid="6f1035b36fe3077fdc7582a52da893ac" id="tgt273" class="tgtSentence"> 在字符串中，<placeholder>&lt;YourTenantID&gt;</placeholder> 是你租户的 GUID，<placeholder>&lt;region&gt;</placeholder> 是你租户注册的区域。</caps:sentence>
                        <caps:sentence sentenceid="4eee3758f1bf4073d94deae936dd0a13" id="tgt274" class="tgtSentence"> 例如，<ui>na</ui> 代表北美，<ui>eu</ui> 代表欧洲，<ui>ap</ui> 代表亚洲。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="a5d54aa5eab26158b954d81318fdc046" id="tgt275" class="tgtSentence">如果你使用 RMS 连接器。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="ff8ccbcb09372ec9fdccd9cf5d9db36b" id="tgt276" class="tgtSentence">此连接器发出的请求将使用服务主体名称来进行记录，该名称是 RMS 在你安装 RMS 连接器时自动生成的。</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </content>
              </section>
              <section>
                <title>
                  <caps:sentence sentenceid="e5d03ec9c876cea77efaaaa6b8c32957" id="tgt277" class="tgtSentence">典型请求类型</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence sentenceid="696555a11237c723e42eb304ff698e39" id="tgt278" class="tgtSentence">Azure Rights Management 中有很多请求类型，但下表列出了其中一些最常用的请求类型。</caps:sentence>
                  </para>
                  <table>
                    <thead>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="334cdaea3eadb364d4d70cdf2c1ba190" id="tgt279" class="tgtSentence">请求类型</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="67daf92c833c41c95db874e18fcb2786" id="tgt280" class="tgtSentence">说明</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="96378d61537db78d2fcef81d104db1b0" id="tgt281" class="tgtSentence">AcquireLicense</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="fb39ef7d90067cd5a33d07376e4b78fe" id="tgt282" class="tgtSentence">基于 Windows 的计算机上的客户端为受 RMS 保护的内容请求许可证。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="63e3a6c5da909ad29bdda18879f82033" id="tgt283" class="tgtSentence">AcquirePreLicense</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="0b997288f6b3696891ca22bf8f1a04bd" id="tgt284" class="tgtSentence">客户端代表用户为受 RMS 保护的内容请求许可证。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="0cd119a21477936392dd8833ff8a0cb0" id="tgt285" class="tgtSentence">AcquireTemplates</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="d21c8ab4a79fdb2819581cd41dac15d1" id="tgt286" class="tgtSentence">进行调用以基于模板 ID 获取模板 </caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="8b4ab876b775930408161069425da90c" id="tgt287" class="tgtSentence">AcquireTemplateInformation</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="48e43feafa7b101a45b17a2317e34488" id="tgt288" class="tgtSentence">进行调用以从服务获取模板的 ID。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="de8b5ce9105c2d038271d81244867b0e" id="tgt289" class="tgtSentence">AddTemplate</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="f00fb2ec9992581d7599908fc1b3aac7" id="tgt290" class="tgtSentence">从 Azure 经典门户进行调用以添加模板。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="925650923c3c094868130f694440ea20" id="tgt291" class="tgtSentence">BECreateEndUserLicenseV1</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="63acce0fedee037357eccf3a2e2158c4" id="tgt292" class="tgtSentence">从移动设备进行调用以创建最终用户许可证。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="8897e225dceab3211ccaaea877f2fe54" id="tgt293" class="tgtSentence">BEGetAllTemplatesV1</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="9cbcbf5d61fe10fd9dcd1236efd6bb20" id="tgt294" class="tgtSentence">从移动设备（后端）进行调用以获取所有模板。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="b3fdd34850de16ddfa25719207b31b1c" id="tgt295" class="tgtSentence">Certify</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="401da8fd74102aafdde063d5b9c5f18f" id="tgt296" class="tgtSentence">客户端正在认证要保护的内容。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="9a2d8ce3ffdcdf2123bddd94d79ef200" id="tgt297" class="tgtSentence">Decrypt</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="b79e84626a4a59644684284b3e47352a" id="tgt298" class="tgtSentence">客户端正在尝试解密受 RMS 保护的内容。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="b5d5255406e5df0b5d67f35cd19d9d90" id="tgt299" class="tgtSentence">DeleteTemplateById</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="7dd6302deff16b57ea00f080c80c4463" id="tgt300" class="tgtSentence">从 Azure 经典门户进行调用以按模板 ID 删除模板。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="10b4933ca977180a3654cfaa8374e898" id="tgt301" class="tgtSentence">ExportTemplateById</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="91ab68a7a376ec114368344ed2f9f24c" id="tgt302" class="tgtSentence">从 Azure 经典门户进行调用以基于模板 ID 导出模板。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="957732255564a6c083ed77bbe2a48e55" id="tgt303" class="tgtSentence">FECreateEndUserLicenseV1</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="51c0c6ce7eb790bd55c39d3bbff5e9bd" id="tgt304" class="tgtSentence">类似于 AcquireLicense 请求，但来自移动设备。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="9fe26a3667ed1dc4b922544eff399527" id="tgt305" class="tgtSentence">FECreatePublishingLicenseV1</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="671360ade676ffa6abe865349bd4222a" id="tgt306" class="tgtSentence">与 Certify 和 GetClientLicensorCert 组合请求相同，来自移动客户端。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="be170906f7b85bf209878794503fb88c" id="tgt307" class="tgtSentence">FEGetAllTemplates</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="43d902653c9f38fa6598321b065fa1df" id="tgt308" class="tgtSentence">从移动设备（前端）进行调用以获取模板。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="bf96a4a7636509cbd02714a73edecddf" id="tgt309" class="tgtSentence">GetAllTemplates</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="5d117e62fc32890c49d4715d1126e7bc" id="tgt310" class="tgtSentence">从 Azure 经典门户进行调用以获取所有模板。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="9fb6765eeb3de2bbfaa48da6ac7e0bf5" id="tgt311" class="tgtSentence">GetClientLicensorCert</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="902a53f30cbf49cdf2627022aff6527f" id="tgt312" class="tgtSentence">客户端正在从基于 Windows 的计算机请求发布证书（随后用于保护内容）。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="4768e58106d46c69889899d955503a8a" id="tgt313" class="tgtSentence">GetConfiguration</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="96ca6781e326059494e6fcad6df6e618" id="tgt314" class="tgtSentence">调用 Azure PowerShell cmdlet 以获取 Azure RMS 租户的配置。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="7475941ce4f57a82c2c16e9925a9c51a" id="tgt315" class="tgtSentence">GetConnectorAuthorizations</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="f01baea35f04cd2df044d27eaf78f450" id="tgt316" class="tgtSentence">从 RMS 连接器进行调用以从云中获取其配置。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="7aead87288df2a51989244d9e87138d0" id="tgt317" class="tgtSentence">GetTenantFunctionalState </caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="e0847c988251dae1f4ad6b172ba0cbfd" id="tgt318" class="tgtSentence">Azure 经典门户检查是否已激活 Azure RMS。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="41a4dee8038bd0dff81e166a178c30ff" id="tgt319" class="tgtSentence">GetTemplateById</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="6bf9a128910b55589e4e9a162bbb73cf" id="tgt320" class="tgtSentence">从 Azure 经典门户进行调用以通过指定模板 ID 来获取模板。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="10b4933ca977180a3654cfaa8374e898" id="tgt321" class="tgtSentence">ExportTemplateById</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="ef804f168a0cc9dccbe9e8db14a72f02" id="tgt322" class="tgtSentence">从 Azure 经典门户进行调用以通过指定模板 ID 来导出模板。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="334f66ab7bb1e6a257d5b4b798606d5f" id="tgt323" class="tgtSentence">FindServiceLocationsForUser</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="e63ebce2b3e3fe64f60d3175d6c756f5" id="tgt324" class="tgtSentence">进行调用以查询 URL，使用该项来调用 Certify 或 AcquireLicense。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="24a443c03a3cec36d18a742fed7edeed" id="tgt325" class="tgtSentence">ImportTemplate</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="a3a925e8bdd3e270e5cfb0b2debd5411" id="tgt326" class="tgtSentence">从 Azure 经典门户进行调用以导入模板。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="6dc5fa8f8186ca3219fd19e3dbdefecd" id="tgt327" class="tgtSentence">ServerCertify</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="7cecacb069ed0aded29d3e084396a308" id="tgt328" class="tgtSentence">从已启用 RMS 的客户端（如 SharePoint）进行调用以认证服务器。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="6c632e47271c0bce1acf3e0ae085b5d8" id="tgt329" class="tgtSentence">SetUsageLogFeatureState</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="906f70ea4316763bdcc21a476bd64af4" id="tgt330" class="tgtSentence">进行调用以启用使用日志记录。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="d7fa965c06a6254a5830dfb4a49e94f3" id="tgt331" class="tgtSentence">SetUsageLogStorageAccount </caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="780ca9388c7f1ceda013318b6e8fc891" id="tgt332" class="tgtSentence">进行调用以指定 Azure RMS 日志的位置。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="4dfcdfef6c8e3bfaa444be440fb8f8cd" id="tgt333" class="tgtSentence">SignDigest</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="d79b10a3cd770c53259b85e8dd936666" id="tgt334" class="tgtSentence">在密钥用于签名目的时进行调用。</caps:sentence>
                            <caps:sentence sentenceid="49fb4a3b71498837be6e2fe05df14cc7" id="tgt335" class="tgtSentence"> 通常是针对每个 AcquireLicence（或 FECreateEndUserLicenseV1）、Certify 和 GetClientLicensorCert（或 FECreatePublishingLicenseV1）请求调用一次此项。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="7ef2e38a51e898044929dcdf8b795ef6" id="tgt336" class="tgtSentence">UpdateTemplate</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="c92d05b92ffb57612e4720ccd6725229" id="tgt337" class="tgtSentence">从 Azure 经典门户进行调用以更新现有模板。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </tbody>
                  </table>
                </content>
              </section>
            </sections>
          </section>
        </sections>
      </section>
      <section address="BKMK_PowerShell">
        <title>
          <caps:sentence sentenceid="c66e6fd3bb5af5f69c506be526e0dc22" id="tgt338" class="tgtSentence">Windows PowerShell 参考</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="73dbf3a08a2c5d59edca127ae1b6ef38" id="tgt339" class="tgtSentence">使用以下 Windows PowerShell cmdlet 帮助你配置和使用 Azure Rights Management 使用日志记录：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence sentenceid="d0dc480c108ffb261a38cd1e05486b0a" id="tgt340" class="tgtSentence">Disable-AadrmUsageLogFeature</caps:sentence>
                  </linkText>
                  <linkUri>https://msdn.microsoft.com/library/azure/dn629404.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence sentenceid="f704ebefdaf11d1921d30b5ff10db15f" id="tgt341" class="tgtSentence">Enable-AadrmUsageLogFeature</caps:sentence>
                  </linkText>
                  <linkUri>https://msdn.microsoft.com/library/azure/dn629421.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence sentenceid="5a8eb9f853ac69882dfa45452cf339bb" id="tgt342" class="tgtSentence">Get-AadrmUsageLog</caps:sentence>
                  </linkText>
                  <linkUri>https://msdn.microsoft.com/library/azure/dn629401.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence sentenceid="4d76b38660f9d40beabed289b8475c97" id="tgt343" class="tgtSentence">Get-AadrmUsageLogFeature</caps:sentence>
                  </linkText>
                  <linkUri>https://msdn.microsoft.com/library/azure/dn629425.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence sentenceid="ac9424114a8cf868df88962200a8e66d" id="tgt344" class="tgtSentence">Get-AadrmUsageLogLastCounterValue</caps:sentence>
                  </linkText>
                  <linkUri>https://msdn.microsoft.com/library/azure/dn629423.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence sentenceid="5f42906261cc1ff100bce385571754cb" id="tgt345" class="tgtSentence">Get-AadrmUsageLogStorageAccount</caps:sentence>
                  </linkText>
                  <linkUri>https://msdn.microsoft.com/library/azure/dn629419.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence sentenceid="da1309c8f2b2998e31604fcd9fc38101" id="tgt346" class="tgtSentence">Set-AadrmUsageLogStorageAccount</caps:sentence>
                  </linkText>
                  <linkUri>https://msdn.microsoft.com/library/azure/dn629426.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="1c07190b9bbb271003793d10b987f8e4" id="tgt347" class="tgtSentence">有关使用适用于 Azure Rights Management 的 Windows PowerShell 的详细信息，请参阅<link xlink:href="a890e04a-4b70-41b5-8d5f-3c210a669faa">Administering Azure Rights Management by Using Windows PowerShell</link>。</caps:sentence>
          </para>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="18564e4a-9364-4ed2-8f17-89d24fc0d878">Using rights management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSTarget>
  <caps:SxSSource locale="en-US">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence id="src1" class="srcSentence">Use the information in this topic to help you understand how you can use usage logging with Azure Rights Management (Azure RMS).</caps:sentence>
          <caps:sentence id="src2" class="srcSentence"> The Azure Rights Management service can log every request that it makes for your organization, which includes requests from users, actions performed by Rights Management administrators in your organization, and actions performed by Microsoft operators to support your Azure Rights Management deployment.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src3" class="srcSentence">You can then use these Azure Rights Management logs to support the following business scenarios:</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <caps:sentence id="src4" class="srcSentence">Analyze for business insights.</caps:sentence>
            </para>
            <para>
              <caps:sentence id="src5" class="srcSentence">Azure Rights Management writes logs in W3C extended log format into an Azure storage account that you provide.</caps:sentence>
              <caps:sentence id="src6" class="srcSentence"> You can then direct these logs into a repository of your choice (such as a database, an online analytical processing (OLAP) system, or a map-reduce system) to analyze the information and produce reports.</caps:sentence>
              <caps:sentence id="src7" class="srcSentence"> As an example, you could identify who is accessing your RMS-protected data.</caps:sentence>
              <caps:sentence id="src8" class="srcSentence"> You can determine what RMS-protected data people are accessing, and from what devices and from where.</caps:sentence>
              <caps:sentence id="src9" class="srcSentence"> You can find out whether people can successfully read protected content.</caps:sentence>
              <caps:sentence id="src10" class="srcSentence"> You can also identify which people have read an important document that was protected.</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence id="src11" class="srcSentence">Monitor for abuse.</caps:sentence>
            </para>
            <para>
              <caps:sentence id="src12" class="srcSentence">Azure Rights Management logging information is available to you in near-real time, so that you can continuously monitor your company’s use of Rights Management .</caps:sentence>
              <caps:sentence id="src13" class="srcSentence"> 99.9% of logs are available within 15 minutes of an RMS-initiated action.</caps:sentence>
            </para>
            <para>
              <caps:sentence id="src14" class="srcSentence">For example, you might want to be alerted if there is a sudden increase of people reading RMS-protected data outside standard working hours, which could indicate that a malicious user is collecting information to sell to competitors.</caps:sentence>
              <caps:sentence id="src15" class="srcSentence"> Or, if the same user apparently accesses data from two different IP addresses within a short time frame, which could indicate that a user account has been compromised.</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence id="src16" class="srcSentence">Perform forensic analysis.</caps:sentence>
            </para>
            <para>
              <caps:sentence id="src17" class="srcSentence">If you have an information leak, you are likely to be asked who recently accessed specific documents and what information did a suspected person access recently.</caps:sentence>
              <caps:sentence id="src18" class="srcSentence"> You can answer these type of questions when you use Azure Rights Management and logging because people who use protected content must always get a Rights Management license to open documents and pictures that are protected by Azure Rights Management, even if these files are moved by email or copied to USB drives or other storage devices.</caps:sentence>
              <caps:sentence id="src19" class="srcSentence"> This means that you can use Azure Rights Management logs as a definitive source of information for forensic analysis when you protect your data by using Azure Rights Management.</caps:sentence>
            </para>
          </listItem>
        </list>
        <alert class="note">
          <para>
            <caps:sentence id="src20" class="srcSentence">If you are interested only in the logging of administrative tasks for Azure Rights Management, and do not want to track how users are using Rights Management, you can use the <externalLink><linkText>Get-AadrmAdminLog</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629430.aspx</linkUri></externalLink> Windows PowerShell cmdlet for Azure Rights Management.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src21" class="srcSentence">You can also use the Azure classic portal for high-level usage reports that include <ui>RMS usage</ui>, <ui>Most active RMS users</ui>, <ui>RMS device usage</ui>, and <ui>RMS enabled application usage</ui>.</caps:sentence>
            <caps:sentence id="src22" class="srcSentence"> To access these reports from the Azure classic portal, click <ui>Active Directory</ui>, select and open a directory, and then click <ui>REPORTS</ui>,</caps:sentence>
          </para>
        </alert>
        <para>
          <caps:sentence id="src23" class="srcSentence">Use the following sections for more information about Azure Rights Management usage logging.</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_EnableRMSLogging">How to enable RMS logging</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_AccesAndUseLogs">How to access and use your RMS logs</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_ManageStorage">How to manage your RMS log storage</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_Delegate">How to delegate access to your RMS logs</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_Interpret">How to interpret your RMS logs</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_PowerShell">Windows PowerShell reference</link>
            </para>
          </listItem>
        </list>
      </introduction>
      <section address="BKMK_EnableRMSLogging">
        <title>
          <caps:sentence id="src24" class="srcSentence">How to enable Azure Rights Management usage logging</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src25" class="srcSentence">Azure Rights Management usage logging is optional, so if you want to use it, you must take specific steps.</caps:sentence>
            <caps:sentence id="src26" class="srcSentence"> When you use Azure Rights Management usage logging, there is no change in how  Rights Management works and the logging process itself is free.</caps:sentence>
            <caps:sentence id="src27" class="srcSentence"> However, you must provide an Azure storage account for the logs and you will be charged for this storage.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src28" class="srcSentence">Before you begin, make sure that you meet the following prerequisites to use Azure Rights Management usage logging:</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src29" class="srcSentence">Requirement</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src30" class="srcSentence">More information</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src31" class="srcSentence">An IT-managed subscription that includes Azure Rights Management</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src32" class="srcSentence">You must have a Microsoft Azure Rights Management subscription that is managed by your organization.</caps:sentence>
                    <caps:sentence id="src33" class="srcSentence"> Organizations that use RMS for individuals cannot use Azure Rights Management usage logging.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src34" class="srcSentence">If your organization has users who use RMS for individuals, Azure Rights Management usage logging provides a very compelling business reason to convert RMS for individuals into a Microsoft Azure Rights Management subscription.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src35" class="srcSentence">For more information about the subscriptions that include Azure RMS, see the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link> section in the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link> topic.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src36" class="srcSentence">For more information about RMS for individuals, see <link xlink:href="2efcb440-fefd-45e9-872b-f471573aadf2">RMS for Individuals and Azure Rights Management</link></caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src37" class="srcSentence">Azure subscription</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src38" class="srcSentence">You must have a subscription to Azure and sufficient storage on Azure for your Azure Rights Management logs.</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src39" class="srcSentence">Windows PowerShell for Azure Rights Management</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src40" class="srcSentence">If you haven’t already done so, download and install the Windows PowerShell module for Azure Rights Management.</caps:sentence>
                    <caps:sentence id="src41" class="srcSentence"> You will use Windows PowerShell cmdlets to configure and manage your Azure Rights Management usage logs.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src42" class="srcSentence">For more information, see <link xlink:href="0d665ed6-b1de-4d63-854a-bc57c1c49844">Installing Windows PowerShell for Azure Rights Management</link>.</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
          <para>
            <caps:sentence id="src43" class="srcSentence">Use the following procedure to enable Azure Rights Management usage logging, which includes steps to create an Azure storage account and then configure Azure to use this storage account for your  Rights Management logs.</caps:sentence>
          </para>
          <alert class="note">
            <para>
              <caps:sentence id="src44" class="srcSentence">This procedure assumes that you have an Azure account.</caps:sentence>
              <caps:sentence id="src45" class="srcSentence"> Azure Rights Management usage logging supports individual accounts but as a best practice, use work or school accounts.</caps:sentence>
              <caps:sentence id="src46" class="srcSentence"> In addition, we recommend that you create a dedicated storage account for your Rights Management logs.</caps:sentence>
              <caps:sentence id="src47" class="srcSentence"> You must share the storage access keys with Azure Rights Management, and potentially with other people if they will also use the log files.</caps:sentence>
            </para>
            <para>
              <caps:sentence id="src48" class="srcSentence">For more information about Azure storage, see the <externalLink><linkText>Azure documentation for Storage</linkText><linkUri>http://azure.microsoft.com/documentation/services/storage/</linkUri></externalLink>.</caps:sentence>
            </para>
          </alert>
          <procedure>
            <title>
              <caps:sentence id="src49" class="srcSentence">How to create your storage account and enable Azure Rights Management usage logging</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src50" class="srcSentence">Sign in to the <externalLink><linkText>Azure portal</linkText><linkUri>https://portal.azure.com/</linkUri></externalLink>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src51" class="srcSentence">On the Hub menu, select <ui>New</ui> -&gt; <ui>Data + Storage</ui> -&gt; <ui>Storage account</ui>.</caps:sentence>
                  </para>
                  <alert class="tip">
                    <para>
                      <caps:sentence id="src52" class="srcSentence">If you do not see this option, check that you have an Azure subscription in addition to your subscription for Rights Management.</caps:sentence>
                    </para>
                  </alert>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src53" class="srcSentence">Keep the default deployment model of <ui>Classic</ui>, and then click <ui>Create</ui>.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src54" class="srcSentence">Specify the name for your storage account, and if necessary, change the selected options for the <ui>Pricing tier</ui>, <ui>Resource Group</ui>, <ui>Subscription</ui>, and whether to <ui>Pin to dashboard</ui>.</caps:sentence>
                    <caps:sentence id="src55" class="srcSentence"> and then click <ui>CREATE</ui>.</caps:sentence>
                    <caps:sentence id="src56" class="srcSentence"> Wait for the <ui>Creating Storage Account</ui> activity to complete.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src57" class="srcSentence">Click the newly created storage account, and then click <ui>Settings</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src58" class="srcSentence">In the <ui>Settings</ui> blade, click the <ui>Keys</ui> icon.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src59" class="srcSentence">In the <ui>Manage keys</ui> blade, copy the value of the  <ui>PRIMARY ACCESS KEY</ui>  and close the blade.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src60" class="srcSentence">Start Windows PowerShell with the <ui>Run as administrator</ui> option.</caps:sentence>
                    <caps:sentence id="src61" class="srcSentence"> Run the <externalLink><linkText>Connect-AadrmService</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629415.aspx</linkUri></externalLink> command to connect to the Azure Rights Management service:</caps:sentence>
                  </para>
                  <code>Connect-AadrmService</code>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src62" class="srcSentence">Use the <externalLink><linkText>Set-AadrmUsageLogStorageAccount</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629426.aspx</linkUri></externalLink> command to specify where you want to keep your Azure Rights Management usage logs, replacing <placeholder>&lt;Access_Key&gt;</placeholder> with the primary access key that you copied in step 6 and <placeholder>&lt;StorageAccount&gt;</placeholder> with the name of the storage account that you created in step 3:</caps:sentence>
                  </para>
                  <code>$accesskey = convertto-securestring -asplaintext -force –string <placeholder xmlns="">&lt;Access_Key&gt;</placeholder> Set-AadrmUsageLogStorageAccount -AccessKey $accesskey -StorageAccount <placeholder xmlns="">&lt;StorageAccount&gt;</placeholder></code>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src63" class="srcSentence">Use the <externalLink><linkText>Enable-AadrmUsageLogFeature</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629421.aspx</linkUri></externalLink> command to enable Azure Rights Management usage logging:</caps:sentence>
                  </para>
                  <code>Enable-AadrmUsageLogFeature</code>
                  <para>
                    <caps:sentence id="src64" class="srcSentence">You should see the message: <ui>The usage log feature is enabled for the Rights management service.</ui></caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence id="src65" class="srcSentence">Now that usage logging is enabled, Azure Rights Management starts to log all actions for your organization and saves this information to your storage account.</caps:sentence>
                  <caps:sentence id="src66" class="srcSentence"> Logging information is not available before this point.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src67" class="srcSentence">For more information about how to create storage accounts, see the  <externalLink><linkText>Create a storage account</linkText><linkUri>https://azure.microsoft.com/documentation/articles/storage-create-storage-account/#create-a-storage-account</linkUri></externalLink> section from the <externalLink><linkText>About Azure storage accounts</linkText><linkUri>https://azure.microsoft.com/documentation/articles/storage-create-storage-account/</linkUri></externalLink> in the Azure documentation.</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
        </content>
      </section>
      <section address="BKMK_AccesAndUseLogs">
        <title>
          <caps:sentence id="src68" class="srcSentence">How to access and use your Azure Rights Management usage logs</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src69" class="srcSentence">Azure Rights Management writes logs to your Azure storage account as a series of blobs.</caps:sentence>
            <caps:sentence id="src70" class="srcSentence"> Each blob contains one or more log records, in W3C extended log format.</caps:sentence>
            <caps:sentence id="src71" class="srcSentence"> The blob names are numbers, in the order in which they were created.</caps:sentence>
            <caps:sentence id="src72" class="srcSentence"> The <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_Interpret">How to interpret the RMS logs</link> section later in this document contains more information about the log contents and their creation.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src73" class="srcSentence">It can take a while for logs to appear in your storage account after an Azure Rights Management action.</caps:sentence>
            <caps:sentence id="src74" class="srcSentence"> Most logs appear within 15 minutes.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src75" class="srcSentence">The storage account that you created for your Azure Rights Management usage logs is like a mailbox and supports reading directly from the storage account, but it is not optimized to be used in this way.</caps:sentence>
            <caps:sentence id="src76" class="srcSentence"> Instead, for best performance and to help reduce costs, we recommend that you download the logs to local storage, such as a local folder, a database, or a map-reduce repository.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src77" class="srcSentence">You can download your usage logs in two ways:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src78" class="srcSentence">Use the Windows PowerShell cmdlet <externalLink><linkText>Get-AadrmUsageLog</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629401.aspx</linkUri></externalLink>.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src79" class="srcSentence">This is the simplest way to access your usage logs.</caps:sentence>
                <caps:sentence id="src80" class="srcSentence"> This cmdlet downloads logs to your computer, downloading each blob as a file to a location that you specify.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src81" class="srcSentence">Use the <externalLink><linkText>Azure Storage SDK</linkText><linkUri>http://www.windowsazure.com/en-us/develop/net/</linkUri></externalLink> to write your own custom application to download the logs.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src82" class="srcSentence">A custom application can provide more flexibility than the Get-AadrmUsageLogs cmdlet.</caps:sentence>
                <caps:sentence id="src83" class="srcSentence"> For example, you might want to delegate the download of logs to somebody or a process that must not use your Azure Rights Management administrative credentials.</caps:sentence>
                <caps:sentence id="src84" class="srcSentence"> Or, you might want to poll the logs in real time because you want to monitor for misuse.</caps:sentence>
              </para>
            </listItem>
          </list>
          <procedure>
            <title>
              <caps:sentence id="src85" class="srcSentence">To download your usage logs by using PowerShell</caps:sentence>
            </title>
            <steps class="bullet">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src86" class="srcSentence">Start Windows PowerShell with the <ui>Run as administrator</ui> option and run <userInput>Get-AadrmUsageLog –Path &lt;location&gt;</userInput>.</caps:sentence>
                    <caps:sentence id="src87" class="srcSentence"> For example, after creating a folder named <system>logs</system> on your E drive:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src88" class="srcSentence">To download all available logs to your E:\logs folder: <codeInline>Get-AadrmUsageLog -Path "e:\logs"</codeInline></caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src89" class="srcSentence">To download a specific range of blobs: <codeInline>Get-AadrmUsageLog –Path "e:\logs" –FromCounter 1024 –ToCounter 2047</codeInline></caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence id="src90" class="srcSentence">When you run these cmdlets, Windows PowerShell displays the name of the last blob that was downloaded.</caps:sentence>
                  <caps:sentence id="src91" class="srcSentence"> You can assign this name to a variable, which lets you run Get-AadrmUsageLog in a loop or a schedule job, downloading only the incremental logs each time.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src92" class="srcSentence">For example:  </caps:sentence>
                </para>
                <para>
                  <ui>
                    <caps:sentence id="src93" class="srcSentence">PS C:\&gt; $LastBlobName = Get-AadrmUsageLog –Path "e:\logs"</caps:sentence>
                  </ui>
                </para>
                <para>
                  <ui>
                    <caps:sentence id="src94" class="srcSentence">1527</caps:sentence>
                  </ui>
                </para>
                <para>
                  <ui>
                    <caps:sentence id="src95" class="srcSentence">PS C:\&gt; $LastBlobName</caps:sentence>
                  </ui>
                </para>
                <para>
                  <ui>
                    <caps:sentence id="src96" class="srcSentence">1527</caps:sentence>
                  </ui>
                </para>
              </content>
            </conclusion>
          </procedure>
          <alert class="tip">
            <para>
              <caps:sentence id="src97" class="srcSentence">You can aggregate all your downloaded log files into a CSV format by using <externalLink><linkText>Microsoft’s Log Parser</linkText><linkUri>http://www.microsoft.com/download/details.aspx?id=24659</linkUri></externalLink>, which is a tool to convert between various well-known log formats.</caps:sentence>
              <caps:sentence id="src98" class="srcSentence"> You can also use this tool to convert data to SYSLOG format, or import it into a database.</caps:sentence>
              <caps:sentence id="src99" class="srcSentence"> After you have installed the tool, run <userInput>LogParser.exe /?</userInput> for help and information to use this tool.</caps:sentence>
              <caps:sentence id="src100" class="srcSentence"> For example, you might run the following command to import all information into a .log file format: <userInput>logparser –i:w3c –o:csv “SELECT * INTO AllLogs.csv FROM *.log”</userInput>.</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence id="src101" class="srcSentence">You can suspend and resume usage logging.</caps:sentence>
            <caps:sentence id="src102" class="srcSentence"> When you suspend logging, Azure Rights Management retains your storage account information, so that you can easily resume logging again.</caps:sentence>
          </para>
          <procedure>
            <title>
              <caps:sentence id="src103" class="srcSentence">To suspend and resume usage logging</caps:sentence>
            </title>
            <steps class="bullet">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src104" class="srcSentence">To suspend logging, use the following cmdlet: <externalLink><linkText>Disable-AadrmUsageLogFeature</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629404.aspx</linkUri></externalLink></caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src105" class="srcSentence">To resume logging, use the following cmdlet: <externalLink><linkText>Enable-AadrmUsageLogFeature</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629421.aspx</linkUri></externalLink></caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src106" class="srcSentence">To check whether logging is enabled or disabled, use the following cmdlet: <externalLink><linkText>Get-AadrmUsageLogFeature</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629425.aspx</linkUri></externalLink></caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src107" class="srcSentence">A value of <ui>True</ui> means that usage logging is enabled for Azure Rights Management and a value of <ui>False</ui> means that usage logging is disabled.</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
          </procedure>
        </content>
      </section>
      <section address="BKMK_ManageStorage">
        <title>
          <caps:sentence id="src108" class="srcSentence">How to manage your Azure Rights Management log storage</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src109" class="srcSentence">You are charged for the storage space that is used to keep your Azure Rights Management logs.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src110" class="srcSentence">Azure Rights Management does no automatic management of your usage log files.</caps:sentence>
            <caps:sentence id="src111" class="srcSentence"> If you take no action, they will remain in your storage account.</caps:sentence>
            <caps:sentence id="src112" class="srcSentence"> However, to conserve space and reduce storage costs, you might want to delete them after you have downloaded them.</caps:sentence>
            <caps:sentence id="src113" class="srcSentence"> Or you can choose which files to delete.</caps:sentence>
            <caps:sentence id="src114" class="srcSentence"> With one exception, Azure Rights Management does not use these log files, so there are no restrictions about when you can delete them.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src115" class="srcSentence">The file that you must not delete (or modify) is named <ui>metadata</ui> that is in the <ui>rms-metadata</ui> container.</caps:sentence>
            <caps:sentence id="src116" class="srcSentence"> Azure Rights Management uses this blob to keep track of the last blob number that it used.</caps:sentence>
            <caps:sentence id="src117" class="srcSentence"> If this file is deleted, Azure Rights Management starts a new container for logs, with a blob number that starts from 1, and all future downloads that use the Get-AadrmUsageLog cmdlet use this new container to download log files.</caps:sentence>
            <caps:sentence id="src118" class="srcSentence"> As a result, any logs in the original container are retained, but orphaned.</caps:sentence>
            <caps:sentence id="src119" class="srcSentence"> The only way to download these orphaned logs is to use the Azure storage SDK.</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence id="src120" class="srcSentence">Instead of managing your Azure Rights Management log storage yourself, you can delegate this management function to another company by sharing your storage account name and access key.</caps:sentence>
              <caps:sentence id="src121" class="srcSentence"> For more information, see the <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_Delegate">How to delegate access to your RMS logs</link> section later in this topic.</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence id="src122" class="srcSentence">In some circumstances, you might want to regenerate your storage access keys.</caps:sentence>
            <caps:sentence id="src123" class="srcSentence"> For example:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src124" class="srcSentence">You change the company that manages your Azure Rights Management usage logs.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src125" class="srcSentence">You suspect that your storage access key is compromised.</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src126" class="srcSentence">If this happens to you, this is when you use the secondary access key (on the assumption that you were previously using the primary access key) to ensure service continuity.</caps:sentence>
            <caps:sentence id="src127" class="srcSentence"> When you regenerate the access key that you were not previously using, you then configure Azure Rights Management to use the new key.</caps:sentence>
            <caps:sentence id="src128" class="srcSentence"> Use the following procedure to regenerate the secondary access key and configure Azure Rights Management to use it:</caps:sentence>
          </para>
          <procedure>
            <title>
              <caps:sentence id="src129" class="srcSentence">To regenerate the secondary access key</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src130" class="srcSentence">Sign in to the <externalLink><linkText>Azure  portal</linkText><linkUri>https://portal.azure.com/</linkUri></externalLink>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src131" class="srcSentence">Click <ui>All Resources</ui>, and search for your storage by typing the storage name in the text box..</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src132" class="srcSentence">Select your storage, and click <ui>Settings</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src133" class="srcSentence">Click the <ui>Keys</ui> icon.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src134" class="srcSentence">In the <ui>Manage  keys</ui> section, click <ui>Regenerate secondary key</ui> click Yes to confirm that you want to regenerate secondary access key, and copy the new secondary access key to the clipboard.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src135" class="srcSentence">Do not close the Azure portal.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src136" class="srcSentence">Start Windows PowerShell with the <ui>Run as administrator</ui> option and use the <externalLink><linkText>Set-AadrmUsageLogStorageAccount</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629426.aspx</linkUri></externalLink> cmdlet to configure Azure Rights Management to use this new access key, replacing <placeholder>&lt;StorageAccount&gt;</placeholder> with the name of your storage account and <placeholder>&lt;Access_Key&gt;</placeholder> with the regenerated secondary access key that you just copied:</caps:sentence>
                  </para>
                  <code>Set-AadrmUsageLogStorageAccount -StorageAccount <placeholder xmlns="">&lt;StorageAccount&gt;</placeholder>-AccessKey <placeholder xmlns="">&lt;Access_Key&gt;</placeholder></code>
                  <alert class="warning">
                    <para>
                      <caps:sentence id="src137" class="srcSentence">Although you can switch to another storage account when you run this command, this action orphans your previous logs and they will no longer be accessible to the Set-AadrmUsageLogStorageAccount cmdlet or similar management commands and functions.</caps:sentence>
                    </para>
                  </alert>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src138" class="srcSentence">Back in the Azure portal, <ui>Manage  Keys</ui> section, regenerate your primary access key.</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence id="src139" class="srcSentence">For more information about how to manage your storage access keys, see the  <externalLink><linkText>Manage your storage access keys</linkText><linkUri>https://azure.microsoft.com/documentation/articles/storage-create-storage-account/#manage-your-storage-access-keys</linkUri></externalLink> section from the <externalLink><linkText>About Azure storage accounts</linkText><linkUri>https://azure.microsoft.com/documentation/articles/storage-create-storage-account/</linkUri></externalLink> in the Azure documentation.</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
        </content>
      </section>
      <section address="BKMK_Delegate">
        <title address="BKMK_DelegateAccess">
          <caps:sentence id="src140" class="srcSentence">How to delegate access to your Azure Rights Management usage logs</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src141" class="srcSentence">You can delegate access to your RMS logs by sharing your storage account name and access key.</caps:sentence>
            <caps:sentence id="src142" class="srcSentence"> You might want to delegate access to another administrative user, to a developer within your own organization, or to an independent software vendor (ISV).</caps:sentence>
            <caps:sentence id="src143" class="srcSentence"> Because they will not have your RMS administrator credentials, they cannot use the Get-AardrmUsageLog cmdlet to download the RMS logs.</caps:sentence>
            <caps:sentence id="src144" class="srcSentence"> Instead, they must use the Windows Storage SDK to download the logs.</caps:sentence>
            <caps:sentence id="src145" class="srcSentence"> Alternatively, they can write an application to read the logs directly from Azure Storage.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src146" class="srcSentence">It is safe to share your storage account name and access key in this way when the storage account is dedicated to your RMS logs.</caps:sentence>
            <caps:sentence id="src147" class="srcSentence"> Even though other people have your access key, they cannot use this to access any other storage account or use your RMS tenant account.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_Interpret">
        <title>
          <caps:sentence id="src148" class="srcSentence">How to interpret your Azure Rights Management usage  logs</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src149" class="srcSentence">Use the following information to help you interpret the Azure Rights Management usage  logs.</caps:sentence>
          </para>
        </content>
        <sections>
          <section>
            <title>
              <caps:sentence id="src150" class="srcSentence">The storage account layout</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src151" class="srcSentence">The first time Azure Rights Management writes logs to your storage account, it creates the following two containers:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src152" class="srcSentence">
                      <ui>Rms-metadata</ui>: This container is reserved for Azure Rights Management .</caps:sentence>
                    <caps:sentence id="src153" class="srcSentence"> Do not modify or delete this container.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src154" class="srcSentence">
                      <ui>Rms-logs-&lt;guid&gt;</ui>: This container is where Azure Rights Management creates and saves the logs.</caps:sentence>
                    <caps:sentence id="src155" class="srcSentence"> You can safely delete any files in this container if you no longer want the logging information that they contain.</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence id="src156" class="srcSentence">Over time, Azure Rights Management might create additional <ui>Rms-logs-&lt;guid&gt;</ui> containers.</caps:sentence>
                <caps:sentence id="src157" class="srcSentence"> For example, if the <ui>Rms-metadata</ui> container becomes corrupted or it is accidentally deleted, Azure Rights Management resets its contents and creates a new <ui>Rms-logs-&lt;guid&gt;</ui> container for all future logs.</caps:sentence>
                <caps:sentence id="src158" class="srcSentence"> The old logs in the old container are not deleted but are orphaned.</caps:sentence>
              </para>
            </content>
          </section>
          <section>
            <title>
              <caps:sentence id="src159" class="srcSentence">The log sequence</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src160" class="srcSentence">Azure Rights Management writes the logs as a series of blobs.</caps:sentence>
                <caps:sentence id="src161" class="srcSentence"> Each blob contains one or more log records, in extended W3C log format.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src162" class="srcSentence">The name of each blob is a number.</caps:sentence>
                <caps:sentence id="src163" class="srcSentence"> Within each log container the first blob is named 000000001.</caps:sentence>
                <caps:sentence id="src164" class="srcSentence"> Each blob is named sequentially in the order in which it was created.</caps:sentence>
                <caps:sentence id="src165" class="srcSentence"> Each blob contains one or more log records.</caps:sentence>
                <caps:sentence id="src166" class="srcSentence"> Each log record has a UTC time stamp that indicates when the corresponding request was served by Azure Rights Management.</caps:sentence>
              </para>
              <alert class="important">
                <para>
                  <caps:sentence id="src167" class="srcSentence">The Azure Rights Management logging system is optimized to provide you with logs quickly, rather than in strict sequential order.</caps:sentence>
                  <caps:sentence id="src168" class="srcSentence"> The order of the blobs, as well as the order of log records within a blob, might be out of chronological sequence.</caps:sentence>
                  <caps:sentence id="src169" class="srcSentence"> The only reason the blobs are named sequentially is to enable you to efficiently download them incrementally.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src170" class="srcSentence">Two examples of potential log sequence results:</caps:sentence>
                </para>
                <list class="bullet">
                  <listItem>
                    <para>
                      <caps:sentence id="src171" class="srcSentence">The log records in blob 000000004 might overlap chronologically with the log records in blob 000000003.</caps:sentence>
                      <caps:sentence id="src172" class="srcSentence"> In an extreme case, all log records in blob 000000004 might have been generated before all log records in blob 000000003.</caps:sentence>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence id="src173" class="srcSentence">The second log record in a blob might have been generated before the first log record, but was written to storage in reverse order.</caps:sentence>
                    </para>
                  </listItem>
                </list>
              </alert>
              <para>
                <caps:sentence id="src174" class="srcSentence">Before you analyze your Azure Rights Management usage logs, we recommend that you download and import the log into a repository where you can sort the logs based on their timestamp.</caps:sentence>
                <caps:sentence id="src175" class="srcSentence"> For more information about to download the logs, see the <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e#BKMK_AccesAndUseLogs">How to access and use your RMS logs</link> section in this topic.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src176" class="srcSentence">Because the logs are not necessarily chronological but the majority of them are written within 15 minutes of the request, when you identify the logs that you want by using their timestamp , add 15 minutes to the time that you are interested in.</caps:sentence>
                <caps:sentence id="src177" class="srcSentence"> Then download these logs.</caps:sentence>
                <caps:sentence id="src178" class="srcSentence"> This strategy should ensure that you get almost all logs.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src179" class="srcSentence">One other thing to remember is that the timestamp on each log record is the local time of the Azure Rights Management service that processed the request.</caps:sentence>
                <caps:sentence id="src180" class="srcSentence"> Because Azure Rights Management runs on multiple servers across multiple data center, sometimes the logs might seem to be out of sequence, even when they are sorted by their timestamp.</caps:sentence>
                <caps:sentence id="src181" class="srcSentence"> However, the different is small and usually within a minute.</caps:sentence>
                <caps:sentence id="src182" class="srcSentence"> In most cases, this is not an issue that would be a problem for log analysis.</caps:sentence>
              </para>
            </content>
          </section>
          <section>
            <title>
              <caps:sentence id="src183" class="srcSentence">The blob format</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src184" class="srcSentence">Each blob is in W3C extended log format.</caps:sentence>
                <caps:sentence id="src185" class="srcSentence"> It starts with the following two lines:</caps:sentence>
              </para>
              <para>
                <ui>
                  <caps:sentence id="src186" class="srcSentence">#Software: RMS</caps:sentence>
                </ui>
              </para>
              <para>
                <ui>
                  <caps:sentence id="src187" class="srcSentence">#Version: 1.1</caps:sentence>
                </ui>
              </para>
              <para>
                <caps:sentence id="src188" class="srcSentence">The first line identifies that these are Azure Rights Management logs.</caps:sentence>
                <caps:sentence id="src189" class="srcSentence"> The second line identifies that the rest of the blob follows the version 1.1 specification.</caps:sentence>
                <caps:sentence id="src190" class="srcSentence"> We recommend that any applications that parse these logs verify these two lines before continuing to parse the rest of the blob.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src191" class="srcSentence">The third line enumerates a list of field names that are separated by tabs:</caps:sentence>
              </para>
              <para>
                <ui>
                  <caps:sentence id="src192" class="srcSentence">#Fields: date            time            row-id        request-type           user-id       result          correlation-id          content-id                owner-email           issuer                     template-id             file-name                  date-published      c-info         c-ip</caps:sentence>
                </ui>
              </para>
              <para>
                <caps:sentence id="src193" class="srcSentence">Each of the subsequent lines is a log record.</caps:sentence>
                <caps:sentence id="src194" class="srcSentence"> The values of the fields are in the same order as the preceding line, and are separated by tabs.</caps:sentence>
                <caps:sentence id="src195" class="srcSentence"> Use the following table to interpret the fields.</caps:sentence>
              </para>
              <table>
                <thead>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src196" class="srcSentence">Field name</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src197" class="srcSentence">W3C data type</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src198" class="srcSentence">Description</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src199" class="srcSentence">Example value</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src200" class="srcSentence">date</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src201" class="srcSentence">Date</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src202" class="srcSentence">UTC date when the request was served.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src203" class="srcSentence">The source is the local clock on the server that served the request.</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src204" class="srcSentence">2013-06-25</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src205" class="srcSentence">time</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src206" class="srcSentence">Time</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src207" class="srcSentence">UTC time in 24-hour format when the request was served.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src208" class="srcSentence">The source is the local clock on the server that served the request.</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src209" class="srcSentence">21:59:28</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src210" class="srcSentence">row-id</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src211" class="srcSentence">Text</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src212" class="srcSentence">Unique GUID for this log record.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src213" class="srcSentence">This value is useful when you aggregate logs or copy logs into another format.</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src214" class="srcSentence">1c3fe7a9-d9e0-4654-97b7-14fafa72ea63</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src215" class="srcSentence">request-type</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src216" class="srcSentence">Name</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src217" class="srcSentence">Name of the RMS API that was requested.</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src218" class="srcSentence">AcquireLicense</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src219" class="srcSentence">user-id</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src220" class="srcSentence">String</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src221" class="srcSentence">The user who made the request.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src222" class="srcSentence">The value is enclosed in single quotation marks.</caps:sentence>
                        <caps:sentence id="src223" class="srcSentence"> Some request types are anonymous, in which case the value is ”.</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src224" class="srcSentence">‘joe@contoso.com’</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src225" class="srcSentence">result</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src226" class="srcSentence">String</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src227" class="srcSentence">‘Success’ if the request was served successful.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src228" class="srcSentence">The error type in single quotation marks if the request failed.</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src229" class="srcSentence">‘Success’</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src230" class="srcSentence">correlation-id</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src231" class="srcSentence">Text</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src232" class="srcSentence">GUID that is common between the RMS client log and server log for a given request.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src233" class="srcSentence">This value can be useful to help troubleshooting client issues.</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src234" class="srcSentence">cab52088-8925-4371-be34-4b71a3112356</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src235" class="srcSentence">content-id</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src236" class="srcSentence">Text</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src237" class="srcSentence">GUID, enclosed in curly braces that identifies the protected content (for example, a document).</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src238" class="srcSentence">This field has a value only if request-type is AcquireLicense and is blank for all other request types.</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src239" class="srcSentence">{bb4af47b-cfed-4719-831d-71b98191a4f2}</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src240" class="srcSentence">owner-email</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src241" class="srcSentence">String</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src242" class="srcSentence">Email address of the owner of the document.</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src243" class="srcSentence">alice@contoso.com</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src244" class="srcSentence">issuer</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src245" class="srcSentence">String</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src246" class="srcSentence">Email address of the document issuer.</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src247" class="srcSentence">alice@contoso.com (or) FederatedEmail.4c1f4d-93bf-00a95fa1e042@contoso.onmicrosoft.com'</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src248" class="srcSentence">Template-id</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src249" class="srcSentence">String</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src250" class="srcSentence">ID of the template used to protect the document.</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src251" class="srcSentence">{6d9371a6-4e2d-4e97-9a38-202233fed26e}</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src252" class="srcSentence">File-name</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src253" class="srcSentence">String</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src254" class="srcSentence">File name of the document that was protected.</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src255" class="srcSentence">TopSecretDocument.docx</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src256" class="srcSentence">Date-published</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src257" class="srcSentence">Date</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src258" class="srcSentence">Date when the document was protected.</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src259" class="srcSentence">2015-10-15T21:37:00</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src260" class="srcSentence">c-info</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src261" class="srcSentence">String</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src262" class="srcSentence">Information about the client platform that is making the request.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src263" class="srcSentence">The specific string varies, depending on the application (for example, the operating system or the browser).</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src264" class="srcSentence">'MSIPC;version=1.0.623.47;AppName=WINWORD.EXE;AppVersion=15.0.4753.1000;AppArch=x86;OSName=Windows;OSVersion=6.1.7601;OSArch=amd64'</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src265" class="srcSentence">c-ip</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src266" class="srcSentence">Address</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src267" class="srcSentence">IP address of the client that makes the request.</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src268" class="srcSentence">64.51.202.144</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </tbody>
              </table>
            </content>
            <sections>
              <section>
                <title>
                  <caps:sentence id="src269" class="srcSentence">Exceptions for the user-id field</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence id="src270" class="srcSentence">Although the user-id field usually indicates the user who made the request, there are two exceptions where the value does not map to a real user:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src271" class="srcSentence">The value <ui>'microsoftrmsonline@&lt;YourTenantID&gt;.rms.&lt;region&gt;.aadrm.com'</ui>.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src272" class="srcSentence">This indicates an Office 365 service, such as Exchange Online or Sharepoint Online, is making the request.</caps:sentence>
                        <caps:sentence id="src273" class="srcSentence"> In the string, <placeholder>&lt;YourTenantID&gt;</placeholder> is the GUID for your tenant and <placeholder>&lt;region&gt;</placeholder> is the region where your tenant is registered.</caps:sentence>
                        <caps:sentence id="src274" class="srcSentence"> For example, <ui>na</ui> represents North America, <ui>eu</ui> represents Europe, and <ui>ap</ui> represents Asia.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src275" class="srcSentence">If you are using the RMS connector.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src276" class="srcSentence">Requests from this connector are logged with the service principal name that RMS automatically generates when you install the RMS connector.</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </content>
              </section>
              <section>
                <title>
                  <caps:sentence id="src277" class="srcSentence">Typical request types</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence id="src278" class="srcSentence">There are many request types for Azure Rights Management but the following table identifies some of the most typically used request types.</caps:sentence>
                  </para>
                  <table>
                    <thead>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src279" class="srcSentence">Request type</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src280" class="srcSentence">Description</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src281" class="srcSentence">AcquireLicense</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src282" class="srcSentence">A client from a Windows based machine is requesting a license for RMS-protected content.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src283" class="srcSentence">AcquirePreLicense</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src284" class="srcSentence">A client, on behalf of the user, is requesting for a license for RMS-protected content.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src285" class="srcSentence">AcquireTemplates</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src286" class="srcSentence">A call was made to acquires templates based on template IDs </caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src287" class="srcSentence">AcquireTemplateInformation</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src288" class="srcSentence">A call was made to get the IDs of the template from the service.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src289" class="srcSentence">AddTemplate</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src290" class="srcSentence">A call is  made from the Azure classic portal to add a template.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src291" class="srcSentence">BECreateEndUserLicenseV1</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src292" class="srcSentence">A call is  made from a mobile device to create an end-user license.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src293" class="srcSentence">BEGetAllTemplatesV1</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src294" class="srcSentence">A call is  made from a mobile device (back-end) to get all the templates.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src295" class="srcSentence">Certify</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src296" class="srcSentence">The client is certifying the content for protection.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src297" class="srcSentence">Decrypt</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src298" class="srcSentence">The client is attempting to decrypt the RMS-protected content.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src299" class="srcSentence">DeleteTemplateById</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src300" class="srcSentence">A call is  made from the Azure classic portal, to delete a template by template  ID.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src301" class="srcSentence">ExportTemplateById</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src302" class="srcSentence">A call is  made from the Azure classic portal to export a template based on a template ID.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src303" class="srcSentence">FECreateEndUserLicenseV1</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src304" class="srcSentence">Similar to the AcquireLicense request but from mobile devices.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src305" class="srcSentence">FECreatePublishingLicenseV1</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src306" class="srcSentence">The same as Certify and GetClientLicensorCert combined, from mobile clients.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src307" class="srcSentence">FEGetAllTemplates</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src308" class="srcSentence">A call is  made, from a mobile device (front-end) to get the templates.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src309" class="srcSentence">GetAllTemplates</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src310" class="srcSentence">A call is  made from the Azure classic portal, to get all the templates.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src311" class="srcSentence">GetClientLicensorCert</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src312" class="srcSentence">The client is requesting a publishing certificate (that is later used to protect content) from a Windows-based computer.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src313" class="srcSentence">GetConfiguration</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src314" class="srcSentence">An Azure PowerShell cmdlet is called to get the configuration of the Azure RMS tenant.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src315" class="srcSentence">GetConnectorAuthorizations</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src316" class="srcSentence">A call  is made from the RMS connectors to get their configuration from the cloud.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src317" class="srcSentence">GetTenantFunctionalState </caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src318" class="srcSentence">The Azure classic portal is checking whether Azure RMS is activated.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src319" class="srcSentence">GetTemplateById</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src320" class="srcSentence">A call is  made from the Azure classic portal to get a template by specifying a template ID.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src321" class="srcSentence">ExportTemplateById</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src322" class="srcSentence">A call is being made from the Azure classic portal to export a template by specifying a template ID.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src323" class="srcSentence">FindServiceLocationsForUser</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src324" class="srcSentence">A call is made to query for URLs, which is used to call Certify or AcquireLicense.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src325" class="srcSentence">ImportTemplate</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src326" class="srcSentence">A call is  made from the Azure classic portal to import a template.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src327" class="srcSentence">ServerCertify</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src328" class="srcSentence">A call is  made from an RMS-enabled client (such as SharePoint) to certify the server.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src329" class="srcSentence">SetUsageLogFeatureState</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src330" class="srcSentence">A call is  made to enable usage logging.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src331" class="srcSentence">SetUsageLogStorageAccount </caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src332" class="srcSentence">A call is  made to specify the location of the Azure RMS logs.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src333" class="srcSentence">SignDigest</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src334" class="srcSentence">A call is made when a key is used for signing purposes.</caps:sentence>
                            <caps:sentence id="src335" class="srcSentence"> This is called typically once per AcquireLicence (or FECreateEndUserLicenseV1), Certify, and GetClientLicensorCert (or FECreatePublishingLicenseV1).</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src336" class="srcSentence">UpdateTemplate</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src337" class="srcSentence">A call is  made from the Azure classic portal to update an existing template.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </tbody>
                  </table>
                </content>
              </section>
            </sections>
          </section>
        </sections>
      </section>
      <section address="BKMK_PowerShell">
        <title>
          <caps:sentence id="src338" class="srcSentence">Windows PowerShell reference</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src339" class="srcSentence">Use the following Windows PowerShell cmdlets to help you configure and use Azure Rights Management usage logging:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence id="src340" class="srcSentence">Disable-AadrmUsageLogFeature</caps:sentence>
                  </linkText>
                  <linkUri>https://msdn.microsoft.com/library/azure/dn629404.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence id="src341" class="srcSentence">Enable-AadrmUsageLogFeature</caps:sentence>
                  </linkText>
                  <linkUri>https://msdn.microsoft.com/library/azure/dn629421.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence id="src342" class="srcSentence">Get-AadrmUsageLog</caps:sentence>
                  </linkText>
                  <linkUri>https://msdn.microsoft.com/library/azure/dn629401.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence id="src343" class="srcSentence">Get-AadrmUsageLogFeature</caps:sentence>
                  </linkText>
                  <linkUri>https://msdn.microsoft.com/library/azure/dn629425.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence id="src344" class="srcSentence">Get-AadrmUsageLogLastCounterValue</caps:sentence>
                  </linkText>
                  <linkUri>https://msdn.microsoft.com/library/azure/dn629423.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence id="src345" class="srcSentence">Get-AadrmUsageLogStorageAccount</caps:sentence>
                  </linkText>
                  <linkUri>https://msdn.microsoft.com/library/azure/dn629419.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence id="src346" class="srcSentence">Set-AadrmUsageLogStorageAccount</caps:sentence>
                  </linkText>
                  <linkUri>https://msdn.microsoft.com/library/azure/dn629426.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src347" class="srcSentence">For more information about using Windows PowerShell for Azure Rights Management, see <link xlink:href="a890e04a-4b70-41b5-8d5f-3c210a669faa">Administering Azure Rights Management by Using Windows PowerShell</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="18564e4a-9364-4ed2-8f17-89d24fc0d878">Using rights management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSSource>
</caps:SxS>