---
title: 开始使用可见性和见解
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: 开始使用可见性和见解。
ms.openlocfilehash: fc7a76154437b57876a52cad5de1f637b8da7bc0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201933"
---
# <a name="get-started-with-visibility-and-insights"></a>开始使用可见性和见解

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

首先从 [https://aka.ms/appgovernance](https://aka.ms/appgovernance) 上的应用治理仪表板开始。 请注意，要查看应用治理数据，你的登录帐户必须具有[这些应用治理管理员角色](app-governance-get-started.md#administrator-roles)之一。

![Microsoft 365 合规中心中的应用治理概述页面。](..\media\manage-app-protection-governance\mapg-cc-overview.png)

你还可以从“**Office 365”>“Microsoft 365 合规中心”>“应用治理”>“概述**”页访问应用治理仪表板。

## <a name="whats-available-on-the-dashboard"></a>仪表板上提供的内容

仪表板包含租户中 Microsoft 365 应用生态系统组件的摘要：

- **租户摘要**：关键应用和警报类别的计数。
- **热门警报**：租户中最新的 10 个活动警报
- **数据和资源访问权限**：在图形中每月的列上移动鼠标以查看相应的值。
  - **过去四个月中的数据访问**: 跟踪租户中所有应用在过去四个日历月中通过 Graph API 访问的数据总数。目前仅包括邮件和文件上传/下载的使用。
  - **过去四个月中排名靠前的资源数据访问**: 过去四个日历月中数据使用情况，按资源类型细分。目前仅包括邮件和文件上传/下载的使用
- **改进应用保护和治理**：建议的操作，例如创建应用使用或权限策略。
- **按类别排列的热门应用**：按以下类别排序的热门应用：
  
  - **所有类别**：对所有可用类别进行排序。
  - **高级特权**：高级权限是根据平台机器学习和信号在内部确定的类别。
  - **过度特权**：当应用治理收到的遥测数据表明向某个应用授予的权限在过去 90 天内未被使用时，该应用则处于过度特权状态。 应用治理必须至少运行 90 天才能确定是否有任何应用处于过度特权状态。  
  - **未验证**：未获得 [发布商认证](/azure/active-directory/develop/publisher-verification-overview)的应用被视为未验证。
  - **仅应用**：[应用程序权限](/azure/active-directory/develop/v2-permissions-and-consent#permission-types)由无需登录用户即可运行的应用使用。 有权访问整个租户内的数据的应用可能具有更高的风险。
  - **新应用**：过去 7 天内注册的新 Microsoft 365 应用。  

## <a name="view-app-insights"></a>查看应用见解

应用治理的主要价值点之一是能够快速查看应用警报和见解。要查看应用的见解，请：

1. 在应用治理门户页面上，选择“**应用**”。
1. 使用“**类别**”下拉列表，从以下选项中进行选择：
    - 所有应用
    - 高权限
    - 特权过多
    - 未经验证的发布者
    - 仅限应用
    - 新应用
1. 选择应用名称以查看详细信息。 选择应用名称将打开右侧的详细信息窗格，如下图所示。

:::image type="content" source="../media/manage-app-protection-governance/app-governance-app-insight.png" alt-text="显示所选应用的详细信息窗格的图像。":::

> [!NOTE]
> 列出的应用将取决于租户中存在的应用。

通过保存查询，可以在当前视图中保存定义的筛选器列表。 这可以节省将来选择数据子集的时间。

通过详细信息窗格，还可以查看应用在过去 30 天内的使用情况、已同意使用该应用的用户以及分配给该应用的权限。 管理员可以查看正在生成警报的应用的活动和权限，并决定是否使用“详细信息”窗格中的“**禁用应用**”按钮来禁用该应用。

## <a name="next-step"></a>后续步骤

[获取有关特定应用的详细见解](app-governance-visibility-insights-view-apps.md)。
