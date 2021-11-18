---
title: 了解信息障碍Microsoft 365
description: 使用信息屏障来确保使用组织中Microsoft Teams通信合规性。
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
ms.localizationpriority: ''
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 515983182bb5f44c08e7d8531656a7a4fb49d5c6
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2021
ms.locfileid: "61064096"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>了解信息障碍Microsoft 365

Microsoft 云服务包括强大的通信和协作能力。 但是，假设您要限制两个组之间的通信和协作，以避免您的组织中出现利益冲突。 或者，您可能要限制组织内部的某些人员之间的通信和协作，以保护内部信息。 Microsoft 365组和组织之间的通信和协作，那么是否在必要时限制特定用户组之间的通信和协作？ 在信息障碍下，你可以！

Microsoft Teams、SharePoint Online 和 OneDrive for Business 支持信息屏障。 假设您[的订阅](#required-licenses-and-permissions)包含信息屏障，合规性管理员或信息屏障管理员可以定义策略，以允许或阻止 Microsoft Teams 中的用户组之间的通信。 信息屏障策略可用于类似以下的情况：

- 日常分组中的用户不应与营销团队通信或共享文件
- 处理机密公司信息的财务人员不应与组织内的某些组通信或共享文件
- 具有商业机密材料的内部团队不应在线呼叫或与组织中某些组的人聊天
- 研究团队只能与产品开发团队在线通话或聊天
- 一天中每天的分组网站不应由日用组外的任何用户共享或访问

> [!IMPORTANT]
> 信息屏障 ***仅支持** _ 双向限制。 单向限制（如营销）可以与日交易者通信和协作，但日交易者无法与营销 _* 进行通信 _和协作不受_ 支持 **。

对于上述所有示例方案 (和更多) ，可以定义信息屏障策略来阻止或允许 Microsoft Teams、SharePoint Online 和 OneDrive 中的通信和协作。 此类策略可以阻止用户呼叫或与不应联系的组聊天，或者使用户仅与用户中的特定组Microsoft Teams。 在信息屏障策略生效后，只要这些策略覆盖的用户尝试与 Microsoft Teams、SharePoint Online 或 OneDrive 中的其他人进行通信和协作，就会执行检查以防止 (或允许) 通信和协作 (如信息屏障策略) 所定义。

若要了解有关具有信息障碍的用户体验详细信息，请参阅：

- [Microsoft Teams 中的信息屏障](/MicrosoftTeams/information-barriers-in-teams)
- [SharePoint Online 中的信息障碍](/sharepoint/information-barriers)
- [信息障碍OneDrive](/onedrive/information-barriers)

> [!IMPORTANT]
> 目前，信息屏障不适用于电子邮件通信。 此外，信息屏障独立于合规性 [边界](set-up-compliance-boundaries.md)。<p> 定义和应用信息屏障策略之前，请确保您的组织没有Exchange[通讯簿](/exchange/address-books/address-book-policies/address-book-policies)策略。  (信息屏障基于通讯簿策略。) 

## <a name="what-happens-with-information-barriers"></a>信息屏障会发生什么情况

当信息屏障策略到位时，不应与其他特定用户通信或共享文件的用户将无法查找、选择、聊天或呼叫这些用户。 由于信息障碍，我们进行检查以防止未经授权的通信和协作。

信息屏障适用于Microsoft Teams (、) 、SharePoint Online 和 OneDrive。 在 Microsoft Teams 中，信息屏障策略确定并阻止以下类型的未经授权的通信：

- 搜索用户
- 向团队添加成员
- 启动与某人的聊天会话
- 启动群组聊天
- 邀请其他人加入会议
- 共享屏幕
- 发出呼叫
- 与其他用户共享文件
- 通过共享链接访问文件

如果将相关人员纳入信息屏障策略以防止该活动，则他们将无法继续操作。 此外，可能阻止信息屏障策略中包含的每个人与 Microsoft Teams 中的其他人通信。 当受信息屏障策略影响的人属于同一个团队或群组聊天时，可能会从这些聊天会话中删除他们，并且可能不允许他们与该组进一步沟通。

若要了解有关具有信息障碍的用户体验详细信息[，请参阅](/MicrosoftTeams/information-barriers-in-teams)Microsoft Teams。

在 SharePoint Online 和 OneDrive 中，信息屏障策略可确定并阻止以下类型的未经授权的协作：

- 向网站添加成员
- 用户访问网站或内容
- 与其他用户共享网站或内容
- 搜索网站

若要了解有关具有信息障碍的用户体验详细信息，请参阅 SharePoint [Online 中的信息障碍](/sharepoint/information-barriers)

## <a name="required-licenses-and-permissions"></a>所需的许可证和权限

在开始内部风险管理之前，你应该确认你的Microsoft 365[订阅](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)和任何加载项。 若要访问和使用信息屏障，你的组织必须具有以下订阅或加载项之一：

- Microsoft 365 E5/A5 订阅 (付费或试用版) 
- Office 365 企业版 E5 订阅（付费或试用版本）
- Office 365 A5 订阅（付费或试用版本）
- Office 365 高级合规版加载项 (不再可用于新订阅) 
- Microsoft 365 E3/A3 订阅 + Microsoft 365 E5/A5 合规性加载项
- Microsoft 365 E3/A3 订阅 + Microsoft 365 E5/A5 内部风险管理加载项

有关详细信息，请参阅Microsoft 365安全[与合规&指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。

若要 [定义或编辑信息屏障策略](information-barriers-policies.md)，必须分配有以下角色之一：

- Microsoft 365 全局管理员
- Office 365 全局管理员
- 合规性管理员
- IB 合规性管理

 (若要了解有关角色和权限的更多信息，请参阅安全与合规Office 365中心[&中的权限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)) 

您必须熟悉 PowerShell cmdlet，才能定义、验证或编辑信息屏障策略。 尽管我们在操作方法文章中提供了 PowerShell cmdlet[](information-barriers-policies.md)的几个示例，但您需要了解组织的其他详细信息（如参数）。

## <a name="next-steps"></a>后续步骤

- [详细了解信息障碍Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [详细了解 SharePoint Online 中的信息障碍](/sharepoint/information-barriers)
- [详细了解信息障碍OneDrive](/onedrive/information-barriers)
- [查看可用于信息屏障策略的属性](information-barriers-attributes.md)
- [定义信息屏障策略](information-barriers-policies.md)
- [编辑（删除）信息屏障策略](information-barriers-edit-segments-policies.md)
