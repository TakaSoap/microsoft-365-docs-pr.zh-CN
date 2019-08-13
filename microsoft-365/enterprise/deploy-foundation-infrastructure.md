---
title: Microsoft 365 企业版底层基础结构
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解组织中部署 Microsoft 365 企业版底层基础结构（也称为核心部署）的主要阶段。
ms.openlocfilehash: 0b54225d3ce9043564788e28ddd88426dae611e9
ms.sourcegitcommit: 86dba00cd786ac8ea761cdfcd85dfbd33e64d088
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2019
ms.locfileid: "36297912"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a>Microsoft 365 企业版底层基础结构

如果你是自行端到端部署 Microsoft 365 企业版，则应首先奠定坚实的基础，在此基础上，应用程序和服务可以在安全的环境中激发创造力和提高团队协作。 该底层有时称为*核心部署*。

对于为部署定义的端到端路径，你可以使用这些阶段来规划和部署 Microsoft 365 企业版的底层基础结构：

| | 阶段 | 结果 |
|:-------|:-----|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[阶段 1：网络](networking-infrastructure.md)| 网络已经过优化，以便访问 Microsoft 365 基于云的服务。 |
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[阶段 2：标识](identity-infrastructure.md)| 管理员帐户受到保护，用户和组经过同步，并且采用强用户身份验证。 |
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[阶段 3：Windows 10 企业版](windows10-infrastructure.md)| 现有基于 Windows 的计算机可以升级至 Windows 10 企业版，并且新设备已安装了 Windows 10 企业版。 |
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[阶段 4：Office 365 专业增强版](office365proplus-infrastructure.md)| 现有 Microsoft Office 用户可以升级到 Office 365 专业增强版。 |
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[阶段 5：移动设备管理](mobility-infrastructure.md)| 可以注册和管理你的设备。 |
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[阶段 6：信息保护](infoprotect-infrastructure.md)| 标签已准备好保护文档并且 Office 365 安全功能已启用。 |

将从最基本的阶段（网络和标识）开始，然后创建基础结构设置和组层，以：

- 在设备上安装最新、最安全的 Windows 版本，并保证其处于最新状态。
- 在设备上安装最新的 Microsoft Office 版本，并保证其处于最新状态。
- 管理组织的设备及其对应用的访问。
- 保护这些设备和云中的信息。

但是，你可以灵活地配置和部署阶段中的各个阶段和步骤，以满足你的 IT 资源和业务需求。

- **如果你是较小或较新的组织**，请根据需要按照各个阶段操作，以便有条不紊地构建基础结构。 有关针对非企业的简化部署，请单击[此处](deploy-foundation-infrastructure-non-enterprises.md)。

-  **如果你是企业组织**，请将阶段视作 IT 基础架构的层，而不是定义的路径，并确定如何更好地工作，以最终满足组织中每个层的要求。

在每个阶段结束时，你可以检查器退出条件，其中包括必须满足的必要条件以及可以考虑的可选条件。 每个阶段的退出条件可确保本地和云基础结构以及相应的端到端配置满足 Microsoft 365 企业版部署的要求。

如需查看内容的组织方式，请观看此短片。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

以下是 Microsoft 365 企业版整体部署指南中的底层基础结构：

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="at-a-glance"></a>概览

[Microsoft 365 企业版底层基础结构海报](http://aka.ms/m365efoundinfraposter)是一个可查看各阶段相关情况的中心位置：

- 所处阶段对管理员和用户的整体目标
- 服务、功能和工具
- 针对规划的关键设计决策
- 配置结果
- 新用户的载入进度
- 监视和更新方式

![](./media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.png)

要下载海报副本，请单击[此处](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)。


## <a name="infrastructure-configuration-vs-user-rollout"></a>基础结构配置与用户部署

底层基础结构是一组经过配置的软件和服务，如果针对某一用户将它们组合到一起，可以充分利用 Microsoft 365 企业版具有的全部功能和保护。 端到端部署旅程的最终目标是将此基础结构应用于所有用户及其基于 Windows 的设备。 

但是，必须注意的是，Microsoft 365 企业版底层基础结构与为用户部署软件和服务是不相关的。 ***你可以配置底层基础结构层，而无需将这些曾部署到所有用户中。***

可在将元素部署到组织办公室、区域或部门的众多用户之前配置、测试和试用底层基础结构的元素。

例如，你可以为以下对象创建设置：

| 阶段 | 结果 |
|:-------|:-----|
| 标识 | 帐户同步和适用于基于条件访问策略的组。 |
| Windows 10 企业版 | 将运行 Windows 7 或 Windows 8.1 的计算机自动升级到相应的 Windows 10 企业版的组。 |
| Office 365 专业增强版 | 为使用 Office 2010、Office 2013 或 Office 2016 的用户自动部署 Office 365 的组。 |
| 移动设备管理 | 适合于设备注册和基于设备的条件访问策略的组。 |
| 信息保护 | Office 365 敏感度和 Azure 信息保护标签和组。 |

准备好为用户部署此基础结构的元素时，你可以：

| 阶段 | 部署操作 |
|:-------|:-----|
| 标识 | 将用户帐户添加到基于标识的条件访问策略组。 |
| Windows 10 企业版 | 将帐户添加到组，以便为使用 Windows 7 或 Windows 8.1 的用户自动部署 Windows 10 企业版。 |
| Office 365 专业增强版 | 将用户帐户添加到组，以便为使用 Office 2010、Office 2013 或 Office 2016 的用户自动部署 Office 365 的组。 |
| 移动设备管理 | 将帐户添加到适合于设备注册和基于设备的条件访问策略的组。 |
| 信息保护 | 将用户帐户添加到信息保护标签组。 |

底层基础结构的阶段或元素完成、测试和试用之后，你可以为用户部署已安装的软件（例如 Windows 10 企业版和 Office 365 专业增强版）以及基于云的服务和保护（如设备注册和条件访问策略），以最适合你的业务目标和 IT 资源。

## <a name="deployment-and-project-management-strategies"></a>部署和项目管理策略

若要就如何为组织的试点用户和其他用户进对底层基础结构的不同阶段进行项目管理给出一些看法，请参阅[部署战略](deployment-strategies-microsoft-365-enterprise.md)。

## <a name="deployment-for-non-enterprises"></a>针对非企业的部署

如果你的组织规模较小，而 Microsoft 365 商业版不适合你，则请查看[针对非企业的部署](deploy-foundation-infrastructure-non-enterprises.md)。


## <a name="next-step"></a>后续步骤

| 我当前的境况 | 我需要达成的目标 |
|:-------|:-----|
| 我现在有针对 Office 365、企业移动性 + 安全性 (EMS) 或 Windows 10 企业版的基础结构。 | 请首先[用基础结构进行部署](deploy-with-existing-infrastructure.md)按照步骤了解各阶段的退出条件。 |
| 我要作为企业从头开始 | 通过[阶段 1：网络](networking-infrastructure.md)开启你的端到端部署旅程。 |
| 我要以非企业的身份从头开始 | 通过[针对非企业的部署](deploy-foundation-infrastructure-non-enterprises.md)开启你的端到端部署旅程。 |
