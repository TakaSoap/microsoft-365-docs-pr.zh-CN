---
title: Microsoft 365 管理中心的新增功能有哪些？
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
description: Microsoft 365 管理中心-了解本月添加的功能。
ms.custom:
- MACDashWhatsNew
- AdminSurgePortfolio
ms.openlocfilehash: 64c9939f7dd6c4370b80e74987263942dad0e62f
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208881"
---
# <a name="whats-new-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理中心的新增功能

::: moniker range="o365-21vianet"

> [!NOTE]
> 本文中的某些信息可能不适用于由世纪互联运营的 Office 365。

::: moniker-end

我们不断将新功能添加到 [Microsoft 365 管理中心](microsoft-365-admin-center-preview.md)，修复了我们了解的问题，并根据你的反馈进行了更改。 请查看下面的内容，查看今天可为你提供的内容。 有些功能以不同的速度向客户推出。 如果尚未看到功能， [请尝试将自己添加到目标版本](manage/release-options-in-office-365.md)。

如果你想要了解其他 Microsoft 云服务的新增功能，请执行以下操作：

- [Azure Active Directory 中的新增功能](https://docs.microsoft.com/azure/active-directory/fundamentals/whats-new)
- [Exchange 管理中心中的新增功能](https://docs.microsoft.com/Exchange/whats-new)
- [Microsoft Intune 新增功能](https://docs.microsoft.com/mem/intune/fundamentals/whats-new)
- [Microsoft 365 合规性中心的新增功能](https://docs.microsoft.com/Office365/SecurityCompliance/whats-new)
- [Microsoft 威胁防护的新增功能](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)
- [SharePoint 管理中心的新增功能](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)
- [Office 更新](https://docs.microsoft.com/OfficeUpdates/)

## <a name="ignite-2020-august--september"></a>Ignite 2020 (年9月 &) 

欢迎使用 Microsoft Ignite-我们的第一个仅联机 Ignite。 我们希望在我们的一个会话中看到你： [Microsoft Ignite 2020 Session Catalog](https://myignite.microsoft.com/sessions)。 以下是我们将在 Ignite 中讨论的几个内容。 
> [!NOTE]
> 并不是所有的功能都能立即供所有人使用。 如果你没有看到新功能，请 [加入目标版本](manage/release-options-in-office-365.md)。

### <a name="multi-tenant-management"></a>多租户管理

我们已为多租户管理员开发了一组功能，让你能够更快、更高效地完成工作。

- **你的租户**：在你管理的租户之间快速切换。
- **所有租户**：一个新页面，您可以在其中快速查看所有租户服务、任何打开的服务请求、您的产品和帐单、建议的设置任务以及该租户中的用户数的运行状况。
- **安装程序**： "多租户安装" 页为您提供了 "设置" 页面的列表视图，但为多个租户进行了组织。 您可以查看哪些功能未打开，哪些任务已完成所有租户以及租户仍需要完成的任务。 此视图将帮助您跟踪功能采用情况，并确保始终完成建议的安全设置任务。
- **服务运行状况**：如果任何事件或建议影响租户，则服务运行状况视图将向你显示。 它甚至会告诉你托管的租户中有多少受到影响。 只需选择一个事件即可在 "概述" 选项卡上获取详细信息，然后切换到 "租户受影响" 选项卡，以向下钻取并支持该租户。
- **跨租户邮箱迁移** 是在公共预览版中的一项新服务，它允许您在租户之间移动邮箱，而无需分离，再使用板载邮箱。 
- **跨租户域共享**：不久，您可以加入专用预览，以获取允许您跨多个租户共享域的功能。 例如，如果 Contoso 获取 Wingtip 玩具，Contoso 可以与 Wingtip 玩具共享域，以便两个租户中的人员可以将 "contoso.com" 用作其电子邮件地址。

![具有选定事件的多租户的 "服务运行状况" 页面，且受租户影响的选项卡处于打开状态。 导航菜单将所有租户、安装程序和服务运行状况作为唯一选项。](../media/MAC-WN-MTinServiceHealth.png)

### <a name="monitor-your-most-important-accounts"></a>监视最重要的帐户

您可以监视和跟踪发送给用户的失败或延迟的电子邮件，这些邮件会对业务产生影响，如 CEO。 通过将用户添加到 Microsoft 365 管理中心中的 "优先级帐户" 列表来跟踪优先级帐户。 添加对敏感或高优先级信息具有访问权限的高级管理人员、领导层、经理或其他用户。

优先级帐户仅适用于满足以下两个要求的组织：

- Office 365 E3 或 Microsoft 365 E3，或 Office 365 E5 或 Microsoft 365 E5。
- 至少10000许可证以及至少50个每月活动 Exchange Online 用户。

![功能的设置页面：监视最重要的帐户](../media/MAC-WN-PriorityAccounts.png)

可通过以下两种方法开始操作：

- 转到 " **用户**"，然后在 "其他操作" 菜单中选择 " **管理优先级帐户** "，将用户添加到列表中。
- 转到 " **设置**"，查找 "安装" 任务 " **监视最重要的帐户**"，然后选择 " **开始**"。

有关优先级帐户的详细信息，请查看[针对优先级帐户的](https://docs.microsoft.com/Exchange/mail-flow-best-practices/mail-flow-insights/mfi-email-issues-for-priority-accounts)[监视优先级帐户](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)和电子邮件问题。

### <a name="search-faster-and-get-better-results-from-any-page"></a>更快地搜索并从任何页面获得更好的结果

我们已开始为管理中心推出新的搜索体验，我们无法等待你试用。 ![搜索框已移至横幅区域。 Alt + S 可从任意页面进行搜索。](../media/MAC-WN-GlobalSearch.png)

- 搜索框移到显示 "Microsoft 365 管理中心" 的页眉区域，以便您现在从任何页面（而不只是主页）进行搜索。 我们甚至获得了一个快捷方式： **Alt + S**。
- 搜索更加智能，可提供更好的结果，甚至更快。 尝试键入 "2fa" 以开始。
- 搜索结果按您可以执行的项或操作的类型进行组织。
  - **用户**：选择用户的姓名，可以在此处编辑该用户。 如果您选择其名称旁边的 "更多操作" 菜单，则可以重置其密码。 您可以按显示名称、姓氏、名字、用户名或主电子邮件地址以及电子邮件别名进行搜索。 但是，若要获取完全匹配项，请按主电子邮件地址或用户名进行搜索。
  - **组**：编辑任意页面中的组、添加成员、分配所有者。
  - **操作**：类似于搜索用户和重置其密码的方式，您还可以从任何页面中搜索 "重置密码"，然后为用户重置一个或多个密码。
  - **导航**：导航中的结果可以快速帮助您快速访问 "管理中心" 中的页面。 例如，搜索 "角色" 将转到 Azure AD 角色的角色页面。
  - **设置**：搜索与您的组织相关的任何设置、您订阅的服务以及安全和隐私设置。 
  - **域**：您可以找到指向您的域的快速链接，然后链接将转到该域的 "概述" 和 "运行状况" 页面。
  - **文档**：如果我们找不到你的结果，我们将尝试查找一些文档来寻求帮助。 Curated 列表中的文章若要查找匹配项需要一些时间，因此请等待一秒钟，让搜索查找结果。 
  - **反馈**：未找到你要查找的内容？ 向我们发送来自搜索的反馈。 我们将在管理中心中添加更多页面和更多功能的搜索功能。

### <a name="microsoft-365-admin-mobile-app"></a>Microsoft 365 管理移动应用

你的订阅中附带的 [microsoft 365 管理移动应用](https://www.microsoft.com/microsoft-365/business/manage-office-365-admin-app)可让你从移动设备管理 microsoft 365，这样你就可以离开办公桌去执行日常任务。 事实上，在应用程序中有超过90个功能，我们只添加了几个功能：

- **支持 Microsoft Intune 的移动应用程序管理和条件访问策略**：现在，你可以使用你的个人设备来管理 Microsoft 365，即使你的组织已启用 Intune 的移动应用程序管理和条件访问策略也是如此。
- **邮件中心通知**： **Settings**  >  如果希望收到有关新邮件中心帖子的警报，请在设置**通知**中打开邮件中心通知。 通过通知，我们希望确保你随时了解租户中的重要信息和事件。
- **帐单通知**： **Settings**  >  如果要在订阅即将过期时在设备上获取计费通知，则还可以在设置**通知**中打开计费通知。
- **深色模式**：欢迎使用移动应用程序的黑色侧边。 这是我们最常请求的功能之一。 转到 "**设置**  >  "**主题**将其打开。
- **报告问题**：现在可以报告应用中的问题或查看其他管理员报告的问题。 请访问 **服务运行状况** 以将其签出。

![Microsoft 365 admin 应用中的 "运行状况" 页，其中包含有关消息中心、服务运行状况和计费警报的通知。](../media/MAC-WN-AdminMobileApp.png)

### <a name="usage-recommendations-for-small-and-medium-businesses"></a>中小型企业的使用建议

如果组织中的某些人员不积极使用团队、OneDrive 或 Office 应用，则中小型企业可能会在 **主页** 上获得建议。 在查看建议时，可以快速将 Microsoft 培训的电子邮件发送给非活动用户，以帮助他们开始使用应用程序，并确保从你的订阅中获取全部价值。

### <a name="remote-work-collection"></a>远程工作集合

在10月，我们将添加一个远程工作集，以帮助小型企业所有者和员工在远程工作。  **远程工作重点** 安装程序是 Microsoft 建议安全启用远程工作和有效协作的所有功能的 curated 列表。 在几周内，你可以在**安装**  >  **远程工作概要**中试用它。

![安装中有7个任务的远程工作重点页未启动。](../media/MAC-WN-RemoteWork.png)

若要详细了解如何安全地允许远程工作和便于记忆和共享的方便的 web 地址，请转到 [aka.ms/remote-business](https://aka.ms/remote-business)。

### <a name="need-help-moving-to-more-admin-centers"></a>需要帮助？移动到更多管理中心

我们将连续查看并更新内容和工具，以及时掌握产品中的更改。 现在，我们提供了更多自助服务诊断工具，可帮助您快速高效地解决问题。 以下是最近添加的少数几项：

- 更改 Exchange Web 服务限制策略
- 检查团队预配和验证对特定用户的状态
- 修复 DKIM 安装问题
- 诊断 Intune 用户注册错误

我们正在推出您在 Microsoft 365 管理中心中已看到的新的和改进的支持体验。 团队管理中心和安全性和合规性管理中心已具有此新体验。 此外， **Exchange 管理中心**、 **SharePoint 管理中心**和 **Office.com** 将随管理员的这一新帮助体验进行更新。

### <a name="manage-changes-with-microsoft-planner"></a>使用 Microsoft Planner 管理更改

在5月，我们宣布你将很快能够将邮件中心帖子同步到 Microsoft Planner，现在它可供所有人使用。  您现在可以从邮件中创建任务，对其进行分配，并将其跟踪到完成。 首次选择 " **Planner 同步** " 时，您需要连接到相应的计划。

!["首选项" 按钮旁边的命令栏中突出显示了 "规划同步" 的 "邮件中心" 页。](../media/MAC-WN-MCPlannerSync.png)

若要了解详细信息，请查看本文和视频以了解其工作方式： [在 Planner 中跟踪你的消息中心帖子](https://docs.microsoft.com/Office365/Planner/track-message-center-tasks-planner)

### <a name="documentation-training-and-videos"></a>文档、培训和视频

- Microsoft Ignite--[虚拟集线器](https://adoption.microsoft.com/virtual-hub/)的全新和实时全新品牌。 深入了解 IT 专业人员和开发人员的技术培训。 作为 #SIDETRACKED 的一部分，快速查找20个新视频，这一年的 Ignite 管理跟踪的名称。
- [Microsoft 365 视频系列的新增](https://www.youtube.com/watch?v=OVjb2lGJ4GU&t=2s) 功能：本月，我们介绍了在团队和 web 上的白板中提供的新功能、如何自动执行向 Azure AD 的用户预配、新的 Power 自动执行团队中的触发器和操作等。 并在下个月中保持关注，我们将在 Ignite 中获得所有极好的事情的回顾！
- 我们已对 [Microsoft 365 文档](https://docs.microsoft.com/microsoft-365) 页面进行了重新设计，重点介绍了解决方案。 我们将重点介绍在此页面上可用的新解决方案，因此请立即注意。

![适用于 Microsoft 365 解决方案文档的新登陆页，其中包含 "提供远程工作人员" 等解决方案。](../media/MAC-WN-M365Docspage.png)

## <a name="july-2020"></a>2020 年 7 月

### <a name="getting-ready-for-ignite-2020"></a>准备 Ignite 2020

正如我们在 Microsoft 的 Ignite 赛季中所做的那样，我们没有发布许多功能，因此我们在会话过程中有很多讨论。

本文的下一次更新将在最初仅联机 Ignite 的开始日期。 在今年，它可以自由参加！ 将其签出，请进行注册： [Microsoft Ignite 2020](https://www.microsoft.com/ignite)。

### <a name="your-products"></a>你的产品

在 "订阅管理" 中完成了大量工作，以使页面的加载速度更快，更快地查找要查找的内容，并满足 ([WCAG 2.1 准则](http://www.w3.org/TR/WCAG21/)) 的 web 辅助功能标准。

- **表重新设计**：表已经过重新设计，以便您可以对相似的订阅进行分组。 转到 "**付费**  >  **产品**"。
- **产品详细信息**：通过选择列表中的产品获取有关你的订阅的更多详细信息。
- **从此处完成所有**操作：无需转到多个页面来管理一个产品。 例如，如果您需要取消订阅，面板将打开以在此处执行操作。

!["产品" 页面，并打开 "取消订阅" 面板。](../media/MAC-WN-SubscrDetails.png)

### <a name="domains"></a>域

域管理可能非常复杂，我们已发布了一项新功能，使其变得更加轻松。 转到 "设置" > 域，然后选择一个域以获取有关您的域和域的运行状况的详细信息。

:::image type="content" source="../media/MAC-WN-DomainDNS.PNG" alt-text="Contoso.com 的域详细信息页面":::

### <a name="docs-training-and-videos-july-2020"></a>2020年7月 (文档、培训和视频) 

[Microsoft 365](https://youtu.be/m1Nu8WJgCDY) 视频系列的新增功能：本月，我们将介绍新的 yammer 体验，适用于 web 和移动、如何将 yammer 社区应用程序与 Microsoft 团队集成、支持 Firstline 工作线程和经理的新策略包等。

## <a name="june-2020"></a>2020 年 6 月

### <a name="keeping-up-with-office-whats-new-management"></a>与 Office 保持最新的管理

几个月前，我们添加了一个设置，通过它可以管理 [在用户的 Office 应用中显示的内容的新增消息](#office-whats-new-management)。 本月，我们发布了一个新的主页卡片，可帮助你快速操作并跟踪你希望向组织中的用户显示的 **新** 消息。

### <a name="docs-training-and-videos-june"></a> (六月) 的文档、培训和视频

- [团队入门](https://support.microsoft.com/office/184f1aba-2f91-43f0-86e1-9fae607e24f6)

## <a name="may-2020"></a>2020 年 5 月

### <a name="new-update-channel-for-office"></a>Office 的新更新频道

5月12日，我们宣布推出新的 Office 更新频道：每月企业频道的可用性。 此更新频道在每月的第二个星期二为你的用户提供新的 Office 功能。

如果您允许用户从门户自行安装 Office，则可以为其选择每月的企业频道。 为此，请登录 Microsoft 365 管理中心并转到 "**显示所有**  > **设置**" "  >  **组织**  >  **Services**  >  **Office 软件下载设置**"。 如果选择 " **每月一次， (每月企业频道) **"，则会将 Office 的任何新的自安装配置为使用每月企业版频道。

与每月企业频道的发布一起，我们还将修订现有更新频道的名称。 例如，每月频道将被重命名为当前频道。 新名称将在2020年6月9日生效。

有关详细信息，请参阅 [对 Microsoft 365 应用更新频道的更改](https://docs.microsoft.com/DeployOffice/update-channels-changes)。

### <a name="new-admin-roles"></a>新管理员角色

我们已将一些新的 Azure Active Directory 管理员角色添加到 Microsoft 365 管理中心。

- 混合标识管理员角色向用户提供管理云设置和身份验证服务的权限。
- 通过网络管理员角色，用户可以管理网络位置并查看 Microsoft 365 软件作为服务应用程序的网络见解。
- 打印机管理员角色授予管理打印机和打印机连接的所有方面的权限。
- 打印机技术人员是打印机管理员角色的子集，用户可在其中注册和注销打印机，并更新打印机状态。
若要了解有关这些角色的详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

### <a name="export-groups-list"></a>导出组列表

我们从很多管理员那里听说过，他们需要共享有关组的信息以及他们对管理员中心不具有访问权限的人员的使用。 现在，您可以将 "组" 列表导出为 CSV 文件，以进行审核，这意味着您可以扔掉旧的 PowerShell 脚本。 若要试用，请转到 "**组**  >  **Groups**" 组，然后从命令栏中选择 "**导出组**"。

### <a name="microsoft-365-solution-and-architecture-center"></a>Microsoft 365 解决方案和体系结构中心

仅在本月发布了一个 [https://docs.microsoft.com](https://docs.microsoft.com) 名为 [Microsoft 365 解决方案和体系结构中心](https://docs.microsoft.com/microsoft-365/solutions/solution-architecture-center)的新网站，该网站提供了了解、规划和实施集成的 Microsoft 365 解决方案以实现安全和合规协作所需的技术指导。 在此中心中，你将发现：

- 基础解决方案指南
- 工作负载解决方案和方案指南
- 海报 (的解决方案和体系结构插图!!!) 
- 特定于行业的指南
- 企业体系结构设计主体

### <a name="docs-training-and-videos-may"></a> (可能) 的文档、培训和视频

- **Microsoft 365 video 系列中的新增功能**：本月，我们将在团队管理员和安全与合规中心、规划器与邮件中心的集成以及 Microsoft 团队中的新的3x3 视频布局中介绍新的支持体验。 
- [Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/)页面已更新，可帮助您更快地找到所需内容。 如果你现在查看此页，我们添加了卡片以通知你重要更新和更改。

## <a name="april-2020"></a>2020 年 4 月

### <a name="intune-roles-management"></a>Intune 角色管理

[2020 年 4 月](#april-2020)

嗯，我们做了！ 我们已采用了统一角色体验的第二步，你现在可以在 Microsoft 365 管理中心管理 Intune 角色。 您还可以利用功能（如搜索角色和查看角色权限的功能）。 这意味着，您不需要两个单独的工具来管理 Microsoft 365 和 Intune 的角色。 登录到 Microsoft 365 管理中心后，你将看到 "角色" 页面上有两个透视，一个用于 Azure AD，另一个用于 Intune。

![选择了 Intune 数据透视的 "角色" 页](../media/MAC-WN-IntuneRoles.png)

### <a name="sync-message-center-posts-to-planner"></a>将邮件中心发布内容同步到规划器

从可能的开始，在目标版本中的管理员将开始查看邮件中心的 "Planner 同步" 按钮。 现在，您可以跟踪需要操作的邮件，选择要跟踪的邮件类型，分配要作为任务跟踪的邮件，并标记邮件以供以后注意。

[加入目标发行版](manage/release-options-in-office-365.md) 以开始！

### <a name="need-help-launched-in-teams-admin-center--security-and-compliance-centers"></a>"需要帮助？" 在团队管理中心中启动 & 安全与合规中心

团队管理中心、安全中心和合规性中心现在使用相同的 "需要帮助？" Microsoft 365 管理中心用于查找帮助和联系支持的功能。 我们收到了来自管理员的大量反馈，你希望获得相同级别的帮助和支持，我们乐意为你带来这种情况。 请试用并向我们提供反馈！

#### <a name="need-chat"></a>需要聊天？

我们的支持代理已在家工作，同时仍接受客户案例和 internet 带宽限制，同时在家工作可能会影响客户呼叫质量。 为了继续支持，我们已为 Microsoft 365 管理中心的商业客户启动 live chat 支持选项。

创建服务请求时，除了电话和电子邮件，您现在还会看到 "聊天" 作为一个选项。 选择 "聊天" 作为通信的首选渠道并创建请求。 创建请求后，可以在准备好与 Microsoft 代理聊天时启动聊天。

### <a name="teams-updates"></a>团队更新

随着团队使用的提高，我们添加了几个功能来帮助您管理它们。

- "管理中心" 主页上的新建议卡片显示了哪些用户的活动团队的30天未被使用。 您可以向这些用户发送培训电子邮件，让他们使用团队开始使用。
- 将**人员与团队一起使用**：转到 "**设置**" 以查看新页面，以帮助你打开授权用户的团队并允许来宾访问，以便你可以与团队中的外部客户协作。
- 现在，Microsoft 团队卡片在默认情况下固定到主页。 它显示团队是否已打开，以及是否允许来宾访问。 它还允许您检查新授权团队用户的安装状态，并检查网络问题是否可能影响团队用户。
- 最后，如果您购买了包含团队的许可证，则团队现在是最初设置流中的一个步骤。

### <a name="productivity-score"></a>生产力分数

生产效率分数提供了有关用户如何使用 Microsoft 云服务和支持这些服务的技术体验的见解。 分数反映了组织在员工和技术经验方面的绩效，并将您的成绩与您的组织（如您的组织）进行比较。 本月，我们将为预览体验引入以下新概念：

- 主页的主要见解和类别详细信息页面的趋势视图-添加到技术经验中的终结点分析和网络连接类别
- 员工体验类别中显示的相关技术体验见解
- 作为员工体验一部分的新通信类别
- 员工体验类别中具有组织元数据的用户详细信息

如果你想了解详细信息，请查看博客： [使用 Microsoft 工作效率分数衡量和改进 microsoft 365 体验](https://techcommunity.microsoft.com/t5/microsoft-365-blog/measure-and-improve-the-microsoft-365-experience-with-microsoft/ba-p/1348618)。 工作效率分数目前处于私人预览版中。 [加入 "生产力分数" "私人预览"](https://aka.ms/productivityscorepreview) 以开始。

### <a name="groups-updates"></a>组更新

本月我们为组提供了两项更新：

- 现在，您可以编辑 Office 365 组的电子邮件地址 (也称为 "组" 在 Outlook 中，并且很快称为 "Microsoft 365 组") 。
- 我们已听取你的反馈意见，我们添加了更清楚的错误消息，了解为什么无法将组转换为 Microsoft 团队。

### <a name="docs-videos-and-training-april"></a> (四月) 的文档、视频和培训

**Microsoft 365 video 系列中的新增功能**：本月，我们将介绍一些提示和资源，以帮助小型企业过渡到远程工作，包括如何实施 Microsoft 团队、远程工作培训资源以与客户和合作伙伴保持联系，以及新的 Microsoft 365 商业语音计划。 [Microsoft 365 中的新增功能](https://go.microsoft.com/fwlink/p/?linkid=2118096)

#### <a name="for-your-users"></a>为您的用户

- [安排会议](https://support.microsoft.com/office/c61b4f61-ee62-4a06-8bf7-0a1cd302700a)
- [加入团队会议](https://support.microsoft.com/office/078e9868-f1aa-4414-8bb9-ee88e9236ee4)
- [创建组织范围的团队](https://support.microsoft.com/office/037bb27a-bcc9-48fe-8d72-44d9482420a3)
- [以来宾身份创建团队](https://support.microsoft.com/office/11fbb083-52ee-434d-8c6e-63711fdafac7)
- [将团队加入为来宾](https://support.microsoft.com/office/928d1eef-61e2-49ec-b754-c2fe86b34824)
- [创建组电子邮件地址](https://support.microsoft.com/office/ded875f9-a9de-437f-b559-2ae4f235bb2b)

#### <a name="for-admins-and-business-owners"></a>对于管理员和企业所有者

- [通过远程工作为小型企业提供支持](https://support.microsoft.com/office/9b91a85a-39b4-40a6-a590-0f9bea0ba8e6)
- [运行远程小型企业](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)
- [注册 Microsoft 商业基本版](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)
- [设置双因素登录](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)

## <a name="march-2020"></a>2020 年 3 月

### <a name="featured-feedback-fix-improve-add-user-reliability-for-licensing"></a>特色反馈修复：提高 "添加用户" 的许可可靠性

我们收到了关于管理员在添加用户时分配许可证的困难程度的大量反馈。 我们已对此修补程序进行了第一次更新，我们已迁移到幕后的更可靠服务以处理这些请求。 如果出现问题，您现在将收到一条错误消息，允许您重试。

![添加包含错误的用户确认页。](../media/MAC-WN-ImprovedLicensing.png)

### <a name="microsoft-teams-home-page-card"></a>Microsoft 团队主页卡片

使用 uptick 在团队使用中，一些 emc 将会获取一个固定的仪表板卡片，使团队更易于发现。 该卡片还提供了指向培训和文档的链接，可帮助您的组织过渡到远程工作。 只需转到 " **主页** " 即可查看新卡片。

![Microsoft 团队主页卡片](../media/MAC-WN-TeamsCard.PNG)

### <a name="customize-your-organizations-sharepoint-mobile-app-theme"></a>自定义组织的 SharePoint 移动应用主题

通过使用 Microsoft 365 管理中心，您可以在适用于 Android 的 SharePoint 移动应用中自定义组织的主题和适用于 Android 的 SharePoint 移动应用。 此功能可方便地提供移动 intranet 应用体验，使员工可以在旅途中与您的 SharePoint Online 相匹配。 主题自定义项包括您的徽标图像、导航栏颜色、文本和图标颜色以及强调文字颜色，从而便于识别。

![将管理中心设置映射到移动应用的关系图。](../media/MAC-WN-CustThemeSP.png)

### <a name="improvements-to-the-add-a-group-wizard"></a>对 "添加组" 向导的改进

当管理员创建一个新的组并将其作为同一时间的团队时，他们可以分配没有包含团队的许可证的所有者。 这就产生了一些麻烦。 我们已更新向导流，以验证所有者是否具有团队许可证，以及他们是否不选择将组转换为团队已禁用。

### <a name="microsoft-365-offerings-for-small-and-medium-businesses"></a>适用于中小型企业的 Microsoft 365 产品

我们知道，这是下个月的一次通知，但我们想要确保你做好准备。

从4月21日起，我们将对中小型企业的 Office 365 订阅（和 Office 365 专业增强版进行更改）。 这些产品现在将使用 Microsoft 365 品牌。

新产品名称将在2020年4月21日生效。 这只是产品名称的更改，目前没有任何定价或功能更改。

|当前名称 |新的名称  |
|---------|---------|
|Office 365 商业协作版     |   Microsoft 365 商业基础版      |
|Office 365 商业高级版     |    Microsoft 365 商业标准版     |
|Microsoft 365 商业版     |    Microsoft 365 商业高级版     |
|Office 365 商业版     |    Microsoft 365 商业应用版       |
|Office 365 专业增强版    |   适用于企业的 Microsoft 365 应用程序      |

### <a name="videos-training-and-docs"></a>视频、培训和文档

[Microsoft 365 web 系列中的新增功能](https://go.microsoft.com/fwlink/p/?linkid=2118096)：在本月的几个部分中，我们突出显示了 microsoft 团队的3年周年纪念日，并涵盖了新功能，包括在线会议中改进的音频质量、有关 firstline 管理器的目标通信、团队和 Skype 消费者互操作性等。

## <a name="february-2020"></a>2020 年 2 月

### <a name="featured-feedback-fix-multi-organization-switcher"></a>特色反馈修复：多组织切换器

我们收到了来自合作伙伴和管理员的大量反馈，其中涉及管理多个 Microsoft 云 emc 的挑战。 我们的第一个多组织管理功能是 **组织切换**器，它使您可以在只需2次单击即可在您管理的 emc 之间进行更改。
> [!TIP]
> 您无需执行任何操作即可使组织切换器显示，只要您是至少一个组织的记录合作伙伴即可。

1. 在 Microsoft 365 管理中心，选择组织名称。
![屏幕捕获：主页的顶部，显示带有切换器图标的组织配置文件名称。](../media/MAC-Organization-switcher.png)

2. 在 "组织切换器" 中，选择要管理的组织。
![屏幕捕获：我的组织使用整合的 Messenger 的租户切换器租户突出显示](../media/MAC-OrgSwitcherSelected.png)

这就是它!!!

### <a name="groups"></a>组

本月的 "组" 区域中的两个更改：

- **按组名称排序**：您可以通过选择 " **组名称** " 列按字母顺序对组列表进行排序。
- **还原已删除的 microsoft 365 组**：无需再转到 Exchange 管理中心即可还原已删除的 microsoft 365 组。 转到 **Microsoft 365 管理中心** \> **组** \> **已删除组** \> (从列表) \> **还原组**中选择一个组。 它会将组还原回 " **组** " 列表，并还原组的电子邮件、对话、笔记本、文件和日历。

### <a name="videos-training-and-docs-february"></a> (二月) 的视频、培训和文档

- **Microsoft 365 video 系列中的新增**功能：本月，我们重点介绍了 SharePoint Online 的自定义搜索功能、Office "新增功能" 管理功能，可让您通过应用程序帮助窗格、最新的安全性和 Yammer 中的兼容性更新等，在最终用户中显示或隐藏特定功能。 以下是最新的剧集： [Microsoft 365 的新增功能](https://go.microsoft.com/fwlink/p/?linkid=2118096)

- **文档移动**：我们将 Office 365 管理 web 文章与 Microsoft 365 内容组合在一起，你可能会注意到新的 URL。 例如，本文的宿主使用的是： **docs.microsoft.com/Office365/Admin/whats-new-in-preview**，但现在 URL 为： **docs.microsoft.com/microsoft-365/admin/whats-new-in-preview**。 如果已将页面设置为书签，则应更新链接;但是，内容链接将被重定向到新的内容存储库。

## <a name="january-2020---happy-new-year"></a>2020年1月-新年快乐

> [!NOTE]
> 您是否知道 YouTube 上的 [Microsoft 365 视频系列中有哪些新增功能](https://go.microsoft.com/fwlink/p/?linkid=2118096) ？ 它突出显示了我们向用户推出的最新功能。 在每个月，我们将开始链接到 " [视频、培训和文档](#videos-training-and-docs) " 部分中的最新剧集。 <br> <br> 以下是最新的剧集： [Microsoft 365 的新增功能](https://go.microsoft.com/fwlink/p/?linkid=2118096)

### <a name="dark-mode"></a>深色模式

当我们首次推出深色模式时，它仅在主页上可用。 深色模式现在处于预览阶段，位于管理中心内的大多数页面的目标版本中。

1. 首先，需要打开目标版本：转到 "设置" " **Settings** \> **Settings** \> **组织配置文件** \> **发布首选项**"。
1. 然后，若要打开深色模式，请转到 **主页** ，然后选择 " **深色模式** " 按钮。  (它位于 **搜索** 字段旁边，这篇文章的 " **新增功能** " 链接。 ) 
1. 对于任何可用的深色模式的页面，该按钮位于页面顶部，位于 **新管理中心** 切换的旁边。

### <a name="office-whats-new-management"></a>Office 的新增功能管理

管理员希望控制 Microsoft 如何在 Office 应用程序中向其用户传达 "新增功能"，现在您可以使用该控件。 转到 " **设置**" " \> **Office 新增功能管理预览**"。 选择要查看其详细信息的功能，如果您不希望您的用户看到特定的 "最近更新" 消息，则可以选择 " **从用户隐藏** " 按钮。 例如，你的组织可能正在等待用户了解功能，直到你的组织中的所有人都接受培训。

![Office 的屏幕抓图功能的 "详细信息" 窗格打开的新预览。](../media/whatsnew-officemgmt-preview.png)

此功能首次发布以在11月预览，但有几个功能更新需要了解： [Office 新增内容管理预览更新现已推出](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-preview/ba-p/1020438)

### <a name="partners"></a>合作伙伴

Howdy，合作伙伴！  (无法帮助我。 ) 我们也为你提供了本月更新。 有一项新功能，允许合作伙伴为 CSP 客户提供选择，以接受其 Microsoft 客户协议 (MCA) 在管理中心的 " **付费帐户** " 部分。 在这一新体验中：

1. 客户接收带有链接的邀请电子邮件，以接受合作伙伴关系和 MCA。
2. 客户登录后，他们可以查看和接受来自管理中心的 MCA 和合作伙伴权限。

### <a name="resource-mailboxes"></a>资源邮箱

已将资源邮箱列表更新为新样式。 在 Microsoft 365 管理中心，请转到 **Resources** \> **会议室 & 设备**。

### <a name="videos-training-and-docs-january"></a> (一月) 的视频、培训和文档

查看我们在1月发布的小型企业管理员培训：

- [创建业务网站](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9)
- [查找答案和帮助](https://support.microsoft.com/office/7f681212-c649-4a3e-a43b-32b1d1e58988)
- [获取帮助或支持](https://support.microsoft.com/office/18948a4c-3eb1-4b30-b1bc-a4cc29eb7655)
- [删除用户](https://support.microsoft.com/office/6bcdad7b-732a-4260-997a-8c176bc3d9d6)
- [选择 Microsoft 订阅](https://support.microsoft.com/office/b9f7c78e-430f-4117-89ec-2eeb1dced2ca)
- [Microsoft 365 for business security 概述](https://support.microsoft.com/office/3274b159-a825-46d7-9421-7d6e209389d1)

## <a name="november-and-december-2019"></a>11月和12月2019

我们正在组合11月和12月的新闻，因为在 Ignite 后，我们要做的通知很少。 在新年中看到你！

### <a name="change-from-credit-card-to-invoice-payment"></a>从信用卡更改为发票付款

我们开始推出将支付方式从信用卡更改为发票的功能。 转到 "**付费** \> **产品**"，选择订阅，然后选择信用卡付款旁边的 "**编辑**" 链接。

![屏幕捕获：订阅卡的记帐部分，信用卡以信用卡作为支付方式。](../media/MAC-BillingEditCreditCard.png)

想要了解更多相关信息？ [从信用卡或银行帐户更改为发票](../commerce/billing-and-payments/change-payment-method.md)

### <a name="global-reader"></a>全局读取者

我们在 [10 月 2019-Ignite Edition](#october-2019---ignite-edition)中提到了全局读者角色，但随着它更广泛地推出，我们将讨论一些详细信息：

- 全局读取器角色是全局管理员角色的只读对应角色。 全局读者可以查看全局管理员有权执行的所有操作。
- 除了一些例外情况（如某些合规性和安全功能），全局读者有权查看您的组织授权使用的所有 Microsoft 云管理中心。
- 将全局读者角色分配给需要 it 人员进行规划、审核和调查的用户。
- 您还可以将全局读者角色与具有较少权限的另一个角色结合使用。 例如，可能会为小型企业所有者分配**帐单管理**  +  **全局读者**角色，以便他们可以支付帐单并随时了解其云组织的更改。
- 全局读者可以转到 Microsoft 365 管理中心中的任何页面。 当用户打开可编辑页面时，顶部会出现一条警告，告知他们没有保存更改的权限，并且 "保存" 按钮将被禁用。

我们乐意向你提供有关全局读者角色的反馈以及你希望将来查看的任何基于角色的权限。 [为基于角色的权限提供反馈](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/10115430-have-a-consistent-experience-when-assigning-admin)

### <a name="new-settings-page"></a>新设置页

**组织配置文件**、**安全性 & 隐私**和**服务 & 加载项**页面已全部组合到一个具有3个垂直选项卡的页面中。 和最佳部件--从一个位置开始，您现在可以搜索所有设置。
!["屏幕捕获：包含" "搜索所有设置" 字段在页面顶部突出显示的 "设置" 页。](../media/MAC-SettingsMultiPivotSearch.png)

### <a name="training--docs"></a>培训 & 文档

此部分是本文的一项新功能，我们将开始链接到我们认为你会感兴趣的新培训和文档。

在11月，我们发布了非常多 [关于 Microsoft 学习](https://docs.microsoft.com/learn/) 网站的学习途径，可帮助 IT 专业人员学习并获得 microsoft 365 的培训。 将其签出：

- [Microsoft 365 基础知识](https://docs.microsoft.com/learn/paths/m365-fundamentals/)
- [扩展 Office 基础](https://docs.microsoft.com/learn/paths/extend-office-fundamentals/)
- [Microsoft 365-使用适用于企业的 Windows 10 和 Microsoft 365 应用程序现代化企业级部署](https://docs.microsoft.com/learn/paths/m365-getmodern/)
- [使用 Microsoft 365 管理企业部署](https://docs.microsoft.com/learn/paths/manage-enterprise-deployment-m365/)
- [大规模升级 Microsoft Office for IT](https://docs.microsoft.com/learn/paths/m365-office-for-it/)
- [通过 Windows 虚拟桌面提供 Azure 中的远程桌面和应用 ](https://docs.microsoft.com/learn/paths/m365-wvd/)
- [使用 Microsoft 365 和 Surface for Business 使你的工作场所现代化](https://docs.microsoft.com/learn/paths/modernize-workplace-with-m365-and-surface/)
- [使用 Microsoft 365 保护标识和访问](https://docs.microsoft.com/learn/paths/m365-identity/)
- [使用 Microsoft 365 保护企业信息](https://docs.microsoft.com/learn/paths/m365-information-protection/)
- [使用 Microsoft 365 管理安全性](https://docs.microsoft.com/learn/paths/m365-security-management/)
- [使用 Microsoft 365 和 Microsoft 威胁防护防御威胁](https://docs.microsoft.com/learn/paths/m365-security-threat-protection/)
- [使用 Microsoft Teams 管理团队协作](https://docs.microsoft.com/learn/paths/m365-manage-team-collaboration/)
- [在 Microsoft 365 中配合使用 SharePoint](https://docs.microsoft.com/learn/paths/m365-teams-sharepoint/)

## <a name="october-2019---ignite-edition"></a>10月 2019-Ignite Edition

欢迎使用 Microsoft 365 管理中心中新增功能的 Ignite 版本！ 当然，这不是通知的完整列表，但这里有几个突出介绍。 此外，请查看 Ignite 博客，获取有关发布的更好的信息：

- [Microsoft 365 的管理员安全性、生产力和网络增强功能](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/ADMIN-Security-Productivity-and-Network-Enhancements-for/ba-p/964019)。
- [Microsoft 团队中的新增功能-Ignite 2020](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-New-in-Microsoft-Teams-Ignite-2019/ba-p/937025)。

### <a name="role-based-access-control"></a>基于角色的访问控制

由于我们在6月开始推出，对管理中心中的角色进行了大量更改：

- **比较角色** -最多选择3个角色以比较每个角色的权限。 这将帮助您找到要分配给用户的最小的许可角色。 转到 " **角色**"，使用第一列中的 "多重选择" 复选框选择最多3个角色，然后选择 " **比较角色**"。

    ![比较 Exchange 管理员、技术支持管理员和用户管理员角色。](../media/RBAC-CompareRoles.png)

- **收藏夹** -您可以将星形添加到您喜欢的角色或大多数使用的角色，以便通过对列进行排序或创建筛选器来轻松地找到它们。
- **活动用户**  > **管理角色**-已对此进行了更新，以与角色中的更改保持一致。 与 "角色" 列表一样，我们已将角色的默认列表范围限定为最有用，但您可以通过展开 " **按类别显示所有**角色" 来查看所有角色。
- **全局读者角色** -你需要了解！ 没问题！ [全局读者](add-users/about-admin-roles.md)角色！

### <a name="report-an-issue"></a>报告问题

服务运行状况已更新为新样式，如果您受到您的服务运行状况仪表板上未显示的问题的影响，您可以 **报告问题** 以让 Microsoft 知道。 转到**运行状况**  >  **服务运行状况**。

### <a name="viral-subscriptions"></a>"病毒" 订阅

如你所知，用户可以打开对大量产品（如 Power BI 和应用程序连接）的免费订阅。 现在，你可以看到你的用户尝试的 "病毒订阅"。 转到 "**付费**  >  **产品**"。 选择 "订阅" 选项卡上的 " **帐户类型** " 筛选器，以查看用户购买的订阅。 如果需要，你现在可以从你的帐户中删除这些订阅。

### <a name="user-templates"></a>用户模板

模板使您可以通过保存和重用这些用户的共享设置来轻松地添加多个用户。 您可以保存角色的值、已分配的许可证、联系人信息、位置等。 使用模板创建新用户时，将自动获取这些设置的保存值。 转到 "**用户**  >  **活动用户**"，然后选择 "**用户模板**" 以试用。

### <a name="office-whats-new-management-preview"></a>Office "新增功能" 管理 (预览) 

将重要的 Office 功能发布到 Office 应用程序时，用户将获得 "新增功能" 卡片以了解新功能。 如果不希望用户看到该卡片，可以将其隐藏。 您还可以选择希望用户通过显示来查看卡片的时间。 转到 "**设置**" "  >  **Office 新增功能管理**" 以将其签出。

### <a name="sharepoint-url-change"></a>SharePoint URL 更改

从技术上讲，这不是 Microsoft 365 管理中心的新闻，但我们非常兴奋我们想确保你看到以下新闻：
> [!IMPORTANT]
> 现在，你可以使用常规 URL 访问你的 SharePoint 管理中心： [https://admin.microsoft.com/SharePoint](https://admin.microsoft.com/SharePoint)

有关详细信息，请参阅 [SharePoint 管理中心中的新增功能](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)。

## <a name="september-2019"></a>2019 年 9 月

我们将在 Ignite 2019 推出一些激动人心的功能版本，因此我们只宣布在九月发布了几个新功能。 但请密切关注下个月的文章，它将在 Ignite 的第一天发布！

### <a name="featured-feedback-fix--the-option-to-convert-the-deleted-users-mailbox-to-a-shared-mailbox-is-back"></a>特色反馈修复–将已删除用户的邮箱转换为共享邮箱的选项将返回

我们听到你的反馈很大并清楚，我们重新提供了让其他人通过将已删除用户的邮箱转换为 **共享邮箱**来访问该邮箱的功能。 将此项添加回 "删除用户" 向导，可以决定要对数据执行的操作：

- 电子邮件：通过将其转换为共享邮箱，让其他人能够访问已删除用户的邮箱。
- 文件：保存其 OneDrive 文件并为他人提供访问权限。
- 权限：如果其他人有权访问此邮箱，则删除权限。
- 别名：删除电子邮件别名，使其可立即用于其他用户。
![屏幕捕获：使用电子邮件别名、权限、OneDrive 和电子邮件选项显示的删除用户向导](../media/WhatsNew-DeleteUserWiz.png)

### <a name="initial-setup"></a>初始设置

我们的初始安装向导有一个更新： Microsoft 365 for business。 这些步骤已经过简化，我们已将两个设置任务移动到设置页面：

- **安全 windows 10 计算机** -设置策略以更好地保护 Windows 10 设备免受受黑客攻击的病毒、恶意软件和攻击。
- **自动安装 Office** -当你启用此设置且用户已将其电脑连接到 Microsoft 365 商业版时，其计算机会自动更新到最新的 Office 应用程序，并保持最新。

## <a name="august-2019"></a>2019 年 8 月

### <a name="billing"></a>计费

本月我们提供了有关帐单和订阅的一些更新：

- 基于设备的订阅：可以为 Microsoft 365 管理中心内的设备分配或取消分配 **microsoft 365 应用程序教育版 (设备) ** 许可证。 **Microsoft 365 教育版 (设备) ** 是一个附加许可证，允许您将许可证分配给设备。 转到 "**付费**  >  **产品**" 以查找并购买许可证。
- 基于用户的许可证管理：我们已更新了如何将**用户**  >  **活动用户**中的许可证分配给新样式。 有关详细信息，请参阅：
  - [向用户分配许可证](manage/assign-licenses-to-users.md)
  - [取消分配用户许可证](manage/remove-licenses-from-users.md)

### <a name="setup-page-updates"></a>设置页面更新

安装程序现在有类别和分区，包括 **建议用于您** 在打开功能和设置组织时，我们会在其中智能地建议下一步。 我们还添加了一个新的功能来设置：

- **Office 高级威胁防护** -如果你的组织授权使用 Office ATP，但尚未对其进行配置或将其打开，你将看到此页面。 请转到 " **设置** " 以试用。

### <a name="report-an-issue-august"></a>报告 (八月) 的问题

如果您受到您的服务运行状况仪表板上未展示的问题的影响，则 **报告问题** 功能将为您提供一种快速而简单的方式，让我们知道。 转到**运行状况**  >  **服务运行状况**。

## <a name="july-2019"></a>2019 年 7 月

### <a name="message-center"></a>消息中心

邮件中心已更新为新的设计，看起来非常惊人！

![屏幕捕获：更新了 "所有活动邮件" 选项卡且打开了筛选器菜单的邮件中心。](../media/MAC-MessageCenterUpdated.png)

- 您现在可以 **按状态查看邮件**。 只需选择其中一个选项卡： **所有活动邮件**、 **重要性较高**、 **未读邮件**和 **消除的邮件**。
- 您还可以按类别 **数据隐私**进行筛选 **、规划更改**、 **防止或解决问题**并 **及时** 了解消息类别。
- 从列表中选择一封邮件，并在命令栏中有几个选项： " **取消**"、" **标记为已读** " 或 " **标记为未读**" 或 " **共享**"。
- 打开邮件时，您可以获得更多选项：
  - 将邮件的链接复制到您的剪贴板，以供以后保存或与同事共享。
  - 将邮件标记为已 **读** 或 **未读**。
  - 通过选择 " **喜欢** " 或 "不 **喜欢**" 来提供有关邮件的反馈，则会打开一个反馈窗格，要求您对该邮件的赞或不喜欢的内容提供特定反馈。

### <a name="navigation-pane-intelligence"></a>导航窗格智能

 导航窗格现在会记住你的最后一项操作，并向你显示你上次离开它的状态中的窗格。 它还会使常用项目在默认情况下可见。

### <a name="initial-setup--the-setup-page"></a>初始设置 & 安装程序页面

我们已获得一些令人兴奋的更改，可帮助你设置你的组织。 首先，让我们讨论一下 **安装程序** 与 **设置页面**之间的区别。 **安装程序** 是指用于集成 Microsoft online 服务的初始安装向导。 这通常包括三个具体步骤： **连接域**、 **添加用户**和 **下载 Office 应用**。 " **安装程序" 页面** 是 "管理中心" 中的页面，建议设置任务以确保您最大限度地利用了你购买了许可证的功能。

- **安装** 程序-已为 **Microsoft 365 for business** 订阅更新了初始安装向导。 这一新设计将帮助新的组织更快地完成向导，并获得更大的成功。
- "**设置" 页**-"**设置**" 页可帮助您完成设置并保护订阅附带的服务。 您还可以在 " **设置** " 页上查看任何已消除的建议。 若要查看它是否适用于你的订阅，请转到**Microsoft 365 管理中心**  >  **设置**。

### <a name="billing--subscriptions"></a>帐单 & 订阅

- **软件** 产品类型-你现在可以查看通过云服务提供商购买的软件产品 (CSP) 。 若要查看你的下载和密钥，请转到**付费**  >  **产品**  >  **软件**"选项卡"。
- 你可以从 Microsoft 365 管理中心查看新式 Azure 产品和服务，无论你是从 Microsoft 还是第三方提供商处购买的。 包括新式 Azure 产品的示例：
  - Azure 保留虚拟实例
  - Azure 支持计划
  - Azure 混合使用优势 (AHUB) 
  - 管理应用程序
  - 设备服务
  - Azure 订阅

### <a name="simplify-multi-factor-authentication"></a>简化多因素身份验证

管理员有权访问组织中的敏感信息。 在登录时要求所有管理员使用多重身份验证。 "新建" 向导可帮助您只需一步即可完成此操作。 若要试用，请转到 "**设置**"  >  **加强登录安全性**。

### <a name="users"></a>用户

" **已删除用户** " 和 " **来宾用户** " 页面更新为新样式。

- **来宾用户**：通过邀请用户在 SharePoint 或 OneDrive 中查看或共享文件来添加来宾用户。 您可以从**用户**的  >  **来宾用户**查看来宾用户。
- **已删除用户**：在 "更新的 **已删除用户** " 页面上，您可以执行在旧管理中心中可以执行的所有操作，但现在可以添加和删除列。 ，我们有许多列选项可供选择。 实际上，它与在 " **活动用户** " 页面上选择的列相同。

## <a name="june-2019"></a>2019 年 6 月

### <a name="featured-feedback-request---dark-mode"></a>特色反馈请求-深色模式

在深色模式下查看管理中心是预览！ 您可以立即在 **主页** 上测试此页面。 在 **主页** 上，" **深色模式** " 按钮位于 "新增 **内容** " 链接旁边的命令栏中。

### <a name="roles-management"></a>角色管理

6月结束时，我们开始推出新的方法来管理管理员角色。 为你提供此功能时，请转到**角色**  >  **角色**。 在此之前，请先看看它是非常棒！
<br> ![屏幕捕获：突出显示了 "用户管理员角色详细信息" 窗格的 "管理员角色" 列表。](../media/MAC-AdminRoles-Featured.png) <br>

通过这一新体验，可以更轻松地查看谁拥有管理员权限，并分配为您的管理员授予适当级别的访问权限的角色。 此外，我们还从 Azure AD 添加了更多角色，这样您就不会浪费时间转到多个管理中心。
你还可以在此处执行哪些操作？

- 导出在 Microsoft 365 中分配了 Azure Active Directory 角色的组织中所有管理员的列表。  
- 查看分配给特定角色的所有管理员、在特定角色中添加或删除管理员、按名称和关键字搜索角色，以及了解每个角色允许用户执行的操作的详细信息。
- 快速搜索特定角色并创建筛选器。

### <a name="payment-method"></a>支付方式

我们已更新你的订阅付费方式。 转到**帐单**  >  付款 **& 付款**  >  **方法**。 您可以在列表视图中查看您的付款方式。 选择列表中的任何项目以将其删除，对其进行编辑，并轻松查看与付款方式相关联的订阅。

## <a name="may-2019"></a>2019 年 5 月

### <a name="mays-featured-fix---case-sensitivity"></a>可能的功能修复-区分大小写

现在，当您搜索共享邮箱、联系人、资源和邮箱权限时，您的搜索词不一定区分大小写。

**用户和组管理** 本月，我们更新了 " **阻止用户**"、" **重置密码**"、" **联系人** 列表" 视图、" **组** 列表" 视图和 " **组** 详细信息" 页到新的管理中心样式。

- 使用 "新建 **组** " 列表视图，可以获取有关组的更丰富的数据，并且可以自定义查看数据的方式，并且 "组" 列表记住了您希望查看数据的方式。 例如，现在可以将 **组与团队** 进行筛选，以查看您的组是否是团队的一部分，并且可以添加 " **团队状态** " 列。
- "组" 列表还提供了我们对用户管理中的列表体验所做的所有改进，包括快速操作和上下文命令栏。

**推荐**<br>
你可能会在你的管理中心看到一个新的建议弹出窗口，我们刚刚添加了4个新的。 当然，如果我们认为它将对你的组织有益，你将只会看到建议。 但请不要等到我们向你提出建议-你可以从卡片库添加它。

- **密码到期** -建议将密码设置为 **永不过期**。 如果你的组织有不同的设置，你可能只会看到此建议。
- **全局管理员过多** -由于全局管理员过多而导致安全威胁，如果全局管理员超过4个，将会看到此建议。 建议仅为用户提供完成工作所需的访问权限。
- **Intune 设备保护** -如果你的许可证包括 intune，并且我们检测到你尚未完成设置 intune 或注册设备，我们建议你创建 Intune 策略，以便在用户从其移动设备访问组织的文件时对其进行保护。
- **获取每月 office 功能更新** -我们从非常小的客户那里获得了反馈，当他们获得每月 office 功能更新时，他们的用户会感到更开心。 因此，如果你是一位非常小的企业，并且你目前每六个月都可以获得 Office 功能更新，你将看到此建议。

**Settings** <br>
对于设置，已进行了很多更改。 大多数情况下，只需将现有设置更新为新的管理中心样式即可。 当我们继续发展并添加以前从未见过的新设置时，我们将在此处开始提及它们。 同时，我们还准备了一个完整的设置来宣布： **新式验证**。 是的，有新的设置可启用 **新式验证**！ 若要将其签出，请转到**Settings**  >  **Services & 外接程序**  >  **新式身份验证**。

## <a name="april-2019"></a>2019 年 4 月

对于管理中心来说，事情看起来非常出色。 我们已阅读你的反馈和建议，回答其中的大部分问题，并真正让你必须向心形说。 当然，我们仍在执行工作，以确保与旧管理中心的所有内容都能进行奇偶校验。 请记住，在我们推出新功能时，你可能无法立即获得。

### <a name="featured-feature---add-users"></a>特色功能-添加用户

对于四月份，我们提供了可指导您完成的 " **添加用户** 向导"。等待它 .。。添加用户。 本分步介绍了如何添加用户的基本信息，如电子邮件和显示名称、分配许可证和角色、添加联系人信息，然后在提交之前查看用户帐户。 **为什么要进行此更改？** 我们听说你不喜欢几乎无限滚动以在以前的体验中添加用户的反馈。
<br> !["添加用户" 向导的屏幕捕获。](../media/MAC-AddUserWizard.png) <br>

有两种方法可以将其签出： <br>

1. 从**主页**中，选择 "从**用户管理**卡**添加用户**"。 向导将在此处打开，因此您无需从在 **主页** 上执行的任何工作中进行导航。
2. 转到 "**用户**  >  **活动用户**"，然后从命令栏中选择 "**添加用户**"。
<br><br>

我们已经对 **用户管理**进行了一些更改，下面是一个快速列表：

- " **管理角色** " 窗格已更新为新样式且可访问。 我们还更新了 **阻止用户** 并删除了新样式的 **用户** 窗格。
- 管理命令栏中的 "**产品许可证**更改位置"。
- 现在，更改用户照片变得更加简单。 在 " **活动用户** " 中，选择一个用户，然后更改其图片下的 **照片** 。

### <a name="but-wait-theres-more"></a>但请等待！ 还有更多

- **主页**上有一个新的安装标题，如果尚未完成设置步骤（如添加域、添加用户和下载 Office 应用），您将看到此标题。
- **组**列表和详细信息窗格已更新为新样式。 转到 "**组**  >  **Groups** " 组以查看更改。
  - 说到组，我们还向组详细信息窗格添加了 **Microsoft 团队** 选项卡，您可以在其中将任何 Microsoft 365 组转到团队中。 若要将组从列表中选择任何 Microsoft 365 组，请选择 " **Microsoft 团队** " 选项卡，然后 **创建 "团队**"。 如果该组已经是团队，您将获得从 **团队管理中心**管理它的链接。
  - 最后，您可以将 **团队状态** 添加到 " **组** " 列表中。 在列标题上，选择 "**选择列**  >  **团队状态**  >  **保存**"。
- **新的有限管理员角色** -我们已发布了一些新的管理员角色，以便用户只能为用户提供所需的访问权限。
  - **Kaizala admin**：此角色中的用户具有在 Microsoft Kaizala 中执行所有管理任务的权限，包括在 Kaizala 目录中创建和管理用户、管理 Kaizala 组、管理操作卡和连接器以及创建服务请求。
  - **搜索管理员**：此角色中的用户拥有对 microsoft 365 管理中心中所有 microsoft 搜索管理功能的完全访问权限。 搜索管理员可以将搜索管理和搜索编辑器角色委派给用户，并创建和管理内容，如书签、Q&项目和位置。 此外，这些用户可以查看消息中心、监视服务运行状况和创建服务请求。
  - **搜索编辑器**：此角色中的用户可以在 microsoft 365 管理中心中创建、管理和删除 microsoft Search 的内容，包括书签、Q&项目和位置。
- 本月有一 bonanza **帐单** 更改 .。。
  - 您现在可以更新现有信用卡的 CVV，而无需将其删除并再次添加它。 您可以通过转到**帐单**  >  **支付方法**更新 CVV。
    - 我们使你的 **发票** 更易于查找，并了解你的帐户可能遇到的任何帐单问题。 现在，您可以在 web 浏览器中查看您的帐单，而无需下载 PDF。 转到 "**汇票**  >  **发票**"。
    - 在 " **产品** " 页上，如果您有多个相同类型的订阅，我们现在会聚合您的订阅信息。

## <a name="march-2019---weve-officially-released-the-admin-center"></a>2019年3月-正式发布管理中心

嗯，如果你错过了令人兴奋的新闻，我们正式发布了新的和改进的 Microsoft 365 管理中心！ 下面是我们宣布发布的博客文章：现已 [推出新的 Microsoft 365 管理中心](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/The-new-Microsoft-365-admin-center-available-today/ba-p/377870)。 在三月份，我们将依靠博客文章查看已发布的功能-此外，您还可以阅读在不久的将来发布的功能的帖子，我们不允许在核心内容中执行此操作。
<br> ![Microsoft 365 管理中心主页的屏幕捕获。](../media/M365AC-HomePage.png) <br>
我们对 **帐单 & 订阅** 区域有一处更改，我们想提。 我的意思是，y'all 不能认为我们在改进它之后做了吗？ 因为我们不是这样！ 事实上，我们添加了管理与**计费**帐户之间的合作伙伴关系的能力  >  **Billing accounts**。 您可以从这里查看您在各顾问、CSP 和间接分销商之间的合作伙伴关系。 您还可以接受新的合作伙伴关系请求，包括委派的管理员权限。

正如往常一样，你的反馈对我们非常重要，因此将其保持起来！ 在管理中心的任何页面上，**通过选择 "** **需要帮助"** 旁边的右下方提供反馈，可以提供反馈。

## <a name="february-2019---billing--subscriptions-edition"></a>二月 2019-帐单 & 订阅版

本月，我们将重点介绍我们对 affectionately 称为 "付费和订阅" 的领域所做的所有改进。 过去，您可能没有参考这些内容 affectionately，但我们认为你现在将 .。。

- **付款方式** -我们听到你的反馈，即更新你的付款方式很困难，我们已在其周围进行了大量更改。 转到 "**付费**  >  **支付方式**"。 您可以轻松地查看您的付款方式，如您的签证卡片以及与之关联的订阅。 在付款方法列表中，选择 " **更多** " 菜单 (到期日期) 旁边的3个点，然后选择 " **查看订阅**"。 您还可以使用 " **更多** " 菜单编辑和删除付款方式。
- **付费帐户** 定向发布客户将首先看到新的帐单帐户页面，然后将其汇总到世界范围。 如果可供你使用，请转到 "**付费**  >  **帐单帐户**"。 您可以对新的帐单帐户页执行哪些操作？ 很高兴你询问：
  - 直接从此页面更新组织配置文件中的地址和其他联系人信息。 除非需要，否则无需转到 "**设置**  >  **组织配置文件**"。
  - 我们正在为直接或批量许可客户提供更轻松的工作，您可以接受并查看 **帐单帐户**中的客户协议。 您还可以使用其他 emc 连接，从而将 emc 链接在一起，以共享许可证和资源。
- 我们还完成了一些较小的增强和错误修复：
  - 重新激活具有发票付款的订阅
  - 编辑订阅的服务使用地址
  - 在 "清点详细信息" 页上，我们添加了一些通知增强功能，我们将你链接到实际可执行工作的页面，并对库存详细信息卡片执行更多操作。 转到 "**记帐**  >  **汇票**  >  " 查看任何发票上的**详细信息**。

## <a name="january-2019---happy-new-year"></a>2019年1月-新年快乐

- 仍在 **服务 & 加载项** 中添加-我们已更新了多个 **设置 > 服务 & 外接程序** 页面。 尝试集成的应用或报告以查看最新的。
- **搜索改进？** 在命令栏中的 **搜索** 框中不会再进行查找。 已将其更新为允许您搜索任务。 例如，尝试 "密码重置" 或 "添加用户"。

### <a name="featured-feedback-fix---licenses-and-apps"></a>特色反馈修复-许可证和应用

根据你的反馈，我们在用户详细信息窗格中重新组合 **许可证和应用** 。 我们最初分离了这两个功能，以提供有关所有许可证和所有应用程序可能性的详细信息。 我们听说你将许可证和应用分成两个相混淆的窗格。 我们听取了许可证和应用，并将许可证和应用重新组合到一个选项卡中。现在，您可以确保在一个窗格中为用户分配的所有许可证中的应用程序处于关闭状态。 牛奶和 cookies。 许可证和应用。 我们现在可以获取它。

将其签出： **用户 > 的活动用户 > 编辑** 或 **添加用户 > 许可证和应用程序**
