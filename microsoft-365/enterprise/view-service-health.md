---
title: 如何检查 Microsoft 365 服务运行状况
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_ServiceHealthModern
- O365M_ServiceHealthModern
- O365E_ViewStatusServices
- O365E_ServiceHealthModern
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
- IWA160
ms.assetid: 932ad3ad-533c-418a-b938-6e44e8bc33b0
description: 在致电支持部门之前，查看 Microsoft 365 服务的运行状况，以查看是否有活动服务中断。
ms.openlocfilehash: e0ab4eaa1f7a96168839a4abef2f0f254a21d0ad
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644628"
---
# <a name="how-to-check-microsoft-365-service-health"></a>如何检查 Microsoft 365 服务运行状况

[![显示管理中心正在更改且你可在 aka.ms/aboutM365preview 找到更多详细信息的标签。](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)

可以在[Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339)管理中心的"服务运行状况"页上查看 Microsoft 服务的运行状况，包括 Office 网页版、Yammer、Microsoft Dynamics CRM 和移动设备管理云服务。  If you are experiencing problems with a cloud service, you can check the service health to determine whether this is a known issue with a resolution in progress before you call support or spend time troubleshooting.

如果无法登录管理中心，可以使用服务状态页面检查阻止登录租户的已知[](https://status.office365.com)问题。  此外，在 Twitter 上的 [@MSFT365status注册](https://twitter.com/MSFT365Status) 以关注我们，以查看有关特定事件的信息。

  
### <a name="how-to-check-service-health"></a>如何查看服务运行状况

1. 转到 Microsoft 365 管理中心 ，然后 [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) 使用管理员帐户登录。

    > [!NOTE]
    > 分配了全局管理员或服务支持管理员角色的用户可以查看服务运行状况。 若要允许 Exchange、SharePoint 和 Skype for Business 管理员查看服务运行状况，必须向他们分配服务管理员角色。 有关可以查看服务运行状况的角色详细信息，请参阅关于 [管理员角色](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles)。
  
2. 如果未使用新的管理中心，请在主页上，选择右上角的"试用新的管理中心"切换。

3. 若要查看服务运行状况，请在管理中心中，转到"运行状况服务运行状况"，或选择"主页"仪表板上的"服务  >  运行状况 **"卡**。  仪表板卡片指示是否有活动服务问题，以及指向详细"服务运行状况" **页面** 的链接。
  
4. 在 **"服务运行状况** "页上，每个云服务的运行状况以表格格式显示。

   ![View of current issues in service health](../media/service-health-all-services.png)

" **所有服务** " (默认视图) 显示所有服务及其当前运行状况。 图标和" **状态"** 列指示每个服务的状态。 

若要筛选视图以筛选当前遇到事件的服务，请选择页面顶部的"事件"选项卡。 选择 **"公告"** 选项卡将只显示当前已发布公告的服务。 

" **历史记录** "选项卡显示已解决的事件和公告的历史记录。

如果你遇到 Microsoft 365 服务问题，并且未在"服务运行状况"页上看到该问题，请通过选择"报告问题"并完成简短窗体来告诉我们该问题。 我们将查看来自其他组织的个人数据和报告，以查看问题是如何普遍出现，以及问题是否源自于我们的服务。 如果是这样，我们将在"服务运行状况"页上将其添加为新事件或公告，可在其中跟踪其解决方案。 如果你在大约 30 分钟内未在列表中看到它，请考虑联系支持部门以解决该问题。

若要自定义在仪表板上显示哪些服务的视图，请选择"首选项""自定义视图"，并清除要从服务运行状况仪表板视图中筛选  >  出的服务的复选框。 确保选中了要监视的每个服务的复选框。    

若要注册影响活动事件的租户和状态更改的新事件的电子邮件通知，请选择"首选项""电子邮件"，单击"在电子邮件中向我发送服务热度通知"，然后  >  指定： 

- 最多两个电子邮件地址。
- 是否需要事件或公告通知
- 要通知的服务

> [!NOTE]
> 每个管理员都可以设置其首选项，并且每个管理员帐户具有两个电子邮件地址的上述限制。

> [!TIP]
> 还可以在移动设备上使用 [Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=627216) 管理应用查看服务运行状况，这是一种使用推送通知保持最新状态的方式。 
  
### <a name="view-details-of-posted-service-health"></a>查看已发布服务的运行状况详细信息

在 **"所有服务** "视图中，选择服务状态将打开公告或事件的摘要视图。
  
[![显示服务公告的屏幕截图 ](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)

公告或事件摘要提供以下信息：

- **标题** - 问题的摘要。
- **服务** - 受影响服务的名称。
- **ID** - 问题的数值标识符。
- **Status** - 此问题对服务有何影响。
- **开始时间** - 问题开始的时间。
- **上次更新** 时间 - 上次更新服务运行状况消息的时间。 我们频繁发布消息，告知你在应用解决方案方面的进度。

选择问题标题以查看问题详细信息页面，其中显示有关该问题的详细信息，包括我们在处理解决方案时发布的所有[](#history)消息的历史记录。

![显示问题详细信息的屏幕截图](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>翻译服务运行状况详细信息

服务运行状况说明是实时发布的，因此这些说明不会自动翻译成你的语言，并且服务事件的详细信息仅以英语形式提供。若要翻译这些说明，请遵循以下步骤：
  
1. 转到[翻译工具](https://www.bing.com/translator/)。

2. 在" **服务运行状况**"页上，选择一个事件或公告。在" **显示详细信息**"下，复制关于该问题的文本。

3. 在"翻译工具"中，粘贴文本，然后选择" **翻译**"。

### <a name="definitions"></a>定义

大多数情况下，服务显示为正常，没有进一步的信息。 服务出现问题时，该问题会标识为公告或事件，并显示当前状态。
  
> [!TIP]
> 服务运行状况中不会显示计划内维护事件。 可以通过" **消息中心**"随时了解最新消息，从而跟踪计划内维护事件。 筛选出分类为"更改计划"的消息，了解发生更改的时间、其影响以及如何做好相应准备。 有关详细信息 [，请参阅 Microsoft 365 中的](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) 邮件中心。
  
### <a name="incidents-and-advisories"></a>事件和公告

| 图标 | 说明 |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|如果服务显示公告，这意味着某问题正在影响一些用户，但该服务仍然可用。公告中通常存在针对该问题的变通方法，并且该问题可能是间歇性的，或其作用范围和对用户的影响有限。  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|如果服务显示遇到活动事件，则说明遇到关键问题，且服务或其主要功能目前不可用。例如，用户可能无法发送和接收电子邮件，或无法登录。事件会对用户产生显著影响。对于正在进行的事件，我们会在服务运行状况仪表板中提供有关调查、缓解措施和解决方法确认的更新。  <br/> |

### <a name="status-definitions"></a>状态定义

| 状态 | 定义 |
|:-----|:-----|
|**正在调查** | 我们已发现存在潜在问题，我们正在收集有关情况和影响范围的详细信息。 |
|**服务降级** | 我们已确认存在可能影响服务或功能使用的问题。例如，如果服务的执行速度比平常慢、存在间歇性中断或某功能运行不正常，则可能看到此状态。 |
|**服务中断** | 如果我们确定某问题影响用户访问服务的能力，则你将看到此状态。在本例中，问题十分重大且可持续重现。 |
|**正在还原服务** | 我们已确定问题成因，知晓需要采取的纠正措施，并正在将服务恢复到正常状态。 |
|**延期恢复** | 此状态表示正在执行纠正措施，为大多数用户恢复服务，但恢复所有受影响的系统仍需一些时间。如果我们为了减轻影响，而在实施永久解决措施前实施临时措施，你也可能看到此状态。 |
|**调查暂停** | 如果对潜在问题的详细调查需要请求客户提供其他信息，以便进行进一步的调查，则你将看到此状态。如果我们需要你的参与，我们会告知你所需的数据或日志。 |
|**已还原服务** | 我们确认纠正措施已解决基础问题，且服务已还原到正常状态。若要了解出了什么问题，请查看问题详细信息。 |
|**误报** | 经过详细调查后，我们已确认服务运行正常且运行正常。 未观察到对服务的影响或源自服务外部的事件的原因。 |
|**已发布的事件后报告** | 我们发布了关于特定问题的事后报告，其中包括根本原因信息和确保类似问题不再发生的下一步步骤。 |

### <a name="history"></a>历史记录

服务运行状况允许你查看当前运行状况，并查看过去 30 天内影响租户的任何服务公告和事件的历史记录。 若要查看所有服务的过去运行状况，请选择问题 **详细信息** 页面上的"查看历史记录"。
  
![Show link to health history](../media/service-health-view-history.png)
  
显示在选定时间范围内发布的所有服务运行状况消息的列表，如下所示：
  
![View service health history](../media/service-health-history.png)
  
展开任意行以查看有关问题的更多详细信息。
  
有关我们对正常运行时间的承诺，请参阅 [Microsoft 365 透明操作](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)。

## <a name="related-topics"></a>相关主题

[Microsoft 365 管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 
[消息中心首选项](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)<br/>
[如何在管理中心上检查 Windows 版本运行状况](https://docs.microsoft.com/windows/deployment/update/check-release-health)
