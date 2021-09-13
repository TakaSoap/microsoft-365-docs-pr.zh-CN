---
title: 部署Microsoft 365 Lighthouse基线
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (MSP) 使用Microsoft 365 Lighthouse，了解如何部署Microsoft 365 Lighthouse基线。
ms.openlocfilehash: 62fc9afcbf10a0cd77c2fe2d2f7140b5197dd42a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59171296"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a>部署Microsoft 365 Lighthouse基线 

> [!NOTE]
> 本文中所述的功能在预览版中，可能会更改，并且仅对满足要求 [的合作伙伴可用](m365-lighthouse-requirements.md)。 如果你的组织没有此Microsoft 365 Lighthouse，请参阅[注册Microsoft 365 Lighthouse。](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse基线，您可以部署标准托管租户配置，以确保客户租户中的用户、设备和数据安全。 Lighthouse 有六种标准的默认基线配置：

- 要求管理员使用 MFA
- 要求最终用户使用 MFA
- 阻止旧式身份验证
- 在 Azure AD Microsoft Endpoint Manager中设置设备注册
- 为设备配置 Defender 防病毒Windows策略
- 为设备配置Windows策略

## <a name="before-you-begin"></a>开始之前

确保你和客户租户满足要求中所列的要求[Microsoft 365 Lighthouse。](m365-lighthouse-requirements.md)

## <a name="learn-more-about-the-default-baseline"></a>详细了解默认基线

从 **左侧导航** 窗格中选择"比较基准"以打开"比较基准"页。 你将看到默认基线已添加到默认租户组， (租户) 。 若要查看默认基线配置，请选择" **查看比较基准** "以打开"默认比较基准"页。 配置作为部署步骤列出。 选择任意部署步骤以查看部署详细信息和用户影响。

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="Default baseline page.>。":::

## <a name="deploy-a-baseline-configuration"></a>部署基线配置  

1. 在左侧导航页中，选择"租户"以查看已载入租户的列表。

2. 选择要将基线配置部署到的租户。

3. 选择 **"部署计划** "选项卡以查看基线中已添加到租户部署计划的所有部署步骤。

4. 选择部署步骤以打开部署步骤页。

5. 选择 **"应用** "将所选部署步骤应用到租户。 如果部署步骤指示"此操作需要手动步骤"，请确保完成手动步骤，以便正确应用部署步骤。

## <a name="related-content"></a>相关内容

[使用基线部署标准租户配置的](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) 概述 (文章) \
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) 