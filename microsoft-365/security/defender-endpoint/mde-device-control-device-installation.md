---
title: Microsoft Defender for Endpoint 设备控制设备安装
description: 本主题提供有关适用于终结点设备控制设备安装的 Microsoft Defender 的演练
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5f0828d24ddb4c02d533d0fced2389ca3cb61ce4
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167066"
---
# <a name="microsoft-defender-for-endpoint-device-control-device-installation"></a>Microsoft Defender for Endpoint 设备控制设备安装 

**适用对象**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint 设备控制可移动存储访问控制使你能够执行以下任务：

- 阻止用户安装特定设备。
- 允许用户安装特定设备，但阻止其他设备。

> [!NOTE]
> 若要查找设备安装和可移动存储访问控制的区别，请参阅 Microsoft Defender [for Endpoint Device Control Removable 存储 Protection](/microsoft-365/security/defender-endpoint/device-control-removable-storage-protection?view=o365-worldwide&preserve-view=true)。

|Privilege|权限|
|---|---|
|Access|设备安装 |
|操作模式|允许、阻止 |
|云解决方案提供商支持|是|
|GPO 支持|是|
|基于用户的支持|否|
|基于计算机的支持|是|

## <a name="prepare-your-endpoints"></a>准备终结点

在 Windows 10 Server 2022 Windows 11设备上部署Windows安装。

## <a name="device-properties"></a>设备属性

设备安装支持支持以下设备属性：

- 设备 ID 
- 硬件 ID 
- 兼容 ID 
- 设备类 
- "可移动设备"设备类型：某些设备可分类为可移动设备。 如果设备所连接的设备的驱动程序指示设备是可移动的，则认为该设备是可移动的。 例如，USB 设备被设备连接到的 USB 集线器的驱动程序报告为可移动。 有关详细信息，请参阅设备[安装Windows。](/windows/client-management/manage-device-installation-with-group-policy)

## <a name="policies"></a>策略

### <a name="allow-installation-of-devices-that-match-any-of-these-device-ids"></a>允许安装与这些设备任何一个匹配的设备

此策略设置允许你为允许安装的设备指定即插即用硬件WINDOWS兼容 ID 的列表。 此策略设置仅在启用"跨所有设备匹配条件应用设备安装策略的分层评估顺序"策略设置时使用。

当启用此策略设置以及"跨所有设备匹配条件允许和阻止设备安装策略的分层评估顺序"策略设置时，Windows 将允许安装或更新其即插即用硬件 ID 或兼容 ID 显示在你创建列表中的任何设备，除非层次结构中相同或更高层的另一个策略设置专门阻止该安装， 如以下策略设置：

- 阻止安装与这些设备的 ID 匹配的设备。
- 阻止安装与这些设备实例任何一个匹配的设备。

如果未通过此 **策略设置** 启用"跨所有设备匹配条件允许和阻止设备安装策略"的"应用分层评估顺序"策略设置，则专门阻止安装的其他策略设置将优先。 

> [!NOTE]
> 对于受支持的目标 Windows 10 版本和 Windows 11，"阻止由其他策略设置描述的设备安装"策略设置已替换为"跨所有设备匹配条件允许和阻止设备安装策略"的"应用分层评估顺序"Windows 11。 建议尽可能在所有设备匹配 **条件** 策略设置中对"允许"和"阻止设备安装策略"使用应用分层评估顺序。

### <a name="allow-installation-of-devices-that-match-any-of-these-device-instance-ids"></a>允许安装与这些设备实例任何一个匹配的设备 

此策略设置允许你为允许安装即插即用Windows设备实例 ID 列表。 此策略设置仅在启用"跨所有设备匹配条件应用设备安装策略的分层评估顺序"策略设置时使用。 

当此策略设置与"跨所有设备匹配条件允许和阻止设备安装策略应用分层评估顺序"策略设置一起启用时，Windows 将允许安装或更新其即插即用设备实例 ID 显示在你创建的列表中的任何设备，除非层次结构中相同或更高层的另一个策略设置专门阻止该安装， 如以下策略设置：

- 阻止安装与这些设备实例 ID 匹配的设备 

如果未通过此 **策略设置** 启用"跨所有设备匹配条件允许和阻止设备安装策略"的"应用分层评估顺序"策略设置，则专门阻止安装的其他策略设置将优先。 

### <a name="allow-installation-of-devices-using-drivers-that-match-these-device-setup-classes"></a>允许使用与这些设备设置类匹配的驱动程序安装设备 

此策略设置允许你为允许安装的驱动程序包 (GUID) 设备设置类全局唯一标识符Windows列表。 此策略设置仅在启用"跨所有设备匹配条件应用设备安装策略的分层评估顺序"策略设置时使用。

当此策略设置与"跨所有设备匹配条件允许和阻止设备安装策略应用分层评估顺序"策略设置一起启用时，Windows 将允许安装或更新其设备设置类 GUID 显示在你创建的列表中的驱动程序包，除非层次结构中相同或更高层的另一个策略设置专门阻止该安装， 如以下策略设置： 

- 阻止为这些设备类安装设备 
- 阻止安装与这些设备 ID 匹配的设备 
- 阻止安装与这些设备实例 ID 匹配的设备 

如果未通过此 **策略设置** 启用"跨所有设备匹配条件允许和阻止设备安装策略"的"应用分层评估顺序"策略设置，则专门阻止安装的其他策略设置将优先。

### <a name="apply-layered-order-of-evaluation-for-allow-and-prevent-device-installation-policies-across-all-device-match-criteria"></a>跨所有设备匹配条件应用允许和阻止设备安装策略的分层评估顺序 

当多个安装策略设置适用于给定设备时，此策略设置将更改应用允许和阻止策略设置的评估顺序。 启用此策略设置，以确保基于已建立的层次结构应用重叠设备匹配条件，其中更具体的匹配条件将取代不太具体的匹配条件。 指定设备匹配条件的策略设置的评估层次结构顺序如下：

**设备实例>设备>设备设置类>可移动设备**

#### <a name="device-instance-ids"></a>设备实例 ID 

1. 阻止使用与这些设备实例 ID 匹配的驱动程序安装设备。
2. 允许使用与这些设备实例 ID 匹配的驱动程序安装设备。

#### <a name="device-ids"></a>设备 ID 

1. 阻止使用与这些设备 ID 匹配的驱动程序安装设备。
2. 允许使用与这些设备 ID 匹配的驱动程序安装设备。

#### <a name="device-setup-class"></a>设备设置类 

1. 阻止使用与这些设备设置类匹配的驱动程序安装设备。
2. 允许使用与这些设备设置类匹配的驱动程序安装设备。

#### <a name="removable-devices"></a>可移动设备 

阻止安装可移动设备 

> [!NOTE]
> 此策略设置提供比"阻止 **安装其他** 策略设置策略未描述的设备"策略设置更精细的控制。 如果同时启用这些冲突的策略设置，将启用"跨所有设备匹配条件应用允许和阻止设备安装策略的分层评估顺序"策略设置，并且将忽略其他策略设置。 

### <a name="prevent-installation-of-devices-that-match-any-of-these-device-ids"></a>阻止安装与这些设备的任何 ID 匹配的设备 

此策略设置允许你为阻止安装的设备指定即插即用硬件WINDOWS兼容 ID 的列表。 默认情况下，此策略设置优先于任何其他允许Windows安装设备的策略设置。

> [!NOTE]
> 若要为适用设备启用"允许安装与这些设备实例 **IDs** 匹配的设备"策略设置以取代此策略设置，请启用"允许和阻止跨所有设备匹配条件的设备安装策略"策略设置的"应用分层评估顺序"。 

如果启用此策略设置，Windows将阻止安装其硬件 ID 或兼容 ID 显示在你创建的列表中的设备。 如果在远程桌面服务器上启用此策略设置，则策略设置将影响指定设备从远程桌面客户端重定向到远程桌面服务器。

如果禁用或不配置此策略设置，则其他策略设置可以允许或阻止设备进行安装和更新。 

### <a name="prevent-installation-of-devices-that-match-any-of-these-device-instance-ids"></a>阻止安装与这些设备实例 ID 匹配的设备 

此策略设置允许你为阻止其安装的设备指定Windows即插即用设备实例 ID 的列表。 此策略设置优先于任何其他允许Windows安装设备的策略设置。 

如果启用此策略设置，Windows将阻止安装设备实例 ID 显示在你创建的列表中的设备。 如果在远程桌面服务器上启用此策略设置，则策略设置将影响指定设备从远程桌面客户端重定向到远程桌面服务器。 

如果禁用或不配置此策略设置，则其他策略设置可以允许或阻止设备进行安装和更新。 

### <a name="prevent-installation-of-devices-using-drivers-that-match-these-device-setup-classes"></a>阻止使用与这些设备设置类匹配的驱动程序安装设备 

此策略设置允许你为阻止安装 (的驱动程序包) 设备设置类全局唯一标识符Windows GUID 列表。 默认情况下，此策略设置优先于任何其他允许Windows安装设备的策略设置。

> [!NOTE]
> 若要为适用设备启用"允许安装与这些设备的任何设备 **ID** 匹配的设备"和"允许安装与这些设备实例 **IDs** 匹配的设备"策略设置来取代此策略设置，请启用"允许"和"阻止跨所有设备匹配条件的设备安装策略"评估的分层评估顺序策略设置。

如果启用此策略设置，Windows安装或更新其设备设置类 GUID 显示在你创建的列表中的驱动程序包。 如果在远程桌面服务器上启用此策略设置，则策略设置将影响指定设备从远程桌面客户端重定向到远程桌面服务器。 

如果禁用或不配置此策略设置，Windows策略设置允许或阻止的设备安装和更新。 

### <a name="prevent-installation-of-removable-devices"></a>阻止安装可移动设备 

此策略设置允许你阻止Windows移动设备。 如果设备所连接的设备的驱动程序指示设备是可移动的，则认为该设备是可移动的。 例如，通用串行总线 (USB) 设备被设备连接到的 USB 集线器的驱动程序报告为可移动。 默认情况下，此策略设置优先于任何其他允许Windows安装设备的策略设置。 

> [!NOTE]
> 若要启用"允许使用与这些设备设置类匹配的驱动程序安装设备"、"允许安装与这些设备的任何 **ID** 匹配的设备"和"允许安装与这些设备实例 **IDs** 策略设置匹配的设备"策略设置来取代适用于适用设备的此策略设置，请启用"允许"和"阻止跨所有设备匹配条件的设备安装策略"策略设置的"应用分层评估顺序"。

如果启用此策略设置，Windows无法安装可移动设备，并且现有可移动设备无法更新其驱动程序。 如果在远程桌面服务器上启用此策略设置，该策略设置将影响从远程桌面客户端到远程桌面服务器的可移动设备的重定向。

如果禁用或不配置此策略设置，Windows其他策略设置允许或阻止的设备安装和更新可移动设备的驱动程序包。

## <a name="common-removable-storage-access-control-scenarios"></a>常见的可移动存储访问控制方案

为了帮助你熟悉 Microsoft Defender for Endpoint Removable 存储访问控制，我们将一些常见方案放在一起供你遵循。

### <a name="scenario-1-prevent-installation-of-all-usb-devices-while-allowing-an-installation-of-only-an-authorized-usb-thumb-drive"></a>方案 1：阻止安装所有 USB 设备，同时仅允许安装授权的 USB U 盘 

对于此方案，将采用以下策略：

- 阻止使用与这些设备设置类匹配的驱动程序安装设备。
- 跨所有设备匹配条件应用允许和阻止设备安装策略的分层评估顺序。
- 允许安装与这些设备实例任何一个匹配的设备，或允许安装与这些设备任何 ID 匹配的设备。

#### <a name="deploying-and-managing-policy-via-intune"></a>通过 Intune 部署和管理策略 

设备安装功能允许你通过 Intune 将策略应用到设备。

#### <a name="licensing"></a>授权 

在开始使用设备安装之前，你应该确认你的Microsoft 365 [订阅](https://www.microsoft.com/en-in/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。 若要访问和使用设备安装，你必须拥有Microsoft 365 E3。

#### <a name="permission"></a>权限 

对于 Intune 中的策略部署，该帐户必须具有创建、编辑、更新或删除设备配置文件的权限。 可以创建自定义角色或使用具有以下权限的任何内置角色：  

- 策略和配置文件管理器角色
- 或为设备配置文件启用创建/编辑/更新/读取/删除/查看报告权限的自定义角色
- 或全局管理员

#### <a name="deploying-policy"></a>部署策略 

In Microsoft Endpoint Manager [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)  

1. 配置 **使用与这些设备设置类匹配的驱动程序阻止安装设备**。

    - Open Endpoint security > Attack surface reduction > Create Policy > Platform： Windows 10 (and later) & Profile： Device control.
    
      :::image type="content" source="../../media/devicepolicy-editprofile.png" alt-text="编辑配置文件":::
    
2. 插入 USB、设备，你将看到以下错误消息：

      :::image type="content" source="../../media/devicepolicy-errormsg.png" alt-text="错误消息":::

3. 启用 **应用跨所有设备匹配条件的允许和阻止设备安装策略的分层评估顺序**。

    - **现在仅支持 OMA-URI：>** 配置文件>创建配置文件>平台：Windows 10 (及更高版本) &配置文件：自定义
    
      :::image type="content" source="../../media/devicepolicy-editrow.png" alt-text="编辑行":::

4. 启用和添加允许的 USB 实例 ID – 允许安装与这些设备 ID 匹配 **的设备**。

    - 更新步骤 1 设备控件配置文件
    
      :::image type="content" source="../../media/devicepolicy-devicecontrol.png" alt-text="devicecontrol":::
       
    添加 PCI\CC_0C03;PCI\CC_0C0330;PCI\VEN_8086;PNP0CA1;PNP0CA1 &HOST; USB\ROOT_HUB30;USB\ROOT_HUB20;USB\USB20_HUB以上屏幕捕获的原因是，仅启用单个硬件 ID 以启用单个 USB U 盘是不够的。 你必须确保不会阻止目标设备之前的所有 USB 设备 (允许) 设备。 你可以打开设备管理器，将视图更改为"通过连接的设备"以查看设备在 PnP 树中的安装方式。 在我们的案例中，必须允许以下设备，以便也可以允许目标 U 盘： 

    - "Intel (R) USB 3.0 eXtensible 主机控制器 – 1.0 (Microsoft) " -> PCI\CC_0C03 
    - "USB 根集线器 (USB 3.0) " -> USB\ROOT_HUB30 
    - "通用 USB 集线器"-> USB\USB20_HUB

    :::image type="content" source="../../media/devicepolicy-devicemgr.png" alt-text="设备控件":::

    > [!NOTE]
    > 系统中的某些设备具有多个连接层来定义在系统上的安装。 USB U 盘是此类设备。 因此，当在系统上查找阻止或允许它们时，了解每台设备的连接路径非常重要。 系统通常使用一些通用设备 ID，可以在此类情况下为生成"允许列表"提供良好的开始。 下面是一个示例 (所有 USB 并不总是一样;你需要了解要通过设备管理器管理的设备 PnP 树) ：
    >
    > PCI\CC_0C03;PCI\CC_0C0330;PCI\VEN_8086;PNP0CA1;PNP0CA1&HOST (for Host Controllers) / USB\ROOT_HUB30;USB\ROOT_HUB20 (U 盘的 USB 根) / USB\USB20_HUB (通用 USB 中心) / 
    >
    > 特别是对于桌面计算机，在以上列表中列出键盘和鼠标连接的所有 USB 设备非常重要。 如果不这样做，可能会阻止用户通过 HID 设备访问其计算机。 
    >
    > 不同的电脑制造商有时使用不同的方法将 USB 设备嵌套在 PnP 树中，但一般情况下，这是操作方法。 

5. 再次插入允许的 USB。 你将看到它现在允许并且可用。

    :::image type="content" source="../../media/devicepolicy-removedrive.png" alt-text="删除驱动器":::

#### <a name="deploying-and-managing-policy-via-group-policy"></a>通过组策略部署和管理策略

设备安装功能允许你通过组策略应用策略。

#### <a name="licensing"></a>授权

若要访问和使用设备安装，必须拥有 Windows E3。

#### <a name="deploying-policy"></a>部署策略

你可以在此处找到部署详细信息[：Manage Device Installation with Group Policy (Windows 10) - Windows Client](/windows/client-management/manage-device-installation-with-group-policy)。

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 存储设备控件可移动访问控件数据

安全[Microsoft 365显示](https://sip.security.microsoft.com/homepage)设备控制设备安装阻止的可移动存储。 若要访问Microsoft 365安全性，您必须具有以下订阅：

- Microsoft 365 E5 报告

```kusto
//events triggered by Device Installation policies 
DeviceEvents 
| where ActionType == "PnpDeviceBlocked" or ActionType == "PnpDeviceAllowed" 
| extend parsed=parse_json(AdditionalFields) 
| extend MediaClassGuid = tostring(parsed.ClassGuid)  
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaDeviceId = tostring(parsed.MatchingDeviceId) 
| project Timestamp , DeviceId, DeviceName, ActionType, MediaClassGuid, MediaDeviceId, MediaInstanceId, AdditionalFields 
| order by Timestamp desc 
```

:::image type="content" source="../../media/block-removable-storage2.png" alt-text="阻止存储":::

## <a name="frequently-asked-questions"></a>常见问题

### <a name="how-can-i-know-whether-the-target-machine-gets-the-deployed-policy"></a>如何知道目标计算机是否获取已部署的策略？ 
可以使用以下查询在安全门户上获取反恶意软件Microsoft 365版本：

```kusto
//check whether the Device installation policy has been deployed to the target machine, event only when modification happens   
DeviceRegistryEvents 
| where RegistryKey contains "HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\DeviceInstall\\" 
| order by Timestamp desc
```

## <a name="why-the-allow-policy-doesnt-work"></a>为什么允许策略不起作用？
仅启用单个硬件 ID 以启用单个 USB U 盘是不够的。 确保不会阻止目标设备之前的所有 USB (允许) 设备。

:::image type="content" source="../../media/devicemgrscrnshot.png" alt-text="设备安装常见问题解答":::

