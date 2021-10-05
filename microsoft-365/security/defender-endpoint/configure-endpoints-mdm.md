---
title: 使用Windows管理工具载入设备
description: 使用移动设备管理工具在设备上部署配置包，以便它们可以载入服务。
keywords: 使用 mdm 载入设备， 设备管理， 载入 Microsoft Defender for Endpoint 设备， mdm
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6cb99f300c7d87497f31729507695a9a633b345a
ms.sourcegitcommit: d78553deeba23d2f8238f10e64c2e27f235dc37f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2021
ms.locfileid: "60124693"
---
# <a name="onboard-the-windows-devices-using-mobile-device-management-tools"></a>使用Windows管理工具载入新设备

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)。

可以使用移动设备管理 (MDM) 配置设备。 Defender for Endpoint 通过提供创建OMA-URIs管理设备的策略来支持 MDM。

有关使用 Defender for Endpoint CSP 有关详细信息，请参阅 [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) 和 [WindowsAdvancedThreatProtection DDF 文件](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)。

## <a name="before-you-begin"></a>准备工作

如果你使用的是 Microsoft Intune，则必须已注册设备 MDM。 否则，设置将不能成功应用。

有关使用移动设备启用 MDM Microsoft Intune，请参阅设备[注册 (Microsoft Intune) 。 ](/mem/intune/enrollment/device-enrollment)

## <a name="onboard-devices-using-microsoft-intune"></a>使用移动设备载入Microsoft Intune

请查看[PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)或[Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx)查看部署 Defender for Endpoint 的各种路径。

按照 [Intune 中的说明操作](/intune/advanced-threat-protection)。

有关使用 Defender for Endpoint CSP 有关详细信息，请参阅 [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) 和 [WindowsAdvancedThreatProtection DDF 文件](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)。

> [!NOTE]
>
> - 载入 **设备的运行状况策略** 使用只读属性，并且无法修正。
> - 诊断数据报告频率的配置仅适用于 Windows 10 版本 1703 上的设备。


请查看[PDF 或](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf) [Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx)查看部署 Microsoft Defender for Endpoint 的各种路径。

## <a name="run-a-detection-test-to-verify-onboarding"></a>运行检测测试以验证载入
载入设备后，你可以选择运行检测测试，以验证设备是否正确载入到服务。 有关详细信息，请参阅对新载入的 [Microsoft Defender for Endpoint](run-detection-test.md)设备运行检测测试。


## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>使用移动设备管理工具离开并监视设备

出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。 发送到设备的过期载出包将被拒绝。 下载载出包时，你将收到程序包到期日期的通知，该日期也将包含在程序包名称中。

> [!NOTE]
> 不得同时在同一设备上部署载入和载出策略，否则将导致不可预知的冲突。

1. 从门户获取Microsoft 365 Defender[包](https://security.microsoft.com/)：

   1. 在导航窗格中，选择 **"设置** \>  \> **终结点设备管理** \> **""载出"。**

   1. 选择Windows 10或Windows 11 作为操作系统。

   1. 在"**部署方法"** 字段中，选择 **"移动设备管理/Microsoft Intune"。**

   1. 单击 **"下载程序包**"，然后保存.zip文件。

2. 将 .zip 文件的内容解压缩到将部署包的网络管理员可以访问的共享只读位置。 你应该有一个名为 *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding 的文件*。

3. 使用Microsoft Intune配置策略部署以下受支持的 OMA-URI 设置。
   - OMA-URI：./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding
   - 日期类型：String
   - 值：[复制并粘贴文件内容中的WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding 文件]

有关策略设置Microsoft Intune，请参阅 Windows 10[中的策略Microsoft Intune。](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)

> [!NOTE]
> " **载出设备的运行状况状态"策略** 使用只读属性，并且无法修正。

> [!IMPORTANT]
> "载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留 6 个月。

## <a name="related-topics"></a>相关主题

- [使用Windows载入设备](configure-endpoints-gp.md)
- [使用Windows载入设备Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [使用Windows脚本载入设备](configure-endpoints-script.md)
- [载入非永久虚拟桌面基础结构 （VDI） 设备](configure-endpoints-vdi.md)
- [在新载入的 Microsoft Defender 终结点设备上运行检测测试](run-detection-test.md)
- [Microsoft Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)
