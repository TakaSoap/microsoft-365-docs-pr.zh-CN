---
title: Microsoft Defender for Endpoint 设备控制打印机保护
description: Microsoft Defender for Endpoint 设备控制打印机保护会阻止用户通过非公司打印机或未批准的 USB 打印机进行打印。
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: dansimp
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.openlocfilehash: f97a5ae486ff2ebd39a1adedeb008ac675ee9941
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962815"
---
# <a name="device-control-printer-protection"></a>设备控制打印机保护

Microsoft Defender for Endpoint 设备控制打印机保护会阻止用户通过非公司打印机或未批准的 USB 打印机进行打印。

## <a name="licensing"></a>授权

在开始使用打印机保护之前，你应该[确认你的Microsoft 365订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)。 若要访问和使用打印机保护，您必须具有以下各项：

- Microsoft 365 E3/策略部署
- Microsoft 365 E5报告功能

## <a name="permission"></a>权限

对于 Intune 中的策略部署，若要通过 OMA-URI 部署策略，帐户必须具有创建、编辑、更新或删除设备配置文件的权限。 可以创建自定义角色或使用具有以下权限的任何内置角色：

- 策略和配置文件管理器角色。
- 或为设备配置文件启用创建/编辑/更新/读取/删除/查看报告权限的自定义角色
- 或全局管理员

若要查看设备配置报告，该帐户必须具有查看报告权限。 你可以创建自定义角色或使用具有以下权限的内置角色：

- 全局安全管理员
- 安全管理员
- 安全信息读取者

## <a name="prepare-your-endpoints"></a>准备终结点

确保已Windows 10或Windows 11部署打印机保护以满足这些要求的设备。

1. 已安装以下 Windows 更新。
    - For Windows 1809： install Windows Update [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)
    - For Windows 1909： install Windows Update [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)
    - For Windows 2004 or later

2. 如果你计划通过组策略部署策略，则必须将设备载入 Microsoft Defender，以加入终结点;如果你计划通过 Microsoft Endpoint Manager 部署策略，则必须使用 Microsoft Intune。

## <a name="deploy-device-control-printer-protection-policy"></a>部署设备控制打印机保护策略

可以通过组策略或 Intune 部署策略。

<br>

****

|Title|说明|云解决方案提供商支持 | GPO 支持 | 基于用户的支持 | 基于计算机的支持 |
|---|---|:---:|:---:|:---:|:---:|
|**启用设备控制打印限制**|阻止用户通过非公司打印机打印|是|是|是|是|
|**已批准的 USB 连接打印设备列表**\*|允许特定 USB 打印机|是|是|是|是|
|

\* 此策略必须与启用设备控制 **打印限制一同使用**。

## <a name="deploy-policy-via-intune"></a>通过 Intune 部署策略

对于 Intune，当前设备控制打印机保护仅支持 OMA-URI。

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a>方案 1：使用 Intune 阻止用户通过任何非公司打印机打印

- 在计算机上应用策略：

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- 对用户应用策略：

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

CSP 支持字符串，包含 `<enabled/>` ：

:::image type="content" source="../../media/customeditrow.png" alt-text="自定义编辑行。":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a>方案 2：允许使用 Intune 的特定批准的 USB 打印机

- 在计算机上应用策略：

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- 对用户应用策略：

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

通过"ApprovedUsbPrintDevices"属性批准的 USB 打印机的云解决方案提供商支持字符串，示例 `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">` ：

:::image type="content" source="../../media/editrow.png" alt-text="编辑行。":::

## <a name="deploy-policy-via-group-policy"></a>通过组策略部署策略

如果设备未加入 Intune，则还可以通过组策略部署策略。

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a>方案 1：使用组策略阻止用户通过任何非公司打印机打印

- 在计算机上应用策略：

  计算机配置 \> 管理模板 \> 打印机：启用设备控制打印限制

- 对用户应用策略：

  用户配置 \> 管理模板 \> 控制面板 \> 打印机：启用设备控件打印限制

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="启用设备打印限制。":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a>方案 2：允许使用组策略的特定批准的 USB 打印机

- 在计算机上应用策略：

  计算机配置 \> 管理模板 \> 打印机：已批准 USB 连接的打印设备列表

- 对用户应用策略：

  用户配置 \> 管理模板 \> 控制面板 \> 打印机：已批准 USB 连接的打印设备列表

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="批准的 usb 连接打印设备列表。":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a>在 Microsoft Defender 终结点门户中查看设备控制打印机保护数据

安全<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365显示</a>上述设备控制打印机保护策略阻止的打印。

```kusto
DeviceEvents
| where ActionType == 'PrintJobBlocked'
| extend parsed=parse_json(AdditionalFields)
| extend PrintedFile=tostring(parsed.JobOrDocumentName)
| extend PrintPortName=tostring(parsed.PortName)
| extend PrinterName=tostring(parsed.PrinterName)
| extend Policy=tostring(parsed.RestrictionReason) 
| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName, Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields
| order by Timestamp desc
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="高级搜寻。":::

 可以使用 PnP 事件查找组织中使用的 USB 打印机：

```kusto
//find the USB Printer VID/PID
DeviceEvents
| where ActionType == "PnpDeviceConnected"
| extend parsed=parse_json(AdditionalFields)
| extend DeviceDescription = tostring(parsed.DeviceDescription) 
| extend PrinterDeviceId = tostring(parsed.DeviceId) 
| extend VID_PID_Array = split(split(PrinterDeviceId, "\\")[1], "&")
| extend VID_PID = replace_string(strcat(VID_PID_Array[0], '/', VID_PID_Array[1]), 'VID_', '')
| extend VID_PID = replace_string(VID_PID, 'PID_', '')
| extend ClassId = tostring(parsed.ClassId) 
| extend VendorIds = tostring(parsed.VendorIds) 
| where DeviceDescription == 'USB Printing Support'
| project Timestamp , DeviceId, DeviceName, ActionType, DeviceDescription, VID_PID, ClassId, PrinterDeviceId, VendorIds, parsed
| order by Timestamp desc
```

 :::image type="content" source="https://user-images.githubusercontent.com/81826151/128954383-71df3009-77ef-40db-b575-79c73fda332b.png" alt-text="高级搜寻":::








 
 
 
 
