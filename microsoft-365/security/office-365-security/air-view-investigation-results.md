---
title: 在 Microsoft 365 中查看自动调查的结果
keywords: 空气、autoIR、ATP、自动化、调查、响应、修正、威胁、高级、威胁、保护
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 在 Microsoft 365 中进行自动调查的过程中和之后，您可以查看结果和主要发现。
ms.date: 11/05/2020
ms.openlocfilehash: 0f472c117ff1f6c2b563063d0eeb9a27cc5afebe
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931986"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Microsoft 365 中的自动调查的详细信息和结果

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在[Microsoft Defender For Office 365](office-365-atp.md)中进行[自动调查](office-365-air.md)时，有关调查的详细信息在自动调查过程期间和之后都可用。 如果您具有必要的权限，则可以在 Microsoft 365 安全中心中查看这些详细信息。 调查详细信息为你提供最新状态，并能够批准任何挂起的操作。

## <a name="investigation-status"></a>调查状态

调查状态指示分析和操作的进度。 在调查运行时，状态更改以指示是否发现威胁，以及是否已批准操作。

|状态|说明|
|:---|:---|
|**即将开始** | 调查已触发并等待开始运行。|
|**正在运行** | 调查过程已开始，正在进行中。 在审批 [挂起的操作](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions#approve-or-reject-pending-actions) 时，也会发生此状态。|
|**找不到威胁** | 调查已完成，且未标识 (用户帐户、电子邮件、URL 或文件) 的威胁。 <br/><br/>**提示** ：如果你怀疑缺少某些内容 (例如误报) ，则可以使用 [威胁资源管理器](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)执行操作。|
|**发现威胁** |自动调查发现了问题，但没有解决这些问题的具体补救措施。<br/><br/> 当确定了某些类型的用户活动但没有可用的清除操作时，可能会出现 " **威胁已发现** " 状态。 示例包括以下任何用户活动： <br/>- (DLP) 事件的[数据丢失防护](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) <br/>-发送异常的电子邮件 <br/>-发送的恶意软件 <br/>-发送的网络钓鱼<br/>调查发现没有要修正的恶意 Url、文件或电子邮件，并且没有要修复的邮箱活动，例如关闭转发规则或委派。 <br/><br/>**提示** ：如果你怀疑缺少某些内容 (例如误报) ，则可以使用 [威胁资源管理器](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)进行调查并采取措施。|
|**已由系统终止** | 调查已停止。 调查可能因以下几个原因而停止：<br/>-调查的待处理操作已过期。 等待为期一周的批准后，待处理的操作超时。 <br/>-操作过多。 例如，如果单击恶意 Url 的用户过多，则可能会超过调查运行所有分析器的能力，因此调查将暂停。 <br/><br/>**提示** ：如果调查在执行操作之前停止，请尝试使用 [威胁资源管理器](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) 查找和解决威胁。|
|**挂起的操作** | 调查发现威胁，如恶意电子邮件、恶意 URL 或有风险的邮箱设置，以及用于补救威胁正在 [等待批准](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions)的操作。<br/><br/>如果发现任何具有相应操作的威胁，则会触发 **挂起操作** 状态。 但是，在调查运行时，挂起操作的列表可能会增加。 检查 [调查日志](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#playbook-log) 以查看其他项目是否仍处于待完成状态。|
|**已修正** | 调查已完成，并批准了所有修正操作 (这将被视为完全修正) 。<br/><br/>**注意** ：批准的修正操作可能会出现错误，从而导致无法执行操作。 无论纠正措施是否成功完成，调查状态不会更改。 检查 [调查日志](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results) 中的详细结果。|
|**部分修正**| 调查导致了补救措施，有些已批准并已完成。 其他操作仍 [处于挂起状态](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions)。|
|**失败** | 至少一个调查分析器遇到无法正确完成的问题。 <br/><br/>**注意** ：如果在批准了修正操作后调查失败，则修正操作可能仍为 "成功"。 检查 [调查日志](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results) 中的详细结果。|
|**按限制排队** | 在队列中保留调查。 当其他调查完成时，将开始排队调查。 限制有助于避免较差的服务性能。 <br/><br/>**提示** ：挂起的操作可能会限制可运行的新调查数。 请务必 [批准 (或拒绝) 挂起的操作](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions#approve-or-reject-pending-actions)。|
|**已通过限制终止** | 如果队列中保留的调查过长，它将停止。 <br/><br/>**提示** ：您可以 [从威胁资源管理器开始调查](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。|
|

## <a name="view-details-of-an-investigation"></a>查看调查的详细信息

1. 请转到 Security & 合规性中心 ([https://protection.office.com](https://protection.office.com)) 并登录。

2. 执行下列操作之一：

    - 转到 " **威胁管理**  >  **仪表板** "。 这将转到 [安全仪表板](security-dashboard.md)。 您的空中小组件显示在 [安全仪表板](security-dashboard.md)的顶部。 选择一个小部件，如 **调查摘要** 。

    - 转到 **威胁管理**  >  **调查** 。

    每种方法都将转到调查列表。

    ![空气的主要调查页面](../../media/air-maininvestigationpage.png)

3. 在调查列表中，选择 " **ID** " 列中的项目。 这将打开 "调查详细信息" 页，从视图中的调查图形开始。

    ![空中调查图形页面](../../media/air-investigationgraphpage.png)

   使用各种选项卡了解有关调查的详细信息。

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>查看与调查相关的警报的详细信息

某些类型的警报会在 Microsoft 365 中触发自动调查。 若要了解详细信息，请参阅 [触发自动调查的警报策略](office-365-air.md#which-alert-policies-trigger-automated-investigations)。 

使用以下过程可查看与自动调查相关联的警报的详细信息。

1. 请转到 Security & 合规性中心 ([https://protection.office.com](https://protection.office.com)) 并登录。

2. 转到 **威胁管理**  >  **调查** 。

3. 在调查列表中，选择 " **ID** " 列中的项目。

4. 通过打开调查的详细信息，选择 " **通知** " 选项卡。下面列出了所有触发调查的警报。

5. 选择列表项。 将打开一个浮出控件，其中包含有关该警报的详细信息以及指向其他信息和操作的链接。

6. 查看浮出控件上的信息，根据特定的通知执行操作，如 **Resolve** 、 **隐含** 或 **通知用户** 。

    - **Resolve** 等效于关闭通知

    - **禁止** 使策略在指定时间段内触发警报

    - **通知用户** 启动电子邮件，其中包含已输入的用户电子邮件地址，并允许安全操作团队向这些用户键入邮件。  (这类似于使用 [威胁资源管理器](threat-explorer.md)向收件人发送邮件。 ) 

## <a name="how-to-use-the-various-tabs"></a>如何使用各种选项卡

以下各节将引导您完成 "自动调查" 页面上的各种选项卡，以及如何使用这些信息。

### <a name="automated-investigations-page"></a>自动调查页面

"自动调查" 页面显示您的组织的调查及其当前状态。

![空气的主要调查页面](../../media/air-maininvestigationpage.png)

可执行下列操作：

- 直接导航到调查 (选择 **调查 ID** ) 。

- 应用筛选器。 从 **调查类型** 、 **时间范围** 、 **状态** 或这些情况的组合中进行选择。

- 将数据导出到 .csv 文件。

### <a name="investigation-graph"></a>调查图形

当您打开特定调查时，您将看到 "调查图形" 页。 此页面显示了所有不同的实体：电子邮件、用户 (及其活动) ，以及作为触发的警报的一部分自动调查的设备。

![空中调查图形页面](../../media/air-investigationgraphpage.png)

可执行下列操作：

- 获取当前调查的直观概述。

- 查看调查持续时间的摘要。

- 在可视化中选择一个节点以查看该节点的详细信息。

- 在顶部选择一个选项卡以查看该选项卡的详细信息。

### <a name="alert-investigation"></a>通知调查

在调查的 " **通知** " 选项卡上，您可以查看与调查相关的警报。 详细信息包括触发调查的警报以及与调查相关的其他关联警报（如有风险的登录、 [DLP 策略](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) 冲突等）。 在此页面中，安全分析员还可以查看各个通知的其他详细信息。

![空气警报页面](../../media/air-investigationalertspage.png)

可执行下列操作：

- 获取当前触发警报和任何关联警报的直观概述。

- 在列表中选择一个警报，打开显示完整警报详细信息的飞出页面。

### <a name="email-investigation"></a>电子邮件调查

在调查的 " **电子邮件** " 选项卡上，您可以查看原始电子邮件和在调查过程中标识的类似电子邮件的群集。 " **电子邮件** " 选项卡还显示与调查相关的电子邮件项目，例如用户报告的电子邮件详细信息、报告的原始电子邮件、电子邮件 (s) zapped 由于恶意软件/网络钓鱼诈骗等。

![空中电子邮件调查页面](../../media/air-investigationemailpage.png)

通过电子邮件调查，可以执行以下操作：

- 获取当前群集结果和发现的威胁的直观概述。

- 单击 "群集" 实体或威胁列表打开显示完整警报详细信息的弹出页面。

- 通过单击 " **电子邮件群集详细信息** " 选项卡顶部的 " **在资源管理器中打开** " 链接进一步调查电子邮件群集

![使用浮出控件详细信息的航空调查电子邮件](../../media/air-investigationemailpageflyoutdetails.png)

鉴于组织中的用户发送和接收的大量电子邮件，以及电子邮件通信和攻击的多用户性质，以下过程可能需要很长时间：

1. 根据邮件头、正文、URL 和附件中的类似属性来群集电子邮件

2. 将恶意电子邮件与优质电子邮件分开

3. 对恶意电子邮件采取操作

AIR 自动化了此过程，从而节省了贵组织的安全团队时间和精力。 

#### <a name="types-of-email-clusters"></a>电子邮件群集的类型

电子邮件分析步骤中可以识别三种不同类型的电子邮件群集：相似性群集 (所有调查) 、指示器群集 (所有调查) 和邮箱/用户群集。 下表介绍了这些类型的电子邮件群集。

|电子邮件群集  |说明  |
|---------|---------|
|相似性群集     |通过搜寻电子邮件（具有类似的发件人和内容属性）来识别的电子邮件。 根据原始检测结果评估这些群集中的恶意内容。 包含足够恶意电子邮件检测的电子邮件群集被视为恶意电子邮件。         |
|指示器群集 | 通过搜寻同一指示器实体标识的电子邮件 (来自原始电子邮件的文件哈希或 URL) 。 将原始文件/URL 实体标识为恶意时，AIR 会将指示器判定为包含该实体的电子邮件的整个群集。 被标识为恶意软件的文件意味着包含该文件的电子邮件群集将被视为恶意软件电子邮件。 |
|邮箱/用户群集 | 与用户泄露调查中涉及的用户相关的电子邮件。  这些电子邮件群集可供安全操作团队进行进一步分析，且不会生成电子邮件修正操作。 <br/> 已损坏的用户安全行动手册将检查要分析的用户发送的电子邮件，以便了解从邮箱发送的电子邮件的潜在影响。 |

> [!NOTE]
> 群集的目标是查找和查找与攻击或市场活动中的同一发件人发送的其他相关电子邮件。  在某些情况下，合法的电子邮件可能会触发调查 (例如，用户会报告营销电子邮件) 。  在这些方案中，电子邮件群集应确定电子邮件群集不是恶意的–如果它相应地执行此操作，则不会表示威胁，也 **不** 会建议删除电子邮件。

#### <a name="email-classifications"></a>电子邮件分类

在分析电子邮件时，会将它们归为 " *恶意* "、" *可疑* " 或 " *清除* " (，但 *不标识为威胁* ) ：

- 从邮箱/用户发送的 *恶意电子邮件* 表明邮箱/帐户可能会受到危害。 将显示可能受恶意电子邮件影响的其他用户/邮箱作为危害的一部分。

- 邮箱/用户发送的 *可疑电子邮件* 表明可能存在已损坏的帐户或不需要的电子邮件活动。 这些邮件包括从邮箱发送的任何垃圾邮件/批量电子邮件。

- *清理电子邮件* (被视为不受) 邮箱/用户发送的威胁的电子邮件可以向安全操作团队提供已发送的合法用户电子邮件的视图。 但是，如果电子邮件帐户受到威胁，这些电子邮件也可能包含数据 exfiltration。

#### <a name="more-about-email-counts"></a>有关电子邮件计数的详细信息

"电子邮件" 选项卡上标识的电子邮件计数当前表示在 " **电子邮件** " 选项卡上显示的所有电子邮件的总数。由于电子邮件存在于多个群集中，因此 (的电子邮件的实际总数) 是在所有群集和原始收件人的电子邮件中显示的唯一电子邮件数。

根据每个收件人， [资源管理器](threat-explorer.md) 和空中计数电子邮件，因为安全 verdicts、操作和传递位置在每个收件人的基础上是不同的。 因此，发送给三个用户的原始电子邮件总共计三封电子邮件，而不是一封电子邮件。 

在某些情况下，可能会对电子邮件进行两次或多次计数，例如电子邮件在其上有多个操作，或当所有操作发生时有多个电子邮件副本时。 

例如，在传递时检测到的恶意软件电子邮件会导致阻止 (隔离) 电子邮件，并将替换的电子邮件 (威胁文件替换为警告文件，然后传递到用户的邮箱) 。 由于系统中的电子邮件有两个副本，这两个副本可能会在群集计数中进行计数。

> [!IMPORTANT]
> 下面是一些需要注意的事项：
> 
> - 电子邮件计数是在调查时计算的，在您打开基于基础查询) 的调查 flyouts (时，会重新计算一些计数。 
> 
> - 为 " **电子邮件** " 选项卡上的电子邮件群集显示的电子邮件计数，在调查时将计算在 "群集浮出控件" 上显示的电子邮件数量值，并且不要更改。 
> 
> - 在电子邮件群集浮出控件的 " **电子邮件** " 选项卡底部显示的电子邮件计数，资源管理器中显示的电子邮件计数反映在调查的初始分析之后收到的电子邮件。 

因此，显示原始数量10封电子邮件的电子邮件群集将在调查分析阶段和管理员审查调查时，显示一个电子邮件列表总计15封电子邮件。 同样，旧调查可能会开始显示比资源管理器查询更高的计数，因为 Microsoft Defender for Office 365 计划2中的数据在试用版的7天后过期，在30天后适用于付费许可证。  

在不同视图中显示计数历史和当前计数已完成，以指示调查时的电子邮件影响和当前影响，直到运行补救时间为止。

> [!NOTE]
> 在电子邮件上下文中，您可能会在调查过程中看到一个卷异常威胁曲面。 卷异常表明调查事件时间与之前的时间框架相比，与调查事件的类似电子邮件中的峰值。 这种具有类似特征的电子邮件通信中的此峰值 (例如，subject 和发件人域、正文相似性和发件人 IP) 通常是电子邮件市场活动或攻击的开始。 但是，批量、垃圾邮件和合法电子邮件活动通常共享这些特征。 
>
> 由于使用反病毒引擎、沙箱或恶意信誉识别的恶意软件或网络钓鱼威胁相比，大量异常会带来潜在的威胁，因此可能会降低严重程度。

### <a name="user-investigation"></a>用户调查

在 " **用户** " 选项卡上，您可以看到标识为调查的一部分的所有用户。 当存在事件或指示这些用户帐户可能受到影响或受到威胁时，用户帐户将出现在调查中。

例如，在下图中，空气根据创建的新收件箱规则确定了安全指标和异常情况。 可通过此选项卡中的详细视图获取调查 (证据) 的其他详细信息。损坏的现象和异常也可能包含来自 [Microsoft 云应用安全性](https://docs.microsoft.com/cloud-app-security)的异常检测。

![空中调查用户页](../../media/air-investigationuserspage.png)

可执行下列操作：

- 获取已确定的用户结果和发现的风险的直观概述。

- 选择用户以打开显示完整警报详细信息的飞出页面。

### <a name="machine-investigation"></a>机器调查

在 " **计算机** " 选项卡上，您可以看到标识为调查的一部分的所有计算机。

![空中调查计算机页面](../../media/air-investigationmachinepage.png)

作为一些行动手册的一部分，空中将电子邮件威胁与设备关联 (例如，Zapped 恶意软件) 。 例如，调查会将恶意文件哈希传递到 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) 以进行调查。 这样，就可以为您的用户自动调查相关的计算机，以帮助确保在云中和终结点上解决威胁。

可执行下列操作：

- 获取发现的当前计算机和威胁的直观概述。

-  选择一台计算机以打开在 Microsoft Defender 安全中心的相关 [Microsoft defender For Endpoint 调查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) 中的视图。

### <a name="entity-investigation"></a>实体调查

在 " **实体** " 选项卡上，您可以看到在调查过程中标识和分析的实体。

在这里，您可以查看调查的实体和实体类型的详细信息，例如电子邮件、群集、IP 地址、用户等。 您还可以查看已分析的实体数以及与每个实体相关联的威胁。

!["航空调查实体" 页](../../media/air-investigationentitiespage.png)

可执行下列操作：

- 获取发现的调查实体和威胁的直观概述。

- 选择一个实体以打开显示相关实体详细信息的飞出页面。

![空中调查实体详细信息](../../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a>行动手册日志

在 " **日志** " 选项卡上，您可以查看调查过程中的所有操作手册步骤。 该日志将捕获由 Office 365 自动调查功能作为空气的一部分完成的所有分析器和操作的完整清单。 它提供了所执行的所有步骤的清晰视图，包括操作本身、说明以及实际 "开始到完成" 的持续时间。

![航空调查日志页](../../media/air-investigationlogpage.png)

可执行下列操作：

- 获取有关执行操作手册步骤的直观概述。

- 将结果导出到 CSV 文件。
- 筛选视图。

### <a name="recommended-actions"></a>建议的操作

在 " **操作** " 选项卡上，您可以查看在调查完成后建议用于修正的所有操作手册操作。 操作会捕获 Microsoft 建议在调查结束时执行的步骤。 您可以通过选择一个或多个操作来采取补救措施。 

选择 " **批准** " 可开始进行修正。  (需要适当的权限-必须具备 **搜索和清除** 角色才能从资源管理器和 AIR) 运行操作。 

例如，安全读者可以查看操作，但不能批准。 

> [!IMPORTANT]
> 您无需批准每个操作。 如果您不同意建议的操作，或者您的组织未选择特定类型的操作，则可以选择 **拒绝** 这些操作，也可以仅忽略它们，不执行任何操作。 "批准和/或拒绝所有操作" 可让调查完全关闭 (状态变为 "已修正") ，而保留某些操作不完整将导致调查状态更改为 "部分修正" 状态。

![航空调查操作页](../../media/air-investigationactionspage.png)

可执行下列操作：

- 获取对操作手册建议的操作的直观概述。

- 选择一个或多个操作。

- 使用注释批准或拒绝建议的操作。

- 将结果导出到 CSV 文件。

- 筛选视图。

## <a name="next-steps"></a>后续步骤

- [查看和批准挂起的操作](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)

