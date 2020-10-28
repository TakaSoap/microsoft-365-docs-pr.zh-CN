---
title: 通过组策略的板载 Windows 10 设备
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 使用组策略在 Windows 10 设备上部署配置包，以使其载入服务。
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769398"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>使用组策略的板载 Windows 10 设备 

**适用于：**

- [Microsoft 365 Endpoint data 丢失防护 (DLP) ](/microsoft-365/compliance/endpoint-dlp-learn-about)
- 组策略

> [!NOTE]
> 若要使用组策略 (GP) 部署程序包的更新，您必须在 Windows Server 2008 R2 或更高版本上。

> 对于 Windows Server 2019，您可能需要将 NT AUTHORITY\Well-Known-System-Account 替换为组策略首选项所创建的 XML 文件的 NT AUTHORITY\SYSTEM。

## <a name="onboard-devices-using-group-policy"></a>使用组策略的板载设备

1. 打开您从 "服务载入" 向导下载 *DeviceComplianceOnboardingPackage.zip* )  (的 GP configuration 包 .zip 文件。 你也可以从[Microsoft 合规性中心](https://compliance.microsoft.com/compliancesettings/deviceonboarding)获取程序包

2. 在导航窗格中，选择 " **设置**  >  **设备载入** "。

3. 在 " **部署方法** " 字段中，选择 " **组策略** "。

4. 单击 " **下载包** " 并保存该 .zip 文件。

5. 将 .zip 文件的内容提取到可由设备访问的共享只读位置。 您应该具有一个名为 *OptionalParamsPolicy* 的文件夹和文件 *DeviceComplianceLocalOnboardingScript* 。

6. 打开 [组策略管理控制台](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) ，右键单击要配置的组策略对象 (GPO) ，然后单击 " **编辑** "。

7. 在 " **组策略管理编辑器** " 中，依次转到 " **计算机配置** "、" **首选项** " 和 **"控制面板设置"** 。

8. 右键单击 " **计划的任务** "，指向 " **新建** "，然后单击 " **即时任务 (至少是 Windows 7)** 。

9. 在打开的 **任务** 窗口中，转到 " **常规** " 选项卡。在 " **安全选项** " 下，依次单击 " **更改用户或组** 和类型系统 **"** ，然后单击 " **检查名称** "。 NT AUTHORITY\SYSTEM 显示为作为任务运行方式的用户帐户。

10. 选择 " **不管用户是否登录都要运行"** ，然后选中 " **使用最高特权运行** " 复选框。

11. 转到 " **操作** " 选项卡，然后单击 " **新建 ...** "。确保在 " **操作** " 字段中选择 " **启动程序** "。 输入共享 *WindowsDefenderATPOnboardingScript* 文件的文件名和位置。

12. 单击 **"确定"** ，然后关闭任何打开的 GPMC 窗口。


## <a name="offboard-devices-using-group-policy"></a>使用组策略的分离设备
出于安全考虑，用于分离设备的包将在下载后的30天后过期。 发送到设备的已过期的脱离程序包将被拒绝。 下载一个脱离程序包时，系统会通知你提供程序包到期日期，并且它也将包含在包名称中。

> [!NOTE]
> 无法同时在同一设备上部署载入和脱离策略，否则会导致不可预测的冲突。

1. 从 [Microsoft 合规性中心](https://compliance.microsoft.com/compliancesettings/deviceonboarding)获取脱离程序包。

2. 在导航窗格中，选择 " **设置** "  >  **//Device "加入**  >  **脱离** "。

3. 在 " **部署方法** " 字段中，选择 " **组策略** "。

4. 单击 " **下载包** " 并保存该 .zip 文件。

5. 将 .zip 文件的内容提取到可由设备访问的共享只读位置。 您应具有一个名为 *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd* 的文件。

6. 打开 [组策略管理控制台](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) ，右键单击要配置的组策略对象 (GPO) ，然后单击 " **编辑** "。

7. 在 " **组策略管理编辑器** " 中，依次转到 " **计算机配置"、** " **首选项** " 和 **"控制面板设置"** 。

8. 右键单击 " **任务计划** "，指向 " **新建** "，然后单击 " **即时任务** "。

9. 在打开的 **任务** 窗口中，转到 " **常规** " 选项卡。在 " **安全选项** " 下的 " (BUILTIN\SYSTEM) 中选择" 本地系统 "用户帐户。

10. 选择 " **不管用户是否登录都要运行** "，然后选中 " **使用最高权限运行** " 复选框。

11. 转到 " **操作** " 选项卡，然后单击 " **新建 ...** "。确保在 " **操作** " 字段中选择 " **启动程序** "。 输入共享  *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd* 文件的文件名和位置。

12. 单击 **"确定"** ，然后关闭任何打开的 GPMC 窗口。

> [!IMPORTANT]
> 脱离将导致设备停止将传感器数据发送到门户，而不是来自设备的数据。


## <a name="monitor-device-configuration"></a>监视设备配置
使用组策略时，没有选项可监视设备上的策略部署。 可以直接在门户或使用不同的部署工具进行监视。

## <a name="monitor-devices-using-the-portal"></a>使用门户监视设备
1. 转到 [Microsoft 合规性中心](https://compliance.microsoft.com/)。
2. 单击 " **设备** 列表"。
3. 验证设备是否显示。

> [!NOTE]
> 可能需要几天的时间才能在 " **设备" 列表** 中显示设备。 这包括将策略分发给设备所需的时间、用户登录前所需的时间以及终结点开始报告所需的时间。


## <a name="related-topics"></a>相关主题
- [使用 Microsoft 终结点配置管理器的板载 Windows 10 设备](dlp-configure-endpoints-sccm.md)
- [使用移动设备管理工具的板载 Windows 10 设备](dlp-configure-endpoints-mdm.md)
- [使用本地脚本的板载 Windows 10 设备](dlp-configure-endpoints-script.md)
- [ (VDI) 设备的板载非永久性虚拟桌面基础结构](dlp-configure-endpoints-vdi.md)
- [在新载入上运行检测测试 Microsoft Defender ATP 设备](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [解决 Microsoft Defender 高级威胁防护载入问题](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
