---
description: na
keywords: na
pagetitle: Quick Start Tutorial for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1db923bf-7d19-4fdd-a413-bfeb58af5e03
---
# Azure Rights Management 快速入门教程
<?xml version="1.0" encoding="utf-8"?>
<caps:SxS xmlns:caps="http://schemas.microsoft.com/build/caps/2013/11">
  <caps:SxSTarget locale="zh-CN">
    <developerConceptualDocument xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <introduction>
        <para>
          <caps:sentence sentenceid="940649db38ed2d3f79877c600095a330" id="tgt1" class="tgtSentence">使用本教程，你可以快速试用适合你组织的 Microsoft Azure 权限管理（也称 Azure RMS），只需执行 5 个步骤，所需时间不到 15 分钟。</caps:sentence>
          <caps:sentence sentenceid="0920179cc231cc0a3c9bbdfd9bc8fc91" id="tgt2" class="tgtSentence"> 你需要激活服务，然后即可通过电子邮件将机密文档安全地发送给其他组织的人员，并可跟踪该文档何时被打开。</caps:sentence>
          <caps:sentence sentenceid="bdc778f379d69a0ea23b374ac6062c56" id="tgt3" class="tgtSentence"> 通过电子邮件发送机密文档时，该文档在传输过程中会进行加密，只能由收件人使用发件人设置的权限来打开。</caps:sentence>
        </para>
        <para>
          <mediaLinkInline>
            <image xlink:href="3c893b16-6b7c-44e5-91e2-057ef42a9932"></image>
          </mediaLinkInline>
        </para>
        <para>
          <caps:sentence sentenceid="3be089740944bc19a9c18936f5f933dc" id="tgt4" class="tgtSentence">本教程针对的是 IT 管理员和顾问，目的是帮助他们评估 Azure 权限管理的作用，看其是否适合用作组织的信息保护解决方案。</caps:sentence>
          <caps:sentence sentenceid="fb074e7efe93746706819829f0e83518" id="tgt5" class="tgtSentence"> 在生产环境中，应该由管理员按说明来激活服务，由最终用户按说明来发送文档。</caps:sentence>
          <caps:sentence sentenceid="c1c6641e1bc841168ba85af28d1f6a2e" id="tgt6" class="tgtSentence"> 这两套说明都包括在本教程中，其所展示的端到端方案说明了如何将机密文档安全地发送到其他组织的人员手中。</caps:sentence>
          <caps:sentence sentenceid="f846c98052f044a2da609584cf4e023e" id="tgt7" class="tgtSentence"> 如果你在完成本教程的过程中遇到问题，请发送电子邮件至 <externalLink><linkText>AskIPTeam</linkText><linkUri>mailto:askipteam@microsoft.com?subject=Having%20problems%20with%20the%20Quick%20Start%20tutorial</linkUri></externalLink>，我们会帮助你解决问题。</caps:sentence>
        </para>
        <para>
          <caps:sentence sentenceid="18f8f4b00a8fc67143c8dca5cd642100" id="tgt8" class="tgtSentence">若要完成本教程，你需要满足以下先决条件：</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <caps:sentence sentenceid="06409497b42cc1d884270754c6f51fe7" id="tgt9" class="tgtSentence">支持 Azure Rights Management 的订阅。</caps:sentence>
              <caps:sentence sentenceid="95ad92b9d9e75065d09a01f9d237ffaf" id="tgt10" class="tgtSentence"> 该订阅可以是付费订阅，也可以是试用订阅。</caps:sentence>
              <caps:sentence sentenceid="88bffdcfb2a69f3d5ebc4498af03da3a" id="tgt11" class="tgtSentence"> 如果你想要使用文档跟踪（本教程中的步骤 5需要使用此功能），你的订阅必须支持文档跟踪。</caps:sentence>
              <caps:sentence sentenceid="c2b2a13032c49909c5d23008d6db9bf1" id="tgt12" class="tgtSentence"> 有关订阅选项以及免费试用版链接的详细信息，请参阅 <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link>主题中的<link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link>部分。</caps:sentence>
            </para>
            <para>
              <caps:sentence sentenceid="4f28c0ce2496de27b40e7b8cb488571c" id="tgt13" class="tgtSentence">提示：如果你需要获取某个订阅，请提前进行，因为该过程有时需要一定的时间才能完成。</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence sentenceid="dd88e5ba3a73482d9babc20a680490ba" id="tgt14" class="tgtSentence">用于登录到 Office 365 管理中心或 Azure 经典门户的管理员帐户，你可以使用该帐户来激活 Rights Management 服务。</caps:sentence>
              <caps:sentence sentenceid="73362d72867645e5af7a61c63d7138ca" id="tgt15" class="tgtSentence"> 此帐户还必须有电子邮件地址和可用的电子邮件服务（例如，Exchange Online 或 Exchange Server）。</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence sentenceid="076c6001b57aa7abb308c5143aec1689" id="tgt16" class="tgtSentence">运行 Windows（最低配置为 Windows 7 SP1）并已安装 Office 2016、Office 2013 或 Office 2010 的计算机。</caps:sentence>
            </para>
          </listItem>
        </list>
        <para>
          <caps:sentence sentenceid="3b3764e5a9a94133e8d50e55941852ab" id="tgt17" class="tgtSentence">让我们开始吧。</caps:sentence>
        </para>
      </introduction>
      <section>
        <title>
          <caps:sentence sentenceid="cc8c0b753ed15fec45135ea95934ae80" id="tgt18" class="tgtSentence">步骤 1：激活权限管理服务</caps:sentence>
        </title>
        <content>
          <para>
            <mediaLinkInline>
              <image xlink:href="6b066564-3b43-43eb-999a-ce0c0cf7d25b"></image>
            </mediaLinkInline>
          </para>
          <para>
            <caps:sentence sentenceid="e3ba7687d02de29fde1527b5dfced3d8" id="tgt19" class="tgtSentence">即使你的订阅支持 Azure 权限管理，该服务在默认情况下也是禁用的。</caps:sentence>
            <caps:sentence sentenceid="e3609809d3665769a43efa8a4aa04fac" id="tgt20" class="tgtSentence"> 你可以使用 Office 365 管理中心或 Azure 经典门户来激活它：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="9d6c3d07afc0c89c2031e72a2f1ad3df" id="tgt21" class="tgtSentence">如果你有一个包含 Azure Rights Management 的 Office 365 订阅，或者虽然你的 Office 365 订阅不包含 Azure Rights Management，但你有一个包含 Azure RMS Premium 的订阅，则可执行以下操作：<embeddedLabel>使用 Office 365 管理中心</embeddedLabel>。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="050f7f3c76db401b759812886538f754" id="tgt22" class="tgtSentence">如果你没有 Office 365 订阅，则可执行以下操作：<embeddedLabel>使用 Azure 经典门户</embeddedLabel>。</caps:sentence>
              </para>
            </listItem>
          </list>
          <mediaLink>
            <image xlink:href="4c4e5cad-e22a-4bcb-81b8-4048187357f1"></image>
          </mediaLink>
          <procedure>
            <title>
              <caps:sentence sentenceid="448a932b5daf8b0098f4c07c904ee0af" id="tgt23" class="tgtSentence">从 Office 365 管理中心激活权限管理</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="45568fffc1aefb85bb60ebc96a472dda" id="tgt24" class="tgtSentence">转到 <externalLink><linkText>Office 365 门户</linkText><linkUri>https://portal.office.com/</linkUri></externalLink>，使用你的工作或学校帐户登录。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="366163a9370090bf4c891cf2b299c773" id="tgt25" class="tgtSentence">如果未自动显示 Office 365 管理中心，请选择左上方的应用程序启动程序图标，然后选择<ui>“管理”</ui>。</caps:sentence>
                    <caps:sentence sentenceid="90adbbe7112a5ab0269194573e650cc6" id="tgt26" class="tgtSentence"> “管理”<ui></ui>磁贴只会向 Office 365 管理员显示。</caps:sentence>
                  </para>
                  <alert class="tip">
                    <para>
                      <caps:sentence sentenceid="4472b591452aabf0231d9ac41fc2e859" id="tgt27" class="tgtSentence">有关管理中心的帮助，请参阅<externalLink><linkText>关于 Office 365 管理中心 - 管理员帮助</linkText><linkUri>https://support.office.com/article/About-the-Office-365-admin-center-Admin-Help-58537702-d421-4d02-8141-e128e3703547</linkUri></externalLink>。</caps:sentence>
                    </para>
                  </alert>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="1225aff0618ff618a682e6c673274bf1" id="tgt28" class="tgtSentence">在左窗格中，单击“服务设置”<ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="ccbe2a6c96a5df5e1966988e40064061" id="tgt29" class="tgtSentence">单击“权限管理”<ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="87c942eae0180b2f79691fe9cf6c988f" id="tgt30" class="tgtSentence">在“权限管理”页上，单击“管理”<ui></ui><ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="87c942eae0180b2f79691fe9cf6c988f" id="tgt31" class="tgtSentence">在“权限管理”页上，单击“激活”<ui></ui><ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="7e260026e3b6cd45c8d06073fd587d67" id="tgt32" class="tgtSentence">当提示“是否要激活权限管理?”时，请单击“激活”<ui></ui><ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence sentenceid="a9b5a907acedb28952be8ea483888cea" id="tgt33" class="tgtSentence">你现在应该看到<ui>“权限管理已激活”</ui>以及停用选项（可能需要手动刷新该页）。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="1689a3cbd42b7199556c4c080b459961" id="tgt34" class="tgtSentence">此时请勿单击<ui>“高级功能”</ui>。</caps:sentence>
                  <caps:sentence sentenceid="a2349b8f30dcf0a92bc9794c4fa9647d" id="tgt35" class="tgtSentence"> 单击该选项会将你转到可在其中配置模板的 Azure 经典门户，这些模板不是本教程所必需的。</caps:sentence>
                  <caps:sentence sentenceid="62da051cafafd321dd9d6db9c240e9ed" id="tgt36" class="tgtSentence"> 与之相反，你可以关闭 Office 365 管理中心。</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
          <procedure>
            <title>
              <caps:sentence sentenceid="5377d3bbb754ec4b89ea810b7974f3d0" id="tgt37" class="tgtSentence">从 Azure 门户激活权限管理</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="45568fffc1aefb85bb60ebc96a472dda" id="tgt38" class="tgtSentence">转到 <externalLink><linkText>Azure 经典门户</linkText><linkUri>http://go.microsoft.com/fwlink/p/?LinkID=275081</linkUri></externalLink>并登录。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="a8879a4a3869e56124428ea4bfed75ac" id="tgt39" class="tgtSentence">在左窗格中，单击“ACTIVE DIRECTORY”<ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="1d78457e80b3c77f152c8c399312bb34" id="tgt40" class="tgtSentence">在“Active Directory”页中，单击“Rights Management”<ui></ui><ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="90fb845b80cb92da481c22c0f1c5097a" id="tgt41" class="tgtSentence">为<token>aad_rightsmanagement_2</token>选择要管理的目录，单击“激活”，然后确认你的操作<ui></ui>。</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence sentenceid="e3eb16afdbabab150c5da0ade825a14d" id="tgt42" class="tgtSentence">
                    <ui>“权限管理状态”</ui>现在应该显示<ui>“活动”</ui>，而<ui>“激活”</ui>选项将替换为<ui>“停用”</ui>。</caps:sentence>
                </para>
                <para>
                  <caps:sentence sentenceid="a3007566b05d1bce8572c8ee408df81a" id="tgt43" class="tgtSentence">虽然你可以在门户中配置 Rights Management 的其他选项，但这些选项不是本教程所必需的，因此可关闭 Azure 经典门户。</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
          <para>
            <caps:sentence sentenceid="7336afa5bd557a56736dfcf11d128e34" id="tgt44" class="tgtSentence">此第一步只需执行这些操作。</caps:sentence>
            <caps:sentence sentenceid="08e4786f7ebfbf32720556445cf8c6a1" id="tgt45" class="tgtSentence"> 激活此服务后，你组织中的所有用户就可以对重要的和敏感的文档进行保护。</caps:sentence>
            <caps:sentence sentenceid="124041334946a8fab343a0c8ecdd46f4" id="tgt46" class="tgtSentence"> 在生产环境中，你可能需要对谁能在开始的时候执行此操作进行限制，以方便分阶段部署。</caps:sentence>
            <caps:sentence sentenceid="b5f46da1bc79a0a2d8c6c5b39723a685" id="tgt47" class="tgtSentence"> 不过，本教程不需要这样。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="3a32eb87f38f4bc71c98b6ea47ad8e49" id="tgt48" class="tgtSentence">进行生产部署时，你可能还需要配置自定义模板，当然本教程不包含此部分内容。</caps:sentence>
            <caps:sentence sentenceid="21aa1cdacf8582b9c9065bf5facc1ded" id="tgt49" class="tgtSentence"> 在需要对文件进行保护时，用户可以使用模板更快速、轻松地应用正确的设置。</caps:sentence>
            <caps:sentence sentenceid="8ed4fb1a651d5e7ddb6a0d190d1fdff3" id="tgt50" class="tgtSentence"> 激活权限管理时，你将自动获得 2 个默认的模板，而在生产环境中，你可能需要使用自己的自定义模板对这些模板进行补充。</caps:sentence>
            <caps:sentence sentenceid="fc76b095107642f0ca25f26a635c0ff4" id="tgt51" class="tgtSentence"> 但本教程不需要模板，因此你可以转到下一步。</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="3595f5ce672f7f50c9aed66fb85c26d6" id="tgt52" class="tgtSentence">如果你想了解更多信息</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="4eec452dee7d15acfb78a023b487bf19" id="tgt53" class="tgtSentence">其他信息</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="1a5b1978cfe523b64bc27b5d993aa6f0" id="tgt54" class="tgtSentence">关于如何激活权限管理以后如何在激活该服务后控制谁能对文件和电子邮件进行保护   →</caps:sentence>
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
                    <caps:sentence sentenceid="df561e4fb1699a8e2c2eafac28794afc" id="tgt55" class="tgtSentence">关于默认模板以及如何创建新的自定义模板   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <link xlink:href="1775d8d0-9a59-42c8-914f-ce285b71ac1c">Configuring Custom Templates for Azure Rights Management</link>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence sentenceid="9d0326859653ad60d213770a943d75be" id="tgt56" class="tgtSentence">步骤 2：安装权限管理共享应用程序</caps:sentence>
        </title>
        <content>
          <para>
            <mediaLinkInline>
              <image xlink:href="56ac1537-75ba-453b-b65a-ff12ebe1f468"></image>
            </mediaLinkInline>
          </para>
          <para>
            <caps:sentence sentenceid="309ef3a79b3ad1ec018931a0c503c1bd" id="tgt57" class="tgtSentence">权限管理共享应用程序（也称"RMS 共享应用程序"）不是 Azure 权限管理所必需的，但我们建议将其用于支持 Azure 权限管理的所有计算机和移动设备。</caps:sentence>
            <caps:sentence sentenceid="e0ef3721a07cfd0fbcd46eed9494d671" id="tgt58" class="tgtSentence"> 通过安装 Office 加载项，RMS 共享应用程序可与 Office 应用程序集成在一起，使得用户能够轻松地从功能区直接保护文件。</caps:sentence>
            <caps:sentence sentenceid="e17093f9e55ba9730e6ca7252ff79ce1" id="tgt59" class="tgtSentence"> 此外，它还可以向本来不受 Azure 权限管理支持的文件应用常规保护，从而保护所有文件类型，并可为用户设置一个文档跟踪站点，方便其跟踪和撤销受保护的文件。</caps:sentence>
            <caps:sentence sentenceid="8e4759049decbb8cb4e664199d9c2e5c" id="tgt60" class="tgtSentence"> 我们将在本教程的后面部分用到文档跟踪站点。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="8630ad71c26f4a3dddfa6823fa6d1a3c" id="tgt61" class="tgtSentence">此应用程序可免费下载，并可针对生产环境进行脚本化安装。</caps:sentence>
            <caps:sentence sentenceid="60e99bafe4b630e513fb2d8e1ef3a10b" id="tgt62" class="tgtSentence"> 不过就本教程来说，我们将在本地安装它。</caps:sentence>
          </para>
          <mediaLink>
            <image xlink:href="01e1ff01-4bca-4690-b8f1-9e8fe2a784b1"></image>
          </mediaLink>
          <procedure>
            <title>
              <caps:sentence sentenceid="3cf4cc52a998b14c5c7984a40033c719" id="tgt63" class="tgtSentence">下载并安装权限管理共享应用程序</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="45568fffc1aefb85bb60ebc96a472dda" id="tgt64" class="tgtSentence">转到 Microsoft 网站上的 <externalLink><linkText>Microsoft 权限管理</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=303970</linkUri></externalLink>页。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="004dc0ceb5e9b2247446dc0a40f7a169" id="tgt65" class="tgtSentence">在<ui>“计算机”</ui>部分，单击<ui>“适用于 Windows 的 RMS 应用程序”</ui>图标，然后保存用于安装 Microsoft 权限管理共享应用程序的 <ui>Setup.exe</ui> 文件。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="19541cec65c563b2a81abd4f25b5cfc1" id="tgt66" class="tgtSentence">若要进行本地安装，你必须使用管理员帐户运行已下载的 Setup.exe 文件。</caps:sentence>
                    <caps:sentence sentenceid="3128d0949f78aa053b17854e1f2b00a7" id="tgt67" class="tgtSentence"> 如果系统提示你继续，请单击<ui>“是”</ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="87c942eae0180b2f79691fe9cf6c988f" id="tgt68" class="tgtSentence">在<ui>“安装 Microsoft RMS”</ui>页上，单击<ui>“下一步”</ui>，然后等待安装完成。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="18765a5ae99adebe7a46f76546a62af2" id="tgt69" class="tgtSentence">安装完成后，请单击<ui>“重新启动”</ui>（如果系统提示你重新启动计算机），或单击<ui>“关闭”</ui>完成安装。</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence sentenceid="61b9d2e9fec05c79a2530e1e7c2d9300" id="tgt70" class="tgtSentence">现在，你可以开始对那些你希望只与指定人员共享其中所含信息的文件进行保护。</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="3595f5ce672f7f50c9aed66fb85c26d6" id="tgt71" class="tgtSentence">如果你想了解更多信息</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="4eec452dee7d15acfb78a023b487bf19" id="tgt72" class="tgtSentence">其他信息</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="c12bbfe2430f0c1b13805dce370dd79b" id="tgt73" class="tgtSentence">关于适用于 Windows 的权限管理共享应用程序的本地安装以及用户说明   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence sentenceid="5a82d1d6328fcf4e332c7353808716e6" id="tgt74" class="tgtSentence">权限管理共享应用程序用户指南</caps:sentence>
                      </linkText>
                      <linkUri>http://technet.microsoft.com/library/dn339006.aspx</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="d6cb8af2e8a6ad24853418285ccacf0a" id="tgt75" class="tgtSentence">关于适用于 Windows 的权限管理共享应用程序的脚本化安装以及更多技术信息   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence sentenceid="45fd73cece8c888a3560a65a749417d4" id="tgt76" class="tgtSentence">权限管理共享应用程序管理员指南</caps:sentence>
                      </linkText>
                      <linkUri>http://technet.microsoft.com/library/dn339003.aspx</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="30a40f5b787f839eb427ce1bd224b165" id="tgt77" class="tgtSentence">了解本机保护和常规保护的区别   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="9af7c117d9de9a06fba7a5f1ea5fcc2d" id="tgt78" class="tgtSentence">
                      <externalLink>
                        <linkText>常规保护和内置（本机）保护的区别是什么？</linkText>
                        <linkUri>https://technet.microsoft.com/library/dn574738.aspx</linkUri>
                      </externalLink> </caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence sentenceid="dae3cc7b2a8ab82b58e3a9260fa3f23a" id="tgt79" class="tgtSentence">步骤 3：通过电子邮件发送要保护的文档</caps:sentence>
        </title>
        <content>
          <para>
            <mediaLinkInline>
              <image xlink:href="5faba8d1-045d-4caa-b34d-b408a61e6a3b"></image>
            </mediaLinkInline>
          </para>
          <para>
            <caps:sentence sentenceid="128d32e17c480180133a110ad331ee04" id="tgt80" class="tgtSentence">就这一步来说，首先请使用 Word 创建并保存一个文档，该文档就是你需要保护的文档，你可以将其命名为 <system>Confidential.docx</system>。</caps:sentence>
            <caps:sentence sentenceid="f0c8a130b00ad2808cc262607a411ab2" id="tgt81" class="tgtSentence"> 就本教程来说，该文档实际包含什么文本并不重要，而之所以需要让其包含一些文本，是为了方便你确认所授权的收件人能够阅读它。</caps:sentence>
            <caps:sentence sentenceid="e3e9dbea6e58dd0c90c8f3d887e672e8" id="tgt82" class="tgtSentence"> 例如，你可以键入：<userInputLocalizable>如果你可以阅读电子邮件附件中的此内容，则说明发件人已通过 Azure RMS 成功共享了受保护的文件。</userInputLocalizable></caps:sentence> </para>
          <para>
            <caps:sentence sentenceid="5cb437e4d9f3a6da6c201ce03109975c" id="tgt83" class="tgtSentence">然后你就可以安全地通过电子邮件共享此文档。</caps:sentence>
          </para>
          <mediaLink>
            <image xlink:href="4243c4fb-517d-4f4a-a80a-c0ff470947aa"></image>
          </mediaLink>
          <procedure>
            <title>
              <caps:sentence sentenceid="bcb13b7c8b46696e92a923ed291328d2" id="tgt84" class="tgtSentence">通过电子邮件安全地共享你的文档</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="034dbf0405a7eebedf1777787602cfb3" id="tgt85" class="tgtSentence">使用 Outlook 创建一封新邮件，然后将你刚创建的文件添加到附件中。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="004dc0ceb5e9b2247446dc0a40f7a169" id="tgt86" class="tgtSentence">在<ui>“收件人”</ui>框中，键入一个或多个业务电子邮件地址。</caps:sentence>
                    <caps:sentence sentenceid="cc8ec0be727f5f8539a75d2e3443228d" id="tgt87" class="tgtSentence"> 请务必指定业务电子邮件地址，例如 <userInput>janetm@contoso.com</userInput> 或 <userInput>p.dover@fabrikam.com</userInput>，因为 Azure Rights Management 目前不支持 Internet 提供商提供的可在家里使用的个人电子邮件地址。</caps:sentence>
                    <caps:sentence sentenceid="5bc3e9009ccb35ae4a97658b485ddf2f" id="tgt88" class="tgtSentence"> 请不要担心你向其发送电子邮件的人是否也有 Azure 权限管理。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="2a1eb836964dab56865b4f4f468eb5fc" id="tgt89" class="tgtSentence">键入一个主题，例如<userInputLocalizable>“机密文档”</userInputLocalizable>，然后键入简短的电子邮件内容，例如<userInputLocalizable>“请阅读此机密文档，不要与其他人共享。”</userInputLocalizable></caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="ecf5ae4c8bc3e81193563be55f7666e7" id="tgt90" class="tgtSentence">然后，在<ui>“RMS”</ui>组的<ui>“消息”</ui>选项卡中，单击<ui>“共享保护项”</ui>，然后再次单击<ui>“共享保护项”</ui>：</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="004dc0ceb5e9b2247446dc0a40f7a169" id="tgt91" class="tgtSentence">在<ui>“共享保护项”</ui>对话框中，执行以下操作：</caps:sentence>
                  </para>
                  <list class="ordered">
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="3d28822ef6b543a688f36f914f7304b4" id="tgt92" class="tgtSentence">选择<ui>“查看者 – 仅查看”</ui>。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="c8617a6ec5cd1f4b8bb1305b9e6fa54d" id="tgt93" class="tgtSentence">这意味着收件人能够查看该文档，但不能进行编辑或打印。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="3d28822ef6b543a688f36f914f7304b4" id="tgt94" class="tgtSentence">选择<ui>“当有人尝试打开这些文档时，给我发电子邮件”</ui>。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="a4d002603767dc3ffee4b81d295924e1" id="tgt95" class="tgtSentence">每次收件人尝试打开该附件时，你都会收到电子邮件通知。另外，如果其他人尝试打开该附件（例如，收件人将电子邮件转发给同事），你也会收到电子邮件通知。</caps:sentence>
                        <caps:sentence sentenceid="6aca58314a95c1d66a9732674611f219" id="tgt96" class="tgtSentence"> 在最后这种情况中，你会看到访问被拒绝，你可以根据用户详细信息来决定是否向该人发送一份允许其打开的文档。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="3d28822ef6b543a688f36f914f7304b4" id="tgt97" class="tgtSentence">选择<ui>“允许我立即撤消对这些文档的访问权限”</ui>。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="317dc6bc9d9a0929dc75fe1f759ca37c" id="tgt98" class="tgtSentence">此选项要求收件人每次打开该附件时都要有 Internet 连接，但好处是，如果你在以后撤销该文档，则收件人下次将无法打开它。</caps:sentence>
                        <caps:sentence sentenceid="2d678561414d7eb3f9e42f9ab631c4e8" id="tgt99" class="tgtSentence"> 如果你不选择此选项，则收件人在没有 Internet 连接的情况下也可以打开该文档，但坏处是，如果你在以后撤销该文档，则可能需要延迟一段时间才能生效。</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence sentenceid="ccbe2a6c96a5df5e1966988e40064061" id="tgt100" class="tgtSentence">单击<ui>“立即发送”</ui>。</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence sentenceid="c608f94063c8cd9710c1af26bc67e4c0" id="tgt101" class="tgtSentence">将向你所指定的电子邮件地址发送带附件的电子邮件。</caps:sentence>
                        <caps:sentence sentenceid="e3202adc8887884e5790b333916f512a" id="tgt102" class="tgtSentence"> 除了你的电子邮件，他们还会看到有关如何阅读受 Azure 权限管理保护的附加文档的说明。</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </content>
              </step>
            </steps>
          </procedure>
          <para>
            <caps:sentence sentenceid="fd227d01baa0b756476a5e55c55cd841" id="tgt103" class="tgtSentence">现在，你已发送受保护文档，你可以要求收件人等待该文档，在其到达后打开它。</caps:sentence>
            <caps:sentence sentenceid="6edd3e6faf9adecfa1ea51744b54c4a6" id="tgt104" class="tgtSentence"> 但请勿关闭 Outlook，因为我们需要在最后一步再次使用它来跟踪该附件。</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="3595f5ce672f7f50c9aed66fb85c26d6" id="tgt105" class="tgtSentence">如果你想了解更多信息</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="4eec452dee7d15acfb78a023b487bf19" id="tgt106" class="tgtSentence">其他信息</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="d7ff14043f5dd045a491ffaee66fcec2" id="tgt107" class="tgtSentence">有关保护通过电子邮件进行共享的文件的完整说明和替代方法   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence sentenceid="c3f04f5507167fd0366fa7d88b0c1ad2" id="tgt108" class="tgtSentence">使用权限管理共享应用程序保护通过电子邮件进行共享的文件</caps:sentence>
                      </linkText>
                      <linkUri>https://technet.microsoft.com/library/dn574735.aspx</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="04723f2e0aecf9bb30ee26662714873b" id="tgt109" class="tgtSentence">关于<ui>“共享保护项”</ui>对话框中的选项   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence sentenceid="13cef8b13123a7c436788f60855c4248" id="tgt110" class="tgtSentence">权限管理共享应用程序的的对话框选项</caps:sentence>
                      </linkText>
                      <linkUri>https://technet.microsoft.com/library/dn574738.aspx</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence sentenceid="abd3311922c5dca4140aeccbc679ce20" id="tgt111" class="tgtSentence">步骤 4：要求收件人打开通过电子邮件发送的文档</caps:sentence>
        </title>
        <content>
          <para>
            <mediaLinkInline>
              <image xlink:href="a0705091-4f9d-4d41-897b-b99e6000e006"></image>
            </mediaLinkInline>
          </para>
          <para>
            <caps:sentence sentenceid="e4b87e713ac76a7489edf6e71d1d252c" id="tgt112" class="tgtSentence">收件人可以使用很多设备来阅读你以电子邮件附件形式发送的受保护文档。</caps:sentence>
            <caps:sentence sentenceid="f293df5c84168f5317a26f965fd34e8a" id="tgt113" class="tgtSentence"> 这些设备包括 iPad、iPhone、Android 平板电脑和手机、Mac 计算机，以及 Windows 计算机。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="37212e4d35d929941350285ae004355f" id="tgt114" class="tgtSentence">要求他们阅读你发送的电子邮件。</caps:sentence>
            <caps:sentence sentenceid="428cf1f28216fd28b82ce04473cae3de" id="tgt115" class="tgtSentence"> 他们会看到你的电子邮件，而在此之前，他们会看到以下文本：</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="9af7c117d9de9a06fba7a5f1ea5fcc2d" id="tgt116" class="tgtSentence">
              <ui>发件人已使用 Microsoft RMS 保护了附件。你必须</ui>
              <externalLink>
                <linkText>登录</linkText>
                <linkUri>http://aka.ms/rms</linkUri>
              </externalLink>
              <ui>才能打开它们。</ui> </caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="25851d87b86378a5f9a0dc12c1bd63d2" id="tgt117" class="tgtSentence">当他们单击此链接时，会显示相关说明，告知他们如何安装 RMS 共享应用程序，以及如何在必要时注册免费的帐户。</caps:sentence>
            <caps:sentence sentenceid="831f9947c2f3082b73f8bf72f06a6fa4" id="tgt118" class="tgtSentence"> 该免费帐户提供个人 RMS 订阅，因此可确保被授权的用户始终能够阅读受保护的文档，即使其组织没有 Azure RMS。</caps:sentence>
            <caps:sentence sentenceid="c6ea192ef05750cbfd52acd943ae5a4c" id="tgt119" class="tgtSentence"> 然后，他们就可以根据以下说明阅读受保护的附件。</caps:sentence>
          </para>
          <mediaLink>
            <image xlink:href="f370d881-a296-417a-8905-c32a8d8ac9bb"></image>
          </mediaLink>
          <procedure>
            <title>
              <caps:sentence sentenceid="5dd3fb02a42121176525edd1a9e5dfd9" id="tgt120" class="tgtSentence">查看受保护的文档附件</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="940507240ca116990a45520084144e68" id="tgt121" class="tgtSentence">由于 Azure 权限管理对 Word 文档进行了保护，因此该电子邮件有两个附件。</caps:sentence>
                    <caps:sentence sentenceid="58e24f2a3eec8a1ae54a7bc603f09ded" id="tgt122" class="tgtSentence"> 这实际上是同一文件的两个版本，仅文件扩展名不同。</caps:sentence>
                    <caps:sentence sentenceid="168572d44fb652d9ac384892fb7fb731" id="tgt123" class="tgtSentence"> 打开文件扩展名为 <system>.ppdf</system> 的版本 (<system>Confidential.ppdf</system>)。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="9b938708247dfae36be39cdef3ebd3b2" id="tgt124" class="tgtSentence">如果你设备上的 <externalLink><linkText>Office 版本支持权限管理</linkText><linkUri>https://technet.microsoft.com/library/dn655136.aspx#BKMK_SupportedApplications</linkUri></externalLink>，你可以打开该文件的其他版本 (<system>Confidential.docx</system>)，让其在 Word 中打开。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="2bb0ad84150e128501de2fc72cb401ce" id="tgt125" class="tgtSentence">如果系统提示你输入用户名和密码，请在输入用户名时采用与发送电子邮件和附件时所用电子邮件地址相同的格式。</caps:sentence>
                    <caps:sentence sentenceid="4eee3758f1bf4073d94deae936dd0a13" id="tgt126" class="tgtSentence"> 例如，<userInput>janetm@contoso.com</userInput> 或 <userInput>p.dover@fabrikam.com</userInput>。</caps:sentence>
                    <caps:sentence sentenceid="53b9bd351140021d2610e63d8ebbb96a" id="tgt127" class="tgtSentence"> 至于密码，请键入注册个人 RMS 时提供的密码。</caps:sentence>
                    <caps:sentence sentenceid="e2b4f294763a716d07225abcdf2f2ec0" id="tgt128" class="tgtSentence"> 如果你的组织有 Azure RMS，则也可输入通常的工作密码。</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence sentenceid="fdf3b3a333944e357a5ab268357c7e5a" id="tgt129" class="tgtSentence">此时该文档会打开，你可以阅读其内容。</caps:sentence>
                  <caps:sentence sentenceid="fb83ca99976f93fd63e5860f02865ddf" id="tgt130" class="tgtSentence"> 例如，文档内容可能是：<userInputLocalizable>如果你可以阅读电子邮件附件中的此内容，则说明发件人已通过 Azure RMS 成功共享了受保护的文件。</userInputLocalizable>由于该文档为只读文档，因此无法更改其内容。</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
          <para>
            <caps:sentence sentenceid="e73262e68fb7fcb96df76692b6d3a88e" id="tgt131" class="tgtSentence">你也可以要求收件人将电子邮件转发给没有包括在你的原始电子邮件中的其他人，此为可选步骤。</caps:sentence>
            <caps:sentence sentenceid="d90b403e84515bacfd9a02d80c9c15da" id="tgt132" class="tgtSentence"> 即使这些其他人所工作的组织有 Azure 权限管理，或者这些人申请了自己的个人 RMS 订阅，他们也无法打开该附件。</caps:sentence>
            <caps:sentence sentenceid="6461861f4baec8190ac6153053a070fb" id="tgt133" class="tgtSentence"> 当系统要求他们提供用户名时，将会拒绝其对文档的访问。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="e6c8ec70c679659fff8526017e0f53bf" id="tgt134" class="tgtSentence">现在，收件人已打开该附件并选择性地将其转发给他人，因此正常情况下你会获得电子邮件通知，该通知会报告此活动。</caps:sentence>
            <caps:sentence sentenceid="d3b2402b65c7a730c1db650c8b5e873e" id="tgt135" class="tgtSentence"> 不过，时间越长，电子邮件越不容易查找，因此若要跟踪谁访问了你的文档，更好的方法是使用文档跟踪站点，这会在最后一步进行介绍。</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="3595f5ce672f7f50c9aed66fb85c26d6" id="tgt136" class="tgtSentence">如果你想了解更多信息</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="4eec452dee7d15acfb78a023b487bf19" id="tgt137" class="tgtSentence">其他信息</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="bc48e37909f8c825f0eced9bf688c455" id="tgt138" class="tgtSentence">关于如何查看受 Azure 权限管理保护的文件的完整说明   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence sentenceid="5027005987755a9b1503b04f02dab7d8" id="tgt139" class="tgtSentence">查看和使用受权限管理保护的文件</caps:sentence>
                      </linkText>
                      <linkUri>https://technet.microsoft.com/library/dn574741.aspx</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="d114ce5efd05466e03b15e0bd0208813" id="tgt140" class="tgtSentence">关于免费订阅：个人 RMS   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <link xlink:href="2efcb440-fefd-45e9-872b-f471573aadf2">RMS for Individuals and Azure Rights Management</link>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="e0271e7fc8aa8c7997a4262e12d26b45" id="tgt141" class="tgtSentence">关于你所看到的两个版本的电子邮件附件文件   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence sentenceid="2b34d2d7b1575556df73d94c4d931762" id="tgt142" class="tgtSentence">自动创建的 .ppdf 文件是什么文件？</caps:sentence>
                      </linkText>
                      <linkUri>https://technet.microsoft.com/library/dn574738.aspx</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence sentenceid="283e27696cc8a6f684c81f9a3dceb07f" id="tgt143" class="tgtSentence">步骤 5：跟踪受保护文档</caps:sentence>
        </title>
        <content>
          <para>
            <mediaLinkInline>
              <image xlink:href="3d1ce494-490f-4493-8158-523ecda40fae"></image>
            </mediaLinkInline>
          </para>
          <alert class="note">
            <para>
              <caps:sentence sentenceid="2a6afe33ce452b7635c80e7642551f2a" id="tgt144" class="tgtSentence">就此步骤来说，你必须有一个支持文档跟踪的订阅。</caps:sentence>
              <caps:sentence sentenceid="112070a095650c7d700d1d4f78c766e9" id="tgt145" class="tgtSentence"> 若要查看你的订阅是否包括文档跟踪，请参阅<externalLink><linkText>权限管理服务 (RMS) 各项功能的比较</linkText><linkUri>https://technet.microsoft.com/dn858608.aspx</linkUri></externalLink>。</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence sentenceid="ec84999fa8b806b91646d2526da5858c" id="tgt146" class="tgtSentence">虽然此步骤为可选步骤，但大多数人都想知道其所发送的附件是否被打开、何时被打开甚至从何处打开。</caps:sentence>
            <caps:sentence sentenceid="4be0bb25039056347740ae85bcda324d" id="tgt147" class="tgtSentence"> 例如：</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence sentenceid="873504c32f68ebb54eb9cd7ffabe1b1e" id="tgt148" class="tgtSentence">你希望某人能在指定的时间内进行回应，但你从文档跟踪站点了解到，虽然截止时间快到了，但她并没有打开该文档。</caps:sentence>
                <caps:sentence sentenceid="09d9cfcfdaab5180c143d6717908ed8b" id="tgt149" class="tgtSentence"> 你给她发送跟进电子邮件或打电话提醒她。</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence sentenceid="0802a85de9177a132199b8720de5dad7" id="tgt150" class="tgtSentence">在看到有人打开了该文档后，你继续跟进，询问她是否有任何问题，或者是否需要其他信息。</caps:sentence>
              </para>
            </listItem>
          </list>
          <mediaLink>
            <image xlink:href="5b799166-171f-45dc-91b8-3f4c3c2992a8"></image>
          </mediaLink>
          <procedure>
            <title>
              <caps:sentence sentenceid="99209045ec0bd1e1d5007c5649ebf3bd" id="tgt151" class="tgtSentence">跟踪受保护文档</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="1608b68925db9fb206daaf6d38c11c6f" id="tgt152" class="tgtSentence">使用 Outlook 时，请在<ui>“RMS”</ui>组的<ui>“主页”</ui>选项卡上，单击<ui>“跟踪使用情况”</ui>。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="6b032de11adfc83f9a38a579b0903157" id="tgt153" class="tgtSentence">如果你看到<ui>“按你的方式保护和共享”</ui>页，请单击<ui>“登录”</ui>，然后再次提供用户名和密码。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="87c942eae0180b2f79691fe9cf6c988f" id="tgt154" class="tgtSentence">在<ui>“你的共享文档”</ui>页上，你会看到附加到电子邮件中的文档 <system>Confidential.docx</system>。</caps:sentence>
                    <caps:sentence sentenceid="f3af7f349f69efe702dbf4e531cf20d5" id="tgt155" class="tgtSentence"> 此时，该文档是唯一显示的文件，但当你共享更多的受保护文档时，此列表会扩大。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="aec33280b797530e720e2c9b9792de01" id="tgt156" class="tgtSentence">在此页上，你会看到你何时共享了该文档（何时发送了带受保护附件的电子邮件）、上次活动的日期，以及你向其发送电子邮件的收件人的名称。</caps:sentence>
                    <caps:sentence sentenceid="431e7f5e4d2334ab658b0529a1c50bd9" id="tgt157" class="tgtSentence"> 单击文档名可获取更多详细信息。</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence sentenceid="2483d7acc987ef9d255137893351cee8" id="tgt158" class="tgtSentence">在新页（包含你所单击的文件的名称）上，你只会看到该文档的摘要详细信息，以及可供文档使用的其他选项的列表（<ui>“列表”</ui>、<ui>“时间线”</ui>、<ui>“映射”</ui>、<ui>“设置”</ui>）。</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence sentenceid="758b4c85fdd069358f6b639f6ce7f655" id="tgt159" class="tgtSentence">单击每个选项，了解如何使用不同的方式来跟踪受保护文档。</caps:sentence>
                    <caps:sentence sentenceid="5c5b6166a1df0e9d362ffe25f6ec9ca5" id="tgt160" class="tgtSentence"> 此外，你也可以在<ui>“摘要”</ui>页上单击<ui>“在 Excel 中打开”</ui>以将信息导出到电子表格，或者单击<ui>“撤消访问权限”</ui>以停止共享该文档。</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence sentenceid="c5cf16c86c527b1005890671dd108d57" id="tgt161" class="tgtSentence">你可以返回此站点来跟踪受保护文档的更多活动，或者根据需要撤消访问权限。</caps:sentence>
                  <caps:sentence sentenceid="1f0af725682649ba2ba21b243e3eb9a9" id="tgt162" class="tgtSentence"> 你甚至可以通过移动设备或平板电脑来访问该站点，只需使用浏览器访问以下链接即可：<externalLink><linkText>文档跟踪</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=529562</linkUri></externalLink></caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="3595f5ce672f7f50c9aed66fb85c26d6" id="tgt163" class="tgtSentence">如果你想了解更多信息</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence sentenceid="4eec452dee7d15acfb78a023b487bf19" id="tgt164" class="tgtSentence">其他信息</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="c356f6bf8a346c0e7cb6483ddb57f1b4" id="tgt165" class="tgtSentence">关于文档跟踪的完整说明   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence sentenceid="08e07c08a82f9e8ba0aa6af551660dd1" id="tgt166" class="tgtSentence">使用 RMS 共享应用程序跟踪和撤销文档</caps:sentence>
                      </linkText>
                      <linkUri>https://technet.microsoft.com/library/dn986611.aspx</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="b2ea99effd4ed45b46b1b29377c18ef7" id="tgt167" class="tgtSentence">说明并演示文档跟踪的两分钟视频   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence sentenceid="359f977b97a00d540b44bcfc1c2c01f7" id="tgt168" class="tgtSentence">Azure RMS 文档跟踪和撤销</caps:sentence>
                      </linkText>
                      <linkUri>http://channel9.msdn.com/Series/Information-Protection/Azure-RMS-Document-Tracking-and-Revocation</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence sentenceid="a0c75e43ab29adce4875806462967e5c" id="tgt169" class="tgtSentence">有关疑难解答和客户方面的问题   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence sentenceid="1ea15bf16350f6bd7bee6a3388afa295" id="tgt170" class="tgtSentence">文档跟踪常见问题</caps:sentence>
                      </linkText>
                      <linkUri>https://technet.microsoft.com/dn947488</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence sentenceid="0a4f90ce90fc062c4fc00532513d86da" id="tgt171" class="tgtSentence">后续步骤</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence sentenceid="b54608b6581cf4e69aee32f02473f011" id="tgt172" class="tgtSentence">本教程为你逐步演示了一个方案，即如果通过 Azure RMS 来帮助保护你的数据。</caps:sentence>
            <caps:sentence sentenceid="5ef9e95be322ba34a00d67b44f2c324a" id="tgt173" class="tgtSentence"> 若要查看其他常见用途，请参阅<link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link>这篇文章的<externalLink><linkText>运行中的 Azure RMS</linkText><linkUri>https://technet.microsoft.com/library/jj585026.aspx#BKMK_RMSpictures</linkUri></externalLink> 部分。</caps:sentence>
            <caps:sentence sentenceid="8f110d2b6c26a7c4deaf5743edaf6076" id="tgt174" class="tgtSentence"> 你可能还会发现这篇文章中的其他部分也很有用，例如 Azure RMS 的工作原理以及它能够解决哪些业务问题。</caps:sentence>
          </para>
          <para>
            <caps:sentence sentenceid="85c60260bc8c3d1857711e31a9706dbe" id="tgt175" class="tgtSentence">当你做好开始部署 Azure RMS 的准备时，请通过 <link xlink:href="086600c2-c5d8-47ec-a4c0-c782e1797486">Azure Rights Management Deployment Roadmap</link>获取部署步骤和操作说明链接。</caps:sentence>
          </para>
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
          <caps:sentence id="src1" class="srcSentence">Use this tutorial to quickly try out Microsoft Azure Rights Management (also known as Azure RMS) for your organization with just 5 steps that should take you less than 15 minutes.</caps:sentence>
          <caps:sentence id="src2" class="srcSentence"> You’ll activate the service, securely send a confidential document by email to somebody in another organization, and then be able to track when that document is opened.</caps:sentence>
          <caps:sentence id="src3" class="srcSentence"> When the confidential document is emailed, it is encrypted while in transit and can be read only by the person it is sent to, using the permissions that are set by the sender.</caps:sentence>
        </para>
        <para>
          <mediaLinkInline>
            <image xlink:href="3c893b16-6b7c-44e5-91e2-057ef42a9932"></image>
          </mediaLinkInline>
        </para>
        <para>
          <caps:sentence id="src4" class="srcSentence">This tutorial is aimed at IT administrators and consultants, to help them evaluate Azure Rights Management as an information protection solution for an organization.</caps:sentence>
          <caps:sentence id="src5" class="srcSentence"> In a production environment, the instructions to activate the service would be done by an administrator and the instructions to send the document would be done by end users.</caps:sentence>
          <caps:sentence id="src6" class="srcSentence"> Both sets of instructions are included in this tutorial, to demonstrate the end-to-end scenario of securely sending a confidential document to somebody in another organization.</caps:sentence>
          <caps:sentence id="src7" class="srcSentence"> If you have any problems completing this tutorial, send an email message to <externalLink><linkText>AskIPTeam</linkText><linkUri>mailto:askipteam@microsoft.com?subject=Having%20problems%20with%20the%20Quick%20Start%20tutorial</linkUri></externalLink> and we will help you out.</caps:sentence>
        </para>
        <para>
          <caps:sentence id="src8" class="srcSentence">To complete this tutorial, you will need the following:</caps:sentence>
        </para>
        <list class="bullet">
          <listItem>
            <para>
              <caps:sentence id="src9" class="srcSentence">A subscription that supports Azure Rights Management .</caps:sentence>
              <caps:sentence id="src10" class="srcSentence"> This can be a paid subscription or a trial subscription.</caps:sentence>
              <caps:sentence id="src11" class="srcSentence"> If you want to use document tracking, which is required for step 5 in this tutorial, your subscription must support document tracking.</caps:sentence>
              <caps:sentence id="src12" class="srcSentence"> For more information about the subscription options and links to free trials, see the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb#BKMK_SupportedSubscriptions">Cloud subscriptions that support Azure RMS</link> section in the <link xlink:href="dc78321d-d759-4653-8818-80da74b6cdeb">Requirements for Azure Rights Management</link> topic.</caps:sentence>
            </para>
            <para>
              <caps:sentence id="src13" class="srcSentence">Tip: If you need to get a subscription, do this in advance because this process can sometimes take a while to complete.</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence id="src14" class="srcSentence">An administrator account to sign in to the Office 365 admin center or the Azure classic portal, so that you can activate the Rights Management service.</caps:sentence>
              <caps:sentence id="src15" class="srcSentence"> This account must also have an email address and a working email service (for example, Exchange Online or Exchange Server).</caps:sentence>
            </para>
          </listItem>
          <listItem>
            <para>
              <caps:sentence id="src16" class="srcSentence">A computer running Windows (minimum of Windows 7 SP1), and which has installed either Office 2016, Office 2013, or Office 2010.</caps:sentence>
            </para>
          </listItem>
        </list>
        <para>
          <caps:sentence id="src17" class="srcSentence">Let’s get started.</caps:sentence>
        </para>
      </introduction>
      <section>
        <title>
          <caps:sentence id="src18" class="srcSentence">Step 1: Activate the Rights Management service</caps:sentence>
        </title>
        <content>
          <para>
            <mediaLinkInline>
              <image xlink:href="6b066564-3b43-43eb-999a-ce0c0cf7d25b"></image>
            </mediaLinkInline>
          </para>
          <para>
            <caps:sentence id="src19" class="srcSentence">Even though you might have a subscription that supports Azure Rights Management, the service is disabled by default.</caps:sentence>
            <caps:sentence id="src20" class="srcSentence"> To activate it, you can use either the Office 365 admin center, or the Azure classic portal:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src21" class="srcSentence">If you have an Office 365 subscription that includes Azure Rights Management, or an Office 365 subscription that excludes Azure Rights Management but you have a subscription for Azure RMS Premium: <embeddedLabel>Use the Office 365 admin center</embeddedLabel>.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src22" class="srcSentence">If you do not have an Office 365 subscription: <embeddedLabel>Use the Azure classic portal</embeddedLabel>.</caps:sentence>
              </para>
            </listItem>
          </list>
          <mediaLink>
            <image xlink:href="4c4e5cad-e22a-4bcb-81b8-4048187357f1"></image>
          </mediaLink>
          <procedure>
            <title>
              <caps:sentence id="src23" class="srcSentence">To activate Rights Management from the Office 365 admin center</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src24" class="srcSentence">Go to the <externalLink><linkText>Office 365 portal</linkText><linkUri>https://portal.office.com/</linkUri></externalLink> and sign in with your work or school account.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src25" class="srcSentence">If the Office 365 admin center does not automatically display, select the app launcher icon in the upper-left and choose <ui>Admin</ui>.</caps:sentence>
                    <caps:sentence id="src26" class="srcSentence"> The <ui>Admin</ui> tile appears only to Office 365 administrators.</caps:sentence>
                  </para>
                  <alert class="tip">
                    <para>
                      <caps:sentence id="src27" class="srcSentence">For admin center help, see <externalLink><linkText>About the Office 365 admin center - Admin Help</linkText><linkUri>https://support.office.com/article/About-the-Office-365-admin-center-Admin-Help-58537702-d421-4d02-8141-e128e3703547</linkUri></externalLink>.</caps:sentence>
                    </para>
                  </alert>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src28" class="srcSentence">In the left pane, expand <ui>SERVICE SETTINGS</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src29" class="srcSentence">Click <ui>Rights Management</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src30" class="srcSentence">On the <ui>RIGHTS MANAGEMENT</ui> page, click <ui>Manage</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src31" class="srcSentence">On the <ui>rights management</ui> page, click <ui>activate</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src32" class="srcSentence">When prompted <ui>Do you want to activate Rights Management?</ui>, click <ui>activate</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence id="src33" class="srcSentence">You should now see <ui>Rights management is activated</ui> and the option to deactivate (you might need to manually refresh the page)</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src34" class="srcSentence">At this time, do not click <ui>advanced features</ui>.</caps:sentence>
                  <caps:sentence id="src35" class="srcSentence"> This takes you to the Azure classic portal where you can configure templates, which are not needed for this tutorial.</caps:sentence>
                  <caps:sentence id="src36" class="srcSentence"> Instead, you can close the Office 365 admin center.</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
          <procedure>
            <title>
              <caps:sentence id="src37" class="srcSentence">To activate Rights Management from the Azure portal</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src38" class="srcSentence">Go to the <externalLink><linkText>Azure classic portal</linkText><linkUri>http://go.microsoft.com/fwlink/p/?LinkID=275081</linkUri></externalLink> and sign in.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src39" class="srcSentence">In the left pane, click <ui>ACTIVE DIRECTORY</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src40" class="srcSentence">From the <ui>active directory</ui> page, click <ui>RIGHTS MANAGEMENT</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src41" class="srcSentence">Select the directory to manage for <token>aad_rightsmanagement_2</token>, click <ui>ACTIVATE</ui>, and then confirm your action.</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence id="src42" class="srcSentence">The <ui>RIGHTS MANAGEMENT STATUS</ui> should now display <ui>Active</ui> and the <ui>ACTIVATE</ui> option is replaced with <ui>DEACTIVATE</ui>.</caps:sentence>
                </para>
                <para>
                  <caps:sentence id="src43" class="srcSentence">Although you can configure other options for Rights Management in the portal, these are not needed for this tutorial, so you can close the Azure classic portal.</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
          <para>
            <caps:sentence id="src44" class="srcSentence">That’s all you need to do for this first step.</caps:sentence>
            <caps:sentence id="src45" class="srcSentence"> The service is activated so all users in your organization can now start to protect important and sensitive documents.</caps:sentence>
            <caps:sentence id="src46" class="srcSentence"> In a production environment, you might want to restrict who can do this initially, for a phased rollout.</caps:sentence>
            <caps:sentence id="src47" class="srcSentence"> But it’s not necessary for this tutorial.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src48" class="srcSentence">Although not included here, for a production deployment, you probably will also probably want to configure custom templates.</caps:sentence>
            <caps:sentence id="src49" class="srcSentence"> Templates make it easier for users to quickly apply the right settings when they need to protect files.</caps:sentence>
            <caps:sentence id="src50" class="srcSentence"> When you activate Rights Management, you automatically get 2 default templates and it’s likely you will want to supplement these with your own custom templates in a production environment.</caps:sentence>
            <caps:sentence id="src51" class="srcSentence"> But templates are not needed for this tutorial, so you’re ready to go to the next step.</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src52" class="srcSentence">If you want more information</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src53" class="srcSentence">Additional information</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src54" class="srcSentence">About activating Rights Management and controlling who can protect files and email when the service is activated   →</caps:sentence>
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
                    <caps:sentence id="src55" class="srcSentence">About the default templates and how to create new, custom templates   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <link xlink:href="1775d8d0-9a59-42c8-914f-ce285b71ac1c">Configuring Custom Templates for Azure Rights Management</link>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence id="src56" class="srcSentence">Step 2: Install the Rights Management sharing application</caps:sentence>
        </title>
        <content>
          <para>
            <mediaLinkInline>
              <image xlink:href="56ac1537-75ba-453b-b65a-ff12ebe1f468"></image>
            </mediaLinkInline>
          </para>
          <para>
            <caps:sentence id="src57" class="srcSentence">The Rights Management sharing application (also known as the “RMS sharing app”) isn’t a requirement for Azure Rights Management, but we recommend it for all computers and mobile devices that support Azure Rights Management.</caps:sentence>
            <caps:sentence id="src58" class="srcSentence"> The RMS sharing application integrates with Office applications by installing an Office add-in so that users can easily protect files directly from the ribbon.</caps:sentence>
            <caps:sentence id="src59" class="srcSentence"> It also makes it possible to protect all files types by applying generic protection for files that are not natively supported by Azure Rights Management, and a document tracking site for users to track and revoke files that they have protected.</caps:sentence>
            <caps:sentence id="src60" class="srcSentence"> We’ll be using the document tracking site later in this tutorial.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src61" class="srcSentence">This application is free to download and offers a scripted install for production environments.</caps:sentence>
            <caps:sentence id="src62" class="srcSentence"> But for this tutorial, we’ll install it locally.</caps:sentence>
          </para>
          <mediaLink>
            <image xlink:href="01e1ff01-4bca-4690-b8f1-9e8fe2a784b1"></image>
          </mediaLink>
          <procedure>
            <title>
              <caps:sentence id="src63" class="srcSentence">To download and install the Rights Management sharing application</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src64" class="srcSentence">Go to the <externalLink><linkText>Microsoft Rights Management</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=303970</linkUri></externalLink> page on the Microsoft website.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src65" class="srcSentence">In the <ui>Computers</ui> section, click the icon for the <ui>RMS app for Windows</ui> and save the <ui>Setup.exe</ui> file to install the Microsoft Rights Management sharing application.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src66" class="srcSentence">For a local install, you must use an administrator account to run the Setup.exe file that was downloaded.</caps:sentence>
                    <caps:sentence id="src67" class="srcSentence"> If you are prompted to continue, click <ui>Yes</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src68" class="srcSentence">On the <ui>Setup Microsoft RMS</ui> page, click <ui>Next</ui>, and wait for the installation to finish.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src69" class="srcSentence">When the installation finishes, click <ui>Restart</ui> if prompted to restart your computer, or click  <ui>Close</ui> to complete the installation.</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence id="src70" class="srcSentence">You’re now ready to start protecting files that contain information that you want to share but only with the people that you specify.</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src71" class="srcSentence">If you want more information</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src72" class="srcSentence">Additional information</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src73" class="srcSentence">About a local installation of the Rights Management sharing application for Windows and user instructions   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence id="src74" class="srcSentence">Rights Management sharing application user guide</caps:sentence>
                      </linkText>
                      <linkUri>http://technet.microsoft.com/library/dn339006.aspx</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src75" class="srcSentence">About the scripted installation of the Rights Management sharing application for Windows and more technical information   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence id="src76" class="srcSentence">Rights Management sharing application administrator guide</caps:sentence>
                      </linkText>
                      <linkUri>http://technet.microsoft.com/library/dn339003.aspx</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src77" class="srcSentence">To understand the difference between native protection and generic protection   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src78" class="srcSentence">
                      <externalLink>
                        <linkText>What’s the difference between generic protection and built-in (native) protection?</linkText>
                        <linkUri>https://technet.microsoft.com/library/dn574738.aspx</linkUri>
                      </externalLink> </caps:sentence>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence id="src79" class="srcSentence">Step 3: Email your document that you want to protect</caps:sentence>
        </title>
        <content>
          <para>
            <mediaLinkInline>
              <image xlink:href="5faba8d1-045d-4caa-b34d-b408a61e6a3b"></image>
            </mediaLinkInline>
          </para>
          <para>
            <caps:sentence id="src80" class="srcSentence">For this step, first create and save a document using Word that will represent your document that you want to protect, and name it <system>Confidential.docx</system>.</caps:sentence>
            <caps:sentence id="src81" class="srcSentence"> For this tutorial, it doesn’t matter what text it actually contains, but you will want it to contain some text so you can more easily confirm that the authorized recipient could read it.</caps:sentence>
            <caps:sentence id="src82" class="srcSentence"> For example, you might type: <userInputLocalizable>If you can read this from your email attachment, the sender has successfully shared a file that was protected with Azure RMS.</userInputLocalizable></caps:sentence> </para>
          <para>
            <caps:sentence id="src83" class="srcSentence">You’re then ready to safely share this document by email.</caps:sentence>
          </para>
          <mediaLink>
            <image xlink:href="4243c4fb-517d-4f4a-a80a-c0ff470947aa"></image>
          </mediaLink>
          <procedure>
            <title>
              <caps:sentence id="src84" class="srcSentence">To safely share your document by email</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src85" class="srcSentence">Using Outlook, create a new message and attach the file that you just created.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src86" class="srcSentence">In the <ui>To</ui> box, type one or more business email addresses.</caps:sentence>
                    <caps:sentence id="src87" class="srcSentence"> Make sure you specify a business email address, such as <userInput>janetm@contoso.com</userInput> or <userInput>p.dover@fabrikam.com</userInput> because currently, Azure Rights Management doesn’t support personal email addresses that you might use at home from your Internet provider.</caps:sentence>
                    <caps:sentence id="src88" class="srcSentence"> Don’t worry about whether the person you’re sending it to also has Azure Rights Management or not.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src89" class="srcSentence">Type a subject, such as  <userInputLocalizable>Confidential document</userInputLocalizable> and then type a short message for the email, such as <userInputLocalizable>Please read this confidential document and do not share it with others.</userInputLocalizable></caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src90" class="srcSentence">Then, on the <ui>Message</ui> tab, in the <ui>RMS</ui> group, click <ui>Share Protected</ui> and then click <ui>Share Protected</ui> again:</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src91" class="srcSentence">In the <ui>share protected</ui> dialog box:</caps:sentence>
                  </para>
                  <list class="ordered">
                    <listItem>
                      <para>
                        <caps:sentence id="src92" class="srcSentence">Select <ui>Viewer – View Only</ui>.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src93" class="srcSentence">This means our recipients will be able to view the document but not edit or print it.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src94" class="srcSentence">Select <ui>Email me when somebody tries to open these documents</ui>.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src95" class="srcSentence">You’ll get an email notification each time the recipients try to open the attachment, and also if somebody else tries to open it—for example, your recipient forwards the email to co-worker.</caps:sentence>
                        <caps:sentence id="src96" class="srcSentence"> In this last scenario, you’ll see that access was denied and from the user details, you can decide whether to send that person a copy of the document that they can open.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src97" class="srcSentence">Select <ui>Allow me to instantly revoke access to these documents</ui>.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src98" class="srcSentence">This option requires the recipients to have an Internet connection each time they open the attachment but with the benefit that if you later revoke the document, the next time they try to open it, they will not be able to.</caps:sentence>
                        <caps:sentence id="src99" class="srcSentence"> If you do not select this option, the recipients might be able to open it even without an Internet connection but with the disadvantage that if you later revoke the document, there might be a delay for when that takes effect.</caps:sentence>
                      </para>
                    </listItem>
                    <listItem>
                      <para>
                        <caps:sentence id="src100" class="srcSentence">Click <ui>Send Now</ui>.</caps:sentence>
                      </para>
                      <para>
                        <caps:sentence id="src101" class="srcSentence">The email with attachment is sent to the email addresses that you specified.</caps:sentence>
                        <caps:sentence id="src102" class="srcSentence"> In addition to your email message, they will see instructions how to read the attached document that is protected by Azure Rights Management.</caps:sentence>
                      </para>
                    </listItem>
                  </list>
                </content>
              </step>
            </steps>
          </procedure>
          <para>
            <caps:sentence id="src103" class="srcSentence">Now you’ve sent your protected document, you’re ready to ask your recipients to wait for it to arrive and then open it.</caps:sentence>
            <caps:sentence id="src104" class="srcSentence"> But don’t close Outlook, because we’ll use it again in our final step to track the attachment.</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src105" class="srcSentence">If you want more information</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src106" class="srcSentence">Additional information</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src107" class="srcSentence">Full instructions and alternative methods for protecting files that you share by email   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence id="src108" class="srcSentence">Protect a file that you share by email by using the Rights Management sharing application</caps:sentence>
                      </linkText>
                      <linkUri>https://technet.microsoft.com/library/dn574735.aspx</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src109" class="srcSentence">About the options in the <ui>share protected</ui> dialog box   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence id="src110" class="srcSentence">Dialog box options for the Rights Management sharing application</caps:sentence>
                      </linkText>
                      <linkUri>https://technet.microsoft.com/library/dn574738.aspx</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence id="src111" class="srcSentence">Step 4: Ask your recipients to open the emailed document</caps:sentence>
        </title>
        <content>
          <para>
            <mediaLinkInline>
              <image xlink:href="a0705091-4f9d-4d41-897b-b99e6000e006"></image>
            </mediaLinkInline>
          </para>
          <para>
            <caps:sentence id="src112" class="srcSentence">Your recipients can use many devices to read the protected document that you sent as an email attachment.</caps:sentence>
            <caps:sentence id="src113" class="srcSentence"> The devices include iPads, iPhones, Android tablets and phones, Mac computers, as well as Windows computers.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src114" class="srcSentence">Ask them to read the email message that you sent.</caps:sentence>
            <caps:sentence id="src115" class="srcSentence"> They will see your email message and before that, the following text:</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src116" class="srcSentence">
              <ui>The sender has protected the attachments with Microsoft RMS. You must</ui> <externalLink><linkText>sign in</linkText><linkUri>http://aka.ms/rms</linkUri></externalLink> <ui>to open them.</ui> </caps:sentence>
          </para>
          <para>
            <caps:sentence id="src117" class="srcSentence">When they click the link, it takes them to instructions to install the RMS sharing app and if necessary, sign up for a free account.</caps:sentence>
            <caps:sentence id="src118" class="srcSentence"> The free account grants them a subscription for RMS for individuals, which ensures that authorized users can always read a protected document, even if their organization does not have Azure RMS.</caps:sentence>
            <caps:sentence id="src119" class="srcSentence"> They are then ready to read the protected attachment by using the following instructions.</caps:sentence>
          </para>
          <mediaLink>
            <image xlink:href="f370d881-a296-417a-8905-c32a8d8ac9bb"></image>
          </mediaLink>
          <procedure>
            <title>
              <caps:sentence id="src120" class="srcSentence">To view the protected document attachment</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src121" class="srcSentence">Because Azure Rights Management protected a Word document, there are two attachments for the email message.</caps:sentence>
                    <caps:sentence id="src122" class="srcSentence"> These are actually two versions of the same file but with different file name extensions.</caps:sentence>
                    <caps:sentence id="src123" class="srcSentence"> Open the version that has the <system>.ppdf</system> file name extension (<system>Confidential.ppdf</system>).</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src124" class="srcSentence">If you have a version of <externalLink><linkText>Office on your device that supports Rights Management</linkText><linkUri>https://technet.microsoft.com/library/dn655136.aspx#BKMK_SupportedApplications</linkUri></externalLink>, you can open the other version of the file (<system>Confidential.docx</system>), so that it opens in Word.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src125" class="srcSentence">If you are prompted for your user name and password, enter your user name in the same format as the email address that was used to send you the email and attachment.</caps:sentence>
                    <caps:sentence id="src126" class="srcSentence"> For example, <userInput>janetm@contoso.com</userInput> or <userInput>p.dover@fabrikam.com</userInput>.</caps:sentence>
                    <caps:sentence id="src127" class="srcSentence"> For your password, type the password that you supplied when you signed up for RMS for individuals.</caps:sentence>
                    <caps:sentence id="src128" class="srcSentence"> Or, if your organization has Azure RMS, enter your usual work password.</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence id="src129" class="srcSentence">The document opens and you can now read the contents.</caps:sentence>
                  <caps:sentence id="src130" class="srcSentence"> For example, it might say <userInputLocalizable>If you can read this from your email attachment, the sender has successfully shared a file that was protected with Azure RMS.</userInputLocalizable> Because it’s read-only, you cannot change the contents.</caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
          <para>
            <caps:sentence id="src131" class="srcSentence">As an optional step, you could ask your recipient to forward the email to other people that you didn’t include in your original email.</caps:sentence>
            <caps:sentence id="src132" class="srcSentence"> Even if those other people work for an organization that has Azure Rights Management or they apply for their own RMS for individuals subscription, they won’t be able to open the attachment.</caps:sentence>
            <caps:sentence id="src133" class="srcSentence"> When they are promoted for their user name, access to the document will be denied.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src134" class="srcSentence">Now that the recipient has opened the attachment and optionally, forwarded it to somebody else, expect to get an email notification that reports this activity.</caps:sentence>
            <caps:sentence id="src135" class="srcSentence"> But email messages are easy to lose over time, so a better way to track who accessed your document is to use the document tracking site, which is covered in the final step.</caps:sentence>
          </para>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src136" class="srcSentence">If you want more information</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src137" class="srcSentence">Additional information</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src138" class="srcSentence">Full instructions for viewing files that are protected by Azure Rights Management   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence id="src139" class="srcSentence">View and use files that have been protected by Rights Management</caps:sentence>
                      </linkText>
                      <linkUri>https://technet.microsoft.com/library/dn574741.aspx</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src140" class="srcSentence">About the free subscription, RMS for individuals   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <link xlink:href="2efcb440-fefd-45e9-872b-f471573aadf2">RMS for Individuals and Azure Rights Management</link>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src141" class="srcSentence">About the two versions of the file that you see attached to the email message   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence id="src142" class="srcSentence">What’s the .ppdf file that’s automatically created?</caps:sentence>
                      </linkText>
                      <linkUri>https://technet.microsoft.com/library/dn574738.aspx</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence id="src143" class="srcSentence">Step 5: Track your protected document</caps:sentence>
        </title>
        <content>
          <para>
            <mediaLinkInline>
              <image xlink:href="3d1ce494-490f-4493-8158-523ecda40fae"></image>
            </mediaLinkInline>
          </para>
          <alert class="note">
            <para>
              <caps:sentence id="src144" class="srcSentence">For this step, you must have a subscription that supports document tracking.</caps:sentence>
              <caps:sentence id="src145" class="srcSentence"> To check whether your subscription includes document tracking, see <externalLink><linkText>Comparison of Rights Management Services (RMS) Offerings</linkText><linkUri>https://technet.microsoft.com/dn858608.aspx</linkUri></externalLink>.</caps:sentence>
            </para>
          </alert>
          <para>
            <caps:sentence id="src146" class="srcSentence">This step is optional, but most people like to know if the attachment they sent to people has been opened, when, and even from where.</caps:sentence>
            <caps:sentence id="src147" class="srcSentence"> For example:</caps:sentence>
          </para>
          <list class="bullet">
            <listItem>
              <para>
                <caps:sentence id="src148" class="srcSentence">You’re expecting a response from somebody by a specified time and you can see from the document tracking site that she hasn’t opened the document even though the deadline is approaching.</caps:sentence>
                <caps:sentence id="src149" class="srcSentence"> You send her a follow-up email or telephone her as a timely reminder.</caps:sentence>
              </para>
            </listItem>
            <listItem>
              <para>
                <caps:sentence id="src150" class="srcSentence">After seeing that somebody has opened the document, you follow up to ask her if she has any questions or requires additional information.</caps:sentence>
              </para>
            </listItem>
          </list>
          <mediaLink>
            <image xlink:href="5b799166-171f-45dc-91b8-3f4c3c2992a8"></image>
          </mediaLink>
          <procedure>
            <title>
              <caps:sentence id="src151" class="srcSentence">To track your protected document</caps:sentence>
            </title>
            <steps class="ordered">
              <step>
                <content>
                  <para>
                    <caps:sentence id="src152" class="srcSentence">Using Outlook, on the <ui>Home</ui> tab, in the <ui>RMS</ui> group, click <ui>Track Usage</ui>.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src153" class="srcSentence">If you see the <ui>Protect and share on your terms</ui> page, click <ui>Sign in</ui> and supply your user name and password again.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src154" class="srcSentence">On the <ui>Your shared documents</ui> page, you’ll see the document that you attached to the email, <system>Confidential.docx</system>.</caps:sentence>
                    <caps:sentence id="src155" class="srcSentence"> At this point, it’s the only file displayed but as you share additional protected documents, the list will grow.</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src156" class="srcSentence">From this page, you’ll see when you shared the document (when you sent the email with the protected attachment), the date of the last activity, and the name of the recipient you sent the email to.</caps:sentence>
                    <caps:sentence id="src157" class="srcSentence"> Click the document name for additional details.</caps:sentence>
                  </para>
                </content>
              </step>
              <step>
                <content>
                  <para>
                    <caps:sentence id="src158" class="srcSentence">On the new page, which has the name of the file that you clicked, you’ll see summary details for that document only, and a list of other options that are available for the document (<ui>List</ui>, <ui>Timeline</ui>, <ui>Map</ui>, <ui>Settings</ui>).</caps:sentence>
                  </para>
                  <para>
                    <caps:sentence id="src159" class="srcSentence">Click each option to explore different ways to track your protected document.</caps:sentence>
                    <caps:sentence id="src160" class="srcSentence"> Or, still on the <ui>Summary</ui> page, click <ui>Open in Excel</ui> to export the information to a spreadsheet, or click <ui>Revoke access</ui> to stop sharing the document.</caps:sentence>
                  </para>
                </content>
              </step>
            </steps>
            <conclusion>
              <content>
                <para>
                  <caps:sentence id="src161" class="srcSentence">You can return to this site to track further activity for your protected document, or revoke access if necessary.</caps:sentence>
                  <caps:sentence id="src162" class="srcSentence"> You can even access the site from your mobile device or tablet, by using a browser with this link: <externalLink><linkText>document tracking</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=529562</linkUri></externalLink></caps:sentence>
                </para>
              </content>
            </conclusion>
          </procedure>
          <table>
            <thead>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src163" class="srcSentence">If you want more information</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <caps:sentence id="src164" class="srcSentence">Additional information</caps:sentence>
                  </para>
                </TD>
              </tr>
            </thead>
            <tbody>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src165" class="srcSentence">Full instructions for tracking your documents   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence id="src166" class="srcSentence">Track and revoke your documents when you use the RMS sharing application</caps:sentence>
                      </linkText>
                      <linkUri>https://technet.microsoft.com/library/dn986611.aspx</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src167" class="srcSentence">Two minute video that explains and shows document tracking   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence id="src168" class="srcSentence">Azure RMS Document Tracking and Revocation</caps:sentence>
                      </linkText>
                      <linkUri>http://channel9.msdn.com/Series/Information-Protection/Azure-RMS-Document-Tracking-and-Revocation</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
              <tr>
                <TD>
                  <para>
                    <caps:sentence id="src169" class="srcSentence">For troubleshooting and customer questions   →</caps:sentence>
                  </para>
                </TD>
                <TD>
                  <para>
                    <externalLink>
                      <linkText>
                        <caps:sentence id="src170" class="srcSentence">FAQ for Document Tracking</caps:sentence>
                      </linkText>
                      <linkUri>https://technet.microsoft.com/dn947488</linkUri>
                    </externalLink>
                  </para>
                </TD>
              </tr>
            </tbody>
          </table>
        </content>
      </section>
      <section>
        <title>
          <caps:sentence id="src171" class="srcSentence">Next Steps</caps:sentence>
        </title>
        <content>
          <para>
            <caps:sentence id="src172" class="srcSentence">This tutorial stepped you through just one scenario for how Azure RMS can help protect your data.</caps:sentence>
            <caps:sentence id="src173" class="srcSentence"> To see other common uses, see the <externalLink><linkText>Azure RMS in action</linkText><linkUri>https://technet.microsoft.com/library/jj585026.aspx#BKMK_RMSpictures</linkUri></externalLink> section from the <link xlink:href="aeeebcd7-6646-4405-addf-ee1cc74df5df">What is Azure Rights Management?</link> article.</caps:sentence>
            <caps:sentence id="src174" class="srcSentence"> There are other sections in this article that you might also find useful, such as how Azure RMS works and what business problems it can solve.</caps:sentence>
          </para>
          <para>
            <caps:sentence id="src175" class="srcSentence">If you’re ready to start deploying Azure RMS, use the <link xlink:href="086600c2-c5d8-47ec-a4c0-c782e1797486">Azure Rights Management Deployment Roadmap</link> for your deployment steps and links for how-to instructions.</caps:sentence>
          </para>
        </content>
      </section>
      <relatedTopics>
        <link xlink:href="5214667c-ec69-42ca-8bbf-8cb22da8c62e">Getting Started with Azure Rights Management</link>
      </relatedTopics>
    </developerConceptualDocument>
  </caps:SxSSource>
</caps:SxS>