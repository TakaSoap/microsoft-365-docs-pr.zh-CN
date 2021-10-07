---
title: Microsoft Defender for Endpoint 的最低要求
description: 了解将设备载入到服务的许可要求
keywords: 最低要求， 许可， 比较表
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fcfce563a177dd90e312da2da3bc578ec39b15b5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152042"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 的最低要求

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-minreqs-abovefoldlink)。

将设备载入到服务有一些最低要求。 了解许可、硬件和软件要求以及其他配置设置，以将设备载入服务。

> [!TIP]
>
> - 本文介绍了 Microsoft Defender 终结点计划 2 的最低要求。 如果你要查找有关 Defender for Endpoint Plan 1 (preview) 的信息，请参阅 Defender [for Endpoint Plan 1 (preview) ](mde-p1-setup-configuration.md#review-the-requirements)。
> - 了解 Defender for Endpoint： Defender [for Endpoint Tech](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)Community 中的最新增强功能。
> - Defender for Endpoint 在最新的 MITRE 评估中展示了行业领先的光学镜头和检测功能。 阅读：[来自基于 MITRE ATT&CK 的评估的见解](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。

## <a name="licensing-requirements"></a>许可要求

Microsoft Defender for Endpoint 需要以下 Microsoft 批量许可优惠之一：

- Windows 11 Enterprise E5
- Windows 11 教育版 A5
- Windows 10 企业版E5
- Windows 10 教育版 A5
- Microsoft 365 E5 (M365 E5) 包括 Windows 10 企业版 E5 或 Windows 11 Enterprise E5
- Microsoft 365 A5 (M365 A5) 
- Microsoft 365 E5 安全性
- Microsoft 365 A5 安全性
- Microsoft Defender for Endpoint

> [!NOTE]
> 符合条件的许可用户可以在最多五台并发设备上使用 Microsoft Defender for Endpoint。
> Microsoft Defender for Endpoint 还可从云解决方案提供商云解决方案提供商 (购买) 。
> RDSH VM 不需要单独的 Defender for Endpoint 许可证。

适用于服务器的 Microsoft Defender for Endpoint 需要以下许可选项之一：

- [启用 Azure Defender 的 Azure 安全中心](/azure/security-center/security-center-pricing)
- Microsoft Defender for Endpoint for Server (覆盖的服务器服务器配置一) 

> [!NOTE]
> 如果 (对于以下一个或多个用户许可证，客户至少可以获取 50 个许可证，每个覆盖的服务器操作系统环境 (OSE) ) 可以获取一个服务器许可证：
>
> - Microsoft Defender for Endpoint
> - WindowsE5/A5
> - Microsoft 365 E5/A5
> - Microsoft 365 E5/A5 安全性

有关许可的详细信息，请参阅产品 [条款网站](https://www.microsoft.com/licensing/terms/) ，并与你的帐户团队合作，了解有关条款和条件的详细信息。

有关不同版本中功能数组Windows，请参阅[比较Windows版本](https://www.microsoft.com/windowsforbusiness/compare)。

## <a name="browser-requirements"></a>浏览器要求

通过浏览器（支持以下浏览器）访问 Defender for Endpoint：

- Microsoft Edge
- Google Chrome

> [!NOTE]
> 虽然其他浏览器可能正常工作，但所提及的浏览器是受支持的浏览器。

## <a name="hardware-and-software-requirements"></a>硬件和软件要求

### <a name="supported-windows-versions"></a>支持的 Windows 版本

- Windows 7 SP1 Enterprise ([需要 ESU 以支持](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).) 
- Windows 7 SP1 Pro ([需要 ESU 以支持](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).) 
- Windows 8.1 企业版
- Windows 8.1 专业版
- Windows 11 企业版
- Windows 11 教育版
- Windows 11 Pro
- Windows 11 Pro 教育版
- Windows 10 企业版
- [Windows 10 企业版LTSC 2016 (或更高版本) ](/windows/whats-new/ltsc/)
- Windows 10 教育版
- Windows 10 专业版
- Windows 10 专业教育版
- Windows服务器
  - Windows Server 2008 R2 SP1
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows服务器版本 1803 或更高版本
  - Windows Server 2019
  - Windows Server 2022
- Windows 虚拟桌面

你的网络上设备必须运行这些版本之一。

对于受支持的版本，设备上 Defender for Endpoint 的硬件要求相同。

> [!NOTE]
> 不支持运行移动版本的 Windows (（如 Windows CE 和 Windows 10 移动版) ）。
>
> 如果运行Windows 10 企业版 2016 长期服务版非 Microsoft 虚拟化平台上运行，则运行虚拟机可能会遇到性能问题。
>
> 对于虚拟环境，建议使用 Windows 10 企业版 LTSC 2019 或更高版本。

### <a name="other-supported-operating-systems"></a>其他支持的操作系统

- [Android](microsoft-defender-endpoint-android.md)
- [iOS](microsoft-defender-endpoint-ios.md)
- [Linux](microsoft-defender-endpoint-linux.md)
- [macOS](microsoft-defender-endpoint-mac.md)

> [!NOTE]
> 你需要确认 Android、iOS 和 macOS 的 Linux 分发和版本与 Defender for Endpoint 兼容，集成工作。

### <a name="network-and-data-storage-and-configuration-requirements"></a>网络和数据存储以及配置要求

首次运行载入向导时，必须选择 Microsoft Defender 终结点相关信息的存储位置：欧盟、英国或美国数据中心。

> [!NOTE]
>
> - 首次设置后，无法更改数据存储位置。
> - 查看 [适用于终结点的 Microsoft Defender 数据存储](data-storage-privacy.md) 和隐私，详细了解 Microsoft 存储你的数据的位置和方法。

### <a name="diagnostic-data-settings"></a>诊断数据设置

> [!NOTE]
> Microsoft Defender for Endpoint 不需要任何特定的诊断级别，只要它已启用。

确保在你的组织的所有设备上启用了诊断数据服务。
默认情况下，此服务已启用。 最佳做法是检查以确保从它们获取传感器数据。

#### <a name="use-the-command-line-to-check-the-windows-diagnostic-data-service-startup-type"></a>使用命令行检查诊断Windows服务启动类型

1. 在设备上打开提升的命令行提示符：
   1. 转到“**开始**”并键入“**cmd**”。
   2. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

2. 输入以下命令，然后按 **Enter：**

   ```console
   sc qc diagtrack
   ```

   如果服务已启用，则结果应如以下屏幕截图所示：

   ![diagtrack 的 sc 查询命令的结果。](images/windefatp-sc-qc-diagtrack.png)

如果服务未设置为 START_TYPE，则需要将服务设置为自动 **AUTO_START。** 

#### <a name="use-the-command-line-to-set-the-windows-diagnostic-data-service-to-automatically-start"></a>使用命令行将 Windows数据服务设置为自动启动

1. 在终结点上打开提升的命令行提示符：
    1. 转到“**开始**”并键入“**cmd**”。
    2. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

2. 输入以下命令，然后按 **Enter：**

    ```console
    sc config diagtrack start=auto
    ```

3. 将显示成功消息。 通过输入以下命令验证更改，然后按 **Enter：**

    ```console
    sc qc diagtrack
    ```

#### <a name="internet-connectivity"></a>Internet 连接

可直接或通过代理在设备上建立 Internet 连接。

Defender for Endpoint 传感器可以使用每日平均带宽 5 MB 与 Defender for Endpoint 云服务进行通信并报告网络数据。 此每日平均带宽中不包含文件上载和调查包收集等一次活动。

有关其他代理配置设置的信息，请参阅配置 [设备代理和 Internet 连接设置](configure-proxy-internet.md)。

在载入设备之前，必须启用诊断数据服务。 该服务默认在 11 Windows 10 Windows启用。

## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Microsoft Defender 防病毒配置要求

Defender for Endpoint 代理依赖于用户Microsoft Defender 防病毒扫描文件并提供有关文件的信息的能力。

在 Defender for Endpoint 设备上配置安全智能更新Microsoft Defender 防病毒反恶意软件是否有效。 有关详细信息，请参阅管理更新[Microsoft Defender 防病毒应用基线](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)。

如果Microsoft Defender 防病毒在你的组织中不是主动反恶意软件，并且你使用 Defender for Endpoint 服务，Microsoft Defender 防病毒被动模式。

如果组织已通过组策略Microsoft Defender 防病毒关闭已载入的设备，则必须从该组策略中排除已载入的设备。

如果你正在载入服务器，Microsoft Defender 防病毒服务器上不是主动反恶意软件，Microsoft Defender 防病毒需要配置为进入被动模式或卸载。 配置取决于服务器版本。 有关详细信息，请参阅兼容性[Microsoft Defender 防病毒兼容性](microsoft-defender-antivirus-compatibility.md)。

> [!NOTE]
> 常规组策略不适用于防篡改保护，当防篡改保护打开Microsoft Defender 防病毒将忽略对组设置所做的更改。

## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Microsoft Defender 防病毒启用早期启动反恶意软件 (ELAM) 已启用

如果你正在设备上Microsoft Defender 防病毒作为主要的反恶意软件产品，则 Defender for Endpoint 代理将成功载入。

如果正在运行第三方反恶意软件客户端并使用移动设备管理解决方案或 Microsoft Endpoint Manager (current branch) ，则需要确保 Microsoft Defender 防病毒 ELAM 驱动程序已启用。 有关详细信息，请参阅[确保策略Microsoft Defender 防病毒禁用策略。](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)

## <a name="related-topics"></a>相关主题

- [设置 Microsoft Defender for Endpoint 部署](production-deployment.md)
- [载入设备](onboard-configure.md)
