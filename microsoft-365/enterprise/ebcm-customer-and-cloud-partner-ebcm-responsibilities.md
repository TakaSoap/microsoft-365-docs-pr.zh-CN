---
title: 客户和云合作伙伴在企业业务连续性方面的责任
author: chrfox
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Microsoft 在服务事件期间采取了哪些措施来让你能够更好地准备业务连续性计划。
ms.openlocfilehash: 9bbf73c736a4391a51edd451db7d23869aa36603
ms.sourcegitcommit: 7690c8bfdea6e6d245cfa7c5b09b913b092cde0a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2019
ms.locfileid: "37122342"
---
# <a name="enterprise-business-continuity-management-customer-and-cloud-partner-responsibilities"></a>客户和云合作伙伴在企业业务连续性方面的责任

你的组织与 Microsoft 之间建立了合作关系，让你能够向用户提供 Microsoft 365 云服务。 由 Microsoft 提供服务，而你负责连接客户端终结点、管理标识和访问权限并管理这些服务的使用方式。 也有一些共同的责任，例如标识和目录基础结构。 本文介绍了在出现服务事件的情况下要保证业务正常运转而需注意的一些关键事项，它可帮助你对发生服务事件时 Microsoft 要执行哪些操作设定预期。

## <a name="transparency-during-service-incidents"></a>服务事件期间操作公开透明

Microsoft 是值得信赖的合作伙伴，它构建了高弹性的云服务并按照结构化流程在服务事件发生时加以处理。 当服务事件发生时，Microsoft 意识到**及时**、**有针对性的**和**高度可触达的**通信对客户而言非常重要。

## <a name="timely"></a>及时
Microsoft 通过更新 Microsoft 365 管理门户上租户专用的服务运行状况仪表板 (SHD) 来通知 Microsoft 365 管理员。 服务事件动态通常每小时提供一次。 如果需调整频率，我们将在 SHD 通信公告中让你获知所做的更改。

## <a name="targeted"></a>有针对性
在大多数情况下，当我们的监视系统检测到问题时，我们可确定受影响的客户群（范围从一名客户到区域或更大范围不等），并向这些客户发送必要的通知。 这可帮助你了解业务须知信息，而不受对你没有影响的不必要通知的干扰。 例如，如果特定邮箱数据库受到影响，我们能够准确确定哪些客户有用户位于受影响的基础结构中并向他们发送通知。 如果事件影响范围不明确，我们会向可能受到影响的范围最广的客户发送通知。

## <a name="highly-avaliable"></a>高度可触达
Microsoft 维持了多个渠道可供客户用来获取服务状态通知。

- 如果管理中心或其中的服务运行状况仪表板不可用，你可使用我们的[备份网站](https://status.office365.com/)监视服务状态。
- 我们保留了 Twitter 帐户 [@MSFT365Status](https://twitter.com/msft365status?lang=en)，我们将在这里答复影响报告并发布 SHD 影响事件的最新动态。
- 借助适用于 Microsoft 365 租户管理员的管理应用，可随时随地了解你所在组织的 Microsoft 365 服务状态。 租户管理员可在其移动设备上查看服务运行状况信息和维护状态更新。 有关详细信息，请访问[管理应用常见问题解答](https://docs.microsoft.com/zh-CN/office365/admin/admin-overview/admin-mobile-app?view=o365-worldwide)。
- 通过 [Microsoft 365 服务通信 API](https://docs.microsoft.com/zh-CN/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#office-365-service-communications-api) 可访问服务通知，从而可更轻松地监视你的环境。 可连接到 API、接收实时服务运行状况数据，还可在内部仪表板上发布消息，将事件告知给企业用户。 通过在内部分发信息，可降低服务中断期间支持人员的负担。
- 对于主要事件，Microsoft 会在管理中心向 SHD 发布事后回顾 (PIR)。 PIR 包含了关键事件信息，可帮助你了解服务中断的本质。 它通常包含以下部分：
    - 对用户的影响
    - 影响范围
    - 事件开始/结束日期和时间
    - 根本原因
    - 执行的操作
    - 后续步骤
- 可在 Microsoft 365 消息中心查看辅助消息，例如有关即将进行的更改、新功能或计划内维护的通知。
- 有关详细信息，请参阅[服务运行状况和连续性指南](https://docs.microsoft.com/zh-CN/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)，详细了解不同的通信渠道以及服务运行状况监视方式。
 
你的组织与 Microsoft 之间建立了合作关系，让你能够提供对 Microsoft 365 联机服务的访问权限。 下图总结了服务事件和定期操作期间 Microsoft 与客户之间责任的平衡。

![客户与 Microsoft 责任间的平衡](media\ebcm\responsibilities.png)

## <a name="your-environment---service-continuity"></a>你的环境 - 服务连续性
考虑连续性计划时，请注意可能影响你的组织的事件以及其整体通知能力。 概括来讲，有三个因素可能会影响你的业务。

### <a name="people"></a>人员
考虑自然灾害或流行病等会影响员工的事件。 如果员工分布广泛，则由于本质上不太可能造成大规模的影响，因而此因素常会被忽略。 但是，如果有很大比例的员工没法工作，你的企业才会继续运转吗？ 那么如何缓解这一影响呢？

### <a name="location"></a>位置
很多组织都要求员工在特定的物理位置或网络位置工作，以便连接到企业系统和云服务。  
Microsoft 发布了[网络连接原则](https://docs.microsoft.com/zh-CN/office365/enterprise/office-365-network-connectivity-principles)，它可引导企业找到最佳做法来设置到云资源的网络连接。 优化示例包括实施拆分的隧道 VPN，以便直接从用户的网络而不是通过 VPN 隧道进行连接。  虽然这些连接原则对维持低延迟连接很重要，但要保证服务弹性，需要用替代方法连接到公司资源来进行常规协作。

### <a name="systems"></a>系统
很多协作解决方案都依赖于系统，例如公司广域网 (WAN)。 当这些系统不可用时，你的组织会如何应对？
下图展示了可能影响多个方面的问题。 随附的表格提供了要考虑的示例

![维恩图](media\ebcm\venn-diagram.png)

你的连续性计划应将上述每个方面都考虑在内。 例如，如果你需要用户访问公司网络，但当地下暴风雪了，那么这些用户如果能够访问关键资源呢？ 如果大雪让用户没法抵达办公室，而服务工程师必须连接到公司网络，有没有策略批准他们在家中持有公司笔记本电脑呢？
