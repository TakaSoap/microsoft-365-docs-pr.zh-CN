---
title: Microsoft Defender for Endpoint 设备控件可移动存储空间访问控制
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
ms.openlocfilehash: cb23987600a5f87a99449510f7651c4fdcd45f66
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028399"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="0be75-104">Microsoft Defender for Endpoint 设备控件可移动存储空间访问控制</span><span class="sxs-lookup"><span data-stu-id="0be75-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="0be75-105">Microsoft Defender for Endpoint 设备控制可移动存储空间访问控制使你能够执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="0be75-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="0be75-106">审核，允许或阻止对可移动存储进行读取、写入或执行访问（带排除或不排除）</span><span class="sxs-lookup"><span data-stu-id="0be75-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="0be75-107">Privilege</span><span class="sxs-lookup"><span data-stu-id="0be75-107">Privilege</span></span> |<span data-ttu-id="0be75-108">权限</span><span class="sxs-lookup"><span data-stu-id="0be75-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="0be75-109">Access</span><span class="sxs-lookup"><span data-stu-id="0be75-109">Access</span></span>    |  <span data-ttu-id="0be75-110">读取、写入、执行</span><span class="sxs-lookup"><span data-stu-id="0be75-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="0be75-111">操作模式</span><span class="sxs-lookup"><span data-stu-id="0be75-111">Action Mode</span></span>    |    <span data-ttu-id="0be75-112">审核、允许、阻止</span><span class="sxs-lookup"><span data-stu-id="0be75-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="0be75-113">云解决方案提供商支持</span><span class="sxs-lookup"><span data-stu-id="0be75-113">CSP Support</span></span>   |   <span data-ttu-id="0be75-114">是</span><span class="sxs-lookup"><span data-stu-id="0be75-114">Yes</span></span>      |
|<span data-ttu-id="0be75-115">GPO 支持</span><span class="sxs-lookup"><span data-stu-id="0be75-115">GPO Support</span></span>    |   <span data-ttu-id="0be75-116">是</span><span class="sxs-lookup"><span data-stu-id="0be75-116">Yes</span></span>      |
|<span data-ttu-id="0be75-117">基于用户的支持</span><span class="sxs-lookup"><span data-stu-id="0be75-117">User-based Support</span></span>     |   <span data-ttu-id="0be75-118">是</span><span class="sxs-lookup"><span data-stu-id="0be75-118">Yes</span></span>      |
|<span data-ttu-id="0be75-119">基于计算机的支持</span><span class="sxs-lookup"><span data-stu-id="0be75-119">Machine-based Support</span></span>    |    <span data-ttu-id="0be75-120">是</span><span class="sxs-lookup"><span data-stu-id="0be75-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="0be75-121">准备终结点</span><span class="sxs-lookup"><span data-stu-id="0be75-121">Prepare your endpoints</span></span>

<span data-ttu-id="0be75-122">在存储空间 **4.18.2103.3** Windows 10或更高版本的设备上部署可移动访问控制。</span><span class="sxs-lookup"><span data-stu-id="0be75-122">Deploy Removable Storage Access Control on Windows 10 devices that have antimalware client version **4.18.2103.3 or later**.</span></span>

- <span data-ttu-id="0be75-123">**4.18.2104 或更高版本**：添加 SerialNumberId、VID_PID、基于 filepath 的 GPO 支持、ComputerSid</span><span class="sxs-lookup"><span data-stu-id="0be75-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span></span>

- <span data-ttu-id="0be75-124">**4.18.2105** 或更高版本：添加对 HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId 的通配符支持、特定计算机上特定用户的组合、可删除的 SSD (SanDisk 极性 SSD) /USB 附加 SCSI (UAS) 支持</span><span class="sxs-lookup"><span data-stu-id="0be75-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="PowerShell 接口":::

> [!NOTE]
> <span data-ttu-id="0be75-126">任何Windows 安全中心组件都不需要处于活动状态，您可以运行可移动存储空间访问控制，而不受Windows 安全中心状态。</span><span class="sxs-lookup"><span data-stu-id="0be75-126">None of Windows Security components need to be active, you can run Removable Storage Access Control independent of Windows Security status.</span></span>

## <a name="policy-properties"></a><span data-ttu-id="0be75-127">策略属性</span><span class="sxs-lookup"><span data-stu-id="0be75-127">Policy properties</span></span>

<span data-ttu-id="0be75-128">可以使用以下属性创建可移动存储组：</span><span class="sxs-lookup"><span data-stu-id="0be75-128">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="0be75-129">**属性名称：组 ID**</span><span class="sxs-lookup"><span data-stu-id="0be75-129">**Property name: Group Id**</span></span>

1. <span data-ttu-id="0be75-130">说明 [：GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)是一个唯一 ID，表示组，将在策略中使用。</span><span class="sxs-lookup"><span data-stu-id="0be75-130">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="0be75-131">**属性名称：DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="0be75-131">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="0be75-132">说明：列出你想要在组中覆盖的设备属性。</span><span class="sxs-lookup"><span data-stu-id="0be75-132">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="0be75-133">列出你想要在组中覆盖的设备属性。</span><span class="sxs-lookup"><span data-stu-id="0be75-133">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="0be75-134">有关每个设备属性的详细信息， **请参阅上面的设备** 属性部分。</span><span class="sxs-lookup"><span data-stu-id="0be75-134">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="0be75-135">选项：</span><span class="sxs-lookup"><span data-stu-id="0be75-135">Options:</span></span>

    - <span data-ttu-id="0be75-136">主 ID</span><span class="sxs-lookup"><span data-stu-id="0be75-136">Primary ID</span></span>
        - <span data-ttu-id="0be75-137">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="0be75-137">RemovableMediaDevices</span></span>
        - <span data-ttu-id="0be75-138">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="0be75-138">CdRomDevices</span></span>
    - <span data-ttu-id="0be75-139">DeviceId</span><span class="sxs-lookup"><span data-stu-id="0be75-139">DeviceId</span></span>
    - <span data-ttu-id="0be75-140">HardwareId</span><span class="sxs-lookup"><span data-stu-id="0be75-140">HardwareId</span></span>
    - <span data-ttu-id="0be75-141">InstancePathId：InstancePathId 是一个唯一标识系统中设备的字符串，例如 USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0。</span><span class="sxs-lookup"><span data-stu-id="0be75-141">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="0be75-142">末尾的号码 (例如 0&**0**) 表示可用插槽，并且可能会从设备更改为设备。</span><span class="sxs-lookup"><span data-stu-id="0be75-142">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="0be75-143">为获得最佳结果，请结尾使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0be75-143">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="0be75-144">例如，USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="0be75-144">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="0be75-145">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="0be75-145">FriendlyNameId</span></span>
    - <span data-ttu-id="0be75-146">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="0be75-146">SerialNumberId</span></span>
    - <span data-ttu-id="0be75-147">VID</span><span class="sxs-lookup"><span data-stu-id="0be75-147">VID</span></span>
    - <span data-ttu-id="0be75-148">PID</span><span class="sxs-lookup"><span data-stu-id="0be75-148">PID</span></span>
    - <span data-ttu-id="0be75-149">VID_PID</span><span class="sxs-lookup"><span data-stu-id="0be75-149">VID_PID</span></span>
        - <span data-ttu-id="0be75-150">0751_55E0：匹配此精确的 VID/PID 对</span><span class="sxs-lookup"><span data-stu-id="0be75-150">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="0be75-151">_55E0：将任何媒体与 PID=55E0 匹配</span><span class="sxs-lookup"><span data-stu-id="0be75-151">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="0be75-152">0751_：将任何媒体与 VID=0751 匹配</span><span class="sxs-lookup"><span data-stu-id="0be75-152">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="0be75-153">**属性名称：MatchType**</span><span class="sxs-lookup"><span data-stu-id="0be75-153">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="0be75-154">说明：当 DescriptorIDList 中使用多个设备属性时，MatchType 定义关系。</span><span class="sxs-lookup"><span data-stu-id="0be75-154">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="0be75-155">选项：</span><span class="sxs-lookup"><span data-stu-id="0be75-155">Options:</span></span>

    - <span data-ttu-id="0be75-156">MatchAll：DescriptorIdList 下的任何属性将为 **And** 关系;例如，如果管理员将 DeviceID 和 InstancePathID 放在每个连接的 USB 上，系统将检查 USB 是否同时满足这两个值。</span><span class="sxs-lookup"><span data-stu-id="0be75-156">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>
    - <span data-ttu-id="0be75-157">MatchAny：DescriptorIdList 下的属性将为 **Or** 关系;例如，如果管理员将 DeviceID 和 InstancePathID 放在每个连接的 USB 上，只要 USB 具有相同的 **DeviceID** 或 **InstanceID** 值，系统就会执行强制操作。</span><span class="sxs-lookup"><span data-stu-id="0be75-157">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="0be75-158">以下是访问控制策略属性：</span><span class="sxs-lookup"><span data-stu-id="0be75-158">Following are the access control policy properties:</span></span>

<span data-ttu-id="0be75-159">**属性名称：PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="0be75-159">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="0be75-160">说明 [：GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)是一个唯一 ID，表示策略，将用于报告和疑难解答。</span><span class="sxs-lookup"><span data-stu-id="0be75-160">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="0be75-161">**属性名称：IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="0be75-161">**Property name: IncludedIdList**</span></span>

2. <span data-ttu-id="0be75-162">说明： (策略) 的组。</span><span class="sxs-lookup"><span data-stu-id="0be75-162">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="0be75-163">如果添加了多个组，该策略将应用于所有这些组的任何媒体。</span><span class="sxs-lookup"><span data-stu-id="0be75-163">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

3. <span data-ttu-id="0be75-164">选项：必须在此实例使用组 ID/GUID。</span><span class="sxs-lookup"><span data-stu-id="0be75-164">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="0be75-165">以下示例显示 GroupID 的用法：</span><span class="sxs-lookup"><span data-stu-id="0be75-165">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="0be75-166">**属性名称：ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="0be75-166">**Property name: ExcludedIDList**</span></span>

<span data-ttu-id="0be75-167">说明： (策略) 的组。</span><span class="sxs-lookup"><span data-stu-id="0be75-167">Description: The group(s) that the policy will not be applied to.</span></span>

<span data-ttu-id="0be75-168">选项：必须在此实例使用组 ID/GUID。</span><span class="sxs-lookup"><span data-stu-id="0be75-168">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="0be75-169">**属性名称：条目 ID**</span><span class="sxs-lookup"><span data-stu-id="0be75-169">**Property name: Entry Id**</span></span>

1. <span data-ttu-id="0be75-170">说明：一个 PolicyRule 可以有多个条目;每个具有唯一 GUID 的条目告知设备控件一个限制。</span><span class="sxs-lookup"><span data-stu-id="0be75-170">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="0be75-171">**属性名称：Type**</span><span class="sxs-lookup"><span data-stu-id="0be75-171">**Property name: Type**</span></span>

1. <span data-ttu-id="0be75-172">说明：定义 IncludedIDList 中可移动存储组的操作。</span><span class="sxs-lookup"><span data-stu-id="0be75-172">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="0be75-173">强制：允许或拒绝</span><span class="sxs-lookup"><span data-stu-id="0be75-173">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="0be75-174">审核：AuditAllowed 或 AuditDenied</span><span class="sxs-lookup"><span data-stu-id="0be75-174">Audit: AuditAllowed or AuditDenied</span></span> 

2. <span data-ttu-id="0be75-175">选项：</span><span class="sxs-lookup"><span data-stu-id="0be75-175">Options:</span></span>

    - <span data-ttu-id="0be75-176">允许</span><span class="sxs-lookup"><span data-stu-id="0be75-176">Allow</span></span>
    - <span data-ttu-id="0be75-177">拒绝</span><span class="sxs-lookup"><span data-stu-id="0be75-177">Deny</span></span>
    - <span data-ttu-id="0be75-178">AuditAllowed：定义允许访问时的通知和事件</span><span class="sxs-lookup"><span data-stu-id="0be75-178">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="0be75-179">AuditDenied：定义拒绝访问时的通知和事件;必须配合拒绝 **条目** 一起工作。</span><span class="sxs-lookup"><span data-stu-id="0be75-179">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="0be75-180">当同一媒体存在冲突类型时，系统将应用策略中的第一个冲突类型。</span><span class="sxs-lookup"><span data-stu-id="0be75-180">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="0be75-181">冲突类型的一个示例是 **"允许"和**"**拒绝"。**</span><span class="sxs-lookup"><span data-stu-id="0be75-181">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="0be75-182">**属性名称：Sid**</span><span class="sxs-lookup"><span data-stu-id="0be75-182">**Property name: Sid**</span></span>

<span data-ttu-id="0be75-183">说明：定义是否对特定用户或用户组应用此策略;一个条目最多可具有一个 Sid 和一个不带任何 Sid 的条目，这意味着在计算机中应用策略。</span><span class="sxs-lookup"><span data-stu-id="0be75-183">Description: Defines whether apply this policy over specific user or user group; one entry can have maximum one Sid and an entry without any Sid means applying the policy over the machine.</span></span>

<span data-ttu-id="0be75-184">**属性名称：ComputerSid**</span><span class="sxs-lookup"><span data-stu-id="0be75-184">**Property name: ComputerSid**</span></span>

<span data-ttu-id="0be75-185">说明：定义是否对特定计算机或计算机组应用此策略;一个条目最多可具有一个 ComputerSid，一个条目不带任何 ComputerSid 意味着将策略应用到计算机。</span><span class="sxs-lookup"><span data-stu-id="0be75-185">Description: Defines whether apply this policy over specific machine or machine group; one entry can have maximum one ComputerSid and an entry without any ComputerSid means applying the policy over the machine.</span></span> <span data-ttu-id="0be75-186">如果要将条目应用于特定用户和特定计算机，请同时将 Sid 和 ComputerSid 添加到同一条目中。</span><span class="sxs-lookup"><span data-stu-id="0be75-186">If you want to apply an Entry to a specific user and specific machine, add both Sid and ComputerSid into the same Entry.</span></span>

<span data-ttu-id="0be75-187">**属性名称：Options**</span><span class="sxs-lookup"><span data-stu-id="0be75-187">**Property name: Options**</span></span>

<span data-ttu-id="0be75-188">说明：定义是否显示通知。</span><span class="sxs-lookup"><span data-stu-id="0be75-188">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="可在其中查看设备状态的屏幕":::

<span data-ttu-id="0be75-190">选项：0-4。</span><span class="sxs-lookup"><span data-stu-id="0be75-190">Options: 0-4.</span></span> <span data-ttu-id="0be75-191">选择"类型允许"或"拒绝"时：</span><span class="sxs-lookup"><span data-stu-id="0be75-191">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="0be75-192">0：无</span><span class="sxs-lookup"><span data-stu-id="0be75-192">0: nothing</span></span>
   - <span data-ttu-id="0be75-193">4：对此条目 **禁用 AuditAllowed** **和 AuditDenied。**</span><span class="sxs-lookup"><span data-stu-id="0be75-193">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="0be75-194">即使 **发生阻止** 且已配置 **AuditDenied** 设置，系统也将不会显示通知。</span><span class="sxs-lookup"><span data-stu-id="0be75-194">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="0be75-195">选择" **类型 AuditAllowed"** 或 **"AuditDenied"** 时：</span><span class="sxs-lookup"><span data-stu-id="0be75-195">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="0be75-196">0：无</span><span class="sxs-lookup"><span data-stu-id="0be75-196">0: nothing</span></span>
   - <span data-ttu-id="0be75-197">1：显示通知</span><span class="sxs-lookup"><span data-stu-id="0be75-197">1: show notification</span></span>
   - <span data-ttu-id="0be75-198">2：发送事件</span><span class="sxs-lookup"><span data-stu-id="0be75-198">2: send event</span></span>
   - <span data-ttu-id="0be75-199">3：显示通知和发送事件</span><span class="sxs-lookup"><span data-stu-id="0be75-199">3: show notification and send event</span></span>

<span data-ttu-id="0be75-200">**属性名称：AccessMask**</span><span class="sxs-lookup"><span data-stu-id="0be75-200">**Property name: AccessMask**</span></span>

<span data-ttu-id="0be75-201">说明：定义访问权限。</span><span class="sxs-lookup"><span data-stu-id="0be75-201">Description: Defines the access.</span></span>

<span data-ttu-id="0be75-202">选项 1-7：</span><span class="sxs-lookup"><span data-stu-id="0be75-202">Options 1-7:</span></span>
  - <span data-ttu-id="0be75-203">1：读取</span><span class="sxs-lookup"><span data-stu-id="0be75-203">1: Read</span></span>
  - <span data-ttu-id="0be75-204">2：写入</span><span class="sxs-lookup"><span data-stu-id="0be75-204">2: Write</span></span>
  - <span data-ttu-id="0be75-205">3：读取和写入</span><span class="sxs-lookup"><span data-stu-id="0be75-205">3: Read and Write</span></span>
  - <span data-ttu-id="0be75-206">4：执行</span><span class="sxs-lookup"><span data-stu-id="0be75-206">4: Execute</span></span>
  - <span data-ttu-id="0be75-207">5：读取和执行</span><span class="sxs-lookup"><span data-stu-id="0be75-207">5: Read and Execute</span></span>
  - <span data-ttu-id="0be75-208">6：写入和执行</span><span class="sxs-lookup"><span data-stu-id="0be75-208">6: Write and Execute</span></span>
  - <span data-ttu-id="0be75-209">7：读取、写入和执行</span><span class="sxs-lookup"><span data-stu-id="0be75-209">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="0be75-210">常见的可移动存储空间访问控制方案</span><span class="sxs-lookup"><span data-stu-id="0be75-210">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="0be75-211">为了帮助你熟悉 Microsoft Defender for Endpoint Removable 存储空间访问控制，我们将一些常见方案放在一起，以便你可以遵循。</span><span class="sxs-lookup"><span data-stu-id="0be75-211">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="0be75-212">方案 1：阻止对全部 USB 执行写入和执行访问，但允许特定批准的 USB</span><span class="sxs-lookup"><span data-stu-id="0be75-212">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="0be75-213">创建组</span><span class="sxs-lookup"><span data-stu-id="0be75-213">Create groups</span></span>

    1. <span data-ttu-id="0be75-214">组 1：任何可移动存储和 CD/DVD。</span><span class="sxs-lookup"><span data-stu-id="0be75-214">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="0be75-215">可移动存储和 CD/DVD 的一个示例是：示例 Any [Removable 存储空间 and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file中的组 **9b28fae8-72f7-4267-a1a5-685f747a7146。**</span><span class="sxs-lookup"><span data-stu-id="0be75-215">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="0be75-216">组 2：基于设备属性批准的 USB。</span><span class="sxs-lookup"><span data-stu-id="0be75-216">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="0be75-217">此用例的一个示例是：示例已批准 [USB Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件中的实例 ID – 组 **65fa649a-a111-4912-9294-fb6337a25038。**</span><span class="sxs-lookup"><span data-stu-id="0be75-217">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0be75-218">您必须在 值 `&` 中 `&amp;` 将 替换为 。</span><span class="sxs-lookup"><span data-stu-id="0be75-218">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="0be75-219">创建策略</span><span class="sxs-lookup"><span data-stu-id="0be75-219">Create policy</span></span>

    1. <span data-ttu-id="0be75-220">策略 1：阻止写入和执行访问，但允许批准的 USB。</span><span class="sxs-lookup"><span data-stu-id="0be75-220">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="0be75-221">此用例的一个示例是：示例方案 [1](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)阻止写入和执行访问但允许批准的 USBs.xml文件中的 PolicyRule **c544a991-5786-4402-949e-a032cb790d0e。**</span><span class="sxs-lookup"><span data-stu-id="0be75-221">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="0be75-222">策略 2：审核对允许的 USB 的写入和执行访问权限。</span><span class="sxs-lookup"><span data-stu-id="0be75-222">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="0be75-223">此用例的一个示例是：对批准的 [USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件进行审核写入和执行访问示例中的 PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c。**</span><span class="sxs-lookup"><span data-stu-id="0be75-223">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="0be75-224">方案 2：审核对全部（但阻止特定未批准的 USB）的写入和执行访问权限</span><span class="sxs-lookup"><span data-stu-id="0be75-224">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="0be75-225">创建组</span><span class="sxs-lookup"><span data-stu-id="0be75-225">Create groups</span></span>

    1. <span data-ttu-id="0be75-226">组 1：任何可移动存储和 CD/DVD。</span><span class="sxs-lookup"><span data-stu-id="0be75-226">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="0be75-227">此用例的一个示例是：示例 Any [Removable 存储空间 and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件中 Group **9b28fae8-72f7-4267-a1a5-685f747a7146。**</span><span class="sxs-lookup"><span data-stu-id="0be75-227">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="0be75-228">组 2：基于设备属性（例如，供应商 ID/产品 ID、友好名称 – 组 **65fa649a-a111-4912-9294-fb6337a25038）** 的未批准 USB Group.xml文件中未批准的 [USB。](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="0be75-228">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="0be75-229">您必须在 值 `&` 中 `&amp;` 将 替换为 。</span><span class="sxs-lookup"><span data-stu-id="0be75-229">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="0be75-230">创建策略</span><span class="sxs-lookup"><span data-stu-id="0be75-230">Create policy</span></span>

    1. <span data-ttu-id="0be75-231">策略 1：阻止对全部（但阻止特定未批准的 USB）的写入和执行访问。</span><span class="sxs-lookup"><span data-stu-id="0be75-231">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="0be75-232">此用例的一个示例是：示例方案 2 审核写入和执行对除阻止特定未批准的 [USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件的访问中的 PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98。**</span><span class="sxs-lookup"><span data-stu-id="0be75-232">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="0be75-233">策略 2：审核写入和执行对他人的访问。</span><span class="sxs-lookup"><span data-stu-id="0be75-233">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="0be75-234">此用例的一个示例是：对 [others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件进行审核写入和执行访问示例中的 PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48。**</span><span class="sxs-lookup"><span data-stu-id="0be75-234">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="0be75-235">通过组策略部署和管理策略</span><span class="sxs-lookup"><span data-stu-id="0be75-235">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="0be75-236">通过"存储空间访问控制"功能，可以通过组策略将策略应用于用户或设备，或同时应用于两者。</span><span class="sxs-lookup"><span data-stu-id="0be75-236">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="0be75-237">授权</span><span class="sxs-lookup"><span data-stu-id="0be75-237">Licensing</span></span>

<span data-ttu-id="0be75-238">在开始使用"可移动存储空间访问控制"之前，必须确认Microsoft 365 [订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。</span><span class="sxs-lookup"><span data-stu-id="0be75-238">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="0be75-239">若要访问和使用可移动存储空间访问控制，您必须具有Microsoft 365 E3或Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="0be75-239">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="0be75-240">通过组策略部署策略</span><span class="sxs-lookup"><span data-stu-id="0be75-240">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="0be75-241">将所有组组合到 `<Groups>` `</Groups>` 一个 xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="0be75-241">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="0be75-242">下图演示了方案 [1：](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)阻止对全部 USB 进行写入和执行访问，但允许特定批准的 USB 的示例。</span><span class="sxs-lookup"><span data-stu-id="0be75-242">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="显示允许在设备上允许特定批准的 USB 的配置设置的屏幕":::
    
2. <span data-ttu-id="0be75-244">将所有规则合并到 `<PolicyRules>` `</PolicyRules>` 一个 xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="0be75-244">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="0be75-245">如果要限制特定用户，请使用 Entry 中的 SID 属性。</span><span class="sxs-lookup"><span data-stu-id="0be75-245">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="0be75-246">如果策略条目中没有任何 SID，则条目将应用于计算机的每一个登录实例。</span><span class="sxs-lookup"><span data-stu-id="0be75-246">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="0be75-247">下图演示了 SID 属性的用法，以及方案 [1：](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)阻止对全部但允许特定批准的 USB 的写入和执行访问的示例。</span><span class="sxs-lookup"><span data-stu-id="0be75-247">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="显示指示 SID 属性属性使用情况的代码的屏幕":::

3. <span data-ttu-id="0be75-249">在网络共享文件夹中保存规则和组 XML 文件，将网络共享文件夹路径放入组策略设置：**计算机配置 -> 管理模板 -> Windows 组件 -> Microsoft Defender 防病毒 -> 设备控制："定义设备** 控制策略组"和"定义设备控制策略规则"。</span><span class="sxs-lookup"><span data-stu-id="0be75-249">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="0be75-250">目标计算机必须能够访问网络共享才能拥有策略。</span><span class="sxs-lookup"><span data-stu-id="0be75-250">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="0be75-251">但是，读取策略后，不再需要网络连接，即使在计算机重新启动后也不例外。</span><span class="sxs-lookup"><span data-stu-id="0be75-251">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="设备控制屏幕":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="0be75-253">通过 Intune OMA-URI 部署和管理策略</span><span class="sxs-lookup"><span data-stu-id="0be75-253">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="0be75-254">通过可移动存储空间访问控制功能，你可以将策略通过 OMA-URI 应用到用户或设备，或同时应用到两者。</span><span class="sxs-lookup"><span data-stu-id="0be75-254">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="0be75-255">授权</span><span class="sxs-lookup"><span data-stu-id="0be75-255">Licensing</span></span>

<span data-ttu-id="0be75-256">在开始使用"可移动存储空间访问控制"之前，必须确认Microsoft 365 [订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。</span><span class="sxs-lookup"><span data-stu-id="0be75-256">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="0be75-257">若要访问和使用可移动存储空间访问控制，您必须具有Microsoft 365 E3或Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="0be75-257">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="0be75-258">权限</span><span class="sxs-lookup"><span data-stu-id="0be75-258">Permission</span></span>

<span data-ttu-id="0be75-259">对于 Intune 中的策略部署，该帐户必须具有创建、编辑、更新或删除设备配置文件的权限。</span><span class="sxs-lookup"><span data-stu-id="0be75-259">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="0be75-260">可以创建自定义角色或使用具有这些权限的任何内置角色。</span><span class="sxs-lookup"><span data-stu-id="0be75-260">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="0be75-261">策略和配置文件管理器角色</span><span class="sxs-lookup"><span data-stu-id="0be75-261">Policy and profile Manager role</span></span>
- <span data-ttu-id="0be75-262">为设备配置文件启用"创建/编辑/更新/读取/删除/查看报告"权限的自定义角色</span><span class="sxs-lookup"><span data-stu-id="0be75-262">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="0be75-263">全局管理员</span><span class="sxs-lookup"><span data-stu-id="0be75-263">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="0be75-264">通过 OMA-URI 部署策略</span><span class="sxs-lookup"><span data-stu-id="0be75-264">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="0be75-265">**Microsoft Endpoint Manager管理中心 (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform： Windows 10 and later & Profile： Custom**</span><span class="sxs-lookup"><span data-stu-id="0be75-265">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="0be75-266">对于每个组，创建 OMA-URI 规则：</span><span class="sxs-lookup"><span data-stu-id="0be75-266">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="0be75-267">OMA-URI： </span><span class="sxs-lookup"><span data-stu-id="0be75-267">OMA-URI:</span></span>

      <span data-ttu-id="0be75-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="0be75-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="0be75-269">例如，对于 **示例中的任何可移动存储和 CD/DVD** 组，该链接必须为：</span><span class="sxs-lookup"><span data-stu-id="0be75-269">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="0be75-270">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="0be75-270">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="0be75-271">数据类型：String (XML 文件) </span><span class="sxs-lookup"><span data-stu-id="0be75-271">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="STRING 文件的 xml 数据类型":::

2. <span data-ttu-id="0be75-273">对于每个策略，还要创建 OMA-URI：</span><span class="sxs-lookup"><span data-stu-id="0be75-273">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="0be75-274">OMA-URI： </span><span class="sxs-lookup"><span data-stu-id="0be75-274">OMA-URI:</span></span>

      <span data-ttu-id="0be75-275">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="0be75-275">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="0be75-276">例如，对于示例中 **的"阻止写入和执行访问但允许批准的 USB"** 规则，该链接必须是：</span><span class="sxs-lookup"><span data-stu-id="0be75-276">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="0be75-277">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData。</span><span class="sxs-lookup"><span data-stu-id="0be75-277">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="0be75-278">数据类型：String (XML 文件) </span><span class="sxs-lookup"><span data-stu-id="0be75-278">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="STRING 文件的 XML 文件的数据类型":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="0be75-280">使用 Intune 用户界面部署和管理策略</span><span class="sxs-lookup"><span data-stu-id="0be75-280">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="0be75-281">此功能 (Microsoft Endpoint Manager 管理中心 (> 设备 > 配置文件 > 创建配置文件 https://endpoint.microsoft.com/) > 平台：Windows 10 及更高版本 & 配置文件：设备控制) 尚不可用。</span><span class="sxs-lookup"><span data-stu-id="0be75-281">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="0be75-282">在 Microsoft Defender for Endpoint 存储空间设备控件可移动访问控件数据</span><span class="sxs-lookup"><span data-stu-id="0be75-282">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="0be75-283">安全Microsoft 365门户显示受设备控件可移动控件和访问控制存储空间存储。</span><span class="sxs-lookup"><span data-stu-id="0be75-283">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="0be75-284">若要访问Microsoft 365安全性，您必须具有以下订阅：</span><span class="sxs-lookup"><span data-stu-id="0be75-284">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="0be75-285">Microsoft 365 E5 报告</span><span class="sxs-lookup"><span data-stu-id="0be75-285">Microsoft 365 for E5 reporting</span></span>

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

## <a name="frequently-asked-questions"></a><span data-ttu-id="0be75-287">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="0be75-287">Frequently asked questions</span></span>
<span data-ttu-id="0be75-288">**最大 USB 数量的可移动存储媒体限制是什么？**</span><span class="sxs-lookup"><span data-stu-id="0be75-288">**What is the removable storage media limitation for the maximum number of USBs?**</span></span>

<span data-ttu-id="0be75-289">我们已验证一个具有 100，000 个媒体的 USB 组 - 大小最高为 7 MB。</span><span class="sxs-lookup"><span data-stu-id="0be75-289">We have validated one USB group with 100,000 media - up to 7 MB in size.</span></span> <span data-ttu-id="0be75-290">该策略在 Intune 和 GPO 中均有效，而未发生性能问题。</span><span class="sxs-lookup"><span data-stu-id="0be75-290">The policy works in both Intune and GPO without performance issues.</span></span>

<span data-ttu-id="0be75-291">**为什么策略不起作用？**</span><span class="sxs-lookup"><span data-stu-id="0be75-291">**Why does the policy not work?**</span></span>

<span data-ttu-id="0be75-292">最常见的原因是不需要反 [恶意软件客户端版本](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control?view=o365-worldwide#prepare-your-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="0be75-292">The most common reason is there is no required [antimalware client version](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control?view=o365-worldwide#prepare-your-endpoints).</span></span>

<span data-ttu-id="0be75-293">另一个原因是 XML 文件格式不正确，例如，未对 XML 文件中"&"字符使用正确的 markdown 格式，或者文本编辑器可能在文件的开头添加字节顺序标记 (BOM) 0xEF 0xBB 0xBF，这会导致 XML 分析不起作用。</span><span class="sxs-lookup"><span data-stu-id="0be75-293">Another reason could be that the XML file is not correctly formatted, for example, not using the correct markdown formatting for the "&" character in the XML file, or the text editor might add a byte order mark (BOM) 0xEF 0xBB 0xBF at the beginning of the files which causes the XML parsing not to work.</span></span> <span data-ttu-id="0be75-294">一个简单的解决方案是下载示例文件 [， ("](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)**原始**"，**然后选择"另** 存为) 然后更新。</span><span class="sxs-lookup"><span data-stu-id="0be75-294">One simple solution is to download the [sample file](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (select **Raw** and then **Save as**) and then update.</span></span>

<span data-ttu-id="0be75-295">如果有值并且策略通过组策略进行管理，请检查客户端设备是否可以访问策略 XML 路径。</span><span class="sxs-lookup"><span data-stu-id="0be75-295">If there is a value and the policy is managed via Group Policy, check whether the client device can access the policy XML path.</span></span>

<span data-ttu-id="0be75-296">**如何知道哪个计算机正在使用组织中过期的反恶意软件客户端版本？**</span><span class="sxs-lookup"><span data-stu-id="0be75-296">**How can I know which machine is using out of date antimalware client version in the organization?**</span></span>

<span data-ttu-id="0be75-297">可以使用以下查询在安全门户上获取反恶意软件Microsoft 365版本：</span><span class="sxs-lookup"><span data-stu-id="0be75-297">You can use following query to get antimalware client version on the Microsoft 365 security portal:</span></span>
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

