---
description: na
keywords: na
pagetitle: Activating Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f8707e01-b239-4d1a-a1ea-0d1cf9a8d215
---
# 激活 Azure 权限管理
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="zh-CN">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="a6612aef320d9abc20fafd1f6419437d" id="tgt1" class="tgtSentence">激活 <token>aad_rightsmanagement_1</token> (Azure RMS) 后，你的组织便可以开始使用支持此信息保护解决方案的应用程序和服务保护重要数据了。</caps:sentence>
          <caps:sentence sentenceid="cd901582498f63e623385c204f0d8d5c" id="tgt2" class="tgtSentence"> 管理员还可以管理和监视你的组织拥有的受保护文件和电子邮件。</caps:sentence>
          <caps:sentence sentenceid="22dcdf3660a156294f18d1e831a92f41" id="tgt3" class="tgtSentence"> 能够开始在 Office、SharePoint 和 Exchange 中使用信息权限管理 (IRM) 功能保护任何敏感或机密文件之前，你必须启用<token>aad_rightsmanagement_2</token>。</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="74456a294208f3dd6905611042c09e91" id="tgt4" class="tgtSentence">如果你要在激活该服务之前了解有关 Azure 权限管理的详细信息（例如，它解决了哪些业务问题、一些典型用例以及它的工作原理），请参阅<link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link></caps:sentence>
        </para>
        <alert class="important">
          <para>
            <caps:sentence sentenceid="7250facfba37da4337c78bf3f22a5142" id="tgt5" class="tgtSentence">在激活 <token>aad_rightsmanagement_2</token> 之前，请确保你的组织具有包含 <token>aad_rightsmanagement_2</token> 服务的服务计划。</caps:sentence>
            <caps:sentence sentenceid="29bb318556909d9053fa1f38fc6a39d5" id="tgt6" class="tgtSentence"> 如果没有，你将不能激活 Azure RMS。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="a7cc2a447bbad2f255de22373cbf7531" id="tgt7" class="tgtSentence">有关详细信息，请参阅<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>主题中的<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link>部分。</caps:sentence>
          </para>
        </alert>
        <para>
          <caps:sentence sentenceid="62d6ec9edce2bebe4d4a8936b0298e58" id="tgt8" class="tgtSentence">激活 Azure RMS 后，你的组织中的所有用户将可以对其文件应用信息保护，并且所有用户均可打开（使用）受 Azure RMS 保护的文件。</caps:sentence>
          <caps:sentence sentenceid="2cbb91bc42479949c19a23cfeafb47f1" id="tgt9" class="tgtSentence"> 但是，如果你愿意，可以通过对分阶段部署使用加入控制来限制哪些人员可以应用信息保护。</caps:sentence>
          <caps:sentence sentenceid="be021ab36c2c99a549fc25f5fcee238c" id="tgt10" class="tgtSentence"> 有关详细信息，请参阅本主题中的<link xlink:href="f8707e01-b239-4d1a-a1ea-0d1cf9a8d214#BKMK_OnboardingControls">Configuring onboarding controls for a phased deployment</link>部分。</caps:sentence>
        </para>
      </introduction>
      <section>
        <title>
          <caps:sentence sentenceid="3022a99e2b94fbe3bd0785117f820a04" id="tgt11" class="tgtSentence">激活权限管理 </caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="35a74ca2dc11a759f77ad4315ead651c" id="tgt12" class="tgtSentence">使用以下某一个过程来激活 <token>aad_rightsmanagement_2</token>。</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence sentenceid="97e7ca47410358e198c4a3d1581e4fe8" id="tgt13" class="tgtSentence">也可以使用 Windows PowerShell cmdlet <externalLink><linkText>Enable-Aadrm</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629412.aspx</linkUri></externalLink> 来激活 <token>aad_rightsmanagement_2</token>。</caps:sentence>
            </para>
          </alert>
          <procedure>
            <title>
              <caps:sentence sentenceid="448a932b5daf8b0098f4c07c904ee0af" id="tgt14" class="tgtSentence">从 Office 365 管理中心激活权限管理</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="61f42da7e9827aae32c2306164be0017" id="tgt15" class="tgtSentence">在注册包含 Rights Management 的 Office 365 计划后，<externalLink><linkText>使用你的工作或学校帐户登录到 Office 365</linkText><linkUri>https://portal.office.com/</linkUri></externalLink>，该帐户应是 Office 365 部署的管理员。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="ca1b5f2c940838d19f527ddf5e790a12" id="tgt16" class="tgtSentence">如果未自动显示 Office 365 管理中心，请选择左上方的应用程序启动程序图标，然后选择“管理”<ui></ui>。</caps:sentence>
                    <caps:sentence sentenceid="90adbbe7112a5ab0269194573e650cc6" id="tgt17" class="tgtSentence"> “管理”<ui></ui>磁贴只会向 Office 365 管理员显示。</caps:sentence>
                  </para>
                  <alert class="tip">
                    <para>
                      <caps:sentence sentenceid="4472b591452aabf0231d9ac41fc2e859" id="tgt18" class="tgtSentence">有关管理中心的帮助，请参阅<externalLink><linkText>关于 Office 365 管理中心 - 管理员帮助</linkText><linkUri>https://support.office.com/article/About-the-Office-365-admin-center-Admin-Help-58537702-d421-4d02-8141-e128e3703547</linkUri></externalLink>。</caps:sentence>
                    </para>
                  </alert>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="1225aff0618ff618a682e6c673274bf1" id="tgt19" class="tgtSentence">在左窗格中，单击“服务设置”<ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="ccbe2a6c96a5df5e1966988e40064061" id="tgt20" class="tgtSentence">单击“Rights Management”<ui></ui>。</caps:sentence>
                  </para>
                  <alert class="note">
                    <para>
                      <caps:sentence sentenceid="c0c5afb05f1c8cd09ba042475e12ab43" id="tgt21" class="tgtSentence">如果你没有看到此选项，原因可能是你的服务计划或产品版本无法支持权限管理，或者尚未经过升级以支持权限管理。</caps:sentence>
                    </para>
                    <para>
                      <caps:sentence sentenceid="f7e7aac84fd51f6b2bdb21e2323ca629" id="tgt22" class="tgtSentence">请使用<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>主题中<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link>部分的信息来确认是否支持。</caps:sentence>
                      <caps:sentence sentenceid="6647515c01356f609900ef6a82d9b00d" id="tgt23" class="tgtSentence"> 如果支持你的服务计划或产品版本，但你却没有看到“权限管理”选项，则原因可能是服务尚未升级。</caps:sentence>
                      <caps:sentence sentenceid="41b3525f168249c124096df64854dced" id="tgt24" class="tgtSentence"> 若要获取有关此问题的帮助，请发送电子邮件至 <externalLink><linkText>askipteam</linkText><linkUri>mailto:askipteam@microsoft.com?subject=I%20cannot%20activate%20RMS</linkUri></externalLink>。</caps:sentence>
                    </para>
                  </alert>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="87c942eae0180b2f79691fe9cf6c988f" id="tgt25" class="tgtSentence">在“Rights Management”页上，单击“管理”<ui></ui><ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="87c942eae0180b2f79691fe9cf6c988f" id="tgt26" class="tgtSentence">在“权限管理”页上，单击“激活”<ui></ui><ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="7e260026e3b6cd45c8d06073fd587d67" id="tgt27" class="tgtSentence">当提示<ui>“是否要激活权限管理?”</ui>时，请单击<ui>“激活”</ui>。</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence sentenceid="a9b5a907acedb28952be8ea483888cea" id="tgt28" class="tgtSentence">现在，应会显示“Rights Management 已激活”<ui></ui>和用于停用的选项。</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
          <procedure>
            <title>
              <caps:sentence sentenceid="765859a88a8ee65331c68d9c8332ad4d" id="tgt29" class="tgtSentence">从 Azure 经典门户激活 Rights Management</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="234d010a4b4e5b7885b98c586322831a" id="tgt30" class="tgtSentence">注册 Azure 帐户后，<externalLink><linkText>登录到 Azure 经典门户</linkText><linkUri>http://go.microsoft.com/fwlink/p/?LinkID=275081</linkUri></externalLink>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="a8879a4a3869e56124428ea4bfed75ac" id="tgt31" class="tgtSentence">在左窗格中，单击“ACTIVE DIRECTORY”<ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="1d78457e80b3c77f152c8c399312bb34" id="tgt32" class="tgtSentence">在“Active Directory”页中，单击“Rights Management”<ui></ui><ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="90fb845b80cb92da481c22c0f1c5097a" id="tgt33" class="tgtSentence">选择要进行<token>aad_rightsmanagement_2</token>的待管理目录，单击<ui>“激活”</ui>，然后确认你的操作。</caps:sentence>
                  </para>
                  <alert class="note">
                    <para>
                      <caps:sentence sentenceid="5d88ab66c4715b439dc2f545d21aedd2" id="tgt34" class="tgtSentence">如果看到激活错误，则原因可能是你的服务计划或产品版本不支持 <token>aad_rightsmanagement_2</token>。</caps:sentence>
                    </para>
                    <para>
                      <caps:sentence sentenceid="f7e7aac84fd51f6b2bdb21e2323ca629" id="tgt35" class="tgtSentence">请使用 <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>主题中<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link>部分的信息来确认是否提供 RMS 支持。</caps:sentence>
                      <caps:sentence sentenceid="41b3525f168249c124096df64854dced" id="tgt36" class="tgtSentence"> 若要获取有关此问题的帮助，请发送电子邮件至 <externalLink><linkText>askipteam</linkText><linkUri>mailto:askipteam?subject=I%20cannot%20activate%20RMS</linkUri></externalLink>。</caps:sentence>
                    </para>
                  </alert>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence sentenceid="e3eb16afdbabab150c5da0ade825a14d" id="tgt37" class="tgtSentence">
                    <ui>“权限管理状态”</ui>现在应该显示<ui>“活动”</ui>，而<ui>“激活”</ui>选项将替换为<ui>“停用”</ui>。</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
        </content>
        <sections>
          <section>
            <title>
              <caps:sentence sentenceid="b4690d4e7783bb84a0b96edbfd6e2a8a" id="tgt38" class="tgtSentence">Azure 经典门户中的 Rights Management 状态值和说明</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence sentenceid="8dd500487f519d3ae467391e72780a2a" id="tgt39" class="tgtSentence">除了“活动”状态（该状态指示 Rights Management 服务已启用并可供使用）外，你可能还会看到“非活动”、“不可用”或“未授权”<ui></ui><ui></ui><ui></ui><ui></ui>。</caps:sentence>
              </para>
              <table>
                <thead>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="b2f4b464924666ba415f57c6f1dba985" id="tgt40" class="tgtSentence">状态值</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="67daf92c833c41c95db874e18fcb2786" id="tgt41" class="tgtSentence">说明</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <TD>
                      <para>
                        <ui>
                          <caps:sentence sentenceid="c76a5e84e4bdee527e274ea30c680d79" id="tgt42" class="tgtSentence">活动</caps:sentence>
                        </ui>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="b7d5d1fb2494aac47ae24f0951add2c1" id="tgt43" class="tgtSentence">
                          <token>aad_rightsmanagement_2</token> 已启用并可供使用。</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>
                          <caps:sentence sentenceid="19d3894f53ce79c3f836f26cf8a3be3b" id="tgt44" class="tgtSentence">非活动</caps:sentence>
                        </ui>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="e29b24589eca87c679cf0194ecad79c3" id="tgt45" class="tgtSentence">
                          <token>aad_rightsmanagement_2</token> 已禁用，必须先将其激活，然后组织才能保护文件。</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>
                          <caps:sentence sentenceid="7060e0481896e00b3f7d20f1e8e2749a" id="tgt46" class="tgtSentence">Unavailable</caps:sentence>
                        </ui>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="e3eb16afdbabab150c5da0ade825a14d" id="tgt47" class="tgtSentence">
                          <token>aad_rightsmanagement_2</token> 服务已关闭。</caps:sentence>
                        <caps:sentence sentenceid="12ed261dd80c65c845c736d472953791" id="tgt48" class="tgtSentence"> 请稍后重试。</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>
                          <caps:sentence sentenceid="36fd540552b3b1b34e8f0bd8897cbf1e" id="tgt49" class="tgtSentence">未授权</caps:sentence>
                        </ui>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence sentenceid="85fc8820ae2d7b3471db714b1196157e" id="tgt50" class="tgtSentence">你无权查看 <token>aad_rightsmanagement_2</token> 服务的状态。</caps:sentence>
                        <caps:sentence sentenceid="c045436ae0945b496092d2dbd7a2068f" id="tgt51" class="tgtSentence"> 例如，你的帐户已被锁定，或者你不是所选租户的全局管理员。</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </tbody>
              </table>
            </content>
          </section>
        </sections>
      </section>
      <section address="BKMK_OnboardingControls">
        <title>
          <caps:sentence sentenceid="8b4b4d674e2cc15294406e917503e80e" id="tgt52" class="tgtSentence">为分阶段部署配置加入控制</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="f4b6e91f1c8bb410c14dcf4c17e3940c" id="tgt53" class="tgtSentence">如果你不希望所有用户都能立即使用 Azure RMS 保护文件，则可以使用 <externalLink><linkText>Set-AadrmOnboardingControlPolicy</linkText><linkUri>http://msdn.microsoft.com/library/azure/dn857521.aspx</linkUri></externalLink> Windows PowerShell 命令来配置用户加入控制。</caps:sentence>
            <caps:sentence sentenceid="2f401a4a9ff4c1e5087b24b25b4e742f" id="tgt54" class="tgtSentence"> 在激活 Azure RMS 之前或之后，你可以运行此命令。</caps:sentence>
          </para>
          <alert class="important">
            <para>
              <caps:sentence sentenceid="fcafef637d89aacb685000d8af79f534" id="tgt55" class="tgtSentence">若要使用此命令，你必须安装至少 <embeddedLabel>2.1.0.0</embeddedLabel> 版的 <externalLink><linkText>Azure RMS Windows PowerShell 模块</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=257721</linkUri></externalLink>。</caps:sentence>
            </para>
            <para>
              <caps:sentence sentenceid="c62c43f7d283b2ccddec7797ae4f88de" id="tgt56" class="tgtSentence">若要查看已安装的版本，请运行：<userInput>(Get-Module aadrm –ListAvailable).Version</userInput></caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence sentenceid="44a66d8985ae4ee89785a4110a82ce7e" id="tgt57" class="tgtSentence">例如，如果出于测试目的，你最初只想让“IT 部门”组（具有对象 ID fbb99ded-32a0-45f1-b038-38b519009503）中的管理员能够保护内容，请使用以下命令：</caps:sentence>
          </para>
          <code>Set-AadrmOnboardingControlPolicy – SecurityGroupObjectId fbb99ded-32a0-45f1-b038-38b519009503</code>
          <para>
            <caps:sentence sentenceid="e9db20b887ed97caa276c4cd7c8cbd07" id="tgt58" class="tgtSentence">请注意：对于此配置选项，必须指定组，不能指定单个用户。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="022bf1cac1528f63193a4925e27b3307" id="tgt59" class="tgtSentence">或者，如果你要确保只有正确获得使用 Azure RMS 的许可的用户可以保护内容，请使用以下命令：</caps:sentence>
          </para>
          <code>Set-AadrmOnboardingControlPolicy -UseRmsUserLicense $true</code>
          <para>
            <caps:sentence sentenceid="4eabcb94a77e92c79c963eb8ae31c84d" id="tgt60" class="tgtSentence">使用这些加入控制时，组织中的所有用户始终可以使用由用户的子集保护的受保护内容，但他们自身将不能从客户端应用程序应用信息保护。</caps:sentence>
            <caps:sentence sentenceid="0e5c8a8b0624bf97b70fbc70950e64e9" id="tgt61" class="tgtSentence"> 例如，他们将在其 Office 客户端中看不到激活 Azure RMS 时自动发布的默认模板，也看不到你可能会配置的自定义模板。</caps:sentence>
            <caps:sentence sentenceid="07005bd4c19304139c0a6f681f1721d3" id="tgt62" class="tgtSentence">  服务器端应用程序（如 Exchange）可以为 RMS 集成实现自己的每用户控制，以获得相同的结果。</caps:sentence>
          </para>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence sentenceid="0a4f90ce90fc062c4fc00532513d86da" id="tgt63" class="tgtSentence">后续步骤</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="49189154f5c8ec7b288347a9cc898274" id="tgt64" class="tgtSentence">为组织激活 <token>aad_rightsmanagement_1</token>之后，向用户和管理员推出 <link xlink:href="086600c2-c5d8-47ec-a4c0-c782e1797486">Azure Rights Management Deployment Roadmap</link>之前，你可以使用 <token>aad_rightsmanagement_1</token>来检查是否还需要执行其他配置步骤。</caps:sentence>
            <caps:sentence sentenceid="d2c373441af56d1dc6f59221b55a1d0a" id="tgt65" class="tgtSentence"> 例如，你可能需要使用<externalLink><linkText>自定义模板</linkText><linkUri>http://technet.microsoft.com/library/dn642472.aspx</linkUri></externalLink>使用户更方便地向文件应用信息保护，通过安装 <externalLink><linkText>RMS 连接器</linkText><linkUri>http://technet.microsoft.com/library/dn375964.aspx</linkUri></externalLink>来连接本地服务器以使用 <token>aad_rightsmanagement_1</token>，以及部署 <externalLink><linkText>Rights Management</linkText><linkUri>http://technet.microsoft.com/library/jj585031.aspx</linkUri></externalLink> 共享应用程序，以便对所有设备上的所有文件类型进行保护。</caps:sentence>
            <caps:sentence sentenceid="70f200565c084e4a2a59dd4d06860972" id="tgt66" class="tgtSentence"> Exchange Online 和 SharePoint Online 等 Office 服务需要进行其他配置，然后才能使用其信息权限管理 (IRM) 功能。</caps:sentence>
            <caps:sentence sentenceid="b2a8c86161818cf1e3671287eb835d53" id="tgt67" class="tgtSentence"> 但是，如果不需要执行其他配置步骤，请参阅<link xlink:href="18564e4a-9364-4ed2-8f17-89d24fc0d878">Using Azure Rights Management</link>以获取操作指导，帮助你的组织成功完成部署。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="98c593e10ffacef2a76104d73fafbfc4" id="tgt68" class="tgtSentence">有关应用程序如何与 <token>aad_rightsmanagement_1</token>配合工作的信息，请参阅<link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9">How Applications Support Azure Rights Management</link>。</caps:sentence>
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
          <caps:sentence id="src1" class="srcSentence">When you activate <token>aad_rightsmanagement_1</token> (Azure RMS), your organization can start to protect important data by using applications and services that support this information protection solution.</caps:sentence>
          <caps:sentence id="src2" class="srcSentence"> Administrators can also manage and monitor protected files and emails that your organization owns.</caps:sentence>
          <caps:sentence id="src3" class="srcSentence"> You must enable <token>aad_rightsmanagement_2</token> before you can begin to use the information rights management (IRM) features within Office, SharePoint, and Exchange, and protect any sensitive or confidential file.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src4" class="srcSentence">If you want to learn more about Azure Rights Management before you activate the service—for example, what business problems it solves, some typical use cases, and how it works—see <link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link></caps:sentence>
        </para>
        <alert class="important">
          <para>
            <caps:sentence id="src5" class="srcSentence">Before you activate <token>aad_rightsmanagement_2</token>, make sure that your organization has a service plan that includes <token>aad_rightsmanagement_2</token> services.</caps:sentence>
            <caps:sentence id="src6" class="srcSentence"> If not, you will not be able to activate Azure RMS.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src7" class="srcSentence">For more information, see the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link> section in the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link> topic.</caps:sentence>
          </para>
        </alert>
        <para>
          <caps:sentence id="src8" class="srcSentence">After you have activated Azure RMS, all users in your organization can apply information protection to their files, and all users can open (consume) files that have been protected by Azure RMS.</caps:sentence>
          <caps:sentence id="src9" class="srcSentence"> However, if you prefer, you can restrict who can apply information protection, by using onboarding controls for a phased deployment.</caps:sentence>
          <caps:sentence id="src10" class="srcSentence"> For more information, see the <link xlink:href="f8707e01-b239-4d1a-a1ea-0d1cf9a8d214#BKMK_OnboardingControls">Configuring onboarding controls for a phased deployment</link> section in this topic.</caps:sentence>
        </para>
      </introduction>
      <section>
        <title>
          <caps:sentence id="src11" class="srcSentence">Activating Rights Management </caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src12" class="srcSentence">Use one of the following procedures to activate <token>aad_rightsmanagement_2</token>.</caps:sentence>
          </para>
          <alert class="tip">
            <para>
              <caps:sentence id="src13" class="srcSentence">You can also use the Windows PowerShell cmdlet, <externalLink><linkText>Enable-Aadrm</linkText><linkUri>http://msdn.microsoft.com/library/windowsazure/dn629412.aspx</linkUri></externalLink>, to activate <token>aad_rightsmanagement_2</token>.</caps:sentence>
            </para>
          </alert>
          <procedure>
            <title>
              <caps:sentence id="src14" class="srcSentence">To activate Rights Management from the Office 365 admin center</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src15" class="srcSentence">After you have signed up for an Office 365 plan that includes Rights Management, <externalLink><linkText>sign in to Office 365 with your work or school account</linkText><linkUri>https://portal.office.com/</linkUri></externalLink> that is an administrator for your Office 365 deployment.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src16" class="srcSentence">If the Office 365 admin center does not automatically display, select the app launcher icon in the upper-left and choose <ui>Admin</ui>.</caps:sentence>
                    <caps:sentence id="src17" class="srcSentence"> The <ui>Admin</ui> tile appears only to Office 365 administrators.</caps:sentence>
                  </para>
                  <alert class="tip">
                    <para>
                      <caps:sentence id="src18" class="srcSentence">For admin center help, see <externalLink><linkText>About the Office 365 admin center - Admin Help</linkText><linkUri>https://support.office.com/article/About-the-Office-365-admin-center-Admin-Help-58537702-d421-4d02-8141-e128e3703547</linkUri></externalLink>.</caps:sentence>
                    </para>
                  </alert>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src19" class="srcSentence">In the left pane, expand <ui>SERVICE SETTINGS</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src20" class="srcSentence">Click <ui>Rights Management</ui>.</caps:sentence>
                  </para>
                  <alert class="note">
                    <para>
                      <caps:sentence id="src21" class="srcSentence">If you do not see this option, it might be because your service plan or product version cannot support Rights Management, or it has not yet been upgraded to support Rights Management.</caps:sentence>
                    </para>
                    <para>
                      <caps:sentence id="src22" class="srcSentence">Use the information in the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link> section in the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link> topic to confirm support.</caps:sentence>
                      <caps:sentence id="src23" class="srcSentence"> If your service plan or product version is supported but you do not see the Rights Management option, it might be because the service is not yet upgraded.</caps:sentence>
                      <caps:sentence id="src24" class="srcSentence"> For help with this issue, send an email message to <externalLink><linkText>askipteam</linkText><linkUri>mailto:askipteam@microsoft.com?subject=I%20cannot%20activate%20RMS</linkUri></externalLink>.</caps:sentence>
                    </para>
                  </alert>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src25" class="srcSentence">On the <ui>RIGHTS MANAGEMENT</ui> page, click <ui>Manage</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src26" class="srcSentence">On the <ui>rights management</ui> page, click <ui>activate</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src27" class="srcSentence">When prompted <ui>Do you want to activate Rights Management?</ui>, click <ui>activate</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence id="src28" class="srcSentence">You should now see <ui>Rights management is activated</ui> and the option to deactivate.</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
          <procedure>
            <title>
              <caps:sentence id="src29" class="srcSentence">To activate Rights Management from the Azure classic portal</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src30" class="srcSentence">After you have signed up for your Azure account, <externalLink><linkText>sign in to the Azure classic portal</linkText><linkUri>http://go.microsoft.com/fwlink/p/?LinkID=275081</linkUri></externalLink>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src31" class="srcSentence">In the left pane, click <ui>ACTIVE DIRECTORY</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src32" class="srcSentence">From the <ui>active directory</ui> page, click <ui>RIGHTS MANAGEMENT</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src33" class="srcSentence">Select the directory to manage for <token>aad_rightsmanagement_2</token>, click <ui>ACTIVATE</ui>, and then confirm your action.</caps:sentence>
                  </para>
                  <alert class="note">
                    <para>
                      <caps:sentence id="src34" class="srcSentence">If you see an activation error, it might be because your service plan or product version cannot support <token>aad_rightsmanagement_2</token>.</caps:sentence>
                    </para>
                    <para>
                      <caps:sentence id="src35" class="srcSentence">Use the information in the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link> section in the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link> topic to confirm RMS support.</caps:sentence>
                      <caps:sentence id="src36" class="srcSentence"> For help with this issue, send an email message to <externalLink><linkText>askipteam</linkText><linkUri>mailto:askipteam?subject=I%20cannot%20activate%20RMS</linkUri></externalLink>.</caps:sentence>
                    </para>
                  </alert>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence id="src37" class="srcSentence">The <ui>RIGHTS MANAGEMENT STATUS</ui> should now display <ui>Active</ui> and the <ui>ACTIVATE</ui> option is replaced with <ui>DEACTIVATE</ui>.</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
        </content>
        <sections>
          <section>
            <title>
              <caps:sentence id="src38" class="srcSentence">Rights Management status values and descriptions in the Azure classic portal</caps:sentence>
            </title>
            <content>
              <para>
                <caps:sentence id="src39" class="srcSentence">In addition to the <ui>Active</ui> status, which indicates that the Rights Management service is enabled and ready to use, you might also see <ui>Inactive</ui>, <ui>Unavailable</ui>, or <ui>Unauthorized</ui>.</caps:sentence>
              </para>
              <table>
                <thead>
                  <tr>
                    <TD>
                      <para>
                        <caps:sentence id="src40" class="srcSentence">Status value</caps:sentence>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src41" class="srcSentence">Description</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <TD>
                      <para>
                        <ui>
                          <caps:sentence id="src42" class="srcSentence">Active</caps:sentence>
                        </ui>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src43" class="srcSentence">
                          <token>aad_rightsmanagement_2</token> is enabled and ready for use.</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>
                          <caps:sentence id="src44" class="srcSentence">Inactive</caps:sentence>
                        </ui>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src45" class="srcSentence">
                          <token>aad_rightsmanagement_2</token> is disabled and must be activated before your organization can protect files.</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>
                          <caps:sentence id="src46" class="srcSentence">Unavailable</caps:sentence>
                        </ui>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src47" class="srcSentence">The <token>aad_rightsmanagement_2</token> service is down.</caps:sentence>
                        <caps:sentence id="src48" class="srcSentence"> Try again later.</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                  <tr>
                    <TD>
                      <para>
                        <ui>
                          <caps:sentence id="src49" class="srcSentence">Unauthorized</caps:sentence>
                        </ui>
                      </para>
                    </TD>
                    <TD>
                      <para>
                        <caps:sentence id="src50" class="srcSentence">You do not have permissions to view the status of the <token>aad_rightsmanagement_2</token> service.</caps:sentence>
                        <caps:sentence id="src51" class="srcSentence"> For example, your account is locked out or you are not the global administrator for the selected tenant.</caps:sentence>
                      </para>
                    </TD>
                  </tr>
                </tbody>
              </table>
            </content>
          </section>
        </sections>
      </section>
      <section address="BKMK_OnboardingControls">
        <title>
          <caps:sentence id="src52" class="srcSentence">Configuring onboarding controls for a phased deployment</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src53" class="srcSentence">If you don’t want all users to be able to protect files immediately by using Azure RMS, you can configure user onboarding controls by using the <externalLink><linkText>Set-AadrmOnboardingControlPolicy</linkText><linkUri>http://msdn.microsoft.com/library/azure/dn857521.aspx</linkUri></externalLink> Windows PowerShell command.</caps:sentence>
            <caps:sentence id="src54" class="srcSentence"> You can run this command before or after you activate Azure RMS.</caps:sentence>
          </para>
          <alert class="important">
            <para>
              <caps:sentence id="src55" class="srcSentence">To use this command, you must have at least version <embeddedLabel>2.1.0.0</embeddedLabel> of the <externalLink><linkText>Azure RMS Windows PowerShell module</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=257721</linkUri></externalLink>.</caps:sentence>
            </para>
            <para>
              <caps:sentence id="src56" class="srcSentence">To check the version you have installed, run: <userInput>(Get-Module aadrm –ListAvailable).Version</userInput></caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence id="src57" class="srcSentence">For example, if you initially want only administrators in the “IT department” group (that has an object ID of fbb99ded-32a0-45f1-b038-38b519009503) to be able to protect content for testing purposes, use the following command:</caps:sentence>
          </para>
          <code>Set-AadrmOnboardingControlPolicy – SecurityGroupObjectId fbb99ded-32a0-45f1-b038-38b519009503</code>
          <para>
            <caps:sentence id="src58" class="srcSentence">Note that for this configuration option, you must specify a group; you cannot specify individual users.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src59" class="srcSentence">Or, if you want to ensure that only users who are correctly licensed to use Azure RMS can protect content:</caps:sentence>
          </para>
          <code>Set-AadrmOnboardingControlPolicy -UseRmsUserLicense $true</code>
          <para>
            <caps:sentence id="src60" class="srcSentence">When you use these onboarding controls, all users in the organization can always consume protected content that has been protected by your subset of users, but they won’t be able to apply information protection themselves from client applications.</caps:sentence>
            <caps:sentence id="src61" class="srcSentence"> For example, they won’t see in their Office clients the default templates that are automatically published when Azure RMS is activated, or custom templates that you might configure.</caps:sentence>
            <caps:sentence id="src62" class="srcSentence">  Server-side applications, such as Exchange, can implement their own per-user controls for RMS-integration to achieve the same result.</caps:sentence>
          </para>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence id="src63" class="srcSentence">Next steps</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src64" class="srcSentence">Now that you’ve activated <token>aad_rightsmanagement_1</token> for your organization, use the <link xlink:href="086600c2-c5d8-47ec-a4c0-c782e1797486">Azure Rights Management Deployment Roadmap</link> to check whether there are other configuration steps that you might need to do before you roll out <token>aad_rightsmanagement_1</token> to users and administrators.</caps:sentence>
            <caps:sentence id="src65" class="srcSentence"> For example, you might want to use <externalLink><linkText>custom templates</linkText><linkUri>http://technet.microsoft.com/library/dn642472.aspx</linkUri></externalLink> to make it easier for users to apply information protection to files, connect your on-premises servers to use <token>aad_rightsmanagement_1</token> by installing the <externalLink><linkText>RMS connector</linkText><linkUri>http://technet.microsoft.com/library/dn375964.aspx</linkUri></externalLink>, and deploy the <externalLink><linkText>Rights Management sharing application</linkText><linkUri>http://technet.microsoft.com/library/jj585031.aspx</linkUri></externalLink> that supports protecting all file types on all devices.</caps:sentence>
            <caps:sentence id="src66" class="srcSentence"> Office services,  such as Exchange Online and SharePoint Online require additional configuration before you can use their Information Rights Management (IRM) features.</caps:sentence>
            <caps:sentence id="src67" class="srcSentence"> However, if there are no other configuration steps that you need to do, see <link xlink:href="18564e4a-9364-4ed2-8f17-89d24fc0d878">Using Azure Rights Management</link> for operational guidance to support a successful deployment for your organization.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src68" class="srcSentence">For information about how your applications work with <token>aad_rightsmanagement_1</token>, see <link xlink:href="2cdc7bde-4044-4021-b887-11476f99afd9">How Applications Support Azure Rights Management</link>.</caps:sentence>
          </para>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="206a0bfe-0912-4e0e-aa15-484b000b264c">Configuring rights management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSSource>
</caps:SxS>
