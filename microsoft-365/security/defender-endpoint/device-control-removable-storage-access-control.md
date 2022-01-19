---
title: Microsoft Defender for Endpoint 设备控件可移动存储访问控制，可移动存储媒体
description: 有关 Microsoft Defender for Endpoint 的演练
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: mde
ms.date: 01/10/2022
ms.openlocfilehash: 6ebda98668f1593268433ee620406b70eafab2da
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2022
ms.locfileid: "62073655"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender for Endpoint 设备控件可移动存储访问控制

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!NOTE]
> 该产品的组策略管理现已在 (4.18.2106) ：请参阅 Tech Community 博客：使用[Microsoft Defender for Endpoint](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806)保护可移动存储和打印机


Microsoft Defender for Endpoint 设备控制可移动存储访问控制使你能够执行以下任务：

- 审核，允许或阻止对可移动存储进行读取、写入或执行访问（带排除或不排除）

<br/><br/>

|Privilege|权限|
|---|---|
|访问|读取、写入、执行|
|操作模式|审核、允许、阻止|
|云解决方案提供商支持|是|
|GPO 支持|是|
|基于用户的支持|是|
|基于计算机的支持|是|

<br/><br/>

|功能|说明|通过 Intune 部署|通过组策略部署|
|---|---|---|---|
|可移动媒体组创建|允许你创建可重用的可移动媒体组|通过[OMA-URI](#deploying-policy-via-oma-uri)部署策略部分的步骤 1 和步骤 3 | 通过组策略[部署策略部分](#deploying-policy-via-group-policy)的步骤 1|
|策略创建|允许你创建策略以强制执行每个可移动媒体组|通过[OMA-URI](#deploying-policy-via-oma-uri)部署策略部分的步骤 2 和 3 | 通过组策略[部署策略部分](#deploying-policy-via-group-policy)的步骤 2 |
|默认强制|允许你将默认访问设置为" ("或"允许) 访问可移动媒体"（如果没有策略）|通过[OMA-URI](#deploying-policy-via-oma-uri)部署策略部分的步骤 4 | 通过组策略[部署策略部分](#deploying-policy-via-group-policy)的步骤 3 |
|启用或禁用可移动存储访问控制|如果设置"禁用"，它将在此计算机上禁用存储"访问控制"策略| 通过[OMA-URI](#deploying-policy-via-oma-uri)部署策略部分的步骤 5 | 通过组策略[部署策略部分](#deploying-policy-via-group-policy)的步骤 4 |

## <a name="prepare-your-endpoints"></a>准备终结点

在存储 **4.18.2103.3** 或更高版本的 Windows 10 和 Windows 11 设备上部署可移动访问控制。

- **4.18.2104 或更高版本**：添加 SerialNumberId、VID_PID、基于 filepath 的 GPO 支持、ComputerSid

- **4.18.2105** 或更高版本：添加对 HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId 的通配符支持，特定计算机上特定用户的组合、可删除的 SSD (SanDisk 极性 SSD) /USB 附加 SCSI (UAS) 支持

- **4.18.2107 或** 更高版本：为移动设备（如平板电脑) ）添加 Windows 便携设备 (WPD) 支持 (;将 AccountName 添加到高级搜寻中 [](device-control-removable-storage-access-control.md#view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint)

- **4.18.2111 或** 更高版本：通过 PowerShell 添加"启用或禁用可移动 存储 访问控制"、"默认强制"，客户端计算机策略更新时间。

:::image type="content" source="images/powershell.png" alt-text="PowerShell 接口。":::

> [!NOTE]
> 任何Windows 安全中心组件都不需要处于活动状态，因为您可以独立于用户状态存储可移动Windows 安全中心访问控制。

## <a name="policy-properties"></a>策略属性

可以使用以下属性创建可移动存储组：

> [!NOTE]
> 可以使用 XML 注释表示法的注释在 Rule 和 Group XML 文件中使用，但它们必须位于第一个 XML 标记中，而不是 XML 文件的第一 `<!-- COMMENT -->` 行内。

### <a name="removable-storage-group"></a>可移动存储组

<br/><br/>

|属性名称|说明|Options|
|---|---|---|
|**GroupId**|GUID 是一个唯一 ID，表示组，将在策略中使用。||
|**DescriptorIdList**|列出你想要在组中覆盖的设备属性。 有关每个设备属性的详细信息，请参阅 [设备](device-control-removable-storage-protection.md) 属性。 所有属性都区分大小写。 |**PrimaryId**： `RemovableMediaDevices` 、 `CdRomDevices` 、 `WpdDevices`<p>**BusId**：例如，USB、SCSI<p>**DeviceId**<p>**HardwareId**<p>**InstancePathId**：InstancePathId 是一个字符串，用于唯一标识系统中设备，例如 ， `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0` 。 末尾的号码 (例如 0 &0) 表示可用插槽，并且可能会从设备更改为设备。 为获得最佳结果，请结尾使用通配符。 例如，`USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*`。<p>**FriendlyNameId**<p>**SerialNumberId**<p>**VID**<p>**PID**<p>**VID_PID**<p>0751_55E0：匹配此精确的 VID/PID 对<p>55E0：匹配 PID=55E0 的任何媒体 <p>0751：匹配任何具有 VID=0751 的媒体|
|**MatchType**|当 在 中使用多个设备属性时 `DescriptorIDList` ，MatchType 定义关系。|**MatchAll：** 下的任何属性将为 And 关系;例如，如果管理员将 和 放在每个连接的 USB 上，系统将检查 USB 是否同时满足这 `DescriptorIdList`  `DeviceID` `InstancePathID` 两个值。 <p> **MatchAny**：DescriptorIdList 下的属性将为 **Or** 关系;例如，如果管理员将 和 放在 ，则对于每个连接的 USB，只要 USB 具有相同的 DeviceID 或 InstanceID 值，系统就会执行 `DeviceID` `InstancePathID` **强制** 操作。  |

### <a name="access-control-policy"></a>访问控制策略

<br/><br/>

| 属性名称 | 说明 | Options |
|---|---|---|
| **PolicyRuleId** | GUID 是一个唯一 ID，表示策略，将用于报告和疑难解答。 | |
| **IncludedIdList** | 组 (策略) 的组。 如果添加了多个组，该策略将应用于所有这些组的任何媒体。|必须在此实例中使用组 ID/GUID。 <p> 以下示例显示 GroupID 的用法： <p> `<IncludedIdList> <GroupId> {EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>` |
| **ExcludedIDList** | 组 (策略) 的组。 | 必须在此实例中使用组 ID/GUID。 |
| **条目 ID** | 一个 PolicyRule 可以有多个条目;每个具有唯一 GUID 的条目告知设备控件一个限制。| |
| **类型** | 定义 IncludedIDList 中可移动存储组的操作。 <p>强制：允许或拒绝 <p>审核：AuditAllowed 或 AuditDenied<p> | 允许<p>拒绝 <p>AuditAllowed：定义允许访问时的通知和事件 <p>AuditDenied：定义拒绝访问时的通知和事件;必须配合拒绝 **条目** 一起工作。<p> 当同一媒体存在冲突类型时，系统将应用策略中的第一个冲突类型。 冲突类型的一个示例是 **"允许"和**"**拒绝"。** |
| **Sid** | 本地用户 Sid 或用户 Sid 组或 AD 对象的 Sid 定义是否对特定用户或用户组应用此策略;一个条目最多可具有一个 Sid 和一个不带任何 Sid 的条目，这意味着在计算机中应用策略。 |  |
| **ComputerSid** | 本地计算机 Sid 或计算机 Sid 组或 AD 对象的 Sid 定义是否对特定计算机或计算机组应用此策略;一个条目最多可具有一个 ComputerSid，而一个条目没有任何 ComputerSid 意味着将策略应用到计算机。 如果要将条目应用于特定用户和特定计算机，请同时将 Sid 和 ComputerSid 添加到同一条目中。 |  |
| **选项** | 定义是否显示通知 |**0 或 4：** 选择"允许"或"拒绝"时。 <p>0：无<p>4：对此条目 **禁用 AuditAllowed** **和 AuditDenied。** 即使 **发生阻止** 且已配置 AuditDenied 设置，系统也将不会显示通知。 <p> 选择" **类型 AuditAllowed"** 时： <p>0：无 <p>1：无 <p>2：发送事件<p>3：发送事件 <p> 选择" **类型 AuditDenied"** 时： <p>0：无 <p>1：显示通知 <p>2：发送事件<p>3：显示通知和发送事件 |
|AccessMask|定义访问权限。 | **1-7**： <p>1：读取 <p>2：写入 <p>3：读取和写入 <p>4：执行 <p>5：读取和执行<p>6：写入和执行 <p>7：读取、写入和执行 |

## <a name="common-removable-storage-access-control-scenarios"></a>常见的可移动存储访问控制方案

为了帮助你熟悉 Microsoft Defender for Endpoint Removable 存储访问控制，我们将一些常见方案放在一起，以便你可以遵循。

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>方案 1：阻止对全部 USB 执行写入和执行访问，但允许特定批准的 USB

1. 创建组

    1. 组 1：任何可移动存储和 CD/DVD。 可移动存储和 CD/DVD 的一个示例是：示例任何可移动 存储 和 [CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件中的组 **9b28fae8-72f7-4267-a1a5-685f747a7146。**

    2. 组 2：基于设备属性批准的 USB。 此用例的一个示例是：示例已批准 [USB Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件中的实例 ID - 组 **65fa649a-a111-4912-9294-fb6337a25038。**

    > [!TIP]
    > 将 `&` 替换为 `&amp;` 值。

2. 创建策略

    1. 策略 1：阻止写入和执行访问，但允许批准的 USB。 此用例的一个示例是：示例方案 [1](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)阻止写入和执行访问但允许批准的 USBs.xml文件中的 PolicyRule **c544a991-5786-4402-949e-a032cb790d0e。**

    2. 策略 2：审核对允许的 USB 的写入和执行访问权限。 此用例的一个示例是：对已批准的 [USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件进行审核写入和执行访问示例中的 PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c。**

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>方案 2：审核对全部（但阻止特定未批准的 USB）的写入和执行访问权限

1. 创建组

    1. 组 1：任何可移动存储和 CD/DVD。 此用例的一个示例是：示例 Any [Removable 存储 and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file中的 Group **9b28fae8-72f7-4267-a1a5-685f747a7146。**

    2. 组 2：基于设备属性的未批准的 USB，例如未批准的 USB Group.xml文件中的示例供应商 ID/产品 ID、友好名称 – 组 **65fa649a-a111-4912-9294-fb6337a25038。** [](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)

    > [!TIP]
    > 将 `&` 替换为 `&amp;` 值。

2. 创建策略

    1. 策略 1：阻止对全部（但阻止特定未批准的 USB）的写入和执行访问。 此用例的一个示例是：示例方案 2 审核写入和执行对除阻止特定未批准的 [USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件的访问中的 PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98。**

    2. 策略 2：审核写入和执行对他人的访问。 此用例的一个示例是：对 [others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件进行审核写入和执行访问示例中的 PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48。**

## <a name="deploying-and-managing-policy-via-group-policy"></a>通过组策略部署和管理策略

使用"存储访问控制"功能，可以通过组策略将策略应用于用户或设备，或同时应用于两者。

### <a name="licensing"></a>授权

在开始使用可移动存储访问控制之前，必须确认Microsoft 365[订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。 若要访问和使用可移动存储访问控制，您必须具有Microsoft 365 E3或Microsoft 365 E5。

### <a name="deploying-policy-via-group-policy"></a>通过组策略部署策略

1. 将所有组组合到 `<Groups>` `</Groups>` 一个 xml 文件中。

    下图演示了方案 [1：](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)阻止对全部但允许特定批准的 USB 的写入和执行访问的示例。

    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="显示允许在设备上允许特定批准的 USB 的配置设置的屏幕。":::

2. 将所有规则合并到 `<PolicyRules>` `</PolicyRules>` 一个 xml 文件中。

    如果要限制特定用户，请使用 Entry 中的 SID 属性。 如果策略条目中没有任何 SID，则条目将应用于计算机的每一个登录实例。

    下图演示了 SID 属性的用法，以及方案 [1：](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)阻止对全部但允许特定批准的 USB 的写入和执行访问的示例。

    :::image type="content" source="images/usage-sid-property.png" alt-text="显示指示 SID 属性属性使用情况的代码的屏幕。":::

3. 在网络共享文件夹中保存规则和组 XML 文件，将网络共享文件夹路径放入组策略设置：**计算机配置** 管理模板 \>  \> **Windows 组件** \> **Microsoft Defender 防病毒** \> **设备控制****：'定义设备控制策略组'** 和'定义设备控制 **策略规则'**.

   如果在组策略中找不到策略配置 UX，则可以通过选择"原始"，然后选择"另存为"来下载 [WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml)和 [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) **文件**。

   - 目标计算机必须能够访问网络共享才能拥有策略。 但是，读取策略后，不再需要网络连接，即使在计算机重新启动后也不例外。

    :::image type="content" source="images/device-control.png" alt-text="设备控制屏幕。":::

4. 默认强制：允许你设置默认访问 (，如果) 策略，则允许访问可移动媒体。 例如，仅对 RemovableMediaDevices 具有策略 (Deny 或 Allow) ，但没有针对 CdRomDevices 或 WpdDevices 的任何策略，并且通过此策略设置默认拒绝，将阻止对 CdRomDevices 或 WpdDevices 的读/写/执行访问。

   - 部署此设置后，你将看到"**默认允许"** 或"**默认拒绝"。**

    :::image type="content" source="images/148609579-a7df650b-7792-4085-b552-500b28a35885.png" alt-text="默认允许或默认拒绝 PowerShell 代码":::

5. 启用或禁用存储访问控制：可以设置此值以暂时禁用"可存储访问控制"。

    :::image type="content" source="images/148608318-5cda043d-b996-4146-9642-14fccabcb017.png" alt-text="设备控制设置":::

   - 部署此设置后，你将看到"已启用"或"已禁用"- "已禁用"表示此计算机没有运行"可存储"访问控制策略。

    :::image type="content" source="images/148609685-4c05f002-5cbe-4aab-9245-83e730c5449e.png" alt-text="在 PowerShell 代码中启用或禁用设备控件":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>通过 Intune OMA-URI 部署和管理策略

通过可移动存储访问控制功能，你可以将策略通过 OMA-URI 应用到用户或设备，或同时应用到两者。

### <a name="licensing-requirements"></a>许可要求

在开始使用"可移动存储访问控制"之前，必须确认Microsoft 365[订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。 若要访问和使用可移动存储访问控制，您必须具有Microsoft 365 E3或Microsoft 365 E5。

### <a name="permission"></a>权限

对于 Intune 中的策略部署，该帐户必须具有创建、编辑、更新或删除设备配置文件的权限。 可以创建自定义角色或使用具有这些权限的任何内置角色。

- 策略和配置文件管理器角色

- 为设备配置文件启用"创建/编辑/更新/读取/删除/查看报告"权限的自定义角色

- 全局管理员

### <a name="deploying-policy-via-oma-uri"></a>通过 OMA-URI 部署策略

Microsoft Endpoint Manager管理中心 <https://endpoint.microsoft.com/> () 配置文件 创建 \>  \>  \> **配置文件** 平台 \> **：Windows 10及更高版本&配置文件：自定义**

1. 对于每个组，创建 OMA-URI 规则：

    - OMA-URI： 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b**GroupGUID**%7d/GroupData`

      例如，对于 **示例中的任何可移动存储和 CD/DVD** 组，该链接必须为：

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData`

    - 数据类型：String (XML) 

      :::image type="content" source="images/xml-data-type-string.png" alt-text="STRING 文件的 xml 数据类型。":::

2. 对于每个策略，还要创建 OMA-URI：

    - OMA-URI： 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7b**PolicyRuleGUID**%7d/RuleData`

      例如，对于示例中 **的"阻止写入和执行访问但允许批准的 USB"** 规则，该链接必须是：

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData`

    - 数据类型：String (XML) 

3. 默认强制：允许你设置默认访问 (，如果) 策略，则允许访问可移动媒体。 例如，仅对 RemovableMediaDevices 具有策略 (Deny 或 Allow) ，但没有针对 CdRomDevices 或 WpdDevices 的任何策略，并且通过此策略设置默认拒绝，将阻止对 CdRomDevices 或 WpdDevices 的读/写/执行访问。

    - OMA-URI： `./Vendor/MSFT/Defender/Configuration/DefaultEnforcement`

    - 数据类型：Int

      `DefaultEnforcementAllow = 1`
      `DefaultEnforcementDeny = 2`

    - 部署此设置后，你将看到" **默认允许"** 或" **默认拒绝"**

    :::image type="content" source="images/148609590-c67cfab8-8e2c-49f8-be2b-96444e9dfc2c.png" alt-text="默认强制允许 PowerShell 代码":::

4. 启用或禁用存储访问控制：可以设置此值以暂时禁用"可存储访问控制"。

   - OMA-URI： `./Vendor/MSFT/Defender/Configuration/DeviceControlEnabled`

   - 数据类型：Int `Disable: 0`
     `Enable: 1`

   - 部署此设置后， **你将看到已启用** 或 **已禁用**

    **已禁用** 意味着此计算机没有运行存储可移动控件策略

    :::image type="content" source="images/148609770-3e555883-f26f-45ab-9181-3fb1ff7a38ac.png" alt-text="PowerShell 存储可删除的访问控制":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>使用 Intune 用户界面部署和管理策略

此功能在管理中心Microsoft Endpoint Manager中心 <https://endpoint.microsoft.com/> () 。 转到终结点 **安全**  >  **攻击面减少**  >  **创建策略**。 选择 **"平台：Windows 10****配置文件：设备控件"和更高版本**。

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 存储设备控件可移动访问控件数据

该[Microsoft 365 Defender门户](https://security.microsoft.com/advanced-hunting)显示由设备控件可移动控件存储访问控制触发的事件。 若要访问Microsoft 365安全性，您必须具有以下订阅：

- Microsoft 365 E5 报告

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == "RemovableStoragePolicyTriggered"
| extend parsed=parse_json(AdditionalFields)
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)
| extend MediaBusType = tostring(parsed.BusType)
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId)
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId)
| extend MediaName = tostring(parsed.MediaName)
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)
| extend MediaProductId = tostring(parsed.ProductId)
| extend MediaVendorId = tostring(parsed.VendorId)
| extend MediaSerialNumber = tostring(parsed.SerialNumber)
|project Timestamp, DeviceId, DeviceName, InitiatingProcessAccountName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="描述可移动存储被阻止的屏幕。":::

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="what-is-the-removable-storage-media-limitation-for-the-maximum-number-of-usbs"></a>最大 USB 数量的可移动存储媒体限制是什么？

我们已验证一个具有 100，000 个媒体的 USB 组 - 大小最高为 7 MB。 该策略在 Intune 和 GPO 中均有效，而未发生性能问题。

### <a name="why-does-the-policy-not-work"></a>为什么策略不起作用？

最常见的原因是不需要反 [恶意软件客户端版本](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)。

另一个原因是 XML 文件格式不正确，例如，未对 XML 文件中"&"字符使用正确的 markdown 格式，或者文本编辑器可能在文件开头添加字节顺序标记 (BOM) 0xEF 0xBB 0xBF，这会导致 XML 分析不起作用。 一个简单的解决方案是下载示例文件 [](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)**， ("原始****"，** 然后选择"另存为) 然后更新。

如果要通过组策略部署和管理策略，请确保将所有 PolicyRule 合并到名为 PolicyRules 的父节点内的一个 XML 文件中，将所有 Group 合并到名为 Groups 的父节点内的一个 XML 文件中;如果你通过 Intune 进行管理，请保留一个 PolicyRule 一个 XML 文件，同一个内容，一个组一个 XML 文件。

### <a name="there-is-no-configuration-ux-for-define-device-control-policy-groups-and-define-device-control-policy-rules-on-my-group-policy"></a>我的组策略上没有"定义设备控制策略组"和"定义设备控制策略规则"的配置 UX

我们不备份组策略配置 UX，但你仍然可以获取相关的 adml 和 admx 文件，方法是在 [WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) 和 [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) 文件中单击"Raw"和"另存为"。


### <a name="how-can-i-know-whether-the-latest-policy-has-been-deployed-to-the-target-machine"></a>如何知道是否已将最新策略部署到目标计算机？

你可以以管理员角色在 PowerShell 上运行"Get-MpComputerStatus"。 以下值将显示是否已将最新的策略应用于目标计算机。

:::image type="icon" source="images/148609885-bea388a9-c07d-47ef-b848-999d794d24b8.png" border="false":::

### <a name="how-can-i-know-which-machine-is-using-out-of-date-antimalware-client-version-in-the-organization"></a>如何知道哪个计算机正在使用组织中过期的反恶意软件客户端版本？

可以使用以下查询在安全门户上获取反恶意软件Microsoft 365版本：

```kusto
//check the antimalware client version
DeviceFileEvents
|where FileName == "MsMpEng.exe"
|where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
|extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//|project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
|summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
|order by PlatformVersion desc
```
