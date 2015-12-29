---
description: na
keywords: na
pagetitle: 应用程序如何支持 Azure 权限管理
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2cdc7bde-4044-4021-b887-11476f99afd9
---
# 应用程序如何支持 Azure 权限管理
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="zh-CN">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="2c4ef293537bf2a2fd133f2ea35f9b2f" id="tgt1" class="tgtSentence">使用以下信息可以帮助你了解最终用户应用程序（例如 Office 应用程序，包括 Word、Excel、PowerPoint 和 Outlook）和服务（例如 Exchange 和 SharePoint）如何才能使用 Microsoft <token>aad_rightsmanagement_1</token> 来帮助保护组织的数据：</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9#BKMK_SharingAppIntro">RMS sharing application for Windows and mobile platforms</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9#BKMK_OfficeAppsIntro">Office applications: Word, Excel, PowerPoint, Outlook</link>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9#BKMK_ExchangeIntro">Exchange Online and Exchange Server</link>
                </para>
              </listItem>
              <listItem>
                <para>
                  <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9#BKMK_SharePointIntro">SharePoint Online and SharePoint Server</link>
                </para>
              </listItem>
            </list>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9#BKMK_FCIIntro">File servers that run Windows Server and use File Classification Infrastructure (FCI)</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9#BKMK_APIAppsIntro">Other applications that support the RMS APIs</link>
            </para>
          </listItem>
        </list>
        <alert class="note">
          <para>
            <caps:sentence sentenceid="21b6d2aefffd2ec28b5ead032a3db9a3" id="tgt2" class="tgtSentence">若要确认 <token>aad_rightsmanagement_1</token> (Azure RMS) 支持的应用程序和版本，请参阅 <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>。</caps:sentence>
          </para>
        </alert>
        <para>
          <caps:sentence sentenceid="a939cf5b90f330679b74eda704a74a2a" id="tgt3" class="tgtSentence">某些情况下，将根据你配置的策略来自动应用信息保护。</caps:sentence>
          <caps:sentence sentenceid="d9f9cc689fc84f4139db76ae8c620182" id="tgt4" class="tgtSentence"> 例如，SharePoint 库、分类文件和 Exchange 传输规则就属于此种情况。</caps:sentence>
          <caps:sentence sentenceid="7d505a1b797eb9004a5090d00fc4d235" id="tgt5" class="tgtSentence"> 在其他情况下，用户必须自动通过应用程序（不管是通过选择模板还是通过选择特定选项）来应用信息保护。</caps:sentence>
          <caps:sentence sentenceid="cf5389cd798d49b035f49af4b3a61fd6" id="tgt6" class="tgtSentence"> 例如，用户可通过电子邮件来共享文件，或者通过将访问权限和使用权限限制给选定用户或组织外部用户来保护现有文件。</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="2069038249ee40a1074eac95aba018e1" id="tgt7" class="tgtSentence">利用模板，用户（以及配置策略的管理员）能够更加轻松地应用正确级别的保护，并将访问权限限制给组织内部人员。</caps:sentence>
          <caps:sentence sentenceid="e8cab0ae1534575e30ca93f416212a59" id="tgt8" class="tgtSentence"> 虽然 <token>aad_rightsmanagement_1</token> 附带了两个默认模板，但你可能还希望创建自定义模板，以减少使用模板指定各个选项所需的时间。</caps:sentence>
          <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt9" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="1775d8d0-9a59-42c8-914f-ce285b71ac1c">Configuring Custom Templates for Azure Rights Management</link>。</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="c62e29cade752dd82a469ce01f55d682" id="tgt10" class="tgtSentence">对于用户必须自行应用信息保护的情况，请务必为他们提供有关信息保护应用方式和时机的说明和指导。</caps:sentence>
          <caps:sentence sentenceid="a96dc4e5fc951bc693affb056185d9dc" id="tgt11" class="tgtSentence"> 这些说明应该专门针对他们使用的特定应用程序和版本及其使用方式，有关信息保护应用时机和方式的指导应该适用于你的企业。</caps:sentence>
          <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt12" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="58f9a6ff-4121-4c8c-9865-1bb290604ad2">Instruct Users How to Protect Files by using Azure Rights Management</link>。</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="a1cb7985a9a932e604b1671e67d86954" id="tgt13" class="tgtSentence">有关如何为 Azure RMS 配置 这些应用程序的信息，请参阅<link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36">Configuring Applications for Azure Rights Management</link>。</caps:sentence>
        </para>
        <alert class="tip">
          <para>
            <caps:sentence sentenceid="515a0266be4c03e953d3b7826bb0c722" id="tgt14" class="tgtSentence">有关使用 Azure RMS 的应用程序的示例和屏幕截图，请参阅<link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link>主题中的<link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df#BKMK_RMSpictures">Azure RMS in action: What administrators and users see</link>部分。</caps:sentence>
          </para>
        </alert>
      </introduction>
      <section address="BKMK_SharingAppIntro">
        <title>
          <caps:sentence sentenceid="8fd6704f8167322156faf50718f02152" id="tgt15" class="tgtSentence">Windows 和移动平台的 RMS 共享应用程序</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="fd0b72a29488e67ffcbcf27f2ef04deb" id="tgt16" class="tgtSentence">RMS 共享应用程序是支持 Office 2010 所必需的免费可下载应用程序，但我们也建议将其用于 Windows 计算机、Mac 计算机和移动设备。</caps:sentence>
            <caps:sentence sentenceid="e5cd7ad1339c864db3e8c92009401d49" id="tgt17" class="tgtSentence"> 它的一大优点是能够为无法以本机方式支持 <token>aad_rightsmanagement_2</token> 的应用程序和文件提供通用保护，这意味着所有文件都能得到保护。</caps:sentence>
            <caps:sentence sentenceid="075f4dd6531d816048dcfa5a6a6c0813" id="tgt18" class="tgtSentence"> 有关不同保护级别的详细信息，请参阅 <externalLink><linkText>Rights Management 共享应用程序管理员指南</linkText><linkUri>http://technet.microsoft.com/library/dn339003.aspx</linkUri></externalLink>中的<externalLink><linkText>保护级别 – 本机和常规</linkText><linkUri>http://technet.microsoft.com/library/dn339003.aspx#BKMK_LevelsofProtection</linkUri></externalLink>部分。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="6aa90e52909c533510b6821027685f23" id="tgt19" class="tgtSentence">当用户通过使用 RMS 共享应用程序保护其文件时，他们还可以跟踪他们保护的文档，如有必要，撤消对这些文档的访问权限。</caps:sentence>
            <caps:sentence sentenceid="66530490023015292bfda85e3d212308" id="tgt20" class="tgtSentence"> 他们通过使用<externalLink><linkText>文档跟踪站点</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=529562</linkUri></externalLink>来执行此操作。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="4e0eeffbbcafe9cf44bca0caa805ecd7" id="tgt21" class="tgtSentence">对于 Windows 计算机，RMS 共享应用程序可与用户已在使用的应用程序轻松集成，并且增强这些应用程序的功能： </caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="0be37b6164a02efa383d5b8763fb562f" id="tgt22" class="tgtSentence">安装 Word、Excel、PowerPoint 和 Outlook 的 Office 加载项。</caps:sentence>
                <caps:sentence sentenceid="c789093054fa885d12a8fa0fa74dc0a7" id="tgt23" class="tgtSentence"> 这样可在功能区上为用户提供“共享保护内容”按钮，该按钮可以调用一个易于使用的对话框，其中包含用于保护要通过电子邮件发送的文件的最常用设置<ui></ui>。</caps:sentence>
                <caps:sentence sentenceid="9c466cfa6fd5a1edc29094431b2d93cb" id="tgt24" class="tgtSentence"> 此按钮还提供了用于访问文档跟踪站点的快捷方式。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="1ecc769afb277fabf142f7c0ecc4352b" id="tgt25" class="tgtSentence">文件资源管理器的全新右键单击选项。</caps:sentence>
                <caps:sentence sentenceid="c789093054fa885d12a8fa0fa74dc0a7" id="tgt26" class="tgtSentence"> 它可在功能区上为用户提供“就地保护”选项，该选项可以调用一个易于使用的对话框，其中包含用于保护存储在磁盘上的文件的最常用设置<ui></ui>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="294ad2990df50e4179e749fef0bf473c" id="tgt27" class="tgtSentence">一个查看器，用于打开受 <token>aad_rightsmanagement_2</token> 保护的文件。</caps:sentence>
                <caps:sentence sentenceid="45e20352474135fd480a5176e747dc67" id="tgt28" class="tgtSentence"> 当没有其他已安装的应用程序可以打开受保护文件时，将自动调用此查看器。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="bb18a942a01106390bffa2da565f482a" id="tgt29" class="tgtSentence">Office 2010 的后端配置，让此套件的 Word、Excel、PowerPoint 和 Outlook 能够与 <token>aad_rightsmanagement_1</token> 无缝集成。</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="77e5cb308abac096b57cc475cbed24ea" id="tgt30" class="tgtSentence">虽然可通过使用 <externalLink><linkText>Microsoft Rights Management 页</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=303970</linkUri></externalLink>为单台计算机下载和安装适用于 Windows 的 RMS 共享应用程序，但它也支持企业部署的静默安装和自定义配置。</caps:sentence>
            <caps:sentence sentenceid="d3d094e25e7ac14a4098802b5757e141" id="tgt31" class="tgtSentence"> 有关详细信息，请参阅下列资源：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence sentenceid="45fd73cece8c888a3560a65a749417d4" id="tgt32" class="tgtSentence">权限管理共享应用程序管理员指南</caps:sentence>
                  </linkText>
                  <linkUri>http://technet.microsoft.com/library/dn339003.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence sentenceid="5a82d1d6328fcf4e332c7353808716e6" id="tgt33" class="tgtSentence">权限管理共享应用程序用户指南</caps:sentence>
                  </linkText>
                  <linkUri>http://technet.microsoft.com/library/dn339006.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="376f96fbe49dacb622794e28acf9f6f0" id="tgt34" class="tgtSentence">适用于移动设备的 RMS 共享应用程序支持最常用的移动设备，例如 iPad 和 iPhone、Android、Windows Phone 和 Windows RT。</caps:sentence>
            <caps:sentence sentenceid="9124e99e611bb6ed339cd1e09193367a" id="tgt35" class="tgtSentence"> 用户可以从相关应用商店下载此应用，<externalLink><linkText>Microsoft 权限管理页</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=303970</linkUri></externalLink>提供这些应用商店的链接。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_OfficeAppsIntro">
        <title>
          <caps:sentence sentenceid="c34ae920feec696b27cfd3b100ae6a72" id="tgt36" class="tgtSentence">Office 应用程序：Word、Excel、PowerPoint、Outlook</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="cfc201439612ce748c1ec3f1f3d86dd5" id="tgt37" class="tgtSentence">这些应用程序通过使用信息权限管理 (IRM) 以本机方式支持权限管理，让用户能够将保护应用于已保存文档，或者应用于要发送的电子邮件。</caps:sentence>
            <caps:sentence sentenceid="1718a8c16ac552e71ccbb9eec5b54f3f" id="tgt38" class="tgtSentence"> 用户可以应用模板或选择针对访问、权限和使用限制的高度自定义设置。</caps:sentence>
            <caps:sentence sentenceid="9b8e7d0f7d0935ea5a46a19be7710ebd" id="tgt39" class="tgtSentence"> 例如，用户可以通过配置文件仅允许组织内人员访问该文件，还可以控制是否允许编辑该文件、是否将其限制为只读，以及是否禁止打印该文件。</caps:sentence>
            <caps:sentence sentenceid="dc28da06aa5a2671b8f829e3ed76f54f" id="tgt40" class="tgtSentence"> 对于时间敏感型文件，可以配置一个过期时间（直接由用户配置，或者应用模板进行配置），在过期之后无法再访问该文件。</caps:sentence>
            <caps:sentence sentenceid="d9b247a102a90eafec6daf4206618f74" id="tgt41" class="tgtSentence"> 对于 Outlook，用户还可以选择“不要转发”选项来帮助防止数据泄漏<ui></ui>。</caps:sentence>
          </para>
        </content>
        <sections>
          <section address="BKMK_ExchangeIntro">
            <title>
              <caps:sentence sentenceid="67f7404f1323c5a892421c8c12d68e94" id="tgt42" class="tgtSentence">Exchange Online 和 Exchange Server</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="2ea4c69dac443e59bc9ae5b0f170eefe" id="tgt43" class="tgtSentence">使用 Exchange Online 或 Exchange Server 时，你可以使用信息权限管理 (IRM) 集成，它提供更多信息保护解决方案：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="ccd7c8b782d6ad1b11686823d7a011f5" id="tgt44" class="tgtSentence">
                      <legacyBold>Exchange ActiveSync IRM</legacyBold>，让移动设备能够保护和使用受保护的电子邮件。</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="f451b332c6df1804f334e74f6d5a65af" id="tgt45" class="tgtSentence">
                      <legacyBold>Outlook Web 应用</legacyBold>的 RMS 支持，其实施方法与 Outlook 客户端类似，让用户能够通过模板或指定各个选项来保护电子邮件，用户能够阅读和使用发送给他们的受保护电子邮件。</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="c9c5dc83067177f744e8bc3c63943289" id="tgt46" class="tgtSentence">适用于 Outlook 客户端的<legacyBold>保护规则</legacyBold>，管理员能够配置这些规则，以便自动将 RMS 模板应用于发送给指定收件人的电子邮件。</caps:sentence>
                    <caps:sentence sentenceid="a255ba072deb5d2699736fd0910bcbe3" id="tgt47" class="tgtSentence"> 例如，在将内部电子邮件发送至法律部门时，只允许法律部门成员阅读这些邮件，而且不能转发。</caps:sentence>
                    <caps:sentence sentenceid="84ba63ce5a27d7348e4a2798bd41f483" id="tgt48" class="tgtSentence"> 在发送电子邮件之前，用户可以看到应用于电子邮件的保护，而默认情况下，如果他们确定该电子邮件不是必须发送的，则可将其删除。</caps:sentence>
                    <caps:sentence sentenceid="823755670240569244e044ad2505f966" id="tgt49" class="tgtSentence"> 电子邮件在发送之前进行了加密。</caps:sentence>
                    <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt50" class="tgtSentence"> 有关详细信息，请参阅 Exchange 库中的 <externalLink><linkText>Outlook 保护规则</linkText><linkUri>http://technet.microsoft.com/library/dd638178(v=exchg.150).aspx</linkUri></externalLink>和<externalLink><linkText>创建 Outlook 保护规则</linkText><linkUri>http://technet.microsoft.com/library/dd638196(v=exchg.150).aspx</linkUri></externalLink>。</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="f3f1bc9258eb108fc1b2821887331a37" id="tgt51" class="tgtSentence">
                      <legacyBold>传输规则</legacyBold>，管理员能够配置这些规则，根据各种属性（例如发件人、收件人、邮件主题和内容），自动将 RMS 模板应用于电子邮件。</caps:sentence>
                    <caps:sentence sentenceid="dcb4186ec20acb80780e40dce7156053" id="tgt52" class="tgtSentence"> 这些规则在概念上类似于保护规则，但不允许用户取消保护；这些规则可以应用于 Outlook Web Access 和通过移动设备发送的电子邮件；在从客户端发送电子邮件之前，这些规则不对其进行加密。</caps:sentence>
                    <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt53" class="tgtSentence"> 有关详细信息，请参阅 Exchange 库中的<externalLink><linkText>创建传输保护规则</linkText><linkUri>http://technet.microsoft.com/library/dd302432.aspx</linkUri></externalLink>。</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="70adc4e6e8ba10f5578c68fea24fe6ba" id="tgt54" class="tgtSentence">
                      <legacyBold>数据丢失预防 (DLP) 策略</legacyBold>，包含一系列筛选邮件的条件，有助于防止机密或敏感内容（例如个人信息或信用卡信息）的数据丢失。</caps:sentence>
                    <caps:sentence sentenceid="da85c29db1f099c0e441560b7d91e8ae" id="tgt55" class="tgtSentence"> 检测到敏感数据时，可以使用策略提示，根据电子邮件中的内容，警告用户他们可能需要应用信息保护。</caps:sentence>
                    <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt56" class="tgtSentence"> 有关详细信息，请参阅 Exchange 库中的<externalLink><linkText>数据丢失预防</linkText><linkUri>http://technet.microsoft.com/library/jj150527(v=exchg.150).aspx</linkUri></externalLink>。</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="d607bed5cdf67efd23203db0bb40c0b3" id="tgt57" class="tgtSentence">
                      <legacyBold>Office 365 邮件加密</legacyBold>，使用传输规则将加密电子邮件发送到公司外部人员，该电子邮件在浏览器中阅读，浏览器界面与 Outlook Web App 相似。</caps:sentence>
                    <caps:sentence sentenceid="8d4a2008bddc59432f7148a63be55a69" id="tgt58" class="tgtSentence"> 你可以在公司的加密电子邮件中自定义免责声明文本和标题文本，甚至添加你公司的徽标。</caps:sentence>
                    <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt59" class="tgtSentence"> 有关详细信息，请参阅 Office 网站上的 <externalLink><linkText>Office 365 邮件加密</linkText><linkUri>http://office.microsoft.com/o365-message-encryption-FX104179182.aspx</linkUri></externalLink>。</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence sentenceid="c3bc6609c95b85b304a0589e6cfcb774" id="tgt60" class="tgtSentence">如果使用 Exchange Server，则可以通过部署 RMS 连接器，将其用作内部部署服务器和 RMS 云服务之间的中继，从而利用 <token>aad_rightsmanagement_1</token> 的信息保护功能。</caps:sentence>
                <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt61" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066">Deploying the Azure Rights Management Connector</link>。</caps:sentence>
              </para>
            </content>
          </section>
          <section address="BKMK_SharePointIntro">
            <title>
              <caps:sentence sentenceid="8e0cd9ed0afa0870825b16ce70a4dd8f" id="tgt62" class="tgtSentence">SharePoint Online 和 SharePoint Server</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="11306bf874b80c12c3247fd908151ca7" id="tgt63" class="tgtSentence">使用 SharePoint Online 或 SharePoint Server 时，你可以使用信息权限管理 (IRM) 集成，让管理员保护列表或库，这样当用户签出文档时，文件将会受到保护，只有授权人员能够根据你指定的信息保护策略来查看和使用文件。</caps:sentence>
                <caps:sentence sentenceid="87f2d68ebe63b9e14760ad4494a10db6" id="tgt64" class="tgtSentence"> 例如，文件可能是只读的，可能会禁用文本复制，可能会阻止保存本地副本，可能会阻止打印文件。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="ac58e3868c93af0d71a146c5418eff47" id="tgt65" class="tgtSentence">对于列表和库，始终由管理员（永远不会由最终用户）应用信息保护。</caps:sentence>
                <caps:sentence sentenceid="75a917d19256af7f867dc3c5fb2400c2" id="tgt66" class="tgtSentence"> 对于该容器中的所有文档，信息保护是在列表或库级别上应用的，而不是在单独文件级别上应用。</caps:sentence>
                <caps:sentence sentenceid="56db1e6eb4802caa6d010e0430aa8f13" id="tgt67" class="tgtSentence">  如果你使用 SharePoint Online，用户还可以对其 OneDrive for Business 库应用 IRM。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="e60a59662173d63f008158c393b35aac" id="tgt68" class="tgtSentence">必须首先为 SharePoint 启用 IRM 服务。</caps:sentence>
                <caps:sentence sentenceid="2159e92963440c41a292a010b9a5d489" id="tgt69" class="tgtSentence"> 然后，为库指定信息权限管理。</caps:sentence>
                <caps:sentence sentenceid="9c7370f94dd3022c3e2ee49721c41bf7" id="tgt70" class="tgtSentence"> 对于 SharePoint Online 和 OneDrive for Business，用户还可以为其 OneDrive for Business 库指定信息权限管理。</caps:sentence>
                <caps:sentence sentenceid="b7a1f410b77350f8d6137a88cfcad960" id="tgt71" class="tgtSentence"> SharePoint 不使用权限策略模板，虽然你可以选择的 SharePoint 配置设置非常匹配你可以在模板中指定的设置。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="8317ebcce681229e7bd374b583289a41" id="tgt72" class="tgtSentence">如果使用 SharePoint Server，则可以通过部署 RMS 连接器，将其用作内部部署服务器和 RMS 云服务之间的中继，从而利用 <token>aad_rightsmanagement_1</token>的信息保护功能。</caps:sentence>
                <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt73" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066">Deploying the Azure Rights Management Connector</link>。</caps:sentence>
              </para>
              <alert class="note">
                <para>
                  <caps:sentence sentenceid="33c18a321ba13e1200c1d8c1ecb70c79" id="tgt74" class="tgtSentence">目前，将 IRM 用于 SharePoint 时有一些限制：</caps:sentence>
                </para>
                <list class="bullet">
                  <listItem>
                    <para>
                      <caps:sentence sentenceid="a7bf445eab0ac67103e642fc6b2133b0" id="tgt75" class="tgtSentence">不能使用在 Azure 经典门户中管理的默认模板或自定义模板。</caps:sentence>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence sentenceid="926b48b0499febb2d39fa4b63e5c3f8a" id="tgt76" class="tgtSentence">不支持带 .PPDF 文件扩展名的受保护 PDF 文件。</caps:sentence>
                      <caps:sentence sentenceid="781c671e997e3f4dc1db09aba8f48176" id="tgt77" class="tgtSentence"> 当你使用本机支持 RMS 的 PDF 阅读器时时，支持带 PDF 文件扩展名的文件以及受 RMS 本机保护的文件。</caps:sentence>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence sentenceid="1034024627fd79b72907a8bb0a8f0244" id="tgt78" class="tgtSentence"> 由于移动设备上的 Office 尚不支持 RMS，因此这些设备必须使用浏览器来查看已使用 RMS 保护的文件，并且这些文件是只读的。</caps:sentence>
                    </para>
                  </listItem>
                </list>
              </alert>
              <para>
                <caps:sentence sentenceid="5b1283e08025c47323a453cb8a89ac41" id="tgt79" class="tgtSentence">Azure RMS 会在从 SharePoint 下载文档时为文档应用使用限制和数据加密，而不是在 SharePoint 中首次创建文档或将其上载到库中时进行此类操作。</caps:sentence>
                <caps:sentence sentenceid="9b69c7606bc7bed2bc13c5b92794bd54" id="tgt80" class="tgtSentence"> 有关如何在下载文档前对其进行保护的信息，请参阅 SharePoint 文档中的 <externalLink><linkText>OneDrive for Business 和 SharePoint Online 中的数据加密</linkText><linkUri>https://technet.microsoft.com/library/dn905447.aspx</linkUri></externalLink>。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="17484494547fc6c5721bd7f1b69375cb" id="tgt81" class="tgtSentence">有关在 SharePoint 中使用 Azure RMS 的详细信息，请参阅 Office 博客中的以下文章：<externalLink><linkText>SharePoint 和 SharePoint 中的信息权限管理的新增功能</linkText><linkUri>http://blogs.office.com/2012/11/09/whats-new-with-information-rights-management-in-sharepoint-and-sharepoint-online/</linkUri></externalLink></caps:sentence>
              </para>
            </content>
          </section>
        </sections>
      </section>
      <section address="BKMK_FCIIntro">
        <title>
          <caps:sentence sentenceid="cf4019b714b3ac39dcc146f936037bd6" id="tgt82" class="tgtSentence">运行 Windows Server 和使用文件分类基础结构 (FCI) 的文件服务器</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="d908b46655c04cb2e35d69dd6488ceb4" id="tgt83" class="tgtSentence">当你将 Windows Server 配置为使用文件分类基础结构时，此文件服务器资源管理器功能可以扫描本地文件，并确定它们是否包含敏感数据。</caps:sentence>
            <caps:sentence sentenceid="4961f30cb50d823b5d00f874631e9f6a" id="tgt84" class="tgtSentence"> 对于满足此条件的文件，可以使用管理员定义的分类属性，对其进行标记。</caps:sentence>
            <caps:sentence sentenceid="4aa3dcae3af9ff68edfd186b27b01fdb" id="tgt85" class="tgtSentence"> 然后，文件分类基础结构可根据分类执行自动操作。</caps:sentence>
            <caps:sentence sentenceid="c6fbc9296e4e611d21ecf0ca7d28f1c4" id="tgt86" class="tgtSentence"> 其中一种操作是使用 <token>aad_rightsmanagement_1</token> 来应用信息保护，并部署 Rights Management 连接器（也称为 RMS 连接器）。</caps:sentence>
            <caps:sentence sentenceid="a37daa5cd46e9ab0673d063ae2a407a8" id="tgt87" class="tgtSentence"> 然后，由 Azure RMS 自动保护 Office 文件。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="03b34b52e6f0de8dce1f577ed46193da" id="tgt88" class="tgtSentence">若要保护所有文件类型，将不使用 RMS 连接器，而是改为使用 <externalLink><linkText>RMS 保护工具</linkText><linkUri>https://www.microsoft.com/en-us/download/details.aspx?id=47256</linkUri></externalLink>中提供的 cmdlet 运行 Windows PowerShell 脚本。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="e0588fb42cce3108a9e33302579446b5" id="tgt89" class="tgtSentence">分类策略是完全可以配置的，并且具有高度的可扩展性，因此你可以防止未授权和已授权用户可能发生的数据泄漏。</caps:sentence>
            <caps:sentence sentenceid="f58ed9a22eda60004e56bd62c86d3cce" id="tgt90" class="tgtSentence"> 它甚至有助于降低网络管理员的数据泄漏风险，因为你可以配置不要求这些管理员具有文件访问权限的策略。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="9b9f80a1107236a61414125b1d9b0277" id="tgt91" class="tgtSentence">有关为 Office 文件部署和配置 RMS 连接器的说明，请参阅 <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066">Deploying the Azure Rights Management Connector</link>。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="aec5dddd61320b936d5b0be71d59a777" id="tgt92" class="tgtSentence">有关对所有文件类型使用 Windows PowerShell 脚本的说明，请参阅 <link xlink:href="9aa693db-9727-4284-9f64-867681e114c9">RMS Protection with Windows Server File Classification Infrastructure (FCI)</link>。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_APIAppsIntro">
        <title>
          <caps:sentence sentenceid="b8c31eeb7e365689f25cc0defcdab212" id="tgt93" class="tgtSentence">支持 RMS API 的其他应用程序</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="6394907342680e3055cf25f9711c01b5" id="tgt94" class="tgtSentence">使用 RMS SDK，内部开发人员可以编写业务线应用程序，以本机方式支持 <token>aad_rightsmanagement_1</token>。</caps:sentence>
            <caps:sentence sentenceid="946270a3df45ea8b1523cac3309d9c66" id="tgt95" class="tgtSentence"> 信息保护与这些应用程序的集成方式取决于编写应用程序的方式。</caps:sentence>
            <caps:sentence sentenceid="855aa387257d2b17f6c702a660d64fe6" id="tgt96" class="tgtSentence"> 例如，这种集成可以是自动应用的，只需很少的用户交互，或者为了提供更多自定义体验，可能会提示用户配置相关设置，以便对文件应用信息保护。</caps:sentence>
            <caps:sentence sentenceid="60eed1e9a839539dedf8e20824c39bf6" id="tgt97" class="tgtSentence"> 有关 SDK 的详细信息，请参阅 <externalLink><linkText>Microsoft Rights Management SDK</linkText><linkUri>http://msdn.microsoft.com/library/hh552972(v=vs.85).aspx</linkUri></externalLink>。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="162976d03051109b1fa902eb1235c8d3" id="tgt98" class="tgtSentence">同样，很多软件供应商提供各种应用程序作为信息保护解决方案，也称为企业权限管理 (ERM) 产品。</caps:sentence>
            <caps:sentence sentenceid="fe641e81032d7a5691d99d37e23f62e0" id="tgt99" class="tgtSentence"> 常见的例子是支持特定平台的 <token>aad_rightsmanagement_2</token> 的 PDF 阅读器。</caps:sentence>
            <caps:sentence sentenceid="34560e4a2e8f794afb6d14351b400ba9" id="tgt100" class="tgtSentence"> 可以使用 <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link> 主题的 <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_ClientCapabilities">Client device capabilities</link> 部分中的表来确定支持 RMS 的应用程序（启用 RMS 的应用程序），然后使用 web 搜索购买或下载应用程序。</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence sentenceid="22d81c8be4b374f318d669e13cbdc1c8" id="tgt101" class="tgtSentence">对于新发布的应用程序，请查看在 <link xlink:href="7cc73d92-27d6-49ff-a8ab-2fae73519b4b">Information and Support for Azure Rights Management</link>中列出的 RMS 社区频道。</caps:sentence>
            </para>
          </alert>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="5214667c-ec69-42ca-8bbf-8cb22da8c62e">Getting started with Azure Rights Management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSTarget>
  <caps:SxSSource locale="en-US">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence id="src1" class="srcSentence">Use the following information to help you understand how your end-user applications (such as the Office applications, Word, Excel, PowerPoint, and Outlook) and services (such as Exchange and SharePoint) can use Microsoft <token>aad_rightsmanagement_1</token> to help protect your organization’s data:</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9#BKMK_SharingAppIntro">RMS sharing application for Windows and mobile platforms</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9#BKMK_OfficeAppsIntro">Office applications: Word, Excel, PowerPoint, Outlook</link>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9#BKMK_ExchangeIntro">Exchange Online and Exchange Server</link>
                </para>
              </listItem>
              <listItem>
                <para>
                  <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9#BKMK_SharePointIntro">SharePoint Online and SharePoint Server</link>
                </para>
              </listItem>
            </list>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9#BKMK_FCIIntro">File servers that run Windows Server and use File Classification Infrastructure (FCI)</link>
            </para>
          </listItem>
          <listItem>
            <para>
              <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9#BKMK_APIAppsIntro">Other applications that support the RMS APIs</link>
            </para>
          </listItem>
        </list>
        <alert class="note">
          <para>
            <caps:sentence id="src2" class="srcSentence">To verify the applications and versions that <token>aad_rightsmanagement_1</token> (Azure RMS) supports, see <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>.</caps:sentence>
          </para>
        </alert>
        <para>
          <caps:sentence id="src3" class="srcSentence">In some cases, information protection is automatically applied, according to policies that you configure.</caps:sentence>
          <caps:sentence id="src4" class="srcSentence"> For example, this is the case with SharePoint libraries, classified files, and Exchange transport rules.</caps:sentence>
          <caps:sentence id="src5" class="srcSentence"> In other cases, users must apply information protection themselves from their applications, either by selecting a template or by selecting specific options.</caps:sentence>
          <caps:sentence id="src6" class="srcSentence"> For example, this is the case when users share a file by email, or protect a file in-place by restricting access or usage to selected users or to users outside the organization.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src7" class="srcSentence">Templates make it easier for users (and administrators who configure policies) to apply the correct level of protection and restrict access to people inside your organization.</caps:sentence>
          <caps:sentence id="src8" class="srcSentence"> Although <token>aad_rightsmanagement_1</token> comes with two default templates, you will probably want to create custom templates to reduce the times when they have to specify individual options.</caps:sentence>
          <caps:sentence id="src9" class="srcSentence"> For more information, see <link xlink:href="1775d8d0-9a59-42c8-914f-ce285b71ac1c">Configuring Custom Templates for Azure Rights Management</link>.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src10" class="srcSentence">For the cases where users must apply information protection themselves, be sure to provide them with instructions and guidance how and when to do this.</caps:sentence>
          <caps:sentence id="src11" class="srcSentence"> The instructions should be specific for the application and versions that they use and how they use them, and the guidance for when and how to apply information protection should be appropriate for your business.</caps:sentence>
          <caps:sentence id="src12" class="srcSentence"> For more information, see <link xlink:href="58f9a6ff-4121-4c8c-9865-1bb290604ad2">Instruct Users How to Protect Files by using Azure Rights Management</link>.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src13" class="srcSentence">For information about how to configure these applications for Azure RMS, see <link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36">Configuring Applications for Azure Rights Management</link>.</caps:sentence>
        </para>
        <alert class="tip">
          <para>
            <caps:sentence id="src14" class="srcSentence">For examples and screenshots of applications using Azure RMS, see the <link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df#BKMK_RMSpictures">Azure RMS in action: What administrators and users see</link> section from the <link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link> topic.</caps:sentence>
          </para>
        </alert>
      </introduction>
      <section address="BKMK_SharingAppIntro">
        <title>
          <caps:sentence id="src15" class="srcSentence">RMS sharing application for Windows and mobile platforms</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src16" class="srcSentence">The RMS sharing application is a free, downloadable application that is required to support Office 2010, but also recommended for Windows computers, Mac computers, and mobile devices.</caps:sentence>
            <caps:sentence id="src17" class="srcSentence"> One of its benefits is that it can apply generic protection for applications and files that do not natively support <token>aad_rightsmanagement_2</token>, which means that all files can be protected.</caps:sentence>
            <caps:sentence id="src18" class="srcSentence"> For more information about the different protection levels, see the <externalLink><linkText>Level of protection – native and generic</linkText><linkUri>http://technet.microsoft.com/library/dn339003.aspx#BKMK_LevelsofProtection</linkUri></externalLink> section from the <externalLink><linkText>Rights Management sharing application administrator guide</linkText><linkUri>http://technet.microsoft.com/library/dn339003.aspx</linkUri></externalLink>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src19" class="srcSentence">When users protect their files by using the RMS sharing application, they can also track the documents that they protected, and if necessary, revoke access to them.</caps:sentence>
            <caps:sentence id="src20" class="srcSentence"> They do this by using the <externalLink><linkText>document tracking site</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=529562</linkUri></externalLink>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src21" class="srcSentence">For Windows computers, the RMS sharing application unobtrusively integrates with and enhances the  applications that users already use: </caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src22" class="srcSentence">An Office add-in for Word, Excel, PowerPoint, and Outlook is installed.</caps:sentence>
                <caps:sentence id="src23" class="srcSentence"> This provides users with a <ui>Share Protected</ui> button on the ribbon, which invokes an easy-to-use dialog box of settings that are most commonly used to protect files to be emailed.</caps:sentence>
                <caps:sentence id="src24" class="srcSentence"> This button also provides a quick way to access the document tracking site.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src25" class="srcSentence">A new right-click option for File Explorer.</caps:sentence>
                <caps:sentence id="src26" class="srcSentence"> This provides users with a <ui>Protect in-place</ui> option, which invokes an easy-to-use dialog box of settings that are most commonly used to protect files stored on a disk.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src27" class="srcSentence">A viewer to open files that have been protected by <token>aad_rightsmanagement_2</token>.</caps:sentence>
                <caps:sentence id="src28" class="srcSentence"> This viewer is automatically invoked when there is no other application installed that could open the protected file.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src29" class="srcSentence">Backend configuration for Office 2010 that lets Word, Excel, PowerPoint, and Outlook from this suite work seamlessly with <token>aad_rightsmanagement_1</token>.</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src30" class="srcSentence">Although the RMS sharing application for Windows can be downloaded and installed for a single computer by using the <externalLink><linkText>Microsoft Rights Management page</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=303970</linkUri></externalLink>, it also supports an enterprise deployment for silent installation and custom configuration.</caps:sentence>
            <caps:sentence id="src31" class="srcSentence"> For more information, see the following resources:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence id="src32" class="srcSentence">Rights Management sharing application administrator guide</caps:sentence>
                  </linkText>
                  <linkUri>http://technet.microsoft.com/library/dn339003.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
            <listItem>
              <para>
                <externalLink>
                  <linkText>
                    <caps:sentence id="src33" class="srcSentence">Rights Management sharing application user guide</caps:sentence>
                  </linkText>
                  <linkUri>http://technet.microsoft.com/library/dn339006.aspx</linkUri>
                </externalLink>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src34" class="srcSentence">The RMS sharing application for mobile devices supports the most commonly used mobile devices, such as iPad and iPhone, Android, Windows Phone, and Windows RT.</caps:sentence>
            <caps:sentence id="src35" class="srcSentence"> Users can download this app from the relevant store, and there are links to these from the <externalLink><linkText>Microsoft Rights Management page</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=303970</linkUri></externalLink>.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_OfficeAppsIntro">
        <title>
          <caps:sentence id="src36" class="srcSentence">Office applications: Word, Excel, PowerPoint, Outlook</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src37" class="srcSentence">These applications natively support Rights Management by using information rights management (IRM) and let users apply protection to a saved document or to an email message to be sent.</caps:sentence>
            <caps:sentence id="src38" class="srcSentence"> Users can apply templates or choose very customized settings for access, rights, and usage restrictions.</caps:sentence>
            <caps:sentence id="src39" class="srcSentence"> For example, users can configure a file so that it can be accessed only by people in your organization, or control whether the file can be edited, or restricted to read-only, or prevent it from being printed.</caps:sentence>
            <caps:sentence id="src40" class="srcSentence"> For time-sensitive files, an expiration time can be configured (directly by users or by applying a template) for when the file can no longer be accessed.</caps:sentence>
            <caps:sentence id="src41" class="srcSentence"> For Outlook, users can also choose the <ui>Do Not Forward</ui> option to help prevent data leakage.</caps:sentence>
          </para>
        </content>
        <sections>
          <section address="BKMK_ExchangeIntro">
            <title>
              <caps:sentence id="src42" class="srcSentence">Exchange Online and Exchange Server</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src43" class="srcSentence">When you use Exchange Online or Exchange Server, you can use information rights management (IRM) integration, which provides additional information protection solutions:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src44" class="srcSentence">
                      <legacyBold>Exchange ActiveSync IRM</legacyBold> so that mobile devices can protect and consume protected email messages.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src45" class="srcSentence">RMS support for the <legacyBold>Outlook Web App</legacyBold>, implemented similarly to the Outlook client, so that users can protect email messages by templates or by specifying individual options, and users can read and use protected email messages that are sent to them.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src46" class="srcSentence">
                      <legacyBold>Protection rules</legacyBold> for Outlook clients that an administrator configures to automatically apply RMS templates to email messages for specified recipients.</caps:sentence>
                    <caps:sentence id="src47" class="srcSentence"> For example, when internal emails are sent to your legal department, they can only be read by members of the legal department and cannot be forwarded.</caps:sentence>
                    <caps:sentence id="src48" class="srcSentence"> Users see the protection applied to the email message before sending it, and by default, they can remove it if they decide it is not necessary.</caps:sentence>
                    <caps:sentence id="src49" class="srcSentence"> Emails are encrypted before they are sent.</caps:sentence>
                    <caps:sentence id="src50" class="srcSentence"> For more information, see <externalLink><linkText>Outlook Protection Rules</linkText><linkUri>http://technet.microsoft.com/library/dd638178(v=exchg.150).aspx</linkUri></externalLink> and <externalLink><linkText>Create an Outlook Protection Rule</linkText><linkUri>http://technet.microsoft.com/library/dd638196(v=exchg.150).aspx</linkUri></externalLink> in the Exchange library.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src51" class="srcSentence">
                      <legacyBold>Transport rules</legacyBold> that an administrator configures to automatically apply RMS templates to email messages based on properties such as sender, recipient, message subject, and content.</caps:sentence>
                    <caps:sentence id="src52" class="srcSentence"> These are similar in concept to protection rules but do not let users remove the protection, can be applied to Outlook Web Access and emails sent by mobile devices, and do not encrypt email messages before they are sent from the client.</caps:sentence>
                    <caps:sentence id="src53" class="srcSentence"> For more information, see <externalLink><linkText>Create a Transport Protection Rule</linkText><linkUri>http://technet.microsoft.com/library/dd302432.aspx</linkUri></externalLink> in the Exchange library.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src54" class="srcSentence">
                      <legacyBold>Data loss prevention (DLP) policies</legacyBold> that contain sets of conditions to filter email messages, and take actions to help prevent data loss for confidential or sensitive content (for example, personal information or credit card information).</caps:sentence>
                    <caps:sentence id="src55" class="srcSentence"> Policy Tips can be used when sensitive data is detected, to alert users that they might need to apply information protection, based on the information in the email message.</caps:sentence>
                    <caps:sentence id="src56" class="srcSentence"> For more information, see <externalLink><linkText>Data Loss Prevention</linkText><linkUri>http://technet.microsoft.com/library/jj150527(v=exchg.150).aspx</linkUri></externalLink> in the Exchange library.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src57" class="srcSentence">
                      <legacyBold>Office 365 Message Encryption</legacyBold> that uses transport rules to send encrypted emails to people outside your company, and the email is read in a browser with an interface similar to the Outlook Web App.</caps:sentence>
                    <caps:sentence id="src58" class="srcSentence"> You can customize the disclaimer text and header text in your company’s encrypted emails, and even add your company logo.</caps:sentence>
                    <caps:sentence id="src59" class="srcSentence"> For more information, see <externalLink><linkText>Office 365 Message Encryption</linkText><linkUri>http://office.microsoft.com/o365-message-encryption-FX104179182.aspx</linkUri></externalLink> from the Office website.</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence id="src60" class="srcSentence">If you use Exchange Server, you can use the information protection features with <token>aad_rightsmanagement_1</token> by deploying the RMS connector, which acts as a relay between your on-premises servers and the RMS cloud service.</caps:sentence>
                <caps:sentence id="src61" class="srcSentence"> For more information, see <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066">Deploying the Azure Rights Management Connector</link>.</caps:sentence>
              </para>
            </content>
          </section>
          <section address="BKMK_SharePointIntro">
            <title>
              <caps:sentence id="src62" class="srcSentence">SharePoint Online and SharePoint Server</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src63" class="srcSentence">When you use SharePoint Online or SharePoint Server, you can use information rights management (IRM) integration, which lets administrators protect lists or libraries so that when a user checks-out a document, the file is protected so that only authorized people can view and use the file according to the information protection policies that you specify.</caps:sentence>
                <caps:sentence id="src64" class="srcSentence"> For example, the file might be read-only, disable the copying of text, prevent saving a local copy, and prevent printing the file.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src65" class="srcSentence">For lists and libraries,  information protection is always applied by an administrator, never an end user.</caps:sentence>
                <caps:sentence id="src66" class="srcSentence"> And it is applied at the list or library level for all documents in that container, rather than on individual files.</caps:sentence>
                <caps:sentence id="src67" class="srcSentence">  If you use SharePoint Online, users can also apply IRM to their OneDrive for Business library.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src68" class="srcSentence">The IRM service must first be enabled for SharePoint.</caps:sentence>
                <caps:sentence id="src69" class="srcSentence"> Then, you specify Information Rights Management for a library.</caps:sentence>
                <caps:sentence id="src70" class="srcSentence"> In the case of SharePoint Online and OneDrive for Business, users can also specify Information Rights Management for their OneDrive for Business library.</caps:sentence>
                <caps:sentence id="src71" class="srcSentence"> SharePoint does not use rights policy templates, although there are SharePoint configuration settings that you can select that closely match the settings that you can specify in templates.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src72" class="srcSentence">If you use SharePoint Server, you can use the information protection features with <token>aad_rightsmanagement_1</token> by deploying the RMS connector, which acts as a relay between your on-premises servers and the RMS cloud service.</caps:sentence>
                <caps:sentence id="src73" class="srcSentence"> For more information, see <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066">Deploying the Azure Rights Management Connector</link>.</caps:sentence>
              </para>
              <alert class="note">
                <para>
                  <caps:sentence id="src74" class="srcSentence">Currently, there are some limitations when you use IRM with SharePoint:</caps:sentence>
                </para>
                <list class="bullet">
                  <listItem>
                    <para>
                      <caps:sentence id="src75" class="srcSentence">You cannot use the default or custom templates that you manage in the Azure classic portal.</caps:sentence>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence id="src76" class="srcSentence">Files that have a .PPDF file name extension for protected PDF files are not supported.</caps:sentence>
                      <caps:sentence id="src77" class="srcSentence"> Files that have .PDF file name extension and that have been natively protected by RMS are supported when you use a PDF reader that natively supports RMS.</caps:sentence>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence id="src78" class="srcSentence"> Because Office on mobile devices does not yet support RMS, these devices must use a browser to view files that have been protected with RMS, and the files are read-only.</caps:sentence>
                    </para>
                  </listItem>
                </list>
              </alert>
              <para>
                <caps:sentence id="src79" class="srcSentence">Azure RMS applies usage restrictions and data encryption for documents when they are downloaded from SharePoint, and not when the document is first created in SharePoint or uploaded to the library.</caps:sentence>
                <caps:sentence id="src80" class="srcSentence"> For information about how documents are protected before they are downloaded, see <externalLink><linkText>Data Encryption in OneDrive for Business and SharePoint Online</linkText><linkUri>https://technet.microsoft.com/library/dn905447.aspx</linkUri></externalLink> from the SharePoint documentation.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src81" class="srcSentence">For more information about using Azure RMS with SharePoint, see the following  post from the Office blog: <externalLink><linkText>What’s New with Information Rights Management in SharePoint and SharePoint Online</linkText><linkUri>http://blogs.office.com/2012/11/09/whats-new-with-information-rights-management-in-sharepoint-and-sharepoint-online/</linkUri></externalLink></caps:sentence>
              </para>
            </content>
          </section>
        </sections>
      </section>
      <section address="BKMK_FCIIntro">
        <title>
          <caps:sentence id="src82" class="srcSentence">File servers that run Windows Server and use File Classification Infrastructure (FCI)</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src83" class="srcSentence">When you configure Windows Server to use File Classification Infrastructure, this File Server Resource Manager feature can scan local files and determine whether they contain sensitive data.</caps:sentence>
            <caps:sentence id="src84" class="srcSentence"> For files that meet this criteria, they are tagged with classification properties that an administrator defines.</caps:sentence>
            <caps:sentence id="src85" class="srcSentence"> The File Classification Infrastructure can then take automatic action, according to the classification.</caps:sentence>
            <caps:sentence id="src86" class="srcSentence"> One of these actions include applying information protection by using <token>aad_rightsmanagement_1</token> and the deployment of the Rights Management connector (also known as the RMS connector).</caps:sentence>
            <caps:sentence id="src87" class="srcSentence"> Office files are then automatically protected by Azure RMS.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src88" class="srcSentence">To protect all file types, you would not use the RMS connector, but instead, run a Windows PowerShell script, using cmdlets from the <externalLink><linkText>RMS Protection tool</linkText><linkUri>https://www.microsoft.com/en-us/download/details.aspx?id=47256</linkUri></externalLink>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src89" class="srcSentence">The classification policies are fully configurable and highly extensible so that you can prevent potential data leakage from unauthorized and authorized users.</caps:sentence>
            <caps:sentence id="src90" class="srcSentence"> It can even help to reduce the risk of data leakage by network administrators because you can configure policies that don’t require these administrators to have access to the files.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src91" class="srcSentence">For instructions to deploy and configure the RMS connector for Office files, see <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066">Deploying the Azure Rights Management Connector</link>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src92" class="srcSentence">For instructions to use the Windows PowerShell script for all file types, see <link xlink:href="9aa693db-9727-4284-9f64-867681e114c9">RMS Protection with Windows Server File Classification Infrastructure (FCI)</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_APIAppsIntro">
        <title>
          <caps:sentence id="src93" class="srcSentence">Other applications that support the RMS APIs</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src94" class="srcSentence">By using the RMS SDK, your internal developers can write line-of-business applications to natively support <token>aad_rightsmanagement_1</token>.</caps:sentence>
            <caps:sentence id="src95" class="srcSentence"> How information protection is integrated with these applications depends on how they are written.</caps:sentence>
            <caps:sentence id="src96" class="srcSentence"> For example, the integration might be automatically applied with minimal user interaction required, or for a more customized experience, users might be prompted to configure settings to apply information protection to files.</caps:sentence>
            <caps:sentence id="src97" class="srcSentence"> For more information about the SDK, see the <externalLink><linkText>Microsoft Rights Management SDK</linkText><linkUri>http://msdn.microsoft.com/library/hh552972(v=vs.85).aspx</linkUri></externalLink>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src98" class="srcSentence">Similarly, many software vendors provide applications to provide  information protection solutions, also known as enterprise rights management (ERM) products.</caps:sentence>
            <caps:sentence id="src99" class="srcSentence"> A popular example is a PDF reader that supports <token>aad_rightsmanagement_2</token> for specific platforms.</caps:sentence>
            <caps:sentence id="src100" class="srcSentence"> You can use the table in the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_ClientCapabilities">Client device capabilities</link> section of the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link> topic to identify applications that support RMS (RMS-enlightened applications), and then use a web search to purchase or download the application.</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence id="src101" class="srcSentence">For newly released applications, check the RMS community channels, listed in <link xlink:href="7cc73d92-27d6-49ff-a8ab-2fae73519b4b">Information and Support for Azure Rights Management</link>.</caps:sentence>
            </para>
          </alert>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="5214667c-ec69-42ca-8bbf-8cb22da8c62e">Getting started with Azure Rights Management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSSource>
</caps:SxS>