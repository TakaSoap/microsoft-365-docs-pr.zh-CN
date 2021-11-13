---
title: 使用Windows 10 Windows 11脚本载入设备和设备
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: 使用本地脚本在设备上部署配置包，以便它们可以载入到服务。
ms.openlocfilehash: 14412e782cffd597786a4d2c322fe2b8fc20e5ca
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950818"
---
# <a name="onboard-windows-10-and-windows-11-devices-using-a-local-script"></a>使用Windows 10 Windows 11脚本载入设备和设备

**适用于：**

- [Microsoft 365 DLP (终结点数据丢失) ](./endpoint-dlp-learn-about.md)
- [内部风险管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

还可以手动载入各个设备以Microsoft 365。 在承诺载入网络内的所有设备之前，你可能希望先在测试服务时这样做。

> [!IMPORTANT]
> 此脚本已优化为在最多 10 台设备上使用。
>
> 若要大规模部署，请使用 [其他部署选项](device-onboarding-overview.md)。 例如，可以使用在使用组策略的载入Windows 10中提供的脚本，将载入脚本部署到生产中的 10[多个设备](device-onboarding-gp.md)。

## <a name="onboard-devices"></a>载入设备
 
1. 从 Microsoft 合规性.zip获取 *(DeviceComplianceOnboardingPackage.zip)* 包 [中的配置包文件](https://compliance.microsoft.com)

2. 在导航窗格中，选择 <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**"设置**</a>  >  **载入"。**

3. 在"**部署方法"** 字段中，选择"**本地脚本"。**

4. 单击 **下载程序包** 并保存.zip文件。
  
5. 将配置包的内容解压缩到你想要载入 (的位置，例如桌面) 。 你应该有一个名为 *DeviceOnboardingScript.cmd 的文件*。

6. 在设备上打开提升的命令行提示符并运行脚本：

7. 转到“**开始**”并键入“**cmd**”。

8. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

    ![指向"开始"菜单以管理员角色运行"的窗口。](../media/dlp-run-as-admin.png)

9. 键入脚本文件的位置。 如果将文件复制到桌面，请键入 *：%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10. 按 **Enter 键** 或单击"确定 **"。**

若要了解如何手动验证设备是否合规并正确报告传感器数据，请参阅 Microsoft Defender 高级威胁防护 [载入问题疑难解答](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)。

## <a name="offboard-devices-using-a-local-script"></a>使用本地脚本的载出设备

出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。 发送到设备的过期载出包将被拒绝。 下载载出包时，你将收到程序包到期日期的通知，该日期也将包含在程序包名称中。

> [!NOTE]
> 不得同时在同一设备上部署载入和载出策略，否则将导致不可预知的冲突。

1. 从 Microsoft 365 合规中心 获取<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心。</a>

2. 在导航窗格中，选择 <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**"设置**</a>  >  **设备载出"。**

3. 在"**部署方法"** 字段中，选择"**本地脚本"。**

4. 单击 **下载程序包** 并保存.zip文件。

5. 将 .zip 文件的内容提取到设备可以访问的共享只读位置。 你应该有一个名为 *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd 的文件*。

6. 在设备上打开提升的命令行提示符并运行脚本：

7. 转到“**开始**”并键入“**cmd**”。

8. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

    ![指向"开始"菜单以管理员角色运行"的窗口。](../media/dlp-run-as-admin.png)

9. 键入脚本文件的位置。 如果将文件复制到桌面，请键入 *：%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

10. 按 **Enter 键** 或单击"确定 **"。**

> [!IMPORTANT]
> 载出导致设备停止向门户发送传感器数据。

## <a name="monitor-device-configuration"></a>监视设备配置

你可以按照 [载入问题疑难解答] ( (/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) 中的不同验证步骤来验证脚本是否成功完成且代理正在运行。

也可以直接在门户上或使用不同的部署工具进行监视。

### <a name="monitor-devices-using-the-portal"></a>使用门户监视设备

1. 转到["Microsoft 365合规中心"。](https://compliance.microsoft.com)

2. 选择 **设置**  >  **设备**  >  **载入设备"。**

1. 转到"Microsoft 365 合规中心"，然后选择 <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**"设置**</a>  >  **载入**  >  **设备"。**

1. 验证设备是否显示。

## <a name="related-topics"></a>相关主题
- [使用Windows 10组Windows 11载入和加入设备](device-onboarding-gp.md)
- [使用 Windows 10 Windows 11载入设备和 Microsoft Endpoint Configuration Manager](device-onboarding-sccm.md)
- [使用Windows 10管理工具Windows 11移动设备和移动设备](device-onboarding-mdm.md)
- [载入非永久虚拟桌面基础结构 （VDI） 设备](device-onboarding-vdi.md)
- [在新载入的 Microsoft Defender 终结点设备上运行检测测试](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender 高级威胁防护载入问题疑难解答](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)