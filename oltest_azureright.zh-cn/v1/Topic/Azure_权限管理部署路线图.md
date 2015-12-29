---
description: na
keywords: na
pagetitle: Azure 权限管理部署路线图
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 086600c2-c5d8-47ec-a4c0-c782e1797486
---
# Azure 权限管理部署路线图
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="zh-CN">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="c6cf674d72a88f823f3d4684efae87fd" id="tgt1" class="tgtSentence">使用以下步骤为你的组织准备、实现和管理 Azure Rights Management (Azure RMS)。</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="12c30ae9131ee42486add94d60d64147" id="tgt2" class="tgtSentence">不过，如果你只是想要自己大致试用一下 Azure RMS，请不是将它部署在生产环境中，具体请参阅 <link xlink:href="1db923bf-7d19-4fdd-a413-bfeb58af5e03">Quick Start Tutorial for Azure Rights Management</link>。</caps:sentence>
        </para>
        <alert class="important">
          <para>
            <caps:sentence sentenceid="c3bba104906ad0a38bfd20be178b8276" id="tgt3" class="tgtSentence">在执行以下步骤之前，请确保已查看 <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>。</caps:sentence>
          </para>
        </alert>
      </introduction>
      <section>
        <title>
          <caps:sentence sentenceid="9a60d573ffbd5394bd0b3bb88a0e5c62" id="tgt4" class="tgtSentence">步骤 1：确认你有一个包含 Azure Rights Management 的订阅</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="9b1b271065dbe50a132917dac1775868" id="tgt5" class="tgtSentence">有多种类型的订阅包含 <token>aad_rightsmanagement_1</token>。</caps:sentence>
            <caps:sentence sentenceid="3950a377ccc2e153a1563c0d5971a0cb" id="tgt6" class="tgtSentence"> 请参阅 <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>主题中的<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link>，并参考 <externalLink><linkText>Rights Management 服务 (RMS) 产品比较</linkText><linkUri>https://technet.microsoft.com/dn858608</linkUri></externalLink>中的表格，检查订阅是否包含你要在组织中使用的功能。</caps:sentence>
          </para>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence sentenceid="29fc8913f73c56b275c3339d9721a737" id="tgt7" class="tgtSentence">步骤 2：准备你的租户帐户以便使用权限管理</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="73ad74e39033ab42104ed88779a2b4ec" id="tgt8" class="tgtSentence">开始使用 <token>aad_rightsmanagement_2</token> 之前，请进行以下准备工作： </caps:sentence>
          </para>
          <list class="ordered">
            <listItem>
              <para>
                <caps:sentence sentenceid="dc6545375fbd76284130504231c55e8a" id="tgt9" class="tgtSentence">确保 Azure 或 Office 365 租户包含 Azure RMS 用来对你组织中的用户进行身份验证的用户帐户和组。</caps:sentence>
                <caps:sentence sentenceid="5045677d0492bccd1c098d17fe128d12" id="tgt10" class="tgtSentence"> 如有必要，请创建这些帐户和组，或者从本地目录同步这些帐户和组。</caps:sentence>
                <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt11" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="afbca2d6-32a7-4bda-8aaf-9f93f5da5abc">Prepare for rights management</link>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="4142afd4a35d4e9c03c22b5232956062" id="tgt12" class="tgtSentence">决定你是希望 Microsoft 管理你的租户密钥（默认设置），还是自行生成和管理你的租户密钥（也称为“自带密钥”，简称 BYOK）。</caps:sentence>
                <caps:sentence sentenceid="6cd227dd00d682908d89521b5b6d12a1" id="tgt13" class="tgtSentence"> 请注意，如果你当前使用了 Exchange Online，则不能使用 BYOK。</caps:sentence>
                <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt14" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and operations for your Rights Management tenant key</link>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="841fe4c71dfe4c2e05ae4f6776173813" id="tgt15" class="tgtSentence">至少在一台可以访问 Internet 的计算机上安装适用于 <token>aad_rightsmanagement_2</token> 的 Windows PowerShell 模块。</caps:sentence>
                <caps:sentence sentenceid="9a2dcdbaae07eea24956e02960a3a3fe" id="tgt16" class="tgtSentence"> 你可以立即执行此步骤，也可以稍后执行。</caps:sentence>
                <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt17" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="0d665ed6-b1de-4d63-854a-bc57c1c49844">Install Windows PowerShell for rights management</link>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="55a1e5801d69f90093fdbc63c10ce3b8" id="tgt18" class="tgtSentence">如果你目前正在使用本地权限管理服务，则必须执行以下操作：执行迁移操作以将密钥、模板和 URL 移到云中。</caps:sentence>
                <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt19" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172">Migrating from AD RMS to Azure Rights Management</link>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="617ddfabe0b84559b52a98a5eca2f6cc" id="tgt20" class="tgtSentence">激活权限管理，然后即可使用该服务。</caps:sentence>
                <caps:sentence sentenceid="24cc7ca2593104c8945513833a91ca4e" id="tgt21" class="tgtSentence"> 如果需要分阶段部署，请配置用户载入控件以将其使用限于特定用户。</caps:sentence>
                <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt22" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="f8707e01-b239-4d1a-a1ea-0d1cf9a8d214">Activating rights management</link>。</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="bfd4956a3a11f92c3e70a55295b4d1eb" id="tgt23" class="tgtSentence">（可选）考虑进行以下配置： </caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="83869c34c35fcab6624263b10e05f9db" id="tgt24" class="tgtSentence">自定义模板，前提是默认权限策略模式不足以满足你组织的要求。</caps:sentence>
                <caps:sentence sentenceid="9a2dcdbaae07eea24956e02960a3a3fe" id="tgt25" class="tgtSentence"> 你可以立即执行此步骤，也可以稍后执行。</caps:sentence>
                <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt26" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="1775d8d0-9a59-42c8-914f-ce285b71ac1c">Configuring Custom Templates for Azure Rights Management</link>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="c5b8cd0a8f0782f4f4841775a47886fe" id="tgt27" class="tgtSentence">使用日志记录，以便你能够监控你组织使用权限管理的情况。</caps:sentence>
                <caps:sentence sentenceid="9a2dcdbaae07eea24956e02960a3a3fe" id="tgt28" class="tgtSentence"> 你可以立即执行此步骤，也可以稍后执行。</caps:sentence>
                <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt29" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e">Log and analyze rights management usage</link>。</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence sentenceid="953e88227353eea5d76a22fffafc654e" id="tgt30" class="tgtSentence">步骤 3：配置要运行 Rights Management 的应用程序和服务</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="32be72ff474123f4ae6551aa91e878c0" id="tgt31" class="tgtSentence">配置应用程序的过程可能包括安装权限管理共享应用程序、在 SharePoint Online 或 Exchange Online 中启用对信息权限管理 (IRM) 功能的支持。</caps:sentence>
            <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt32" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36">Configuring Applications for Azure Rights Management</link>。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="69f77dc5288ab85fb5d20eb0d0601caa" id="tgt33" class="tgtSentence">如果你的现有 IT 服务（例如数据泄漏防护 (DLP) 解决方案、内容加密网关 (CEG) 和反恶意软件产品）需要检查 Azure RMS 将要保护的文件，请将服务帐户配置为 Azure RMS 的超级用户。</caps:sentence>
            <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt34" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="acb4c00b-d3a9-4d74-94fe-91eeb481f7e3">Configuring Super Users for Azure Rights Management and Discovery Services or Data Recovery</link>。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="de51ed597d08c825d5709259eef440ca" id="tgt35" class="tgtSentence">如果你希望将 Azure 权限管理用于本地服务，请安装和配置权限管理连接器。</caps:sentence>
            <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt36" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066">Rights management connector</link>。</caps:sentence>
          </para>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence sentenceid="e0184636a3360f889eab05182935aa58" id="tgt37" class="tgtSentence">步骤 4：发布和使用受权限保护的内容 </caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="571021b609e792cc9aab1a7f89be4f4f" id="tgt38" class="tgtSentence">现在，你可以发布和使用受保护的内容，并记录公司如何使用 Rights Management。</caps:sentence>
            <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt39" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="18564e4a-9364-4ed2-8f17-89d24fc0d878">Using rights management</link>。</caps:sentence>
          </para>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence sentenceid="3e17551cf12121c9753a43327942d7b9" id="tgt40" class="tgtSentence">步骤 5：根据需要管理租户帐户的权限管理</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="69ae3b28351675d26c06b1c31f9d9644" id="tgt41" class="tgtSentence">开始使用 <token>aad_rightsmanagement_2</token> 时，你可能发现适用于 Windows PowerShell 的 <token>aad_rightsmanagement_2</token> 模块可以帮助你编写脚本或自动执行管理更改。</caps:sentence>
            <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt42" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="a890e04a-4b70-41b5-8d5f-3c210a669faa">Administering rights management</link>。</caps:sentence>
          </para>
        </content>
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
          <caps:sentence id="src1" class="srcSentence">Use the following steps to prepare for, implement, and manage Azure Rights Management (Azure RMS) for your organization.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src2" class="srcSentence">However, if you just want to quickly try Azure RMS for yourself, rather than roll it out in a production environment, see <link xlink:href="1db923bf-7d19-4fdd-a413-bfeb58af5e03">Quick Start Tutorial for Azure Rights Management</link>.</caps:sentence>
        </para>
        <alert class="important">
          <para>
            <caps:sentence id="src3" class="srcSentence">Before you do the following steps, make sure that you have reviewed <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>.</caps:sentence>
          </para>
        </alert>
      </introduction>
      <section>
        <title>
          <caps:sentence id="src4" class="srcSentence">Step 1: Confirm that you have a subscription that includes Azure Rights Management</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src5" class="srcSentence">There is more than one type of subscription that includes <token>aad_rightsmanagement_1</token>.</caps:sentence>
            <caps:sentence id="src6" class="srcSentence"> See the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link> section in the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link> topic, and check that your subscription includes the functionality that you want to use in your organization by referring to the table in <externalLink><linkText>Comparison of Rights Management Services (RMS) Offerings</linkText><linkUri>https://technet.microsoft.com/dn858608</linkUri></externalLink>.</caps:sentence>
          </para>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence id="src7" class="srcSentence">Step 2: Prepare your tenant account to use Rights Management</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src8" class="srcSentence">Before you begin using <token>aad_rightsmanagement_2</token>, do the following preparation: </caps:sentence>
          </para>
          <list class="ordered">
            <listItem>
              <para>
                <caps:sentence id="src9" class="srcSentence">Make sure that your Azure or Office 365 tenant contains the user accounts and groups that will be used by Azure RMS to authenticate users from your organization.</caps:sentence>
                <caps:sentence id="src10" class="srcSentence"> If necessary, create these account and groups, or synchronize them from your on-premises directory.</caps:sentence>
                <caps:sentence id="src11" class="srcSentence"> For more information, see <link xlink:href="afbca2d6-32a7-4bda-8aaf-9f93f5da5abc">Prepare for rights management</link>.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src12" class="srcSentence">Decide whether you want Microsoft to manage your tenant key (the default), or generate and manage your tenant key yourself (known as bring your own key, or BYOK).</caps:sentence>
                <caps:sentence id="src13" class="srcSentence"> Note that currently, you cannot use BYOK if you use Exchange Online.</caps:sentence>
                <caps:sentence id="src14" class="srcSentence"> For more information, see <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and operations for your Rights Management tenant key</link>.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src15" class="srcSentence">Install the Windows PowerShell module for <token>aad_rightsmanagement_2</token> on at least one computer that has Internet access.</caps:sentence>
                <caps:sentence id="src16" class="srcSentence"> You can do this step now, or later.</caps:sentence>
                <caps:sentence id="src17" class="srcSentence"> For more information, see <link xlink:href="0d665ed6-b1de-4d63-854a-bc57c1c49844">Install Windows PowerShell for rights management</link>.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src18" class="srcSentence">If you are currently using on-premises Rights Management services: Perform a migration to move the keys, templates, and URLs to the cloud.</caps:sentence>
                <caps:sentence id="src19" class="srcSentence"> For more information, see <link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172">Migrating from AD RMS to Azure Rights Management</link>.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src20" class="srcSentence">Activate Rights Management so that you can begin to use the service.</caps:sentence>
                <caps:sentence id="src21" class="srcSentence"> If a phased deployment is required, configure user onboarding controls to restrict usage to specific users.</caps:sentence>
                <caps:sentence id="src22" class="srcSentence"> For more information, see <link xlink:href="f8707e01-b239-4d1a-a1ea-0d1cf9a8d214">Activating rights management</link>.</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src23" class="srcSentence">Optionally, consider configuring the following: </caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src24" class="srcSentence">Custom templates if the default rights policy templates are not sufficient for your organization.</caps:sentence>
                <caps:sentence id="src25" class="srcSentence"> You can do this step now, or later.</caps:sentence>
                <caps:sentence id="src26" class="srcSentence"> For more information, see <link xlink:href="1775d8d0-9a59-42c8-914f-ce285b71ac1c">Configuring Custom Templates for Azure Rights Management</link>.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src27" class="srcSentence">Usage logging so that you can monitor how your organization is using Rights Management.</caps:sentence>
                <caps:sentence id="src28" class="srcSentence"> You can do this step now, or later.</caps:sentence>
                <caps:sentence id="src29" class="srcSentence"> For more information, see <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e">Log and analyze rights management usage</link>.</caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence id="src30" class="srcSentence">Step 3: Configure your applications and services for Rights Management</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src31" class="srcSentence">Configuring your applications can include installing the Rights Management sharing application and enabling support for information rights management (IRM) features in SharePoint Online or Exchange Online.</caps:sentence>
            <caps:sentence id="src32" class="srcSentence"> For more information, see <link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36">Configuring Applications for Azure Rights Management</link>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src33" class="srcSentence">If you have existing IT services that need to inspect files that Azure RMS will protect—such as data leak prevention (DLP) solutions, content encryption gateways (CEG), and anti-malware products—configure the service accounts to be super users for Azure RMS.</caps:sentence>
            <caps:sentence id="src34" class="srcSentence"> For more information, see <link xlink:href="acb4c00b-d3a9-4d74-94fe-91eeb481f7e3">Configuring Super Users for Azure Rights Management and Discovery Services or Data Recovery</link>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src35" class="srcSentence">If you have on-premises services that you want to use with Azure Rights Management, install and configure the Rights Management connector.</caps:sentence>
            <caps:sentence id="src36" class="srcSentence"> For more information, see <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066">Rights management connector</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence id="src37" class="srcSentence">Step 4: Publish and consume rights-protected content </caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src38" class="srcSentence">You’re now ready to publish and consume protected content, and log how your company is using Rights Management.</caps:sentence>
            <caps:sentence id="src39" class="srcSentence"> For more information, see <link xlink:href="18564e4a-9364-4ed2-8f17-89d24fc0d878">Using rights management</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence id="src40" class="srcSentence">Step 5: Administer Rights Management for your tenant account as needed</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src41" class="srcSentence">As you begin to use <token>aad_rightsmanagement_2</token>, you might find the <token>aad_rightsmanagement_2</token> module for Windows PowerShell useful to help script or automate administrative changes.</caps:sentence>
            <caps:sentence id="src42" class="srcSentence"> For more information, see <link xlink:href="a890e04a-4b70-41b5-8d5f-3c210a669faa">Administering rights management</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="206a0bfe-0912-4e0e-aa15-484b000b264c">Configuring Azure Rights Management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSSource>
</caps:SxS>