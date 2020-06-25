---
title: 了解用于自动保留或删除内容的保留策略
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解如何使用保留策略来保留或删除内容，以及如何将单个策略应用于整个组织或特定位置或用户。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ffd7b644f33e7f432c62c182e2d69e07c8bce730
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818922"
---
# <a name="learn-about-retention-policies"></a>了解有关保留策略的信息

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:
  
- **主动遵守规定至少必须在一段时间内保留内容的行业法规和内部策略**：例如，《萨班斯-奥克斯利法案》规定，必须保留特定类型的内容七年。 
    
- **降低发生诉讼或出现安全漏洞的风险**：通过永久删除不再需要保留的旧内容。 
    
- **帮助组织有效共享知识并提高敏捷性**：通过确保用户仅处理与自己相关的最新内容。 
    
A retention policy can help you achieve all of these goals. Managing content commonly requires two actions:
  
- **保留**内容，这样除非保留期到期，否则无法永久删除内容。 
    
- 在保留期到期时永久**删除**内容。 
    
借助保留策略，你可以：
  
- 主动决定是保留内容还是删除内容 — 亦或是先保留再删除内容。
    
- 将一个策略应用于整个组织，或应用于特定位置或用户。
    
- 将策略应用于所有内容，或满足特定条件（如包含特定关键字或[特定类型的敏感信息](what-the-sensitive-information-types-look-for.md)）的内容。
    
When content is subject to a retention policy, people can continue to edit and work with the content as if nothing's changed. The content is retained in place, in its original location. But if someone edits or deletes content that's subject to the retention policy, a copy of the original content is saved to a secure location where it's retained while the retention policy for that content is in effect. For more information, see the [How a retention policy works with content in place](#how-a-retention-policy-works-with-content-in-place) section on this page
  
最后，某些组织可能需要遵从特定规则，如美国证券交易委员会 (SEC) 规则 17a-4。 这要求在某个保留策略启用后，不得关闭该策略或减少限制。 为满足这一要求，你可以使用**保留锁定**。 锁定某个保留策略后，包括管理员在内的任何人都无法关闭该策略或减少其限制。 有关详细信息，请参阅此页面上的[使用保留锁定遵从合规性要求](#use-preservation-lock-to-comply-with-regulatory-requirements)部分。

## <a name="how-a-retention-policy-works-with-content-in-place"></a>保留策略如何处理留在原处的内容

将某个位置（例如网站或邮箱）包含在保留策略中时，相关内容仍保留在原处。 用户可以继续使用其文档或邮件，就像没有发生任何变动一样。 但是，如果用户编辑或删除了保留策略中包含的内容，则会保留应用策略时的内容的副本。
  
- 对于 SharePoint 和 OneDrive 网站：副本保留在**保存保留**库中。 请注意，保存保留库将占用网站的存储配额。

- 对于电子邮件和公用文件夹：副本保留在“**可恢复的项目**”文件夹中。 

- 对于 Teams 内容：副本保留在 Exchange“**可恢复的项目**”文件夹中。

- 对于 Microsoft 365 组（[以前的 Office 365 组](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)）： 
    - 组邮箱保留在 Exchange“**可恢复的项目**”文件夹中。
    - 任何网站内容都将保留在**保存保留**库中。

> [!NOTE]
> 保存保留库占用的存储不受网站的存储配额限制。 对 SharePoint 和 Microsoft 365 组使用保留策略时，可能需要增加存储空间。
> 
这些安全位置和保留内容对大部分用户不可见。 使用保留策略后，用户甚至无需知晓已向其内容应用了该策略。

有关保留策略如何用于不同工作负载的更多详细信息，请参阅以下文章：

- [了解 SharePoint 和 OneDrive 的保留策略](retention-policies-sharepoint.md)
- [了解 Microsoft Teams 的保留策略](retention-policies-teams.md)
- [了解 Exchange 的保留策略](retention-policies-exchange.md)

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>保留原则或优先级

可能对内容应用了多个保留策略，每个策略具有不同的操作（保留、删除或先保留再删除）和保留期。 哪些内容优先？ 请放心，在最高级别中，某保留策略保留的内容不可被其他保留策略永久删除。
  
![保留原则关系图](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
若要了解不同保留策略是如何应用于内容的，请注意下面这些保留原则：
  
1. **保留优先于删除。** 如果某保留策略配置为在 3 年后删除 Exchange 电子邮件，但另一保留策略配置为将 Exchange 电子邮件保留 5 年后再删除。 达到 3 年的内容将被删除并隐藏，但仍保留在“可恢复项目”文件夹中，然后在达到 5 年后被永久删除。 
    
2. **优选最长的保留期。** 如果对内容应用了多个保留策略，它将采用最长的保留期。 
    
3. **显式包含优先于隐式包含。** 这意味着： 
    
    1. 如果具有保留设置的保留标签由用户手动分配给某项目（例如 Exchange 电子邮件或 OneDrive 文档），该保留标签优先于在站点或邮箱级别分配的保留策略以及由文档库分配的默认保留标签。 例如，如果显式保留标签配置为将内容保留 10 年，但分配给此站点的保留策略仅配置为将内容保留 5 年，则优选保留标签的保留期。 自动应用保留标签被视为隐式标签，而不是显式标签，因为它们由 Microsoft 365 自动应用。
    
    2. 如果保留策略包含特定位置（如特定用户的邮箱或 OneDrive 帐户），此保留策略优先于应用于所有用户邮箱或 OneDrive 帐户（而不是包含具体用户邮箱）的其他保留策略。
    
4. **最短删除期优先。** 同样，如果内容受多个保留策略约束（删除无保留期的内容），它将在最短保留期到期时被删除。 
    
请注意，保留原则就像是自上而下打破平局的流：如果所有保留策略或保留标签应用的规则在一个级别上是相同的，流就会向下移至下一个级别，以确定优先应用哪个规则。
  
最后一点，保留策略或保留标签不能永久删除任何保留用于电子数据展示的内容。 解除限制时，此内容将可再次用于上述清除过程。

## <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a>使用保留锁定遵从合规性要求

某些组织可能需要遵从由监管机构定义的规则，如美国证券交易委员会 (SEC) 规则 17a-4，这要求在某个保留策略启用后，不得关闭该策略或减少其限制。 

保留锁定可确保你的组织符合此类法规要求，因为它可以锁定某个保留策略，包括管理员在内的任何人都无法关闭该策略或减少其限制。
  
锁定某个保留策略后：

- 任何人都不能将其关闭
- 可以添加位置，但不能删除位置 
- 无法在保留期内修改或删除受策略制约的内容
- 可以延长保留期，但不能缩短保留期

总而言之，锁定的保留策略可以增加或扩展锁定的策略，但不能减少或关闭策略。
  
> [!IMPORTANT]
> 在锁定保留策略之前，请务必了解其影响并确定组织是否需要该策略以满足合规性要求。

## <a name="releasing-a-retention-policy"></a>解除保留策略

若保留策略没有保留锁定，则可随时关闭或删除它。 

当你这样做时，任何被保留在保留库中的 SharePoint 或 OneDrive 内容都不会立即遭永久删除。 相反，为了防止意外的数据丢失，我们设置了 30 天的宽限期。在此期间，相应策略的内容不会在保留库中到期，所以你可以根据需要从其中还原任何内容。 此外，在宽限期内无法手动删除此内容。

可在宽限期内重新启用保留策略，相应策略的任何内容都不会遭删除。

SharePoint 和 OneDrive 中的此 30 天宽限期对应于 Exchange 中的 30 天延迟保留。 有关详细信息，请参阅[管理延迟保留的邮箱](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。

## <a name="use-a-retention-policy-instead-of-older-features"></a>使用保留策略代替早期功能

可轻松将单个保留策略应用到整个组织和 Microsoft 365 中的位置，包括 Exchange Online、SharePoint Online、OneDrive 和 Microsoft 365 组。 如果需要保留或删除 Microsoft 365 中任意位置的内容，建议使用保留策略并可辅以[保留标签](labels.md)。
  
如果你以前使用过其他配置保留或删除 Microsoft 365 中的内容，它们将继续与保留策略和保留标签配合使用。 但我们建议今后使用保留策略和保留标签。 它们为你提供了在 Microsoft 365 中集中管理内容保留和删除的单一机制。

你可能使用过的早期功能有：
  
**Exchange Online 中的早期功能：**

- [就地保留和诉讼保留](https://go.microsoft.com/fwlink/?linkid=846124)（电子数据展示保留） 

- [如何识别为 Exchange Online 邮箱设置的保留类型](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- [保留标记和保留策略](https://go.microsoft.com/fwlink/?linkid=846125)，亦称为[邮件传递记录管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126)（仅限删除）
    
另请参阅[旧版电子数据展示工具的停用](legacy-ediscovery-retirement.md)。


**SharePoint 和 OneDrive 中的早期功能：**

- [在电子数据展示中心内将内容添加到案件集并保留源](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center)（电子数据展示保留） 
    
- [文档删除策略](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff)（仅删除）
    
- [配置就地记录管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a)（仅限保留） 
    
- [使用网站关闭和删除策略](https://support.microsoft.com/zh-CN/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5)（仅限删除） 
    
- [信息管理策略](intro-to-info-mgmt-policies.md)（仅限删除）
     
如果之前使用了任何电子数据展示保留进行信息管理，为实现主动合规，请改为使用保留策略。 仅对保留策略使用电子数据展示。
  
### <a name="retention-policies-and-sharepoint-content-type-policies-or-information-management-policies"></a>保留策略和 SharePoint 内容类型策略或信息管理策略

如果已将 SharePoint 网站配置为应用保留列表或库的内容的内容类型策略或信息管理策略，则这些策略会在保留策略生效时被忽略。 
  
### <a name="preservation-policies-are-converted-to-retention-policies"></a>保存策略转换为保留策略

如果之前使用保存策略保留邮箱、SharePoint 或 OneDrive 网站或公用文件夹中的数据，则保存策略已自动转换为保留策略 — 只会保留内容，而不会删除内容。 与你配置的保留策略的结果相同，无需进行任何更改。

有关配置的任何保存策略的信息，可查看 [Microsoft 365 合规中心](https://compliance.microsoft.com/)的“**策略**”页面，或者[安全&amp;合规中心](https://protection.office.com/)内“**信息管理**”下的“**保留**”页面。 可以编辑保存策略，以更改保存期限，但是无法进行添加或移动位置等其他更改。 


## <a name="related-information"></a>相关信息

- [了解保留标签](labels.md)
- [SharePoint Online 限制](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Microsoft Teams 的限制和规范](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [符合 SEC 规则 17a-4](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## <a name="next-steps"></a>后续步骤

如果已准备好创建保留策略，请参阅[创建和配置保留策略](create-retention-policies.md)。

