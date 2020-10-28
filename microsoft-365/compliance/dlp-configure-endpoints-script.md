---
title: 使用本地脚本的板载 Windows 10 设备
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 使用本地脚本在设备上部署配置包，以使其载入服务。
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769406"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>使用本地脚本的板载 Windows 10 设备

**适用于：**

- [Microsoft 365 Endpoint data 丢失防护 (DLP) ](/microsoft-365/compliance/endpoint-dlp-learn-about)

此外，还可以将单个设备手动集成到 Microsoft 365 终结点数据丢失防护中。 在您提交以在网络中加入所有设备之前测试服务时，您可能需要先执行此操作。

> [!IMPORTANT]
> 此脚本已经过优化，可在最多10台设备上使用。
>
> 若要在扩展时部署，请使用 [其他部署选项](dlp-configure-endpoints.md)。 例如，您可以使用组策略将载入脚本部署到生产环境中的10个以上的设备，并在 [Windows 10 的板载 Windows 10 设备](dlp-configure-endpoints-gp.md)中提供的脚本。

## <a name="onboard-devices"></a>板载设备
 
1.  打开您从 "服务载入" 向导下载 *DeviceComplianceOnboardingPackage.zip* )  (的 GP configuration 包 .zip 文件。 你也可以从[Microsoft 合规性中心](https://compliance.microsoft.com)获取程序包

2. 在导航窗格中，选择 " **设置**  >  **设备载入** "。

3. 在 " **部署方法** " 字段中，选择 " **本地脚本** "。

4. 单击 " **下载包** " 并保存该 .zip 文件。
  
5. 将配置包的内容解压缩到设备上要板载 (的位置。例如，桌面) 。 您应该具有一个名为 *DeviceOnboardingScript* 的文件。

6.  在设备上打开提升的命令行提示符并运行脚本：

7.  转到 " **开始** " 并键入 **cmd** 。

8.  右键单击 " **命令提示符** "，然后选择 " **以管理员身份运行** "。

![指向 "以管理员身份运行" 窗口的 "开始" 菜单](../media/dlp-run-as-admin.png)

9.  键入脚本文件的位置。 如果将文件复制到桌面，请键入： *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10.  按 **enter** 键或单击 **"确定"** 。

有关如何手动验证设备是否合规并正确报告传感器数据的信息，请参阅 [解决 Microsoft Defender 高级威胁防护的载入问题](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)。

## <a name="offboard-devices-using-a-local-script"></a>使用本地脚本的分离设备
出于安全考虑，用于分离设备的包将在下载后的30天后过期。 发送到设备的已过期的脱离程序包将被拒绝。 下载一个脱离程序包时，系统会通知你提供程序包到期日期，并且它也将包含在包名称中。

> [!NOTE]
> 无法同时在同一设备上部署载入和脱离策略，否则会导致不可预测的冲突。

1. 从[Microsoft 合规性中心](https://compliance.microsoft.com)获取脱离程序包

2. 在导航窗格中，选择 " **设置**  >  **设备脱离** "。

3. 在 " **部署方法** " 字段中，选择 " **本地脚本** "。

4. 单击 " **下载包** " 并保存该 .zip 文件。

5. 将 .zip 文件的内容提取到可由设备访问的共享只读位置。 您应具有一个名为 *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd* 的文件。

6.  在设备上打开提升的命令行提示符并运行脚本：

7.  转到 " **开始** " 并键入 **cmd** 。

8.  右键单击 " **命令提示符** "，然后选择 " **以管理员身份运行** "。

![指向 "以管理员身份运行" 窗口的 "开始" 菜单](../media/dlp-run-as-admin.png)

9.  键入脚本文件的位置。 如果将文件复制到桌面，请键入： *%userprofile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd*

10.  按 **enter** 键或单击 **"确定"** 。

> [!IMPORTANT]
> 脱离将导致设备停止将传感器数据发送到门户。


## <a name="monitor-device-configuration"></a>监视设备配置
您可以按照 [解决载入问题] ( # B1 中的不同验证步骤操作， https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) 以验证脚本是否已成功完成且代理正在运行。

还可以直接在门户或使用不同的部署工具进行监视。

### <a name="monitor-devices-using-the-portal"></a>使用门户监视设备
1. 转到 [Microsoft 365 合规性中心](https://compliance.microsoft.com)。

2. 选择 " **设置**  >  **设备加入**  >  **设备"** 。

3. 验证设备是否显示。


## <a name="related-topics"></a>相关主题
- [使用组策略的板载 Windows 10 设备](dlp-configure-endpoints-gp.md)
- [使用 Microsoft 终结点配置管理器的板载 Windows 10 设备](dlp-configure-endpoints-sccm.md)
- [使用移动设备管理工具的板载 Windows 10 设备](dlp-configure-endpoints-mdm.md)
- [ (VDI) 设备的板载非永久性虚拟桌面基础结构](dlp-configure-endpoints-vdi.md)
- [在新载入上运行检测测试 Microsoft Defender ATP 设备](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [解决 Microsoft Defender 高级威胁防护载入问题](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
