---
title: '如何使用 Intune 设备控制 USB 设备和其他可移动 (Windows 10) '
description: 你可以配置 Intune 设置以减少来自可移动存储（如 USB 设备）的威胁。
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: dansimp
author: dansimp
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 44d00bfd073b41f608a26106488e38c88d59bbecc4747c401fc70690bef1a110
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53903863"
---
# <a name="how-to-control-usb-devices-and-other-removable-media-using-microsoft-defender-for-endpoint"></a>如何使用 Microsoft Defender for Endpoint 控制 USB 设备和其他可移动媒体

**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)

Microsoft [建议使用分层](https://aka.ms/devicecontrolblog)方法来保护可移动媒体，并且 Microsoft Defender for Endpoint 提供了多个监视和控制功能，以帮助防止未经授权的外围设备中的威胁危害你的设备：

1. [在适用于终结点高级搜寻](#discover-plug-and-play-connected-events)的 Microsoft Defender 中发现外设的即插即用连接事件。 识别或调查可疑的使用活动。

2. 配置为仅允许或阻止某些可移动设备并防止威胁。
    1. [根据粒度配置允许](#allow-or-block-removable-devices) 或阻止可移动设备，以拒绝对可移动磁盘的写入访问，以及使用 USB 设备 ID 批准或拒绝设备。 根据单个或一组 Azure AD 用户和设备，灵活分配Azure Active Directory (Azure AD) 设置。

    2. [通过启用：防止](#prevent-threats-from-removable-storage) 由可移动存储设备引入的可移动存储的威胁：  
        - Microsoft Defender 防病毒 RTP (RTP) 扫描可移动存储中恶意软件。  
        - 攻击面减少 (ASR) USB 规则来阻止从 USB 运行的不受信任的和未签名的进程。  
        - Direct Memory Access (DMA) DMA 保护设置来缓解 DMA 攻击，包括适用于 Thunderbolt 的内核 DMA 保护和在用户登录之前阻止 DMA。  

3. [创建自定义警报和响应操作](#create-customized-alerts-and-response-actions) ，以基于这些即插即用事件或其他任何具有自定义检测规则的 Microsoft Defender 终结点事件监视可移动 [设备的使用情况](/microsoft-365/security/defender-endpoint/custom-detection-rules)。

4. [根据每个](#respond-to-threats) 外设报告的属性，实时响应来自外设的威胁。

> [!NOTE]
> 这些威胁减少措施有助于防止恶意软件进入你的环境。 若要防止企业数据离开环境，还可以配置数据丢失防护措施。 例如，在 Windows 10 设备上，你可以配置[BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview.md)和[Windows 信息](/windows/security/information-protection/create-wip-policy-using-intune-azure.md)保护，这将加密公司数据，即使数据存储在个人设备上，也可以使用[存储/RemovableDiskDenyWriteAccess CSP](/windows/client-management/mdm/policy-csp-storage#storage-removablediskdenywriteaccess)拒绝对可移动磁盘的写访问。 此外[，可以使用](/windows/security/threat-protection/windows-defender-atp/information-protection-in-windows-overview)Microsoft Defender for Endpoint 和 Azure (对 Windows 设备上的文件进行分类和保护) 包括已装载的 USB 设备。

## <a name="discover-plug-and-play-connected-events"></a>发现即插即用连接事件

可以在 Microsoft Defender for Endpoint 高级搜寻中查看即插即用连接事件，以识别可疑的使用活动或执行内部调查。
有关 Defender for Endpoint 高级搜寻查询的示例，请参阅适用于终结点的 Microsoft Defender 搜寻查询[GitHub存储库](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries)。

示例Power BI模板可用于可用于高级搜寻查询的 Microsoft Defender for Endpoint。 借助这些示例模板（包括用于设备控件的模板）可以将高级搜寻功能集成到Power BI。 有关详细信息[，GitHub PowerBI 模板的](https://github.com/microsoft/MDATP-PowerBI-Templates)存储库。 请参阅[使用自定义Power BI，](/microsoft-365/security/defender-endpoint/api-power-bi)详细了解Power BI集成。

## <a name="allow-or-block-removable-devices"></a>允许或阻止可移动设备
下表介绍了 Microsoft Defender for Endpoint 根据具体配置允许或阻止可移动设备的方式。

<br>

****

|控制|说明|
|---|---|
|[限制 USB 驱动器和其他外围设备](#restrict-usb-drives-and-other-peripherals)|你可以允许/阻止用户仅安装已授权/未授权设备或设备类型列表中包含的 USB 驱动器和其他外围设备。|
|[阻止安装和使用可移动存储](#block-installation-and-usage-of-removable-storage)|你无法安装或使用可移动存储。|
|[允许安装和使用专门批准的外围设备](#allow-installation-and-usage-of-specifically-approved-peripherals)|只能安装和使用报告其固件中的特定属性的已批准外围设备。|
|[阻止安装专门禁止的外围设备](#prevent-installation-of-specifically-prohibited-peripherals)|你无法安装或使用在固件中报告特定属性的禁止的外围设备。|
|[允许安装和使用具有匹配设备实例 ID 的专门批准的外围设备](#allow-installation-and-usage-of-specifically-approved-peripherals-with-matching-device-instance-ids)|只能安装和使用与这些设备实例任何一个匹配的已批准外围设备。|
|[使用匹配的设备实例 ID 阻止安装和使用专门禁止的外围设备](#prevent-installation-and-usage-of-specifically-prohibited-peripherals-with-matching-device-instance-ids)|你无法安装或使用与这些设备实例 ID 匹配的任何禁止的外围设备。|
|[限制使用服务蓝牙](#limit-services-that-use-bluetooth)|您可以限制可以使用此蓝牙。|
|[使用 Microsoft Defender for Endpoint 基线设置](#use-microsoft-defender-for-endpoint-baseline-settings)|可以使用 Defender for Endpoint 安全基线设置 ATP 的建议配置。|
|

### <a name="restrict-usb-drives-and-other-peripherals"></a>限制 USB 驱动器和其他外围设备

为了防止恶意软件感染或数据丢失，组织可能会限制 USB 驱动器和其他外围设备。 下表介绍了 Microsoft Defender for Endpoint 可帮助阻止安装和使用 USB 驱动器和其他外围设备的方法。

<br>

****

|控制|说明
|---|---|
|[允许安装和使用 USB 驱动器和其他外围设备](#allow-installation-and-usage-of-usb-drives-and-other-peripherals)|允许用户仅安装已授权设备或设备类型列表中包含的 USB 驱动器和其他外围设备|
|[阻止安装和使用 USB 驱动器和其他外围设备](#prevent-installation-and-usage-of-usb-drives-and-other-peripherals)|阻止用户安装未经授权的设备和设备类型列表中包含的 USB 驱动器和其他外围设备|
|

上述所有控件都可以通过 Intune 管理 [模板进行设置](/intune/administrative-templates-windows)。 相关策略位于 Intune 管理员模板中：

![管理模板列表的屏幕截图](images/admintemplates.png)

> [!NOTE]
> 使用 Intune，你可以将设备配置策略应用于 Azure AD 用户和/或设备组。
还可通过设备安装 CSP 设置和设备安装 [GPO](/windows/client-management/mdm/policy-csp-deviceinstallation) [设置上述策略](/previous-versions/dotnet/articles/bb530324(v=msdn.10))。
>
> 在生产中应用这些设置之前，请始终先使用一组试点用户和设备测试和优化这些设置。
有关控制 USB 设备的信息，请参阅 [Microsoft Defender for Endpoint 博客](https://www.microsoft.com/security/blog/2018/12/19/windows-defender-atp-has-protections-for-usb-and-removable-devices/)。

#### <a name="allow-installation-and-usage-of-usb-drives-and-other-peripherals"></a>允许安装和使用 USB 驱动器和其他外围设备

允许安装和使用 USB 驱动器和其他外围设备的一个方法是首先允许一切。 之后，你可以开始减少允许的 USB 驱动程序和其他外围设备。

> [!NOTE]
> 由于未经授权的 USB 外围设备的固件可能会欺骗其 USB 属性，因此我们建议仅允许专门批准的 USB 外围设备并限制可以访问它们的用户。

1. Enable **Prevent installation of devices not described by other policy settings** to all users.
2. 启用 **允许使用匹配所有设备** 设置类的这些设备设置类的 [驱动程序安装设备](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)。

若要对已安装的设备强制执行策略，请应用具有此设置的阻止策略。

配置允许设备安装策略时，还必须允许所有父属性。 可以通过打开设备管理器来查看设备的父项，并按连接查看。

![按连接显示的设备](images/devicesbyconnection.png)

在此例中，需要添加以下类：HID、Keyboard 和 {36fc9e60-c465-11cf-8056-444553540000}。 有关详细信息 [，请参阅 Microsoft 提供的 USB](/windows-hardware/drivers/usbcon/supported-usb-classes) 驱动程序。

![设备主机控制器](images/devicehostcontroller.jpg)

如果要限制某些设备，请删除要限制的外围设备的设备设置类。 然后添加要添加的设备 ID。 设备 ID 基于设备的供应商 ID 和产品 ID 值。 有关设备 ID 格式的信息，请参阅标准 [USB 标识符](/windows-hardware/drivers/install/standard-usb-identifiers)。 

若要查找设备 ID，请参阅查找[设备 ID。](#look-up-device-id) 

例如：

1. 从允许使用与这些设备设置匹配的驱动程序安装 **设备中删除类** USBDevice。
2. 在"允许安装与这些设备 ID 匹配的任何设备"中添加 **要允许的设备 ID。** 

#### <a name="prevent-installation-and-usage-of-usb-drives-and-other-peripherals"></a>阻止安装和使用 USB 驱动器和其他外围设备

如果你想要阻止安装设备类或某些设备，可以使用阻止设备安装策略：

1. 启用 **"阻止安装与这些设备的任何 ID** 匹配的设备"，并将其添加到列表中。
2. 启用 **使用与这些设备设置类匹配的驱动程序阻止安装设备**。

> [!NOTE]
> 阻止设备安装策略优先于允许设备安装策略。

通过 **阻止安装与这些设备任何一个匹配的设备策略**，你可以指定阻止安装Windows设备列表。

若要阻止安装与这些设备的任何 ID 匹配的设备： 

1. [查找要](#look-up-device-id)阻止安装Windows的设备 ID。

   ![查找供应商或产品 ID](images/lookup-vendor-product-id.png)

2. 启用 **"阻止安装与这些设备的任何 ID** 匹配的设备"，并添加供应商或产品 ID 到列表中。

    ![添加供应商 ID 以阻止列表](images/add-vendor-id-to-prevent-list.png)

#### <a name="look-up-device-id"></a>查找设备 ID

可以使用设备管理器查找设备 ID。

1. 打开设备管理器。
2. 单击 **"查看**"，**然后按连接选择"设备"。**
3. 从树中，右键单击设备并选择"属性 **"。**
4. 在所选设备的对话框中，单击"详细信息 **"** 选项卡。
5. 单击"**属性**"下拉列表，然后选择"**硬件 ID"。**
6. 右键单击顶部 ID 值， **然后选择复制**。

有关设备 ID 格式的信息，请参阅标准 [USB 标识符](/windows-hardware/drivers/install/standard-usb-identifiers)。

有关供应商 ID 的信息，请参阅 [USB 成员](https://www.usb.org/members)。

下面是使用 PowerShell 查找设备供应商 ID 或产品 ID (，这是设备 ID) 的一部分： 

```powershell
Get-WMIObject -Class Win32_DiskDrive | Select-Object -Property * 
```

使用 **与这些设备设置** 类匹配的驱动程序阻止安装设备策略允许你指定阻止Windows安装类。

若要阻止安装特定设备类：

1. 从供应商可用的系统定义的设备设置类中查找 [设备设置类的](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)GUID。

2. 启用 **"阻止使用与这些设备** 设置类匹配的驱动程序安装设备"，然后向列表中添加类 GUID。

    > [!div class="mx-imgBorder"]
    > ![添加设备设置类以阻止列表](images/Add-device-setup-class-to-prevent-list.png)

### <a name="block-installation-and-usage-of-removable-storage"></a>阻止安装和使用可移动存储

1. 登录到管理[Microsoft Endpoint Manager中心](https://endpoint.microsoft.com/)。

2. 单击 **"设备**  >  **配置文件**  >  **""创建配置文件"。**

    > [!div class="mx-imgBorder"]
    > ![创建设备配置文件](images/create-device-configuration-profile.png)

3. 使用以下设置：
   - 名称：键入配置文件的名称
   - 说明：键入说明
   - 平台：Windows 10及更高版本
   - 配置文件类型：设备限制

   > [!div class="mx-imgBorder"]
   > ![创建配置文件](images/create-profile.png)

4. 单击"**配置**  >  **常规"。**  

5. 对于 **"仅移动版** (可移动存储和 **USB) ，请选择"** 阻止 **"。** **可移动存储** 包括 USB 驱动器， (移动连接) USB 充电，但仅包括移动设备上的其他 USB 连接。  

   ![常规设置](images/general-settings.png)

6. 单击 **确定** 关闭 **常规** 设置 **和设备限制**。

7. 单击 **"创建** "保存配置文件。

### <a name="allow-installation-and-usage-of-specifically-approved-peripherals"></a>允许安装和使用专门批准的外围设备

允许安装的外围设备可通过其硬件标识 [进行指定](/windows-hardware/drivers/install/device-identification-strings)。 有关常见标识符结构的列表，请参阅 [设备标识符格式](/windows-hardware/drivers/install/device-identifier-formats)。 在部署配置之前测试它，以确保它阻止并允许预期的设备。 理想情况下，测试硬件的各种实例。 例如，测试多个 U 盘，而不是只测试一个 U 盘。

有关允许安装特定设备 ID 的 SyncML 示例，请参阅[DeviceInstallation/AllowInstallationOfMatchingDeviceIDs CSP。](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdeviceids) 若要允许特定设备类，请参阅[DeviceInstallation/AllowInstallationOfMatchingDeviceSetupClasses CSP。](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdevicesetupclasses)
允许安装特定设备还需要启用 [DeviceInstallation/PreventInstallationOfDevicesNotDescribedByOtherPolicySettings](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofdevicesnotdescribedbyotherpolicysettings)。

### <a name="prevent-installation-of-specifically-prohibited-peripherals"></a>阻止安装专门禁止的外围设备

Microsoft Defender for Endpoint 使用以下任一选项阻止安装和使用禁止的外围设备：

- [管理模板](/intune/administrative-templates-windows) 可以阻止具有匹配硬件 ID 或安装类的任何设备。  
- [Intune 中具有](/windows/client-management/mdm/policy-csp-deviceinstallation) 自定义配置文件的设备安装 CSP 设置。 你可以[阻止安装特定设备 ID 或](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceids)[阻止特定设备类](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdevicesetupclasses)。

### <a name="allow-installation-and-usage-of-specifically-approved-peripherals-with-matching-device-instance-ids"></a>允许安装和使用具有匹配设备实例 ID 的专门批准的外围设备

允许安装的外围设备可通过其设备实例 [ID 指定](/windows-hardware/drivers/install/device-instance-ids)。 在推出配置之前测试该配置，以确保它支持预期的设备。 理想情况下，测试硬件的各种实例。 例如，测试多个 U 盘，而不是只测试一个 U 盘。

通过 [配置 DeviceInstallation/AllowInstallationOfMatchingDeviceInstanceIDs](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdeviceinstanceids) 策略设置，可以允许安装和使用具有匹配设备实例 ID 的已批准外围设备。

### <a name="prevent-installation-and-usage-of-specifically-prohibited-peripherals-with-matching-device-instance-ids"></a>使用匹配的设备实例 ID 阻止安装和使用专门禁止的外围设备

禁止安装的外围设备可通过其设备实例 [ID 指定](/windows-hardware/drivers/install/device-instance-ids)。 在推出配置之前测试该配置，以确保它支持预期的设备。 理想情况下，测试硬件的各种实例。 例如，测试多个 U 盘，而不是只测试一个 U 盘。

通过配置 [DeviceInstallation/PreventInstallationOfMatchingDeviceInstanceIDs](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceinstanceids) 策略设置，可以阻止使用匹配的设备实例 ID 安装禁止的外围设备。

### <a name="limit-services-that-use-bluetooth"></a>限制使用服务蓝牙

使用 Intune，你可以限制可通过"蓝牙服务"使用蓝牙[服务](/windows/client-management/mdm/policy-csp-bluetooth#servicesallowedlist-usage-guide)。 默认状态"蓝牙允许的服务"设置意味着允许一切。  一旦添加服务，即成为允许列表。 如果客户添加了 Keyboards 和鼠标值，但未添加文件传输 GUID，应阻止文件传输。

> [!div class="mx-imgBorder"]
> !["设置蓝牙屏幕截图](images/bluetooth.png)

### <a name="use-microsoft-defender-for-endpoint-baseline-settings"></a>使用 Microsoft Defender for Endpoint 基线设置

Microsoft Defender for Endpoint 基线设置表示威胁防护的建议配置。 基线的配置设置位于配置设置的编辑配置文件页中。

> [!div class="mx-imgBorder"]
> ![MEM 中的基线](images/baselines.png)

## <a name="prevent-threats-from-removable-storage"></a>防止来自可移动存储的威胁
  
可移动存储设备可能会给组织带来额外的安全风险。 Microsoft Defender for Endpoint 可帮助识别和阻止可移动存储设备上的恶意文件。

Microsoft Defender for Endpoint 还可以阻止在设备上使用 USB 外围设备，以帮助防止外部威胁。 它通过使用 USB 外围设备报告的属性来确定是否可以在设备上安装和使用它们来这样做。

请注意，如果你使用设备安装策略阻止 USB 设备或任何其他设备类，连接的设备（如手机）仍可以收费。

> [!NOTE]
> 在广泛分发到组织之前，请始终首先使用一组试点用户和设备测试和优化这些设置。 

下表介绍了 Microsoft Defender for Endpoint 可帮助防止来自可移动存储的威胁的方法。

有关控制 USB 设备的信息，请参阅 [Microsoft Defender for Endpoint 博客](https://aka.ms/devicecontrolblog)。

<br>

****

|控制|说明|
|---|---|
|[启用Microsoft Defender 防病毒扫描](#enable-microsoft-defender-antivirus-scanning)|启用Microsoft Defender 防病毒扫描进行实时保护或计划扫描。|
|[在 USB 外围设备上阻止不受信任的和未签名的进程](#block-untrusted-and-unsigned-processes-on-usb-peripherals)|阻止未签名或不受信任的 USB 文件。|
|[防止直接内存访问 (DMA) 攻击](#protect-against-direct-memory-access-dma-attacks)|配置设置以抵御 DMA 攻击。|
|

> [!NOTE]
> 由于未经授权的 USB 外围设备的固件可能会欺骗其 USB 属性，因此我们建议仅允许专门批准的 USB 外围设备并限制可以访问它们的用户。

### <a name="enable-microsoft-defender-antivirus-scanning"></a>启用Microsoft Defender 防病毒扫描

使用安全机制保护Microsoft Defender 防病毒可移动[存储需要启用](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus)实时保护或计划扫描，并配置可移动驱动器进行扫描。

- 如果启用了实时保护，则先扫描文件，然后再访问和执行这些文件。 扫描范围包括所有文件，包括已装载的可移动设备（如 USB 驱动器）上的文件。 可以选择运行[PowerShell](/samples/browse/?redirectedfrom=TechNet-Gallery)脚本，在安装 U 盘后执行自定义扫描，以便 Microsoft Defender 防病毒 在连接可移动设备后开始扫描可移动设备上的所有文件。 但是，我们建议启用实时保护以提高扫描性能，特别是对于大型存储设备。

- 如果使用计划扫描，则需要禁用默认启用 (DisableRemovableDriveScanning 设置) 以在完全扫描期间扫描可移动设备。 无论 DisableRemovableDriveScanning 设置如何，均可在快速或自定义扫描过程中扫描可移动设备。

> [!NOTE]
> 我们建议为扫描启用实时监视。 在 Intune 中，你可以为设备限制配置Windows 10实时监视中的Microsoft Defender 防病毒  >    >    >  **实时监视**。

<!-- Need to build out point in the preceding note. 
-->

### <a name="block-untrusted-and-unsigned-processes-on-usb-peripherals"></a>在 USB 外围设备上阻止不受信任的和未签名的进程

最终用户可能会插入感染恶意软件的可移动设备。
为了防止感染，公司可以阻止未签名或不受信任的 USB 文件。
或者，公司可以利用攻击面减少规则的审核功能[](/microsoft-365/security/defender-endpoint/attack-surface-reduction)来监视在 USB 外围设备上执行的不受信任的和未签名进程的活动。
这可以通过将从 USB 运行的 **不受信任的** 和未签名的进程分别 **设置为"仅** 阻止"或" **仅审核**"来完成。
通过此规则，管理员可以阻止或审核未签名或不受信任的可执行文件从 USB 可移动驱动器（包括 SD 卡）运行。
受影响的文件类型包括可执行文件 (（如 .exe、.dll 或 .scr) ）和脚本文件（如 PowerShell (.ps) 、VisualBasic (.vbs) 或 JavaScript (.js) 文件）。

这些设置需要 [启用实时保护](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus)。

1. 登录到[Microsoft Endpoint Manager。](https://endpoint.microsoft.com/)

2. 单击 **"设备**  >  **Windows**  >  **配置策略**  >  **""创建配置文件"。** 

    ![创建设备配置文件](images/create-device-configuration-profile.png)

3. 使用以下设置：
   - 平台：Windows 10及更高版本 
   - 配置文件类型：设备限制

   > [!div class="mx-imgBorder"]
   > ![创建终结点保护配置文件](images/create-endpoint-protection-profile.png)

4. 单击“**创建**”。  

5. 对于 **从 USB 运行的未** 签名和不受信任进程，选择"阻止 **"。**

   ![阻止不受信任的进程](images/block-untrusted-processes.png)

6. 单击 **"** 确定"关闭设置 **和设备限制**。

### <a name="protect-against-direct-memory-access-dma-attacks"></a>防止直接内存访问 (DMA) 攻击

DMA 攻击可能会导致泄露驻留在电脑上的敏感信息，甚至导致恶意软件注入，攻击者可以绕过锁屏界面或远程控制电脑。 以下设置有助于防止 DMA 攻击：

1. 从 Windows 10版本 1803 开始，Microsoft 引入了[适用于 Thunderbolt 的内核 DMA](/windows/security/information-protection/kernel-dma-protection-for-thunderbolt.md)保护，以提供通过 Thunderbolt 端口抵御 DMA 攻击的本机保护。 适用于 Thunderbolt 的内核 DMA 保护由系统制造商启用，用户无法打开或关闭。

   从 Windows 10版本 1809 开始，可以通过配置 DMA Guard CSP 来调整内核[DMA 保护级别](/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy)。 这是对不支持设备内存隔离的外围设备的额外 (也称为 DMA 重新映射) 。 内存隔离允许操作系统利用设备的 I/O 内存管理单元 (IOMMU) 来阻止外围设备内存沙盒 (不允许的 I/O 或内存) 。 换句话说，操作系统向外设分配特定内存范围。 如果外设尝试读取/写入指定范围之外的内存，操作系统将阻止它。

   支持设备内存隔离的外围设备始终可以连接。 只有在用户登录后才能阻止、允许或允许的外围设备 (默认) 。

2. 在Windows 10内核 DMA 保护的系统上，你可以：

   - [阻止 DMA，直到用户登录](/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)
   - [通过 Thunderbolt 端口连接阻止所有 (包括 USB 设备) ](https://support.microsoft.com/help/2516445/blocking-the-sbp-2-driver-and-thunderbolt-controllers-to-reduce-1394-d)

## <a name="create-customized-alerts-and-response-actions"></a>创建自定义警报和响应操作

可以使用 WDATP 连接器和自定义检测规则创建自定义警报和响应操作：

**Wdatp 连接器响应操作：**

**调查：** 启动调查、收集调查包并隔离计算机。

**USB** 设备上的威胁扫描。

**限制计算机上除** 预定义集之外的所有应用程序的执行

MDATP 连接器是 200 多个预定义连接器之一，包括 Outlook、Teams、Slack 等。可以构建自定义连接器。

- [有关 WDATP 连接器响应操作的信息](/connectors/wdatp/)

**自定义检测规则响应操作：**

可以同时应用计算机和文件级别操作。

- [有关自定义检测规则响应操作的信息](/microsoft-365/security/defender-endpoint/custom-detection-rules)

有关与设备控制相关的高级搜寻事件和如何创建自定义警报的示例的信息，请参阅高级搜寻更新：USB 事件、计算机级操作和 [架构更改](https://techcommunity.microsoft.com/t5/Microsoft-Defender-ATP/Advanced-hunting-updates-USB-events-machine-level-actions-and/ba-p/824152)。

## <a name="respond-to-threats"></a>响应威胁

可以使用 Microsoft Defender 终结点自定义检测规则创建自定义警报和 [自动响应操作](/microsoft-365/security/defender-endpoint/custom-detection-rules)。 自定义检测中的响应操作涵盖计算机和文件级别操作。 您还可以使用[PowerApps](https://powerapps.microsoft.com/)创建警报和自动响应操作[，Flow](https://flow.microsoft.com/) Microsoft Defender for [Endpoint 连接器。](/connectors/wdatp/) 连接器支持调查、威胁扫描和限制正在运行的应用程序的操作。 它是 200 多个预定义连接器之一，包括 Outlook、Teams、Slack 等。 还可以构建自定义连接器。 请参阅 [连接器](/connectors/) ，详细了解连接器。

例如，使用任一方法，你都可以在将 USB Microsoft Defender 防病毒装载到计算机上时自动运行该 U 盘。

## <a name="related-topics"></a>相关主题

- [配置实时保护Microsoft Defender 防病毒](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus)
- [Defender/AllowFullScanRemovableDriveScanning](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning)
- [策略/DeviceInstallation CSP](/windows/client-management/mdm/policy-csp-deviceinstallation)
- [对可移动设备执行自定义扫描](/samples/browse/?redirectedfrom=TechNet-Gallery)
- [用于自定义报告的设备控制 PowerBI 模板](https://github.com/microsoft/MDATP-PowerBI-Templates)
- [BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview.md) 
- [Windows 信息保护](/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure.md)
