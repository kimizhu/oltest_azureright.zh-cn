---
description: na
keywords: na
pagetitle: Deploying the Azure Rights Management Connector
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 90e7e33f-9ecc-497b-89c5-09205ffc5066
---
# 部署 Azure 权限管理连接器
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="zh-CN">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="7a6162944876d30464058f0949503015" id="tgt1" class="tgtSentence">使用以下信息可以了解 Microsoft 权限管理 (RMS) 连接器，以及如何使用该连接器提供信息保护，包括保护使用 Microsoft Exchange Server、Microsoft SharePoint Server 或文件服务器（运行 Windows Server 并使用文件服务器资源管理器的文件分类基础结构 (FCI) 功能）的现有本地部署。</caps:sentence>
        </para>
        <alert class="tip">
          <para>
            <caps:sentence sentenceid="7fc01b361b5631a192db69caffdcd7e8" id="tgt2" class="tgtSentence">有关带屏幕截图的高级示例方案，请参阅<link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link>主题中的<link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df#BKMK_Example_FCI">Automatically protecting files on file servers running Windows Server and File Classification Infrastructure</link> 部分。</caps:sentence>
          </para>
        </alert>
      </introduction>
      <section address="OverviewConnector">
        <title>
          <caps:sentence sentenceid="b5d593e32f204c735a7cc2a1ee26773f" id="tgt3" class="tgtSentence">Microsoft 权限管理连接器概述</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="055cd4a135730b9a2452b3f71e42bcae" id="tgt4" class="tgtSentence">借助 Microsoft Rights Management (RMS) 连接器，你可以迅速让现有本地服务器将信息权限管理 (IRM) 功能用于基于云的 Microsoft Rights Management 服务 (Azure RMS)。</caps:sentence>
            <caps:sentence sentenceid="d37cd5e9cee3f98d1e1e8e14925cc908" id="tgt5" class="tgtSentence"> 使用此功能，IT 部门和用户能够轻松地保护组织内部和外部的文档和图片，既无需安装其他基础结构，也无需建立与其他组织的信任关系。</caps:sentence>
            <caps:sentence sentenceid="8b4640e162d8b6f30ce69650ec8dec72" id="tgt6" class="tgtSentence"> 你可以在混合方案中使用此连接器，即使你的一些用户连接到了在线服务。</caps:sentence>
            <caps:sentence sentenceid="92aa1d9cff38a744b73674c9684d348c" id="tgt7" class="tgtSentence"> 例如，一些用户的邮箱使用 Exchange Online，一些用户的邮箱使用 Exchange Server。</caps:sentence>
            <caps:sentence sentenceid="f1340f9202cba685f30dcd8a9408f1d5" id="tgt8" class="tgtSentence"> 安装 RMS 连接器后，所有用户都可以使用 Azure RMS 保护和使用电子邮件和附件，并且信息保护在两套部署配置中无缝合作。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="e709d918112fb063e845785a8ddc51c8" id="tgt9" class="tgtSentence">RMS 连接器是一种小型化服务，你可将其安装在本地，包括安装在运行 Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2 的服务器上。</caps:sentence>
            <caps:sentence sentenceid="65102465684db5837c8273fc9062a53c" id="tgt10" class="tgtSentence"> 除了在物理计算机上运行连接器之外，你也可以在虚拟机（包括 Azure IaaS VM）上运行它。</caps:sentence>
            <caps:sentence sentenceid="18dd3d1247d38f9a03fd4aeaf5b05844" id="tgt11" class="tgtSentence"> 在你安装和配置连接器之后，它将充当本地服务器和云服务之间的通信接口（一种中继）。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="906859d1fbb2c7b383c26bbd802771a5" id="tgt12" class="tgtSentence">如果你自行管理 Azure RMS 的租户密钥（自带密钥，即 BYOK 方案），RMS 连接器和使用该连接器的本地服务器不会访问包含你的租户密钥的硬件安全模块 (HSM)。</caps:sentence>
            <caps:sentence sentenceid="da886071099dcdb972fc5b81a3c7dbb2" id="tgt13" class="tgtSentence"> 这是因为，使用租户密钥的所有加密操作都是在 Azure RMS 中并不是在本地执行的。</caps:sentence>
          </para>
          <mediaLink>
            <image xlink:href="fca243be-b886-43ad-91e6-6900f7e2cd85"></image>
          </mediaLink>
          <para></para>
          <para></para>
          <para>
            <caps:sentence sentenceid="9791cbcb95885c74e73fb153b6a17c09" id="tgt14" class="tgtSentence">RMS 连接器支持以下本地服务器：Exchange Server、SharePoint Server 以及文件服务器，这些文件服务器运行 Windows Server 并使用文件分类基础结构来进行分类并将策略应用于文件夹内 Office 文档。</caps:sentence>
            <caps:sentence sentenceid="e1ff50040607e9a3434a57e3d86f49d3" id="tgt15" class="tgtSentence"> 如果你想要通过文件分类保护所有文件类型，请勿使用 RMS 连接器，而是使用 <externalLink><linkText>RMS 保护 cmdlet</linkText><linkUri>https://msdn.microsoft.com/library/azure/mt433195.aspx</linkUri></externalLink>。</caps:sentence>
          </para>
          <alert class="note">
            <para>
              <caps:sentence sentenceid="52ccad7301b8accfe3221729aca291fb" id="tgt16" class="tgtSentence">有关这些本地服务器的受支持版本，请参阅 <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedApplications">Applications that support Azure RMS</link>主题<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>部分中的“支持 Azure RMS 的本地服务器”。</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence sentenceid="c1feb4df24b8f53572830176cc5d76ae" id="tgt17" class="tgtSentence">使用以下部分可帮助你计划、安装和配置 RMS 连接器。</caps:sentence>
            <caps:sentence sentenceid="c02f0587eb0c5f44ea097651abb7371e" id="tgt18" class="tgtSentence"> 你必须随后进行一些安装后配置，使得你的服务器能够使用连接器。</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_Prereqs">Prerequisites for the RMS connector</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <embeddedLabel>
                  <caps:sentence sentenceid="6ca7c6f16311428a9540360a29c0a7da" id="tgt19" class="tgtSentence">步骤 1： </caps:sentence>
                </embeddedLabel>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_InstallingConnector">Installing the RMS connector</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <embeddedLabel>
                  <caps:sentence sentenceid="029a39daeec69f6bae5275d8aabbe5c2" id="tgt20" class="tgtSentence">步骤 2： </caps:sentence>
                </embeddedLabel>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#EnteringCredentials">Entering credentials</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <embeddedLabel>
                  <caps:sentence sentenceid="6f60a71936fbce180817beb0074f20ce" id="tgt21" class="tgtSentence">步骤 3： </caps:sentence>
                </embeddedLabel>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#AuthorizingServers">Authorizing servers to use the RMS connector</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <embeddedLabel>
                  <caps:sentence sentenceid="58e2e9cd07b16bc37c239296a4cfe3e1" id="tgt22" class="tgtSentence">步骤 4： </caps:sentence>
                </embeddedLabel>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#ConfiguringConnector">Configuring load balancing and high availability</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="16b3cffc06da141a8ba5bb6c27709e12" id="tgt23" class="tgtSentence">可选：<link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ConfiguringHTTPS">Configuring the RMS connector to use HTTPS</link></caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="16b3cffc06da141a8ba5bb6c27709e12" id="tgt24" class="tgtSentence">可选：<link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ConfiguringWebProxy">Configuring the RMS connector for a web proxy server</link></caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="16b3cffc06da141a8ba5bb6c27709e12" id="tgt25" class="tgtSentence">可选：<link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_InstallingStandaloneTool">Installing the RMS connector administration tool on administrative computers</link></caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <embeddedLabel>
                  <caps:sentence sentenceid="f30fc367a4cf35d144e04c4d95519c8a" id="tgt26" class="tgtSentence">步骤 5： </caps:sentence>
                </embeddedLabel>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#ConfiguringServers">Configuring servers to use the RMS connector</link>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ExchangeServer">Configuring an Exchange server to use the connector</link>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ConfiguringSharePoint">Configuring a SharePoint server to use the connector</link>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_FileServer">Configuring a file server for File Classification Infrastructure to use the connector</link>
                  </para>
                </listItem>
              </list>
            </listItem>
            <listItem>
              <para>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_NextSteps">Next steps</link>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section address="BKMK_Prereqs">
        <title>
          <caps:sentence sentenceid="1ccfe81dd120310397a2c86bb13142f5" id="tgt27" class="tgtSentence">RMS 连接器的必备组件</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="2753d692d0129a3db955c26257fc24be" id="tgt28" class="tgtSentence">在安装 RMS 连接器之前，请确保符合以下要求。</caps:sentence>
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
                    <caps:sentence sentenceid="4cc693aa561a743fe51fd95b50ec9ab4" id="tgt31" class="tgtSentence">权限管理服务 (RMS) 已激活</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <link xlink:href="f8707e01-b239-4d1a-a1ea-0d1cf9a8d214">Activating Azure Rights Management</link>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="a39487505ec7117bf1492b761a6f6441" id="tgt32" class="tgtSentence">Active Directory 林和 Azure Active Directory 之间的目录同步</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="8c4c3dd641424a103119c6e1f8b9940b" id="tgt33" class="tgtSentence">RMS 激活之后，必须将 Azure Active Directory 配置为用于 Active Directory 数据库中的用户和组。</caps:sentence>
                  </para>
                  <alert class="important">
                    <para>
                      <caps:sentence sentenceid="509b0b290dfd78fe591e65518a910d87" id="tgt34" class="tgtSentence">要使 RMS 连接器正常工作，你必须执行此目录同步步骤，即使对于测试网络，也是如此。</caps:sentence>
                      <caps:sentence sentenceid="3ee60f6a516d94750c9130d7f944a827" id="tgt35" class="tgtSentence"> 尽管你可以通过在 Azure Active Directory 中手动创建的帐户来使用 Office 365 和 Azure Active Directory，但此连接器要求 Azure Active Directory 中的帐户必须与 Active Directory 域服务同步；进行手动密码同步是不够的。</caps:sentence>
                    </para>
                  </alert>
                  <para>
                    <caps:sentence sentenceid="8a4bbdf5f66ee36c5612a9237510a57f" id="tgt36" class="tgtSentence">有关详细信息，请参阅下列资源：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <externalLink>
                          <linkText>
                            <caps:sentence sentenceid="3e65fcb329eccafe488ef11660214ac5" id="tgt37" class="tgtSentence">有关配置 Azure AD 租户的说明</caps:sentence>
                          </linkText>
                          <linkUri>http://technet.microsoft.com/library/hh967611.aspx</linkUri>
                        </externalLink>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <externalLink>
                          <linkText>
                            <caps:sentence sentenceid="366821e84306191c5ec1b4ff9e8ccb11" id="tgt38" class="tgtSentence">有关使用 DirSync 实现与 AAD 的目录同步的说明</caps:sentence>
                          </linkText>
                          <linkUri>http://technet.microsoft.com/library/hh967642.aspx</linkUri>
                        </externalLink>
                        <br />
                      </para>
                    </listItem>
                  </list>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="818270815a83e7634bad4832d21d9d5d" id="tgt39" class="tgtSentence">只是可选但也推荐的选项： </caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="82d267c56f58dfbc3812cafed3444112" id="tgt40" class="tgtSentence">启用本地 Active Directory 和 Azure Active Directory 之间的联合身份验证  </caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="8392c40c5baf1a26c9344283ee2d6a36" id="tgt41" class="tgtSentence">你可以启用本地目录和 Azure Active Directory 之间的联合身份验证。</caps:sentence>
                    <caps:sentence sentenceid="4176578bb48c0aaaddbc4626333bad56" id="tgt42" class="tgtSentence"> 此配置使用 RMS 服务单一登录，实现更加无缝的用户体验。</caps:sentence>
                    <caps:sentence sentenceid="1c6ed80577ce90979fbe4402e70c8195" id="tgt43" class="tgtSentence"> 而如果没有单一登录，用户在能够使用权限保护内容之前，会收到提供凭据的提示。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="b2365eee5db710147350dcfd7fe810da" id="tgt44" class="tgtSentence">有关使用 Active Directory 联合身份验证服务 (AD FS) 来配置 Active Directory 域服务和 Azure Active Directory 之间的联合身份验证的说明，请参阅 Windows Server 库中的<externalLink><linkText>清单：使用 AD FS 实现和管理单一登录</linkText><linkUri>http://technet.microsoft.com/library/jj205462.aspx</linkUri></externalLink>。</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="071b86d5dceed0e99b064aaa5b0cf0ad" id="tgt45" class="tgtSentence">在最少两台成员计算机上安装 RMS 连接器：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="743ac00b3533aa77df2122ea451e0af2" id="tgt46" class="tgtSentence">64 位物理或虚拟计算机，运行以下操作系统之一： </caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="dcfe8446422dcac28d99767b484594f0" id="tgt47" class="tgtSentence">Windows Server 2012 R2</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="0e22230e53d6559d213afe9ce343ebf5" id="tgt48" class="tgtSentence">Windows Server 2012</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="e4dd9fe1b5efc59f4b6383a1e8e6ccd0" id="tgt49" class="tgtSentence">Windows Server 2008 R2</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="fb46a715b458a6439f4c1c8954c58a24" id="tgt50" class="tgtSentence">至少 1 GB 的 RAM</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="de435841b10527c4c6543b5389a57ef3" id="tgt51" class="tgtSentence">至少 64 GB 的磁盘空间</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="8a22600aef9db831ec10619c162d4aba" id="tgt52" class="tgtSentence">至少一个网络接口</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="411b32416763480d0426f0201d575c0d" id="tgt53" class="tgtSentence">通过防火墙（或 Web 代理）访问 Internet，无需进行身份验证</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="482d832f7ce2667a49d4ec0bb76ff242" id="tgt54" class="tgtSentence">必须位于某个林或域中，而该林或域信任组织内的其他林（包含要用于 RMS 连接器的 Exchange 或 SharePoint 服务器安装）</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="be829763c3ab214a76cc04344f3e4aca" id="tgt55" class="tgtSentence">为了实现容错和高可用性，你必须在至少两台计算机上安装 RMS 连接器。</caps:sentence>
                  </para>
                  <alert class="tip">
                    <para>
                      <caps:sentence sentenceid="e06f17edc1c0af9ca06d63df33e0254d" id="tgt56" class="tgtSentence">如果你正在使用 Outlook Web Access 或装有 Exchange ActiveSync IRM 的移动设备，并且你必须保持对 Azure RMS 保护的电子邮件和附件的访问权限，则我们建议你部署一组负载平衡的连接器服务器，以确保高可用性。</caps:sentence>
                    </para>
                  </alert>
                  <para>
                    <caps:sentence sentenceid="5afb51fb26e7c5af4abb8660840eccfc" id="tgt57" class="tgtSentence">你不需要专用服务器来运行连接器，但必须在将要使用连接器的服务器之外的一台独立计算机上安装连接器。</caps:sentence>
                  </para>
                  <alert class="important">
                    <para>
                      <caps:sentence sentenceid="ce6105ea435c7505486ad146f3d6eb5e" id="tgt58" class="tgtSentence">如果你希望在使用这些服务提供的功能时运行 Azure RMS，请不要将连接器安装在运行 Exchange Server、SharePoint Server 或文件服务器（已针对文件分类基础结构进行配置，前提是你希望将这些服务提供的功能用于  Azure RMS）的计算机上。</caps:sentence>
                      <caps:sentence sentenceid="5952ef47c89b6eeb70c806f4e256b86b" id="tgt59" class="tgtSentence"> 此外，请不要在域控制器上安装此连接器。</caps:sentence>
                    </para>
                  </alert>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section address="BKMK_InstallingConnector">
        <title>
          <caps:sentence sentenceid="a097531c7c73ba2168b7fd0023037981" id="tgt60" class="tgtSentence">安装 RMS 连接器</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="2683aff2913538589624d5341751493f" id="tgt61" class="tgtSentence">在你确认满足前一部分中的先决条件之后，请根据以下说明来安装 RMS 连接器：</caps:sentence>
          </para>
          <list class="ordered">
            <listItem>
              <para>
                <caps:sentence sentenceid="5dba1d0f718bd4797a48a73d554aa7e9" id="tgt62" class="tgtSentence">确定将要运行 RMS 连接器的计算机（最少两台）。</caps:sentence>
                <caps:sentence sentenceid="65a75631b3c8a144e8c2790e1fe01c8d" id="tgt63" class="tgtSentence"> 它们必须达到前一部分所列的最低规格。</caps:sentence>
              </para>
              <alert class="note">
                <para>
                  <caps:sentence sentenceid="29fbb72aff9e109ed56013148758d88f" id="tgt64" class="tgtSentence">你将为每个租户（Office 365 租户或 Azure AD 租户）安装单个 RMS 连接器（包含多个服务器以实现高可用性）。</caps:sentence>
                  <caps:sentence sentenceid="eb01f1c670f3277d52a2d3c7b03907a4" id="tgt65" class="tgtSentence"> 与 Active Directory RMS 不同，你无需在每个林中安装 RMS 连接器。</caps:sentence>
                </para>
              </alert>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="6ad617dfefeb1ce2bdd17602e58ee19c" id="tgt66" class="tgtSentence">从 <externalLink><linkText>Microsoft 下载中心</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=314106</linkUri></externalLink>下载 RMS 连接器的源文件。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="2baf601fe5549c9246d69973f36aa263" id="tgt67" class="tgtSentence">若要安装 RMS 连接器，请下载 RMSConnectorSetup.exe。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="cffdd0bc68b81b41855c6d1dfd403038" id="tgt68" class="tgtSentence">此外：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="db53535715f025a7acec80ecfa44282c" id="tgt69" class="tgtSentence">如果你以后要从 32 位计算机配置连接器，请下载 RMSConnectorAdminToolSetup_x86.exe。</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="c7e0e8551b1daf0b1878241811edcb12" id="tgt70" class="tgtSentence">如果你要使用 RMS 连接器的服务器配置工具，自动执行本地服务器上的注册表设置的配置，也请下载 GenConnectorConfig.ps1。</caps:sentence>
                  </para>
                </listItem>
              </list>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="7df8401333044f571ba23d79452b23e2" id="tgt71" class="tgtSentence">在你要安装 RMS 连接器的计算机上，以管理员权限运行 <legacyBold>RMSConnectorSetup.exe</legacyBold>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="fb1f144df529fb3686201af678647e9f" id="tgt72" class="tgtSentence">在“Microsoft Rights Management 连接器设置”页面的欢迎页上，选择“在计算机上安装 Microsoft Rights Management 连接器”，然后单击“下一步”<ui></ui><ui></ui>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="f6750556263fa6a90035e84aca8a3a88" id="tgt73" class="tgtSentence">阅读并同意 RMS 连接器许可条款，然后单击“下一步”<legacyBold></legacyBold>。</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="b9be15fccc81a0be0495ca57869884b4" id="tgt74" class="tgtSentence">若要继续，请输入帐号和密码以配置 RMS 连接器。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="EnteringCredentials">
        <title>
          <caps:sentence sentenceid="f3ab65572ec1a60cccba387066475792" id="tgt75" class="tgtSentence">输入凭据</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="cb348a59fe77cb8a13563b6c2d096435" id="tgt76" class="tgtSentence">在能够配置 RMS 连接器之前，你必须输入具有足够 RMS 连接器配置权限的帐户的凭据。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="d3d920ac821595ad446b513e8e9a2cfa" id="tgt77" class="tgtSentence">此外，如果你实现了<externalLink><linkText>内置控件</linkText><linkUri>https://technet.microsoft.com/library/jj658941.aspx#BKMK_OnboardingControls</linkUri></externalLink>，请确保你指定的帐户能够保护内容。例如，如果你将保护内容的功能限制给“IT 部门”组，则在此指定的帐户必须是该组成员。如果不是，你将看到以下错误消息：“发现管理服务和组织位置的尝试失败。”<ui></ui>“请确保为你的组织启用了 Microsoft Rights Management 服务。”<ui></ui></caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="f1bb02f59ce23ab4c46f5cfdb0be3f02" id="tgt78" class="tgtSentence">你可以使用具有以下某一种权限的帐户：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="721928e95c3e4470484e63ec4a0a892e" id="tgt79" class="tgtSentence">
                  <legacyBold>Office 365 租户管理员</legacyBold>：Office 365 租户的全局管理员帐户。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="aaa4c1c71dd5c17c11a14f0253bd01e5" id="tgt80" class="tgtSentence">
                  <legacyBold>Azure Rights Management 全局管理员</legacyBold>：具有 Azure RMS 租户管理员权限的帐户。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="6d3697a2c3fc42aec1c10c7baafe0a34" id="tgt81" class="tgtSentence">
                  <legacyBold>Microsoft RMS 连接器管理员</legacyBold>：Azure Active Directory 中的一个帐户，已被授予为你的组织安装和管理 RMS 连接器的权限。</caps:sentence>
              </para>
              <para></para>
              <alert class="note">
                <para>
                  <caps:sentence sentenceid="a4cfb8c9b77637682a5f4eca5c437c52" id="tgt82" class="tgtSentence">如果你希望使用 Microsoft RMS 连接器管理员帐户，则必须先执行以下操作以分配 RMS 连接器管理员角色：</caps:sentence>
                </para>
                <list class="ordered">
                  <listItem>
                    <para>
                      <caps:sentence sentenceid="fdf56343b661842aa0b6e37fdf12a7f3" id="tgt83" class="tgtSentence">在同一台计算机上，下载和安装适用于权限管理的 Windows PowerShell。</caps:sentence>
                      <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt84" class="tgtSentence"> 有关详细信息，请参阅<link xlink:href="0d665ed6-b1de-4d63-854a-bc57c1c49844">Installing Windows PowerShell for Azure Rights Management</link>。</caps:sentence>
                    </para>
                    <para>
                      <caps:sentence sentenceid="a796808f0542040254624a40c5de067c" id="tgt85" class="tgtSentence">使用<ui>“以管理员身份运行”</ui>命令启动 Windows PowerShell，并使用 <externalLink><linkText>Connect-AadrmService</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629415.aspx</linkUri></externalLink> 命令连接到 Azure RMS 服务： </caps:sentence>
                    </para>
                    <code>Connect-AadrmService                   //provide Office 365 tenant administrator or Azure RMS global administrator credentials</code>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence sentenceid="8919365c5c68f46a9fe26ea91750f360" id="tgt86" class="tgtSentence">然后运行 <externalLink><linkText>Add-AadrmRoleBasedAdministrator</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629417.aspx</linkUri></externalLink> 命令，仅使用以下参数之一：   </caps:sentence>
                    </para>
                    <code>Add-AadrmRoleBasedAdministrator -EmailAddress &lt;email address&gt; -Role "ConnectorAdministrator"</code>
                    <code>Add-AadrmRoleBasedAdministrator -ObjectId &lt;object id&gt; -Role "ConnectorAdministrator"</code>
                    <code>Add-AadrmRoleBasedAdministrator -SecurityGroupDisplayName &lt;group Name&gt; -Role "ConnectorAdministrator"</code>
                    <para>
                      <caps:sentence sentenceid="62f09bdf0c668d96dae04afe4a65c6c0" id="tgt87" class="tgtSentence">例如，键入：<userInput>Add-AadrmRoleBasedAdministrator -EmailAddress melisa@contoso.com -Role " ConnectorAdministrator "</userInput></caps:sentence>
                    </para>
                    <para>
                      <caps:sentence sentenceid="216f4216e4c945f3c920e7500c84d937" id="tgt88" class="tgtSentence">尽管这些命令使用 ConnectorAdministrator 角色，但你也可以在此处使用 GlobalAdministrator 角色。</caps:sentence>
                    </para>
                  </listItem>
                </list>
              </alert>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="48c33e420a248058e2bbd625b7a34970" id="tgt89" class="tgtSentence">在 RMS 连接器安装过程中，将会验证和安装所有必备软件。如果还没有 Internet Information Services (IIS)，则会安装该服务。另外还要安装和配置连接器软件。</caps:sentence>
            <caps:sentence sentenceid="beb35addbc938394bbd44ea88e344c6f" id="tgt90" class="tgtSentence"> 此外，还会创建以下各项，做好配置 Azure RMS 的准备：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="1e4cdaf9ab90508068e985fa431c9f26" id="tgt91" class="tgtSentence">一个空表，用于列出被授权使用连接器与 Azure RMS 通信的服务器。</caps:sentence>
                <caps:sentence sentenceid="955f4d8c6905a4bbb95744d0c6f6cc1b" id="tgt92" class="tgtSentence"> 你以后可将服务器添加至此表。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="be814012ee77847e7183933f5f00bfdb" id="tgt93" class="tgtSentence">一组连接器安全令牌，授权对 Azure RMS 所进行的操作。</caps:sentence>
                <caps:sentence sentenceid="ebc2ff50cd76fd12aa3c159e735dfc8b" id="tgt94" class="tgtSentence"> 可从 Azure RMS 下载这些令牌，并安装在注册表中的本地计算机上。</caps:sentence>
                <caps:sentence sentenceid="ce6b2a1425f0bcda64af2c1fbf277f6e" id="tgt95" class="tgtSentence"> 它们通过使用数据保护应用程序编程接口 (DPAPI) 和本地系统帐户凭据得到保护。</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="585f16e4f6f2ac28947880d321fd082b" id="tgt96" class="tgtSentence">在向导的最后一页上执行以下操作，然后单击“完成”<ui></ui>：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="e7a8aad1e2923e9f3a5eb5a441f023c2" id="tgt97" class="tgtSentence">如果这是你安装的第一个连接器，此时请不要选择“启动连接器管理员控制台对服务器授权”<ui></ui>。</caps:sentence>
                <caps:sentence sentenceid="b3270ab9c3d0af9feb445dd94f6b6f5e" id="tgt98" class="tgtSentence"> 在安装第二个（或最后一个）RMS 连接器之后，再选择此选项。</caps:sentence>
                <caps:sentence sentenceid="2b4e0a614cd77b42f7d76081228dbf62" id="tgt99" class="tgtSentence"> 请在至少一台其他计算机上再次运行向导。</caps:sentence>
                <caps:sentence sentenceid="0902aa712955f05caec15a8b74d25ce9" id="tgt100" class="tgtSentence"> 你必须安装至少两个连接器。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="2a8dbb6ef8c095f46e806d796b75a30b" id="tgt101" class="tgtSentence">如果你已安装第二个（或最后一个）连接器，请选择“启动连接器管理员控制台对服务器授权”<ui></ui>。</caps:sentence>
              </para>
            </listItem>
          </list>
          <alert class="tip">
            <para>
              <caps:sentence sentenceid="df6dcb3a83256911b88b67bb071ae445" id="tgt102" class="tgtSentence">现在，你可以执行一项验证测试，以测试 RMS 连接器的 Web 服务是否可以运行： </caps:sentence>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <caps:sentence sentenceid="e2caec12484fc91954de516e88a6e270" id="tgt103" class="tgtSentence">从 Web 浏览器连接至 <userInput>http://&lt;connectoraddress&gt;/_wmcs/certification/servercertification.asmx</userInput>，将 <placeholder>&lt;connectoraddress&gt;</placeholder> 替换为安装 RMS 连接器的服务器地址或名称。</caps:sentence>
                  <caps:sentence sentenceid="96f9568af7dcb52bbe651774991fa54d" id="tgt104" class="tgtSentence"> 如果成功连接，则将显示 <ui>ServerCertificationWebService</ui> 页。</caps:sentence>
                </para>
              </listItem>
            </list>
          </alert>
          <para>
            <caps:sentence sentenceid="f2d538e4f0c1c2e742e383da8171c027" id="tgt105" class="tgtSentence">如果你需要卸载 RMS 连接器，请再次运行向导并选择卸载选项。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="AuthorizingServers">
        <title>
          <caps:sentence sentenceid="8214573b296103dbf1a5995811a1f621" id="tgt106" class="tgtSentence">授权服务器使用 RMS 连接器</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="1d3d4797d2c7b0915d44aa19c772697b" id="tgt107" class="tgtSentence">在至少两台计算机上安装 RMS 连接器之后，即可为你希望其使用 RMS 连接器的服务器和服务授权。</caps:sentence>
            <caps:sentence sentenceid="c2a56e3bbc38fd5b16f71436ba5d2ce6" id="tgt108" class="tgtSentence"> 例如运行 Exchange Server 2013 或 SharePoint Server 2013 的服务器。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="b3b86015971adac6b8f3e444ecb4d5aa" id="tgt109" class="tgtSentence">若要定义这些服务器，请运行 RMS 连接器管理工具，然后向允许服务器列表添加条目。</caps:sentence>
            <caps:sentence sentenceid="13168f22ff5466332095675df81a5d13" id="tgt110" class="tgtSentence"> 如果你在 Microsoft Rights Management 连接器设置向导结束时选择了“启动连接器管理员控制台对服务器授权”<ui></ui>，则可运行此工具，也可从向导单独运行此工具。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="ddfbe0c4ee033218eceaa53926be88a1" id="tgt111" class="tgtSentence">当你向这些服务器授权时，请注意以下事项：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="101ebdc12421108a1e09ccb784b5e510" id="tgt112" class="tgtSentence">你添加的服务器将被授予特殊权限。</caps:sentence>
                <caps:sentence sentenceid="4fd11713639079db66ddbd3b56934f67" id="tgt113" class="tgtSentence"> 你在连接器中为 Exchange Server 角色指定的所有帐户将在 Azure RMS 中授予<externalLink><linkText>超级用户角色</linkText><linkUri>https://technet.microsoft.com/library/mt147272.aspx</linkUri></externalLink>，这将给予他们访问所有此 RMS 租户的所有内容的权限。</caps:sentence>
                <caps:sentence sentenceid="c960a65524412d07fa83118cbee540c4" id="tgt114" class="tgtSentence"> 如有必要，超级用户功能将在此时自动启用。</caps:sentence>
                <caps:sentence sentenceid="5e7a4edd8a45688746b57b47c13facfc" id="tgt115" class="tgtSentence"> 为了避免权限提升带来的安全风险，请注意仅指定你的组织的 Exchange 服务器使用的帐户。</caps:sentence>
                <caps:sentence sentenceid="89b8846d51dac31d9c31bcf4d31a7173" id="tgt116" class="tgtSentence"> 配置为 SharePoint 服务器的所有服务器或使用 FCI 的文件服务器将被授予常规用户权限。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="d05e949be91d74ff1fd012b56939f1db" id="tgt117" class="tgtSentence">你可以通过指定 Active Directory 安全或分发组，或由多台服务器使用的服务帐户，添加多个服务器作为单个条目。</caps:sentence>
                <caps:sentence sentenceid="700a748799136643f241bb185af329f0" id="tgt118" class="tgtSentence"> 当你使用此配置时，服务器组将共享相同的 RMS 证书，并且会被视为其中任何一个服务器保护的内容的所有者。</caps:sentence>
                <caps:sentence sentenceid="37f27ab8e26a1787691255d375aa011c" id="tgt119" class="tgtSentence"> 为了最大程度地减少管理开销，我们建议你使用这种单组配置，而不是使用单独服务器的配置，为组织的 Exchange 服务器或 SharePoint 服务器场授权。</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="87c942eae0180b2f79691fe9cf6c988f" id="tgt120" class="tgtSentence">在“被允许使用连接器的服务器”页上，单击“添加”<ui></ui><ui></ui>。</caps:sentence>
          </para>
        </content>
        <sections>
          <section address="BKMK_AddServer">
            <title>
              <caps:sentence sentenceid="14abea1c2bfc5791205ea144663cbd47" id="tgt121" class="tgtSentence">将服务器添加到允许服务器列表。</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="87c942eae0180b2f79691fe9cf6c988f" id="tgt122" class="tgtSentence">在“允许服务器使用连接器”页上，输入对象的名称，或进行浏览以确定要授权的对象<ui></ui>。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="a850f1ef21d283acc5f7437d3d4b1c21" id="tgt123" class="tgtSentence">必须为正确的对象授权，这一点非常重要。</caps:sentence>
                <caps:sentence sentenceid="bcd7cac37b32b3645578df87a01522d3" id="tgt124" class="tgtSentence"> 若要让服务器使用连接器，必须选择运行本地服务（例如 Exchange 或 SharePoint）的帐户来进行授权。</caps:sentence>
                <caps:sentence sentenceid="6e42100cbfb4b7483b579a291cec06fc" id="tgt125" class="tgtSentence"> 例如，如果服务作为配置的服务帐户运行，请将该服务帐户的名称添加到列表。</caps:sentence>
                <caps:sentence sentenceid="1ffc6906ab4dd3e65d5edfb969f21a3b" id="tgt126" class="tgtSentence"> 如果服务作为本地系统运行，请添加该计算机对象的名称（例如 SERVERNAME$）。</caps:sentence>
                <caps:sentence sentenceid="e7aeabf9f8d208053898aa5944c47dbc" id="tgt127" class="tgtSentence"> 最佳做法是创建一个包含这些帐户的组并指定该组，而不是指定单独的服务器名称。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="4e65b04de4a199b2dc7cf8cf59088377" id="tgt128" class="tgtSentence">有关不同服务器角色的详细信息：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="c36ed3bd2f47ee5610078f81000f550f" id="tgt129" class="tgtSentence">对于运行 Exchange 的服务器：必须指定一个安全组，并可使用 Exchange 自动创建和维护的包含林中所有 Exchange 服务器的默认组（“Exchange 服务器”）<ui></ui>。</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="431c88da3303d82a5d63d601d48f851a" id="tgt130" class="tgtSentence">对于运行 SharePoint 的服务器： </caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="9f7e007bd69bc299dda2a379909d1f42" id="tgt131" class="tgtSentence">如果 SharePoint 2010 服务器配置为作为本地系统（它不使用服务帐户）运行，请在 Active Directory 域服务中手动创建安全组，并将此配置中的服务器的计算机名称对象添加到此组。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="ab82a845c2c646f4f8112b80483b6758" id="tgt132" class="tgtSentence">如果 SharePoint 服务器配置为使用服务帐户（SharePoint 2010 的建议做法，并且是 SharePoint 2013 的唯一选项），请执行以下操作：</caps:sentence>
                      </para>
                      <list class="ordered">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="95dc43df1668336ffdc23440d6ca41ac" id="tgt133" class="tgtSentence">添加运行 SharePoint 管理中心服务的服务帐户，以便从管理员控制台配置 SharePoint。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="f83b6e14857e379b24024800fa080459" id="tgt134" class="tgtSentence">添加为 SharePoint 应用池配置的帐户。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <alert class="tip">
                        <para>
                          <caps:sentence sentenceid="35b8c2b7036dc41f31c9eedd41af2618" id="tgt135" class="tgtSentence">如果上述两个帐户是不同的，可考虑创建包含这两个帐户的单个组，以最大程度地降低管理开销。</caps:sentence>
                        </para>
                      </alert>
                    </listItem>
                  </list>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="7022e31bdb2b82cfc831936790b529bb" id="tgt136" class="tgtSentence">对于使用文件分类基础结构的文件服务器，相关服务作为本地系统帐户运行，因此你必须为文件服务器（例如 SERVERNAME$）的计算机帐户或包含这些计算机帐户的组授权。</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence sentenceid="ca12fcb347ae7a98476777536faa020a" id="tgt137" class="tgtSentence">在将服务器添加至列表之后，请单击“关闭”<ui></ui>。</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="8cd07aa9575e6ba1199e187d32afc8c0" id="tgt138" class="tgtSentence">如果尚未配置负载平衡，则现在必须为安装了 RMS 连接器的服务器配置负载平衡，并考虑是否使用 HTTPS 在这些服务器和你刚才授权的服务器之间进行连接。</caps:sentence>
              </para>
            </content>
          </section>
        </sections>
      </section>
      <section address="ConfiguringConnector">
        <title>
          <caps:sentence sentenceid="b9d3f87e64bd72d1b8a3af29fb98d785" id="tgt139" class="tgtSentence">配置负载平衡和高可用性</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="2fbe27422cd3fbb3544d351a72ce2e53" id="tgt140" class="tgtSentence">在你安装第二个或最后一个 RMS 连接器实例之后，请定义连接器 URL 服务器名称并配置负载平衡系统。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="8b676bf7ae0610785175239af6993c22" id="tgt141" class="tgtSentence">连接器 URL 服务器名称可以是你控制的命名空间中的任何名称。</caps:sentence>
            <caps:sentence sentenceid="3234547ad470d131db6e55dc2edd63d0" id="tgt142" class="tgtSentence"> 例如，你可在 DNS 系统中为 <userInput>rmsconnector.contoso.com</userInput> 创建一个条目，并将此条目配置为使用负载平衡系统中的 IP 地址。</caps:sentence>
            <caps:sentence sentenceid="d252bcebaf1e0a99853146377279ee89" id="tgt143" class="tgtSentence"> 此名称没有任何特殊要求，也无需在连接器服务器本身上进行配置。</caps:sentence>
            <caps:sentence sentenceid="ef70e1e93629262689c3e3309a7b6413" id="tgt144" class="tgtSentence"> 除非你的 Exchange 和 SharePoint 服务器要通过 Internet 与连接器通信，否则此名称无需在 Internet 上解析。</caps:sentence>
          </para>
          <alert class="important">
            <para>
              <caps:sentence sentenceid="f187618170083b0b2b19066488f93670" id="tgt145" class="tgtSentence">在将 Exchange 或 SharePoint 服务器配置为使用连接器之后，我们建议你不要更改该名称，因为你随后必须清除这些服务器的所有 IRM 配置，然后重新进行配置。</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence sentenceid="d6d0f1e53afffec21069db10e0ecbfec" id="tgt146" class="tgtSentence">在 DNS 中创建名称并配置 IP 地址之后，请配置该地址的负载平衡，将流量定向到连接器服务器。</caps:sentence>
            <caps:sentence sentenceid="d7305ec48e40b34f0eaa42ac26b92064" id="tgt147" class="tgtSentence"> 你可以使用任何基于 IP 的负载平衡器来达到此目的，该负载平衡器应包括 Windows Server 中的网络负载平衡 (NLB) 功能。</caps:sentence>
            <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt148" class="tgtSentence"> 有关详细信息，请参阅<externalLink><linkText>负载平衡部署指南</linkText><linkUri>http://technet.microsoft.com/library/cc754833(v=WS.10).aspx</linkUri></externalLink>。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="cf4fb16767518f48195ba3f946728caa" id="tgt149" class="tgtSentence">使用以下设置来配置 NLB 群集：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="feeb3797f0549991724a949eaa053b37" id="tgt150" class="tgtSentence">端口：80（对于 HTTP）或 443（对于 HTTPS）</caps:sentence>
              </para>
              <para>
                <caps:sentence sentenceid="1653c99d41f41e3f9ea479e95ad21ac4" id="tgt151" class="tgtSentence">有关如何使用 HTTP 或 HTTPS 的详细信息，请参阅下一部分。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="2cbe97607860ac168d6763b6802b2681" id="tgt152" class="tgtSentence">地缘组：无</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="fffbe5db38ffa671e782f9e55e4f980b" id="tgt153" class="tgtSentence">分发方法：等于</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="70b9ef85fcd69000856a2bca8a849588" id="tgt154" class="tgtSentence">为负载平衡的系统（为运行 RMS 连接器服务的服务器）定义的此名称是你稍后将本地服务器配置为使用 Azure RMS 时要使用的组织 RMS 连接器名称。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_ConfiguringHTTPS">
        <title>
          <caps:sentence sentenceid="77ec061e6df54b764ab96859bad97a9e" id="tgt155" class="tgtSentence">将 RMS 连接器配置为使用 HTTPS</caps:sentence>
        </title>
        <content>
          <alert class="note">
            <para>
              <caps:sentence sentenceid="adef3a240ea0ba176a4a53bff8d02540" id="tgt156" class="tgtSentence">此配置步骤是可选的，但建议执行此步骤以提高安全性。</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence sentenceid="805bf92503a1da709b7b4cc9706a3649" id="tgt157" class="tgtSentence">虽然使用 TLS 或 SSL 对于 RMS 连接器是可选的，但我们建议将其用于任何基于 HTTP 的安全敏感服务。</caps:sentence>
            <caps:sentence sentenceid="a2c93bde42fd8a2caea2f206df051119" id="tgt158" class="tgtSentence"> 在此配置中，运行连接器的服务器向使用连接器的 Exchange 和 SharePoint 服务器进行身份验证。</caps:sentence>
            <caps:sentence sentenceid="a40550bd88df79e22227e779d901419d" id="tgt159" class="tgtSentence"> 此外，从这些服务器向连接器发送的所有数据都进行了加密。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="182d8d028289f6f0f3cecc33d5a10dd0" id="tgt160" class="tgtSentence">若要让 RMS 连接器能够使用 TLS，请在运行 RMS 连接器的每个服务器上安装服务器身份验证证书，其中包含你将用于连接器的名称。</caps:sentence>
            <caps:sentence sentenceid="fc617969b1a217fd42479cceb563bd02" id="tgt161" class="tgtSentence"> 例如，如果你在 DNS 中定义的 RMS 连接器名称为 <system>rmsconnector.contoso.com</system>，请部署一个服务器身份验证证书，其中的证书使用者包含 <system>rmsconnector.contoso.com</system> 作为通用名称。</caps:sentence>
            <caps:sentence sentenceid="c6152d12661a75eaef3f4ec463aba688" id="tgt162" class="tgtSentence"> 也可以在证书备选名称中指定 <system>rmsconnector.contoso.com</system> 作为 DNS 值。</caps:sentence>
            <caps:sentence sentenceid="0820af866ffd98ce739ce6af617cdece" id="tgt163" class="tgtSentence"> 证书不一定必须包括服务器的名称。</caps:sentence>
            <caps:sentence sentenceid="d8a7921d1cc583ed1be4c2d4aea1c254" id="tgt164" class="tgtSentence"> 然后在 IIS 中，将此证书绑定到默认网站。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="7bfb369589d448d139ea2249a55ebc6f" id="tgt165" class="tgtSentence">如果你使用 HTTPS 选项，请确保运行连接器的所有服务器都具有有效的服务器身份验证证书，该证书链接到 Exchange 和 SharePoint 服务器信任的根 CA。</caps:sentence>
            <caps:sentence sentenceid="12b94bf1b90a5f1dfc699edb772ff2f2" id="tgt166" class="tgtSentence"> 此外，如果为连接器服务器颁发证书的证书颁发机构 (CA) 发布了证书吊销列表 (CRL)，则 Exchange 和 SharePoint 服务器必须能够下载此 CRL。</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence sentenceid="5e19cd30bbf23d0e8432875f7737ae18" id="tgt167" class="tgtSentence">你可以使用以下信息和资源，帮助请求和安装服务器身份验证证书，并将此证书绑定到 IIS 中的默认网站：</caps:sentence>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <caps:sentence sentenceid="b806d67763b33e943caf2576141ed412" id="tgt168" class="tgtSentence">如果使用 Active Directory 证书服务 (AD CS) 和企业证书颁发机构 (CA) 来部署这些服务器身份验证证书，则你可以复制和使用 Web 服务器证书模板。</caps:sentence>
                  <caps:sentence sentenceid="013085b0b42d20c932aba492fa3aa956" id="tgt169" class="tgtSentence"> 此证书模板使用“在请求中提供”作为证书使用者名称，这意味着在你请求证书时，可以提供 RMS 连接器名称的 FQDN 作为证书使用者名称或使用者备选名称<ui></ui>。</caps:sentence>
                </para>
              </listItem>
              <listItem>
                <para>
                  <caps:sentence sentenceid="6ff693df102d320dbcbaf74584cce73d" id="tgt170" class="tgtSentence">如果你使用独立 CA 或从其他公司购买此证书，请参阅 TechNet 上 <externalLink><linkText>Web Server (IIS)</linkText><linkUri>http://technet.microsoft.com/library/cc753433(v=ws.10).aspx</linkUri></externalLink> 文档库中的<externalLink><linkText>配置 Internet 服务器证书 (IIS 7)</linkText><linkUri>http://technet.microsoft.com/library/cc731977(v=ws.10).aspx</linkUri></externalLink>。</caps:sentence>
                </para>
              </listItem>
              <listItem>
                <para>
                  <caps:sentence sentenceid="ea3c18c6812e5c4578da6145289f355f" id="tgt171" class="tgtSentence">若要将 IIS 配置为使用证书，请参阅 TechNet 上 <externalLink><linkText>Web Server (IIS)</linkText><linkUri>http://technet.microsoft.com/library/cc753433(v=ws.10).aspx</linkUri></externalLink> 文档库中的<externalLink><linkText>添加网站绑定 (IIS 7)</linkText><linkUri>http://technet.microsoft.com/library/cc731692.aspx</linkUri></externalLink>。</caps:sentence>
                </para>
              </listItem>
            </list>
          </alert>
        </content>
      </section>
      <section address="BKMK_ConfiguringWebProxy">
        <title>
          <caps:sentence sentenceid="470350076c092a07e1efa445e9a8eaa0" id="tgt172" class="tgtSentence">为 Web 代理服务器配置 RMS 连接器</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="d4ca6ed64a55ee164b5a661ebd25aa9a" id="tgt173" class="tgtSentence">如果你的连接器服务器安装在没有直接 Internet 连接的网络中，需要手动配置出站 Internet 访问的 Web 代理服务器，则必须在 RMS 连接器的这些服务器上配置注册表。</caps:sentence>
          </para>
          <procedure>
            <title>
              <caps:sentence sentenceid="3a69bed528711f3a4a9cf4e546098566" id="tgt174" class="tgtSentence">将 RMS 连接器配置为使用 Web 代理服务器</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="c9a0088c5d7c5508f7af41b873246b66" id="tgt175" class="tgtSentence">在运行 RMS 连接器的每台服务器上，打开注册表编辑器，例如 Regedit。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="52a0a486115949d5009cfa2b41666228" id="tgt176" class="tgtSentence">导航至 <ui>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AADRM\Connector</ui></caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="cfe6c7e5de4ac45d09deeed107852ddf" id="tgt177" class="tgtSentence">添加 <ui>ProxyAddress</ui> 的字符串值，然后将此值的数据设置为 <ui>http://&lt;MyProxyDomainOrIPaddress&gt;:&lt;MyProxyPort&gt;</ui></caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="d05370276e06291b048268558cc39bee" id="tgt178" class="tgtSentence">例如：<userInput>http://proxyserver.contoso.com:8080</userInput></caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="a5444341c5554ac673a8d830e8e91b7c" id="tgt179" class="tgtSentence">关闭注册表编辑器，然后重新启动服务器，或者执行 IISReset 命令以重新启动 IIS。</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
          </procedure>
        </content>
      </section>
      <section address="BKMK_InstallingStandaloneTool">
        <title>
          <caps:sentence sentenceid="87b721e8df1d5b7207fd6e05c93a8c14" id="tgt180" class="tgtSentence">在管理计算机上安装 RMS 连接器管理工具</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="ea648935604210387d51ae1aca3e3567" id="tgt181" class="tgtSentence">可以在未安装 RMS 连接器的计算机上运行 RMS 连接器管理工具，前提是该计算机符合以下要求：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="965f4b130debf6c988269afef269e961" id="tgt182" class="tgtSentence">运行 Windows Server 2012 或 Windows Server 2012 R2（所有版本）、Windows Server 2008 R2 或 Windows Server 2008 R2 Service Pack 1（所有版本）、Windows 8.1、Windows 8 或 Windows 7 的物理或虚拟计算机。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="a184309d02204286057d805a56928206" id="tgt183" class="tgtSentence">至少 1 GB 的 RAM。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="0f6f15494b5fabde6354d833d11f8ad4" id="tgt184" class="tgtSentence">至少 64 GB 的磁盘空间。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="387bf14f59f185bf1b10187db81a5887" id="tgt185" class="tgtSentence">至少一个网络接口。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="606f0f7a808fd0972b0f1ed4e359c1a2" id="tgt186" class="tgtSentence">通过防火墙（或 Web 代理）访问 Internet。</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="ea4085a910b5e1a30d93625a6ffb9f22" id="tgt187" class="tgtSentence">若要安装 RMS 连接器管理工具，请运行以下文件：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="5a29c4564da1c8b825649b46aa338ef4" id="tgt188" class="tgtSentence">对于 32 位计算机：RMSConnectorAdminToolSetup_x86.exe</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="7debc5e80182b4f674dfcda627c792bb" id="tgt189" class="tgtSentence">对于 64 位计算机：RMSConnectorSetup.exe</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="e5fc65457f5284596b2fcbbf8887b240" id="tgt190" class="tgtSentence">如果你尚未下载这些文件，可从 <externalLink><linkText>Microsoft 下载中心</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=314106</linkUri></externalLink>下载。</caps:sentence>
          </para>
        </content>
      </section>
      <section address="ConfiguringServers">
        <title>
          <caps:sentence sentenceid="74f4aac82aa84ad266b8253a7bd81f84" id="tgt191" class="tgtSentence">将服务器配置为使用 RMS 连接器</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="4f5e120cbab68e245fac99819263bd21" id="tgt192" class="tgtSentence">安装并配置 RMS 连接器之后，即可将本地服务器配置为使用权限管理并通过连接器连接到 Azure RMS。</caps:sentence>
            <caps:sentence sentenceid="b500f1273e74b5dc1851fb98b7953408" id="tgt193" class="tgtSentence"> 这意味着需要配置以下服务器：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="75ab9f7302e3c0fd43bfe63aae6ed893" id="tgt194" class="tgtSentence">对于 Exchange 2013：客户端访问服务器和邮箱服务器</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="f9225d260844019a9000684099b2d221" id="tgt195" class="tgtSentence">对于 Exchange 2010：客户端访问服务器和中心传输服务器</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="d579234f8b0a3b253825bc5455efef5a" id="tgt196" class="tgtSentence">对于 SharePoint：前端 SharePoint Web 服务器，包括托管中心管理服务器的 Web 服务器</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="950a68f86e387e8fcf5f43b7cfbaf476" id="tgt197" class="tgtSentence">对于文件分类基础结构：装有文件资源管理器的 Windows Server 计算机</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="adcdbbeb59fae881c7bad2ca86f9685b" id="tgt198" class="tgtSentence">这种配置需要注册表设置。</caps:sentence>
            <caps:sentence sentenceid="ca7dd50b718b601f0cff4f1c16a1d4ac" id="tgt199" class="tgtSentence"> 执行此操作时，你有两个选项：</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="c56624f03735109b674157dbec3ee2c4" id="tgt200" class="tgtSentence">配置选项</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="faee742e2b3290f02a639a53e875a4a9" id="tgt201" class="tgtSentence">优点</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="eee807afe84fa8929a981009cda95720" id="tgt202" class="tgtSentence">缺点</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="a50e60770c165f10aec7ec16c6f2d17b" id="tgt203" class="tgtSentence">使用适用于 Microsoft RMS 连接器的服务器配置工具来自动配置</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="b2f440fca4b0f4e9d5f2ccfb0e9b9f6f" id="tgt204" class="tgtSentence">不直接编辑注册表。</caps:sentence>
                    <caps:sentence sentenceid="15edfe5b858de477a2e6df54e812b906" id="tgt205" class="tgtSentence"> 可以使用脚本进行自动编辑。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="50fffd7cff719fce9b20aa0d5c662d2a" id="tgt206" class="tgtSentence">无需运行 Windows PowerShell cmdlet 来获取你的 Microsoft RMS URL。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="1cb8a9c9852b509605bbac7684272a67" id="tgt207" class="tgtSentence">如果你本地运行工具，则自动为你检查必备组件（但不自动进行补救）。</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="6eae477a74fb6dcc19138c1c1df14eae" id="tgt208" class="tgtSentence">当你运行工具时，必须连接到已在运行 RMS 连接器的服务器。</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="b88e392ac6de32731a1af908b2386862" id="tgt209" class="tgtSentence">通过编辑注册表进行手动配置</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="4dae4c54dd8523538b9b1088d924b5c1" id="tgt210" class="tgtSentence">不需要连接到运行 RMS 连接器的服务器。</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="ea5dee735dc6be3a6c6dadbd062a1b93" id="tgt211" class="tgtSentence">更多管理开销，容易发生错误。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="4cf59648f7c34689179b98e2b78da6f9" id="tgt212" class="tgtSentence">你必须获取 Microsoft RMS URL，这需要你运行 Windows PowerShell 命令。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="ce1962c627f471b08268ec28c6abf85e" id="tgt213" class="tgtSentence">你必须始终自行进行所有必备组件检查。</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
          <para></para>
          <alert class="important">
            <para>
              <caps:sentence sentenceid="ed7c3e2f3b240bb253492a68010ea038" id="tgt214" class="tgtSentence">对于这两种情况，都必须手动安装所有必备组件，并将 Exchange、SharePoint 和文件分类基础结构配置为使用权限管理。</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence sentenceid="66c5ed030691ea50ef8dc9063dd00e68" id="tgt215" class="tgtSentence">对于大多数组织，使用适用于 Microsoft RMS 连接器的服务器配置工具进行自动配置是更好的选择，因为它提供优于手动配置的效率和可靠性。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="6bb95e0fe54658143777b991e5c45b8f" id="tgt216" class="tgtSentence">在这些服务器上进行配置更改之后，如果这些服务器正在运行 Exchange 或 SharePoint 并且以前配置为使用 AD RMS，则你必须重新启动它们。</caps:sentence>
            <caps:sentence sentenceid="9629643a0086c00faac4a3a8817026f5" id="tgt217" class="tgtSentence"> 在首次将它们配置为使用权限管理时，无需重新启动它们。</caps:sentence>
            <caps:sentence sentenceid="088dc00b3bb91ee0b9aa7d5a5a8933e4" id="tgt218" class="tgtSentence"> 进行这些配置更改后，始终必须重新启动配置为使用文件分类基础结构的文件服务器。</caps:sentence>
          </para>
          <procedure address="BKMK_HowToRunTheTool">
            <title>
              <caps:sentence sentenceid="474b37d2c4ee0a9d48d3a2eace0a33c9" id="tgt219" class="tgtSentence">如何使用适用于 Microsoft RMS 连接器的服务器配置工具</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="4cd85d335ea3adb7465f130a6c329533" id="tgt220" class="tgtSentence">如果你尚未下载适用于 Microsoft RMS 连接器的服务器配置工具的脚本 (GenConnectorConfig.ps1)，请从 <externalLink><linkText>Microsoft 下载中心</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=314106</linkUri></externalLink>下载。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="ee565b68fa3207a84aced68cf71478cb" id="tgt221" class="tgtSentence">将 GenConnectorConfig.ps1 文件保存在你要运行工具的计算机上。</caps:sentence>
                    <caps:sentence sentenceid="8fff5a18866da527b640bffa8a45179f" id="tgt222" class="tgtSentence"> 如果要在本地运行该工具，则此计算机必须是你想要配置为与 RMS 连接器通信的服务器。</caps:sentence>
                    <caps:sentence sentenceid="e982fc40fbc0d125d065b97b2040d601" id="tgt223" class="tgtSentence"> 否则，你可将文件保存在任何计算机上。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="fe3f6190c07c4210a6d38e17685afbb1" id="tgt224" class="tgtSentence">确定如何运行工具：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="541d9ea5c06c020da2e6f7412c2a5ca5" id="tgt225" class="tgtSentence">
                          <embeddedLabel>本地</embeddedLabel>：可以从要将配置为与 RMS 连接器通信的服务器以交互方式运行该工具。</caps:sentence>
                        <caps:sentence sentenceid="c4e32d98878c1032ff4fce8b6b74f656" id="tgt226" class="tgtSentence"> 这对于一次性配置（例如测试环境）非常有用。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="3551e53bd26b5127721e1325eba85f79" id="tgt227" class="tgtSentence">
                          <embeddedLabel>软件部署</embeddedLabel>：你可以运行工具以生成注册表文件，然后使用支持软件部署的系统管理应用程序（例如 System Center Configuration Manager），将这些注册表文件部署到一个或多个相关服务器。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="5bd26da783bcef74076c48270966baf7" id="tgt228" class="tgtSentence">
                          <embeddedLabel>组策略设置</embeddedLabel>：你可以运行工具以生成脚本，然后将脚本提供给管理员，管理员可为要配置的服务器创建组策略对象。</caps:sentence>
                        <caps:sentence sentenceid="15225b0d22073ce07aebf0b983350300" id="tgt229" class="tgtSentence"> 此脚本为要配置的每个服务器类型创建一个组策略对象，然后管理员能够将此对象分配给相关服务器。</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <alert class="note">
                    <para>
                      <caps:sentence sentenceid="1e18c8657b38c3e7f1d5d1d6aa500ad2" id="tgt230" class="tgtSentence">此工具可以配置将与 RMS 连接器通信并已在本部分开头列出的服务器。</caps:sentence>
                      <caps:sentence sentenceid="5d9ad58123246feee655ea75b7a7082a" id="tgt231" class="tgtSentence"> 不要在运行 RMS 连接器的服务器上运行此工具。</caps:sentence>
                    </para>
                  </alert>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="986a1e9cf69d28fc407425532bc33082" id="tgt232" class="tgtSentence">使用“以管理员身份运行”选项启动 Windows PowerShell，然后使用 Get-help 命令阅读有关如何将工具用于你选择的配置方法的说明<ui></ui>：</caps:sentence>
                  </para>
                  <code>Get-help .\GenConnectorConfig.ps1 -detailed</code>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence sentenceid="9f5cb11e117fee46e846fc7fbf2b967e" id="tgt233" class="tgtSentence">若要运行脚本，你必须输入组织的 RMS 连接器的 URL。</caps:sentence>
                  <caps:sentence sentenceid="ac313f03669a05284f565868408ee90f" id="tgt234" class="tgtSentence"> 输入协议前缀（HTTP:// 或 HTTPS://），以及你在 DNS 中为连接器的负载平衡地址定义的连接器名称，</caps:sentence>
                  <caps:sentence sentenceid="b51da18abcdaf8a72d8f62df4b62b8be" id="tgt235" class="tgtSentence"> 例如 https://connector.contoso.com。</caps:sentence>
                  <caps:sentence sentenceid="a44dd3bd6b0c624f84973ad942e7b081" id="tgt236" class="tgtSentence"> 然后，此工具会使用该 URL 来联系运行 RMS 连接器的服务器，并获取用于创建所需配置的其他参数。</caps:sentence>
                </para>
                <alert class="important">
                  <para>
                    <caps:sentence sentenceid="83796ae083ea77d8b72a0748d72a9f63" id="tgt237" class="tgtSentence">当你运行此工具时，请确保指定组织的负载平衡 RMS 连接器的名称，而不要指定运行 RMS 连接器服务的单个服务器的名称。</caps:sentence>
                  </para>
                </alert>
              </content>
            </conclusion>
          </procedure>
          <para>
            <caps:sentence sentenceid="5c008d1edcebe6c72c32bd7111662b81" id="tgt238" class="tgtSentence">使用以下部分获取每个服务类型的特定信息：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ExchangeServer">Configuring an Exchange server to use the connector</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ConfiguringSharePoint">Configuring a SharePoint server to use the connector</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_FileServer">Configuring a file server for File Classification Infrastructure to use the connector</link>
              </para>
            </listItem>
          </list>
          <alert class="note">
            <para>
              <caps:sentence sentenceid="2ca1797944d1696b53594317cc20252d" id="tgt239" class="tgtSentence">在将这些服务器配置为使用连接器之后，本地安装在这些服务器上的客户端应用程序可能无法使用 RMS。</caps:sentence>
              <caps:sentence sentenceid="bf8cef0d32a59188dd405114cda550a5" id="tgt240" class="tgtSentence"> 发生这种情况的原因是应用程序试图使用连接器而不是直接使用 RMS，但这种方式不受支持。</caps:sentence>
            </para>
            <para>
              <caps:sentence sentenceid="bbcb4953c0bcb16f2ed76e21ea8ac465" id="tgt241" class="tgtSentence">此外，如果 Office 2010 本地安装在 Exchange 服务器上，则在将服务器配置为使用连接器之后，客户端应用的 IRM 功能可能从该计算机运行，但这种方式不受支持。</caps:sentence>
            </para>
            <para>
              <caps:sentence sentenceid="8ac468a4b72bc2ffff2d8e7a8d691e5d" id="tgt242" class="tgtSentence">在上述两种情况下，你必须在没有配置为使用连接器的单独计算机上安装客户端应用程序。</caps:sentence>
              <caps:sentence sentenceid="2479c18c80624e6ebe088f2df8250317" id="tgt243" class="tgtSentence"> 然后它们即可正确地直接使用 RMS。</caps:sentence>
            </para>
          </alert>
        </content>
        <sections>
          <section address="BKMK_ExchangeServer">
            <title>
              <caps:sentence sentenceid="6f8902761cd662d41021c9b8ae5aeca2" id="tgt244" class="tgtSentence">将 Exchange 服务器配置为使用连接器</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="5da369a2abff2b68d2601cd47f9c7e7c" id="tgt245" class="tgtSentence">以下 Exchange 角色将与 RMS 连接器通信：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="2ae2efbcf3ff4a434659305e19c73bb9" id="tgt246" class="tgtSentence">对于 Exchange 2013：客户端访问服务器和邮箱服务器</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="627d3c1dbcce04e2da8e179f76b665e4" id="tgt247" class="tgtSentence">对于 Exchange 2010：客户端访问服务器和中心传输服务器</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence sentenceid="05314a8d540a6f8eae2186bef3d6251a" id="tgt248" class="tgtSentence">若要使用 RMS 连接器，这些运行 Exchange 的服务器必须运行以下软件版本之一：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="9fa293b4ba1a0a055d1542dc03958970" id="tgt249" class="tgtSentence">Exchange Server 2013，附带 Exchange 2013 累积更新 3</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="bc07df932ed238061e8bde54b636d371" id="tgt250" class="tgtSentence">Exchange Server 2010，附带 Exchange 2010 Service Pack 3 汇总更新 6</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence sentenceid="0a1b926c903022e1a9ee77402097cb83" id="tgt251" class="tgtSentence">你还需要在服务器上安装能够支持 RMS 加密模式 2 的 RMS 客户端版本。</caps:sentence>
                <caps:sentence sentenceid="d7354911a146d254dfc5a95b545aa942" id="tgt252" class="tgtSentence"> Windows Server 2008 支持的最低版本包括在修补程序中，你可从<externalLink><linkText>在 Windows Server 2008 R2 和 Windows Server 2008 中，AD RMS 的 RSA 密钥长度增加到 2048 位</linkText><linkUri>http://support.microsoft.com/kb/2627272</linkUri></externalLink>下载该修补程序。</caps:sentence>
                <caps:sentence sentenceid="f092a8c0c7ff427b36ec960c0d5cef84" id="tgt253" class="tgtSentence"> 适用于 Windows Server 2008 R2 的最低版本可从<externalLink><linkText>在 Windows 7 或 Windows Server 2008 R2 中，AD RMS 的 RSA 密钥长度增加到 2048 位</linkText><linkUri>http://support.microsoft.com/kb/2627273</linkUri></externalLink>下载。</caps:sentence>
                <caps:sentence sentenceid="3f2d9f3e1d7e9f51e73e65c4f9a0d210" id="tgt254" class="tgtSentence"> Windows Server 2012 和 Windows Server 2012 R2 以本机方式支持加密模式 2。</caps:sentence>
              </para>
              <alert class="important">
                <para>
                  <caps:sentence sentenceid="65fd65b2af65ebacf47f03d8dda514a5" id="tgt255" class="tgtSentence">如果没有安装这些版本或更高版本的 Exchange 和 RMS 客户端，你就无法将 Exchange 配置为使用连接器。</caps:sentence>
                  <caps:sentence sentenceid="6a79deab0bab16e8b1e7ce2437da8b32" id="tgt256" class="tgtSentence"> 继续之前，请确认已安装这些版本。</caps:sentence>
                </para>
              </alert>
              <procedure>
                <title>
                  <caps:sentence sentenceid="8b571dab8bec8ac749efaa1bd3cddad8" id="tgt257" class="tgtSentence">将 Exchange 服务器配置为使用连接器</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="f4dcf06a3c6c76ed81983602e69a932e" id="tgt258" class="tgtSentence">在与 RMS 连接器通信的 Exchange 服务器角色上执行以下任一操作：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="063549edfc9dd655691728ca4f9f28e9" id="tgt259" class="tgtSentence">运行适用于 Microsoft RMS 连接器的服务器配置工具。</caps:sentence>
                            <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt260" class="tgtSentence"> 有关详细信息，请参阅本主题中的<link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_HowToRunTheTool">How to use the server configuration tool for Microsoft RMS connector</link>。</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence sentenceid="8a5ed0273d0042b026cc052fe80af2b1" id="tgt261" class="tgtSentence">例如，若要在本地运行该工具以配置运行 Exchange 2013 的服务器，请执行以下操作： </caps:sentence>
                          </para>
                          <code>.\GenConnectorConfig.ps1 -ConnectorUri https://rmsconnector.contoso.com -SetExchange2013</code>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="3eb38313fcab30a4abdb15491967954c" id="tgt262" class="tgtSentence">使用以下部分的表格，在服务器上手动添加注册表设置，进行手动注册表编辑。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="b9b1843ed74ab2eab43cda358047a376" id="tgt263" class="tgtSentence">在 Exchange 中启用 IRM 功能。</caps:sentence>
                        <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt264" class="tgtSentence"> 有关详细信息，请参阅 Exchange 库中的<externalLink><linkText>信息权限管理过程</linkText><linkUri>https://technet.microsoft.com/library/dd351212(v=exchg.150).aspx</linkUri></externalLink>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
              <para>
                <caps:sentence sentenceid="524e639c5fc8e9152b93f6e835c9acd9" id="tgt265" class="tgtSentence">只有当你需要在服务器上手动添加或检查将这些服务器配置为使用 RMS 连接器的注册表设置时，才使用以下部分的表格。</caps:sentence>
                <caps:sentence sentenceid="516b17f9c3f5d0db4a96a4e8c632613c" id="tgt266" class="tgtSentence"> 有关何时使用这些表格的说明：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="53fa3f5e0f111dc66718fdc1136c3e56" id="tgt267" class="tgtSentence">
                      <placeholder>MicrosoftRMSURL</placeholder> 是你组织的 Microsoft RMS 服务 URL。</caps:sentence>
                    <caps:sentence sentenceid="347410f9de63594a5a8baf48a20f257c" id="tgt268" class="tgtSentence"> 查找此值：</caps:sentence>
                  </para>
                  <list class="ordered">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="3a3aa7b24413b30b9af6fcd3f9f9f652" id="tgt269" class="tgtSentence">对 Azure RMS 运行 <externalLink><linkText>Get-AadrmConfiguration</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629410.aspx</linkUri></externalLink> cmdlet。</caps:sentence>
                        <caps:sentence sentenceid="392df028cf931bb6a18776d3a688dda0" id="tgt270" class="tgtSentence"> 如果你尚未安装适用于 Azure RMS 的 Windows PowerShell 模块，请参阅<link xlink:href="0d665ed6-b1de-4d63-854a-bc57c1c49844">Installing Windows PowerShell for Azure Rights Management</link>。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="ae3e3733f4fd83ce1d71232828624cb0" id="tgt271" class="tgtSentence">在输出中找到 <ui>LicensingIntranetDistributionPointUrl</ui> 值。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="d05370276e06291b048268558cc39bee" id="tgt272" class="tgtSentence">例如：<ui>LicensingIntranetDistributionPointUrl   : https://5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com/_wmcs/licensing</ui></caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="329dda22837a719a5a3008628608d0cc" id="tgt273" class="tgtSentence">该值中，将 <ui>/_wmcs/licensing</ui> 从此字符串删除。</caps:sentence>
                        <caps:sentence sentenceid="ea79174a667e4ce268e4422bd74aff5a" id="tgt274" class="tgtSentence"> 剩余字符串就是你的 Microsoft RMS URL。</caps:sentence>
                        <caps:sentence sentenceid="4ec4e88e5c682c0bd6034bfc49168c70" id="tgt275" class="tgtSentence"> 在我们的示例中，Microsoft RMS URL 应为以下值：</caps:sentence>
                      </para>
                      <para>
                        <ui>
                          <caps:sentence sentenceid="3a510940ac5f0bf0d12f8307afb8c7aa" id="tgt276" class="tgtSentence">https://5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com</caps:sentence>
                        </ui>
                      </para>
                    </listItem>
                  </list>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="040c27cf3069e277567eec1f0b7c9ab4" id="tgt277" class="tgtSentence">
                      <placeholder>ConnectorFQDN</placeholder> 是你在 DNS 中为连接器定义的负载平衡名称。</caps:sentence>
                    <caps:sentence sentenceid="4eee3758f1bf4073d94deae936dd0a13" id="tgt278" class="tgtSentence"> 例如 <system>rmsconnector.contoso.com</system>。</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="ed69df32fb51528c4623b7b5da5828fa" id="tgt279" class="tgtSentence">如果你已将连接器配置为使用 HTTPS 与本地服务器通信，请使用 HTTPS 前缀作为连接器 URL。</caps:sentence>
                    <caps:sentence sentenceid="be021ab36c2c99a549fc25f5fcee238c" id="tgt280" class="tgtSentence"> 有关详细信息，请参阅本主题中的<link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ConfiguringHTTPS">Configuring the RMS connector to use HTTPS</link>部分。</caps:sentence>
                    <caps:sentence sentenceid="378cbd311a843a7701e45a31ba958471" id="tgt281" class="tgtSentence"> Microsoft RMS URL 始终使用 HTTPS。</caps:sentence>
                  </para>
                </listItem>
              </list>
            </content>
            <sections>
              <section expanded="false">
                <title>
                  <caps:sentence sentenceid="7f14ce57459fb0db4b6eada5724c32dc" id="tgt282" class="tgtSentence">Exchange 2013 注册表设置表</caps:sentence>
                </title>
                <content>
                  <table>
                    <thead>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="b75ba2542571d3ceaab9c5d83c92075c" id="tgt283" class="tgtSentence">注册表路径</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="599dcce2998a6b40b1e38e8c6006cb0a" id="tgt284" class="tgtSentence">类型</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2063c1608d6e0baf80249c42e2be5804" id="tgt285" class="tgtSentence">值</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="8d777f385d3dfec8815d20f7496026dc" id="tgt286" class="tgtSentence">数据</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="40d2921628d72e2b9fe991a68c260ea7" id="tgt287" class="tgtSentence">HKEY_LOCAL_MACHINE\Software\Microsoft\MSDRM\ServiceLocation\Activation</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt288" class="tgtSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="c21f969b5f03d33d43e04f8f136e7682" id="tgt289" class="tgtSentence">默认</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="f8eae6750519389e078e1eb1bcb3d708" id="tgt290" class="tgtSentence">https://<placeholder>MicrosoftRMSURL/_wmcs/certification</placeholder></caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="1968469740d260461985dbaee69c890d" id="tgt291" class="tgtSentence">HKEY_LOCAL_MACHINE\Software\Microsoft\MSDRM\ServiceLocation\EnterprisePublishing</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt292" class="tgtSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="c21f969b5f03d33d43e04f8f136e7682" id="tgt293" class="tgtSentence">默认</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="a08eea8e5273aedda6feb796d49d643b" id="tgt294" class="tgtSentence">https://MicrosoftRMSURL/_wmcs/Licensing</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="b422ee7b9c081ec95e5c95d5a9e6f2dc" id="tgt295" class="tgtSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExchangeServer\v15\IRM\CertificationServerRedirection</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt296" class="tgtSentence">Reg_SZ</caps:sentence>
                          </para>
                          <para></para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="f8eae6750519389e078e1eb1bcb3d708" id="tgt297" class="tgtSentence">https://<placeholder>MicrosoftRMSURL</placeholder></caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="5e9f115816f9a71685775cd8d7bf469f" id="tgt298" class="tgtSentence">以下前缀之一，具体取决于 Exchange 服务器与 RMS 连接器之间的连接是使用 HTTP 还是 HTTPS：</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="dbd7790bcd23fde7607101ef6a633779" id="tgt299" class="tgtSentence">http://<placeholder>ConnectorFQDN</placeholder></caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="f8eae6750519389e078e1eb1bcb3d708" id="tgt300" class="tgtSentence">https://<placeholder>ConnectorFQDN</placeholder></caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="8d386fa8e79b481db738381489bcf29b" id="tgt301" class="tgtSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExchangeServer\v15\IRM\LicenseServerRedirection</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt302" class="tgtSentence">Reg_SZ</caps:sentence>
                          </para>
                          <para></para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="f8eae6750519389e078e1eb1bcb3d708" id="tgt303" class="tgtSentence">https://<placeholder>MicrosoftRMSURL</placeholder></caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="5e9f115816f9a71685775cd8d7bf469f" id="tgt304" class="tgtSentence">以下前缀之一，具体取决于 Exchange 服务器与 RMS 连接器之间的连接是使用 HTTP 还是 HTTPS：</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="dbd7790bcd23fde7607101ef6a633779" id="tgt305" class="tgtSentence">http://<placeholder>ConnectorFQDN</placeholder></caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="f8eae6750519389e078e1eb1bcb3d708" id="tgt306" class="tgtSentence">https://<placeholder>ConnectorFQDN</placeholder></caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </TD>
                      </tr>
                    </tbody>
                  </table>
                </content>
              </section>
              <section expanded="false">
                <title>
                  <caps:sentence sentenceid="a5476942e0ac240a59f25d5be535b72d" id="tgt307" class="tgtSentence">Exchange 2010 注册表设置表</caps:sentence>
                </title>
                <content>
                  <table>
                    <thead>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="b75ba2542571d3ceaab9c5d83c92075c" id="tgt308" class="tgtSentence">注册表路径</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="599dcce2998a6b40b1e38e8c6006cb0a" id="tgt309" class="tgtSentence">类型</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2063c1608d6e0baf80249c42e2be5804" id="tgt310" class="tgtSentence">值</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="8d777f385d3dfec8815d20f7496026dc" id="tgt311" class="tgtSentence">数据</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="40d2921628d72e2b9fe991a68c260ea7" id="tgt312" class="tgtSentence">HKEY_LOCAL_MACHINE\Software\Microsoft\MSDRM\ServiceLocation\Activation</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt313" class="tgtSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="c21f969b5f03d33d43e04f8f136e7682" id="tgt314" class="tgtSentence">默认</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="f8eae6750519389e078e1eb1bcb3d708" id="tgt315" class="tgtSentence">https://<placeholder>MicrosoftRMSURL</placeholder>/_wmcs/certification</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="1968469740d260461985dbaee69c890d" id="tgt316" class="tgtSentence">HKEY_LOCAL_MACHINE\Software\Microsoft\MSDRM\ServiceLocation\EnterprisePublishing</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt317" class="tgtSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="c21f969b5f03d33d43e04f8f136e7682" id="tgt318" class="tgtSentence">默认</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="f8eae6750519389e078e1eb1bcb3d708" id="tgt319" class="tgtSentence">https://<placeholder>MicrosoftRMSURL</placeholder>/_wmcs/Licensing</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="f79261c614e5a42a2b495720d2e71d27" id="tgt320" class="tgtSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExchangeServer\v14\IRM\CertificationServerRedirection</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt321" class="tgtSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="f8eae6750519389e078e1eb1bcb3d708" id="tgt322" class="tgtSentence">https://<placeholder>MicrosoftRMSURL</placeholder></caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="5e9f115816f9a71685775cd8d7bf469f" id="tgt323" class="tgtSentence">以下前缀之一，具体取决于 Exchange 服务器与 RMS 连接器之间的连接是使用 HTTP 还是 HTTPS：</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="dbd7790bcd23fde7607101ef6a633779" id="tgt324" class="tgtSentence">http://<placeholder>ConnectorFQDN</placeholder></caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="f8eae6750519389e078e1eb1bcb3d708" id="tgt325" class="tgtSentence">https://<placeholder>ConnectorFQDN</placeholder></caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="9ef008b28f9abb5f0c22fcbe9cf20585" id="tgt326" class="tgtSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExchangeServer\v14\IRM\LicenseServerRedirection</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt327" class="tgtSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="f8eae6750519389e078e1eb1bcb3d708" id="tgt328" class="tgtSentence">https://<placeholder>MicrosoftRMSURL</placeholder></caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="5e9f115816f9a71685775cd8d7bf469f" id="tgt329" class="tgtSentence">以下前缀之一，具体取决于 Exchange 服务器与 RMS 连接器之间的连接是使用 HTTP 还是 HTTPS：</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="dbd7790bcd23fde7607101ef6a633779" id="tgt330" class="tgtSentence">http://<placeholder>ConnectorFQDN</placeholder></caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="f8eae6750519389e078e1eb1bcb3d708" id="tgt331" class="tgtSentence">https://<placeholder>ConnectorFQDN</placeholder></caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </TD>
                      </tr>
                    </tbody>
                  </table>
                </content>
              </section>
            </sections>
          </section>
          <section address="BKMK_ConfiguringSharePoint">
            <title>
              <caps:sentence sentenceid="cc0d9be880f5ebbe982fd3ac32404743" id="tgt332" class="tgtSentence">将 SharePoint 服务器配置为使用连接器</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="cea9638235b316274203c972b038fab5" id="tgt333" class="tgtSentence">以下 SharePoint 角色将与 RMS 连接器通信：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="d6c3aca227e10a02fc3d1aa88a01e6a9" id="tgt334" class="tgtSentence">前端 SharePoint Web 服务器，包括托管中心管理服务器的 Web 服务器</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence sentenceid="cb8a5db9648789f4fb37fda863c033c5" id="tgt335" class="tgtSentence">若要使用 RMS 连接器，这些运行 SharePoint 的服务器必须运行以下软件版本之一：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="b279dfbc63630c1d69db32965313e462" id="tgt336" class="tgtSentence">SharePoint Server 2013</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="963b0beeac78c2c2122cf389c55f7ec1" id="tgt337" class="tgtSentence">SharePoint Server 2010</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence sentenceid="a9e013ed7de6efef4e3d102904a5e4e0" id="tgt338" class="tgtSentence">SharePoint 2013 服务器也必须运行版本从 1.0.622.34 到 1.0.10907.0 的 MSIPC 客户端 2.1。</caps:sentence>
              </para>
              <alert class="warning">
                <para>
                  <caps:sentence sentenceid="25ae79362814d278ed6f5cbdcccbac69" id="tgt339" class="tgtSentence">有多个版本的 MSIPC 2.1 客户端，因此请务必安装本文提及的版本。</caps:sentence> </para>
                <para>
                  <caps:sentence sentenceid="f411832ad3a1f54800f1242c6e8dcb8e" id="tgt340" class="tgtSentence">你可以通过检查位于 <system>\Program Files\Active Directory Rights Management Services Client 2.1</system> 中的 MSIPC.dll 的版本号来验证客户端版本。</caps:sentence>
                  <caps:sentence sentenceid="87e687dd6042ff2e467b47091a1a1d53" id="tgt341" class="tgtSentence"> 属性对话框将显示 MSIPC 2.1 客户端的版本号。</caps:sentence>
                </para>
              </alert>
              <para>
                <caps:sentence sentenceid="8b7e3605c6f2fb41922db9309700ff18" id="tgt342" class="tgtSentence">这些运行 SharePoint 2010 的服务器必须安装了能够支持 RMS 加密模式 2 的 MSDRM 客户端版本。</caps:sentence>
                <caps:sentence sentenceid="d7354911a146d254dfc5a95b545aa942" id="tgt343" class="tgtSentence"> Windows Server 2008 支持的最低版本包括在修补程序中，你可从<externalLink><linkText>在 Windows Server 2008 R2 和 Windows Server 2008 中，AD RMS 的 RSA 密钥长度增加到 2048 位</linkText><linkUri>http://support.microsoft.com/kb/2627272</linkUri></externalLink>下载该修补程序。适用于 Windows Server 2008 R2 的最低版本可从<externalLink><linkText>在 Windows 7 或 Windows Server 2008 R2 中，AD RMS 的 RSA 密钥长度增加到 2048 位</linkText><linkUri>http://support.microsoft.com/kb/2627273</linkUri></externalLink>下载。</caps:sentence>
                <caps:sentence sentenceid="ca0e04e3a450fd1994299cee720d7cfb" id="tgt344" class="tgtSentence"> Windows Server 2012 和 Windows Server 2012 R2 以本机方式支持加密模式 2。</caps:sentence>
              </para>
              <procedure>
                <title>
                  <caps:sentence sentenceid="d6a6383b8a793c65494de2da699d3d6e" id="tgt345" class="tgtSentence">将 SharePoint 服务器配置为使用连接器</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="a9fcd74e91355864b4f13b22ef032165" id="tgt346" class="tgtSentence">在与 RMS 连接器通信的 SharePoint 服务器上执行以下任一操作：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="063549edfc9dd655691728ca4f9f28e9" id="tgt347" class="tgtSentence">运行适用于 Microsoft RMS 连接器的服务器配置工具。</caps:sentence>
                            <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt348" class="tgtSentence"> 有关详细信息，请参阅本主题中的<link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_HowToRunTheTool">How to use the server configuration tool for Microsoft RMS connector</link>。</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence sentenceid="024cff3c470c7498cb937bce12c87d1d" id="tgt349" class="tgtSentence">例如，若要在本地运行该工具以配置运行 SharePoint 2013 的服务器，请执行以下操作： </caps:sentence>
                          </para>
                          <code>.\GenConnectorConfig.ps1 -ConnectorUri https://rmsconnector.contoso.com -SetSharePoint2013</code>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="3704a9924c4759d4255e5f4dff866022" id="tgt350" class="tgtSentence">如果你使用 SharePoint 2013，请使用以下部分的表格，在服务器上手动添加注册表设置，进行手动注册表编辑。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="0b0b9fde661d43480a1c57bc0412e139" id="tgt351" class="tgtSentence">在 SharePoint 中启用 IRM。</caps:sentence>
                        <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt352" class="tgtSentence"> 有关详细信息，请参阅 SharePoint 库中的<externalLink><linkText>配置信息权限管理 (SharePoint Server 2010)</linkText><linkUri>https://technet.microsoft.com/library/hh545607(v=office.14).aspx</linkUri></externalLink>。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="76fb7604be6ef8a21950f3c84fd52bb2" id="tgt353" class="tgtSentence">当你按照这些说明操作时，必须通过指定<ui>“使用此 RMS 服务器”</ui>，将 SharePoint 配置为使用连接器，然后输入你配置的负载平衡连接器 URL。</caps:sentence>
                        <caps:sentence sentenceid="ac313f03669a05284f565868408ee90f" id="tgt354" class="tgtSentence"> 输入协议前缀（HTTP:// 或 HTTPS://），以及你在 DNS 中为连接器的负载平衡地址定义的连接器名称，</caps:sentence>
                        <caps:sentence sentenceid="a7d443ddbdbaf838a2631c13130b3d4a" id="tgt355" class="tgtSentence"> 例如，如果你的连接器名称为 https://connector.contoso.com，则配置将如下图所示：</caps:sentence>
                      </para>
                      <para>
                        <mediaLinkInline>
                          <image xlink:href="82377fdd-0c4b-4c2a-8c52-4d19e19f2cda"></image>
                        </mediaLinkInline>
                      </para>
                      <para>
                        <caps:sentence sentenceid="938938a19c5a5a838bd3e6be2afc0180" id="tgt356" class="tgtSentence">在 SharePoint 场上启用 IRM 之后，你可以使用每个库的<ui>“库设置”</ui>页上的<ui>“信息权限管理”</ui>选项，在各个库上启用 IRM。</caps:sentence>
                      </para>
                      <alert class="important">
                        <para>
                          <caps:sentence sentenceid="6e0770cc88b0a99bf07a6f875450ae20" id="tgt357" class="tgtSentence">要让 SharePoint 使用连接器访问 RMS，你必须在 RMS 连接器管理工具中向相应的帐户授权。</caps:sentence>
                          <caps:sentence sentenceid="388659ba0d628f64135b93d94856d5e7" id="tgt358" class="tgtSentence"> 如果你尚未执行此操作，请参阅本主题中的<link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#AuthorizingServers">Authorizing servers to use the RMS connector</link>。</caps:sentence>
                        </para>
                      </alert>
                    </content>
                  </step>
                </steps>
              </procedure>
              <para>
                <caps:sentence sentenceid="915fd880a282872dd1e24a7f995bce88" id="tgt359" class="tgtSentence">只有当你需要在运行 SharePoint 2013 的服务器上手动添加或检查注册表设置时，才使用以下部分的表格。</caps:sentence>
              </para>
            </content>
            <sections>
              <section expanded="false">
                <title>
                  <caps:sentence sentenceid="a1105de718ad7416b50ad14db063cc9d" id="tgt360" class="tgtSentence">SharePoint 2013 注册表设置表</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence sentenceid="914b52489db7031497ab4b2c5cf60a6e" id="tgt361" class="tgtSentence">有关何时使用此表格的说明：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="53fa3f5e0f111dc66718fdc1136c3e56" id="tgt362" class="tgtSentence">
                          <placeholder>MicrosoftRMSURL</placeholder> 是你组织的 Microsoft RMS 服务 URL。</caps:sentence>
                        <caps:sentence sentenceid="347410f9de63594a5a8baf48a20f257c" id="tgt363" class="tgtSentence"> 查找此值：</caps:sentence>
                      </para>
                      <list class="ordered">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="3a3aa7b24413b30b9af6fcd3f9f9f652" id="tgt364" class="tgtSentence">对 Azure RMS 运行 <externalLink><linkText>Get-AadrmConfiguration</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629410.aspx</linkUri></externalLink> cmdlet。</caps:sentence>
                            <caps:sentence sentenceid="392df028cf931bb6a18776d3a688dda0" id="tgt365" class="tgtSentence"> 如果你尚未安装适用于 Azure RMS 的 Windows PowerShell 模块，请参阅<link xlink:href="0d665ed6-b1de-4d63-854a-bc57c1c49844">Installing Windows PowerShell for Azure Rights Management</link>。</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="ae3e3733f4fd83ce1d71232828624cb0" id="tgt366" class="tgtSentence">在输出中找到 <ui>LicensingIntranetDistributionPointUrl</ui> 值。</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence sentenceid="d05370276e06291b048268558cc39bee" id="tgt367" class="tgtSentence">例如：<ui>LicensingIntranetDistributionPointUrl   : https://5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com/_wmcs/licensing</ui></caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="329dda22837a719a5a3008628608d0cc" id="tgt368" class="tgtSentence">该值中，将 <ui>/_wmcs/licensing</ui> 从此字符串删除。</caps:sentence>
                            <caps:sentence sentenceid="ea79174a667e4ce268e4422bd74aff5a" id="tgt369" class="tgtSentence"> 剩余字符串就是你的 Microsoft RMS URL。</caps:sentence>
                            <caps:sentence sentenceid="4ec4e88e5c682c0bd6034bfc49168c70" id="tgt370" class="tgtSentence"> 在我们的示例中，Microsoft RMS URL 应为以下值：</caps:sentence>
                          </para>
                          <para>
                            <ui>
                              <caps:sentence sentenceid="3a510940ac5f0bf0d12f8307afb8c7aa" id="tgt371" class="tgtSentence">https://5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com</caps:sentence>
                            </ui>
                          </para>
                        </listItem>
                      </list>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="040c27cf3069e277567eec1f0b7c9ab4" id="tgt372" class="tgtSentence">
                          <placeholder>ConnectorFQDN</placeholder> 是你在 DNS 中为连接器定义的负载平衡名称。</caps:sentence>
                        <caps:sentence sentenceid="4eee3758f1bf4073d94deae936dd0a13" id="tgt373" class="tgtSentence"> 例如 <system>rmsconnector.contoso.com</system>。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="ed69df32fb51528c4623b7b5da5828fa" id="tgt374" class="tgtSentence">如果你已将连接器配置为使用 HTTPS 与本地服务器通信，请使用 HTTPS 前缀作为连接器 URL。</caps:sentence>
                        <caps:sentence sentenceid="be021ab36c2c99a549fc25f5fcee238c" id="tgt375" class="tgtSentence"> 有关详细信息，请参阅本主题中的<link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ConfiguringHTTPS">Configuring the RMS connector to use HTTPS</link>部分。</caps:sentence>
                        <caps:sentence sentenceid="378cbd311a843a7701e45a31ba958471" id="tgt376" class="tgtSentence"> Microsoft RMS URL 始终使用 HTTPS。</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <table>
                    <thead>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="32dc846aee8a4677c0e887c786acaa73" id="tgt377" class="tgtSentence">注册表路径 </caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="599dcce2998a6b40b1e38e8c6006cb0a" id="tgt378" class="tgtSentence">类型</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2063c1608d6e0baf80249c42e2be5804" id="tgt379" class="tgtSentence">值</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="8d777f385d3dfec8815d20f7496026dc" id="tgt380" class="tgtSentence">数据</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="a44f68e8dc7b33eda05152583ca8308f" id="tgt381" class="tgtSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\LicensingRedirection</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt382" class="tgtSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="f8eae6750519389e078e1eb1bcb3d708" id="tgt383" class="tgtSentence">https://<placeholder>MicrosoftRMSURL</placeholder>/_wmcs/licensing</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="d96648669089faf8782c0fec974c48ad" id="tgt384" class="tgtSentence">以下前缀之一，具体取决于 SharePoint 服务器与 RMS 连接器之间的连接是使用 HTTP 还是 HTTPS：</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="dbd7790bcd23fde7607101ef6a633779" id="tgt385" class="tgtSentence">http://<placeholder>ConnectorFQDN</placeholder>/_wmcs/licensing</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="f8eae6750519389e078e1eb1bcb3d708" id="tgt386" class="tgtSentence">https://<placeholder>ConnectorFQDN</placeholder>/_wmcs/licensing</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="cfdaee60a3037aee34d42b496f4e4488" id="tgt387" class="tgtSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\EnterpriseCertification</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt388" class="tgtSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="c21f969b5f03d33d43e04f8f136e7682" id="tgt389" class="tgtSentence">默认</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="d96648669089faf8782c0fec974c48ad" id="tgt390" class="tgtSentence">以下前缀之一，具体取决于 SharePoint 服务器与 RMS 连接器之间的连接是使用 HTTP 还是 HTTPS：</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="dbd7790bcd23fde7607101ef6a633779" id="tgt391" class="tgtSentence">http://<placeholder>ConnectorFQDN</placeholder>/_wmcs/certification</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="f8eae6750519389e078e1eb1bcb3d708" id="tgt392" class="tgtSentence">https://<placeholder>ConnectorFQDN</placeholder>/_wmcs/certification</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="06d797cfd9dc4c2730156b866a454d0f" id="tgt393" class="tgtSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\EnterprisePublishing</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt394" class="tgtSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="c21f969b5f03d33d43e04f8f136e7682" id="tgt395" class="tgtSentence">默认</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="d96648669089faf8782c0fec974c48ad" id="tgt396" class="tgtSentence">以下前缀之一，具体取决于 SharePoint 服务器与 RMS 连接器之间的连接是使用 HTTP 还是 HTTPS：</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="dbd7790bcd23fde7607101ef6a633779" id="tgt397" class="tgtSentence">http://<placeholder>ConnectorFQDN</placeholder>/_wmcs/licensing</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence sentenceid="f8eae6750519389e078e1eb1bcb3d708" id="tgt398" class="tgtSentence">https://<placeholder>ConnectorFQDN</placeholder>/_wmcs/licensing</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </TD>
                      </tr>
                    </tbody>
                  </table>
                </content>
              </section>
            </sections>
          </section>
          <section address="BKMK_FileServer">
            <title>
              <caps:sentence sentenceid="da15d1a07d45de43331d9a9b899aeba1" id="tgt399" class="tgtSentence">将文件分类基础结构的文件服务器配置为使用连接器</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="73f163f0548a4e4810890ff693d22a30" id="tgt400" class="tgtSentence">若要使用 RMS 连接器和文件分类基础结构来保护 Office 文档，文件服务器必须运行以下操作系统之一：</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence sentenceid="dcfe8446422dcac28d99767b484594f0" id="tgt401" class="tgtSentence">Windows Server 2012 R2</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence sentenceid="0e22230e53d6559d213afe9ce343ebf5" id="tgt402" class="tgtSentence">Windows Server 2012</caps:sentence>
                  </para>
                </listItem>
              </list>
              <procedure>
                <title>
                  <caps:sentence sentenceid="366dcca03e45a4f70f1def3ecb1aa0e0" id="tgt403" class="tgtSentence">将文件服务器配置为使用连接器</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="3fe6334b98b13756f6ce7dcdb25927ff" id="tgt404" class="tgtSentence">在为文件分类基础结构配置的、将与 RMS 连接器通信的文件服务器上执行以下任一操作：</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="063549edfc9dd655691728ca4f9f28e9" id="tgt405" class="tgtSentence">运行适用于 Microsoft RMS 连接器的服务器配置工具。</caps:sentence>
                            <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt406" class="tgtSentence"> 有关详细信息，请参阅本主题中的<link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_HowToRunTheTool">How to use the server configuration tool for Microsoft RMS connector</link>。</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence sentenceid="228fd625c9dc383aca7012be0be433de" id="tgt407" class="tgtSentence">例如，若要在本地运行该工具以配置运行 FCI 的文件服务器，请执行以下操作： </caps:sentence>
                          </para>
                          <code>.\GenConnectorConfig.ps1 -ConnectorUri https://rmsconnector.contoso.com -SetFCI2012</code>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence sentenceid="71bc7c940032c6a7815b73d7b8635478" id="tgt408" class="tgtSentence">使用以下部分的表格，在服务器上手动添加注册表设置，进行手动注册表编辑。</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence sentenceid="99100e6b2e2f49c27506c24706afc879" id="tgt409" class="tgtSentence">创建分类规则和文件管理任务，才能使用 RMS 加密保护文档，然后指定一个用于自动将 RMS 策略的应用的 RMS 模板。</caps:sentence>
                        <caps:sentence sentenceid="1070f425823a6e05a98eb2d747f0c53d" id="tgt410" class="tgtSentence"> 有关详细信息，请参阅 Windows Server 文档库中的<externalLink><linkText>文件服务器资源管理器概述</linkText><linkUri>http://technet.microsoft.com/library/hh831701.aspx</linkUri></externalLink>。</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
              <para>
                <caps:sentence sentenceid="2b424857701920ac87ca46c7eb00c755" id="tgt411" class="tgtSentence">只有当你需要在使用文件分类基础结构来保护文档的文件服务器上手动添加或检查注册表设置时，才使用以下部分的表格。</caps:sentence>
              </para>
            </content>
            <sections>
              <section expanded="false">
                <title>
                  <caps:sentence sentenceid="d65f30f583b3a9fe88786da1197d0010" id="tgt412" class="tgtSentence">文件服务器和文件分类基础结构注册表设置表</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence sentenceid="914b52489db7031497ab4b2c5cf60a6e" id="tgt413" class="tgtSentence">有关何时使用此表格的说明：</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="040c27cf3069e277567eec1f0b7c9ab4" id="tgt414" class="tgtSentence">
                          <placeholder>ConnectorFQDN</placeholder> 是你在 DNS 中为连接器定义的负载平衡名称。</caps:sentence>
                        <caps:sentence sentenceid="4eee3758f1bf4073d94deae936dd0a13" id="tgt415" class="tgtSentence"> 例如 <system>rmsconnector.contoso.com</system>。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="ed69df32fb51528c4623b7b5da5828fa" id="tgt416" class="tgtSentence">如果你已将连接器配置为使用 HTTPS 与本地服务器通信，请使用 HTTPS 前缀作为连接器 URL。</caps:sentence>
                        <caps:sentence sentenceid="be021ab36c2c99a549fc25f5fcee238c" id="tgt417" class="tgtSentence"> 有关详细信息，请参阅本主题中的<link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ConfiguringHTTPS">Configuring the RMS connector to use HTTPS</link>部分。</caps:sentence>
                        <caps:sentence sentenceid="378cbd311a843a7701e45a31ba958471" id="tgt418" class="tgtSentence"> Microsoft RMS URL 始终使用 HTTPS。</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <table>
                    <thead>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="32dc846aee8a4677c0e887c786acaa73" id="tgt419" class="tgtSentence">注册表路径 </caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="599dcce2998a6b40b1e38e8c6006cb0a" id="tgt420" class="tgtSentence">类型</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2063c1608d6e0baf80249c42e2be5804" id="tgt421" class="tgtSentence">值</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="8d777f385d3dfec8815d20f7496026dc" id="tgt422" class="tgtSentence">数据</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="1968469740d260461985dbaee69c890d" id="tgt423" class="tgtSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\ServiceLocation\EnterprisePublishing</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt424" class="tgtSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="c21f969b5f03d33d43e04f8f136e7682" id="tgt425" class="tgtSentence">默认</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="dbd7790bcd23fde7607101ef6a633779" id="tgt426" class="tgtSentence">http://<placeholder>ConnectorFQDN</placeholder>/_wmcs/licensing</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="40d2921628d72e2b9fe991a68c260ea7" id="tgt427" class="tgtSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\ServiceLocation\Activation</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="2b1bda4361069cdf7a4437824c22893c" id="tgt428" class="tgtSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="c21f969b5f03d33d43e04f8f136e7682" id="tgt429" class="tgtSentence">默认</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence sentenceid="dbd7790bcd23fde7607101ef6a633779" id="tgt430" class="tgtSentence">http://<placeholder>ConnectorFQDN</placeholder>/_wmcs/certification</caps:sentence>
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
      <section address="BKMK_NextSteps">
        <title>
          <caps:sentence sentenceid="0a4f90ce90fc062c4fc00532513d86da" id="tgt431" class="tgtSentence">后续步骤</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="15fcfe7bdbf319a4b1f75c148e3600f6" id="tgt432" class="tgtSentence">现已安装并配置 RMS 连接器，并且你的服务器已配置为使用该连接器，IT 管理员和用户可以使用 Azure RMS 保护和使用电子邮件与文档了。</caps:sentence>
            <caps:sentence sentenceid="a405b0dc575d6a6e91ea3726dd0f118a" id="tgt433" class="tgtSentence"> 若要让用户轻松使用此功能，请部署 RMS 共享应用程序，它会安装 Office 的外接程序并在文件资源管理器中添加新的右键单击选项。</caps:sentence>
            <caps:sentence sentenceid="be021ab36c2c99a549fc25f5fcee238c" id="tgt434" class="tgtSentence"> 有关详细信息，请参阅<externalLink><linkText>Rights Management 共享应用程序管理员指南</linkText><linkUri>http://technet.microsoft.com/library/ dn339003(v=ws.10).aspx</linkUri></externalLink>。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="77f07411e6aa714057e408622313919f" id="tgt435" class="tgtSentence">此外，你可以考虑使用以下方法，帮助你监控 RMS 连接器以及组织使用 Azure RMS 的情况：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="742217359badf83e7eccf3d924afcdc2" id="tgt436" class="tgtSentence">内置 <ui>Microsoft Rights Management 连接器</ui>性能计数器。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="e3eb16afdbabab150c5da0ade825a14d" id="tgt437" class="tgtSentence">
                  <externalLink>
                    <linkText>RMS 分析器工具</linkText>
                    <linkUri>https://www.microsoft.com/en-us/download/details.aspx?id=46437</linkUri>
                  </externalLink>，使用 RMS 连接器选项来帮助你监视连接器的运行状况并确定配置问题。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e">Log and analyze rights management usage</link>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence sentenceid="796a75db26fb2b5ed1340e1b901fe1fd" id="tgt438" class="tgtSentence">向用户和管理员推出 <link xlink:href="086600c2-c5d8-47ec-a4c0-c782e1797486">Azure Rights Management Deployment Roadmap</link> 之前，你可以使用 <token>aad_rightsmanagement_1</token>来检查是否还需要执行其他配置步骤。</caps:sentence>
            <caps:sentence sentenceid="30abe7ab952a58bd862c49f0e10fca5b" id="tgt439" class="tgtSentence"> 如果不需要执行其他配置步骤，请参阅<link xlink:href="18564e4a-9364-4ed2-8f17-89d24fc0d878">Using Azure Rights Management</link> 以获取操作指导，帮助你的组织成功完成部署。</caps:sentence>
          </para>
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
          <caps:sentence id="src1" class="srcSentence">Use this information to learn about the Microsoft Rights Management (RMS) connector and how you can use it to provide information protection with existing on-premises deployments that use Microsoft Exchange Server, Microsoft SharePoint Server, or file servers that run Windows Server and use the File Classification Infrastructure (FCI) capability of File Server Resource Manager.</caps:sentence>
        </para>
        <alert class="tip">
          <para>
            <caps:sentence id="src2" class="srcSentence">For a high-level example scenario with screenshots, see the <link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df#BKMK_Example_FCI">Automatically protecting files on file servers running Windows Server and File Classification Infrastructure</link> section in the <link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link> topic.</caps:sentence>
          </para>
        </alert>
      </introduction>
      <section address="OverviewConnector">
        <title>
          <caps:sentence id="src3" class="srcSentence">Overview of the Microsoft Rights Management connector</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src4" class="srcSentence">The Microsoft Rights Management (RMS) connector lets you quickly enable existing on-premises servers to use their Information Rights Management (IRM) functionality with the cloud-based Microsoft Rights Management service (Azure RMS).</caps:sentence>
            <caps:sentence id="src5" class="srcSentence"> With this functionality, IT and users can easily protect documents and pictures both inside your organization and outside, without having to install additional infrastructure or establish trust relationships with other organizations.</caps:sentence>
            <caps:sentence id="src6" class="srcSentence"> You can use this connector even if some of your users are connecting to online services, in a hybrid scenario.</caps:sentence>
            <caps:sentence id="src7" class="srcSentence"> For example, some users' mailboxes use Exchange Online and some users' mailboxes use Exchange Server.</caps:sentence>
            <caps:sentence id="src8" class="srcSentence"> After you install the RMS connector, all users can protect and consume emails and attachments by using Azure RMS, and information protection works seamlessly between the two deployment configurations.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src9" class="srcSentence">The RMS connector is a small-footprint service that you install on-premises, on servers that run Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2.</caps:sentence>
            <caps:sentence id="src10" class="srcSentence"> In addition to running the connector on physical computers, you can also run it on virtual machines, including Azure IaaS VMs.</caps:sentence>
            <caps:sentence id="src11" class="srcSentence"> After you install and configure the connector, it acts as a communications interface (a relay) between the on-premises servers and the cloud service.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src12" class="srcSentence">If you manage your own tenant key for Azure RMS (the bring you own key, or BYOK scenario), the RMS connector and the on-premises servers that use it do not access the hardware security module (HSM) that contains your tenant key.</caps:sentence>
            <caps:sentence id="src13" class="srcSentence"> This is because all cryptographic operations that use the tenant key are performed in Azure RMS, and not on-premises.</caps:sentence>
          </para>
          <mediaLink>
            <image xlink:href="fca243be-b886-43ad-91e6-6900f7e2cd85"></image>
          </mediaLink>
          <para></para>
          <para></para>
          <para>
            <caps:sentence id="src14" class="srcSentence">The RMS connector supports the following on-premises servers: Exchange Server, SharePoint Server, and file servers that run Windows Server and use File Classification Infrastructure to classify and apply policies to Office documents in a folder.</caps:sentence>
            <caps:sentence id="src15" class="srcSentence"> If you want to protect all files types using File Classification, do not use the RMS connector, but instead, use the <externalLink><linkText>RMS Protection cmdlets</linkText><linkUri>https://msdn.microsoft.com/library/azure/mt433195.aspx</linkUri></externalLink>.</caps:sentence>
          </para>
          <alert class="note">
            <para>
              <caps:sentence id="src16" class="srcSentence">For supported versions of these on-premises servers, see “On-premises servers that support Azure RMS” in the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedApplications">Applications that support Azure RMS</link> section of the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link> topic.</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence id="src17" class="srcSentence">Use the following sections to help you plan for, install, and configure the RMS connector.</caps:sentence>
            <caps:sentence id="src18" class="srcSentence"> You must then do some post installation configuration so that your servers can use the connector.</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_Prereqs">Prerequisites for the RMS connector</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <embeddedLabel>
                  <caps:sentence id="src19" class="srcSentence">Step 1: </caps:sentence>
                </embeddedLabel>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_InstallingConnector">Installing the RMS connector</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <embeddedLabel>
                  <caps:sentence id="src20" class="srcSentence">Step 2: </caps:sentence>
                </embeddedLabel>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#EnteringCredentials">Entering credentials</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <embeddedLabel>
                  <caps:sentence id="src21" class="srcSentence">Step 3: </caps:sentence>
                </embeddedLabel>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#AuthorizingServers">Authorizing servers to use the RMS connector</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <embeddedLabel>
                  <caps:sentence id="src22" class="srcSentence">Step 4: </caps:sentence>
                </embeddedLabel>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#ConfiguringConnector">Configuring load balancing and high availability</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src23" class="srcSentence">Optional: <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ConfiguringHTTPS">Configuring the RMS connector to use HTTPS</link></caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src24" class="srcSentence">Optional: <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ConfiguringWebProxy">Configuring the RMS connector for a web proxy server</link></caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src25" class="srcSentence">Optional: <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_InstallingStandaloneTool">Installing the RMS connector administration tool on administrative computers</link></caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <embeddedLabel>
                  <caps:sentence id="src26" class="srcSentence">Step 5: </caps:sentence>
                </embeddedLabel>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#ConfiguringServers">Configuring servers to use the RMS connector</link>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ExchangeServer">Configuring an Exchange server to use the connector</link>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ConfiguringSharePoint">Configuring a SharePoint server to use the connector</link>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_FileServer">Configuring a file server for File Classification Infrastructure to use the connector</link>
                  </para>
                </listItem>
              </list>
            </listItem>
            <listItem>
              <para>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_NextSteps">Next steps</link>
              </para>
            </listItem>
          </list>
        </content>
      </section>
      <section address="BKMK_Prereqs">
        <title>
          <caps:sentence id="src27" class="srcSentence">Prerequisites for the RMS connector</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src28" class="srcSentence">Before you install the RMS connector, make sure that the following requirements are in place.</caps:sentence>
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
                    <caps:sentence id="src31" class="srcSentence">The Rights Management (RMS) service is activated</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <link xlink:href="f8707e01-b239-4d1a-a1ea-0d1cf9a8d214">Activating Azure Rights Management</link>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src32" class="srcSentence">Directory synchronization between your Active Directory forests and Azure Active Directory</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src33" class="srcSentence">After RMS is activated, Azure Active Directory must be configured to work with the users and groups in your Active Directory database.</caps:sentence>
                  </para>
                  <alert class="important">
                    <para>
                      <caps:sentence id="src34" class="srcSentence">You must do this directory synchronization step for the RMS connector to work, even for a test network.</caps:sentence>
                      <caps:sentence id="src35" class="srcSentence"> Although you can use Office 365 and Azure Active Directory by using accounts that you manually create in Azure Active Directory, this connector requires that the accounts in Azure Active Directory are synchronized with Active Directory Domain Services; manual password synchronization is not sufficient.</caps:sentence>
                    </para>
                  </alert>
                  <para>
                    <caps:sentence id="src36" class="srcSentence">For more information, see the following resources:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <externalLink>
                          <linkText>
                            <caps:sentence id="src37" class="srcSentence">Instructions for configuring your Azure AD tenant</caps:sentence>
                          </linkText>
                          <linkUri>http://technet.microsoft.com/library/hh967611.aspx</linkUri>
                        </externalLink>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <externalLink>
                          <linkText>
                            <caps:sentence id="src38" class="srcSentence">Instructions for enabling directory synchronization with AAD using DirSync</caps:sentence>
                          </linkText>
                          <linkUri>http://technet.microsoft.com/library/hh967642.aspx</linkUri>
                        </externalLink>
                        <br />
                      </para>
                    </listItem>
                  </list>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src39" class="srcSentence">Optional but recommended: </caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src40" class="srcSentence">Enable federation between your on-premises Active Directory and Azure Active Directory  </caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src41" class="srcSentence">You can enable identity federation between your on-premises directory and Azure Active Directory.</caps:sentence>
                    <caps:sentence id="src42" class="srcSentence"> This configuration enables a more seamless user experience by using single sign-on to the RMS service.</caps:sentence>
                    <caps:sentence id="src43" class="srcSentence"> Without single sign on, users are prompted for their credentials before they can use rights-protected content.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src44" class="srcSentence">For instructions to configure federation by using Active Directory Federation Services (AD FS) between Active Directory Domain Services and Azure Active Directory, see the <externalLink><linkText>Checklist: Use AD FS to implement and manage single sign-on</linkText><linkUri>http://technet.microsoft.com/library/jj205462.aspx</linkUri></externalLink> in the Windows Server library.</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src45" class="srcSentence">A minimum of two member computers on which to install the RMS connector:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src46" class="srcSentence">A 64-bit physical or virtual computer running one of the following operating systems: </caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src47" class="srcSentence">Windows Server 2012 R2</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src48" class="srcSentence">Windows Server 2012</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src49" class="srcSentence">Windows Server 2008 R2</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src50" class="srcSentence">At least 1 GB of RAM</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src51" class="srcSentence">A minimum of 64 GB of disk space</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src52" class="srcSentence">At least one network interface</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src53" class="srcSentence">Access to the Internet via a firewall (or web proxy) that does not require authentication</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src54" class="srcSentence">Must be in a forest or domain that trusts other forests in the organization that contain installations of Exchange or SharePoint servers that you want to use with the RMS connector</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src55" class="srcSentence">For fault tolerance and high availability, you must install the RMS connector on a minimum of two computers.</caps:sentence>
                  </para>
                  <alert class="tip">
                    <para>
                      <caps:sentence id="src56" class="srcSentence">If you are using Outlook Web Access or mobile devices that use Exchange ActiveSync IRM and it is critical that you maintain access to emails and attachments that are protected by Azure RMS, we recommend that you deploy a load-balanced group of connector servers to ensure high availability.</caps:sentence>
                    </para>
                  </alert>
                  <para>
                    <caps:sentence id="src57" class="srcSentence">You do not need dedicated servers to run the connector but you must install it on a separate computer from the servers that will use the connector.</caps:sentence>
                  </para>
                  <alert class="important">
                    <para>
                      <caps:sentence id="src58" class="srcSentence">Do not install the connector on a computer that runs Exchange Server, SharePoint Server, or a file server that is configured for file classification infrastructure if you want to use the functionality from these services with Azure RMS.</caps:sentence>
                      <caps:sentence id="src59" class="srcSentence"> Also, do not install this connector on a domain controller.</caps:sentence>
                    </para>
                  </alert>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section address="BKMK_InstallingConnector">
        <title>
          <caps:sentence id="src60" class="srcSentence">Installing the RMS connector</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src61" class="srcSentence">After you have confirmed the prerequisites in the preceding section, use the following instructions to install the RMS connector:</caps:sentence>
          </para>
          <list class="ordered">
            <listItem>
              <para>
                <caps:sentence id="src62" class="srcSentence">Identify the computers (minimum of two) that will run the RMS connector.</caps:sentence>
                <caps:sentence id="src63" class="srcSentence"> They must meet the minimum specification listed in the preceding section.</caps:sentence>
              </para>
              <alert class="note">
                <para>
                  <caps:sentence id="src64" class="srcSentence">You will install a single RMS connector (consisting of multiple servers for high availability) per tenant (Office 365 tenant or Azure AD tenant).</caps:sentence>
                  <caps:sentence id="src65" class="srcSentence"> Unlike Active Directory RMS, you do not have to install an RMS connector in each forest.</caps:sentence>
                </para>
              </alert>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src66" class="srcSentence">Download the source files for the RMS connector from the <externalLink><linkText>Microsoft Download Center</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=314106</linkUri></externalLink>.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src67" class="srcSentence">To install the RMS connector, download RMSConnectorSetup.exe.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src68" class="srcSentence">In addition:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src69" class="srcSentence">If you later want to configure the connector from a 32-bit computer, also download RMSConnectorAdminToolSetup_x86.exe.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src70" class="srcSentence">If you want to use the server configuration tool for the RMS connector, to automate the configuration of registry settings on you on-premises servers, also download GenConnectorConfig.ps1.</caps:sentence>
                  </para>
                </listItem>
              </list>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src71" class="srcSentence">On the computer on which you want to install the RMS connector, run <legacyBold>RMSConnectorSetup.exe</legacyBold> with Administrator privileges.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src72" class="srcSentence">On the Welcome page of the Microsoft Rights Management Connector Setup page, select <ui>Install Microsoft Rights Management connector on the computer</ui>, and then click <ui>Next</ui>.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src73" class="srcSentence">Read and agree to the RMS connector license terms, and then click <legacyBold>Next</legacyBold>.</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src74" class="srcSentence">To continue, enter an account and password to configure the RMS connector.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="EnteringCredentials">
        <title>
          <caps:sentence id="src75" class="srcSentence">Entering credentials</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src76" class="srcSentence">Before you can configure the RMS connector, you must enter credentials for an account that has sufficient privileges to configure the RMS connector.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src77" class="srcSentence">In addition, if you have implemented <externalLink><linkText>onboarding controls</linkText><linkUri>https://technet.microsoft.com/library/jj658941.aspx#BKMK_OnboardingControls</linkUri></externalLink>, make sure that the account you specify is able to protect content. For example, if you restricted the ability to protect content to the “IT department” group, the account that you specify here must be a member of that group. If not, you will see the error message: <ui>The attempt to discover the location of the administration service and organization failed. Make sure Microsoft Rights Management service is enabled for your organization.</ui></caps:sentence>
          </para>
          <para>
            <caps:sentence id="src78" class="srcSentence">You can use an account that has one of the following privileges:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src79" class="srcSentence">
                  <legacyBold>Office 365 tenant administrator</legacyBold>: An account that is a global admin for your Office 365 tenant.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src80" class="srcSentence">
                  <legacyBold> Azure Rights Management global administrator</legacyBold>: An account with administrator privileges for the Azure RMS tenant.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src81" class="srcSentence">
                  <legacyBold>Microsoft RMS connector Administrator</legacyBold>: An account in Azure Active Directory that has been granted rights to install and administer the RMS connector for your organization.</caps:sentence>
              </para>
              <para></para>
              <alert class="note">
                <para>
                  <caps:sentence id="src82" class="srcSentence">If you want to use the Microsoft RMS connector Administrator account, you must first do the following to assign the RMS connector administrator role:</caps:sentence>
                </para>
                <list class="ordered">
                  <listItem>
                    <para>
                      <caps:sentence id="src83" class="srcSentence">On the same computer, download and install Windows PowerShell for Rights Management.</caps:sentence>
                      <caps:sentence id="src84" class="srcSentence"> For more information, see <link xlink:href="0d665ed6-b1de-4d63-854a-bc57c1c49844">Installing Windows PowerShell for Azure Rights Management</link>.</caps:sentence>
                    </para>
                    <para>
                      <caps:sentence id="src85" class="srcSentence">Start Windows PowerShell with the <ui>Run as administrator</ui> command, and connect to the Azure RMS service by using the <externalLink><linkText>Connect-AadrmService</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629415.aspx</linkUri></externalLink> command: </caps:sentence>
                    </para>
                    <code>Connect-AadrmService                   //provide Office 365 tenant administrator or Azure RMS global administrator credentials</code>
                  </listItem>
                  <listItem>
                    <para>
                      <caps:sentence id="src86" class="srcSentence">Then run the <externalLink><linkText>Add-AadrmRoleBasedAdministrator</linkText><linkUri>https://msdn.microsoft.com/library/azure/dn629417.aspx</linkUri></externalLink> command, using just one of the following parameters:   </caps:sentence>
                    </para>
                    <code>Add-AadrmRoleBasedAdministrator -EmailAddress &lt;email address&gt; -Role "ConnectorAdministrator"</code>
                    <code>Add-AadrmRoleBasedAdministrator -ObjectId &lt;object id&gt; -Role "ConnectorAdministrator"</code>
                    <code>Add-AadrmRoleBasedAdministrator -SecurityGroupDisplayName &lt;group Name&gt; -Role "ConnectorAdministrator"</code>
                    <para>
                      <caps:sentence id="src87" class="srcSentence">For example, type: <userInput>Add-AadrmRoleBasedAdministrator -EmailAddress melisa@contoso.com -Role " ConnectorAdministrator "</userInput></caps:sentence>
                    </para>
                    <para>
                      <caps:sentence id="src88" class="srcSentence">Although these commands use the ConnectorAdministrator role, you could also use the GlobalAdministrator role here, as well.</caps:sentence>
                    </para>
                  </listItem>
                </list>
              </alert>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src89" class="srcSentence">During the RMS connector installation process, all prerequisite software is validated and installed, Internet Information Services (IIS) is installed if not already present, and the connector software is installed and configured.</caps:sentence>
            <caps:sentence id="src90" class="srcSentence"> In addition, Azure RMS is prepared for configuration by creating the following:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src91" class="srcSentence">An empty table of servers that are authorized to use the connector to communicate with Azure RMS.</caps:sentence>
                <caps:sentence id="src92" class="srcSentence"> You will add servers to this table later.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src93" class="srcSentence">A set of security tokens for the connector, which authorize operations with Azure RMS.</caps:sentence>
                <caps:sentence id="src94" class="srcSentence"> These tokens are downloaded from Azure RMS and installed on the local computer in the registry.</caps:sentence>
                <caps:sentence id="src95" class="srcSentence"> They are protected by using the data protection application programming interface (DPAPI) and the Local System account credentials.</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src96" class="srcSentence">On the final page of the wizard, do the following, and then click <ui>Finish</ui>:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src97" class="srcSentence">If this is the first connector that you have installed, do not select <ui>Launch connector administrator console to authorize servers</ui> at this time.</caps:sentence>
                <caps:sentence id="src98" class="srcSentence"> You will select this option after you have installed your second (or final) RMS connector.</caps:sentence>
                <caps:sentence id="src99" class="srcSentence"> Instead, run the wizard again on at least one other computer.</caps:sentence>
                <caps:sentence id="src100" class="srcSentence"> You must install a minimum of two connectors.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src101" class="srcSentence">If you have installed your second (or final) connector, select <ui>Launch connector administrator console to authorize servers</ui>.</caps:sentence>
              </para>
            </listItem>
          </list>
          <alert class="tip">
            <para>
              <caps:sentence id="src102" class="srcSentence">At this point, there is a verification test that you can perform to test whether the web services for the RMS connector are operational: </caps:sentence>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <caps:sentence id="src103" class="srcSentence">From a web browser, connect to <userInput>http://&lt;connectoraddress&gt;/_wmcs/certification/servercertification.asmx</userInput>, replacing <placeholder>&lt;connectoraddress&gt;</placeholder> with the server address or name that has the RMS connector installed.</caps:sentence>
                  <caps:sentence id="src104" class="srcSentence"> A successful connection displays a <ui>ServerCertificationWebService</ui> page.</caps:sentence>
                </para>
              </listItem>
            </list>
          </alert>
          <para>
            <caps:sentence id="src105" class="srcSentence">If you need to uninstall the RMS connector, run the wizard again and select the uninstall option.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="AuthorizingServers">
        <title>
          <caps:sentence id="src106" class="srcSentence">Authorizing servers to use the RMS connector</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src107" class="srcSentence">When you have installed the RMS connector on at least two computers, you are ready to authorize the servers and services that you want to use the RMS connector.</caps:sentence>
            <caps:sentence id="src108" class="srcSentence"> For example, servers running Exchange Server 2013 or SharePoint Server 2013.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src109" class="srcSentence">To define these servers, run the RMS connector administration tool and add entries to the list of allowed servers.</caps:sentence>
            <caps:sentence id="src110" class="srcSentence"> You can run this tool when you select <ui>Launch connector administration console to authorize servers</ui> at the end of the Microsoft Rights Management connector Setup wizard, or you can run it separately from the wizard.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src111" class="srcSentence">When you authorize these servers, be aware of the following considerations:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src112" class="srcSentence">Servers that you add will be granted special privileges.</caps:sentence>
                <caps:sentence id="src113" class="srcSentence"> All accounts that you specify for the Exchange Server role in the connector configuration will be granted the <externalLink><linkText>super user role</linkText><linkUri>https://technet.microsoft.com/library/mt147272.aspx</linkUri></externalLink> in Azure RMS, which gives them access to all content for this RMS tenant.</caps:sentence>
                <caps:sentence id="src114" class="srcSentence"> The super user feature is automatically enabled at this point, if necessary.</caps:sentence>
                <caps:sentence id="src115" class="srcSentence"> To avoid the security risk of elevation of privileges, be careful to specify only the accounts that are used by your organization’s Exchange servers.</caps:sentence>
                <caps:sentence id="src116" class="srcSentence"> All servers configured as SharePoint servers or file servers that use FCI will be granted regular user privileges.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src117" class="srcSentence">You can add multiple servers as a single entry by specifying an Active Directory security or distribution group, or a service account that is used by more than one server.</caps:sentence>
                <caps:sentence id="src118" class="srcSentence"> When you use this configuration, the group of servers will share the same RMS certificates and will all be considered owners for content that any of them have protected.</caps:sentence>
                <caps:sentence id="src119" class="srcSentence"> To minimize administrative overheads, we recommend that you use this configuration of a single group rather than individual servers to authorize your organization’s Exchange servers or a SharePoint server farm.</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src120" class="srcSentence">On the <ui>Servers allowed to utilize the connector</ui> page, click <ui>Add</ui>.</caps:sentence>
          </para>
        </content>
        <sections>
          <section address="BKMK_AddServer">
            <title>
              <caps:sentence id="src121" class="srcSentence">Add a server to the list of allowed servers</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src122" class="srcSentence">On the <ui>Allow a server to utilize the connector</ui> page, enter the name of the object, or browse to identify the object to authorize.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src123" class="srcSentence">It is important that you authorize the correct object.</caps:sentence>
                <caps:sentence id="src124" class="srcSentence"> For a server to use the connector, the account that runs the on-premises service (for example, Exchange or SharePoint) must be selected for authorization.</caps:sentence>
                <caps:sentence id="src125" class="srcSentence"> For example, if the service is running as a configured service account, add the name of that service account to the list.</caps:sentence>
                <caps:sentence id="src126" class="srcSentence"> If the service is running as Local System, add the name of the computer object (for example, SERVERNAME$).</caps:sentence>
                <caps:sentence id="src127" class="srcSentence"> As a best practice, create a group that contains these accounts and specify the group instead of individual server names.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src128" class="srcSentence">More information about the different server roles:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src129" class="srcSentence">For servers that run Exchange: You must specify a security group and you can use the default group (<ui>Exchange Servers</ui>) that Exchange automatically creates and maintains of all Exchange servers in the forest.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src130" class="srcSentence">For servers that run SharePoint: </caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src131" class="srcSentence">If a SharePoint 2010 server is configured to run as Local System (it's not using a service account), manually create a security group in Active Directory Domain Services, and add the computer name object for the server in this configuration to this group.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src132" class="srcSentence">If a SharePoint server is configured to use a service account (the recommended practice for SharePoint 2010 and the only option for SharePoint 2013), do the following:</caps:sentence>
                      </para>
                      <list class="ordered">
                        <listItem>
                          <para>
                            <caps:sentence id="src133" class="srcSentence">Add the service account that runs the SharePoint Central Administration service to enable SharePoint to be configured from its administrator console.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src134" class="srcSentence">Add the account that is configured for the SharePoint App Pool.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                      <alert class="tip">
                        <para>
                          <caps:sentence id="src135" class="srcSentence">If these two accounts are different, consider creating a single group that contains both accounts to minimize the administrative overheads.</caps:sentence>
                        </para>
                      </alert>
                    </listItem>
                  </list>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src136" class="srcSentence">For file servers that use File Classification Infrastructure, the associated services run as the Local System account, so you must authorize the computer account for the file servers (for example, SERVERNAME$) or a group that contains those computer accounts.</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence id="src137" class="srcSentence">When you have finished adding servers to the list, click <ui>Close</ui>.</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src138" class="srcSentence">If you haven’t already done so, you must now configure load balancing for the servers that have the RMS connector installed, and consider whether to use HTTPS for the connections between these servers and the servers that you have just authorized.</caps:sentence>
              </para>
            </content>
          </section>
        </sections>
      </section>
      <section address="ConfiguringConnector">
        <title>
          <caps:sentence id="src139" class="srcSentence">Configuring load balancing and high availability</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src140" class="srcSentence">After you have installed the second or final instance of the RMS connector, define a connector URL server name and configure a load balancing system.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src141" class="srcSentence">The connector URL server name can be any name under a namespace that you control.</caps:sentence>
            <caps:sentence id="src142" class="srcSentence"> For example, you could create an entry in your DNS system for <userInput>rmsconnector.contoso.com</userInput> and configure this entry to use an IP address in your load balancing system.</caps:sentence>
            <caps:sentence id="src143" class="srcSentence"> There are no special requirements for this name and it doesn’t need to be configured on the connector servers themselves.</caps:sentence>
            <caps:sentence id="src144" class="srcSentence"> Unless your Exchange and SharePoint servers are going to be communicating with the connector over the Internet, this name doesn’t have to resolve on the Internet.</caps:sentence>
          </para>
          <alert class="important">
            <para>
              <caps:sentence id="src145" class="srcSentence">We recommend that you don’t change this name after you have configured Exchange or SharePoint servers to use the connector, because you have to then clear these servers of all IRM configurations and then reconfigure them.</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence id="src146" class="srcSentence">After the name is created in DNS and is configured for an IP address, configure load balancing for that address, which directs traffic to the connector servers.</caps:sentence>
            <caps:sentence id="src147" class="srcSentence"> You can use any IP-based load balancer for this purpose, which includes  the Network Load Balancing (NLB) feature in Windows Server.</caps:sentence>
            <caps:sentence id="src148" class="srcSentence"> For more information, see <externalLink><linkText>Load Balancing Deployment Guide</linkText><linkUri>http://technet.microsoft.com/library/cc754833(v=WS.10).aspx</linkUri></externalLink>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src149" class="srcSentence">Use the following settings to configure the NLB cluster:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src150" class="srcSentence">Ports: 80 (for HTTP) or 443 (for HTTPS)</caps:sentence>
              </para>
              <para>
                <caps:sentence id="src151" class="srcSentence">For more information about whether to use HTTP or HTTPS, see the next section.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src152" class="srcSentence">Affinity: None</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src153" class="srcSentence">Distribution method: Equal</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src154" class="srcSentence">This name that you define for the load-balanced system (for the servers running the RMS connector service) is your organization’s RMS connector name that you will use later, when you configure the on-premises servers to use Azure RMS.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="BKMK_ConfiguringHTTPS">
        <title>
          <caps:sentence id="src155" class="srcSentence">Configuring the RMS connector to use HTTPS</caps:sentence>
        </title>
        <content>
          <alert class="note">
            <para>
              <caps:sentence id="src156" class="srcSentence">This configuration step is optional, but recommended for additional security.</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence id="src157" class="srcSentence">Although the use of TLS or SSL is optional for the RMS connector, we recommend it for any HTTP-based security-sensitive service.</caps:sentence>
            <caps:sentence id="src158" class="srcSentence"> This configuration authenticates the servers running the connector to your Exchange and SharePoint servers that use the connector.</caps:sentence>
            <caps:sentence id="src159" class="srcSentence"> In addition, all data that is sent from these servers to the connector is encrypted.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src160" class="srcSentence">To enable the RMS connector to use TLS, on each server that runs the RMS connector, install a server authentication certificate that contains the name that you will use for the connector.</caps:sentence>
            <caps:sentence id="src161" class="srcSentence"> For example, if your RMS connector name that you defined in DNS is <system>rmsconnector.contoso.com</system>, deploy a server authentication certificate that contains <system>rmsconnector.contoso.com</system> in the certificate subject as the common name.</caps:sentence>
            <caps:sentence id="src162" class="srcSentence"> Or, specify <system>rmsconnector.contoso.com</system> in the certificate alternative name as the DNS value.</caps:sentence>
            <caps:sentence id="src163" class="srcSentence"> The certificate does not have to include the name of the server.</caps:sentence>
            <caps:sentence id="src164" class="srcSentence"> Then in IIS, bind this certificate to the Default Web Site.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src165" class="srcSentence">If you use the HTTPS option, ensure that all servers that run the connector have a valid server authentication certificate that chains to a root CA that your Exchange and SharePoint servers trust.</caps:sentence>
            <caps:sentence id="src166" class="srcSentence"> In addition, if the certification authority (CA) that issued the certificates for the connector servers publishes a certificate revocation list (CRL), the Exchange and SharePoint servers must be able to download this CRL.</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence id="src167" class="srcSentence">You can use the following information and resources to help you request and install a server authentication certificate, and to bind this certificate to the Default Web Site in IIS:</caps:sentence>
            </para>
            <list class="bullet">
              <listItem>
                <para>
                  <caps:sentence id="src168" class="srcSentence">If you use Active Directory Certificate Services (AD CS) and an enterprise certification authority (CA) to deploy these server authentication certificates, you can duplicate and then use the Web Server certificate template.</caps:sentence>
                  <caps:sentence id="src169" class="srcSentence"> This certificate template uses <ui>Supplied in the request</ui> for the certificate subject name, which means that you can provide the FQDN of the RMS connector name for the certificate subject name or subject alternative name when you request the certificate.</caps:sentence>
                </para>
              </listItem>
              <listItem>
                <para>
                  <caps:sentence id="src170" class="srcSentence">If you use a stand-alone CA or purchase this certificate from another company, see <externalLink><linkText>Configuring Internet Server Certificates (IIS 7)</linkText><linkUri>http://technet.microsoft.com/library/cc731977(v=ws.10).aspx</linkUri></externalLink> in the <externalLink><linkText>Web Server (IIS)</linkText><linkUri>http://technet.microsoft.com/library/cc753433(v=ws.10).aspx</linkUri></externalLink> documentation library on TechNet.</caps:sentence>
                </para>
              </listItem>
              <listItem>
                <para>
                  <caps:sentence id="src171" class="srcSentence">To configure IIS to use the certificate, see <externalLink><linkText>Add a Binding to a Site (IIS 7)</linkText><linkUri>http://technet.microsoft.com/library/cc731692.aspx</linkUri></externalLink> in the in the <externalLink><linkText>Web Server (IIS)</linkText><linkUri>http://technet.microsoft.com/library/cc753433(v=ws.10).aspx</linkUri></externalLink> documentation library on TechNet.</caps:sentence>
                </para>
              </listItem>
            </list>
          </alert>
        </content>
      </section>
      <section address="BKMK_ConfiguringWebProxy">
        <title>
          <caps:sentence id="src172" class="srcSentence">Configuring the RMS connector for a web proxy server</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src173" class="srcSentence">If your connector servers are installed in a network that does not have direct Internet connectivity and requires manual configuration of a web proxy server for outbound Internet access, you must configure the registry on these servers for the RMS connector.</caps:sentence>
          </para>
          <procedure>
            <title>
              <caps:sentence id="src174" class="srcSentence">To configure the RMS connector to use a web proxy server</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src175" class="srcSentence">On each server running the RMS connector, open a registry editor, such as Regedit.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src176" class="srcSentence">Navigate to <ui>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AADRM\Connector</ui></caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src177" class="srcSentence">Add the string value of <ui>ProxyAddress</ui> and then set the Data for this value to be <ui>http://&lt;MyProxyDomainOrIPaddress&gt;:&lt;MyProxyPort&gt;</ui></caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src178" class="srcSentence">For example: <userInput>http://proxyserver.contoso.com:8080</userInput></caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src179" class="srcSentence">Close the registry editor, and then restart the server or perform an IISReset command to restart IIS.</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
          </procedure>
        </content>
      </section>
      <section address="BKMK_InstallingStandaloneTool">
        <title>
          <caps:sentence id="src180" class="srcSentence">Installing the RMS connector administration tool on administrative computers</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src181" class="srcSentence">You can run the RMS connector administration tool from a computer that does not have the RMS connector installed, if that computer meets the following requirements:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src182" class="srcSentence">A physical or virtual computer running Windows Server 2012 or Windows Server 2012 R2 (all editions), Windows Server 2008 R2 or Windows Server 2008 R2 Service Pack 1 (all editions), Windows 8.1, Windows 8, or Windows 7.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src183" class="srcSentence">At least 1 GB of RAM.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src184" class="srcSentence">A minimum of 64 GB of disk space.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src185" class="srcSentence">At least one network interface.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src186" class="srcSentence">Access to the Internet via a firewall (or web proxy).</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src187" class="srcSentence">To install the RMS connector administration tool, run the following files:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src188" class="srcSentence">For a 32-bit computer: RMSConnectorAdminToolSetup_x86.exe</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src189" class="srcSentence">For a 64-bit computer: RMSConnectorSetup.exe</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src190" class="srcSentence">If you haven’t already downloaded these files, you can do so from the <externalLink><linkText>Microsoft Download Center</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=314106</linkUri></externalLink>.</caps:sentence>
          </para>
        </content>
      </section>
      <section address="ConfiguringServers">
        <title>
          <caps:sentence id="src191" class="srcSentence">Configuring servers to use the RMS connector</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src192" class="srcSentence">After you have installed and configured the RMS connector, you are ready to configure your on-premises servers that will use Rights Management and connect to Azure RMS by using the connector.</caps:sentence>
            <caps:sentence id="src193" class="srcSentence"> This means configuring the following servers:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src194" class="srcSentence">For Exchange 2013: Client access servers and mailbox servers</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src195" class="srcSentence">For Exchange 2010: Client access servers and hub transport servers</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src196" class="srcSentence">For SharePoint: Front-end SharePoint webservers, including those hosting the Central Administration server</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src197" class="srcSentence">For File Classification Infrastructure: Windows Server computers that have installed File Resource Manager</caps:sentence>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src198" class="srcSentence">This configuration requires registry settings.</caps:sentence>
            <caps:sentence id="src199" class="srcSentence"> To do this, you have two options:</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src200" class="srcSentence">Configuration option</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src201" class="srcSentence">Advantages</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src202" class="srcSentence">Disadvantages</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src203" class="srcSentence">Automatically by using the server configuration tool for Microsoft RMS connector</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src204" class="srcSentence">No direct editing of the registry.</caps:sentence>
                    <caps:sentence id="src205" class="srcSentence"> This is automated for you by using a script.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src206" class="srcSentence">No need to run a Windows PowerShell cmdlet to obtain your Microsoft RMS URL.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src207" class="srcSentence">The prerequisites are automatically checked for you (but not automatically remediated) if you run it locally.</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src208" class="srcSentence">When you run the tool, you must make a connection to a server that is already running the RMS connector.</caps:sentence>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src209" class="srcSentence">Manually by editing the registry</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src210" class="srcSentence">No connectivity to a server running the RMS connector is required.</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src211" class="srcSentence">More administrative overheads that are error-prone.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src212" class="srcSentence">You must obtain your Microsoft RMS URL, which requires you to run a Windows PowerShell command.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src213" class="srcSentence">You must always make all the prerequisites checks yourself.</caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
          <para></para>
          <alert class="important">
            <para>
              <caps:sentence id="src214" class="srcSentence">In both cases, you must manually install any prerequisites and configure Exchange, SharePoint, and File Classification Infrastructure to use Rights Management.</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence id="src215" class="srcSentence">For most organizations, automatic configuration by using the server configuration tool for Microsoft RMS connector will be the better option, because it provides greater efficiency and reliability than manual configuration.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src216" class="srcSentence">After making the configuration changes on these servers, you must restart them if they are running Exchange or SharePoint and previously configured to use AD RMS.</caps:sentence>
            <caps:sentence id="src217" class="srcSentence"> There is no need to restart these servers if you are configuring them for Rights Management for the first time.</caps:sentence>
            <caps:sentence id="src218" class="srcSentence"> You must always restart the file server that is configured to use File Classification Infrastructure after you make these configuration changes.</caps:sentence>
          </para>
          <procedure address="BKMK_HowToRunTheTool">
            <title>
              <caps:sentence id="src219" class="srcSentence">How to use the server configuration tool for Microsoft RMS connector</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src220" class="srcSentence">If you haven’t already downloaded the script for the server configuration tool for Microsoft RMS connector (GenConnectorConfig.ps1), download it from the <externalLink><linkText>Microsoft Download Center</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=314106</linkUri></externalLink>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src221" class="srcSentence">Save the GenConnectorConfig.ps1 file on the computer where you will run the tool.</caps:sentence>
                    <caps:sentence id="src222" class="srcSentence"> If you will run the tool locally, this must be the server that you want to configure to communicate with the RMS connector.</caps:sentence>
                    <caps:sentence id="src223" class="srcSentence"> Otherwise, you can save it on any computer.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src224" class="srcSentence">Decide how to run the tool:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src225" class="srcSentence">
                          <embeddedLabel>Locally</embeddedLabel>: You can run the tool interactively, from the server to be configured to communicate with the RMS connector.</caps:sentence>
                        <caps:sentence id="src226" class="srcSentence"> This is useful for a one-off configuration, such as a testing environment.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src227" class="srcSentence">
                          <embeddedLabel>Software deployment</embeddedLabel>: You can run the tool to produce registry files that you then deploy to one or more relevant servers by using a systems management application that supports software deployment, such as System Center Configuration Manager.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src228" class="srcSentence">
                          <embeddedLabel>Group Policy</embeddedLabel>: You can run the tool to produce a script that you give to an administrator who can create Group Policy objects for the servers to be configured.</caps:sentence>
                        <caps:sentence id="src229" class="srcSentence"> This script creates one Group Policy object for each server type to be configured, which the administrator can then assign to the relevant servers.</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <alert class="note">
                    <para>
                      <caps:sentence id="src230" class="srcSentence">This tool configures the servers that will communicate with the RMS connector and that are listed at the beginning of this section.</caps:sentence>
                      <caps:sentence id="src231" class="srcSentence"> Do not run this tool on the servers that run the RMS connector.</caps:sentence>
                    </para>
                  </alert>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src232" class="srcSentence">Start Windows PowerShell with the <ui>Run as an administrator</ui> option, and use the Get-help command to read instructions how to the use the tool for your chosen configuration method:</caps:sentence>
                  </para>
                  <code>Get-help .\GenConnectorConfig.ps1 -detailed</code>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence id="src233" class="srcSentence">To run the script, you must enter the URL of the RMS connector for your organization.</caps:sentence>
                  <caps:sentence id="src234" class="srcSentence"> Enter the protocol prefix (HTTP:// or HTTPS://) and the name of the connector that you defined in DNS for the load balanced address of your connector.</caps:sentence>
                  <caps:sentence id="src235" class="srcSentence"> For example, https://connector.contoso.com.</caps:sentence>
                  <caps:sentence id="src236" class="srcSentence"> The tool then uses that URL to contact the servers running the RMS connector and obtain other parameters that are used to create the required configurations.</caps:sentence>
                </para>
                <alert class="important">
                  <para>
                    <caps:sentence id="src237" class="srcSentence">When you run this tool, make sure that you specify the name of the load-balanced RMS connector for your organization and not the name of a single server that runs the RMS connector service.</caps:sentence>
                  </para>
                </alert>
              </content>
            </conclusion>
          </procedure>
          <para>
            <caps:sentence id="src238" class="srcSentence">Use the following sections for specific information for each service type:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ExchangeServer">Configuring an Exchange server to use the connector</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ConfiguringSharePoint">Configuring a SharePoint server to use the connector</link>
              </para>
            </listItem>
            <listItem>
              <para>
                <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_FileServer">Configuring a file server for File Classification Infrastructure to use the connector</link>
              </para>
            </listItem>
          </list>
          <alert class="note">
            <para>
              <caps:sentence id="src239" class="srcSentence">After these servers are configured to use the connector, client applications that are installed locally on these servers might not work with RMS.</caps:sentence>
              <caps:sentence id="src240" class="srcSentence"> When this happens, it is because the applications try to use the connector rather than use RMS directly, which is not supported.</caps:sentence>
            </para>
            <para>
              <caps:sentence id="src241" class="srcSentence">In addition, if Office 2010 is installed locally on an Exchange server, the client app’s IRM features might work from that computer after the server is configured to use the connector, but this is not supported.</caps:sentence>
            </para>
            <para>
              <caps:sentence id="src242" class="srcSentence">In both scenarios, you must install the client applications on separate computers that are not configured to use the connector.</caps:sentence>
              <caps:sentence id="src243" class="srcSentence"> They will then correctly use RMS directly.</caps:sentence>
            </para>
          </alert>
        </content>
        <sections>
          <section address="BKMK_ExchangeServer">
            <title>
              <caps:sentence id="src244" class="srcSentence">Configuring an Exchange server to use the connector</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src245" class="srcSentence">The following Exchange roles communicate with the RMS connector:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src246" class="srcSentence">For Exchange 2013: Client access server and mailbox server</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src247" class="srcSentence">For Exchange 2010: Client access server and hub transport server</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence id="src248" class="srcSentence">To use the RMS connector, these servers running Exchange must be running one of the following software versions:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src249" class="srcSentence">Exchange Server 2013 with Exchange 2013 Cumulative Update 3</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src250" class="srcSentence">Exchange Server 2010 with Exchange 2010 Service Pack 3 Rollup Update 6</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence id="src251" class="srcSentence">You will also need to install on these servers, a version of the RMS client that includes support for RMS Cryptographic Mode 2.</caps:sentence>
                <caps:sentence id="src252" class="srcSentence"> The minimum version that is supported in Windows Server 2008 is included in the hotfix that you can download from <externalLink><linkText>RSA key length is increased to 2048 bits for AD RMS in Windows Server 2008 R2 and in Windows Server 2008</linkText><linkUri>http://support.microsoft.com/kb/2627272</linkUri></externalLink>.</caps:sentence>
                <caps:sentence id="src253" class="srcSentence"> The minimum version for Windows Server 2008 R2 can be downloaded from <externalLink><linkText>RSA key length is increased to 2048 bits for AD RMS in Windows 7 or in Windows Server 2008 R2</linkText><linkUri>http://support.microsoft.com/kb/2627273</linkUri></externalLink>.</caps:sentence>
                <caps:sentence id="src254" class="srcSentence"> Windows Server 2012 and Windows Server 2012 R2 natively support Cryptographic Mode 2.</caps:sentence>
              </para>
              <alert class="important">
                <para>
                  <caps:sentence id="src255" class="srcSentence">If these versions or later versions of Exchange and the RMS client are not installed, you will not be able to configure Exchange to use the connector.</caps:sentence>
                  <caps:sentence id="src256" class="srcSentence"> Check that these versions are installed before you continue.</caps:sentence>
                </para>
              </alert>
              <procedure>
                <title>
                  <caps:sentence id="src257" class="srcSentence">To configure Exchange servers to use the connector</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src258" class="srcSentence">On the Exchange server roles that communicate with the RMS connector, do one of the following:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src259" class="srcSentence">Run the server configuration tool for Microsoft RMS connector.</caps:sentence>
                            <caps:sentence id="src260" class="srcSentence"> For more information, see <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_HowToRunTheTool">How to use the server configuration tool for Microsoft RMS connector</link> in this topic.</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence id="src261" class="srcSentence">For example, to run the tool locally to configure a server running Exchange 2013: </caps:sentence>
                          </para>
                          <code>.\GenConnectorConfig.ps1 -ConnectorUri https://rmsconnector.contoso.com -SetExchange2013</code>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src262" class="srcSentence">Make manual registry edits by using the tables in the following sections to manually add registry settings on the servers.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src263" class="srcSentence">Enable IRM functionality in Exchange.</caps:sentence>
                        <caps:sentence id="src264" class="srcSentence"> For more information, see <externalLink><linkText>Information Rights Management Procedures</linkText><linkUri>https://technet.microsoft.com/library/dd351212(v=exchg.150).aspx</linkUri></externalLink> in the Exchange library.</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
              <para>
                <caps:sentence id="src265" class="srcSentence">Use the tables in the following sections only if you want to manually add or check registry settings on these servers, which configures the servers to use the RMS connector.</caps:sentence>
                <caps:sentence id="src266" class="srcSentence"> Instructions for when you use these tables:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src267" class="srcSentence">
                      <placeholder>MicrosoftRMSURL</placeholder> is your organization’s Microsoft RMS service URL.</caps:sentence>
                    <caps:sentence id="src268" class="srcSentence"> To find this value:</caps:sentence>
                  </para>
                  <list class="ordered">
                    <listItem>
                      <para>
                        <caps:sentence id="src269" class="srcSentence">Run the <externalLink><linkText>Get-AadrmConfiguration</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629410.aspx</linkUri></externalLink> cmdlet for Azure RMS.</caps:sentence>
                        <caps:sentence id="src270" class="srcSentence"> If you haven’t already installed the Windows PowerShell module for Azure RMS, see <link xlink:href="0d665ed6-b1de-4d63-854a-bc57c1c49844">Installing Windows PowerShell for Azure Rights Management</link>.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src271" class="srcSentence">From the output, identify the <ui>LicensingIntranetDistributionPointUrl</ui> value.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src272" class="srcSentence">For example: <ui>LicensingIntranetDistributionPointUrl   : https://5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com/_wmcs/licensing</ui></caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src273" class="srcSentence">From the value, remove <ui>/_wmcs/licensing</ui> from this string.</caps:sentence>
                        <caps:sentence id="src274" class="srcSentence"> The remaining string is your Microsoft RMS URL.</caps:sentence>
                        <caps:sentence id="src275" class="srcSentence"> In our example, the Microsoft RMS URL would be the following value:</caps:sentence>
                      </para>
                      <para>
                        <ui>
                          <caps:sentence id="src276" class="srcSentence">https://5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com</caps:sentence>
                        </ui>
                      </para>
                    </listItem>
                  </list>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src277" class="srcSentence">
                      <placeholder>ConnectorFQDN</placeholder> is the load-balancing name that you defined in DNS for the connector.</caps:sentence>
                    <caps:sentence id="src278" class="srcSentence"> For example, <system>rmsconnector.contoso.com</system>.</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src279" class="srcSentence">Use the HTTPS prefix for the connector URL if you have configured the connector to use HTTPS to communicate with your on-premises servers.</caps:sentence>
                    <caps:sentence id="src280" class="srcSentence"> For more information, see the <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ConfiguringHTTPS">Configuring the RMS connector to use HTTPS</link> section in this topic.</caps:sentence>
                    <caps:sentence id="src281" class="srcSentence"> The Microsoft RMS URLs always use HTTPS.</caps:sentence>
                  </para>
                </listItem>
              </list>
            </content>
            <sections>
              <section expanded="false">
                <title>
                  <caps:sentence id="src282" class="srcSentence">Table for Exchange 2013 registry settings</caps:sentence>
                </title>
                <content>
                  <table>
                    <thead>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src283" class="srcSentence">Registry path</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src284" class="srcSentence">Type</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src285" class="srcSentence">Value</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src286" class="srcSentence">Data</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src287" class="srcSentence">HKEY_LOCAL_MACHINE\Software\Microsoft\MSDRM\ServiceLocation\Activation</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src288" class="srcSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src289" class="srcSentence">Default</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src290" class="srcSentence">https://<placeholder>MicrosoftRMSURL/_wmcs/certification</placeholder></caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src291" class="srcSentence">HKEY_LOCAL_MACHINE\Software\Microsoft\MSDRM\ServiceLocation\EnterprisePublishing</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src292" class="srcSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src293" class="srcSentence">Default</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src294" class="srcSentence">https://MicrosoftRMSURL/_wmcs/Licensing</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src295" class="srcSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExchangeServer\v15\IRM\CertificationServerRedirection</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src296" class="srcSentence">Reg_SZ</caps:sentence>
                          </para>
                          <para></para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src297" class="srcSentence">https://<placeholder>MicrosoftRMSURL</placeholder></caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src298" class="srcSentence">One of the following, depending on whether you are using HTTP or HTTPS from your Exchange server to the RMS connector:</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence id="src299" class="srcSentence">http://<placeholder>ConnectorFQDN</placeholder></caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src300" class="srcSentence">https://<placeholder>ConnectorFQDN</placeholder></caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src301" class="srcSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExchangeServer\v15\IRM\LicenseServerRedirection</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src302" class="srcSentence">Reg_SZ</caps:sentence>
                          </para>
                          <para></para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src303" class="srcSentence">https://<placeholder>MicrosoftRMSURL</placeholder></caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src304" class="srcSentence">One of the following, depending on whether you are using HTTP or HTTPS from your Exchange server to the RMS connector:</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence id="src305" class="srcSentence">http://<placeholder>ConnectorFQDN</placeholder></caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src306" class="srcSentence">https://<placeholder>ConnectorFQDN</placeholder></caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </TD>
                      </tr>
                    </tbody>
                  </table>
                </content>
              </section>
              <section expanded="false">
                <title>
                  <caps:sentence id="src307" class="srcSentence">Table for Exchange 2010 registry settings</caps:sentence>
                </title>
                <content>
                  <table>
                    <thead>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src308" class="srcSentence">Registry path</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src309" class="srcSentence">Type</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src310" class="srcSentence">Value</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src311" class="srcSentence">Data</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src312" class="srcSentence">HKEY_LOCAL_MACHINE\Software\Microsoft\MSDRM\ServiceLocation\Activation</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src313" class="srcSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src314" class="srcSentence">Default</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src315" class="srcSentence">https://<placeholder>MicrosoftRMSURL</placeholder>/_wmcs/certification</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src316" class="srcSentence">HKEY_LOCAL_MACHINE\Software\Microsoft\MSDRM\ServiceLocation\EnterprisePublishing</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src317" class="srcSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src318" class="srcSentence">Default</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src319" class="srcSentence">https://<placeholder>MicrosoftRMSURL</placeholder>/_wmcs/Licensing</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src320" class="srcSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExchangeServer\v14\IRM\CertificationServerRedirection</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src321" class="srcSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src322" class="srcSentence">https://<placeholder>MicrosoftRMSURL</placeholder></caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src323" class="srcSentence">One of the following, depending on whether you are using HTTP or HTTPS from your Exchange server to the RMS connector:</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence id="src324" class="srcSentence">http://<placeholder>ConnectorFQDN</placeholder></caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src325" class="srcSentence">https://<placeholder>ConnectorFQDN</placeholder></caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src326" class="srcSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExchangeServer\v14\IRM\LicenseServerRedirection</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src327" class="srcSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src328" class="srcSentence">https://<placeholder>MicrosoftRMSURL</placeholder></caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src329" class="srcSentence">One of the following, depending on whether you are using HTTP or HTTPS from your Exchange server to the RMS connector:</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence id="src330" class="srcSentence">http://<placeholder>ConnectorFQDN</placeholder></caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src331" class="srcSentence">https://<placeholder>ConnectorFQDN</placeholder></caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </TD>
                      </tr>
                    </tbody>
                  </table>
                </content>
              </section>
            </sections>
          </section>
          <section address="BKMK_ConfiguringSharePoint">
            <title>
              <caps:sentence id="src332" class="srcSentence">Configuring a SharePoint server to use the connector</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src333" class="srcSentence">The following SharePoint roles communicate with the RMS connector:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src334" class="srcSentence">Front-end SharePoint webservers, including those hosting the Central Administration server</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence id="src335" class="srcSentence">To use the RMS connector, these servers running SharePoint must be running one of the following software versions:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src336" class="srcSentence">SharePoint Server 2013</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src337" class="srcSentence">SharePoint Server 2010</caps:sentence>
                  </para>
                </listItem>
              </list>
              <para>
                <caps:sentence id="src338" class="srcSentence">A SharePoint 2013 server must also be running a version of the MSIPC client 2.1 that is from1.0.622.34 through 1.0.10907.0.</caps:sentence>
              </para>
              <alert class="warning">
                <para>
                  <caps:sentence id="src339" class="srcSentence">There are multiple versions of the MSIPC 2.1 client, so make sure to install a version referenced in this article.</caps:sentence> </para>
                <para>
                  <caps:sentence id="src340" class="srcSentence">You can verify the client version by checking the version number of MSIPC.dll, which is located in <system>\Program Files\Active Directory Rights Management Services Client 2.1</system>.</caps:sentence>
                  <caps:sentence id="src341" class="srcSentence"> The properties dialog box  shows the version number of the MSIPC 2.1 client.</caps:sentence>
                </para>
              </alert>
              <para>
                <caps:sentence id="src342" class="srcSentence">These servers running SharePoint 2010 must have installed a version of the MSDRM client that includes support for RMS Cryptographic Mode 2.</caps:sentence>
                <caps:sentence id="src343" class="srcSentence"> The minimum version that is supported in Windows Server 2008 is included in the hotfix that you can download from <externalLink><linkText>RSA key length is increased to 2048 bits for AD RMS in Windows Server 2008 R2 and in Windows Server 2008</linkText><linkUri>http://support.microsoft.com/kb/2627272</linkUri></externalLink>, and the minimum version for Windows Server 2008 R2 can be downloaded from <externalLink><linkText>RSA key length is increased to 2048 bits for AD RMS in Windows 7 or in Windows Server 2008 R2</linkText><linkUri>http://support.microsoft.com/kb/2627273</linkUri></externalLink>.</caps:sentence>
                <caps:sentence id="src344" class="srcSentence"> Windows Server 2012 and Windows Server 2012 R2 natively support Cryptographic Mode 2.</caps:sentence>
              </para>
              <procedure>
                <title>
                  <caps:sentence id="src345" class="srcSentence">To configure SharePoint servers to use the connector</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src346" class="srcSentence">On the SharePoint servers that communicate with the RMS connector, do one of the following:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src347" class="srcSentence">Run the server configuration tool for Microsoft RMS connector.</caps:sentence>
                            <caps:sentence id="src348" class="srcSentence"> For more information, see <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_HowToRunTheTool">How to use the server configuration tool for Microsoft RMS connector</link> in this topic.</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence id="src349" class="srcSentence">For example, to run the tool locally to configure a server running SharePoint 2013: </caps:sentence>
                          </para>
                          <code>.\GenConnectorConfig.ps1 -ConnectorUri https://rmsconnector.contoso.com -SetSharePoint2013</code>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src350" class="srcSentence">If you are using SharePoint 2013, make manual registry edits by using the table in the following section to manually add registry settings on the servers.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src351" class="srcSentence">Enable IRM in SharePoint.</caps:sentence>
                        <caps:sentence id="src352" class="srcSentence"> For more information, see <externalLink><linkText>Configure Information Rights Management (SharePoint Server 2010)</linkText><linkUri>https://technet.microsoft.com/library/hh545607(v=office.14).aspx</linkUri></externalLink> in the SharePoint library.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src353" class="srcSentence">When you follow these instructions, you must configure SharePoint to use the connector by specifying <ui>Use this RMS server</ui>, and then enter the load-balancing connector URL that you configured.</caps:sentence>
                        <caps:sentence id="src354" class="srcSentence"> Enter the protocol prefix (HTTP:// or HTTPS://) and the name of the connector that you defined in DNS for the load balanced address of your connector.</caps:sentence>
                        <caps:sentence id="src355" class="srcSentence"> For example, if your connector name is  https://connector.contoso.com, your configuration will look like the following picture:</caps:sentence>
                      </para>
                      <para>
                        <mediaLinkInline>
                          <image xlink:href="82377fdd-0c4b-4c2a-8c52-4d19e19f2cda"></image>
                        </mediaLinkInline>
                      </para>
                      <para>
                        <caps:sentence id="src356" class="srcSentence">After IRM is enabled on a SharePoint farm, you can enable IRM on individual libraries by using the <ui>Information Rights Management</ui> option on the <ui>Library Settings</ui> page for each of the libraries.</caps:sentence>
                      </para>
                      <alert class="important">
                        <para>
                          <caps:sentence id="src357" class="srcSentence">For SharePoint to access RMS by using the connector, you must authorize the corresponding accounts in the RMS connector administration tool.</caps:sentence>
                          <caps:sentence id="src358" class="srcSentence"> If you haven’t already done this, see <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#AuthorizingServers">Authorizing servers to use the RMS connector</link> in this topic.</caps:sentence>
                        </para>
                      </alert>
                    </content>
                  </step>
                </steps>
              </procedure>
              <para>
                <caps:sentence id="src359" class="srcSentence">Use the table in the following section only if you want to manually add or check registry settings on a server that runs SharePoint 2013.</caps:sentence>
              </para>
            </content>
            <sections>
              <section expanded="false">
                <title>
                  <caps:sentence id="src360" class="srcSentence">Table for SharePoint 2013 registry settings</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence id="src361" class="srcSentence">Instructions for when you use this table:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src362" class="srcSentence">
                          <placeholder>MicrosoftRMSURL</placeholder> is your organization’s Microsoft RMS service URL.</caps:sentence>
                        <caps:sentence id="src363" class="srcSentence"> To find this value:</caps:sentence>
                      </para>
                      <list class="ordered">
                        <listItem>
                          <para>
                            <caps:sentence id="src364" class="srcSentence">Run the <externalLink><linkText>Get-AadrmConfiguration</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629410.aspx</linkUri></externalLink> cmdlet for Azure RMS.</caps:sentence>
                            <caps:sentence id="src365" class="srcSentence"> If you haven’t already installed the Windows PowerShell module for Azure RMS, see <link xlink:href="0d665ed6-b1de-4d63-854a-bc57c1c49844">Installing Windows PowerShell for Azure Rights Management</link>.</caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src366" class="srcSentence">From the output, identify the <ui>LicensingIntranetDistributionPointUrl</ui> value.</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence id="src367" class="srcSentence">For example: <ui>LicensingIntranetDistributionPointUrl   : https://5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com/_wmcs/licensing</ui></caps:sentence>
                          </para>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src368" class="srcSentence">From the value, remove <ui>/_wmcs/licensing</ui> from this string.</caps:sentence>
                            <caps:sentence id="src369" class="srcSentence"> The remaining string is your Microsoft RMS URL.</caps:sentence>
                            <caps:sentence id="src370" class="srcSentence"> In our example, the Microsoft RMS URL would be the following value:</caps:sentence>
                          </para>
                          <para>
                            <ui>
                              <caps:sentence id="src371" class="srcSentence">https://5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com</caps:sentence>
                            </ui>
                          </para>
                        </listItem>
                      </list>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src372" class="srcSentence">
                          <placeholder>ConnectorFQDN</placeholder> is the load-balancing name that you defined in DNS for the connector.</caps:sentence>
                        <caps:sentence id="src373" class="srcSentence"> For example, <system>rmsconnector.contoso.com</system>.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src374" class="srcSentence">Use the HTTPS prefix for the connector URL if you have configured the connector to use HTTPS to communicate with your on-premises servers.</caps:sentence>
                        <caps:sentence id="src375" class="srcSentence"> For more information, see the <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ConfiguringHTTPS">Configuring the RMS connector to use HTTPS</link> section in this topic.</caps:sentence>
                        <caps:sentence id="src376" class="srcSentence"> The Microsoft RMS URLs always use HTTPS.</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <table>
                    <thead>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src377" class="srcSentence">Registry path </caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src378" class="srcSentence">Type</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src379" class="srcSentence">Value</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src380" class="srcSentence">Data</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src381" class="srcSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\LicensingRedirection</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src382" class="srcSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src383" class="srcSentence">https://<placeholder>MicrosoftRMSURL</placeholder>/_wmcs/licensing</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src384" class="srcSentence">One of the following, depending on whether you are using HTTP or HTTPS from your SharePoint server to the RMS connector:</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence id="src385" class="srcSentence">http://<placeholder>ConnectorFQDN</placeholder>/_wmcs/licensing</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src386" class="srcSentence">https://<placeholder>ConnectorFQDN</placeholder>/_wmcs/licensing</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src387" class="srcSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\EnterpriseCertification</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src388" class="srcSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src389" class="srcSentence">Default</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src390" class="srcSentence">One of the following, depending on whether you are using HTTP or HTTPS from your SharePoint server to the RMS connector:</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence id="src391" class="srcSentence">http://<placeholder>ConnectorFQDN</placeholder>/_wmcs/certification</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src392" class="srcSentence">https://<placeholder>ConnectorFQDN</placeholder>/_wmcs/certification</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src393" class="srcSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\EnterprisePublishing</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src394" class="srcSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src395" class="srcSentence">Default</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src396" class="srcSentence">One of the following, depending on whether you are using HTTP or HTTPS from your SharePoint server to the RMS connector:</caps:sentence>
                          </para>
                          <list class="bullet">
                            <listItem>
                              <para>
                                <caps:sentence id="src397" class="srcSentence">http://<placeholder>ConnectorFQDN</placeholder>/_wmcs/licensing</caps:sentence>
                              </para>
                            </listItem>
                            <listItem>
                              <para>
                                <caps:sentence id="src398" class="srcSentence">https://<placeholder>ConnectorFQDN</placeholder>/_wmcs/licensing</caps:sentence>
                              </para>
                            </listItem>
                          </list>
                        </TD>
                      </tr>
                    </tbody>
                  </table>
                </content>
              </section>
            </sections>
          </section>
          <section address="BKMK_FileServer">
            <title>
              <caps:sentence id="src399" class="srcSentence">Configuring a file server for File Classification Infrastructure to use the connector</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src400" class="srcSentence">To use the RMS connector and File Classification Infrastructure to protect Office documents, the file server must be running one of the following operating systems:</caps:sentence>
              </para>
              <list class="bullet">
                <listItem>
                  <para>
                    <caps:sentence id="src401" class="srcSentence">Windows Server 2012 R2</caps:sentence>
                  </para>
                </listItem>
                <listItem>
                  <para>
                    <caps:sentence id="src402" class="srcSentence">Windows Server 2012</caps:sentence>
                  </para>
                </listItem>
              </list>
              <procedure>
                <title>
                  <caps:sentence id="src403" class="srcSentence">To configure file servers to use the connector</caps:sentence>
                </title>
                <steps class="ordered">
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src404" class="srcSentence">On the file servers configured for File Classification Infrastructure and that will communicate with the RMS connector, do one of the following:</caps:sentence>
                      </para>
                      <list class="bullet">
                        <listItem>
                          <para>
                            <caps:sentence id="src405" class="srcSentence">Run the server configuration tool for Microsoft RMS connector.</caps:sentence>
                            <caps:sentence id="src406" class="srcSentence"> For more information, see <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_HowToRunTheTool">How to use the server configuration tool for Microsoft RMS connector</link> in this topic.</caps:sentence>
                          </para>
                          <para>
                            <caps:sentence id="src407" class="srcSentence">For example, to run the tool locally to configure a file server running FCI: </caps:sentence>
                          </para>
                          <code>.\GenConnectorConfig.ps1 -ConnectorUri https://rmsconnector.contoso.com -SetFCI2012</code>
                        </listItem>
                        <listItem>
                          <para>
                            <caps:sentence id="src408" class="srcSentence">Make manual registry edits by using the table in the following section to manually add registry settings on the servers.</caps:sentence>
                          </para>
                        </listItem>
                      </list>
                    </content>
                  </step>
                  <step>
                    <content>
                      <para>
                        <caps:sentence id="src409" class="srcSentence">Create classification rules and file management tasks to protect documents with RMS Encryption, and then specify an RMS template to automatically apply RMS policies.</caps:sentence>
                        <caps:sentence id="src410" class="srcSentence"> For more information, see <externalLink><linkText>File Server Resource Manager Overview</linkText><linkUri>http://technet.microsoft.com/library/hh831701.aspx</linkUri></externalLink> in the Windows Server documentation library.</caps:sentence>
                      </para>
                    </content>
                  </step>
                </steps>
              </procedure>
              <para>
                <caps:sentence id="src411" class="srcSentence">Use the table in the following section only if you want to manually add or check registry settings on a file server that uses the File Classification Infrastructure to protect documents.</caps:sentence>
              </para>
            </content>
            <sections>
              <section expanded="false">
                <title>
                  <caps:sentence id="src412" class="srcSentence">Table for file server and File Classification Infrastructure registry settings</caps:sentence>
                </title>
                <content>
                  <para>
                    <caps:sentence id="src413" class="srcSentence">Instructions for when you use this table:</caps:sentence>
                  </para>
                  <list class="bullet">
                    <listItem>
                      <para>
                        <caps:sentence id="src414" class="srcSentence">
                          <placeholder>ConnectorFQDN</placeholder> is the load-balancing name that you defined in DNS for the connector.</caps:sentence>
                        <caps:sentence id="src415" class="srcSentence"> For example, <system>rmsconnector.contoso.com</system>.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src416" class="srcSentence">Use the HTTPS prefix for the connector URL if you have configured the connector to use HTTPS to communicate with your on-premises servers.</caps:sentence>
                        <caps:sentence id="src417" class="srcSentence"> For more information, see the <link xlink:href="90e7e33f-9ecc-497b-89c5-09205ffc5066#BKMK_ConfiguringHTTPS">Configuring the RMS connector to use HTTPS</link> section in this topic.</caps:sentence>
                        <caps:sentence id="src418" class="srcSentence"> The Microsoft RMS URLs always use HTTPS.</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                  <table>
                    <thead>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src419" class="srcSentence">Registry path </caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src420" class="srcSentence">Type</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src421" class="srcSentence">Value</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src422" class="srcSentence">Data</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src423" class="srcSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\ServiceLocation\EnterprisePublishing</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src424" class="srcSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src425" class="srcSentence">Default</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src426" class="srcSentence">http://<placeholder>ConnectorFQDN</placeholder>/_wmcs/licensing</caps:sentence>
                          </para>
                        </TD>
                      </tr>
                      <tr>
                        <TD>
                          <para>
                            <caps:sentence id="src427" class="srcSentence">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\ServiceLocation\Activation</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src428" class="srcSentence">Reg_SZ</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src429" class="srcSentence">Default</caps:sentence>
                          </para>
                        </TD>
                        <TD>
                          <para>
                            <caps:sentence id="src430" class="srcSentence">http://<placeholder>ConnectorFQDN</placeholder>/_wmcs/certification</caps:sentence>
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
      <section address="BKMK_NextSteps">
        <title>
          <caps:sentence id="src431" class="srcSentence">Next steps</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src432" class="srcSentence">Now that the RMS connector is installed and configured, and your servers are configured to use it, IT administrators and users can protect and consume email message and documents by using Azure RMS.</caps:sentence>
            <caps:sentence id="src433" class="srcSentence"> To make this easy for users, deploy the RMS sharing application, which installs an add-on for Office and adds new right-click options to File Explorer.</caps:sentence>
            <caps:sentence id="src434" class="srcSentence"> For more information, see the <externalLink><linkText>Rights Management sharing application administrator guide</linkText><linkUri>http://technet.microsoft.com/library/ dn339003(v=ws.10).aspx</linkUri></externalLink>.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src435" class="srcSentence">In addition, you might consider the following to help you monitor the RMS connector and your organization’s usage of Azure RMS:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src436" class="srcSentence">The built-in <ui>Microsoft Rights Management connector</ui> performance counters.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src437" class="srcSentence">The <externalLink><linkText>RMS Analyzer tool</linkText><linkUri>https://www.microsoft.com/en-us/download/details.aspx?id=46437</linkUri></externalLink>, using the RMS connector option to help you monitor the health of the connector and identify any configuration issues.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <link xlink:href="a735f3f7-6eb2-4901-9084-8c3cd3a9087e">Log and analyze rights management usage</link>
              </para>
            </listItem>
          </list>
          <para>
            <caps:sentence id="src438" class="srcSentence">You can use the <link xlink:href="086600c2-c5d8-47ec-a4c0-c782e1797486">Azure Rights Management Deployment Roadmap</link> to check whether there are other configuration steps that you might want to do before you roll out <token>aad_rightsmanagement_1</token> to users and administrators.</caps:sentence>
            <caps:sentence id="src439" class="srcSentence"> If there are no other configuration steps that you need to do, see <link xlink:href="18564e4a-9364-4ed2-8f17-89d24fc0d878">Using Azure Rights Management</link> for operational guidance to support a successful deployment for your organization.</caps:sentence>
          </para>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="206a0bfe-0912-4e0e-aa15-484b000b264c">Configuring rights management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSSource>
</caps:SxS>