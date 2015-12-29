---
description: na
keywords: na
pagetitle: Azure 权限管理的信息和支持
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 7cc73d92-27d6-49ff-a8ab-2fae73519b4b
---
# Azure 权限管理的信息和支持
使用以下资源获取有关 Microsoft [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] (Azure RMS) 的其他信息。

|要执行的操作…|.. 采取的措施：|
|-----------|-------------|
|… 阅读最新 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 产品文档 →|使用 [Azure Rights Management](../Topic/Azure_Rights_Management.md) 的 TechNet 文档库|
|… 提供有关文档的反馈或咨询有关文档的问题 →|发送电子邮件至 [askipteam](mailto: askipteam@microsoft.com?subject=Documentation%20feedback)|
|… 接收有关 Rights Management 的推文，以及来自产品组的关于文档更新的公告 →|跟踪帮助领导 Microsoft 权限管理团队的 Dan Plastina 的动态。 参阅 [Dan Plastina @TheRMSGuy](https://twitter.com/TheRMSGuy)|
|… 获取 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 试用版 →|[注册获取免费 30 天试用](https://portal.microsoftonline.com/Signup/MainSignUp15.aspx?&amp;OfferId=A43415D3-404C-4df3-B31B-AAD28118A778&amp;dl=RIGHTSMANAGEMENT&amp;ali=1)|
以下部分提供有关 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 的更多信息：

-   [Search the documentation library](../Topic/Information_and_Support_for_Azure_Rights_Management.md#BKMK_SearchTips)

-   [Downloadable documentation](../Topic/Information_and_Support_for_Azure_Rights_Management.md#BKMK_Download)

-   [The Rights Management product group blog](../Topic/Information_and_Support_for_Azure_Rights_Management.md#BKMK_ProductGroupBlog)

-   [Support options and community resources](../Topic/Information_and_Support_for_Azure_Rights_Management.md#BKMK_SupportOptions)

## <a name="BKMK_SearchTips"></a>搜索文档库
[使用这种限定范围的搜索查询](http://www.bing.com/search?q=%28"Rights%20Management"%29%20site:technet.microsoft.com/library%20meta:search.MSCategory%28jj619159%29)查找 TechNet 库中的文档，范围限定为 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]。

该查询的搜索范围不包括关于 Active Directory 权限管理服务 (AD RMS)、Windows 权限管理或社区资源的结果。 你可将 URL 中的“权限管理”字符串替换为自己的搜索字符串，从而进一步缩小搜索结果范围。

### 示例搜索
[使用此搜索查询](http://www.bing.com/search?q=%28"Rights%20Management"%29%20site:technet.microsoft.com/library%20meta:search.MSCategory%28jj619159%29)，然后使用以下示例自定义搜索。

-   单个搜索字符串：若要搜索包含搜索字符串“RMS 连接器”的主题，请将“Rights Management”替换为“RMS 连接器”：

    ```
    ("RMS connector") site:technet.microsoft.com/library meta:search.MSCategory(jj619159)
    ```

-   合并搜索字符串：若要搜索同时包含搜索字符串“Exchange”和“SharePoint”的主题，请使用 **AND** 运算符：

    ```
    ("Exchange") AND ("SharePoint") site:technet.microsoft.com/library meta:search.MSCategory(jj619159)
    ```

-   可选搜索字符串：若要搜索包含搜索字符串“Exchange”或“SharePoint”的主题，请使用 **OR** 运算符：

    ```
    ("Exchange" OR "SharePoint") site:technet.microsoft.com/library meta:search.MSCategory(jj619159)
    ```

-   排除搜索字符串：若要搜索包含搜索字符串“Exchange”的主题并排除有关“SharePoint”的主题，请使用 **NOT** 运算符：

    ```
    ("Exchange)" NOT ("SharePoint") site:technet.microsoft.com/library meta:search.MSCategory(jj619159)
    ```

### 搜索提示
使用以下搜索提示可帮助你找到需要的信息：

-   搜索正式文档时，请使用与你在用户界面 (UI) 和 TechNet 文档中看到的内容相匹配的搜索词，而不要使用你可能会在社区内容中看到的非正式术语或缩写。 例如，应搜索“Azure 权限管理”，而不是“AADRMS”或这种云服务的其他非正式缩写。 虽然你可能经常听到和看到“RMS”，但它的全称是“权限管理服务”，因此在查找正式文档时，应尝试搜索“权限管理”而不是“RMS”。 你可以使用 [Azure 权限管理术语](../Topic/Terminology_for_Azure_Rights_Management.md)来帮助识别专用于 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 的正式术语。

-   当你在 TechNet 中的页面上进行搜索（按 Ctrl-F，然后在“查找”框中输入搜索词）时，搜索结果不包括折叠部分中的文本。 若要搜索折叠部分中的文本，请在搜索页面之前展开这些部分。 为此，你可以单击页面顶部的“全部展开”按钮，或者双击任何折叠部分。 所有部分都展开之后，页面搜索操作将会搜索该页面上的所有部分。

-   在可能的情况下，请使用 TechNet 联机库，而不要使用下载文档。 TechNet 联机库包含最新信息，而下载文档可能不包含你要搜索的信息。此外，还可能有一些联机更正或添加的信息。

-   如果你认为搜索本地存储的文档更加简单快捷，可以选择 TechNet 上的多个主题，并将它们保存到本地。 有关详细信息，请参阅下一部分。

## <a name="BKMK_Download"></a>可下载文档
你可以下载 TechNet 页面并将它们保存到本地 — 例如将它们保存为 PDF 文件，在没有 Internet 连接时在笔记本电脑、平板电脑或手机上阅读。 也可以自行添加注解并打印信息。 使用这种方法，你可以将一组特定任务或某个端到端方案所需的主题汇集到一起，有效地创建自己的白皮书或项目文档。

此方法适用于 TechNet 上的所有文档库，而不仅是 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]。

#### 从 TechNet 下载文档：

1.  登录到 TechNet。

2.  在你要保存到本地的页面的顶部，单击“导出”（在“打印”旁边）。

    然后你可以看到“导出多组页面”横幅，你可通过它添加和删除要保存的页面。

3.  单击“管理网页”以导出页面。

有关更多信息，请单击横幅上的“帮助”。

> [!NOTE]
> 由于 TechNet 上的信息经常更新，因此请尽可能使用联机版本，以确保获取最新信息。
> 
> 你可以使用 [Microsoft Rights Management (RMS) 团队博客和文档标记](http://blogs.technet.com/b/rms/archive/tags/docs/)上的每月文档公告，检查你以前下载的 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 主题现在是否已修订，以及进行了哪些更改。

## <a name="BKMK_ProductGroupBlog"></a>权限管理产品组博客
Rights Management 产品组使用 [Microsoft Rights Management (RMS) 团队博客](http://blogs.technet.com/b/rms/)，为你提供技术信息以及有关 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]、AD RMS 和相关技术的其他新闻。 这些博客文章可为产品文档和技术支持信息提供补充。

> [!TIP]
> 如果你要为 Azure RMS 或 AD RMS 开发应用程序，你可能还会对 [Active Directory Rights Management 服务 (AD RMS) 开发人员活动角博客](http://blogs.msdn.com/b/rms/)感兴趣。

## <a name="BKMK_SupportOptions"></a>支持选项和社区资源
以下链接提供有关支持选项和故障排除选项以及社区资源的信息：

-   [RMS 分析工具](http://www.microsoft.com/en-us/download/details.aspx?id=46437)

-   [Yammer：Microsoft Rights Management (RMS)](http://www.yammer.com/AskIPTeam)

-   [论坛：Microsoft RMS（云）](https://social.technet.microsoft.com/Forums/en-US/home?forum=rmscloud)

-   [论坛：用户 RMS（应用程序）](https://social.technet.microsoft.com/Forums/en-US/home?forum=rmsapps)

-   [Microsoft 帮助和支持](http://go.microsoft.com/fwlink/?LinkId=243064)

此外，请访问 [Microsoft Rights Management 服务门户](http://www.microsoft.com/rms)以查找 [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] 的其他支持资源。

## 请参阅
[Azure 权限管理入门](../Topic/Getting_Started_with_Azure_Rights_Management.md)

