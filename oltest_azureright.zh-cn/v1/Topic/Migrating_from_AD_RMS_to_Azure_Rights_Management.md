---
description: na
keywords: na
pagetitle: Migrating from AD RMS to Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 828cf1f7-d0e7-4edf-8525-91896dbe3172
---
# 从 AD RMS 迁移到 Azure 权限管理
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="zh-CN">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="7e1093f11a5de031bec12bda815bee57" id="tgt1" class="tgtSentence">使用下面的一组指令将 Active Directory 权限管理服务 (AD RMS) 部署迁移到 Azure Rights Management (Azure RMS)。</caps:sentence>
          <caps:sentence sentenceid="1fc10734b5a495bb1694a544301201c5" id="tgt2" class="tgtSentence"> 迁移之后，用户将仍然可以访问你的组织使用 AD RMS 来保护的文档和电子邮件，新保护的内容将使用 Azure RMS。</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="f1f77b5de4e8083120506a9394617442" id="tgt3" class="tgtSentence">不确定这种 AD RMS 迁移是否适合你的组织？</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <caps:sentence sentenceid="1b4cba74d699f78e0dee21550f909cdb" id="tgt4" class="tgtSentence">有关 Azure RMS 的简介、它可以解决的业务问题、它对管理员和用户来说是什么样子，以及它是如何工作的，请参阅 <link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link></caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence sentenceid="0450240d9c722338056c9ad6de10cb77" id="tgt5" class="tgtSentence">有关 Azure RMS 与 AD RMS 的比较，请参阅 <link xlink:href="8123bd62-1814-4d79-b306-e20c1a00e264">Comparing Azure Rights Management and AD RMS</link>。</caps:sentence>
            </para>
          </listItem>
        </list>
      </introduction>
      <section>
        <title>
          <caps:sentence sentenceid="5628de21bd65d29e43995c98b581fb4c" id="tgt6" class="tgtSentence">将 AD RMS 迁移到 Azure RMS 的先决条件</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="464db707f8d458530d2faa8267ef40f9" id="tgt7" class="tgtSentence">在开始迁移到 Azure RMS 之前，请确保具备以下先决条件，并确保你了解所有限制。</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="ba12fb48e2d23bb2bd2819f64d02ec7e" id="tgt8" class="tgtSentence">要求</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="5dc731e46ae38b87ff3e3e2eaf459db2" id="tgt9" class="tgtSentence">更多信息</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="8c09c4ba1af9e8b2527a29a424486a91" id="tgt10" class="tgtSentence">支持的 RMS 部署</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="a4618ccf08306a67fc9a8df7c8d82827" id="tgt11" class="tgtSentence">AD RMS 的所有版本（从 Windows Server 2008 到 Windows Server 2012 R2）均支持迁移到 Azure RMS：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="b33d517673e01450cdc5dd68f42d526f" id="tgt12" class="tgtSentence">Windows Server 2008（x86 或 x64）</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="5b49d77d595e430fb98a078e8af23ff9" id="tgt13" class="tgtSentence">Windows Server 2008 R2 (x64)</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="8c3656681a6763ef49ffe59d9ae8208b" id="tgt14" class="tgtSentence">Windows Server 2012 (x64)</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="cfb81116c57d2d5bbe86aaadd996b205" id="tgt15" class="tgtSentence">Windows Server 2012 R2 (x64)</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <alert class="note">
                    <para>
                      <caps:sentence sentenceid="2ae22f44d0fa5149950d578528edfc21" id="tgt16" class="tgtSentence">如果你正在 Windows Server 2003 上运行 Windows RMS，请注意，我们将在 2015 年停止对此操作系统版本的支持。</caps:sentence>
                      <caps:sentence sentenceid="70981c284a7509c571c31779289ffe68" id="tgt17" class="tgtSentence"> 你可以将此版本的 RMS 迁移到 Azure RMS，但仅当此操作系统仍受支持时，才支持这种迁移。</caps:sentence>
                      <caps:sentence sentenceid="93fadfc4f84f023636c830010449d31c" id="tgt18" class="tgtSentence"> 一种解决方法是，可以将受信任的发布域 (TPD) 导入到支持的 AD RMS 版本，然后不使用 RMS 1.0 兼容性选项重新导入 TPD。</caps:sentence>
                      <caps:sentence sentenceid="1f5f606b4ae46273756548ceeb471e8d" id="tgt19" class="tgtSentence"> 有关 TPD 的详细信息，请参阅<externalLink><linkText>受信任的发布域</linkText><linkUri>http://technet.microsoft.com/library/dd996639(v=ws.10).aspx</linkUri></externalLink></caps:sentence>
                    </para>
                  </alert>
                  <para>
                    <caps:sentence sentenceid="7ac523a739204bc8a0fd195097224b76" id="tgt20" class="tgtSentence">支持所有有效的 AD RMS 拓扑：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="aa541a950d7c0be5f5379fdb4e3688a6" id="tgt21" class="tgtSentence">单个林、单个 RMS 群集</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="9d6c47c780c3c79f7de85d5bedaef053" id="tgt22" class="tgtSentence">单个林、多个仅授权 RMS 群集</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="9e0660df87010fc22772e4272acd7dbd" id="tgt23" class="tgtSentence">多个林、多个 RMS 群集</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <alert class="note">
                    <para>
                      <caps:sentence sentenceid="55f86f0427e122442e1af8fb7c177d8c" id="tgt24" class="tgtSentence">默认情况下，多个 RMS 群集将迁移到单个 Azure RMS 租户。</caps:sentence>
                      <caps:sentence sentenceid="937f9b4b6b4a8e446bbde7d3a82237c6" id="tgt25" class="tgtSentence"> 如果你想要迁移到不同的 RMS 租户，必须将它们视为不同的迁移。</caps:sentence>
                      <caps:sentence sentenceid="c46d3d0f13b0b4cc7c8c46ca341dbee1" id="tgt26" class="tgtSentence"> 不能将一个 RMS 群集的密钥导入到多个 Azure RMS 租户。</caps:sentence>
                    </para>
                  </alert>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="1b8f14374bc6cd88798b18d698fa0ec5" id="tgt27" class="tgtSentence">运行 Azure RMS（包括 Azure RMS 租户（未激活））的所有要求</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="4462659de4d522ffbc363a78e3f7fd9f" id="tgt28" class="tgtSentence">请参阅 <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="5b4aedae3914c0fb85692e4739501835" id="tgt29" class="tgtSentence">尽管在从 AD RMS 迁移之前你必须拥有 Azure RMS 租户，但我们建议在迁移之前不要激活 Rights Management 服务。</caps:sentence>
                    <caps:sentence sentenceid="b1dc2ea89658fb844cc7318be2badd36" id="tgt30" class="tgtSentence"> 迁移过程包括此步骤，在从 AD RMS 导出密钥和模板并将其导入到 Azure RMS 之后执行此操作。</caps:sentence>
                    <caps:sentence sentenceid="ab77b94551487a9d00c1995e82f86b5a" id="tgt31" class="tgtSentence"> 但是，如果 Azure RMS 已激活，你仍可以从 AD RMS 迁移。</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="09189aa7fb0d0b633f119604b093ac0d" id="tgt32" class="tgtSentence">为 Azure RMS 做准备：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="8ecd274a2b3ef0b0fe4ec034bcc2d721" id="tgt33" class="tgtSentence">在本地目录和 Azure Active Directory 之间进行目录同步</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="d03d4eeeaaf82ae4ba6349c1c3822ada" id="tgt34" class="tgtSentence">在 Azure Active Directory 中已启用邮件的组</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="4462659de4d522ffbc363a78e3f7fd9f" id="tgt35" class="tgtSentence">请参阅 <link xlink:href="afbca2d6-32a7-4bda-8aaf-9f93f5da5abc">Preparing for Azure Rights Management</link>。</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="cf6da7690e2f4fcbcbd33fe6bf65bef3" id="tgt36" class="tgtSentence">如果你已使用过 Exchange Server 的信息权限管理 (IRM) 功能（例如，传输规则和 Outlook Web Access）或带 AD RMS 的 SharePoint Server：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="69194a3ca7b97af28634a43befc9823f" id="tgt37" class="tgtSentence">为这些服务器上未提供 IRM 的较短期间拟定计划</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="2c4963a25e25da3add0b0250dbf40fba" id="tgt38" class="tgtSentence">在迁移后，你可以继续将这些服务器上的 IRM 与 Azure RMS 一起使用。</caps:sentence>
                    <caps:sentence sentenceid="5886b7adf35c4d8a1bd656b8d330ca17" id="tgt39" class="tgtSentence"> 但是，其中一个迁移步骤是暂时禁用 IRM 服务、安装并配置连接器、重新配置服务器，然后重新启用 IRM。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="05d67ef2b02b32aa29c30c2019652b18" id="tgt40" class="tgtSentence">在迁移过程中，只有这一步会出现服务中断。</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
          <para>
            <caps:sentence sentenceid="d2f2ded167a3bc2d5846271643e6d4a3" id="tgt41" class="tgtSentence">限制：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="7045979f47814ad634a33b1d72db2c10" id="tgt42" class="tgtSentence">虽然迁移过程支持将服务器授权证书 (SLC) 密钥迁移到 Azure RMS 的硬件安全模块 (HSM)，但 Exchange Online 目前不支持此配置。如果你希望在迁移到 Azure RMS 之后获得 Exchange Online 的完整 IRM 功能，必须<externalLink><linkText>由 Microsoft 管理</linkText><linkUri>http://technet.microsoft.com/library/dn440580.aspx</linkUri></externalLink>你的 Azure RMS 租户密钥。你也可以自行管理 Azure RMS 租户 (BYOK)，在这种情况下，Exchange Online 的 IRM 功能将会受限。有关将 Exchange Online 与 Azure RMS 配合使用的详细信息，请参阅本文中的<link xlink:href="#BKMK_Step6Migration">Step 6. Configure IRM integration for Exchange Online</link>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="c76c74fb4f3e617b7225abe3010aa8e8" id="tgt43" class="tgtSentence">如果你的软件和客户端不受 Azure RMS 支持，则它们将不能保护或使用受 Azure RMS 保护的内容。</caps:sentence>
                <caps:sentence sentenceid="76d643a5ba1bea30bd2d0ca3c797f33f" id="tgt44" class="tgtSentence"> 请务必查看 <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>主题中“支持的应用程序和客户端”部分。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="ad5dedaa2ff99bbc93331604a5108441" id="tgt45" class="tgtSentence">如果你将本地密钥作为存档导入 Azure RMS（在导入过程中未将 TPD 设置为活动）并在分阶段迁移过程中分批迁移用户，则 AD RMS 中保留的用户将无法访问已迁移用户最近保护的内容。</caps:sentence>
                <caps:sentence sentenceid="04c11e9d679e974b49006806631654f4" id="tgt46" class="tgtSentence"> 在这种情况下，请尽量缩短迁移持续时间，并以逻辑批的形式迁移用户，以便在用户相互协作的情况下会一起迁移。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="533ed82f5209cbd53fca1f8b47f50dd6" id="tgt47" class="tgtSentence">如果你在导入过程中将 TPD 设置为活动，则不存在这种限制，因为所有用户将使用同一密钥保护内容。</caps:sentence>
                <caps:sentence sentenceid="b7bf882340f8fa084276a093aded0906" id="tgt48" class="tgtSentence"> 我们建议采用这种配置，因为这样你就可以根据自己的步调单独迁移所有用户。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="59650ba2910c3f7cd10aa37a53ebd08e" id="tgt49" class="tgtSentence">如果你与外部合作伙伴协作（例如，通过使用受信任的用户域或联合），则在你迁移的同时或之后尽早的时间，这些合作伙伴也必须迁移到 Azure RMS。</caps:sentence>
                <caps:sentence sentenceid="feb97bb633dea67a239709ac84eba4b9" id="tgt50" class="tgtSentence"> 若要继续访问你的组织以前使用 AD RMS 保护的内容，这些合作伙伴必须进行与你进行的更改（在本文档中提供了这些更改）类似的客户端配置更改。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="2d97b5d730b78206f98044c79e7725e4" id="tgt51" class="tgtSentence">由于你的合作伙伴进行的配置可能有所变动，确切说明此重新配置已超出了本文档的范围。</caps:sentence>
                <caps:sentence sentenceid="d5cb703e9c63be2d9e5d0cfe3d7ff4f5" id="tgt52" class="tgtSentence"> 有关帮助，请与 Microsoft 客户支持服务 (CSS) 联系。</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence sentenceid="c44752dc608ae1486f687465ec71380b" id="tgt53" class="tgtSentence">将 AD RMS 迁移到 Azure RMS 的步骤</caps:sentence>
        </title>
        <content>
          <para></para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="249b1959ad300e46d244c63b635f7194" id="tgt54" class="tgtSentence">迁移步骤</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="5dc731e46ae38b87ff3e3e2eaf459db2" id="tgt55" class="tgtSentence">更多信息</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>
                      <caps:sentence sentenceid="5dd1c2055143474357639df5f5a3b070" id="tgt56" class="tgtSentence">1.下载“Azure RMS 管理”管理工具</caps:sentence>
                    </embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="f1bcbb94613d91032d33beb396e5a9fb" id="tgt57" class="tgtSentence">有关说明，请参阅<link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172#BKMK_Step1Migration">Step 1: Download the Azure Rights Management Administration Tool</link>。</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>
                      <caps:sentence sentenceid="ba0e05024c12ef76be258f2e2d4cf1db" id="tgt58" class="tgtSentence">2.从 AD RMS 中导出配置数据并将其导入到 Azure RMS 中</caps:sentence>
                    </embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="c15b04b43569b8a19349feab7c3cd90a" id="tgt59" class="tgtSentence">将 AD RMS 中的配置数据（密钥、模板、URL）导出到 XML 文件，然后使用 Import-AadrmTpd Windows PowerShell cmdlet 将该文件上载到 Azure RMS。</caps:sentence>
                    <caps:sentence sentenceid="c6d836a701d21e2d9cc18234cd4140dc" id="tgt60" class="tgtSentence"> 可能需要其他步骤，具体取决于你的 AD RMS 密钥配置：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="083c7bb86d0bca53c5b02e9406b21056" id="tgt61" class="tgtSentence">软件保护密钥到软件保护密钥的迁移：集中管理的基于密码的密钥迁移到由 Microsoft 管理的 Azure RMS 租户密钥。</caps:sentence>
                        <caps:sentence sentenceid="248cf34360a22dba69726af20714a564" id="tgt62" class="tgtSentence"> 这是最简单的迁移路径，并且无需执行任何附加步骤。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="b79366ad4da5a2a9b7e9bc00604c4616" id="tgt63" class="tgtSentence">HSM 保护密钥到 HSM 保护密钥的迁移：将 HSM 存储的 AD RMS 密钥迁移到客户管理的 Azure RMS 租户密钥（“自带密钥”方案，简称 BYOK）。</caps:sentence>
                        <caps:sentence sentenceid="151d3e02771181e35d02c16b561d0231" id="tgt64" class="tgtSentence"> 这需要执行附加步骤，以将密钥从本地 Thales HSM 传输到 Azure RMS HSM。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="847ea4b718777808c8e1dc9711ea2e87" id="tgt65" class="tgtSentence">软件保护密钥到 HSM 保护密钥的迁移：AD RMS 中集中管理的基于密码的密钥迁移到由客户管理的 Azure RMS 租户密钥（“携带你自己的密钥”或 BYOK 方案）。</caps:sentence>
                        <caps:sentence sentenceid="c815745846edb8cef716ed34bde85a7e" id="tgt66" class="tgtSentence"> 这需要的配置最多，因为你必须先提取软件密钥并将其导入到本地 HSM 中，然后再执行附加步骤以将该密钥从本地 Thales HSM 传输到 Azure RMS HSM。</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <para>
                    <caps:sentence sentenceid="f1bcbb94613d91032d33beb396e5a9fb" id="tgt67" class="tgtSentence">有关说明，请参阅<link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172#BKMK_Step2Migration">Step 2. Export configuration data from AD RMS and import it to Azure RMS</link>。</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>
                      <caps:sentence sentenceid="5a3f6c2098cb9f7e242273dd7923e245" id="tgt68" class="tgtSentence">3.激活你的 RMS 租户</caps:sentence>
                    </embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="2c680cdefdce9364458747ce841533cb" id="tgt69" class="tgtSentence">如果可能，请在执行导入过程之后而不是之前执行此步骤。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="3dad81dd51d8bde90a1e99c299ce2323" id="tgt70" class="tgtSentence">有关详细信息和说明，请参阅<link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172#BKMK_Step3Migration">Step 3. Activate your RMS tenant</link>。</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>
                      <caps:sentence sentenceid="8ce4d085869ea294d3fcebb64c17136a" id="tgt71" class="tgtSentence">4.配置导入的模板</caps:sentence>
                    </embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="08c2ba72e673a3e9402928261199ddd9" id="tgt72" class="tgtSentence">当你导入权限策略模板时，系统会将其状态存档。</caps:sentence>
                    <caps:sentence sentenceid="8aaca0e3f9f4c7fecf1d94bb31db19cb" id="tgt73" class="tgtSentence"> 如果你希望用户能够查看并使用这些模板，则必须在 Azure 经典门户中将模板状态更改为“已发布”。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="f1bcbb94613d91032d33beb396e5a9fb" id="tgt74" class="tgtSentence">有关说明，请参阅<link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172#BKMK_Step4Migration">Step 4. Configure imported templates</link>。</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>
                      <caps:sentence sentenceid="36bc033d5901e8e02c5002d980d60330" id="tgt75" class="tgtSentence">5.将客户端重新配置为使用 Azure RMS</caps:sentence>
                    </embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="d790da94e39cb677936e6eeb11395b79" id="tgt76" class="tgtSentence">必须将现有 Windows 计算机重新配置为使用 Azure RMS 服务而不是 AD RMS。</caps:sentence>
                    <caps:sentence sentenceid="355b2210f20722b85725ea57fa3f1f41" id="tgt77" class="tgtSentence"> 此步骤适用于你组织中的计算机以及合作伙伴组织(如果你在运行 AD RMS 时已与其协作)中的计算机。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="7ad5d9d2cdac24f0ee616a66e1c39ea0" id="tgt78" class="tgtSentence">此外，如果你部署了<externalLink><linkText>移动设备扩展</linkText><linkUri>http://technet.microsoft.com/library/dn673574.aspx</linkUri></externalLink>以支持移动设备（如 iOS 手机和 iPad、Android 手机和平板电脑、Windows phone 以及 Mac 计算机），你必须删除 DNS 中重定向这些客户端的 SRV 记录以使用 AD RMS。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="f1bcbb94613d91032d33beb396e5a9fb" id="tgt79" class="tgtSentence">有关说明，请参阅<link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172#BKMK_Step5Migration">Step 5. Reconfigure clients to use Azure RMS</link>。</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>
                      <caps:sentence sentenceid="f2632949f5cb705ab557a07f0a1b2e55" id="tgt80" class="tgtSentence">6.配置 IRM 与 Exchange Online 的集成</caps:sentence>
                    </embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="94ed4585c34b26e1c82a821e74d23a22" id="tgt81" class="tgtSentence">如果要将 Exchange Online 与 Azure RMS 配合使用，则必须执行此步骤。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="f1bcbb94613d91032d33beb396e5a9fb" id="tgt82" class="tgtSentence">有关说明，请参阅<link xlink:href="#BKMK_Step6Migration">Step 6. Configure IRM integration for Exchange Online</link>。</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>
                      <caps:sentence sentenceid="140da34a0e8f8faf3106d69800ecc7d5" id="tgt83" class="tgtSentence">7.部署 RMS 连接器</caps:sentence>
                    </embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="89a43e63b6d3568dbbea9c788ac5356a" id="tgt84" class="tgtSentence">如果要将以下任何本地服务与 Azure RMS 配合使用，此步骤是必需的：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="3dda89d997b4887b0621a65c9276e65f" id="tgt85" class="tgtSentence">Exchange Server（例如，传输规则和 Outlook Web Access）</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="7d2daf2c6bc276a6baf2ca2f452c6496" id="tgt86" class="tgtSentence">SharePoint Server </caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="0f9d889aedcac973e41b8531c65b8b2d" id="tgt87" class="tgtSentence">运行文件分类基础结构的 Windows Server</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <para>
                    <caps:sentence sentenceid="f1bcbb94613d91032d33beb396e5a9fb" id="tgt88" class="tgtSentence">有关说明，请参阅<link xlink:href="#BKMK_Step7Migration">Step 7. Deploy the RMS connector</link>。</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="9af7c117d9de9a06fba7a5f1ea5fcc2d" id="tgt89" class="tgtSentence">
                      <embeddedLabel>8.解除 AD RMS 的授权</embeddedLabel> </caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="cffedc4ac3b2e3b4f1bfd1908f34fb0c" id="tgt90" class="tgtSentence">当你已确认所有客户端均使用 Azure RMS 而不再访问 AD RMS 服务器，你可以解除 AD RMS 部署的授权。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="f1bcbb94613d91032d33beb396e5a9fb" id="tgt91" class="tgtSentence">有关说明，请参阅<link xlink:href="#BKMK_Step8Migration">Step 8. Decommission AD RMS</link>。</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>
                      <caps:sentence sentenceid="e44252b7e2b0818adae058a8f50bed7c" id="tgt92" class="tgtSentence">9.重新键入你的 Azure RMS 租户密钥</caps:sentence>
                    </embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="64d64f2292c30071e0b54747793b151c" id="tgt93" class="tgtSentence">如果在迁移前未运行加密模式 2，此步骤是必需的；对于所有迁移来说，此步骤是可选的但建议执行，以帮助保护 Azure RMS 租户密钥的安全性。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="f1bcbb94613d91032d33beb396e5a9fb" id="tgt94" class="tgtSentence">有关说明，请参阅<link xlink:href="#BKMK_Step9Migration">Step 9. Re-key your Azure RMS tenant key</link>。</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
        <sections>
          <section address="BKMK_Step1Migration">
            <title>
              <caps:sentence sentenceid="7805b4aef1ee01bb46d3e3066c48c22c" id="tgt95" class="tgtSentence">步骤 1：下载“Azure 权限管理”管理工具</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="569fffc045110bd6191896e6504d5ee6" id="tgt96" class="tgtSentence">转到 Microsoft 下载中心并下载 <externalLink><linkText>Azure Rights Management 管理工具</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=257721</linkUri></externalLink>，其中包含 Windows PowerShell 的 Azure RMS 管理模块。</caps:sentence>
              </para>
            </content>
          </section>
          <section address="BKMK_Step2Migration">
            <title>
              <caps:sentence sentenceid="bbda0a46b68df43bb2a6abe0b891d724" id="tgt97" class="tgtSentence">步骤 2.</caps:sentence>
              <caps:sentence sentenceid="3a70e246ce81a5a8263af846eafd4519" id="tgt98" class="tgtSentence"> 从 AD RMS 中导出配置数据并将其导入到 Azure RMS 中</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="514542f0d85c4624fe4ddbd36177d435" id="tgt99" class="tgtSentence">此步骤是一个分为两部分的过程：</caps:sentence>
              </para>
              <list class="ordered">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="0e3f916eef8ead3f8780cebc0df6fa84" id="tgt100" class="tgtSentence">通过将受信任的发布域 (TPD) 导出到 .xml 文件，从 AD RMS 导出配置数据。</caps:sentence>
                    <caps:sentence sentenceid="6a848f8ebb16d9f58d2a7ea4d2c61742" id="tgt101" class="tgtSentence"> 此过程对于所有迁移是相同的。</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="8c9d05771a9c8c5d9fb961ea6455f684" id="tgt102" class="tgtSentence">将配置数据导入到 Azure RMS。</caps:sentence>
                    <caps:sentence sentenceid="f48cec05328a3a3092c6a88f6d3fd85d" id="tgt103" class="tgtSentence"> 此步骤具有不同处理，具体取决于你的当前 AD RMS 部署配置以及 Azure RMS 租户密钥的首选拓扑。</caps:sentence>
                  </para>
                </listItem>
              </list>
            </content>
            <sections>
              <section>
                <title>
                  <caps:sentence sentenceid="a927df83adb490dccc1e9c178b4b52ea" id="tgt104" class="tgtSentence">从 AD RMS 导出配置数据</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence sentenceid="c6c0f805f214b635d7b303be0955fb3a" id="tgt105" class="tgtSentence">在所有 AD RMS 群集中，针对已保护你组织内容的所有受信任的发布域执行以下过程。</caps:sentence>
                    <caps:sentence sentenceid="d41c234d6ccf9e3b52dea221094a80b2" id="tgt106" class="tgtSentence"> 无需在仅授权群集上运行此过程。</caps:sentence>
                  </para>
                  <alert class="note">
                    <para>
                      <caps:sentence sentenceid="938561b99440632029af4d54e4ee67fa" id="tgt107" class="tgtSentence">如果你使用的是 Windows Server 2003 Rights Management，请按照<externalLink><linkText>从 Windows RMS 迁移到不同基础结构中的 AD RMS</linkText><linkUri>http://technet.microsoft.com/library/jj835767(v=ws.10).aspx</linkUri></externalLink> 主题中的过程<externalLink><linkText>导出 SLC、TUD、TPD 和 RMS 私钥</linkText><linkUri>http://technet.microsoft.com/library/jj835767(v=ws.10).aspx</linkUri></externalLink>（而不是按上述说明）进行操作。</caps:sentence>
                    </para>
                  </alert>
                  <procedure>
                    <title>
                      <caps:sentence sentenceid="96b8c7cc965fba3b6e5ae99fc1f084e1" id="tgt108" class="tgtSentence">导出配置数据（受信任的发布域信息）</caps:sentence>
                    </title>
                    <steps class="ordered">
                      <step>
                        <content>
                          <para>
                            <caps:sentence sentenceid="754c08bccb0f094ae7a6da26b52c1c5a" id="tgt109" class="tgtSentence">以具有 AD RMS 管理权限的用户身份登录到 AD RMS 群集。</caps:sentence>
                          </para>
                        </content>
                      </step>
                      <step>
                        <content>
                          <para>
                            <caps:sentence sentenceid="952d3e6193558e6b9cf79493fafae4a7" id="tgt110" class="tgtSentence">从 AD RMS 管理控制台 (<ui>Active Directory Rights Management Services</ui>)，展开 AD RMS 群集名称，展开“信任策略”，然后单击“受信任的发布域”<ui></ui><ui></ui>。</caps:sentence>
                          </para>
                        </content>
                      </step>
                      <step>
                        <content>
                          <para>
                            <caps:sentence sentenceid="1ac874db7a207ce084ea06f3d2c4ccb2" id="tgt111" class="tgtSentence">在结果窗格中，选择受信任的发布域，然后在操作窗格中单击“导出受信任的发布域”<ui></ui>。</caps:sentence>
                          </para>
                        </content>
                      </step>
                      <step>
                        <content>
                          <para>
                            <caps:sentence sentenceid="004dc0ceb5e9b2247446dc0a40f7a169" id="tgt112" class="tgtSentence">在“导出受信任的发布域”对话框中<ui></ui>： </caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="ccbe2a6c96a5df5e1966988e40064061" id="tgt113" class="tgtSentence">单击“另存为”并将其保存到所选的路径和文件名<ui></ui>。</caps:sentence>
                                <caps:sentence sentenceid="94326ec278af6643af1d92bfa45d7a0c" id="tgt114" class="tgtSentence"> 请确保指定 <userInput>.xml</userInput> 作为文件扩展名（此扩展名不会自动追加）。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="f2cbdf8071427b0d9f28809710ce3c21" id="tgt115" class="tgtSentence">指定并确认一个强密码。</caps:sentence>
                                <caps:sentence sentenceid="01960238fe98c1a575c1cff4c51fad09" id="tgt116" class="tgtSentence"> 请记住此密码，因为稍后在将配置数据导入到 Azure RMS 时，将需要此密码。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="93043851f494b0f5951a50628b8b220a" id="tgt117" class="tgtSentence">不要选中将受信任的域文件保存在 RMS 版本 1.0 中的复选框。</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </content>
                      </step>
                    </steps>
                    <conclusion>
                      <content>
                        <para>
                          <caps:sentence sentenceid="80db68cac396143711c135bff9c4904b" id="tgt118" class="tgtSentence">当你已导出所有受信任的发布域后，便可以启动将此数据导入到 Azure RMS 的过程了。</caps:sentence>
                        </para>
                      </content>
                    </conclusion>
                  </procedure>
                </content>
              </section>
              <section>
                <title>
                  <caps:sentence sentenceid="68e772f492c3ebc8b7a3f29b2fb84376" id="tgt119" class="tgtSentence">将配置数据导入到 Azure RMS</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence sentenceid="f3fa2011be807b30894fe8895bfe595c" id="tgt120" class="tgtSentence">此步骤的确切过程取决于你的当前 AD RMS 部署配置以及 Azure RMS 租户密钥的首选拓扑。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="22834af228ea32cbd0ff163a5e9b6331" id="tgt121" class="tgtSentence">你的当前 AD RMS 部署将对服务器许可方证书 (SLC) 密钥使用以下配置之一：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="a95a6f19e6157f4b93df09df5b6edcf8" id="tgt122" class="tgtSentence">AD RMS 数据库中的密码保护。</caps:sentence>
                        <caps:sentence sentenceid="32d0aeb2cbb512efc1db0c2d91b22d05" id="tgt123" class="tgtSentence"> 这是默认设置。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="8495b16466dcd05f59a7eafb503e325a" id="tgt124" class="tgtSentence">通过使用 Thales 硬件安全模块 (HSM) 进行 HSM 保护。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="fb54f72e2ce58ea366653d0e0f5762a8" id="tgt125" class="tgtSentence">通过使用 Thales 以外的供应商提供的硬件安全模块 (HSM) 进行 HSM 保护。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="c2eb35576d4bdaaf85e56ded33b3f45d" id="tgt126" class="tgtSentence">通过使用外部加密提供程序进行密码保护。</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <alert class="note">
                    <para>
                      <caps:sentence sentenceid="4a4ed69a5659a845b02f4807627c230c" id="tgt127" class="tgtSentence">有关将硬件安全模块与 AD RMS 配合使用的详细信息，请参阅<externalLink><linkText>将 AD RMS 与硬件安全模块配合使用</linkText><linkUri>http://technet.microsoft.com/library/jj651024.aspx</linkUri></externalLink>。</caps:sentence>
                    </para>
                  </alert>
                  <para>
                    <caps:sentence sentenceid="47287a38c1798822432c179a565636c1" id="tgt128" class="tgtSentence">两个 Azure RMS 租户密钥拓扑选项包括：Microsoft 管理你的租户密钥（<embeddedLabel>由 Microsoft 管理</embeddedLabel>），或者你自行管理租户密钥（<embeddedLabel>由客户管理</embeddedLabel>）。</caps:sentence>
                    <caps:sentence sentenceid="50be791a7cb39cce9b952df378a3730d" id="tgt129" class="tgtSentence"> 如果你自行管理 Azure RMS 租户密钥，则这有时也称为“自带密钥”(BYOK)，需要 Thales 提供的硬件安全模块 (HSM)。</caps:sentence>
                    <caps:sentence sentenceid="be021ab36c2c99a549fc25f5fcee238c" id="tgt130" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and Implementing Your Azure Rights Management Tenant Key</link>主题中的<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_ChooseTenantKey">Choose your tenant key topology: Managed by Microsoft (the default) or managed by you (BYOK)</link>部分。</caps:sentence>
                  </para>
                  <alert class="important">
                    <para>
                      <caps:sentence sentenceid="75d863f411e139d0a683b954fe84aa85" id="tgt131" class="tgtSentence"> Exchange Online 当前与 Azure RMS BYOK 不兼容。</caps:sentence>
                      <caps:sentence sentenceid="0e96c6c6fe380419563490e0d5843430" id="tgt132" class="tgtSentence">  如果你想要在迁移后使用 BYOK 并打算使用 Exchange Online，请务必了解，这种配置会缩减 Exchange Online 的 IRM 功能。</caps:sentence>
                      <caps:sentence sentenceid="876b8591adaaf6947b953603981b230a" id="tgt133" class="tgtSentence"> 请查看<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and Implementing Your Azure Rights Management Tenant Key</link>主题中的<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_Pricing">BYOK pricing and restrictions</link>部分，以帮助选择最适合你的迁移方案的 Azure RMS 租户密钥拓扑。</caps:sentence>
                    </para>
                  </alert>
                  <para>
                    <caps:sentence sentenceid="d9fb47d43d938970982d27ef116e1927" id="tgt134" class="tgtSentence">使用下表来确定要使用哪个过程进行迁移。</caps:sentence>
                    <caps:sentence sentenceid="a0cd56ea813cdfd0fdce182e4c17b1f3" id="tgt135" class="tgtSentence"> 不支持未列出的组合。</caps:sentence>
                  </para>
                  <table>
                    <thead>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="55bcf4aa8c710228c1687091120c1f8e" id="tgt136" class="tgtSentence">当前的 AD RMS 部署</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="42b6eea116fe2f5c1c1ec42ac067573f" id="tgt137" class="tgtSentence">已选择 Azure RMS 租户密钥拓扑</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="635c0bbff8d67282bf2607b2dc797c4f" id="tgt138" class="tgtSentence">迁移说明</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="7a27d6340f65f47727bf6a7923f48571" id="tgt139" class="tgtSentence">AD RMS 数据库中的密码保护</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="c5fb0d393ff6dd6a4e8740a507704f5a" id="tgt140" class="tgtSentence">由 Microsoft 管理</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="abda7877548e2693387fce7b54bf4008" id="tgt141" class="tgtSentence">请参阅此表后面的<embeddedLabel>软件保护密钥到软件保护密钥的迁移</embeddedLabel>过程。</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence sentenceid="1cf2ec56d8c98b2d3dff7a9e80d74358" id="tgt142" class="tgtSentence">这是最简单的迁移路径，只需要将配置数据传输到 Azure RMS。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="a2038560ad20a765998daa21a9ba9a90" id="tgt143" class="tgtSentence">通过使用 Thales nShield 硬件安全模块 (HSM) 进行 HSM 保护</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="bb42b180ba57d0d33beaafa4ec1de882" id="tgt144" class="tgtSentence">由客户管理 (BYOK)</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="abda7877548e2693387fce7b54bf4008" id="tgt145" class="tgtSentence">请参阅此表后面的 <embeddedLabel>HSM 保护密钥到 HSM 保护密钥的迁移</embeddedLabel>过程。</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence sentenceid="49cdd820f8e663f23c1fee45b68a8214" id="tgt146" class="tgtSentence">这需要 BYOK 工具集和以下两组步骤：将密钥从本地 HSM 传输到 Azure RMS HSM，然后将配置数据传输到 Azure RMS。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="7a27d6340f65f47727bf6a7923f48571" id="tgt147" class="tgtSentence">AD RMS 数据库中的密码保护</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="bb42b180ba57d0d33beaafa4ec1de882" id="tgt148" class="tgtSentence">由客户管理 (BYOK)</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="abda7877548e2693387fce7b54bf4008" id="tgt149" class="tgtSentence">请参阅此表后面的<embeddedLabel>软件保护密钥到 HSM 保护密钥的迁移</embeddedLabel>过程。</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence sentenceid="e6208ea50baab5801f04a600ddcccdea" id="tgt150" class="tgtSentence">这需要 BYOK 工具集和以下三组步骤：首先提取软件密钥并将其导入到本地 HSM，然后将密钥从本地 HSM 传输到 Azure RMS HSM，最后将配置数据传输到 Azure RMS。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="1cccf4e07e7352ab837a0c52cc12bcf5" id="tgt151" class="tgtSentence">通过使用 Thales 以外的供应商提供的硬件安全模块 (HSM) 进行 HSM 保护</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="bb42b180ba57d0d33beaafa4ec1de882" id="tgt152" class="tgtSentence">由客户管理 (BYOK)</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="0fbbef83992d74ba964154c296f2b7d1" id="tgt153" class="tgtSentence">与 HSM 供应商联系以获取有关如何将密钥从此 HSM 传输到 Thales nShield 硬件安全模块 (HSM) 的说明。</caps:sentence>
                            <caps:sentence sentenceid="a4c97bd314b44cc9ee64777264117bf4" id="tgt154" class="tgtSentence"> 然后遵照此表后面的 <embeddedLabel>HSM 保护密钥到 HSM 保护密钥的迁移</embeddedLabel>过程中的说明。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="fbf74c8a30e188f501f77cce6b17f673" id="tgt155" class="tgtSentence">通过使用外部加密提供程序进行密码保护</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="bb42b180ba57d0d33beaafa4ec1de882" id="tgt156" class="tgtSentence">由客户管理 (BYOK)</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="c133b46736ecd35151ad19d805c089ec" id="tgt157" class="tgtSentence">与加密提供程序的供应商联系以获取有关如何将密钥传输到 Thales nShield 硬件安全模块 (HSM) 的说明。</caps:sentence>
                            <caps:sentence sentenceid="a4c97bd314b44cc9ee64777264117bf4" id="tgt158" class="tgtSentence"> 然后遵照此表后面的 <embeddedLabel>HSM 保护密钥到 HSM 保护密钥的迁移</embeddedLabel>过程中的说明。</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </tbody>
                  </table>
                  <para>
                    <caps:sentence sentenceid="2b99df0603fbc3ab0b245064051af3da" id="tgt159" class="tgtSentence">在开始这些过程之前，请确保你可以访问先前在导出受信任的发布域时创建的 .xml 文件。</caps:sentence>
                    <caps:sentence sentenceid="bf3769f079784f5b46c3cd09f212bfad" id="tgt160" class="tgtSentence"> 例如，可以将这些文件保存到从 AD RMS 服务器移到接入 Internet 的工作站的 U 盘。</caps:sentence>
                  </para>
                  <alert class="security note">
                    <para>
                      <caps:sentence sentenceid="78c4993d05d81a47dfcb2bfcb645029e" id="tgt161" class="tgtSentence">但是，你将存储这些文件，请使用安全最佳做法来保护它们，因为此数据包含你的私钥。</caps:sentence>
                    </para>
                  </alert>
                </content>
                <sections>
                  <section expanded="false">
                    <title>
                      <caps:sentence sentenceid="43a577cfe853156c7b9287f847f8fa60" id="tgt162" class="tgtSentence">软件保护密钥到软件保护密钥的迁移</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="dc891f09233b1692de4d142e20c73b14" id="tgt163" class="tgtSentence">使用此过程将 AD RMS 配置导入到 Azure RMS，以生成由 Microsoft 管理的 Azure RMS 租户密钥。</caps:sentence>
                      </para>
                      <procedure>
                        <title>
                          <caps:sentence sentenceid="e080f04ad82c2e0822ae16145b991993" id="tgt164" class="tgtSentence">将配置数据导入到 Azure RMS</caps:sentence>
                        </title>
                        <steps class="ordered">
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="1a58a0749a5ef4600f28cc3abc7ed4ee" id="tgt165" class="tgtSentence">在连接 Internet 的工作站上，下载并安装用于 Azure RMS 的 Windows PowerShell 模块（最低版本 2.1.0.0），其中包括 <externalLink><linkText>Import-AadrmTpd</linkText><linkUri>http://msdn.microsoft.com/library/azure/dn857523.aspx</linkUri></externalLink> cmdlet。</caps:sentence>
                              </para>
                              <alert class="tip">
                                <para>
                                  <caps:sentence sentenceid="ad9de9badcaf0c18cff82a61c9291579" id="tgt166" class="tgtSentence">如果你以前已下载并安装过该模块，请通过运行以下命令检查版本号：<codeInline>(Get-Module aadrm -ListAvailable).Version</codeInline></caps:sentence>
                                </para>
                              </alert>
                              <para>
                                <caps:sentence sentenceid="9b8b89d25f443ebfc7497fedc34ed4ca" id="tgt167" class="tgtSentence">有关安装说明，请参阅<link xlink:href="0d665ed6-b1de-4d63-854a-bc57c1c49844">Installing Windows PowerShell for Azure Rights Management</link>。</caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="986a1e9cf69d28fc407425532bc33082" id="tgt168" class="tgtSentence">使用“以管理员身份运行”<ui></ui>选项启动 Windows PowerShell，然后使用 <externalLink><linkText>Connect-AadrmService</linkText><linkUri>http://msdn.microsoft.com/library/azure/dn629415.aspx</linkUri></externalLink> cmdlet 连接到 Azure RMS 服务：</caps:sentence>
                              </para>
                              <code>Connect-AadrmService</code>
                              <para>
                                <caps:sentence sentenceid="4029bc06e3eeccb6ce05b9512cc14d97" id="tgt169" class="tgtSentence">出现提示时，输入 <token>aad_rightsmanagement_1</token> 租户管理员凭据（通常，将使用作为 Azure Active Directory 或 Office 365 的全局管理员的帐户）。</caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="16859c9da62799922bc88b1c7de34fc3" id="tgt170" class="tgtSentence">使用 <externalLink><linkText>Import-AadrmTpd</linkText><linkUri>http://msdn.microsoft.com/library/azure/dn857523.aspx</linkUri></externalLink> cmdlet 上载首先导出的受信任发布域 (.xml) 文件。</caps:sentence>
                                <caps:sentence sentenceid="14a9730d980469ea1785fc40d3011ad4" id="tgt171" class="tgtSentence"> 如果你有多个 .xml 文件（因为有多个受信任发布域），请选择包含已导出受信任发布域的文件，你要在 Azure RMS 中使用该文件来在迁移后保护内容。</caps:sentence>
                                <caps:sentence sentenceid="8b30551c6f81bc11c5e9502037601555" id="tgt172" class="tgtSentence"> 使用以下命令：</caps:sentence>
                              </para>
                              <code>Import-AadrmTpd -TpdFile &lt;PathToTpdPackageFile&gt; -ProtectionPassword -Active $True -Verbose 
</code>
                              <para>
                                <caps:sentence sentenceid="d05370276e06291b048268558cc39bee" id="tgt173" class="tgtSentence">例如：<userInput>Import-AadrmTpd -TpdFile E:\contosokey1.xml -ProtectionPassword -Active $true -Verbose</userInput></caps:sentence>
                              </para>
                              <para>
                                <caps:sentence sentenceid="bdf90db64bc835dde7ee09fe0c01bd71" id="tgt174" class="tgtSentence">出现提示时，输入你先前指定的密码，并确认要执行此操作。</caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="8afeeaa5d17a9f91abb0fcc38cecfbb6" id="tgt175" class="tgtSentence">该命令完成后，请对你通过导出受信任发布域创建的每个剩余 .xml 文件重复执行步骤 3。</caps:sentence>
                                <caps:sentence sentenceid="84b5ba88804238a7fab867f8f0ae13d5" id="tgt176" class="tgtSentence"> 但对于这些文件，在运行 Import 命令时将 <userInput>-Active</userInput> 设为 <userInput>false</userInput>。</caps:sentence>
                                <caps:sentence sentenceid="407e8379b5443b7c0092c35c8bab7f29" id="tgt177" class="tgtSentence"> 例如：<userInput>Import-AadrmTpd -TpdFile E:\contosokey2.xml -ProtectionPassword -Active $false -Verbose</userInput></caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="16859c9da62799922bc88b1c7de34fc3" id="tgt178" class="tgtSentence">使用 <externalLink><linkText>Disconnect-AadrmService</linkText><linkUri>http://msdn.microsoft.com/library/azure/dn629416.aspx</linkUri></externalLink> cmdlet 断开与 Azure RMS 服务的连接：</caps:sentence>
                              </para>
                              <code>Disconnect-AadrmService</code>
                            </content>
                          </step>
                        </steps>
                        <conclusion>
                          <content>
                            <para>
                              <caps:sentence sentenceid="e8393e916064352781cb463d173cc280" id="tgt179" class="tgtSentence">现在，你已可以转到<link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172#BKMK_Step3Migration">Step 3. Activate your RMS tenant</link>了。</caps:sentence>
                            </para>
                          </content>
                        </conclusion>
                      </procedure>
                    </content>
                  </section>
                  <section expanded="false">
                    <title>
                      <caps:sentence sentenceid="79d770e64ba910a7d3a1919258322d15" id="tgt180" class="tgtSentence">HSM 保护密钥到 HSM 保护密钥的迁移</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="7fc31851698774585cee1419d3e4fbf0" id="tgt181" class="tgtSentence">此过程分为两部分，可将 HSM 密钥和 AD RMS 配置导入到 Azure RMS，以生成由你管理的 Azure RMS 租户密钥 (BYOK)。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="7307f9fbc74ce9ad6a544238b4f83f47" id="tgt182" class="tgtSentence">你必须先打包 HSM 密钥以便随时可将其传输到 Azure RMS，然后再将其连同配置数据一起导入。</caps:sentence>
                      </para>
                      <procedure>
                        <title>
                          <caps:sentence sentenceid="1568a99c9922711ef507dce608aeef93" id="tgt183" class="tgtSentence">第 1 部分：打包 HSM 密钥以便随时可将其传输到 Azure RMS</caps:sentence>
                        </title>
                        <steps class="ordered">
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="1ce48bdd76c7b3edd2f11eb0283fe381" id="tgt184" class="tgtSentence">使用过程<embeddedLabel>生成并传输租户密钥 - 通过 Internet</embeddedLabel>，并按照<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and Implementing Your Azure Rights Management Tenant Key</link>的<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_ImplementBYOK">Implementing bring your own key (BYOK)</link>部分中的步骤进行操作，但以下两点例外：</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="034d95d731d57d6b533537bbc00fb872" id="tgt185" class="tgtSentence">不要遵循<embeddedLabel>生成你的租户密钥</embeddedLabel>中的步骤，因为你已从 AD RMS 部署获得等效物。</caps:sentence>
                                    <caps:sentence sentenceid="546dfa9ba2d608126cf2bfcc448bf164" id="tgt186" class="tgtSentence"> 你必须标识 AD RMS 服务器使用的从 Thales 安装获得的密钥，并在迁移期间使用此密钥。</caps:sentence>
                                    <caps:sentence sentenceid="854d132d1b3341bceb61d290ca83fa92" id="tgt187" class="tgtSentence"> Thales 加密的密钥文件通常在本地服务器上名为 <ui>key_(keyAppName)_(keyIdentifier)</ui>。</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="034d95d731d57d6b533537bbc00fb872" id="tgt188" class="tgtSentence">不要遵循<embeddedLabel>将你的租户密钥传送到 Azure RMS</embeddedLabel> 中的步骤，因为此操作使用 Add-AadrmKey 命令。</caps:sentence>
                                    <caps:sentence sentenceid="bb1a16ebb8482461d33a9081c7ce4233" id="tgt189" class="tgtSentence">  你应该在上载所导出的受信任发布域时，使用 Import-AadrmTpd 命令传输你准备好的 HSM 密钥。</caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="92b256a028ba1ac9ab443940bbae1e90" id="tgt190" class="tgtSentence">在已连接 Internet 的工作站上，通过 Windows PowerShell 会话重新连接到 Azure RMS 服务。</caps:sentence>
                              </para>
                            </content>
                          </step>
                        </steps>
                        <conclusion>
                          <content>
                            <para>
                              <caps:sentence sentenceid="6b711d337027506973104e4c461927a7" id="tgt191" class="tgtSentence">现在，你已经为 Azure RMS 准备好了 HSM 密钥，接下来可以导入 HSM 密钥文件和 AD RMS 配置数据。</caps:sentence>
                            </para>
                          </content>
                        </conclusion>
                      </procedure>
                      <procedure>
                        <title>
                          <caps:sentence sentenceid="a77dc71f92c3decdd8206e8fcffa89b8" id="tgt192" class="tgtSentence">第 2 部分：将 HSM 密钥和配置数据导入到 Azure RMS</caps:sentence>
                        </title>
                        <steps class="ordered">
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="1983fc332527e4f1b93ca306553c042a" id="tgt193" class="tgtSentence">仍在连接 Internet 的工作站上的 Windows PowerShell 会话中，上载首先导出的受信任发布域 (.xml) 文件。</caps:sentence>
                                <caps:sentence sentenceid="dac6d0c09c16fbd0c73804284e571477" id="tgt194" class="tgtSentence"> 如果你有多个 .xml 文件（因为有多个受信任发布域），请选择包含与 HSM 密钥对应的已导出受信任发布域的文件，你要在 Azure RMS 中使用该文件来在迁移后保护内容。</caps:sentence>
                                <caps:sentence sentenceid="8b30551c6f81bc11c5e9502037601555" id="tgt195" class="tgtSentence"> 使用以下命令：</caps:sentence>
                              </para>
                              <code>Import-AadrmTpd -TpdFile &lt;PathToTpdPackageFile&gt; -ProtectionPassword -HsmKeyFile &lt;PathToBYOKPackage&gt; -Active $True -Verbose</code>
                              <para>
                                <caps:sentence sentenceid="d05370276e06291b048268558cc39bee" id="tgt196" class="tgtSentence">例如：<userInput>Import -TpdFile E:\no_key_tpd_contosokey1.xml  -HsmKeyFile E:\KeyTransferPackage-contosokey.byok -ProtectionPassword -Active $true -Verbose</userInput></caps:sentence>
                              </para>
                              <para>
                                <caps:sentence sentenceid="bdf90db64bc835dde7ee09fe0c01bd71" id="tgt197" class="tgtSentence">出现提示时，输入你先前指定的密码，并确认要执行此操作。</caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="304c3a82083750773bf4fa16c248bea7" id="tgt198" class="tgtSentence">该命令完成后，请对你通过导出受信任发布域创建的每个剩余 .xml 文件重复执行步骤 1。</caps:sentence>
                                <caps:sentence sentenceid="84b5ba88804238a7fab867f8f0ae13d5" id="tgt199" class="tgtSentence"> 但对于这些文件，在运行 Import 命令时将 <userInput>-Active</userInput> 设为 <userInput>false</userInput>。</caps:sentence>
                                <caps:sentence sentenceid="969122afb7e203ce34ae3ffc285d83e5" id="tgt200" class="tgtSentence">  例如：<userInput>Import -TpdFile E:\contosokey2.xml -HsmKeyFile E:\KeyTransferPackage-contosokey.byok -ProtectionPassword -Active $false -Verbose</userInput></caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="16859c9da62799922bc88b1c7de34fc3" id="tgt201" class="tgtSentence">使用 <externalLink><linkText>Disconnect-AadrmService</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629416.aspx</linkUri></externalLink> cmdlet 断开与 Azure RMS 服务的连接：</caps:sentence>
                              </para>
                              <code>Disconnect-AadrmService</code>
                            </content>
                          </step>
                        </steps>
                        <conclusion>
                          <content>
                            <para>
                              <caps:sentence sentenceid="e8393e916064352781cb463d173cc280" id="tgt202" class="tgtSentence">现在，你已可以转到<link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172#BKMK_Step3Migration">Step 3. Activate your RMS tenant</link>了。</caps:sentence>
                            </para>
                          </content>
                        </conclusion>
                      </procedure>
                    </content>
                  </section>
                  <section expanded="false">
                    <title>
                      <caps:sentence sentenceid="e449bff9e10c98b1a91495f05606d77c" id="tgt203" class="tgtSentence">软件保护密钥到 HSM 保护密钥的迁移</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="d400abc307e43a60c9fb7b6a47454cef" id="tgt204" class="tgtSentence">此过程分为三部分，用于将 AD RMS 配置导入到 Azure RMS，以生成由你管理的 Azure RMS 租户密钥 (BYOK)。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="9ba71160e9807c77cf11bfb30ec09012" id="tgt205" class="tgtSentence">必须首先从配置数据中提取服务器许可方证书 (SLC) 密钥并将该密钥传输到本地 Thales HSM，然后打包 HSM 密钥并将其传输到 Azure RMS，最后导入配置数据。</caps:sentence>
                      </para>
                      <procedure>
                        <title>
                          <caps:sentence sentenceid="c4313a333fe6f83b450cb5698458a23d" id="tgt206" class="tgtSentence">第 1 部分：从配置数据中提取 SLC，并将密钥导入到本地 HSM</caps:sentence>
                        </title>
                        <steps class="ordered">
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="2564f9d4990abdb6c8406c2678526798" id="tgt207" class="tgtSentence">使用<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and Implementing Your Azure Rights Management Tenant Key</link>主题的<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_ImplementBYOK">Implementing bring your own key (BYOK)</link> 部分中的以下步骤：</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="e265492707dd0595fd1f399bb8a2690e" id="tgt208" class="tgtSentence">
                                      <embeddedLabel>生成和传送租户密钥 – 通过 Internet</embeddedLabel>：<embeddedLabel>准备你的连接 Internet 的工作站</embeddedLabel></caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="e265492707dd0595fd1f399bb8a2690e" id="tgt209" class="tgtSentence">
                                      <embeddedLabel>生成和传送租户密钥 – 通过 Internet</embeddedLabel>：<embeddedLabel>准备你的未连接工作站</embeddedLabel></caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                              <para>
                                <caps:sentence sentenceid="5a805607a590f53bd5c9d48ac363568b" id="tgt210" class="tgtSentence">不用按照这些步骤生成租户密钥，因为你在导出的配置数据 (.xml) 文件中已有等效项。</caps:sentence>
                                <caps:sentence sentenceid="7914923580376d1d1f2635fb1da8c681" id="tgt211" class="tgtSentence"> 你将改为运行命令以从该文件中提取此密钥并将其导入到本地 HSM。</caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="9016ee10dbce7c06044a304e2f389ba6" id="tgt212" class="tgtSentence">在断开连接的工作站上，运行以下命令：</caps:sentence>
                              </para>
                              <code>KeyTransferRemote.exe -ImportRmsCentrallyManagedKey -TpdFilePath &lt;TPD&gt; -ProtectionPassword -KeyIdentifier &lt;KeyID&gt; -ExchangeKeyPackage &lt;BYOK-KEK-pka-Region&gt; -NewSecurityWorldPackage &lt;BYOK-SecurityWorld-pkg-Region&gt;</code>
                              <para>
                                <caps:sentence sentenceid="6767ded2b561c516fe3b5e56f147abb2" id="tgt213" class="tgtSentence">例如，对于北美地区：<userInput>KeyTransferRemote.exe -ImportRmsCentrallyManagedKey -TpdFilePath E:\contosokey1.xml -ProtectionPassword -KeyIdentifier contosorms1key –- -ExchangeKeyPackage &lt;BYOK-KEK-pka-NA-1&gt; -NewSecurityWorldPackage &lt;BYOK-SecurityWorld-pkg-NA-1&gt;</userInput></caps:sentence>
                              </para>
                              <para>
                                <caps:sentence sentenceid="c80e9d4e4171ecff41ff04fe5ffb6917" id="tgt214" class="tgtSentence">其他信息:</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="2c3e87f07013ef0a820ba4ac0a783bf6" id="tgt215" class="tgtSentence">ImportRmsCentrallyManagedKey 参数指示该操作是导入 SLC 密钥。</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="4e5876f46a374c209a1e8c7efd766687" id="tgt216" class="tgtSentence">如果你未在命令中指定密码，则将提示你指定它。</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="f35edd5674fb649f724c48b7fc8d0e0d" id="tgt217" class="tgtSentence">KeyIdentifier 参数指定用于创建密钥文件名的密钥友好名称。</caps:sentence>
                                    <caps:sentence sentenceid="cd4bb580bcc724e7dc7935c08d1f4c74" id="tgt218" class="tgtSentence"> 你必须使用仅小写的 ASCII 字符。</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="f4c9e89632c9d7b293e21cf54b05a895" id="tgt219" class="tgtSentence">ExchangeKeyPackage 参数指定特定于区域的密钥交换密钥 (KEK) 软件包，该软件包的名称以“BYOK-KEK-pkg-”开头。</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="54a153639be36aa861863090c1177601" id="tgt220" class="tgtSentence">NewSecurityWorldPackage 参数指定特定于区域的安全体系包，该包的名称以“BYOK-SecurityWorld-pkg-”开头。</caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                              <para>
                                <caps:sentence sentenceid="e5594da2d2abc1ae7ca06668f59a1137" id="tgt221" class="tgtSentence">此命令将生成以下项：</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="e8a38bb7eea904f2107c52e55618741e" id="tgt222" class="tgtSentence">HSM 密钥文件：%NFAST_KMDATA%\local\key_mscapi_&lt;KeyID&gt;</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="191abb451b135925ecdd57fbdaa14073" id="tgt223" class="tgtSentence">SLC 已被删除的 RMS 配置数据文件：%NFAST_KMDATA%\local\no_key_tpd_&lt;KeyID&gt;.xml</caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="8b29675e8a1f53d8c8bb17a9b75f49cd" id="tgt224" class="tgtSentence">如果你有多个 RMS 配置数据文件，请对这些文件的其余部分重复执行步骤 2。</caps:sentence>
                              </para>
                            </content>
                          </step>
                        </steps>
                        <conclusion>
                          <content>
                            <para>
                              <caps:sentence sentenceid="dee04f3f6ad3a9c25d19ee34a0df0c9f" id="tgt225" class="tgtSentence">现在，你已提取 SLC 使其成为基于 HSM 的密钥，你已可以将其打包并传输到 Azure RMS 了。</caps:sentence>
                            </para>
                          </content>
                        </conclusion>
                      </procedure>
                      <procedure>
                        <title>
                          <caps:sentence sentenceid="2feaabefc7c24d6f622cb7dca95621bf" id="tgt226" class="tgtSentence">第 2 部分：打包 HSM 密钥并将其传输到 Azure RMS</caps:sentence>
                        </title>
                        <steps class="ordered">
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="e70e56cdb9cdcd5fb91a2d69e891961f" id="tgt227" class="tgtSentence">使用<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and Implementing Your Azure Rights Management Tenant Key</link>的<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_ImplementBYOK">Implementing bring your own key (BYOK)</link>部分中的以下步骤：</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="e265492707dd0595fd1f399bb8a2690e" id="tgt228" class="tgtSentence">
                                      <embeddedLabel>生成和传送租户密钥 – 通过 Internet</embeddedLabel>：<embeddedLabel>准备要传送的租户密钥</embeddedLabel></caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="e265492707dd0595fd1f399bb8a2690e" id="tgt229" class="tgtSentence">
                                      <embeddedLabel>生成和传送租户密钥 – 通过 Internet</embeddedLabel>：<embeddedLabel>将你的租户密钥传送到 Azure RMS</embeddedLabel></caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                            </content>
                          </step>
                        </steps>
                        <conclusion>
                          <content>
                            <para>
                              <caps:sentence sentenceid="bc050b6d0f973332c1adf193ac13fd8b" id="tgt230" class="tgtSentence">现在，你已将 HSM 密钥传输到 Azure RMS，已可以导入 AD RMS 配置数据（其中只包含指向新传输的租户密钥的指针）了。</caps:sentence>
                            </para>
                          </content>
                        </conclusion>
                      </procedure>
                      <procedure>
                        <title>
                          <caps:sentence sentenceid="630383ca2e18816108cce9cc20ec87c8" id="tgt231" class="tgtSentence">第 3 部分：将配置数据导入到 Azure RMS</caps:sentence>
                        </title>
                        <steps class="ordered">
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="52dde1ac053f9367b40671e8c20eb102" id="tgt232" class="tgtSentence">仍在连接 Internet 的工作站上的 Windows PowerShell 会话中，从断开连接的工作站复制删除了 SLC 的 RMS 配置文件 (%NFAST_KMDATA%\local\no_key_tpd_&lt;KeyID&gt;.xml)</caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="202bd58572981ff5eeb24c2b1e3cf44b" id="tgt233" class="tgtSentence">上载第一个文件。</caps:sentence>
                                <caps:sentence sentenceid="dac6d0c09c16fbd0c73804284e571477" id="tgt234" class="tgtSentence"> 如果你有多个 .xml 文件（因为有多个受信任发布域），请选择包含与 HSM 密钥对应的已导出受信任发布域的文件，你要在 Azure RMS 中使用该文件来在迁移后保护内容。</caps:sentence>
                                <caps:sentence sentenceid="8b30551c6f81bc11c5e9502037601555" id="tgt235" class="tgtSentence"> 使用以下命令：</caps:sentence>
                              </para>
                              <code>Import-AadrmTpd -TpdFile &lt;PathToNoKeyTpdPackageFile&gt; -ProtectionPassword -HsmKeyFile &lt;PathToKeyTransferPackage&gt; -Active $true -Verbose </code>
                              <para>
                                <caps:sentence sentenceid="d05370276e06291b048268558cc39bee" id="tgt236" class="tgtSentence">例如：<userInput>Import -TpdFile E:\no_key_tpd_contosorms1key.xml -ProtectionPassword -HsmKeyFile E:\KeyTransferPackage-contosorms1key.byok -Active $true -Verbose </userInput></caps:sentence>
                              </para>
                              <para>
                                <caps:sentence sentenceid="bdf90db64bc835dde7ee09fe0c01bd71" id="tgt237" class="tgtSentence">出现提示时，输入你先前指定的密码，并确认要执行此操作。</caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="ac0901fe2044dcb2cc068b7524667831" id="tgt238" class="tgtSentence">该命令完成后，请对你通过导出受信任发布域创建的每个剩余 .xml 文件重复执行步骤 2。</caps:sentence>
                                <caps:sentence sentenceid="84b5ba88804238a7fab867f8f0ae13d5" id="tgt239" class="tgtSentence"> 但对于这些文件，在运行 Import 命令时将 <userInput>-Active</userInput> 设为 <userInput>false</userInput>。</caps:sentence>
                                <caps:sentence sentenceid="407e8379b5443b7c0092c35c8bab7f29" id="tgt240" class="tgtSentence"> 例如：<userInput>Import -TpdFile E:\no_key_tpd_contosorms2key.xml -ProtectionPassword -HsmKeyFile E:\KeyTransferPackage-contosorms1key.byok -Active $false -Verbose </userInput></caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="16859c9da62799922bc88b1c7de34fc3" id="tgt241" class="tgtSentence">使用 <externalLink><linkText>Disconnect-AadrmService</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629416.aspx</linkUri></externalLink> cmdlet 断开与 Azure RMS 服务的连接：</caps:sentence>
                              </para>
                              <code>Disconnect-AadrmService</code>
                            </content>
                          </step>
                        </steps>
                        <conclusion>
                          <content>
                            <para>
                              <caps:sentence sentenceid="e8393e916064352781cb463d173cc280" id="tgt242" class="tgtSentence">现在，你已可以转到<link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172#BKMK_Step3Migration">Step 3. Activate your RMS tenant</link>了。</caps:sentence>
                            </para>
                          </content>
                        </conclusion>
                      </procedure>
                    </content>
                  </section>
                </sections>
              </section>
            </sections>
          </section>
          <section address="BKMK_Step3Migration">
            <title>
              <caps:sentence sentenceid="109514fd8cd9e2015190a63d21e7c991" id="tgt243" class="tgtSentence">步骤 3.</caps:sentence>
              <caps:sentence sentenceid="ffa6ca6573c72d8f004b6b25226f1468" id="tgt244" class="tgtSentence"> 激活你的 RMS 租户</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="3fa616e8d09f47e4613a608a5ab40b61" id="tgt245" class="tgtSentence">
                  <link xlink:href="f8707e01-b239-4d1a-a1ea-0d1cf9a8d214">Activating Azure Rights Management</link>主题中全面说明了此步骤。</caps:sentence>
              </para>
              <alert class="tip">
                <para>
                  <caps:sentence sentenceid="9a3fec79df6d035db9bf50b7636f1e25" id="tgt246" class="tgtSentence">如果你有 Office 365 订阅，则可以从 Office 365 管理中心或 Azure 经典门户激活 Azure RMS。</caps:sentence>
                  <caps:sentence sentenceid="af78cd8483c136c8b7fc88eda98f497b" id="tgt247" class="tgtSentence"> 建议你使用 Azure 经典门户，因为你将使用该管理门户来完成下一步操作。</caps:sentence>
                </para>
              </alert>
              <para>
                <caps:sentence sentenceid="62576c444793c839ecacd1bae075cafd" id="tgt248" class="tgtSentence">
                  <embeddedLabel>如果 Azure RMS 租户已激活了会怎么样？</embeddedLabel>如果已经为你的组织激活了 Azure RMS 服务，则用户可能已使用 Azure RMS 和自动生成的租户密钥（与默认模板）而不是 AD RMS 中的现有密钥（和模板）来保护内容。</caps:sentence>
                <caps:sentence sentenceid="0ed02c45af6fb8a877cd0de9328b63b7" id="tgt249" class="tgtSentence"> 在 Intranet 中妥善管理的计算机上不太可能会发生这种情况，因为这些计算机会自动根据 AD RMS 基础结构进行配置。</caps:sentence>
                <caps:sentence sentenceid="c65d1ddccf3401da27a54736965d9b50" id="tgt250" class="tgtSentence"> 但是，在工作组计算机或很少连接到 Intranet 的计算机上，可能会发生这种情况。</caps:sentence>
                <caps:sentence sentenceid="61a9c88a9e631bef540eede6fd229823" id="tgt251" class="tgtSentence"> 遗憾的是，这些计算机也很难识别，正因如此，我们建议在从 AD RMS 导入配置数据之前不要激活该服务。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="587749ba1f609ee7f51650ee509c8a99" id="tgt252" class="tgtSentence">如果你的 Azure RMS 租户已激活并且可以识别这些计算机，请确保根据步骤 5 中所述，在这些计算机上运行 CleanUpRMS_RUN_Elevated.cmd 脚本。</caps:sentence>
                <caps:sentence sentenceid="202ffab1a468fd4607ec7254f9a2d368" id="tgt253" class="tgtSentence"> 运行此脚本会强制这些计算机重新初始化用户环境，以便下载更新的租户密钥和导入的模板。</caps:sentence>
              </para>
            </content>
          </section>
          <section address="BKMK_Step4Migration">
            <title>
              <caps:sentence sentenceid="323241aef2be0c46e26a80632199dfb4" id="tgt254" class="tgtSentence">步骤 4.</caps:sentence>
              <caps:sentence sentenceid="dec2d8c6239478bcc3df92273496f727" id="tgt255" class="tgtSentence"> 配置导入的模板</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="789e297da3c8f43f2e89dfb802da264a" id="tgt256" class="tgtSentence">由于你导入的模板具有“已存档”的默认状态，如果你希望用户能够将这些模板用于 Azure RMS，必须将此状态更改为“已发布”<ui></ui><ui></ui>。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="790354c8613148f9f8cfd8a6b3f0df3c" id="tgt257" class="tgtSentence">此外，如果你在 AD RMS 中的模板使用 <ui>ANYONE</ui> 组，则当你将这些模板导入 Azure RMS 中时，系统会自动删除该组；你必须将相应的组或用户以及相同的权限手动添加到已导入的模板中。</caps:sentence>
                <caps:sentence sentenceid="4680928f50076c8a650c95ec8f5882a5" id="tgt258" class="tgtSentence"> 与 Azure RMS 相对应的组名为 <system>AllStaff-&lt;tenant_GUID&gt;@&lt;tenant_name&gt;.onmicrosoft.com</system>。</caps:sentence>
                <caps:sentence sentenceid="4f2a8e43314a42a39d01921595a49e66" id="tgt259" class="tgtSentence"> 例如，如果公司为 Contoso，则该组可能会如下所示：<system>AllStaff-9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a@contoso.onmicrosoft.com</system>。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="5e74cf089e636e7ec5b7c1259ccb81ac" id="tgt260" class="tgtSentence">如果你不确定你的 AD RMS 模板是否包括 ANYONE 组，请在此步骤中展开 <link xlink:href="#BKMK_ScriptForANYONE">PowerShell script to identify AD RMS templates that include the ANYONE group</link> 节以复制并使用示例 PowerShell 脚本来标识这些模板。</caps:sentence>
                <caps:sentence sentenceid="c67985e4e4ceb311ab268f8f6998e0f8" id="tgt261" class="tgtSentence"> 有关将 Windows PowerShell 用于 AD RMS 的详细信息，请参阅 <externalLink><linkText>使用 Windows PowerShell 管理 AD RMS</linkText><linkUri>https://technet.microsoft.com/library/ee221079(v=ws.10).aspx</linkUri></externalLink>。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="8d85b35bc3605b384c6479e039a283e2" id="tgt262" class="tgtSentence">你可以看到组织自动创建的组，前提是将某个默认权限策略模板复制到 Azure 经典门户中，然后确定“权限”页上的“用户名”。<ui></ui><ui></ui></caps:sentence>
                <caps:sentence sentenceid="80c94e27704f7aff98c5dd1f0780e712" id="tgt263" class="tgtSentence"> 但是，你不能使用经典门户将该组添加到已手动创建或导入的模板中，而是必须使用以下 Azure RMS PowerShell 选项之一：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="16859c9da62799922bc88b1c7de34fc3" id="tgt264" class="tgtSentence">使用 <externalLink><linkText>New-AadrmRightsDefinition</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn727080.aspx</linkUri></externalLink> PowerShell cmdlet 将“AllStaff”组和权限定义为权限定义对象，然后除了 ANYONE 组外，再次对原始模板中已被授予权限的每个其他组或用户运行此命令。</caps:sentence>
                    <caps:sentence sentenceid="68d40b9728b4c4ee251a6967c171233b" id="tgt265" class="tgtSentence"> 然后，使用 <externalLink><linkText>Set-AadrmTemplateProperty</linkText><linkUri>https://msdn.microsoft.com/en-us/library/azure/dn727076.aspx</linkUri></externalLink> cmdlet 将所有这些权限定义对象添加到模板中。</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="16859c9da62799922bc88b1c7de34fc3" id="tgt266" class="tgtSentence">使用 <externalLink><linkText>Export-AadrmTemplate</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn727078.aspx</linkUri></externalLink> cmdlet 将模板导出到 .XML 文件中，通过编辑该文件将“AllStaff”组和权限添加到现有组和权限中，然后使用 <externalLink><linkText>Import-AadrmTemplate</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn727077.aspx</linkUri></externalLink> cmdlet 将所做的更改导回 Azure RMS 中。</caps:sentence>
                  </para>
                </listItem>
              </list>
              <alert class="note">
                <para>
                  <caps:sentence sentenceid="66bce28c3c39e3aa13ce91c1bbe60528" id="tgt267" class="tgtSentence">这个相应的“AllStaff”组并非完全等同于 AD RMS 中的 ANYONE 组：“AllStaff”组包括你的 Azure 租户中的所有用户，而 ANYONE 组则包括所有经过身份验证的用户，这些用户可能不在你的组织中。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="9236e27d78a4cab57bb74db879ef4d2d" id="tgt268" class="tgtSentence">由于这两个组存在这种差异，你可能还需要向“AllStaff”组添加外部用户。</caps:sentence>
                  <caps:sentence sentenceid="7b8435a7e049840b390e4e8eb4c4d168" id="tgt269" class="tgtSentence"> 目前不支持对组使用外部电子邮件地址。</caps:sentence>
                </para>
              </alert>
              <para>
                <caps:sentence sentenceid="c252fbbfeb7650309546988a57b464e1" id="tgt270" class="tgtSentence">你从 AD RMS 导入的模板的外观和行为就像你可以在 Azure 经典门户中创建的自定义模板一样。</caps:sentence>
                <caps:sentence sentenceid="bdc1d87d3013b77c09cecc8c14c73adc" id="tgt271" class="tgtSentence"> 若要将导入的模板更改为“已发布”，以便用户可以查看它们以及从应用程序中选择它们，或者要对模板进行其他更改，请参阅<link xlink:href="1775d8d0-9a59-42c8-914f-ce285b71ac1c">Configuring Custom Templates for Azure Rights Management</link>。</caps:sentence>
              </para>
              <alert class="tip">
                <para>
                  <caps:sentence sentenceid="a6583b5544e5b6aa76107950d5dc4169" id="tgt272" class="tgtSentence">为了在迁移过程中向用户提供更一致的体验，请不要对导入的模板进行这两项更改以外的其他更改，请不要发布 Azure RMS 附带的两个默认模板，也不要在此时创建新模板。</caps:sentence>
                  <caps:sentence sentenceid="33114e4183694206ed98efd7df18d911" id="tgt273" class="tgtSentence"> 请等到迁移过程完成并已解除 AD RMS 服务器的授权。</caps:sentence>
                </para>
              </alert>
            </content>
            <sections>
              <section expanded="false" address="BKMK_ScriptForANYONE">
                <title>
                  <caps:sentence sentenceid="c9417a4f464a216ccd9380ac080132e5" id="tgt274" class="tgtSentence">示例 Windows PowerShell 脚本，用于识别包括 ANYONE 组的 AD RMS 模板</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence sentenceid="6a63ca9096ce03b685acda780220a557" id="tgt275" class="tgtSentence">本节包含示例脚本，用于帮助你确定定义有 ANYONE 组的 AD RMS 模板，如前一节所述。</caps:sentence>
                  </para>
                  <para>
                    <legacyItalic>
                      <caps:sentence sentenceid="291039e00dd33ca07dd04e988654da22" id="tgt276" class="tgtSentence">
                        <embeddedLabel>免责声明：</embeddedLabel>此示例脚本在任何 Microsoft 标准支持计划或服务下均不受支持。</caps:sentence>
                      <caps:sentence sentenceid="c62eb79717d2870aba23b3fa99ed9aa4" id="tgt277" class="tgtSentence"> 此示例脚本按原样提供，不提供任何形式的保证。</caps:sentence>
                    </legacyItalic>
                  </para>
                  <code>import-module adrmsadmin New-PSDrive -Name MyRmsAdmin -PsProvider AdRmsAdmin -Root https://localhost -Force $ListofTemplates=dir MyRmsAdmin:\RightsPolicyTemplate foreach($Template in $ListofTemplates) { $templateID=$Template.id $rights = dir MyRmsAdmin:\RightsPolicyTemplate\$Templateid\userright $templateName=$Template.DefaultDisplayName if ($rights.usergroupname -eq "anyone") { $templateName = $Template.defaultdisplayname write-host "Template " -NoNewline write-host -NoNewline $templateName -ForegroundColor Red write-host " contains rights for " -NoNewline write-host ANYONE  -ForegroundColor Red } } Remove-PSDrive MyRmsAdmin -force
</code>
                </content>
              </section>
            </sections>
          </section>
          <section address="BKMK_Step5Migration">
            <title>
              <caps:sentence sentenceid="b07068230cd9957fd61de6376c46207a" id="tgt278" class="tgtSentence">步骤 5.</caps:sentence>
              <caps:sentence sentenceid="4211c7ea703db35fd23d534f8f4b4547" id="tgt279" class="tgtSentence"> 将客户端重新配置为使用 Azure RMS</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="cfd608dfbc0540950dcbd6b3dcd30e82" id="tgt280" class="tgtSentence">对于 Windows 客户端：</caps:sentence>
              </para>
              <list class="ordered">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="e265492707dd0595fd1f399bb8a2690e" id="tgt281" class="tgtSentence">
                      <externalLink>
                        <linkText>下载迁移脚本</linkText>
                        <linkUri>http://go.microsoft.com/fwlink/?LinkId=524619</linkUri>
                      </externalLink>： </caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="c540add67544ede964e67cf3d7a93dd2" id="tgt282" class="tgtSentence">CleanUpRMS_RUN_Elevated.cmd</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="4ba5c672db6295a1c089c027a3803da3" id="tgt283" class="tgtSentence">Redirect_OnPrem.cmd</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <para>
                    <caps:sentence sentenceid="5d5c6c7d62e65db194f21a564bfa2e19" id="tgt284" class="tgtSentence">这些脚本将重置 Windows 计算机上的配置，以使其将使用 Azure RMS 服务而不是 AD RMS。</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="d4a9a5cb446ccbb5c67aedfd03a926a4" id="tgt285" class="tgtSentence">按照重定向脚本 (Redirect_OnPrem.cmd) 中的说明修改脚本，使其指向新的 Azure RMS 租户。</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="5323f31a189c997652d5a3a0ed5fb256" id="tgt286" class="tgtSentence">在 Windows 计算机上，使用提升的特权，在用户的上下文中运行这些脚本。</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence sentenceid="6e449c2c59a1e1e8912452b875d45e5f" id="tgt287" class="tgtSentence">对于移动设备客户端和 Mac 计算机：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="37794107207a9e8a9ac8109c11aeee74" id="tgt288" class="tgtSentence">删除在部署 <externalLink><linkText>AD RMS 移动设备扩展</linkText><linkUri>http://technet.microsoft.com/library/dn673574.aspx</linkUri></externalLink>时创建的 DNS SRV 记录。</caps:sentence>
                  </para>
                </listItem>
              </list>
            </content>
            <sections>
              <section expanded="false">
                <title>
                  <caps:sentence sentenceid="73990d4d365d797e9b6da85d325975a9" id="tgt289" class="tgtSentence">由迁移脚本进行的更改</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence sentenceid="5cae975640e774b0ec1a50e5cbbcdecc" id="tgt290" class="tgtSentence">本节介绍迁移脚本进行的更改。</caps:sentence>
                    <caps:sentence sentenceid="7e0092d6290c6a143e8205e7d783bf90" id="tgt291" class="tgtSentence"> 你只能将此信息出于参考目的，或用于故障排除，或者用于你想要自己进行这些更改的场合。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="a5ec859cfc6dca2f0377fe527ae4ccde" id="tgt292" class="tgtSentence">CleanUpRMS_RUN_Elevated.cmd：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="19fc8030eb87b6a393d10d5c8767e2d6" id="tgt293" class="tgtSentence">删除 %userprofile%\AppData\Local\Microsoft\DRM 和 %userprofile%\AppData\Local\Microsoft\MSIPC 文件夹的内容，包括任何子文件夹以及具有长文件名的任何文件。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="b722a91a8467d1fb862ece0d3ba416e3" id="tgt294" class="tgtSentence">删除以下注册表项的内容：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="7a43cfee3d40f2d2b9074c8fcb1d9923" id="tgt295" class="tgtSentence">HKEY_LOCAL_MACHINE\Software\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="eafa82a559f1413fe776f53dfc3b4137" id="tgt296" class="tgtSentence">HKEY_CURRENT_USER\Software\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="c7f38463861e65ee71515aebf39769fb" id="tgt297" class="tgtSentence">HKEY_LOCAL_MACHINE\Software\WoW6432Node\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="a43c9e4d926e4a1d36f630272b378c35" id="tgt298" class="tgtSentence">HKEY_CURRENT_USER\Software\WoW6432Node\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="3b029246c53d388da4cdced405deea46" id="tgt299" class="tgtSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="66712671dae4821cb4c97211bf62133a" id="tgt300" class="tgtSentence">HKEY_LOCAL_MACHINE\SOFTWARE\WoW6432Node\Microsoft\MSIPC\ServiceLocation</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="9e38087a294154bad98452ad73430016" id="tgt301" class="tgtSentence">HKEY_LOCAL_MACHINE\Software\Microsoft\MSDRM\ServiceLocation</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="7285873bc66bd51ab54618f5108e69e7" id="tgt302" class="tgtSentence">删除以下注册表值：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="41ab5dbb0aa718831126a06e17a48842" id="tgt303" class="tgtSentence">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\DRM\DefaultServerURL</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="1eaa9bffc767d3f5c991d4adda593b80" id="tgt304" class="tgtSentence">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\DRM\DefaultServer</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </listItem>
                  </list>
                  <para>
                    <caps:sentence sentenceid="b60e278d76351e700cac68621743b526" id="tgt305" class="tgtSentence">Redirect_OnPrem.cmd：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="59a3ee9cceaa5043e6203a402300b83b" id="tgt306" class="tgtSentence">为以下每个位置下作为参数提供的每个 URL 创建以下注册表值：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="22819938d1af49b9a662ddef60fc5885" id="tgt307" class="tgtSentence">HKEY_CURRENT_USER\Software\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM\LicenseServerRedirection</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="c8985d1d050d5973ebab9c4201209411" id="tgt308" class="tgtSentence">HKEY_CURRENT_USER\Software\WoW6432Node\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM\LicenseServerRedirection</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="24879e3cb182f3c99abe21c4ee9eca9a" id="tgt309" class="tgtSentence">HKEY_LOCAL_MACHINE\Software\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM\LicenseServerRedirection</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="406df330896cd3c0794920f46cd938fd" id="tgt310" class="tgtSentence">HKEY_LOCAL_MACHINE\Software\WoW6432Node\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM\LicenseServerRedirection</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="02a964ee4a12efdb687ad0d436119760" id="tgt311" class="tgtSentence">HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC\LicensingRedirection</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence sentenceid="3bbdc6d5a2543bdf56ad63364f55a174" id="tgt312" class="tgtSentence">每一项均具有 REG_SZ 值 <ui>https://OldRMSserverURL/_wmcs/licensing</ui>，其数据采用以下格式：<ui>https://&lt;YourTenantURL&gt;/_wmcs/licensing</ui>。</caps:sentence>
                      </para>
                      <alert class="note">
                        <para>
                          <caps:sentence sentenceid="80305a496e1bd4363b3917c9b5acd933" id="tgt313" class="tgtSentence">
                            <placeholder>&lt;YourTenantURL&gt;</placeholder> 采用以下格式：<ui>{GUID}.rms.[Region].aadrm.com</ui>。</caps:sentence>
                        </para>
                        <para>
                          <caps:sentence sentenceid="b922f2b29ac449fbea90ff49fbc782c0" id="tgt314" class="tgtSentence">例如：5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com</caps:sentence>
                        </para>
                        <para>
                          <caps:sentence sentenceid="1c2c13a341ef0efefe79e91fb5532568" id="tgt315" class="tgtSentence">在对 Azure RMS 运行 <externalLink><linkText>Get-AadrmConfiguration</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629410.aspx</linkUri></externalLink> cmdlet 时，可以通过标识 <ui>RightsManagementServiceId</ui> 值找到此值。</caps:sentence>
                        </para>
                      </alert>
                    </listItem>
                  </list>
                </content>
              </section>
            </sections>
          </section>
          <section address="BKMK_Step6Migration">
            <title>
              <caps:sentence sentenceid="f908b923db8fd9da757a6e8223a5a8fc" id="tgt316" class="tgtSentence">步骤 6.</caps:sentence>
              <caps:sentence sentenceid="36a0d72df947da56074f640aa8a226bd" id="tgt317" class="tgtSentence"> 为 Exchange Online 配置 IRM 集成</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="7cdefa985f73cfe79da57362b0e94de9" id="tgt318" class="tgtSentence">如果以前已将 TDP 从 AD RMS 导入 Exchange Online，则必须删除此 TDP，以避免在迁移到 Azure RMS 后发生模板和策略冲突。</caps:sentence>
                <caps:sentence sentenceid="8c1b10166db1b06c63557d94794bc5bc" id="tgt319" class="tgtSentence"> 为此，请在 Exchange Online 中使用 <externalLink><linkText>Remove-RMSTrustedPublishingDomain</linkText><linkUri>https://technet.microsoft.com/en-us/library/jj200720(v=exchg.150).aspx</linkUri></externalLink> cmdlet。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="a729f647b41ab0ae3990e2d2787356c6" id="tgt320" class="tgtSentence">如果你选择了 <embeddedLabel>Microsoft 管理</embeddedLabel>的 Azure RMS 租户密钥拓扑：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="abda7877548e2693387fce7b54bf4008" id="tgt321" class="tgtSentence">参阅<link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36">Configuring Applications for Azure Rights Management</link>主题中的<link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36#BKMK_ExchangeOnline">Exchange Online: IRM Configuration</link>部分。</caps:sentence>
                    <caps:sentence sentenceid="f0bf7dea8f5e087cb78dfa16ecb7991d" id="tgt322" class="tgtSentence"> 此部分介绍了一些典型的命令，运行这些命令可以连接到 Exchange Online 服务、从 Azure RMS 导入租户密钥，以及为 Exchange Online 启用 IRM 功能。</caps:sentence>
                    <caps:sentence sentenceid="00f4cc711369136298c1cb7344b12769" id="tgt323" class="tgtSentence"> 完成这些步骤后，你将获得 Exchange Online 的完整 RMS 功能。</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence sentenceid="a729f647b41ab0ae3990e2d2787356c6" id="tgt324" class="tgtSentence">如果你选择了<embeddedLabel>客户管理 (BYOK)</embeddedLabel> 的 Azure RMS 租户密钥拓扑：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="146f9fe0969ee405166209fc122b7c07" id="tgt325" class="tgtSentence"> 削减 Exchange Online 的 RMS 功能，如<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and Implementing Your Azure Rights Management Tenant Key</link>主题中的 <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_Pricing">BYOK pricing and restrictions</link>所述。</caps:sentence>
                  </para>
                </listItem>
              </list>
            </content>
          </section>
          <section address="BKMK_Step7Migration">
            <title>
              <caps:sentence sentenceid="82b70be280a638b7b2939b8f72fff4d1" id="tgt326" class="tgtSentence">步骤 7.</caps:sentence>
              <caps:sentence sentenceid="c215284fc4d7fd29381f8f3286d3f9e1" id="tgt327" class="tgtSentence"> 部署 RMS 连接器</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="4a01051fd06342e667c04e3200d092b9" id="tgt328" class="tgtSentence">如果你已将 Exchange Server 或 SharePoint Server 的信息权限管理 (IRM) 功能与 AD RMS 一起使用，则必须先在这些服务器上禁用 IRM 并删除 AD RMS 配置。</caps:sentence>
                <caps:sentence sentenceid="e66d9816131b27122114e5328c323428" id="tgt329" class="tgtSentence"> 然后，部署权限管理 (RMS) 连接器，该连接器将充当本地服务器和 Azure RMS 之间的通信接口（中继）。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="206af5939efcb63715156bee2aa2b580" id="tgt330" class="tgtSentence">此步骤的最后一步，如果你已将多个用于保护电子邮件的 TPD 导入到 Azure RMS ，则必须手动编辑 Exchange Server 计算机上的注册表，将所有 TPD URL 重定向到 RMS 连接器。</caps:sentence>
              </para>
              <alert class="note">
                <para>
                  <caps:sentence sentenceid="3e9efa01b5a0b590b4b23f45c0807b3f" id="tgt331" class="tgtSentence">在开始之前，请在 <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>主题的<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedApplications">Applications that support Azure RMS</link>部分的“支持 Azure RMS 的本地服务器”中，核实 RMS 连接器支持的本地服务器的受支持版本。</caps:sentence>
                </para>
              </alert>
              <procedure>
                <title>
                  <caps:sentence sentenceid="4cb1f0643b31ab6707fd50d284154dff" id="tgt332" class="tgtSentence">在 Exchange 服务器上禁用 IRM 并删除 AD RMS 配置</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="b945916b620db993b5b16a140be8714d" id="tgt333" class="tgtSentence">在每个 Exchange 服务器上，找到以下文件夹，并删除该文件夹中的所有条目：\ProgramData\Microsoft\DRM\Server\S-1-5-18</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="20c089aa8f08762007eb2b71e0adcfa6" id="tgt334" class="tgtSentence">在任一 Exchange 服务器上，使用 Exchange <externalLink><linkText>Set_IRMConfiguration</linkText><linkUri>http://technet.microsoft.com/library/dd979792.aspx</linkUri></externalLink> cmdlet，先对向内部收件人发送的消息禁用 IRM 功能： </caps:sentence>
                      </para>
                      <code>Set-IRMConfiguration -InternalLicensingEnabled $false</code>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="6ae07daf41a6a2c4dcbec8711a5a9c82" id="tgt335" class="tgtSentence">然后使用同一 cmdlet 对向外部收件人发送的消息禁用 IRM 功能：</caps:sentence>
                      </para>
                      <code>Set-IRMConfiguration -ExternalLicensingEnabled $false</code>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="fd6ff6360c0e7a850f960a26269700b7" id="tgt336" class="tgtSentence">接下来，使用同一 cmdlet 在 Microsoft Office Outlook Web App 和 Microsoft Exchange ActiveSync 中禁用 IRM：</caps:sentence>
                      </para>
                      <code>Set-IRMConfiguration -ClientAccessServerEnabled $false</code>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="98cf0c7145d90ac7991609db3ce37057" id="tgt337" class="tgtSentence">最后，使用同一 cmdlet 清除所有缓存的证书：</caps:sentence>
                      </para>
                      <code>Set-IRMConfiguration -RefreshServerCertificates</code>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="8d3e2a4c29ff51e7a7767129532d2cda" id="tgt338" class="tgtSentence">现在，在每个 Exchange 服务器上重置 IIS，例如，通过以管理员身份运行命令提示符并键入 <userInput>iisreset</userInput>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
              <procedure>
                <title>
                  <caps:sentence sentenceid="275b5b52b6f28df41b12437e7216b8ee" id="tgt339" class="tgtSentence">在 SharePoint 服务器上禁用 IRM 并删除 AD RMS 配置</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="80d713860e5cbaf688244278ebaeaf25" id="tgt340" class="tgtSentence">请确保没有文档从 RMS 保护的库中签出。</caps:sentence>
                        <caps:sentence sentenceid="ddfe5764cd983e85e68912f4bed899bb" id="tgt341" class="tgtSentence"> 如果有，这些文档将在此过程结束时变为不可访问。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="6cdcc6ef76d8d81a6874cb91d62efb5c" id="tgt342" class="tgtSentence">在 SharePoint 管理中心网站的“快速启动”部分中，单击“安全性”<ui></ui><ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="87c942eae0180b2f79691fe9cf6c988f" id="tgt343" class="tgtSentence">在“安全性”页的“信息策略”部分中，单击“配置信息权限管理”<ui></ui><ui></ui><ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="87c942eae0180b2f79691fe9cf6c988f" id="tgt344" class="tgtSentence">在“信息权限管理”页的“信息权限管理”部分中，选择“不在此服务器上使用 IRM”，然后单击“确定”<ui></ui><ui></ui><ui></ui><ui></ui>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="49c6a2f12f1769ccb4dfbc7840e3425e" id="tgt345" class="tgtSentence">在每台 SharePoint Server 计算机上，删除文件夹“\ProgramData\Microsoft\MSIPC\Server\<placeholder>&lt;运行 SharePoint Server 的帐户的 SID&gt;</placeholder>”的内容。</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
              <procedure>
                <title>
                  <caps:sentence sentenceid="5f8cb0a4420a79f1c6c0e9c89404dd36" id="tgt346" class="tgtSentence">安装并配置 RMS 连接器</caps:sentence>
                </title>
                <steps class="bullet">
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="235ed0a4f8aa910730d1f6941a38502b" id="tgt347" class="tgtSentence">使用<link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066">Deploying the Azure Rights Management Connector</link>主题中的说明。</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
              <procedure>
                <title>
                  <caps:sentence sentenceid="45b9132d6a804689d624987ff64d2707" id="tgt348" class="tgtSentence">对于仅 Exchange 和多个 TPD：编辑注册表</caps:sentence>
                </title>
                <steps class="bullet">
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="d3aa9434a1a3f112f1065166ec769d1e" id="tgt349" class="tgtSentence">在每个 Exchange 服务器上，手动为每个已导入的附加 TPD 添加以下注册表项，将 TPD URL 重定向到 RMS 连接器。</caps:sentence>
                        <caps:sentence sentenceid="37c3a328b94d5b92973ffd92a6bfe5f5" id="tgt350" class="tgtSentence"> 这些注册表项特定于迁移，并且不是通过 Microsoft RMS 连接器的服务器配置工具添加的。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="cbc9cb4a5151b6bbd82dd788a4b03e96" id="tgt351" class="tgtSentence">进行这些注册表编辑时，请使用以下说明：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="05d18373e30d5a4c6a58e6f3b2e3e7ab" id="tgt352" class="tgtSentence">将 <placeholder>ConnectorFQDN</placeholder> 替换为你在 DNS 中为连接器定义的名称。</caps:sentence>
                            <caps:sentence sentenceid="4eee3758f1bf4073d94deae936dd0a13" id="tgt353" class="tgtSentence"> 例如 <ui>rmsconnector.contoso.com</ui>。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="525aa5b6a77435179938bcb6a80c3748" id="tgt354" class="tgtSentence">对连接器 URL 使用 HTTP 或 HTTPS 前缀，具体取决于你已将连接器配置为使用 HTTP 还是使用 HTTPS 与本地服务器通信。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para> </para>
                      <para>
                        <embeddedLabel>
                          <caps:sentence sentenceid="88138f7ee93a43414511f38caed9e21f" id="tgt355" class="tgtSentence">对于 Exchange 2013：</caps:sentence>
                        </embeddedLabel>
                      </para>
                      <table>
                        <thead>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="b75ba2542571d3ceaab9c5d83c92075c" id="tgt356" class="tgtSentence">注册表路径</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="599dcce2998a6b40b1e38e8c6006cb0a" id="tgt357" class="tgtSentence">类型</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="2063c1608d6e0baf80249c42e2be5804" id="tgt358" class="tgtSentence">值</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="8d777f385d3dfec8815d20f7496026dc" id="tgt359" class="tgtSentence">数据</caps:sentence>
                              </para>
                            </TD>
                          </tr>
                        </thead>
                        <tbody>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="51bd899ad0b193c2861a83d1d8f8c447" id="tgt360" class="tgtSentence">HKLM\SOFTWARE\Microsoft\ExchangeServer\v15\IRM\LicenseServerRedirection</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt361" class="tgtSentence">Reg_SZ</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="c3d957a855225df0e45cb87b34facd88" id="tgt362" class="tgtSentence">https://&lt;AD RMS Intranet 授权 URL&gt;/_wmcs/licensing</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="5e9f115816f9a71685775cd8d7bf469f" id="tgt363" class="tgtSentence">以下前缀之一，具体取决于 Exchange 服务器与 RMS 连接器之间的连接是使用 HTTP 还是 HTTPS：</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="199c6265e21e51538d2129bb847d8773" id="tgt364" class="tgtSentence">http://&lt;连接器 FQDN&gt;/_wmcs/licensing</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="fb67fe12165a832ef54d0fde1c564982" id="tgt365" class="tgtSentence">https://&lt;连接器名称&gt;/_wmcs/licensing</caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                            </TD>
                          </tr>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="47a5fe058dba39acbc92107d29512f94" id="tgt366" class="tgtSentence">HKLM\SOFTWARE\Microsoft\ExchangeServer\v15\IRM\LicenseServerRedirection </caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt367" class="tgtSentence">Reg_SZ</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="c59e0643dded1f67b95dc4bd20e91159" id="tgt368" class="tgtSentence">https://&lt;AD RMS Extranet 授权 URL&gt;/_wmcs/licensing</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="5e9f115816f9a71685775cd8d7bf469f" id="tgt369" class="tgtSentence">以下前缀之一，具体取决于 Exchange 服务器与 RMS 连接器之间的连接是使用 HTTP 还是 HTTPS：</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="199c6265e21e51538d2129bb847d8773" id="tgt370" class="tgtSentence">http://&lt;连接器 FQDN&gt;/_wmcs/licensing</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="65298cd1387373567c3ce80fc50563a7" id="tgt371" class="tgtSentence">https://&lt;连接器 FQDN&gt;/_wmcs/licensing</caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                            </TD>
                          </tr>
                        </tbody>
                      </table>
                      <para>
                        <embeddedLabel>
                          <caps:sentence sentenceid="72a43bf3a41b9e52faaec8adcc836ab2" id="tgt372" class="tgtSentence">对于 Exchange Server 2010：</caps:sentence>
                        </embeddedLabel>
                      </para>
                      <table>
                        <thead>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="b75ba2542571d3ceaab9c5d83c92075c" id="tgt373" class="tgtSentence">注册表路径</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="599dcce2998a6b40b1e38e8c6006cb0a" id="tgt374" class="tgtSentence">类型</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="2063c1608d6e0baf80249c42e2be5804" id="tgt375" class="tgtSentence">值</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="8d777f385d3dfec8815d20f7496026dc" id="tgt376" class="tgtSentence">数据</caps:sentence>
                              </para>
                            </TD>
                          </tr>
                        </thead>
                        <tbody>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="79ca1b8c2bde5ffb54f84618991ea02c" id="tgt377" class="tgtSentence">HKLM\SOFTWARE\Microsoft\ExchangeServer\v14\IRM\LicenseServerRedirection</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt378" class="tgtSentence">Reg_SZ</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="c3d957a855225df0e45cb87b34facd88" id="tgt379" class="tgtSentence">https://&lt;AD RMS Intranet 授权 URL&gt;/_wmcs/licensing</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="5e9f115816f9a71685775cd8d7bf469f" id="tgt380" class="tgtSentence">以下前缀之一，具体取决于 Exchange 服务器与 RMS 连接器之间的连接是使用 HTTP 还是 HTTPS：</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="6378b91b7748d08e6db05d742d0d9341" id="tgt381" class="tgtSentence">http://&lt;连接器名称&gt;/_wmcs/licensing</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="fb67fe12165a832ef54d0fde1c564982" id="tgt382" class="tgtSentence">https://&lt;连接器名称&gt;/_wmcs/licensing</caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                            </TD>
                          </tr>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="f74b707c98c3d36302cf00f38d047678" id="tgt383" class="tgtSentence">HKLM\SOFTWARE\Microsoft\ExchangeServer\v14\IRM\LicenseServerRedirection </caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt384" class="tgtSentence">Reg_SZ</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="c59e0643dded1f67b95dc4bd20e91159" id="tgt385" class="tgtSentence">https://&lt;AD RMS Extranet 授权 URL&gt;/_wmcs/licensing</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="5e9f115816f9a71685775cd8d7bf469f" id="tgt386" class="tgtSentence">以下前缀之一，具体取决于 Exchange 服务器与 RMS 连接器之间的连接是使用 HTTP 还是 HTTPS：</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="6378b91b7748d08e6db05d742d0d9341" id="tgt387" class="tgtSentence">http://&lt;连接器名称&gt;/_wmcs/licensing</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="fb67fe12165a832ef54d0fde1c564982" id="tgt388" class="tgtSentence">https://&lt;连接器名称&gt;/_wmcs/licensing</caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                            </TD>
                          </tr>
                        </tbody>
                      </table>
                    </content>
                  </step>
                </steps>
              </procedure>
              <para>
                <caps:sentence sentenceid="0c0abd7b51e76b51a287edcfa68680ef" id="tgt389" class="tgtSentence">完成这些过程之后，请务必阅读<link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066">Deploying the Azure Rights Management Connector</link>主题中的“后续步骤”<embeddedLabel></embeddedLabel>部分。</caps:sentence>
              </para>
            </content>
          </section>
          <section address="BKMK_Step8Migration">
            <title>
              <caps:sentence sentenceid="d8785da18caa06d14c0e8952f7dcd32b" id="tgt390" class="tgtSentence">步骤 8.</caps:sentence>
              <caps:sentence sentenceid="a46740565efff323a443abd3c32c5ec1" id="tgt391" class="tgtSentence"> 解除 AD RMS 的授权</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="f24462cc508f5bf969819d53db8282eb" id="tgt392" class="tgtSentence">可选：从 Active Directory 中删除服务连接点 (SCP) 以防止计算机发现你的本地权限管理基础结构。</caps:sentence>
                <caps:sentence sentenceid="fb1479a40c4c4ecf3411a4711e9fdae8" id="tgt393" class="tgtSentence"> 由于你在注册表中配置的重定向（例如，通过运行迁移脚本），此步骤是可选的。</caps:sentence>
                <caps:sentence sentenceid="4edd9136b92d92ec99f88fd06bca3788" id="tgt394" class="tgtSentence"> 若要删除服务连接点，请使用 <externalLink><linkText>Rights Management Services 管理工具包</linkText><linkUri>http://www.microsoft.com/download/details.aspx?id=1479</linkUri></externalLink>中的 AD SCP 注册工具。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="6358aa903cadff21f0dd08ad1132af44" id="tgt395" class="tgtSentence">监视 AD RMS 服务器的活动，例如，通过检查<externalLink><linkText>系统运行状况报告中的请求</linkText><linkUri>https://technet.microsoft.com/library/ee221012(v=ws.10).aspx</linkUri></externalLink>、<externalLink><linkText>ServiceRequest 表</linkText><linkUri>http://technet.microsoft.com/library/dd772686(v=ws.10).aspx</linkUri></externalLink>，或者<externalLink><linkText>审核用户对受保护内容的访问权限</linkText><linkUri>http://social.technet.microsoft.com/wiki/contents/articles/3440.ad-rms-frequently-asked-questions-faq.aspx</linkUri></externalLink>。</caps:sentence>
                <caps:sentence sentenceid="dc3fe8e83a556aee7fff9c3dc5de0824" id="tgt396" class="tgtSentence"> 当你确认 RMS 客户端将不再与这些服务器进行通信，并且客户端成功使用 Azure RMS 时，你可以从这些服务器中删除 AD RMS 服务器角色。</caps:sentence>
                <caps:sentence sentenceid="b73f62cbcca2f9dd62969242fc593aa0" id="tgt397" class="tgtSentence"> 当你调查为什么客户端未使用 Azure RMS 时，如果你使用的是专用服务器，你可能希望采取警告步骤，即先关闭服务器一段时间，以确保没有报告可能需要重新启动这些服务器以确保服务连续性的问题。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="b445dc536cdcaac5e52afab6f17ccc04" id="tgt398" class="tgtSentence">解除 AD RMS 服务器的授权后，你可能想要利用此机会来查看你在 Azure 经典门户中的模板并将其合并以使用户有较少的选项，或重新配置它们，或者甚至添加新模板。</caps:sentence>
                <caps:sentence sentenceid="1c24f8517834ee2908d00b738c4a1e08" id="tgt399" class="tgtSentence"> 这还将是发布默认模板的好时机。</caps:sentence>
                <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt400" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="1775d8d0-9a59-42c8-914f-ce285b71ac1c">Configuring Custom Templates for Azure Rights Management</link>。</caps:sentence>
              </para>
            </content>
          </section>
          <section address="BKMK_Step9Migration">
            <title>
              <caps:sentence sentenceid="9740009227fb6c485ee9234e2bb22aad" id="tgt401" class="tgtSentence">步骤 9.</caps:sentence>
              <caps:sentence sentenceid="712c1499aa587e340e896f4ad5f549f6" id="tgt402" class="tgtSentence"> 重新键入你的 Azure RMS 租户密钥</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="3590f7e71dbdd8af3a75878020ec66a2" id="tgt403" class="tgtSentence">迁移完成时，如果 AD RMS 部署使用的是 RMS 加密模式 1，则此步骤是必需的，因为重新键入将创建使用 RMS 加密模式 2 的新租户密钥。</caps:sentence>
                <caps:sentence sentenceid="46fb3a8918cfddefa14d51b279e44b8c" id="tgt404" class="tgtSentence"> 将 Azure RMS 与加密模式 1 配合使用仅在迁移过程中受支持。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="4d6b96ac0fd56ec3524bd8e8eb8209c2" id="tgt405" class="tgtSentence">迁移完成时，此步骤是可选的但建议使用（即使你已以 RMS 加密模式 2 运行），因为它可帮助保护你的 Azure RMS 租户密钥，使 AD RMS 密钥免遭潜在的安全漏洞的威胁。</caps:sentence>
                <caps:sentence sentenceid="cf1ef74a2b503a8f29a4f96b475f3620" id="tgt406" class="tgtSentence"> 当你重新键入 Azure RMS 租户密钥（也称为“滚动密钥”）时，将创建新的密钥，并将原始密钥存档。</caps:sentence>
                <caps:sentence sentenceid="9c76dda946a62e989f0d2f106da2d0b8" id="tgt407" class="tgtSentence"> 但是，由于从一个密钥移到另一个密钥并不会立即发生，而是经过几周才会发生，请不要等到你怀疑原始密钥受到破坏再进行，而应在迁移完成时，立即重新键入你的 RMS 租户密钥。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="760ae5f1e9e540510c59d7672295d5a1" id="tgt408" class="tgtSentence">若要重新键入你的 Azure RMS 租户密钥，请执行以下操作：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="d75850d3af942b4c253ea62e47f8bd5d" id="tgt409" class="tgtSentence">如果你的 RMS 租户密钥由 Microsoft 管理：致电 Microsoft 客户支持服务 (CSS)，并证明你是 RMS 租户管理员。</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="556593379eb58e05fab79933f104f64d" id="tgt410" class="tgtSentence">如果你的 RMS 租户密钥由你管理 (BYOK)：重复执行 BYOK 过程以通过 Internet 或亲自生成并创建新的密钥。</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence sentenceid="3bd4825c070d7882d0e732aaebeb0c48" id="tgt411" class="tgtSentence">有关管理 RMS 租户密钥的详细信息，请参阅<link xlink:href="1284d0ee-0a72-45ba-a64c-3dcb25846c3d">Operations for Your Azure Rights Management Tenant Key</link>。</caps:sentence>
              </para>
            </content>
          </section>
        </sections>
      </section>
      <relatedTopics>
        <link xlink:href="206a0bfe-0912-4e0e-aa15-484b000b264c">Configuring Azure Rights Management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSTarget>
  <caps:SxSSource locale="en-US">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence id="src1" class="srcSentence">Use the following set of instructions to  migrate your Active Directory Rights Management Services (AD RMS) deployment to Azure Rights Management (Azure RMS).</caps:sentence>
          <caps:sentence id="src2" class="srcSentence"> After the migration, users will still have access to documents and email messages that your organization protected by using AD RMS, and newly protected content will use Azure RMS.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src3" class="srcSentence">Not sure whether this AD RMS migration is right for your organization?</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <caps:sentence id="src4" class="srcSentence">For an introduction to Azure RMS,  the business problems that it can solve, what it looks like to administrators and users, and how it works, see <link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link></caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence id="src5" class="srcSentence">For a comparison of Azure RMS with AD RMS, see <link xlink:href="8123bd62-1814-4d79-b306-e20c1a00e264">Comparing Azure Rights Management and AD RMS</link>.</caps:sentence>
            </para>
          </listItem>
        </list>
      </introduction>
      <section>
        <title>
          <caps:sentence id="src6" class="srcSentence">Prerequisites for migrating AD RMS to Azure RMS</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src7" class="srcSentence">Before you start the migration to Azure RMS, make sure that the following prerequisites are in place and that you understand any limitations.</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src8" class="srcSentence">Requirement</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src9" class="srcSentence">More information</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src10" class="srcSentence">A supported RMS deployment</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src11" class="srcSentence">All releases of AD RMS from Windows Server 2008 through Windows Server 2012 R2 support a migration to Azure RMS:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src12" class="srcSentence">Windows Server 2008 (x86 or x64)</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src13" class="srcSentence">Windows Server 2008 R2 (x64)</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src14" class="srcSentence">Windows Server 2012 (x64)</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src15" class="srcSentence">Windows Server 2012 R2 (x64)</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <alert class="note">
                    <para>
                      <caps:sentence id="src16" class="srcSentence">If you are running Windows RMS on Windows Server 2003, this version of the operating system will be out of support during 2015.</caps:sentence>
                      <caps:sentence id="src17" class="srcSentence"> You can migrate this version of RMS to Azure RMS, but this process is supported only if the operating system is still supported.</caps:sentence>
                      <caps:sentence id="src18" class="srcSentence"> As a workaround, you could import your trusted publishing domain (TPD) to a version of AD RMS that is supported, and then re-import the TPD without the RMS 1.0 compatibility option.</caps:sentence>
                      <caps:sentence id="src19" class="srcSentence"> For more information about TPDs, see <externalLink><linkText>Trusted Publishing Domain</linkText><linkUri>http://technet.microsoft.com/library/dd996639(v=ws.10).aspx</linkUri></externalLink></caps:sentence>
                    </para>
                  </alert>
                  <para>
                    <caps:sentence id="src20" class="srcSentence">All valid AD RMS topologies are supported:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src21" class="srcSentence">Single forest, single RMS cluster</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src22" class="srcSentence">Single forest, multiple licensing-only RMS clusters</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src23" class="srcSentence">Multiple forests, multiple RMS clusters</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <alert class="note">
                    <para>
                      <caps:sentence id="src24" class="srcSentence">By default, multiple RMS clusters migrate to a single Azure RMS tenant.</caps:sentence>
                      <caps:sentence id="src25" class="srcSentence"> If you want different RMS tenants, you must treat them as different migrations.</caps:sentence>
                      <caps:sentence id="src26" class="srcSentence"> A key from one RMS cluster cannot be imported to more than one Azure RMS tenant.</caps:sentence>
                    </para>
                  </alert>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src27" class="srcSentence">All requirements to run Azure RMS, including an Azure RMS tenant (not activated)</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src28" class="srcSentence">See <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src29" class="srcSentence">Although you must have an Azure RMS tenant before you can migrate from AD RMS, we recommend that you do not activate the Rights Management service before the migration.</caps:sentence>
                    <caps:sentence id="src30" class="srcSentence"> The migration process includes this step after you have exported keys and templates from AD RMS and imported them to Azure RMS.</caps:sentence>
                    <caps:sentence id="src31" class="srcSentence"> However, if Azure RMS is already activated, you can still migrate from AD RMS.</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src32" class="srcSentence">Preparation for Azure RMS:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src33" class="srcSentence">Directory synchronization between your on-premises directory and Azure Active Directory</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src34" class="srcSentence">Mail-enabled groups in Azure Active Directory</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src35" class="srcSentence">See <link xlink:href="afbca2d6-32a7-4bda-8aaf-9f93f5da5abc">Preparing for Azure Rights Management</link>.</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src36" class="srcSentence">If you have used the Information Rights Management (IRM) functionality of Exchange Server (for example, transport rules and Outlook Web Access) or SharePoint Server with AD RMS:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src37" class="srcSentence">Plan for a short period of time when IRM will not be available on these servers</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src38" class="srcSentence">You can continue to use IRM on these servers with Azure RMS after the migration.</caps:sentence>
                    <caps:sentence id="src39" class="srcSentence"> However, one of the migration steps is to temporarily disable the IRM service, install and configure a connector, reconfigure the servers, and then re-enable IRM.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src40" class="srcSentence">This is the only interruption to service during the migration process.</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
          <para>
            <caps:sentence id="src41" class="srcSentence">Limitations:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src42" class="srcSentence">Although the migration process supports migrating your server licensing certificate (SLC) key to a hardware security module (HSM) for Azure RMS, Exchange Online does not currently support this configuration. If you want full IRM functionality with Exchange Online after you migrate to Azure RMS, your Azure RMS tenant key must be <externalLink><linkText>managed by Microsoft</linkText><linkUri>http://technet.microsoft.com/library/dn440580.aspx</linkUri></externalLink>. Alternatively, you can run IRM with reduced functionality in Exchange Online  when your Azure RMS tenant is managed by you (BYOK). For more information about using Exchange Online with Azure RMS, see <link xlink:href="#BKMK_Step6Migration">Step 6. Configure IRM integration for Exchange Online</link> in these instructions.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src43" class="srcSentence">If you have software and clients that are not supported with Azure RMS, they will not be able to protect or consume content that is protected by Azure RMS.</caps:sentence>
                <caps:sentence id="src44" class="srcSentence"> Be sure to check the supported applications and clients section in the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link> topic.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src45" class="srcSentence">If you import your on-premises key to Azure RMS as archived (you do not set the TPD to be the active during the import process) and you migrate users in batches for a phased migration, content that is newly protected by the migrated users will not be accessible to users who remain on AD RMS.</caps:sentence>
                <caps:sentence id="src46" class="srcSentence"> In this scenario, whenever  possible, keep the migration time short and migrate users in logical batches such that if they collaborate with one another, they are migrated together.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src47" class="srcSentence">This limitation does not apply when you set the TPD to active during the import process, because all users will protect content by using the same key.</caps:sentence>
                <caps:sentence id="src48" class="srcSentence"> We recommend this configuration because it lets you migrate all users independently and at your own pace.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src49" class="srcSentence">If you collaborate with external partners (for example, by using trusted user domains or federation), they must also migrate to Azure RMS either at the same time as your migration, or as soon as possible afterwards.</caps:sentence>
                <caps:sentence id="src50" class="srcSentence"> To continue to access content that your organization previously protected by using AD RMS, they must make client configuration changes that are similar to those that you make, and included in this document.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src51" class="srcSentence">Because of the possible configuration variations that your partners might have, exact instructions for this reconfiguration are out of scope for this document.</caps:sentence>
                <caps:sentence id="src52" class="srcSentence"> For help, contact Microsoft Customer Support Services (CSS).</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence id="src53" class="srcSentence">Steps for migrating AD RMS to Azure RMS</caps:sentence>
        </title>
        <content>
          <para></para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src54" class="srcSentence">Migration step</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src55" class="srcSentence">More information</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>
                      <caps:sentence id="src56" class="srcSentence">1. Download the Azure RMS Management Administration Tools</caps:sentence>
                    </embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src57" class="srcSentence">For instructions, see <link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172#BKMK_Step1Migration">Step 1: Download the Azure Rights Management Administration Tool</link>.</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>
                      <caps:sentence id="src58" class="srcSentence">2. Export configuration data from AD RMS and import it to Azure RMS</caps:sentence>
                    </embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src59" class="srcSentence">You export the configuration data (keys, templates, URLs) from AD RMS to an XML file, and then upload that file to Azure RMS by using the Import-AadrmTpd Windows PowerShell cmdlet.</caps:sentence>
                    <caps:sentence id="src60" class="srcSentence"> Additional steps might be needed, depending your on AD RMS key configuration:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src61" class="srcSentence">Software-protected key to software-protected key migration: Centrally managed, password-based keys in AD RMS to Microsoft-managed Azure RMS tenant key.</caps:sentence>
                        <caps:sentence id="src62" class="srcSentence"> This is the simplest migration path and no additional steps are required.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src63" class="srcSentence">HSM-protected  key to HSM-protected key migration: Keys that are stored by an HSM for AD RMS to customer-managed Azure RMS tenant key (the “bring your own key” or BYOK scenario).</caps:sentence>
                        <caps:sentence id="src64" class="srcSentence"> This requires additional steps to transfer the key from your on-premises Thales HSM to the Azure RMS HSM.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src65" class="srcSentence">Software-protected key to HSM-protected key migration: Centrally managed, password-based keys in AD RMS to customer-managed Azure RMS tenant key (the “bring your own key” or BYOK scenario).</caps:sentence>
                        <caps:sentence id="src66" class="srcSentence"> This requires the most configuration because you must first extract your software key and import it to an on-premises HSM, and then do the additional steps to transfer the key from your on-premises Thales HSM to the Azure RMS HSM.</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <para>
                    <caps:sentence id="src67" class="srcSentence">For instructions, see <link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172#BKMK_Step2Migration">Step 2. Export configuration data from AD RMS and import it to Azure RMS</link>.</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>
                      <caps:sentence id="src68" class="srcSentence">3. Activate your RMS tenant</caps:sentence>
                    </embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src69" class="srcSentence">If possible, do this step after the import process and not before.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src70" class="srcSentence">For more information and instructions, see <link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172#BKMK_Step3Migration">Step 3. Activate your RMS tenant</link>.</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>
                      <caps:sentence id="src71" class="srcSentence">4. Configure imported templates</caps:sentence>
                    </embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src72" class="srcSentence">When you import your rights policy templates, their status is archived.</caps:sentence>
                    <caps:sentence id="src73" class="srcSentence"> If you want users to be able to see and use them, you must change the template status to published in the Azure classic portal.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src74" class="srcSentence">For instructions, see <link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172#BKMK_Step4Migration">Step 4. Configure imported templates</link>.</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>
                      <caps:sentence id="src75" class="srcSentence">5. Reconfigure clients to use Azure RMS</caps:sentence>
                    </embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src76" class="srcSentence">Existing Windows computers must be reconfigured to use the Azure RMS service instead of AD RMS.</caps:sentence>
                    <caps:sentence id="src77" class="srcSentence"> This step applies to computers in your organization, and to computers in partner organizations if you have collaborated with them while you were running AD RMS.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src78" class="srcSentence">In addition, if you have deployed the <externalLink><linkText>mobile device extensions</linkText><linkUri>http://technet.microsoft.com/library/dn673574.aspx</linkUri></externalLink> to support mobile devices such as iOS phones and iPads, Android phones and tablets, Windows phone, and Mac computers, you must remove the SRV records in DNS that redirected these clients to use AD RMS.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src79" class="srcSentence">For instructions, see <link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172#BKMK_Step5Migration">Step 5. Reconfigure clients to use Azure RMS</link>.</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>
                      <caps:sentence id="src80" class="srcSentence">6. Configure IRM integration with Exchange Online</caps:sentence>
                    </embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src81" class="srcSentence">This step is required if you want to use Exchange Online with Azure RMS.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src82" class="srcSentence">For instructions, see <link xlink:href="#BKMK_Step6Migration">Step 6. Configure IRM integration for Exchange Online</link>.</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>
                      <caps:sentence id="src83" class="srcSentence">7. Deploy the RMS connector</caps:sentence>
                    </embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src84" class="srcSentence">This step is required if you want to use any of the following on-premises services with Azure RMS:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src85" class="srcSentence">Exchange Server (for example, transport rules and Outlook Web Access)</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src86" class="srcSentence">SharePoint Server </caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src87" class="srcSentence">Windows Server that runs File Classification Infrastructure</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <para>
                    <caps:sentence id="src88" class="srcSentence">For instructions, see <link xlink:href="#BKMK_Step7Migration">Step 7. Deploy the RMS connector</link>.</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src89" class="srcSentence">
                      <embeddedLabel>8. Decommission AD RMS</embeddedLabel> </caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src90" class="srcSentence">When you have confirmed that all clients are using Azure RMS and no longer accessing the AD RMS servers, you can decommission your AD RMS deployment.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src91" class="srcSentence">For instructions, see <link xlink:href="#BKMK_Step8Migration">Step 8. Decommission AD RMS</link>.</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <embeddedLabel>
                      <caps:sentence id="src92" class="srcSentence">9. Re-key your Azure RMS tenant key</caps:sentence>
                    </embeddedLabel>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src93" class="srcSentence">This step is required if you were not running in Cryptographic Mode 2 before the migration, and optional but recommended for all migrations to help safeguard the security of your Azure RMS tenant key.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src94" class="srcSentence">For instructions, see <link xlink:href="#BKMK_Step9Migration">Step 9. Re-key your Azure RMS tenant key</link>.</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
        <sections>
          <section address="BKMK_Step1Migration">
            <title>
              <caps:sentence id="src95" class="srcSentence">Step 1: Download the Azure Rights Management Administration Tool</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src96" class="srcSentence">Go to the Microsoft Download Center and download the <externalLink><linkText>Azure Rights Management Administration Tool</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=257721</linkUri></externalLink>, which contains the Azure RMS administration module for Windows PowerShell.</caps:sentence>
              </para>
            </content>
          </section>
          <section address="BKMK_Step2Migration">
            <title>
              <caps:sentence id="src97" class="srcSentence">Step 2.</caps:sentence>
              <caps:sentence id="src98" class="srcSentence"> Export configuration data from AD RMS and import it to Azure RMS</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src99" class="srcSentence">This step is a two-part process:</caps:sentence>
              </para>
              <list class="ordered">
                <listItem>
                  <para>
                    <caps:sentence id="src100" class="srcSentence">Export the configuration data from AD RMS by exporting the trusted publishing domains (TPDs) to an .xml file.</caps:sentence>
                    <caps:sentence id="src101" class="srcSentence"> This process is the same for all migrations.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src102" class="srcSentence">Import the configuration data to Azure RMS.</caps:sentence>
                    <caps:sentence id="src103" class="srcSentence"> There are different processes for this step, depending on your current AD RMS deployment configuration and your preferred topology for your Azure RMS tenant key.</caps:sentence>
                  </para>
                </listItem>
              </list>
            </content>
            <sections>
              <section>
                <title>
                  <caps:sentence id="src104" class="srcSentence">Export the configuration data from AD RMS</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence id="src105" class="srcSentence">Do the following procedure on all AD RMS clusters, for all trusted publishing domains that have protected content for your organization.</caps:sentence>
                    <caps:sentence id="src106" class="srcSentence"> You do not need to run this on licensing-only clusters.</caps:sentence>
                  </para>
                  <alert class="note">
                    <para>
                      <caps:sentence id="src107" class="srcSentence">If you are using Windows Server 2003 Rights Management, instead of these instructions, follow the procedure <externalLink><linkText>Export SLC, TUD, TPD and RMS private key</linkText><linkUri>http://technet.microsoft.com/library/jj835767(v=ws.10).aspx</linkUri></externalLink> from the <externalLink><linkText>Migrating from Windows RMS to AD RMS in a Different Infrastructure</linkText><linkUri>http://technet.microsoft.com/library/jj835767(v=ws.10).aspx</linkUri></externalLink> topic.</caps:sentence>
                    </para>
                  </alert>
                  <procedure>
                    <title>
                      <caps:sentence id="src108" class="srcSentence">To export the configuration data (trusted publishing domain information)</caps:sentence>
                    </title>
                    <steps class="ordered">
                      <step>
                        <content>
                          <para>
                            <caps:sentence id="src109" class="srcSentence">Log on the AD RMS cluster as a user with AD RMS administration permissions.</caps:sentence>
                          </para>
                        </content>
                      </step>
                      <step>
                        <content>
                          <para>
                            <caps:sentence id="src110" class="srcSentence">From the AD RMS management console (<ui>Active Directory Rights Management Services</ui>), expand the AD RMS cluster name, expand <ui>Trust Policies</ui>, and then click <ui>Trusted Publishing Domains</ui>.</caps:sentence>
                          </para>
                        </content>
                      </step>
                      <step>
                        <content>
                          <para>
                            <caps:sentence id="src111" class="srcSentence">In the results pane, select the trusted publishing domain, and then, from the Actions pane, click <ui>Export Trusted Publishing Domain</ui>.</caps:sentence>
                          </para>
                        </content>
                      </step>
                      <step>
                        <content>
                          <para>
                            <caps:sentence id="src112" class="srcSentence">In the <ui>Export Trusted Publishing Domain</ui> dialog box: </caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence id="src113" class="srcSentence">Click <ui>Save As</ui> and save to path and a file name of your choice.</caps:sentence>
                                <caps:sentence id="src114" class="srcSentence"> Make sure to specify <userInput>.xml</userInput> as the file name extension (this is not appended automatically).</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src115" class="srcSentence">Specify and confirm a strong password.</caps:sentence>
                                <caps:sentence id="src116" class="srcSentence"> Remember this password, because you will need it later, when you import the configuration data to Azure RMS.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src117" class="srcSentence">Do not select the checkbox to save the trusted domain file in RMS version 1.0.</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </content>
                      </step>
                    </steps>
                    <conclusion>
                      <content>
                        <para>
                          <caps:sentence id="src118" class="srcSentence">When you have exported all the trusted publishing domains, you’re ready to start the procedure to import this data to Azure RMS.</caps:sentence>
                        </para>
                      </content>
                    </conclusion>
                  </procedure>
                </content>
              </section>
              <section>
                <title>
                  <caps:sentence id="src119" class="srcSentence">Import the configuration data to Azure RMS</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence id="src120" class="srcSentence">The exact procedures for this step depend on your current AD RMS deployment configuration, and your preferred topology for your Azure RMS tenant key.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src121" class="srcSentence">Your current AD RMS deployment will be using one of the following configurations for your server licensor certificate (SLC) key:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src122" class="srcSentence">Password protection in the AD RMS database.</caps:sentence>
                        <caps:sentence id="src123" class="srcSentence"> This is the default configuration.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src124" class="srcSentence">HSM protection by using a Thales hardware security module (HSM).</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src125" class="srcSentence">HSM protection by using a hardware security module (HSM) from a supplier other than Thales.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src126" class="srcSentence">Password protected by using an external cryptographic provider.</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <alert class="note">
                    <para>
                      <caps:sentence id="src127" class="srcSentence">For more information about using hardware security modules with AD RMS, see <externalLink><linkText>Using AD RMS with Hardware Security Modules</linkText><linkUri>http://technet.microsoft.com/library/jj651024.aspx</linkUri></externalLink>.</caps:sentence>
                    </para>
                  </alert>
                  <para>
                    <caps:sentence id="src128" class="srcSentence">The two Azure RMS tenant key topology options are: Microsoft manages your tenant key (<embeddedLabel>Microsoft-managed</embeddedLabel>) or you manage your tenant key (<embeddedLabel>customer-managed</embeddedLabel>).</caps:sentence>
                    <caps:sentence id="src129" class="srcSentence"> When you manage your own Azure RMS tenant key, it’s sometimes referred to as “bring your own key” (BYOK) and requires a hardware security module (HSM) from Thales.</caps:sentence>
                    <caps:sentence id="src130" class="srcSentence"> For more information, see the <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_ChooseTenantKey">Choose your tenant key topology: Managed by Microsoft (the default) or managed by you (BYOK)</link> section in the <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and Implementing Your Azure Rights Management Tenant Key</link> topic.</caps:sentence>
                  </para>
                  <alert class="important">
                    <para>
                      <caps:sentence id="src131" class="srcSentence"> Exchange Online is not currently  compatible with Azure RMS BYOK.</caps:sentence>
                      <caps:sentence id="src132" class="srcSentence">  If you want to use BYOK after your migration and plan to use Exchange Online, make sure that you understand how this configuration reduces IRM functionality for Exchange Online.</caps:sentence>
                      <caps:sentence id="src133" class="srcSentence"> Review  the information in the <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_Pricing">BYOK pricing and restrictions</link> section in the  <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and Implementing Your Azure Rights Management Tenant Key</link> topic to help you choose the best Azure RMS tenant key topology for your migration.</caps:sentence>
                    </para>
                  </alert>
                  <para>
                    <caps:sentence id="src134" class="srcSentence">Use the following table to identify which procedure to use for your migration.</caps:sentence>
                    <caps:sentence id="src135" class="srcSentence"> Combinations that are not listed are not supported.</caps:sentence>
                  </para>
                  <table>
                    <thead>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src136" class="srcSentence">Current AD RMS deployment</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src137" class="srcSentence">Chosen Azure RMS tenant key topology</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src138" class="srcSentence">Migration instructions</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src139" class="srcSentence">Password protection in the AD RMS database</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src140" class="srcSentence">Microsoft-managed</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src141" class="srcSentence">See the <embeddedLabel>Software-protected key to software-protected key migration</embeddedLabel> procedure after this table.</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence id="src142" class="srcSentence">This is the simplest migration path and requires only that you transfer your configuration data to Azure RMS.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src143" class="srcSentence">HSM protection by using a Thales nShield hardware security module (HSM)</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src144" class="srcSentence">Customer-managed (BYOK)</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src145" class="srcSentence">See the <embeddedLabel>HSM-protected key to HSM-protected key migration</embeddedLabel> procedure after this table.</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence id="src146" class="srcSentence">This requires the BYOK toolset and two set of steps to transfer the key from your on-premises HSM to the Azure RMS HSMs and then transfer your configuration data to Azure RMS.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src147" class="srcSentence">Password protection in the AD RMS database</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src148" class="srcSentence">Customer-managed (BYOK)</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src149" class="srcSentence">See the <embeddedLabel>Software-protected key to HSM-protected key migration</embeddedLabel> procedure after this table.</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence id="src150" class="srcSentence">This requires the BYOK toolset and three sets of steps to first extract your software key and import it to an on-premises HSM, then transfer the key from your on-premises HSM to the Azure RMS HSMs, and finally transfer your configuration data to Azure RMS.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src151" class="srcSentence">HSM protection by using a hardware security module (HSM) from a supplier other than Thales</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src152" class="srcSentence">Customer-managed (BYOK)</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src153" class="srcSentence">Contact the supplier for you HSM for instructions how to transfer your key from this HSM to a Thales nShield Hardware Security Module (HSM).</caps:sentence>
                            <caps:sentence id="src154" class="srcSentence"> Then follow the instructions for the <embeddedLabel>HSM-protected key to HSM-protected key migration</embeddedLabel> procedure after this table.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src155" class="srcSentence">Password protected by using an external cryptographic provider</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src156" class="srcSentence">Customer-managed (BYOK)</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src157" class="srcSentence">Contact the supplier for you cryptographic provider for instructions how to transfer your key to a Thales nShield hardware security module (HSM).</caps:sentence>
                            <caps:sentence id="src158" class="srcSentence"> Then follow the instructions for the <embeddedLabel>HSM-protected key to HSM-protected key migration</embeddedLabel> procedure after this table.</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </tbody>
                  </table>
                  <para>
                    <caps:sentence id="src159" class="srcSentence">Before you start these procedures, make sure that you can access the .xml files that you created earlier when you exported the trusted publishing domains.</caps:sentence>
                    <caps:sentence id="src160" class="srcSentence"> For example, these might be saved to a USB thumb drive that you move from the AD RMS server to the Internet-connected workstation.</caps:sentence>
                  </para>
                  <alert class="security note">
                    <para>
                      <caps:sentence id="src161" class="srcSentence">However you store these files, use security best practices to protect them because this data includes your private key.</caps:sentence>
                    </para>
                  </alert>
                </content>
                <sections>
                  <section expanded="false">
                    <title>
                      <caps:sentence id="src162" class="srcSentence">Software-protected key to software-protected key migration</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src163" class="srcSentence">Use this procedure to import the AD RMS configuration to Azure RMS, to result in your Azure RMS tenant key that is managed by Microsoft.</caps:sentence>
                      </para>
                      <procedure>
                        <title>
                          <caps:sentence id="src164" class="srcSentence">To import the configuration data to Azure RMS</caps:sentence>
                        </title>
                        <steps class="ordered">
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src165" class="srcSentence">On an Internet-connected workstation, download and install the Windows PowerShell module for Azure RMS (minimum version 2.1.0.0), which includes the <externalLink><linkText>Import-AadrmTpd</linkText><linkUri>http://msdn.microsoft.com/library/azure/dn857523.aspx</linkUri></externalLink> cmdlet.</caps:sentence>
                              </para>
                              <alert class="tip">
                                <para>
                                  <caps:sentence id="src166" class="srcSentence">If you have previously downloaded and installed the module, check the version number by running: <codeInline>(Get-Module aadrm -ListAvailable).Version</codeInline></caps:sentence>
                                </para>
                              </alert>
                              <para>
                                <caps:sentence id="src167" class="srcSentence">For installation instructions, see <link xlink:href="0d665ed6-b1de-4d63-854a-bc57c1c49844">Installing Windows PowerShell for Azure Rights Management</link>.</caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src168" class="srcSentence">Start Windows PowerShell with the <ui>Run as administrator</ui> option and use the <externalLink><linkText>Connect-AadrmService</linkText><linkUri>http://msdn.microsoft.com/library/azure/dn629415.aspx</linkUri></externalLink> cmdlet to connect to the Azure RMS service:</caps:sentence>
                              </para>
                              <code>Connect-AadrmService</code>
                              <para>
                                <caps:sentence id="src169" class="srcSentence">When prompted, enter your <token>aad_rightsmanagement_1</token> tenant administrator credentials (typically, you will use an account that is a global administrator for Azure Active Directory or Office 365).</caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src170" class="srcSentence">Use the <externalLink><linkText>Import-AadrmTpd</linkText><linkUri>http://msdn.microsoft.com/library/azure/dn857523.aspx</linkUri></externalLink> cmdlet to upload the first exported trusted publishing domain (.xml) file.</caps:sentence>
                                <caps:sentence id="src171" class="srcSentence"> If you have more than one .xml file because you had multiple trusted publishing domains, choose the file that contains the exported trusted publishing domain that you want to use in Azure RMS to protect content after the migration.</caps:sentence>
                                <caps:sentence id="src172" class="srcSentence"> Use the following command:</caps:sentence>
                              </para>
                              <code>Import-AadrmTpd -TpdFile &lt;PathToTpdPackageFile&gt; -ProtectionPassword -Active $True -Verbose 
</code>
                              <para>
                                <caps:sentence id="src173" class="srcSentence">For example: <userInput>Import-AadrmTpd -TpdFile E:\contosokey1.xml -ProtectionPassword -Active $true -Verbose</userInput></caps:sentence>
                              </para>
                              <para>
                                <caps:sentence id="src174" class="srcSentence">When prompted, enter the password that you specified earlier, and confirm that you want to perform this action.</caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src175" class="srcSentence">When the command completes, repeat step 3 for each remaining  .xml file that you created by exporting your trusted publishing domains.</caps:sentence>
                                <caps:sentence id="src176" class="srcSentence"> But for these files, set <userInput>-Active</userInput> to <userInput>false</userInput> when you run the Import command.</caps:sentence>
                                <caps:sentence id="src177" class="srcSentence"> For example: <userInput>Import-AadrmTpd -TpdFile E:\contosokey2.xml -ProtectionPassword -Active $false -Verbose</userInput></caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src178" class="srcSentence">Use the <externalLink><linkText>Disconnect-AadrmService</linkText><linkUri>http://msdn.microsoft.com/library/azure/dn629416.aspx</linkUri></externalLink> cmdlet to disconnect from the Azure RMS service:</caps:sentence>
                              </para>
                              <code>Disconnect-AadrmService</code>
                            </content>
                          </step>
                        </steps>
                        <conclusion>
                          <content>
                            <para>
                              <caps:sentence id="src179" class="srcSentence">You’re now ready to go to <link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172#BKMK_Step3Migration">Step 3. Activate your RMS tenant</link>.</caps:sentence>
                            </para>
                          </content>
                        </conclusion>
                      </procedure>
                    </content>
                  </section>
                  <section expanded="false">
                    <title>
                      <caps:sentence id="src180" class="srcSentence">HSM-protected key to HSM-protected key migration</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src181" class="srcSentence">It’s a two-part procedure to import your HSM key and AD RMS configuration to Azure RMS, to result in your Azure RMS tenant key that is managed by you (BYOK).</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src182" class="srcSentence">You must first package your HSM key so it's ready to transfer to Azure RMS, and then import it with the configuration data.</caps:sentence>
                      </para>
                      <procedure>
                        <title>
                          <caps:sentence id="src183" class="srcSentence">Part 1: Package your HSM key so it's ready to transfer to Azure RMS</caps:sentence>
                        </title>
                        <steps class="ordered">
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src184" class="srcSentence">Follow the steps in the <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_ImplementBYOK">Implementing bring your own key (BYOK)</link> section of the <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and Implementing Your Azure Rights Management Tenant Key</link>, using the procedure <embeddedLabel>Generate and transfer your tenant key – over the Internet</embeddedLabel> with the following exceptions:</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence id="src185" class="srcSentence">Do not follow the steps for <embeddedLabel>Generate your tenant key</embeddedLabel>, because you already have the equivalent from your AD RMS deployment.</caps:sentence>
                                    <caps:sentence id="src186" class="srcSentence"> You must identify the key used by your AD RMS server from the Thales installation and use this key during the migration.</caps:sentence>
                                    <caps:sentence id="src187" class="srcSentence"> Thales encrypted key files are usually named <ui>key_(keyAppName)_(keyIdentifier)</ui> locally on the server.</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence id="src188" class="srcSentence">Do not follow the steps for <embeddedLabel>Transfer your tenant key to Azure RMS</embeddedLabel>, which uses the  Add-AadrmKey command.</caps:sentence>
                                    <caps:sentence id="src189" class="srcSentence">  Instead, you will transfer your prepared HSM key when you upload your exported trusted publishing domain, by using the Import-AadrmTpd command.</caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src190" class="srcSentence">On the Internet-connected workstation, in Windows PowerShell session, reconnect to the Azure RMS service.</caps:sentence>
                              </para>
                            </content>
                          </step>
                        </steps>
                        <conclusion>
                          <content>
                            <para>
                              <caps:sentence id="src191" class="srcSentence">Now that you’ve prepared your HSM key for Azure RMS, you’re ready to import your HSM key file and AD RMS configuration data.</caps:sentence>
                            </para>
                          </content>
                        </conclusion>
                      </procedure>
                      <procedure>
                        <title>
                          <caps:sentence id="src192" class="srcSentence">Part 2: Import the HSM key and configuration data to Azure RMS</caps:sentence>
                        </title>
                        <steps class="ordered">
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src193" class="srcSentence">Still on the Internet-connect workstation and in the Windows PowerShell session, upload the first exported trusted publishing domain (.xml) file.</caps:sentence>
                                <caps:sentence id="src194" class="srcSentence"> If you have more than one .xml file because you had multiple trusted publishing domains, choose the file that contains the exported trusted publishing domain that corresponds to the HSM key you want to use in Azure RMS to protect content after the migration.</caps:sentence>
                                <caps:sentence id="src195" class="srcSentence"> Use the following command:</caps:sentence>
                              </para>
                              <code>Import-AadrmTpd -TpdFile &lt;PathToTpdPackageFile&gt; -ProtectionPassword -HsmKeyFile &lt;PathToBYOKPackage&gt; -Active $True -Verbose</code>
                              <para>
                                <caps:sentence id="src196" class="srcSentence">For example: <userInput>Import -TpdFile E:\no_key_tpd_contosokey1.xml  -HsmKeyFile E:\KeyTransferPackage-contosokey.byok -ProtectionPassword -Active $true -Verbose</userInput></caps:sentence>
                              </para>
                              <para>
                                <caps:sentence id="src197" class="srcSentence">When prompted, enter the password that you specified earlier, and confirm that you want to perform this action.</caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src198" class="srcSentence">When the command completes, repeat step 1 for each remaining  .xml file that you created by exporting your trusted publishing domains.</caps:sentence>
                                <caps:sentence id="src199" class="srcSentence"> But for these files, set <userInput>-Active</userInput> to <userInput>false</userInput> when you run the Import command.</caps:sentence>
                                <caps:sentence id="src200" class="srcSentence">  For example: <userInput>Import -TpdFile E:\contosokey2.xml -HsmKeyFile E:\KeyTransferPackage-contosokey.byok -ProtectionPassword -Active $false -Verbose</userInput></caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src201" class="srcSentence">Use the <externalLink><linkText>Disconnect-AadrmService</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629416.aspx</linkUri></externalLink> cmdlet to disconnect from the Azure RMS service:</caps:sentence>
                              </para>
                              <code>Disconnect-AadrmService</code>
                            </content>
                          </step>
                        </steps>
                        <conclusion>
                          <content>
                            <para>
                              <caps:sentence id="src202" class="srcSentence">You’re now ready to go to <link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172#BKMK_Step3Migration">Step 3. Activate your RMS tenant</link>.</caps:sentence>
                            </para>
                          </content>
                        </conclusion>
                      </procedure>
                    </content>
                  </section>
                  <section expanded="false">
                    <title>
                      <caps:sentence id="src203" class="srcSentence">Software-protected key to HSM-protected key migration</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src204" class="srcSentence">It’s a three-part procedure to import the AD RMS configuration to Azure RMS, to result in your Azure RMS tenant key that is managed by you (BYOK).</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src205" class="srcSentence">You must first extract your server licensor certificate (SLC) key from the configuration data and transfer the key to an on-premises Thales HSM, then package and transfer your HSM key to Azure RMS, and then import the configuration data.</caps:sentence>
                      </para>
                      <procedure>
                        <title>
                          <caps:sentence id="src206" class="srcSentence">Part 1: Extract your SLC from the configuration data and import the key to your on-premises HSM</caps:sentence>
                        </title>
                        <steps class="ordered">
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src207" class="srcSentence">Use the following steps in the <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_ImplementBYOK">Implementing bring your own key (BYOK)</link> section of the <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and Implementing Your Azure Rights Management Tenant Key</link> topic:</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence id="src208" class="srcSentence">
                                      <embeddedLabel>Generate and transfer your tenant key – over the Internet</embeddedLabel>: <embeddedLabel>Prepare your Internet-connected workstation</embeddedLabel></caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence id="src209" class="srcSentence">
                                      <embeddedLabel>Generate and transfer your tenant key – over the Internet</embeddedLabel>: <embeddedLabel>Prepare your disconnected workstation</embeddedLabel></caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                              <para>
                                <caps:sentence id="src210" class="srcSentence">Do not follow the steps to generate your tenant key, because you already have the equivalent in the exported configuration data (.xml) file.</caps:sentence>
                                <caps:sentence id="src211" class="srcSentence"> Instead, you will run a command to extract this key from the file and import it to your on-premises HSM.</caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src212" class="srcSentence">On the disconnected workstation, run the following command:</caps:sentence>
                              </para>
                              <code>KeyTransferRemote.exe -ImportRmsCentrallyManagedKey -TpdFilePath &lt;TPD&gt; -ProtectionPassword -KeyIdentifier &lt;KeyID&gt; -ExchangeKeyPackage &lt;BYOK-KEK-pka-Region&gt; -NewSecurityWorldPackage &lt;BYOK-SecurityWorld-pkg-Region&gt;</code>
                              <para>
                                <caps:sentence id="src213" class="srcSentence">For example, for North America: <userInput>KeyTransferRemote.exe -ImportRmsCentrallyManagedKey -TpdFilePath E:\contosokey1.xml -ProtectionPassword -KeyIdentifier contosorms1key –- -ExchangeKeyPackage &lt;BYOK-KEK-pka-NA-1&gt; -NewSecurityWorldPackage &lt;BYOK-SecurityWorld-pkg-NA-1&gt;</userInput></caps:sentence>
                              </para>
                              <para>
                                <caps:sentence id="src214" class="srcSentence">Additional information:</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence id="src215" class="srcSentence">The ImportRmsCentrallyManagedKey parameter indicates that the operation is to import the SLC key.</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence id="src216" class="srcSentence">If you don’t specify the password in the command, you will be prompted to specify it.</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence id="src217" class="srcSentence">The KeyIdentifier parameter is for a key friendly name that creates the key file name.</caps:sentence>
                                    <caps:sentence id="src218" class="srcSentence"> You must use only lower-case ASCII characters.</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence id="src219" class="srcSentence">The ExchangeKeyPackage parameter specifies a region-specific key exchange key (KEK) package that has a name beginning with BYOK-KEK-pkg-.</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence id="src220" class="srcSentence">The NewSecurityWorldPackage parameter specifies a region-specific security world package that has a name beginning with BYOK-SecurityWorld-pkg-.</caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                              <para>
                                <caps:sentence id="src221" class="srcSentence">This command results in the following:</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence id="src222" class="srcSentence">An HSM key file: %NFAST_KMDATA%\local\key_mscapi_&lt;KeyID&gt;</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence id="src223" class="srcSentence">RMS configuration data file with the SLC removed: %NFAST_KMDATA%\local\no_key_tpd_&lt;KeyID&gt;.xml</caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src224" class="srcSentence">If you have more than one RMS configuration data files, repeat step 2 for the remainder of these files.</caps:sentence>
                              </para>
                            </content>
                          </step>
                        </steps>
                        <conclusion>
                          <content>
                            <para>
                              <caps:sentence id="src225" class="srcSentence">Now that your SLC has been extracted so that it’s an HSM-based key, you’re ready to package and transfer it to Azure RMS.</caps:sentence>
                            </para>
                          </content>
                        </conclusion>
                      </procedure>
                      <procedure>
                        <title>
                          <caps:sentence id="src226" class="srcSentence">Part 2: Package and transfer your HSM key to Azure RMS</caps:sentence>
                        </title>
                        <steps class="ordered">
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src227" class="srcSentence">Use the following steps from the <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_ImplementBYOK">Implementing bring your own key (BYOK)</link> section of the <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and Implementing Your Azure Rights Management Tenant Key</link>:</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence id="src228" class="srcSentence">
                                      <embeddedLabel>Generate and transfer your tenant key – over the Internet</embeddedLabel>: <embeddedLabel>Prepare your tenant key for transfer</embeddedLabel></caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence id="src229" class="srcSentence">
                                      <embeddedLabel>Generate and transfer your tenant key – over the Internet</embeddedLabel>: <embeddedLabel>Transfer your tenant key to Azure RMS</embeddedLabel></caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                            </content>
                          </step>
                        </steps>
                        <conclusion>
                          <content>
                            <para>
                              <caps:sentence id="src230" class="srcSentence">Now that you’ve transferred your HSM key to Azure RMS, you’re ready to import your AD RMS configuration data, which contains only a pointer to the newly transferred tenant key.</caps:sentence>
                            </para>
                          </content>
                        </conclusion>
                      </procedure>
                      <procedure>
                        <title>
                          <caps:sentence id="src231" class="srcSentence">Part 3: Import the configuration data to Azure RMS</caps:sentence>
                        </title>
                        <steps class="ordered">
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src232" class="srcSentence">Still on the Internet-connected workstation and in the Windows PowerShell session, copy over the RMS configuration files with the SLC removed (from the disconnected workstation, %NFAST_KMDATA%\local\no_key_tpd_&lt;KeyID&gt;.xml)</caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src233" class="srcSentence">Upload the first file.</caps:sentence>
                                <caps:sentence id="src234" class="srcSentence"> If you have more than one .xml file because you had multiple trusted publishing domains, choose the file that contains the exported trusted publishing domain that corresponds to the HSM key you want to use in Azure RMS to protect content after the migration.</caps:sentence>
                                <caps:sentence id="src235" class="srcSentence"> Use the following command:</caps:sentence>
                              </para>
                              <code>Import-AadrmTpd -TpdFile &lt;PathToNoKeyTpdPackageFile&gt; -ProtectionPassword -HsmKeyFile &lt;PathToKeyTransferPackage&gt; -Active $true -Verbose </code>
                              <para>
                                <caps:sentence id="src236" class="srcSentence">For example: <userInput>Import -TpdFile E:\no_key_tpd_contosorms1key.xml -ProtectionPassword -HsmKeyFile E:\KeyTransferPackage-contosorms1key.byok -Active $true -Verbose </userInput></caps:sentence>
                              </para>
                              <para>
                                <caps:sentence id="src237" class="srcSentence">When prompted, enter the password that you specified earlier, and confirm that you want to perform this action.</caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src238" class="srcSentence">When the command completes, repeat step 2 for each remaining  .xml file that you created by exporting your trusted publishing domains.</caps:sentence>
                                <caps:sentence id="src239" class="srcSentence"> But for these files, set <userInput>-Active</userInput> to <userInput>false</userInput> when you run the Import command.</caps:sentence>
                                <caps:sentence id="src240" class="srcSentence"> For example: <userInput>Import -TpdFile E:\no_key_tpd_contosorms2key.xml -ProtectionPassword -HsmKeyFile E:\KeyTransferPackage-contosorms1key.byok -Active $false -Verbose </userInput></caps:sentence>
                              </para>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src241" class="srcSentence">Use the <externalLink><linkText>Disconnect-AadrmService</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629416.aspx</linkUri></externalLink> cmdlet to disconnect from the Azure RMS service:</caps:sentence>
                              </para>
                              <code>Disconnect-AadrmService</code>
                            </content>
                          </step>
                        </steps>
                        <conclusion>
                          <content>
                            <para>
                              <caps:sentence id="src242" class="srcSentence">You’re now ready to go to <link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172#BKMK_Step3Migration">Step 3. Activate your RMS tenant</link>.</caps:sentence>
                            </para>
                          </content>
                        </conclusion>
                      </procedure>
                    </content>
                  </section>
                </sections>
              </section>
            </sections>
          </section>
          <section address="BKMK_Step3Migration">
            <title>
              <caps:sentence id="src243" class="srcSentence">Step 3.</caps:sentence>
              <caps:sentence id="src244" class="srcSentence"> Activate your RMS tenant</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src245" class="srcSentence">Instructions  for this step are fully covered in the <link xlink:href="f8707e01-b239-4d1a-a1ea-0d1cf9a8d214">Activating Azure Rights Management</link> topic.</caps:sentence>
              </para>
              <alert class="tip">
                <para>
                  <caps:sentence id="src246" class="srcSentence">If you have an Office 365 subscription, you can activate Azure RMS from the Office 365 admin center or the Azure classic portal.</caps:sentence>
                  <caps:sentence id="src247" class="srcSentence"> We recommend that you use the Azure classic portal because you will use this management portal to complete the next step.</caps:sentence>
                </para>
              </alert>
              <para>
                <caps:sentence id="src248" class="srcSentence">
                  <embeddedLabel>What if your Azure RMS tenant is already activated?</embeddedLabel> If the Azure RMS service is already activated for your organization, users might have already used Azure RMS to protect content with an automatically generated tenant key (and the default templates) rather than your existing keys (and templates) from AD RMS.</caps:sentence>
                <caps:sentence id="src249" class="srcSentence"> This is unlikely to happen on computers that are well-managed on your intranet, because they will be automatically configured for your AD RMS infrastructure.</caps:sentence>
                <caps:sentence id="src250" class="srcSentence"> But it can happen on workgroup computers or computers that infrequently connect to your intranet.</caps:sentence>
                <caps:sentence id="src251" class="srcSentence"> Unfortunately, it’s also difficult to identify these computers, which is why we recommend you do not activate the service before you import the configuration data from AD RMS.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src252" class="srcSentence">If your Azure RMS tenant is already activated and you can identify these computers, make sure that you run the CleanUpRMS_RUN_Elevated.cmd script on these computers, as described in Step 5.</caps:sentence>
                <caps:sentence id="src253" class="srcSentence"> Running this script forces them to reinitialize the user environment, so that they download the updated tenant key and imported templates.</caps:sentence>
              </para>
            </content>
          </section>
          <section address="BKMK_Step4Migration">
            <title>
              <caps:sentence id="src254" class="srcSentence">Step 4.</caps:sentence>
              <caps:sentence id="src255" class="srcSentence"> Configure imported templates</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src256" class="srcSentence">Because the templates that you imported have a default state of <ui>Archived</ui>, you must change this state to be <ui>Published</ui> if you want users to be able to use these templates with Azure RMS.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src257" class="srcSentence">In addition, if your templates in AD RMS used the <ui>ANYONE</ui> group, this group is automatically removed  when you import the templates to Azure RMS; you must manually add the equivalent group or users and the same rights to the imported templates.</caps:sentence>
                <caps:sentence id="src258" class="srcSentence"> The equivalent group for Azure RMS is named <system>AllStaff-&lt;tenant_GUID&gt;@&lt;tenant_name&gt;.onmicrosoft.com</system>.</caps:sentence>
                <caps:sentence id="src259" class="srcSentence"> For example, this group might look like the following for Contoso: <system>AllStaff-9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a@contoso.onmicrosoft.com</system>.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src260" class="srcSentence">If  you're not sure whether your AD RMS templates include the ANYONE group, expand the  <link xlink:href="#BKMK_ScriptForANYONE">PowerShell script to identify AD RMS templates that include the ANYONE group</link> section in this step to copy and use the sample PowerShell script to identify these templates.</caps:sentence>
                <caps:sentence id="src261" class="srcSentence"> For more information about using Windows PowerShell with AD RMS, see  <externalLink><linkText>Using Windows PowerShell to Administer AD RMS</linkText><linkUri>https://technet.microsoft.com/library/ee221079(v=ws.10).aspx</linkUri></externalLink>.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src262" class="srcSentence">You can see your organization's automatically created group if you copy one of the default rights policy templates in the Azure classic portal, and then identify the <ui>USER NAME</ui> on the <ui>RIGHTS</ui> page.</caps:sentence>
                <caps:sentence id="src263" class="srcSentence"> However, you cannot use the classic portal to add this group to a template that was manually created or imported and instead must use one of the following Azure RMS PowerShell options:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src264" class="srcSentence">Use the <externalLink><linkText>New-AadrmRightsDefinition</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn727080.aspx</linkUri></externalLink> PowerShell cmdlet to define the  "AllStaff" group and rights as a rights definition object, and run this command again for each of the other groups or users already granted rights in the original template in addition to the ANYONE group.</caps:sentence>
                    <caps:sentence id="src265" class="srcSentence"> Then add all these rights definition objects to the templates by using the  <externalLink><linkText>Set-AadrmTemplateProperty</linkText><linkUri>https://msdn.microsoft.com/en-us/library/azure/dn727076.aspx</linkUri></externalLink> cmdlet.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src266" class="srcSentence">Use the <externalLink><linkText>Export-AadrmTemplate</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn727078.aspx</linkUri></externalLink> cmdlet to export the template to a .XML file that you can edit to add the "AllStaff" group and rights to the existing groups and rights, and then use the <externalLink><linkText>Import-AadrmTemplate</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn727077.aspx</linkUri></externalLink> cmdlet to import this change back into Azure RMS.</caps:sentence>
                  </para>
                </listItem>
              </list>
              <alert class="note">
                <para>
                  <caps:sentence id="src267" class="srcSentence">This "AllStaff" equivalent group isn't exactly the same as the ANYONE group in AD RMS:  The "AllStaff" group includes all users in your Azure tenant, whereas the ANYONE group includes all authenticated users, who could be outside your organization.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src268" class="srcSentence">Because of this difference between the two groups, you might need to also add external users in addition to the "AllStaff" group.</caps:sentence>
                  <caps:sentence id="src269" class="srcSentence"> External email addresses for groups are not currently supported.</caps:sentence>
                </para>
              </alert>
              <para>
                <caps:sentence id="src270" class="srcSentence">Templates that you import from AD RMS look and behave just like custom templates that you can create in the Azure classic portal.</caps:sentence>
                <caps:sentence id="src271" class="srcSentence"> To change imported templates to be published so that users can see them and select them from applications, or to make other changes to the templates, see <link xlink:href="1775d8d0-9a59-42c8-914f-ce285b71ac1c">Configuring Custom Templates for Azure Rights Management</link>.</caps:sentence>
              </para>
              <alert class="tip">
                <para>
                  <caps:sentence id="src272" class="srcSentence">For a more consistent experience for users during the migration process, do not make changes to the imported templates other than these two changes; and do not publish the two default templates that come with Azure RMS, or create new templates at this time.</caps:sentence>
                  <caps:sentence id="src273" class="srcSentence"> Instead, wait until the migration process is complete and you have decommissioned the AD RMS servers.</caps:sentence>
                </para>
              </alert>
            </content>
            <sections>
              <section expanded="false" address="BKMK_ScriptForANYONE">
                <title>
                  <caps:sentence id="src274" class="srcSentence">Sample Windows PowerShell script to identify AD RMS templates that include the ANYONE group</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence id="src275" class="srcSentence">This section contains the sample script to help you identify AD RMS templates that have the ANYONE group defined, as described in the preceding section.</caps:sentence>
                  </para>
                  <para>
                    <legacyItalic>
                      <caps:sentence id="src276" class="srcSentence">
                        <embeddedLabel>Disclaimer:</embeddedLabel> This sample script is not supported under any Microsoft standard support program or service.</caps:sentence>
                      <caps:sentence id="src277" class="srcSentence"> This sample script is provided AS IS without warranty of any kind.</caps:sentence>
                    </legacyItalic>
                  </para>
                  <code>import-module adrmsadmin New-PSDrive -Name MyRmsAdmin -PsProvider AdRmsAdmin -Root https://localhost -Force $ListofTemplates=dir MyRmsAdmin:\RightsPolicyTemplate foreach($Template in $ListofTemplates) { $templateID=$Template.id $rights = dir MyRmsAdmin:\RightsPolicyTemplate\$Templateid\userright $templateName=$Template.DefaultDisplayName if ($rights.usergroupname -eq "anyone") { $templateName = $Template.defaultdisplayname write-host "Template " -NoNewline write-host -NoNewline $templateName -ForegroundColor Red write-host " contains rights for " -NoNewline write-host ANYONE  -ForegroundColor Red } } Remove-PSDrive MyRmsAdmin -force
</code>
                </content>
              </section>
            </sections>
          </section>
          <section address="BKMK_Step5Migration">
            <title>
              <caps:sentence id="src278" class="srcSentence">Step 5.</caps:sentence>
              <caps:sentence id="src279" class="srcSentence"> Reconfigure clients to use Azure RMS</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src280" class="srcSentence">For Windows clients:</caps:sentence>
              </para>
              <list class="ordered">
                <listItem>
                  <para>
                    <caps:sentence id="src281" class="srcSentence">
                      <externalLink>
                        <linkText>Download the migration scripts</linkText>
                        <linkUri>http://go.microsoft.com/fwlink/?LinkId=524619</linkUri>
                      </externalLink>: </caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src282" class="srcSentence">CleanUpRMS_RUN_Elevated.cmd</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src283" class="srcSentence">Redirect_OnPrem.cmd</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <para>
                    <caps:sentence id="src284" class="srcSentence">These scripts reset the configuration on Windows computers so that they will use the Azure RMS service rather than AD RMS.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src285" class="srcSentence">Follow the instructions in the redirection script (Redirect_OnPrem.cmd) to modify the script to point to your new Azure RMS tenant.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src286" class="srcSentence">On the Windows computers, run these scripts with elevated privileges in the user’s context.</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence id="src287" class="srcSentence">For mobile device clients and Mac computers:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src288" class="srcSentence">Remove the DNS SRV records that you created when you deployed the <externalLink><linkText>AD RMS mobile device extension</linkText><linkUri>http://technet.microsoft.com/library/dn673574.aspx</linkUri></externalLink>.</caps:sentence>
                  </para>
                </listItem>
              </list>
            </content>
            <sections>
              <section expanded="false">
                <title>
                  <caps:sentence id="src289" class="srcSentence">Changes made by the migration scripts</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence id="src290" class="srcSentence">This section documents the changes that the migration scripts make.</caps:sentence>
                    <caps:sentence id="src291" class="srcSentence"> You can use this information for reference purposes only, or for troubleshooting, or if you prefer to make these changes yourself.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src292" class="srcSentence">CleanUpRMS_RUN_Elevated.cmd:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src293" class="srcSentence">Delete the contents of the %userprofile%\AppData\Local\Microsoft\DRM and %userprofile%\AppData\Local\Microsoft\MSIPC folders, including any subfolders and any files with long file names.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src294" class="srcSentence">Delete the contents of the following registry keys:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src295" class="srcSentence">HKEY_LOCAL_MACHINE\Software\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src296" class="srcSentence">HKEY_CURRENT_USER\Software\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src297" class="srcSentence">HKEY_LOCAL_MACHINE\Software\WoW6432Node\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src298" class="srcSentence">HKEY_CURRENT_USER\Software\WoW6432Node\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src299" class="srcSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src300" class="srcSentence">HKEY_LOCAL_MACHINE\SOFTWARE\WoW6432Node\Microsoft\MSIPC\ServiceLocation</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src301" class="srcSentence">HKEY_LOCAL_MACHINE\Software\Microsoft\MSDRM\ServiceLocation</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src302" class="srcSentence">Delete the following registry values:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src303" class="srcSentence">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\DRM\DefaultServerURL</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src304" class="srcSentence">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\DRM\DefaultServer</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </listItem>
                  </list>
                  <para>
                    <caps:sentence id="src305" class="srcSentence">Redirect_OnPrem.cmd:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src306" class="srcSentence">Create the following registry values for each URL supplied as a parameter under each of the following locations:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src307" class="srcSentence">HKEY_CURRENT_USER\Software\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM\LicenseServerRedirection</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src308" class="srcSentence">HKEY_CURRENT_USER\Software\WoW6432Node\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM\LicenseServerRedirection</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src309" class="srcSentence">HKEY_LOCAL_MACHINE\Software\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM\LicenseServerRedirection</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src310" class="srcSentence">HKEY_LOCAL_MACHINE\Software\WoW6432Node\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM\LicenseServerRedirection</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src311" class="srcSentence">HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC\LicensingRedirection</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence id="src312" class="srcSentence">Each entry has a REG_SZ value of <ui>https://OldRMSserverURL/_wmcs/licensing</ui> with the data in the following format: <ui>https://&lt;YourTenantURL&gt;/_wmcs/licensing</ui>.</caps:sentence>
                      </para>
                      <alert class="note">
                        <para>
                          <caps:sentence id="src313" class="srcSentence">
                            <placeholder>&lt;YourTenantURL&gt;</placeholder> has the following format: <ui>{GUID}.rms.[Region].aadrm.com</ui>.</caps:sentence>
                        </para>
                        <para>
                          <caps:sentence id="src314" class="srcSentence">For example:  5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com</caps:sentence>
                        </para>
                        <para>
                          <caps:sentence id="src315" class="srcSentence">You can find this value by identifying the <ui>RightsManagementServiceId</ui> value when you run the <externalLink><linkText>Get-AadrmConfiguration</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629410.aspx</linkUri></externalLink> cmdlet for Azure RMS.</caps:sentence>
                        </para>
                      </alert>
                    </listItem>
                  </list>
                </content>
              </section>
            </sections>
          </section>
          <section address="BKMK_Step6Migration">
            <title>
              <caps:sentence id="src316" class="srcSentence">Step 6.</caps:sentence>
              <caps:sentence id="src317" class="srcSentence"> Configure IRM integration for Exchange Online</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src318" class="srcSentence">If you have previously imported your TDP from AD RMS to Exchange Online, you must remove this TDP to avoid conflicting templates and policies after you have migrated to Azure RMS.</caps:sentence>
                <caps:sentence id="src319" class="srcSentence"> To do this, use the <externalLink><linkText>Remove-RMSTrustedPublishingDomain</linkText><linkUri>https://technet.microsoft.com/en-us/library/jj200720(v=exchg.150).aspx</linkUri></externalLink> cmdlet from Exchange Online.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src320" class="srcSentence">If you chose an Azure RMS tenant key topology of <embeddedLabel>Microsoft managed</embeddedLabel>:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src321" class="srcSentence">See the <link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36#BKMK_ExchangeOnline">Exchange Online: IRM Configuration</link> section in the <link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36">Configuring Applications for Azure Rights Management</link> topic.</caps:sentence>
                    <caps:sentence id="src322" class="srcSentence"> This section includes typical commands to run that connects to the Exchange Online service, imports the tenant key from Azure RMS,  and enables IRM functionality for Exchange Online.</caps:sentence>
                    <caps:sentence id="src323" class="srcSentence"> After you complete these steps, you will have full RMS functionality with Exchange Online.</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence id="src324" class="srcSentence">If you chose an Azure RMS tenant key topology of <embeddedLabel>customer-managed (BYOK)</embeddedLabel>:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src325" class="srcSentence"> You will  have reduced RMS functionality with Exchange Online, as described in the <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_Pricing">BYOK pricing and restrictions</link> section in the <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and Implementing Your Azure Rights Management Tenant Key</link> topic.</caps:sentence>
                  </para>
                </listItem>
              </list>
            </content>
          </section>
          <section address="BKMK_Step7Migration">
            <title>
              <caps:sentence id="src326" class="srcSentence">Step 7.</caps:sentence>
              <caps:sentence id="src327" class="srcSentence"> Deploy the RMS connector</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src328" class="srcSentence">If you have used the Information Rights Management (IRM) functionality of Exchange Server or SharePoint Server with AD RMS, you must first disable IRM on these servers and remove AD RMS configuration.</caps:sentence>
                <caps:sentence id="src329" class="srcSentence"> Then, deploy the Rights Management (RMS) connector, which acts as a communications interface (a relay) between the on-premises servers and Azure RMS.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src330" class="srcSentence">Finally for this step, if you have imported multiple TPDs into Azure RMS that were used to protect email messages, you must manually edit the registry on the Exchange Server computers to redirect all TPDs URLs to the RMS connector.</caps:sentence>
              </para>
              <alert class="note">
                <para>
                  <caps:sentence id="src331" class="srcSentence">Before you start, check the supported versions of the on-premises servers that the RMS connector supports in “On-premises servers that support Azure RMS” in the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedApplications">Applications that support Azure RMS</link> section of the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link> topic.</caps:sentence>
                </para>
              </alert>
              <procedure>
                <title>
                  <caps:sentence id="src332" class="srcSentence">Disable IRM on Exchange Servers and remove AD RMS configuration</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src333" class="srcSentence">On each Exchange server, locate the following folder and delete all the entries in that folder: \ProgramData\Microsoft\DRM\Server\S-1-5-18</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src334" class="srcSentence">From one of the Exchange servers, use the Exchange <externalLink><linkText>Set_IRMConfiguration</linkText><linkUri>http://technet.microsoft.com/library/dd979792.aspx</linkUri></externalLink> cmdlet to first disable IRM features for messages that are sent to internal recipients: </caps:sentence>
                      </para>
                      <code>Set-IRMConfiguration -InternalLicensingEnabled $false</code>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src335" class="srcSentence">Then use the same cmdlet to disable IRM features for messages that are sent to external recipients:</caps:sentence>
                      </para>
                      <code>Set-IRMConfiguration -ExternalLicensingEnabled $false</code>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src336" class="srcSentence">Next, use the same cmdlet to disable IRM in Microsoft Office Outlook Web App and in Microsoft Exchange ActiveSync:</caps:sentence>
                      </para>
                      <code>Set-IRMConfiguration -ClientAccessServerEnabled $false</code>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src337" class="srcSentence">Finally, use the same cmdlet to clear any cached certificates:</caps:sentence>
                      </para>
                      <code>Set-IRMConfiguration -RefreshServerCertificates</code>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src338" class="srcSentence">On each Exchange Server, now reset IIS, for example, by running a command prompt as an administrator and typing <userInput>iisreset</userInput>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
              <procedure>
                <title>
                  <caps:sentence id="src339" class="srcSentence">Disable IRM on SharePoint Servers and remove AD RMS configuration</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src340" class="srcSentence">Make sure that there are no documents checked out from RMS-protected libraries.</caps:sentence>
                        <caps:sentence id="src341" class="srcSentence"> If there are, they will be become inaccessible at the end of this procedure.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src342" class="srcSentence">On the SharePoint Central Administration Web site, in the <ui>Quick Launch</ui> section, click <ui>Security</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src343" class="srcSentence">On the <ui>Security</ui> page, in the <ui>Information Policy</ui> section, click <ui>Configure information rights management</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src344" class="srcSentence">On the <ui>Information Rights Management</ui> page, in the <ui>Information Rights Management</ui> section, select <ui>Do not use IRM on this server</ui>, then click <ui>OK</ui>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src345" class="srcSentence">On each of the SharePoint Server computers, delete the contents of the folder \ProgramData\Microsoft\MSIPC\Server\<placeholder>&lt;SID of the account running SharePoint Server&gt;</placeholder>.</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
              <procedure>
                <title>
                  <caps:sentence id="src346" class="srcSentence">Install and configure the RMS connector</caps:sentence>
                </title>
                <steps class="bullet">
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src347" class="srcSentence">Use the instructions in the <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066">Deploying the Azure Rights Management Connector</link> topic.</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
              <procedure>
                <title>
                  <caps:sentence id="src348" class="srcSentence">For Exchange only and multiple TPDs: Edit the registry</caps:sentence>
                </title>
                <steps class="bullet">
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src349" class="srcSentence">On each Exchange Server, manually add the following registry keys for each additional TPD that you imported, to redirect the TPD URLs to the RMS connector.</caps:sentence>
                        <caps:sentence id="src350" class="srcSentence"> These registry entries are specific to migration and are not added by the server configuration tool for Microsoft RMS connector.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src351" class="srcSentence">When you make these registry edits, use the following instructions:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src352" class="srcSentence">Replace <placeholder>ConnectorFQDN</placeholder> with the name that you defined in DNS for the connector.</caps:sentence>
                            <caps:sentence id="src353" class="srcSentence"> For example, <ui>rmsconnector.contoso.com</ui>.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src354" class="srcSentence">Use the HTTP or HTTPS prefix for the connector URL, depending on whether you have configured the connector to use HTTP or HTTPS to communicate with your on-premises servers.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para> </para>
                      <para>
                        <embeddedLabel>
                          <caps:sentence id="src355" class="srcSentence">For Exchange 2013:</caps:sentence>
                        </embeddedLabel>
                      </para>
                      <table>
                        <thead>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence id="src356" class="srcSentence">Registry path</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src357" class="srcSentence">Type</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src358" class="srcSentence">Value</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src359" class="srcSentence">Data</caps:sentence>
                              </para>
                            </TD>
                          </tr>
                        </thead>
                        <tbody>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence id="src360" class="srcSentence">HKLM\SOFTWARE\Microsoft\ExchangeServer\v15\IRM\LicenseServerRedirection</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src361" class="srcSentence">Reg_SZ</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src362" class="srcSentence">https://&lt;AD RMS Intranet Licensing URL&gt;/_wmcs/licensing</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src363" class="srcSentence">One of the following, depending on whether you are using HTTP or HTTPS from your Exchange server to the RMS connector:</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence id="src364" class="srcSentence">http://&lt;connectorFQDN&gt;/_wmcs/licensing</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence id="src365" class="srcSentence">https://&lt;connectorName&gt;/_wmcs/licensing</caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                            </TD>
                          </tr>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence id="src366" class="srcSentence">HKLM\SOFTWARE\Microsoft\ExchangeServer\v15\IRM\LicenseServerRedirection </caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src367" class="srcSentence">Reg_SZ</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src368" class="srcSentence">https://&lt;AD RMS Extranet Licensing URL&gt;/_wmcs/licensing</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src369" class="srcSentence">One of the following, depending on whether you are using HTTP or HTTPS from your Exchange server to the RMS connector:</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence id="src370" class="srcSentence">http://&lt;connectorFQDN&gt;/_wmcs/licensing</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence id="src371" class="srcSentence">https://&lt;connectorFQDN&gt;/_wmcs/licensing</caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                            </TD>
                          </tr>
                        </tbody>
                      </table>
                      <para>
                        <embeddedLabel>
                          <caps:sentence id="src372" class="srcSentence">For Exchange Server 2010:</caps:sentence>
                        </embeddedLabel>
                      </para>
                      <table>
                        <thead>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence id="src373" class="srcSentence">Registry path</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src374" class="srcSentence">Type</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src375" class="srcSentence">Value</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src376" class="srcSentence">Data</caps:sentence>
                              </para>
                            </TD>
                          </tr>
                        </thead>
                        <tbody>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence id="src377" class="srcSentence">HKLM\SOFTWARE\Microsoft\ExchangeServer\v14\IRM\LicenseServerRedirection</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src378" class="srcSentence">Reg_SZ</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src379" class="srcSentence">https://&lt;AD RMS Intranet Licensing URL&gt;/_wmcs/licensing</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src380" class="srcSentence">One of the following, depending on whether you are using HTTP or HTTPS from your Exchange server to the RMS connector:</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence id="src381" class="srcSentence">http://&lt;connectorName&gt;/_wmcs/licensing</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence id="src382" class="srcSentence">https://&lt;connectorName&gt;/_wmcs/licensing</caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                            </TD>
                          </tr>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence id="src383" class="srcSentence">HKLM\SOFTWARE\Microsoft\ExchangeServer\v14\IRM\LicenseServerRedirection </caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src384" class="srcSentence">Reg_SZ</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src385" class="srcSentence">https://&lt;AD RMS Extranet Licensing URL&gt;/_wmcs/licensing</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src386" class="srcSentence">One of the following, depending on whether you are using HTTP or HTTPS from your Exchange server to the RMS connector:</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence id="src387" class="srcSentence">http://&lt;connectorName&gt;/_wmcs/licensing</caps:sentence>
                                  </para>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence id="src388" class="srcSentence">https://&lt;connectorName&gt;/_wmcs/licensing</caps:sentence>
                                  </para>
                                </listItem>
                              </list>
                            </TD>
                          </tr>
                        </tbody>
                      </table>
                    </content>
                  </step>
                </steps>
              </procedure>
              <para>
                <caps:sentence id="src389" class="srcSentence">After you have completed these procedures, be sure to read the <embeddedLabel>Next steps</embeddedLabel> section in the <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066">Deploying the Azure Rights Management Connector</link> topic.</caps:sentence>
              </para>
            </content>
          </section>
          <section address="BKMK_Step8Migration">
            <title>
              <caps:sentence id="src390" class="srcSentence">Step 8.</caps:sentence>
              <caps:sentence id="src391" class="srcSentence"> Decommission AD RMS</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src392" class="srcSentence">Optional: Remove the Service Connection Point (SCP) from Active Directory to prevent computers from discovering your on-premises Rights Management infrastructure.</caps:sentence>
                <caps:sentence id="src393" class="srcSentence"> This is optional because of the redirection that you configured in the registry (for example, by running the migration script).</caps:sentence>
                <caps:sentence id="src394" class="srcSentence"> To remove the Service Connection Point, use the AD SCP Register tool from the <externalLink><linkText>Rights Management Services Administration Toolkit</linkText><linkUri>http://www.microsoft.com/download/details.aspx?id=1479</linkUri></externalLink>.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src395" class="srcSentence">Monitor your AD RMS servers for activity, for example, by checking the <externalLink><linkText>requests in the System Health report</linkText><linkUri>https://technet.microsoft.com/library/ee221012(v=ws.10).aspx</linkUri></externalLink>, the <externalLink><linkText>ServiceRequest table</linkText><linkUri>http://technet.microsoft.com/library/dd772686(v=ws.10).aspx</linkUri></externalLink> or <externalLink><linkText>auditing of user access to protected content</linkText><linkUri>http://social.technet.microsoft.com/wiki/contents/articles/3440.ad-rms-frequently-asked-questions-faq.aspx</linkUri></externalLink>.</caps:sentence>
                <caps:sentence id="src396" class="srcSentence"> When you have confirmed that RMS clients are no longer communicating with these servers and that clients are successfully using Azure RMS, you can remove the AD RMS server role from these server.</caps:sentence>
                <caps:sentence id="src397" class="srcSentence"> If you’re using dedicated servers, you might prefer the cautionary step of first shutting down the servers for a period of time to make sure that there are no reported problems that might require restarting these servers to ensure service continuity while you investigate why clients are not using Azure RMS.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src398" class="srcSentence">After decommissioning your AD RMS servers, you might want to take the opportunity to review your templates in the Azure classic portal and consolidate them so that users have fewer to choose between, or reconfigure them, or even add new templates.</caps:sentence>
                <caps:sentence id="src399" class="srcSentence"> This would be also a good time to publish the default templates.</caps:sentence>
                <caps:sentence id="src400" class="srcSentence"> For more information, see <link xlink:href="1775d8d0-9a59-42c8-914f-ce285b71ac1c">Configuring Custom Templates for Azure Rights Management</link>.</caps:sentence>
              </para>
            </content>
          </section>
          <section address="BKMK_Step9Migration">
            <title>
              <caps:sentence id="src401" class="srcSentence">Step 9.</caps:sentence>
              <caps:sentence id="src402" class="srcSentence"> Re-key your Azure RMS tenant key</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src403" class="srcSentence">This step is required when migration is complete if your AD RMS deployment was using RMS Cryptographic Mode 1, because re-keying creates a new tenant key that uses RMS Cryptographic Mode 2.</caps:sentence>
                <caps:sentence id="src404" class="srcSentence"> Using Azure RMS with Cryptographic Mode 1 is supported only during the migration process.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src405" class="srcSentence">This step is optional but recommended when migration is complete even if you were running in RMS Cryptographic Mode 2, because it helps to secure your Azure RMS tenant key from potential security breaches to your AD RMS key.</caps:sentence>
                <caps:sentence id="src406" class="srcSentence"> When you re-key your Azure RMS tenant key (also known as “rolling your key”), a new key is created and the original key is archived.</caps:sentence>
                <caps:sentence id="src407" class="srcSentence"> However, because moving from one key to another doesn’t happen immediately but over a few weeks, do not wait until you suspect a breach to your original key but re-key your RMS tenant key as soon as the migration is complete.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src408" class="srcSentence">To re-key your Azure RMS tenant key:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src409" class="srcSentence">If your RMS tenant key is managed by Microsoft: Call Microsoft Customer Support Services (CSS) and prove that you are the RMS tenant administrator.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src410" class="srcSentence">If your RMS tenant key is managed by you (BYOK): Repeat the BYOK procedure to generate and create a new key over the Internet or in person.</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence id="src411" class="srcSentence">For more information about managing your RMS tenant key, see <link xlink:href="1284d0ee-0a72-45ba-a64c-3dcb25846c3d">Operations for Your Azure Rights Management Tenant Key</link>.</caps:sentence>
              </para>
            </content>
          </section>
        </sections>
      </section>
      <relatedTopics>
        <link xlink:href="206a0bfe-0912-4e0e-aa15-484b000b264c">Configuring Azure Rights Management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSSource>
</caps:SxS>