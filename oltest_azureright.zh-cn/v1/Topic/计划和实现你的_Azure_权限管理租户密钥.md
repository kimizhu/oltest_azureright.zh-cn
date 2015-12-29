---
description: na
keywords: na
pagetitle: 计划和实现你的 Azure 权限管理租户密钥
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14
---
# 计划和实现你的 Azure 权限管理租户密钥
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="zh-CN">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="798725df8246833c5490c3ff9d755434" id="tgt1" class="tgtSentence">使用本主题中的信息可帮助你计划和管理 Azure RMS 的权限管理服务 (RMS) 租户密钥。</caps:sentence>
          <caps:sentence sentenceid="5290d270be87068b274ec471c3cbe083" id="tgt2" class="tgtSentence"> 例如，为了遵守组织的具体规定，你不能让 Microsoft 管理你的租户密钥（默认设置），而想要自行管理租户密钥。</caps:sentence>
          <caps:sentence sentenceid="07e873f6318eac1e5dda1a9742f76c3e" id="tgt3" class="tgtSentence">  自行管理租户密钥也称为自带密钥 (BYOK)。</caps:sentence>
        </para>
        <alert class="note">
          <para>
            <caps:sentence sentenceid="fae1bbf20fa62bb2b66522dea89dfe16" id="tgt4" class="tgtSentence">RMS 租户密钥也称为服务器许可方证书 (SLC) 密钥。</caps:sentence>
            <caps:sentence sentenceid="2223ade043efd5512c8bbbdc0e28c062" id="tgt5" class="tgtSentence"> Azure RMS 为订阅 Azure RMS 的每个组织维护一个或多个密钥。</caps:sentence>
            <caps:sentence sentenceid="20b477a91edd7155148becc33aa1104e" id="tgt6" class="tgtSentence"> 只要将密钥用于组织内部的 RMS（例如用户密钥、计算机密钥、文档加密密钥），它们将通过加密方式链接到你的 RMS 租户密钥。</caps:sentence>
          </para>
        </alert>
        <para>
          <caps:sentence sentenceid="f78893ad696e82a2f26a44de86d0efef" id="tgt7" class="tgtSentence">
            <embeddedLabel>概览：</embeddedLabel>参考下表来快速了解建议的租户密钥拓扑。</caps:sentence>
          <caps:sentence sentenceid="c41f3336db11dc4d8143b71a8886bb98" id="tgt8" class="tgtSentence"> 然后，参考其他部分来了解详细信息。</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="46dd27038659a6515b4fdeab1523b264" id="tgt9" class="tgtSentence">如果你使用 Microsoft 管理的租户密钥部署 Azure RMS，则你以后可以改为使用 BYOK。</caps:sentence>
          <caps:sentence sentenceid="0bc29371288b5bab6bc90f1a0a2de0dd" id="tgt10" class="tgtSentence"> 但是，目前你无法将 Azure RMS 租户密钥从 BYOK 改为由 Microsoft 管理。</caps:sentence>
        </para>
        <table>
          <tbody>
            <tr>
              <TH>
                <para>
                  <caps:sentence sentenceid="3297dc52043781143271569d7aeb0ce8" id="tgt11" class="tgtSentence">业务要求</caps:sentence>
                </para>
              </TH>
              <TH>
                <para>
                  <caps:sentence sentenceid="2b3bed08b42fc58def3af7bee70ffe63" id="tgt12" class="tgtSentence">建议的租户密钥拓扑</caps:sentence>
                </para>
              </TH>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="8814def9c82fc9056095f2a9b4ddc1e8" id="tgt13" class="tgtSentence">快速部署 Azure RMS，而无需特殊硬件</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="874e6f5cb5666e172ff4d4d74a9158b1" id="tgt14" class="tgtSentence">由 Microsoft 管理</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="d86c86c29dc0333ffd2e3ea70b8bc93f" id="tgt15" class="tgtSentence">需要装有 Azure RMS 的 Exchange Online 中的完整 IRM 功能</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="874e6f5cb5666e172ff4d4d74a9158b1" id="tgt16" class="tgtSentence">由 Microsoft 管理</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="57dca6265b824f1ce4c0ea80a8a36549" id="tgt17" class="tgtSentence">你的密钥由你自己创建，并在硬件安全模块 (HSM) 中受保护</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="f4d73285894a12147099e15d0c53e19e" id="tgt18" class="tgtSentence">BYOK</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="63eeafe3a2029cbcdece7c02e27ebed3" id="tgt19" class="tgtSentence">目前，此配置将导致 Exchange Online 中的 IRM 功能降低。</caps:sentence>
                  <caps:sentence sentenceid="be021ab36c2c99a549fc25f5fcee238c" id="tgt20" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_Pricing">BYOK pricing and restrictions</link>部分。</caps:sentence>
                </para>
              </TD>
            </tr>
          </tbody>
        </table>
        <para>
          <caps:sentence sentenceid="252fbfcb6978ae2270ea941e70a082e3" id="tgt21" class="tgtSentence">使用以下部分可帮助你选择要使用的租户密钥拓扑，了解租户密钥生命周期和实现自带密钥 (BYOK) 的方式，以及要采取的后续步骤：</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_ChooseTenantKey">Choose your tenant key topology: Managed by Microsoft (the default) or managed by you (BYOK)</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_Pricing">BYOK pricing and restrictions</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_ImplementBYOK">Implementing bring your own key (BYOK)</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_NextSteps">Next steps</link>
            </para>
          </listItem>
        </list>
      </introduction>
      <section address="BKMK_ChooseTenantKey">
        <title>
          <caps:sentence sentenceid="5390992fd79b5a87a6ce8c72213c8fa5" id="tgt22" class="tgtSentence">选择你的租户密钥拓扑：由 Microsoft 管理（默认设置）或由你管理 (BYOK)</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="9bd0bc0662633a437dcc15a7546cd84d" id="tgt23" class="tgtSentence">确定哪种租户密钥拓扑最适合你的组织。</caps:sentence>
            <caps:sentence sentenceid="fa404d9137b3bc8e968083a80a51587e" id="tgt24" class="tgtSentence"> 默认情况下，Azure RMS 生成你的租户密钥，并管理租户密钥生命周期的大多数方面。</caps:sentence>
            <caps:sentence sentenceid="ba9cf4793f7912c52b3905657550e44e" id="tgt25" class="tgtSentence"> 这是最简单的选项，管理开销最低。</caps:sentence>
            <caps:sentence sentenceid="91968b3b8d2f3431421d3b1bab6e2530" id="tgt26" class="tgtSentence"> 大多数情况下，你甚至不需要知道自己有租户密钥。</caps:sentence>
            <caps:sentence sentenceid="39a9fd6c2cc065b5e9d25c3b29bea097" id="tgt27" class="tgtSentence"> 你只需注册 Azure RMS，密钥管理过程的剩余部分将由 Microsoft 处理。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="e1df4a55b66ee82e46354d03c3cbb01a" id="tgt28" class="tgtSentence">或者，你可能希望完全控制自己的租户密钥，这就需要创建你的租户密钥，并将主副本保存在本地。</caps:sentence>
            <caps:sentence sentenceid="55dda572509896a3b9ecc0a1ba4ca8d8" id="tgt29" class="tgtSentence"> 这种方案通常称为自带密钥 (BYOK)。</caps:sentence>
            <caps:sentence sentenceid="9c08e42f584d337b05110ea51991a9f9" id="tgt30" class="tgtSentence"> 使用这种选项的过程如下：</caps:sentence>
          </para>
          <list class="ordered">
            <listItem>
              <para>
                <caps:sentence sentenceid="708508bcb952e70b9dbecf4506d2576b" id="tgt31" class="tgtSentence">你根据 IT 策略在本地生成租户密钥。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="0d3179f372731791f8cb2d60b7bf39ee" id="tgt32" class="tgtSentence">你将租户密钥从自己掌握的硬件安全模块 (HSM) 安全传送到由 Microsoft 拥有和管理的 HSM。</caps:sentence>
                <caps:sentence sentenceid="f65825397b9c9801c0230374e9df5bfd" id="tgt33" class="tgtSentence"> 整个过程中，你的租户密钥从未离开硬件保护范围。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="1425e92a1b4f095df7fbbf40fd5b9365" id="tgt34" class="tgtSentence">当你将租户密钥传送到 Microsoft 时，它始终处于 Thales HSM 保护下。</caps:sentence>
                <caps:sentence sentenceid="2553d096b1bfbf123247aa19c22eea91" id="tgt35" class="tgtSentence"> Microsoft 与 Thales 进行了合作，确保你的租户密钥无法从 Microsoft 的 HSM 提取。</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="3c522548f78e4ab2b86b626af9ab2368" id="tgt36" class="tgtSentence">虽然这是可选的，但你可能希望使用 Azure RMS 提供的接近实时的使用日志，以便准确了解你的租户密钥的使用时间和方式。</caps:sentence>
          </para>
          <alert class="note">
            <para>
              <caps:sentence sentenceid="589525cae034c66bdbec169bd31c3f3a" id="tgt37" class="tgtSentence">作为一种附加保护措施，Azure RMS 在位于北美、EMEA 地区（欧洲、中东和非州）和亚洲的数据中心使用单独的安全体系。</caps:sentence>
              <caps:sentence sentenceid="67ac3de5474f663d62ace1386431ae58" id="tgt38" class="tgtSentence"> 当你管理自己的租户密钥时，它将关联到你的 RMS 租户注册所在地区的安全体系。</caps:sentence>
              <caps:sentence sentenceid="77922f4f821da35333a019fa6d4032d9" id="tgt39" class="tgtSentence"> 例如，欧洲客户的租户密钥无法在北美或亚洲的数据中心使用。</caps:sentence>
            </para>
          </alert>
        </content>
      </section>
      <section address="BKMK_OverviewLifecycle">
        <title>
          <caps:sentence sentenceid="fbbb664a9d39c2ba627484cab2f98cd9" id="tgt40" class="tgtSentence">租户密钥生命周期</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="d9ab7c3838cf8e65633957dfe45164c6" id="tgt41" class="tgtSentence">如果你决定由 Microsoft 管理你的租户密钥，Microsoft 将处理大多数密钥生命周期操作。</caps:sentence>
            <caps:sentence sentenceid="bd7fb9ffacbcd3da5d91ded2f02adbd6" id="tgt42" class="tgtSentence"> 但是，如果你决定自行管理租户密钥，则要负责很多密钥生命周期操作，以及其他一些过程。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="e09407dac8c9111cd8badb983cb08d8a" id="tgt43" class="tgtSentence">下图显示和比较了这两个选项。</caps:sentence>
            <caps:sentence sentenceid="010d9ec47c95ff4b0e4b3bb443deaeb2" id="tgt44" class="tgtSentence"> 第一张图显示在由 Microsoft 管理租户密钥的默认配置中，管理员开销非常低。</caps:sentence>
          </para>
          <mediaLink>
            <caption>
              <caps:sentence sentenceid="7cace59d6a583f0ebffb677f8614234e" id="tgt45" class="tgtSentence">由 Microsoft 管理租户密钥</caps:sentence>
            </caption>
            <image xlink:href="66905ef5-1ba4-4c93-9513-c6d7a9173453"></image>
          </mediaLink>
          <para></para>
          <para>
            <caps:sentence sentenceid="52ea43745d984083964888551137c252" id="tgt46" class="tgtSentence">第二张图显示当你自行管理租户密钥时需要的其他步骤。</caps:sentence>
          </para>
          <mediaLink>
            <caption>
              <caps:sentence sentenceid="a3b583394ffe0cd82110414f925b3079" id="tgt47" class="tgtSentence">自行管理租户密钥 (BYOK)</caps:sentence>
            </caption>
            <image xlink:href="ec00ba88-ad16-4426-81e3-d5d074ce0c31"></image>
          </mediaLink>
          <para></para>
          <para>
            <caps:sentence sentenceid="6631a977fb4b90cf31897e9b80b6f685" id="tgt48" class="tgtSentence">如果你决定让 Microsoft 管理你的租户密钥，则除了生成密钥之外，再无需任何额外操作，你可以跳过以下部分，直接执行<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_NextSteps">Next steps</link>。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="4545640189381acaadc7212544535370" id="tgt49" class="tgtSentence">如果你决定自行管理租户密钥，请阅读以下部分以获取更多信息。</caps:sentence>
          </para>
        </content>
        <sections>
          <section expanded="false">
            <title>
              <caps:sentence sentenceid="330e3ba5e392345936394defcae419cc" id="tgt50" class="tgtSentence">有关 Thales HSM 和 Microsoft 添加件的详细信息</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="50468b0ec4dc4a45f712be38f6740bf0" id="tgt51" class="tgtSentence">Azure RMS 使用 Thales HSM 来保护你的密钥。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="bd35151199ff09403c25a1ce04b28f52" id="tgt52" class="tgtSentence">Thales e-Security 是一家全球领先的数据加密和网络安全解决方案提供商，面向金融服务、高科技、制造、政府机构和技术行业。</caps:sentence>
                <caps:sentence sentenceid="551fde8a2489dbebb9b39a98f1b0c39a" id="tgt53" class="tgtSentence"> Thales 解决方案在保护企业和政府信息方面拥有 40 年的悠久历史，在五分之四的大型能源和航天公司以及 22 个 NATO 国家/地区得以使用，为全球 80% 以上的支付交易提供安全保护。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="49c8ff1bc944f72940fd3b490a8a5055" id="tgt54" class="tgtSentence">Microsoft 与 Thales 联手协作，不断增强这些 HSM 的功能。</caps:sentence>
                <caps:sentence sentenceid="bd23408902a1862cf98740aa1df99f9f" id="tgt55" class="tgtSentence"> 通过这些增强功能，你可以享受托管服务的典型优势，而无需放弃对密钥的控制。</caps:sentence>
                <caps:sentence sentenceid="8d699a8a9de3e5f70a8775238ecacb2a" id="tgt56" class="tgtSentence"> 具体来说，这些增强功能让 Microsoft 管理 HSM，因此你无需进行管理。</caps:sentence>
                <caps:sentence sentenceid="02fae9287297ec99b49f5ef027395f75" id="tgt57" class="tgtSentence"> 作为一种云服务，Azure RMS 可在短时间内扩展，以满足你组织的使用高峰需求。</caps:sentence>
                <caps:sentence sentenceid="f08caa478248b70bc640918198fbcc6e" id="tgt58" class="tgtSentence"> 同时，你的密钥在 Microsoft 的 HSM 内部得到保护：你可以保持对密钥生命周期的控制，因为你将生成密钥并将其传送到 Microsoft 的 HSM。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="d1aee644e17abda9397214172b7615de" id="tgt59" class="tgtSentence">有关详细信息，请参阅 Thales 网站上的 <externalLink><linkText>Thales HSM 和 Azure RMS</linkText><linkUri>http://www.thales-esecurity.com/msrms/cloud</linkUri></externalLink>。</caps:sentence>
              </para>
            </content>
          </section>
        </sections>
      </section>
      <section address="BKMK_Pricing">
        <title>
          <caps:sentence sentenceid="f17fa7a6c90411e52a8697700bce67e1" id="tgt60" class="tgtSentence">BYOK 定价和限制</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="5a6af29ace38b4ba386fa7c7b630bdc3" id="tgt61" class="tgtSentence">具有 IT 托管的 Azure 订阅的组织可以使用 BYOK 并记录其使用情况，而无需额外付费。</caps:sentence>
            <caps:sentence sentenceid="22ebedd1d47855fd2ca9304885662eca" id="tgt62" class="tgtSentence"> 使用个人 RMS 的组织无法使用 BYOK 和日志记录，因为他们没有租户管理员来配置这些功能。</caps:sentence>
          </para>
          <alert class="note">
            <para>
              <caps:sentence sentenceid="2c68cac55d3d19f5ed96e3e819906777" id="tgt63" class="tgtSentence">有关个人 RMS 的详细信息，请参阅<link xlink:href="2efcb440-fefd-45e9-872b-f471573aadf2">RMS for Individuals and Azure Rights Management</link>。</caps:sentence>
            </para>
          </alert>
          <mediaLink>
            <image xlink:href="6417311a-9193-4c6e-a284-ac92b335ea80"></image>
          </mediaLink>
          <para></para>
          <para>
            <caps:sentence sentenceid="ac478ac98607346a4d2296751fb40c2e" id="tgt64" class="tgtSentence">BYOK 和日志记录可以无缝应用程序于任何与 Azure RMS 集成的应用程序。</caps:sentence>
            <caps:sentence sentenceid="f5824487b2da197b951cca2f7dbb4e81" id="tgt65" class="tgtSentence"> 其中包括 SharePoint Online 等云服务、运行 Exchange 和 SharePoint 的本地服务器（它们通过使用 RMS 连接器来运行 Azure RMS）、Office 2013 等客户端应用程序。</caps:sentence>
            <caps:sentence sentenceid="bce066f4b094bf83ea0c87bc43f563cc" id="tgt66" class="tgtSentence"> 无论哪个应用程序请求 Azure RMS，你都将获得密钥使用日志。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="af89fbd98e11a2aedb93028a1145fe72" id="tgt67" class="tgtSentence">但有一个例外：目前，<embeddedLabel>Azure RMS BYOK 不兼容 Exchange Online</embeddedLabel>。</caps:sentence>
            <caps:sentence sentenceid="d18835901ff66e63effd08dab1efb80b" id="tgt68" class="tgtSentence">  如果你使用 Exchange Online，我们建议你暂时以默认密钥管理模式部署 Azure RMS，由 Microsoft 生成和管理你的密钥。</caps:sentence>
            <caps:sentence sentenceid="0bb39f0d3e59962a4474b50624e18f57" id="tgt69" class="tgtSentence"> 例如，以后你可以在 Exchange Online 不支持 Azure RMS BYOK 时，选择改用 BYOK。</caps:sentence>
            <caps:sentence sentenceid="59192f0793668ffcba5ea57f9639b1bb" id="tgt70" class="tgtSentence"> 但是，如果你不能等待，则目前可以采用另一种做法，那就是使用 BYOK 部署 Azure RMS，在这种情况下，Exchange 的 RMS 功能将会下降（未受保护的电子邮件和未受保护的附件将保持完全正常运行）：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="0dde62f76ded1aa611f59e070cd1ff8c" id="tgt71" class="tgtSentence">无法显示 Outlook Web Access 中受保护的电子邮件或受保护的附件。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="4f0b0efcf1e6dc2f88d29ccb5630bfd7" id="tgt72" class="tgtSentence">无法显示使用 Exchange ActiveSync IRM 的移动设备上的受保护电子邮件。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="28cffd9353e1ab7839a4ad018666f270" id="tgt73" class="tgtSentence">无法进行传输解密（例如，扫描恶意软件）和日记解密，因此将跳过受保护的电子邮件和受保护的附件。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="dffb361fab6426949d23e73cf4d9a3d6" id="tgt74" class="tgtSentence">无法执行会强制 IRM 策略的传输保护规则和数据丢失预防 (DLP)，因此，无法使用这些方法应用 RMS 保护。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="6f8c830290e6c2f4a0a9caa37be9fda2" id="tgt75" class="tgtSentence">基于服务器的受保护的电子邮件，因此将跳过受保护的电子邮件搜索。</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="dd4f745570471e2561c278a403d89a6e" id="tgt76" class="tgtSentence">当你对 Exchange Online 使用 RMS 功能缩减的 Azure RMS BYOK 时，RMS 将适用于 Windows 和 Mac 上 Outlook 中的电子邮件客户端，以及在不使用 Exchange ActiveSync IRM 的其他电子邮件客户端。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="968e42ab49018ea5ec01980776c20b2c" id="tgt77" class="tgtSentence">如果你正在从 AD RMS 迁移到 Azure RMS，你可能已导入你的密钥作为可信发布域 (TPD) 到 Exchange Online（在 Exchange 术语中也称为 BYOK，这不同于 Azure RMS BYOK）。</caps:sentence>
            <caps:sentence sentenceid="45413f014e2305f9f5fe8e3101de0c38" id="tgt78" class="tgtSentence"> 在此情况下，你必须从 Exchange Online 中删除 TPD，以避免模板和策略冲突。</caps:sentence>
            <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt79" class="tgtSentence"> 有关详细信息，请参阅 Exchange Online cmdlet 库中的 <externalLink><linkText>Remove-RMSTrustedPublishingDomain</linkText><linkUri>https://technet.microsoft.com/library/jj200720(v=exchg.150).aspx</linkUri></externalLink>。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="9c12881b4e283ae3fbbb0156dbab7f31" id="tgt80" class="tgtSentence">有时，Exchange Online 的 Azure RMS BYOK 异常实际上并不是问题。</caps:sentence>
            <caps:sentence sentenceid="bca05da2abebf74d74c3bebe3be9c04a" id="tgt81" class="tgtSentence"> 例如，需要 BYOK 和日志记录功能的组织在本地运行他们的数据应用程序（Exchange、SharePoint、Office），并使用 Azure RMS 提供使用本地 AD RMS 不易实现的功能（例如，与其他公司协作，从移动客户端进行访问）。</caps:sentence>
            <caps:sentence sentenceid="9f05f26f63ffd64648ecdda14c67a344" id="tgt82" class="tgtSentence"> BYOK 和日志记录功能在这种方案中使用效果非常好，让组织能够完全控制他们的 Azure RMS 订阅。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_ImplementBYOK">
        <title>
          <caps:sentence sentenceid="e37f1848ad47b60f4bd95fbe2658aa7d" id="tgt83" class="tgtSentence">实现“自带密钥”(BYOK)</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="39300db403a5fa3e0bbf13165d2e8956" id="tgt84" class="tgtSentence">如果你决定自行生成和管理租户密钥，请使用本部分中的信息和过程；“自带密钥”(BYOK) 方案：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_Preqs">Prerequisites for BYOK</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_BYOK_Internet">Generate and transfer your tenant key – over the Internet</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="9af7c117d9de9a06fba7a5f1ea5fcc2d" id="tgt85" class="tgtSentence">
                  <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_BYOK_InPerson">Generate and transfer your tenant key – in person</link> </caps:sentence>
              </para>
            </listItem>
          </list>
          <alert class="important">
            <para>
              <caps:sentence sentenceid="efac44eb7e202b6326fce4d2039a1505" id="tgt86" class="tgtSentence">如果你已经开始使用 <token>aad_rightsmanagement_1</token>（服务已激活），但有些用户在运行 Office 2010，则在运行这些过程之前，请联系 Microsoft 客户支持服务 (CSS)。</caps:sentence>
              <caps:sentence sentenceid="dad8dc3743a347bdf20d16a0a1acf9d6" id="tgt87" class="tgtSentence"> 根据你的方案和要求，你仍然可以使用 BYOK，但会受到一些限制，或者需要执行一些额外步骤。</caps:sentence>
            </para>
            <para>
              <caps:sentence sentenceid="e20d61575749113275ff5753f9e002ad" id="tgt88" class="tgtSentence">如果你的组织制定了关于密钥处理的特定政策，也请联系 CSS。</caps:sentence>
            </para>
          </alert>
        </content>
        <sections>
          <section address="BKMK_Preqs">
            <title>
              <caps:sentence sentenceid="343e07a4b78192894f0d0a45f49acd81" id="tgt89" class="tgtSentence">BYOK 的先决条件</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="f8035107f88238aec28254e3cc84d758" id="tgt90" class="tgtSentence">有关自带密钥 (BYOK) 的先决条件列表，请参阅以下表格。</caps:sentence>
              </para>
              <table>
                <thead>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="ba12fb48e2d23bb2bd2819f64d02ec7e" id="tgt91" class="tgtSentence">要求</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="5dc731e46ae38b87ff3e3e2eaf459db2" id="tgt92" class="tgtSentence">更多信息</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="e68a5d95cb21434f56573506142069b3" id="tgt93" class="tgtSentence">支持 Azure RMS 的订阅</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="6f5448b6afc092f1a26d705aaf8a8151" id="tgt94" class="tgtSentence">有关可用订阅的详细信息，请参阅 <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>主题中的<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link>部分。</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="73da2544473da79f503a5332ead62305" id="tgt95" class="tgtSentence">请不要使用个人 RMS 或 Exchange Online。</caps:sentence>
                        <caps:sentence sentenceid="66b83d0b2a400bff82d3d8f7e9305412" id="tgt96" class="tgtSentence"> 或者，如果你使用 Exchange Online，应了解并接受对此配置使用 BYOK 的限制。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="f0f459c6269ffdf6220e3d782100a4cb" id="tgt97" class="tgtSentence">有关 BYOK 当前限制的详细信息，请参阅本主题中的 <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_Pricing">BYOK pricing and restrictions</link>部分。</caps:sentence>
                      </para>
                      <alert class="important">
                        <para>
                          <caps:sentence sentenceid="5e59707b31b44fb3ecc7a7fbe5442e50" id="tgt98" class="tgtSentence">目前，BYOK 不兼容 Exchange Online。</caps:sentence>
                        </para>
                      </alert>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="bd6c8201308830332fd688f2c0a53c66" id="tgt99" class="tgtSentence">Thales HSM、智能卡和支持软件</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="1e8aef8ec540c46aba1ce17e67bd979a" id="tgt100" class="tgtSentence">如果要使用软件密钥到硬件密钥从 AD RMS 迁移到 Azure RMS，必须拥有 Thales 驱动程序的最低版本 11.62。</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="91ab780e123822ff682e61c04222dbb6" id="tgt101" class="tgtSentence">你必须能够使用 Thales 硬件安全模块，并且掌握有关 Thales HSM 的基本操作知识。</caps:sentence>
                        <caps:sentence sentenceid="78876cede6e051df998fab51465986f4" id="tgt102" class="tgtSentence"> 有关兼容型号的列表，请参阅 <externalLink><linkText>Thales 硬件安全模块</linkText><linkUri>http://www.thales-esecurity.com/msrms/buy</linkUri></externalLink>，如果你还没有 HSM，请及时购买。</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="ac3e7acb76bc792049e5d06cabdd8ced" id="tgt103" class="tgtSentence">如果你希望通过 Internet 传送租户密钥，而不是亲自前往美国 Redmond 传送租户密钥：</caps:sentence>
                      </para>
                      <list class="ordered">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="1d21da441e2715e2d35431224870ca8b" id="tgt104" class="tgtSentence">脱机 x64 工作站，Windows 操作系统版本最低为 Windows 7，Thales nShield 软件至少为版本 11.62。</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence sentenceid="166899902ddb31cd8634509e199155e3" id="tgt105" class="tgtSentence">如果此工作站运行 Windows 7，则必须安装 <externalLink><linkText>Microsoft .NET Framework 4.5</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=225702</linkUri></externalLink>。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="ec6100d340398205dbbc282cb0b38623" id="tgt106" class="tgtSentence">连接到 Internet 的工作站，Windows 操作系统版本最低为 Windows 7。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="d3c8157574b0685da3ed4a32cc5ce064" id="tgt107" class="tgtSentence">USB 驱动器或其他便携式存储设备，至少 16 MB 可用空间。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="9cbbcd371aa434ac8d07bc2942c00870" id="tgt108" class="tgtSentence">如果你亲自将租户密钥送到 Redmond，则不需要这些先决条件。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="f318faf8a098ab7534ecb90e4cc8045a" id="tgt109" class="tgtSentence">出于安全原因，我们建议第一个工作站不要连接到网络。</caps:sentence>
                        <caps:sentence sentenceid="826dfe13ad2a6b5fffbba57f264521e5" id="tgt110" class="tgtSentence"> 但是，程序对此没有强制要求。</caps:sentence>
                      </para>
                      <alert class="note">
                        <para>
                          <caps:sentence sentenceid="1883efd0ddf69b9a7b2041ec330705a7" id="tgt111" class="tgtSentence">在接下来的说明中，此工作站称为未连接工作站。</caps:sentence>
                        </para>
                      </alert>
                      <para>
                        <caps:sentence sentenceid="f8890993e12b3f70c0b912b40b0e5baf" id="tgt112" class="tgtSentence">此外，如果你的租户密钥用于生产网络，我们建议你使用第二个独立工作站来下载工具集和上载租户密钥。</caps:sentence>
                        <caps:sentence sentenceid="9013b4eb52669a1d88c97db216b34b4e" id="tgt113" class="tgtSentence"> 但如果用于测试目的，你可以使用同一个工作站。</caps:sentence>
                      </para>
                      <alert class="note">
                        <para>
                          <caps:sentence sentenceid="0903dd5368092bc6f6e679e168df67c8" id="tgt114" class="tgtSentence">在接下来的说明中，这第二个工作站称为连接 Internet 的工作站。</caps:sentence>
                        </para>
                      </alert>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="b92ff1547b3cad276e5b90c741014eba" id="tgt115" class="tgtSentence">可选：Azure 订阅 </caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="ef9eda89b9937de4904cf53c86cd0b6a" id="tgt116" class="tgtSentence">如果你希望记录租户密钥使用情况（以及权限管理使用情况 ），则必须具有 Azure 订阅，而且在 Azure 上有足够的存储空间来存储你的日志。</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </tbody>
              </table>
              <para>
                <caps:sentence sentenceid="93d5c6bdb1dcf1765969e9cef2956904" id="tgt117" class="tgtSentence">生成和使用自己的租户密钥的过程，具体取决于你是要通过 Internet 传送租户密钥还是亲自传送租户密钥：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="7fe466bb578a58bb9a5db1cd263b6dd8" id="tgt118" class="tgtSentence">
                      <legacyBold>通过 Internet：</legacyBold>这种方式需要一些额外配置步骤，例如下载并使用工具集和 Windows PowerShell cmdlet。</caps:sentence>
                    <caps:sentence sentenceid="9cab9b7337610162feab0ab3a4ed66fd" id="tgt119" class="tgtSentence"> 但是，你无需亲自前往 Microsoft 设施传送你的租户密钥。</caps:sentence>
                    <caps:sentence sentenceid="5da8091e1e58c0e8ad1b362274256c2d" id="tgt120" class="tgtSentence"> 通过以下方法维护安全性：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="5d75261b2bf52cab0e9755c07cdcac14" id="tgt121" class="tgtSentence">你从脱机工作站生成租户密钥，这样可以减小攻击面。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="cae24edc97afb34726dece46afbc8ad2" id="tgt122" class="tgtSentence">租户密钥使用“密钥交换密钥”(KEK) 进行了加密，这样在传送到 Azure RMS HSM 之前可以一直保持加密状态。</caps:sentence>
                        <caps:sentence sentenceid="fa2a263a7252441575267153e52ea5f1" id="tgt123" class="tgtSentence"> 只有已加密版本的租户密钥才能离开原始工作站。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="cf26497a4b820e9e2021ac1661e7e3b2" id="tgt124" class="tgtSentence">你的租户密钥的一个工具集属性，该属性将你的租户密钥绑定到 Azure RMS 安全体系。</caps:sentence>
                        <caps:sentence sentenceid="a7ee211096e21b7c5e982b316f47969e" id="tgt125" class="tgtSentence"> 因此，在 Azure RMS HSM 收到和解密你的租户密钥之后，只有这些 HSM 能够使用该密钥。</caps:sentence>
                        <caps:sentence sentenceid="ede227437724ea64371975e835cf5f64" id="tgt126" class="tgtSentence"> 你的租户密钥无法导出。</caps:sentence>
                        <caps:sentence sentenceid="ca7da79976c8a300829f8ec49cace7db" id="tgt127" class="tgtSentence"> 绑定由 Thales HSM 实施。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="be7f414b3670d379cdd560d31ef332a6" id="tgt128" class="tgtSentence">用于加密你的租户密钥的“密钥交换密钥”(KEK) 在 Azure RMS HSM 内部生成，而且无法导出。</caps:sentence>
                        <caps:sentence sentenceid="651d36bb62e01394237f6ef750337fc2" id="tgt129" class="tgtSentence"> HSM 强制要求在 HSM 外部不能有 KEK 的明文版本。</caps:sentence>
                        <caps:sentence sentenceid="058f52ee76cc7fade115116bd2eea807" id="tgt130" class="tgtSentence"> 此外，工具集包括来自 Thales 的证明，它证实 KEK 是无法导出的，在 Thales 制造的真品 HSM 内部生成。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="806c4d636bc79d76bb09b1f017b56816" id="tgt131" class="tgtSentence">工具集还包括来自 Thales 的证明，它证实 Azure RMS 安全体系也在 Thales 制造的真品 HSM 上生成。</caps:sentence>
                        <caps:sentence sentenceid="3b02b7bbbee60716fb363431b6d91cfe" id="tgt132" class="tgtSentence"> 这样可向你证明 Microsoft 使用了真品硬件。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="a1ed468b51c91c04e9b9fbe1bc507ef4" id="tgt133" class="tgtSentence">Microsoft 使用单独的 KEK，而且在每个地理区域中使用独立的安全体系，这样可以确保你的租户密钥只能在对其进行加密的区域内的数据中心使用。</caps:sentence>
                        <caps:sentence sentenceid="1949e97da2c3cb4f3e84f6c678f9c880" id="tgt134" class="tgtSentence"> 例如，欧洲客户的租户密钥无法在北美或亚洲的数据中心使用。</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <alert class="note">
                    <para>
                      <caps:sentence sentenceid="f755a0efa40930cdff34c97a35be7723" id="tgt135" class="tgtSentence">你的租户密钥可在不受信任的计算机和网络之间安全传送，因为它进行了加密，并且通过访问控制级别权限得到保护，只能在你的 HSM 和 Microsoft 的用于 Azure RMS 的 HSM 内部使用。</caps:sentence>
                      <caps:sentence sentenceid="41e5b600037ccf98618c67989cad27c2" id="tgt136" class="tgtSentence"> 你可以使用工具集中提供的脚本来验证安全措施，并且阅读 Thales 提供的此方面内容的详细信息：<externalLink><linkText>RMS 云中的硬件密钥管理</linkText><linkUri>https://www.thales-esecurity.com/knowledge-base/white-papers/hardware-key-management-in-the-rms-cloud</linkUri></externalLink>。</caps:sentence>
                    </para>
                  </alert>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="d31c6392e94299efb7583e2522680e8a" id="tgt137" class="tgtSentence">
                      <legacyBold>亲自传送密钥：</legacyBold>这种方式要求你联系 Microsoft 客户支持服务 (CSS) 来安排 Azure RMS 的密钥传送预约。</caps:sentence>
                    <caps:sentence sentenceid="19591a2b72bad9f0e37ef26c48a417db" id="tgt138" class="tgtSentence"> 你必须亲自前往位于美国华盛顿州 Redmond 市的 Microsoft 办事处，将你的租户密钥传送到 Azure RMS 安全体系。</caps:sentence>
                  </para>
                </listItem>
              </list>
            </content>
          </section>
          <section address="BKMK_BYOK_Internet" expanded="false">
            <title>
              <caps:sentence sentenceid="72c07f0cba62efa9db481cca56681cf2" id="tgt139" class="tgtSentence">生成和传送租户密钥 – 通过 Internet</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="84e29389d78f56b13694985609e81e76" id="tgt140" class="tgtSentence">如果你希望通过 Internet 传送租户密钥，而不是亲自前往 Microsoft 设施来传送密钥，请使用以下过程： </caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetPrepareWorkstation">Prepare your Internet-connected workstation</link>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_DisconnectedPrepareWorkstation">Prepare your disconnected workstation</link>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetGenerate">Generate your tenant key</link>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetPrepareTransfer">Prepare your tenant key for transfer</link>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetTransfer">Transfer your tenant key to Azure RMS</link>
                  </para>
                </listItem>
              </list>
            </content>
            <sections>
              <section address="BKMK_InternetPrepareWorkstation">
                <title>
                  <caps:sentence sentenceid="54b73cfe72f17921f48a732c3190729c" id="tgt141" class="tgtSentence">准备你的连接 Internet 的工作站</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence sentenceid="cfbfa2b9b936b537193ce7279641b8cc" id="tgt142" class="tgtSentence">为了准备连接 Internet 的工作站，请按照以下 3 个步骤操作：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_PrepareInternetConnectedWorkstation1">Step 1: Install Windows PowerShell for Azure Rights Management</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_PrepareInternetConnectedWorkstation2">Step 2: Get your Azure Active Directory tenant ID</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_PrepareInternetConnectedWorkstation3">Step 3: Download the BYOK toolset</link>
                      </para>
                    </listItem>
                  </list>
                </content>
                <sections>
                  <section address="BKMK_PrepareInternetConnectedWorkstation1">
                    <title>
                      <caps:sentence sentenceid="e5b41d6c21fef5b9b02bc608577ebb01" id="tgt143" class="tgtSentence">步骤 1：安装适用于 Azure 权限管理的 Windows PowerShell</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="7fce2a98a077e5fcbeaf6f093abd4f15" id="tgt144" class="tgtSentence">在连接 Internet 的工作站上下载和安装适用于 Azure 权限管理的 Windows PowerShell 模块。</caps:sentence>
                      </para>
                      <alert class="note">
                        <para>
                          <caps:sentence sentenceid="ddc11251862cd3ecdd7f4b89bb34441e" id="tgt145" class="tgtSentence">如果你之前已下载了此 Windows PowerShell 模块，请运行以下命令来检查你的版本号是否至少为 2.1.0.0：<codeInline>(Get-Module aadrm -ListAvailable).Version</codeInline> </caps:sentence>
                        </para>
                      </alert>
                      <para>
                        <caps:sentence sentenceid="9b8b89d25f443ebfc7497fedc34ed4ca" id="tgt146" class="tgtSentence">有关安装说明，请参阅<link xlink:href="0d665ed6-b1de-4d63-854a-bc57c1c49844">Installing Windows PowerShell for Azure Rights Management</link>。</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_PrepareInternetConnectedWorkstation2">
                    <title>
                      <caps:sentence sentenceid="ab49e31d6d82d91e5c410bea3cb7e6f1" id="tgt147" class="tgtSentence">步骤 2：获取你的 Azure Active Directory 租户 ID</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="986a1e9cf69d28fc407425532bc33082" id="tgt148" class="tgtSentence">使用“以管理员身份运行”选项启动 Windows PowerShell，然后运行以下命令<ui></ui>：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="16859c9da62799922bc88b1c7de34fc3" id="tgt149" class="tgtSentence">使用 <externalLink><linkText>Connect-AadrmService</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629415.aspx</linkUri></externalLink> cmdlet 连接到 Azure RMS 服务：</caps:sentence>
                          </para>
                          <code>Connect-AadrmService</code>
                          <para>
                            <caps:sentence sentenceid="4029bc06e3eeccb6ce05b9512cc14d97" id="tgt150" class="tgtSentence">出现提示时，输入 <token>aad_rightsmanagement_1</token> 租户管理员凭据（通常，将使用作为 Azure Active Directory 或 Office 365 的全局管理员的帐户）。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="16859c9da62799922bc88b1c7de34fc3" id="tgt151" class="tgtSentence">使用 <externalLink><linkText>Get-AadrmConfiguration</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629410.aspx</linkUri></externalLink> cmdlet 显示租户的配置：</caps:sentence>
                          </para>
                          <code>Get-AadrmConfiguration</code>
                          <para>
                            <caps:sentence sentenceid="195e2e7a93bc9d4dcd1fd4d5a8ac8e53" id="tgt152" class="tgtSentence">保存输出的第一行中的 GUID (BPOSId)。</caps:sentence>
                            <caps:sentence sentenceid="e5db0b16a4567cf5ef5e28b8fddca92d" id="tgt153" class="tgtSentence"> 这是你的 Azure Active Directory 租户 ID，以后你在准备要上载的租户密钥时需要使用它。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="16859c9da62799922bc88b1c7de34fc3" id="tgt154" class="tgtSentence">使用 <externalLink><linkText>Disconnect-AadrmService</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629416.aspx</linkUri></externalLink> cmdlet 断开与 Azure RMS 服务的连接，直至你为上载密钥做好准备：</caps:sentence>
                          </para>
                          <code>Disconnect-AadrmService</code>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence sentenceid="0fbfac7a23681cb56fc08367bcacbc07" id="tgt155" class="tgtSentence">不要关闭 Windows PowerShell 窗口。</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_PrepareInternetConnectedWorkstation3">
                    <title address="BKMK_PrepareWorkstationInternetKey2">
                      <caps:sentence sentenceid="f85b08872a356174c3a3b5b275f55069" id="tgt156" class="tgtSentence">步骤 3：下载 BYOK 工具集</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="7209f861321ac5cf48673edd9ea6749e" id="tgt157" class="tgtSentence">转到 Microsoft 下载中心并<externalLink><linkText>下载适用于你所在区域的 BYOK 工具集</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=335781</linkUri></externalLink>：</caps:sentence>
                      </para>
                      <table>
                        <thead>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="960db2ed82202a9706b97775a4269378" id="tgt158" class="tgtSentence">区域</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="cd1ba76ea4375bdcf65cb5c11a876bde" id="tgt159" class="tgtSentence">包名称</caps:sentence>
                              </para>
                            </TD>
                          </tr>
                        </thead>
                        <tbody>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="460491fc520f4dbfcff22d1a45f6b056" id="tgt160" class="tgtSentence">北美</caps:sentence>
                              </para>
                              <para></para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="9a20b75733233f93d58544abe0a946c2" id="tgt161" class="tgtSentence">AzureRMS-BYOK-tools-UnitedStates.zip</caps:sentence>
                              </para>
                            </TD>
                          </tr>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="7612e84033b6f5f1a8b8039d9e25d9b5" id="tgt162" class="tgtSentence">欧洲</caps:sentence>
                              </para>
                              <para></para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="67848a17eb073e88f6eba825ee3df6b8" id="tgt163" class="tgtSentence">AzureRMS-BYOK-tools-Europe.zip</caps:sentence>
                              </para>
                            </TD>
                          </tr>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="cffe819d4413b95dd8c35c0085930789" id="tgt164" class="tgtSentence">亚洲</caps:sentence>
                              </para>
                              <para></para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence sentenceid="3ac20d104649812e3040b526accbbda3" id="tgt165" class="tgtSentence">AzureRMS-BYOK-tools-AsiaPacific.zip</caps:sentence>
                              </para>
                            </TD>
                          </tr>
                        </tbody>
                      </table>
                      <para>
                        <caps:sentence sentenceid="8041902343e5c5cf16aeabe62da4fe8d" id="tgt166" class="tgtSentence">工具集包括以下部分：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="bb09ea516ca9defa464629b0977c765d" id="tgt167" class="tgtSentence">“密钥交换密钥”(KEK) 软件包，名称以 <ui>BYOK-KEK-pkg-</ui> 开头。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="079d8f0308cda4fdc6864a41c605de53" id="tgt168" class="tgtSentence">安全体系包，名称以 <ui>BYOK-SecurityWorld-pkg-</ui> 开头。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="ed56990d847627b15cd8c67ec93c3db0" id="tgt169" class="tgtSentence">名为 <ui>verifykeypackage.py</ui> 的 Python 脚本。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="5f8c8f30d45ee86ffde37d15075b7326" id="tgt170" class="tgtSentence">一个名为 <ui>KeyTransferRemote.exe</ui> 的命令行可执行文件、一个名为 <ui>KeyTransferRemote.exe.config</ui> 的元数据文件以及关联的 DLL。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="0f87d58440af68f6b7a69dfeb01a7f28" id="tgt171" class="tgtSentence">名为 <ui>vcredist_x64.exe</ui> 的 Visual C++ 可再分发包。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence sentenceid="c4fb36fa29b0750a3c528a03ae8ee5b6" id="tgt172" class="tgtSentence">将包复制到 USB 驱动器或其他便携式存储设备。</caps:sentence>
                      </para>
                    </content>
                  </section>
                </sections>
              </section>
              <section address="BKMK_DisconnectedPrepareWorkstation">
                <title>
                  <caps:sentence sentenceid="a241d7d85e49f9f57149daa8ab94e6be" id="tgt173" class="tgtSentence">准备你的未连接工作站</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence sentenceid="f15ea2fdd28cebaa74905862c4aac173" id="tgt174" class="tgtSentence">为了准备未连接到网络（Internet 或内部网络）的工作站，请按照以下 2 个步骤操作：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_PrepareDisconnectedWorkstation1">Step 1: Prepare the disconnected workstation with Thales HSM</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_PrepareDisconnectedWorkstation2">Step 2: Install the BYOK toolset on the disconnected workstation</link>
                      </para>
                    </listItem>
                  </list>
                </content>
                <sections>
                  <section address="BKMK_PrepareDisconnectedWorkstation1">
                    <title address="BKMK_PrepareWorkstationInternetKey1">
                      <caps:sentence sentenceid="700330b30a14a695d9bf7f009b233280" id="tgt175" class="tgtSentence">步骤 1：准备要运行 Thales HSM 的未连接工作站</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="bbf7165fb1fee7f7cf74ab03ccca7529" id="tgt176" class="tgtSentence">在未连接工作站的 Windows 计算机上安装 nCipher (Thales) 支持软件，然后将 Thales HSM 连接到该计算机。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="8e003d3d8a416c5d5a1d64b6c24bdcab" id="tgt177" class="tgtSentence">确保 Thales 工具在你的路径（<system>(%nfast_home%\bin</system> 和 <system>%nfast_home%\python\bin</system>）中。</caps:sentence>
                        <caps:sentence sentenceid="d9df8f2a0645df90a5da64d9b01f6f99" id="tgt178" class="tgtSentence"> 例如，键入以下命令：</caps:sentence>
                      </para>
                      <code>set PATH=%PATH%;”%nfast_home%\bin”;”%nfast_home%\python\bin”</code>
                      <para>
                        <caps:sentence sentenceid="3adc6b0e3ab6f060b1d8780091b5a463" id="tgt179" class="tgtSentence">有关详细信息，请参阅 Thales HSM 附带的用户指南，或者访问 Thales 的 Azure RMS 网站，地址为 <externalLink><linkText>http://www.thales-esecurity.com/msrms/cloud</linkText><linkUri>http://www.thales-esecurity.com/msrms/cloud</linkUri></externalLink>。</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_PrepareDisconnectedWorkstation2">
                    <title>
                      <caps:sentence sentenceid="2edecd670b7bef4e821fdffe7b50f331" id="tgt180" class="tgtSentence">步骤 2：在未连接工作站上安装 BYOK 工具集</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="f577ffcf9831eae1533ee0d9e6d2d0c0" id="tgt181" class="tgtSentence">从 USB 驱动器或其他便携式存储设备复制 BYOK 工具集包，然后执行以下操作：</caps:sentence>
                      </para>
                      <list class="ordered">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="348df8b4f61336cbac256df5b935ffa0" id="tgt182" class="tgtSentence">将文件从下载包解压到任意文件夹。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="2b0b710da6bd5c4e7172bec32b6e52ea" id="tgt183" class="tgtSentence">在该文件夹下运行 vcredist_x64.exe。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="8c2856959bc2e2f9f2cf32c19e8c46b7" id="tgt184" class="tgtSentence">按照以下说明安装 Visual Studio 2012 的 Visual C++ 运行时组件。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </content>
                  </section>
                </sections>
              </section>
              <section address="BKMK_InternetGenerate">
                <title>
                  <caps:sentence sentenceid="dc1fa9cd8fab3c7ce3d9741746a53951" id="tgt185" class="tgtSentence">生成你的租户密钥</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence sentenceid="778300ecf11a0a407fe47ad700a6855c" id="tgt186" class="tgtSentence">在未连接工作站上，按照以下 3 个步骤，生成你自己的租户密钥： </caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetGenerate1">Step 1: Create a security world</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetGenerate2">Step 2: Validate the downloaded package</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetGenerate3">Step 3: Create a new key</link>
                      </para>
                    </listItem>
                  </list>
                </content>
                <sections>
                  <section address="BKMK_InternetGenerate1">
                    <title>
                      <caps:sentence sentenceid="23b4b793a02a09c05073ee1eed92d18a" id="tgt187" class="tgtSentence">步骤 1：创建安全体系</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="e2b0d541d8230781174e58c88eeff6ad" id="tgt188" class="tgtSentence">启动命令提示符，并运行 Thales new-world 程序。</caps:sentence>
                      </para>
                      <code>new-world.exe --initialize --cipher-suite=DLf1024s160mRijndael --module=1 --acs-quorum=2/3
</code>
                      <para>
                        <caps:sentence sentenceid="10d22a80b9e75b2f92c209648b7920b1" id="tgt189" class="tgtSentence">此程序可在 %NFAST_KMDATA%\local\world（与 C:\ProgramData\nCipher\Key Management Data\local 文件夹对应）下创建一个<embeddedLabel>安全体系</embeddedLabel>文件。</caps:sentence>
                        <caps:sentence sentenceid="6e982f4689d3422999b3906876da29d6" id="tgt190" class="tgtSentence"> 你可以使用不同值进行仲裁，但在我们的示例中，系统提示你输入三个空白卡，以及每个卡的 Pin。</caps:sentence>
                        <caps:sentence sentenceid="664021a24d578be6c0917102c93f82c3" id="tgt191" class="tgtSentence"> 然后，将要求任意两个卡对安全体系（你的指定仲裁）具有管理访问权限。</caps:sentence>
                        <caps:sentence sentenceid="bf8c77d3261be1165176b90e3f1d17fc" id="tgt192" class="tgtSentence">  这些卡变成新安全体系的<embeddedLabel>管理员卡集</embeddedLabel>。</caps:sentence>
                        <caps:sentence sentenceid="e050517fe3063681fc5f2cc0cd3154fa" id="tgt193" class="tgtSentence"> 在此阶段，你可以为每个 ACS 卡指定密码或 PIN，也可以在以后使用命令添加它。</caps:sentence>
                      </para>
                      <alert class="tip">
                        <para>
                          <caps:sentence sentenceid="0b248d02dbd09de2e88556a86426c952" id="tgt194" class="tgtSentence">你可以使用 <codeInline>nkminfo</codeInline> 命令验证 HSM 的当前配置状态。</caps:sentence>
                        </para>
                      </alert>
                      <para>
                        <caps:sentence sentenceid="e2f5e4fcd97322877deb9cf4d0242428" id="tgt195" class="tgtSentence">然后执行下列操作：</caps:sentence>
                      </para>
                      <list class="ordered">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="fea36b6f270e161b575c87733efd729b" id="tgt196" class="tgtSentence">按照 Thales 文档中的说明，安装 Thales CNG 提供程序，并将其配置为使用新安全体系。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="d35e5f6bcbdbb573f11c0230b13569b3" id="tgt197" class="tgtSentence">备份 <embeddedLabel>%nfast_kmdata%\local</embeddedLabel> 中的体系文件。</caps:sentence>
                            <caps:sentence sentenceid="1bc54fb5cc8aebacbad97f2e945d8385" id="tgt198" class="tgtSentence"> 保护体系文件、管理员卡及其 PIN，确保没有任何用户能够访问多个卡。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </content>
                  </section>
                  <section address="BKMK_InternetGenerate2">
                    <title>
                      <caps:sentence sentenceid="c74d8dd7a3261d356bf8c5a365f82748" id="tgt199" class="tgtSentence">步骤 2：验证下载的包</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="f3f85d4ff06da3d251bf7306829b326f" id="tgt200" class="tgtSentence">此步骤是可选的，但我们建议执行此步骤，以便能够进行以下验证：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="278c05ff1f165ca28d50f68bf8baaccc" id="tgt201" class="tgtSentence">工具集包括的“密钥交换密钥”是从真品 Thales HSM 生成的。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="4c51cb7dad362e48c579b10381673511" id="tgt202" class="tgtSentence">工具集包括的 Azure RMS 安全体系的哈希是在真品 Thales HSM 中生成的。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="0a8ec555f2cd41fe3d29036728e43b92" id="tgt203" class="tgtSentence">“密钥交换密钥”是无法导出的。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <alert class="note">
                        <para>
                          <caps:sentence sentenceid="d9ee92d34e24525e4049ebfe1515b16a" id="tgt204" class="tgtSentence">若要验证下载的包，HSM 必须处于连接状态且接通电源，其上必须有安全体系（例如你刚才创建的那一个）。</caps:sentence>
                        </para>
                      </alert>
                      <procedure>
                        <title>
                          <caps:sentence sentenceid="c96343bfb9191d473ab57878eba09ac5" id="tgt205" class="tgtSentence">验证下载的包</caps:sentence>
                        </title>
                        <steps class="ordered">
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="11082c4be5874823a067e242da084dc5" id="tgt206" class="tgtSentence">根据你所在的地区，键入以下命令之一，以运行 verifykeypackage.py 脚本：</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="07b7966f446597db1081f7a14285849c" id="tgt207" class="tgtSentence">适用于北美：</caps:sentence>
                                  </para>
                                  <code>python verifykeypackage.py -k BYOK-KEK-pkg-NA-1 -w BYOK-SecurityWorld-pkg-NA-1</code>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="efb82bea4793d01165057d389b0c3c27" id="tgt208" class="tgtSentence">适用于欧洲：</caps:sentence>
                                  </para>
                                  <code>python verifykeypackage.py -k BYOK-KEK-pkg-EU-1 -w BYOK-SecurityWorld-pkg-EU-1</code>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence sentenceid="53ef12914c50d3fbf7a1aba6af951e90" id="tgt209" class="tgtSentence">适用于亚洲：</caps:sentence>
                                  </para>
                                  <code>python verifykeypackage.py -k BYOK-KEK-pkg-AP-1 -w BYOK-SecurityWorld-pkg-AP-1</code>
                                </listItem>
                              </list>
                              <alert class="tip">
                                <para>
                                  <caps:sentence sentenceid="35ae305f1bfb2fcba11bffb5cf8ae3b2" id="tgt210" class="tgtSentence">Thales 软件包括了一个 Python 解释器（位于 %NFAST_HOME%\python\bin 中）</caps:sentence>
                                </para>
                              </alert>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence sentenceid="fefc93181955c2bc601ee3a381959961" id="tgt211" class="tgtSentence">确认你看到以下结果，它表示验证成功：<ui>结果：SUCCESS</ui></caps:sentence>
                              </para>
                            </content>
                          </step>
                        </steps>
                        <conclusion>
                          <content>
                            <para>
                              <caps:sentence sentenceid="cbffb89e528e0f34c8cf7da5174e7b49" id="tgt212" class="tgtSentence">此脚本验证签名人链，一直到 Thales 根密钥。</caps:sentence>
                              <caps:sentence sentenceid="fda75ff98db1cba0e920408987c718c5" id="tgt213" class="tgtSentence"> 此根密钥的哈希嵌入到脚本中，其值应为 <ui>59178a47 de508c3f 291277ee 184f46c4 f1d9c639</ui>。</caps:sentence>
                              <caps:sentence sentenceid="d9ed93ffc21ea6ad75ffb2758a53b0de" id="tgt214" class="tgtSentence"> 你也可以通过访问 <externalLink><linkText>Thales 网站</linkText><linkUri>http://www.thalesesec.com/</linkUri></externalLink>，单独确认该值。</caps:sentence>
                            </para>
                          </content>
                        </conclusion>
                      </procedure>
                      <para>
                        <caps:sentence sentenceid="21ce20b42056b744a95cd74c2b20c16a" id="tgt215" class="tgtSentence">你现在可以创建一个新密钥，作为你的 RMS 租户密钥。</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_InternetGenerate3">
                    <title>
                      <caps:sentence sentenceid="55292337964bb5c6f9970cf825f1e7e7" id="tgt216" class="tgtSentence">步骤 3：创建新密钥</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="6d4047c00776260d9086509290711e4e" id="tgt217" class="tgtSentence">使用 Thales <userInputLocalizable>generatekey</userInputLocalizable> 和<userInputLocalizable>cngimport</userInputLocalizable> 程序创建一个 CNG 密钥。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="10d640bf5ba02f9c1252209ae762a1c8" id="tgt218" class="tgtSentence">运行以下命令以生成密钥：</caps:sentence>
                      </para>
                      <code>generatekey --generate simple type=RSA size=2048 protect=module ident=contosokey plainname=contosokey nvram=no pubexp=
</code>
                      <para>
                        <caps:sentence sentenceid="5afe8d9185f3085883d990ce28ece6df" id="tgt219" class="tgtSentence">当你运行此命令时，请使用以下说明：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="35896e62a720173ed94d38b4834190a6" id="tgt220" class="tgtSentence">对于密钥大小，我们建议为 2048 位，但也支持现有 AD RMS 客户拥有 1024 位 RSA 密钥，这些客户使用此类密钥向 Azure RMS 迁移。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="8fd685e2c123b014cf3f46aed3fe622a" id="tgt221" class="tgtSentence">将 <ui>ident</ui> 和 <ui>plainname</ui> 的 <placeholder>contosokey</placeholder> 值替换为任何字符串值。</caps:sentence>
                            <caps:sentence sentenceid="a26ba6f66e3538e5310453bf1d9eac56" id="tgt222" class="tgtSentence"> 为了最大程度地减少管理开销和降低错误风险，我们建议两者使用相同的值，并且全部使用小写字符。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="024da1ef10ab582f0dbf0113864d7d37" id="tgt223" class="tgtSentence">在本例中，pubexp 保留空白（默认值），但你可以指定特定值。</caps:sentence>
                            <caps:sentence sentenceid="150c881b1c4c467cc209d98789728cef" id="tgt224" class="tgtSentence"> 有关详细信息，请参阅 Thales 文档。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence sentenceid="41fcaf20edf172f440187e9372259ea4" id="tgt225" class="tgtSentence">然后运行以下命令，将密钥导入 CNG：</caps:sentence>
                      </para>
                      <code>cngimport --import -M --key=contosokey --appname=simple contosokey</code>
                      <para>
                        <caps:sentence sentenceid="5afe8d9185f3085883d990ce28ece6df" id="tgt226" class="tgtSentence">当你运行此命令时，请使用以下说明：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="05d18373e30d5a4c6a58e6f3b2e3e7ab" id="tgt227" class="tgtSentence">将 <placeholder>contosokey</placeholder> 替换为<legacyItalic>在生成你的租户密钥</legacyItalic>部分的<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetGenerate1">Step 1: Create a security world</link>中指定的同一值。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="16859c9da62799922bc88b1c7de34fc3" id="tgt228" class="tgtSentence">请使用 <ui>-M</ui> 选项，使得密钥适合此方案。</caps:sentence>
                            <caps:sentence sentenceid="d859f34de478873d7ace218e5167747c" id="tgt229" class="tgtSentence"> 在不使用此选项的情况下，生成的密钥将是当前用户的用户特定密钥。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence sentenceid="b008673846d3ef7593030d1c99b701ca" id="tgt230" class="tgtSentence">此命令可在你的 %NFAST_KMDATA%\local 文件夹中创建一个标记化密钥文件，其名称以 <ui>key_caping_</ui> 开头，后跟 SID。</caps:sentence>
                        <caps:sentence sentenceid="407e8379b5443b7c0092c35c8bab7f29" id="tgt231" class="tgtSentence"> 例如：<system>key_caping_machine--801c1a878c925fd9df4d62ba001b94701c039e2fb</system>。</caps:sentence>
                        <caps:sentence sentenceid="f1639ecb5cd3da7d6eea8643b41ed9dc" id="tgt232" class="tgtSentence"> 此文件包含加密密钥。</caps:sentence>
                      </para>
                      <alert class="tip">
                        <para>
                          <caps:sentence sentenceid="ff7858e9d9d5f74d6129caf612bc0a32" id="tgt233" class="tgtSentence">你可以使用 <codeInline>nkminfo –k</codeInline> 命令查看密钥的当前配置状态。</caps:sentence>
                        </para>
                      </alert>
                      <para>
                        <caps:sentence sentenceid="9ed59eb6fe46867517b16822db7181d8" id="tgt234" class="tgtSentence">在安全位置备份这个标记化密钥文件。</caps:sentence>
                      </para>
                      <alert class="important">
                        <para>
                          <caps:sentence sentenceid="607b015ce782d371f45f9c1c357c224b" id="tgt235" class="tgtSentence">当你以后将密钥传送到 Azure RMS 时，Microsoft 无法再将此密钥导出给你，因此你必须安全地备份密钥和安全体系，这一点极为重要。</caps:sentence>
                          <caps:sentence sentenceid="92f1cde5ecf6c32adfa8abb2e50b3082" id="tgt236" class="tgtSentence"> 请联系 Thales 以获得备份密钥的指导和最佳实践。</caps:sentence>
                        </para>
                      </alert>
                      <para>
                        <caps:sentence sentenceid="beb9e2f44e20944afe619f027cf80557" id="tgt237" class="tgtSentence">你现在可将租户密钥传送到 Azure RMS。</caps:sentence>
                      </para>
                    </content>
                  </section>
                </sections>
              </section>
              <section address="BKMK_InternetPrepareTransfer">
                <title>
                  <caps:sentence sentenceid="dbd297e7c357efd805aba72d985c9b99" id="tgt238" class="tgtSentence">准备要传送的租户密钥</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence sentenceid="4178d498c4593ab229c5d396258b45e4" id="tgt239" class="tgtSentence">在未连接工作站上，按照以下 4 个步骤，准备你自己的租户密钥：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetPrepareTransfer1">Step 1: Create a copy of your key with reduced permissions</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetPrepareTransfer2">Step 2: Inspect the new copy of the key</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetPrepareTransfer3">Step 3: Encrypt your key by using Microsoft’s Key Exchange Key</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetPrepareTransfer4">Step 4: Copy your key transfer package to the Internet-connected workstation </link>
                      </para>
                    </listItem>
                  </list>
                </content>
                <sections>
                  <section address="BKMK_InternetPrepareTransfer1">
                    <title>
                      <caps:sentence sentenceid="91f8a245cb56097da988a7380837e648" id="tgt240" class="tgtSentence">步骤 1：创建你的密钥副本，该副本具有降低的权限</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="cda3c9247852ad0de8fbb227849a6535" id="tgt241" class="tgtSentence">若要降低你的租户密钥的权限，请执行以下操作： </caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="1b4a9f33e72a02b3cf57e218a5f76c55" id="tgt242" class="tgtSentence">根据你所在的地区，从命令提示符处运行以下命令之一：</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="07b7966f446597db1081f7a14285849c" id="tgt243" class="tgtSentence">适用于北美：</caps:sentence>
                              </para>
                              <code>KeyTransferRemote.exe -ModifyAcls -KeyAppName simple -KeyIdentifier contosokey -ExchangeKeyPackage BYOK-KEK-pkg-NA-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-NA-1</code>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="efb82bea4793d01165057d389b0c3c27" id="tgt244" class="tgtSentence">适用于欧洲：</caps:sentence>
                              </para>
                              <code>KeyTransferRemote.exe -ModifyAcls -KeyAppName simple -KeyIdentifier contosokey -ExchangeKeyPackage BYOK-KEK-pkg-EU-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-EU-1</code>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="53ef12914c50d3fbf7a1aba6af951e90" id="tgt245" class="tgtSentence">适用于亚洲：</caps:sentence>
                              </para>
                              <code>KeyTransferRemote.exe -ModifyAcls -KeyAppName simple -KeyIdentifier contosokey -ExchangeKeyPackage BYOK-KEK-pkg-AP-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-AP-1</code>
                            </listItem>
                          </list>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence sentenceid="72e1bb8a18200aa792925fadb998e779" id="tgt246" class="tgtSentence">运行此命令时，请将 <placeholder>contosokey</placeholder> 替换为<legacyItalic>在生成你的租户密钥</legacyItalic>部分的<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetGenerate1">Step 1: Create a security world</link>中指定的同一值。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="d6c0a8dd28f973672ae45ca4d68e9eef" id="tgt247" class="tgtSentence">可能会要求你插入安全体系 ACS 卡，并且如果指定了其密码或 PIN，还会要求提供它们。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="0ed89ab1e1edfbfb328ed81dee7646f3" id="tgt248" class="tgtSentence">命令完成时，你将看到 <ui>Result:SUCCESS</ui>，具有降低的权限的租户密钥副本将位于名为 key_xferacId_<placeholder>&lt;contosokey&gt;</placeholder> 的文件中。</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_InternetPrepareTransfer2">
                    <title>
                      <caps:sentence sentenceid="cb5717cdc065fc38047925893d1a1dec" id="tgt249" class="tgtSentence">步骤 2：检测新的密钥副本</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="b369230e10b2903efcec1d8ee15ac9fc" id="tgt250" class="tgtSentence">或者，运行 Thales 实用工具以确认新租户密钥的最低权限：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="27ff8ecae1d98381d5d734e0675b6e5d" id="tgt251" class="tgtSentence">aclprint.py：</caps:sentence>
                          </para>
                          <code>"%nfast_home%\bin\preload.exe" -m 1 -A xferacld -K contosokey "%nfast_home%\python\bin\python" "%nfast_home%\python\examples\aclprint.py"</code>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="3fabfaf77d92db57eb3930d06df9c225" id="tgt252" class="tgtSentence">kmfile-dump.exe：</caps:sentence>
                          </para>
                          <code>"%nfast_home%\bin\kmfile-dump.exe" "%NFAST_KMDATA%\local\key_xferacld_contosokey"
</code>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence sentenceid="ed1269cb47c4386bdb9a8ad8d4ed4872" id="tgt253" class="tgtSentence">运行这些命令时，请将 <placeholder>contosokey</placeholder> 替换为<legacyItalic>在生成你的租户密钥</legacyItalic>部分的<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetGenerate1">Step 1: Create a security world</link>中指定的同一值。</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_InternetPrepareTransfer3">
                    <title>
                      <caps:sentence sentenceid="3aa3be783b7fa69bb794543d87df5c15" id="tgt254" class="tgtSentence">步骤 3：使用 Microsoft 的“密钥交换密钥”加密你的密钥</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="be41730bfbff57f825e75193dea584d9" id="tgt255" class="tgtSentence">根据你所在的地区，运行以下命令之一：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="07b7966f446597db1081f7a14285849c" id="tgt256" class="tgtSentence">适用于北美：</caps:sentence>
                          </para>
                          <code>KeyTransferRemote.exe -Package -KeyIdentifier <placeholder xmlns="">contosokey</placeholder> -ExchangeKeyPackage BYOK-KEK-pkg-NA-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-NA-1 -TenantBposId <placeholder xmlns="">GUID</placeholder> -KeyFriendlyName <placeholder xmlns="">ContosoFirstkey</placeholder></code>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="efb82bea4793d01165057d389b0c3c27" id="tgt257" class="tgtSentence">适用于欧洲：</caps:sentence>
                          </para>
                          <code>KeyTransferRemote.exe -Package -KeyIdentifier <placeholder xmlns="">contosokey</placeholder> -ExchangeKeyPackage BYOK-KEK-pkg-EU-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-EU-1 -TenantBposId <placeholder xmlns="">GUID</placeholder> -KeyFriendlyName <placeholder xmlns="">ContosoFirstkey</placeholder></code>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="53ef12914c50d3fbf7a1aba6af951e90" id="tgt258" class="tgtSentence">适用于亚洲：</caps:sentence>
                          </para>
                          <code>KeyTransferRemote.exe -Package -KeyIdentifier <placeholder xmlns="">contosokey</placeholder> -ExchangeKeyPackage BYOK-KEK-pkg-AP-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-AP-1 -TenantBposId <placeholder xmlns="">GUID</placeholder> -KeyFriendlyName <placeholder xmlns="">ContosoFirstkey</placeholder></code>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence sentenceid="5afe8d9185f3085883d990ce28ece6df" id="tgt259" class="tgtSentence">当你运行此命令时，请使用以下说明：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="05d18373e30d5a4c6a58e6f3b2e3e7ab" id="tgt260" class="tgtSentence">将 <placeholder>contosokey</placeholder> 替换为你在<legacyItalic>生成你的租户密钥</legacyItalic>部分的<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetGenerate1">Step 1: Create a security world</link>中用于生成密钥的标识符。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="05d18373e30d5a4c6a58e6f3b2e3e7ab" id="tgt261" class="tgtSentence">将 <placeholder>GUID</placeholder> 替换为你在<legacyItalic>准备你的连接 Internet 的工作站</legacyItalic>部分的<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_PrepareInternetConnectedWorkstation2">Step 2: Get your Azure Active Directory tenant ID</link>中检索的 Azure Active Directory 租户 ID。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="05d18373e30d5a4c6a58e6f3b2e3e7ab" id="tgt262" class="tgtSentence">将 <placeholder>ContosoFirstKey</placeholder> 替换为将用作输出文件名称的标签。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence sentenceid="ba736121726a435db99f03575bdf1fae" id="tgt263" class="tgtSentence">成功完成后，它将显示 <ui>Result:SUCCESS</ui>，当前文件夹中将有一个新文件，名称如下：TransferPackage-<placeholder>ContosoFirstkey</placeholder>.byok</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_InternetPrepareTransfer4">
                    <title>
                      <caps:sentence sentenceid="9740a2a6210cbd15ba2a10d5bcf8a667" id="tgt264" class="tgtSentence">步骤 4：将你的密钥传送包复制到连接 Internet 的工作站 </caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="0d34092421e0755e41c40d1789500b72" id="tgt265" class="tgtSentence">使用 USB 驱动器或其他便携式存储设备，将前一步骤中的输出文件 (KeyTransferPackage-<placeholder>ContosoFirstkey</placeholder>.byok) 复制到连接 Internet 的工作站。</caps:sentence>
                      </para>
                      <alert class="security note">
                        <para>
                          <caps:sentence sentenceid="2f6dc825861d5a68b5eafa05ea457ea7" id="tgt266" class="tgtSentence">运用安全实践来保护该文件，因为其中包含你的私钥。</caps:sentence>
                        </para>
                      </alert>
                    </content>
                  </section>
                </sections>
              </section>
              <section address="BKMK_InternetTransfer">
                <title>
                  <caps:sentence sentenceid="7662732f07e53fa857481d002b495249" id="tgt267" class="tgtSentence">将你的租户密钥传送到 Azure RMS</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence sentenceid="78f85780a2cb76201b0873799b3a6d84" id="tgt268" class="tgtSentence">在连接 Internet 的工作站上，按照以下 3 个步骤，将你的新租户密钥传送到 Azure RMS：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetTransfer1">Step 1: Connect to Azure RMS</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetTransfer2">Step 2: Upload the key package</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetTransfer3">Step 3: Enumerate your tenant keys – as needed</link>
                      </para>
                    </listItem>
                  </list>
                </content>
                <sections>
                  <section address="BKMK_InternetTransfer1">
                    <title>
                      <caps:sentence sentenceid="1835e46eb9dbe3eb84c42cf49dc2a4ef" id="tgt269" class="tgtSentence">步骤 1：连接到 Azure RMS</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="0e65683c5fa04d944227bbba6eb7317a" id="tgt270" class="tgtSentence">返回到 Windows PowerShell 窗口并键入以下命令： </caps:sentence>
                      </para>
                      <list class="ordered">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="ef1446272cacf87d21e13cdcb14ca1ca" id="tgt271" class="tgtSentence">重新连接到 <token>aad_rightsmanagement_1</token> 服务：</caps:sentence>
                          </para>
                          <code>Connect-AadrmService</code>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="16859c9da62799922bc88b1c7de34fc3" id="tgt272" class="tgtSentence">使用 <externalLink><linkText>Get-AadrmKeys</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629420.aspx</linkUri></externalLink> cmdlet 查看你的当前租户密钥配置：</caps:sentence>
                          </para>
                          <code>Get-AadrmKeys</code>
                        </listItem>
                      </list>
                    </content>
                  </section>
                  <section address="BKMK_InternetTransfer2">
                    <title>
                      <caps:sentence sentenceid="9450da6d731356b6b1ea403caed93e25" id="tgt273" class="tgtSentence">步骤 2：上载密钥包</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="16859c9da62799922bc88b1c7de34fc3" id="tgt274" class="tgtSentence">使用 <externalLink><linkText>Add-AadrmKey</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629418.aspx</linkUri></externalLink> cmdlet 上载你从未连接工作站复制的密钥传送包：</caps:sentence>
                      </para>
                      <code>Add-AadrmKey –KeyFile &lt;PathToPackageFile&gt; -Verbose</code>
                      <alert class="warning">
                        <para>
                          <caps:sentence sentenceid="97813e43a798d452fcbbca07f0f8cb3f" id="tgt275" class="tgtSentence">系统将提示你确认此操作。</caps:sentence>
                          <caps:sentence sentenceid="8f6b41ce8924229511734545c28a462b" id="tgt276" class="tgtSentence"> 必须知道此操作是无法撤销的，这一点非常重要。</caps:sentence>
                          <caps:sentence sentenceid="874b221c6ab312ea1027344f9b8b82d5" id="tgt277" class="tgtSentence"> 当你上载租户文件时，它自动成为你组织的首选租户密钥，用户将在保护文档和文件时开始使用此租户密钥。</caps:sentence>
                        </para>
                      </alert>
                      <para></para>
                      <para>
                        <caps:sentence sentenceid="0f014176a87954b3ae438873efdd8182" id="tgt278" class="tgtSentence">如果上载成功，你将看到以下消息：<ui>Rights Management 服务已成功添加密钥。</ui></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="629f36237e5b2c2fc8ade5d882f51869" id="tgt279" class="tgtSentence">当更改传播到所有 <token>aad_rightsmanagement_1</token> 数据中心时，将会出现复制延迟。</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_InternetTransfer3">
                    <title>
                      <caps:sentence sentenceid="226051132aa01f6b9306290cbdab0583" id="tgt280" class="tgtSentence">步骤 3：根据需要枚举你的租户密钥</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="4b426fe2f3654b6efb22e9fdda4c7cff" id="tgt281" class="tgtSentence">每当你希望查看租户密钥列表以及查看租户密钥的更改时，可再次使用 Get-AadrmKeys cmdlet。</caps:sentence>
                        <caps:sentence sentenceid="7b90fba7edd8a46e03e45c4d4cc4884e" id="tgt282" class="tgtSentence"> 显示的租户密钥包括 Microsoft 为你生成的初始租户密钥，以及你添加的任何租户密钥：</caps:sentence>
                      </para>
                      <code>Get-AadrmKeys</code>
                      <para>
                        <caps:sentence sentenceid="11d13d85bd1025b6fa43734b054762ba" id="tgt283" class="tgtSentence">标记为“活动”的租户密钥是你的组织当前用于保护文档和文件的密钥<ui></ui>。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="e9ca1606310983d29ef2fa463a6d8508" id="tgt284" class="tgtSentence">你现在已经完成了通过 Internet 自带密钥所需的全部步骤，接下来可以执行<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_NextSteps">Next steps</link>。</caps:sentence>
                      </para>
                    </content>
                  </section>
                </sections>
              </section>
            </sections>
          </section>
          <section address="BKMK_BYOK_InPerson" expanded="false">
            <title>
              <caps:sentence sentenceid="d76bbe3dafe5c8b0807448b86347128b" id="tgt285" class="tgtSentence">亲自生成和传送你的租户密钥</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="6d3e89040953cbc3f365d36e8c58e457" id="tgt286" class="tgtSentence">如果你不希望通过 Internet 传送你的租户密钥，请使用以下过程亲自传送你的租户密钥。</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_GenerateKey">Generate your tenant key</link>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_Transfer">Transfer your tenant key to Azure RMS</link>
                  </para>
                </listItem>
              </list>
            </content>
            <sections>
              <section address="BKMK_GenerateKey">
                <title>
                  <caps:sentence sentenceid="dc1fa9cd8fab3c7ce3d9741746a53951" id="tgt287" class="tgtSentence">生成你的租户密钥</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence sentenceid="368ece73a2a216d23013558719657cb3" id="tgt288" class="tgtSentence">若要生成你自己的租户密钥，请执行以下 3 个步骤： </caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_GenerateYourKey1">Step 1: Prepare a workstation with Thales HSM</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_GenerateYourKey2">Step 2: Create a security world</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_GenerateYourKey3">Step 3: Create a new key</link>
                      </para>
                    </listItem>
                  </list>
                </content>
                <sections>
                  <section address="BKMK_GenerateYourKey1">
                    <title>
                      <caps:sentence sentenceid="8b3f03aa65d6315df22ca100804c5e0c" id="tgt289" class="tgtSentence">步骤 1：准备运行 Thales HSM 的工作站</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="77a431bb6997d33c02c78fd6d3e32c96" id="tgt290" class="tgtSentence">在 Windows 计算机上安装 nCipher (Thales) 支持软件。</caps:sentence>
                        <caps:sentence sentenceid="318dc804025d0e2e9f69bb25dd1c081f" id="tgt291" class="tgtSentence"> 将 Thales HSM 连接到该计算机。</caps:sentence>
                        <caps:sentence sentenceid="4755da75d458a2588e1ebe2919a0b598" id="tgt292" class="tgtSentence"> 确保 Thales 工具在你的路径中。</caps:sentence>
                        <caps:sentence sentenceid="b011f9013e9f7c37ea62ae830742f381" id="tgt293" class="tgtSentence"> 有关详细信息，请参阅 Thales HSM 附带的用户指南，或者访问 Thales 的 Azure RMS 网站，地址为 <externalLink><linkText>http://www.thales-esecurity.com/msrms/cloud</linkText><linkUri>http://www.thales-esecurity.com/msrms/cloud</linkUri></externalLink>。</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_GenerateYourKey2">
                    <title>
                      <caps:sentence sentenceid="8e5e154ee1a3ee8ad0a7b5d199164e75" id="tgt294" class="tgtSentence">步骤 2：创建安全体系</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="e2b0d541d8230781174e58c88eeff6ad" id="tgt295" class="tgtSentence">启动命令提示符，并运行 Thales new-world 程序。</caps:sentence>
                      </para>
                      <code>new-world.exe --initialize --cipher-suite=DLf1024s160mRijndael --module=1 --acs-quorum=2/3
</code>
                      <para>
                        <caps:sentence sentenceid="10d22a80b9e75b2f92c209648b7920b1" id="tgt296" class="tgtSentence">此程序可在 %NFAST_KMDATA%\local\world（与 C:\ProgramData\nCipher\Key Management Data\local 文件夹对应）下创建一个<embeddedLabel>安全体系</embeddedLabel>文件。</caps:sentence>
                        <caps:sentence sentenceid="6e982f4689d3422999b3906876da29d6" id="tgt297" class="tgtSentence"> 你可以使用不同值进行仲裁，但在我们的示例中，系统提示你输入三个空白卡，以及每个卡的 Pin。</caps:sentence>
                        <caps:sentence sentenceid="6a318f478531fb06304c9f40cb50fcee" id="tgt298" class="tgtSentence"> 因此，其中任意二个卡将提供对安全体系的完全访问权限。</caps:sentence>
                        <caps:sentence sentenceid="bf8c77d3261be1165176b90e3f1d17fc" id="tgt299" class="tgtSentence">  这些卡变成新安全体系的<embeddedLabel>管理员卡集</embeddedLabel>。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="e2f5e4fcd97322877deb9cf4d0242428" id="tgt300" class="tgtSentence">然后执行下列操作：</caps:sentence>
                      </para>
                      <list class="ordered">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="fea36b6f270e161b575c87733efd729b" id="tgt301" class="tgtSentence">按照 Thales 文档中的说明，安装 Thales CNG 提供程序，并将其配置为使用新安全体系。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="3d06c3adeeed020b70b322773a463aa3" id="tgt302" class="tgtSentence">备份体系文件。</caps:sentence>
                            <caps:sentence sentenceid="1bc54fb5cc8aebacbad97f2e945d8385" id="tgt303" class="tgtSentence"> 保护体系文件、管理员卡及其 PIN，确保没有任何用户能够访问多个卡。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence sentenceid="21ce20b42056b744a95cd74c2b20c16a" id="tgt304" class="tgtSentence">你现在可以创建一个新密钥，作为你的 RMS 租户密钥。</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_GenerateYourKey3">
                    <title>
                      <caps:sentence sentenceid="55292337964bb5c6f9970cf825f1e7e7" id="tgt305" class="tgtSentence">步骤 3：创建新密钥</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence sentenceid="6d4047c00776260d9086509290711e4e" id="tgt306" class="tgtSentence">使用 Thales <userInputLocalizable>generatekey</userInputLocalizable> 和<userInputLocalizable>cngimport</userInputLocalizable> 程序创建一个 CNG 密钥。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="10d640bf5ba02f9c1252209ae762a1c8" id="tgt307" class="tgtSentence">运行以下命令以生成密钥：</caps:sentence>
                      </para>
                      <code>generatekey --generate simple type=RSA size=2048 protect=module ident=contosokey plainname=contosokey nvram=no pubexp=
</code>
                      <para>
                        <caps:sentence sentenceid="5afe8d9185f3085883d990ce28ece6df" id="tgt308" class="tgtSentence">当你运行此命令时，请使用以下说明：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="f426b308f36891b6c2d3aedebce803b8" id="tgt309" class="tgtSentence">对于密钥大小，我们建议为 2048 位，但也支持现有 AD RMS 客户拥有 1024 位 RSA 密钥，这些客户使用此类密钥向 Azure RMS 迁移。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="8fd685e2c123b014cf3f46aed3fe622a" id="tgt310" class="tgtSentence">将 <ui>ident</ui> 和 <ui>plainname</ui> 的 <placeholder>contosokey</placeholder> 值替换为任何字符串值。</caps:sentence>
                            <caps:sentence sentenceid="a26ba6f66e3538e5310453bf1d9eac56" id="tgt311" class="tgtSentence"> 为了最大程度地减少管理开销和降低错误风险，我们建议两者使用相同的值，并且全部使用小写字符。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="024da1ef10ab582f0dbf0113864d7d37" id="tgt312" class="tgtSentence">在本例中，pubexp 保留空白（默认值），但你可以指定特定值。</caps:sentence>
                            <caps:sentence sentenceid="150c881b1c4c467cc209d98789728cef" id="tgt313" class="tgtSentence"> 有关详细信息，请参阅 Thales 文档。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence sentenceid="41fcaf20edf172f440187e9372259ea4" id="tgt314" class="tgtSentence">然后运行以下命令，将密钥导入 CNG：</caps:sentence>
                      </para>
                      <code>cngimport --import –M --key=contosokey --appname=simple contosokey</code>
                      <para>
                        <caps:sentence sentenceid="5afe8d9185f3085883d990ce28ece6df" id="tgt315" class="tgtSentence">当你运行此命令时，请使用以下说明：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="05d18373e30d5a4c6a58e6f3b2e3e7ab" id="tgt316" class="tgtSentence">将 <placeholder>contosokey</placeholder> 替换为你在步骤 1 中指定的同一值。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="16859c9da62799922bc88b1c7de34fc3" id="tgt317" class="tgtSentence">请使用 <ui>-M</ui> 选项，使得密钥适合此方案。</caps:sentence>
                            <caps:sentence sentenceid="d859f34de478873d7ace218e5167747c" id="tgt318" class="tgtSentence"> 在不使用此选项的情况下，生成的密钥将是当前用户的用户特定密钥。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence sentenceid="b008673846d3ef7593030d1c99b701ca" id="tgt319" class="tgtSentence">此命令可在你的 %NFAST_KMDATA%\local 文件夹中创建一个标记化密钥文件，其名称以 <ui>key_caping_</ui> 开头，后跟 SID。</caps:sentence>
                        <caps:sentence sentenceid="407e8379b5443b7c0092c35c8bab7f29" id="tgt320" class="tgtSentence"> 例如：<system>key_caping_machine--801c1a878c925fd9df4d62ba001b94701c039e2fb</system>。</caps:sentence>
                        <caps:sentence sentenceid="f1639ecb5cd3da7d6eea8643b41ed9dc" id="tgt321" class="tgtSentence"> 此文件包含加密密钥。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="9ed59eb6fe46867517b16822db7181d8" id="tgt322" class="tgtSentence">在安全位置备份这个标记化密钥文件。</caps:sentence>
                      </para>
                      <alert class="important">
                        <para>
                          <caps:sentence sentenceid="5399c16f8656d5b012dd874858db7ce5" id="tgt323" class="tgtSentence">当你以后将密钥传送到 Azure RMS 时，Microsoft 将拥有你的密钥的不可恢复副本。</caps:sentence>
                          <caps:sentence sentenceid="fe8c74b9a54859c2c54f0f5bda8b738f" id="tgt324" class="tgtSentence"> 这意味着 Microsoft 的任何人都无法从 HSM 检索你的密钥。</caps:sentence>
                          <caps:sentence sentenceid="f0bfa635207860524bcb7ccd2eac457f" id="tgt325" class="tgtSentence"> 这使你能够保持对租户密钥的独有控制。</caps:sentence>
                          <caps:sentence sentenceid="2bf65bbcf52d69b45f72cded6dac2fde" id="tgt326" class="tgtSentence"> 因此，你必须安全地备份密钥和安全体系，这一点极为重要。</caps:sentence>
                          <caps:sentence sentenceid="92f1cde5ecf6c32adfa8abb2e50b3082" id="tgt327" class="tgtSentence"> 请联系 Thales 以获得备份密钥的指导和最佳实践。</caps:sentence>
                        </para>
                      </alert>
                      <para>
                        <caps:sentence sentenceid="72fb694573a90c94659e590118b6ff6d" id="tgt328" class="tgtSentence">你现在可将租户密钥传送到 Azure RMS。</caps:sentence>
                      </para>
                    </content>
                  </section>
                </sections>
              </section>
              <section address="BKMK_Transfer">
                <title>
                  <caps:sentence sentenceid="7662732f07e53fa857481d002b495249" id="tgt329" class="tgtSentence">将你的租户密钥传送到 Azure RMS</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence sentenceid="76a71d0faec7937efd4de481d9a1a5cb" id="tgt330" class="tgtSentence">在你生成自己的密钥之后，在使用之前，必须将其传送到 Azure RMS。</caps:sentence>
                    <caps:sentence sentenceid="2ba74c79693b70876ff2653b5047c512" id="tgt331" class="tgtSentence"> 为了达到最高级别的安全性，这种传送采用人工过程，要求你亲自前往位于美国华盛顿州 Redmond 市的 Microsoft 办事处。</caps:sentence>
                    <caps:sentence sentenceid="5d0d4c9ea0ab23082f9040ea382725b4" id="tgt332" class="tgtSentence"> 若要完成此过程，请执行以下 3 个步骤：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_TransferYourKey1">Step 1: Bring your key to Microsoft</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_TransferYourKey2">Step 2: Transfer your key to the Window Azure RMS security world</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_TransferYourKey3">Step 3: Closing procedures</link>
                      </para>
                    </listItem>
                  </list>
                  <procedure address="BKMK_TransferYourKey1">
                    <title>
                      <caps:sentence sentenceid="799062afb48c5c079e44f0fd82ef7e2f" id="tgt333" class="tgtSentence">步骤 1：将你的密钥提供给 Microsoft</caps:sentence>
                    </title>
                    <steps class="bullet">
                      <step>
                        <content>
                          <para>
                            <caps:sentence sentenceid="d5babc769aec361d8c62fcd326a8a255" id="tgt334" class="tgtSentence">联系 Microsoft 客户支持服务 (CSS)，安排 Azure RMS 的密钥传送预约。</caps:sentence>
                            <caps:sentence sentenceid="06c948ca77103974e3a22f3d3c05891a" id="tgt335" class="tgtSentence"> 向位于 Redmond 市的 Microsoft 设施提交以下项目：</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="981602cd7020ee97cde1ad801da29adf" id="tgt336" class="tgtSentence">管理卡的仲裁。</caps:sentence>
                                <caps:sentence sentenceid="00f649230a8d74b4d9570610be474bae" id="tgt337" class="tgtSentence"> 如果你遵循了前面<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_GenerateYourKey2">Step 2: Create a security world</link>中的说明，则它们是三个卡中的任意两个卡。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="32c426e8fed8cf1af2fdf1bd95b49eea" id="tgt338" class="tgtSentence">被授权携带你的管理卡和 PIN 的员工，通常有两位（一人一卡）。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="989dfac0eaa00c1c920f3ce457d8817d" id="tgt339" class="tgtSentence">你的安全体系文件 (%NFAST_KMDATA%\local\world)，保存在 USB 驱动器上。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="705ddf6b0ed2ffe9a964cf5d9fd1a714" id="tgt340" class="tgtSentence">你的标记化密钥文件，保存在 USB 驱动器上。</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </content>
                      </step>
                    </steps>
                  </procedure>
                  <procedure address="BKMK_TransferYourKey2">
                    <title>
                      <caps:sentence sentenceid="1099528ec40216ecbc5a66fda59e8359" id="tgt341" class="tgtSentence">步骤 2：将你的密钥传送到 Window Azure RMS 安全体系</caps:sentence>
                    </title>
                    <steps class="ordered">
                      <step>
                        <content>
                          <para>
                            <caps:sentence sentenceid="5f66c3a717635b3c8676c1b626c43136" id="tgt342" class="tgtSentence">当你亲自前往 Microsoft 传送你的密钥时，会发生以下情况：</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="907048162d4cfd03c657070f45ff0792" id="tgt343" class="tgtSentence">Microsoft 为你提供连接 Thales HSM 的脱机工作站，它安装了 Thales 软件，并将 Azure RMS 安全体系文件预先加载到文件夹 C:\Temp\Destination。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="47bfdd99b590293267c1f7f66ef051dc" id="tgt344" class="tgtSentence">在此工作站上，你将 USB 驱动器上的安全体系文件和标记化密钥文件加载到 C:\Temp\Source 文件夹中。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="a4a62bd08eb0687ff8331fab1deef409" id="tgt345" class="tgtSentence">Azure RMS 操作人员使用 Thales 实用工具，将你的密钥安全传送到 Azure RMS 安全体系。</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                          <para>
                            <caps:sentence sentenceid="58b5c10eed239d9cbbf707e3a95681b2" id="tgt346" class="tgtSentence">这个过程与以下过程类似，本例中的最后一个参数 key-xfer-im 替换为你的标记化密钥文件名称：</caps:sentence>
                          </para>
                          <para>
                            <ui>
                              <caps:sentence sentenceid="603cdc880a57822f72c77a8537e934e3" id="tgt347" class="tgtSentence">C:\&gt; mk-reprogram.exe --owner c:\Temp\Destination add c:\Temp\Source</caps:sentence>
                            </ui>
                          </para>
                          <para>
                            <ui>
                              <caps:sentence sentenceid="7871b94fe8f44bda66ad2139943e3e28" id="tgt348" class="tgtSentence">C:\&gt; key-xfer-im.exe c:\Temp\Source c:\Temp\Destination --module c:\Temp\Source\key_caping_machine--801c1a878c925fd9df4d62ba001b94701c039e2fb</caps:sentence>
                            </ui>
                          </para>
                        </content>
                      </step>
                      <step>
                        <content>
                          <para>
                            <caps:sentence sentenceid="c6cd78f0301dd47b5d71d9e2d3fe2b49" id="tgt349" class="tgtSentence">Mk-reprogram 将请求你和 Azure RMS 操作人员插入相应的管理员卡和 PIN。</caps:sentence>
                            <caps:sentence sentenceid="beb1dfb3dc93ece54af44c442e8a3881" id="tgt350" class="tgtSentence"> 这些命令在包含受 Azure RMS 安全体系保护的密钥的 C:\Temp\Destination 目录中输出一个标记化密钥文件。</caps:sentence>
                          </para>
                        </content>
                      </step>
                    </steps>
                  </procedure>
                  <procedure address="BKMK_TransferYourKey3">
                    <title>
                      <caps:sentence sentenceid="4a67edaf84271698eb13e9628c02c085" id="tgt351" class="tgtSentence">步骤 3：完成过程</caps:sentence>
                    </title>
                    <steps class="bullet">
                      <step>
                        <content>
                          <para>
                            <caps:sentence sentenceid="95575413d943dde2b0254dc39de69ad0" id="tgt352" class="tgtSentence">当你在场的情况下，Azure RMS 操作人员执行以下操作：</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="e1d664419b2311a18b8a6211b0356871" id="tgt353" class="tgtSentence">运行 Microsoft 和 Thales 协作开发的一种工具，用于删除两种权限：恢复密钥的权限、更改权限的权限。</caps:sentence>
                                <caps:sentence sentenceid="aaf43a8922f8194a0795ec33f4d11f03" id="tgt354" class="tgtSentence"> 完成此操作后，你的这个密钥副本将会锁定到 Azure RMS 安全体系。</caps:sentence>
                                <caps:sentence sentenceid="fda5d71a9ceaabf313738f0dde511dd6" id="tgt355" class="tgtSentence"> Thales HSM 将不允许拥有管理员卡的 Azure RM 操作人员恢复密钥明文副本。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="3aaf270c93ee20a6732d30e4ebb7defa" id="tgt356" class="tgtSentence">将生成的密钥文件复制到 USB 驱动器，以便以后上载到 Azure RMS 服务。</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="e9e7523aba06ad681d10823c8aafa1f1" id="tgt357" class="tgtSentence">对 HSM 进行出厂重置，将工作站擦除干净。</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </content>
                      </step>
                    </steps>
                  </procedure>
                  <para>
                    <caps:sentence sentenceid="c8d9708bfb32a2c95fa8d0ffec8b4cce" id="tgt358" class="tgtSentence">你现在已经完成了自带密钥所需的全部步骤，可以返回到组织执行后续步骤。</caps:sentence>
                  </para>
                </content>
              </section>
            </sections>
          </section>
        </sections>
      </section>
      <section address="BKMK_NextSteps">
        <title>
          <caps:sentence sentenceid="0a4f90ce90fc062c4fc00532513d86da" id="tgt359" class="tgtSentence">后续步骤</caps:sentence>
        </title>
        <content>
          <list class="ordered">
            <listItem>
              <para>
                <caps:sentence sentenceid="514ca66f5f9c6459370b74efca579c51" id="tgt360" class="tgtSentence">开始使用你的租户密钥：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="35dc57f310915958306d59fdf07ac3c9" id="tgt361" class="tgtSentence">如果尚未开始使用，你必须立即启用权限管理，以便你的组织能够开始使用 RMS。</caps:sentence>
                    <caps:sentence sentenceid="20e78531c8e6d31839a397ed982a9d70" id="tgt362" class="tgtSentence"> 用户立即开始使用你的租户密钥（由 Microsoft 管理或由你管理）。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="0d03ba68f222bc8d1eae62867499253b" id="tgt363" class="tgtSentence">有关激活的详细信息，请参阅<link xlink:href="f8707e01-b239-4d1a-a1ea-0d1cf9a8d214">Activating Azure Rights Management</link>。</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="0869c20afd1e1a2e6bb23e75747e6f34" id="tgt364" class="tgtSentence">如果你已经激活了权限管理，然后决定自行管理租户密钥，用户将逐渐从旧租户密钥迁移到新租户密钥，这种交错式迁移可能需要花费几周才能完成。</caps:sentence>
                    <caps:sentence sentenceid="30a5b7b56e26207de0b40c4a82f9da3e" id="tgt365" class="tgtSentence"> 受旧租户密钥保护的文档和文件仍然可供授权用户访问。</caps:sentence>
                  </para>
                </listItem>
              </list>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="d9d63d2cbeab08bde402d3cea3846be4" id="tgt366" class="tgtSentence">请考虑启用使用日志记录，该功能可记录 RMS 执行的每一个事务。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="b77a57ca32d0a3f72e99749afbad5759" id="tgt367" class="tgtSentence">如果你决定自行管理租户密钥，则日志记录包括租户密钥的使用信息。</caps:sentence>
                <caps:sentence sentenceid="f8cbf118618ee8a56e2cacbf42ba142e" id="tgt368" class="tgtSentence"> 请参阅在 Excel 中显示的以下日志文件示例，其中的 <ui>Decrypt</ui> 和 <ui>SignDigest</ui> 请求类型显示该租户密钥正在使用中。</caps:sentence>
              </para>
              <mediaLink>
                <image xlink:href="6b958831-fba1-46b6-81c5-f20cf645927a"></image>
              </mediaLink>
              <para></para>
              <para>
                <caps:sentence sentenceid="ccfb6d38f4dcbbe3ca9bd3f064020409" id="tgt369" class="tgtSentence">有关使用日志记录的详细信息，请参阅<link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e">Log and analyze rights management usage</link>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="5e6244e9b994aedd9928ea16c2c50276" id="tgt370" class="tgtSentence">维护你的租户密钥。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="d1aee644e17abda9397214172b7615de" id="tgt371" class="tgtSentence">有关详细信息，请参阅<link xlink:href="1284d0ee-0a72-45ba-a64c-3dcb25846c3d">Operations for your Rights Management Tenant Key</link>。</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="206a0bfe-0912-4e0e-aa15-484b000b264c">Configuring rights management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSTarget>
  <caps:SxSSource locale="en-US">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence id="src1" class="srcSentence">Use the information in this topic to help you plan for and manage your Rights Management service (RMS) tenant key for Azure RMS.</caps:sentence>
          <caps:sentence id="src2" class="srcSentence"> For example, instead of Microsoft managing your tenant key (the default), you might want to manage your own tenant key to comply with specific regulations that apply to your organization.</caps:sentence>
          <caps:sentence id="src3" class="srcSentence">  Managing your own tenant key is also referred to as bring your own key, or BYOK.</caps:sentence>
        </para>
        <alert class="note">
          <para>
            <caps:sentence id="src4" class="srcSentence">The RMS tenant key is also known as the Server Licensor Certificate (SLC) key.</caps:sentence>
            <caps:sentence id="src5" class="srcSentence"> Azure RMS maintains one or more keys for each organization that subscribes to Azure RMS.</caps:sentence>
            <caps:sentence id="src6" class="srcSentence"> Whenever a key is used for RMS within an organization (such as user keys, computer keys, document encryption keys), they cryptographically chain to your RMS tenant key.</caps:sentence>
          </para>
        </alert>
        <para>
          <caps:sentence id="src7" class="srcSentence">
            <embeddedLabel>At a glance:</embeddedLabel> Use the following table as a quick guide to your recommended tenant key topology.</caps:sentence>
          <caps:sentence id="src8" class="srcSentence"> Then, use the additional sections for more information.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src9" class="srcSentence">If you deploy Azure RMS by using a tenant key that is managed by Microsoft, you can change to BYOK later.</caps:sentence>
          <caps:sentence id="src10" class="srcSentence"> However, you cannot currently change your Azure RMS tenant key from BYOK to managed by Microsoft.</caps:sentence>
        </para>
        <table>
          <tbody>
            <tr>
              <TH>
                <para>
                  <caps:sentence id="src11" class="srcSentence">Business requirement</caps:sentence>
                </para>
              </TH>
              <TH>
                <para>
                  <caps:sentence id="src12" class="srcSentence">Recommended tenant key topology</caps:sentence>
                </para>
              </TH>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src13" class="srcSentence">Deploy Azure RMS quickly and without requiring special hardware</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src14" class="srcSentence">Managed by Microsoft</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src15" class="srcSentence">Need full IRM functionality in Exchange Online with Azure RMS</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src16" class="srcSentence">Managed by Microsoft</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src17" class="srcSentence">Your keys are created by you and protected in a hardware security module (HSM)</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src18" class="srcSentence">BYOK</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src19" class="srcSentence">Currently, this configuration will result in reduced IRM functionality in Exchange Online.</caps:sentence>
                  <caps:sentence id="src20" class="srcSentence"> For more information, see the <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_Pricing">BYOK pricing and restrictions</link> section.</caps:sentence>
                </para>
              </TD>
            </tr>
          </tbody>
        </table>
        <para>
          <caps:sentence id="src21" class="srcSentence">Use the following sections to help you choose which tenant key topology to use, understand the tenant key lifecycle, how to implement bring your own key (BYOK), and what steps to take next:</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_ChooseTenantKey">Choose your tenant key topology: Managed by Microsoft (the default) or managed by you (BYOK)</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_Pricing">BYOK pricing and restrictions</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_ImplementBYOK">Implementing bring your own key (BYOK)</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_NextSteps">Next steps</link>
            </para>
          </listItem>
        </list>
      </introduction>
      <section address="BKMK_ChooseTenantKey">
        <title>
          <caps:sentence id="src22" class="srcSentence">Choose your tenant key topology: Managed by Microsoft (the default) or managed by you (BYOK)</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src23" class="srcSentence">Decide which tenant key topology is best for your organization.</caps:sentence>
            <caps:sentence id="src24" class="srcSentence"> By default, Azure RMS generates your tenant key and manages most aspects of the tenant key lifecycle.</caps:sentence>
            <caps:sentence id="src25" class="srcSentence"> This is the simplest option with the lowest administrative overheads.</caps:sentence>
            <caps:sentence id="src26" class="srcSentence"> In most cases, you do not even need to know that you have a tenant key.</caps:sentence>
            <caps:sentence id="src27" class="srcSentence"> You just sign up for Azure RMS and the rest of the key management process is handled by Microsoft.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src28" class="srcSentence">Alternatively, you might want complete control over your tenant key, which involves creating your tenant key and keeping the master copy on your premises.</caps:sentence>
            <caps:sentence id="src29" class="srcSentence"> This scenario is often referred to as bring your own key (BYOK).</caps:sentence>
            <caps:sentence id="src30" class="srcSentence"> With this option, the following happens:</caps:sentence>
          </para>
          <list class="ordered">
            <listItem>
              <para>
                <caps:sentence id="src31" class="srcSentence">You generate your tenant key on your premises, in line with your IT policies.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src32" class="srcSentence">You securely transfer the tenant key from a Hardware Security Module (HSM) in your possession to HSMs that are owned and managed by Microsoft.</caps:sentence>
                <caps:sentence id="src33" class="srcSentence"> Throughout this process, your tenant key never leaves the hardware protection boundary.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src34" class="srcSentence">When you transfer your tenant key to Microsoft, it stays protected by Thales HSMs.</caps:sentence>
                <caps:sentence id="src35" class="srcSentence"> Microsoft has worked with Thales to ensure that your tenant key cannot be extracted from Microsoft’s HSMs.</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src36" class="srcSentence">Although it’s optional, you will also probably want to use the near real-time usage logs from Azure RMS to see exactly how and when your tenant key is being used.</caps:sentence>
          </para>
          <alert class="note">
            <para>
              <caps:sentence id="src37" class="srcSentence">As an additional protection measure, Azure RMS uses separate security worlds for its data centers in North America, EMEA (Europe, Middle East and Africa), and Asia.</caps:sentence>
              <caps:sentence id="src38" class="srcSentence"> When you manage your own tenant key, it is tied to the security world of the region in which your RMS tenant is registered.</caps:sentence>
              <caps:sentence id="src39" class="srcSentence"> For example, a tenant key from a European customer cannot be used in data centers in North America or Asia.</caps:sentence>
            </para>
          </alert>
        </content>
      </section>
      <section address="BKMK_OverviewLifecycle">
        <title>
          <caps:sentence id="src40" class="srcSentence">The tenant key lifecycle</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src41" class="srcSentence">If you decide that Microsoft should manage your tenant key, Microsoft handles most of the key lifecycle operations.</caps:sentence>
            <caps:sentence id="src42" class="srcSentence"> However, if you decide to manage your tenant key, you are responsible for many of the key lifecycle operations and some additional procedures.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src43" class="srcSentence">The following diagrams show and compares these two options.</caps:sentence>
            <caps:sentence id="src44" class="srcSentence"> The first diagram shows how little administrator overheads there are for you in the default configuration when Microsoft manages the tenant key.</caps:sentence>
          </para>
          <mediaLink>
            <caption>
              <caps:sentence id="src45" class="srcSentence">Tenant key managed by Microsoft</caps:sentence>
            </caption>
            <image xlink:href="66905ef5-1ba4-4c93-9513-c6d7a9173453"></image>
          </mediaLink>
          <para></para>
          <para>
            <caps:sentence id="src46" class="srcSentence">The second diagram shows the additional steps required when you manage your own tenant key.</caps:sentence>
          </para>
          <mediaLink>
            <caption>
              <caps:sentence id="src47" class="srcSentence">Tenant key managed by you (BYOK)</caps:sentence>
            </caption>
            <image xlink:href="ec00ba88-ad16-4426-81e3-d5d074ce0c31"></image>
          </mediaLink>
          <para></para>
          <para>
            <caps:sentence id="src48" class="srcSentence">If you decide to let Microsoft manage your tenant key, no further action is required for you to generate the key and you can skip the following sections and go straight to <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_NextSteps">Next steps</link>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src49" class="srcSentence">If you decide to manage your tenant key yourself, read the following sections for more information.</caps:sentence>
          </para>
        </content>
        <sections>
          <section expanded="false">
            <title>
              <caps:sentence id="src50" class="srcSentence">More information about Thales HSMs and Microsoft additions</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src51" class="srcSentence">Azure RMS uses Thales HSMs to protect your keys.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src52" class="srcSentence">Thales e-Security is a leading global provider of data encryption and cyber security solutions to the financial services, high technology, manufacturing, government, and technology sectors.</caps:sentence>
                <caps:sentence id="src53" class="srcSentence"> With a 40-year track record of protecting corporate and government information, Thales solutions are used by four of the five largest energy and aerospace companies, 22 NATO countries, and secure more than 80 per cent of worldwide payment transactions.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src54" class="srcSentence">Microsoft has collaborated with Thales to enhance the state of art for HSMs.</caps:sentence>
                <caps:sentence id="src55" class="srcSentence"> These enhancements enable you to get the typical benefits of hosted services without relinquishing control over your keys.</caps:sentence>
                <caps:sentence id="src56" class="srcSentence"> Specifically, these enhancements let Microsoft manage the HSMs so that you do not have to.</caps:sentence>
                <caps:sentence id="src57" class="srcSentence"> As a cloud service, Azure RMS scales up at short notice to meet your organization’s usage spikes.</caps:sentence>
                <caps:sentence id="src58" class="srcSentence"> At the same time, your key is protected inside Microsoft’s HSMs: You retain control over the key lifecycle because you generate the key and transfer it to Microsoft’s HSMs.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src59" class="srcSentence">For more information, see <externalLink><linkText>Thales HSMs and Azure RMS</linkText><linkUri>http://www.thales-esecurity.com/msrms/cloud</linkUri></externalLink> on the Thales web site.</caps:sentence>
              </para>
            </content>
          </section>
        </sections>
      </section>
      <section address="BKMK_Pricing">
        <title>
          <caps:sentence id="src60" class="srcSentence">BYOK pricing and restrictions</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src61" class="srcSentence">Organization that have an IT-managed Azure subscription can use BYOK and log its usage at no extra charge.</caps:sentence>
            <caps:sentence id="src62" class="srcSentence"> Organizations that use RMS for individuals cannot use BYOK and logging because they do not have a tenant administrator to configure these features.</caps:sentence>
          </para>
          <alert class="note">
            <para>
              <caps:sentence id="src63" class="srcSentence">For more information about RMS for individuals, see <link xlink:href="2efcb440-fefd-45e9-872b-f471573aadf2">RMS for Individuals and Azure Rights Management</link>.</caps:sentence>
            </para>
          </alert>
          <mediaLink>
            <image xlink:href="6417311a-9193-4c6e-a284-ac92b335ea80"></image>
          </mediaLink>
          <para></para>
          <para>
            <caps:sentence id="src64" class="srcSentence">BYOK and logging work seamlessly with every application that integrates with Azure RMS.</caps:sentence>
            <caps:sentence id="src65" class="srcSentence"> This includes cloud services such as SharePoint Online, on-premises servers that run Exchange and SharePoint that work with Azure RMS by using the RMS connector, and client applications such as Office 2013.</caps:sentence>
            <caps:sentence id="src66" class="srcSentence"> You will get key usage logs regardless of which application makes requests of Azure RMS.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src67" class="srcSentence">There is one exception: Currently, <embeddedLabel>Azure RMS BYOK is not compatible with Exchange Online</embeddedLabel>.</caps:sentence>
            <caps:sentence id="src68" class="srcSentence">  If you want to use Exchange Online, we recommend that you deploy Azure RMS in the default key management mode now, where Microsoft generates and manages your key.</caps:sentence>
            <caps:sentence id="src69" class="srcSentence"> You have the option to move to BYOK later, for example, when Exchange Online does support Azure RMS BYOK.</caps:sentence>
            <caps:sentence id="src70" class="srcSentence"> However, if you cannot wait, another option is to deploy Azure RMS with BYOK now, with reduced RMS functionality for Exchange Online (unprotected emails and unprotected attachments remain fully functional):</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src71" class="srcSentence">Protected emails or protected attachments in Outlook Web Access cannot be displayed.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src72" class="srcSentence">Protected emails on mobile devices that use Exchange ActiveSync IRM cannot be displayed.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src73" class="srcSentence">Transport decryption (for example, to scan for malware) and journal  decryption is not possible, so protected emails and protected attachments will be skipped.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src74" class="srcSentence">Transport protection rules and data loss prevention (DLP) that enforce IRM policies is not possible, so RMS protection cannot be applied by using these methods.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src75" class="srcSentence">Server-based search for protected emails, so protected emails will be skipped.</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src76" class="srcSentence">When you use Azure RMS BYOK with reduced RMS functionality for Exchange Online, RMS will work with email clients in Outlook on Windows and Mac, and on other email clients that don't use Exchange ActiveSync IRM.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src77" class="srcSentence">If you are migrating to Azure RMS from AD RMS, you might have imported your key as a trusted publishing domain (TPD) to Exchange Online (also called BYOK in Exchange terminology, which is separate from Azure RMS BYOK).</caps:sentence>
            <caps:sentence id="src78" class="srcSentence"> In this scenario, you must remove the TPD from Exchange Online to avoid conflicting templates and policies.</caps:sentence>
            <caps:sentence id="src79" class="srcSentence"> For more information, see <externalLink><linkText>Remove-RMSTrustedPublishingDomain</linkText><linkUri>https://technet.microsoft.com/library/jj200720(v=exchg.150).aspx</linkUri></externalLink> from the Exchange Online cmdlets library.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src80" class="srcSentence">Sometimes, the Azure RMS BYOK  exception for Exchange Online is not a problem in practice.</caps:sentence>
            <caps:sentence id="src81" class="srcSentence"> For example, organizations that need BYOK and logging run their data applications (Exchange, SharePoint, Office) on-premises, and use Azure RMS for functionality that is not easily available with on-premises AD RMS (for example, collaboration with other companies and access from mobile clients).</caps:sentence>
            <caps:sentence id="src82" class="srcSentence"> Both BYOK and logging work well in this scenario and allow the organization to have full control over their Azure RMS subscription.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_ImplementBYOK">
        <title>
          <caps:sentence id="src83" class="srcSentence">Implementing bring your own key (BYOK)</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src84" class="srcSentence">Use the information and procedures in this section if you have decided to generate and manage your tenant key; the bring your own key (BYOK) scenario:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_Preqs">Prerequisites for BYOK</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_BYOK_Internet">Generate and transfer your tenant key – over the Internet</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src85" class="srcSentence">
                  <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_BYOK_InPerson">Generate and transfer your tenant key – in person</link> </caps:sentence>
              </para>
            </listItem>
          </list>
          <alert class="important">
            <para>
              <caps:sentence id="src86" class="srcSentence">If you have already started to use <token>aad_rightsmanagement_1</token> (the service is activated) and you have users who run Office 2010, contact Microsoft Customer Support Services (CSS) before you run these procedures.</caps:sentence>
              <caps:sentence id="src87" class="srcSentence"> Depending on your scenario and requirements, you can still use BYOK but with some limitations or additional steps.</caps:sentence>
            </para>
            <para>
              <caps:sentence id="src88" class="srcSentence">Also contact CSS if your organization has specific policies for handling keys.</caps:sentence>
            </para>
          </alert>
        </content>
        <sections>
          <section address="BKMK_Preqs">
            <title>
              <caps:sentence id="src89" class="srcSentence">Prerequisites for BYOK</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src90" class="srcSentence">See the following table for a list of prerequisites for bring your own key (BYOK).</caps:sentence>
              </para>
              <table>
                <thead>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src91" class="srcSentence">Requirement</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src92" class="srcSentence">More information</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src93" class="srcSentence">A subscription that supports Azure RMS</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src94" class="srcSentence">For more information about the available subscriptions, see the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link> section in the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link> topic.</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src95" class="srcSentence">You do not use RMS for individuals or Exchange Online.</caps:sentence>
                        <caps:sentence id="src96" class="srcSentence"> Or, if you use Exchange Online, you understand and accept the limitations of using BYOK with this configuration.</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src97" class="srcSentence">For more information about the restrictions and current limitations for BYOK, see the <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_Pricing">BYOK pricing and restrictions</link> section in this topic.</caps:sentence>
                      </para>
                      <alert class="important">
                        <para>
                          <caps:sentence id="src98" class="srcSentence">Currently, BYOK is not compatible with Exchange Online.</caps:sentence>
                        </para>
                      </alert>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src99" class="srcSentence">Thales HSM, smartcards, and support software</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src100" class="srcSentence">If you are migrating from AD RMS to Azure RMS by using software key to hardware key, you must have a minimum version of 11.62 for the Thales drivers.</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src101" class="srcSentence">You must have access to a Thales Hardware Security Module and basic operational knowledge of Thales HSMs.</caps:sentence>
                        <caps:sentence id="src102" class="srcSentence"> See <externalLink><linkText>Thales Hardware Security Module</linkText><linkUri>http://www.thales-esecurity.com/msrms/buy</linkUri></externalLink> for the list of compatible models, or to purchase an HSM if you do not have one.</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src103" class="srcSentence">If you want to transfer your tenant key over the Internet rather than physically be present in Redmond, USA:</caps:sentence>
                      </para>
                      <list class="ordered">
                        <listItem>
                          <para>
                            <caps:sentence id="src104" class="srcSentence">An offline x64 workstation with a minimum Windows operation system of Windows 7 and Thales nShield software that is at least version 11.62.</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence id="src105" class="srcSentence">If this workstation runs Windows 7, you must <externalLink><linkText>install Microsoft .NET Framework 4.5</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=225702</linkUri></externalLink>.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src106" class="srcSentence">A workstation that is connected to the Internet and has a minimum Windows operation system of Windows 7.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src107" class="srcSentence">A USB drive or other portable storage device that has at least 16 MB free space.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src108" class="srcSentence">These prerequisites are not required if you travel to Redmond and transfer your tenant key in person.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src109" class="srcSentence">For security reasons, we recommend that the first workstation is not connected to a network.</caps:sentence>
                        <caps:sentence id="src110" class="srcSentence"> However, this is not programmatically enforced.</caps:sentence>
                      </para>
                      <alert class="note">
                        <para>
                          <caps:sentence id="src111" class="srcSentence">In the instructions that follow, this workstation is referred to as the disconnected workstation.</caps:sentence>
                        </para>
                      </alert>
                      <para>
                        <caps:sentence id="src112" class="srcSentence">In addition, if your tenant key is for a production network, we recommend that you use a second, separate workstation to download the toolset and upload the tenant key.</caps:sentence>
                        <caps:sentence id="src113" class="srcSentence"> But for testing purposes, you can use the same workstation as the first one.</caps:sentence>
                      </para>
                      <alert class="note">
                        <para>
                          <caps:sentence id="src114" class="srcSentence">In the instructions that follow, this second workstation is referred to as the Internet-connected workstation.</caps:sentence>
                        </para>
                      </alert>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src115" class="srcSentence">Optional: Azure subscription </caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src116" class="srcSentence">If you want to log your tenant key usage (and Rights Management usage), you must have a subscription to Azure and sufficient storage on Azure to store your logs.</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </tbody>
              </table>
              <para>
                <caps:sentence id="src117" class="srcSentence">The procedures to generate and use your own tenant key depend on whether you want to do this over the Internet or in person:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src118" class="srcSentence">
                      <legacyBold>Over the Internet:</legacyBold> This requires some extra configuration steps, such as downloading and using a toolset and Windows PowerShell cmdlets.</caps:sentence>
                    <caps:sentence id="src119" class="srcSentence"> However, you do not have to physically be in a Microsoft facility to transfer your tenant key.</caps:sentence>
                    <caps:sentence id="src120" class="srcSentence"> Security is maintained by the following methods:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src121" class="srcSentence">You generate the tenant key from an offline workstation, which reduces the attack surface.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src122" class="srcSentence">The tenant key is encrypted with a Key Exchange Key (KEK), which stays encrypted until it is transferred to the Azure RMS HSMs.</caps:sentence>
                        <caps:sentence id="src123" class="srcSentence"> Only the encrypted version of your tenant key leaves the original workstation.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src124" class="srcSentence">A tool sets properties on your tenant key that binds your tenant key to the Azure RMS security world.</caps:sentence>
                        <caps:sentence id="src125" class="srcSentence"> So after the Azure RMS HSMs receive and decrypt your tenant key, only these HSMs can use it.</caps:sentence>
                        <caps:sentence id="src126" class="srcSentence"> Your tenant key cannot be exported.</caps:sentence>
                        <caps:sentence id="src127" class="srcSentence"> This binding is enforced by the Thales HSMs.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src128" class="srcSentence">The Key Exchange Key (KEK) that is used to encrypt your tenant key is generated inside the Azure RMS HSMs and is not exportable.</caps:sentence>
                        <caps:sentence id="src129" class="srcSentence"> The HSMs enforce that there can be no clear version of the KEK outside the HSMs.</caps:sentence>
                        <caps:sentence id="src130" class="srcSentence"> In addition, the toolset includes attestation from Thales that the KEK is not exportable and was generated inside a genuine HSM that was manufactured by Thales.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src131" class="srcSentence">The toolset includes attestation from Thales that the Azure RMS security world was also generated on a genuine HSM manufactured by Thales.</caps:sentence>
                        <caps:sentence id="src132" class="srcSentence"> This proves to you that Microsoft is using genuine hardware.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src133" class="srcSentence">Microsoft uses separate KEKs as well as separate Security Worlds in each geographical region, which ensures that your tenant key can be used only in data centers in the region in which you encrypted it.</caps:sentence>
                        <caps:sentence id="src134" class="srcSentence"> For example, a tenant key from a European customer cannot be used in data centers in North American or Asia.</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <alert class="note">
                    <para>
                      <caps:sentence id="src135" class="srcSentence">Your tenant key can safely move through untrusted computers and networks because it is encrypted and secured with access control level permissions, which makes it usable only within your HSMs and Microsoft’s HSMs for Azure RMS.</caps:sentence>
                      <caps:sentence id="src136" class="srcSentence"> You can use the scripts that are provided in the toolset to verify the security measures and read more information about how this works from Thales: <externalLink><linkText>Hardware Key management in the RMS Cloud</linkText><linkUri>https://www.thales-esecurity.com/knowledge-base/white-papers/hardware-key-management-in-the-rms-cloud</linkUri></externalLink>.</caps:sentence>
                    </para>
                  </alert>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src137" class="srcSentence">
                      <legacyBold>In person:</legacyBold> This requires that you contact Microsoft Customer Support Services (CSS) to schedule a key transfer appointment for Azure RMS.</caps:sentence>
                    <caps:sentence id="src138" class="srcSentence"> You must travel to a Microsoft office in Redmond, Washington, United States of America to transfer your tenant key to the Azure RMS security world.</caps:sentence>
                  </para>
                </listItem>
              </list>
            </content>
          </section>
          <section address="BKMK_BYOK_Internet" expanded="false">
            <title>
              <caps:sentence id="src139" class="srcSentence">Generate and transfer your tenant key – over the Internet</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src140" class="srcSentence">Use the following procedures if you want to transfer your tenant key over the Internet rather than travel to a Microsoft facility to transfer the tenant key in person: </caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetPrepareWorkstation">Prepare your Internet-connected workstation</link>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_DisconnectedPrepareWorkstation">Prepare your disconnected workstation</link>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetGenerate">Generate your tenant key</link>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetPrepareTransfer">Prepare your tenant key for transfer</link>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetTransfer">Transfer your tenant key to Azure RMS</link>
                  </para>
                </listItem>
              </list>
            </content>
            <sections>
              <section address="BKMK_InternetPrepareWorkstation">
                <title>
                  <caps:sentence id="src141" class="srcSentence">Prepare your Internet-connected workstation</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence id="src142" class="srcSentence">To prepare your workstation that is connected to the Internet, follow these 3 steps:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_PrepareInternetConnectedWorkstation1">Step 1: Install Windows PowerShell for Azure Rights Management</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_PrepareInternetConnectedWorkstation2">Step 2: Get your Azure Active Directory tenant ID</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_PrepareInternetConnectedWorkstation3">Step 3: Download the BYOK toolset</link>
                      </para>
                    </listItem>
                  </list>
                </content>
                <sections>
                  <section address="BKMK_PrepareInternetConnectedWorkstation1">
                    <title>
                      <caps:sentence id="src143" class="srcSentence">Step 1: Install Windows PowerShell for Azure Rights Management</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src144" class="srcSentence">From the Internet-connected workstation, download and install the Windows PowerShell module for Azure Rights Management.</caps:sentence>
                      </para>
                      <alert class="note">
                        <para>
                          <caps:sentence id="src145" class="srcSentence">If you have previously downloaded this Windows PowerShell module, run the following command to check that your version number is at least 2.1.0.0: <codeInline>(Get-Module aadrm -ListAvailable).Version</codeInline> </caps:sentence>
                        </para>
                      </alert>
                      <para>
                        <caps:sentence id="src146" class="srcSentence">For installation instructions, see <link xlink:href="0d665ed6-b1de-4d63-854a-bc57c1c49844">Installing Windows PowerShell for Azure Rights Management</link>.</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_PrepareInternetConnectedWorkstation2">
                    <title>
                      <caps:sentence id="src147" class="srcSentence">Step 2: Get your Azure Active Directory tenant ID</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src148" class="srcSentence">Start Windows PowerShell with the <ui>Run as administrator</ui> option, and then run the following commands:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src149" class="srcSentence">Use the <externalLink><linkText>Connect-AadrmService</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629415.aspx</linkUri></externalLink> cmdlet to connect to the Azure RMS service:</caps:sentence>
                          </para>
                          <code>Connect-AadrmService</code>
                          <para>
                            <caps:sentence id="src150" class="srcSentence">When prompted, enter your <token>aad_rightsmanagement_1</token> tenant administrator credentials (typically, you will use an account that is a global administrator for Azure Active Directory or Office 365).</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src151" class="srcSentence">Use the <externalLink><linkText>Get-AadrmConfiguration</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629410.aspx</linkUri></externalLink> cmdlet to display the configuration of your tenant:</caps:sentence>
                          </para>
                          <code>Get-AadrmConfiguration</code>
                          <para>
                            <caps:sentence id="src152" class="srcSentence">From the output, save the GUID from the first line (BPOSId).</caps:sentence>
                            <caps:sentence id="src153" class="srcSentence"> This is your Azure Active Directory tenant ID, which you will need later when you prepare your tenant key for upload.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src154" class="srcSentence">Use the <externalLink><linkText>Disconnect-AadrmService</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629416.aspx</linkUri></externalLink> cmdlet to disconnect from the Azure RMS service until you are ready to upload your key:</caps:sentence>
                          </para>
                          <code>Disconnect-AadrmService</code>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence id="src155" class="srcSentence">Do not close the Windows PowerShell window.</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_PrepareInternetConnectedWorkstation3">
                    <title address="BKMK_PrepareWorkstationInternetKey2">
                      <caps:sentence id="src156" class="srcSentence">Step 3: Download the BYOK toolset</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src157" class="srcSentence">Go to the Microsoft Download Center and <externalLink><linkText>download the BYOK toolset</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=335781</linkUri></externalLink> for your region:</caps:sentence>
                      </para>
                      <table>
                        <thead>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence id="src158" class="srcSentence">Region</caps:sentence>
                              </para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src159" class="srcSentence">Package name</caps:sentence>
                              </para>
                            </TD>
                          </tr>
                        </thead>
                        <tbody>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence id="src160" class="srcSentence">North America</caps:sentence>
                              </para>
                              <para></para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src161" class="srcSentence">AzureRMS-BYOK-tools-UnitedStates.zip</caps:sentence>
                              </para>
                            </TD>
                          </tr>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence id="src162" class="srcSentence">Europe</caps:sentence>
                              </para>
                              <para></para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src163" class="srcSentence">AzureRMS-BYOK-tools-Europe.zip</caps:sentence>
                              </para>
                            </TD>
                          </tr>
                          <tr>
                            <TD>
                              <para>
                                <caps:sentence id="src164" class="srcSentence">Asia</caps:sentence>
                              </para>
                              <para></para>
                            </TD>
                            <TD>
                              <para>
                                <caps:sentence id="src165" class="srcSentence">AzureRMS-BYOK-tools-AsiaPacific.zip</caps:sentence>
                              </para>
                            </TD>
                          </tr>
                        </tbody>
                      </table>
                      <para>
                        <caps:sentence id="src166" class="srcSentence">The toolset includes the following :</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src167" class="srcSentence">A Key Exchange Key (KEK) package that has a name beginning with <ui>BYOK-KEK-pkg-</ui>.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src168" class="srcSentence">A Security World package that has a name beginning with <ui>BYOK-SecurityWorld-pkg-</ui>.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src169" class="srcSentence">A python script named <ui>verifykeypackage.py</ui>.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src170" class="srcSentence">A command-line executable file named <ui>KeyTransferRemote.exe</ui>, a metadata file named <ui>KeyTransferRemote.exe.config</ui>, and associated DLLs.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src171" class="srcSentence">A Visual C++ Redistributable Package, named <ui>vcredist_x64.exe</ui>.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence id="src172" class="srcSentence">Copy the package to a USB drive or other portable storage.</caps:sentence>
                      </para>
                    </content>
                  </section>
                </sections>
              </section>
              <section address="BKMK_DisconnectedPrepareWorkstation">
                <title>
                  <caps:sentence id="src173" class="srcSentence">Prepare your disconnected workstation</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence id="src174" class="srcSentence">To prepare your workstation that is not connected to a network (either the Internet or your internal network), follow these 2 steps:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_PrepareDisconnectedWorkstation1">Step 1: Prepare the disconnected workstation with Thales HSM</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_PrepareDisconnectedWorkstation2">Step 2: Install the BYOK toolset on the disconnected workstation</link>
                      </para>
                    </listItem>
                  </list>
                </content>
                <sections>
                  <section address="BKMK_PrepareDisconnectedWorkstation1">
                    <title address="BKMK_PrepareWorkstationInternetKey1">
                      <caps:sentence id="src175" class="srcSentence">Step 1: Prepare the disconnected workstation with Thales HSM</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src176" class="srcSentence">On the disconnected workstation, install the nCipher (Thales) support software on a Windows computer, and then attach a Thales HSM to that computer.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src177" class="srcSentence">Ensure that the Thales tools are in your path <system>(%nfast_home%\bin</system> and <system>%nfast_home%\python\bin</system>).</caps:sentence>
                        <caps:sentence id="src178" class="srcSentence"> For example, type the following:</caps:sentence>
                      </para>
                      <code>set PATH=%PATH%;”%nfast_home%\bin”;”%nfast_home%\python\bin”</code>
                      <para>
                        <caps:sentence id="src179" class="srcSentence">For more information, see the user guide included with the Thales HSM, or visit the Thales website for Azure RMS at <externalLink><linkText>http://www.thales-esecurity.com/msrms/cloud</linkText><linkUri>http://www.thales-esecurity.com/msrms/cloud</linkUri></externalLink>.</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_PrepareDisconnectedWorkstation2">
                    <title>
                      <caps:sentence id="src180" class="srcSentence">Step 2: Install the BYOK toolset on the disconnected workstation</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src181" class="srcSentence">Copy the BYOK toolset package from the USB drive or other portable storage, and then do the following:</caps:sentence>
                      </para>
                      <list class="ordered">
                        <listItem>
                          <para>
                            <caps:sentence id="src182" class="srcSentence">Extract the files from the downloaded package into any folder.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src183" class="srcSentence">From that folder, run vcredist_x64.exe.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src184" class="srcSentence">Follow the instructions to the install the Visual C++ runtime components for Visual Studio 2012.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </content>
                  </section>
                </sections>
              </section>
              <section address="BKMK_InternetGenerate">
                <title>
                  <caps:sentence id="src185" class="srcSentence">Generate your tenant key</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence id="src186" class="srcSentence">On the disconnected workstation, following these 3 steps to generate your own tenant key: </caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetGenerate1">Step 1: Create a security world</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetGenerate2">Step 2: Validate the downloaded package</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetGenerate3">Step 3: Create a new key</link>
                      </para>
                    </listItem>
                  </list>
                </content>
                <sections>
                  <section address="BKMK_InternetGenerate1">
                    <title>
                      <caps:sentence id="src187" class="srcSentence">Step 1: Create a security world</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src188" class="srcSentence">Start a command prompt and run the Thales new-world program.</caps:sentence>
                      </para>
                      <code>new-world.exe --initialize --cipher-suite=DLf1024s160mRijndael --module=1 --acs-quorum=2/3
</code>
                      <para>
                        <caps:sentence id="src189" class="srcSentence">This program creates a <embeddedLabel>Security World</embeddedLabel> file at %NFAST_KMDATA%\local\world, which corresponds to the C:\ProgramData\nCipher\Key Management Data\local folder.</caps:sentence>
                        <caps:sentence id="src190" class="srcSentence"> You can use different values for the quorum but in our example, you’re prompted to enter three blank cards and pins for each one.</caps:sentence>
                        <caps:sentence id="src191" class="srcSentence"> Then, any two cards will be required to have administrative access to the security world (your specified quorum).</caps:sentence>
                        <caps:sentence id="src192" class="srcSentence">  These cards become the <embeddedLabel>Administrator Card Set</embeddedLabel> for the new security world.</caps:sentence>
                        <caps:sentence id="src193" class="srcSentence"> At this stage, you can specify the password or PIN for each ACS card, or add it later with a command.</caps:sentence>
                      </para>
                      <alert class="tip">
                        <para>
                          <caps:sentence id="src194" class="srcSentence">You can verify the current configuration status of your HSM by using the <codeInline>nkminfo</codeInline> command.</caps:sentence>
                        </para>
                      </alert>
                      <para>
                        <caps:sentence id="src195" class="srcSentence">Then do the following:</caps:sentence>
                      </para>
                      <list class="ordered">
                        <listItem>
                          <para>
                            <caps:sentence id="src196" class="srcSentence">Install the Thales CNG provider as described in the Thales documentation, and configure it to use the new security world.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src197" class="srcSentence">Back up the world file in <embeddedLabel>%nfast_kmdata%\local</embeddedLabel>.</caps:sentence>
                            <caps:sentence id="src198" class="srcSentence"> Secure and protect the world file, the Administrator Cards, and their pins, and make sure that no single person has access to more than one card.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </content>
                  </section>
                  <section address="BKMK_InternetGenerate2">
                    <title>
                      <caps:sentence id="src199" class="srcSentence">Step 2: Validate the downloaded package</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src200" class="srcSentence">This step is optional but recommended so that you can validate the following:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src201" class="srcSentence">The Key Exchange Key that is included in the toolset has been generated from a genuine Thales HSM.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src202" class="srcSentence">The hash of the Azure RMS Security World that is included in the toolset has been generated in a genuine Thales HSM.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src203" class="srcSentence">The Key Exchange Key is non-exportable.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <alert class="note">
                        <para>
                          <caps:sentence id="src204" class="srcSentence">To validate the downloaded package, the HSM must be connected, powered on, and must have a security world on it (such as the one you’ve just created).</caps:sentence>
                        </para>
                      </alert>
                      <procedure>
                        <title>
                          <caps:sentence id="src205" class="srcSentence">To validate the downloaded package</caps:sentence>
                        </title>
                        <steps class="ordered">
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src206" class="srcSentence">Run the verifykeypackage.py script by tying one of the following, depending on your region:</caps:sentence>
                              </para>
                              <list class="bullet">
                                <listItem>
                                  <para>
                                    <caps:sentence id="src207" class="srcSentence">For North America:</caps:sentence>
                                  </para>
                                  <code>python verifykeypackage.py -k BYOK-KEK-pkg-NA-1 -w BYOK-SecurityWorld-pkg-NA-1</code>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence id="src208" class="srcSentence">For Europe:</caps:sentence>
                                  </para>
                                  <code>python verifykeypackage.py -k BYOK-KEK-pkg-EU-1 -w BYOK-SecurityWorld-pkg-EU-1</code>
                                </listItem>
                                <listItem>
                                  <para>
                                    <caps:sentence id="src209" class="srcSentence">For Asia:</caps:sentence>
                                  </para>
                                  <code>python verifykeypackage.py -k BYOK-KEK-pkg-AP-1 -w BYOK-SecurityWorld-pkg-AP-1</code>
                                </listItem>
                              </list>
                              <alert class="tip">
                                <para>
                                  <caps:sentence id="src210" class="srcSentence">The Thales software includes a Python interpreter at %NFAST_HOME%\python\bin</caps:sentence>
                                </para>
                              </alert>
                            </content>
                          </step>
                          <step>
                            <content>
                              <para>
                                <caps:sentence id="src211" class="srcSentence">Confirm that you see the following, which indicates successful validation: <ui>Result:  SUCCESS</ui></caps:sentence>
                              </para>
                            </content>
                          </step>
                        </steps>
                        <conclusion>
                          <content>
                            <para>
                              <caps:sentence id="src212" class="srcSentence">This script validates the signer chain up to the Thales root key.</caps:sentence>
                              <caps:sentence id="src213" class="srcSentence"> The hash of this root key is embedded in the script and its value should be <ui>59178a47 de508c3f 291277ee 184f46c4 f1d9c639</ui>.</caps:sentence>
                              <caps:sentence id="src214" class="srcSentence"> You can also confirm this value separately by visiting the <externalLink><linkText>Thales website</linkText><linkUri>http://www.thalesesec.com/</linkUri></externalLink>.</caps:sentence>
                            </para>
                          </content>
                        </conclusion>
                      </procedure>
                      <para>
                        <caps:sentence id="src215" class="srcSentence">You’re now ready to create a new key that will be your RMS tenant key.</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_InternetGenerate3">
                    <title>
                      <caps:sentence id="src216" class="srcSentence">Step 3: Create a new key</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src217" class="srcSentence">Generate a CNG key by using the Thales <userInputLocalizable>generatekey</userInputLocalizable> and <userInputLocalizable>cngimport</userInputLocalizable> programs.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src218" class="srcSentence">Run the following command to generate the key:</caps:sentence>
                      </para>
                      <code>generatekey --generate simple type=RSA size=2048 protect=module ident=contosokey plainname=contosokey nvram=no pubexp=
</code>
                      <para>
                        <caps:sentence id="src219" class="srcSentence">When you run this command, use these instructions:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src220" class="srcSentence">For the key size, we recommend 2048 but also support 1024-bit RSA keys for existing AD RMS customers who have such keys and are migrating to Azure RMS.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src221" class="srcSentence">Replace the value of <placeholder>contosokey</placeholder> for the <ui>ident</ui> and <ui>plainname</ui> with any string value.</caps:sentence>
                            <caps:sentence id="src222" class="srcSentence"> To minimize administrative overheads and reduce the risk of errors, we recommend that you use the same value for both, and use all lower case characters.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src223" class="srcSentence">The pubexp is left blank (default) in this example, but you can specify specific values.</caps:sentence>
                            <caps:sentence id="src224" class="srcSentence"> For more information, see the Thales documentation.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence id="src225" class="srcSentence">Then run the following command to import the key to CNG:</caps:sentence>
                      </para>
                      <code>cngimport --import -M --key=contosokey --appname=simple contosokey</code>
                      <para>
                        <caps:sentence id="src226" class="srcSentence">When you run this command, use these instructions:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src227" class="srcSentence">Replace <placeholder>contosokey</placeholder> with the same value that you specified in <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetGenerate1">Step 1: Create a security world</link> from the <legacyItalic>Generate your tenant key</legacyItalic> section.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src228" class="srcSentence">Use the <ui>-M</ui> option so that the key is suitable for this scenario.</caps:sentence>
                            <caps:sentence id="src229" class="srcSentence"> Without this, the resultant key will be a user-specific key for the current user.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence id="src230" class="srcSentence">This command creates a Tokenized Key file in your %NFAST_KMDATA%\local folder with a name starting with <ui>key_caping_</ui> followed by a SID.</caps:sentence>
                        <caps:sentence id="src231" class="srcSentence"> For example: <system>key_caping_machine--801c1a878c925fd9df4d62ba001b94701c039e2fb</system>.</caps:sentence>
                        <caps:sentence id="src232" class="srcSentence"> This file contains an encrypted key.</caps:sentence>
                      </para>
                      <alert class="tip">
                        <para>
                          <caps:sentence id="src233" class="srcSentence">You can see the current configuration status of your keys by using the <codeInline>nkminfo –k</codeInline> command.</caps:sentence>
                        </para>
                      </alert>
                      <para>
                        <caps:sentence id="src234" class="srcSentence">Back up this Tokenized Key File in a safe location.</caps:sentence>
                      </para>
                      <alert class="important">
                        <para>
                          <caps:sentence id="src235" class="srcSentence">When you later transfer your key to Azure RMS, Microsoft cannot export this key back to you so it becomes extremely important that you back up your key and security world safely.</caps:sentence>
                          <caps:sentence id="src236" class="srcSentence"> Contact Thales for guidance and best practices for backing up your key.</caps:sentence>
                        </para>
                      </alert>
                      <para>
                        <caps:sentence id="src237" class="srcSentence">You are now ready to transfer your tenant key to Azure RMS.</caps:sentence>
                      </para>
                    </content>
                  </section>
                </sections>
              </section>
              <section address="BKMK_InternetPrepareTransfer">
                <title>
                  <caps:sentence id="src238" class="srcSentence">Prepare your tenant key for transfer</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence id="src239" class="srcSentence">On the disconnected workstation, following these 4 steps to prepare your own tenant key:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetPrepareTransfer1">Step 1: Create a copy of your key with reduced permissions</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetPrepareTransfer2">Step 2: Inspect the new copy of the key</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetPrepareTransfer3">Step 3: Encrypt your key by using Microsoft’s Key Exchange Key</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetPrepareTransfer4">Step 4: Copy your key transfer package to the Internet-connected workstation </link>
                      </para>
                    </listItem>
                  </list>
                </content>
                <sections>
                  <section address="BKMK_InternetPrepareTransfer1">
                    <title>
                      <caps:sentence id="src240" class="srcSentence">Step 1: Create a copy of your key with reduced permissions</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src241" class="srcSentence">To reduce the permissions on your tenant key, do the following: </caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src242" class="srcSentence">From a command prompt, run one of the following, depending on your region:</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence id="src243" class="srcSentence">For North America:</caps:sentence>
                              </para>
                              <code>KeyTransferRemote.exe -ModifyAcls -KeyAppName simple -KeyIdentifier contosokey -ExchangeKeyPackage BYOK-KEK-pkg-NA-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-NA-1</code>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src244" class="srcSentence">For Europe:</caps:sentence>
                              </para>
                              <code>KeyTransferRemote.exe -ModifyAcls -KeyAppName simple -KeyIdentifier contosokey -ExchangeKeyPackage BYOK-KEK-pkg-EU-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-EU-1</code>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src245" class="srcSentence">For Asia:</caps:sentence>
                              </para>
                              <code>KeyTransferRemote.exe -ModifyAcls -KeyAppName simple -KeyIdentifier contosokey -ExchangeKeyPackage BYOK-KEK-pkg-AP-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-AP-1</code>
                            </listItem>
                          </list>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence id="src246" class="srcSentence">When you run this command, replace <placeholder>contosokey</placeholder> with the same value you specified in <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetGenerate1">Step 1: Create a security world</link> from the <legacyItalic>Generate your tenant key</legacyItalic> section.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src247" class="srcSentence">You will be asked to plug in your security world ACS cards, and if specified, their password or PIN..</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src248" class="srcSentence">When the command completes, you will see <ui>Result: SUCCESS</ui> and the copy of your tenant key with reduced permissions will be in the file named key_xferacId_<placeholder>&lt;contosokey&gt;</placeholder>.</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_InternetPrepareTransfer2">
                    <title>
                      <caps:sentence id="src249" class="srcSentence">Step 2: Inspect the new copy of the key</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src250" class="srcSentence">Optionally, run the Thales utilities to confirm the minimal permissions on the new tenant key:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src251" class="srcSentence">aclprint.py:</caps:sentence>
                          </para>
                          <code>"%nfast_home%\bin\preload.exe" -m 1 -A xferacld -K contosokey "%nfast_home%\python\bin\python" "%nfast_home%\python\examples\aclprint.py"</code>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src252" class="srcSentence">kmfile-dump.exe:</caps:sentence>
                          </para>
                          <code>"%nfast_home%\bin\kmfile-dump.exe" "%NFAST_KMDATA%\local\key_xferacld_contosokey"
</code>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence id="src253" class="srcSentence">When you run these command, replace <placeholder>contosokey</placeholder> with the same value you specified in <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetGenerate1">Step 1: Create a security world</link> from the <legacyItalic>Generate your tenant key</legacyItalic> section.</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_InternetPrepareTransfer3">
                    <title>
                      <caps:sentence id="src254" class="srcSentence">Step 3: Encrypt your key by using Microsoft’s Key Exchange Key</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src255" class="srcSentence">Run one of the following commands, depending on your region:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src256" class="srcSentence">For North America:</caps:sentence>
                          </para>
                          <code>KeyTransferRemote.exe -Package -KeyIdentifier <placeholder xmlns="">contosokey</placeholder> -ExchangeKeyPackage BYOK-KEK-pkg-NA-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-NA-1 -TenantBposId <placeholder xmlns="">GUID</placeholder> -KeyFriendlyName <placeholder xmlns="">ContosoFirstkey</placeholder></code>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src257" class="srcSentence">For Europe:</caps:sentence>
                          </para>
                          <code>KeyTransferRemote.exe -Package -KeyIdentifier <placeholder xmlns="">contosokey</placeholder> -ExchangeKeyPackage BYOK-KEK-pkg-EU-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-EU-1 -TenantBposId <placeholder xmlns="">GUID</placeholder> -KeyFriendlyName <placeholder xmlns="">ContosoFirstkey</placeholder></code>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src258" class="srcSentence">For Asia:</caps:sentence>
                          </para>
                          <code>KeyTransferRemote.exe -Package -KeyIdentifier <placeholder xmlns="">contosokey</placeholder> -ExchangeKeyPackage BYOK-KEK-pkg-AP-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-AP-1 -TenantBposId <placeholder xmlns="">GUID</placeholder> -KeyFriendlyName <placeholder xmlns="">ContosoFirstkey</placeholder></code>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence id="src259" class="srcSentence">When you run this command, use these instructions:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src260" class="srcSentence">Replace <placeholder>contosokey</placeholder> with the identifier that you used to generate the key in <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetGenerate1">Step 1: Create a security world</link> from the <legacyItalic>Generate your tenant key</legacyItalic> section.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src261" class="srcSentence">Replace <placeholder>GUID</placeholder> with your Azure Active Directory tenant ID that you retrieved in <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_PrepareInternetConnectedWorkstation2">Step 2: Get your Azure Active Directory tenant ID</link> from the <legacyItalic>Prepare your Internet-connected workstation</legacyItalic> section.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src262" class="srcSentence">Replace <placeholder>ContosoFirstKey</placeholder> with a label that will be used for your output file name.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence id="src263" class="srcSentence">When this completes successfully it displays <ui>Result: SUCCESS</ui> and there will be a new file in the current folder that has the following name: TransferPackage-<placeholder>ContosoFirstkey</placeholder>.byok</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_InternetPrepareTransfer4">
                    <title>
                      <caps:sentence id="src264" class="srcSentence">Step 4: Copy your key transfer package to the Internet-connected workstation </caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src265" class="srcSentence">Use a USB drive or other portable storage to copy the output file from the previous step (KeyTransferPackage-<placeholder>ContosoFirstkey</placeholder>.byok) to your Internet-connected workstation.</caps:sentence>
                      </para>
                      <alert class="security note">
                        <para>
                          <caps:sentence id="src266" class="srcSentence">Use security practices to protect the file because it includes your private key.</caps:sentence>
                        </para>
                      </alert>
                    </content>
                  </section>
                </sections>
              </section>
              <section address="BKMK_InternetTransfer">
                <title>
                  <caps:sentence id="src267" class="srcSentence">Transfer your tenant key to Azure RMS</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence id="src268" class="srcSentence">On the Internet-connected workstation,  follow these 3 steps To transfer your new tenant key to Azure RMS, :</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetTransfer1">Step 1: Connect to Azure RMS</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetTransfer2">Step 2: Upload the key package</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_InternetTransfer3">Step 3: Enumerate your tenant keys – as needed</link>
                      </para>
                    </listItem>
                  </list>
                </content>
                <sections>
                  <section address="BKMK_InternetTransfer1">
                    <title>
                      <caps:sentence id="src269" class="srcSentence">Step 1: Connect to Azure RMS</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src270" class="srcSentence">Return to the Windows PowerShell window and type the following: </caps:sentence>
                      </para>
                      <list class="ordered">
                        <listItem>
                          <para>
                            <caps:sentence id="src271" class="srcSentence">Reconnect to the <token>aad_rightsmanagement_1</token> service:</caps:sentence>
                          </para>
                          <code>Connect-AadrmService</code>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src272" class="srcSentence">Use the <externalLink><linkText>Get-AadrmKeys</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629420.aspx</linkUri></externalLink> cmdlet to see your current tenant key configuration:</caps:sentence>
                          </para>
                          <code>Get-AadrmKeys</code>
                        </listItem>
                      </list>
                    </content>
                  </section>
                  <section address="BKMK_InternetTransfer2">
                    <title>
                      <caps:sentence id="src273" class="srcSentence">Step 2: Upload the key package</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src274" class="srcSentence">Use the <externalLink><linkText>Add-AadrmKey</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629418.aspx</linkUri></externalLink> cmdlet to upload the key transfer package that you copied from the disconnected workstation:</caps:sentence>
                      </para>
                      <code>Add-AadrmKey –KeyFile &lt;PathToPackageFile&gt; -Verbose</code>
                      <alert class="warning">
                        <para>
                          <caps:sentence id="src275" class="srcSentence">You are prompted to confirm this action.</caps:sentence>
                          <caps:sentence id="src276" class="srcSentence"> It’s important to understand that this action cannot be undone.</caps:sentence>
                          <caps:sentence id="src277" class="srcSentence"> When you upload a tenant key, it automatically becomes your organization’s primary tenant key and users will start to use this tenant key when they protect documents and files.</caps:sentence>
                        </para>
                      </alert>
                      <para></para>
                      <para>
                        <caps:sentence id="src278" class="srcSentence">If the upload is successful, you will see the following message: <ui>The Rights management service successfully added the key.</ui></caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src279" class="srcSentence">Expect a replication delay for the change to propagate to all <token>aad_rightsmanagement_1</token> data centers.</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_InternetTransfer3">
                    <title>
                      <caps:sentence id="src280" class="srcSentence">Step 3: Enumerate your tenant keys – as needed</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src281" class="srcSentence">Use the Get-AadrmKeys cmdlet again to see the change in your tenant key, and whenever you want to see a list of your tenant keys.</caps:sentence>
                        <caps:sentence id="src282" class="srcSentence"> The tenant keys displayed include the initial tenant key that Microsoft generated for you, and any tenant keys that you added:</caps:sentence>
                      </para>
                      <code>Get-AadrmKeys</code>
                      <para>
                        <caps:sentence id="src283" class="srcSentence">The tenant key that is marked <ui>Active</ui> is the one that your organization is currently using to protect documents and files.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src284" class="srcSentence">You have now completed all the steps required for bring your own key over the Internet and can go to <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_NextSteps">Next steps</link>.</caps:sentence>
                      </para>
                    </content>
                  </section>
                </sections>
              </section>
            </sections>
          </section>
          <section address="BKMK_BYOK_InPerson" expanded="false">
            <title>
              <caps:sentence id="src285" class="srcSentence">Generate and transfer your tenant key – in person</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src286" class="srcSentence">Use the following procedures if you do not want to transfer your tenant key over the Internet, but instead, transfer your tenant key in person.</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_GenerateKey">Generate your tenant key</link>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_Transfer">Transfer your tenant key to Azure RMS</link>
                  </para>
                </listItem>
              </list>
            </content>
            <sections>
              <section address="BKMK_GenerateKey">
                <title>
                  <caps:sentence id="src287" class="srcSentence">Generate your tenant key</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence id="src288" class="srcSentence">To generate your own tenant key, follow these 3 steps: </caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_GenerateYourKey1">Step 1: Prepare a workstation with Thales HSM</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_GenerateYourKey2">Step 2: Create a security world</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_GenerateYourKey3">Step 3: Create a new key</link>
                      </para>
                    </listItem>
                  </list>
                </content>
                <sections>
                  <section address="BKMK_GenerateYourKey1">
                    <title>
                      <caps:sentence id="src289" class="srcSentence">Step 1: Prepare a workstation with Thales HSM</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src290" class="srcSentence">Install the nCipher (Thales) support software on a Windows computer.</caps:sentence>
                        <caps:sentence id="src291" class="srcSentence"> Attach a Thales HSM to that computer.</caps:sentence>
                        <caps:sentence id="src292" class="srcSentence"> Ensure the Thales tools are in your path.</caps:sentence>
                        <caps:sentence id="src293" class="srcSentence"> For more information, see the user guide included with the Thales HSM, or visit the Thales website for Azure RMS at <externalLink><linkText>http://www.thales-esecurity.com/msrms/cloud</linkText><linkUri>http://www.thales-esecurity.com/msrms/cloud</linkUri></externalLink>.</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_GenerateYourKey2">
                    <title>
                      <caps:sentence id="src294" class="srcSentence">Step 2: Create a security world</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src295" class="srcSentence">Start a command prompt and run the Thales new-world program.</caps:sentence>
                      </para>
                      <code>new-world.exe --initialize --cipher-suite=DLf1024s160mRijndael --module=1 --acs-quorum=2/3
</code>
                      <para>
                        <caps:sentence id="src296" class="srcSentence">This program creates a <embeddedLabel>Security World</embeddedLabel> file at %NFAST_KMDATA%\local\world, which corresponds to the C:\ProgramData\nCipher\Key Management Data\local folder.</caps:sentence>
                        <caps:sentence id="src297" class="srcSentence"> You can use different values for the quorum but in our example, you’re prompted to enter three blank cards and pins for each one.</caps:sentence>
                        <caps:sentence id="src298" class="srcSentence"> Then, any two cards will give full access to the security world.</caps:sentence>
                        <caps:sentence id="src299" class="srcSentence">  These cards become the <embeddedLabel>Administrator Card Set</embeddedLabel> for the new security world.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src300" class="srcSentence">Then do the following:</caps:sentence>
                      </para>
                      <list class="ordered">
                        <listItem>
                          <para>
                            <caps:sentence id="src301" class="srcSentence">Install the Thales CNG provider as described in the Thales documentation, and configure it to use the new security world.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src302" class="srcSentence">Back up the world file.</caps:sentence>
                            <caps:sentence id="src303" class="srcSentence"> Secure and protect the world file, the Administrator Cards, and their pins, and make sure that no single person has access to more than one card.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence id="src304" class="srcSentence">You’re now ready to create a new key that will be your RMS tenant key.</caps:sentence>
                      </para>
                    </content>
                  </section>
                  <section address="BKMK_GenerateYourKey3">
                    <title>
                      <caps:sentence id="src305" class="srcSentence">Step 3: Create a new key</caps:sentence>
                    </title>
                    <content>
                      <para>
                        <caps:sentence id="src306" class="srcSentence">Generate a CNG key by using the Thales <userInputLocalizable>generatekey</userInputLocalizable> and <userInputLocalizable>cngimport</userInputLocalizable> programs.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src307" class="srcSentence">Run the following command to generate the key:</caps:sentence>
                      </para>
                      <code>generatekey --generate simple type=RSA size=2048 protect=module ident=contosokey plainname=contosokey nvram=no pubexp=
</code>
                      <para>
                        <caps:sentence id="src308" class="srcSentence">When you run this command, use these instructions:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src309" class="srcSentence">For the key size, we recommend 2048 but also support 1024-bit RSA keys for existing AD RMS customers who have such keys and are migrating to Azure RMS.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src310" class="srcSentence">Replace the value of <placeholder>contosokey</placeholder> for the <ui>ident</ui> and <ui>plainname</ui> with any string value.</caps:sentence>
                            <caps:sentence id="src311" class="srcSentence"> To minimize administrative overheads and reduce the risk of errors, we recommend that you use the same value for both, and use all lower case characters.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src312" class="srcSentence">The pubexp is left blank (default) in this example, but you can specify specific values.</caps:sentence>
                            <caps:sentence id="src313" class="srcSentence"> For more information, see the Thales documentation.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence id="src314" class="srcSentence">Then run the following command to import the key to CNG:</caps:sentence>
                      </para>
                      <code>cngimport --import –M --key=contosokey --appname=simple contosokey</code>
                      <para>
                        <caps:sentence id="src315" class="srcSentence">When you run this command, use these instructions:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src316" class="srcSentence">Replace <placeholder>contosokey</placeholder> with the same value that you specified in Step 1.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src317" class="srcSentence">Use the <ui>-M</ui> option so that the key is suitable for this scenario.</caps:sentence>
                            <caps:sentence id="src318" class="srcSentence"> Without this, the resultant key will be a user-specific key for the current user.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <para>
                        <caps:sentence id="src319" class="srcSentence">This command creates a Tokenized Key file in your %NFAST_KMDATA%\local folder with a name starting with <ui>key_caping_</ui> followed by a SID.</caps:sentence>
                        <caps:sentence id="src320" class="srcSentence"> For example: <system>key_caping_machine--801c1a878c925fd9df4d62ba001b94701c039e2fb</system>.</caps:sentence>
                        <caps:sentence id="src321" class="srcSentence"> This file contains an encrypted key.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src322" class="srcSentence">Back up this Tokenized Key File in a safe location.</caps:sentence>
                      </para>
                      <alert class="important">
                        <para>
                          <caps:sentence id="src323" class="srcSentence">When you later transfer your key to Azure RMS, Microsoft will have a non-recoverable copy of your key.</caps:sentence>
                          <caps:sentence id="src324" class="srcSentence"> This means that nobody can retrieve your key from the HSMs at Microsoft.</caps:sentence>
                          <caps:sentence id="src325" class="srcSentence"> This allows you to retain exclusive control over your tenant key.</caps:sentence>
                          <caps:sentence id="src326" class="srcSentence"> Therefore it becomes extremely important that you back up your key and security world safely.</caps:sentence>
                          <caps:sentence id="src327" class="srcSentence"> Contact Thales for guidance and best practices for backing up your key.</caps:sentence>
                        </para>
                      </alert>
                      <para>
                        <caps:sentence id="src328" class="srcSentence">You are now ready to transfer your tenant key to Azure RMS.</caps:sentence>
                      </para>
                    </content>
                  </section>
                </sections>
              </section>
              <section address="BKMK_Transfer">
                <title>
                  <caps:sentence id="src329" class="srcSentence">Transfer your tenant key to Azure RMS</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence id="src330" class="srcSentence">After you have generated your own key, you must transfer it to Azure RMS before you use it.</caps:sentence>
                    <caps:sentence id="src331" class="srcSentence"> For the highest level of security, this transfer is a manual process that requires you to fly to the Microsoft office in Redmond, Washington, United States of America.</caps:sentence>
                    <caps:sentence id="src332" class="srcSentence"> To complete this process, follow these 3 steps:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_TransferYourKey1">Step 1: Bring your key to Microsoft</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_TransferYourKey2">Step 2: Transfer your key to the Window Azure RMS security world</link>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_TransferYourKey3">Step 3: Closing procedures</link>
                      </para>
                    </listItem>
                  </list>
                  <procedure address="BKMK_TransferYourKey1">
                    <title>
                      <caps:sentence id="src333" class="srcSentence">Step 1: Bring your key to Microsoft</caps:sentence>
                    </title>
                    <steps class="bullet">
                      <step>
                        <content>
                          <para>
                            <caps:sentence id="src334" class="srcSentence">Contact Microsoft Customer Support Services (CSS) to schedule a key transfer appointment for Azure RMS.</caps:sentence>
                            <caps:sentence id="src335" class="srcSentence"> Bring the following to Microsoft in Redmond:</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence id="src336" class="srcSentence">A quorum of your Administrative Cards.</caps:sentence>
                                <caps:sentence id="src337" class="srcSentence"> If you followed the previous instructions in <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_GenerateYourKey2">Step 2: Create a security world</link>, these are any two of your three cards.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src338" class="srcSentence">Personnel authorized to carry your Administrative Cards and pins, typically two (one for each card).</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src339" class="srcSentence">Your Security World file (%NFAST_KMDATA%\local\world) on a USB drive.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src340" class="srcSentence">Your Tokenized Key File on a USB drive.</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </content>
                      </step>
                    </steps>
                  </procedure>
                  <procedure address="BKMK_TransferYourKey2">
                    <title>
                      <caps:sentence id="src341" class="srcSentence">Step 2: Transfer your key to the Window Azure RMS security world</caps:sentence>
                    </title>
                    <steps class="ordered">
                      <step>
                        <content>
                          <para>
                            <caps:sentence id="src342" class="srcSentence">When you arrive at Microsoft to transfer your key, the following happens:</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence id="src343" class="srcSentence">Microsoft provides you with an offline workstation that has a Thales HSM attached, Thales software installed, and a Azure RMS Security World file pre-loaded into the folder C:\Temp\Destination.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src344" class="srcSentence">On this workstation, you load your Security World file and Tokenized Key File from your USB drive into the C:\Temp\Source folder.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src345" class="srcSentence">Azure RMS operators securely transfer your key to the Azure RMS security world by using Thales utilities.</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                          <para>
                            <caps:sentence id="src346" class="srcSentence">This process will look similar to the following, where the last parameter of key-xfer-im in this example is replaced by your Tokenized Key File name:</caps:sentence>
                          </para>
                          <para>
                            <ui>
                              <caps:sentence id="src347" class="srcSentence">C:\&gt; mk-reprogram.exe --owner c:\Temp\Destination add c:\Temp\Source</caps:sentence>
                            </ui>
                          </para>
                          <para>
                            <ui>
                              <caps:sentence id="src348" class="srcSentence">C:\&gt; key-xfer-im.exe c:\Temp\Source c:\Temp\Destination --module c:\Temp\Source\key_caping_machine--801c1a878c925fd9df4d62ba001b94701c039e2fb</caps:sentence>
                            </ui>
                          </para>
                        </content>
                      </step>
                      <step>
                        <content>
                          <para>
                            <caps:sentence id="src349" class="srcSentence">Mk-reprogram will ask you and the Azure RMS operators to plug in their respective Administrator cards and pins.</caps:sentence>
                            <caps:sentence id="src350" class="srcSentence"> These commands output a Tokenized Key File in C:\Temp\Destination that contains your key protected by Azure RMS security world.</caps:sentence>
                          </para>
                        </content>
                      </step>
                    </steps>
                  </procedure>
                  <procedure address="BKMK_TransferYourKey3">
                    <title>
                      <caps:sentence id="src351" class="srcSentence">Step 3: Closing procedures</caps:sentence>
                    </title>
                    <steps class="bullet">
                      <step>
                        <content>
                          <para>
                            <caps:sentence id="src352" class="srcSentence">In your presence, Azure RMS operators do the following:</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence id="src353" class="srcSentence">Run a tool that Microsoft developed in collaboration with Thales that removes two permissions: The permission to recover the key, and the permission to change permissions.</caps:sentence>
                                <caps:sentence id="src354" class="srcSentence"> After this is done, this copy of your key is locked to the Azure RMS security world.</caps:sentence>
                                <caps:sentence id="src355" class="srcSentence"> Thales HSMs will not allow Azure RMs operators with their Administrator cards to recover the plaintext copy of your key.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src356" class="srcSentence">Copy the resulting key file to a USB drive to later upload to the Azure RMS service.</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src357" class="srcSentence">Factory-reset the HSM, and wipe the workstation clean.</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </content>
                      </step>
                    </steps>
                  </procedure>
                  <para>
                    <caps:sentence id="src358" class="srcSentence">You have now completed all the steps required for bring your own key in person and can return to your organization for the next steps.</caps:sentence>
                  </para>
                </content>
              </section>
            </sections>
          </section>
        </sections>
      </section>
      <section address="BKMK_NextSteps">
        <title>
          <caps:sentence id="src359" class="srcSentence">Next steps</caps:sentence>
        </title>
        <content>
          <list class="ordered">
            <listItem>
              <para>
                <caps:sentence id="src360" class="srcSentence">Start to use your tenant key:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src361" class="srcSentence">If you haven’t already done so, you must now activate Rights Management so that your organization can start to use RMS.</caps:sentence>
                    <caps:sentence id="src362" class="srcSentence"> Users immediately start to use your tenant key (managed by Microsoft or managed by you).</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src363" class="srcSentence">For more information about activation, see <link xlink:href="f8707e01-b239-4d1a-a1ea-0d1cf9a8d214">Activating Azure Rights Management</link>.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src364" class="srcSentence">If you had already activated Rights Management and then decided to manage your own tenant key, users gradually transition from the old tenant key to the new tenant key, and this staggered transition can take a few weeks to complete.</caps:sentence>
                    <caps:sentence id="src365" class="srcSentence"> Documents and files that were protected with the old tenant key remains accessible to authorized users.</caps:sentence>
                  </para>
                </listItem>
              </list>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src366" class="srcSentence">Consider enabling usage logging, which logs every transaction that RMS performs.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src367" class="srcSentence">If you decided to manage your own tenant key, logging includes information about using your tenant key.</caps:sentence>
                <caps:sentence id="src368" class="srcSentence"> See the following example of a log file displayed in Excel where the <ui>Decrypt</ui> and <ui>SignDigest</ui> Request Types show that the tenant key is being used.</caps:sentence>
              </para>
              <mediaLink>
                <image xlink:href="6b958831-fba1-46b6-81c5-f20cf645927a"></image>
              </mediaLink>
              <para></para>
              <para>
                <caps:sentence id="src369" class="srcSentence">For more information about usage logging, see <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e">Log and analyze rights management usage</link>.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src370" class="srcSentence">Maintain your tenant key.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src371" class="srcSentence">For more information, see <link xlink:href="1284d0ee-0a72-45ba-a64c-3dcb25846c3d">Operations for your Rights Management Tenant Key</link>.</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="206a0bfe-0912-4e0e-aa15-484b000b264c">Configuring rights management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSSource>
</caps:SxS>