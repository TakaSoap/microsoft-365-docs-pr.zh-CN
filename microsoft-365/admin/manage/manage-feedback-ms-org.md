---
title: 为组织管理 Microsoft 反馈
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
description: 管理你的用户可以向 Microsoft 发送有关 Microsoft 产品的反馈。
ms.openlocfilehash: 8cd20b1a6138f389ba996bdaee8cae8ae24d2974
ms.sourcegitcommit: 601ab9ad2b624e3b5e04eed927a08884c885c72a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2022
ms.locfileid: "64403558"
---
# <a name="manage-microsoft-feedback-for-your-organization"></a>为组织管理 Microsoft 反馈

作为 Microsoft 365 管理员，现在有几种策略可帮助您管理用户在使用 Microsoft 365 应用程序时的反馈收集和客户参与体验。 你可以针对每个策略在组织中创建和使用现有 Azure Active directory 组。 借助这些管理，你可以控制组织中不同部门向 Microsoft 发送反馈的方式。 Microsoft 会审核客户提交的所有反馈，并使用此反馈改进产品。 将反馈体验保持 **打开** 可让你查看用户关于他们使用的 Microsoft 产品的意见。 我们从你的用户收集的反馈将很快在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心。</a>

若要了解有关反馈类型以及 Microsoft 如何使用用户反馈的信息，请参阅 [了解组织的 Microsoft 反馈](../misc/feedback-user-control.md)。

下表显示了当前连接到反馈策略表所示的反馈策略的应用和服务。 有关屏幕截图示例，请参阅下表。

|**Apps & Services**|**产品内反馈** <br> |**产品内调查** <br> |**元数据集合** <br> |**客户参与度** <br> |
|:-----|:-----|:-----|:-----|:-----|
|**Access**|是|是|是|是|
|**Excel**|是|是|是|是|
|**Office.com**|即将推出|即将推出|即将推出|即将推出|
|**OneNote**|是|是|是|是|
|**OneDrive**|[某些设置当前由其他控件管理。](/onedrive/disable-contact-support-send-feedback)||||
|**Outlook**|即将推出|即将推出|即将推出|即将推出|
|**PowerPoint**|是|是|是|是|
|**项目**|即将推出|即将推出|即将推出|即将推出|
|**发布程序**|是|是|是|是|
|**SharePoint**|[某些设置当前由其他控件管理。](/powershell/module/sharepoint-online/set-spotenant)||||
|**Teams**|[某些设置当前由其他控件管理。](/microsoftteams/manage-feedback-policies-in-teams)||||
|**Word**|是|是|是|是|
|**Visio**|是|是|是|是|
|**Yammer**|是|是|是|是|

[有关产品内调查和反馈的一些示例，请参阅此处。](/microsoft-365/admin/misc/feedback-user-control#in-product-surveys)

**元数据集合**

:::image type="content" source="../../media/feedback-metadata2.png" alt-text="Screenshot： Feedback page showing metadata example":::

**客户参与度**

:::image type="content" source="../../media/feedback-in-product-customer-engagement.png" alt-text="屏幕截图：产品内客户研究问题示例":::

## <a name="before-you-begin"></a>准备工作

你的设备必须采用最低内部版本号，以使用这些策略。 有关详细信息，请参阅下表。

|**内部版本#**|**Win32**|**iOS**|**Android**|**Mac**|**Web**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|产品内反馈|至少为版本 2010|至少为 2.42|至少 16.0.13328|至少为 16.42|公开可用|
|产品内调查|至少为版本 2010|至少为 2.42|至少 16.0.13426|至少为 16.42|挂起推出|
|元数据集合|至少为版本 2010|至少为 2.42|至少 16.0.13328|至少为 16.42|公开可用|
|客户参与度|至少为版本 2010|至少为 2.42|至少 16.0.13426|至少为 16.42|挂起推出|

## <a name="specific-policies-you-can-configure"></a>可以配置的特定策略

### <a name="feedback-policies"></a>反馈策略

|**策略名称**|**默认状态**|**控件摘要**|
|:-----|:-----|:-----|
|允许用户向 Microsoft 提交反馈|打开|控制跨应用程序的反馈入口点|
|允许用户接收和响应来自 Microsoft 的产品内调查|打开|控制产品内的调查提示|
|允许用户在向 Microsoft 提交反馈时包含屏幕截图和附件|关闭|确定用户可以决定通过反馈/调查提交哪些元数据|
|允许 Microsoft 跟进用户提交的反馈|关闭|确定用户能否与反馈/调查共享联系人信息|
|允许用户在向 Microsoft 提交反馈时包括日志文件和内容示例|关闭|确定用户可以通过反馈/调查决定提交的元数据|

## <a name="configure-policies"></a>配置策略

若要配置这些策略设置，可以使用 Office云策略服务。 有关详细信息，请参阅云策略[Office概述](/deployoffice/overview-office-cloud-policy-service)。 可以在云策略服务 UI 中搜索Office反馈"或"调查"，以查找配置策略设置。 

如果使用组策略，这些策略设置也可用。 若要使用这些策略设置，请至少下载 2021 年 3 月 22 日发布的管理模板文件 [ (ADMX/ADML) ](https://www.microsoft.com/download/details.aspx?id=49030)5146.1000 版本。

您可以在"用户配置\策略\管理模板\Microsoft Office 2016\隐私\信任中心"下找到这些策略设置。

> [!NOTE]
> 客户端应用程序需要几个小时才能更新。
