---
title: 保留策略和保留标签策略的限制
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: 了解策略、每个保留策略和保留标签策略项目的最大数量
ms.openlocfilehash: 881aa208036bab4fe476bb424e42ff16dbb5344f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195565"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a>保留策略和保留标签策略的限制

>*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

使用“[保留策略和保留](retention.md#retention-policies-and-retention-labels)”来自动保留或删除组织数据时，请注意一些最大数量。

## <a name="maximum-number-of-retention-labels-per-tenant"></a>每个租户的最大保留标签数

每个租户最多支持 1,000 个保留标签。

## <a name="maximum-number-of-policies-per-tenant"></a>每个租户策略的最大数

单个租户最多可有 10,000 个策略（任何配置）。 此最大数量包括不同的保留策略，以及用于合规性的其他策略，例如 DLP、信息屏障、电子数据展示保留和敏感度标签。

在此 10,000 个策略限制内，每个工作负载的最大保留策略数也有一些限制:

- Exchange Online（任何配置）：1800
- SharePoint 或 OneDrive：（自动包含所有网站）：13
- SharePoint 或 OneDrive（包含或排除的特定位置）：2,600

尽管 Microsoft Teams 和 Yammer 的保留策略使用邮箱来存储数据以用于保留，但 Exchange Online 的最大策略数排除 Teams 和 Yammer 的保留策略。

## <a name="maximum-number-of-items-per-policy"></a>每个策略的最大项目数

当使用可选配置将保留设置搜索范围缩小到特定用户、特定 Microsoft 365 组或特定网站时，才需要注意每个策略的限制： 

每个保留策略的最大项目数：

- Exchange 邮箱：1000
- Microsoft 365 组：1000
- Teams 频道消息：1000
- Teams 聊天：1000
- Yammer 社区消息：1000
- Yammer 用户消息：1000
- SharePoint 网站：100
- OneDrive 帐户：100

Skype for Business 仅限于特定用户，且每个策略支持的数量上限是 1000。

因为这些限制针对每个策略，因此如果你需要使用会导致超过这些数字的特定包含或排除，则可以创建具有相同保留设置的额外策略。 请参阅下一节，了解为此理由使用多重保留策略的一些 [场景示例和解决方案](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers)。

但是，多重保留策略会产生更高的管理费用，因此要时刻确认自己是否真的需要包含和排除。 请记住，适用于整个位置的默认配置没有任何限制，这种配置选择可能是比创建和维护多重策略更好的解决方案。

> [!TIP]
> 如果需要为此方案创建和维护多重策略，请考虑使用 [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) 以实现更高效的配置。

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a>使用多个策略以避免超过最大数量的示例

下面的示例提供了一些设计方案，可在不能仅指定保留策略的位置，并且必须考虑上一节中所述的最大项目数时使用。

Exchange 示例：

- **要求**：在具有超过40000个用户邮箱的组织中，大多数用户必须将其电子邮件保留7年，但一部分已确定的用户（425）的电子邮件仅必须保留5年。

- **解决方案**：为 Exchange 电子邮件创建一个保留期为7年的保留策略，并排除用户子集。 然后为 Exchange 电子邮件创建保留期为5年的第二个保留策略，其中包括用户子集。 
    
    在这两种情况下，包含和排除的数目都低于单个策略的最大指定邮箱数，并且用户的子集必须从第一个策略中明确排除，因为它的[保留期](retention.md#the-principles-of-retention-or-what-takes-precedence)比第二个策略长。如果用户的子集需要更长的保留策略，则不需要将他们从第一个策略中排除。
     
    使用此解决方案，如果有其他人新加入组织，则其邮箱将自动包含在限期为7年的第一个策略中，并且不会对支持的最大数量产生任何影响。 但是，需要 5 年保留期的新用户将添加到包括和不包括数量中，并且该限制将达到 1000 个。

SharePoint 示例：

- **要求**：一个组织拥有几千个 SharePoint 网站，但只有2000个网站需要10年的保留期，8000个网站要求保留期为4年。

- **解决方案**：为 SharePoint 创建20个保留策略，保留期为10年，其中包括100个特定的网站，并为 SharePoint 创建80条保留策略，保留期为4年，其中包括100个特定网站。
    
    由于无需保留所有 SharePoint 网站，因此必须创建指定特定网站的保留策略。 由于一个保留策略不支持超过100个指定网站，因此必须为两个保留期创建多个策略。 这些保留策略中包含的网站数量最多，因此下一个需要保留的新网站需要一个新的保留策略，而不考虑保留期。

## <a name="maximum-number-of-items-for-disposition"></a>每个处置的最大项目数

对于[内容处置](disposition.md)，有一些需要注意的限制:

- 每个保留标签在每个阶段最多 1000000 个等待处置的项

- 处置证明在项被处置后至多七年内可用，此期间每个保留标签最多 1000000 个项。 
    
如果你需要超过 1000000 个记录项的证明，请联系 [Microsoft 支持](../business-video/get-help-support.md)。
