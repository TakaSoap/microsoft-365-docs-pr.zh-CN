---
title: Microsoft 365 enterprise 的 Windows 10 企业基础结构
description: 在 Microsoft 365 Enterprise 的一部分部署 Pc 上的 Windows 10 Enterprise 所需的步骤提供高级指导。
keywords: Microsoft 365 Microsoft 365 企业版，Microsoft 365 文档，Windows 10 企业部署
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 80d7c1b56434647387b9c428ca07effdff929abf
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865403"
---
# <a name="phase-3-windows-10-enterprise"></a>阶段 3：Windows 10 企业版

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 企业版包括 Windows 10 Enterprise，为您提供的工具来执行操作的详细信息，并保持安全。Windows 10 Enterprise:

- **为了简单起见集成**的工具在云中的强大功能可帮助减少管理今天的复杂性的现代 IT 设备环境，无论大小。
- **具有智能安全**-以往任何时候都是最安全的版本的 Windows、 智能安全功能，旨在协同工作以更好地保护您的组织。
- **使创造和团队协作**-解除对创造和团队合作，以提供最高效体验的用户和 IT 将喜欢的事物。

您需要了解不同的方式可以部署 Windows 10 操作系统，然后选择适合您的组织。根据您的 Microsoft 365 企业版订阅，也有 Windows 10 服务和安全功能，您需要配置为充分利用 Windows 10。

Windows 10 启用 Microsoft 365 企业版这些战略业务方案：

- 通过使员工能够发现、共享和改进整个组织的文件、信息和想法，充分利用集体知识和专长
- 随时随地跨设备安全工作，在保持灵活工作方式的同时实现更多功能
- 提供尽可安心的控件和可见性，行业认证达标且符合全球标准
- 保护信息并降低数据丢失的风险
- 检测防范外部威胁-监视器报告和分析活动迅速做出反应以提供组织的安全
- 保护您的用户和其帐户
- 帮助组织增强隐私和合规性以符合一般数据保护条例 (GDPR)
- 获取最新信息并使用最新的桌面软件和设备，同时降低安全风险并最大限度提高 IT 效率

有关详细信息，请参阅[使用 Microsoft 365 实现数字化化转型](http://transform.microsoft.com)。 

>[!Note]
>若要同时部署 Windows 10 企业版和 Office 365 专业增强版，并迁移到[新式桌面](https://www.microsoft.com/microsoft-365/modern-desktop)，请参阅[新式桌面部署中心](http://aka.ms/howtoshift)。
>

## <a name="windows-10-deployment"></a>Windows 10 部署

有多种方法可以为您的组织中部署 Windows 10 Enterprise。在这里，我们将专注于如何配置和部署 Windows 10 Enterprise 映像通过这些现代的部署方案。

| 部署方案 | 何时使用它 |
|:--- |:--- |
| [使用 System Center Configuration Manager 作为就地升级](windows10-deploy-inplaceupgrade.md) | 如果您需要升级 Windows 7 或<a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager （当前分支）</a>与当前托管到 Windows 10 Enterprise 的<a href="https://aka.ms/windows-10-release-information" target="_blank">当前版本</a>的 Windows 8.1 计算机和您的计算机，请选择此选项。 |
| [使用 Windows 自动执行某些操作](windows10-deploy-autopilot.md) | 如果要设置新有 Windows 10 Enterprise 1703 或更高版本预安装版本的 Windows 计算机，请选择此选项。最终用户将启动安装程序使用通过输入其工作所需的配置或学校帐户凭据。 |

如果这些部署方案不适合您组织的需要，您可以了解其他方案，并了解功能和限制的[Windows 10 部署方案](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)中的每个。您还可以在您自己的<a href="https://aka.ms/planforwin10deployment" target="_blank">Windows 10 部署规划</a>。

您可以使用这些文章了解有关 Windows 10 的详细信息：

- [Microsoft 365 Enterprise 产品页](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [部署和更新 Windows 10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>其他服务和功能
作为 Windows 10 企业的部署的一部分，您可以添加这些其他服务和功能。

### <a name="windows-analytics"></a>Windows Analytics

Windows 使用诊断数据提供丰富的、 可操作的信息，以帮助您获得深度见解运营效率和您的环境中的 Windows 10 设备的运行状况。

* 升级准备-升级准备将帮助您将移动到 Windows 10 和获得最新的 Windows 10 功能更新。 
* 更新合规性-更新合规性被面向 IT 管理员用户想要获取其所有 Windows 10 设备，无需任何其他基础结构要求的整体视图。
* 设备运行状况-您可以使用设备运行状况主动检测和修正最终用户产生影响的问题。

有关详细信息，请参阅[Windows 分析 Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) 。

### <a name="windows-security"></a>Windows 安全

Windows 10 提供了功能来帮助保护抵御威胁，帮助您保护您的设备，并帮助访问控制。使用 Windows 10，您可以获取从开始保护您的设备右侧的重要的安全功能。Microsoft 365 E3 将添加业务、 Windows Defender 应用程序控制和 Windows 信息保护安全功能，如 Windows Hello。与 Microsoft 365 E5 从 Microsoft 365 E3 安全以及基于云的安全功能和 Windows Defender 高级威胁保护获取所有保护。 

若要了解有关您获取 Windows 10 Enterprise 和获取指导如何部署、 管理、 配置和解决三个关键安全功能的安全功能的详细信息，请参阅[第 5 步： 部署 Windows 10 企业安全功能](windows10-enable-security-features.md)。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何使用 Microsoft 365 企业版

若要查看 Microsoft 内部并了解公司如何规划、 部署，以及管理更新的 Windows 10，请参阅：

- [为组织准备 Windows 10 无缝部署](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [在 Microsoft 中采用 Windows 作为服务](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [在 Microsoft 中将 Windows 10 部署为就地升级](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [使用 Windows Hello 企业版实现功能强大的用户身份验证](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- [Windows 10 部署：来自 Microsoft IT 部门的提示和技巧](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT)（视频）
- [Windows Defender ATP 有助于检测到复杂的威胁](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- [使用 Windows Defender 和 Windows Defender ATP 保护现代企业的安全](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP)（视频）

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 如何使用 Microsoft 365 企业版

请参阅如何 Contoso Corporation、 虚构但代表性跨国企业、[部署 Windows 10 Enterprise](contoso-win10.md)。

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [准备您的组织 Windows 10 Enterprise](windows10-prepare-your-org.md) |
