---
title: 使用率Microsoft 365疑难解答
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: 了解如何排查有关 Microsoft 365 使用情况分析模板应用的问题。
ms.openlocfilehash: afa9841b38beefcfdd091f27e7b1f328cdf52a5e
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531071"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>使用率Microsoft 365疑难解答

浏览以下错误消息列表，获取有关有关使用情况分析的最常见Microsoft 365的帮助。
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>无法处理你的请求。 你首先必须订阅数据Microsoft 365 管理中心

 **错误代码** ：422 
  
 **将在什么位置看到此消息：** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs. 
  
 **原因：** 在可以连接到应用之前，你必须从应用程序订阅Microsoft 365 管理中心。 如果未首先完成此步骤，则你将无法连接到模板应用，即使你提供你的Microsoft 365 ID。 
  
 **若要修复此错误：** 若要订阅数据，请转到管理中心"报告使用情况"，Microsoft 365主仪表板页面上的"使用情况分析" \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a>磁贴。 选择 **"开始"** 按钮，然后在打开的"报告"窗格中，打开"使数据可用于Microsoft 365使用情况分析"设置 **Power BI"****保存"。**
  
## <a name="we-are-processing-your-data"></a>正在处理你的数据

 **将在什么位置看到此消息：** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 管理中心. 
  
 **原因：** 当你 [选择从模板](enable-usage-analytics.md)应用中查看模板Microsoft 365 管理中心时，Microsoft 365系统开始为组织生成历史使用情况数据。 此步骤可能需要 2 至 48 小时的时间，具体取决于租户的大小。 
  
 **若要修复此问题，请进行修复：** 请耐心等待，但如果邮件未在 3天后更改为"数据已准备就绪"，[联系 Microsoft 365 for business support] (获取支持] (。/get-help-support.md) 。
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>我们现在无法处理你的请求。仍在准备组织数据

 **错误代码：** 423 
  
 **将在什么位置看到此消息：** In Power BI， when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs. 
  
 **原因：** 当你 [选择从管理中心查看](enable-usage-analytics.md)模板应用中的数据时，Microsoft 365系统开始为组织生成历史使用情况数据。 根据租户大小，此步骤可能需要 2 小时到 48 小时之间的任意时间。 
  
 **若要修复此问题，请进行修复：** 请耐心等待，但如果消息在启动 3天后未更改为"数据已准备就绪"，请与Microsoft 365 [联系](../../business-video/get-help-support.md)。
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>提供的租户 ID 格式不正确

 **错误代码：** 400 
  
 **将在什么位置看到此消息：** In Power BI， when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs. 
  
 **原因：** 租户 ID 是 guid，必须采用 xxxxxxxx-xxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx 格式。 如果在租户输入框中输入任何其他字符串，将收到此错误。 
  
 **若要修复此错误：** 转到管理中心 \> **"报告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>"，Microsoft 365仪表板页面上的"使用率分析"磁贴。 租户 ID 在磁贴上列出。 你可以从此处复制它，并将其粘贴到对话框中以连接到模板应用。 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>系统无法识别你提供的租户 ID

 **错误代码：** 404 
  
 **将在什么位置看到此消息：** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs. 
  
 **原因：** 你提供的租户 ID 无效或不存在。 
  
 **若要修复此错误：** 转到管理中心 \> **"报告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>"，Microsoft 365仪表板页面上的"使用率分析"磁贴。 租户 ID 在磁贴上列出。 你可以从此处复制它，并将其粘贴到对话框中以连接到模板应用。 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>请重新输入凭据以再次登录到 Power BI

错误代码:302
  
 **将在什么位置看到此消息：** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs. 
  
 **原因：** 授权代码失败，可能需要再次输入凭据。 
  
 **若要修复此错误：** 注销 Power BI，然后再次登录。 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>你不具有访问此数据的正确授权。需要是全局管理员或任一产品管理员才能获取从该服务访问数据的权限

 **错误代码：** 403 
  
 **将在什么位置看到此消息：** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs. 
  
 **原因：** 授权代码失败，因为尝试连接到模板应用的用户没有访问此数据的授权级别。 
  
 **若要修复此错误：** 提供全局管理员、Exchange 管理员、Skype for Business 管理员、SharePoint管理员、全局读取者或报表读取者的用户的凭据，以连接到模板应用。   有关详细信息 [，请参阅](../add-users/about-admin-roles.md) 关于管理员角色。 
  
## <a name="refresh-failed"></a>刷新失败

 **将出现此消息的情况：** Power BI 中的电子邮件或刷新历史记录中的失败状态。 
  
 **原因：** 有时，连接到模板应用的用户的凭据会重置，并且不会在模板应用的连接设置中更新，从而导致用户看到刷新失败错误。 
  
 **若要修复此错误：** 在Power BI中，找到与"Microsoft 365分析"模板应用对应的数据集，选择"计划刷新"并提供管理员凭据。 
  
如果不起作用，请清除缓存，然后重新创建模板应用。
  
  
