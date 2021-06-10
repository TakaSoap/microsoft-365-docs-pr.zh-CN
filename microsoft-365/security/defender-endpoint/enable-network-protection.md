---
title: 启用网络保护功能
description: 使用组策略、PowerShell 或移动设备管理和配置管理器启用网络保护。
keywords: 网络保护， 攻击， 恶意网站， ip， 域， 启用， 打开
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b62659360e990467524ec632968dfea313d0b164
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861667"
---
# <a name="turn-on-network-protection"></a>启用网络保护功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[网络](network-protection.md) 保护有助于防止员工使用任何应用程序访问可能承载网络钓鱼欺诈、攻击和 Internet 上的其他恶意内容危险域。 可以在 [测试环境中](evaluate-network-protection.md) 审核网络保护，以查看在启用应用之前将阻止哪些应用。

[了解有关网络筛选配置选项的详细信息](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>检查网络保护是否已启用

使用注册表编辑器检查是否在本地设备上启用了网络保护。

1. 选择 **任务栏中的** "开始"按钮并键入 **regedit** 以打开注册表编辑器

2. 从 **HKEY_LOCAL_MACHINE** 菜单中选择"选项"

3. 在嵌套菜单中导航到 **SOFTWARE**  >  **Microsoft**  >  **Windows Defender Windows Defender** Exploit  >  **Guard**  >  **网络保护**

4. 选择 **EnableNetworkProtection** 以查看设备上网络保护的当前状态

    * 0 或 **Off**
    * 1 或 **On**
    * 2 或 **审核** 模式
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a>启用网络保护

使用以下任一方法启用网络保护：

* [PowerShell](#powershell)
* [移动设备管理 (MDM) ](#mobile-device-management-mdm)
* [Microsoft Endpoint Manager /Intune](#microsoft-endpoint-manager-formerly-intune)
* [组策略](#group-policy)

### <a name="powershell"></a>PowerShell

1. 在 **"开始"菜单中键入 powershell，** 右 **键单击**"Windows PowerShell并选择"以 **管理员角色运行"**
2. 输入以下 cmdlet：

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. 可选：使用下列 cmdlet 在审核模式下启用该功能：

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    使用 `Disabled` 而不是 `AuditMode` 或 `Enabled` 来关闭该功能。

### <a name="mobile-device-management-mdm"></a>移动设备管理(MDM)

使用 [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) 配置服务提供程序 (CSP) 启用或禁用网络保护或启用审核模式。

### <a name="microsoft-endpoint-manager-formerly-intune"></a>Microsoft Endpoint Manager (以前为 Intune) 

1. 登录到管理Microsoft Endpoint Manager中心 (https://endpoint.microsoft.com)

2. 创建或编辑 [终结点保护配置文件](/mem/intune/protect/endpoint-protection-configure)

3. 在 **配置文件设置** 配置策略"下，转到"Microsoft Defender 攻击防护  >  **网络** 筛选  >  **""** 仅启用或  >  审核 **"**

### <a name="group-policy"></a>组策略

使用以下过程在加入域的计算机或独立计算机上启用网络保护。

1. 在独立计算机上，**转到"开始**"，然后键入并选择"**编辑组策略"。**

    *-Or-*

    在加入域的组策略管理计算机上，打开组策略 [](https://technet.microsoft.com/library/cc731212.aspx)管理控制台，右键单击要配置的组策略对象，**然后选择编辑**。

2. 在 **策略管理编辑器** 中， **计算机配置** 并选择 **管理模板**。

3. 展开树以 **Windows Exploit** Guard  >  **网络Microsoft Defender 防病毒Windows Defender**  >    >  **的组件**。

> [!NOTE]
> 在早期版本的 Windows 中，组策略路径可能Windows Defender 防病毒"而不是"Microsoft Defender 防病毒"。

4. 双击阻止用户和应用 **访问** 危险网站设置，将选项设置为 **已启用**。 在选项部分中，必须指定以下选项之一：
    * **阻止** - 用户无法访问恶意 IP 地址和域
    * **禁用 (默认)** - 网络保护功能不起作用。 不会阻止用户访问恶意域
    * **审核模式**- 如果用户访问恶意 IP 地址或域，事件将记录在Windows日志中。 但是，不会阻止用户访问地址。

> [!IMPORTANT]
> 若要完全启用网络保护，必须将组策略选项设置为 **已启用**，还要在选项下拉菜单中选择阻止。

使用注册表编辑器确认在本地计算机上启用网络保护：

1. 选择 **"开始** " **并键入 regedit** 以 **打开注册表编辑器**。

2. 导航到 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection\EnableNetworkProtection**

3. 选择 **EnableNetworkProtection** 并确认值：
   * 0=Off
   * 1=打开
   * 2=审核

## <a name="see-also"></a>另请参阅

* [网络保护](network-protection.md)
* [网络保护功能评估](evaluate-network-protection.md)
* [网络保护疑难解答](troubleshoot-np.md)
