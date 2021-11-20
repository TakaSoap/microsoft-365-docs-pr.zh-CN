---
title: 适用于新版本的 Microsoft Defender for Endpoint 的服务器迁移方案
description: 阅读本文，大致了解如何将服务器从以前的基于 MMA 的解决方案迁移到当前的 Defender for Endpoint 统一解决方案包。
keywords: 迁移服务器， 服务器， 2012r2， 2016， 服务器迁移， 设备管理， 为终结点服务器配置 Microsoft Defender， 载入 Microsoft Defender for Endpoint Server
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9e4381063d872a097423fed4a3cb47b05b42bf38
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61122353"
---
# <a name="server-migration-scenarios-from-the-previous-mma-based-microsoft-defender-for-endpoint-solution"></a>上一个基于 MMA 的 Microsoft Defender 终结点解决方案中的服务器迁移方案

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- Windows Server 2012 R2
- Windows Server 2016

[!include[Prerelease information](../../includes/prerelease.md)]

> [!NOTE]
> 在继续Microsoft Defender 防病毒升级之前，Windows Server 2016更新更新。 若要接收适用于传感器组件的常规产品改进和EDR，请确保Windows[更新 KB5005292](https://go.microsoft.com/fwlink/?linkid=2168277)获得应用或批准。 此外，若要使保护组件保持更新，请参考管理Microsoft Defender 防病毒[更新和应用基线](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)。

这些说明适用于适用于 Windows Server 2012 R2 和 Windows Server 2016 的 Microsoft Defender for Endpoint 的新统一解决方案和Windows Server 2016。 本文包含有关从上一个解决方案到当前解决方案的各种可能迁移方案的高级别说明。 这些高级步骤旨在指导你根据环境中可用的部署和配置工具进行调整。

> [!NOTE]
> 不支持安装 Microsoft Defender for Endpoint 的操作系统升级。 请先卸载，然后再继续升级。

> [!NOTE]
> 在预览期间，Microsoft Endpoint Configuration Manager 2111 版 MECM 中提供了用于执行自动升级的完全自动化和集成功能。 从 2107 版本中，可以使用 Endpoint Protection 节点进行配置，以及组策略、PowerShell、Microsoft Endpoint Manager租户附加或本地配置。 此外，您还可以利用 Microsoft Endpoint Configuration Manager中的现有功能来自动执行手动升级步骤;下面介绍其方法。

## <a name="installer-script"></a>安装程序脚本

为了便于在 Microsoft Endpoint Configuration Manager 或 Microsoft Defender for Cloud 不可用或尚无法执行升级时进行升级，可以使用此升级[脚本](https://github.com/microsoft/mdefordownlevelserver)。 它可以帮助自动执行以下所需步骤：

1. 删除 Microsoft Defender 终结点的 OMS 工作区 (可选) 。
2. 如果System Center Endpoint Protection，请删除客户端。
3. 下载并安装 (Windows Server 2012 R2) [必备](configure-server-endpoints.md#prerequisites)组件（如果需要）。
4. 安装 Microsoft Defender for Endpoint。
5. 应用载入脚本 **，以与** 从 Microsoft Defender 安全中心 下载的组 [策略一Microsoft Defender 安全中心。](https://securitycenter.microsoft.com)

若要使用脚本，请将其下载到安装目录，其中还放置了安装和载入 (请参阅配置 [服务器](configure-server-endpoints.md) 终结点) 。

示例：.\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd"

## <a name="microsoft-endpoint-configuration-manager-migration-scenarios"></a>Microsoft Endpoint Configuration Manager迁移方案 

### <a name="you-are-currently-using-microsoft-endpoint-configuration-manager-to-manage-your-servers-including-system-center-endpoint-protection-scep-and-are-running-the-microsoft-monitoring-agent-mma-based-sensor-you-want-to-upgrade-to-the-microsoft-defender-for-endpoint-unified-solution-preview"></a>你当前正在使用Microsoft Endpoint Configuration Manager管理服务器，包括 System Center Endpoint Protection (SCEP) ，并且正在运行基于 MMA Microsoft Monitoring Agent () 传感器。 你想要升级到 Microsoft Defender for Endpoint 统一解决方案 **预览** 版。

>[!NOTE]
>你需要安装 2107 Microsoft Endpoint Configuration Manager版本。


迁移步骤： 

1. 完全更新计算机，包括Microsoft Defender 防病毒 (Windows Server 2016) 。
2. 创建一个包含成员身份规则的新集合，以包含要迁移的计算机。
3. [创建应用程序](/mem/configmgr/apps/deploy-use/create-applications) 以执行以下任务： 
   1. 删除 Microsoft Defender for Endpoint 的 MMA 工作区配置。 请参阅 [使用 PowerShell 删除工作区](/azure/azure-monitor/agents/agent-manage)。 此步骤是可选的;上一EDR传感器将在较新的传感器变为活动状态后停止 (请注意，这可能需要几个小时) 。
   2. 卸载 SCEP。
   3. 安装 [必备组件](configure-server-endpoints.md#prerequisites) （如果适用）。
   4. 安装 Microsoft Defender for Endpoint (请参阅 [配置服务器终结点](configure-server-endpoints.md)) 。
   5. 应用载入脚本 **，以与** 从 Microsoft Defender 安全中心 下载的组 [策略一Microsoft Defender 安全中心。](https://securitycenter.microsoft.com) 

   > [!TIP]
   > 可以将安装程序 [脚本用作](server-migration.md#installer-script) 应用程序的一部分，以自动执行上述步骤。
4. 将应用程序部署到新集合。
5. 创建和/或 (现有) Endpoint Protection策略分配给集合。
6. 应用更新。

### <a name="you-are-currently-using-microsoft-endpoint-configuration-manager-to-manage-your-servers-are-running-a-non-microsoft-antivirus-solution-and-the-mma-based-sensor-you-want-to-upgrade-to-the-new-microsoft-defender-for-endpoint"></a>您当前Microsoft Endpoint Configuration Manager服务器，正在运行非 Microsoft 防病毒解决方案和基于 MMA 的传感器。 你想要升级到新的 Microsoft Defender for Endpoint。

迁移步骤：

1. 完全更新计算机，包括Microsoft Defender 防病毒 (Windows Server 2016) 。
2. 创建一个包含成员身份规则的新集合，以包含要迁移的计算机。 
3. 确保第三方防病毒管理不再将防病毒推送到这些计算机。*
4. 在 MECM 的 Endpoint Protection 节点中创作您的策略，并面向新创建的集合。*
5. 创建应用程序以执行以下任务：
   1. 删除 Microsoft Defender for Endpoint 的 MMA 工作区配置。 请参阅 [使用 PowerShell 删除工作区](/azure/azure-monitor/agents/agent-manage)。 此步骤是可选的;上一EDR传感器将在较新的传感器变为活动状态后停止 (请注意，这可能需要几个小时) 。
   2. 安装 [必备组件](configure-server-endpoints.md#prerequisites) （如果适用）。
   3. 安装适用于 R2 和 2016 Windows Server 2012的 Microsoft Defender for Endpoint 并 **启用被动模式**。 请参阅[Install Microsoft Defender 防病毒 using command line](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-command-line)。
   4. 应用载入脚本 **，以与** 从 Microsoft Defender 安全中心 下载的组 [策略一Microsoft Defender 安全中心。](https://securitycenter.microsoft.com)
6. 应用更新。
7. 使用非 Microsoft 防病毒控制台或根据情况使用 Microsoft Endpoint Configuration Manager删除非 Microsoft 防病毒软件。 确保删除被动模式配置。*

> [!TIP]
> 可以将安装程序 [脚本用作](server-migration.md#installer script) 应用程序的一部分，以自动执行上述步骤。 若要启用被动模式，请应用 -Passive 标志。 例如，.\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive

*这些步骤仅适用于要替换非 Microsoft 防病毒解决方案时。 请参阅[更好地结合：Microsoft Defender 防病毒和 Microsoft Defender for Endpoint](why-use-microsoft-defender-antivirus.md)。

若要将计算机从被动模式移开，将以下键设置为 0：

路径：HKLM\SOFTWARE\Policies\Microsoft\Windows 高级威胁防护名称：ForceDefenderPassiveMode 类型：REG_DWORD值：0


## <a name="other-migration-scenarios"></a>其他迁移方案

### <a name="you-have-a-server-that-has-been-onboarded-using-the-mma-based-microsoft-defender-for-endpoint-it-has-scep-installed-windows-server-2012-r2-or-microsoft-defender-antivirus-windows-server-2016-this-machine-is-not-managed-through-microsoft-defender-for-cloud-microsoft-endpoint-manager-or-microsoft-endpoint-configuration-manager"></a>你的服务器已使用基于 MMA 的 Microsoft Defender for Endpoint 载入。 它已安装 SCEP (Windows Server 2012 R2) 或 Microsoft Defender 防病毒 (Windows Server 2016) 。 此计算机 **不通过** Microsoft Defender for Cloud、Microsoft Endpoint Manager 或 Microsoft Endpoint Configuration Manager。

1. 完全更新计算机，包括Microsoft Defender 防病毒 (Windows Server 2016) 。
2. 删除 Microsoft Defender for Endpoint 的 MMA 工作区配置。 请参阅 [使用 PowerShell 删除工作区](/azure/azure-monitor/agents/agent-manage)。
3. 卸载System Center Endpoint Protection (Windows Server 2012 R2) 。
4. 安装 [必备组件](configure-server-endpoints.md#prerequisites) （如果适用）。 
5. 安装 Microsoft Defender for Endpoint (请参阅 [配置服务器](configure-server-endpoints.md)终结点 .) 
6. 应用载入脚本 **，以与** 从 Microsoft Defender 安全中心 下载的组 [策略一Microsoft Defender 安全中心。](https://securitycenter.microsoft.com) 
7. 应用更新。
8. 使用组策略、PowerShell 或第三方管理解决方案创建和应用策略。

> [!TIP]
> 可以使用安装程序脚本自动执行上述步骤。

### <a name="you-have-a-server-on-which-you-want-to-install-microsoft-defender-for-endpoint-it-has-a-non-microsoft-endpoint-protection-or-endpoint-detection-and-response-solution-installed-you-do-not-intend-to-use-microsoft-endpoint-configuration-manager-or-microsoft-defender-for-cloud-you-use-your-own-deployment-mechanism"></a>你有一个要安装 Microsoft Defender for Endpoint 的服务器。 它安装了非 Microsoft 终结点保护或终结点检测和响应解决方案。 你不打算使用 Microsoft Endpoint Configuration Manager 或 Microsoft Defender for Cloud。 使用自己的部署机制。 

1. 完全更新计算机，包括Microsoft Defender 防病毒 (Windows Server 2016) 。
2. 安装适用于 2016 Windows Server 2012 R2 & 的 Microsoft Defender for Endpoint 并 **启用被动模式**。 请参阅[Install Microsoft Defender 防病毒 using command line](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-command-line)。
3. 应用载入脚本（适用于你的环境，从 Microsoft Defender 安全中心[下载）。](https://securitycenter.microsoft.com) 
4. 删除非 Microsoft 终结点保护或终结点检测和响应解决方案，并删除被动模式。*
5. 应用更新。
6. 使用组策略、PowerShell 或第三方管理解决方案创建和应用策略。

> [!TIP]
> 可以使用安装程序 [脚本来帮助自动](server-migration.md#installer-script) 执行步骤 1 到步骤 4。 若要启用被动模式，请应用 -Passive 标志，这将确保 Defender 防病毒在载入前进入被动模式，并且不会干扰非 Microsoft 反恶意软件解决方案。 然后，确保 Defender 防病毒在载入后保持被动模式，以支持 EDR 功能，如 EDR Block，请确保设置"ForceDefenderPassiveMode"注册表项。 示例： `.\install.ps1 -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive`


*此步骤仅适用于要替换非 Microsoft 防病毒解决方案的情况。 我们建议使用 Microsoft Defender 防病毒（包含在 Microsoft Defender for Endpoint 中）来提供完整的功能集。 请参阅[更好的一起：Microsoft Defender 防病毒和 Microsoft Defender for Endpoint](why-use-microsoft-defender-antivirus.md)。

若要将计算机从被动模式移开，将以下键设置为 0：

路径：HKLM\SOFTWARE\Policies\Microsoft\Windows高级威胁防护名称：ForceDefenderPassiveMode 类型：REG_DWORD值：0


## <a name="microsoft-defender-for-cloud-scenarios"></a>Microsoft Defender 云方案

### <a name="youre-using-microsoft-defender-for-cloud-the-microsoft-monitoring-agent-mma-andor-microsoft-antimalware-for-azure-scep-are-installed-and-you-want-to-upgrade"></a>你正在使用 Microsoft Defender for Cloud。 已安装Microsoft Monitoring Agent (Azure) SCEP Microsoft Antimalware 的 MMA (和/或) ，并且你想要升级。
如果你使用的是 Microsoft Defender for Cloud，你可以利用自动升级过程。 请参阅使用 Defender [for Cloud 集成解决方案保护EDR：Microsoft Defender for Endpoint。](/azure/security-center/security-center-wdatp#enable-the-microsoft-defender-for-endpoint-integration)

## <a name="group-policy-configuration"></a>组策略配置
对于使用组策略的配置，请确保使用中央存储中的最新 ADMX 文件访问正确的 Defender for Endpoint 策略选项。 请参考 [如何创建](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)和管理集中存储组策略管理模板Windows下载最新文件 **以用于Windows 10**。
