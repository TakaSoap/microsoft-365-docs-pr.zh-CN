---
title: 第 4 阶段：Microsoft 365 企业应用版
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 这些步骤用于为 Microsoft 365 企业版部署 Microsoft 365 企业应用版基础结构。
ms.openlocfilehash: 5143ef8872a7ebd119e77c6148288828a39e20d9
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011943"
---
# <a name="phase-4-microsoft-365-apps-for-enterprise"></a>第 4 阶段：Microsoft 365 企业应用版

![第 4 阶段：Microsoft 365 企业应用版](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

** 这适用于 Microsoft 365 企业版和 Microsoft 365 教育版的 E3 和 E5 版本

Microsoft 365 企业版包括 Microsoft 365 企业应用版（即订阅版 Office）。 与 Office 2019 一样，Microsoft 365 企业应用版包含所有 Office 应用程序，这些应用程序直接安装在客户端设备上。 与 Office 2019 不同的是，Microsoft 365 企业应用版定期接收包含新功能的更新，并有基于用户的许可模型，可便于用户在多个设备上安装 Office。 如需了解更多详情，请参阅[关于 Microsoft 365 企业应用版](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)。

在此阶段，你将 Microsoft 365 企业应用版部署到客户端设备，作为 Microsoft 365 企业版的一部分。除了本指南之外，还建议使用 [Microsoft FastTrack](https://fasttrack.microsoft.com/office) 来帮助进行部署。 

如果已部署 Microsoft 365 企业应用版，请参阅此阶段的[退出条件](office365proplus-exit-criteria.md)，以确保它满足 Microsoft 365 企业版的必需条件。

>[!Note]
>若要同时部署 Windows 10 企业版和 Microsoft 365 企业应用版，请参阅[桌面部署中心](desktop-deployment-center-home.md)。
>

## <a name="step-1-assess-your-environment"></a>第 1 步：评估环境

部署 Microsoft 365 企业应用版前，请遵循[评估部署 Microsoft 365 应用版的环境和要求](https://docs.microsoft.com/DeployOffice/assess-microsoft-365-apps)中的指南。此评估包括系统要求、客户端设备的详细信息（如体系结构和所需语言）、许可要求、网络能力和应用程序兼容性。完成此评估将有助于你在计划部署过程中做出关键决策。

## <a name="step-2-plan-your-deployment"></a>步骤 2：规划部署

评估环境后，请遵循[计划部署 Microsoft 365 应用](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps)中的指南来创建部署计划。此计划包括做出以下决策： 

- 如何部署 Office，包括要使用哪种工具（如 Microsoft Endpoint Configuration Manager 或 Office 部署工具），以及从何处安装 Office
- 如何管理 Office 更新
- 使用哪个更新通道（Office 更新通道将控制用户接收其 Office 应用程序功能更新的频率）
- 要使用的 Office 安装程序包和部署组，包括应对什么样的用户安装哪些 Office 应用程序和语言

[规划文章](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps)列出了所有这些选项的最佳做法，包括管理部署、管理更新、定义安装程序包和创建部署组。 

## <a name="step-3-deploy"></a>步骤 3：部署

基于部署计划，选择所需的部署方式：

- **[使用 Configuration Manager 部署 Microsoft 365 应用](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-configuration-manager)：** 使用 Configuration Manager 来管理部署，并从网络上的分发点下载和部署 Office

- **[从云中部署 Microsoft 365 企业应用版](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-cloud)：** 使用 ODT 来管理部署，并在客户端设备上直接从 Office CDN 安装 Office
 
- **[在 Office 门户中自助安装 Microsoft 365 企业应用版](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365)：** 在 Office 门户中管理部署，并让用户在其客户端设备上直接从门户安装 Office

许多组织将针对不同用户使用这些选项组合。例如，组织可能使用配置管理器对大部分用户部署 Office，但对不经常连接到内部网络的一小组工作人员启用自助安装。 

如果组织使用配置管理器，建议升级到 Current Branch 并更新到当前版本。有关详细信息，请参阅[应使用配置管理器的哪个分支？](https://docs.microsoft.com/mem/configmgr/core/understand/which-branch-should-i-use)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何对 Microsoft 365 企业版执行操作

了解 Microsoft 专家如何[部署和管理 Microsoft 365 企业应用版更新](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7)。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 是如何使用 Microsoft 365 企业版的

看看 Contoso Corporation（有代表性的虚构跨国企业）是如何[部署 Microsoft 365 企业应用版](contoso-o365pp.md)的。

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>后续步骤

[Microsoft 365 企业应用版基础结构退出条件](office365proplus-exit-criteria.md)
