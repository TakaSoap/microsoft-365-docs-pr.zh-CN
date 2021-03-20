---
title: 使环境准备好使用 Microsoft Viva 主题
description: 准备好环境，以便使用 Microsoft Viva 主题尽可能为用户提供内容。
ms.author: samanro
author: samanro
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 2db8654bf7bb1bc5ef4759c1617a84ae2153553a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917388"
---
# <a name="get-your-environment-ready-for-microsoft-viva-topics"></a>使环境准备好使用 Microsoft Viva 主题

为了充分利用 Viva 主题，您希望包含尽可能多的主题发现内容，以便为用户提供一组丰富的主题。 但是，哪些内容应该用于主题发现？ 如何在保持控制的同时最大化已编制索引的内容？ 范围内的内容越多，人工智能可以发现的见解就越好。 本文将指导你完成规划步骤，以确保包含适当的内容，并且具有合适的人员和资源来为用户提供良好的体验。

若要规划 Viva 主题，您需要：

![迁移、连接、现代化、安全并确定载入知识管理的步骤](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [将内容迁移到 SharePoint](#1-migrate-content-to-microsoft-365)
    - 主题索引仅包括 SharePoint 网站上的内容。
      - 如果可能，请从外部源将有价值的内容迁移到 SharePoint Online。
      - 确定内容源的优先级，这些内容源具有很高的引文知识的可能性。
      - 强调知识管理的好处，鼓励用户将内容从 OneDrive 移动到 SharePoint 网站。

2. [将信息连接到 Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - 将来，外部内容可以进入知识图表并可用。
    - 对于无法移动的内容，请考虑使用 Graph 连接器增强搜索功能，并为将来包含做好准备。

3. [现代化 SharePoint 页面](#3-modernize-sharepoint-pages)
    - 主题卡片只能在新式页面上显示。
    - 确定作为现代化候选项的高配置文件经典页面。

4. [适当地保护内容](#4-secure-content-appropriately)
    - 根据用户的权限对主题资源进行安全修整。
    - 确定可能具有不正确广泛或限制权限的任何内容：
      - 鼓励网站所有者使用共享报告查看权限
      - 使管理员使用搜索审核广泛共享的内容
      - 鼓励内容所有者共享不敏感并且可能为组织带来更广泛的好处的内容。
    - 查看有关用户和内容的 Microsoft Graph 配置：
      - 主题索引使用不包括搜索或 Delve (内容的配置，例如，NOINDEX) 。 检查这些配置是否仍然相关。

5. [确定知识管理人员和主题](#5-identify-knowledge-managers-and-topics)
    - 使用现有分类手动创建主题，或帮助确认 AI 建议的主题。
    - 确定针对预期 (或) 的中小型企业的行业专家。
    - 确定涉及大量有价值的数据的网站，这些数据可用于试验主题挖掘。
    - 与知识管理人员和实践社区互动。

## <a name="1-migrate-content-to-microsoft-365"></a>1. 将内容迁移到 Microsoft 365

可以使用多种工具和服务来帮助进行迁移 -你可以从将内容迁移到 [Microsoft 365](/sharepointmigration/migrate-to-sharepoint-online)获取有关如何迁移的概述和信息。 迁移工具包括：

- [迁移管理器](/sharepointmigration/mm-get-started)
- [SharePoint 迁移工具 (SPMT)](/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [合作伙伴迁移工具和服务](https://www.microsoft.com/solution-providers)

充分利用迁移：

- 迁移到包括 Microsoft Teams 的新式网站。 尽管索引可以在任何 SharePoint 网站上进行 (或新式) ，但通过突出显示和卡片向用户显示主题仅发生在新式页面上。
- 维护用户名 - 大多数迁移工具都允许您在整个迁移中映射用户标识，以便迁移后保留"创建者"或"修改者"等属性。 这对主题非常重要，因为文件的作者身份用于标识添加到主题页面或卡片的专家。 
- 使服务帐户名称具有描述性 - 在某些情况下，无法维护用户名。 例如，如果要迁移由不再是组织员工的人创建的内容。 在这种情况下，大多数迁移工具都会移动文件，就像文件由管理员帐户或服务帐户创建一样。 如果频繁发生这种情况，那么该服务帐户随后可能会作为专家根据主题列出。 这是该帐户的命名变得非常重要的地方。 如果你进行描述性说明，则用户使用主题时将可以理解这些非人工帐户的存在。

## <a name="2-connect-information-to-microsoft-graph"></a>2. 将信息连接到 Microsoft Graph

如果无法迁移某些内容，请将其与 Microsoft Graph 连接：

- 请考虑实现 [Graph 内容连接器](/microsoftsearch/connectors-overview)。 通过使用连接器，可以将外部内容索引到 Microsoft Graph 中，然后用户可以通过 Microsoft 搜索发现它。
- 未来的开发将外部数据引入 Viva 主题。

## <a name="3-modernize-sharepoint-pages"></a>3. 现代化 SharePoint 页面

因为主题卡片和突出显示内容只能显示在新式页面上，所以请更新任何要包括在 Viva 主题中的页面，从经典页面更新为新式主题。 请参阅 [现代化经典 SharePoint 网站](/sharepoint/dev/transform/modernize-classic-sites)。 可以使用 [SharePoint 现代化扫描程序](/sharepoint/dev/transform/modernize-scanner) 为现代化经典网站做好准备。

如果有很多经典网站，请确定要转换为新式页面的高配置文件页面的优先级。

## <a name="4-secure-content-appropriately"></a>4. 适当地保护内容

当用户与主题卡片或主题页面交互时，他们可能会看到不同的资源。 这是因为他们有权访问与主题关联的不同文件。 如果基础权限过于严格，则通过主题发现信息的潜在方面可能会减少。 另一方面，如果内容过于广泛，则主题可能会向用户显示您不希望他们看到的内容。
这里，良好的权限管理至关重要。 良好的权限管理基于管理员和内容所有者之间的持续合作关系。 尽管这可能是一项持续的活动，但您可以在准备主题时采取一些实际步骤：

- 鼓励网站所有者查看共享和权限。

  SharePoint 网站所有者可以审阅其网站的共享报告，该报告显示网站上配置的所有权限和共享链接的完整详细信息，请参阅 [共享报告](/sharepoint/sharing-reports)。 这将列出来宾用户 (外部) 用户。

  网站所有者还可以访问"网站权限"和"高级权限设置"页，查看哪些人 **具有网站权限**。

  1. On your site， choose **Settings**  >  **Site permissions**. 查看"网站所有者、网站成员"和"网站访问者"下列出的用户。 检查是否有来宾用户。
  2. 在"**权限"** 页上，选择"**高级权限设置"。** 您可以检查唯一权限，并查看谁对网站中任何项目具有受限访问权限。

- 审核 Microsoft 365 组和 Teams，以确保它们被正确设置为公共或专用组或团队。 默认情况下，新 Teams 和 Microsoft 365 组设置为专用，但在首次发布时默认为公开发布。 如果您之前是这些技术的采用者，您可能需要查看。 此外，团队的功能通常会在其生命周期内不断发展，并且可能需要更新设置以反映团队的当前使用。
- 查看"每个人"、"除外部用户以外的每个人"或广泛安全组的使用。 内容可能错误地与这些值共享。 若要查看这些组的使用，您可以：
  - 创建没有组成员身份的帐户
  - 使用此帐户使用搜索来发现广泛共享的内容。
  - 如果此帐户通过搜索看到不适当的内容，您可以与网站所有者一起更正权限配置。

除了权限之外，还可以控制可通过主题发现内容的范围。 您始终可以控制所编制索引的索引。

管理员可以在 Microsoft 365 管理中心中配置索引。 设置知识管理 [时](set-up-topic-experiences.md)，您可以：

- 允许跨所有 SharePoint 网站进行发现，或指定将网站包含或排除为主题源。
- 在有敏感术语的地方，还可以按名称排除主题。 例如，如果您具有敏感项目的名称，而您不希望显示突出显示或卡片，而不考虑用户的权限，您可以排除该项目名称。

在内容级别，还可以控制可发现的内容。 您为从搜索中排除内容所做的任何配置也将由内容发现使用。 因此，例如，如果您将特定文档库从搜索结果中排除，则此文档库不会用于主题发现。

## <a name="5-identify-knowledge-managers-and-topics"></a>5. 确定知识管理人员和主题

管理主题涉及三个关键角色，包括两个新的 Azure Active Directory (AAD) 角色：知识管理员和知识管理员：

- KA (管理员) 是一个技术角色，通常是 IT 人员。 此角色允许在 M365 管理中心中设置 Viva 主题，并配置主题发现和可见性。
- KM (管理员) 主题本身，并监督其质量和完整性。
- 主题参与者 (TCS) 不基于 AAD 角色，而是基于管理中心中的权限。 他们是主题专家，能够处理主题内容、添加资源和人员。

根据你的组织，可能只有很少或多人担任这些角色。 对于一些组织，这些人员可能是同一个人。

| 知识管理员 | 知识管理器 | 主题参与者 |
|:-------|:-------|:-------|:-------|
| AAD 角色 | AAD 角色 | SME |
| 有权访问管理中心 | 有权访问管理中心 | 无法访问管理中心 |
| 设置 Viva 主题 | 拥有主题的管理和质量 | 基于他们的专业知识为主题做贡献。 |
| 确保强制实施安全性和合规性标准并了解许可协议。| 执行主题管理任务，如创建、编辑、删除和拒绝主题。 支持主题参与者执行其任务。 | 在主题页面上组织信息和内容，包括将哪些人员和资源固定到该主题。 |

当用户在 SharePoint 中浏览新式页面时，其工作上下文中将显示突出显示和卡片。 您可以控制主题的最终用户体验。

- 谁可以看到主题？ 主题可见性在 Microsoft 365 管理中心中配置。 选择要允许查看主题的组：
  - 我的组织中的每个人。 "每个人"不包括来宾，它是目录中的所有内部用户
  - 仅所选人员或安全 (此选项在您仍然推出 Viva 主题时) 。 如果希望来宾查看主题，将需要使用"所选人员或安全组"选项，并授予他们许可证。
  - 没有人。

    所有用户（甚至是来宾用户）都需要应用许可证才能查看主题体验。 请记住，权限始终控制可见内容。

- 哪些主题可见？ 可以选择：
  - 显示所有候选主题。
  - 只显示已确认的主题。

现在我们已拥有经理、专家和用户，我们可以讨论这些主题本身。

- 最佳做法是，将主题设定为主题列表的种子。 主题的质量和数量基于您的内容 - 只有主题包含在范围内的内容中时，才能作为主题创建。 如果主题有足够的信息和证据，它将由 AI 创建。 种子设定主题是知识管理器和主题专家可以提供帮助的地方。 将人类知识与 AI 相结合是质量主题的最佳途径。 因此，如果预计有主题，可以在主题中心手动创建这些主题。 这样做将为 AI 提供该主题的相关性的强信号，并且它将标识要与该主题关联的资源和人员。
- 使用现有分类，从 SharePoint 或其他位置帮助你进行主题规划。 现有分类通常包括组织术语、产品、主题区域等。 主题源也可以来自项目列表、现有搜索书签等。