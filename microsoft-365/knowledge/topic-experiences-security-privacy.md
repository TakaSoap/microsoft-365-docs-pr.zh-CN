---
title: 安全与隐私主题Microsoft Viva主题
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
ms.localizationpriority: medium
description: 了解如何在"主题"中规划Microsoft Viva隐私。
ms.openlocfilehash: 4b0c94244badab9aa7e294b04b20b09149ead3b7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168430"
---
# <a name="security-and-privacy-in-microsoft-viva-topics"></a>安全与隐私主题Microsoft Viva主题

主题使用组织中现有的内容安全功能Microsoft 365管理控件，以控制向组织用户显示哪些 AI 生成的内容。 它是网站Microsoft 365安全设置 (网站、文件和文件夹) 和主题管理员设置的组合，确定给定用户可以在主题中看到的内容。

设置主题不会修改组织中对于内容的任何现有访问控制。 用户将只能查看有权访问的内容。

本文介绍主题从安全角度的工作方式，以及知识管理员和知识管理员控制主题可见性时必须选择的选项。 阅读本文作为规划主题 [的一部分](plan-topic-experiences.md)。

在阅读[本文之前，](topic-experiences-overview.md)您应熟悉什么是主题、[](topic-center-overview.md)主题中心，以及如何使用主题[](manage-topics.md)中心中的主题。

## <a name="what-users-can-see-in-topics"></a>用户可以在主题中查看哪些内容

若要查看主题，用户必须：

- 拥有 Viva 主题许可证
- 成为主题 [查看器](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization)、 [参与者或知识管理员](topic-experiences-user-permissions.md)

这两项内容使用户能够查看对主题中心的访问权限，并允许用户查看突出显示和主题卡片。

主题参与者还 [具有主题的](topic-experiences-user-permissions.md) 创建和编辑权限，并且知识管理人员可以确认或删除主题。

首次发现主题时，知识管理人员可以在主题中心看到它。 根据主题的完整性和相关性，主题查看者可能会或可能不会看到主题卡片中提供的主题。

主题可以包含 AI 生成的信息以及由主题参与者或知识管理员添加或编辑的信息。

- 主题中由 AI 添加的信息仅对具有对该源内容访问权限的人员可见。
- 主题参与者或知识管理员手动添加或编辑的文本对可以看到该主题的每个人可见。

主题查看者和参与者可以在主题中心查看已确认和已发布主题的列表，但给定人员可以看到的主题详细信息取决于他们对源材料拥有的权限以及主题是否已手动编辑。

下表介绍了哪些用户（主题查看者、参与者和知识管理员）可以基于其权限在给定主题中查看。

|主题项|用户可以看到的内容|
|:---------|:------------------|
|主题名称|用户可以在主题中心查看主题的主题名称。 如果用户对源内容没有权限或与用户相关性较低，则某些主题可能不可见。|
|主题描述|AI 生成的描述仅对具有源内容权限的用户可见。 手动输入或编辑的描述对所有用户可见。|
|人员|固定的人员对所有用户可见。 建议的人员仅对具有源内容权限的用户可见。|
|文件|文件仅对具有源内容权限的用户可见。|
|页面|页面仅对具有源内容权限的用户可见。|
|网站|网站仅对具有源内容权限的用户可见。|

## <a name="users-personal-and-private-data"></a>用户的个人数据和私有数据

Viva 主题仅发现您SharePoint网站中的主题。 不包括用户的个人存储，如OneDrive邮件或邮件。

## <a name="best-practices"></a>最佳做法

主题根据用户现有的内容权限向用户显示信息。 Microsoft 365提供了多种方式来确保敏感内容仅限于适当的用户。 除了标准团队或网站权限之外，您还可以使用敏感度标签或数据丢失防护[](../compliance/dlp-learn-about-dlp.md)来限制对内容和访问评审的访问，以[](/azure/active-directory/governance/access-reviews-overview)定期检查用户对敏感信息的访问。 [](../compliance/sensitivity-labels.md)

建议您使用这些工具来确保在组织内部正确设置内容权限。 然后，主题体验可以为用户提供有用的适当信息。

如果要将主题完全从主题体验中排除，还可以：

- [从主题SharePoint排除敏感网站](topic-experiences-discovery.md#select-sharepoint-topic-sources)。 这些网站的内容不会出现在主题经验中。

- [按名称排除主题](topic-experiences-discovery.md#exclude-topics-by-name)。 明确排除的主题将不会出现在主题体验中。

- 使知识管理员删除主题中心中的主题。

此外，我们建议采用以下最佳做法：

- 从组织的不同区域招聘知识经理。 让具有各种专业知识的知识管理人员（以及访问 AI 使用的基础内容）可以帮助你为用户选择最有用的知识，并删除敏感信息（如果找到）。

- 设置用于请求更改的工作流。 知识经理、团队或网站所有者应具有一个流程，当在组织中启动新项目或当他们发现内容具有不适当的权限设置时，他们可以请求排除主题或网站。

- 在创建主题描述时要注意受众和信息的敏感度。 这些描述可能对没有权限访问该主题源内容的用户可见。

虽然可以改变个别主题页面的权限，以缩小对特定用户群的访问范围，但我们不推荐这种方法，因为这需要高度的管理工作量。

## <a name="see-also"></a>另请参阅

[配置具有三层保护的 Teams](../solutions/configure-teams-three-tiers-protection.md)

[计划主题体验](plan-topic-experiences.md)

[设置主题体验](set-up-topic-experiences.md)
