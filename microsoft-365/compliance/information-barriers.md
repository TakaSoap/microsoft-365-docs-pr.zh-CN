---
title: 了解 Microsoft 365 中的信息障碍
description: 使用信息屏障来确保在组织中使用 Microsoft Teams 的通信合规性。
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6ca1502c16accc0d9d9c0453e407eadaeb4c12e5
ms.sourcegitcommit: c10eb675da725830e9776d2a0566ba3622eb361c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980065"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>了解 Microsoft 365 中的信息障碍

Microsoft 云服务包括强大的通信和协作功能。 但是，假设您要限制两个组之间的通信和协作，以避免在组织中发生利益冲突。 或者，您可能要限制组织内部某些人员之间的通信和协作，以保护内部信息。 Microsoft 365 支持跨组和组织的通信和协作，因此是否在必要时限制特定用户组之间的通信和协作？ 在信息屏障中，你可以！

Microsoft Teams、SharePoint Online 和 OneDrive for Business 支持信息屏障。 假定你的 [订阅](#required-licenses-and-permissions) 包含信息屏障，合规性管理员或信息屏障管理员可以定义策略以允许或阻止 Microsoft Teams 中的用户组之间的通信。 信息屏障策略可用于以下情况：

- 一天中工作组中的用户不应与营销团队通信或共享文件
- 处理机密公司信息的财务人员不应与组织内的某些组通信或共享文件
- 具有商业机密材料的内部团队不应与组织内某些组的人在线通话或聊天
- 研究团队应仅与产品开发团队在线通话或聊天

> [!IMPORTANT]
> 信息屏障 ***仅支持** _ 双向限制。 单向限制（如营销）可以与日交易者通信，但日交易者无法与营销 _*_进行通信不受支持_**。

对于上述所有示例方案 (更多) ，可以定义信息屏障策略来阻止或允许 Microsoft Teams 中的通信。 此类策略可以阻止用户呼叫或与不应联系的人聊天，或者使用户仅与 Microsoft Teams 中的特定组进行通信。 在信息屏障策略生效后，只要这些策略覆盖的用户尝试与 Microsoft Teams 中的其他人通信，就会进行检查以防止 (或允许) 通信 (如信息屏障策略) 。 若要了解有关具有信息障碍的用户体验详细信息，请参阅 Microsoft [Teams 中的信息屏障](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。

> [!IMPORTANT]
> 目前，信息屏障不适用于电子邮件通信。 此外，信息屏障独立于合规性 [边界](set-up-compliance-boundaries.md)。<p> 在定义和应用信息屏障策略之前，请确保您的组织没有 [生效的 Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) 通讯簿策略。  (信息屏障基于通讯簿策略。) 

## <a name="what-happens-with-information-barriers"></a>信息屏障会发生什么情况

当信息屏障策略到位时，不应与其他特定用户通信或共享文件的用户将无法查找、选择、聊天或呼叫这些用户。 在信息屏障下，将进行检查以防止未经授权的通信。

最初，信息屏障仅适用于 Microsoft Teams 聊天和频道。 在 Microsoft Teams 中，信息屏障策略确定并阻止以下类型的未经授权的通信：

- 搜索用户
- 向团队添加成员
- 开始与某人的聊天会话
- 启动群聊
- 邀请某人加入会议
- 共享屏幕
- 发出呼叫
- 与其他用户共享文件
- 通过共享链接访问文件

如果参与人员包含在信息屏障策略中以阻止活动，他们将不能继续。 此外，可能阻止信息屏障策略中包含的每个人与 Microsoft Teams 中的其他人通信。 当受信息屏障策略影响的人属于同一团队或群组聊天时，他们可能会从这些聊天会话中删除，并且可能不允许与组进一步通信。

若要了解有关具有信息障碍的用户体验详细信息，请参阅 Microsoft [Teams 中的信息屏障](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。

## <a name="required-licenses-and-permissions"></a>所需的许可证和权限

信息屏障现已推出，并包含在订阅中，例如：

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Office 365 高级合规版
- Microsoft 365 合规性 E5/A5
- Microsoft 365 内部风险管理

有关详细信息，请参阅 [Microsoft 365 安全与合规&指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。

若要 [定义或编辑信息屏障策略](information-barriers-policies.md)，必须分配有以下角色之一：

- Microsoft 365 全局管理员
- Office 365 全局管理员
- 合规性管理员
- IBM 合规性管理

 (详细了解角色和权限，请参阅 [Office 365](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)安全与合规中心&中的权限) 

您必须熟悉 PowerShell cmdlet，才能定义、验证或编辑信息屏障策略。 尽管我们在操作方法文章中提供了 PowerShell cmdlet[](information-barriers-policies.md)的几个示例，但您需要了解组织的其他详细信息（如参数）。

## <a name="next-steps"></a>后续步骤

- [了解有关 Microsoft Teams 中信息屏障的信息详细信息](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [查看可用于信息屏障策略的属性](information-barriers-attributes.md)
- [定义信息屏障策略](information-barriers-policies.md)
- [编辑 (或删除) 信息屏障策略](information-barriers-edit-segments-policies.md)
- [了解有关 SharePoint Online 中信息屏障的信息详细信息](https://docs.microsoft.com/sharepoint/information-barriers)
- [了解有关 OneDrive for Business 中信息屏障的信息详细信息](https://docs.microsoft.com/onedrive/information-barriers)