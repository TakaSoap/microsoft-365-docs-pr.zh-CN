---
title: Microsoft 365 组、团队和 SharePoint 协作的合规性选项
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
description: 了解 Microsoft 365 组、团队和 SharePoint 协作的合规性选项。
ms.openlocfilehash: 0383b0728d9b8ea12ce75de8bf0e250932d14ae5
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377529"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Microsoft 365 组、团队和 SharePoint 协作的合规性选项

Microsoft 365 提供了全套工具，以在用户协作的同时保持合规性。 查看这些选项并考虑它们如何映射到您的业务需求、数据的敏感性以及用户需要与之协作的人员的范围。

下表提供了适用于 Microsoft 365 中的合规性控件的快速参考。 以下各节提供了详细信息。

|类别|说明|参考|
|:-------|:----------|:--------|
|信息保留|||
||保留组邮件和 SharePoint 内容|[了解 SharePoint 和 OneDrive 的保留策略](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||保留聊天和消息|[了解 Microsoft Teams 的保留策略](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|信息分类|||
||对组和团队进行分类|[使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||自动对敏感内容进行分类|[将敏感度标签自动应用于内容](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||加密敏感内容|[通过敏感度标签应用加密，从而限制对内容的访问](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|信息保护|||
||防止敏感信息丢失|[数据丢失防护概述](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||保护聊天中的敏感信息。|[数据丢失防护和 Microsoft 团队](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||定义组织的敏感信息|[自定义敏感信息类型](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|用户细分|||
||限制用户区段之间的通信|[信息屏障](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>信息保留

保留策略可用于保留或删除组和团队中用于协作的项目，包括文件、邮件和邮件。 可以将策略设置为保留和删除、仅保留或仅删除。 当组或团队过期或被删除时，保留策略所涵盖的信息将受到保护。

为 Microsoft 365 组配置保留策略将覆盖组邮箱以及关联的 SharePoint 网站和文件。

- [了解 SharePoint 和 OneDrive 的保留策略](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

工作组的保留策略保留聊天和频道消息。 虽然聊天和频道邮件存储在 Exchange 邮箱中，但它们不受 Exchange 保留策略的影响。 您必须设置保留策略以应用于团队聊天和团队频道邮件：

- [了解 Microsoft Teams 的保留策略](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Microsoft Teams 中的保留策略](https://docs.microsoft.com/microsoftteams/retention-policies)

可以将单个保留策略设置为适用于 Microsoft 365 组、团队聊天和团队频道消息。 

其他资源：

- [了解有关保留策略的信息](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- Exchange 中的[保留标记和保留策略](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

## <a name="information-classification"></a>信息分类

您可以使用敏感度标签管理来宾访问、组和团队隐私，并为组和团队提供非托管设备的访问权限。 通过应用标签，这些设置将自动配置为由标签设置指定的设置。

- [使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

您可以根据您指定的条件，将 Microsoft 365 配置为自动将灵敏度标签应用于文件和电子邮件，包括检测敏感信息类型或与 trainable 分类程序的模式匹配。

- [将敏感度标签自动应用于内容](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

您可以使用敏感度标签对文件进行加密，仅允许具有解密和读取这些文件的权限。

- [通过敏感度标签应用加密，从而限制对内容的访问](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [配置具有安全隔离的团队](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

其他资源：

- [了解敏感度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>信息保护

DLP 策略可防止在 SharePoint、Exchange 和团队之间意外共享敏感信息。 您可以创建策略来指定要执行的操作 (如基于一组规则阻止访问) 。

- [数据丢失防护概述](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

团队中的 DLP 可以通过删除包含敏感信息的邮件来帮助保护工作组聊天和频道消息中的敏感信息。

- [数据丢失防护和 Microsoft 团队](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

如果您有组织特有的敏感信息（如项目代码名称），您可以创建自己的敏感信息类型，并将其应用于 DLP 策略以保护组、团队和 Sharepoint 中的内容。

- [自定义敏感信息类型](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>用户细分

通过信息障碍，您可以对数据和用户进行分段，以限制组之间的不必要的通信和协作，并避免组织中的利益冲突。 信息障碍允许您创建策略以允许或阻止组织中的人员组之间的文件协作、聊天、通话或会议邀请。

- [信息屏障](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Microsoft 团队中的信息障碍](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [在 SharePoint 中使用信息障碍](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>相关主题

[Exchange Online 的安全性和合规性](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[保护信息](https://docs.microsoft.com/microsoft-365/compliance/protect-information)


