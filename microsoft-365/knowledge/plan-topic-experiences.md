---
title: 规划Microsoft Viva主题
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
ms.localizationpriority: medium
description: 了解如何规划主题Microsoft Viva主题。
ms.openlocfilehash: 61729eeaa4a30a3f7e0faf50ab40320d88f3d78a
ms.sourcegitcommit: 317fab13e84b2867087a6ba0a593313ecf43bbed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2021
ms.locfileid: "60364575"
---
# <a name="plan-for-microsoft-viva-topics"></a>规划Microsoft Viva主题

你可以控制主题在组织中是如何体验的。 针对主题的规划决策可确保向用户显示高质量主题，并且他们有权使用和提供知识。

本文将介绍这些规划决策：

- 要SharePoint主题爬网的网站
- 您希望从主题体验中排除的主题（如果有）
- 您希望使主题对哪些用户可见
- 要向哪些用户授予在主题中心管理主题的权限
- 要向哪些用户授予在主题中心创建或编辑主题的权限
- 要为主题中心指定什么名称

将尊重数据的安全和隐私，并且主题体验不会向用户授予对无权限文件的额外访问权限。 作为规划过程的[一Microsoft Viva，](topic-experiences-security-privacy.md)我们还建议您阅读主题安全和隐私。

若要了解有关 Viva 主题背后的 AI 技术，请阅读以下主题Microsoft Viva[从大数据到大数据中的 Alexandria。](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge)

请记住，Viva 主题需要访问用户每天使用的网站和文件。 在测试或开发环境中部署 Viva 主题可能不会产生有用的结果。

## <a name="requirements"></a>要求

您必须订阅[Viva 主题](https://www.microsoft.com/microsoft-viva/topics)，并且必须是全局管理员或 SharePoint管理员才能访问Microsoft 365 管理中心设置主题。

将使用主题的所有用户都需要主题 **体验** 许可证。 Set up Microsoft Viva Topics 中介绍了[分配许可证](set-up-topic-experiences.md)。

## <a name="topic-discovery"></a>主题发现

主题发现设置指定将哪些 SharePoint 网站用作主题源。 这包括经典网站和新式网站，以及与组Microsoft Teams Microsoft 365网站。 OneDrive网站。

可以选择包含所有 SharePoint 网站、特定网站列表或无网站。 我们建议您选择所有网站，以便主题体验可以发现大量适合用户的主题。

当设置好主题后，可从下列选项中进行选择：

- **所有网站**：组织内的所有 SharePoint 网站。 这其中包括当前和未来的网站。
- **除所选网站之外的所有网站**：除指定网站之外的所有网站。 将来创建的网站将包含为主题发现源。 
- **仅选定网站**：仅指定网站。 将不包含未来创建的网站作为发现源。
- **无网站**：不包含任何 SharePoint 网站。

我们建议选择足够的网站以包含至少 20，000 个文档，以从 Viva 主题获得最佳结果。

如果您选择"全部 **"（** 所选网站除外）或"仅选定网站"，您可以上载包含.csv列表的配置文件。 如果你进行试验并且希望包含有限数量的站点来启动，这些选项非常有用。

你可以复制以下.csv模板：

``` csv
Site name,URL
```

我们不建议选择"否 **网站** "，因为它会阻止自动创建或更新主题。 但是，如果要设置"主题"，稍后再添加网站，可以选择此选项。

建议为用户或知识管理员创建一个流程，以请求从主题发现中删除各个网站（如果需要）。

### <a name="multi-geo"></a>多地理位置

如果组织已Microsoft 365[多](/microsoft-365/enterprise/microsoft-365-multi-geo)地理位置，Viva 主题通过确保主题数据始终存储在正确的地理位置来尊重数据威胁。 主题中心在中心位置进行预配，并且所有地理位置的内容都在那里进行处理。 结果发现的主题与源内容存储在相同的地理位置。 如果主题源数据在地理位置之间移动，则相应的主题属性（如说明）也移动。

## <a name="user-permissions"></a>用户权限

您指定的用户权限确定组织中哪些人员与主题交互以及他们可以做什么。

> [!Note] 
> 目前，Viva 主题不支持为来宾和外部用户 (许可证) 权限。 

*管理主题*

知识管理人员监督信息的质量、信息的结构化方式以及组织的其他最佳做法。 他们可以确认和拒绝主题。

虽然您可以指定各个主题管理员，但建议您创建一个安全 (或使用包含您希望成为知识管理员) 的现有安全组。 您可以在安装过程中指定此安全组。

*创建和编辑主题*

主题参与者是贵组织中冠军和主题专家。 他们可以创建和编辑主题。 

建议允许组织中的每个人创建和编辑主题，因为主题体验在所有用户都可以共享信息时效果最佳。

如果要将创建和编辑主题限制为特定人员或组，请为这些人员或组创建一个安全组，在设置过程中指定它。

你可以选择不允许任何人参与主题，但建议不要这样做。 如果选择此选项，知识管理员仍可以编辑和创建主题。

*主题查看器*

主题查看者可以在搜索结果和主题页面等内容中突出显示主题SharePoint信息。 只有在用户有权访问发现主题的文件和页面时，他们才能看到已发现的主题。

设置主题查看器时，可以选择：

- **我的组织中的每个人**
- **仅选定人员或安全组**
- **没人**

我们建议 **"我的组织"中的**"每个人"，但如果进行试点，你可能希望仅选择所选人员或安全组。 如果要设置 **主题** ，但不允许用户查看主题，也可以选择"否"。  (管理员仍可访问，以便他们查看主题并帮助做出使主题广泛可用的决定。) 

## <a name="knowledge-rules"></a>知识规则

作为管理员，你可以从主题体验中排除某些主题。 如果希望使敏感数据不显示在主题中，这将非常有用。 虽然知识管理员可以排除主题中心中的主题，但管理员排除的主题甚至对知识管理员不可见。  (管理员还可以在发现之后删除主题中心) 

如果要排除管理员级别的主题，则必须将它们添加到.csv文件并上载该文件。 可以在安装过程中或以后执行这些操作。

.csv文件必须包含以下参数：

- **名称**：键入要排除的主题的名称。 可以通过两种方式来执行此操作：
- **MatchType-Exact/Partial**：键入您输入 *的名称是精确* 匹配类型还是 *部分* 匹配类型。
    - 完全匹配：可以包含确切的名称或缩写词 (例如 *Contoso* 或 *ATL*) 。
    - 部分匹配：可以排除其中包含特定单词的所有主题。  例如 *，arc 将* 排除包含单词 *arc* 的所有主题，如弧 *形圆*、*弧* 形圆或 *培训弧*。请注意，它将不会排除将文本作为单词的一部分包含的主题，例如体系结构 *。*
- **代表 (** 可选) ： (也称为扩展 *)* 如果要排除缩略词，请键入首字母缩写词代表的单词。

    ![排除 CSV 模板中的主题。](../media/exclude-topics-csv.png) 

你可以复制下面的 csv 模板：

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>管理

在设置主题时，作为设置过程的一部分，将自动创建主题中心。 考虑要命名主题中心的内容以及希望 URL 的名称。 可以在设置过程中同时设置名称和 URL，也可以稍后在 (中更改名称) URL Microsoft 365 管理中心。 只能有一个主题中心。

## <a name="setup-checklist"></a>设置清单

设置主题体验时，在安装向导中需要以下项：

> [!div class="checklist"]
> * 不包含所有主题发现网站时要包括或排除的网站列表
> * 不允许所有用户查看主题时，查看者的安全组
> * 不允许所有用户创建和编辑主题时，参与者的安全组
> * 不允许所有用户管理主题时，知识管理员的安全组
> * 主题发现中排除的敏感主题列表
> * 主题中心网站的名称

## <a name="see-also"></a>另请参阅

[设置主题体验](set-up-topic-experiences.md)

[在"管理主题发现"Microsoft 365](topic-experiences-discovery.md)

[管理主题在Microsoft 365](topic-experiences-knowledge-rules.md)

[在管理中管理主题Microsoft 365](topic-experiences-user-permissions.md)

[更改主题中心的名称Microsoft 365](topic-experiences-administration.md)
