---
description: na
keywords: na
pagetitle: 比较 Azure 权限管理和 AD RMS
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8123bd62-1814-4d79-b306-e20c1a00e264
---
# 比较 Azure 权限管理和 AD RMS
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="zh-CN">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="be25ac4f204bed6de6cc00c3d2151712" id="tgt1" class="tgtSentence">如果你了解或以前部署过 Active Directory Rights Management Services (AD RMS)，你可能想知道 <token>aad_rightsmanagement_1</token> (Azure RMS) 在功能和要求方面与它相比有何差别。</caps:sentence>
          <caps:sentence sentenceid="7521f402d78b6d6a9e6af41797eeb376" id="tgt2" class="tgtSentence"> 我们使用以下表格，对 Azure RMS 和 AD RMS 的功能和优势进行了并排比较。</caps:sentence>
          <caps:sentence sentenceid="477b7ad1b46e2ee44e39c4afd0fb2bca" id="tgt3" class="tgtSentence"> 如果你有安全方面的比较问题，请参阅本主题中的<link xlink:href="8123bd62-1814-4d79-b306-e20c1a00e264#BKMK_CryptographicControls">Cryptographic controls for signing and encryption</link>部分。</caps:sentence>
        </para>
        <alert class="note">
          <para>
            <caps:sentence sentenceid="e4a3fc033304896ba3a0e61385c14c43" id="tgt4" class="tgtSentence">为了简化这种比较，本文重复了<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>中的一些信息。</caps:sentence>
            <caps:sentence sentenceid="0cd4c1d3f91d7ae77c08f593962d05f0" id="tgt5" class="tgtSentence"> 使用该主题可获取有关 <token>aad_rightsmanagement_1</token>的更加具体的支持和版本信息。</caps:sentence>
          </para>
        </alert>
        <table>
          <thead>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="dd4f6fdc095b925cadccfa4eb2ce8992" id="tgt6" class="tgtSentence">
                    <token>aad_rightsmanagement_1</token> (Azure RMS)</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="10a13a8b285d52c5b282df542498604e" id="tgt7" class="tgtSentence">Active Directory 权限管理服务 (AD RMS)</caps:sentence>
                </para>
              </TD>
            </tr>
          </thead>
          <tbody>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="c226d017716059bae93cc2282f3d9f6b" id="tgt8" class="tgtSentence">支持 Microsoft Online Services（例如  Exchange Online 和 SharePoint Online 以及 Office 365）中的信息权限管理 (IRM) 功能。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="9b5f164a21936d69d5b7397bfcefcc45" id="tgt9" class="tgtSentence">还支持本地 Microsoft 服务器产品，例如 Exchange Server、SharePoint Server 以及运行 Windows Server 和文件分类基础结构 (FCI) 的文件服务器。</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="1995a1879bb2d9456bd368c9b2ec38e1" id="tgt10" class="tgtSentence">支持本地 Microsoft 服务器产品，例如 Exchange Server、SharePoint Server 以及运行 Windows Server 和文件分类基础结构 (FCI) 的文件服务器。</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="9d6f0d1b12f5ac6f8069f3011c8ccf65" id="tgt11" class="tgtSentence">实现组织之间和任何组织内用户之间的隐式信任。</caps:sentence>
                  <caps:sentence sentenceid="46a010c667f3f122bd68b8588f7976f2" id="tgt12" class="tgtSentence"> 这意味着在用户使用 <token>o365_1</token>、<token>aad_rightsmanagement_1</token> 的情况下，或在用户注册了个人 RMS 的情况下，受保护内容可在同一组织或不同组织的用户之间共享。</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="e4d80a66edb1aabddd202df89bade3ce" id="tgt13" class="tgtSentence">信任必须在两个组织间以直接点对点的关系显式定义，方法是使用受信任用户域 (TUD) 或使用 Active Directory 联合身份验证服务 (AD FS) 创建的联合信任。</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="cf824711edeafa82dd0e696b3bb00797" id="tgt14" class="tgtSentence">提供两个默认权限策略模板，将内容的访问权限仅限于自己的组织范围内；一个模板提供受保护内容的只读查看，另一个模板提供受保护内容的写入或修改权限。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="c32920dbddea453d27ed2552111c501a" id="tgt15" class="tgtSentence">你还可以创建自己的自定义模板，其中包括只对用户的子集可见的部门模板。</caps:sentence>
                  <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt16" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="1775d8d0-9a59-42c8-914f-ce285b71ac1c">Configuring Custom Templates for Azure Rights Management</link>。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="ae1f5210a74032fc1d953b2d1ed459b1" id="tgt17" class="tgtSentence">此外，如果模板不能满足需求，用户可以定义自己的一组权限。</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="06e3add49ca6e40e1780062f07c59af6" id="tgt18" class="tgtSentence">没有默认权限策略模板；必须创建这些模板，然后分发它们。</caps:sentence>
                  <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt19" class="tgtSentence"> 有关详细信息，请参阅 <externalLink><linkText>AD RMS 策略模板注意事项</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=154765</linkUri></externalLink>。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="ae1f5210a74032fc1d953b2d1ed459b1" id="tgt20" class="tgtSentence">此外，如果模板不能满足需求，用户可以定义自己的一组权限。</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="7073d95864453524b17bdf524d445113" id="tgt21" class="tgtSentence">支持的 Microsoft Office 最低版本为 Office 2010，它需要 <externalLink><linkText>RMS 共享应用程序</linkText><linkUri>http://technet.microsoft.com/library/dn339006.aspx</linkUri></externalLink>。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="089b36a8b9fa0ac782da93dc9258739f" id="tgt22" class="tgtSentence">Microsoft Office for Mac：</caps:sentence>
                </para>
                <list class="bullet">
                  <listItem>
                    <para>
                      <caps:sentence sentenceid="7ed7dfb2807e363eb82e8a6e364cdd8e" id="tgt23" class="tgtSentence">Microsoft Office for Mac 2016：支持 </caps:sentence>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence sentenceid="358004ba515360a0a6dc5a5e2d27bd28" id="tgt24" class="tgtSentence">Microsoft Office for Mac 2011：不支持</caps:sentence>
                    </para>
                  </listItem>
                </list>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="62467d1fcd99053d1e1ee017e390a0e2" id="tgt25" class="tgtSentence">支持的 Microsoft Office 最低版本为 Office 2007。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="089b36a8b9fa0ac782da93dc9258739f" id="tgt26" class="tgtSentence">Microsoft Office for Mac：</caps:sentence>
                </para>
                <list class="bullet">
                  <listItem>
                    <para>
                      <caps:sentence sentenceid="7ed7dfb2807e363eb82e8a6e364cdd8e" id="tgt27" class="tgtSentence">Microsoft Office for Mac 2016：支持 </caps:sentence>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence sentenceid="edbda5e83a8969c87c2606e80502b6af" id="tgt28" class="tgtSentence">Microsoft Office for Mac 2011：支持</caps:sentence>
                    </para>
                  </listItem>
                </list>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="5a44cbe0528fe9b3a432efa887efe9d4" id="tgt29" class="tgtSentence">支持适用于 Windows、Mac 计算机和移动设备的 <externalLink><linkText>RMS 共享应用程序</linkText><linkUri>https://technet.microsoft.com/library/dn919648(v=ws.10).aspx</linkUri></externalLink>。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="bb7a03883462a6dff52ca65650785781" id="tgt30" class="tgtSentence">此外，RMS 共享应用程序支持以下内容：</caps:sentence>
                </para>
                <list class="bullet">
                  <listItem>
                    <para>
                      <caps:sentence sentenceid="45d8e9896f26b4eeaca6647411aed19a" id="tgt31" class="tgtSentence">与其他组织的用户共享。</caps:sentence>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence sentenceid="f1573c9bf41ba010ba2fb89e01f0184c" id="tgt32" class="tgtSentence">电子邮件通知，让发件人知道有人尝试打开受保护附件。</caps:sentence>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence sentenceid="26cfeb93740377fc2b69227c8b206672" id="tgt33" class="tgtSentence">适用于用户的文档跟踪站点，包括撤消文档的功能。</caps:sentence>
                    </para>
                  </listItem>
                </list>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="5a44cbe0528fe9b3a432efa887efe9d4" id="tgt34" class="tgtSentence">支持适用于 Windows、Mac 计算机和移动设备的 <externalLink><linkText>RMS 共享应用程序</linkText><linkUri>https://technet.microsoft.com/library/dn919648(v=ws.10).aspx</linkUri></externalLink>。</caps:sentence>
                  <caps:sentence sentenceid="dd173a3d57a12041b1f5129da0180fec" id="tgt35" class="tgtSentence"> 但是，共享不支持与其他组织的用户共享、电子邮件通知、或文档跟踪站点以及用户撤消文档的功能。</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="a46a7c9e2c10c694b173556c4246065e" id="tgt36" class="tgtSentence">可以<externalLink><linkText>在使用 RMS 共享应用程序时，通过本机保护或一般性保护</linkText><linkUri>https://technet.microsoft.com/library/dn339003(v=ws.10).aspx</linkUri></externalLink>，保护所有文件类型。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="c764f0831f0d534a1c5abe38da35883c" id="tgt37" class="tgtSentence">对于其他应用程序，请查看<externalLink><linkText>客户端功能表</linkText><linkUri>https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities</linkUri></externalLink>。</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="a46a7c9e2c10c694b173556c4246065e" id="tgt38" class="tgtSentence">可以<externalLink><linkText>在使用 RMS 共享应用程序时，通过本机保护或一般性保护</linkText><linkUri>https://technet.microsoft.com/library/dn339003(v=ws.10).aspx</linkUri></externalLink>，保护所有文件类型。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="c764f0831f0d534a1c5abe38da35883c" id="tgt39" class="tgtSentence">对于其他应用程序，请查看<externalLink><linkText>客户端功能表</linkText><linkUri>https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities</linkUri></externalLink>。</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="1a950922d8aa42a0e9c69b90f132adca" id="tgt40" class="tgtSentence">支持的 Windows 客户端最低版本为 Windows 7。</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="3ed613461ffa4e945ed9d53d282fe86c" id="tgt41" class="tgtSentence">支持的 Windows 客户端最低版本为 Windows Vista Service Pack 2。</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="81dcee029fa924fc3ac2237da1216695" id="tgt42" class="tgtSentence">移动设备支持包括 Windows Phone、Android、iOS 和 Windows RT。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="113b3fcd5f151a897fa5c8054b41db91" id="tgt43" class="tgtSentence">在支持 Exchange ActiveSync IRM 协议的所有移动设备平台上，也支持使用该协议管理电子邮件。</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="4bd990e460e79d6f48833a87bbe50326" id="tgt44" class="tgtSentence">移动设备支持包括 Windows Phone、Android、iOS 和 Windows RT，并需要 <externalLink><linkText>Active Directory Rights Management 服务移动设备扩展</linkText><linkUri>http://technet.microsoft.com/library/a69ead9d-7dd3-4b38-9830-4728e9757341</linkUri></externalLink>。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="d5735a77570ccef9f0bc7a8390b83756" id="tgt45" class="tgtSentence">在支持 Exchange ActiveSync IRM 协议的所有移动设备平台上，支持使用 Exchange ActiveSync IRM 管理电子邮件。</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="fcb7d1a9e41a6dc637a4384e8c8f6d5a" id="tgt46" class="tgtSentence">支持适用于计算机和移动设备的多因素身份验证 (MFA)。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="a7cc2a447bbad2f255de22373cbf7531" id="tgt47" class="tgtSentence">有关详细信息，请参阅<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_MFA">Multi-factor authentication (MFA) and Azure RMS</link>主题中的<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>部分。</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="5087140bf65daf7329294318da6ec5dd" id="tgt48" class="tgtSentence">如果将 IIS 配置为请求证书，将支持智能卡身份验证。</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="236d25e740b717f60b568dc604c8be31" id="tgt49" class="tgtSentence">支持加密模式 2，而无需额外配置，该模式针对各种密钥长度和加密算法提供更强大的安全性。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="a7cc2a447bbad2f255de22373cbf7531" id="tgt50" class="tgtSentence">有关详细信息，请参阅本主题中的<link xlink:href="8123bd62-1814-4d79-b306-e20c1a00e264#BKMK_CryptographicControls">Cryptographic controls for signing and encryption</link>部分以及 <externalLink><linkText>AD RMS 加密模式</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=266659</linkUri></externalLink>。</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="90441462f2c8d70a3d1dbd87fdc0128b" id="tgt51" class="tgtSentence">默认情况下支持加密模式 1，需要额外配置才能支持加密算法 2，以提供更强大的安全性。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="a7cc2a447bbad2f255de22373cbf7531" id="tgt52" class="tgtSentence">有关详细信息，请参阅本主题中的<link xlink:href="8123bd62-1814-4d79-b306-e20c1a00e264#BKMK_CryptographicControls">Cryptographic controls for signing and encryption</link>部分以及 <externalLink><linkText>AD RMS 加密模式</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=266659</linkUri></externalLink>。</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="4def02a064e66227834742a39a6453f3" id="tgt53" class="tgtSentence">支持从 AD RMS 迁移，如果需要，支持迁移到 AD RMS： </caps:sentence>
                </para>
                <list class="bullet">
                  <listItem>
                    <para>
                      <link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172">Migrating from AD RMS to Azure Rights Management</link>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <link xlink:href="0b1c2064-0d01-45ae-a541-cebd7fd762ad">Decommissioning and Deactivating Azure Rights Management</link>
                    </para>
                  </listItem>
                </list>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="513724b8b2b3212f787289ae26ce8fa2" id="tgt54" class="tgtSentence">支持从 Azure RMS 迁移和迁移到 Azure RMS： </caps:sentence>
                </para>
                <list class="bullet">
                  <listItem>
                    <para>
                      <link xlink:href="0b1c2064-0d01-45ae-a541-cebd7fd762ad">Decommissioning and Deactivating Azure Rights Management</link>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172">Migrating from AD RMS to Azure Rights Management</link>
                    </para>
                  </listItem>
                </list>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence sentenceid="29b599c925c450626495c3ff43158732" id="tgt55" class="tgtSentence">需要 RMS 许可证才能保护内容。</caps:sentence>
                  <caps:sentence sentenceid="26a5fc5335b8a10dc4883b69f7e21ff9" id="tgt56" class="tgtSentence"> 无需 RMS 许可证即可使用已受 Azure RMS（包括另一个组织的用户）保护的内容。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="a7cc2a447bbad2f255de22373cbf7531" id="tgt57" class="tgtSentence">有关详细信息，请参阅<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>中的<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link>部分。</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence sentenceid="65d9e23380b2805f3e5ca4471819d677" id="tgt58" class="tgtSentence">需要 RMS 许可证才能保护内容，以及使用已受 AD RMS 保护的内容。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="eae6c1e66d93e13082e0b15cec8c4880" id="tgt59" class="tgtSentence">有关 AD RMS 授权的详细信息，如果是一般信息，请参阅<externalLink><linkText>客户端访问许可证和管理许可证</linkText><linkUri>https://www.microsoft.com/en-us/Licensing/product-licensing/client-access-license.aspx</linkUri></externalLink>，如果是特定信息，请联系 Microsoft 合作伙伴或 Microsoft 代表。</caps:sentence>
                </para>
              </TD>
            </tr>
          </tbody>
        </table>
      </introduction>
      <section address="BKMK_CryptographicControls">
        <title>
          <caps:sentence sentenceid="20b0a8c650d4d227b140686d54647780" id="tgt60" class="tgtSentence">对签名和加密的加密控制</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="c5e04f946cd6c16d66fa7d8f20731ca9" id="tgt61" class="tgtSentence">
              <token>aad_rightsmanagement_1</token> 始终将 RSA 2048 用于所有公钥加密，将 SHA 256 用于签名操作。</caps:sentence>
            <caps:sentence sentenceid="3dc922db82310826d25792271933fca9" id="tgt62" class="tgtSentence"> 相比之下，AD RMS 支持 RSA 1024 和 RSA 2048，还将 SHA 1 或 SHA 256 用于签名操作。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="5f0e8c5ce4dcc5b9f1f947b9852a27e3" id="tgt63" class="tgtSentence">
              <token>aad_rightsmanagement_1</token> 和 AD RMS 都将 AES 128 用于对称加密。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="40a655ccaa6c95b5538430b0b76927be" id="tgt64" class="tgtSentence">如果创建了租户密钥并由 Microsoft 管理（默认），或者如果你管理自己的租户密钥（称为 BYOK），<token>aad_rightsmanagement_1</token> 将遵守 FIPS 140-2。</caps:sentence>
            <caps:sentence sentenceid="fdb479d690e25f23f156a1ccd4da20b1" id="tgt65" class="tgtSentence"> 有关管理租户密钥的详细信息，请参阅<link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and Implementing Your Azure Rights Management Tenant Key</link>。</caps:sentence>
          </para>
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
          <caps:sentence id="src1" class="srcSentence">If you know or have previously deployed Active Directory Rights Management Services (AD RMS), you might be wondering how <token>aad_rightsmanagement_1</token> (Azure RMS) compares in terms of functionality and requirements.</caps:sentence>
          <caps:sentence id="src2" class="srcSentence"> Use the following table for a side-by-side comparison of the features and benefits of Azure RMS and AD RMS.</caps:sentence>
          <caps:sentence id="src3" class="srcSentence"> If you have security-specific comparison questions, see the <link xlink:href="8123bd62-1814-4d79-b306-e20c1a00e264#BKMK_CryptographicControls">Cryptographic controls for signing and encryption</link> section in this topic.</caps:sentence>
        </para>
        <alert class="note">
          <para>
            <caps:sentence id="src4" class="srcSentence">To make this comparison easier, some information here is repeated from <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>.</caps:sentence>
            <caps:sentence id="src5" class="srcSentence"> Use that topic for more specific support and version information for <token>aad_rightsmanagement_1</token>.</caps:sentence>
          </para>
        </alert>
        <table>
          <thead>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src6" class="srcSentence">
                    <token>aad_rightsmanagement_1</token> (Azure RMS)</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src7" class="srcSentence">Active Directory Rights Management Services (AD RMS)</caps:sentence>
                </para>
              </TD>
            </tr>
          </thead>
          <tbody>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src8" class="srcSentence">Supports information rights management (IRM) capabilities in Microsoft Online services such as Exchange Online and SharePoint Online, as well as Office 365.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src9" class="srcSentence">Also supports on-premises Microsoft server products, such as Exchange Server, SharePoint Server, and file servers that run Windows Server and File Classification Infrastructure (FCI).</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src10" class="srcSentence">Supports on-premises Microsoft server products such as Exchange Server, SharePoint Server, and file servers that run Windows Server and File Classification Infrastructure (FCI).</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src11" class="srcSentence">Enables implicit trust between organizations and users in any organization.</caps:sentence>
                  <caps:sentence id="src12" class="srcSentence"> This means that protected content can be shared between users within the same organization or across organizations when users have <token>o365_1</token>, or <token>aad_rightsmanagement_1</token>, or users sign up for RMS for individuals.</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src13" class="srcSentence">Trusts must be explicitly defined in a direct point-to-point relationship between two organizations by using either trusted user domains (TUDs) or federated trusts that you create by using Active Directory Federation Services (AD FS).</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src14" class="srcSentence">Provides two default rights policy templates that restrict access of the content to your own organization; one that provides read-only viewing of protected content and another template that provides write or modify permissions for the protected content.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src15" class="srcSentence">You can also create your own custom templates, which includes departmental templates that are visible to only a subset of users.</caps:sentence>
                  <caps:sentence id="src16" class="srcSentence"> For more information, see <link xlink:href="1775d8d0-9a59-42c8-914f-ce285b71ac1c">Configuring Custom Templates for Azure Rights Management</link>.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src17" class="srcSentence">In addition, users can define their own set of permissions if the templates are not sufficient.</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src18" class="srcSentence">There are no default rights policy templates; you must create and then distribute these.</caps:sentence>
                  <caps:sentence id="src19" class="srcSentence"> For more information, see <externalLink><linkText>AD RMS Policy Template Considerations</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=154765</linkUri></externalLink>.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src20" class="srcSentence">In addition, users can define their own set of permissions if the templates are not sufficient.</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src21" class="srcSentence">Minimum supported version of Microsoft Office is Office 2010, which requires the <externalLink><linkText>RMS sharing application</linkText><linkUri>http://technet.microsoft.com/library/dn339006.aspx</linkUri></externalLink>.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src22" class="srcSentence">Microsoft Office for Mac:</caps:sentence>
                </para>
                <list class="bullet">
                  <listItem>
                    <para>
                      <caps:sentence id="src23" class="srcSentence">Microsoft Office for Mac 2016: Supported </caps:sentence>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence id="src24" class="srcSentence">Microsoft Office for Mac 2011: Not supported</caps:sentence>
                    </para>
                  </listItem>
                </list>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src25" class="srcSentence">Minimum supported version of Microsoft Office is Office 2007.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src26" class="srcSentence">Microsoft Office for Mac:</caps:sentence>
                </para>
                <list class="bullet">
                  <listItem>
                    <para>
                      <caps:sentence id="src27" class="srcSentence">Microsoft Office for Mac 2016: Supported </caps:sentence>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence id="src28" class="srcSentence">Microsoft Office for Mac 2011: Supported</caps:sentence>
                    </para>
                  </listItem>
                </list>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src29" class="srcSentence">Supports the <externalLink><linkText>RMS sharing application</linkText><linkUri>https://technet.microsoft.com/library/dn919648(v=ws.10).aspx</linkUri></externalLink> for Windows, Mac computers, and mobile devices.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src30" class="srcSentence">In addition, the RMS sharing application supports the following:</caps:sentence>
                </para>
                <list class="bullet">
                  <listItem>
                    <para>
                      <caps:sentence id="src31" class="srcSentence">Sharing with people in another organization.</caps:sentence>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence id="src32" class="srcSentence">Email notification, which lets the sender know when somebody tries to open a protected attachment.</caps:sentence>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence id="src33" class="srcSentence">A document tracking site for users, which includes the ability to revoke a document.</caps:sentence>
                    </para>
                  </listItem>
                </list>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src34" class="srcSentence">Supports the <externalLink><linkText>RMS sharing application</linkText><linkUri>https://technet.microsoft.com/library/dn919648(v=ws.10).aspx</linkUri></externalLink> for Windows, Mac computers, and mobile devices.</caps:sentence>
                  <caps:sentence id="src35" class="srcSentence"> However, sharing does not support sharing with people in another organization, email notification, or the document tracking site and the ability for users to revoke documents.</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src36" class="srcSentence">All file types can be protected with <externalLink><linkText>native or generic protection when you use the RMS sharing application</linkText><linkUri>https://technet.microsoft.com/library/dn339003(v=ws.10).aspx</linkUri></externalLink>.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src37" class="srcSentence">For other applications, check the <externalLink><linkText>client capabilities table</linkText><linkUri>https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities</linkUri></externalLink>.</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src38" class="srcSentence">All file types can be protected with <externalLink><linkText>native or generic protection when you use the RMS sharing application</linkText><linkUri>https://technet.microsoft.com/library/dn339003(v=ws.10).aspx</linkUri></externalLink>.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src39" class="srcSentence">For other applications, check the <externalLink><linkText>client capabilities table</linkText><linkUri>https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities</linkUri></externalLink>.</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src40" class="srcSentence">Minimum supported version of the Windows client is Windows 7.</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src41" class="srcSentence">Minimum supported version of the Windows client is Windows Vista Service Pack 2.</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src42" class="srcSentence">Mobile device support includes Windows Phone, Android, iOS, and Windows RT.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src43" class="srcSentence">Email support by using Exchange ActiveSync IRM is also supported on all mobile device platforms that support this protocol.</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src44" class="srcSentence">Mobile device support includes Windows Phone, Android, iOS, and Windows RT, and requires the <externalLink><linkText>Active Directory Rights Management Services Mobile Device Extension</linkText><linkUri>http://technet.microsoft.com/library/a69ead9d-7dd3-4b38-9830-4728e9757341</linkUri></externalLink>.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src45" class="srcSentence">Email support by using Exchange ActiveSync IRM is supported on all mobile device platforms that support this protocol.</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src46" class="srcSentence">Supports multi-factor authentication (MFA) for computers and mobile devices.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src47" class="srcSentence">For more information, see the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_MFA">Multi-factor authentication (MFA) and Azure RMS</link> section in the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link> topic.</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src48" class="srcSentence">Supports smart card authentication if IIS is configured to request certificates.</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src49" class="srcSentence">Supports Cryptographic Mode 2 without additional configuration, which provides stronger security for key lengths and encryption algorithms.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src50" class="srcSentence">For more information, see the <link xlink:href="8123bd62-1814-4d79-b306-e20c1a00e264#BKMK_CryptographicControls">Cryptographic controls for signing and encryption</link> section in this topic, and <externalLink><linkText>AD RMS Cryptographic Modes</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=266659</linkUri></externalLink>.</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src51" class="srcSentence">Supports Cryptographic Mode 1 by default and requires additional configuration to support Cryptographic Mode 2 for stronger security.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src52" class="srcSentence">For more information, see the <link xlink:href="8123bd62-1814-4d79-b306-e20c1a00e264#BKMK_CryptographicControls">Cryptographic controls for signing and encryption</link> section in this topic, and <externalLink><linkText>AD RMS Cryptographic Modes</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=266659</linkUri></externalLink>.</caps:sentence>
                </para>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src53" class="srcSentence">Supports migration from AD RMS and if required, to AD RMS: </caps:sentence>
                </para>
                <list class="bullet">
                  <listItem>
                    <para>
                      <link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172">Migrating from AD RMS to Azure Rights Management</link>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <link xlink:href="0b1c2064-0d01-45ae-a541-cebd7fd762ad">Decommissioning and Deactivating Azure Rights Management</link>
                    </para>
                  </listItem>
                </list>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src54" class="srcSentence">Supports migration from Azure RMS and to Azure RMS: </caps:sentence>
                </para>
                <list class="bullet">
                  <listItem>
                    <para>
                      <link xlink:href="0b1c2064-0d01-45ae-a541-cebd7fd762ad">Decommissioning and Deactivating Azure Rights Management</link>
                    </para>
                  </listItem>
                  <listItem>
                    <para>
                      <link xlink:href="828cf1f7-d0e7-4edf-8525-91896dbe3172">Migrating from AD RMS to Azure Rights Management</link>
                    </para>
                  </listItem>
                </list>
              </TD>
            </tr>
            <tr>
              <TD>
                <para>
                  <caps:sentence id="src55" class="srcSentence">Requires an RMS license to protect content.</caps:sentence>
                  <caps:sentence id="src56" class="srcSentence"> No RMS license is required to consume content that has been protected by Azure RMS (includes users from another organization).</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src57" class="srcSentence">For more information, see the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link> section from    <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>.</caps:sentence>
                </para>
              </TD>
              <TD>
                <para>
                  <caps:sentence id="src58" class="srcSentence">Requires an RMS license to protect content, and to consume  content that has been protected by AD RMS.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src59" class="srcSentence">For more information about licensing for AD RMS, see <externalLink><linkText>Client Access Licenses and Management Licenses</linkText><linkUri>https://www.microsoft.com/en-us/Licensing/product-licensing/client-access-license.aspx</linkUri></externalLink> for general information, but contact your Microsoft partner or Microsoft representative for specific information.</caps:sentence>
                </para>
              </TD>
            </tr>
          </tbody>
        </table>
      </introduction>
      <section address="BKMK_CryptographicControls">
        <title>
          <caps:sentence id="src60" class="srcSentence">Cryptographic controls for signing and encryption</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src61" class="srcSentence">
              <token>aad_rightsmanagement_1</token> always uses RSA 2048 for all public key cryptography and SHA 256 for signing operations.</caps:sentence>
            <caps:sentence id="src62" class="srcSentence"> In comparison, AD RMS supports RSA 1024 and RSA 2048, and SHA 1 or SHA 256 for signing operations.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src63" class="srcSentence">Both <token>aad_rightsmanagement_1</token> and AD RMS use AES 128 for symmetric encryption.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src64" class="srcSentence">
              <token>aad_rightsmanagement_1</token> is compliant with FIPS 140-2 when your tenant key is created and managed by Microsoft (the default), or if you manage your own tenant key (known as BYOK).</caps:sentence>
            <caps:sentence id="src65" class="srcSentence"> For more information about managing your tenant key, see <link xlink:href="f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14">Planning and Implementing Your Azure Rights Management Tenant Key</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="5214667c-ec69-42ca-8bbf-8cb22da8c62e">Getting started with Azure Rights Management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSSource>
</caps:SxS>