---
title: Microsoft 365 使用情况分析疑难解答
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: 了解如何解决 Microsoft 365 使用情况分析模板应用的问题。
ms.openlocfilehash: bc7f1f7188a209188f1a67a20bf79477c6e1d4a0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580734"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Microsoft 365 使用情况分析疑难解答

浏览以下错误消息列表，获取有关 Microsoft 365 使用情况分析的最常见问题的帮助。
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>无法处理你的请求。 你首先需要从 Microsoft 365 管理中心订阅此数据

 **错误代码** ：422 
  
 **将在什么位置看到此消息：** 在 Power BI 中，当连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 API 时。 
  
 **原因：** 在连接到应用之前，你必须从 Microsoft 365 管理中心订阅数据。 如果未首先完成此步骤，则即使提供 Microsoft 365 租户 ID，也将无法连接到模板应用。 
  
 **若要修复此错误：** 若要订阅数据，请转到管理中心"报告使用情况"，并找到主仪表板页面上的 \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a>"Microsoft 365 使用情况分析"磁贴。 选择 **"开始"** 按钮，然后在打开的"报告"窗格中，打开"向 **Microsoft 365 使用情况分析提供 Power BI** 数据"设置并 **"保存"。**
  
## <a name="we-are-processing-your-data"></a>正在处理你的数据

 **将在什么位置看到此消息：** 在 **Microsoft 365** 管理中心使用情况仪表板上的 Microsoft 365 使用情况分析磁贴中。 
  
 **原因：** 当你 [选择从](enable-usage-analytics.md) Microsoft 365 管理中心查看模板应用中的数据时，Microsoft 365 系统开始为组织生成历史使用情况数据。 此步骤可能需要 2 至 48 小时的时间，具体取决于租户的大小。 
  
 **若要修复此问题，请进行修复：** 请耐心等待，但如果邮件未在 3天后更改为你的数据已准备就绪，请联系 [Microsoft 365 商业版支持](../contact-support-for-business-products.md)人员。
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>我们现在无法处理你的请求。 仍在准备组织数据

 **错误代码：** 423 
  
 **将在什么位置看到此消息：** 在 Power BI 中，当你连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 API 时。 
  
 **原因：** 当你 [选择从管理中心查看](enable-usage-analytics.md) 模板应用中的数据时，Microsoft 365 系统开始为组织生成历史使用情况数据。 根据租户大小，此步骤可能需要 2 小时到 48 小时之间的任意时间。 
  
 **若要修复此问题，请进行修复：** 请耐心等待，但如果消息在启动 3天后未更改为你的数据已准备就绪，请联系 [Microsoft 365 商业版支持](../contact-support-for-business-products.md)人员。
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>提供的租户 ID 格式不正确

 **错误代码：** 400 
  
 **将在什么位置看到此消息：** 在 Power BI 中，当你连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 API 时。 
  
 **原因：** 租户 ID 是 guid，必须采用 xxxxxxxx-xxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx 格式。 如果在租户输入框中输入任何其他字符串，将收到此错误。 
  
 **若要修复此错误：** 转到管理中心 \> **"报告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况"，</a> 在主仪表板页面上找到"Microsoft 365 使用情况分析"磁贴。 租户 ID 在磁贴上列出。 你可以从此处复制它，并将其粘贴到对话框中以连接到模板应用。 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>系统无法识别你提供的租户 ID

 **错误代码：** 404 
  
 **将在什么位置看到此消息：** 在 Power BI 中，当连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 API 时。 
  
 **原因：** 你提供的租户 ID 无效或不存在。 
  
 **若要修复此错误：** 转到管理中心 \> **"报告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况"，</a> 在主仪表板页面上找到"Microsoft 365 使用情况分析"磁贴。 租户 ID 在磁贴上列出。 你可以从此处复制它，并将其粘贴到对话框中以连接到模板应用。 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>请重新输入凭据以再次登录到 Power BI

错误代码:302
  
 **将在什么位置看到此消息：** 在 Power BI 中，当连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 API 时。 
  
 **原因：** 授权代码失败，可能需要再次输入凭据。 
  
 **若要修复此错误：** 注销 Power BI，然后再次登录。 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>你不具有访问此数据的正确授权。 需要是全局管理员或任一产品管理员才能获取从该服务访问数据的权限

 **错误代码：** 403 
  
 **将在什么位置看到此消息：** 在 Power BI 中，当连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 API 时。 
  
 **原因：** 授权代码失败，因为尝试连接到模板应用的用户没有访问此数据的授权级别。 
  
 **若要修复此错误：** 提供全局管理员 **、Exchange** 管理员 **、Skype for Business** 管理员 **、SharePoint** 管理员、全局读取者或报表阅读者的用户凭据，以连接到模板应用。  有关详细信息 [，请参阅](../add-users/about-admin-roles.md) 关于管理员角色。 
  
## <a name="refresh-failed"></a>刷新失败

 **将出现此消息的情况：** Power BI 中的电子邮件或刷新历史记录中的失败状态。 
  
 **原因：** 有时，连接到模板应用的用户的凭据会重置，并且不会在模板应用的连接设置中更新，从而导致用户看到刷新失败错误。 
  
 **若要修复此错误：** 在 Power BI 中，查找与 Microsoft 365 使用情况分析模板应用对应的数据集，选择计划刷新并提供管理员凭据。 
  
如果不起作用，请清除缓存，然后重新创建模板应用。
  
  
