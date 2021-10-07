---
title: 使环境准备好使用Microsoft Viva主题
description: 准备好你的环境，以便你可以为用户提供尽可能多的内容，Microsoft Viva主题。
ms.author: samanro
author: samanro
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
ms.localizationpriority: medium
ms.openlocfilehash: a2e6ffc768f52d3738b9389d460ddba2a156152e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60214065"
---
# <a name="get-your-environment-ready-for-microsoft-viva-topics"></a>使环境准备好使用Microsoft Viva主题

为了充分利用 Viva 主题，您希望包含尽可能多的主题发现内容，以便为用户提供一组丰富的主题。 但是，哪些内容应该用于主题发现？ 如何在保持控制的同时最大化已编制索引的内容？ 范围内的内容越多，人工智能可以发现的见解就越好。 本文将引导你完成规划步骤，以确保包括适当的内容，并且你拥有合适的人员和资源来为用户提供良好的体验。

若要规划 Viva 主题，您需要：

![迁移、连接、现代化、安全，并确定载入 Viva 主题的步骤。](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [将内容迁移到SharePoint](#1-migrate-content-to-microsoft-365)
    - 主题索引仅包括网站SharePoint内容。
      - 如果可能，请从外部源将SharePoint内容迁移到 SharePoint Online。
      - 确定内容源的优先级，这些内容源具有很高的引文知识的可能性。
      - 强调 Viva 主题的好处，鼓励用户将内容从OneDrive移动到SharePoint网站。

2. [连接信息到 Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - 将来，外部内容可以进入知识图并可用。
    - 对于无法移动的内容，请考虑使用 Graph 连接器来增强搜索并准备将来包含。

3. [现代化SharePoint页面](#3-modernize-sharepoint-pages)
    - 主题卡片只能在新式页面上显示。
    - 确定作为现代化候选项的高配置文件经典页面。

4. [适当地保护内容](#4-secure-content-appropriately)
    - 根据用户的权限对主题资源进行安全修整。
    - 确定可能具有不正确广泛或限制权限的任何内容：
      - 鼓励网站所有者使用共享报告查看权限
      - 使管理员使用搜索审核广泛共享的内容
      - 鼓励内容所有者共享不敏感并且可能为组织带来更广泛的好处的内容。
    - 查看你的 Microsoft Graph用户和内容配置：
      - 主题索引使用不包括搜索或搜索内容的配置Delve (例如，NOINDEX) 。 检查这些配置是否仍然相关。

5. [确定知识管理人员和主题](#5-identify-knowledge-managers-and-topics)
    - 使用现有分类手动创建主题，或帮助确认 AI 建议的主题。
    - 确定针对预期主题 (或种子) 适用于中小型企业的行业专家。
    - 确定涉及大量有价值的数据的网站，这些数据可用于试验主题挖掘。
    - 与知识管理人员和实践社区互动。

## <a name="1-migrate-content-to-microsoft-365"></a>1. 将内容迁移到Microsoft 365

有几种工具和服务可帮助您进行迁移 -您可以在将内容迁移到迁移中获取有关如何迁移[的概述Microsoft 365。](/sharepointmigration/migrate-to-sharepoint-online) 迁移工具包括：

- [迁移管理器](/sharepointmigration/mm-get-started)
- [SharePoint 迁移工具 (SPMT)](/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [合作伙伴迁移工具和服务](https://www.microsoft.com/solution-providers)

充分利用迁移：

- 迁移到新式网站 - 包括Microsoft Teams。 虽然任何 SharePoint 网站 (经典或新式) 都可以进行索引，但通过突出显示和卡片向用户显示主题的情况只发生在新式页面。
- 维护用户名 - 大多数迁移工具都允许您在整个迁移中映射用户标识，以便迁移后保留"创建者"或"修改者"等属性。 这对主题非常重要，因为文件的作者身份用于标识添加到主题页面或卡片的专家。 
- 使服务帐户名称具有描述性 - 在某些情况下，无法维护用户名。 例如，如果要迁移由不再是组织员工的人创建的内容。 在这种情况下，大多数迁移工具会把文件当作是由管理员账户或服务账户创建的文件来迁移。 如果频繁发生这种情况，那么该服务帐户随后可能会作为专家根据主题列出。 这是该帐户的命名变得非常重要的地方。 如果你进行描述性说明，则用户使用主题时将可以理解这些非人工帐户的存在。

## <a name="2-connect-information-to-microsoft-graph"></a>2. 连接信息到 Microsoft Graph

如果无法迁移某些内容，请将其与 Microsoft Graph：

- 请考虑实现[Graph连接器。](/microsoftsearch/connectors-overview) 通过使用连接器，可以将外部内容索引到 Microsoft Graph，然后用户可以通过连接器Microsoft 搜索。
- 未来的开发将外部数据引入 Viva 主题。

## <a name="3-modernize-sharepoint-pages"></a>3. SharePoint页面

因为主题卡片和突出显示内容只能显示在新式页面上，所以请更新任何要包括在 Viva 主题中的页面，从经典页面更新为新式主题。 请参阅[现代化经典SharePoint网站](/sharepoint/dev/transform/modernize-classic-sites)。 可以使用现代化扫描[SharePoint](/sharepoint/dev/transform/modernize-scanner)为现代化经典网站做好准备。

如果很多经典网站，则请优先考虑将高配置文件页面转换为新式的。

## <a name="4-secure-content-appropriately"></a>4. 适当地保护内容

当用户与主题卡片或主题页面交互时，他们可能会看到不同的资源。 这是因为他们有权访问与主题关联的不同文件。 如果基础权限过于严格，则通过主题发现信息的潜在方面可能会减少。 另一方面，如果内容过于广泛，则主题可能会向用户显示您不希望他们看到的内容。
这里，良好的权限管理至关重要。 良好的权限管理基于管理员和内容所有者之间的持续合作关系。 虽然这可能是一项持续的活动，但您可以在准备主题时采取一些实际步骤：

- 鼓励网站所有者查看共享和权限。

  SharePoint查看其网站的共享报告，该报告显示网站上配置的所有权限和共享链接的完整详细信息，请参阅[共享报告](/sharepoint/sharing-reports)。 这将列出来宾用户的 (外部) 用户。

  网站所有者还可以访问"网站权限"和"高级权限"页面，查看哪些用户具有 **设置** 权限。

  1. On your site， choose **设置**  >  **Site permissions**. 检查列在 “网站所有者”、“网站成员” 和 “网站访问者” 之下的人员。 检查是否有任何 “来宾” 用户。
  2. 在 **“访问权限”** 窗格中，选择 **“高级访问权限设置”**。 可检查独有的访问权限，查看对网站中的任意项目有有限访问权的人员。

- 审核 Microsoft 365 组和 Teams，确保适当地设置它们为公共或专用组或团队。 默认情况下Teams组Microsoft 365组和组的新组设置为专用组，但在首次发布时，默认情况下是公开的。 如果您之前是这些技术的采用者，您可能需要查看。 此外，团队的功能往往在其生命周期中不断演变，设置可能需要更新以反映该团队的当前用途。
- 查看"每个人"、"除外部用户以外的每个人"或广泛安全组的使用。 可能被错误地与这些值共享内容。 若要查看这些组的使用，您可以：
  - 创建没有组成员身份的帐户
  - 使用此账户的搜索以发现广泛共享的内容。
  - 如果此帐户通过搜索看到不适当的内容，您可以与网站所有者一起更正权限配置。

除了权限之外，还可以控制可通过主题发现内容的范围。 您始终可以控制所编制索引的索引。

管理员可以在管理中心中Microsoft 365 管理索引。 设置 [Viva 主题时](set-up-topic-experiences.md)，您可以：

- 允许所有 SharePoint 站点上的发现，或指定要包含或排除的站点作为主题源。
- 如果有敏感术语，还可以按名称排除主题。例如，如果具有敏感项目的名称，并且不希望突出显示或显示卡片，则无论用户的权限如何，都可以排除该项目名称。

在内容级别，还可以控制可发现的内容。 您为从搜索中排除内容所做的任何配置也将由内容发现使用。 因此，例如，如果您将特定文档库从搜索结果中排除，则此文档库不会用于主题发现。

## <a name="5-identify-knowledge-managers-and-topics"></a>5. 确定知识管理人员和主题

管理主题涉及三个关键角色，包括两个新的 AAD Azure Active Directory (角色) 知识管理员和知识管理员：

- KA 管理员 (KA) 是一个技术角色，通常担任 IT 人员。 此角色允许在 M365 管理中心中设置 Viva 主题，并配置主题发现和可见性。
- KM (管理员) 主题本身，并监督其质量和完整性。
- 主题参与者 (TCS) 不基于 AAD 角色，而是基于管理中心中的权限。 他们是主题专家，能够处理主题内容、添加资源和人员。

根据你的组织，可能只有很少或多人担任这些角色。 对于一些组织，这些人员可能是同一个人。

| 知识管理员 | 知识经理 | 主题参与者 |
|:-------|:-------|:-------|:-------|
| AAD 角色 | AAD 角色 | SME |
| 有权访问管理中心 | 有权访问管理中心 | 无法访问管理中心 |
| 设置 Viva 主题 | 拥有主题的管理和质量 | 基于他们的专业知识参与主题。 |
| 确保强制实施安全性和合规性标准并了解许可协议。| 执行主题管理任务，如创建、编辑、删除和拒绝主题。 支持主题参与者执行其任务。 | 在主题页面上组织信息和内容，包括将哪些人员和资源固定到该主题。 |

用户将在工作上下文中显示突出显示和卡片，例如，当用户在 SharePoint 中浏览新式页面时。 您可以控制主题的最终用户体验。

- Who主题？ 主题可见性在中心Microsoft 365 管理配置。 选择要允许查看主题的组：
  - 组织中的每个人。 "每个人"不包括来宾，它是目录中的所有内部用户
  - 仅所选人员或安全 (此选项在仍推出 Viva 主题时) 。 如果希望来宾查看主题，将需要使用"所选人员或安全组"选项，并授予他们许可证。
  - 没有人。

    所有用户（甚至是来宾用户）都需要应用许可证才能查看主题体验。 请记住，权限始终控制可见内容。

- 哪些主题是可见的? 可选择:
  - 显示所有候选主题。
  - 仅显示已确认的主题。

现在我们已拥有经理、专家和用户，我们可以讨论这些主题本身。

- 最佳做法是，将主题设定为主题列表的种子。 主题的质量和数量基于您的内容 -只有主题包含在范围内的内容中时，才能作为主题创建。 如果主题有足够的信息和证据，它将由 AI 创建。 种子设定主题是知识管理器和主题专家可以提供帮助的地方。 将人类知识与 AI 合并是提供高质量主题的最佳方法。 因此，如果预计有主题，可以在主题中心手动创建这些主题。 这样做将为 AI 提供该主题相关性的强信号，并标识要与该主题关联的资源和人员。
- 使用现有分类来帮助你进行主题规划，无论是SharePoint规划。 现有分类通常包括组织术语、产品、主题区域等。 主题源也可以来自项目列表、现有搜索书签等。