---
title: 使用移动设备管理工具载入 Windows 设备
description: 使用移动设备管理工具在设备上部署配置包，以便它们可以载入 Defender for Endpoint 服务。
keywords: 使用 mdm 载入设备， 设备管理， Microsoft Defender for Endpoint设备， mdm
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f3b13df5b9368609e888b92cbba49a58a0db3008
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634748"
---
# <a name="onboard-windows-devices-using-mobile-device-management-tools"></a>使用移动设备管理工具载入 Windows 设备

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)。

可以使用移动设备管理 (MDM) 配置Windows 10设备。 Defender for Endpoint 通过提供创建OMA-URIs管理设备的策略来支持 MDM。


有关为终结点 CSP 使用 Defender 的信息，请参阅 [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) 和 [WindowsAdvancedThreatProtection DDF 文件](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)。

## <a name="before-you-begin"></a>开始之前

如果你使用的是设备Microsoft Intune，则必须已注册设备 MDM。 否则，设置将不能成功应用。

有关使用移动设备启用 MDM Microsoft Intune，请参阅设备[注册 (Microsoft Intune) ](/mem/intune/enrollment/device-enrollment)。

## <a name="onboard-devices-using-microsoft-intune"></a>使用移动设备载入Microsoft Intune

请查看 [PDF 或](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)[Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx)查看部署 Defender for Endpoint 中的各种路径。

按照以下命令中的[Intune](/mem/intune/protect/advanced-threat-protection-configure)。

有关为终结点 CSP 使用 Defender 的信息，请参阅 [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) 和 [WindowsAdvancedThreatProtection DDF 文件](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)。

> [!NOTE]
>
> - 载入 **设备的运行状况策略** 使用只读属性，并且无法修正。
> - 诊断数据报告频率的配置仅适用于 Windows 10 版本 1703 上的设备。


请查看 [PDF 或](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)[Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx)查看部署部署策略时Microsoft Defender for Endpoint。

## <a name="run-a-detection-test-to-verify-onboarding"></a>运行检测测试以验证载入
载入设备后，你可以选择运行检测测试，以验证设备是否正确载入到服务。 有关详细信息，请参阅[在新载入](run-detection-test.md)的设备上运行检测Microsoft Defender for Endpoint测试。


## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>使用移动和移动设备工具设备管理设备

出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。 发送到设备的过期载出包将被拒绝。 下载载出包时，你将收到程序包到期日期的通知，该日期也将包含在程序包名称中。

> [!NOTE]
> 不得同时在同一设备上部署载入和载出策略，否则将导致不可预知的冲突。

1. 从门户获取Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">包</a>：

   1. 在导航窗格中，选择"**设置** \> **终结点设备** \> **管理** \> **""载出"**。

   1. 选择Windows 10或Windows 11操作系统。

   1. 在"**部署方法"** 字段中，选择"**移动设备管理/Microsoft Intune**。

   1. 单击 **下载程序包**，然后保存.zip文件。

2. 将 .zip 文件的内容解压缩到将部署包的网络管理员可以访问的共享只读位置。 你应该有一个名为 *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding 的文件*。

3. 使用Microsoft Intune配置策略部署以下受支持的 OMA-URI 设置。
   - OMA-URI：./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding
   - 日期类型：String
   - 值：[复制并粘贴 WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding 文件的内容中的值]

有关策略设置Microsoft Intune，请参阅Windows 10[策略设置Microsoft Intune](/mem/intune/configuration/custom-settings-windows-10)。

> [!NOTE]
> " **载出设备的运行状况状态"策略** 使用只读属性，并且无法修正。

> [!IMPORTANT]
> "载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留 6 个月。

## <a name="related-topics"></a>相关主题
- [使用组策略载入 Windows 设备](configure-endpoints-gp.md)
- [使用 Microsoft Endpoint Configuration Manager 载入 Windows 设备](configure-endpoints-sccm.md)
- [使用本地脚本载入 Windows 设备](configure-endpoints-script.md)
- [载入非永久虚拟桌面基础结构 （VDI） 设备](configure-endpoints-vdi.md)
- [在新载入的设备上运行检测Microsoft Defender for Endpoint测试](run-detection-test.md)
- [载入Microsoft Defender for Endpoint疑难解答](troubleshoot-onboarding.md)
