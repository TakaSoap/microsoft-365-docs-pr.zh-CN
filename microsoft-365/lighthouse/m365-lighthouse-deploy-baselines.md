---
title: 部署Microsoft 365 Lighthouse基线
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (使用) 托管服务提供商Microsoft 365 Lighthouse，了解如何部署Microsoft 365 Lighthouse基线。
ms.openlocfilehash: c4cef0b966e1c35d5b8d4f282e5eeee4cb76a998
ms.sourcegitcommit: 6e43aeff217afe97876137b1ead8df26db6e9937
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "62859297"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a>部署Microsoft 365 Lighthouse基线 

> [!NOTE]
> 本文中所述的功能为预览版，可能会更改，并且仅对满足要求的合作伙伴 [可用](m365-lighthouse-requirements.md)。 如果你的组织没有此Microsoft 365 Lighthouse，请参阅[注册Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。

Microsoft 365 Lighthouse基线，您可以部署标准托管租户配置，以确保客户租户中的用户、设备和数据的安全。 Lighthouse 有六种标准的默认基线配置：

- 要求管理员使用 MFA
- 要求最终用户使用 MFA
- 阻止旧式身份验证
- 在 Microsoft Endpoint Manager - Azure AD 中设置设备注册
- 为设备配置 defender 防病毒Windows策略
- 为设备配置Windows策略

## <a name="before-you-begin"></a>开始之前

确保你和客户租户满足 Requirements [for Microsoft 365 Lighthouse中列出的要求](m365-lighthouse-requirements.md)。

## <a name="learn-more-about-the-default-baseline"></a>详细了解默认基线

从 **左侧导航** 窗格中选择"比较基准"以打开"比较基准"页。 你将看到默认基线已添加到默认租户组， (租户) 。 若要查看默认基线配置，请选择" **查看比较基准** "以打开"默认比较基准"页。 配置作为部署步骤列出。 选择任意部署步骤以查看部署详细信息和用户影响。

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="&quot;默认基线&quot;页的屏幕截图>。":::

## <a name="deploy-a-baseline-configuration"></a>部署基线配置  

1. In the left navigation pane in Lighthouse， select **Tenants** to view a list of your onboarded tenants.

2. 选择要将基线配置部署到的租户。

3. 选择 **"部署计划** "选项卡以查看基线中已添加到租户部署计划的所有部署步骤。

4. 选择部署步骤以打开部署步骤页。

5. 选择 **"应用** "将所选部署步骤应用到租户。 如果部署步骤指示"此操作需要手动步骤"，请确保完成手动步骤，以便正确应用部署步骤。

## <a name="related-content"></a>相关内容

[使用基线部署标准租户配置的](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) 概述 (文章) \
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) 
