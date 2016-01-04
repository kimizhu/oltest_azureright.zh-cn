---
description: na
keywords: na
pagetitle: Helping Users to Protect Files by Using Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 58f9a6ff-4121-4c8c-9865-1bb290604ad2
---
# 帮助用户使用 Azure 权限管理保护文件
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="zh-CN">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="3b8ce9f16f924193b9387d5e0a378b4b" id="tgt1" class="tgtSentence">在你为组织部署和配置 Azure Rights Management (Azure RMS) 之后，请为用户、管理员和你的技术支持提供以下帮助和指导：</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <legacyBold>
                <caps:sentence sentenceid="a06d94b37c91b7239122f44974c9dd99" id="tgt2" class="tgtSentence">最终用户信息：</caps:sentence>
              </legacyBold>
            </para>
            <para>
              <caps:sentence sentenceid="d2e97eb77bd4d1e4aaaf54de1d743405" id="tgt3" class="tgtSentence">让用户知道如何以及何时保护包含敏感信息的文档和电子邮件。</caps:sentence>
              <caps:sentence sentenceid="6eb26a52d2b3aa54bd98706f4174438a" id="tgt4" class="tgtSentence"> 只要有可能，都应该提供其现有工作流的这些信息，使他们可以将附加的步骤合并到熟知的过程中，而不是引入全新的过程。</caps:sentence>
              <caps:sentence sentenceid="f3cbc880c4a823174188bb89e944da11" id="tgt5" class="tgtSentence"> 请务必让他们知道你的业务的相关优势（和风险），并提供有关何时应该保护文件和电子邮件的指导。</caps:sentence>
              <caps:sentence sentenceid="be841b2b3e55c0dd14ea15df0c70e3b6" id="tgt6" class="tgtSentence"> 如果你配置了<externalLink><linkText>自定义模板</linkText><linkUri>http://technet.microsoft.com/library/dn642472.aspx</linkUri></externalLink>，请提供有关在模板名称和描述不足以帮助用户选择正确模板时应该选择哪个模板的说明。</caps:sentence>
            </para>
            <alert class="tip">
              <para>
                <caps:sentence sentenceid="e84dce0ec9e18b134850622db2a67ff0" id="tgt7" class="tgtSentence">最终用户示例视频 </caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="9af7c117d9de9a06fba7a5f1ea5fcc2d" id="tgt8" class="tgtSentence"> <externalLink><linkText>Azure RMS 用户体验</linkText><linkUri>http://channel9.msdn.com/Series/Information-Protection/Azure-RMS-user-experience</linkUri></externalLink></caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="9af7c117d9de9a06fba7a5f1ea5fcc2d" id="tgt9" class="tgtSentence"> <externalLink><linkText>Azure RMS 文档跟踪和撤销</linkText><linkUri>http://channel9.msdn.com/Series/Information-Protection/Azure-RMS-Document-Tracking-and-Revocation</linkUri></externalLink></caps:sentence>
                  </para>
                </listItem>
              </list>
            </alert>
          </listItem>
          <listItem>
            <para>
              <legacyBold>
                <caps:sentence sentenceid="5869acc600a1907c4b4c5856d3942043" id="tgt10" class="tgtSentence">管理员信息：</caps:sentence>
              </legacyBold>
            </para>
            <para>
              <caps:sentence sentenceid="f9a054bb68f20961bd3238d346c7180d" id="tgt11" class="tgtSentence">有些应用程序使用管理员配置的策略和设置来自动应用信息保护。</caps:sentence>
              <caps:sentence sentenceid="281408d3668eef9e9fd5cc52d2b7fe9e" id="tgt12" class="tgtSentence"> 你可能需要为管理这些应用程序和服务的其他管理员提供这些应用程序的说明。</caps:sentence>
              <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt13" class="tgtSentence"> 有关详细信息，请参阅 <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9">How Applications Support Azure Rights Management</link>和<link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36">Configuring Applications for Azure Rights Management</link>。</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <legacyBold>
                <caps:sentence sentenceid="2b1d96a6ff3e1dd7110d855019f7eb7b" id="tgt14" class="tgtSentence">技术支持信息：</caps:sentence>
              </legacyBold>
            </para>
            <para>
              <caps:sentence sentenceid="b5afa67e52867b2a4d0dcf584e3469cb" id="tgt15" class="tgtSentence">为技术支持人员提供的最有用工具之一是 <externalLink><linkText>RMS 分析器</linkText><linkUri>https://www.microsoft.com/en-us/download/details.aspx?id=46437</linkUri></externalLink>。</caps:sentence>
              <caps:sentence sentenceid="50136391400d8d0d855ad7a11f1ab293" id="tgt16" class="tgtSentence">   技术支持操作员可以配合 Azure RMS 管理员选项运行该工具，并且可以要求用户配合 Azure RMS 用户选项运行该工具。</caps:sentence>
              <caps:sentence sentenceid="dab43185e49fccb9d271eea08a727114" id="tgt17" class="tgtSentence"> 此工具不仅可以帮助识别问题，而且还能修复找到的问题，并且不能修复，则会记录跟踪日志。</caps:sentence>
            </para>
            <para>
              <caps:sentence sentenceid="ce2269b58dc1921542e1fec9b29951c7" id="tgt18" class="tgtSentence">如果有人合法请求对受保护文档的完全访问权限（例如，某位离职后，法律部门或经理发出此类请求），请确保技术支持人员使用 Azure RMS <externalLink><linkText>超级用户功能</linkText><linkUri>https://technet.microsoft.com/en-us/library/mt147272.aspx</linkUri></externalLink>并遵循相应的流程来处理此请求。</caps:sentence>
            </para>
            <para>
              <caps:sentence sentenceid="92d83e6c141d12a392f0a78226dab83e" id="tgt19" class="tgtSentence">此外，下面是用户可能会报告的一些典型问题： </caps:sentence>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <legacyBold>
                    <caps:sentence sentenceid="615d149c6aded81e3b9066ea7577cfb8" id="tgt20" class="tgtSentence">登录帮助：</caps:sentence>
                  </legacyBold>
                </para>
                <para>
                  <caps:sentence sentenceid="b428ad5bc4f4f93bda49a55b096bb0b8" id="tgt21" class="tgtSentence">当 Azure RMS 需要对用户进行身份验证且无法使用缓存的凭据时，可能提示用户提供凭据。</caps:sentence>
                  <caps:sentence sentenceid="cf422d290d786d5d0f49ac76ed30f53e" id="tgt22" class="tgtSentence"> 该凭据是用户的工作或学校帐户和密码，与你的 Office 365 租户或 Azure Active Directory 租户相关联。</caps:sentence>
                  <caps:sentence sentenceid="39fa82219719457304bd431c7dfcc080" id="tgt23" class="tgtSentence"> 它不是 Microsoft 帐户（以前的 Microsoft Live ID）或用户的个人电子邮件帐户，因为 Azure RMS 当前不支持这些帐号。</caps:sentence>
                  <caps:sentence sentenceid="119024c26490ad07111c5303def15b6b" id="tgt24" class="tgtSentence"> 为用户和你的技术支持提供说明，阐明在 Azure RMS 上使用这些应用程序的情况下，当提示用户提供凭据时，应该使用何种帐户。</caps:sentence>
                </para>
              </listItem>
              <listItem>
                <para>
                  <legacyBold>
                    <caps:sentence sentenceid="3169e7ef48fed3285ec65f532fb7d16b" id="tgt25" class="tgtSentence">与保护或使用内容相关的问题：</caps:sentence>
                  </legacyBold>
                </para>
                <para>
                  <caps:sentence sentenceid="d0fe93d0078e43610e43f505bfbb29fd" id="tgt26" class="tgtSentence">确保用户获得了有关他们所用应用程序的相应说明，并使用 Azure RMS 支持的应用程序和设备。</caps:sentence>
                  <caps:sentence sentenceid="c30979b59228bce30cdca855ee764f08" id="tgt27" class="tgtSentence"> 有关支持的应用程序和设备的详细信息，请参阅<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="9aaebedc1b9d903a7b8f487616586802" id="tgt28" class="tgtSentence">如果用户在尝试保护或使用内容时看到错误，请要求他们以 Azure RMS 用户的身份运行 <externalLink><linkText>RMS 分析器</linkText><linkUri>https://www.microsoft.com/en-us/download/details.aspx?id=46437</linkUri></externalLink>。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="898a00bbab39ae20639f5603c9fe944a" id="tgt29" class="tgtSentence">如果用户报告他们可以打开受保护的内容，但没有所需的权限，请要求他们以 Azure RMS 用户的身份运行 <externalLink><linkText>RMS 分析器</linkText><linkUri>https://www.microsoft.com/en-us/download/details.aspx?id=46437</linkUri></externalLink>，并下载和查看模板。</caps:sentence>
                  <caps:sentence sentenceid="d41212e9387d04e9ab834704cde4c0d6" id="tgt30" class="tgtSentence"> 这将会确认他们已成功下载模板，以及模板提供的权限。</caps:sentence>
                  <caps:sentence sentenceid="47a7a57db2c2db4f4818ddebff2356de" id="tgt31" class="tgtSentence"> 问题的原因可能是，该用户不在针对模板配置的正确组中，或者需要为该用户重新配置模板。</caps:sentence>
                </para>
              </listItem>
            </list>
          </listItem>
        </list>
        <para>
          <caps:sentence sentenceid="8cbaa97281cd5b4b5edf9f891e83c080" id="tgt32" class="tgtSentence">请参阅以下关于应用程序特定信息的部分，帮助用户保护敏感的文档和电子邮件。</caps:sentence>
        </para>
      </introduction>
      <section>
        <title>
          <caps:sentence sentenceid="0885c3c7ae8d4645d78659808ff6cfd3" id="tgt33" class="tgtSentence">使用权限管理共享应用程序提供的信息保护</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="e556ac2273229a7e0b2f9263f46ab5e1" id="tgt34" class="tgtSentence">如果用户使用 Office 2010，则权限管理 (RMS) 共享应用程序是他们进行内容保护和使用受保护内容所必需的。另外，我们还建议将其用于支持 Azure RMS 的所有计算机和移动设备。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="2b4f22ce96c4820f06dc290b0d757c6d" id="tgt35" class="tgtSentence">除了使用户更轻松地保护重要文档以外，RMS 共享应用程序还允许用户跟踪他们保护的文档，并根据需要撤消对文档的访问权限。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="804108e5363b3e81e4a869da6fbb30ad" id="tgt36" class="tgtSentence">有关如何将此应用程序用于 Windows 计算机的说明，请参阅 <externalLink><linkText>Rights Management 共享应用程序用户指南</linkText><linkUri>http://technet.microsoft.com/library/dn339006.aspx</linkUri></externalLink>。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="c153ba00d98aded0cdda66ce93e8c9a9" id="tgt37" class="tgtSentence">对于移动设备，请参阅<externalLink><linkText>适用于移动平台的 Microsoft Rights Management 共享应用程序的常见问题</linkText><linkUri>http://technet.microsoft.com/dn451248</linkUri></externalLink>。</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence sentenceid="7fc01b361b5631a192db69caffdcd7e8" id="tgt38" class="tgtSentence">有关带屏幕截图的高级示例方案，请参阅<link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df#BKMK_Example_SharingApp">Users safely share attachments with mobile users</link>主题中的<link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link>部分。</caps:sentence>
            </para>
          </alert>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence sentenceid="82065ecfa54f8aaa7819fc1c6529965d" id="tgt39" class="tgtSentence">在 Office 365、Office 2016 或 Office 2013 中使用信息保护</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="93128e9edc8965ab3dac48e8ed78dcb5" id="tgt40" class="tgtSentence">如果你使用 Azure RMS，但尚未安装权限管理共享应用程序，则用户将不会在功能区上看到<ui>“共享保护”</ui>按钮，也不会在文件资源管理器中看到帮助他们更加轻松地保护文件的<ui>“保护现有”</ui>选项。</caps:sentence>
            <caps:sentence sentenceid="d4343c1afd41c2e27a52f05c2877f42c" id="tgt41" class="tgtSentence"> 对于这些用户，他们必须遵循类似以下的说明。</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence sentenceid="af69bf89391fd6650ce07d46f2ea49e6" id="tgt42" class="tgtSentence">若要查找应用程序特定帮助，以及有关在这些应用程序中使用信息保护的说明，请搜索 <userInput>IRM</userInput> 和应用程序名称及版本。</caps:sentence>
            </para>
          </alert>
          <procedure>
            <title>
              <caps:sentence sentenceid="fb03aa6b56d5f6bb9dadb1db79b09b6d" id="tgt43" class="tgtSentence">在 Word 2013 中保护文档</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="2a0da9cfb1a9b4b6041fa42a95641cc5" id="tgt44" class="tgtSentence">在 Microsoft Word 中创建一个新文档。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="1d78457e80b3c77f152c8c399312bb34" id="tgt45" class="tgtSentence">在“文件”菜单中，依次单击“信息”、“保护文档”、“限制访问”，然后选择一个模板以快速应用相应的使用权限，或者选择“限制访问”并自行选择使用权限<ui></ui><ui></ui><ui></ui><ui></ui><ui></ui>。</caps:sentence>
                  </para>
                  <alert class="note">
                    <para>
                      <caps:sentence sentenceid="efff46041521421081e3f71cb45746b5" id="tgt46" class="tgtSentence">如果这是你第一次使用 Rights Management，你需要联系 <token>aad_rightsmanagement_1</token> 服务，它将提示你提供凭据，以便配置 Office IRM 客户端。</caps:sentence>
                    </para>
                  </alert>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="d979f8b4a960b7919b890c579786157c" id="tgt47" class="tgtSentence">保存文档。</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence sentenceid="f67ae9121005786275e1e182e792fdef" id="tgt48" class="tgtSentence">当其他人打开文档时，首先会对他们进行身份验证。</caps:sentence>
                  <caps:sentence sentenceid="5a339fc47ff1a8618648a4452a5decc4" id="tgt49" class="tgtSentence"> 如果他们未被授权打开文档，则文档不会打开。</caps:sentence>
                  <caps:sentence sentenceid="99ddc70880c02a7575fb4947cdeb7504" id="tgt50" class="tgtSentence"> 如果他们已被授权打开文档，则文档将会打开，并提供为该用户指定的受限使用权限。</caps:sentence>
                  <caps:sentence sentenceid="9f8876cf8f09b9b2cc73acc5a584beaf" id="tgt51" class="tgtSentence"> 例如，“仅查看”使用权限不允许用户编辑或保存文档，即便先将文档复制到其他位置也是如此。</caps:sentence>
                  <caps:sentence sentenceid="c0b08b906fe68ce1aef1243a80a2cd88" id="tgt52" class="tgtSentence"> 这些使用权限以限制横幅方式显示在文档顶部。</caps:sentence>
                  <caps:sentence sentenceid="d93ed6606cca06320ecaef42ead8df29" id="tgt53" class="tgtSentence"> 该横幅可能显示适用于文档的权限，或者提供显示权限的链接。</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
          <procedure>
            <title>
              <caps:sentence sentenceid="8c4550df648e73c54c38183fc622886e" id="tgt54" class="tgtSentence">使用 Outlook 2013 和 Exchange Online 保护电子邮件</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="0397fd8c1fca2554fcef6b2eb5d1938a" id="tgt55" class="tgtSentence">在 Outlook 中，创建一封发送至组织内部收件人的新电子邮件。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="1d78457e80b3c77f152c8c399312bb34" id="tgt56" class="tgtSentence">在“选项”选项卡中，单击“权限”，然后选择某个选项<ui></ui><ui></ui>。</caps:sentence>
                    <caps:sentence sentenceid="407e8379b5443b7c0092c35c8bab7f29" id="tgt57" class="tgtSentence"> 例如：<ui>“不要转发”</ui>、<ui>“&lt;公司名称&gt; - 机密”</ui>或<ui>“&lt;公司名称&gt; - 机密，仅供查阅”</ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="0198c5fb120b81f0e08364960ff3ae80" id="tgt58" class="tgtSentence">发送电子邮件。</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence sentenceid="458dc7dfc99c7dbee47cd0d0a275d86c" id="tgt59" class="tgtSentence">与查看受保护文档相似，当收件人接收电子邮件时，首先会对他们进行身份验证。</caps:sentence>
                  <caps:sentence sentenceid="e75a777b8c518ede23dbeb3bbdfb803b" id="tgt60" class="tgtSentence"> 如果他们已被授权查看电子邮件，则电子邮件将会打开，并提供为该用户指定的受限使用权限。</caps:sentence>
                  <caps:sentence sentenceid="46bf1ba3791a5082f2b5eac627207177" id="tgt61" class="tgtSentence"> 例如，如果你选择了“不要转发”，则功能区上的“转发”按钮不可用<ui></ui>。</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
          <procedure>
            <title>
              <caps:sentence sentenceid="95338ec064649cddcdbaefce88efe33f" id="tgt62" class="tgtSentence">使用 Outlook Web App 保护电子邮件</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="5bf1830e7b01c6315a24f664a4a71b79" id="tgt63" class="tgtSentence">在 Outlook Web App 中，创建一封发送至组织内部收件人的新电子邮件。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="cfa39a0a21515994aeaf71498c07869a" id="tgt64" class="tgtSentence">单击“...”，再单击“设置权限”，然后选择某个选项<ui></ui><ui></ui>。</caps:sentence>
                    <caps:sentence sentenceid="407e8379b5443b7c0092c35c8bab7f29" id="tgt65" class="tgtSentence"> 例如：<ui>“不要转发”</ui>、<ui>“不要全部答复”</ui>、<ui>“&lt;公司名称&gt; - 机密”</ui>或<ui>“&lt;公司名称&gt; - 机密，仅供查阅”</ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="0198c5fb120b81f0e08364960ff3ae80" id="tgt66" class="tgtSentence">发送电子邮件。</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence sentenceid="458dc7dfc99c7dbee47cd0d0a275d86c" id="tgt67" class="tgtSentence">与查看受保护文档相似，当收件人接收电子邮件时，首先会对他们进行身份验证。</caps:sentence>
                  <caps:sentence sentenceid="e75a777b8c518ede23dbeb3bbdfb803b" id="tgt68" class="tgtSentence"> 如果他们已被授权查看电子邮件，则电子邮件将会打开，并提供为该用户指定的受限使用权限。</caps:sentence>
                  <caps:sentence sentenceid="46bf1ba3791a5082f2b5eac627207177" id="tgt69" class="tgtSentence"> 例如，如果你选择了“不要全部答复”，则电子邮件窗口中的“全部答复”选项不可用<ui></ui><ui></ui>。</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
        </content>
        <sections></sections>
      </section>
      <relatedTopics>
        <link xlink:href="18564e4a-9364-4ed2-8f17-89d24fc0d878">Using Azure Rights Management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSTarget>
  <caps:SxSSource locale="en-US">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence id="src1" class="srcSentence">After you have deployed and configured Azure Rights Management (Azure RMS) for your organization, provide help and guidance for users, administrators, and your help desk:</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <legacyBold>
                <caps:sentence id="src2" class="srcSentence">End-user information:</caps:sentence>
              </legacyBold>
            </para>
            <para>
              <caps:sentence id="src3" class="srcSentence">Let users know how and when to protect documents and emails that contain sensitive information.</caps:sentence>
              <caps:sentence id="src4" class="srcSentence"> Whenever possible, provide this information for  their existing work flows so that they can incorporate the additional steps to an already-familiar process rather than introducing completely new processes .</caps:sentence>
              <caps:sentence id="src5" class="srcSentence"> Be sure to let them know the benefits (and the risks) that are specific to your business, as well as providing guidance for when they should protect files and emails.</caps:sentence>
              <caps:sentence id="src6" class="srcSentence"> If you have configured <externalLink><linkText>custom templates</linkText><linkUri>http://technet.microsoft.com/library/dn642472.aspx</linkUri></externalLink>, provide instructions about which one to select if the template name and description is not sufficient for them to choose the correct one.</caps:sentence>
            </para>
            <alert class="tip">
              <para>
                <caps:sentence id="src7" class="srcSentence">Example videos for end users: </caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src8" class="srcSentence"> <externalLink><linkText>Azure RMS user experience</linkText><linkUri>http://channel9.msdn.com/Series/Information-Protection/Azure-RMS-user-experience</linkUri></externalLink></caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src9" class="srcSentence"> <externalLink><linkText>Azure RMS Document Tracking and Revocation</linkText><linkUri>http://channel9.msdn.com/Series/Information-Protection/Azure-RMS-Document-Tracking-and-Revocation</linkUri></externalLink></caps:sentence>
                  </para>
                </listItem>
              </list>
            </alert>
          </listItem>
          <listItem>
            <para>
              <legacyBold>
                <caps:sentence id="src10" class="srcSentence">Administrator information:</caps:sentence>
              </legacyBold>
            </para>
            <para>
              <caps:sentence id="src11" class="srcSentence">Some applications automatically apply information protection, by using policies and settings that administrators configure.</caps:sentence>
              <caps:sentence id="src12" class="srcSentence"> For these applications, you might need to provide instructions for other administrators who manage these applications and services.</caps:sentence>
              <caps:sentence id="src13" class="srcSentence"> For more information, see <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9">How Applications Support Azure Rights Management</link> and <link xlink:href="ea09cbc5-b98b-444e-8b60-5bc3cb199c36">Configuring Applications for Azure Rights Management</link>.</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <legacyBold>
                <caps:sentence id="src14" class="srcSentence">Help desk information:</caps:sentence>
              </legacyBold>
            </para>
            <para>
              <caps:sentence id="src15" class="srcSentence">One of the most useful tools for the help desk is the <externalLink><linkText>RMS Analyzer</linkText><linkUri>https://www.microsoft.com/en-us/download/details.aspx?id=46437</linkUri></externalLink>.</caps:sentence>
              <caps:sentence id="src16" class="srcSentence">   Help desk operators can run it with the Azure RMS administrator option, and they can ask users to run it with the Azure RMS user option.</caps:sentence>
              <caps:sentence id="src17" class="srcSentence"> This tool can not only help identify problems, but also fix problems that it finds, and if still not fixed, record trace logs.</caps:sentence>
            </para>
            <para>
              <caps:sentence id="src18" class="srcSentence">If there are legitimate requests to have full rights access to protected documents, for example a request by the legal department or a manager after an employee has left the organization, make sure the help desk has processes to request this by using the Azure RMS <externalLink><linkText>super user feature</linkText><linkUri>https://technet.microsoft.com/en-us/library/mt147272.aspx</linkUri></externalLink>.</caps:sentence>
            </para>
            <para>
              <caps:sentence id="src19" class="srcSentence">In  addition, these are some of the typical problems that users might report: </caps:sentence>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <legacyBold>
                    <caps:sentence id="src20" class="srcSentence">Sign in help:</caps:sentence>
                  </legacyBold>
                </para>
                <para>
                  <caps:sentence id="src21" class="srcSentence">Users might be prompted for credentials when Azure RMS needs to authenticate a user and cannot use cached credentials.</caps:sentence>
                  <caps:sentence id="src22" class="srcSentence"> This will be the user’s work or school account and password that is associated with your Office 365 tenant or Azure Active Directory tenant.</caps:sentence>
                  <caps:sentence id="src23" class="srcSentence"> It will not be a Microsoft account (formerly Microsoft Live ID) or their personal email account, because these are not currently supported by Azure RMS.</caps:sentence>
                  <caps:sentence id="src24" class="srcSentence"> Provide users and your help desk with instructions about which account to use when users are prompted for credentials when they use these applications with Azure RMS.</caps:sentence>
                </para>
              </listItem>
              <listItem>
                <para>
                  <legacyBold>
                    <caps:sentence id="src25" class="srcSentence">Problems protecting or consuming content:</caps:sentence>
                  </legacyBold>
                </para>
                <para>
                  <caps:sentence id="src26" class="srcSentence">Make sure that users have the appropriate instructions for the applications that they use, and are using applications and devices that are supported by Azure RMS.</caps:sentence>
                  <caps:sentence id="src27" class="srcSentence"> For more information about supported applications and devices, see <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src28" class="srcSentence">If users see an error when trying to protect or consume content, ask them to run the <externalLink><linkText>RMS Analyzer</linkText><linkUri>https://www.microsoft.com/en-us/download/details.aspx?id=46437</linkUri></externalLink> as an Azure RMS user.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src29" class="srcSentence">If users report that they can open protected content but don't have the rights that they need, ask them to run the <externalLink><linkText>RMS Analyzer</linkText><linkUri>https://www.microsoft.com/en-us/download/details.aspx?id=46437</linkUri></externalLink> as an Azure RMS user and download and view the templates.</caps:sentence>
                  <caps:sentence id="src30" class="srcSentence"> This will confirm that they have successfully downloaded the templates and what rights the templates provide.</caps:sentence>
                  <caps:sentence id="src31" class="srcSentence"> The problem might be that the user is not in the correct group that's configured for the template, or that the template needs reconfiguring for the user.</caps:sentence>
                </para>
              </listItem>
            </list>
          </listItem>
        </list>
        <para>
          <caps:sentence id="src32" class="srcSentence">Use the following sections for application-specific information to help users protect sensitive documents and emails.</caps:sentence>
        </para>
      </introduction>
      <section>
        <title>
          <caps:sentence id="src33" class="srcSentence">Using information protection with the Rights Management sharing application</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src34" class="srcSentence">The Rights Management (RMS) sharing application is required for users to protect and consume protected content if they use Office 2010, but also recommended for all computers and mobile devices that support Azure RMS.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src35" class="srcSentence">In addition to making it easier for users to protect important documents, the RMS sharing application lets users track the documents that they have protected, and if necessary, revoke access to them.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src36" class="srcSentence">For instructions to use this application for Windows computers, see the <externalLink><linkText>Rights Management sharing application user guide</linkText><linkUri>http://technet.microsoft.com/library/dn339006.aspx</linkUri></externalLink>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src37" class="srcSentence">For mobile devices, see the <externalLink><linkText>FAQ for Microsoft Rights Management Sharing Application for Mobile Platforms</linkText><linkUri>http://technet.microsoft.com/dn451248</linkUri></externalLink>.</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence id="src38" class="srcSentence">For a high-level example scenario with screenshots, see the <link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df#BKMK_Example_SharingApp">Users safely share attachments with mobile users</link> section in the <link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link> topic.</caps:sentence>
            </para>
          </alert>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence id="src39" class="srcSentence">Using information protection with Office 365, Office 2016, or Office 2013</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src40" class="srcSentence">If you are using Azure RMS and have not installed the Rights Management sharing application, users will not see the <ui>Share Protected</ui> button on the ribbon or <ui>Protect in-place</ui> from File Explorer that makes it easier for them to protect files.</caps:sentence>
            <caps:sentence id="src41" class="srcSentence"> For these users, they must follow instructions similar to these.</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence id="src42" class="srcSentence">To find application-specific help and instructions for using information protection with these applications, search for <userInput>IRM</userInput> and the application name and version.</caps:sentence>
            </para>
          </alert>
          <procedure>
            <title>
              <caps:sentence id="src43" class="srcSentence">To protect a document in Word 2013</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src44" class="srcSentence">Within Microsoft Word, create a new document.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src45" class="srcSentence">From the <ui>File</ui> menu, click <ui>Info</ui>, click <ui>Protect Document</ui>, click <ui>Restrict Access</ui>, and then choose a template to quickly apply the appropriate usage rights, or select <ui>Restrict Access</ui> and select the usage rights yourself.</caps:sentence>
                  </para>
                  <alert class="note">
                    <para>
                      <caps:sentence id="src46" class="srcSentence">If this is the first time that you have used Rights Management, you will contact the <token>aad_rightsmanagement_1</token> service and will be prompted for credentials to configure the Office IRM client.</caps:sentence>
                    </para>
                  </alert>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src47" class="srcSentence">Save the document.</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence id="src48" class="srcSentence">When others open the document, they are first authenticated.</caps:sentence>
                  <caps:sentence id="src49" class="srcSentence"> If they are not authorized to open the document, the document does not open.</caps:sentence>
                  <caps:sentence id="src50" class="srcSentence"> If they are authorized to open the document, it opens with the restricted usage rights that were specified for that user.</caps:sentence>
                  <caps:sentence id="src51" class="srcSentence"> For example, a usage right of View-only does not allow the user to edit or save the document, even if it is first copied to another location.</caps:sentence>
                  <caps:sentence id="src52" class="srcSentence"> The usage rights are displayed at the top of the document by using a restriction banner.</caps:sentence>
                  <caps:sentence id="src53" class="srcSentence"> The banner might display the permissions that are applied to the document, or it might provide a link to display them.</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
          <procedure>
            <title>
              <caps:sentence id="src54" class="srcSentence">To protect an email message using Outlook 2013 and Exchange Online</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src55" class="srcSentence">Within Outlook, create a new mail message addressed to a recipient within your organization.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src56" class="srcSentence">From the <ui>OPTIONS</ui> tab,  click <ui>Permission</ui>, and then select an option.</caps:sentence>
                    <caps:sentence id="src57" class="srcSentence"> For example: <ui>Do Not Forward</ui>, <ui>&lt;Company Name&gt; - Confidential</ui> or <ui>&lt;Company Name&gt; - Confidential View Only</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src58" class="srcSentence">Send the message.</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence id="src59" class="srcSentence">Similarly to viewing a protected document, when the recipients receive the email message, they are first authenticated.</caps:sentence>
                  <caps:sentence id="src60" class="srcSentence"> If they are authorized to see the email message, it opens with the restricted usage rights that were specified for that user.</caps:sentence>
                  <caps:sentence id="src61" class="srcSentence"> For example, if you selected <ui>Do Not Forward</ui>, the Forward button on the ribbon is not available.</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
          <procedure>
            <title>
              <caps:sentence id="src62" class="srcSentence">To protect an email message using the Outlook Web App</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src63" class="srcSentence">Within the Outlook Web App, create a new mail message addressed to a recipient within your organization.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src64" class="srcSentence">Click  <ui>…</ui>,  click <ui>set permission</ui>, and then select an option.</caps:sentence>
                    <caps:sentence id="src65" class="srcSentence"> For example: <ui>Do Not Forward</ui>, <ui>Do Not Reply All</ui>, <ui>&lt;Company Name&gt; - Confidential</ui> or <ui>&lt;Company Name&gt; - Confidential View Only</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src66" class="srcSentence">Send the message.</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence id="src67" class="srcSentence">Similarly to viewing a protected document, when the recipients receive the email message, they are first authenticated.</caps:sentence>
                  <caps:sentence id="src68" class="srcSentence"> If they are authorized to see the email message, it opens with the restricted usage rights that were specified for that user.</caps:sentence>
                  <caps:sentence id="src69" class="srcSentence"> For example, if you selected <ui>Do Not Reply All</ui>, the <ui>REPLY ALL</ui> option in the message window is not available.</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
        </content>
        <sections></sections>
      </section>
      <relatedTopics>
        <link xlink:href="18564e4a-9364-4ed2-8f17-89d24fc0d878">Using Azure Rights Management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSSource>
</caps:SxS>