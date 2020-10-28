---
title: 使用移动设备管理工具的板载 Windows 10 设备
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
description: 使用移动设备管理工具在设备上部署配置包，以使其载入服务。
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769408"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>使用移动设备管理工具的板载 Windows 10 设备

**适用于：**

- [Microsoft 365 Endpoint data 丢失防护 (DLP) ](/microsoft-365/compliance/endpoint-dlp-learn-about)

您可以使用 (MDM) 解决方案的移动设备管理来配置设备。 Microsoft 365 终结点数据丢失防护通过提供 OMA-URIs 来创建用于管理设备的策略，从而支持 MDMs。


## <a name="before-you-begin"></a>准备工作
如果使用的是 Microsoft Intune，则必须注册设备 MDM。 否则，将无法成功应用设置。 

有关使用 Microsoft Intune 启用 MDM 的详细信息，请参阅 [Device 注册 (Microsoft intune) ](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)。

## <a name="onboard-devices-using-microsoft-intune"></a>使用 Microsoft Intune 的板载设备

按照 [Intune](https://docs.microsoft.com/intune/advanced-threat-protection)中的说明进行操作。

> [!NOTE]
> - **载入设备策略的运行状况状态** 使用只读属性，不能修正。

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>使用移动设备管理工具分离和监控设备

出于安全考虑，用于分离设备的包将在下载后的30天后过期。 发送到设备的已过期的脱离程序包将被拒绝。 下载一个脱离程序包时，系统会通知你提供程序包到期日期，并且它也将包含在包名称中。

> [!NOTE]
> 无法同时在同一设备上部署载入和脱离策略，否则会导致不可预测的冲突。

1. 从 [Microsoft 合规性中心](https://compliance.microsoft.com/)获取脱离程序包。

2. 在导航窗格中，选择 " **设置**  >  **设备加入**  >  **脱离** "。

3. 在 " **部署方法** " 字段中，选择 " **移动设备管理/Microsoft Intune** "。
    
4. 单击 " **下载包** "，并保存 .zip 文件。

5. 将 .zip 文件的内容提取到一个共享的只读位置，该位置可供将部署该包的网络管理员访问。 应具有一个名为 *DEVICECOMPLIANCE_VALID_UNTIL_YYYY MM 的* 文件。

6. 使用 Microsoft Intune 自定义配置策略部署以下受支持的 OMA URI 设置。

      OMA-URI：./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      日期类型： String      
      值： [从 DeviceCompliance_valid_until_YYYY-DD 文件的内容复制并粘贴值]

有关 Microsoft Intune 策略设置的详细信息，请参阅 [Microsoft intune 中的 Windows 10 策略设置](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)。

> [!NOTE]
> **Offboarded 设备策略的运行状况状态** 使用只读属性，不能修正。

> [!IMPORTANT]
> 脱离将导致设备停止向门户发送传感器数据，但设备中的数据（包括对其已有的任何警报的引用）将保留最长6个月。

## <a name="related-topics"></a>相关主题
- [使用组策略的板载 Windows 10 设备](dlp-configure-endpoints-gp.md)
- [使用 Microsoft 终结点配置管理器的板载 Windows 10 设备](dlp-configure-endpoints-sccm.md)
- [使用本地脚本的板载 Windows 10 设备](dlp-configure-endpoints-script.md)
- [ (VDI) 设备的板载非永久性虚拟桌面基础结构](dlp-configure-endpoints-vdi.md)
- [解决 Microsoft Defender 高级威胁防护载入问题](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
