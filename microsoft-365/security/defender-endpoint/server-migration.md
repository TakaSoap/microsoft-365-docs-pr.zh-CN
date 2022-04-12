---
title: 新版Microsoft Defender for Endpoint的服务器迁移方案
description: 阅读本文，大致了解如何将服务器从基于 MMA 的上一个解决方案迁移到当前 Defender for Endpoint 统一解决方案包。
keywords: 迁移服务器、服务器、2012r2、2016、服务器迁移、设备管理、配置Microsoft Defender for Endpoint服务器、载入Microsoft Defender for Endpoint服务器
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ed31a629f6cde18af03c3c6102b821cb6a04dd96
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782650"
---
# <a name="server-migration-scenarios-from-the-previous-mma-based-microsoft-defender-for-endpoint-solution"></a>基于 MMA 的上一个基于 MMA 的Microsoft Defender for Endpoint解决方案中的服务器迁移方案

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- Windows Server 2012 R2
- Windows Server 2016
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> [!NOTE]
> 在继续安装或升级之前，请始终确保操作系统和Windows Server 2016上的Microsoft Defender 防病毒已完全更新。 若要接收EDR传感器组件的常规产品改进和修复，请确保在安装后应用或批准[Windows 更新 KB5005292](https://go.microsoft.com/fwlink/?linkid=2168277)。 此外，若要保持保护组件的更新，请参考[“管理Microsoft Defender 防病毒更新并应用基线](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)。

这些说明适用于新的统一解决方案和安装程序 (MSI) Windows Server 2012 R2 和 Windows Server 2016 的Microsoft Defender for Endpoint包。 本文包含有关从上一个解决方案到当前解决方案的各种可能迁移方案的高级说明。 这些高级步骤旨在作为指南，以适应环境中可用的部署和配置工具。

> [!NOTE]
> 不支持安装Microsoft Defender for Endpoint的操作系统升级。 请在继续升级之前卸载。

> [!NOTE]
> 用于执行自动升级的完全Microsoft Endpoint Configuration Manager自动化和集成将在更高版本的 MECM 中提供。 从具有最新修补程序汇总的 2107 版本中，可以使用Endpoint Protection节点进行配置以及组策略、PowerShell、Microsoft Endpoint Manager 租户附加或本地配置。 此外，还可以利用Microsoft Endpoint Configuration Manager中的现有功能自动执行手动升级步骤;如下所述的方法。


## <a name="installer-script"></a>安装程序脚本

若要在Microsoft Endpoint Configuration Manager或Microsoft Defender for Cloud未使用或尚不可执行升级时促进升级，可以使用此[升级脚本](https://github.com/microsoft/mdefordownlevelserver)。 它可以帮助自动执行以下必需步骤：

1. 删除 Microsoft Defender for Endpoint (OPTIONAL) 的 OMS 工作区。
2. 如果已安装，请删除System Center Endpoint Protection (SCEP) 客户端。
3. 下载并安装 (Windows Server 2012 R2) [必备组件](configure-server-endpoints.md#prerequisites)（如果需要）。
4. 安装Microsoft Defender for Endpoint。
5. 应用载入脚本 **以用于从Microsoft 365 Defender** 下载的 [组策略](https://security.microsoft.com)。

若要使用该脚本，请将其下载到安装目录，其中还放置了安装和载入包 (请参阅 [“配置服务器终结点](configure-server-endpoints.md)”。

示例：.\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript “.\WindowsDefenderATPOnboardingScript.cmd”

## <a name="microsoft-endpoint-configuration-manager-migration-scenarios"></a>Microsoft Endpoint Configuration Manager迁移方案 

>[!NOTE]
>需要Microsoft Endpoint Configuration Manager版本 2107 或更高版本。

迁移步骤： 

1. 完全更新计算机，包括Microsoft Defender 防病毒 (Windows Server 2016) 。
2. 创建包含成员资格规则的新集合，以包含要迁移的计算机。
3. [创建应用程序](/mem/configmgr/apps/deploy-use/create-applications) 以执行以下任务： 
   1. 卸载 SCEP。
   2. 在适用的情况下安装 [先决条件](configure-server-endpoints.md#prerequisites) 。
   3. 安装Microsoft Defender for Endpoint (请参阅[配置服务器终结点](configure-server-endpoints.md)。
   4. 应用载入脚本 **以用于从Microsoft 365 Defender** 下载的 [组策略](https://security.microsoft.com)。 
   > [!TIP]
   > 可以将 [安装程序脚本](server-migration.md#installer-script) 用作应用程序的一部分，以自动执行上述步骤。
4. 将应用程序部署到新集合。
5. 创建和/或向集合分配 (现有) Endpoint Protection策略。
6. 应用更新。

### <a name="you-are-currently-using-microsoft-endpoint-configuration-manager-to-manage-your-servers-are-running-a-non-microsoft-antivirus-solution-and-the-mma-based-sensor-you-want-to-upgrade-to-the-new-microsoft-defender-for-endpoint"></a>你当前正在使用Microsoft Endpoint Configuration Manager来管理服务器、运行非 Microsoft 防病毒解决方案和基于 MMA 的传感器。 你想要升级到新Microsoft Defender for Endpoint。

迁移步骤：

1. 完全更新计算机，包括Microsoft Defender 防病毒 (Windows Server 2016) 。
2. 创建包含成员资格规则的新集合，以包含要迁移的计算机。 
3. 确保第三方防病毒管理不再将防病毒推送到这些计算机。*
4. 在 MECM 的Endpoint Protection节点中创作策略，并面向新创建的集合。*
5. 创建应用程序以执行以下任务：
   1. 删除用于Microsoft Defender for Endpoint的 MMA 工作区配置。 请参阅 [使用 PowerShell 删除工作区](/azure/azure-monitor/agents/agent-manage)。 此步骤是可选的;在较新的传感器处于活动状态后，以前的EDR传感器将停止运行。
   2. 在适用的情况下安装 [先决条件](configure-server-endpoints.md#prerequisites) 。
   3. 安装 Windows Server 2012 R2 和 2016 包的Microsoft Defender for Endpoint并 **启用被动模式**。 请参阅[使用命令行安装Microsoft Defender 防病毒](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-the-command-line)。
   4. 应用载入脚本 **以用于从Microsoft 365 Defender** 下载的 [组策略](https://security.microsoft.com)。
6. 应用更新。
7. 使用非 Microsoft 防病毒控制台或根据需要使用Microsoft Endpoint Configuration Manager删除非 Microsoft 防病毒软件。 请确保删除被动模式配置。*

> [!TIP]
> 可以使用 [安装程序脚本](server-migration.md#installer script) 作为应用程序的一部分自动执行上述步骤。 若要启用被动模式，请应用 -Passive 标志。 例如，.\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript “.\WindowsDefenderATPOnboardingScript.cmd” -Passive

*仅当打算替换非 Microsoft 防病毒解决方案时，这些步骤才适用。 [一起查看更好：Microsoft Defender 防病毒和Microsoft Defender for Endpoint](why-use-microsoft-defender-antivirus.md)。

若要将计算机移出被动模式，请将以下键设置为 0：

路径：HKLM\SOFTWARE\Policies\Microsoft\Windows高级威胁防护名称：ForceDefenderPassiveMode 类型：REG_DWORD值： 0


## <a name="other-migration-scenarios"></a>其他迁移方案

### <a name="you-have-a-server-that-has-been-onboarded-using-the-mma-based-microsoft-defender-for-endpoint-it-has-scep-installed-windows-server-2012-r2-or-microsoft-defender-antivirus-windows-server-2016-this-machine-is-not-managed-through-microsoft-defender-for-cloud-microsoft-endpoint-manager-or-microsoft-endpoint-configuration-manager"></a>你有一个已使用基于 MMA 的Microsoft Defender for Endpoint载入的服务器。 它已在 R2) 或Microsoft Defender 防病毒 (Windows Server 2016)  (Windows Server 2012安装 SCEP。 此计算机 **不是** 通过Microsoft Defender for Cloud、Microsoft Endpoint Manager 或Microsoft Endpoint Configuration Manager管理的。

1. 完全更新计算机，包括Microsoft Defender 防病毒 (Windows Server 2016) 。
2. 删除用于Microsoft Defender for Endpoint的 MMA 工作区配置。 请参阅 [使用 PowerShell 删除工作区](/azure/azure-monitor/agents/agent-manage)。
3. 卸载System Center Endpoint Protection (Windows Server 2012 R2) 。
4. 在适用的情况下安装 [先决条件](configure-server-endpoints.md#prerequisites) 。 
5. 安装Microsoft Defender for Endpoint (请参阅[配置服务器终结点](configure-server-endpoints.md).) 
6. 应用载入脚本 **以用于从Microsoft 365 Defender** 下载的 [组策略](https://security.microsoft.com)。 
7. 应用更新。
8. 使用组策略、PowerShell 或第三方管理解决方案创建和应用策略。

> [!TIP]
> 可以使用安装程序脚本自动执行上述步骤。

### <a name="you-have-a-server-on-which-you-want-to-install-microsoft-defender-for-endpoint-it-has-a-non-microsoft-endpoint-protection-or-endpoint-detection-and-response-solution-installed-you-do-not-intend-to-use-microsoft-endpoint-configuration-manager-or-microsoft-defender-for-cloud-you-use-your-own-deployment-mechanism"></a>你有一个要在其上安装Microsoft Defender for Endpoint的服务器。 它安装了非 Microsoft 终结点保护或终结点检测和响应解决方案。 你不打算使用Microsoft Endpoint Configuration Manager或Microsoft Defender for Cloud。 使用自己的部署机制。 

1. 完全更新计算机，包括Microsoft Defender 防病毒 (Windows Server 2016) 。
2. 安装 Windows Server 2012 R2 & 2016 包的Microsoft Defender for Endpoint并 **启用被动模式**。 请参阅[使用命令行安装Microsoft Defender 防病毒](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-the-command-line)。
3. 应用从[Microsoft 365 Defender](https://security.microsoft.com)下载的适合环境的载入脚本。 
4. 删除非 Microsoft 终结点保护或终结点检测和响应解决方案，并删除被动模式。*
5. 应用更新。
6. 使用组策略、PowerShell 或第三方管理解决方案创建和应用策略。

> [!TIP]
> 可以使用 [安装程序脚本](server-migration.md#installer-script) 帮助自动执行步骤 1 到步骤 4。 若要启用被动模式，请应用 -Passive 标志，确保 Defender 防病毒在加入之前进入被动模式，并且不会干扰非 Microsoft 反恶意软件解决方案。 然后，若要确保 Defender 防病毒在载入后仍处于被动模式，以支持EDR功能，例如EDR块，请确保设置“ForceDefenderPassiveMode”注册表项。 例子： `.\install.ps1 -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive`


*仅当打算替换非 Microsoft 防病毒解决方案时，此步骤才适用。 建议使用Microsoft Defender for Endpoint中包含的Microsoft Defender 防病毒提供完整的功能集。 [一起查看更好：Microsoft Defender 防病毒和Microsoft Defender for Endpoint](why-use-microsoft-defender-antivirus.md)。

若要将计算机移出被动模式，请将以下键设置为 0：

路径：HKLM\SOFTWARE\Policies\Microsoft\Windows高级威胁防护名称：ForceDefenderPassiveMode 类型：REG_DWORD值： 0


## <a name="microsoft-defender-for-cloud-scenarios"></a>Microsoft Defender for Cloud方案

### <a name="youre-using-microsoft-defender-for-cloud-the-microsoft-monitoring-agent-mma-andor-microsoft-antimalware-for-azure-scep-are-installed-and-you-want-to-upgrade"></a>你正在使用Microsoft Defender for Cloud。 已安装适用于 Azure (SCEP) 的 Microsoft Monitoring Agent (MMA) 和/或 Microsoft Antimalware，你想要升级。
如果使用的是Microsoft Defender for Cloud，则可以利用自动升级过程。 请参阅[使用Defender for Cloud的集成EDR解决方案保护终结点：Microsoft Defender for Endpoint](/azure/security-center/security-center-wdatp#enable-the-microsoft-defender-for-endpoint-integration)。

## <a name="group-policy-configuration"></a>组策略配置
若要使用组策略进行配置，请确保使用中央存储中的最新 ADMX 文件来访问正确的 Defender for Endpoint 策略选项。 请参阅 [如何在Windows中创建和管理用于组策略管理模板的 Central Store](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)，并下载 **要与Windows 10配合使用** 的最新文件。
