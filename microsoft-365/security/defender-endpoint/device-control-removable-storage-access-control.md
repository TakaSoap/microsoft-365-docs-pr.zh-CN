---
title: Microsoft Defender for Endpoint设备控制可移动存储 访问控制，可移动存储介质
description: 有关Microsoft Defender for Endpoint的演练
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
ms.date: 03/18/2022
ms.openlocfilehash: 03efd5f8681824b5625611e0c8c871bfc7fd03a6
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665131"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender for Endpoint设备控制可移动存储 访问控制

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!NOTE]
> 此产品的 组策略 管理和 Intune OMA-URI/自定义策略管理现已 (4.18.2106) 正式发布：请参阅 [Tech Community 博客：使用Microsoft Defender for Endpoint保护可移动存储和打印机](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806)。

Microsoft Defender for Endpoint设备控制可移动存储 访问控制使你能够执行以下任务：

- 审核、允许或阻止读取、写入或执行对可移动存储的访问，无论是否排除

|特权|权限|
|---|---|
|Access|读取、写入、执行|
|操作模式|审核、允许、阻止|
|CSP 支持|是|
|GPO 支持|是|
|基于用户的支持|是|
|基于计算机的支持|是|

|功能|说明|通过Intune进行部署|通过组策略进行部署|
|---|---|---|---|
|可移动媒体组创建|允许创建可重用的可移动媒体组|本部分中的步骤 1： [通过 OMA-URI 部署策略](#deploying-policy-via-oma-uri) | 本部分中的步骤 1：[通过 组策略 部署策略](#deploying-policy-via-group-policy)|
|策略创建|允许创建策略来强制执行每个可移动媒体组|本部分中的步骤 2： [通过 OMA-URI 部署策略](#deploying-policy-via-oma-uri) | 本部分中的步骤 2 和步骤 3，[通过 组策略 部署策略](#deploying-policy-via-group-policy) |
|默认强制|如果没有策略，则允许设置默认访问 (拒绝或允许) 可移动媒体|本部分中的步骤 3： [通过 OMA-URI 部署策略](#deploying-policy-via-oma-uri) | 本部分中的步骤 4：[通过组策略部署策略](#deploying-policy-via-group-policy) |
|启用或禁用可移动存储 访问控制|如果设置"禁用"，它将禁用此计算机上的"可移动存储 访问控制"策略| 本部分中的步骤 4： [通过 OMA-URI 部署策略](#deploying-policy-via-oma-uri) | 本部分中的步骤 5：[通过 组策略 部署策略](#deploying-policy-via-group-policy) |
|捕获文件信息|允许创建策略，以便在发生写入访问时捕获文件信息| 本部分中的步骤 2 和步骤 5， [通过 OMA-URI 部署策略](#deploying-policy-via-oma-uri) | 第 2 步和第 6 步，通过[组策略部署策略](#deploying-policy-via-group-policy) |

## <a name="prepare-your-endpoints"></a>准备终结点

在具有反恶意软件客户端 **4.18.2103.3 或更高** 版本的Windows 10和Windows 11设备上部署可移动存储 访问控制。

- **4.18.2104 或更高版本**：添加 SerialNumberId、VID_PID、基于文件路径的 GPO 支持、ComputerSid

- **4.18.2105 或更高版本**：添加对 HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId 的通配符支持，它是特定计算机上特定用户的组合，可删除 SSD (SanDisk Extreme SSD) /USB 附加 SCSI (UAS) 支持

- **4.18.2107 或更高版本**：添加Windows可移植设备 (WPD) 对移动设备（如平板电脑) ）的支持 (;将 AccountName 添加到 [高级搜寻](device-control-removable-storage-access-control.md#view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint)中

:::image type="content" source="images/powershell.png" alt-text="PowerShell 接口" lightbox="images/powershell.png":::

> [!NOTE]
> Windows 安全中心组件都不需要处于活动状态，因为可以独立于Windows 安全中心状态运行可移动存储 访问控制。

## <a name="policy-properties"></a>策略属性

可以使用以下属性创建可移动存储组：

> [!NOTE]
> 使用 XML 注释表示法的注释 `<!-- COMMENT -->` 可以在规则和组 XML 文件中使用，但它们必须位于第一个 XML 标记中，而不是 XML 文件的第一行内。

### <a name="removable-storage-group"></a>可移动存储组

|属性名称|说明|Options|
|---|---|---|
|**组 ID**|GUID（唯一 ID）表示组，并将在策略中用作 GroupId||
|**DescriptorIdList**|列出要用于在组中覆盖的设备属性。 有关每个设备属性，请参阅 [设备属性](device-control-removable-storage-protection.md) 以获取更多详细信息。 所有属性都区分大小写。 |**PrimaryId**： `RemovableMediaDevices`， `CdRomDevices``WpdDevices`<p>**BusId**：例如 USB、SCSI<p>**DeviceId**<p>**HardwareId**<p>**InstancePathId**：InstancePathId 是一个字符串，用于唯一标识系统中的设备，例如。 `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0` 末尾 (的数字，例如&0) 表示可用槽，并且可能会从设备更改为设备。 为了获得最佳结果，请在末尾使用通配符。 例如，`USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*`。<p>**FriendlyNameId**<p>**SerialNumberId**<p>**VID**<p>**PID**<p>**VID_PID**<p>`0751_55E0`：匹配此完全 VID/PID 对<p>`_55E0`：将任何媒体与 PID=55E0 匹配 <p>`0751_`：将任何媒体与 VID=0751 匹配|
|**MatchType**|当在其中使用 `DescriptorIDList`多个设备属性时，MatchType 将定义关系。|**MatchAll**：该属性下`DescriptorIdList`的任何属性都将是 **And** 关系;例如，如果管理员放置`DeviceID``InstancePathID`每个连接的 USB，系统将检查 USB 是否满足这两个值。 <p> **MatchAny**：DescriptorIdList 下的属性将为 **Or** 关系;例如，如果管理员为每个已连接的 USB 放置 `DeviceID` 并 `InstancePathID`执行强制执行操作，只要 USB 具有相同的 **DeviceID** 或 **InstanceID** 值。 |

### <a name="access-control-policy"></a>访问控制策略

| 属性名称 | 说明 | Options |
|---|---|---|
| **PolicyRule Id** | GUID 是一个唯一 ID，表示策略，将用于报告和故障排除。 | |
| **IncludedIdList** | 该组 (将应用策略的) 。 如果添加了多个组，则策略将应用于所有这些组中的任何媒体。|组 ID/GUID 必须在此实例中使用。 <p> 以下示例演示 GroupID 的用法： <p> `<IncludedIdList> <GroupId> {EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>` |
| **ExcludedIDList** | 组 (不会应用策略的) 。 | 组 ID/GUID 必须在此实例中使用。 |
| **条目 ID** | 一个 PolicyRule 可以有多个条目;每个具有唯一 GUID 的条目告诉设备控制一个限制。| |
| **Type** | 定义 IncludedIDList 中可移动存储组的操作。 <p>强制措施：允许或拒绝 <p>审核：AuditAllowed 或 AuditDenied<p> | 允许<p>拒绝 <p>AuditAllowed：定义允许访问时的通知和事件 <p>AuditDenied：定义拒绝访问时的通知和事件;必须与 **Deny** 条目协同工作。<p> 当同一媒体存在冲突类型时，系统将应用策略中的第一种。 冲突类型的示例是 **允许** 和 **拒绝**。 |
| **希** | 本地用户 Sid、用户 Sid 组或 AD 对象的 Sid 定义是对特定用户或用户组应用此策略;一个条目最多可以有一个 Sid 和一个条目，没有任何 Sid 意味着在计算机上应用策略。 |  |
| **ComputerSid** | 本地计算机 Sid、计算机 Sid 组或 AD 对象的 Sid 定义是对特定计算机或计算机组应用此策略：一个条目最多可以有一个 ComputerSid，一个条目没有任何 ComputerSid 意味着在计算机上应用策略。 如果要向特定用户和特定计算机应用条目，请将 Sid 和 ComputerSid 添加到同一条目中。 |  |
| **选项** | 定义是否显示通知 |**选择"允许类型"时**： <p>0：无<p>4：为此条目禁用 **AuditAllowed** 和 **AuditDenied** 。 即使 **发生"允许** "且已配置 AuditAllowed 设置，系统也不会发送事件。 <p>8：捕获文件信息，并将文件副本作为写入访问的证据。 <p>16：捕获文件信息以进行写入访问。 <p>**选择"拒绝类型"时**： <p>0：无<p>4：为此项禁用 **AuditDenied** 。 即使发生 **阻止** 且 AuditDenied 已配置设置，系统也不会显示通知。 <p>**选择" **AuditAllowed** 类型"时**： <p>0：无 <p>1：无 <p>2：发送事件<p>3：发送事件 <p> **选择"类型 **AuditDenied** "时**： <p>0：无 <p>1：显示通知 <p>2：发送事件<p>3：显示通知和发送事件 |
|AccessMask|定义访问权限。 | **磁盘级别访问**： <p>1：读取 <p>2：写入 <p>4：执行 <p>**文件系统级别访问**： <p>8：文件系统读取 <p>16：文件系统写入 <p>32：文件系统执行 <p><p>可以通过执行二进制 OR 操作获得多个访问权限，例如，用于读取和写入和执行的 AccessMask 将为 7;用于读取和写入的 AccessMask 将为 3。|

## <a name="common-removable-storage-access-control-scenarios"></a>常见可移动存储 访问控制方案

为了帮助你熟悉Microsoft Defender for Endpoint可移动存储 访问控制，我们已整理了一些常见方案供你关注。

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>方案 1：阻止对除允许特定批准的 USB 之外的所有用户进行写入和执行访问

1. 创建组

    1. 组 1：任何可移动存储和 CD/DVD。 可移动存储和 CD/DVD 的示例是：所有 [可移动存储和 CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件示例中的组 **9b28fae8-72f7-4267-a1a5-685f747a7146**。

    2. 组 2：基于设备属性的已批准 USB。 此用例的一个示例是：示例 [已批准 USB](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Group.xml文件中的实例 ID - 组 **65fa649a-a111-4912-9294-fb6337a25038**。

    > [!TIP]
    > 替换 `&` 为 `&amp;` 值中。

2. 创建策略

    1. 策略 1：阻止写入和执行访问，但允许批准的 USB。 此用例的示例是：示例方案 1 中的 PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** [阻止写入和执行访问，但允许批准的USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 文件。

    2. 策略 2：审核对允许的 USB 的写入和执行访问权限。 此用例的示例是：示例方案 1 中的 PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** [审核写入和执行对已批准USBs.xml文件的访问权限](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 。

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>方案 2：审核写入和执行对除阻止特定未批准的 USB 之外的所有访问权限

1. 创建组

    1. 组 1：任何可移动存储和 CD/DVD。 此用例的一个示例是：示例"[任意可移动存储和 CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 文件中的组 **9b28fae8-72f7-4267-a1a5-685f747a7146**。

    2. 组 2：基于设备属性（例如，供应商 ID/产品 ID、友好名称 - 组 **65fa649a-a111-4912-9294-fb6337a25038** ）的未经 [批准的 USB Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 文件。

    > [!TIP]
    > 替换 `&` 为 `&amp;` 值中。

2. 创建策略

    1. 策略 1：阻止对除阻止特定未批准的 USB 之外的所有 U 盘进行写入和执行访问。 此用例的一个示例是：示例方案 2 中的 PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** [审核写入和执行对除阻止特定未批准USBs.xml文件之外的所有访问权限](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 。

    2. 策略 2：审核写入和执行对他人的访问权限。 此用例的示例是：示例方案 2 中的 PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** [审核写入和执行others.xml文件的访问权限](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 。

## <a name="deploying-and-managing-policy-via-group-policy"></a>通过组策略部署和管理策略

可移动存储 访问控制功能使你可以通过组策略将策略应用到用户或设备，或者同时应用两者。

### <a name="licensing"></a>授权

在开始使用可移动存储 访问控制之前，必须确认[Microsoft 365订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。 若要访问和使用可移动存储 访问控制，必须具有Microsoft 365 E3或Microsoft 365 E5。

### <a name="deploying-policy-via-group-policy"></a>通过组策略部署策略

1. 将内`<Groups>``</Groups>`的所有组合并到一个 xml 文件中。

    下图演示了 [方案 1 的示例：阻止对除允许特定批准的 USB 之外的所有用户进行写入和执行访问](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)。

    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="在设备上允许特定批准的 USB 的配置设置" lightbox="images/prevent-write-access-allow-usb.png":::

2. 将内`<PolicyRules>``</PolicyRules>`的所有规则合并到一个 xml 文件中。

    如果要限制特定用户，请在条目中使用 SID 属性。 如果策略条目中没有 SID，则该条目将应用于计算机的所有人登录实例。

    若要监视文件信息以进行写入访问，请将正确的 AccessMask 与正确的选项 (16) ;下面是 [捕获文件信息](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Audit%20File%20Information.xml)的示例。

    下图演示了 SID 属性的使用情况，以及 [方案 1 的示例：阻止写入和执行对除允许特定批准的 USB 之外的所有用户的访问](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)。

    :::image type="content" source="images/usage-sid-property.png" alt-text="指示 SID 属性属性使用情况的代码" lightbox="images/usage-sid-property.png":::

3. 将规则和组 XML 文件保存在网络共享文件夹中，并将网络共享文件夹路径放入组策略设置：**计算机配置** \> **管理模板** \> **Windows组件** \> **Microsoft Defender 防病毒** \> **设备控制**："**定义设备控制策略组"** 和 **"定义设备控制策略规则"。**

   如果在组策略中找不到策略配置 UX，则可以通过选择 **"原始**"，然后 **另存为** 下载 [WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) 和 [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) 文件。

   - 目标计算机必须能够访问网络共享才能拥有策略。 但是，读取策略后，即使计算机重新启动，也不再需要网络共享连接。

    :::image type="content" source="images/device-control.png" alt-text="&quot;设备控制&quot;屏幕" lightbox="images/device-control.png":::

4. 默认强制：允许将默认访问 ("拒绝"或"允许) "设置为可移动媒体（如果没有策略）。 例如，只有针对 RemovableMediaDevices 的"拒绝"或"允许) "策略 (，但对于 CdRomDevices 或 WpdDevices 没有任何策略，并且通过此策略设置默认拒绝，将阻止对 CdRomDevices 或 WpdDevices 的读/写/执行访问。

   - 部署此设置后，将看到 **默认允许** 或 **默认拒绝**。
   - 配置此设置时，请考虑磁盘级别和文件系统级别 AccessMask，例如，如果想要默认拒绝但允许特定存储，则必须同时允许磁盘级别和文件系统级别访问，则必须将 AccessMask 设置为 63。

    :::image type="content" source="images/148609579-a7df650b-7792-4085-b552-500b28a35885.png" alt-text="默认允许或默认拒绝 PowerShell 代码":::

5. 启用或禁用可移动存储 访问控制：可以将此值设置为暂时禁用可移动存储 访问控制。

    :::image type="content" source="images/148608318-5cda043d-b996-4146-9642-14fccabcb017.png" alt-text="设备控制设置":::

   - 部署此设置后，将看到 **"已启用** "或" **已禁用**"。 禁用意味着此计算机没有运行可移动存储 访问控制策略。

    :::image type="content" source="images/148609685-4c05f002-5cbe-4aab-9245-83e730c5449e.png" alt-text="PowerShell 代码中启用或禁用的设备控制":::

6. 设置文件副本的位置：如果希望在进行写入访问时拥有该文件的副本，则必须设置系统可以保存该副本的位置。

    将此项与正确的 AccessMask 和选项一起部署 - 请参阅上面的步骤 2。

    :::image type="content" source="../../media/define-device-control-policy-rules.png" alt-text="组策略 - 为文件证据设置 locaiton":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>通过 Intune OMA-URI 部署和管理策略

可移动存储 访问控制功能使你能够通过 OMA-URI 将策略应用到用户或设备，或者同时应用两者。

### <a name="licensing-requirements"></a>许可要求

在开始使用可移动存储 访问控制之前，必须确认[Microsoft 365订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。 若要访问和使用可移动存储 访问控制，必须具有Microsoft 365 E3或Microsoft 365 E5。

### <a name="permission"></a>权限

对于Intune中的策略部署，帐户必须具有创建、编辑、更新或删除设备配置文件的权限。 可以创建自定义角色或使用具有这些权限的任何内置角色。

- 策略和配置文件管理器角色

- 启用了设备配置文件的"创建/编辑/更新/读取/删除/查看报表"权限的自定义角色

- 全局管理员

### <a name="deploying-policy-via-oma-uri"></a>通过 OMA-URI 部署策略

Microsoft Endpoint Manager管理中心 (<https://endpoint.microsoft.com/>) \> **设备** \> **配置文件****创建配置文件** \> \> **平台：Windows 10及更高版本&配置文件：自定义**

1. 对于每个组，创建 OMA-URI 规则：

    - OMA-URI： 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b**GroupGUID**%7d/GroupData`

      例如，对于示例中 **的任何可移动存储和 CD/DVD** 组，链接必须为：

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData`

    - 数据类型：字符串 (XML 文件) 

      :::image type="content" source="images/xml-data-type-string.png" alt-text="&quot;添加行&quot;页中的数据类型字段" lightbox="images/xml-data-type-string.png":::

2. 对于每个策略，还创建 OMA-URI：

    - OMA-URI： 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7b**PolicyRuleGUID**%7d/RuleData`

      例如，对于 **块写入和执行访问，但在示例中允许批准的 USB** 规则，链接必须是：

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData`

    - 数据类型：字符串 (XML 文件) 

    若要监视文件信息以进行写入访问，请将正确的 AccessMask 与正确的选项 (16) ;下面是 [捕获文件信息](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Audit%20File%20Information.xml)的示例。

3. 默认强制：允许将默认访问 ("拒绝"或"允许) "设置为可移动媒体（如果没有策略）。 例如，只有针对 RemovableMediaDevices 的"拒绝"或"允许) "策略 (，但对于 CdRomDevices 或 WpdDevices 没有任何策略，并且通过此策略设置默认拒绝，将阻止对 CdRomDevices 或 WpdDevices 的读/写/执行访问。

    - OMA-URI： `./Vendor/MSFT/Defender/Configuration/DefaultEnforcement`

    - 数据类型：Int

      `DefaultEnforcementAllow = 1`
      `DefaultEnforcementDeny = 2`

    - 部署此设置后，将看到 **默认允许** 或 **默认拒绝**
    - 配置此设置时，请考虑磁盘级别和文件系统级别 AccessMask，例如，如果想要默认拒绝但允许特定存储，则必须同时允许磁盘级别和文件系统级别访问，则必须将 AccessMask 设置为 63。

    :::image type="content" source="images/148609590-c67cfab8-8e2c-49f8-be2b-96444e9dfc2c.png" alt-text="默认强制允许 PowerShell 代码":::

4. 启用或禁用可移动存储 访问控制：可以将此值设置为暂时禁用可移动存储 访问控制。

   - OMA-URI： `./Vendor/MSFT/Defender/Configuration/DeviceControlEnabled`

   - 数据类型：Int `Disable: 0`
     `Enable: 1`

   - 部署此设置后，将看到 **"已启用**"或"**已禁用**"

    **禁用** 意味着此计算机未运行可移动存储 访问控制策略

    :::image type="content" source="images/148609770-3e555883-f26f-45ab-9181-3fb1ff7a38ac.png" alt-text="PowerShell 代码中的可删除存储 访问控制":::

5. 设置文件副本的位置：如果希望在发生写入访问时拥有该文件的副本，则必须设置系统可以保存该副本的位置。

    - OMA-URI： `./Vendor/MSFT/Defender/Configuration/DataDuplicationRemoteLocation;**username**;**password**`

    - 数据类型：String

    必须将此选项与正确的 AccessMask 和正确的选项一起部署 - 请参阅上面的步骤 2。

    :::image type="content" source="../../media/device-control-oma-uri-edit-row.png" alt-text="为文件证据设置 locaiton":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>使用Intune用户界面部署和管理策略

 (*即将推出！*) 此功能将在Microsoft Endpoint Manager管理中心 () <https://endpoint.microsoft.com/> 中提供。 转到 **Endpoint SecurityAttack** >  **Surface** **ReductionCreate** >  策略。 选择 **平台：使用配置文件Windows 10及更高版本****：设备控件**。

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>在Microsoft Defender for Endpoint中查看设备控件可移动存储 访问控制数据

[Microsoft 365 Defender门户](https://security.microsoft.com/advanced-hunting)显示设备控件可移动存储 访问控制触发的事件。 若要访问Microsoft 365安全性，必须具有以下订阅：

- 用于 E5 报告的Microsoft 365

```kusto
//RemovableStoragePolicyTriggered: event triggered by Disk level enforcement
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

```kusto
//information of file written to removable storage 
DeviceEvents
| where ActionType contains "RemovableStorageFileEvent"
| extend parsed=parse_json(AdditionalFields)
| extend Policy = tostring(parsed.Policy) 
| extend PolicyRuleId = tostring(parsed.PolicyRuleId) 
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaInstanceId = tostring(parsed.InstanceId)
| extend MediaName = tostring(parsed.MediaName)
| extend MediaProductId = tostring(parsed.ProductId) 
| extend MediaVendorId = tostring(parsed.VendorId) 
| extend MediaSerialNumber = tostring(parsed.SerialNumber) 
| extend FileInformationOperation = tostring(parsed.DuplicatedOperation)
| extend FileEvidenceLocation = tostring(parsed.TargetFileLocation) 
| project Timestamp, DeviceId, DeviceName, InitiatingProcessAccountName, ActionType, Policy, PolicyRuleId, FileInformationOperation, MediaClassName, MediaInstanceId, MediaName, MediaProductId, MediaVendorId, MediaSerialNumber, FileName, FolderPath, FileSize, FileEvidenceLocation, AdditionalFields
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="描述可移动存储的阻塞的屏幕。":::

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="how-to-generate-guid-for-group-idpolicyrule-identry-id"></a>如何为组 ID/PolicyRule ID/条目 ID 生成 GUID？

可以通过联机开放源代码或 PowerShell 生成 [GUID - 如何通过 PowerShell 生成 GUID](/powershell/module/microsoft.powershell.utility/new-guid)

![image](https://user-images.githubusercontent.com/81826151/159046476-26ea0a21-8087-4f01-b8ae-5aa73b392d8f.png)

### <a name="what-is-the-removable-storage-media-limitation-for-the-maximum-number-of-usbs"></a>最大 USB 数的可移动存储介质限制是什么？

我们已使用 100，000 个媒体验证了一个 USB 组，其大小高达 7 MB。 该策略在Intune和 GPO 中均有效，不会出现性能问题。

### <a name="why-does-the-policy-not-work"></a>为什么策略不起作用？

1. 最常见的原因是没有必需 [的反恶意软件客户端版本](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)。

2. 另一个原因可能是 XML 文件格式不正确，例如，未对 XML 文件中的"&"字符使用正确的 markdown 格式，或者文本编辑器可能会在文件开头 (BOM) 0xEF 0xBB 0xBF添加字节顺序标记，从而导致 XML 分析不起作用。 一个简单的解决方案是下载 [示例文件](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (选择 **"原始** "，然后 **另存为**) ，然后更新。

3. 如果要通过组策略部署和管理策略，请确保将所有 PolicyRule 合并到名为 PolicyRules 的父节点中的一个 XML 文件中，并将所有组合并到名为"组"的父节点内的一个 XML 文件中;如果通过Intune进行管理，请保留一个 PolicyRule 一个 XML 文件，同样，一个组一个 XML 文件。

如果仍然不起作用，你可能想要通过与管理员运行 cmd 来联系我们并共享支持 cab："%programfiles%\Windows Defender\MpCmdRun.exe" -GetFiles

### <a name="there-is-no-configuration-ux-for-define-device-control-policy-groups-and-define-device-control-policy-rules-on-my-group-policy"></a>我的组策略上没有用于"定义设备控制策略组"和"定义设备控制策略规则"的配置 UX

我们不支持组策略配置 UX，但你仍可以通过单击 [WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) 和 [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) 文件中的"Raw"和"Save as"来获取相关的 adml 和 admx 文件。

### <a name="how-can-i-know-whether-the-latest-policy-has-been-deployed-to-the-target-machine"></a>如何知道最新策略是否已部署到目标计算机？

可以以管理员身份在 PowerShell 上运行"Get-MpComputerStatus"。 以下值将显示是否已将最新策略应用到目标计算机。

:::image type="icon" source="images/148609885-bea388a9-c07d-47ef-b848-999d794d24b8.png" border="false":::

### <a name="how-can-i-know-which-machine-is-using-out-of-date-antimalware-client-version-in-the-organization"></a>如何知道哪个计算机在组织中使用过时的反恶意软件客户端版本？

可以在Microsoft 365安全门户上使用以下查询获取反恶意软件客户端版本：

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
