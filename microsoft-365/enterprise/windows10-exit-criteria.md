---
title: 阶段 3：Windows 10 企业版基础结构退出条件
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 确保你的配置符合 Microsoft 365 企业版针对 Windows 10 企业版的条件。
ms.openlocfilehash: d51392572c78edb1a21f5edc3229057b9af3f514
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801217"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a>阶段 3：Windows 10 企业版基础结构退出条件

![阶段 3：Windows 10 企业版](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

确保你的 Windows 10 企业版基础结构符合以下必需条件，以及你认为可选的那些条件。

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a>必需：已添加 Microsoft 365 域并已对其验证

Office 365 和 Intune 订阅的 Azure AD 租户是使用 Internet 域名（例如，contoso.com）配置的，而不是仅使用包含“onmicrosoft.com”的域名配置的。 

如果不这样做，则会在身份验证方法中限制你可以进行的配置。例如，传递和联合身份验证无法使用“onmicrosoft.com”域名。

如果需要，可在[步骤 1](windows10-prepare-your-org.md) 中进行设置以满足此要求。

## <a name="optional-your-users-are-added-and-licensed"></a>可选：已添加用户并已对其许可

已添加对应于用户的帐户（直接添加到 Office 365 和 Intune 订阅的 Azure AD 租户，或从本地 Active Directory 域服务 (AD DS) 中的目录同步）。

添加用户后，即可向其分配 Microsoft 365 企业版许可证（可直接分配为全局或用户管理员，或通过组成员身份自动分配）。

如果需要，可在[步骤 1](windows10-prepare-your-org.md) 中设置此选项。

## <a name="optional-diagnostics-are-enabled"></a>可选：已启用诊断

已使用组策略、Microsoft Intune、注册表编辑器或命令提示符启用了诊断数据设置。

如果需要，可在[步骤 1](windows10-prepare-your-org.md) 中设置此选项。

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a>需要就地升级：为操作系统部署创建 Configuration Manager 任务序列

若要对运行 Windows 7 或 Windows 8.1 的设备启动 Configuration Manager 任务序列以执行就地升级，必须完成以下设置：

- 设置合适的 Windows 诊断数据级别
- 已验证 Windows 升级准备就绪情况
- 已创建一个 Configuration Manager 任务序列，其中包括使用 Windows 10 OS 映像的设备集合和操作系统部署

完成以上设置后，即可对已准备好升级 Windows 的设备执行就地升级。为了发挥 Microsoft 365 企业版的最佳功能，请尽量将运行 Windows 7 和 Windows 8.1 的设备进行升级。 

每个运行 Windows 10 企业版的设备都可以体验 Microsoft 365 企业版集成解决方案带来的优势。其他运行 Windows 7 或 Windows 8.1 的设备将无法使用 Windows 10 企业版的云连接技术和高级功能。

如果需要，可在[步骤 2](windows10-deploy-inplaceupgrade.md) 中进行设置以满足此要求。

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a>需要新设备：配置的 Windows Autopilot

若要使用 Windows Autopilot 对新设备部署和自定义 Windows 10 企业版，必须完成以下设置：

- 已配置合适的 Windows 诊断数据级别
- 已配置 Windows Autopilot 的先决条件，其中包括：
   - 设备注册和 OOBE 自定义
   - 针对 OOBE 的公司品牌塑造
   - Microsoft Intune 中的 MDM 自动注册
   - Windows Autopilot 所使用的云服务的网络连接
- 已预安装 Windows 10 版本 1703 或更高版本的设备
- 已为组织选择了 Windows Autopilot 部署计划

一旦 Windows Autopilot 配置准备就绪，即可使用它来为以下设备配置和自定义开箱即用 (OOBE) 的 Windows 10 企业版体验：

- 新设备
- 组织中已完成自带设置的设备。 

Windows Autopilot 配置设备并将其连接到 Azure AD。

如未安装 Windows Autopilot，则必须手动配置新设备，包括与 Azure AD 的连接。

如果需要，可在[步骤 3](windows10-deploy-autopilot.md) 中进行设置以满足此要求。

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a>可选：你正在使用 Windows Analytics 设备运行状况来监控基于 Windows 10 企业版的设备。

你将监视器中有关设备运行状况的信息与设备运行状况结合使用，以检测和修正影响最终用户的问题。快速解决最终用户的问题可减少你的支持成本，并可向用户展示 IT 部门对 Windows 10 企业版的承诺，以帮助推动整个组织使用 Windows 10 企业版。 

如果需要，可在[步骤 4](windows10-enable-windows-analytics.md) 中设置此选项。

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a>必需：你正在使用 Windows Defender 防病毒或正在使用你自己的反恶意软件解决方案

已部署 Windows Defender 防病毒软件或已部署你自己的防病毒解决方案来保护运行 Windows 10 企业版的设备免受恶意软件的侵害。如果已部署 Windows Defender 防病毒软件，则已实施报告方法（例如，Microsoft Endpoint Configuration Manager 或 Microsoft Intune）来监控防病毒事件和活动。

如果需要，可在[步骤 5](windows10-enable-security-features.md#windows10-sec-av) 中进行设置以满足此要求。

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a>必需：你正在使用 Windows Defender 攻击防护

已部署 Windows Defender 攻击防护来保护运行 Windows 10 企业版的设备免受入侵，并已实施报告方法（例如，Configuration Manager 或 Microsoft Intune）来监控入侵事件和活动。

如果需要，可在[步骤 5](windows10-enable-security-features.md#windows10-sec-eg) 中进行设置以满足此要求。

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-e5-only"></a>必需：你正在使用 Microsoft Defender 高级威胁防护（仅限 Microsoft 365 E5）

已部署 Microsoft Defender 高级威胁防护 (ATP)，以针对运行 Windows 10 企业版的网络和设备检测、调查和响应高级威胁。 

（可选）已将 Microsoft Defender ATP 与其他工具集成，以扩展其功能。

如果需要，可在[步骤 5](windows10-enable-security-features.md#windows10-sec-atp) 中进行设置以满足此要求。

## <a name="results-and-next-steps"></a>结果和后续步骤

你的 Windows 10 企业版基础架构已准备好开始在新设备上安装并在运行以前版本的 Windows 的设备上就地升级，并且你正在使用 Windows 10 企业版的主要安全功能。

|||
|:-------|:-----|
|![阶段 4：Office 365 专业增强版](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| 如果你正在执行 Microsoft 365 企业版端到端部署的各个阶段，下一个阶段是 [Office 365 专业增强版](office365proplus-infrastructure.md)。 |
