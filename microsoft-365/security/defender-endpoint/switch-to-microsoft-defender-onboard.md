---
title: 切换到 Microsoft Defender for Endpoint - 载入
description: 这是第 3 阶段，载入，用于从非 Microsoft 解决方案迁移到 Microsoft Defender for Endpoint。
keywords: 迁移， windows defender 高级威胁防护， atp， edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
ms.custom: migrationguides
ms.topic: article
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 2916f113f3c26a9c33c6da1f235a9b143667b9cf
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056511"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>切换到 Microsoft Defender for Endpoint - 阶段 3：载入

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![阶段 1：准备 3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[阶段 1：准备](switch-to-microsoft-defender-prepare.md) | [![阶段 2：设置](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[阶段 2：设置](switch-to-microsoft-defender-setup.md) | ![阶段 3：载入](images/phase-diagrams/onboard.png)<br/>阶段 3：载入 |
|--|--|--|
|| |*你在这里！* |


**欢迎使用切换到 Microsoft [Defender for Endpoint 的第](switch-to-microsoft-defender-migration.md#the-migration-process)3 阶段**。 此迁移阶段包括以下步骤：

1. [将设备载入到 Microsoft Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint)。
2. [运行检测测试](#run-a-detection-test)。
3. [卸载非 Microsoft 解决方案](#uninstall-your-non-microsoft-solution)。
4. [确保 Microsoft Defender for Endpoint 在活动模式下](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)。

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>将设备载入到 Microsoft Defender for Endpoint

1. 转到 Microsoft Defender 安全中心 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) () 并登录。
2. 选择 **设置**  >  **设备管理**  >  **载入**。 
3. 在 **"选择操作系统以开始载入过程"列表中** ，选择操作系统。 
4. 在 **"部署方法**"下，选择一个选项。 按照链接和提示载入组织的设备。 需要帮助？ 请参阅 [本文 (](#onboarding-methods) 载入方法) 。

### <a name="onboarding-methods"></a>载入方法
 
部署方法因选择的操作系统而异。 请参阅下表中列出的资源，获取有关载入的帮助。

|操作系统  |方法  |
|---------|---------|
|Windows 10     |- [组策略](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)<br/>- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)<br/>- [Intune (移动设备) ](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-mdm)<br/>- [本地脚本](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/><br/>**注意**：本地脚本适用于概念证明，但不应用于生产部署。 对于生产部署，我们建议使用组策略、Microsoft Endpoint Configuration Manager 或 Intune。         |
|- Windows 8.1 企业版 <br/>- Windows 8.1 专业版 <br/>- Windows 7 SP1 企业版 <br/>- Windows 7 SP1 专业版     | [Microsoft 监视代理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-atp)<br/><br/>**注意**：Microsoft 监视代理现在是 Azure Log Analytics 代理。 若要了解更多信息，请参阅 [Log Analytics agent overview](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)。        |
|- Windows Server 2019 及更高版本 <br/>- Windows Server 2019 核心版本 <br/>- Windows Server 版本 1803 和更高版本 |- [本地脚本](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/>- [组策略](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp) <br/>- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm) <br/>- [System Center Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#onboard-windows-10-devices-using-earlier-versions-of-system-center-configuration-manager) <br/>- [用于非永久性设备的 VDI 载入脚本](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi) <br/><br/>**注意**：本地脚本适用于概念证明，但不应用于生产部署。 对于生产部署，我们建议使用组策略、Microsoft Endpoint Configuration Manager 或 Intune。    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Microsoft Defender 安全中心](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#option-1-onboard-servers-through-microsoft-defender-security-center)<br/>- [Azure 安全中心](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>- 10.15 (加泰罗尼亚语) <br/>- 10.14 (Mojave) <br/>- 10.13 (High Sierra) <br/><br/>iOS<br/><br/>Linux：<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2 及以上<br/>- Ubuntu 16 LTS 或更高版本 LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[载入非 Windows 设备](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-non-windows)  |

## <a name="run-a-detection-test"></a>运行检测测试

若要验证载入的设备是否正确连接到 Microsoft Defender for Endpoint，可以运行检测测试。

|操作系统  |指南  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server 版本 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |请参阅 [运行检测测试](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test)。 <br/><br/>请访问 Microsoft Defender for Endpoint 演示方案站点 () [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) 并尝试一个或多个方案。 例如，尝试 **云提供的保护演示** 方案。         |
|macOS<br/>- 10.15 (加泰罗尼亚语) <br/>- 10.14 (Mojave) <br/>- 10.13 (High Sierra)      |从 下载并使用 DIY 应用 [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) 。 <br/><br/>有关详细信息，请参阅[Microsoft Defender for Endpoint for Mac。](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac)        |
|Linux：<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2 及以上<br/>- Ubuntu 16 LTS 或更高版本 LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. 运行以下命令，并查找 **结果 1：** <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. 打开"终端"窗口，并运行以下命令： <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. 运行以下命令以列出任何检测到的威胁： <br/>`mdatp threat list`. <br/><br/>有关详细信息，请参阅适用于[Linux 的 Microsoft Defender ATP。](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux) |

## <a name="uninstall-your-non-microsoft-solution"></a>卸载非 Microsoft 解决方案

现在，你已将组织的设备载入 Microsoft Defender for Endpoint，下一步是卸载非 Microsoft 终结点保护解决方案。

若要获取有关此步骤的帮助，请联系解决方案提供商的技术支持团队。

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>确保 Microsoft Defender for Endpoint 已进入活动模式

现在，你已卸载非 Microsoft 终结点保护解决方案，下一步是确保 Microsoft Defender 防病毒和 Microsoft Defender for Endpoint 已启用且处于活动状态。

为此，请访问 Microsoft Defender 终结点演示方案站点 [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) () 。 尝试该页面上的一个或多个演示方案，包括至少以下方案：
- 云保护
- PUA (可能不需要) 
- 网络保护 (NP) 

> [!IMPORTANT]
> 如果你使用的是 Windows Server 2016，可能需要手动启动 Microsoft Defender 防病毒。 为此，可以在设备上使用 PowerShell `mpcmdrun.exe -wdenable` cmdlet。

## <a name="next-steps"></a>后续步骤

**恭喜！** 你已完成到 [Microsoft Defender for Endpoint 的迁移](switch-to-microsoft-defender-migration.md#the-migration-process)！ 

- [访问 Microsoft](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard) Defender 安全中心安全中心安全 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) () 。 
- [管理 Microsoft Defender for Endpoint，迁移后](manage-atp-post-migration.md)。
