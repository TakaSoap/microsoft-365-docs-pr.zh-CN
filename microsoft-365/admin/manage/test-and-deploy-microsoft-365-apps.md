---
title: 由合作伙伴在集成应用门户中测试和部署 Microsoft 365 应用版
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 从 Microsoft 365 管理中心中的集成应用门户查找、测试和部署组织中用户和组的 Microsoft 和 Microsoft 合作伙伴应用。
ms.openlocfilehash: da67cbe5f8b6e5f2da42e1f4b57a55d7d4a768fb
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644472"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a>由合作伙伴在集成应用门户中测试和部署 Microsoft 365 应用版

Microsoft 365 管理中心让你能够灵活地从单个位置部署单个应用商店应用、自定义业务线应用和 Microsoft 365 合作伙伴应用。 可以在 Microsoft 管理中心访问该位置，>集成>设置"。 通过集成应用门户查找、测试并完全部署由 Microsoft 合作伙伴购买和许可的应用，可为组织保持业务服务的定期更新和高效运行带来便利和好处。

有关从组织的合作伙伴购买和许可 Microsoft 365 应用的其他信息，请参阅从 [Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)管理中心管理和部署 Microsoft 365 应用。

若要详细了解合作伙伴如何创建这些应用，请参阅如何为商业市场规划 [SaaS 产品](https://go.microsoft.com/fwlink/?linkid=2158277)

集成应用门户仅可供全局管理员访问，并且仅适用于全球客户。 此功能在自主云和政府云中不可用。

集成应用门户显示应用列表，其中包括单个应用和部署你的组织的合作伙伴的 Microsoft 365 应用。 仅列出了 Web 应用、SPFx 应用、Office 加载项和 Teams 应用。 对于 Web 应用，你可以看到 2 种类型的应用。

- SaaS 应用可在 appsource.microsoft.com 中提供，并且由管理员代表组织进行部署。
- 与 Office 加载项链接的 SAML 库应用。

## <a name="manage-apps-in-the-integrated-apps-portal"></a>在集成应用门户中管理应用

你可以管理从合作伙伴处购买和许可的 Microsoft 365 应用的测试和部署。

1. 在管理中心的左侧导航中，选择 **"设置**"，然后选择"集成 **应用"。**

2. 选择"状态 **"** 为 **"更多应用"的应用，** 以打开 **"管理"** 窗格。 通过 **更多可用应用** 的状态，你可以知道来自 ISV 的更多集成尚未部署。

3. 在"概述 **"选项卡上**，选择"部署 **"。** 某些应用要求你先添加用户，然后才能选择部署。

4. 选择 **"用户**"，选择 **"这是测试部署**"，然后选择 **"整个** 组织 **"、"特定用户/组**"或"**只有我"。** 如果你想要等待将 **应用部署到** 整个组织，还可以选择测试部署。 特定用户或组可以是 Microsoft 365 组、安全组或通讯组。

5. 选择 **"更新**"，然后选择"**完成"。** 现在，可以在"概述"选项卡上选择"部署"。

6. 查看应用信息，然后选择部署 **。**

7. 在 **"** 部署已完成"页上选择"完成"，并查看"概述"选项卡上的测试或完整 **部署** 的详细信息。

8. 如果应用程序的状态为"更新挂起 **"，** 你可以单击该应用程序以打开"管理"窗格并更新应用程序。

## <a name="find-published-apps-for-testing-and-full-deployment"></a>查找已发布的应用以进行测试和完整部署

你可以查找、测试和完全部署未显示在"集成应用"页上的列表中的已发布应用。 通过从管理中心购买和许可应用，可以从单个位置将 Microsoft 和 Microsoft 合作伙伴应用添加到你的列表中。

1. 在管理中心的左侧导航中，选择 **"设置**"，然后选择"集成 **应用"。**

2. 选择 **"获取** 应用"，获取应用的视图。

3. 在 **"Microsoft 365** 应用发布应用"页面上，通过选择"立即获取"选择要 **部署的应用**。 显示的应用程序主要是 Word、PowerPoint、Excel、Outlook 外接程序、Teams 应用和 SharePoint (SharePoint 框架技术) 。 接受权限，然后选择"继续 **"。**

5. 选择 **页面** 顶部引用等待部署的消息旁边的"部署"。

    如果所选应用由 ISV 链接到 SaaS 产品/服务，则属于此链接优惠的所有其他应用将显示在"配置"页面上。 如果选择部署所有应用，请选择"下一 **步"。** 否则， **请选择"编辑**"，然后选择要部署的应用。 某些应用要求你先添加用户， **然后才能选择部署**。

6. 选择 **"添加用户"，** 选择 **"这是测试部署**"，然后选择 **"整个** 组织"或"**特定用户/组**"或"**只有我"。**

    特定用户/组可以是 Microsoft 365 组、安全组或分布式组。 如果你想要等待将 **应用部署到** 整个组织，还可以选择测试部署。

7. 选择 **"下** 一步"以进入 **"接受权限请求"** 页。 列出了每个应用的应用功能和权限。 如果应用需要同意，请选择 **"接受权限"。** 只有全局管理员可以同意。

8. 选择 **"下** 一步"查看部署，然后选择"**完成部署"。** You can view the deployment from the **Overview** tab by choosing **View this deployment**. 在 Microsoft 365 管理中心中，你可以看到每个已部署应用的状态和部署应用的日期。

> [!NOTE]
> 如果应用以前从集成应用门户外的其他位置部署，则 **部署类型为****自定义。**

## <a name="unsupported-scenarios"></a>不受支持的方案

对于以下方案，无法由合作伙伴从集成应用门户部署单个应用商店应用或 Microsoft 365 应用。

- 同一外接程序链接到多个 SaaS 产品。
- SaaS 产品链接到加载项，但它不与 Microsoft Graph 集成，也不提供 AAD 应用 ID。
- SaaS 产品链接到外接程序，但为 Microsoft Graph 集成提供的 AAD 应用 ID 在多个 SaaS 产品/服务之间共享。

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a>上载自定义业务线应用以进行测试和完整部署

1. 在管理中心的左侧导航中，选择 **"设置**"，然后选择"**集成应用"。**

2. 选择 **上传自定义应用**。 仅支持 Word、PowerPoint、Excel 和 Outlook 的自定义应用程序行。

3. 从设备上载清单文件或添加 URL 链接。 某些应用要求你先添加用户，然后才能选择部署。

4. 选择 **"添加用户"，** 选择 **"这是测试部署**"，**然后选择"整个** 组织"或"**特定用户/组**"或"**只有我"。**

    特定用户/组可以是 Microsoft 365 组、安全组或分布式组。 如果你想要等待将 **应用** 部署到整个组织，还可以选择测试部署。

5. 选择 **"下** 一步"以进入 **"接受权限请求"** 页。 列出了应用的功能和权限。 如果应用需要同意，请选择 **"接受权限"。** 只有全局管理员可以同意。

6. 选择 **"下** 一步"查看部署，然后选择"**完成部署"。** You can view the deployment from the **Overview** tab by choosing **View this deployment**.

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a>我需要哪个管理员角色才能访问集成应用？

只有全局管理员可以访问集成应用。 集成应用不会在其他管理员的左侧导航中显示。

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a>为什么在"设置"而非"集成应用"下的左侧导航中会看到外接程序？

可能有几个原因：

- 登录的管理员是 Exchange 管理员。
- 客户位于独立云中，集成应用体验还可供独立云客户使用。

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a>可以从集成应用部署哪些应用？

集成应用允许部署 Web 应用、Teams 应用、Excel、PowerPoint、Word、Outlook 加载项和 SPFx 应用。 对于外接程序，集成应用支持部署到 Exchange Online 邮箱，而不是本地 Exchange 邮箱。

### <a name="can-administrators-delete-or-remove-apps"></a>管理员能否删除或删除应用？

能。 全局管理员可以删除或删除应用。

- 从列表视图中选择应用。 在" **配置"** 选项卡上，选择要删除的应用。  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a>集成应用在自主云中是否可用？

否。 集成应用对独立云客户不可用。

### <a name="is-integrated-apps-available-in-government-clouds"></a>集成应用在政府云中是否可用？

否。 集成应用不适用于政府云客户。
