---
title: 通过Windows 10 Windows 11载入设备和设备
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: 使用组策略在 Windows 10 和 Windows 11部署配置包，以便它们可以载入到服务。
ms.openlocfilehash: fbba73fcf15ee9f71c4caacc57155a64e6cb9e9c
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950813"
---
# <a name="onboard-windows-10-devices-and-windows-11-using-group-policy"></a>使用Windows 10组策略Windows 11设备和设备载入 

**适用于：**

- [Microsoft 365 DLP (终结点数据丢失) ](./endpoint-dlp-learn-about.md)
- [内部风险管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)
- 组策略

> [!NOTE]
> 若要使用组策略 (GP) 更新来部署程序包，必须在 Windows Server 2008 R2 或更高版本上。

> 对于 Windows Server 2019，您可能需要将 NT AUTHORITY\Well-Known-System-Account 替换为组策略首选项创建的 XML 文件的 NT AUTHORITY\SYSTEM。

## <a name="onboard-devices-using-group-policy"></a>使用组策略载入设备

1. 打开合规 [中心](https://compliance.microsoft.com)。

2. 在导航窗格中，选择 **"设置**  >  **载入"。**

3. 在"**部署方法"** 字段中，选择"**组策略"。**

4. 单击 **下载程序包** 并保存.zip文件。

5. 将 .zip 文件的内容提取到设备可以访问的共享只读位置。 你应该有一个称为 *OptionalParamsPolicy* 的文件夹和文件 *DeviceComplianceLocalOnboardingScript.cmd*。

6. 打开组策略管理控制台 [ (](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC) ，右键单击要配置的组策略对象 (GPO) 然后单击 **编辑。**

7. 在组 **策略管理编辑器中**，转到"**计算机配置**"，然后转到"**首选项**"，然后转到"**控制面板设置"。**

8. 右键单击 **计划任务**，指向 **新建**，然后单击即时任务 (**至少Windows 7)**。

9. 在打开 **的任务** 窗口中，转到常规 **选项卡**。在 **"安全选项"** 下，单击 **"更改用户或组**"，然后键入"系统"，然后单击"**检查名称**"，然后单击"确定 **"。** NT AUTHORITY\SYSTEM 显示为任务将运行的用户帐户。

10. Select **Run whether user is logged on or not and** check the Run with highest **privileges** check box.

11. 转到"操作 **"选项卡** ，然后单击" **新建..."。** 确保在 **"操作"** 字段中选择了"启动 **程序** "。 输入共享 *WindowsDefenderATPOnboardingScript.cmd* 文件的文件名和位置。

12. 单击 **"确定** "并关闭任何打开的 GPMC 窗口。

## <a name="offboard-devices-using-group-policy"></a>使用组策略的载出设备
出于安全考虑，用于载出设备的程序包将在下载日期 30 天后过期。 发送到设备的过期载出包将被拒绝。 下载载出包时，你将收到程序包到期日期的通知，该日期也将包含在程序包名称中。

> [!NOTE]
> 不得同时在同一设备上部署载入和载出策略，否则将导致不可预知的冲突。

1. 从 Microsoft 合规性中心获取 [载出包](https://compliance.microsoft.com/compliancesettings/deviceonboarding)。

2. 在导航窗格中，**选择**  >  **"设置//设备载入**  >  **""载出"。**

3. 在"**部署方法"** 字段中，选择"**组策略"。**

4. 单击 **下载程序包** 并保存.zip文件。

5. 将 .zip 文件的内容提取到设备可以访问的共享只读位置。 你应该有一个名为 *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd 的文件*。

6. 打开组策略管理控制台 [ (](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) GPMC) ，右键单击要配置的组策略对象 (GPO) 然后单击 **编辑。**

7. 在组 **策略管理编辑器中**，转到"**计算机配置"，然后** 转到"**首选项**"，然后转到"**控制面板设置"。**

8. 右键单击 **"计划任务"，** 指向 **"新建"，** 然后单击"**立即任务"。**

9. 在打开 **的任务** 窗口中，转到常规 **选项卡** 。在"安全选项"下 ("BUILTIN\SYSTEM **) "下选择本地系统用户帐户**。

10. Select **Run whether user is logged on or not and** check the Run with highest **privileges** check-box.

11. 转到"操作 **"选项卡** ，然后单击"新建 **..."。** 确保在 **"操作"** 字段中选择了"启动 **程序** "。 输入共享文件的文件名和  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* 文件。

12. 单击 **"确定** "并关闭任何打开的 GPMC 窗口。

> [!IMPORTANT]
> 载出会导致设备停止向门户发送传感器数据，但从设备发送数据。


## <a name="monitor-device-configuration"></a>监视设备配置
借助组策略，无法监视设备上策略的部署。 可以直接在门户上或使用不同的部署工具进行监视。

## <a name="monitor-devices-using-the-portal"></a>使用门户监视设备
1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心</a>。
2. 单击 **"设备列表** "。
3. 验证设备是否显示。

> [!NOTE]
> 设备可能需要几天时间才能开始在 **"设备"列表上显示**。 这包括将策略分发到设备所花的时间、用户登录之前所花的时间以及终结点开始报告所花的时间。


## <a name="related-topics"></a>相关主题
- [使用 Windows 10 Windows 11载入设备和 Microsoft Endpoint Configuration Manager](device-onboarding-sccm.md)
- [使用Windows 10管理工具Windows 11移动设备和移动设备](device-onboarding-mdm.md)
- [使用Windows 10 Windows 11脚本载入设备和设备](device-onboarding-script.md)
- [载入非永久虚拟桌面基础结构 （VDI） 设备](device-onboarding-vdi.md)
- [对新载入的适用于终结点的 Microsoft Defender 设备运行检测测试](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender 高级威胁防护载入问题疑难解答](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)