---
title: Microsoft 365 使用情况分析疑难解答
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 了解如何解决 Microsoft 365 使用情况分析模板应用程序中的问题。
ms.openlocfilehash: bf8e4ece7b1e310d91f418f5388cae9aa27f2aa7
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841431"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Microsoft 365 使用情况分析疑难解答

浏览以下错误消息列表，以获取有关 Microsoft 365 使用情况分析中最常见问题的帮助。
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>无法处理你的请求。 您必须先从 Microsoft 365 管理中心订阅此数据

 **错误代码：** 422 
  
 **您将在其中看到以下消息：** 在 Power BI 中，当您连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 Api 时。 
  
 **原因：** 在连接到应用程序之前，您必须订阅来自 Microsoft 365 管理中心的数据。 如果不先执行此步骤，则不能连接到模板应用程序，即使你提供 Microsoft 365 租户 ID 也是如此。 
  
 **若要修复此错误：** 若要订阅数据，请转到管理中心 \> **报告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a> ，并在主仪表板页面上找到 Microsoft 365 使用情况分析磁贴。 选择 " **开始** 使用" 按钮，然后在打开的 " **报告** " 窗格中，打开 "将 **数据提供给 Power BI 的 Microsoft 365 使用情况分析** " 和 " **保存** "。
  
## <a name="we-are-processing-your-data"></a>正在处理你的数据

 **您将在其中看到以下消息：** 在 microsoft 365 管理中心的 **使用** 仪表板上的 **microsoft 365 使用情况分析** 磁贴中。 
  
 **原因：** 当您在 Microsoft 365 管理中心中 [选择查看模板应用程序](enable-usage-analytics.md) 中的数据时，Microsoft 365 系统会开始为您的组织生成历史使用情况数据。 此步骤可能需要 2 至 48 小时的时间，具体取决于租户的大小。 
  
 **若要修复此问题：** 只需耐心等待，但如果在3天后消息未更改为 " **数据已就绪** "，请 [联系 Microsoft 365 以获取商业支持](../contact-support-for-business-products.md)。
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>我们现在无法处理你的请求。 仍在准备组织数据

 **错误代码：** 423 
  
 **您将在其中看到以下消息：** 在 Power BI 中，当您连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 Api 时。 
  
 **原因：** 当您 [选择从管理中心查看模板应用程序](enable-usage-analytics.md) 中的数据时，Microsoft 365 系统会开始为您的组织生成历史使用情况数据。 根据你的租户的规模，此步骤可能需要两个小时到48小时之间的任何时间。 
  
 **若要修复此问题：** 只需耐心等待，但是如果自启动以来，如果消息未更改为 " **数据已就绪** "，则 [请联系 Microsoft 365 以获取商业支持](../contact-support-for-business-products.md)。
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>提供的租户 ID 格式不正确

 **错误代码：** 400 
  
 **您将在其中看到以下消息：** 在 Power BI 中，当您连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 Api 时。 
  
 **原因：** 租户 ID 是一个 guid，并且必须采用 xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx 格式的 "格式"。 如果在 "租户输入" 框中输入任何其他字符串，则会收到此错误。 
  
 **若要修复此错误：** 转到 "管理中心" \> **报告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a> ，并在主仪表板页面上找到 "Microsoft 365 使用情况分析" 磁贴。 图块上列出了租户 ID。 您可以从此处复制它，并将其粘贴到对话框中，以连接到模板应用程序。 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>系统无法识别你提供的租户 ID

 **错误代码：** 404 
  
 **您将在其中看到以下消息：** 在 Power BI 中，当您连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 Api 时。 
  
 **原因：** 你提供的租户 ID 无效或不存在。 
  
 **若要修复此错误：** 转到 "管理中心" \> **报告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a> ，并在主仪表板页面上找到 "Microsoft 365 使用情况分析" 磁贴。 图块上列出了租户 ID。 您可以从此处复制它，并将其粘贴到对话框中，以连接到模板应用程序。 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>请重新输入凭据以再次登录到 Power BI

错误代码:302
  
 **您将在其中看到以下消息：** 在 Power BI 中，当您连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 Api 时。 
  
 **原因：** 授权代码失败，可能需要再次输入凭据。 
  
 **若要修复此错误：** 注销 Power BI，然后再次登录。 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>你不具有访问此数据的正确授权。 需要是全局管理员或任一产品管理员才能获取从该服务访问数据的权限

 **错误代码：** 403 
  
 **您将在其中看到以下消息：** 在 Power BI 中，当您连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 Api 时。 
  
 **原因：** 授权代码失败，因为尝试连接到模板应用程序的用户不具有访问此数据的适当级别的授权。 
  
 **若要修复此错误：** 提供用户的凭据，该用户是 **全局管理员** 、 **Exchange 管理员** 、 **Skype for business 管理员** 、 **SharePoint 管理员** 、 **全局读者** 或 **报告阅读器** 以连接到模板应用。 有关详细信息，请参阅 [关于管理员角色](../add-users/about-admin-roles.md) 。 
  
## <a name="refresh-failed"></a>刷新失败

 **将出现此消息的情况：** Power BI 中的电子邮件或刷新历史记录中的失败状态。 
  
 **原因：** 有时，连接到模板应用程序的用户的凭据会重置，并且未在模板应用程序的连接设置中进行更新，从而导致用户看到刷新失败错误。 
  
 **若要修复此错误：** 在 Power BI 中，查找与 Microsoft 365 使用情况分析模板应用程序对应的数据集，选择 " **计划刷新** 并提供管理员凭据"。 
  
如果不起作用，请清除缓存，然后重新创建模板应用。
  
  
