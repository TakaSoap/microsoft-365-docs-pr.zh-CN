---
title: Microsoft Defender for Endpoint设备控制设备安装
description: 本主题介绍如何Microsoft Defender for Endpoint设备控制设备安装
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
ms.openlocfilehash: dc05633d1badfc29b2179915ac6d318dd9523834
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666385"
---
# <a name="microsoft-defender-for-endpoint-device-control-device-installation"></a>Microsoft Defender for Endpoint设备控制设备安装

**适用对象**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint设备控制设备安装可以执行以下任务：

- 阻止用户安装特定设备。
- 允许用户安装特定设备，但阻止其他设备。

> [!NOTE]
> 若要查找设备安装和可移动存储访问控制之间的区别，请[参阅Microsoft Defender for Endpoint设备控制可移动存储保护](/microsoft-365/security/defender-endpoint/device-control-removable-storage-protection?view=o365-worldwide&preserve-view=true)。

|特权|权限|
|---|---|
|Access|设备安装 |
|操作模式|允许、阻止 |
|CSP 支持|是|
|GPO 支持|是|
|基于用户的支持|否|
|基于计算机的支持|是|

## <a name="prepare-your-endpoints"></a>准备终结点

在 Windows 10、Windows 11 设备Windows Server 2022 上部署设备安装。

## <a name="device-properties"></a>设备属性

设备安装支持支持以下设备属性：

- 设备 ID
- 硬件 ID
- 兼容 ID
- 设备类
- "可移动设备"设备类型：某些设备可归类为可移动设备。 连接到的设备的驱动程序指示设备可移动时，设备被视为可移动。 例如，据报道，连接到该设备的 USB 中心的驱动程序可移动 USB 设备。
有关详细信息，请参阅[Windows中的设备安装](/windows/client-management/manage-device-installation-with-group-policy)。

## <a name="policies"></a>策略

### <a name="allow-installation-of-devices-that-match-any-of-these-device-ids"></a>允许安装与上述任何设备 ID 匹配的设备

通过此策略设置，可以为允许安装Windows的设备指定即插即用硬件 ID 和兼容 ID 的列表。 仅当启用 **所有设备匹配条件策略设置的"允许和阻止设备安装策略"的应用分层评估顺序** 时，才会使用此策略设置。

当此策略设置与 **所有设备匹配条件策略设置中的允许和阻止设备安装策略的应用分层评估顺序** 一起启用时，允许Windows安装或更新任何设备，其即插即用硬件 ID 或兼容 ID 显示在你创建的列表中，除非层次结构中同一层或更高层的另一个策略设置专门阻止该安装， 例如，以下策略设置：

- 阻止安装与这些设备 ID 匹配的设备。
- 阻止安装与上述任何设备实例 ID 匹配的设备。

如果未使用此策略设置启用 **所有设备匹配条件策略设置的允许和阻止设备安装策略的应用分层评估顺序** ，则专门阻止安装的任何其他策略设置都将优先。

> [!NOTE]
> **阻止安装其他策略设置策略设置未描述的设备** 已被所有设备匹配条件策略设置中受支持的目标Windows 10版本和Windows 11的"**允许和阻止设备安装策略的应用分层评估顺序**"替换。 建议尽可能在 **所有设备匹配条件策略设置中使用"允许和阻止设备安装策略"的应用分层评估顺序** 。

### <a name="allow-installation-of-devices-that-match-any-of-these-device-instance-ids"></a>允许安装与上述任何设备实例 ID 匹配的设备

通过此策略设置，可以为允许安装Windows的设备指定即插即用设备实例 ID 列表。 仅当启用 **所有设备匹配条件策略设置的"允许和阻止设备安装策略"的应用分层评估顺序** 时，才会使用此策略设置。

当此策略设置与 **所有设备匹配条件策略设置中的允许和阻止设备安装策略的应用分层评估顺序** 一起启用时，允许Windows安装或更新即插即用设备实例 ID 显示在你创建的列表中的任何设备，除非层次结构中同一层或更高层的另一个策略设置专门阻止了该安装， 例如，以下策略设置：

- 阻止安装与上述任何设备实例 ID 匹配的设备

如果未使用此策略设置启用 **所有设备匹配条件策略设置的允许和阻止设备安装策略的应用分层评估顺序** ，则专门阻止安装的任何其他策略设置都将优先。

### <a name="allow-installation-of-devices-using-drivers-that-match-these-device-setup-classes"></a>允许使用与这些设备设置类匹配的驱动程序安装设备

通过此策略设置，可以指定设备安装程序类全局唯一标识符的列表 (GUID) Windows允许安装的驱动程序包。 仅当启用 **所有设备匹配条件策略设置的"允许和阻止设备安装策略"的应用分层评估顺序** 时，才会使用此策略设置。

如果将此策略设置与 **所有设备匹配条件策略设置中的允许和阻止设备安装策略的应用分层评估顺序** 一起启用，则允许Windows安装或更新设备安装类 GUID 显示在列表中的驱动程序包，除非层次结构中同一层或更高层的另一个策略设置专门阻止了该安装， 例如，以下策略设置：

- 阻止安装这些设备类的设备
- 阻止安装与这些设备 ID 匹配的设备
- 阻止安装与上述任何设备实例 ID 匹配的设备

如果未使用此策略设置启用 **所有设备匹配条件策略设置的允许和阻止设备安装策略的应用分层评估顺序** ，则专门阻止安装的任何其他策略设置都将优先。

### <a name="apply-layered-order-of-evaluation-for-allow-and-prevent-device-installation-policies-across-all-device-match-criteria"></a>在所有设备匹配条件中应用"允许和阻止设备安装策略"的分层评估顺序

此策略设置将更改在多个安装策略设置适用于给定设备时应用允许和阻止策略设置的评估顺序。 启用此策略设置可确保基于一个已建立的层次结构应用重叠的设备匹配条件，其中更具体的匹配条件取代了不太具体的匹配条件。 指定设备匹配条件的策略设置的分层评估顺序如下：

**设备实例 ID** \>**设备 ID** \>**设备安装程序类** \>**可移动设备**

#### <a name="device-instance-ids"></a>设备实例 ID

1. 禁止使用与这些设备实例 ID 匹配的驱动程序安装设备。
2. 允许使用与这些设备实例 ID 匹配的驱动程序安装设备。

#### <a name="device-ids"></a>设备 ID

1. 禁止使用与这些设备 ID 匹配的驱动程序安装设备。
2. 允许使用与这些设备 ID 匹配的驱动程序安装设备。

#### <a name="device-setup-class"></a>设备安装程序类

1. 禁止使用与这些设备设置类匹配的驱动程序安装设备。
2. 允许使用与这些设备设置类匹配的驱动程序安装设备。

#### <a name="removable-devices"></a>可移动设备

阻止安装可移动设备

> [!NOTE]
> 此策略设置提供比 **阻止安装其他策略设置策略设置未描述的设备** 更精细的控制。 如果同时启用这些冲突策略设置，则将启用 **所有设备匹配条件策略设置中"允许和阻止设备安装策略"的应用分层评估顺序** ，并忽略其他策略设置。

### <a name="prevent-installation-of-devices-that-match-any-of-these-device-ids"></a>阻止安装与上述任何设备 ID 匹配的设备

通过此策略设置，可以为阻止安装Windows的设备指定即插即用硬件 ID 和兼容 ID 的列表。 默认情况下，此策略设置优先于允许Windows安装设备的任何其他策略设置。

> [!NOTE]
> 若要启用 **与上述任何设备实例 ID 策略设置匹配的设备的允许安装** ，以取代适用于适用设备的此策略设置，请 **在所有设备匹配条件策略设置中启用"允许和阻止设备安装策略"的应用分层评估顺序** 。

如果启用此策略设置，Windows将无法安装其硬件 ID 或兼容 ID 显示在创建的列表中的设备。 如果在远程桌面服务器上启用此策略设置，则策略设置会影响将指定设备从远程桌面客户端重定向到远程桌面服务器。

如果禁用或未配置此策略设置，则可以根据允许或阻止其他策略设置安装和更新设备。

### <a name="prevent-installation-of-devices-that-match-any-of-these-device-instance-ids"></a>阻止安装与上述任何设备实例 ID 匹配的设备

通过此策略设置，可以为阻止安装Windows的设备指定即插即用设备实例 ID 的列表。 此策略设置优先于允许Windows安装设备的任何其他策略设置。

如果启用此策略设置，将阻止Windows安装设备，其设备实例 ID 显示在创建的列表中。 如果在远程桌面服务器上启用此策略设置，则策略设置会影响将指定设备从远程桌面客户端重定向到远程桌面服务器。

如果禁用或未配置此策略设置，则可以根据允许或阻止其他策略设置安装和更新设备。

### <a name="prevent-installation-of-devices-using-drivers-that-match-these-device-setup-classes"></a>使用与这些设备设置类匹配的驱动程序阻止安装设备

通过此策略设置，可以指定设备安装程序类全局唯一标识符的列表， () Windows阻止安装的驱动程序包的 GUID。 默认情况下，此策略设置优先于允许Windows安装设备的任何其他策略设置。

> [!NOTE]
> 若要启用 **与上述任何设备 ID 匹配的设备的允许安装** ，并 **允许安装与上述任何设备实例 ID 策略设置匹配的设备** 以取代适用于适用设备的此策略设置，请 **在所有设备匹配条件策略设置中启用"允许和阻止设备安装策略"的应用分层评估顺序** 。

如果启用此策略设置，将阻止Windows安装或更新设备安装类 GUID 显示在你创建的列表中的驱动程序包。 如果在远程桌面服务器上启用此策略设置，则策略设置会影响将指定设备从远程桌面客户端重定向到远程桌面服务器。

如果禁用或未配置此策略设置，Windows可以根据其他策略设置允许或阻止安装和更新设备。

### <a name="prevent-installation-of-removable-devices"></a>阻止安装可移动设备

通过此策略设置，可以防止Windows安装可移动设备。 连接到的设备的驱动程序指示设备可移动时，设备被视为可移动。 例如，一个通用串行总线 (USB) 设备报告可由设备连接到的 USB 中心的驱动程序移动。 默认情况下，此策略设置优先于允许Windows安装设备的任何其他策略设置。

> [!NOTE]
> 若要 **使用与这些设备设置类匹配的驱动程序启用允许安装设备**， **请允许安装与上述任何设备 ID 匹配的设备**，并 **允许安装与这些设备实例 ID 策略设置匹配的设备** ，以取代适用于适用设备的此策略设置，为 **所有设备匹配条件策略设置启用允许和阻止设备安装策略的应用分层评估顺序** 。

如果启用此策略设置，将阻止Windows安装可移动设备，现有可移动设备无法更新其驱动程序。 如果在远程桌面服务器上启用此策略设置，则策略设置会影响将可移动设备从远程桌面客户端重定向到远程桌面服务器。

如果禁用或未配置此策略设置，Windows可以根据其他策略设置允许或阻止安装和更新可移动设备的驱动程序包。

## <a name="common-removable-storage-access-control-scenarios"></a>常见可移动存储 访问控制方案

为了帮助你熟悉Microsoft Defender for Endpoint可移动存储 访问控制，我们已整理了一些常见方案供你关注。

### <a name="scenario-1-prevent-installation-of-all-usb-devices-while-allowing-an-installation-of-only-an-authorized-usb-thumb-drive"></a>方案 1：在仅允许安装授权 USB 拇指驱动器的同时，阻止安装所有 USB 设备

对于此方案，将使用以下策略：

- 禁止使用与这些设备设置类匹配的驱动程序安装设备。
- 在所有设备匹配条件中应用允许和阻止设备安装策略的分层评估顺序。
- 允许安装与上述任何设备实例 ID 匹配的设备，或允许安装与这些设备 ID 之一匹配的设备。

#### <a name="deploying-and-managing-policy-via-intune"></a>通过Intune部署和管理策略

设备安装功能允许通过Intune向设备应用策略。

#### <a name="licensing"></a>授权

在开始安装设备之前，应确认[Microsoft 365订阅](https://www.microsoft.com/en-in/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。 若要访问和使用设备安装，必须具有Microsoft 365 E3。

#### <a name="permission"></a>权限

对于Intune中的策略部署，帐户必须具有创建、编辑、更新或删除设备配置文件的权限。 可以创建自定义角色或使用具有以下权限的任何内置角色：

- 策略和配置文件管理器角色
- 或自定义角色，具有为设备配置文件启用的创建/编辑/更新/读取/删除/查看报表权限
- 或全局管理员

#### <a name="deploying-policy"></a>部署策略

在Microsoft Endpoint Manager [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)

1. **使用与这些设备设置类匹配的驱动程序配置阻止安装设备**。

    - 打开 Endpoint 安全>攻击面减少>创建策略>平台：Windows 10 (及更高版本) &配置文件：设备控制。

      :::image type="content" source="../../media/devicepolicy-editprofile.png" alt-text="&quot;编辑配置文件&quot;页" lightbox="../../media/devicepolicy-editprofile.png":::

2. 插入 USB、设备，你将看到以下错误消息：

      :::image type="content" source="../../media/devicepolicy-errormsg.png" alt-text="错误消息" lightbox="../../media/devicepolicy-errormsg.png":::

3. 为 **所有设备匹配条件的允许和阻止设备安装策略启用应用分层评估顺序**。

    - **目前仅支持 OMA-URI**：设备>配置文件>创建配置文件>平台：Windows 10 (和更高版本) &配置文件：自定义

      :::image type="content" source="../../media/devicepolicy-editrow.png" alt-text="&quot;编辑行&quot;页" lightbox="../../media/devicepolicy-editrow.png":::

4. 启用并添加允许的 USB 实例 ID – **允许安装与上述任何设备 ID 匹配的设备**。

    - 更新步骤 1 设备控制配置文件

      :::image type="content" source="../../media/devicepolicy-devicecontrol.png" alt-text="设备控制页中的标识符" lightbox="../../media/devicepolicy-devicecontrol.png":::

    添加 PCI\CC_0C03;PCI\CC_0C0330;PCI\VEN_8086;PNP0CA1;PNP0CA1&HOST; USB\ROOT_HUB30;USB\ROOT_HUB20;上面屏幕捕获上的 USB\USB20_HUB是因为它不足以仅启用单个硬件 ID 来启用单个 USB 缩略图驱动器。 必须确保不会阻止目标设备前面的所有 USB 设备 (也允许) 。 可以打开设备管理器并将视图更改为"按连接安装设备"，以查看设备在 PnP 树中的安装方式。 在本例中，必须允许以下设备，以便也可以允许目标 USB 拇指驱动器：

    添加 PCI\CC_0C03;PCI\CC_0C0330;PCI\VEN_8086;PNP0CA1;PNP0CA1&HOST; USB\ROOT_HUB30;USB\ROOT_HUB20;上面屏幕捕获上的 USB\USB20_HUB是因为它不足以仅启用单个硬件 ID 来启用单个 USB 缩略图驱动器。 必须确保不会阻止目标设备前面的所有 USB 设备 (也允许) 。 可以打开设备管理器并将视图更改为"按连接安装设备"，以查看设备在 PnP 树中的安装方式。 在本例中，必须允许以下设备，以便也可以允许目标 USB 拇指驱动器：

    - "Intel (R) USB 3.0 eXtensible Host Controller – 1.0 (Microsoft) " -> PCI\CC_0C03
    - "USB 根中心 (USB 3.0) " -> USB\ROOT_HUB30
    - "通用 USB 中心" -> USB\USB20_HUB

    :::image type="content" source="../../media/devicepolicy-devicemgr.png" alt-text="设备管理器页中的&quot;视图&quot;菜单项" lightbox="../../media/devicepolicy-devicemgr.png":::

    > [!NOTE]
    > 系统中的某些设备具有多个连接层来定义其在系统上的安装。 USB 拇指驱动器是此类设备。 因此，当希望在系统上阻止或允许它们时，请务必了解每个设备的连接路径。 系统中常用的一些通用设备 ID，可为此类情况下生成"允许列表"提供良好的开端。 下面是一个示例 (对于所有 USB 来说，它并不总是相同的;需要了解要通过设备管理器) 管理的设备的 PnP 树：
    >
    > PCI\CC_0C03;PCI\CC_0C0330;PCI\VEN_8086;PNP0CA1;适用于主机控制器的 PNP0CA1&主机 () /USB\ROOT_HUB30;适用于泛型 USB 中心的 USB 根中心) /USB\USB20_HUB (的 USB\ROOT_HUB20 () /
    >
    > 具体而言，对于桌面机，请务必列出键盘和鼠标通过上述列表连接的所有 USB 设备。 否则，可能会阻止用户通过 HID 设备访问其计算机。
    >
    > 不同的电脑制造商有时有不同的方法在 PnP 树中嵌套 USB 设备，但一般来说，这是它的方式。

5. 再次插入允许的 USB。 你将看到它现在已允许且可用。

    :::image type="content" source="../../media/devicepolicy-removedrive.png" alt-text="&quot;删除驱动器详细信息&quot;页" lightbox="../../media/devicepolicy-removedrive.png":::

#### <a name="deploying-and-managing-policy-via-group-policy"></a>通过组策略部署和管理策略

设备安装功能允许通过组策略应用策略。

#### <a name="licensing"></a>授权

若要访问和使用设备安装，必须具有Windows E3。

#### <a name="deploying-policy"></a>部署策略

可在此处找到部署详细信息：[使用组策略 (Windows 10) 管理设备安装 - Windows客户端](/windows/client-management/manage-device-installation-with-group-policy)。

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>在Microsoft Defender for Endpoint中查看设备控件可移动存储 访问控制数据

[Microsoft 365安全](https://sip.security.microsoft.com/homepage)门户显示设备控制设备安装阻止的可移动存储。 若要访问Microsoft 365安全性，必须具有以下订阅：

- 用于 E5 报告的Microsoft 365

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

:::image type="content" source="../../media/block-removable-storage2.png" alt-text="块存储" lightbox="../../media/block-removable-storage2.png":::

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="how-can-i-know-whether-the-target-machine-gets-the-deployed-policy"></a>如何知道目标计算机是否获取已部署的策略？

可以在Microsoft 365安全门户上使用以下查询获取反恶意软件客户端版本：

```kusto
//check whether the Device installation policy has been deployed to the target machine, event only when modification happens
DeviceRegistryEvents
| where RegistryKey contains "HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\DeviceInstall\\"
| order by Timestamp desc
```

## <a name="why-the-allow-policy-doesnt-work"></a>为什么允许策略不起作用？

仅启用单个硬件 ID 以启用单个 USB 拇指驱动器是不够的。 确保不会阻止目标设备前面的所有 USB 设备 (也允许) 。

:::image type="content" source="../../media/devicemgrscrnshot.png" alt-text="设备安装常见问题解答" lightbox="../../media/devicemgrscrnshot.png":::
