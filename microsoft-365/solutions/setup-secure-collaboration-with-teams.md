---
title: 使用 Microsoft 365 建立安全协作
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: 了解如何在 Teams 中设置安全内容协作，以基于数据的敏感度保护数据。
ms.openlocfilehash: c92dc6dbf62d3fa0cb00307447b3d5a793830394
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233852"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>使用 Microsoft 365 建立安全协作

能够与合适的人员轻松共享信息，同时防止过度共享是组织取得成功的关键。 这包括能够仅与应有权访问敏感数据的人安全地共享敏感数据。 根据项目的不同，这可能包括与组织外部人员共享敏感数据。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

此协作解决方案指南包括两个可帮助你的组件：
- 为每个项目部署具有正确保护级别的 Microsoft Teams
- 使用每个项目的适当安全设置配置外部共享

![部署具有适当保护的 Teams，并配置具有适当安全设置的外部共享](..\media\solutions-architecture-center\secure-collaboration-overview.png)

如果通用且易于使用的内容协作工具不可用，用户通常通过电子邮件进行协作。 这是一种繁琐且容易出错的协作方法，并且会增加信息共享不当的风险。 如果用户发现共享信息太困难，他们可能会恢复为使用不受 IT 监管的消费者产品。 这会带来更大的风险。

借助 Microsoft 365，可以使用各种配置部署 Teams，帮助：

- 保护知识产权
- 实现轻松协作
- 在安全性和可用性之间实现平衡，提高用户满意度并降低卷影 IT 的风险

大多数组织都有各种信息，如果信息共享不当，则其敏感度和业务影响程度各不相同。 根据给定信息的敏感度，您可能需要允许与以下项共享：

- 任何 (未经身份验证) 
- 组织内部人员
- 组织内部的特定人员
- 组织内外的特定人员

营销简介等信息旨在广泛在组织外部共享。 菜单等信息不用于外部共享，但如果在外部共享，则不会影响业务。 这些类型的信息几乎不需要保护或不需要保护。

这些相同的营销手册在开发期间可能只能在组织内部共享。 在这种情况下，Teams 中的默认共享设置可能就足够了。

有关正在开发中的新产品的信息可能被视为敏感，即使在组织内部。 在这种情况下，可能适合使用更大程度的保护。 例如，您可以限制特定团队成员对此信息的访问。 根据项目的不同，您可能需要与组织外部人员（如供应商或合作伙伴组织）进行协作。

对于对组织的成功至关重要的信息，或者具有严格的安全或合规性要求的信息，可能需要更高级别的保护。

![风险范围从低 (发行) 高 (敏感业务数据) ](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

对于上述所有方案，可以使用 Microsoft Teams 中的团队来存储、共享和协作处理信息。 

若要配置安全协作，请使用这些 Microsoft 365 功能和特性。

| 产品或组件 | 功能或特性 | 许可 |
|:-------|:-----|:-------|
| Microsoft Defender for Office 365 | SPO、OneDrive 和 Teams 的安全附件;安全文档;Teams 的安全链接    | Microsoft 365 E1、E3 和 E5 |
| SharePoint    | 网站和文件共享策略、网站共享权限、共享链接、访问请求、网站来宾共享设置 | Microsoft 365 E1、E3 和 E5 |
| Microsoft Teams   | 来宾访问、私人团队、私人频道 | Microsoft 365 E1、E3 和 E5 |
| Microsoft 365 合规中心  | 敏感度标签    | Microsoft 365 E3 和 E5 |

### <a name="using-teams-for-all-kinds-of-data"></a>对所有类型的数据使用 Teams

为了管理对不同敏感信息的访问，我们已为 Teams 开发了三个不同的 [保护层](configure-teams-three-tiers-protection.md)。 您可以自定义这些层中的任意一个，以更好地满足需求或业务。 

![Teams 逻辑体系结构海报缩略图](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


这些层（*基线*、敏感和 *高度敏感*）逐渐增加保护，以帮助防止过度共享和潜在信息泄露，如下表所示。

|-|**基线层**|**敏感层**|**高度敏感的层**|
|:--|:-----------|:------------|:-------------------|
|公共团队或私人团队|两者皆可|Private|Private|
|未经身份验证的共享|Blocked|Blocked|Blocked|
|文件共享|允许|允许|只有团队所有者才能共享。|
|团队成员身份|任何人都可以加入公共团队。<br>加入私人团队需要团队所有者批准。|需要团队所有者批准才能加入。|需要团队所有者批准才能加入。|
|文档加密|||与敏感度标签一起提供|
|来宾共享|允许|允许或阻止|允许或阻止|
|非托管设备|无限制|仅 Web 访问|Blocked|

配置这些层涉及：

- 在 Teams 中配置来宾访问和专用频道的设置
- 在团队的关联 SharePoint 网站中为内部共享和来宾共享、访问请求和共享链接配置设置
- 对于 *敏感和**高度敏感的* 层，配置敏感度标签以对团队进行分类，并控制来宾共享和从非托管设备访问
- 对于 *高度敏感的* 层，配置敏感度标签以加密应用它的文档

从基线层开始，然后根据需要添加使用敏感和 *高度敏感* 层以帮助保护组织中信息的团队。  请参阅以下资源开始：

- [配置具有基线保护的团队](configure-teams-baseline-protection.md)
- [配置具有敏感数据保护的团队](configure-teams-sensitive-protection.md)
- [配置具有高度敏感数据保护的团队](configure-teams-highly-sensitive-protection.md)

如果您的高度敏感项目需要额外保护，甚至无需在组织内部共享，您可以配置一个使用自己的敏感度标签对文件进行加密的团队，以便只有团队成员才能读取这些文件。 有关详细信息 [，请参阅配置具有安全隔离](secure-teams-security-isolation.md) 的团队。

### <a name="sharing-with-people-outside-your-organization"></a>与组织外部人员共享

你可能需要 [与组织外部人员共享任何敏感度的信息](collaborate-with-people-outside-your-organization.md)。 这可能包括与单个人员共享单个文档，到与大型合作伙伴组织或世界各地的供应商协作处理主要项目。 在 Microsoft 365 中，可以轻松完成此范围的外部共享，并提供适当的安全措施来帮助保护敏感信息。

这些资源将帮助您开始设置环境以与组织外部人员协作：

- [协作处理文档](collaborate-on-documents.md) 以共享文件夹的单个文件。
- [在网站中协作](collaborate-in-site.md) 以与 SharePoint 网站中的来宾协作。
- [作为团队进行协作](collaborate-as-team.md) ，与团队中的来宾协作。

根据共享信息的敏感度，您可以添加安全措施以帮助防止过度共享。 这些资源将帮助您设置组织所需的保护：

- [有关与未经认证用户共享文件和文件夹的最佳做法](best-practices-anonymous-sharing.md)
- [在与组织外人员共享文件时限制意外公开信息](share-limit-accidental-exposure.md)
- [创建安全的来宾共享环境](create-secure-guest-sharing-environment.md)

如果你有合作伙伴组织的主要项目，可以使用 Azure 权利管理来管理为该项目设置的团队中的来自该组织的来宾。 有关详细信息[，请参阅创建包含托管来宾的 B2B Extranet。](b2b-extranet.md)

## <a name="deploy-the-secure-collaboration-solution"></a>部署安全协作解决方案

准备好部署此解决方案后，继续执行以下步骤：
1. 配置 [Teams 的三种不同保护层](configure-teams-three-tiers-protection.md)。
2. 配置用于 [与组织外部人员共享任何敏感度信息的设置](collaborate-with-people-outside-your-organization.md)。

## <a name="see-also"></a>另请参阅

[Microsoft 365 安全中心文档](https://docs.microsoft.com/microsoft-365/security)

[Microsoft 365 合规性文档](https://docs.microsoft.com/microsoft-365/compliance)

[欢迎使用 Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
