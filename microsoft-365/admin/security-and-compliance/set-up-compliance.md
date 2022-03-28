---
title: 提高威胁防护Microsoft 365 商业高级版
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 设置合规性功能以防止数据丢失，并帮助保护你和客户敏感信息的安全。
ms.openlocfilehash: baac8bc1ad9a425ad7219a1e76949286858f60e0
ms.sourcegitcommit: 601ab9ad2b624e3b5e04eed927a08884c885c72a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2022
ms.locfileid: "64403698"
---
# <a name="set-up-compliance-features"></a>设置合规性功能

你的Microsoft 365 商业高级版订阅包括合规性和隐私功能。 这些功能有助于保护公司数据，并保护你和客户敏感信息的安全。 本文旨在帮助你开始使用合规性功能。

## <a name="before-you-begin"></a>准备工作

请确保在角色分配中分配了以下角色Azure Active Directory：

- 全局管理员
- 合规管理员

若要了解更多信息，请参阅 [角色入门页面](../add-users/admin-roles-page.md)。

## <a name="use-compliance-manager-to-get-started"></a>使用合规性管理器开始

:::image type="content" source="../../business-premium/media/m365bp-compliancemanager.png" alt-text="合规性管理器在Microsoft 365 商业高级版。":::

Microsoft 365 商业高级版合规性管理器，可帮助你开始设置合规性功能。 这些功能包括数据丢失防护、信息管理和内部风险管理等。 合规性管理器可以通过突出显示建议、合规性分数以及提高分数的方法来节省时间。

下面是如何开始：

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并登录。

2. 在导航窗格中，选择" **合规性管理器"**。

3. 在" **概述"** 选项卡上，查看信息。 选择项目或链接以查看详细信息，或采取一些操作，例如配置 DLP (数据丢失) 策略。 例如，在" **影响分数** 的解决方案"部分，您可以选择"剩余 **操作"列中** 的链接。

   :::image type="content" source="../../business-premium/media/m365bp-compliancesolutions.png" alt-text="影响分数窗格的解决方案的屏幕截图。":::

   该操作将您带至" **改进操作** "选项卡，该选项卡针对所选的项目进行筛选。 本示例中，我们将了解要配置的 DLP 策略。

   :::image type="content" source="../../business-premium/media/m365bp-dlppoliciestoconfigure.png" alt-text="要配置的 DLP 策略的屏幕截图。":::

4. 在" **改进操作"** 选项卡上，选择一个项目。 在我们的示例中，我们选择了"创建自定义 **DLP 策略或个人身份信息"**。 页面加载提供有关要配置的策略详细信息。

   :::image type="content" source="../../business-premium/media/m365bp-dlppolicyinfo.png" alt-text="有关客户内容的 DLP 策略信息的屏幕截图。":::

   按照屏幕上的信息设置 DLP 策略。

有关适用于企业Microsoft 365合规性功能Microsoft 365[合规性文档](../../compliance/index.yml)。

## <a name="use-sensitivity-labels"></a>使用敏感度标签

敏感度标签可用于 Office 应用 (如 Outlook、Word、Excel 和 PowerPoint) 。 标签示例包括：

- 一般
- 个人
- Private
- 机密

但是，也可以为公司定义其他标签。

阅读以下文章，了解敏感度标签：

1. [什么是敏感度标签？](../../compliance/sensitivity-labels.md)

2. [开始创建敏感度标签](../../compliance/get-started-with-sensitivity-labels.md)

3. [发布敏感度标签及其策略](../../compliance/create-sensitivity-labels.md)

4. [向公司人员展示如何使用敏感度标签](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)