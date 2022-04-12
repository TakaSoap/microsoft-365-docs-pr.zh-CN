---
title: 在集成应用门户中测试和部署合作伙伴Microsoft 365 应用版
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 从 Microsoft 365 管理中心 中的集成应用门户查找、测试和部署组织中的用户和组的 Microsoft 和 Microsoft 合作伙伴应用。
ms.openlocfilehash: 2baf6aea136736b1239df9a4da7b7e6a5b456ea6
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782382"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a>在集成应用门户中测试和部署合作伙伴Microsoft 365 应用版

Microsoft 365 管理中心使你可以灵活地从单个位置部署单个应用商店应用、自定义业务线应用和Microsoft 365合作伙伴应用。 可在 Microsoft 管理中心设置中的集成应用中访问该位置。 能够从集成应用门户中查找、测试和完全部署 Microsoft 合作伙伴购买和许可的应用，为组织保持业务服务定期更新和高效运行提供了便利和好处。

有关从组织合作伙伴购买和许可Microsoft 365应用的其他信息，请参阅[Microsoft 365 管理中心中的管理和部署Microsoft 365 应用版](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)。

有关合作伙伴如何创建这些应用的详细信息， [请参阅如何为商业市场规划 SaaS 产品/服务](https://go.microsoft.com/fwlink/?linkid=2158277)

集成应用门户仅可供全局管理员访问，并且仅可供全球客户使用。 此功能在主权云和政府云中不可用。

集成应用门户显示一系列应用，其中包括单个应用和部署组织合作伙伴的Microsoft 365应用。 仅列出 Web 应用、SPFx应用、Office加载项和Teams应用。 对于 Web 应用，可以看到两种类型的应用。

- SaaS 应用在 appsource.microsoft.com 中可用，可由代表组织表示同意的管理员部署。
- 与 Office 加载项链接的 SAML 库应用。

## <a name="manage-apps-in-the-integrated-apps-portal"></a>在集成应用门户中管理应用

可以管理从合作伙伴购买和许可的Microsoft 365 应用版的测试和部署。

1. 在管理中心，选择 **设置**，然后选择 **“集成应用**”。

2. 选择具有 **“更多应用** 的 **状态**”的应用以打开“**管理**”窗格。 **更多可用应用** 的状态使你了解尚未部署的 ISV 中存在更多集成。

3. 在“ **概述** ”选项卡上，选择 **“部署**”。 某些应用要求在选择“部署”之前添加用户。

4. 选择  **“用户**”，选择 **“这是测试部署**”，然后选择 **“整个组织**”、“ **特定用户/组** ”或 **“仅限我**”。 如果希望等待将应用部署到整个组织，也可以选择 **“测试部署** ”。 特定用户或组可以是Microsoft 365组、安全组或通讯组。

5. 选择 **“更新** ”，然后 **完成**。 现在可以在“概述”选项卡上选择“部署”。

6. 查看应用信息，然后选择 **“部署**”。

7. 在“部署完成”页上选择 **“完成** ”，并在“ **概述** ”选项卡上查看测试或完整部署的详细信息。

8. 如果应用的 **“更新”状态处于挂起** 状态，则可以单击该应用打开“管理”窗格并更新应用。

## <a name="find-published-apps-for-testing-and-full-deployment"></a>查找用于测试和完整部署的已发布应用

可以在“集成应用”页上的列表中找到、测试和完全部署尚未显示的已发布应用。 通过从管理中心购买和授权应用，可以从单个位置将 Microsoft 和 Microsoft 合作伙伴应用添加到列表。

1. 在管理中心左侧导航栏中，选择 **设置**，然后选择 <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">**“集成应用**</a>”。

2. 选择 **“获取应用** ”以获取应用视图。

3. 在 **Microsoft 365 应用版** 发布的应用页上，选择要部署的应用，选择 **“立即获取**”。 显示的应用主要包括 Word、PowerPoint、Excel、Outlook 加载项、Teams应用和基于SharePoint 框架技术) 构建 (的SharePoint应用。 接受权限并选择 **“继续**”。

5. 选择“ **在** 邮件旁边的页面顶部部署”，该消息指的是等待部署。

    如果所选应用由 ISV 链接到 SaaS 产品/服务，则属于此链接产品/服务的所有其他应用将显示在“配置”页上。 如果选择部署所有应用，请选择 **“下一步**”。 否则，请选择 **“编辑**”，然后选择要部署的应用。 某些应用要求在选择 **“部署**”之前添加用户。

6. 选择 **“添加用户**”，选择 **“这是测试部署**”，然后选择 **“整个组织** ”或 **“特定用户/组”** 或 **“仅限我**”。

    特定用户/组可以是Microsoft 365组、安全组或分布式组。 如果希望等待将应用部署到整个组织，也可以选择 **“测试部署** ”。

7. 选择 **“下一步** ”可转到“ **接受权限请求** ”页。 列出了每个应用的应用功能和权限。 如果应用需要同意，请选择 **“接受”权限**。 只有全局管理员才能表示同意。

8. 选择 **“下一步** ”查看部署，然后选择 **“完成部署**”。 可以通过选择 **“查看此部署**”从 **“概述**”选项卡查看部署。 在Microsoft 365 管理中心中，可以看到每个已部署应用的状态以及部署应用的日期。

> [!NOTE]
> 如果应用以前是从集成应用门户以外的位置部署的， **则部署类型** 为 **“自定义”。**

## <a name="unsupported-scenarios"></a>不支持的方案

在以下情况下，你将无法从集成应用门户部署单个应用商店应用或由合作伙伴Microsoft 365 应用版。

- 同一加载项链接到多个 SaaS 产品/服务。
- SaaS 产品/服务链接到加载项，但它不与 Microsoft Graph 集成，且未提供AAD应用 ID。
- SaaS 产品/服务链接到加载项，但为 Microsoft Graph集成提供的AAD应用 ID 在多个 SaaS 产品/服务之间共享。

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a>Upload用于测试和完整部署的自定义业务线应用

1. 在管理中心左侧导航栏中，选择 **设置**，然后 **选择集成应用**。

2. 选择 **Upload自定义应用**。 仅支持 Word、PowerPoint、Excel 和 Outlook 的自定义应用行。

3. Upload设备中的清单文件或添加 URL 链接。 某些应用要求在选择“部署”之前添加用户。

4. 选择 **“添加用户**”，选择 **“这是测试部署**”，然后选择 **“整个组织** ”或 **“特定用户/组** ”或 **“仅限我**”。

    特定用户/组可以是Microsoft 365组、安全组或分布式组。 如果要等待将应用部署到整个组织，也可以选择 **“测试部署** ”。

5. 选择 **“下一步** ”可转到“ **接受权限请求** ”页。 列出了应用的应用功能和权限。 如果应用需要同意，请选择 **“接受”权限**。 只有全局管理员才能表示同意。

6. 选择 **“下一步** ”查看部署，然后选择 **“完成部署**”。 可以通过选择 **“查看此部署**”从 **“概述**”选项卡查看部署。

## <a name="prepare-to-deploy-add-ins-in-integrated-apps"></a>准备在集成应用中部署加载项

Office 加载项可帮助用户个性化设置文档并加速访问 Web 上的信息（请参阅开始使用 Office 加载项）。 

加载项提供以下优势： 

- 相关Office应用程序启动时，加载项会自动下载。 如果外接程序支持外接程序命令，则外接程序会自动显示在Office应用程序内的功能区中。 

- 如果管理员关闭或删除加载项，或者从Azure Active Directory或从已分配加载项的组中删除用户，则用户不再显示加载项。 

加载项在三个桌面平台Windows、Mac 和 Online Office 应用中受支持。 iOS 和 Android (Outlook仅) 移动加载项也支持此功能。 

对于所有用户，外接程序最多可能需要 24 小时才能显示为客户端。 

目前，Exchange管理员和全局管理员都可以从集成应用部署加载项。   

### <a name="before-you-begin"></a>准备工作

部署外接程序要求用户使用Microsoft 365商业基本、商业标准、业务高级版) 、Office 365 企业版许可证 ( (E1/E3/E5/F3) 或Microsoft 365 企业版许可证 (E3/E5/F3) 。 用户还需要使用其组织 ID) 登录到Office，并拥有Exchange Online和活动Exchange Online邮箱。 订阅目录必须位于或联合到Azure Active Directory。 

部署不支持以下各项： 

- 针对 Office 2013 中 Word、Excel 或 PowerPoint 的加载项 
- 本地目录服务 
- 加载项部署到Exchange本地邮箱 
- 部署组件对象模型 (COM) 或Visual Studio Tools for Office (VSTO) 加载项。 
- 不包括Exchange Online的Microsoft 365的部署，例如Microsoft 365 应用版商业版和Enterprise Microsoft 365 应用版。  

### <a name="office-requirements"></a>Office要求 

对于 Word、Excel 和PowerPoint加载项，用户必须使用下列操作之一： 
- 在Windows设备上，版本 1704 或更高版本的 Microsoft 365 Business Licenses (Business Basic、Business Standard、Business 高级版) 、Office 365 企业版许可证 (E1/E3/E5/F3) 或 Microsoft 365 企业版 许可证 (E3/E5/F3) 。 
- 在 Mac 版本 15.34 或更高版本上。 

对于Outlook，用户必须使用下列操作之一： 
- Microsoft 365商业基本版、商业标准版、商业高级版) 版、Office 365 企业版许可证 ( (E1/E3/E5/F3) 的版本 1701 或更高版本，或 E3/E5/F3)  (Microsoft 365 企业版许可证。 
- 版本 1808 或更高版本的 Office 专业增强版 2019 或 Office Standard 2019。 
- 16.0.4494.1000 或更高版本的Office 专业增强版 2016 (MSI) 或Office 标准版 2016 (MSI) 。
    > [!NOTE]
    > MSI 版本的Outlook在适当的Outlook功能区中显示管理员安装的加载项，而不是“我的加载项”部分。  
- 版本 15.0.4937.1000 或更高版本Office Professional Plus 2013 (MSI) 或 Office Standard 2013 (MSI) 。
- 版本 16.0.9318.1000 或更高版本的Office 2016 for Mac。 
- 适用于 iOS 的 Outlook 移动版 2.75.0 或更高版本。 
- 适用于 Android 的 Outlook 移动版 2.2.145 或更高版本。 



### <a name="exchange-online-requirements"></a>Exchange Online要求 
Microsoft Exchange 存储组织的租户中的加载项清单。 部署加载项的管理员和接收这些加载项的用户必须位于支持 OAuth 身份验证的Exchange Online版本上。 

请与组织的 Exchange 管理员联系，了解正在使用哪个配置。可使用 [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell cmdlet 验证每个用户的 OAuth 连接。 

### <a name="user-and-group-assignments"></a>用户和组分配
目前，Azure Active Directory支持大多数组（包括Microsoft 365组、通讯组列表和安全组）都支持外接程序的部署。 部署支持没有父组的顶级组或组中的用户，但不支持具有父组的嵌套组或组中的用户。 

> [!NOTE]
> 当前不支持未启用邮件的安全组。 

在以下示例中，Sandra、Sheila 和 Sales Department 组分配给加载项。 由于西海岸销售部门是嵌套组，赵强和熊飞未被分配加载项。 

![销售部门关系图。](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

### <a name="find-out-if-a-group-contains-nested-groups"></a>找出一个组是否包含嵌套组

若要找出一个组是否包含嵌套组，最简单的方法是查看 Outlook 内的组联系人卡片。 如果在电子邮件的 **“收** 件人”字段中输入组名称，然后在解析组名称时选择组名称，则会显示它是否包含用户或嵌套组。 在以下示例中，测试组 Outlook 联系人卡片的" **成员**"选项卡显示没有用户且只有两个子组。 

![Outlook联系人卡片的成员选项卡。](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

可以解析某个组，查看该组是否是任何组的成员，从而进行反向查询。在以下示例中，可以在 Outlook 联系人卡片的" <b>成员身份</b>"选项卡下看到子组 1 是测试组的成员。 

![Outlook联系人卡片的成员身份选项卡。](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

请注意，可以使用Azure Active Directory 图形 API运行查询来查找组中的组列表。 有关详细信息，请参阅 [Operations on groups | Graph API reference](/previous-versions/azure/ad/graph/api/groups-operations)（组操作 | 图形 API 参考）。 

## <a name="recommended-approach-for-deploying-office-add-ins"></a>部署 Office 加载项的推荐方法 
若要使用分阶段方法推出外接程序，建议使用以下方法： 
1. 向小部分业务利益干系人和 IT 部门成员推出加载项。 可以打开标志 **，这是测试部署**。 如果部署成功，请转到步骤 2。 

2. 向企业中的更多人员推出外接程序。 同样，评估结果，如果成功，则继续进行完整部署。 

3. 对所有用户执行完整推出。 关闭此测试 **部署** 的标志。 

根据目标受众的大小，可以添加或删除推出步骤。  

## <a name="deploy-an-office-add-in-using-the-admin-center"></a>使用管理中心部署 Office 加载项 

1. 在管理中心，选择 **设置**，然后选择 **“集成应用**”。 

2. 选择 **“获取** 页面顶部的应用”。 AppSource 将以嵌入格式加载。 搜索加载项或通过单击左侧导航栏上的“产品”找到它。  如果外接程序已由 ISV 链接到 SaaS 应用或其他应用和外接程序，并且 SaaS 应用是付费应用，则会显示一个对话框来购买许可证或部署。 无论是否已购买许可证，都可以继续部署。 选择“部署”。  

3. 你将看到“ **配置** ”页，其中列出了所有应用。 如果没有部署应用的权限或适当访问权限，则会突出显示相应的信息。 可以选择要部署的应用。 通过选择 **“下一步**”，你将查看 **“用户** ”页面。 如果 ISV 尚未链接加载项，则将路由到“用户”页面。 

4. 选择 **“每个人**”、“ **特定用户/组**”或 **“仅我** ”以指定要部署到的加载项。 使用“搜索”框查找特定用户或组。 如果要测试外接程序，请选择 **这是测试部署**。 

5. 选择 **下一步**。 如果应用已Microsoft 365认证，则所有应用功能和权限将与认证信息一起显示在单个窗格中。 选择认证徽标可让用户查看有关认证的更多详细信息。  

6. 查看，然后选择 **“完成”部署**。  

7. 部署加载项时，将显示一个绿色的“滴答声”图标。 按照页面说明测试加载项。 

> [!NOTE]
> 用户可能需要重新启动Office才能在应用功能区上查看加载项图标。 Outlook 加载项可能需要长达 24 小时才能显示在应用的功能区上。 

最好通知用户和组已部署的外接程序可用。 请考虑发送一封电子邮件，说明何时以及如何使用外接程序。 包含或链接以帮助内容或常见问题解答，如果用户在加载项方面遇到问题，这些内容或常见问题解答可能会有所帮助。 

## <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>为用户和组分配加载项时的注意事项 

全局管理员和Exchange管理员可以向所有人或特定用户和组分配加载项。 每个选项都有含义： 

- **每个人 都** 此选项将外接程序分配给组织中的每个用户。 请谨慎使用此选项，且仅应用于真正在组织中通用的加载项。 

- **用户** 如果将加载项分配给单个用户，然后将外接程序部署到新用户，则必须先添加新用户。 

- **组** 如果向组分配加载项，则会自动为添加到组的用户分配加载项。 从组中删除用户时，用户将失去对加载项的访问权限。 在任一情况下，管理员无需执行其他操作。 

- **就我自己** 如果仅将外接程序分配给自己，则将外接程序分配给仅你的帐户，这是测试外接程序的理想之选。 

组织的正确选项取决于配置。 但是，我们建议使用组进行分配。 作为管理员，你可能会发现，通过使用组和控制这些组的成员身份，而不是每次分配单个用户，可以更轻松地管理加载项。 在某些情况下，可能需要通过手动分配用户来向特定用户分配工作，从而限制对一小组用户的访问。 

### <a name="more-about-office-add-ins-security"></a>有关Office加载项安全性的详细信息 
Office 加载项结合了一个包含加载项相关元数据的 XML 清单文件，但最重要的是它指向包含所有代码和逻辑的 Web 应用程序。加载项的功能范围很广。例如，加载项可以：
- 显示数据。 
- 读取用户文档以提供上下文服务。 
- 从用户文档读取数据并向用户文档写入数据，以便向该用户提供价值。  

若要详细了解 Office 加载项的类型和功能，请参阅 [Office Add-ins platform overview](/office/dev/add-ins/overview/office-add-ins)（Office 加载项平台概述），尤其是"Anatomy of an Office Add-in"（Office 加载项分析）一节。 

若要与用户文档进行交互，加载项需要在清单中声明需要哪些权限。五级 JavaScript API 访问权限模型为任务窗格加载项的用户提供隐私和安全性的基础。Office 应用商店 中的大多数加载项是 ReadWriteDocument 级别，几乎所有加载项均至少支持 ReadDocument 级别。有关权限级别的详细信息，请参阅 [Requesting permissions for API use in content and task pane add-ins](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)（请求在内容和任务窗格加载项中使用 API 的权限）。 

更新清单时，通常更改加载项的图标和文本。有时会更改加载项命令。但是，不会更改加载项的权限。Web 应用程序（加载项的所有代码和逻辑在其中运行）可以随时更改，这是 Web 应用程序的特性。 

加载项更新的情况如下： 
- **业务线加载项**：在这种情况下，如果管理员显式上传清单，外接程序要求管理员上传新的清单文件以支持元数据更改。 相关 Office 应用程序下次启动时，该加载项会更新。 Web 应用程序可以随时更改。 

- **Office应用商店加载项**：当管理员从 Office Store 中选择加载项时，如果 Office Store 中的加载项更新，则下次相关Office应用程序启动时，外接程序将更新。 Web 应用程序可以随时更改。 

> [!NOTE]
> 对于 Word，Excel和PowerPoint使用[SharePoint应用目录](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)将外接程序部署到本地环境中的用户，而无需连接到Microsoft 365和/或支持SharePoint外接程序。 对于Outlook使用Exchange控制面板在本地环境中部署，而无需连接到Microsoft 365。  

## <a name="add-in-states"></a>加载项状态
加载项可以处于 **打开** 或 **关闭** 状态。 

| 状态 | 此状态如何出现 | 影响 |
|:-----|:-----|:-----|
|**活动**  <br/> |管理员上传了加载项并将其分配给用户或组。  <br/> |分配了加载项的用户和组可在相关客户端中看到它。  <br/> |
|**已禁用**  <br/> |管理员已禁用加载项。  <br/> |分配了外接程序的用户和组无法再访问它。  <br/> 如果外接程序的状态更改为"可用"，则用户和组将再次有权访问它。  <br/> |
|**已删除**  <br/> |管理员已删除加载项。  <br/> |分配了加载项的用户和组无法再访问它。  <br/> |
 
如果没有人再使用外接程序，请考虑删除它。 例如，如果加载项仅在一年中的特定时间使用，则关闭加载项可能很有意义。 

## <a name="manage-an-office-add-in-using-the-admin-center"></a>使用管理中心管理Office加载项

完成部署后，管理员还可以管理用户对加载项的访问权限。 

1. 在管理中心，选择 **设置**，然后选择 **“集成应用**”。 
2. 在“集成应用”页上，它将显示已与其他应用链接的单个加载项或加载项的应用列表。 
3. 选择具有 **“更多应用的状态”的应用以** 打开“**管理**”窗格。 **更多可用应用** 的状态使你了解尚未部署的 ISV 中存在更多集成。 
4. 在“ **概述** ”选项卡上，选择 **“部署**”。 某些应用要求在选择“部署”之前添加用户。 
5. 选择 **“用户**”，选择 **“这是测试部署**”，然后选择 **“整个组织**”、“ **特定用户/组** ”或 **“仅限我**”。 如果希望等待将应用部署到整个组织，也可以选择 **“测试部署** ”。 特定用户或组可以是Microsoft 365组、安全组或通讯组。 
6. 选择 **“更新** ”，然后选择 **“完成**”。 现在可以在“**概述**”选项卡上选择 **“部署**”。 
7. 查看应用信息，然后选择 **“部署**”。
8. 在 **“部署完成**”页上选择 **“完成**”，并在“**概述**”选项卡上查看测试或完整部署的详细信息。 
9. 如果应用的 **“更新”状态处于挂起** 状态，则可以单击该应用打开“ **管理** ”窗格并更新应用。 
10. 若要仅更新用户，请选择 **“用户** ”选项卡并进行适当的更改。 进行更改后选择 **“更新** ”。  

## <a name="delete-an-add-in"></a>删除加载项

还可以删除已部署的加载项。

1. 在管理中心，选择 **设置**，然后选择 **“集成应用**”。
2. 选择任何行以显示管理窗格。 
3. 选择 **“配置”** 选项卡。 
4. 选择要删除的加载项，然后选择 **“删除**”。  

> [!NOTE]
>  如果加载项已由另一管理员部署，则将禁用“删除”按钮。 只有已部署应用或全局管理员的管理员才能删除外接程序。

## <a name="scenarios-where-exchange-admin-cannot-deploy-an-add-in"></a>Exchange管理员无法部署加载项的方案 

在两种情况下，Exchange管理员将无法部署加载项：
- 如果加载项需要 MS Graph API 的权限，并且需要全局管理员的同意。
- 如果加载项链接到两个或多个加载项和 Web 应用，并且其中至少一个加载项由另一个管理员部署 (exchange/全局) 并且用户分配不统一。 仅当所有已部署的应用的用户分配相同时，我们才允许部署加载项。  


## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a>需要哪个管理员角色才能访问集成应用？

只有全局管理员才能访问集成应用。 对于其他管理员，集成应用不会显示在左侧导航栏中。

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a>为什么在“设置”下的左侧导航栏中看到外接程序，但未看到集成应用？

原因可能有几个：

- 登录的管理员是Exchange管理员。
- 客户处于主权云中，并且集成应用体验可供主权云客户使用。

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a>可以从集成应用部署哪些应用？

集成应用允许部署Web 应用、Teams应用、Excel、PowerPoint、Word、Outlook 加载项和SPFx应用。 对于加载项，集成应用支持部署到Exchange联机邮箱，而不是本地Exchange邮箱。

### <a name="can-administrators-delete-or-remove-apps"></a>管理员是否可以删除或删除应用？

是。 全局管理员可以删除或删除应用。

- 从列表视图中选择应用。 在 **“配置”** 选项卡上，选择要删除的应用。  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a>集成应用是否在主权云中可用？

不是。 集成应用不适用于主权云客户。

### <a name="is-integrated-apps-available-in-government-clouds"></a>集成应用是否在政府云中可用？

不是。 集成应用不适用于政府云客户。
