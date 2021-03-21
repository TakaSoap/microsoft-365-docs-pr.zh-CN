---
title: Microsoft 365 组、Teams 和 SharePoint 协作的合规性选项
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 了解 Microsoft 365 组、Teams 和 SharePoint 协作的合规性选项。
ms.openlocfilehash: 88083d88b274e750e0fc6f1907268c996312163c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920888"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Microsoft 365 组、Teams 和 SharePoint 协作的合规性选项

Microsoft 365 提供了一整套工具来在用户协作时保持合规性。 查看这些选项，并考虑它们如何映射到业务需求、数据的敏感度以及用户需要协作的用户范围。

下表提供了 Microsoft 365 中提供的合规性控件的快速参考。 以下各节提供了进一步的信息。

|类别|说明|参考|
|:-------|:----------|:--------|
|信息保留|||
||保留组邮件和 SharePoint 内容|[了解 SharePoint 和 OneDrive 的保留策略](../compliance/retention-policies-sharepoint.md)|
||保留聊天和消息|[了解 Microsoft Teams 的保留策略](../compliance/retention-policies-teams.md)|
|信息分类|||
||对组和团队进行分类|[使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](../compliance/sensitivity-labels-teams-groups-sites.md)|
||自动对敏感内容进行分类|[将敏感度标签自动应用于内容](../compliance/apply-sensitivity-label-automatically.md)|
||加密敏感内容|[通过敏感度标签应用加密，从而限制对内容的访问](../compliance/encryption-sensitivity-labels.md)|
|信息保护|||
||防止丢失敏感信息|[数据丢失防护概述](../compliance/data-loss-prevention-policies.md)|
||保护聊天中的敏感信息。|[数据丢失防护和 Microsoft Teams](../compliance/dlp-microsoft-teams.md)|
||定义组织的敏感信息|[自定义敏感信息类型](../compliance/sensitive-information-type-learn-about.md)|
|用户细分|||
||限制用户区段之间的通信|[信息屏障](../compliance/information-barriers.md)|

## <a name="information-retention"></a>信息保留

保留策略可用于保留或删除用于组和团队中协作的项目，包括文件、邮件和邮件。 可以将策略设置为保留和删除、仅保留或仅删除。 如果组或团队过期或被删除，保留策略涵盖的信息将受到保护。

为 Microsoft 365 组配置保留策略涵盖组邮箱以及关联的 SharePoint 网站和文件。

- [了解 SharePoint 和 OneDrive 的保留策略](../compliance/retention-policies-sharepoint.md)

Teams 的保留策略保留聊天和频道消息。 当聊天和频道消息存储在 Exchange 邮箱中时，它们不受 Exchange 保留策略的影响。 必须将保留策略设置为应用于 Teams 聊天和 Teams 频道消息。 

即使删除了用户帐户，用户聊天也无限期保留。 如果您不想无限期保留此数据，请考虑使用保留策略在指定的时间后删除用户聊天，或将此删除操作包括在用户删除过程中。

- [了解 Microsoft Teams 的保留策略](../compliance/retention-policies-teams.md)

- [Microsoft Teams 中的保留策略](/microsoftteams/retention-policies)

可以将单个保留策略设置为应用于 Microsoft 365 组、Teams 聊天和 Teams 频道消息。 

其他资源：

- [了解有关保留策略的信息](../compliance/retention.md)

- Exchange[中的保留标记和](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)保留策略

## <a name="information-classification"></a>信息分类

可以使用敏感度标签来管理来宾访问、组和团队隐私，以及组和团队的不受管理设备的访问。 通过应用标签，这些设置将按标签设置指定自动配置。

- [使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](../compliance/sensitivity-labels-teams-groups-sites.md)

你可以配置 Microsoft 365，以根据指定的条件将敏感度标签自动应用于文件和电子邮件，包括检测敏感信息类型或模式与可训练分类器匹配。

- [将敏感度标签自动应用于内容](../compliance/apply-sensitivity-label-automatically.md)

敏感度标签可用于加密文件，仅允许具有解密和读取权限的文件。

- [通过敏感度标签应用加密，从而限制对内容的访问](../compliance/encryption-sensitivity-labels.md)

- [配置具有安全隔离的团队](./secure-teams-security-isolation.md)

其他资源：

- [了解敏感性标签](../compliance/sensitivity-labels.md)


## <a name="information-protection"></a>信息保护

DLP 策略可以防止在 SharePoint、Exchange 和 Teams 之间意外共享敏感信息。 可以创建策略来指定要执行 (操作，例如) 一组规则阻止访问。

- [数据丢失防护概述](../compliance/data-loss-prevention-policies.md)

Teams 中的 DLP 可以通过删除包含敏感信息的消息来帮助保护 Teams 聊天和频道消息中的敏感信息。

- [数据丢失防护和 Microsoft Teams](../compliance/dlp-microsoft-teams.md)

如果您有组织特有的敏感信息（如项目代码名称），您可以创建自己的敏感信息类型，并应用于 DLP 策略以保护组、团队和 Sharepoint 中的内容。

- [自定义敏感信息类型](../compliance/sensitive-information-type-learn-about.md)

## <a name="user-segmentation"></a>用户细分

通过信息屏障，你可以划分数据和用户，以限制组之间不需要的通信和协作，并避免组织的利益冲突。 信息屏障允许你创建策略，以允许或阻止组织中各组人员之间的文件协作、聊天、通话或会议邀请。

- [信息屏障](../compliance/information-barriers.md)

- [Microsoft Teams 中的信息屏障](/microsoftteams/information-barriers-in-teams)

- [在 SharePoint 中使用信息屏障](/sharepoint/information-barriers)

## <a name="related-topics"></a>相关主题

[协作治理规划分步规划](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[创建协作管理计划](collaboration-governance-first.md)

[Exchange Online 安全性和合规性](/exchange/security-and-compliance/security-and-compliance)

[保护信息](../compliance/information-protection.md)