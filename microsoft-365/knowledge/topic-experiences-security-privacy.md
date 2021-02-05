---
title: Microsoft Viva 主题安全和隐私
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: 了解如何规划 Microsoft Viva 主题安全和隐私
ms.openlocfilehash: be5be01bce117a80bd95ee268c193889eccea67f
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107788"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a>Microsoft Viva 主题安全和隐私

主题使用 Microsoft 365 中的现有内容安全功能以及管理控件来控制向组织中用户显示哪些 AI 生成的内容。 它是 Microsoft 365 安全设置和 (网站、文件和文件夹的权限) 主题管理员设置的组合，用于确定给定用户可以在主题中看到的内容。

设置主题不会修改组织中内容的任何现有访问控制。 用户只会看到他们已有权访问哪些内容。

本文从安全角度介绍了主题的工作方式，以及知识管理员和知识管理员控制主题可见性时必须选择的选项。 阅读本文作为规划主题 [的一部分](plan-topic-experiences.md)。

在阅读本文之前，[](topic-experiences-overview.md)您应熟悉主题是什么、主题[中心](topic-center-overview.md)以及如何使用主题中心[](manage-topics.md)中的主题。

## <a name="what-users-can-see-in-topics"></a>用户可以在主题中查看哪些内容

若要查看主题，用户必须：

- 拥有 Viva 主题许可证
- 成为 [主题查看器](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization)、 [参与者或知识管理员](topic-experiences-user-permissions.md)

通过这两项操作，用户可以查看主题中心的访问权限，并允许他们查看突出显示和主题卡片。

此外，主题参与者 [还具有](topic-experiences-user-permissions.md) 主题的创建和编辑权限，并且知识管理员可以确认或删除主题。

首次发现主题时，知识管理人员可以在主题中心看到它。 根据主题的完整性和相关性，主题查看者可能会或可能不会看到主题卡片中提供的主题。

主题可以包含 AI 生成的信息以及主题参与者或知识管理员添加或编辑的信息。

- AI 添加的主题中的信息仅对有权访问源内容的人可见。
- 主题参与者或知识管理员手动添加或编辑的文本对可以看到该主题的每个人可见。

主题查看者和参与者可以在主题中心查看已确认和已发布主题的列表，但给定人员可以看到的主题详细信息取决于他们对源材料的权限以及主题是否已手动编辑。

下表介绍了基于用户的权限在给定主题中可以看到哪些用户（主题查看者、参与者和知识管理员）。

|主题项|用户可以看到哪些内容|
|:---------|:------------------|
|主题名称|用户可以在主题中心查看所有主题的主题名称。 如果某些主题与用户的相关性较低，则这些主题可能不可见。|
|主题说明|AI 生成的说明仅对对源内容具有权限的用户可见。 手动输入或编辑的说明对所有用户都可见。|
|人员|固定人员对所有用户可见。 建议的用户仅对具有源内容权限的用户可见。|
|文件|文件仅对具有源内容权限的用户可见。|
|页面|只有对源内容具有权限的用户才能看到页面。|
|网站|网站仅对具有源内容权限的用户可见。|

## <a name="best-practices"></a>最佳做法

主题根据用户对内容的现有权限向用户显示信息。 Microsoft 365 提供了多种方式来确保敏感内容仅限于适当的用户。 除了标准团队权限或网站权限外，您还可以使用敏感度标签或数据丢失[](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)防护来限制对内容和访问评审的访问，[](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)以定期检查用户对敏感信息的访问。 [](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)

建议您使用这些工具来确保在组织内部正确设置内容权限。 然后，主题体验可以为用户提供有用且合适的信息。

如果你希望从主题体验中完全排除某些主题，则还可以：

- [从主题发现中排除敏感 SharePoint 网站](topic-experiences-discovery.md#select-sharepoint-topic-sources)。 这些网站中的内容不会显示在主题体验中。

- [按名称排除主题](topic-experiences-discovery.md#exclude-topics-by-name)。 明确排除的主题不会显示在主题体验中。

- 使知识经理删除主题中心中的主题。

此外，我们建议采用以下最佳实践：

- 从组织的不同区域招募知识经理。 让知识经理具有各种专业知识（以及访问 AI 使用的基础内容）可以帮助你为用户选择最有用的知识，并删除敏感信息（如果找到）。

- 设置用于请求更改的工作流。 知识管理员或团队或网站所有者应具有一个流程，通过此过程，他们可以请求在组织中启动新项目时排除主题或网站，或者当他们发现内容具有不当权限设置时。

- 在创建主题说明时，请注意访问群体和信息敏感度。 这些说明对于没有主题源内容权限的用户可能可见。

虽然您可以更改单个主题页面上的权限以缩小对特定组用户的访问范围，但我们不建议使用这种方法，因为需要执行很高的管理工作。

## <a name="see-also"></a>另请参阅

[配置具有三层保护的 Teams](../solutions/configure-teams-three-tiers-protection.md)

[计划主题体验](plan-topic-experiences.md)

[设置主题体验](set-up-topic-experiences.md)
