---
title: 组、Microsoft 365和Teams的合规性SharePoint选项
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: 了解组、Microsoft 365和Teams的合规性SharePoint选项。
ms.openlocfilehash: ab840ea5652a13087ecc8d505391bac152ca1052
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2021
ms.locfileid: "61063365"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>组、Microsoft 365和Teams的合规性SharePoint选项

Microsoft 365提供了一整套工具来在用户协作时保持合规性。 查看这些选项，并考虑它们如何映射到业务需求、数据的敏感度以及用户需要协作的用户范围。

下表提供了一个快速参考，以快速了解 Microsoft 365。 以下各节提供了进一步的信息。

|类别|说明|参考|
|:-------|:----------|:--------|
|信息保留|||
||保留组邮件和SharePoint内容|[了解 SharePoint 和 OneDrive 的保留策略](../compliance/retention-policies-sharepoint.md)|
||保留聊天和消息|[了解 Microsoft Teams 的保留策略](../compliance/retention-policies-teams.md)|
|信息分类|||
||对组和团队进行分类|[使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](../compliance/sensitivity-labels-teams-groups-sites.md)|
||自动对敏感内容进行分类|[将敏感度标签自动应用于内容](../compliance/apply-sensitivity-label-automatically.md)|
||加密敏感内容|[通过敏感度标签应用加密，从而限制对内容的访问](../compliance/encryption-sensitivity-labels.md)|
|信息保护|||
||防止丢失敏感信息|[了解数据丢失防护](../compliance/dlp-learn-about-dlp.md)|
||保护聊天中的敏感信息。|[数据丢失防护和 Microsoft Teams](../compliance/dlp-microsoft-teams.md)|
||定义组织的敏感信息|[自定义敏感信息类型](../compliance/sensitive-information-type-learn-about.md)|
|用户细分|||
||限制用户区段之间的通信|[信息屏障](../compliance/information-barriers.md)|
|数据驻留|||
||将数据存储到特定地理位置|[Microsoft 365 多地理位置](/microsoft-365/enterprise/microsoft-365-multi-geo)|

## <a name="information-retention"></a>信息保留

保留策略可用于保留或删除用于组和团队中协作的项目，包括文件、邮件和邮件。 可以将策略设置为保留和删除、仅保留或仅删除。 如果组或团队过期或被删除，保留策略涵盖的信息将受到保护。

为组配置保留策略Microsoft 365组涵盖组邮箱以及网站和SharePoint关联的邮箱。

- [了解 SharePoint 和 OneDrive 的保留策略](../compliance/retention-policies-sharepoint.md)

聊天和Teams消息的保留策略。 当聊天和频道消息存储在Exchange中时，它们不受Exchange策略的影响。 必须将保留策略设置为应用于Teams聊天和Teams消息。 

即使删除了用户帐户，用户聊天也无限期保留。 如果您不想无限期保留此数据，请考虑使用保留策略在指定的时间后删除用户聊天，或将此删除操作包括在用户删除过程中。

- [了解 Microsoft Teams 的保留策略](../compliance/retention-policies-teams.md)

- [Microsoft Teams 中的保留策略](/microsoftteams/retention-policies)

可以将单个保留策略设置为应用于Teams聊天和Teams消息。 

其他资源：

- [了解有关保留策略的信息](../compliance/retention.md)

- [保留标记和保留策略在](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)Exchange

## <a name="information-classification"></a>信息分类

可以使用敏感度标签来管理来宾访问、组和团队隐私，以及组和团队的不受管理设备的访问。 通过应用标签，这些设置将自动根据标签设置指定进行配置。

- [使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](../compliance/sensitivity-labels-teams-groups-sites.md)

你可以配置Microsoft 365，以根据指定的条件将敏感度标签自动应用于文件和电子邮件，包括检测敏感信息类型或模式与可训练分类器匹配。

- [将敏感度标签自动应用于内容](../compliance/apply-sensitivity-label-automatically.md)

敏感度标签可用于加密文件，仅允许具有解密和读取权限的文件。

- [通过敏感度标签应用加密，从而限制对内容的访问](../compliance/encryption-sensitivity-labels.md)

- [配置具有安全隔离的团队](./secure-teams-security-isolation.md)

其他资源：

- [了解敏感性标签](../compliance/sensitivity-labels.md)


## <a name="information-protection"></a>信息保护

DLP 策略可以防止在用户、用户和SharePoint Exchange意外Teams。 可以创建策略来指定要执行 (操作，例如) 一组规则阻止访问。

- [了解数据丢失防护](../compliance/dlp-learn-about-dlp.md)

dlp in Teams can help protect sensitive information in Teams chat and channel messages by deleting messages that contain sensitive information.

- [数据丢失防护和 Microsoft Teams](../compliance/dlp-microsoft-teams.md)

如果您具有组织特有的敏感信息（如项目代码名称），您可以创建您自己的敏感信息类型，并应用于 DLP 策略以保护组、团队和组织中SharePoint。

- [自定义敏感信息类型](../compliance/sensitive-information-type-learn-about.md)

## <a name="user-segmentation"></a>用户细分

通过信息屏障，你可以划分数据和用户，以限制组之间不需要的通信和协作，并避免组织的利益冲突。 信息屏障允许你创建策略，以允许或阻止组织中各组人员之间的文件协作、聊天、通话或会议邀请。

- [信息屏障](../compliance/information-barriers.md)

- [Microsoft Teams 中的信息屏障](/microsoftteams/information-barriers-in-teams)

- [使用信息屏障SharePoint](/sharepoint/information-barriers)

## <a name="data-residency"></a>数据驻留

通过Microsoft 365多地理位置，可以在已选择满足数据驻留要求的地理位置中预配和存储静止数据。 在多地理位置环境中，Microsoft 365 租户包含一个中心位置 (其中最初预配了 Microsoft 365 订阅的) 以及一个或多个附属位置，你可以存储数据。

- [Microsoft 365 多地理位置](/microsoft-365/enterprise/microsoft-365-multi-geo)

- [Microsoft 365 多地理位置计划](/microsoft-365/enterprise/plan-for-multi-geo)

## <a name="related-topics"></a>相关主题

[协作治理规划建议](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[创建协作管理计划](collaboration-governance-first.md)

[Exchange Online 安全性和合规性](/exchange/security-and-compliance/security-and-compliance)

[保护信息](../compliance/information-protection.md)
