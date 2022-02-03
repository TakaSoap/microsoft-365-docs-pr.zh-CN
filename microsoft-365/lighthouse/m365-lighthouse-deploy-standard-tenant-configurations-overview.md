---
title: 使用基线部署标准租户配置的概述
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
description: 对于托管服务提供商 (使用) 托管服务提供商Microsoft 365 Lighthouse，了解如何使用基线部署标准租户配置。
ms.openlocfilehash: 23ebc0d0562cf06bd92456e18c0833a61c564673
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "62321935"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a>使用基线部署标准租户配置的概述 

> [!NOTE]
> 本文中所述的功能为预览版，可能会更改，并且仅对满足要求的合作伙伴 [可用](m365-lighthouse-requirements.md)。 如果你的组织没有此Microsoft 365 Lighthouse，请参阅[注册Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。

Microsoft 365 Lighthouse基线提供了一种可重复且可扩展的方法，让你能够跨多个客户租户Microsoft 365和管理安全设置。 基线还有助于使用保护用户、设备和数据的配置监视核心安全策略和租户合规性标准。

为了帮助客户按自己的节奏采用安全性，Lighthouse 提供了一组标准的基线参数和预定义的配置，Microsoft 365服务。 这些安全配置可帮助衡量租户Microsoft 365安全性和合规性进度。

可以从 Lighthouse 内查看默认基线及其部署步骤。 若要将基线应用于租户 **，请选择左侧** 导航窗格中的"租户"，然后选择租户。 接下来，转到"部署 **计划"** 选项卡，实现所需的基线。

## <a name="standard-baseline-security-templates"></a>标准基线安全模板

安全工作负载的 Lighthouse 标准基线配置旨在帮助所有托管租户达到可接受的安全范围和合规性状态。

下表中的基线配置与 Lighthouse 默认基线一起采用标准配置。<br><br>

| 基线配置 | 说明 |
|--|--|
| 要求管理员使用 MFA | 要求管理员多重身份验证的条件访问策略。 所有云应用程序都需要它。 |
| 要求最终用户使用 MFA | 要求用户进行多重身份验证的条件访问策略。 所有云应用程序都需要它。 |
| 阻止传统身份验证 | 用于阻止旧版客户端身份验证的条件访问策略。 |
| 设置设备注册 | 设备注册，允许租户设备注册Microsoft Endpoint Manager。 这是通过设置用户和用户之间的自动注册Azure Active Directory Microsoft Endpoint Manager。 |
| 配置Microsoft Defender 防病毒Windows 10及更高版本 | 具有预配置Windows配置的设备配置配置文件Microsoft Defender 防病毒设置。 |
| 为设备配置设备合规性策略Windows 10及更高版本 | 一Windows预配置设置的设备策略，以满足基本合规性要求。 |

## <a name="related-content"></a>相关内容

[Deploy Microsoft 365 Lighthouse baselines (](m365-lighthouse-deploy-baselines.md) article) \
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) 
