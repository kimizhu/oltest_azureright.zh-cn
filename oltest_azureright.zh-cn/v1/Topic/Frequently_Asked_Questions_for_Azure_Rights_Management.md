---
description: na
keywords: na
pagetitle: Frequently Asked Questions for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 71ce491f-41c1-4d15-9646-455a6eaa157d
---
# Azure 权限管理常见问题解答
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="zh-CN">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="2ba2d41a10c977d8b86bbd561321b7ab" id="tgt1" class="tgtSentence">Microsoft <token>aad_rightsmanagement_1</token>（也称为 Azure RMS）的某些常见问题：</caps:sentence>
        </para>
      </introduction>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="66e97ac10718c1ed4aae97664b9ceeba" id="tgt2" class="tgtSentence">部署 Azure RMS 需要做好哪些准备，如何能够顺利完成部署？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="230413b603dc29350b2b9328d0cca7a1" id="tgt3" class="tgtSentence">首先，请查看 <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>，其中包含了有关云订阅选项、如何将本地服务器与 Azure RMS 配合使用、当前不支持的部署方案以及哪些设备、应用程序支持 Azure RMS 的信息以及你需要的防火墙和代理服务器的 IP 地址和域名列表链接。</caps:sentence>
            <caps:sentence sentenceid="49e232f9fbcbad92b37b54a363ee284d" id="tgt4" class="tgtSentence"> 你还可能需要查看 <link xlink:href="5214667c-ec69-42ca-8bbf-8cb22da8c62e">Getting Started with Azure Rights Management</link>部分中的其他主题，以基本了解 <token>aad_rightsmanagement_1</token> 如何帮助保护组织的数据、如何与应用程序配合工作、它与 Active Directory Rights Management 的本地版本比起来如何，并了解特定于 <token>aad_rightsmanagement_1</token> 的术语和缩写。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="7501851a2b055256cddcbdac6ea402c4" id="tgt5" class="tgtSentence">然后，便可以自行测试 Azure RMS，或者为组织部署 Azure RMS。请使用 <link xlink:href="086600c2-c5d8-47ec-a4c0-c782e1797486">Azure Rights Management Deployment Roadmap</link>来获取步骤列表，以及用于了解详细信息和操作说明的链接。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="b60d3a643d2a30c9195af5678ed432bd" id="tgt6" class="tgtSentence">如果需要更多信息、资源和支持选项，请参阅 <link xlink:href="7cc73d92-27d6-49ff-a8ab-2fae73519b4b">Information and Support for Azure Rights Management</link>。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="1b22c8a140757b30729701e444aa51d0" id="tgt7" class="tgtSentence">可以将 Azure RMS 与我的本地服务器集成吗？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="4f7b50bec76bcf2b862eeb2140701427" id="tgt8" class="tgtSentence">适用。</caps:sentence>
            <caps:sentence sentenceid="ebde2dbae9729f4683d3fadee4dcc5bb" id="tgt9" class="tgtSentence"> Azure RMS 可以与你的本地服务器集成，如 Exchange Server、SharePoint 和 Windows 文件服务器。</caps:sentence>
            <caps:sentence sentenceid="840aa9edd9b9a56a79e27d9c2a28e587" id="tgt10" class="tgtSentence"> 为此，你需要使用 <externalLink><linkText>Rights Management 连接器</linkText><linkUri>https://technet.microsoft.com/library/dn375964.aspx</linkUri></externalLink>。</caps:sentence>
            <caps:sentence sentenceid="31e51d6ed2882705741f651e7127b5c3" id="tgt11" class="tgtSentence"> 或者，如果你只想对 Windows Server 使用文件分类基础结构 (FC)，则可使用 <externalLink><linkText>RMS 保护 cmdlet</linkText><linkUri>https://technet.microsoft.com/library/mt601315(v=ws.10).aspx</linkUri></externalLink>。</caps:sentence>
            <caps:sentence sentenceid="302f2a8bfbbd90ee67efc8f9b13c1b3b" id="tgt12" class="tgtSentence"> 你还可以使用 <externalLink><linkText>Azure AD Connect</linkText><linkUri>http://azure.microsoft.com/documentation/articles/active-directory-aadconnect/</linkUri></externalLink>，将 Active Directory 域控制器与 Azure AD 同步和联合，为用户提供更为契合的身份验证体验。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="b6ba4a812957a7f9524040e4ae9898e3" id="tgt13" class="tgtSentence">Azure RMS 将根据需要自动生成并管理 XrML 证书，因此它不使用本地 PKI。</caps:sentence>
            <caps:sentence sentenceid="07be572f5bf0c6e12aef29fa78df96ae" id="tgt14" class="tgtSentence"> 有关 Azure RMS 如何使用证书的详细信息，请参阅<link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link>主题中的<link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df#BKMK_Walthrough">Walkthrough of how Azure RMS works: First use, content protection, content consumption</link>部分。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="c8014cba12cbd17f666b2c2fb53e9da2" id="tgt15" class="tgtSentence">我对 Exchange 采用混合部署：Exchange Online 上存在一些用户，而其他用户则在 Exchange Server 上。Azure RMS 支持这种部署吗？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="89e8d84f8a5f0199c7f288e46ffa29dc" id="tgt16" class="tgtSentence">绝对支持，而且很棒的是，用户将受到无缝保护，并可以在两种 Exchange 部署上使用受保护的电子邮件和附件。</caps:sentence>
            <caps:sentence sentenceid="42461d09ddeaba3ce9a8f45e9d2820bb" id="tgt17" class="tgtSentence"> 对于此配置，<externalLink><linkText>激活 Azure RMS</linkText><linkUri>https://technet.microsoft.com/library/jj658941.aspx</linkUri></externalLink> 并<externalLink><linkText>启用适用于 Exchange Online 的 IRM</linkText><linkUri>https://technet.microsoft.com/library/dn151475(v=exchg.150).aspx</linkUri></externalLink>，然后<externalLink><linkText>部署并配置适用于 Exchange Server 的 RMS 连接器</linkText><linkUri>https://technet.microsoft.com/library/dn375964.aspx</linkUri></externalLink>。</caps:sentence>
          </para>
          <para></para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="7e48ebc350fc47296a3eeecc3a0f7eb7" id="tgt18" class="tgtSentence">如果我在生产中部署 Azure RMS，我的公司是否就只能使用该解决方案？或者是否存在无法访问由 Azure RMS 进行保护的内容的风险？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="6790155640269df973548e83a49b5474" id="tgt19" class="tgtSentence">不会，数据始终由你控制，并可以继续访问，即使你决定不再使用 Azure RMS 也是如此。</caps:sentence>
            <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt20" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="0b1c2064-0d01-45ae-a541-cebd7fd762ad">Decommissioning and Deactivating Azure Rights Management</link>。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="682e5165d1c1dbc9e6a1724dd5654952" id="tgt21" class="tgtSentence">但是，在你解除 Azure RMS 部署授权前，我们希望倾听你的意见，了解你为什么做出这个决定。</caps:sentence>
            <caps:sentence sentenceid="aa5bc97fbf1dc93d73bf9a13e9ec5747" id="tgt22" class="tgtSentence"> 如果 Azure RMS 未能满足你的业务要求，请与我们取得联系，或许在不久的将来会计划新功能或存在替代方法。</caps:sentence>
            <caps:sentence sentenceid="4fc4007a0df6d9276fa9ad85703fd048" id="tgt23" class="tgtSentence"> 将电子邮件发送到 <externalLink><linkText>AskIPTeam@Microsoft.com</linkText><linkUri>mailto:askipteam@microsoft.com?subject=Planning%20to%20decommission%20Azure%20RMS</linkUri></externalLink>，我们将很高兴讨论你的技术和商业要求。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="c6222a06b98b2c25c2abed1a67f82f0a" id="tgt24" class="tgtSentence">是否可以控制哪些用户能够使用 Azure RMS 来保护内容？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="83e1de908181d50a284ea38c65bf5f05" id="tgt25" class="tgtSentence">可以，Azure RMS 针对这种情况提供了用户登记控制功能。</caps:sentence>
            <caps:sentence sentenceid="be021ab36c2c99a549fc25f5fcee238c" id="tgt26" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="f8707e01-b239-4d1a-a1ea-0d1cf9a8d214">Activating Azure Rights Management</link>主题中的<link xlink:href="f8707e01-b239-4d1a-a1ea-0d1cf9a8d214#BKMK_OnboardingControls">Configuring onboarding controls for a phased deployment</link>部分。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="84c2eeeb418e723ee15acd26e69a0fa7" id="tgt27" class="tgtSentence">是否可以防止用户与特定的组织共享受保护文档？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="f3c1f7441a84b9022a16ac1fb1197c03" id="tgt28" class="tgtSentence">Azure RMS 的最大优势之一在于，它支持企业与企业的协作，同时，你无需为每个合作伙伴组织配置显式信任关系，因为 Azure AD 会代你处理好身份验证。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="1ff73e65215686a087cbbb35d17dd780" id="tgt29" class="tgtSentence">我们未提供相应的管理选项来防止用户与特定的组织安全共享文档。</caps:sentence>
            <caps:sentence sentenceid="e6d3a6d7acc1fcdaf2159e3395d84868" id="tgt30" class="tgtSentence"> 例如，你想要阻止某家你不信任的或者竞争的组织。</caps:sentence>
            <caps:sentence sentenceid="c4b81dd3d2e76ea1d85e1bc649ae27a4" id="tgt31" class="tgtSentence"> 防止 Azure RMS 向该组织的用户发送受保护文档没有任何意义，因为你的用户到时还是会共享未保护的文档，而这也许是你最终希望发生的事情！</caps:sentence>
            <caps:sentence sentenceid="d61dba8dbf048174d56c5ad6fc76cd31" id="tgt32" class="tgtSentence"> 例如，你无法识别谁在与这些组织的用户共享公司机密文档，但是，如果文档（或电子邮件）受 Azure RMS 的保护，则你可以识别。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="df3090f3d0e98d052437ea89c22d1443" id="tgt33" class="tgtSentence">如果我与公司之外的用户共享受保护文档，该用户如何进行身份验证。</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="c9f4806d21bfa786778a36cc75adc9c7" id="tgt34" class="tgtSentence">Azure RMS 始终使用 Azure Active Directory 帐户和关联的电子邮件地址进行用户身份验证，这为管理员将企业间的协作变得天衣无缝。</caps:sentence>
            <caps:sentence sentenceid="dba8742d75f22de08b0212c977f47aed" id="tgt35" class="tgtSentence"> 如果其他组织使用 Azure 服务，用户将具有 Azure Active Directory 帐户，即使这些帐户是在本地创建和进行管理，然后同步到 Azure。</caps:sentence>
            <caps:sentence sentenceid="a3f01ff5af1e49f799f967e235a42e93" id="tgt36" class="tgtSentence">  如果组织具有 Office 365，此服务在后台还会将 Azure Active Directory 用于用户帐户。</caps:sentence>
            <caps:sentence sentenceid="95421baecb60773269dc4376fab0499a" id="tgt37" class="tgtSentence">  如果用户的组织不具有托管的 Azure 帐户，用户可以注册<externalLink><linkText>个人 RMS</linkText><linkUri>https://technet.microsoft.com/library/dn592127.aspx</linkUri></externalLink>，这将为组织创建非托管的 Azure 租户和目录，并为用户创建帐户，因此，此用户可以进行 Azure RMS 身份验证。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="cdb24e579b3c1f6657a898e7b9932bb6" id="tgt38" class="tgtSentence">这些帐户的身份验证方法各不相同，具体取决于其他组织中的管理员如何配置 Azure Active Directory 帐户。</caps:sentence>
            <caps:sentence sentenceid="a198155cd20332111965af00518202a2" id="tgt39" class="tgtSentence"> 例如，他们可以使用为这些帐户、多重身份验证 (MFA)、联合身份验证创建的密码，或在 Active Directory 域服务中创建、然后同步到 Azure Active Directory 的密码。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="9ccd2e033533c18ef21c1fe22fa7bcb7" id="tgt40" class="tgtSentence">我可以将公司之外的用户添加到自定义模板吗？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="4f7b50bec76bcf2b862eeb2140701427" id="tgt41" class="tgtSentence">适用。</caps:sentence>
            <caps:sentence sentenceid="1c1829ebbd5fe2541bc2b0b3a9ebd548" id="tgt42" class="tgtSentence">  创建最终用户（和管理员）可以从应用程序中选择的自定义模板，可使用户使用你指定的预定义策略应用信息保护变得简单快捷。</caps:sentence>
            <caps:sentence sentenceid="3af81fe0f8f0e08ea7e7a420f3f7b563" id="tgt43" class="tgtSentence"> 该模板中的设置之一是哪些用户能够访问内容，而且你可以指定组织中的用户和组以及组织之外的用户。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="b3729b184fbe178148c5433290b7966e" id="tgt44" class="tgtSentence">若要指定不属于组织的用户，请使用<externalLink><linkText>适用于 Azure Rights Management 的 Windows PowerShell 模块</linkText><linkUri>https://technet.microsoft.com/library/jj585012.aspx</linkUri></externalLink>： </caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="5058f1af8388633f609cadb75a75dc9d" id="tgt45" class="tgtSentence">
                  <embeddedLabel>使用权限定义对象创建或更新模板</embeddedLabel>。</caps:sentence>
                <caps:sentence sentenceid="015c7094d3511e4d1d805d366615b5f8" id="tgt46" class="tgtSentence">    在权限定义对象中指定外部电子邮件地址及其权限，然后你将使用该地址创建或更新模板。</caps:sentence>
                <caps:sentence sentenceid="b21bea2b31c84d7b307b3eea3230bb78" id="tgt47" class="tgtSentence"> 指定权限定义对象时，可使用 <externalLink><linkText>New-AadrmRightsDefinition</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn727080.aspx</linkUri></externalLink> cmdlet 来创建一个变量，然后将该变量提供给 -RightsDefinition 参数，并可使用 <externalLink><linkText>Add-AadrmTemplate</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn727075.aspx</linkUri></externalLink> cmdlet（如果是新模板）或 <externalLink><linkText>Set-AadrmTemplateProperty</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn727076.aspx</linkUri></externalLink> cmdlet（如果需要修改现有模板）。</caps:sentence>
                <caps:sentence sentenceid="a293e7820e4687b9b9e81e7ece359ce6" id="tgt48" class="tgtSentence"> 但是，如果你是将这些用户添加到现有模板中，则需要在模板中为现有组定义权限定义对象，不仅仅只需为外部用户进行此类操作。</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="1fd343e72f394c25e7b08cf2760fc5fd" id="tgt49" class="tgtSentence">有关自定义模板的详细信息，请参阅<link xlink:href="1775d8d0-9a59-42c8-914f-ce285b71ac1c">Configuring Custom Templates for Azure Rights Management</link>。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="3f66f4ab6ebff3e2e2d8050222e45306" id="tgt50" class="tgtSentence">Azure RMS 支持哪些设备和哪种文件类型？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="1ca9c550f65754518050f41ea595c7c1" id="tgt51" class="tgtSentence">有关支持的设备列表，请参阅<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>主题中的<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedDevices">Client devices that support Azure RMS</link>部分。</caps:sentence>
            <caps:sentence sentenceid="f5514b80b58f4440136d61588c2b9bf8" id="tgt52" class="tgtSentence"> 由于并非所有受支持的设备目前都能支持所有 RMS 功能，因此，还请务必查看该主题中的<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_ClientCapabilities">Client device capabilities</link>表。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="6d4d1bffbc1e352b767cbdf8a2219bb3" id="tgt53" class="tgtSentence">Azure RMS 能够支持所有文件类型。</caps:sentence>
            <caps:sentence sentenceid="8fdac9a6a1537847209c06148b89dfcf" id="tgt54" class="tgtSentence"> 对于文字、图像、Microsoft Office (Word、Excel、PowerPoint) 文件、.pdf 文件和一些其他应用程序文件类型，Azure RMS 提供的本地保护包括对权利（权限）的加密和执行。</caps:sentence>
            <caps:sentence sentenceid="ed009ac3bc4655e965b15d1549f808d4" id="tgt55" class="tgtSentence"> 对于其他应用程序和文件类型，通用保护提供文件封装和验证以确认用户是否授权打开文件。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="31d991139abf916b69dfcd5ebbf4a796" id="tgt56" class="tgtSentence">对于 Azure RMS 以本机方式支持的文件扩展名列表，请参阅 <externalLink><linkText>Rights Management 共享应用程序管理员指南</linkText><linkUri>http://technet.microsoft.com/library/dn339003.aspx</linkUri></externalLink>中的<externalLink><linkText>支持的文件类型和文件扩展名</linkText><linkUri>http://technet.microsoft.com/library/dn339003.aspx</linkUri></externalLink>部分。</caps:sentence>
            <caps:sentence sentenceid="2431cba45924083b6773d3ee8e72a814" id="tgt57" class="tgtSentence"> 未列出的文件扩展名支持使用 RMS 共享应用程序，可自动提供通用保护保护这些文件。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="fe22b5c484b0dc62441e36b985f02d28" id="tgt58" class="tgtSentence">你们何时支持从 AD RMS 迁移？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="412e0d72645731f0af67d46701800e7c" id="tgt59" class="tgtSentence">最初，Azure RMS 不支持从本地部署的权限管理（如 AD RMS）迁移。</caps:sentence>
            <caps:sentence sentenceid="75b3ded7e5c9dcc9482c5af191ea48b1" id="tgt60" class="tgtSentence"> 但是，现在支持这种迁移。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="d1aee644e17abda9397214172b7615de" id="tgt61" class="tgtSentence">有关详细信息，请参阅<link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172">Migrating from AD RMS to Azure Rights Management</link>。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="b54518f2fbc3f6f457defcf5b367b403" id="tgt62" class="tgtSentence">我们很想将 BYOK 和 Azure RMS 一起使用，但却了解到这与 Exchange Online 不兼容，你有什么建议呢？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="9f403e1848ea4c4c366bf3ffe28e6753" id="tgt63" class="tgtSentence">不要让此当前限制延迟 Azure RMS 部署。</caps:sentence>
            <caps:sentence sentenceid="04d902db517618a7b9131144662f0c31" id="tgt64" class="tgtSentence"> 如果你具有 Exchange Online 并想要使用自带密钥 (BYOK)，我们建议你暂时以默认密钥管理模式部署 Azure RMS，即由 Microsoft 生成和管理你的密钥。</caps:sentence>
            <caps:sentence sentenceid="8e821538be483d04f7dc1dbcb26a131f" id="tgt65" class="tgtSentence"> 如此一来，你现在可以获取保护重要文件和电子邮件的所有好处，并可以选择以后移动到 BYOK（例如，当 Exchange Online 不支持 BYOK 时）。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="037e12350dbfd149117746fd73dea849" id="tgt66" class="tgtSentence">但是，如果你的公司策略要求你使用硬件安全模块 (HSM)，但这将阻止你的 Azure RMS 部署，可以另作选择，将 Azure RMS 和 BYOK 一起部署，只不过 Exchange 的 RMS 功能会减弱。</caps:sentence>
            <caps:sentence sentenceid="be021ab36c2c99a549fc25f5fcee238c" id="tgt67" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and Implementing Your Azure Rights Management Tenant Key</link>主题中的<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_Pricing">BYOK pricing and restrictions</link>部分。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="9a1298ce82e67b41b6557655da7fa899" id="tgt68" class="tgtSentence">我正在寻找的一项功能看起来不适用于 SharePoint 保护的库。是否计划了针对此功能的支持？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="ccf3f9ba13728f3d5687a0ee5c399a29" id="tgt69" class="tgtSentence">当前，SharePoint 通过使用 IRM 保护的库，支持 RMS 保护的文档，但不支持自定义模板、文档跟踪和一些其他功能。</caps:sentence>
            <caps:sentence sentenceid="017357f9c63d6a8493850b86d7e16620" id="tgt70" class="tgtSentence">  有关详细信息，请展开<link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9">How Applications Support Azure Rights Management</link>主题中的 <link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36#BKMK_SharePointOnline">SharePoint Online and OneDrive for Business: IRM Configuration</link>部分。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="25557db99f32e0754f33cfa321290018" id="tgt71" class="tgtSentence">如果你对当前不支持的某项特定功能感兴趣，请务必关注 <externalLink><linkText>RMS 团队博客</linkText><linkUri>http://blogs.technet.com/b/rms/</linkUri></externalLink>上的公告。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="d48718cc268184e64552069dcea78f35" id="tgt72" class="tgtSentence">如何在 SharePoint Online 中配置 OneDrive for Business，以便用户可以安全地与公司内外的人员共享他们的文件？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="4f0da6314a8b90c6eda3f92fa3669851" id="tgt73" class="tgtSentence">默认情况下，作为 Office 365 管理员，你不用执行此配置，用户会进行配置。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="7a1b1f7d42509e3a2807cf175e2d68b8" id="tgt74" class="tgtSentence">正如 SharePoint 站点管理员为其拥有的 SharePoint 库启用并配置 IRM 一样，根据 OneDrive for Business 的设计，用户也需要为自己的 OneDrive for Business 库启用并配置 IRM。</caps:sentence>
            <caps:sentence sentenceid="1fcba590d90f67460e61d310d5c659c6" id="tgt75" class="tgtSentence">  不过，你可以使用 PowerShell 为他们执行此类操作。</caps:sentence>
            <caps:sentence sentenceid="cd96584e3858390fcc93173795f1ea87" id="tgt76" class="tgtSentence"> 若需说明，请参阅<link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36">Configuring Applications for Azure Rights Management</link>文章中的 <link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36#BKMK_SharePointOnline">SharePoint Online and OneDrive for Business: IRM Configuration</link>部分。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="b77bdcff0dfba49de85c2aadb2595a0a" id="tgt77" class="tgtSentence">是否能够提供有关成功部署 RMS 的任何诀窍或技巧？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="83dfc4134d44b5cc995a3b66efd834cf" id="tgt78" class="tgtSentence">在考察大量的部署并聆听客户、合作伙伴、顾问和支持工程师的意见后，结合自身的经验，我们很乐意与你分享下面这个极其有效的诀窃：<legacyBold>设计并部署简单的权限策略</legacyBold>。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="c467021ec53d51a7fd74ca4208f7235e" id="tgt79" class="tgtSentence">由于 Azure RMS 支持与任何人安全共享，因此，你完全有理由相信自己的信息保护措施的覆盖面。</caps:sentence>
            <caps:sentence sentenceid="b01d59d6c85881e54410eda3d20c8d86" id="tgt80" class="tgtSentence"> 但是，对权限策略应持保守态度。</caps:sentence>
            <caps:sentence sentenceid="3a99033be49fa1839b8378894d1b0e29" id="tgt81" class="tgtSentence"> 对于许多组织而言，对业务产生的最大影响来自于通过应用默认权限策略模板防止数据泄漏，将其访问权限限制给组织中的人员。</caps:sentence>
            <caps:sentence sentenceid="313d4553abbd081c0def61ab0a6d2cba" id="tgt82" class="tgtSentence"> 当然，你可以根据需要采取粒度级比这高得多的措施 - 例如，防止人员打印、编辑，等等。但是，对于确实需要高级安全性的文档，请将更高粒度级的限制保留为例外措施，并且不要一开始就实施这些限制性更强的策略，而是计划采取分阶段的实施方案。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="eb1fa3db8ac747ad8cc849aa7c3267d0" id="tgt83" class="tgtSentence">哪些功能可以或不可以用于 Azure RMS 的不同订阅？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="01ac793622ae26ffa5e03967638328d2" id="tgt84" class="tgtSentence">对于支持 Azure RMS 的付费订阅（Office 365、Azure RMS Premium 和 Enterprise Mobility Suite），在支持的 RMS 功能方面存在一些差异。</caps:sentence>
            <caps:sentence sentenceid="5670c8da584e0c42988afef16c2d3aaf" id="tgt85" class="tgtSentence"> 有关列表，请参阅 <externalLink><linkText>Rights Management 服务 (RMS) 产品比较</linkText><linkUri>http://technet.microsoft.com/dn858608</linkUri></externalLink>。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="6a966ec301895f59ee36fb5e06a52881" id="tgt86" class="tgtSentence">支持 Azure RMS（个人 RMS）的免费订阅支持使用受 Azure RMS 保护的内容。</caps:sentence>
            <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt87" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="2efcb440-fefd-45e9-872b-f471573aadf2">RMS for Individuals and Azure Rights Management</link>。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="5b78ef16b7af2eaa36d347ce97036b8c" id="tgt88" class="tgtSentence">我在哪里可以获取有关 Azure RMS（个人 RMS）免费订阅的技术信息 — 例如它的工作原理、如何控制帐户、哪些域名不可用？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="cc4ab6c7f2648d5dd7f326f9f903fd4d" id="tgt89" class="tgtSentence">你可以在<link xlink:href="2efcb440-fefd-45e9-872b-f471573aadf2">RMS for Individuals and Azure Rights Management</link>主题中找到这些问题的答案。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="b3f526c04ff9371c9aa39b019b4b33c7" id="tgt90" class="tgtSentence">我们如何重新获取对由已离职员工保护的文件的访问权限？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="0aec1192fb6556e951374a7acd0ac3d1" id="tgt91" class="tgtSentence">使用 Azure RMS 的超级用户功能，它可以让授权用户对组织的 RMS 租户授予的所有使用许可证行使所有者权限。</caps:sentence>
            <caps:sentence sentenceid="2039f6db660b10183044be2f62ddc42b" id="tgt92" class="tgtSentence"> 根据需要，此相同功能可以让授权服务编写文件索引和检查文件。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="d1aee644e17abda9397214172b7615de" id="tgt93" class="tgtSentence">有关详细信息，请参阅<link xlink:href="acb4c00b-d3a9-4d74-94fe-91eeb481f7e3">Configuring Super Users for Azure Rights Management and Discovery Services or Data Recovery</link>。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="49a27bce910581cb71979b0d80091b77" id="tgt94" class="tgtSentence">Rights Management 可以防止屏幕截图吗？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="76c02cc38b332d0f345ccd0ebb8d95e9" id="tgt95" class="tgtSentence">Rights Management 能够阻止大多数常用屏幕截图工具进行屏幕截图，这样可以防止因意外或疏忽而泄露机密信息或敏感信息。</caps:sentence>
            <caps:sentence sentenceid="bea5f521ac8c215c2ade0dbd40aab59d" id="tgt96" class="tgtSentence"> 不过，用户可以通过多种方式来共享显示在屏幕上的数据，进行屏幕截图只是其中一种方法。</caps:sentence>
            <caps:sentence sentenceid="f76115b2526bdfa63dbe91aa6c31e1a2" id="tgt97" class="tgtSentence"> 例如，如果想要共享所显示的信息，用户可以使用带相机的手机拍照，可以重新键入相关数据，还可以直接通过口头方式将其传达给某人。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="05d71a7f430be36cf381d4fe0adafc37" id="tgt98" class="tgtSentence">这些示例表明，单纯通过技术手段并不总能阻止用户共享不应共享的数据。</caps:sentence>
            <caps:sentence sentenceid="4d76bf3ba8449ef2a0e4d786a77d3140" id="tgt99" class="tgtSentence"> 虽然 Rights Management 可以通过授权和使用策略的方式来确保重要数据的安全性，但在使用企业权限管理解决方案时还应加入其他控制手段。</caps:sentence>
            <caps:sentence sentenceid="7f351cedcf8c8f73242f71a01657a592" id="tgt100" class="tgtSentence"> 例如，可以实施物理安全措施，可以仔细盘查和监视有权访问组织数据的人员，还可以进行用户教育，让用户了解哪些数据是不应共享的。</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="d27c144c572eb860768eac4e1058714b" id="tgt101" class="tgtSentence">我在何处可以找到 Azure RMS 的支持信息，例如法律、合规性和 SLA？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="56ef49ae0fc7e5b87e4af6a2164f68de" id="tgt102" class="tgtSentence">Azure RMS 支持其他服务，也依赖于其他服务。</caps:sentence>
            <caps:sentence sentenceid="5bee4ed4452fcc7b27072e98986a833e" id="tgt103" class="tgtSentence"> 如果你寻找的信息与 Azure RMS 相关，但与如何使用 Azure RMS 服务无关，请查看以下资源：</caps:sentence>
          </para>
          <para>
            <embeddedLabel>
              <caps:sentence sentenceid="89043590189b057ac4e9ec90f1e74bb2" id="tgt104" class="tgtSentence">法律和隐私：</caps:sentence>
            </embeddedLabel>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="fb4f6c9aeed5c9a0d18d22efe4399d76" id="tgt105" class="tgtSentence">对于 Microsoft Azure 协议信息：<externalLink><linkText>Microsoft Azure 协议</linkText><linkUri>http://azure.microsoft.com/support/legal/subscription-agreement/</linkUri></externalLink></caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="342d26c9340f00b5aee90a909d75fdb2" id="tgt106" class="tgtSentence">对于 Microsoft Azure 隐私信息：<externalLink><linkText>Microsoft Azure 隐私声明</linkText><linkUri>http://azure.microsoft.com/support/legal/privacy-statement/</linkUri></externalLink></caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <embeddedLabel>
              <caps:sentence sentenceid="11c6431e2060fc45be8319d264707565" id="tgt107" class="tgtSentence">安全、相容性和审核：</caps:sentence>
            </embeddedLabel>
          </para>
          <para>
            <caps:sentence sentenceid="abda7877548e2693387fce7b54bf4008" id="tgt108" class="tgtSentence">请参阅<link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link>主题中的<link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df#BKMK_RMScompliance">Security, compliance, and regulatory requirements</link>部分。</caps:sentence>
            <caps:sentence sentenceid="e7fff03a157bc33b1fd16558fd9b5d0b" id="tgt109" class="tgtSentence"> 此外：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="9d820a07c400c222618f55fd97a864eb" id="tgt110" class="tgtSentence">对于 Azure RMS 的外部认证：<externalLink><linkText>Microsoft Azure 信任中心</linkText><linkUri>http://azure.microsoft.com/support/trust-center/</linkUri></externalLink></caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="33b3f58a438ce52218bc8d417abeff21" id="tgt111" class="tgtSentence">对于 FIPS 140 信息：<externalLink><linkText>FIPS 140 验证</linkText><linkUri>https://technet.microsoft.com/library/security/cc750357.aspx</linkUri></externalLink></caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <embeddedLabel>
              <caps:sentence sentenceid="64fc3324d3d4f36ac64377372a054808" id="tgt112" class="tgtSentence">服务级别协议：</caps:sentence>
            </embeddedLabel>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="edcd8bf299a8fe37043b968c24515ae8" id="tgt113" class="tgtSentence">Azure RMS 的服务级别协议（按所选国家/地区列出）：<externalLink><linkText>服务级别协议</linkText><linkUri>http://microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37</linkUri></externalLink> </caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="b590eabbbb7736f666290656345f8c57" id="tgt114" class="tgtSentence">Azure Active Directory 的服务级别协议：<externalLink><linkText>服务级别协议</linkText><linkUri>http://azure.microsoft.com/support/legal/sla/</linkUri></externalLink></caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <embeddedLabel>
              <caps:sentence sentenceid="63adb321a0c16bdb196adb991267517c" id="tgt115" class="tgtSentence">文档：</caps:sentence>
            </embeddedLabel>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="45d337d17ada68217463970cd7168c5d" id="tgt116" class="tgtSentence">Azure Active Directory 文档站点：<externalLink><linkText>Azure Active Directory</linkText><linkUri>http://azure.microsoft.com/documentation/services/active-directory/</linkUri></externalLink></caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="f70e8328349e6445f905139c1c739eaa" id="tgt117" class="tgtSentence">Azure Active Directory 库：<externalLink><linkText>Azure Active Directory</linkText><linkUri>http://msdn.microsoft.com/library/azure/jj673460.aspx</linkUri></externalLink></caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="07dbf8732256ed05dabbb818b60834c8" id="tgt118" class="tgtSentence">Office 365 库：<externalLink><linkText>Office 365</linkText><linkUri>http://technet.microsoft.com/library/dn127064(v=office.14).aspx</linkUri></externalLink></caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence sentenceid="0398fda84f59464004e2d12dfab70ebf" id="tgt119" class="tgtSentence">如果我的问题不在这里，我该如何操作？</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="b65f4c0994bfc28abd75426fc320754a" id="tgt120" class="tgtSentence">使用 <link xlink:href="7cc73d92-27d6-49ff-a8ab-2fae73519b4b">Information and Support for Azure Rights Management</link>中列出的链接和资源。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="98e956464cfc5e2037df20ecfd1b6293" id="tgt121" class="tgtSentence">此外，我们还为最终用户制作了常见问题解答：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence sentenceid="6e530ad535055e4acc7229493acc5ba7" id="tgt122" class="tgtSentence">适用于 Windows 的 Rights Management 共享应用程序常见问题</caps:sentence>
                  </linkText>
                  <linkUri>https://technet.microsoft.com/dn467883</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence sentenceid="1aa2fbb155957558f8fdd797f7e74a8b" id="tgt123" class="tgtSentence"> 适用于移动平台和 Mac 平台的 Rights Management 共享应用程序的常见问题</caps:sentence>
                  </linkText>
                  <linkUri>https://technet.microsoft.com/dn451248</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence sentenceid="1ea15bf16350f6bd7bee6a3388afa295" id="tgt124" class="tgtSentence">文档跟踪常见问题</caps:sentence>
                  </linkText>
                  <linkUri>http://go.microsoft.com/fwlink/?LinkId=523977</linkUri>
                </externalLink>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="ce9ad556813f10c20aa84f1abdf9d940" id="tgt125" class="tgtSentence">此常见问题页将定期更新，其中新添加的内容将在 <externalLink><linkText>Microsoft 权限管理 (RMS) 团队</linkText><linkUri>http://blogs.technet.com/b/rms/</linkUri></externalLink>博客上的每月文档更新公告中列出。</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence sentenceid="796a75db26fb2b5ed1340e1b901fe1fd" id="tgt126" class="tgtSentence">可以使用该博客上的<externalLink><linkText>文档标记</linkText><linkUri>http://blogs.technet.com/b/rms/archive/tags/docs/</linkUri></externalLink>更轻松地找到这些文档公告。</caps:sentence>
            </para>
          </alert>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="5214667c-ec69-42ca-8bbf-8cb22da8c62e">Getting Started with Azure Rights Management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSTarget>
  <caps:SxSSource locale="en-US">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence id="src1" class="srcSentence">Some frequently asked questions for Microsoft <token>aad_rightsmanagement_1</token>, also known as Azure RMS:</caps:sentence>
        </para>
      </introduction>
      <section expanded="false">
        <title>
          <caps:sentence id="src2" class="srcSentence">What do I need to deploy Azure RMS and how do I get going?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src3" class="srcSentence">First, check <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>, which has information about the cloud subscription options, how you can use your on-premises servers with Azure RMS, which deployment scenarios are not currently supported, which devices and applications support Azure RMS, and a link if you need a list of IP addresses and domain names for firewalls or proxy servers.</caps:sentence>
            <caps:sentence id="src4" class="srcSentence"> You might also want to check the other topics in the <link xlink:href="5214667c-ec69-42ca-8bbf-8cb22da8c62e">Getting Started with Azure Rights Management</link> section, to get a basic understanding of how <token>aad_rightsmanagement_1</token> can help protect your organization’s data, how it works with applications, how it compares with the on-premises version of Active Directory Rights Management, and understand the terms and abbreviations that are specific to <token>aad_rightsmanagement_1</token>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src5" class="srcSentence">Then when you’re ready to test Azure RMS for yourself, or deploy it for your organization, use the <link xlink:href="086600c2-c5d8-47ec-a4c0-c782e1797486">Azure Rights Management Deployment Roadmap</link> for a list of steps with links for more information and how-to instructions.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src6" class="srcSentence">If you need additional information, resources, and support options, see <link xlink:href="7cc73d92-27d6-49ff-a8ab-2fae73519b4b">Information and Support for Azure Rights Management</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src7" class="srcSentence">Can I integrate Azure RMS with my on-premises servers?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src8" class="srcSentence">Yes.</caps:sentence>
            <caps:sentence id="src9" class="srcSentence"> Azure RMS can be integrated with your on-premises servers, such as Exchange Server, SharePoint, and Windows file servers.</caps:sentence>
            <caps:sentence id="src10" class="srcSentence"> To do this, you use the <externalLink><linkText>Rights Management connector</linkText><linkUri>https://technet.microsoft.com/library/dn375964.aspx</linkUri></externalLink>.</caps:sentence>
            <caps:sentence id="src11" class="srcSentence"> Or, if you're just interested in using File Classification Infrastructure (FC) with Windows Server, you can use the <externalLink><linkText>RMS Protection cmdlets</linkText><linkUri>https://technet.microsoft.com/library/mt601315(v=ws.10).aspx</linkUri></externalLink>.</caps:sentence>
            <caps:sentence id="src12" class="srcSentence"> You can also synchronize and federate your Active Directory domain controllers with Azure AD for a more seamless authentication experience for users, for example, by using <externalLink><linkText>Azure AD Connect</linkText><linkUri>http://azure.microsoft.com/documentation/articles/active-directory-aadconnect/</linkUri></externalLink>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src13" class="srcSentence">Azure RMS automatically generates and manages XrML certificates as required, so it doesn’t use an on-premises PKI.</caps:sentence>
            <caps:sentence id="src14" class="srcSentence"> For more information about how Azure RMS uses certificates, see the <link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df#BKMK_Walthrough">Walkthrough of how Azure RMS works: First use, content protection, content consumption</link> section in the <link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link> topic.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src15" class="srcSentence">I have a hybrid deployment of Exchange with some users on Exchange Online and others on Exchange Server—is this supported by Azure RMS?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src16" class="srcSentence">Absolutely, and the nice thing is, users will be able to seamlessly protect and consume protected emails and attachments across the two Exchange deployments.</caps:sentence>
            <caps:sentence id="src17" class="srcSentence"> For this configuration, <externalLink><linkText>activate Azure RMS</linkText><linkUri>https://technet.microsoft.com/library/jj658941.aspx</linkUri></externalLink> and <externalLink><linkText>enable IRM for Exchange Online</linkText><linkUri>https://technet.microsoft.com/library/dn151475(v=exchg.150).aspx</linkUri></externalLink>, then <externalLink><linkText>deploy and configure the RMS connector</linkText><linkUri>https://technet.microsoft.com/library/dn375964.aspx</linkUri></externalLink> for Exchange Server.</caps:sentence>
          </para>
          <para></para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src18" class="srcSentence">If I deploy Azure RMS in production, is my company then locked into the solution or risk losing access to content that we protected with Azure RMS?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src19" class="srcSentence">No, you always remain in control of your data and can continue to access it, even if you decide to no longer use Azure RMS.</caps:sentence>
            <caps:sentence id="src20" class="srcSentence"> For more information, see <link xlink:href="0b1c2064-0d01-45ae-a541-cebd7fd762ad">Decommissioning and Deactivating Azure Rights Management</link>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src21" class="srcSentence">However, before you decommission your Azure RMS deployment, we would like to hear from you and understand why you made this decision.</caps:sentence>
            <caps:sentence id="src22" class="srcSentence"> If Azure RMS does not fulfil your business requirements, check with us in case new functionality is planned for the near-future or if there are alternatives.</caps:sentence>
            <caps:sentence id="src23" class="srcSentence"> Send an email message to <externalLink><linkText>AskIPTeam@Microsoft.com</linkText><linkUri>mailto:askipteam@microsoft.com?subject=Planning%20to%20decommission%20Azure%20RMS</linkUri></externalLink> and we’ll be happy to discuss your technical and business requirements.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src24" class="srcSentence">Can I control which of my users can use Azure RMS to protect content?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src25" class="srcSentence">Yes, Azure RMS has user onboarding controls for this scenario.</caps:sentence>
            <caps:sentence id="src26" class="srcSentence"> For more information, see the <link xlink:href="f8707e01-b239-4d1a-a1ea-0d1cf9a8d214#BKMK_OnboardingControls">Configuring onboarding controls for a phased deployment</link> section in the <link xlink:href="f8707e01-b239-4d1a-a1ea-0d1cf9a8d214">Activating Azure Rights Management</link> topic.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src27" class="srcSentence">Can I prevent users from sharing protected documents with specific organizations?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src28" class="srcSentence">One of the biggest benefits of Azure RMS is that it supports business-to-business collaboration without you having to configure explicit trusts for each partner organization, because Azure AD takes care of the authentication for you.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src29" class="srcSentence">There is no administration option to prevent users from securely sharing documents with specific organizations.</caps:sentence>
            <caps:sentence id="src30" class="srcSentence"> For example, you want to block an organization that you don’t trust or that has a competing business.</caps:sentence>
            <caps:sentence id="src31" class="srcSentence"> Preventing Azure RMS from sending protected documents to users in these organizations wouldn’t make sense because your users would then share their documents unprotected, which is probably the last thing you want to happen in this scenario!</caps:sentence>
            <caps:sentence id="src32" class="srcSentence"> For example, you wouldn’t be able to identify who is sharing company-confidential documents with which users in these organizations, which you can do when the document (or email) is protected by Azure RMS.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src33" class="srcSentence">When I share a protected document with somebody outside my company, how does that user get authenticated?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src34" class="srcSentence">Azure RMS always uses an Azure Active Directory account and an associated email address for user authentication, which makes business-to-business collaboration seamless for administrators.</caps:sentence>
            <caps:sentence id="src35" class="srcSentence"> If the other organization uses Azure services, users will already have accounts in Azure Active Directory, even if these accounts are created and managed on-premises and then synchronized to Azure.</caps:sentence>
            <caps:sentence id="src36" class="srcSentence">  If the organization has Office 365, under the covers, this service also uses Azure Active Directory for the user accounts.</caps:sentence>
            <caps:sentence id="src37" class="srcSentence">  If the user’s organization doesn’t have managed accounts in Azure, users can sign up for <externalLink><linkText>RMS for individuals</linkText><linkUri>https://technet.microsoft.com/library/dn592127.aspx</linkUri></externalLink>, which creates an unmanaged Azure tenant and directory for the organization with an account for the user, so that this user can then be authenticated for Azure RMS.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src38" class="srcSentence">The authentication method for these accounts can vary, depending on how the administrator in the other organization has configured the Azure Active Directory accounts.</caps:sentence>
            <caps:sentence id="src39" class="srcSentence"> For example, they could use passwords that were created for these accounts, multi-factor authentication (MFA), federation, or passwords that were created in Active Directory Domain Services and then synchronized to Azure Active Directory.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src40" class="srcSentence">Can I add users from outside my company to custom templates?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src41" class="srcSentence">Yes.</caps:sentence>
            <caps:sentence id="src42" class="srcSentence">  Creating custom templates that end users (and administrators) can select from applications makes it quick and easily for them to apply information protection, using predefined policies that you specify.</caps:sentence>
            <caps:sentence id="src43" class="srcSentence"> One of the settings in the template is who is able to access the content, and you can specify users and groups from within your organization, and users from outside your organization.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src44" class="srcSentence">To specify users from outside your organization, use <externalLink><linkText>Windows PowerShell module for Azure Rights Management</linkText><linkUri>https://technet.microsoft.com/library/jj585012.aspx</linkUri></externalLink>: </caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src45" class="srcSentence">
                  <embeddedLabel>Use a rights definition object to create or update a template</embeddedLabel>.</caps:sentence>
                <caps:sentence id="src46" class="srcSentence">    Specify the external email addresses and their rights in a rights definition object, which you then use to create or update a template.</caps:sentence>
                <caps:sentence id="src47" class="srcSentence"> You specify the rights definition object by using the <externalLink><linkText>New-AadrmRightsDefinition</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn727080.aspx</linkUri></externalLink> cmdlet to create a variable and then supply this variable to the  -RightsDefinition parameter with the <externalLink><linkText>Add-AadrmTemplate</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn727075.aspx</linkUri></externalLink> cmdlet (for a new template) or <externalLink><linkText>Set-AadrmTemplateProperty</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn727076.aspx</linkUri></externalLink> cmdlet (if you're modifying an existing template).</caps:sentence>
                <caps:sentence id="src48" class="srcSentence"> However, if you're adding these users to an existing template, you will need to define rights definition objects for the existing groups in the templates and not just the external users.</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src49" class="srcSentence">For more information about custom templates, see <link xlink:href="1775d8d0-9a59-42c8-914f-ce285b71ac1c">Configuring Custom Templates for Azure Rights Management</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src50" class="srcSentence">What devices and which file types are supported by Azure RMS?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src51" class="srcSentence">For a list of supported devices, see the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedDevices">Client devices that support Azure RMS</link> section in the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link> topic.</caps:sentence>
            <caps:sentence id="src52" class="srcSentence"> Because not all supported devices can currently support all RMS capabilities, be sure to also check the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_ClientCapabilities">Client device capabilities</link> table in the same topic.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src53" class="srcSentence">Azure RMS can support all file types.</caps:sentence>
            <caps:sentence id="src54" class="srcSentence"> For text, image, Microsoft Office (Word, Excel, PowerPoint) files, .pdf files, and some other application file types, Azure RMS provides native protection that includes both encryption and enforcement of rights (permissions).</caps:sentence>
            <caps:sentence id="src55" class="srcSentence"> For all other applications and file types, generic protection provides file encapsulation and authentication to verify if a user is authorized to open the file.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src56" class="srcSentence">For a list of file name extensions that are natively supported by Azure RMS, see the <externalLink><linkText>Supported file types and file name extensions</linkText><linkUri>http://technet.microsoft.com/library/dn339003.aspx</linkUri></externalLink> section of the <externalLink><linkText>Rights Management sharing application administrator guide</linkText><linkUri>http://technet.microsoft.com/library/dn339003.aspx</linkUri></externalLink>.</caps:sentence>
            <caps:sentence id="src57" class="srcSentence"> File name extensions not listed are supported by using the RMS sharing application that automatically applies generic protection to these files.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src58" class="srcSentence">When will you support migration from AD RMS?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src59" class="srcSentence">Initially, Azure RMS didn’t support migration from an on-premises deployment of Rights Management, such as AD RMS.</caps:sentence>
            <caps:sentence id="src60" class="srcSentence"> But it’s supported now.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src61" class="srcSentence">For more information, see <link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172">Migrating from AD RMS to Azure Rights Management</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src62" class="srcSentence">We really want to use BYOK with Azure RMS but learned that this isn’t compatible with Exchange Online—what’s your advice?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src63" class="srcSentence">Don’t let this current limitation delay your Azure RMS deployment.</caps:sentence>
            <caps:sentence id="src64" class="srcSentence"> If you have Exchange Online and want to use bring your own key (BYOK), we recommend that you deploy Azure RMS in the default key management mode now, where Microsoft generates and manages your key.</caps:sentence>
            <caps:sentence id="src65" class="srcSentence"> That way, you get all the benefits of protecting your important files and emails now, with the option to move to BYOK later (for example, when Exchange Online does support BYOK).</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src66" class="srcSentence">However, if your company policies require you to use a hardware security module (HSM) and this would otherwise block your Azure RMS deployment, another option is to deploy Azure RMS with BYOK now, with reduced RMS functionality for Exchange.</caps:sentence>
            <caps:sentence id="src67" class="srcSentence"> For more information, see the <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14#BKMK_Pricing">BYOK pricing and restrictions</link> section in the <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and Implementing Your Azure Rights Management Tenant Key</link> topic.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src68" class="srcSentence">A feature I am looking for doesn’t seem to work with SharePoint protected libraries—is support for my feature planned?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src69" class="srcSentence">Currently, SharePoint supports RMS protected documents by using IRM protected libraries, which do not support custom templates, document tracking, and some other capabilities.</caps:sentence>
            <caps:sentence id="src70" class="srcSentence">  For more information, expand the   <link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36#BKMK_SharePointOnline">SharePoint Online and OneDrive for Business: IRM Configuration</link> section in the <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9">How Applications Support Azure Rights Management</link> topic .</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src71" class="srcSentence">If you are interested in a specific  capability that isn't yet supported,  be sure to keep an eye on announcements on the <externalLink><linkText>RMS team blog</linkText><linkUri>http://blogs.technet.com/b/rms/</linkUri></externalLink>.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src72" class="srcSentence">How do I configure One Drive for Business in SharePoint Online, so that users can safely share their files with people inside and outside the company?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src73" class="srcSentence">By default, as an Office 365 administrator, you don’t configure this; users do.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src74" class="srcSentence">Just as a SharePoint site administrator enables and configures IRM for a SharePoint library that they own, OneDrive for Business is designed for users to enable and configure IRM for their own OneDrive for Business library.</caps:sentence>
            <caps:sentence id="src75" class="srcSentence">  However, by using PowerShell, you can do this for them.</caps:sentence>
            <caps:sentence id="src76" class="srcSentence"> For instructions, expand the <link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36#BKMK_SharePointOnline">SharePoint Online and OneDrive for Business: IRM Configuration</link>  section in the <link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36">Configuring Applications for Azure Rights Management</link> article.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src77" class="srcSentence">Do you have any tips or tricks for a successful RMS deployment?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src78" class="srcSentence">After overseeing many deployments and listening to our customers, partners, consultants, and support engineers – one of the biggest tips we can pass on from experience: <legacyBold>Design and deploy simple rights policies</legacyBold>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src79" class="srcSentence">Because Azure RMS supports sharing securely with anyone, you can afford to be ambitious with your information protection reach.</caps:sentence>
            <caps:sentence id="src80" class="srcSentence"> But be conservative with your rights policies.</caps:sentence>
            <caps:sentence id="src81" class="srcSentence"> For many organizations, the biggest business impact comes from preventing data leakage by applying the default rights policy template that restricts access to people in your organization.</caps:sentence>
            <caps:sentence id="src82" class="srcSentence"> Of course, you can get much more granular than that if you need to – prevent people from printing, editing etc. But keep the more granular restrictions as the exception for documents that really need high-level security, and don’t implement these more restrictive policies on day one, but plan for a more phased approach.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src83" class="srcSentence">What features can or can’t be used with the different subscriptions for Azure RMS?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src84" class="srcSentence">For the paid subscriptions that support Azure RMS (Office 365, Azure RMS Premium, and Enterprise Mobility Suite), there are some differences in the RMS features that are supported.</caps:sentence>
            <caps:sentence id="src85" class="srcSentence"> For a list of these, see <externalLink><linkText>Comparison of Rights Management Services (RMS) Offerings</linkText><linkUri>http://technet.microsoft.com/dn858608</linkUri></externalLink>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src86" class="srcSentence">The free subscription that supports Azure RMS (RMS for individuals) supports consuming content that has been protected by Azure RMS.</caps:sentence>
            <caps:sentence id="src87" class="srcSentence"> For more information, see <link xlink:href="2efcb440-fefd-45e9-872b-f471573aadf2">RMS for Individuals and Azure Rights Management</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src88" class="srcSentence">Where can I get technical information about the free Azure RMS subscription (RMS for individuals)—for example, how it really works, how to take control of the accounts, and which domains can’t be used?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src89" class="srcSentence">You’ll find answers to these questions in the <link xlink:href="2efcb440-fefd-45e9-872b-f471573aadf2">RMS for Individuals and Azure Rights Management</link> topic.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src90" class="srcSentence">How do we regain access to files that were protected by an employee who has now left the organization?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src91" class="srcSentence">Use the super user feature of Azure RMS, which lets authorized users have full owner rights for all use licenses that were granted by your organization’s RMS tenant.</caps:sentence>
            <caps:sentence id="src92" class="srcSentence"> This same feature lets authorized services index and inspect files, as needed.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src93" class="srcSentence">For more information, see <link xlink:href="acb4c00b-d3a9-4d74-94fe-91eeb481f7e3">Configuring Super Users for Azure Rights Management and Discovery Services or Data Recovery</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src94" class="srcSentence">Can Rights Management prevent screen captures?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src95" class="srcSentence">Rights Management does block screen captures from most of the commonly used screen capture tools, which can help to avoid accidental or negligent disclosure of confidential or sensitive information.</caps:sentence>
            <caps:sentence id="src96" class="srcSentence"> However, there are many ways that a user can share data that is displayed on a screen, and taking a screen shot is only one method.</caps:sentence>
            <caps:sentence id="src97" class="srcSentence"> For example, a user intent on sharing displayed information can take a picture of it using their camera phone, retype the data, or simply verbally relay it to somebody.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src98" class="srcSentence">As these examples demonstrate, technology alone cannot always prevent users from sharing data that they should not.</caps:sentence>
            <caps:sentence id="src99" class="srcSentence"> While Rights Management can help to safeguard your important data by using authorization and usage policies, this enterprise rights management solution should be used with other controls.</caps:sentence>
            <caps:sentence id="src100" class="srcSentence"> For example, implement physical security, carefully screen and monitor people who have authorized access to your organization's data, and invest in user education so users understand what data should not be shared.</caps:sentence>
          </para>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src101" class="srcSentence">Where can I find supporting information for Azure RMS—such as legal, compliance, and SLAs?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src102" class="srcSentence">Azure RMS supports other services and also relies on other services.</caps:sentence>
            <caps:sentence id="src103" class="srcSentence"> If you’re looking for information that is related to Azure RMS but not about how to use the Azure RMS service, check the following resources:</caps:sentence>
          </para>
          <para>
            <embeddedLabel>
              <caps:sentence id="src104" class="srcSentence">Legal and privacy:</caps:sentence>
            </embeddedLabel>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src105" class="srcSentence">For Microsoft Azure agreement information: <externalLink><linkText>Microsoft Azure Agreement</linkText><linkUri>http://azure.microsoft.com/support/legal/subscription-agreement/</linkUri></externalLink></caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src106" class="srcSentence">For Microsoft Azure privacy information: <externalLink><linkText>Microsoft Azure Privacy Statement</linkText><linkUri>http://azure.microsoft.com/support/legal/privacy-statement/</linkUri></externalLink></caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <embeddedLabel>
              <caps:sentence id="src107" class="srcSentence">Security, compliance, and auditing:</caps:sentence>
            </embeddedLabel>
          </para>
          <para>
            <caps:sentence id="src108" class="srcSentence">See the <link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df#BKMK_RMScompliance">Security, compliance, and regulatory requirements</link> section in the <link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link> topic.</caps:sentence>
            <caps:sentence id="src109" class="srcSentence"> In addition:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src110" class="srcSentence">For external certifications for Azure RMS: <externalLink><linkText>Microsoft Azure Trust Center</linkText><linkUri>http://azure.microsoft.com/support/trust-center/</linkUri></externalLink></caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src111" class="srcSentence">For FIPS 140 information: <externalLink><linkText>FIPS 140 Validation</linkText><linkUri>https://technet.microsoft.com/library/security/cc750357.aspx</linkUri></externalLink></caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <embeddedLabel>
              <caps:sentence id="src112" class="srcSentence">Service level agreements:</caps:sentence>
            </embeddedLabel>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src113" class="srcSentence">Service level agreement for Azure RMS, by selected country: <externalLink><linkText>Service level agreement</linkText><linkUri>http://microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37</linkUri></externalLink> </caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src114" class="srcSentence">Service level agreement for Azure Active Directory: <externalLink><linkText>Service Level Agreements</linkText><linkUri>http://azure.microsoft.com/support/legal/sla/</linkUri></externalLink></caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <embeddedLabel>
              <caps:sentence id="src115" class="srcSentence">Documentation:</caps:sentence>
            </embeddedLabel>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src116" class="srcSentence">Azure Active Directory Documentation site: <externalLink><linkText>Azure Active Directory</linkText><linkUri>http://azure.microsoft.com/documentation/services/active-directory/</linkUri></externalLink></caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src117" class="srcSentence">Azure Active Directory Library: <externalLink><linkText>Azure Active Directory</linkText><linkUri>http://msdn.microsoft.com/library/azure/jj673460.aspx</linkUri></externalLink></caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src118" class="srcSentence">Office 365 Library: <externalLink><linkText>Office 365</linkText><linkUri>http://technet.microsoft.com/library/dn127064(v=office.14).aspx</linkUri></externalLink></caps:sentence>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section expanded="false">
        <title>
          <caps:sentence id="src119" class="srcSentence">What do I do if my question isn’t here?</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src120" class="srcSentence">Use the links and resources listed in <link xlink:href="7cc73d92-27d6-49ff-a8ab-2fae73519b4b">Information and Support for Azure Rights Management</link>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src121" class="srcSentence">In addition, there are FAQs designed for end-users:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence id="src122" class="srcSentence">FAQ for Rights Management Sharing Application for Windows</caps:sentence>
                  </linkText>
                  <linkUri>https://technet.microsoft.com/dn467883</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence id="src123" class="srcSentence"> FAQ for Rights Management Sharing Application for Mobile and Mac Platforms</caps:sentence>
                  </linkText>
                  <linkUri>https://technet.microsoft.com/dn451248</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence id="src124" class="srcSentence">FAQ for Document Tracking</caps:sentence>
                  </linkText>
                  <linkUri>http://go.microsoft.com/fwlink/?LinkId=523977</linkUri>
                </externalLink>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src125" class="srcSentence">This FAQ page will be updated regularly, with new additions listed in the monthly documentation update announcements on the <externalLink><linkText>Microsoft Rights Management (RMS) Team</linkText><linkUri>http://blogs.technet.com/b/rms/</linkUri></externalLink> blog.</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence id="src126" class="srcSentence">You can use the <externalLink><linkText>docs tag</linkText><linkUri>http://blogs.technet.com/b/rms/archive/tags/docs/</linkUri></externalLink> on the blog, to more easily find these documentation announcements.</caps:sentence>
            </para>
          </alert>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="5214667c-ec69-42ca-8bbf-8cb22da8c62e">Getting Started with Azure Rights Management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSSource>
</caps:SxS>