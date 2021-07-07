---
title: Microsoft Defender for Endpoint 设备控件可移动存储访问控制
description: 有关 Microsoft Defender for Endpoint 的演练
keywords: 可移动存储媒体
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0b0f7c5a4a75fdc80509dbc02a43d28f7c93fd7c
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327043"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="0ddbe-104">Microsoft Defender for Endpoint 设备控件可移动存储访问控制</span><span class="sxs-lookup"><span data-stu-id="0ddbe-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="0ddbe-105">Microsoft Defender for Endpoint 设备控制可移动存储访问控制使你能够执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="0ddbe-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>

- <span data-ttu-id="0ddbe-106">审核，允许或阻止对可移动存储进行读取、写入或执行访问（带排除或不排除）</span><span class="sxs-lookup"><span data-stu-id="0ddbe-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="0ddbe-107">Privilege</span><span class="sxs-lookup"><span data-stu-id="0ddbe-107">Privilege</span></span> |<span data-ttu-id="0ddbe-108">权限</span><span class="sxs-lookup"><span data-stu-id="0ddbe-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="0ddbe-109">Access</span><span class="sxs-lookup"><span data-stu-id="0ddbe-109">Access</span></span>    |  <span data-ttu-id="0ddbe-110">读取、写入、执行</span><span class="sxs-lookup"><span data-stu-id="0ddbe-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="0ddbe-111">操作模式</span><span class="sxs-lookup"><span data-stu-id="0ddbe-111">Action Mode</span></span>    |    <span data-ttu-id="0ddbe-112">审核、允许、阻止</span><span class="sxs-lookup"><span data-stu-id="0ddbe-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="0ddbe-113">云解决方案提供商支持</span><span class="sxs-lookup"><span data-stu-id="0ddbe-113">CSP Support</span></span>   |   <span data-ttu-id="0ddbe-114">是</span><span class="sxs-lookup"><span data-stu-id="0ddbe-114">Yes</span></span>      |
|<span data-ttu-id="0ddbe-115">GPO 支持</span><span class="sxs-lookup"><span data-stu-id="0ddbe-115">GPO Support</span></span>    |   <span data-ttu-id="0ddbe-116">是</span><span class="sxs-lookup"><span data-stu-id="0ddbe-116">Yes</span></span>      |
|<span data-ttu-id="0ddbe-117">基于用户的支持</span><span class="sxs-lookup"><span data-stu-id="0ddbe-117">User-based Support</span></span>     |   <span data-ttu-id="0ddbe-118">是</span><span class="sxs-lookup"><span data-stu-id="0ddbe-118">Yes</span></span>      |
|<span data-ttu-id="0ddbe-119">基于计算机的支持</span><span class="sxs-lookup"><span data-stu-id="0ddbe-119">Machine-based Support</span></span>    |    <span data-ttu-id="0ddbe-120">是</span><span class="sxs-lookup"><span data-stu-id="0ddbe-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="0ddbe-121">准备终结点</span><span class="sxs-lookup"><span data-stu-id="0ddbe-121">Prepare your endpoints</span></span>

<span data-ttu-id="0ddbe-122">在存储 **4.18.2103.3** 或更高版本的 Windows 10 设备上部署可移动访问控制。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-122">Deploy Removable Storage Access Control on Windows 10 devices that have antimalware client version **4.18.2103.3 or later**.</span></span>

- <span data-ttu-id="0ddbe-123">**4.18.2104 或更高版本**：添加 SerialNumberId、VID_PID、基于 filepath 的 GPO 支持、ComputerSid</span><span class="sxs-lookup"><span data-stu-id="0ddbe-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span></span>

- <span data-ttu-id="0ddbe-124">**4.18.2105** 或更高版本：添加对 HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId 的通配符支持、特定计算机上特定用户的组合、可删除的 SSD (SanDisk 极性 SSD) /USB 附加 SCSI (UAS) 支持</span><span class="sxs-lookup"><span data-stu-id="0ddbe-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

- <span data-ttu-id="0ddbe-125">**4.18.2107 或** 更高版本：添加 Windows 可移植设备 (WPD) 支持 (移动设备（如平板电脑或) </span><span class="sxs-lookup"><span data-stu-id="0ddbe-125">**4.18.2107 or later**: Add Windows Portable Device (WPD) support (for mobile devices, such as tablets)</span></span>

:::image type="content" source="images/powershell.png" alt-text="PowerShell 接口":::

> [!NOTE]
> <span data-ttu-id="0ddbe-127">任何Windows 安全中心组件都不需要处于活动状态，您可以运行"可移动存储访问控制"，而不受Windows 安全中心状态。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-127">None of Windows Security components need to be active, you can run Removable Storage Access Control independent of Windows Security status.</span></span>

## <a name="policy-properties"></a><span data-ttu-id="0ddbe-128">策略属性</span><span class="sxs-lookup"><span data-stu-id="0ddbe-128">Policy properties</span></span>

<span data-ttu-id="0ddbe-129">可以使用以下属性创建可移动存储组：</span><span class="sxs-lookup"><span data-stu-id="0ddbe-129">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="0ddbe-130">**属性名称：组 ID**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-130">**Property name: Group Id**</span></span>

1. <span data-ttu-id="0ddbe-131">说明 [：GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)是一个唯一 ID，表示组，将在策略中使用。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-131">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="0ddbe-132">**属性名称：DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-132">**Property name: DescriptorIdList**</span></span>

2. <span data-ttu-id="0ddbe-133">说明：列出你想要在组中覆盖的设备属性。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-133">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="0ddbe-134">有关每个设备属性的详细信息， **请参阅上面的设备** 属性部分。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-134">For each device property, see **Device Properties** section above for more detail.</span></span>

3. <span data-ttu-id="0ddbe-135">选项：</span><span class="sxs-lookup"><span data-stu-id="0ddbe-135">Options:</span></span>
    - <span data-ttu-id="0ddbe-136">PrimaryId</span><span class="sxs-lookup"><span data-stu-id="0ddbe-136">PrimaryId</span></span>
        - <span data-ttu-id="0ddbe-137">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="0ddbe-137">RemovableMediaDevices</span></span>
        - <span data-ttu-id="0ddbe-138">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="0ddbe-138">CdRomDevices</span></span>
        - <span data-ttu-id="0ddbe-139">WpdDevices</span><span class="sxs-lookup"><span data-stu-id="0ddbe-139">WpdDevices</span></span>
    - <span data-ttu-id="0ddbe-140">DeviceId</span><span class="sxs-lookup"><span data-stu-id="0ddbe-140">DeviceId</span></span>
    - <span data-ttu-id="0ddbe-141">HardwareId</span><span class="sxs-lookup"><span data-stu-id="0ddbe-141">HardwareId</span></span>
    - <span data-ttu-id="0ddbe-142">InstancePathId：InstancePathId 是一个唯一标识系统中设备的字符串，例如 USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-142">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="0ddbe-143">末尾的号码 (例如 0&**0**) 表示可用插槽，并且可能会从设备更改为设备。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-143">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="0ddbe-144">为获得最佳结果，请结尾使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-144">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="0ddbe-145">例如，USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="0ddbe-145">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="0ddbe-146">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="0ddbe-146">FriendlyNameId</span></span>
    - <span data-ttu-id="0ddbe-147">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="0ddbe-147">SerialNumberId</span></span>
    - <span data-ttu-id="0ddbe-148">VID</span><span class="sxs-lookup"><span data-stu-id="0ddbe-148">VID</span></span>
    - <span data-ttu-id="0ddbe-149">PID</span><span class="sxs-lookup"><span data-stu-id="0ddbe-149">PID</span></span>
    - <span data-ttu-id="0ddbe-150">VID_PID</span><span class="sxs-lookup"><span data-stu-id="0ddbe-150">VID_PID</span></span>
        - <span data-ttu-id="0ddbe-151">0751_55E0：匹配此精确的 VID/PID 对</span><span class="sxs-lookup"><span data-stu-id="0ddbe-151">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="0ddbe-152">_55E0：将任何媒体与 PID=55E0 匹配</span><span class="sxs-lookup"><span data-stu-id="0ddbe-152">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="0ddbe-153">0751_：将任何媒体与 VID=0751 匹配</span><span class="sxs-lookup"><span data-stu-id="0ddbe-153">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="0ddbe-154">**属性名称：MatchType**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-154">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="0ddbe-155">说明：当 DescriptorIDList 中使用多个设备属性时，MatchType 定义关系。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-155">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

2. <span data-ttu-id="0ddbe-156">选项：</span><span class="sxs-lookup"><span data-stu-id="0ddbe-156">Options:</span></span>

    - <span data-ttu-id="0ddbe-157">MatchAll：DescriptorIdList 下的任何属性将为 **And** 关系;例如，如果管理员将 DeviceID 和 InstancePathID 放在每个连接的 USB 上，系统将检查 USB 是否同时满足这两个值。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-157">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>
    - <span data-ttu-id="0ddbe-158">MatchAny：DescriptorIdList 下的属性将为 **Or** 关系;例如，如果管理员将 DeviceID 和 InstancePathID 放在每个连接的 USB 上，只要 USB 具有相同的 **DeviceID** 或 **InstanceID** 值，系统就会执行强制操作。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-158">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="0ddbe-159">以下是访问控制策略属性：</span><span class="sxs-lookup"><span data-stu-id="0ddbe-159">Following are the access control policy properties:</span></span>

<span data-ttu-id="0ddbe-160">**属性名称：PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-160">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="0ddbe-161">说明 [：GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)是一个唯一 ID，表示策略，将用于报告和疑难解答。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-161">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="0ddbe-162">**属性名称：IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-162">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="0ddbe-163">说明： (策略) 的组。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-163">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="0ddbe-164">如果添加了多个组，该策略将应用于所有这些组的任何媒体。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-164">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

2. <span data-ttu-id="0ddbe-165">选项：必须在此实例使用组 ID/GUID。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-165">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="0ddbe-166">以下示例显示 GroupID 的用法：</span><span class="sxs-lookup"><span data-stu-id="0ddbe-166">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="0ddbe-167">**属性名称：ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-167">**Property name: ExcludedIDList**</span></span>

<span data-ttu-id="0ddbe-168">说明： (策略) 的组。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-168">Description: The group(s) that the policy will not be applied to.</span></span>

<span data-ttu-id="0ddbe-169">选项：必须在此实例使用组 ID/GUID。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-169">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="0ddbe-170">**属性名称：条目 ID**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-170">**Property name: Entry Id**</span></span>

1. <span data-ttu-id="0ddbe-171">说明：一个 PolicyRule 可以有多个条目;每个具有唯一 GUID 的条目告知设备控件一个限制。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-171">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="0ddbe-172">**属性名称：Type**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-172">**Property name: Type**</span></span>

1. <span data-ttu-id="0ddbe-173">说明：定义 IncludedIDList 中可移动存储组的操作。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-173">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="0ddbe-174">强制：允许或拒绝</span><span class="sxs-lookup"><span data-stu-id="0ddbe-174">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="0ddbe-175">审核：AuditAllowed 或 AuditDenied</span><span class="sxs-lookup"><span data-stu-id="0ddbe-175">Audit: AuditAllowed or AuditDenied</span></span> 

2. <span data-ttu-id="0ddbe-176">选项：</span><span class="sxs-lookup"><span data-stu-id="0ddbe-176">Options:</span></span>

    - <span data-ttu-id="0ddbe-177">允许</span><span class="sxs-lookup"><span data-stu-id="0ddbe-177">Allow</span></span>
    - <span data-ttu-id="0ddbe-178">拒绝</span><span class="sxs-lookup"><span data-stu-id="0ddbe-178">Deny</span></span>
    - <span data-ttu-id="0ddbe-179">AuditAllowed：定义允许访问时的通知和事件</span><span class="sxs-lookup"><span data-stu-id="0ddbe-179">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="0ddbe-180">AuditDenied：定义拒绝访问时的通知和事件;必须配合拒绝 **条目** 一起工作。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-180">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="0ddbe-181">当同一媒体存在冲突类型时，系统将应用策略中的第一个冲突类型。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-181">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="0ddbe-182">冲突类型的一个示例是 **"允许"和**"**拒绝"。**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-182">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="0ddbe-183">**属性名称：Sid**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-183">**Property name: Sid**</span></span>

<span data-ttu-id="0ddbe-184">说明：本地计算机 Sid 或 AD 对象的 Sid 定义是否对特定用户或用户组应用此策略;一个条目最多可具有一个 Sid 和一个不带任何 Sid 的条目，这意味着在计算机中应用策略。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-184">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific user or user group; one entry can have a maximum of one Sid and an entry without any Sid means applying the policy over the machine.</span></span>

<span data-ttu-id="0ddbe-185">**属性名称：ComputerSid**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-185">**Property name: ComputerSid**</span></span>

<span data-ttu-id="0ddbe-186">说明：本地计算机 Sid 或 AD 对象的 Sid 定义是否对特定计算机或计算机组应用此策略;一个条目最多可具有一个 ComputerSid，而一个条目没有任何 ComputerSid 意味着将策略应用到计算机。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-186">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific machine or machine group; one entry can have a maximum of one ComputerSid and an entry without any ComputerSid means applying the policy over the machine.</span></span> <span data-ttu-id="0ddbe-187">如果要将条目应用于特定用户和特定计算机，请同时将 Sid 和 ComputerSid 添加到同一条目中。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-187">If you want to apply an Entry to a specific user and specific machine, add both Sid and ComputerSid into the same Entry.</span></span>

<span data-ttu-id="0ddbe-188">**属性名称：Options**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-188">**Property name: Options**</span></span>

<span data-ttu-id="0ddbe-189">说明：定义是否显示通知。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-189">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="可在其中查看设备状态的屏幕":::

<span data-ttu-id="0ddbe-191">选项：0-4。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-191">Options: 0-4.</span></span> <span data-ttu-id="0ddbe-192">选择"类型允许"或"拒绝"时：</span><span class="sxs-lookup"><span data-stu-id="0ddbe-192">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="0ddbe-193">0：无</span><span class="sxs-lookup"><span data-stu-id="0ddbe-193">0: nothing</span></span>
   - <span data-ttu-id="0ddbe-194">4：对此条目 **禁用 AuditAllowed** **和 AuditDenied。**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-194">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="0ddbe-195">即使 **发生阻止** 且已配置 **AuditDenied** 设置，系统也将不会显示通知。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-195">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="0ddbe-196">选择" **类型 AuditAllowed"** 或 **"AuditDenied"** 时：</span><span class="sxs-lookup"><span data-stu-id="0ddbe-196">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="0ddbe-197">0：无</span><span class="sxs-lookup"><span data-stu-id="0ddbe-197">0: nothing</span></span>
   - <span data-ttu-id="0ddbe-198">1：显示通知</span><span class="sxs-lookup"><span data-stu-id="0ddbe-198">1: show notification</span></span>
   - <span data-ttu-id="0ddbe-199">2：发送事件</span><span class="sxs-lookup"><span data-stu-id="0ddbe-199">2: send event</span></span>
   - <span data-ttu-id="0ddbe-200">3：显示通知和发送事件</span><span class="sxs-lookup"><span data-stu-id="0ddbe-200">3: show notification and send event</span></span>

<span data-ttu-id="0ddbe-201">**属性名称：AccessMask**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-201">**Property name: AccessMask**</span></span>

<span data-ttu-id="0ddbe-202">说明：定义访问权限。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-202">Description: Defines the access.</span></span>

<span data-ttu-id="0ddbe-203">选项 1-7：</span><span class="sxs-lookup"><span data-stu-id="0ddbe-203">Options 1-7:</span></span>
  - <span data-ttu-id="0ddbe-204">1：读取</span><span class="sxs-lookup"><span data-stu-id="0ddbe-204">1: Read</span></span>
  - <span data-ttu-id="0ddbe-205">2：写入</span><span class="sxs-lookup"><span data-stu-id="0ddbe-205">2: Write</span></span>
  - <span data-ttu-id="0ddbe-206">3：读取和写入</span><span class="sxs-lookup"><span data-stu-id="0ddbe-206">3: Read and Write</span></span>
  - <span data-ttu-id="0ddbe-207">4：执行</span><span class="sxs-lookup"><span data-stu-id="0ddbe-207">4: Execute</span></span>
  - <span data-ttu-id="0ddbe-208">5：读取和执行</span><span class="sxs-lookup"><span data-stu-id="0ddbe-208">5: Read and Execute</span></span>
  - <span data-ttu-id="0ddbe-209">6：写入和执行</span><span class="sxs-lookup"><span data-stu-id="0ddbe-209">6: Write and Execute</span></span>
  - <span data-ttu-id="0ddbe-210">7：读取、写入和执行</span><span class="sxs-lookup"><span data-stu-id="0ddbe-210">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="0ddbe-211">常见的可移动存储访问控制方案</span><span class="sxs-lookup"><span data-stu-id="0ddbe-211">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="0ddbe-212">为了帮助你熟悉 Microsoft Defender for Endpoint Removable 存储访问控制，我们将一些常见方案放在一起供你遵循。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-212">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="0ddbe-213">方案 1：阻止对全部 USB 执行写入和执行访问，但允许特定批准的 USB</span><span class="sxs-lookup"><span data-stu-id="0ddbe-213">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="0ddbe-214">创建组</span><span class="sxs-lookup"><span data-stu-id="0ddbe-214">Create groups</span></span>

    1. <span data-ttu-id="0ddbe-215">组 1：任何可移动存储和 CD/DVD。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-215">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="0ddbe-216">可移动存储和 CD/DVD 的一个示例是：示例 Any [Removable 存储 and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file中的组 **9b28fae8-72f7-4267-a1a5-685f747a7146。**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-216">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="0ddbe-217">组 2：基于设备属性批准的 USB。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-217">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="0ddbe-218">此用例的一个示例是：示例已批准 [USB Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件中的实例 ID – 组 **65fa649a-a111-4912-9294-fb6337a25038。**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-218">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0ddbe-219">您必须在 值 `&` 中 `&amp;` 将 替换为 。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-219">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="0ddbe-220">创建策略</span><span class="sxs-lookup"><span data-stu-id="0ddbe-220">Create policy</span></span>

    1. <span data-ttu-id="0ddbe-221">策略 1：阻止写入和执行访问，但允许批准的 USB。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-221">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="0ddbe-222">此用例的一个示例是：示例方案 [1](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)阻止写入和执行访问但允许批准的 USBs.xml文件中的 PolicyRule **c544a991-5786-4402-949e-a032cb790d0e。**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-222">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="0ddbe-223">策略 2：审核对允许的 USB 的写入和执行访问权限。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-223">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="0ddbe-224">此用例的一个示例是：对批准的 [USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件进行审核写入和执行访问示例中的 PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c。**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-224">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="0ddbe-225">方案 2：审核对全部（但阻止特定未批准的 USB）的写入和执行访问权限</span><span class="sxs-lookup"><span data-stu-id="0ddbe-225">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="0ddbe-226">创建组</span><span class="sxs-lookup"><span data-stu-id="0ddbe-226">Create groups</span></span>

    1. <span data-ttu-id="0ddbe-227">组 1：任何可移动存储和 CD/DVD。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-227">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="0ddbe-228">此用例的一个示例是：示例 Any [Removable 存储 and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file中的 Group **9b28fae8-72f7-4267-a1a5-685f747a7146。**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-228">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="0ddbe-229">组 2：基于设备属性（例如，供应商 ID/产品 ID、友好名称 – 组 **65fa649a-a111-4912-9294-fb6337a25038）** 的未批准 USB Group.xml文件中未批准的 [USB。](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="0ddbe-229">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="0ddbe-230">您必须在 值 `&` 中 `&amp;` 将 替换为 。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-230">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="0ddbe-231">创建策略</span><span class="sxs-lookup"><span data-stu-id="0ddbe-231">Create policy</span></span>

    1. <span data-ttu-id="0ddbe-232">策略 1：阻止对全部（但阻止特定未批准的 USB）的写入和执行访问。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-232">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="0ddbe-233">此用例的一个示例是：示例方案 2 审核写入和执行对除阻止特定未批准的 [USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件的访问中的 PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98。**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-233">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="0ddbe-234">策略 2：审核写入和执行对他人的访问。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-234">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="0ddbe-235">此用例的一个示例是：对 [others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件进行审核写入和执行访问示例中的 PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48。**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-235">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="0ddbe-236">通过组策略部署和管理策略</span><span class="sxs-lookup"><span data-stu-id="0ddbe-236">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="0ddbe-237">通过"存储访问控制"功能，可以通过组策略将策略应用于用户或设备，或同时应用于两者。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-237">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="0ddbe-238">许可</span><span class="sxs-lookup"><span data-stu-id="0ddbe-238">Licensing</span></span>

<span data-ttu-id="0ddbe-239">在开始使用"可移动存储访问控制"之前，必须确认Microsoft 365 [订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-239">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="0ddbe-240">若要访问和使用可移动存储访问控制，您必须具有Microsoft 365 E3或Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-240">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="0ddbe-241">通过组策略部署策略</span><span class="sxs-lookup"><span data-stu-id="0ddbe-241">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="0ddbe-242">将所有组组合到 `<Groups>` `</Groups>` 一个 xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-242">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="0ddbe-243">下图演示了方案 [1：](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)阻止对全部 USB 进行写入和执行访问，但允许特定批准的 USB 的示例。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-243">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="显示允许在设备上允许特定批准的 USB 的配置设置的屏幕":::
    
2. <span data-ttu-id="0ddbe-245">将所有规则合并到 `<PolicyRules>` `</PolicyRules>` 一个 xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-245">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="0ddbe-246">如果要限制特定用户，请使用 Entry 中的 SID 属性。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-246">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="0ddbe-247">如果策略条目中没有任何 SID，则条目将应用于计算机的每一个登录实例。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-247">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="0ddbe-248">下图演示了 SID 属性的用法，以及方案 [1：](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)阻止对全部但允许特定批准的 USB 的写入和执行访问的示例。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-248">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="显示指示 SID 属性属性使用情况的代码的屏幕":::

3. <span data-ttu-id="0ddbe-250">在网络共享文件夹中保存规则和组 XML 文件，将网络共享文件夹路径放入组策略设置：**计算机配置 -> 管理模板 -> Windows 组件 -> Microsoft Defender 防病毒 -> 设备控制："定义设备** 控制策略组"和"定义设备控制策略规则"。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-250">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="0ddbe-251">目标计算机必须能够访问网络共享才能拥有策略。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-251">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="0ddbe-252">但是，读取策略后，不再需要网络连接，即使在计算机重新启动后也不例外。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-252">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="设备控制屏幕":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="0ddbe-254">通过 Intune OMA-URI 部署和管理策略</span><span class="sxs-lookup"><span data-stu-id="0ddbe-254">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="0ddbe-255">通过可移动存储访问控制功能，你可以将策略通过 OMA-URI 应用到用户或设备，或同时应用到两者。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-255">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="0ddbe-256">许可</span><span class="sxs-lookup"><span data-stu-id="0ddbe-256">Licensing</span></span>

<span data-ttu-id="0ddbe-257">在开始使用"可移动存储访问控制"之前，必须确认Microsoft 365 [订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-257">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="0ddbe-258">若要访问和使用可移动存储访问控制，您必须具有Microsoft 365 E3或Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-258">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="0ddbe-259">权限</span><span class="sxs-lookup"><span data-stu-id="0ddbe-259">Permission</span></span>

<span data-ttu-id="0ddbe-260">对于 Intune 中的策略部署，该帐户必须具有创建、编辑、更新或删除设备配置文件的权限。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-260">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="0ddbe-261">可以创建自定义角色或使用具有这些权限的任何内置角色。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-261">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="0ddbe-262">策略和配置文件管理器角色</span><span class="sxs-lookup"><span data-stu-id="0ddbe-262">Policy and profile Manager role</span></span>
- <span data-ttu-id="0ddbe-263">为设备配置文件启用"创建/编辑/更新/读取/删除/查看报告"权限的自定义角色</span><span class="sxs-lookup"><span data-stu-id="0ddbe-263">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="0ddbe-264">全局管理员</span><span class="sxs-lookup"><span data-stu-id="0ddbe-264">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="0ddbe-265">通过 OMA-URI 部署策略</span><span class="sxs-lookup"><span data-stu-id="0ddbe-265">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="0ddbe-266">**Microsoft Endpoint Manager管理中心 (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform： Windows 10 and later & Profile： Custom**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-266">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="0ddbe-267">对于每个组，创建 OMA-URI 规则：</span><span class="sxs-lookup"><span data-stu-id="0ddbe-267">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="0ddbe-268">OMA-URI： </span><span class="sxs-lookup"><span data-stu-id="0ddbe-268">OMA-URI:</span></span>

      <span data-ttu-id="0ddbe-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="0ddbe-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="0ddbe-270">例如，对于 **示例中的任何可移动存储和 CD/DVD** 组，该链接必须为：</span><span class="sxs-lookup"><span data-stu-id="0ddbe-270">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="0ddbe-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="0ddbe-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="0ddbe-272">数据类型：String (XML 文件) </span><span class="sxs-lookup"><span data-stu-id="0ddbe-272">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="STRING 文件的 xml 数据类型":::

2. <span data-ttu-id="0ddbe-274">对于每个策略，还要创建 OMA-URI：</span><span class="sxs-lookup"><span data-stu-id="0ddbe-274">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="0ddbe-275">OMA-URI： </span><span class="sxs-lookup"><span data-stu-id="0ddbe-275">OMA-URI:</span></span>

      <span data-ttu-id="0ddbe-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="0ddbe-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="0ddbe-277">例如，对于示例中 **的"阻止写入和执行访问但允许批准的 USB"** 规则，该链接必须是：</span><span class="sxs-lookup"><span data-stu-id="0ddbe-277">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="0ddbe-278">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-278">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="0ddbe-279">数据类型：String (XML 文件) </span><span class="sxs-lookup"><span data-stu-id="0ddbe-279">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="STRING 文件的 XML 文件的数据类型":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="0ddbe-281">使用 Intune 用户界面部署和管理策略</span><span class="sxs-lookup"><span data-stu-id="0ddbe-281">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="0ddbe-282">此功能 (Microsoft Endpoint Manager 管理中心 (> 设备 > 配置文件 > 创建配置文件 https://endpoint.microsoft.com/) > 平台：Windows 10 及更高版本 & 配置文件：设备控制) 尚不可用。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-282">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="0ddbe-283">在 Microsoft Defender for Endpoint 存储设备控件可移动访问控件数据</span><span class="sxs-lookup"><span data-stu-id="0ddbe-283">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="0ddbe-284">安全Microsoft 365门户显示受设备控件可移动控件和访问控制存储的可移动存储。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-284">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="0ddbe-285">若要访问Microsoft 365安全性，您必须具有以下订阅：</span><span class="sxs-lookup"><span data-stu-id="0ddbe-285">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="0ddbe-286">Microsoft 365 E5 报告</span><span class="sxs-lookup"><span data-stu-id="0ddbe-286">Microsoft 365 for E5 reporting</span></span>

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="描述可移动存储被阻止的屏幕":::

## <a name="frequently-asked-questions"></a><span data-ttu-id="0ddbe-288">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="0ddbe-288">Frequently asked questions</span></span>

<span data-ttu-id="0ddbe-289">**最大 USB 数量的可移动存储媒体限制是什么？**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-289">**What is the removable storage media limitation for the maximum number of USBs?**</span></span>

<span data-ttu-id="0ddbe-290">我们已验证一个具有 100，000 个媒体的 USB 组 - 大小最高为 7 MB。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-290">We have validated one USB group with 100,000 media - up to 7 MB in size.</span></span> <span data-ttu-id="0ddbe-291">该策略在 Intune 和 GPO 中均有效，而未发生性能问题。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-291">The policy works in both Intune and GPO without performance issues.</span></span>

<span data-ttu-id="0ddbe-292">**为什么策略不起作用？**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-292">**Why does the policy not work?**</span></span>

<span data-ttu-id="0ddbe-293">最常见的原因是不需要反 [恶意软件客户端版本](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-293">The most common reason is there is no required [antimalware client version](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints).</span></span>

<span data-ttu-id="0ddbe-294">另一个原因是 XML 文件格式不正确，例如，未对 XML 文件中"&"字符使用正确的 markdown 格式，或者文本编辑器可能在文件的开头添加字节顺序标记 (BOM) 0xEF 0xBB 0xBF，这会导致 XML 分析不起作用。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-294">Another reason could be that the XML file is not correctly formatted, for example, not using the correct markdown formatting for the "&" character in the XML file, or the text editor might add a byte order mark (BOM) 0xEF 0xBB 0xBF at the beginning of the files which causes the XML parsing not to work.</span></span> <span data-ttu-id="0ddbe-295">一个简单的解决方案是下载示例文件 [， ("](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)**原始**"，**然后选择"另** 存为) 然后更新。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-295">One simple solution is to download the [sample file](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (select **Raw** and then **Save as**) and then update.</span></span>

<span data-ttu-id="0ddbe-296">如果有值并且策略通过组策略进行管理，请检查客户端设备是否可以访问策略 XML 路径。</span><span class="sxs-lookup"><span data-stu-id="0ddbe-296">If there is a value and the policy is managed via Group Policy, check whether the client device can access the policy XML path.</span></span>

<span data-ttu-id="0ddbe-297">**如何知道哪个计算机正在使用组织中过期的反恶意软件客户端版本？**</span><span class="sxs-lookup"><span data-stu-id="0ddbe-297">**How can I know which machine is using out of date antimalware client version in the organization?**</span></span>

<span data-ttu-id="0ddbe-298">可以使用以下查询在安全门户上获取反恶意软件Microsoft 365版本：</span><span class="sxs-lookup"><span data-stu-id="0ddbe-298">You can use following query to get antimalware client version on the Microsoft 365 security portal:</span></span>
```kusto
//check the antimalware client version
DeviceFileEvents
| where FileName == "MsMpEng.exe"
| where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
| extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//| project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
| summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
| order by PlatformVersion desc
```
