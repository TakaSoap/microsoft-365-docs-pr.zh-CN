---
title: 部署 Windows 10 企业安全功能
description: 在 Microsoft 365 Enterprise 的一部分部署 Pc 上的 Windows 10 Enterprise 所需的步骤提供高级指导。
keywords: Microsoft 365 Microsoft 365 企业版，Microsoft 365 文档，Windows 10 企业安全
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: d051f9e56d8e9986fbe0975c2bdc6c606b32a444
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866039"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>步骤 5： 部署 Windows 10 企业安全功能

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 提供了功能来帮助保护抵御威胁，帮助您保护您的设备，并帮助访问控制。 

若要了解有关这些技术的详细信息，请参阅：
* [访问保护](https://docs.microsoft.com/windows/access-protection/)-了解访问控制，S/MIME 数字证书，凭据 Guard 用户帐户控制虚拟智能卡，Windows Hello 业务、 高级安全 Windows 防火墙和的详细信息
* [设备安全](https://docs.microsoft.com/windows/device-security/)-包括 AppLocker、 BitLocker、 设备 Guard 和受信任的平台模块
* [威胁保护](https://docs.microsoft.com/windows/threat-protection/)-包括 Windows Defender 安全中心、 Windows Defender 高级威胁保护、 Windows Defender 防病毒、 Windows Defender 应用程序 Guard、 Windows Defender 智能屏幕上，和 Windows 信息保护

此步骤演示了如何部署、 管理、 配置和解决使用这些安全功能：

* [Windows Defender 防病毒](#windows-defender-antivirus)
* [Windows Defender 攻击防护](#windows-defender-exploit-guard)
* [Windows Defender 高级威胁防护](#windows-defender-advanced-threat-protection)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender 防病毒
Windows Defender 防病毒 (AV) 是内置 Windows 10 反恶意软件解决方案。它为台式机、 便携计算机和服务器提供了安全性和反恶意软件管理。有关 Windows Defender AV、 的最低硬件要求，以及如何管理此功能的详细信息，请参阅[Windows 10 和 Windows Server 2016 中的 Windows Defender 防病毒](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)。

如果您未使用 Windows Defender AV 为主要防病毒客户端，或者如果您还将使用 Windows Defender ATP，有一些注意事项您需要考虑在内。若要了解详细信息，请参阅[Windows Defender AV 兼容性](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility)。

### <a name="deployment-and-management"></a>部署和管理
部署和管理 Windows Defender AV，请按照下面的指南操作：

* [部署、 管理和 Windows Defender AV 报告](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [管理和配置工具的参考主题](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>配置
用户可以配置的功能的数量。人员的详细信息，请参阅以下资源：

* [配置 Windows Defender AV 功能](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [管理和配置工具的参考主题](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

以帮助了解配置选项，请参阅此列表的所有设置 （如定义其组策略配置）：[使用组策略设置来配置和管理 Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

您可以使用[Windows Defender 防病毒保护评估指南](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus)有助于评估的保护级别和 Windows Defender AV 在您的网络影响。这也会很有用创建初始配置或作为快速入门指南，并定期更新用于配置和启用功能，以确保最大保护提供最有用的建议。

### <a name="reporting"></a>报告
您可以获取使用配置工具，如 System Center Configuration Manager 或 Microsoft Intune 报告。您还可以获取从更新合规性 (OMS) 或通过使用 Windows 事件日志中您 SIEM 报告。如果您具有 Windows Defender ATP 许可证，您可以获取 Windows Defender AV 检测到报告和执行基本的补救。人员的详细信息，请参阅以下资源：
* [部署、 管理和 Windows Defender AV 报告](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [报告 Windows Defender 防病毒保护](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Windows Defender ATP 门户的概述 （英文)](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>疑难解答
错误和事件代码的基本疑难解答的信息，请参阅[查看事件日志和错误代码，以解决 Windows Defender AV 的问题](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)。

您还可以使用 Windows Defender 安全智能提交系统提交问题 （如误报）。若要了解如何，请参阅[向 Microsoft 提交问题](https://www.microsoft.com/wdsi/filesubmission)。

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender 攻击防护
Windows Defender 利用 Guard 是一组新的 Windows 10 主机入侵防护功能。有关 Windows Defender 利用 Guard、 的最低硬件要求，以及如何管理此功能的详细信息，请参阅[Windows Defender 利用 Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)。

### <a name="deployment-management-and-configuration"></a>部署、 管理和配置
若要部署、 管理和配置 Windows Defender 利用 Guard，请按照下面的指南：
* [利用保护](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [攻击面保护](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [网络保护](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [控制文件夹访问](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

一系列评估主题可用来帮助评估的保护级别和 Windows Defender 利用保护的网络上的影响。也可以是在创建初始配置或作为快速入门指南有用和主题和指南定期将更新以用于配置和启用功能，以确保最大保护提供最有用的建议。有关详细信息，[利用 Guard 评估 Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard)。

### <a name="reporting"></a>报告
您可以获取使用配置工具，如 System Center Configuration Manager 或 Intune 报告。您还可以获得通过使用 Windows 事件日志中您 SIEM 报告。如果您具有 Windows Defender ATP 许可证，您可以获取 Windows Defender AV 检测到报告和执行基本的补救。人员的详细信息，请参阅以下资源：
* [查看 Windows Defender 利用 Guard 事件](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Windows Defender ATP 门户的概述 （英文)](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>疑难解答
可以执行基本故障排除或 （可选） 使用.cab 文件提供 Microsoft 并使用 Windows Defender 安全智能提交系统提交问题 （如误报）。若要了解如何，请参阅[向 Microsoft 提交问题](https://www.microsoft.com/wdsi/filesubmission)。


<a name="windows10-sec-atp"></a>
## <a name="windows-defender-advanced-threat-protection"></a>Windows Defender 高级威胁防护
Windows Defender ATP，仅适用于 Microsoft 企业 E5 365 计划，使企业客户，能够检测、 调查和响应他们的网络上的高级威胁的安全服务。有关 Windows Defender ATP、 的最低硬件要求，以及如何管理此功能的详细信息，请参阅：

* [Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [最低要求](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>部署、 管理和配置
若要部署 Windows Defender ATP，您需要确保您具有 Windows 许可证的权限。在验证已正确许可证后，您需要决定将存储数据的地理位置。之后，您可以开始加入到服务的终结点。

这些步骤的详细信息，请参阅以下主要的主题： 

* [验证授权设置并完成设置](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [数据存储和隐私](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [板载终结点和安装程序访问](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>检测、 调查、 响应
后成功入职培训终结点到服务，您可以启动调查从各种仪表板的警报。一旦已调查通知，您可以采取响应操作通知。 

有关如何执行这些操作的详细信息，请参阅：
* [Windows Defender ATP 门户的概述 （英文)](https://go.microsoft.com/fwlink/?linkid=861596)
* [使用 Windows Defender ATP 门户](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [采取响应措施](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>与其他产品和工具的集成
Windows Defender ATP 集成，并支持各种其他产品和工具以扩展其安全功能。 

工具和其他产品的详细信息，请参阅：
* [SIEM 工具](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [创建自定义通知](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [使用 Api](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [生成 Power BI 报表](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>疑难解答
您可能会遇到问题时入职培训或同时使用该产品。有关如何解决问题的详细信息，请参阅：
* [解决入职培训问题](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [疑难解答 Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>后续步骤

[Windows 10 企业基础结构退出条件](windows10-exit-criteria.md)
