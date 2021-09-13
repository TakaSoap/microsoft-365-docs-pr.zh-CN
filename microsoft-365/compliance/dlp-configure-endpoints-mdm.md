---
title: 使用移动设备管理工具载入 Windows 10 设备
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
description: 使用移动设备管理工具在设备上部署配置包，以便它们可以载入到服务。
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59175590"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>使用移动设备管理工具载入 Windows 10 设备

**适用于：**

- [Microsoft 365DLP (终结点数据丢失) ](./endpoint-dlp-learn-about.md)

可以使用移动设备管理 (MDM) 配置设备。 Microsoft 365终结点数据丢失防护通过提供用于创建OMA-URIs管理设备的策略来支持 MDM。


## <a name="before-you-begin"></a>开始之前
如果你使用的是 mdm Microsoft Intune，则必须注册设备 MDM。 否则，设置将不会成功应用。 

有关使用移动设备启用 MDM Microsoft Intune，请参阅设备[注册 (Microsoft Intune) 。 ](/mem/intune/enrollment/device-enrollment)

## <a name="onboard-devices-using-microsoft-intune"></a>使用移动设备载入Microsoft Intune

按照 [Intune 中的说明操作](/intune/advanced-threat-protection)。

> [!NOTE]
> - 载入 **设备的运行状况策略** 使用只读属性，并且无法修正。

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>使用移动设备管理工具离开并监视设备

出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。 发送到设备的过期载出包将被拒绝。 下载载出包时，你将收到程序包到期日期的通知，该日期也将包含在程序包名称中。

> [!NOTE]
> 不得同时在同一设备上部署载入和载出策略，否则将导致不可预知的冲突。

1. 从 Microsoft 合规性中心获取 [载出包](https://compliance.microsoft.com/)。

2. 在导航窗格中，选择 **"设置**  >  **载入**  >  **""载出"。**

3. 在"**部署方法"** 字段中，选择 **"移动设备管理/Microsoft Intune"。**
    
4. 单击 **"下载程序包**"，然后保存.zip文件。

5. 将 .zip 文件的内容解压缩到将部署包的网络管理员可以访问的共享只读位置。 你应该有一个名为 *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding 的文件*。

6. 使用Microsoft Intune配置策略部署以下受支持的 OMA-URI 设置。

      OMA-URI：./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      日期类型：String      
      值：[复制并粘贴 DeviceCompliance_valid_until_YYYY-MM-DD.offboarding 文件的内容中的值]

有关策略设置Microsoft Intune，请参阅 Windows 10[中的策略Microsoft Intune。](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)

> [!NOTE]
> " **载出设备的运行状况状态"策略** 使用只读属性，并且无法修正。

> [!IMPORTANT]
> "载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留 6 个月。

## <a name="related-topics"></a>相关主题
- [使用Windows 10载入设备](dlp-configure-endpoints-gp.md)
- [使用Windows 10载入设备Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [使用本地脚本载入 Windows 10 设备](dlp-configure-endpoints-script.md)
- [载入非永久虚拟桌面基础结构 （VDI） 设备](dlp-configure-endpoints-vdi.md)
- [Microsoft Defender 高级威胁防护载入问题疑难解答](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)