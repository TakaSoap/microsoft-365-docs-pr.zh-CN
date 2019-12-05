---
title: 企业业务连续性管理计划的注意事项
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
description: 开发云感知业务连续性计划时要考虑的事项。
ms.openlocfilehash: a9f8b7f6950375fb976202a10da03662c3b2715a
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831665"
---
# <a name="developing-your-continuity-plan"></a>开发连续性计划

本主题提供有关开发业务连续性计划的指南，该计划会将 Microsoft 365 依赖关系纳入到帐户中。 此处推荐了分析业务功能和确定依赖于 Microsoft 365 服务的内容的方法。 执行此分析时，做好将出现服务故障的预计，并且必须为这些可能性做好准备。

一般说来，业务连续性计划包括四个方面，即评估、计划、功能验证以及通信和协调。

## <a name="assessment"></a>评估
首先，你必须确定组织中的业务功能以及支持它们的服务和流程。 这包括完成业务影响分析（其中每个业务功能按照关键程度进行排名），以及确定每个业务功能所依赖的流程和服务。 下面是一个可参考的示例表，它有助于你开始使用自己的评估。

**业务影响评估 (BIA) 示例**

这是适用于 `name of the service, system, process, or function` 的 BIA 文档

|BIA 字段|说明|
|---------|---------|
|BIA 类型|`is it a business process or technology, service or system?`|
|BIA 名称|`name of the service/system/function/process`|
|服务说明|`give a full description of the service, process, or function`|
|企业功能|`some examples: customer services; legal; marketing; risk management, security, sales, information technology, production, manufacturing`|
|财年|`the current fiscal year, re-evaluate these on a regular basis`|
|关键程度|`develop your own classifications, but here are some examples: mission critical, important, deferrable`|
|业务部门|`name of the business unit that owns this business function`|
|过程（服务、功能）|`the name of the process, service, or feature`|
|业务组高级负责人|`the name and contact information of the senior leader of the business group that owns this business process`|
|该技术是否已建立**内部** SLA 或 OLA？|`please explain in as much detail as possible`|
|该技术是否已建立**外部** SLA 或 OLA？|`please explain in as much detail as possible`|
|该技术是否有一个已知的管理法规要求来推动特定的流程 SLA？ 如果是，请详细说明。|`details here`|
|与此服务相关联的数据的丢失或泄露是否会触发重大事件？ 如果是，请详细说明。|`details here`|
|服务对某些或全部关键功能和特征是否有解决方法或替代措施？ 如果是，请详细说明。|`details here`|
|服务是否处理、存储或传输客户数据（例如个人身份信息 (PII)）？ 如果是，请详细说明。|`details here`|
|BIA 状态|`develop your own status classification, here are some examples: planned, started, in-progress, complete, on-hold, expired`|
|完成日期|`the date this BIA was completed`|
|BIA 推动者|`name of the person or group who is responsible for developing and maintaining this BIA`|
|BIA 批准|`name of the person or group who is the executive sponsor of this BIA and who has responsibility for approving it.`|
|参与者|`optional list of the people who helped develop this BIA and their contact information`|
|BIA 批准位置|`indicate where the executive approval is located, or attach proof to this document`|

## <a name="planning"></a>计划

接下来，你将跨业务流程查看存在任何级联依赖关系的位置。 根据结果，你可以确定优先级并形成弹性策略和支持策略的标准操作过程。

可以使用 [Microsoft 服务映射](https://docs.microsoft.com/azure/azure-monitor/insights/service-map)来帮助你使用此映射。 Microsoft 服务映射会自动发现 Windows 和 Linux 系统上的应用程序组件，并映射所有 TCP 依赖关系，标识连接和应用所依赖的远程第三方系统。 它还会将依赖关系映射到传统上黑暗的网络区域，如 Active Directory。

下面是一个可以着手开始的依赖关系分析 (DA) 示例。 在依赖关系分析 (DA) 中，你将确定并检查流程依赖关系。 请确保包括人员、供应商、客户、合作伙伴和设施。 此分析中的数据将用于确定流程的恢复要求与支持依赖关系的恢复功能之间的差距。


|字段|说明|
|---------|---------|
|流程类型|         |
|推动者|         |
|完成者|         |
|完成日期|         |
|参与者|         |
  
## <a name="capability-validation"></a>功能验证

在对业务流程进行盘存并将关系映射到其他流程和技术后，需要为所有流程构建验证方案。 基本而言，就是确定如何验证业务流程连续性计划。 你可能会发现某些人比其他人更重要，你希望对他们设置优先级。
请记住，制定计划后，在事件响应和连续性措施方面定期培训员工是非常重要的。 应通过将学习与每个验证或测试相结合，采用事后回顾的方法来增强复原策略。

## <a name="incident-coordination-and-communication"></a>事件协调和通信

在服务事件期间，正常通信渠道可能会受到影响或变差，因此应预先安排备选方案，帮助贵组织在事件期间保持联系。 在中断前，请务必建立通信渠道，审查安全性和合规性，并在使用方面对用户进行培训。 无法从一个已知状态到另一个已知状态远比用户在危机中想出临时的、未知的解决方案好得多。

在 Microsoft，每个服务团队已建立内部备用通信渠道，帮助我们在正常通信渠道不可用时进行协调。 其中包括备份电话和音频会议解决方案、Yammer 组、Teams 组、内部服务运行状况仪表板以及内部事件管理软件。

在业务影响分析和依赖关系分析期间，将会映射关键流程及其依赖的技术或服务。 在计划和考虑备选方案过程中，请特别留意有关通信的注意事项。 下面是一些示例。

- 如果电子邮件是随时通知用户和利益干系人的主要方法，而电子邮件服务已降级或不可用，那么你可以使用其他服务（如 Microsoft Teams、Yammer 或其他第三方服务）作为备份。 关键是事先建立这些备份，并向用户培训它们的访问位置。 如果不知道 Yammer 线程是否存在，或者没有人对其进行标记，则 Yammer 线程不会有用。  
- 如果内部事件管理流程依赖于语音通信来协调响应，请建立一个备选电话服务解决方案，以便在危机过程中使用。 此解决方案不需要与主要服务保持完全对等，但应当提供最低级别的协作以协调业务连续性和事件管理团队。 此外，要求用户在全局地址列表中发布移动电话号码，可在极端情况下提供额外层面的备份通信。
- 你可能需要创建自定义服务运行状况仪表板或其他此类站点，从而在事件发生期间提供状态更新。 培训用户预先获取信息的位置将有助于减少对帮助台的不必要呼叫，并灌输用户群体对快速高效处理情况的信心。 使用 O365 服务通信 API 绑定到 M365 可获得更高级别的可见性。  
- 重要的是业务连续性计划和标准操作程序的位置应当是众所周知的。 建议保留关键文档的在线和离线副本，例如将 SharePoint Online 或 OneDrive for Business 配置为自动同步到本地设备。 对于服务/网络运营中心和其他对恢复非常关键的类似团队，可能还需要保留可供紧急情况下使用的硬拷贝。

## <a name="know-your-external-points-of-integration"></a>了解外部集成点

无论使用何种商业模型，每家公司都有与客户、合作伙伴和供应商的集成点。 业务价值供应链是在与外部实体集成的基础上构建的。 改进服务中断情况下的业务连续性需要考虑和保护每个集成点。  
分析供应链时，应按照与分析内部通信的相同方式来考虑外部通信。 客户是否依赖 Exchange Online 服务器作为唯一联系方式？ 你是否已建立并让你的供应商清楚正常运行时间受到影响情况下的备选通信方法？ 下面是一个示例表，它针对如何组织你的想法提出了建议。

|外部实体名称|影响事件方案|集成的 Microsoft 365 服务|替代方法|
|---------|---------|---------|---------|
|`vendor name`|邮件流|Exchange Online 是与 Contoso 通信的唯一方式|设置外部 Microsoft Teams 频道或第三方协作软件          |
|`service supplier name`|聊天|Microsoft Teams|第三方即时消息|
|`partner name`|语音|Microsoft Teams|移动或公共 pstn      |
|`supplier name`|文件共享|外部共享的 SharePoint 网站和 OneDrive|第三方文件共享         |
