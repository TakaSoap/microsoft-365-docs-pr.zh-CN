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
description: 对于托管服务提供商 (MSP) 使用Microsoft 365 Lighthouse，了解如何部署Microsoft 365 Lighthouse基线。
ms.openlocfilehash: fa443fa025f0a1ffba6a230427797755611328a3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63324616"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a>部署Microsoft 365 Lighthouse基线 

Microsoft 365 Lighthouse基线，您可以部署标准托管租户配置，以确保客户租户中的用户、设备和数据的安全。 Lighthouse 有七种标准的默认基线配置：

- 要求管理员使用 MFA
- 要求最终用户使用 MFA
- 阻止旧式身份验证
- 在 Microsoft Endpoint Manager - Azure AD 中设置设备注册
- 为用户和更高版本Windows 10 Defender 防病毒策略
- 配置 Microsoft Defender 防火墙Windows 10及更高版本
- 配置适用于 Windows 10 及更高版本的合规性策略

## <a name="before-you-begin"></a>准备工作

确保你和客户租户满足要求 [for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md)。

## <a name="learn-more-about-the-default-baseline"></a>详细了解默认基线

从 **"浅** 楼"的左侧导航窗格中选择"比较基准"以打开"基线"页。 你将看到默认基线已添加到默认租户组， (租户) 。 若要查看默认基线配置，请选择" **查看比较基准** "以打开"默认比较基准"页。 配置作为部署步骤列出。 选择任意部署步骤以查看部署详细信息和用户影响。

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="&quot;默认基线&quot;页的屏幕截图。":::

## <a name="deploy-a-baseline-configuration"></a>部署基线配置  

1. In the left navigation pane in Lighthouse， select **Tenants** to view a list of your onboarded tenants.

2. 选择要将基线配置部署到的租户。

3. 选择 **"部署计划** "选项卡以查看基线中已添加到租户部署计划的所有部署步骤。

4. 选择部署步骤以打开部署步骤页。

5. 选择 **"查看和应用"** 将所选部署步骤应用到租户。 如果部署步骤指示"此操作需要手动步骤"，请确保完成手动步骤，以便正确应用部署步骤。

## <a name="related-content"></a>相关内容

[使用基线部署标准租户配置的](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) 概述 (文章) \
[Microsoft 365浅色租户页面概述 (](m365-lighthouse-tenants-page-overview.md)文章) \
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) \
[配置Microsoft 365 Lighthouse门户安全性 (](m365-lighthouse-configure-portal-security.md)文章)  