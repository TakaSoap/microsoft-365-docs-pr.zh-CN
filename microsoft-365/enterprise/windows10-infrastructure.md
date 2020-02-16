---
title: 适用于 Microsoft 365 企业版的 Windows 10 企业版基础结构
description: 提供了在 Microsoft 365 企业版中将 Windows 10 企业版部署到电脑上所需步骤的高级别指南。
keywords: Microsoft 365，Microsoft 365 企业版，Microsoft 365 文档，Windows 10 企业版，部署
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 72a355a524ff3dd56300566ff228b5ff5007c6cb
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085532"
---
# <a name="phase-3-windows-10-enterprise"></a>第 3 阶段：Windows 10 企业版

![第 3 阶段：Windows 10 企业版](../media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 企业版包括 Windows 10 企业版，为您提供用于执行更多和保持安全保护的工具。 Windows 10 企业版：

- **集成为简单起见**-充分利用云的功能来帮助降低管理当今新式 IT 设备环境的复杂性，而不考虑大小。
- **具有智能安全性**-它是最安全的 Windows 发布，具有旨在协同工作以更好地保护组织的智能安全功能。
- **实现创造性和团队合作**-解锁创造性和团队合作，以提供用户最喜爱的工作体验。

您需要了解部署 Windows 10 操作系统的不同方法，并为您的组织选择正确的方法。 根据你的 Microsoft 365 企业版订阅，还需要配置 Windows 10 服务和安全功能，以充分利用 Windows 10。

>[!Note]
>若要同时部署 Windows 10 企业版和 Office 365 专业增强版，并迁移到[新式桌面](https://www.microsoft.com/microsoft-365/modern-desktop)，请参阅[新式桌面部署中心](https://aka.ms/howtoshift)。
>

## <a name="windows-10-deployment"></a>Windows 10 部署

您可以通过多种方式为您的组织部署 Windows 10 企业版。 在这里，我们将重点介绍如何通过这些新式部署方案配置和部署 Windows 10 企业版映像。

| 部署方案 | 何时使用 |
|:--- |:--- |
| [使用 Microsoft 终结点配置管理器作为就地升级](windows10-deploy-inplaceupgrade.md) | 如果需要将 Windows 7 或 Windows 8.1 计算机升级到<a href="https://aka.ms/windows-10-release-information" target="_blank">当前版本</a>的 Windows 10 企业版，并且您的计算机当前是使用<a href="https://docs.microsoft.com/configmgr/core/understand/introduction" target="_blank">配置管理器（当前分支）</a>管理的，请选择此选项。 |
| [使用 Windows Autopilot](windows10-deploy-autopilot.md) | 如果要设置 Windows 10 企业版、版本1703或更高版本预安装的新 Windows 计算机，请选择此选项。 最终用户将使用所需的配置来启动安装程序，方法是输入其工作或学校帐户凭据。 |

如果这些部署方案不能满足您组织的需求，您可以了解其他方案并了解每个方案在[Windows 10 部署方案](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)中的功能和限制。 也可以自行<a href="https://aka.ms/planforwin10deployment" target="_blank">计划 Windows 10 部署</a>。

您可以通过以下文章了解有关 Windows 10 的详细信息：

- [Microsoft 365 Enterprise 产品页](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [部署和更新 Windows 10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>其他服务和功能
作为 Windows 10 企业版部署的一部分，您可以添加这些额外的服务和功能。

### <a name="windows-analytics"></a>Windows Analytics

Windows 使用诊断数据提供丰富的可操作信息，以帮助您深入了解操作效率以及环境中 Windows 10 设备的运行状况。

* 升级准备情况-升级准备情况将帮助您移动到 Windows 10，并在新的 Windows 10 功能更新中保持最新状态。 
* 更新合规性-更新合规性面向希望获取其所有 Windows 10 设备的整体视图的 IT 管理员，而无需任何其他基础结构要求。
* 设备运行状况-你可以使用设备运行状况主动检测并修正最终用户影响的问题。

有关详细信息，请参阅[Windows Analytics 概述](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview)。

### <a name="windows-security"></a>Windows 安全

Windows 10 提供了一些功能，可帮助保护抵御威胁、帮助保护设备和帮助访问控制。 使用 Windows 10 时，你可以从一开始就获得保护设备的关键安全功能。 Microsoft 365 E3 添加了诸如 Windows Hello 企业版、Windows Defender 应用程序控制和 Windows 信息保护等安全功能。 使用 Microsoft 365 E5，你可以从 Microsoft 365 E3 security 和基于云的安全功能以及 Microsoft Defender 高级威胁防护中获得所有保护。 

若要了解有关使用 Windows 10 企业版获取的安全功能的详细信息，并获取有关如何部署、管理、配置三种关键安全功能以及排除这些问题的指导，请参阅[步骤5：部署 Windows 10 企业版安全功能](windows10-enable-security-features.md)。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何对 Microsoft 365 企业版执行操作

查看并了解公司如何[部署 Windows 10 企业版，以及如何使用强大的身份验证、Intune 和 Microsoft DEFENDER ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6)。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 是如何使用 Microsoft 365 企业版的

请参阅 Contoso Corporation，它是一个虚构但具有代表性的多国企业，[部署了 Windows 10 企业版](contoso-win10.md)。

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![第 1 步](../media/stepnumbers/Step1.png)| [为 Windows 10 企业版准备组织](windows10-prepare-your-org.md) |
