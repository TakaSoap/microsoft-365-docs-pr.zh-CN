---
title: 数据移动常见问题解答
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 1f01bc6f-5d37-4d14-bdd3-9d94a1e23e14
f1.keywords:
- NOCSH
description: 查找常见问题解答 (常见问题解答) 核心数据移动到新的 Office 365 数据中心地理位置。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 46dfdddc50c62970b679a130b3cccf692648cd5c
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52298048"
---
# <a name="data-move-general-faq"></a>数据移动常见问题解答

下面是有关将静止的核心客户数据移动到新数据中心地理位置的一般问题的答案。
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>哪些客户有资格请求移动？
  
选择符合新数据中心地理位置条件的国家/地区的现有 Microsoft 365 商业客户将能够请求迁移。 该计划仅适用于具有分配给 Microsoft 365 租户的符合条件的国家/地区代码的租户，用于将符合条件的工作负载的其余核心客户数据迁移到相应的 Microsoft 365 数据中心地理位置。 请参阅如何请求 [数据移动页面](request-your-data-move.md) 以确认国家/地区资格。   

## <a name="how-do-we-define-core-customer-data"></a>如何定义核心客户数据？
 
核心客户数据是一个术语，它引用在"客户术语"中定义的Microsoft Online Services [子集](https://aka.ms/ost)： 
- Exchange Online 邮箱 (电子邮件正文、日历条目以及电子邮件附件内容) 
- SharePoint Online 网站内容和存储在该网站中的文件
- 上传到 OneDrive for Business 的文件 

## <a name="what-is-in-scope-for-teams-migration"></a>Teams 迁移的范围是什么？

除了 Exchange Online、SharePoint Online 和 OneDrive for Business;Microsoft 将 Teams 数据迁移到本地数据中心。 
- Teams 聊天消息，包括私人消息和频道消息。 
- 聊天中使用的 Teams 图像。 

Teams 文件存储在 SharePoint Online 中，Teams 聊天文件存储在 OneDrive for Business 中。 语音邮件、日历和联系人存储在 Exchange Online 中。 在许多情况下，Exchange Online、SharePoint Online 和 OneDrive for Business 已由本地数据中心地理位置的客户使用，也是符合条件的客户国家/地区 Microsoft 365 迁移计划的一部分。

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>我的迁移在什么时间点完成，以便我的租户的核心客户数据存储在我的新地理位置中？

由于 Exchange Online 和 SharePoint Online/OneDrive for Business 之间的共享依赖关系，在迁移这两个服务之前，任何迁移都被视为已完成。 Exchange Online 和 SharePoint Online/OneDrive for Business 通常在单独的时间相互独立迁移。 客户租户管理员在每个服务迁移完成时在消息中心收到确认，并且随时可以在管理中心查看数据位置卡，以确认每个服务的其余位置的核心客户数据。

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>如何确保在移动期间我的客户数据是安全的，并且不会经历停机时间？
  
数据移动是后端服务操作，对最终用户的影响最小。 在数据移动期间和之后， [会列出可影响的功能](during-and-after-your-data-move.md)。 我们遵守Microsoft Online Services [SLA ](https://go.microsoft.com/fwlink/p/?LinkId=523897) (SLA) ，因此在移动过程中客户无需准备或监视任何内容。 
  
所有 Microsoft 365 服务在数据中心中运行相同版本，因此可以保证功能一致。 服务在整个过程中受到完全支持。
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>将不同的服务位于不同的地理位置会有什么影响？

某些 Microsoft 365 服务可能位于某些现有客户和进行移动过程中间的客户的不同地理位置。 我们的服务相互独立运行，如果是这样，则不会影响用户体验。 但是，出于数据驻留目的，在将 Exchange Online 和 SharePoint Online/OneDrive for Business 迁移到同一数据中心地理位置之前，租户迁移不能被视为已完成。

 ## <a name="where-is-my-core-customer-data-located"></a>我的核心客户数据位于何处？

客户租户管理员可以随时在管理中心内查看数据位置卡，以确认每个服务（特别是针对其租户）的其余位置的核心客户数据。  我们还在 Microsoft 365 交互式数据中心地图上发布了数据中心地理位置、数据中心和 Office [365 ](https://office.com/datamaps) 客户数据的位置，作为新租户的其余位置的当前默认核心客户数据的参考。 可以通过 Microsoft 365 管理中心中"组织配置文件"下的"数据位置"部分验证客户数据处于其余位置。  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>我何时可以请求移动？
  
请参阅如何请求 [数据](request-your-data-move.md) 移动页面，了解数据中心地理位置支持的时间范围。
  
## <a name="how-can-i-request-to-be-moved"></a>如何请求移动？
  
符合条件的客户将看到 Microsoft [365 管理中心中的页面](https://admin.microsoft.com/)。 有关如何 [请求移动的说明，](request-your-data-move.md) 请参阅如何请求数据移动。 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>在请求移动后，我能否更改选择？
  
提交请求后，我们无法从流程中删除你。
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>如果我在截止时间之前没有请求移动，会发生什么情况？
  
在开放注册期后，我们不接受迁移请求。

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>如果我想移动数据以获得更好的网络性能，该做什么？
  
与 Microsoft 365 数据中心的物理邻近度无法保证更好的网络性能。 影响最终用户和 Microsoft 365 服务之间的网络性能的因素和组件有很多。 有关此优化和性能调整的信息，请参阅 [Microsoft 365 的网络规划和性能调整](network-planning-and-performance.md)。
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>所有服务是否在同一天移动数据？
 
每个服务将独立移动，并且可能会在不同时间移动数据。
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>我可以选择何时移动数据？
 
客户无法选择特定日期，他们无法延迟移动，我们无法共享移动的特定日期或时间范围。
  
 ## <a name="can-you-share-when-my-data-will-be-moved"></a>可以共享何时移动我的数据？
  
数据移动是后端操作，对最终用户的影响最小。 在全局运营和自动化环境中执行数据移动所需的复杂性、精度和规模会禁止我们在预计租户或其他任何单个租户完成数据移动时进行共享。 完成数据移动后，客户将在每个参与服务的消息中心收到一个确认。 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>如果用户在数据移动时访问服务，会发生什么情况？

有关 [在每个服务](during-and-after-your-data-move.md) 的数据移动部分过程中可能受到限制的功能的完整列表，请参阅"数据移动期间"和"之后"。 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>我如何知道移动已完成？
  
观看 Microsoft 365 消息中心，确认每项服务数据移动已完成。 当移动每个服务的数据时，我们将发布完成通知，以便你收到三个完成通知：分别针对 Exchange Online、SharePoint Online 和 Skype for Business Online。 您还可以通过 Microsoft 365 管理中心中"组织配置文件"下的"数据位置"部分验证客户数据处于其余位置。  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>我是一个新的数据中心地理位置中的 Microsoft 365 客户，但在注册时，我选择了不同的国家/地区。 如何移动到新的数据中心地理位置？

无法更改与租户关联的注册国家/地区。 相反，你需要使用新订阅创建新的 Microsoft 365 租户，并手动将用户和数据移动到新租户。
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>如果在 Exchange Online 移动期间我们正将电子邮件数据迁移到 Microsoft 365，会发生什么情况？

这是一种非常常见的方案，完全受支持。  数据中心地理位置之间的云迁移不会干扰任何本地到云邮箱的迁移。
  
 ## <a name="can-i-pilot-some-users"></a>能否试用某些用户？
  
你可以创建单独的试用租户来测试连接，但无法以任何方式将试用租户与现有租户结合使用。

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>我不想等待 Microsoft 移动我的数据。 我可以创建新租户并移动自己吗？
  
可以，但该过程不会像 Microsoft 执行数据移动一样无缝。
  
如果在新的数据中心地理位置可用后创建新租户，则新租户将托管在新地理位置中。 此新租户与以前的租户完全分开，你应负责移动所有的用户邮箱、网站内容、域名和任何其他数据。 请注意，你无法将租户名称从一个租户移动到另一个租户。 我们建议你等待 Microsoft 提供的移动计划，因为我们将负责移动用户的所有设置、数据和订阅。
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>我的客户数据已移动到新的数据中心地理位置。 我能否后退？
 
否，这是不可能的。 已移动到新地理位置数据中心的客户无法移回。 作为任何地理位置的客户，你将体验与之前相同的服务质量、性能和安全控制。 [Microsoft 365](https://aka.ms/multi-geo) 多地理位置作为加载项提供给一些客户，允许单个租户创建多个附属地理位置，并借助数据驻留承诺将用户数据移动到这些地理位置。
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>托管于新数据中心的 Microsoft 365 租户将可供美国以外的用户使用吗？
  
是的。 Microsoft 维护了一个大型全球网络，其公共 Internet 连接位于全球 35 个国家/地区中的 130 多个位置，与超过 2，700 个 Internet 服务提供商 (ISP) 。 用户将能够从 Internet 上任何位置访问数据中心。

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>我的租户已配置 [多地理位置加载项](https://aka.ms/multi-geo)。 我是否仍可以在 Microsoft 365 移动计划租户中注册以更改默认地理位置，以及将附属区域外的任何用户移动到新的默认地理位置？

可以，租户符合注册条件，但存在重要注意事项，因为已配置多地理位置的客户未完全支持租户级移动。

SharePoint Online 和 OneDrive for Business 无法通过此计划迁移到租户级别的新数据中心地理位置。 客户管理员可以将 OneDrive for Business 共享配置为使用多地理位置移动到任何可用区域，但在为租户配置多地理位置后，无法更改租户的默认位置。

对于选择迁移的客户 - 我们会将当前默认地理位置的所有 Exchange Online 邮箱移动到新的本地数据中心地理位置，并更新默认 Exchange Online 区域。 我们不会移动在多地理位置附属区域配置的任何 EXO 邮箱，以继续根据预期遵守附属区域数据驻留。 

## <a name="related-topics"></a>相关主题

[将核心数据移动到新的 Microsoft 365 数据中心地理位置](moving-data-to-new-datacenter-geos.md)

[如何请求数据移动](request-your-data-move.md)

[Microsoft 365 多地理位置](https://aka.ms/multi-geo)

[Microsoft 365 交互式数据中心地图](https://office.com/datamaps)

[Microsoft 365 支持](../business-video/get-help-support.md)

[新的数据中心地理位置Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[按区域表示的 Azure 服务](https://azure.microsoft.com/regions/)