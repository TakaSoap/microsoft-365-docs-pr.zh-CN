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
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 开始使用可见性和见解。
ms.openlocfilehash: 0a986bec512c665372ef2e98155533a49500c5d8
ms.sourcegitcommit: 132b8dc316bcd4b456de33d6a30e90ca69b0f956
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589396"
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

## <a name="next-step"></a>后续步骤

[获取有关特定应用的详细见解](app-governance-visibility-insights-view-apps.md)。
