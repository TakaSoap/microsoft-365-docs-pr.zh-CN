---
title: 比较设备合规性策略设置
f1.keywords: NOCSH
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
description: 对于托管服务提供商 (MSP) 使用Microsoft 365 Lighthouse，了解如何比较设备合规性策略设置。
ms.openlocfilehash: 5e4fc396e2ea1e1cce576f6064f4239179db33cc
ms.sourcegitcommit: 6e43aeff217afe97876137b1ead8df26db6e9937
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "62859249"
---
# <a name="compare-device-compliance-policy-settings"></a>比较设备合规性策略设置

> [!NOTE]
> 本文中所述的功能为预览版，可能会更改，并且仅对满足要求的合作伙伴 [可用](m365-lighthouse-requirements.md)。 如果你的组织没有此Microsoft 365 Lighthouse，请参阅[注册Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。

Microsoft 365 Lighthouse，可以在单个视图中查看租户中的合规性策略。 通过比较策略，可以推动租户的安全性和标准化。 你可以筛选视图以查看已配置的设置 (配置与未在) 配置的设置、不同配置中的设置或匹配的设置。 还可以搜索特定设置，以查看它们如何跨策略进行比较。

## <a name="before-you-begin"></a>开始之前

确保设备具有Microsoft Intune许可证，并且已注册MICROSOFT ENDPOINT MANAGER (MEM) 。

## <a name="compare-policy-settings"></a>比较策略设置

1. In the left navigation pane in Lighthouse， select **Devices**.

2. 选择“**策略**”选项卡。

3. 从 **"筛选器** "下拉列表中，选择操作系统或平台。

   > [!NOTE]
   > 只能将策略与相同的操作系统或平台进行比较。

4. 从筛选列表中，最多选择三个要比较的策略。

5. 选择 **"比较"**。

你可以筛选结果以查看不同的 **设置、匹配** 设置 **或** 配置 **设置。**

## <a name="configure-a-policy-setting"></a>配置策略设置

1. In the left navigation pane in Lighthouse， select **Devices**.

2. 选择“**策略**”选项卡。

3. 从列表中选择策略名称。

4. 从"策略详细信息"窗格中，选择"**在策略窗格中查看此Microsoft Endpoint Manager**"。

5. 在 MEM 中，根据需要编辑策略设置。

## <a name="next-steps"></a>后续步骤

进行策略调整时，请确保根据当前基线设置评估更改。 有关详细信息，请参阅使用基线 [部署标准租户配置的概述](m365-lighthouse-deploy-standard-tenant-configurations-overview.md)。

## <a name="related-content"></a>相关内容

[什么是 Intune 中的设备注册?](/mem/intune/enrollment/device-enrollment)  (文章)   
[使用合规性策略为使用 Intune](/mem/intune/protect/device-compliance-get-started) 管理的设备设置规则， (文章)   
[使用基线部署标准租户配置](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) 概述 (文章) 
