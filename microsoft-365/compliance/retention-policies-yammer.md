---
title: 了解用于 Yammer 的保留
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解适用于 Yammer 的保留策略。
ms.openlocfilehash: ea1638b3dd97c97354eff64d0e33d6a4b84a0313
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60175103"
---
# <a name="learn-about-retention-for-yammer"></a>了解用于 Yammer 的保留

>*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

> [!NOTE]
> 此功能暂处于预览阶段，可能会发生变更。

本文中的信息是对[了解保留](retention.md)的补充，因为它包含特定于 Yammer 的信息。

有关其他工作负载，请参阅：

- [了解用于 SharePoint 和 OneDrive 的保留](retention-policies-sharepoint.md)
- [了解用于 Microsoft Teams 的保留](retention-policies-teams.md)
- [了解用于 Exchange 的保留](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>保留和删除包括哪些内容

可以使用 Yammer的保留策略删除 Yammer 用户消息和社区消息，除了消息中的文本外，出于合规性原因，还可以保留以下项目：超文本链接和指向其他 Yammer 消息的链接。

用户消息包括对话中所有人员的姓名，社区消息包括社区名称和消息标题（如有提供）。

使用 Yammer 的保留策略时，不会保留其他人以表情符号的形式做出的反应。

与 Yammer 一起使用的文件不包含在 Yammer 的保留策略中。这些项目有自己的保留策略。

## <a name="how-retention-works-with-yammer"></a>用于 Yammer 的保留的工作原理

使用本节以了解如何通过后端存储和流程满足合规性要求，以及应如何通过电子数据展示工具，而不是通过当前在 Yammer 应用中可见的邮件来进行验证。

可以使用保留策略在 Yammer 中保留社区邮件和用户邮件中的数据，并删除这些邮件。 Exchange 邮箱在后台用于存储从这些邮件中复制的数据。 来自 Yammer 用户邮件的数据存储包含于用户邮件中每个用户邮箱内的隐藏文件夹中，组邮箱中的类似隐藏文件夹则用于社区邮件。

当 @提及用户或通知用户有人答复时，社区邮件的副本也可以存储在用户邮箱的隐藏文件夹中。 尽管这些邮件源自社区邮件，但 Yammer 用户邮件的保留策略通常包括社区邮件的副本。

这些隐藏的文件夹不是为了供用户或管理员直接访问，而是存储合规性管理员可以使用电子数据展示工具搜索的数据。

> [!IMPORTANT]
> 由于社区邮件的副本也可以存储在用户邮箱中，因此对 Yammer 用户邮件执行删除操作的保留策略可能导致 Yammer 应用中的用户不再看到原始社区邮件。
> 
> 但是，原始邮件的副本在社区组邮箱的隐藏文件夹中仍然可用，并可出于合规目的通过电子数据展示搜索进行访问。

Yammer 消息不受为 Exchange 邮箱配置的保留策略的影响。即使 Yammer 消息存储在 Exchange 中，此 Yammer 数据仍将仅包含在为 **Yammer 社区消息** 和 **Yammer 用户消息** 位置配置的保留策略中。

> [!NOTE]
> 如果用户包含在保留 Yammer 数据的活动保留策略中，并且删除了包含在此策略中的用户邮箱，为了保留 Yammer 数据，邮箱会转换为[非活动邮箱](inactive-mailboxes-in-office-365.md)。 如果不需要为用户保留此 Yammer 数据，请在删除用户的邮箱之前，将用户帐户从保留策略中排除。

为 Yammer 消息配置保留策略后，Exchange 服务中的计时器作业会定期评估存储这些 Yammer 消息的隐藏文件夹中的项目。 计时器作业最多需要 7 天才能运行。 这些项目的保留期限到期后，它们将被移至 SubstrateHolds 文件夹，此文件夹是每个用户或组邮箱中的隐藏文件夹，用于在永久删除“软删除”项目之前存储这些项目。

> [!NOTE]
> 由于[第一个保留策略](retention.md#the-principles-of-retention-or-what-takes-precedence)，如果由于另一个保留策略而必须保留同一项目，或者由于法律或调查原因而处于电子数据展示保留状态，则永久删除始终处于暂停状态。

为 Yammer 消息配置保留策略后，内容路径取决于保留策略是“保留后删除”、“仅保留”还是“仅删除”。

如果保留策略为“保留后删除”：

![Yammer 消息的保留流示意图。](../media/yammerretentionlifecycle.png)

对于图中的两条路径：

1. **如果用户在保留期内编辑或删除了 Yammer 消息**，则该原始消息将被立即复制（如果已编辑）或移动（如果已删除）到 SubstrateHolds 文件夹中。 消息将存储在此处，直到保留期到期，然后立即将其永久删除。

2. **如果未删除 Yammer 消息**，并且对于编辑后的当前消息，则保留期到期后，消息将被移至 SubstrateHolds 文件夹。 此操作自到期之日起最多需要 7 天。 如果消息位于 SubstrateHolds 文件夹中时，它将立即被永久删除。 

> [!NOTE]
> 可通过电子数据展示工具搜索 SubstrateHolds 文件夹中的消息。 消息被永久删除（位于 SubstrateHolds 文件夹中）前，仍可由 eDiscovery 工具搜索。

如果保留策略为“仅保留”或“仅删除”，内容路径在“保留后删除”策略的基础上有所变化。

### <a name="content-paths-for-retain-only-retention-policy"></a>“仅保留”保留策略的内容路径

1. **如果编辑或删除了 Yammer 消息**：将立即在 SubstrateHolds 文件夹中创建原始消息的副本，并将其保留在那里，直到保留期到期。然后消息将从 SubstrateHolds 文件夹中立即被永久删除。

2. **如果 Yammer 消息在保持期内未遭修改或删除** 以及保留期内编辑后的当前消息：保留期前后无变化；消息仍保留在原始位置。

### <a name="content-paths-for-delete-only-retention-policy"></a>“仅删除”保留策略的内容路径

1. **如果 Yammer 消息在保持期内未遭删除**：在保持期结束时，消息将移至 SubstrateHolds 文件夹。 此操作自到期之日起最多需要 7 天。 然后，此消息会立即从 SubstrateHolds 文件夹中永久删除。

2. **如果用户在保留期内删除 Yammer 消息**，该项目将立即移至 SubstrateHolds 文件夹，并立即将其永久删除。


## <a name="messages-and-external-users"></a>消息和外部用户

默认情况下，Yammer 用户消息的保留策略应用于组织中的所有用户，但不应用于外部用户。 如果对包含的用户使用“**编辑**”选项并指定其帐户，则可以向外部用户应用保留策略。

目前，不支持 Azure B2B 来宾用户。

## <a name="when-a-user-leaves-the-organization"></a>如果某用户离开组织 

如果用户离开你的组织，并且其 Microsoft 365 帐户被删除，则其要保留的 Yammer 用户消息将存储在非活动邮箱中。 这些消息仍受用户在其邮箱变为非活动状态之前所应用的任何保留策略的约束，并且内容支持电子数据展示搜索。 有关详细信息，请参阅 [Exchange Online 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。 

如果用户在 Yammer 中存储了任何文件，请参阅 SharePoint 和 OneDrive 的[等效部分](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。

## <a name="limitations"></a>限制

Yammer 保留策略目前处于预览阶段，我们正在不断努力优化保留功能。 在此期间，在对 Yammer 社区邮件和用户邮件使用保留时，需要注意以下几个限制：

- 为 **Yammer 用户邮件** 位置选择“**编辑**”时，可能看到来宾和非邮箱用户。 保留策略并非专为这些用户设计的，因此请不要选择他们。

## <a name="configuration-guidance"></a>配置指南

如果你刚开始在 Microsoft 365 中配置保留，请参阅[开始使用保留策略和保留标签](get-started-with-retention.md)。

如果已准备好配置 Teams 的保留策略，请参阅[创建和配置保留策略](create-retention-policies.md)。