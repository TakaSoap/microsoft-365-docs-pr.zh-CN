---
title: Microsoft Defender for Endpoint 的最低要求
description: 了解将设备载入到服务的许可要求
keywords: 最低要求， 许可， 比较表
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7581c606a7903bd6d32c1e192f35992899289f30
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054742"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 的最低要求

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


将设备载入到服务有一些最低要求。 了解许可、硬件和软件要求以及其他配置设置，以将设备载入服务。

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)。

> [!TIP]
> - 了解 Defender for Endpoint： Defender [for Endpoint 技术社区中的最新增强功能](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)。
> - Defender for Endpoint 在最新的 MITRE 评估中展示了行业领先的光学镜头和检测功能。 阅读 [：MITRE ATT 中的见解&基于 CK 的评估](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。

## <a name="licensing-requirements"></a>许可要求
Microsoft Defender for Endpoint 需要以下 Microsoft 批量许可优惠之一：

- Windows 10 企业版 E5
- Windows 10 教育版 A5
- Microsoft 365 E5 (M365 E5) 包括 Windows 10 企业版 E5
- Microsoft 365 A5 (M365 A5) 
- Microsoft 365 E5 安全版
- Microsoft 365 A5 安全性
- Microsoft Defender for Endpoint

> [!NOTE]
> 符合条件的许可用户可以在最多五台并发设备上使用 Microsoft Defender for Endpoint。
> Microsoft Defender for Endpoint 还可从云解决方案提供商云解决方案提供商 (云解决方案提供商) 。

适用于服务器的 Microsoft Defender for Endpoint 需要以下许可选项之一：

- [启用 Azure Defender 的 Azure 安全中心](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- Microsoft Defender for Endpoint for Server (覆盖的服务器服务器一) 

> [!NOTE]
> 如果 (对于以下一个或多个用户许可证，客户至少可以获取 50 个许可证，每个覆盖的服务器操作系统环境 (OSE) ) （适用于服务器的 Microsoft Defender）每覆盖一个许可证：
>
> * Microsoft Defender for Endpoint
> * Windows E5/A5
> * Microsoft 365 E5/A5
> * Microsoft 365 E5/A5 安全

有关许可的详细信息，请参阅产品 [条款网站](https://www.microsoft.com/licensing/terms/) ，并与你的帐户团队一起了解有关条款和条件的详细信息。

有关 Windows 10 版本中的功能数组详细信息，请参阅 [比较 Windows 10 版本](https://www.microsoft.com/windowsforbusiness/compare)。

有关 Windows 10 商业版比较的详细比较表，请参阅[比较 PDF。](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)

## <a name="browser-requirements"></a>浏览器要求
通过浏览器（支持以下浏览器）访问 Defender for Endpoint：

- Microsoft Edge
- Internet Explorer版本 11
- Google Chrome

> [!NOTE]
> 虽然其他浏览器可能正常工作，但所提及的浏览器是受支持的浏览器。


## <a name="hardware-and-software-requirements"></a>硬件和软件要求

### <a name="supported-windows-versions"></a>受支持的 Windows 版本
- Windows 7 SP1 企业 ([需要 ESU 以支持](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).) 
- Windows 7 SP1 专业 ([需要 ESU 以支持](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).) 
- Windows 8.1 企业版
- Windows 8.1 专业版
- Windows 10 企业版
- [Windows 10 企业版 LTSC](https://docs.microsoft.com/windows/whats-new/ltsc/)
- Windows 10 教育版
- Windows 10 专业版
- Windows 10 专业教育版
- Windows 服务器
  - Windows Server 2008 R2 SP1
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Server 版本 1803 或更高版本
  - Windows Server 2019
- Windows 虚拟桌面

你的网络上设备必须运行这些版本之一。

对于受支持的版本，设备上 Defender for Endpoint 的硬件要求相同。

> [!NOTE]
> 不支持运行移动版本的 Windows (（如 Windows CE 和 Windows 10 移动) 的计算机。
>
> 如果运行 Windows 10 企业版 2016 LTSB 的虚拟机在非 Microsoft 虚拟化平台上运行，则可能会遇到性能问题。
>
> 对于虚拟环境，我们建议使用 Windows 10 企业版 LTSC 2019 或更高版本。


### <a name="other-supported-operating-systems"></a>其他支持的操作系统
- Android
- Linux
- macOS

> [!NOTE]
> 你需要了解与 Defender for Endpoint 兼容的 Android 和 macOS 的确切 Linux 分发和版本，集成工作。



### <a name="network-and-data-storage-and-configuration-requirements"></a>网络和数据存储以及配置要求
首次运行载入向导时，必须选择 Microsoft Defender 终结点相关信息的存储位置：欧盟、英国或美国数据中心。

> [!NOTE]
> - 首次设置后，无法更改数据存储位置。
> - 查看 [适用于终结点](data-storage-privacy.md) 的 Microsoft Defender 数据存储和隐私，详细了解 Microsoft 存储你的数据的位置和方法。


### <a name="diagnostic-data-settings"></a>诊断数据设置

> [!NOTE]
> Microsoft Defender for Endpoint 不需要任何特定的诊断级别，只要它已启用。

确保在你的组织的所有设备上启用了诊断数据服务。
默认情况下，此服务已启用。 最佳做法是检查以确保从它们获取传感器数据。

**使用命令行检查 Windows 10 诊断数据服务启动类型**：

1. 在设备上打开提升的命令行提示符：

   1.  转到“**开始**”并键入“**cmd**”。

   1.  右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

2. 输入以下命令，然后按 **Enter：**

   ```console
   sc qc diagtrack
   ```

   如果服务已启用，则结果应如以下屏幕截图所示：

   ![diagtrack 的 sc 查询命令的结果](images/windefatp-sc-qc-diagtrack.png)


如果服务未设置为 START_TYPE，则需要将服务设置为自动 **AUTO_START。** 


**使用命令行将 Windows 10 诊断数据服务设置为自动启动：**

1.  在终结点上打开提升的命令行提示符：

    1. 转到“**开始**”并键入“**cmd**”。

    1. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

2.  输入以下命令，然后按 **Enter：**

    ```console
    sc config diagtrack start=auto
    ```

3.  将显示成功消息。 通过输入以下命令验证更改，然后按 **Enter：**

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a>Internet 连接
可直接或通过代理在设备上建立 Internet 连接。

Defender for Endpoint 传感器可以利用每日平均带宽 5 MB 与 Defender for Endpoint 云服务进行通信并报告网络数据。 此每日平均带宽中不包含文件上载和调查包收集等一次活动。

有关其他代理配置设置的信息，请参阅配置 [设备代理和 Internet 连接设置](configure-proxy-internet.md)。

在载入设备之前，必须启用诊断数据服务。 该服务在 Windows 10 中默认启用。


## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Microsoft Defender 防病毒配置要求
Defender for Endpoint 代理依赖于 Microsoft Defender 防病毒扫描文件并提供有关文件的信息的能力。

在 Defender for Endpoint 设备上配置安全智能更新，无论 Microsoft Defender 防病毒是否是活动的反恶意软件。 有关详细信息，请参阅管理 [Microsoft Defender 防病毒更新和应用基线](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)。

当 Microsoft Defender 防病毒在你的组织中不是主动反恶意软件，并且你使用 Defender for Endpoint 服务时，Microsoft Defender 防病毒将进入被动模式。

如果你的组织已通过组策略或其他方法关闭 Microsoft Defender 防病毒，则必须从该组策略中排除已载入的设备。

如果你正在载入服务器，并且 Microsoft Defender 防病毒不是你的服务器上活动的反恶意软件，则需要将 Microsoft Defender 防病毒配置为进入被动模式或卸载。 配置取决于服务器版本。 有关详细信息，请参阅 [Microsoft Defender 防病毒兼容性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)。

> [!NOTE]
> 常规组策略不适用于防篡改保护，当启用防篡改保护时，将忽略对 Microsoft Defender 防病毒设置所做的更改。


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>已启用 Microsoft Defender 防病毒提前启动反恶意软件 (ELAM) 已启用
如果你正在设备上将 Microsoft Defender 防病毒作为主要的反恶意软件产品运行，则 Defender for Endpoint 代理将成功载入。

如果正在运行第三方反恶意软件客户端并使用移动设备管理解决方案或 Microsoft Endpoint Manager (current branch) ，则需要确保已启用 Microsoft Defender 防病毒 ELAM 驱动程序。 有关详细信息，请参阅 [确保策略](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)未禁用 Microsoft Defender 防病毒。


## <a name="related-topics"></a>相关主题
- [设置 Microsoft Defender for Endpoint 部署](production-deployment.md)
- [载入设备](onboard-configure.md)
