---
title: Symantec 到 Microsoft Defender for Endpoint - 第 3 阶段，载入
description: 这是从 Symantec 迁移到 Microsoft Defender for Endpoint 的第 3 阶段（载入）
keywords: migration， Microsoft Defender for Endpoint， edr
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 05/14/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: f2b2d5ca9f841e36df37f025a9b5856fc7e2dc6a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538359"
---
# <a name="migrate-from-symantec---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>从 Symantec 迁移 - 阶段 3：载入到 Microsoft Defender for Endpoint

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![阶段 1：准备](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[阶段 1：准备](symantec-to-microsoft-defender-atp-prepare.md) |[![阶段 2：设置](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[阶段 2：设置](symantec-to-microsoft-defender-atp-setup.md) |![阶段 3：开始使用](images/phase-diagrams/onboard.png)<br/>阶段 3：开始使用 |
|--|--|--|
|| |*你在这里！* |


**欢迎使用从 [Symantec](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)** 迁移到 Microsoft Defender for Endpoint 的第 3 阶段。 此迁移阶段包括以下步骤：

1. [将设备载入到 Microsoft Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint)。

2. [运行检测测试](#run-a-detection-test)。

3. [确认Microsoft Defender 防病毒终结点处于被动模式](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints)。

4. [获取 Microsoft Defender 防病毒 的更新](#get-updates-for-microsoft-defender-antivirus)。

5. [卸载 Symantec](#uninstall-symantec)。

6. [确保 Microsoft Defender for Endpoint 正常工作](#make-sure-microsoft-defender-for-endpoint-is-working-correctly)。

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>将设备载入到 Microsoft Defender for Endpoint

1. 转到 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) "Microsoft Defender 安全中心 () 并登录。

2. 选择 **设置**  >  **设备管理**  >  **载入"。** 

3. 在 **"选择操作系统以开始载入过程"列表中** ，选择操作系统。 

4. 在 **"部署方法**"下，选择一个选项。 按照链接和提示载入组织的设备。 需要帮助? 请参阅 [本文 (](#onboarding-methods) 载入方法) 。

### <a name="onboarding-methods"></a>载入方法
 
部署方法因选择的操作系统而异。 请参阅下表中列出的资源，获取有关载入的帮助。

|操作系统  |方法  |
|---------|---------|
|Windows 10     | [组策略](configure-endpoints-gp.md)<p>[配置管理器](configure-endpoints-sccm.md)<p>[Intune (移动设备) ](configure-endpoints-mdm.md)<p>[本地脚本](configure-endpoints-script.md) <br/>**注意**：本地脚本适用于概念证明，但不应用于生产部署。 对于生产部署，我们建议使用组策略、Microsoft Endpoint Configuration Manager或 Intune。         |
| Windows 8.1 企业版 <p>Windows 8.1 专业版 <p>Windows 7 SP1 Enterprise<p>Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)<br/>**注意**：Microsoft Monitoring Agent现在为 Azure Log Analytics 代理。 若要了解更多信息，请参阅 [Log Analytics agent overview](/azure/azure-monitor/platform/log-analytics-agent)。        |
| WindowsServer 2019 及更高版本 <p>WindowsServer 2019 核心版本<p>Windows服务器版本 1803 和更高版本 | [本地脚本](configure-endpoints-script.md)<p>[组策略](configure-endpoints-gp.md)<p>[配置管理器](configure-endpoints-sccm.md)<p>[System Center Configuration Manager](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)<p>[用于非永久性设备的 VDI 载入脚本](configure-endpoints-vdi.md) <br/>**注意**：本地脚本适用于概念证明，但不应用于生产部署。 对于生产部署，我们建议使用组策略、Microsoft Endpoint Configuration Manager或 Intune。    |
| Windows Server 2016<p>Windows Server 2012 R2<p>Windows Server 2008 R2 SP1  | [Microsoft Defender 安全中心](configure-server-endpoints.md)<p>[Azure Defender](/azure/security-center/security-center-wdatp) |
|macOS<p>11.3.1 (Big Sur)  <p>10.15 (加泰罗尼亚语) <p>10.14 (Mojave)  |[载入非 Windows 设备](configure-endpoints-non-windows.md)  |
|iOS |[载入非 Windows 设备](configure-endpoints-non-windows.md)  |
|Linux：<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS 或更高版本 LTS<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 |[载入非 Windows 设备](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>运行检测测试

若要验证载入的设备是否正确连接到 Microsoft Defender for Endpoint，可以运行检测测试。

|操作系统  |指南  |
|---------|---------|
| Windows 10<p>Windows Server 2019<p>Windows服务器版本 1803<p>Windows Server 2016<p>Windows Server 2012 R2     |请参阅 [运行检测测试](run-detection-test.md)。 <p>请访问 Microsoft Defender for Endpoint 演示方案站点 () [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) 并尝试一个或多个方案。 例如，尝试 **云提供的保护演示** 方案。         |
|macOS：<p>11.3.1 (Big Sur) <p>10.15 (加泰罗尼亚语) <p>10.14 (Mojave)      |从 下载并使用 DIY 应用 [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) 。 <p>有关详细信息，请参阅 macOS 上的[Microsoft Defender for Endpoint。](microsoft-defender-endpoint-mac.md)        |
|Linux：<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS 或更高版本 LTS<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 |1. 运行以下命令，并查找 **结果 1：** <br/>`mdatp health --field real_time_protection_enabled`. <p>2. 打开"终端"窗口，并运行以下命令： <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. 运行以下命令以列出任何检测到的威胁： <br/>`mdatp threat list`. <p>有关详细信息，请参阅 Linux 上的[Microsoft Defender for Endpoint。](microsoft-defender-endpoint-linux.md) |

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>确认Microsoft Defender 防病毒终结点处于被动模式

现在终结点已载入到 Defender for Endpoint，下一步是确保Microsoft Defender 防病毒处于被动模式。 可以使用命令提示符或 PowerShell 执行此任务，如下表所述：

| 方法    | 需执行的操作 |
|:--|:--|
| 命令提示符    | 1. 在Windows上，以管理员角色打开命令提示符。 <p>2. 键入 `sc query windefend` ，然后按 Enter。 <p>3. 查看结果，确认Microsoft Defender 防病毒处于被动模式。 |
|PowerShell | 1. 在Windows上，以Windows PowerShell打开"登录"。 <p>2. 运行 `Get-MpComputerStatus` cmdlet。 <p>3. 在结果列表中，查找 **AMRunningMode：被动模式** 或 **AMRunningMode：SxS 被动模式**。 |

> [!NOTE]
> 在某些版本的 Windows Defender 防病毒中，Microsoft Defender 防病毒看到 Windows。

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>手动Microsoft Defender 防病毒 Windows服务器设置为被动模式

若要在 Microsoft Defender 防病毒 Server、版本 1803 或更高版本或 Windows Server 2019 上将 Windows 设置为被动模式，请按照以下步骤操作：

1. 打开注册表编辑器，然后导航到 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` 。

2. 编辑 (或创建) **ForcePassiveMode** 的 DWORD 条目，并指定以下设置：

   - 将 DWORD 的值设置为 1。
   - 在"基本"下，选择"十六进制"。

> [!NOTE]
> 可以使用其他方法来设置注册表项，如下所示：
> - 组策略首选项
> - 本地组策略对象工具
> - Configuration Manager 中的程序包

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>从Microsoft Defender 防病毒开始Windows Server 2016

如果使用 Windows Server 2016，可能需要手动Microsoft Defender 防病毒启动。 为此，可以在设备上使用 PowerShell `mpcmdrun.exe -wdenable` cmdlet。

## <a name="get-updates-for-microsoft-defender-antivirus"></a>获取更新Microsoft Defender 防病毒

使Microsoft Defender 防病毒保持最新状态至关重要，可确保你的设备具有防止新的恶意软件和攻击技术所需的最新技术和功能，即使 Microsoft Defender 防病毒 处于被动模式。

有两种类型的更新与使Microsoft Defender 防病毒保持最新有关：

- 安全智能更新
- 产品更新

若要获取更新，请按照管理更新和应用Microsoft Defender 防病毒[中的指南。](manage-updates-baselines-microsoft-defender-antivirus.md)

## <a name="uninstall-symantec"></a>卸载 Symantec

现在，你已将组织的设备载入 Microsoft Defender for Endpoint，下一步是卸载 Symantec。

1. [在](https://knowledge.broadcom.com/external/article?legacyId=tech192023) Symantec 中禁用防篡改保护。

2. 删除 Symantec 的卸载密码：<br/>

   1. 在 Windows设备上，以管理员角色打开注册表编辑器。

   2. 转到 `HKEY_LOCAL_MACHINE\SOFTWARE\Symantec\Symantec Endpoint Protection\SMC`。

   3. 查找名为 **SmcInstData 的条目**。 

   4. 右键单击该项，然后选择"删除 **"。** 

3. 从设备中删除 Symantec。 如果需要相关帮助，请参阅 Broadcom 的文档。 下面是一些 Broadcom 资源： 

   - [卸载 Symantec Endpoint Protection](https://knowledge.broadcom.com/external/article/156148/uninstall-symantec-endpoint-protection.html)

   - Windows设备：手动[卸载 Endpoint Protection 上的 14 Windows](https://knowledge.broadcom.com/external/article?articleId=170040)
   
   - macOS 计算机 [：使用 RemoveSymantecMacFiles 删除适用于 Mac 的 Symantec 软件](https://knowledge.broadcom.com/external/article?articleId=151387)
   
   - Linux 设备[：Linux 上的Endpoint Protection常见问题](https://knowledge.broadcom.com/external/article?articleId=162054)

## <a name="make-sure-microsoft-defender-for-endpoint-is-working-correctly"></a>确保 Microsoft Defender for Endpoint 正常工作

现在，你已卸载 Symantec，下一步是确保 Defender for Endpoint 正常工作。 访问 Microsoft Defender for Endpoint 演示方案站点 [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) () 。 尝试该页面上的一个或多个演示方案，包括至少以下方案：
- 云端保护
- PUA (可能不需要) 
- 网络保护 (NP) 

## <a name="next-steps"></a>后续步骤

**恭喜！** 你已完成从 [Symantec](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)到 Microsoft Defender for Endpoint 的迁移！ 
- [访问安全操作仪表板](security-operations-dashboard.md) [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ，Microsoft Defender 安全中心 () 。 
- [管理 Microsoft Defender for Endpoint，迁移后](manage-atp-post-migration.md)。
