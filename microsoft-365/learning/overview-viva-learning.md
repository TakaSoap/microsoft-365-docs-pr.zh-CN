---
title: 概述Microsoft Viva Learning
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: shirana
ms.date: 11/02/2021
audience: admin
ms.topic: article
ms.custom: intro-overview
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
ms.localizationpriority: medium
description: 了解Microsoft Viva Learning环境中Microsoft 365。
ms.openlocfilehash: c92fc51d11b2d57c7fd051cbd060276d093be019
ms.sourcegitcommit: 16e3a6e6df253de1153e46d058941cd9a2bbf2b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889755"
---
# <a name="overview-of-microsoft-viva-learning"></a>概述Microsoft Viva Learning

Viva Learning是 Microsoft Teams 中一个集中式学习中心，可让你将学习与培养技能无缝集成在一起。 在 Viva Learning，你的团队可以发现、共享、推荐和学习由组织和合作伙伴提供的内容库。 他们无需离开任何项目即可Microsoft Teams。

   ![Teams 中的 Viva Learning主页的屏幕截图。](../media/learning/overview-1.png)

Viva Learning使你无需离开已使用的通信工具，即可轻松为组织创造学习和增长的机会。

## <a name="learn-while-working"></a>工作期间学习

### <a name="everyone"></a>所有人

Viva Learning使你能够轻松地将学习融入你的一天中。 当你在 Microsoft Teams 中打开 Viva Learning，你将看到从你的组织和合作伙伴（如 LinkedIn Learning）学习内容的个性化Learning。 当您继续搜索并完成更多培训时，建议的内容将更新以反映您的兴趣。

- 轻松找到组织提供的学习机会。
- 浏览来自 Microsoft 和第三方内容提供商的课程。
- 搜索吸引你或支持你的职业目标的特定学习内容。
- 在群组聊天或频道中与团队成员或组共享相关、有趣Microsoft Teams学习内容。
- 在频道和选项卡中组织Microsoft Teams学习内容的自定义选择。
- 为感兴趣的课程添加书签。
- 在嵌入式Learning玩 LinkedIn Microsoft Teams。

### <a name="managers"></a>Managers

让团队保持参与并掌握最新所需的技能，而无需跨平台协调学习。 你可以建议个人学习内容，与团队共享内容，并跟踪你建议的学习报告完成状态。

## <a name="admin-roles"></a>管理员角色

Viva Learning在已提供Microsoft Teams内容中默认可用。 若要在 Viva 中设置学习内容源Learning管理单个许可，你将需要以下权限：

- Microsoft Teams管理员
- Microsoft 365全局管理员或SharePoint管理员
- 知识管理员

### <a name="knowledge-admin"></a>知识管理员

知识管理员是 Azure Active Directory (Azure AD) 中新的Microsoft 365 管理中心角色，可分配给组织中的任何人。 此角色通过角色管理组织的学习内容Microsoft 365 管理中心。 有关详细信息，请参阅 [Azure AD内置角色](/azure/active-directory/roles/permissions-reference#knowledge-administrator)。

知识管理员应具有中等技术水平，并且SharePoint管理员凭据。 知识管理员应很好地了解组织的教育、学习、培训或员工体验部分。

## <a name="learning-content-sources"></a>Learning内容源

来自 Microsoft Learn and Microsoft 365 Training 的内容将在 Viva Learning 中自动提供。 还可从 LinkedIn Learning 免费访问一组 125 个课程。 此外，Viva Learning与选择的第三方内容提供商和学习管理系统集成。 若要详细了解如何设置内容源，请参阅管理[Viva 内容源Learning。](content-sources-365-admin-center.md)

## <a name="supported-languages"></a>支持的语言

Viva Learning组织的语言首选项Microsoft 365组织的语言首选项。 但是，viva Learning目前不支持从右向左的语言。 目前，Learning支持 Viva 版本：

:::row:::
   :::column span="":::
      - az-Latn-AZ
      - bg-BG
      - bn-IN
      - ca-ES
      - ca-Es-VALENCIA
      - cs-CZ
      - cy-GB
      - da-DK
      - de-DE
      - el-GR
      - en-GB
      - en-US
      - es-ES
      - es-MX
   :::column-end:::
   :::column span="":::
      - et-企业版
      - eu-ES
      - fi-FI
      - fil-PH
      - fr-CA
      - fr-FR
      - gl-ES
      - gu-IN
      - hi-IN
      - hr-HR
      - hu-HU
      - id-ID
      - is-IS
      - it-IT
   :::column-end:::
   :::column span="":::
      - ja-JP
      - ka-GE
      - kk-KZ
      - kn-IN
      - ko-KR
      - lt-LT
      - lv-LV
      - mk-MK
      - ml-IN
      - mr-IN
      - nb-NO
      - nl-NL
      - nn-NO
      - pl-PL
   :::column-end:::
   :::column span="":::
      - pt-BR
      - pt-PT
      - ro-RO
      - ru-RU
      - sk-SK
      - sl-SI
      - sq-AL
      - sr-Latn-RS
      - sv-标准版，ta-IN
      - te-IN，th-TH
      - tr-TR
      - uk-UA
      - vi-VN
      - zh-CN
      - zh-TW
   :::column-end:::
:::row-end:::

## <a name="data-and-privacy"></a>数据和隐私

Viva Learning数据驻留特定于租户，并且遵循标准Microsoft 365按可用地理位置定义数据存储指南。 有关详细信息，请参阅[我的客户数据Microsoft 365的位置](/microsoft-365/enterprise/o365-data-locations)。

目前SharePoint地理位置托管的网站才支持与租户集成。 例如，法国租户只能将SharePoint网站链接到 Viva Learning。

从 Viva 文件存储Learning包括：

- Learning内容元数据，如标题、说明、作者和语言
- 用户数据，例如书签、最近查看的、推荐的课程、分配的课程和完成记录
- 必需的服务数据，如错误日志
- 诊断数据使用情况

>[!NOTE]
>管理员可以打开或关闭诊断数据存储。

## <a name="get-started"></a>入门

准备好在自定义环境中设置和配置 Viva Learning时Microsoft 365：

- 使用 Microsoft Teams管理中心[管理整个Learning Viva 应用程序](set-up-viva-learning.md)。
- 使用 Microsoft 365 管理中心[配置可用于特定组的学习源](content-sources-365-admin-center.md)。
- 使用SharePoint管理中心[管理和存储自己的学习内容](configure-sharepoint-content-source.md)。
