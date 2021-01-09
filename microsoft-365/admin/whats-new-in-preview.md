---
title: Microsoft 365 管理中心的新增功能是什么？
f1.keywords:
- CSH
ms.author: anfowler
author: adefowler
manager: shohara
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
- FRP150
description: Microsoft 365 管理中心 - 了解本月添加的功能。
ms.custom:
- MACDashWhatsNew
- AdminSurgePortfolio
ms.openlocfilehash: 12b7dfd39a9cf8ac73e8f1c7f2297721c2d629bf
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787875"
---
# <a name="whats-new-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理中心中的新增功能

::: moniker range="o365-21vianet"

> [!NOTE]
> 本文中的某些信息可能不适用于由世纪银行运营的 Office 365。

::: moniker-end

我们正在不断将新功能添加到 Microsoft [365](microsoft-365-admin-center-preview.md)管理中心，修复我们了解的问题，并基于你的反馈进行更改。 请看一下下面，看看现在有什么功能可供你使用。 一些功能以不同的速度向我们的客户推出。 如果尚未看到功能，请尝试 [将自己添加到定向发布](manage/release-options-in-office-365.md)。

如果你希望了解其他 Microsoft 云服务的新增功能：

- [Azure Active Directory 中的新增功能](https://docs.microsoft.com/azure/active-directory/fundamentals/whats-new)
- [Exchange 管理中心中的新增功能](https://docs.microsoft.com/Exchange/whats-new)
- [Microsoft Intune 新增功能](https://docs.microsoft.com/mem/intune/fundamentals/whats-new)
- [Microsoft 365 合规中心的新增功能](https://docs.microsoft.com/Office365/SecurityCompliance/whats-new)
- [Microsoft 365 Defender 的新增功能](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)
- [SharePoint 管理中心中的新增功能](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)
- [Office 更新](https://docs.microsoft.com/OfficeUpdates/)

## <a name="ignite-2020-august--september"></a>Ignite 2020 (&) 

欢迎使用 Microsoft Ignite - 我们的第一个仅联机 Ignite。 我们希望看到你参加我们的其中一个会话 [：Microsoft Ignite 2020 会话目录](https://myignite.microsoft.com/sessions)。 下面只是我们将在 Ignite 上讨论的一些内容。 
> [!NOTE]
> 并非所有功能都可供所有人使用。 如果看不到新功能，请加入 [定向发布](manage/release-options-in-office-365.md)。

### <a name="multi-tenant-management"></a>多租户管理

我们为多租户管理员开发了一组功能，让你更快、更有效地完成工作。 有关详细信息，请参阅"[管理多个租户"。](multi-tenant/manage.md)

- **租户：** 在管理租户之间快速切换。
- **所有** 租户：一个新页面，可快速查看所有租户服务的运行状况、任何打开的服务请求、产品和帐单、建议的安装任务以及该租户中的用户数。
- **安装程序**：多租户安装页提供了"设置"页的列表视图，但会针对许多租户进行组织。 你可以看到哪些功能未打开，哪些任务针对所有租户完成，哪些任务是租户仍然需要完成的任务。 此视图将帮助您跟踪功能采用，并确保始终完成建议的安装程序任务。
- **服务运行状况**：服务运行状况视图显示是否有事件或公告影响租户。 它甚至会告知你受影响的托管租户数。 只需选择事件，在"概述"选项卡上获取详细信息，然后切换到"受影响的租户"选项卡，向下钻取和支持该租户。
- **跨租户邮箱迁移** 现在是公共预览版中的一项新服务，允许你在租户之间移动邮箱，而无需离开然后载入邮箱。 
- **跨租户域共享**：很快，你可以加入专用预览版，以使用可跨多个租户共享域的功能。 例如，如果 Contoso 收购 Wingtip Toys，Contoso 可以与 Wingtip Toys 共享域，以便两个租户中的用户都可以使用"contoso.com"作为他们的电子邮件地址。

![选择事件并打开"受影响的租户"选项卡的多租户的服务运行状况页面。 导航菜单将"所有租户、安装程序和服务运行状况"作为唯一选项。](../media/MAC-WN-MTinServiceHealth.png)

### <a name="monitor-your-most-important-accounts"></a>监视最重要的帐户

您可以监视和跟踪发送给业务影响较高的用户（如 CEO）的失败或延迟电子邮件。 通过向 Microsoft 365 管理中心中的优先级帐户列表添加用户来跟踪优先级帐户。 添加有权访问敏感或高优先级信息的主管人员、领导、经理或其他用户。

优先级帐户仅适用于满足以下两个要求的组织：

- Office 365 E3、Microsoft 365 E3、Office 365 E5 或 Microsoft 365 E5。
- 至少 10，000 个许可证和至少 50 个每月活动的 Exchange Online 用户。

![该功能的"设置"页：监视最重要的帐户](../media/MAC-WN-PriorityAccounts.png)

有两种方法可以开始：

- 转到 **"用户"，** 然后在"更多操作"菜单中选择"管理优先级帐户"以将用户添加到列表中。
- 转到 **"设置"，** 查找安装任务 **"监视最重要的帐户**"，然后选择"**开始使用"。**

有关优先级帐户详细信息，请查看"监视[优先级帐户"。](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)

### <a name="search-faster-and-get-better-results-from-any-page"></a>更快地搜索并获取来自任何页面的更佳结果

我们已开始推出管理中心的新搜索体验，无法等待您试用。 ![搜索框已移动到横幅区域。 要从任意页面搜索的 Alt+S。](../media/MAC-WN-GlobalSearch.png)

- The Search box moved to the header area where it says "Microsoft 365 admin center" so you now search from any page， not just the Home page. 我们甚至有一个快捷方式 **：Alt+S**。
- 搜索更智能，可以更快地获得更好的结果。 尝试键入"2fa"以开始。
- 搜索结果按您可以执行的项目或操作类型进行组织。
  - **用户**：选择用户的名称，你可以编辑该用户。 如果选择其名称旁边的"更多操作"菜单，可以重置其密码。 可以按显示名称、姓氏、名字、用户名或主电子邮件地址以及电子邮件别名进行搜索。 但若要获取完全匹配，请按主电子邮件地址或用户名进行搜索。
  - **组**：从任何页面编辑组、添加成员、分配所有者。
  - **操作**：与搜索用户然后重置其密码的方式类似，您还可以从任何页面搜索"重置密码"，然后为用户重置一个或多个密码。
  - **导航**：导航下的结果可以快速帮助你快速到达管理中心中的页面。 例如，搜索"角色"将让你访问 Azure AD 角色的"角色"页。
  - **设置**：搜索与组织、订阅的服务以及安全和隐私设置相关的任何设置。 
  - **域**：你可以找到指向域的快速链接，然后该链接将你指向该域的"概述和运行状况"页。
  - **文档**：如果我们找不到结果，我们将尝试查找一些文档来提供帮助。 文章的已选择列表查找匹配项需要一点时间，因此请等待一秒钟，让搜索找到结果。 
  - **反馈**：找不到要查找的内容？ 从搜索向我们发送反馈。 我们将在管理中心内为更多页面和更多功能添加搜索功能。

### <a name="microsoft-365-admin-mobile-app"></a>Microsoft 365 管理移动应用

[订阅中包含的 Microsoft 365](https://www.microsoft.com/microsoft-365/business/manage-office-365-admin-app)管理移动应用允许你从移动设备管理 Microsoft 365，以便你可以离开桌面执行日常任务。 实际上，应用中有 90 多个功能，我们刚刚添加了一些功能：

- 支持 **Microsoft Intune** 的移动应用程序管理和条件访问策略：你现在可以使用个人设备管理 Microsoft 365，即使你组织已打开 Intune 的移动应用程序管理和条件访问策略。
- **消息中心通知**：如果希望收到有关新邮件中心帖子的通知，请打开"设置通知"  >  上的消息中心通知。 通过通知，我们希望确保你及时了解租户中的重要信息和事件。
- **计费通知**：如果你希望获取设备上计费通知（如果订阅即将过期）还可以在"设置通知"  >  上启用计费通知。
- **深色模式**：欢迎使用移动应用的深色部分。 这是我们请求最多的功能之一。 转到 **"设置**  >  **主题**"将其打开。
- **报告问题**：你现在可以报告应用中的问题或查看其他管理员报告的问题。 访问 **服务运行状况** 以签出它。

![Microsoft 365 管理应用中的"运行状况"页面，包含消息中心、服务运行状况、帐单通知的通知。](../media/MAC-WN-AdminMobileApp.png)

### <a name="usage-recommendations-for-small-and-medium-businesses"></a>中小型企业的使用建议

如果组织中的某些人员未主动使用 Teams、OneDrive 或 Office 应用，中小型企业可能会在主页上收到建议。  当你查看建议时，你可以向非活动用户快速发送 Microsoft 培训电子邮件，以帮助他们开始使用应用，并确保从订阅获得全部价值。

### <a name="remote-work-collection"></a>远程工作集合

10 月，我们将添加远程工作集合，以帮助小型企业所有者及其员工实现联机和远程工作。  **远程工作协作** 设置是 Microsoft 建议安全启用远程工作并有效协作的所有功能的列表。 在几周内，可以在"设置 **远程工作要素**  >  **"中试用它**。

![安装程序中的"远程工作基本信息"页，包含 7 个未启动的任务。](../media/MAC-WN-RemoteWork.png)

若要详细了解如何安全地允许远程工作以及易于记忆和共享的方便 Web 地址，请转到[aka.ms/remote-business。](https://aka.ms/remote-business)

### <a name="need-help-moving-to-more-admin-centers"></a>需要帮助？移动到更多管理中心

我们正在持续查看和更新内容和工具，以与产品中的更改保持一起。 现在，我们提供了更多自助诊断工具，可帮助你快速高效地解决问题。 下面是最近添加的一些：

- 更改 Exchange Web 服务限制策略
- 检查特定用户的 Teams 预配和验证状态
- 修复 DKIM 设置问题
- 诊断 Intune 用户注册错误

我们正在向其他一些管理中心推出已在 Microsoft 365 管理中心看到的新的和改进的支持体验。 Teams 管理中心和安全与合规管理中心已拥有这一新体验。 很快 **，Exchange 管理中心****、SharePoint** 管理中心Office.com将随此新的管理员帮助体验一起更新。

### <a name="manage-changes-with-microsoft-planner"></a>使用 Microsoft Planner 管理更改

5 月，我们宣布你很快就会能够将消息中心帖子同步到 Microsoft Planner，现在可供所有人使用。  现在，你可以从邮件创建任务、分配任务并跟踪任务完成。 第一次选择 **Planner 同步** 时，需要连接到相应的计划。

![在首选项按钮旁边的命令栏中突出显示"planner syncing"的消息中心页面。](../media/MAC-WN-MCPlannerSync.png)

若要了解有关它的信息，请查看本文和视频以了解其工作方式：在 Planner 中跟踪消息 [中心帖子](https://docs.microsoft.com/Office365/Planner/track-message-center-tasks-planner)

### <a name="documentation-training-and-videos"></a>文档、培训和视频

- 全新的 Microsoft Ignite-虚拟中心[。](https://adoption.microsoft.com/virtual-hub/) 深入了解 IT 专业人员和开发人员的技术培训。 快速查找 20 个新视频，作为 #SIDETRACKED 的一部分，这是 Ignite 管理员跟踪今年的名称。
- [Microsoft 365](https://www.youtube.com/watch?v=OVjb2lGJ4GU&t=2s) 视频系列的新增功能：本月，我们将介绍 Teams 白板和 Web 中提供的新功能、如何自动将用户预配到 Azure AD、Teams 中的新 Power Automate 触发器和操作等。 请继续关注下个月，我们将回顾 Ignite 的所有重大事件！
- 我们重新设计了 Microsoft [365 文档](https://docs.microsoft.com/microsoft-365) 页面，首先侧重于解决方案。 在此页面上提供新解决方案时，我们将突出显示这些解决方案，因此请留意这一点。

![Microsoft 365 解决方案文档的新登录页面，包含"授权远程工作者"等解决方案。](../media/MAC-WN-M365Docspage.png)

## <a name="july-2020"></a>2020 年 7 月

### <a name="getting-ready-for-ignite-2020"></a>准备 Ignite 2020

在我们进入 Microsoft Ignite 的一年时，我们不会发布太多功能，因此在会话期间我们有很多要讨论的功能。

本文的下一个更新将在我们第一个仅联机 Ignite 的开始日发布。 今年，可以免费参加！ 请查看，注册[：Microsoft Ignite 2020。](https://www.microsoft.com/ignite)

### <a name="your-products"></a>你的产品

订阅管理中已完成大量工作，以加快页面加载速度、更快地查找要查找的内容，并满足 Web 辅助功能标准 ([WCAG 2.1](http://www.w3.org/TR/WCAG21/) 指南) 。

- **表重新设计**：该表已重新设计，以便你可以对类似的订阅进行分组。 转到"**计费**  >  **你的产品"。**
- **产品详细信息**：通过在列表中选择产品，获取比以往更多的订阅详细信息。
- **从此处执行所有工作**：你不必跳过多个页面来管理一个产品。 例如，如果需要取消订阅，面板将打开以立即执行该操作。

![打开"取消订阅"面板的"产品"页面。](../media/MAC-WN-SubscrDetails.png)

### <a name="domains"></a>域

域管理可能很复杂，我们发布了一项新功能来简化这一过程。 转到">域"，然后选择一个域，获取有关域和域运行状况详细信息。

:::image type="content" source="../media/MAC-WN-DomainDNS.PNG" alt-text="域详细信息页面contoso.com":::

### <a name="docs-training-and-videos-july-2020"></a>2020 年 7 月 (文档、培训和) 

[Microsoft 365](https://youtu.be/m1Nu8WJgCDY) 视频系列的新增功能：本月，我们将介绍适用于 Web 和移动的新 Yammer 体验、如何集成适用于 Microsoft Teams 的 Yammer 社区应用、支持一线工作人员和管理人员的新策略包等。

## <a name="june-2020"></a>2020 年 6 月

### <a name="keeping-up-with-office-whats-new-management"></a>了解 Office 新增功能管理

几个月之前，我们添加了一个设置，允许你管理显示在用户的 [Office](#office-whats-new-management)应用中的"新增功能"邮件。 本月，我们发布了新的主页卡，该卡将帮助您快速操作并跟踪您希望向组织用户显示的"新增功能"邮件。

### <a name="docs-training-and-videos-june"></a>6 月 (文档、培训和) 

- [Teams 入门](https://support.microsoft.com/office/184f1aba-2f91-43f0-86e1-9fae607e24f6)

## <a name="may-2020"></a>2020 年 5 月

### <a name="new-update-channel-for-office"></a>Office 的新更新频道

5 月 12 日，我们宣布提供 Office 的新更新频道：每月企业频道。 此更新频道每月在每月的第二个星期二为用户提供一次新的 Office 功能。

如果你允许用户从门户自行安装 Office，你可以为用户选择每月企业频道。 为此，请登录到 Microsoft 365 管理中心，然后转到"显示 **所有**  > **设置**  >  **组织设置**  >  **服务**  >  **Office 软件下载设置"。** 如果选择每月一次 **(每月企业频道) ，** 则任何新的 Office 自安装都将配置为使用每月企业频道。

结合每月企业频道的发布，我们还将修改现有更新频道的名称。 例如，每月频道被重命名为当前频道。 新名称将于 2020 年 6 月 9 日生效。

有关详细信息，请参阅 [更改以更新 Microsoft 365 应用版频道](https://docs.microsoft.com/DeployOffice/update-channels-changes)。

### <a name="new-admin-roles"></a>新的管理员角色

我们已将一些新的 Azure Active Directory 管理员角色添加到 Microsoft 365 管理中心。

- 混合标识管理员角色授予用户管理云预配和身份验证服务的权限。
- 网络管理员角色允许用户管理网络位置并查看 Microsoft 365 软件即服务应用的网络见解。
- 打印机管理员角色授予管理打印机和打印机连接的所有方面的权限。
- 打印机技术人员是打印机管理员角色的子集，在这些角色中，这些用户可以注册和注销打印机，并更新打印机状态。
若要了解有关这些角色的更多信息，请参阅["关于管理员角色"。](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

### <a name="export-groups-list"></a>导出组列表

我们收到许多管理员的意见，他们需要向无法访问管理中心的用户共享有关组及其使用情况的信息。 现在可以将组列表导出到 CSV 文件进行审核，这意味着可以抛出该旧的 PowerShell 脚本。 若要试用，**请转到"组**  >  **组**"，然后从命令栏中选择"导出组"。

### <a name="microsoft-365-solution-and-architecture-center"></a>Microsoft 365 解决方案和体系结构中心

就在本月，我们发布了名为 [https://docs.microsoft.com](https://docs.microsoft.com) [Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/solution-architecture-center)解决方案和体系结构中心的新网站，它整合了了解、计划和实施集成 Microsoft 365 解决方案所需的技术指南，以确保安全与合规的协作。 在此中心，你将发现：

- 基础解决方案指南
- 工作负载解决方案和方案指南
- 海报中的解决方案 (体系结构图示!!!) 
- 行业特定指南
- 企业体系结构设计主体

### <a name="docs-training-and-videos-may"></a>5 月 (文档) 

- **Microsoft 365** 视频系列中的新增功能：本月，我们将介绍 Teams 管理员和安全与合规中心的新支持体验、Planner 与消息中心的集成以及 Microsoft Teams 中的新 3x3 视频布局。 
- [Microsoft 365 管理中心帮助](https://docs.microsoft.com/microsoft-365/admin/)中心页面已更新，可帮助你更快找到所需的内容。 如果你立即查看该页面，我们添加了一张卡片，告知你重要更新和更改。

## <a name="april-2020"></a>2020 年 4 月

### <a name="intune-roles-management"></a>Intune 角色管理

[2020 年 4 月](#april-2020)

我们这样做了！ 我们已执行统一角色体验的第二步，现在可以在 Microsoft 365 管理中心管理 Intune 角色。 您还可以利用搜索角色和查看角色权限等功能。 这意味着，无需使用两个单独的工具来管理 Microsoft 365 和 Intune 的角色。 登录 Microsoft 365 管理中心后，你将看到"角色"页面上有两个透视表，一个适用于 Azure AD，另一个适用于 Intune。

![选择 Intune 透视表的角色页](../media/MAC-WN-IntuneRoles.png)

### <a name="sync-message-center-posts-to-planner"></a>将消息中心帖子同步到 Planner

从 5 月开始，目标版本中的管理员将开始在消息中心看到"Planner 同步"按钮。 现在，您可以跟踪需要操作的邮件、选择要跟踪的邮件类型、将要跟踪的邮件分配为任务以及标记邮件供以后关注。

[加入定向发布](manage/release-options-in-office-365.md) 开始！

### <a name="need-help-launched-in-teams-admin-center--security-and-compliance-centers"></a>"需要帮助？" 在 Teams 管理中心&安全与合规中心中启动

Teams 管理中心、安全中心和合规中心现在使用相同的"需要帮助？" Microsoft 365 管理中心用于查找帮助和联系支持人员的功能。 我们收到了许多来自管理员的反馈，你希望获得相同级别的帮助和支持，我们乐意为你带来帮助和支持。 试一试，然后向我们提供反馈！

#### <a name="need-chat"></a>需要聊天？

我们的支持代理一直在在家工作，同时在家工作时仍接受客户案例和 Internet 带宽限制可能会影响客户通话质量。 为了继续支持你，我们已在 Microsoft 365 管理中心为商业客户启动实时聊天支持选项。

创建服务请求时，除了电话和电子邮件之外，你现在还会看到聊天作为一个选项。 选择聊天作为首选的通信通道并创建请求。 创建请求后，可以在准备好与 Microsoft 代理聊天时开始聊天。

### <a name="teams-updates"></a>Teams 更新

随着 Teams 的使用的增加，我们添加了一些功能来帮助你管理这些功能。

- 管理中心主页上的新建议卡显示哪些用户 30 天内未主动使用 Teams。 你可以向这些用户发送培训电子邮件，让他们开始使用 Teams。
- **将人员与团队汇集** 在一起：转到安装程序以查看一个新页面，帮助你为许可用户打开 Teams 并允许来宾访问，以便你可以与 Teams 中的外部客户合作。
- Microsoft Teams 卡现在默认固定到你的主页。 它显示 Teams 是否已打开，以及是否允许来宾访问。 它还允许你检查新许可的 Teams 用户的安装状态，并检查网络问题是否可能会影响 Teams 用户。
- 最后，如果你购买了包含 Teams 的许可证，则 Teams 现在是初始设置流程的一个步骤。

### <a name="productivity-score"></a>工作效率分数

Productivity Score 提供人们如何使用 Microsoft 云服务和支持 Microsoft 云服务的技术体验的见解。 该分数反映你的组织与员工和技术体验度量的绩效，并将你的分数与像你这样的组织进行比较。 本月，我们将向预览体验介绍以下新概念：

- 主页和类别详细信息页面上主要见解的趋势视图 -添加到技术体验的 Endpoint Analytics 和网络连接类别
- 员工体验类别中显示的相关技术体验见解
- 作为员工体验的一部分的新通信类别
- 员工体验类别中具有组织元数据的用户详细信息

若要了解更多信息，请查看博客：使用 Microsoft Productivity Score 测量和改进 [Microsoft 365 体验](https://techcommunity.microsoft.com/t5/microsoft-365-blog/measure-and-improve-the-microsoft-365-experience-with-microsoft/ba-p/1348618)。 工作效率分数目前为个人预览版。 [加入"生产力分数专用预览"](https://aka.ms/productivityscorepreview) 开始。

### <a name="groups-updates"></a>组更新

我们这个月的组有两个更新：

- 现在，您可以编辑 Office 365 组的电子邮件地址 (在 Outlook 中也称为组，并且很快称为 Microsoft 365 组) 。
- 我们收到你的反馈，并且添加了更明确的错误消息，说明你无法将组转换为 Microsoft 团队的原因。

### <a name="docs-videos-and-training-april"></a>) 年 (4 月的文档、视频和) 

**Microsoft 365** 视频系列中的新增功能：本月，我们介绍可帮助小型企业过渡到远程工作的提示和资源，包括如何推出 Microsoft Teams、与客户端和合作伙伴保持联系的远程工作培训资源，以及新的 Microsoft 365 商务语音计划。 [Microsoft 365 中的新增功能](https://go.microsoft.com/fwlink/p/?linkid=2118096)

#### <a name="for-your-users"></a>对于用户

- [安排会议](https://support.microsoft.com/office/c61b4f61-ee62-4a06-8bf7-0a1cd302700a)
- [加入 Teams 会议](https://support.microsoft.com/office/078e9868-f1aa-4414-8bb9-ee88e9236ee4)
- [创建全组织范围小组](https://support.microsoft.com/office/037bb27a-bcc9-48fe-8d72-44d9482420a3)
- [与来宾一起创建团队](https://support.microsoft.com/office/11fbb083-52ee-434d-8c6e-63711fdafac7)
- [作为来宾加入团队](https://support.microsoft.com/office/928d1eef-61e2-49ec-b754-c2fe86b34824)
- [创建组电子邮件地址](https://support.microsoft.com/office/ded875f9-a9de-437f-b559-2ae4f235bb2b)

#### <a name="for-admins-and-business-owners"></a>对于管理员和业务所有者

- [通过远程工作为小型企业提供支持](https://support.microsoft.com/office/9b91a85a-39b4-40a6-a590-0f9bea0ba8e6)
- [运行远程小型企业](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)
- [注册 Microsoft Business Basic](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)
- [设置双重登录](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)

## <a name="march-2020"></a>2020 年 3 月

### <a name="featured-feedback-fix-improve-add-user-reliability-for-licensing"></a>特别推荐的反馈修复：提高许可的"添加用户"可靠性

我们收到了许多来自管理员的反馈，内容是添加用户时分配许可证有多困难。 我们对此修补程序进行了第一次更新，并且已迁移到一个更可靠的后台服务，以处理这些请求。 如果出现错误，现在将看到一条错误消息，让您重试。

![添加包含错误的用户确认页面。](../media/MAC-WN-ImprovedLicensing.png)

### <a name="microsoft-teams-home-page-card"></a>Microsoft Teams 主页卡

随着 Teams 使用情况的上升，一些组织将获取固定的仪表板卡，使打开 Teams 变得更加可发现。 该卡片还具有指向培训和文档的链接，可帮助你的组织过渡到远程工作。 只需转到 **主页** 以查看新卡片。

![Microsoft Teams 主页卡](../media/MAC-WN-TeamsCard.PNG)

### <a name="customize-your-organizations-sharepoint-mobile-app-theme"></a>自定义组织的 SharePoint 移动应用主题

使用 Microsoft 365 管理中心，现在可以在适用于 iOS 的 SharePoint 移动应用和适用于 Android 的 SharePoint 移动应用中自定义组织的主题。 此功能可以方便地为员工提供与 SharePoint Online 匹配的移动 Intranet 应用体验。 主题自定义包括徽标图像、导航栏颜色、文本和图标颜色以及主题色，便于识别。

![将管理中心设置映射到移动应用的图表。](../media/MAC-WN-CustThemeSP.png)

### <a name="improvements-to-the-add-a-group-wizard"></a>对"添加组"向导的改进

当管理员创建一个新组并同时将其创建为团队时，他们可以分配没有包含 Teams 的许可证的所有者。 这导致一些麻烦。 我们更新了向导流，以验证所有者是否拥有 Teams 许可证，以及是否禁用了将组转换为团队的选项。

### <a name="microsoft-365-offerings-for-small-and-medium-businesses"></a>适用于中小型企业的 Microsoft 365 产品/服务

我们知道这是下个月的公告，但我们希望确保你已做好准备。

从 4 月 21 日起，我们将更改与适用于中小型企业的 Office 365 订阅以及 Office 365 专业增强版相关的更改。 这些产品现在将使用 Microsoft 365 品牌。

新产品名称于 2020 年 4 月 21 日生效。 This is a change to the product name only， and there is no pricing or feature changes at this time.

|当前名称 |新的名称  |
|---------|---------|
|Office 365 商业协作版     |   Microsoft 365 商业基础版      |
|Office 365 商业高级版     |    Microsoft 365 商业标准版     |
|Microsoft 365 商业版     |    Microsoft 365 商业高级版     |
|Office 365 商业版     |    Microsoft 365 商业应用版       |
|Office 365 专业增强版    |   Microsoft 365 企业应用版      |

### <a name="videos-training-and-docs"></a>视频、培训和文档

[Microsoft 365 Web](https://go.microsoft.com/fwlink/p/?linkid=2118096)系列中的新增功能：在此月的事件集中，我们重点介绍 Microsoft Teams 的 3 周年纪念日，并涵盖新功能，包括联机会议中改进的音频质量、面向具有 Shifts 应用的一线管理人员的目标通信、Teams 和 Skype 消费者互操作性等。

## <a name="february-2020"></a>2020 年 2 月

### <a name="featured-feedback-fix-multi-organization-switcher"></a>特色反馈修复：多组织切换器

我们收到了合作伙伴和管理员有关管理多个 Microsoft 云组织的挑战的很多反馈。 我们第一个多组织管理功能之一是组织切换器，它使你只需单击 2 次即可在管理的组织之间更改。
> [!TIP]
> 只要至少是一个组织的记录合作伙伴，就不必执行任何操作来使组织切换程序显示。

1. 在 Microsoft 365 管理中心中，选择组织名称。
![屏幕捕获：主页顶部显示具有切换器图标的组织配置文件名称。](../media/MAC-Organization-switcher.png)

2. 在组织切换器中，选择要管理的组织。
![屏幕捕获：突出显示了合并 Messenger 租户的"我的组织"租户切换器](../media/MAC-OrgSwitcherSelected.png)

就字面来说!!!

### <a name="groups"></a>组

本月组区域中的一些更改：

- **按组名称排序**：可以通过选择组名称列，按字母顺序对组 **列表** 进行排序。
- **还原已删除的 Microsoft 365** 组：你不再需要转到 Exchange 管理中心来还原已删除的 Microsoft 365 组。 转到 **Microsoft 365** 管理中心"组已删除 (从"还原"组) \>  \>  \> \> **组**。 它将组还原回 **组列表，** 并还原组的电子邮件、对话、笔记本、文件和日历。

### <a name="videos-training-and-docs-february"></a>2 月 2 月 (视频、培训和) 

- **Microsoft 365** 视频系列中的新增功能：本月，我们专注于 SharePoint Online 的自定义搜索功能、Office"新增功能"管理功能，通过应用内帮助窗格向最终用户显示或隐藏特定功能、Yammer 中的最新安全性和合规性更新等。 以下是最新剧集[：Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)中的新增功能

- **文档移动**：我们将 Office 365 管理员 Web 文章与 Microsoft 365 内容相结合，你可能已注意到新 URL。 例如，本文以前托管在：docs.microsoft.com/Office365/Admin/whats-new-in-preview，但 URL **现在为**：docs.microsoft.com/microsoft-365/admin/whats-new-in-preview。 如果为页面添加书签，应更新链接;但是，内容链接将重定向到新的内容存储库。

## <a name="january-2020---happy-new-year"></a>2020 年 1 月 - 新一年

> [!NOTE]
> 你是否知道 YouTube 上的 [Microsoft 365 视频](https://go.microsoft.com/fwlink/p/?linkid=2118096) 系列中新增了哪些功能？ 它重点介绍了我们向用户推出的最新功能。 每月，我们将开始链接到"视频、培训和文档"部分 [的最新剧](#videos-training-and-docs) 集。 <br> <br> 以下是最新剧集[：Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)中的新增功能

### <a name="dark-mode"></a>深色模式

当我们第一次推出深色模式时，它仅在主页上可用。 深色模式现已退出预览，并且已针对管理中心中的大多数页面进行定向发布。

1. 首先，你需要打开定向发布：**转到"设置** 设置组织配置文件发布 \>  \>  \> **"首选项**。
1. 然后，若要打开深色模式，请转到主页，然后选择"深色 **模式"** 按钮。  ("搜索" **字段旁边，** 本文的"新增功能 **"** 链接旁边) 
1. 对于提供深色模式的任何页面，该按钮位于页面顶部，位于新的管理 **中心切换旁边** 。

### <a name="office-whats-new-management"></a>Office 新增管理

管理员希望控制 Microsoft 如何在 Office 应用中向用户传达"新增功能"，你现在拥有该控制权。 转到"**设置** \> **Office 新增管理预览"。** 选择一个功能以查看其详细信息，如果不希望用户看到特定的"新增功能"消息，可以选择"从用户隐藏"按钮。 例如，您的组织可能正在等待让用户了解功能，直到组织中的每个人都接受该功能培训。

![打开功能的详细信息窗格后，屏幕截图 Office 新增功能预览。](../media/whatsnew-officemgmt-preview.png)

此功能在 11 月首次发布预览，但应了解一些功能更新[：Office 新增](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-preview/ba-p/1020438)管理预览更新现已发布

### <a name="partners"></a>合作伙伴

Howdy，合作伙伴！  (不能帮助自己。) 我们这个月也收到了一个更新。 有一项新功能允许合作伙伴向云解决方案提供商客户提供在管理中心的"计费帐户"部分接受其 Microsoft 客户协议 (MCA ) 的选项。 在此新体验中：

1. 客户会收到一封邀请电子邮件，并包含接受合作伙伴关系和 MCA 的链接。
2. 客户登录后，他们可以从管理中心查看并接受 MCA 和合作伙伴权限。

### <a name="resource-mailboxes"></a>资源邮箱

资源邮箱列表已更新为新样式。 在 Microsoft 365 管理中心，转到 **Resources** \> **Rooms &设备**。

### <a name="videos-training-and-docs-january"></a>) 年 (1 月的视频、培训和) 

查看我们在 1 月发布的小型企业管理员培训：

- [创建业务网站](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9)
- [查找答案和帮助](https://support.microsoft.com/office/7f681212-c649-4a3e-a43b-32b1d1e58988)
- [获取帮助或支持](https://support.microsoft.com/office/18948a4c-3eb1-4b30-b1bc-a4cc29eb7655)
- [删除用户](https://support.microsoft.com/office/6bcdad7b-732a-4260-997a-8c176bc3d9d6)
- [选择 Microsoft 订阅](https://support.microsoft.com/office/b9f7c78e-430f-4117-89ec-2eeb1dced2ca)
- [Microsoft 365 商业安全概述](https://support.microsoft.com/office/3274b159-a825-46d7-9421-7d6e209389d1)

## <a name="november-and-december-2019"></a>2019 年 11 月到 12 月

我们合并了 11 月与 12 月的新闻，因为在 Ignite 之后，我们只有很少的公告要发布。 在新的一年看到您！

### <a name="change-from-credit-card-to-invoice-payment"></a>从信用卡更改为发票付款

我们已开始推出将付款方式从信用卡更改为发票的能力。 转到 **"** \> **计费你的产品"，** 选择订阅，然后选择信用卡付款旁边的"编辑"链接。

![屏幕捕获：使用信用卡作为付款方式的订阅卡的计费部分。](../media/MAC-BillingEditCreditCard.png)

想要阅读有关它更多信息？ [从信用卡或银行帐户更改为发票](../commerce/billing-and-payments/change-payment-method.md)

### <a name="global-reader"></a>全局读取者

我们在 [2019 年 10](#october-2019---ignite-edition)月 - Ignite Edition 中提到全局读者角色，但在它推出范围更广泛的时，让我们讨论一些详细信息：

- 全局读取者角色是全局管理员角色的只读对应角色。 全局读取者可以看到全局管理员有权执行的所有操作。
- 除一些例外情况（如一些合规性和安全功能）外，全局读者有权访问组织授权使用的所有 Microsoft 云管理中心。
- 为规划、审核和调查需要全局读者角色的用户分配该角色。
- 还可以将全局读者角色与具有较少权限的另一个角色结合使用。 例如，可能会为小型企业所有者分配"计费管理员全局读者"角色，以便他们可以支付帐单并随时了解云  +  组织的更改。
- 全局读者可以转到 Microsoft 365 管理中心的任何页面。 当他们打开可编辑的页面时，顶部将显示一条警告，告知他们无权保存更改，并且保存按钮将被禁用。

我们喜欢收到有关全局读者角色以及将来要查看的任何基于角色的权限的反馈。 [提供基于角色的权限的反馈](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/10115430-have-a-consistent-experience-when-assigning-admin)

### <a name="new-settings-page"></a>"新建设置"页

组织 **配置文件、&****隐私** 和服务&外接程序页面已全部合并为一个包含 3 个垂直选项卡的页面。 最佳部分 -- 从一个位置，你现在可以搜索所有设置。
![屏幕捕获："设置"页，页面顶部突出显示了"搜索所有设置"字段。](../media/MAC-SettingsMultiPivotSearch.png)

### <a name="training--docs"></a>培训&文档

本节是本文的一项新功能，我们将开始链接到我们认为您将感兴趣的新培训和文档。

11 月，我们向 [Microsoft Learn](https://docs.microsoft.com/learn/) 网站发布了很多学习路径，以帮助 IT 专业人员了解和接受 Microsoft 365 培训。 查看它们：

- [Microsoft 365 基础](https://docs.microsoft.com/learn/paths/m365-fundamentals/)
- [扩展 Office 基础功能](https://docs.microsoft.com/learn/paths/extend-office-fundamentals/)
- [Microsoft 365 - 使用 Windows 10 和 Microsoft 365 企业应用版现代化企业部署](https://docs.microsoft.com/learn/paths/m365-getmodern/)
- [使用 Microsoft 365 管理企业部署](https://docs.microsoft.com/learn/paths/manage-enterprise-deployment-m365/)
- [大规模升级 Microsoft Office for IT](https://docs.microsoft.com/learn/paths/m365-office-for-it/)
- [通过 Windows 虚拟桌面从 Azure 提供远程桌面和应用 ](https://docs.microsoft.com/learn/paths/m365-wvd/)
- [使用 Microsoft 365 和 Surface for Business 使你的工作场所现代化](https://docs.microsoft.com/learn/paths/modernize-workplace-with-m365-and-surface/)
- [使用 Microsoft 365 保护标识和访问](https://docs.microsoft.com/learn/paths/m365-identity/)
- [使用 Microsoft 365 保护企业信息](https://docs.microsoft.com/learn/paths/m365-information-protection/)
- [使用 Microsoft 365 管理安全性](https://docs.microsoft.com/learn/paths/m365-security-management/)
- [使用 Microsoft 365 Defender 抵御威胁](https://docs.microsoft.com/learn/paths/m365-security-threat-protection/)
- [使用 Microsoft Teams 管理团队协作](https://docs.microsoft.com/learn/paths/m365-manage-team-collaboration/)
- [在 Microsoft 365 中配合使用 SharePoint](https://docs.microsoft.com/learn/paths/m365-teams-sharepoint/)

## <a name="october-2019---ignite-edition"></a>2019 年 10 月 - Ignite Edition

欢迎使用 Microsoft 365 管理中心中的 Ignite 版本新增功能！ 当然，这不是完整的通知列表，但下面是一些要点。 此外，请查看 Ignite 博客，获取有关版本更出色的信息：

- [ADMIN - Microsoft 365](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/ADMIN-Security-Productivity-and-Network-Enhancements-for/ba-p/964019)的安全性、生产力和网络增强功能。
- [Microsoft Teams 中的新增功能 - Ignite 2020](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-New-in-Microsoft-Teams-Ignite-2019/ba-p/937025)。

### <a name="role-based-access-control"></a>基于角色的访问控制

自我们在 6 月开始推出后，管理中心中的角色发生了大量更改：

- **比较角色** - 最多选择 3 个角色，以比较每个角色的权限。 这将帮助你找到要分配给用户最小权限的角色。 转到 **"角色**"，使用第一列中的多选复选框选择最多 3 个角色，然后选择"**比较角色"。**

    ![比较 Exchange 管理员、支持管理员和用户管理员角色。](../media/RBAC-CompareRoles.png)

- **收藏夹** - 你可以向常用或最常用的角色添加星形，以便可以通过对列进行排序或创建筛选器来轻松找到它们。
- **活动用户**  > **管理角色**- 已对此进行了更新，以与角色中的更改保持一致。 与"角色"列表一样，我们已将角色的默认列表的范围设置为最有用，但您可以通过按类别展开"全部显示"来查看 **所有角色**。
- **全局读者角色** - 你要求它！ 没问题！ 全局 [读者](add-users/about-admin-roles.md) 角色！

### <a name="report-an-issue"></a>报告问题

服务运行状况已更新为新样式，如果受未显示在服务运行状况仪表板上的问题的影响，可以报告问题以告知 Microsoft。  转到 **"运行状况**  >  **服务"运行状况**。

### <a name="viral-subscriptions"></a>"更新"订阅

正如你所知，用户可以为大量产品（如 Power BI 和 App Connect）启用免费订阅。 现在，你可以看到用户一直在尝试的"订阅"。 转到"**计费**  >  **你的产品"。** 选择 **"订阅"** 选项卡上的"帐户类型"筛选器以查看用户购买的订阅。 如果需要，你现在能够从帐户中删除这些订阅。

### <a name="user-templates"></a>用户模板

模板允许你通过保存和重新使用这些用户的共享设置来轻松添加许多用户。 你可以保存角色、分配的许可证、联系人信息、位置等的值。 使用模板创建新用户时，将自动获取这些设置的已保存值。 转到 **"用户**  >  **活动用户"，** 然后选择 **"用户模板**"进行试用。

### <a name="office-whats-new-management-preview"></a>Office"新增功能"管理 (预览) 

将重要的 Office 功能发布至 Office 应用后，用户将获得"新增功能"卡片，了解新功能。 如果不希望用户看到该卡片，可以将其隐藏。 还可以选择何时希望用户通过显示卡片来查看卡片。 转到 **"**  >  **设置 Office 新增功能"管理** 以签出它。

### <a name="sharepoint-url-change"></a>SharePoint URL 更改

从技术上说，这不是 Microsoft 365 管理中心要告诉的新闻，但我们非常希望确保你能看到此新闻：
> [!IMPORTANT]
> 现在，可以使用常规 URL 访问 SharePoint 管理中心： [https://admin.microsoft.com/SharePoint](https://admin.microsoft.com/SharePoint)

有关详细信息，请参阅 SharePoint 管理中心中的 [新增功能](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)。

## <a name="september-2019"></a>2019 年 9 月

我们正在加速在 Ignite 2019 上发布一些令人兴奋的功能，因此，我们仅宣布推出一些在 9 月发布的新功能。 但是请继续关注下个月的文章，将在 Ignite 的第一天发布！

### <a name="featured-feedback-fix--the-option-to-convert-the-deleted-users-mailbox-to-a-shared-mailbox-is-back"></a>特别推荐的反馈修复 - 将已删除用户的邮箱转换为共享邮箱的选项已返回

我们听到你的反馈非常清晰，我们通过将其转换为共享邮箱，重新支持其他人访问已删除用户的 **邮箱**。 通过添加回删除用户向导，你可以决定对数据执行哪些操作：

- 电子邮件：将已删除用户的邮箱转换为共享邮箱，使其他人能够访问该邮箱。
- 文件：保存其 OneDrive 文件并授予其他人访问权限。
- 权限：如果其他人有权访问此邮箱，则删除权限。
- 别名：删除电子邮件别名，以便它们可供其他用户立即使用。
![屏幕捕获：删除显示电子邮件别名、权限、OneDrive 和电子邮件选项的用户向导](../media/WhatsNew-DeleteUserWiz.png)

### <a name="initial-setup"></a>初始设置

我们对另一个初始安装向导进行了更新：Microsoft 365 商业版。 这些步骤已简化，我们已将两个设置任务移至"设置"页：

- **保护 Windows 10** 计算机 - 设置策略以更好地保护 Windows 10 设备免受病毒、恶意软件和黑客的攻击。
- **自动安装 Office** - 当你打开此功能并且用户将其电脑连接到 Microsoft 365 商业版时，他们的计算机将自动更新到最新的 Office 应用，并保持最新。

## <a name="august-2019"></a>2019 年 8 月

### <a name="billing"></a>计费

我们这个月的计费和订阅已获取一些更新：

- 基于设备的订阅：你可以向 Microsoft 365 管理中心中的设备分配或取消分配 **Microsoft 365** 教育应用版 (设备) 许可证。 **Microsoft 365** 教育 (设备) 是一个附加许可证，可用于向设备分配许可证。 转到 **"计费**  >  **你的产品"** 以查找并购买许可证。
- 基于用户的许可证管理：我们更新了将用户活动用户中的许可证分配到  >  新样式的方式。 有关详细信息，请参阅：
  - [向用户分配许可证](manage/assign-licenses-to-users.md)
  - [取消分配用户许可证](manage/remove-licenses-from-users.md)

### <a name="setup-page-updates"></a>安装程序页面更新

安装程序现在包含类别和部分，包括"推荐使用"部分，我们可智能地建议下一步启用功能和设置组织。 我们还添加了一个新功能来设置：

- **Microsoft Defender for Office 365** - 如果你的组织已获得使用适用于 Office 365 的 Microsoft Defender 的许可，并且你尚未配置或打开它，你将看到此页面。 转到 **"设置** "进行试用。

### <a name="report-an-issue-august"></a>报告 (8 月) 

如果您受到未显示在服务运行状况仪表板上的问题的影响，"报告问题"功能将为您提供一种快速而简便的方式告知我们。 转到 **"运行状况**  >  **服务"运行状况**。

## <a name="july-2019"></a>2019 年 7 月

### <a name="message-center"></a>消息中心

消息中心已更新到新设计，看起来很神奇！

![屏幕捕获：已更新消息中心，选择"所有活动邮件"选项卡，并打开"筛选器"菜单。](../media/MAC-MessageCenterUpdated.png)

- 你现在可以按 **状态查看邮件**。 只需选择其中一个选项卡：**所有活动邮件**、高重要性邮件 **、未读邮件** 和 **已消除邮件**。
- 您还可以按类别数据隐私、**计划更改**、**阻止或修复问题** 以及 **及时了解邮件** 类别进行筛选。
- Select a message from the list and you have a few options in the command bar： **Dismiss，** **Mark as read** or Mark as **unread，** or **Share.**
- 当您打开邮件时，您具有更多选项：
  - 将邮件的链接复制到剪贴板，将其保存供以后或与同事共享。
  - 将邮件标记为 **"已读**"**或"未读"。**
  - 通过选择"喜欢"或"不喜欢"提供有关邮件的反馈，此时将打开一个反馈窗格，要求您提供有关您喜欢或不喜欢此邮件的特定反馈。

### <a name="navigation-pane-intelligence"></a>导航窗格智能

 导航窗格现在会记住你的最后一个操作，并按上次离开它的状态显示该窗格。 它还会使常用项目在默认情况下可见。

### <a name="initial-setup--the-setup-page"></a>"设置&的初始设置

我们收到了一些令人兴奋的更改，可帮助你建立组织。 首先，我们讨论设置和 **设置页面****的区别**。 **安装程序** 是指你用于载入 Microsoft 联机服务的初始安装向导。 这通常包括三个特定步骤：**连接域****、添加用户****和下载 Office 应用**。 " **设置** "页面是管理中心中的页面，其中推荐了设置任务，以确保你可以从订阅中获得最大功能，例如打开已购买许可证的功能。

- **安装程序** - 初始安装向导已针对 **Microsoft 365 商业版订阅** 进行了更新。 这一新设计将帮助新组织更快地完成向导并取得更大的成功。
- **"** 设置 **"** 页 - "设置"页可帮助您完成订阅所提供服务的设置和保护。 您还可以在"设置"页上看到 **任何已消除** 的建议。 若要了解它是否适用于你的订阅，请转到 **Microsoft 365 管理中心**  >  **安装程序**。

### <a name="billing--subscriptions"></a>计费&订阅

- **软件** 产品类型 - 你现在可以查看通过云服务提供商或云解决方案提供商 (购买) 。 To see your downloads and keys， go to **Billing**  >  **Your products**  >  **Software** tab.
- 无论你是从 Microsoft 还是第三方提供商购买，都可以从 Microsoft 365 管理中心查看新式 Azure 产品和服务。 包括新式 Azure 产品的示例：
  - Azure 预留虚拟实例
  - Azure 支持计划
  - Azure 混合使用权益 (AHUB) 
  - 管理应用程序
  - 设备服务
  - Azure 订阅

### <a name="simplify-multi-factor-authentication"></a>简化多重身份验证

管理员有权访问您组织的敏感信息。 要求所有管理员在登录时使用多重身份验证。 新向导只需一个步骤，就可以帮助您完成该步骤。 若要试用，请转到 **"设置** 加强  >  **"登录安全。**

### <a name="users"></a>用户

已删除 **用户和****来宾用户** 页面已更新为新样式。

- **来宾用户**：通过邀请来宾用户从 SharePoint 或 OneDrive 查看或共享文件来添加来宾用户。 可以从用户来宾用户 **查看**  >  **来宾用户**。
- **已删除用户**： **在更新后的** "已删除用户"页上，可以执行在旧管理中心中可以执行的所有操作，但现在您可以添加和删除列。 我们有很多列选项可供选择。 事实上，它是您可以在"活动用户"页上 **选择的相同** 列。

## <a name="june-2019"></a>2019 年 6 月

### <a name="featured-feedback-request---dark-mode"></a>特别推荐的反馈请求 - 深色模式

在深色模式下查看管理中心是预览版！ 你目前只能在主页上进行测试。  在 **主页** 上，"深色 **模式** "按钮位于"新增功能"链接旁边的 **命令** 栏中。

### <a name="roles-management"></a>角色管理

6 月底，我们开始推出管理管理员角色的新方式。 如果可用，请转到"**角色**  >  **"。** 在此之前，请看一看，这太酷了！
<br> ![屏幕捕获：突出显示了用户管理员角色详细信息窗格的管理员角色列表。](../media/MAC-AdminRoles-Featured.png) <br>

这一新体验使查看谁具有管理员权限以及分配向管理员授予正确级别访问权限的角色变得更加简单。 此外，我们还从 Azure AD 添加了更多角色，以便你不会在进入多个管理中心时浪费时间。
还可以在此处执行哪些功能？

- 导出在 Microsoft 365 中分配了 Azure Active Directory 角色的组织中的所有管理员的列表。  
- 查看分配给特定角色的所有管理员，从特定角色添加或删除管理员，按名称和关键字搜索角色，并详细了解每个角色允许用户执行哪些操作。
- 快速搜索特定角色并创建筛选器。

### <a name="payment-method"></a>付款方式

我们已更新了如何支付订阅费用。 转到计费  >  **帐单&**  >  **付款付款方式**。 您可以在列表视图中查看付款方式。 选择列表中的任意项目将其删除、编辑它，并轻松查看与付款方式关联的订阅。

## <a name="may-2019"></a>2019 年 5 月

### <a name="mays-featured-fix---case-sensitivity"></a>五月特别推荐修复 - 区分大小写

现在，当您搜索共享邮箱、联系人、资源和邮箱权限时，搜索词不必区分大小写。

**用户和组管理** 本月，我们将阻止用户、重置 **密码**、联系人列表视图、组列表视图和 **组详细信息页面** 更新为新的管理中心样式。

- 使用新的 **"组** "列表视图，可以获取有关组的更丰富的数据，并可以自定义查看数据的方式，组列表将记住您希望查看数据的方式。 例如，你现在可以使用 **Teams** 筛选组以查看你的组是否属于团队，并可以添加 **Teams 状态** 列。
- 组列表还带来了我们对用户管理中的列表体验的所有改进，包括快速操作和上下文命令栏。

**推荐**<br>
你可能会在管理中心看到新的建议弹出窗口，我们刚刚添加了 4 个新建议。 当然，只有在我们认为对组织有益处时，你才能看到建议。 但不要等到我们向用户显示建议后，你可以从卡片库添加它。

- **密码过期**- 我们建议将密码设置为"永不 **过期"。** 如果您的组织具有不同的设置，您可能只看到此建议。
- **全局管理员过多** - 由于全局管理员过多是一种安全威胁，因此，如果你有 4 名以上全局管理员，你将看到此建议。 我们建议仅向用户提供完成工作所需的访问权限。
- **Intune** 设备保护 - 如果你的许可证包含 Intune，并且我们检测到你尚未完成 Intune 设置或注册设备，我们建议你创建一个 Intune 策略，以在用户通过移动设备访问组织文件时保护它们。
- **获取每月 Office 功能更新** - 我们已经从非常小的客户提供反馈，他们获取每月的 Office 功能更新时，他们的用户会更满意。 因此，如果你是一家非常小的公司，并且当前每六个月获取一次 Office 功能更新，你将看到此建议。

**设置** <br>
对于设置，已经进行了很多更改。 通常，只需将现有设置更新为新的管理中心样式。 随着我们前进并添加以前从未看到的新设置，我们将在此处开始提及它们。 我们已获得一个整体设置来宣布： **新式验证**。 是的，有一个新设置可打开 **新式验证！** To check out， go to **Settings**  >  **Services & add-ins**  >  **Modern authentication.**

## <a name="april-2019"></a>2019 年 4 月

管理中心看起来非常好。 我们一直在阅读你的反馈和建议，回答大部分反馈和建议，真正将你不得不说出的所有内容都放在心上。 当然，我们仍在努力确保一切与旧管理中心一样。 请记住，当我们推出新功能时，你可能不会马上获得它。

### <a name="featured-feature---add-users"></a>特色功能 - 添加用户

4 月，我们以"添加用户 **"向导为** 特色，引导你完成...等待...添加用户。 这是一个分步操作，可添加用户的基本信息（如电子邮件和 显示名称、分配许可证和角色、添加其联系人信息，然后在提交之前查看用户帐户）。 **我们为什么要进行此更改？** 我们听到您的反馈，您不喜欢几乎无限滚动以在以前的体验中添加用户。
<br> !["添加用户"向导的屏幕捕获。](../media/MAC-AddUserWizard.png) <br>

有两种方法可以签出它： <br>

1. 从 **主页** 上，从 **"用户管理卡** " **中选择"添加** 用户"。 该向导随即打开，因此你不必从正在主页上执行的任何工作 **中** 导航。
2. 转到 **"用户**  >  **活动用户"，** 然后从 **命令栏中** 选择"添加用户"。
<br><br>

我们对用户管理进行了一 **些更改**，下面是一个快速列表：

- " **管理角色** "窗格已更新为新样式，并且可访问。 我们还将"阻止 **用户"和** " **删除用户** "窗格更新为新样式。
- **管理产品许可证** 更改在命令栏中的位置。
- 现在，更改用户的照片更简单。 在 **活动用户** 中选择一个用户，然后 **更改其图片** 下的照片。

### <a name="but-wait-theres-more"></a>但请稍等！ 更多

- 主页上有一个新的设置横幅，如果尚未完成设置步骤，如添加域、添加用户和下载 Office 应用，你将看到该横幅。
- 组 **列表** 和详细信息窗格已更新为新样式。 转到 **"**  >  **组组**"以查看更改。
  - 关于组，我们还向组详细信息窗格添加了 **Microsoft Teams** 选项卡，可在其中将任何 Microsoft 365 组转换为团队。 若要"组合"组，请从列表中选择任何 Microsoft 365 组，选择 **Microsoft Teams** 选项卡，然后 **创建团队**。 如果组已是团队，你可获取从 Teams 管理中心 **管理它的链接**。
  - 最后，你可以将 **Teams 状态添加到****组** 列表。 在列标题上，选择 **"选择列**  >  **Teams 状态保存**  >  **"。**
- **新的受限管理员** 角色 - 我们发布一些新的管理员角色，以便仅为用户提供所需的访问权限。
  - **Kaizala** 管理员：此角色的用户有权在 Microsoft Kaizala 中执行所有管理任务，包括创建和管理 Kaizala 目录中的用户、管理 Kaizala 组、管理操作卡和连接器以及创建服务请求。
  - **搜索管理员**：此角色的用户具有对 Microsoft 365 管理中心中所有 Microsoft 搜索管理功能的完全访问权限。 搜索管理员可以将搜索管理员和搜索编辑器角色委派给用户，并创建和管理内容，如书签、问答&A 项和位置。 此外，这些用户可以查看消息中心、监视服务运行状况以及创建服务请求。
  - **搜索编辑器**：此角色中的用户可以在 Microsoft 365 管理中心创建、管理和删除 Microsoft 搜索的内容，包括书签、问答&和位置。
- 此月有一系列 **帐单** 更改...
  - 现在，您可以更新现有信用卡的 CVV，而无需将其删除并再次添加它。 可以通过进入帐单付款方式来更新  >  CVV。
    - 我们已使查找发票和了解你的帐户可能遇到的任何计费问题变得更加简单。 现在，您可以在 Web 浏览器中查看帐单，而无需下载 PDF。 转到 **"帐单**  >  **发票"。**
    - 在 **"你的产品"** 页面上，如果你已拥有同一类型的多个订阅，我们现在将聚合你的订阅信息。

## <a name="march-2019---weve-officially-released-the-admin-center"></a>2019 年 3 月 - 我们已正式发布管理中心

如果你错过令人兴奋的新闻，我们正式发布新的和改进的 Microsoft 365 管理中心！ 下面是我们宣布它的博客文章：现在提供新的 [Microsoft 365 管理中心](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/The-new-Microsoft-365-admin-center-available-today/ba-p/377870)。 对于 3 月，我们将依赖博客文章来查看发布的功能，此外，还可以阅读有关即将发布的功能的帖子，我们不允许在核心内容中这样做。
<br> ![Microsoft 365 管理中心主页的屏幕截图。](../media/M365AC-HomePage.png) <br>
我们有一个要提及的&订阅区域更改。 我指的是，y't't'all't think we' done with improving it，不是吗？ 因为我们没有！ 事实上，我们这个月添加了管理计费帐户的合作关系  >  **的能力**。 你可以在此处查看顾问、云解决方案提供商和间接经销商之间的合作关系。 还可以接受新的合作伙伴关系请求，包括委派的管理员权限。

与始终一样，您的反馈对我们非常重要，因此请继续提供反馈！ 在管理中心的任何页面上，可以通过选择右下角的"提供反馈"（"需要帮助"旁边）**提供反馈？**

## <a name="february-2019---billing--subscriptions-edition"></a>2019 年 2 月 - &订阅版

这一个月，我们将重点介绍我们对被强烈称为"计费和订阅"的领域进行的所有改进。 过去，你可能没有完全引用那些内容，但我们认为你现在会...

- **付款方式** - 我们收到你的反馈，指出更新付款方式非常困难，我们围绕它进行了大量更改。 转到 **"计费**  >  **付款方式"。** 你可以轻松查看付款方式（如 Visa 卡）及其关联订阅。 In your list of payment methods， select the **More** menu (3 little dots next to the expiration date) ， and then select **View subscriptions.** 您还可以使用"更多"菜单编辑和删除 **付款方式** 。
- **计费帐户** - 定向发布客户将首先看到新的计费帐户页面，然后我们将它向全球推出。 当它可供你使用时，转到 **"计费**  >  **计费"帐户**。 您可以在新的计费帐户页面上执行哪些工作？ 真抱歉您问：
  - 直接从此页面更新组织配置文件中的地址和其他联系人信息。 除非需要，否则不必转到"设置组织  >  "配置文件。
  - 我们正在使直接或批量许可客户更加轻松，你可以接受并查看计费帐户 **的客户协议**。 您还可以与其他组织进行连接，以允许您将组织链接在一起以共享许可证和资源。
- 我们还完成了一些较小的增强功能和 Bug 修复：
  - 使用发票付款重新激活订阅
  - 编辑订阅的服务使用地址
  - 在"清单详细信息"页上，我们添加了一些通知增强功能，我们将你链接到可在其中执行工作的实际页面，并且清单详细信息卡上还有更多操作。 转到任何  >  **发票上的帐单**  >  查看详细信息。

## <a name="january-2019---happy-new-year"></a>2019 年 1 月 - 新一年

- 仍在 **"&** 外接程序中添加 - 我们更新了更多"设置 **">"&加载项** "页面。 试用集成应用或报表，查看最新应用或报表。
- **正在搜索改进功能？** 除了命令栏中的 **"搜索** "框外，再不查找。 它已更新，可让你搜索任务。 例如，请尝试"密码重置"或"添加用户"。

### <a name="featured-feedback-fix---licenses-and-apps"></a>特别推荐的反馈修复 - 许可证和应用

我们根据你的 **反馈** 在用户详细信息窗格中重新组合了许可证和应用。 我们最初将两个功能分开，以提供所有许可证和所有应用可能性的详细信息的空间。 我们收到您的意见，将许可证和应用分为两个窗格，这增加了混淆。 我们聆听了意见，将许可证和应用重新汇集到一个选项卡中。现在，你可以确保在一个窗格中分配给用户的所有许可证中关闭应用。 Cookie 和 Cookie。 许可证和应用。 现在，我们获取它。

签出 **：>活动>"** 编辑或添加用户> **许可证和应用**
