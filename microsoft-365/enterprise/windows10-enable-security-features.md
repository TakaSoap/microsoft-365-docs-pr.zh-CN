---
title: 部署 Windows 10 企业版安全功能
description: 提供了有关在作为 Microsoft 365 企业版一部分的电脑上部署 Windows 10 企业安全功能所需步骤的高级别指南。
keywords: Microsoft 365，Microsoft 365 企业版，Microsoft 365 文档，Windows 10 企业版，安全性
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: c1c39745b2dc891b4dc079ecd657eaf0d883af23
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627456"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>步骤5：部署 Windows 10 企业版安全功能

![第 3 阶段：Windows 10 企业版](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 提供了保护企业用户、停止威胁和防止数据丢失的安全功能。 

若要了解有关这些技术的详细信息，请参阅：

* [Identity protection](https://docs.microsoft.com/windows/security/identity-protection/) -了解 Windows Hello 企业版、Credential Guard 和访问控制。
* [威胁防护](https://docs.microsoft.com/windows/threat-protection/)-了解 Microsoft Defender 高级威胁防护、用于预防性保护的统一平台、入侵后检测、自动调查和响应。
* [信息保护](https://docs.microsoft.com/windows/security/information-protection/)-了解 BitLocker、Windows 信息保护和其他 windows 10 帮助保护企业数据的方式。 

此步骤向您展示了如何使用这些安全功能来部署、管理、配置和排除故障：

* [Windows Defender 防病毒](#windows-defender-antivirus)
* [Windows Defender 攻击防护](#windows-defender-exploit-guard)
* [Microsoft Defender 高级威胁防护](#windows10-sec-atp)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender 防病毒
Windows Defender 防病毒（AV）是内置到 Windows 10 中的反恶意软件解决方案。 它为桌面、便携式计算机和服务器提供安全性和反恶意软件管理。 有关 Windows Defender AV、最低要求以及如何管理此功能的详细信息，请参阅 windows [10 和 Windows Server 2016 中的 Windows Defender 防病毒](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)。

如果你不将 Windows Defender AV 用作主要防病毒客户端，或者如果你还在使用 Microsoft Defender ATP，则需要考虑一些注意事项。 若要了解详细信息，请参阅[Windows DEFENDER AV 兼容性](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility)。

### <a name="deployment-and-management"></a>部署和管理
若要部署和管理 Windows Defender AV，请按照下面的指导进行操作：

* [在 Windows Defender AV 上部署、管理和报告](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [管理和配置工具的参考主题](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>配置
用户可以配置许多功能。 有关详细信息，请参阅以下资源：

* [配置 Windows Defender AV 功能](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [管理和配置工具的参考主题](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

若要帮助了解配置选项，请参阅所有设置的以下列表（如其组策略配置所定义）：[使用组策略设置配置和管理 Windows DEFENDER AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

您可以使用[Windows DEFENDER av 保护评估指南](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus)来帮助评估网络上 WINDOWS defender av 的保护级别和影响。 这在创建初始配置或作为 "快速入门指南" 时也很有用，并且定期进行更新，以提供有关配置和启用功能以确保最大保护的最有用的建议。

### <a name="reporting"></a>Reporting
您可以通过使用配置工具（例如 Microsoft 终结点配置管理器或 Microsoft Intune）获取报告。 您还可以从更新合规性（OMS）中获取报告，也可以通过使用 SIEM 中的 Windows 事件日志来获取报告。 如果你拥有 Microsoft Defender ATP 的许可证，还可以获取 Windows Defender AV 检测中的报告并执行基本修正。 有关详细信息，请参阅以下资源：
* [在 Windows Defender AV 上部署、管理和报告](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Windows Defender AV 保护报告](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Microsoft Defender ATP 门户概述](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>故障排除
有关错误和事件代码的基本故障排除的信息，请参阅[查看事件日志和错误代码，以解决 Windows DEFENDER AV 的问题](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)。

您还可以使用 Windows Defender 安全智能提交系统提交问题（如误报）。 若要了解如何操作，请参阅[将问题提交给 Microsoft](https://www.microsoft.com/wdsi/filesubmission)。

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender 攻击防护
Windows Defender 攻击防护是一组新的 Windows 10 主机入侵防护功能。 有关 Windows Defender 漏洞防护的详细信息，最低要求，以及如何管理此功能，请参阅[Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)。

### <a name="deployment-management-and-configuration"></a>部署、管理和配置
若要部署、管理和配置 Windows Defender 利用防护，请按照下面的指导进行操作：
* [Exploit protection](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [攻击面保护](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [网络保护](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [受控文件夹访问](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

您可以使用一系列评估主题来帮助评估网络上 Windows Defender 攻击防护措施的保护级别和影响。 这在创建初始配置或作为 "快速入门指南" 时也很有用，这些主题和指南定期更新，以提供有关配置和启用功能以确保最大保护的最有用的建议。 有关详细信息，请[评估 Windows Defender 攻击防护](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard)。

### <a name="reporting"></a>Reporting
您可以通过使用配置工具（例如配置管理器或 Intune）获取报告。 您还可以通过使用 SIEM 中的 Windows 事件日志来获取报告。 如果你拥有 Microsoft Defender ATP 的许可证，还可以获取 Windows Defender AV 检测中的报告并执行基本修正。 有关详细信息，请参阅以下资源：
* [查看 Windows Defender 攻击防护事件](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Microsoft Defender ATP 门户概述](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>故障排除
您可以使用 Windows Defender 安全智能提交系统执行基本的故障排除或提供 Microsoft with .cab 文件，并提交问题（如误报）。 若要了解如何操作，请参阅[将问题提交给 Microsoft](https://www.microsoft.com/wdsi/filesubmission)。


<a name="windows10-sec-atp"></a>
## <a name="microsoft-defender-advanced-threat-protection"></a>Microsoft Defender 高级威胁防护
Microsoft Defender ATP 仅适用于 Microsoft 365 企业版 E5 计划，它是一项安全服务，使企业客户能够检测、调查和响应其网络上的高级威胁。 有关 Microsoft Defender ATP、最低要求以及如何管理此功能的详细信息，请参阅：

* [Microsoft Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [最低要求](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>部署、管理和配置
若要部署 Microsoft Defender ATP，你需要确保你具有正确的 Windows 许可证。 验证你是否拥有正确的许可证后，你需要确定将存储数据的地理位置。 之后，你可以启动向服务中加入终结点。

有关这些步骤的更多详细信息，请参阅以下主要主题： 

* [验证许可设置和完成设置](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [数据存储和隐私](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [板载终结点和设置访问权限](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>检测、调查、响应
成功将终结点加入服务后，即可开始调查来自不同仪表板的警报。 在调查完警报之后，您可以对警报采取响应操作。 

有关如何执行这些操作的详细信息，请参阅：
* [Microsoft Defender ATP 门户概述](https://go.microsoft.com/fwlink/?linkid=861596)
* [使用 Microsoft Defender ATP 门户](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [采取响应操作](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>与其他产品和工具集成
Microsoft Defender ATP 集成并支持各种其他产品和工具，以扩展其安全功能。 

有关工具和其他产品的详细信息，请参阅：
* [SIEM 工具](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [创建自定义通知](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [使用 Api](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [构建 Power BI 报表](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>故障排除
在载入或使用产品的过程中，可能会遇到问题。 有关如何解决问题的详细信息，请参阅：
* [解决载入问题](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Microsoft Defender ATP 故障排除](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>后续步骤

[Windows 10 企业版基础结构退出条件](windows10-exit-criteria.md)
