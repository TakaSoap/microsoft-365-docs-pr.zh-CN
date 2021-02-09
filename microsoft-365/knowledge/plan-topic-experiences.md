---
title: 规划 Microsoft Viva 主题
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: 了解如何规划 Microsoft Viva 主题
ms.openlocfilehash: 2f7b85399f0b1f49e25aae1f1d4627413594f618
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150474"
---
# <a name="plan-for-microsoft-viva-topics"></a>规划 Microsoft Viva 主题

你可以控制主题在组织中是如何体验的。 针对主题的规划决策可确保向用户显示高质量主题，并且他们有权使用和贡献知识。

本文将介绍这些规划决策：

- 要针对主题对哪些 SharePoint 网站进行爬网
- 您希望从主题体验中排除的主题（如果有）
- 要向哪些用户显示主题
- 要向哪些用户授予在主题中心管理主题的权限
- 要授予在主题中心创建或编辑主题的权限的用户
- 要为主题中心命名的名称

将尊重数据的安全性和隐私，并且主题体验不会向用户授予对无权限文件的其他访问权限。 作为规划过程的一部分，我们还建议你阅读 [Microsoft Viva](topic-experiences-security-privacy.md) 主题安全和隐私。

## <a name="requirements"></a>要求

您必须订阅 [Viva 主题](https://www.microsoft.com/microsoft-viva/topics) ，并且必须是全局管理员或 SharePoint 管理员才能访问 Microsoft 365 管理中心并设置主题。

将使用主题的所有用户都需要主题 **体验** 许可证。 "设置 Microsoft Viva 主题"中介绍了 [分配许可证的内容](set-up-topic-experiences.md)。

## <a name="topic-discovery"></a>主题发现

主题发现设置指定哪些 SharePoint 网站用作主题源。 您可以选择包括所有 SharePoint 网站、特定网站列表或不包含任何网站。 我们建议你选择所有网站，以便主题体验可以发现大量适合你的用户的主题。

设置主题时，可以从以下选项中进行选择：

- **所有网站**：组织的所有 SharePoint 网站。 这包括当前和将来的网站。
- **所有（所选网站除外**）：除您指定的站点之外的所有网站。 将来创建的网站将包含为主题发现源。 
- **仅选定网站**：仅指定网站。 将来创建的网站不会作为主题发现源包含在内。
- **无网站**：不包括任何 SharePoint 网站。

如果选择"全部 **"（** 所选站点除外）或"仅选定网站"，可以上载包含站点列表的 .csv 文件。 如果你要执行试点并且希望包含有限数量的要启动的网站，这些选项将非常有用。

你可以复制下面的 .csv 模板：

``` csv
Site name,URL
```

我们不建议选择"否 **"网站** ，因为它会阻止自动创建或更新主题。 但是，如果要设置主题，稍后再添加网站，可以选择此选项。

建议为用户或知识管理员创建一个流程，以请求从主题发现中删除各个网站（如果需要）。

## <a name="user-permissions"></a>用户权限

您指定的用户权限决定了组织中哪些人员与主题进行交互以及他们可以做什么。

*管理主题*

知识管理人员监督信息的质量、信息的结构化方式以及组织的其他最佳做法。 他们可以确认和拒绝主题。

虽然您可以指定各个主题管理员，但我们建议您创建一个安全组 (或使用包含要成为知识管理员) 的现有组。 您可以在安装过程中指定此安全组。

*创建和编辑主题*

主题参与者是组织中冠军和主题专家。 他们可以创建和编辑主题。 

我们建议您允许组织中的每个人创建和编辑主题，因为当所有用户都可以共享信息时，主题体验效果最佳。

如果要将创建和编辑主题限制为特定人员或组，请为这些人员或组创建一个安全组，并指定它在安装过程中。

你可以选择不允许任何人参与主题，但不建议这样做。 如果选择此选项，知识管理员仍可以编辑和创建主题。

*主题查看者*

主题查看者可以在搜索结果和 SharePoint 页面等内容中突出显示主题时查看主题页面的信息。 只有在用户有权访问发现主题的文件和页面时，他们才能看到已发现的主题。

设置主题查看器时，您可以选择：

- **我的组织中的每个人**
- **仅选定人员或安全组**
- **没人**

我们建议 **我的组织中的每个人**，但如果进行试点，你可能希望仅选择选定的人员或安全组。 如果要设置 **主题** ，也可以选择"否"，但不允许用户查看主题。  (知识管理员仍可查看这些主题，并帮助他们做出让主题广泛可用的决定。) 

## <a name="knowledge-rules"></a>知识规则

作为管理员，你可以从主题体验中排除某些主题。 如果要使敏感数据不显示在主题中，这将非常有用。 虽然知识管理员可以排除主题中心中的主题，但管理员排除的主题甚至对知识管理员不可见。  (管理员还可以在 discovery.) 之后删除主题中心中的主题) 

如果要排除管理员级别的主题，则必须将它们添加到 .csv 文件并上载文件。 您可以在设置期间或更高版本中执行此操作。

.csv 文件必须包含以下参数：

- **名称**：键入要排除的主题的名称。 可通过 2 种方法执行此操作：
- **MatchType-Exact/Partial：** 键入您输入 *的名称是精确* 匹配类型还是 *部分* 匹配类型。
    - 完全匹配：可以包括确切的名称或首字母缩写词 (例如 *Contoso* 或 *ATL*) 。
    - 部分匹配：可以排除其中具有特定单词的所有主题。  例如 *，arc* 将排除其中带弧字的所有主题，如 *弧形圆*、圆弧 *弧* 线或 *培训弧*。请注意，它将不会排除作为单词的一部分包含的文本的主题，例如 *体系结构。*
- **代表 (** 可选) ： (也称为 *扩展)* 如果要排除首字母缩略词，请键入首字母缩写词代表的单词。

    ![排除 CSV 模板中的主题](../media/exclude-topics-csv.png) 

你可以复制下面的 csv 模板：

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>管理

在设置主题时，作为设置过程的一部分，将自动创建主题中心。 考虑要命名主题中心的内容以及希望 URL 是什么。 可以在设置过程中同时设置名称和 URL，稍后可以在 Microsoft 365 管理中心中更改名称 (但不能更改 URL) URL。 只能有一个主题中心。

## <a name="setup-checklist"></a>设置清单

设置主题体验时，在安装向导中需要以下项：

> [!div class="checklist"]
> * 要包含或排除的网站列表（如果未包括主题发现的所有网站）
> * 如果不允许所有用户查看主题，适用于主题查看者的安全组
> * 如果不允许所有用户创建和编辑主题，适用于主题参与者的安全组
> * 主题知识管理员的安全组（如果不允许所有用户管理主题）
> * 要从主题发现中排除的敏感主题列表
> * 主题中心网站的名称

## <a name="see-also"></a>另请参阅

[设置主题体验](set-up-topic-experiences.md)

[在 Microsoft 365 中管理主题发现](topic-experiences-discovery.md)

[在 Microsoft 365 中管理主题可见性](topic-experiences-knowledge-rules.md)

[在 Microsoft 365 中管理主题权限](topic-experiences-user-permissions.md)

[在 Microsoft 365 中更改主题中心的名称](topic-experiences-administration.md)
