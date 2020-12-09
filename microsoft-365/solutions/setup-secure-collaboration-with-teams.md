---
title: 与 Microsoft 365 建立安全协作
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
description: 了解如何在团队中设置安全内容协作，以根据数据敏感度保护您的数据。
ms.openlocfilehash: 4f2e157025f00660e77ba3377221368e37e45445
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602069"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>与 Microsoft 365 建立安全协作

能够在阻止 oversharing 的情况下轻松地与适当的人共享信息是组织成功的关键。 这包括能够安全地与仅有权访问的人共享敏感数据。 这可能包括与组织外部的人员共享敏感数据，具体取决于项目。

此协作解决方案指南包括两个组件，可帮助您执行以下操作：
- 部署具有针对每个项目的适当级别保护的 Microsoft 团队
- 为每个项目配置具有适当安全设置的外部共享

![使用适当的安全设置来部署具有适当保护的团队并配置外部共享](..\media\solutions-architecture-center\secure-collaboration-overview.png)

如果功能丰富且易于使用的内容协作工具不可用，则用户通常会通过电子邮件进行协作。 这是一种单调乏味且容易出错的协作方法，并且可能会增加不适当共享信息的风险。 如果人员发现共享信息过于困难，他们可以使用不受 IT 管理的消费者产品回复。 这可能会带来更大的风险。

使用 Microsoft 365，可以部署具有多种配置的团队，以帮助：

- 保护您的知识产权
- 实现轻松协作
- 在安全性和可用性之间建立平衡，以提高用户满意度并降低阴影风险

如果信息不恰当地共享，大多数组织都有各种信息，并且敏感程度各不相同，并且业务影响也各不相同。 根据给定信息的敏感度，您可能希望允许与以下内容共享：

-  (未经身份验证的任何人) 
- 组织内部的人员
- 组织内的特定人员
- 组织内部和外部的特定人员

市场营销手册等信息适用于组织外部的共享。 诸如 "自助" 的信息不是为了外部共享，而是在外部共享时不会对业务产生影响。 这些类型的信息需要很少或无保护。

在开发过程中，这些相同的营销手册只能在组织内部共享。 在这种情况下，团队中的默认共享设置可能足够。

有关正在开发的新产品的信息可能被视为敏感，即使在组织内也是如此。 在这种情况下，可能需要更大程度的保护。 例如，您可以将对此信息的访问限制为特定团队的成员。 根据项目，您可能需要与组织外部的人员（如供应商或合作伙伴组织）进行协作。

对组织成功或具有严格的安全性或合规性要求至关重要的信息可能需要更高级别的保护。

![从低 (发布的小册子) 到高 (敏感业务数据的风险范围) ](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

对于以上所述的所有情况，可以使用 Microsoft 团队中的团队来存储、共享和协作处理信息。 

若要配置安全协作，请使用以下 Microsoft 365 功能和功能。

| 产品或组件 | 功能或特性 | 许可 |
|:-------|:-----|:-------|
| Microsoft Defender for Office 365 | SPO、OneDrive 和团队的安全附件;安全文档;团队的安全链接    | Microsoft 365 E1、E3 和 E5 |
| SharePoint    | 网站和文件共享策略、网站共享权限、共享链接、访问请求、网站来宾共享设置 | Microsoft 365 E1、E3 和 E5 |
| Microsoft Teams   | 来宾访问、专用团队、专用频道 | Microsoft 365 E1、E3 和 E5 |
| Microsoft 365 合规中心  | 敏感度标签    | Microsoft 365 E3 和 E5 |

### <a name="using-teams-for-all-kinds-of-data"></a>对所有类型的数据使用团队

若要使用不同的 sensitivities 管理对信息的访问，我们 [为团队开发了三个不同的保护层](configure-teams-three-tiers-protection.md)。 您可以自定义这些层中的任何一个，以更好地满足需求或业务。 

![Teams 逻辑体系结构海报缩略图](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


这些分层- *比较基准*、 *敏感* 和 *高度敏感* 信息-逐渐提高有助于防止 oversharing 和潜在信息泄露的保护，如下表所示。

|-|**基线层**|**敏感层**|**高度敏感的层**|
|:--|:-----------|:------------|:-------------------|
|公共或专用团队|两者皆可|Private|Private|
|未经身份验证的共享|Blocked|Blocked|Blocked|
|文件共享|允许|允许|仅工作组所有者可以共享。|
|团队成员资格|任何人都可以加入公共团队。<br>需要团队所有者批准才能加入私有团队。|需要团队所有者批准才能加入。|需要团队所有者批准才能加入。|
|文档加密|||可使用敏感度标签|
|来宾共享|允许|可以允许或阻止|可以允许或阻止|
|非托管设备|无限制|仅 Web 访问|Blocked|

配置这些层涉及：

- 为来宾访问和专用频道配置团队中的设置
- 在团队关联的 SharePoint 网站中配置用于内部和来宾共享、访问请求和共享链接的设置
- 对于 *敏感* 和 *高度敏感* 的层，配置敏感度标签以对团队进行分类，并控制非托管设备的来宾共享和访问
- 对于 *高度敏感* 的层，配置敏感度标签以加密应用它的文档

从基线层开始，然后根据需要添加使用 *敏感* 和 *高度敏感* 的团队，以帮助保护组织中的信息。 若要开始，请参阅以下资源：

- [配置具有基线保护的团队](configure-teams-baseline-protection.md)
- [配置具有敏感数据保护的团队](configure-teams-sensitive-protection.md)
- [配置具有高度敏感数据保护的团队](configure-teams-highly-sensitive-protection.md)

如果您有一个高度敏感的项目，该项目需要在组织内进行额外的共享保护，则可以将使用其自己的敏感度标签的团队配置为加密文件，以便只有工作组成员可以读取这些文件。 有关详细信息，请参阅 [Configure a team with security 隔离](secure-teams-security-isolation.md) 。

### <a name="sharing-with-people-outside-your-organization"></a>与组织外部的人员共享

您可能需要 [与组织外部的人员共享任何敏感度的信息](collaborate-with-people-outside-your-organization.md)。 这可能包括与单个用户共享单个文档，以便在大型合作伙伴组织或来自世界各地的兼职翻译的主要项目上进行协作。 在 Microsoft 365 中，可以轻松地完成这一范围的外部共享，并提供适当的保护措施来帮助保护您的敏感信息。

这些资源将帮助您开始设置您的环境，以便与组织外部的人员进行协作：

- [对文档进行协作](collaborate-on-documents.md) ，以共享文件夹的各个文件。
- [在网站](collaborate-in-site.md) 中进行协作，以便与 SharePoint 网站中的来宾进行协作。
- [作为团队协作](collaborate-as-team.md) 处理团队中的来宾。

根据所共享的信息的敏感度，您可以添加安全措施来帮助防止 oversharing。 这些资源将帮助您设置您的组织所需的保护：

- [有关与未经认证用户共享文件和文件夹的最佳做法](best-practices-anonymous-sharing.md)
- [在与组织外人员共享文件时限制意外公开信息](share-limit-accidental-exposure.md)
- [创建安全的来宾共享环境](create-secure-guest-sharing-environment.md)

如果您有一个包含合作伙伴组织的主要项目，您可以使用 Azure 权利管理在您为项目设置的团队中管理来自该组织的来宾。 有关详细信息，请参阅 [Create a B2B extranet with 托管来宾](b2b-extranet.md) 。

## <a name="deploy-the-secure-collaboration-solution"></a>部署安全协作解决方案

当您准备好部署此解决方案时，请继续执行以下步骤：
1. [为团队配置三个不同的保护层](configure-teams-three-tiers-protection.md)。
2. 配置 [与组织外部人员共享任何敏感度的信息](collaborate-with-people-outside-your-organization.md)的设置。

## <a name="see-also"></a>另请参阅

[Microsoft 365 安全中心文档](https://docs.microsoft.com/microsoft-365/security)

[Microsoft 365 合规性文档](https://docs.microsoft.com/microsoft-365/compliance)

[欢迎使用 Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
