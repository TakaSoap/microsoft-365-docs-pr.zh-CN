---
title: Microsoft 365 支持与 ServiceNow 配置概述集成
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: ServiceNow 的作用域认证应用程序安装和配置指南。
ms.openlocfilehash: d1e95d308364d92954d53a8ef105dc877d0376a5
ms.sourcegitcommit: 7fd1bcbd8246501029837e3ea92adea64c3406e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2022
ms.locfileid: "62295106"
---
# <a name="microsoft-365-support-integration-with-servicenow-configuration-overview"></a>Microsoft 365 支持与 ServiceNow 配置概述集成

**Microsoft 365集成** 使您可以将Microsoft 365、支持和服务运行状况与 ServiceNow 实例集成。 你可以研究 Microsoft 已知和已报告的问题、解决事件、使用 Microsoft 建议的解决方案完成任务，并在必要时上报给 Microsoft 人员协助支持。

有关 **Microsoft 365** ServiceNow 存储支持集成应用的信息，请转到 [ServiceNow 应用商店](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f)。

## <a name="key-features"></a>关键功能

这些是你将使用 ServiceNow 实例中的 Microsoft 365 集成应用获得的关键功能：

- 服务运行状况事件：有关已知 Microsoft 服务运行状况事件的信息，包括用户影响、范围、当前状态和下一次预期更新。 使用机器学习，ServiceNow 事件根据简短说明字段与 Microsoft 服务运行状况事件匹配。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-description-field-1.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-description-field-1.png" alt-text="&quot;服务运行状况事件说明&quot;域。":::

- 建议的解决方案：任务和事件的说明用于推荐精确的目标解决方案以及由机器学习支持 Microsoft 的相关文章。 如果需要，您还可以使用搜索查找其他解决方案。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-description-field-2.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-description-field-2.png" alt-text="建议的解决方案说明域。":::

- Microsoft 服务请求：将问题上报给 Microsoft 支持代理，并接收你的案例的状态更新。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-service-request.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-service-request.png" alt-text="服务请求表单。":::

## <a name="prerequisites"></a>先决条件

### <a name="permissions-requirements"></a>权限要求

若要继续学习本指南，请确保以下权限在整个过程中可用，并针对你的环境进行配置：

- Azure Active Directory (AAD) 创建应用程序管理员Azure AD管理员

- ServiceNow 管理员

- Microsoft 365租户管理员

### <a name="configuration-highlights"></a>配置要点

若要设置Microsoft 365 **集成：**

- 在 Microsoft Azure Active Directory (AAD) 中注册应用程序，以对出站和入站 API 调用进行身份验证。

- 为出站和入站数据流Microsoft Azure AD应用程序创建 ServiceNow 实体。

- 通过管理门户将 ServiceNow 实例与 Microsoft Microsoft 365集成。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-integration-diagram.png" alt-text="ServiceNow 集成图。":::

### <a name="application-dependencies-in-your-servicenow-environments"></a>ServiceNow 环境中的应用程序依赖关系

所需的权限：

- oauthentity\_

- oauthentityprofile\_\_

安装Microsoft 365集成应用程序后，将创建两个应用程序跨作用域访问。 如果未成功创建，请手动创建它们。

## <a name="what-features-will-work-for-your-organization-based-on-your-configuration"></a>根据你的配置，哪些功能将适用于你的组织？

在设置支持集成Microsoft 365配置之前，请查看对以下问题的回答：

**问题 \#1**：ServiceNow 环境是否允许对入站 web 服务 (使用 ServiceNow 用户凭据) 基本身份验证？

**问题 \#2**：如果你有多个租户，是否计划使用与 ServiceNow 环境集成的单个租户Microsoft 365集成？

根据对以上问题的答案，此表将告诉您哪些功能可用以及如何设置Microsoft 365集成。 有关每个功能的说明，请参阅Microsoft 365[集成](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f)。

| 问题 \#1 答案 | 问题 \#2 答案 | 哪些功能可用？ | 配置步骤 |
|---------------------|---------------------|-----------|----------------|
| 是                 | 是/否              | 服务运行状况事件建议解决方案 Microsoft 服务请求 | [设置Microsoft 365 ServiceNow 基本身份验证集成](servicenow-basic-authentication.md) |
| 否                  | 是                 | 服务运行状况事件建议解决方案 Microsoft 服务请求 | [设置Microsoft 365支持与身份验证Azure AD集成](servicenow-aad-oauth-token.md)                 |
| 否                  | 否                  | 服务运行状况事件建议解决方案                           | [设置Microsoft 365仅支持Insights集成](servicenow-service-health-incidents-solutions-only.md)                    |
