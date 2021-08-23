---
title: 使用基线部署标准租户配置的概述
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
description: 对于托管服务提供商 (MSP) ，Microsoft 365 Lighthouse使用基线部署标准租户配置。
ms.openlocfilehash: 5eea1deae1c8cf56315e121baa29273fc98feca8
ms.sourcegitcommit: 00a8a3376ea02770143af9a80cbe17a2b62636e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2021
ms.locfileid: "58365197"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a>使用基线部署标准租户配置的概述 

> [!NOTE]
> 本文中所述的功能在预览版中，可能会更改，并且仅对满足要求 [的合作伙伴可用](m365-lighthouse-requirements.md)。 如果你的组织没有Microsoft 365 Lighthouse，请参阅[注册Microsoft 365 Lighthouse。](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse基线提供了一种可重复且可扩展的方法，可让你跨多个客户租户Microsoft 365和管理安全设置。 基线还通过保护用户、设备和数据的配置帮助监视核心安全策略和租户合规性标准。

旨在帮助合作伙伴按自己的节奏实现客户采用安全性，Microsoft 365 Lighthouse为服务提供一组标准基线参数和预定义Microsoft 365配置。 这些安全配置可帮助衡量租户Microsoft 365安全性和合规性进度。

可以从内部查看默认基线及其部署Microsoft 365 Lighthouse。 若要将基线应用于租户，请选择左侧导航 **窗格中的** "租户"，然后选择租户。 接下来，转到"部署 **计划"** 选项卡，实现所需的基线。

## <a name="standard-baseline-security-templates"></a>标准基线安全模板

Microsoft 365 Lighthouse工作负载的标准基线配置旨在帮助所有托管租户达到可接受的安全范围和合规性状态。

下表中的基线配置是标准配置，Microsoft 365 Lighthouse默认基线。<br><br>

| 基线配置 | 说明 |
|--|--|
| 要求管理员使用 MFA | 仅报告条件访问策略，要求对管理员进行多重身份验证。 所有云应用程序都需要它。 |
| 要求最终用户使用 MFA | 仅报告条件访问策略，要求用户进行多重身份验证。 所有云应用程序都需要它。 |
| 阻止传统身份验证 | 用于阻止旧客户端身份验证的仅报告条件访问策略。 |
| 在 Azure AD Microsoft Endpoint Manager注册设备 | 设备注册，允许租户设备注册Microsoft Endpoint Manager。 这是通过设置 Azure Active Directory 和 Microsoft Endpoint Manager 之间的自动注册Microsoft Endpoint Manager。 |
| 防病毒 (AV) 策略配置 | 具有预配置Windows配置的设备配置配置文件Microsoft Defender 防病毒配置文件。 |
| 窗口 10 合规性策略设置 | 一Windows预配置设置的设备策略，以满足基本合规性要求。 |

## <a name="related-content"></a>相关内容

[部署Microsoft 365 Lighthouse比较基准](m365-lighthouse-deploy-baselines.md) (文章) \
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) 
