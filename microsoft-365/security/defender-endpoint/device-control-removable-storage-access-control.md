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
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 018bc3549cd7a25df5bdd86d98d351e19027c31f
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796026"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="b9dc8-104">Microsoft Defender for Endpoint 设备控件可移动存储访问控制</span><span class="sxs-lookup"><span data-stu-id="b9dc8-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="b9dc8-105">Microsoft Defender for Endpoint 设备控制可移动存储访问控制使你能够执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="b9dc8-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="b9dc8-106">审核，允许或阻止对可移动存储进行读取、写入或执行访问（带排除或不排除）</span><span class="sxs-lookup"><span data-stu-id="b9dc8-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="b9dc8-107">Privilege</span><span class="sxs-lookup"><span data-stu-id="b9dc8-107">Privilege</span></span> |<span data-ttu-id="b9dc8-108">权限</span><span class="sxs-lookup"><span data-stu-id="b9dc8-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="b9dc8-109">Access</span><span class="sxs-lookup"><span data-stu-id="b9dc8-109">Access</span></span>    |  <span data-ttu-id="b9dc8-110">读取、写入、执行</span><span class="sxs-lookup"><span data-stu-id="b9dc8-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="b9dc8-111">操作模式</span><span class="sxs-lookup"><span data-stu-id="b9dc8-111">Action Mode</span></span>    |    <span data-ttu-id="b9dc8-112">审核、允许、阻止</span><span class="sxs-lookup"><span data-stu-id="b9dc8-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="b9dc8-113">云解决方案提供商支持</span><span class="sxs-lookup"><span data-stu-id="b9dc8-113">CSP Support</span></span>   |   <span data-ttu-id="b9dc8-114">支持</span><span class="sxs-lookup"><span data-stu-id="b9dc8-114">Yes</span></span>      |
|<span data-ttu-id="b9dc8-115">GPO 支持</span><span class="sxs-lookup"><span data-stu-id="b9dc8-115">GPO Support</span></span>    |   <span data-ttu-id="b9dc8-116">支持</span><span class="sxs-lookup"><span data-stu-id="b9dc8-116">Yes</span></span>      |
|<span data-ttu-id="b9dc8-117">基于用户的支持</span><span class="sxs-lookup"><span data-stu-id="b9dc8-117">User-based Support</span></span>     |   <span data-ttu-id="b9dc8-118">支持</span><span class="sxs-lookup"><span data-stu-id="b9dc8-118">Yes</span></span>      |
|<span data-ttu-id="b9dc8-119">基于计算机的支持</span><span class="sxs-lookup"><span data-stu-id="b9dc8-119">Machine-based Support</span></span>    |    <span data-ttu-id="b9dc8-120">支持</span><span class="sxs-lookup"><span data-stu-id="b9dc8-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="b9dc8-121">准备终结点</span><span class="sxs-lookup"><span data-stu-id="b9dc8-121">Prepare your endpoints</span></span>

<span data-ttu-id="b9dc8-122">在存储客户端版本 **4.18.2103.3** 或更高版本的 Windows 10 设备上部署可移动访问控制。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-122">Deploy Removable Storage Access Control on Windows 10 devices that have Anti-malware Client Version **4.18.2103.3 or later**.</span></span>
1. <span data-ttu-id="b9dc8-123">**4.18.2104 或** 更高版本：添加 SerialNumberId、VID_PID、基于文件路径的 GPO 支持</span><span class="sxs-lookup"><span data-stu-id="b9dc8-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support</span></span>

2. <span data-ttu-id="b9dc8-124">**4.18.2105** 或更高版本：添加对 HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId 的通配符支持、特定计算机上特定用户的组合、可删除的 SSD (SanDisk 极性 SSD) /USB 附加 SCSI (UAS) 支持</span><span class="sxs-lookup"><span data-stu-id="b9dc8-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="PowerShell 接口":::

## <a name="policy-properties"></a><span data-ttu-id="b9dc8-126">策略属性</span><span class="sxs-lookup"><span data-stu-id="b9dc8-126">Policy properties</span></span>

<span data-ttu-id="b9dc8-127">可以使用以下属性创建可移动存储组：</span><span class="sxs-lookup"><span data-stu-id="b9dc8-127">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="b9dc8-128">**属性名称：组 ID**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-128">**Property name: Group ID**</span></span>

1. <span data-ttu-id="b9dc8-129">说明 [：GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)是一个唯一 ID，表示组，将在策略中使用。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-129">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="b9dc8-130">**属性名称：DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-130">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="b9dc8-131">说明：列出你想要在组中覆盖的设备属性。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-131">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="b9dc8-132">列出你想要在组中覆盖的设备属性。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-132">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="b9dc8-133">有关每个设备属性的详细信息， **请参阅上面的设备** 属性部分。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-133">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="b9dc8-134">选项：</span><span class="sxs-lookup"><span data-stu-id="b9dc8-134">Options:</span></span>
    - <span data-ttu-id="b9dc8-135">主 ID</span><span class="sxs-lookup"><span data-stu-id="b9dc8-135">Primary ID</span></span>
        - <span data-ttu-id="b9dc8-136">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="b9dc8-136">RemovableMediaDevices</span></span>
        - <span data-ttu-id="b9dc8-137">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="b9dc8-137">CdRomDevices</span></span>
    - <span data-ttu-id="b9dc8-138">DeviceId</span><span class="sxs-lookup"><span data-stu-id="b9dc8-138">DeviceId</span></span>
    - <span data-ttu-id="b9dc8-139">HardwareId</span><span class="sxs-lookup"><span data-stu-id="b9dc8-139">HardwareId</span></span>
    - <span data-ttu-id="b9dc8-140">InstancePathId：InstancePathId 是一个唯一标识系统中设备的字符串，例如 USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-140">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="b9dc8-141">末尾的编号 (例如 0&**0**) 表示空位，并且可能会因设备而更改。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-141">The number at the end (for example **&0**) represents the avaliable slot and may change from device to device.</span></span> <span data-ttu-id="b9dc8-142">为获得最佳结果，请结尾使用通配符。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-142">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="b9dc8-143">例如，USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="b9dc8-143">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="b9dc8-144">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="b9dc8-144">FriendlyNameId</span></span>
    - <span data-ttu-id="b9dc8-145">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="b9dc8-145">SerialNumberId</span></span>
    - <span data-ttu-id="b9dc8-146">VID</span><span class="sxs-lookup"><span data-stu-id="b9dc8-146">VID</span></span>
    - <span data-ttu-id="b9dc8-147">PID</span><span class="sxs-lookup"><span data-stu-id="b9dc8-147">PID</span></span>
    - <span data-ttu-id="b9dc8-148">VID_PID</span><span class="sxs-lookup"><span data-stu-id="b9dc8-148">VID_PID</span></span>
        - <span data-ttu-id="b9dc8-149">0751_55E0：匹配此精确的 VID/PID 对</span><span class="sxs-lookup"><span data-stu-id="b9dc8-149">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="b9dc8-150">_55E0：将任何媒体与 PID=55E0 匹配</span><span class="sxs-lookup"><span data-stu-id="b9dc8-150">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="b9dc8-151">0751_：将任何媒体与 VID=0751 匹配</span><span class="sxs-lookup"><span data-stu-id="b9dc8-151">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="b9dc8-152">**属性名称：MatchType**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-152">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="b9dc8-153">说明：当 DescriptorIDList 中使用多个设备属性时，MatchType 定义关系。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-153">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="b9dc8-154">选项：</span><span class="sxs-lookup"><span data-stu-id="b9dc8-154">Options:</span></span>
    - <span data-ttu-id="b9dc8-155">MatchAll：DescriptorIdList 下的任何属性将为 **And** 关系;例如，如果管理员将 DeviceID 和 InstancePathID 放在每个连接的 USB 上，系统将检查 USB 是否同时满足这两个值。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-155">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>

    - <span data-ttu-id="b9dc8-156">MatchAny：DescriptorIdList 下的属性将为 **Or** 关系;例如，如果管理员将 DeviceID 和 InstancePathID 放在每个连接的 USB 上，只要 USB 具有相同的 **DeviceID** 或 **InstanceID** 值，系统就会执行强制操作。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-156">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="b9dc8-157">以下是访问控制策略属性：</span><span class="sxs-lookup"><span data-stu-id="b9dc8-157">Following are the access control policy properties:</span></span>

<span data-ttu-id="b9dc8-158">**属性名称：PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-158">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="b9dc8-159">说明 [：GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)是一个唯一 ID，表示策略，将用于报告和疑难解答。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-159">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="b9dc8-160">**属性名称：IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-160">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="b9dc8-161">说明： (策略) 的组。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-161">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="b9dc8-162">如果添加了多个组，该策略将应用于所有这些组的任何媒体。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-162">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

1. <span data-ttu-id="b9dc8-163">选项：必须在此实例使用组 ID/GUID。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-163">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="b9dc8-164">以下示例显示 GroupID 的用法：</span><span class="sxs-lookup"><span data-stu-id="b9dc8-164">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="b9dc8-165">**属性名称：ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-165">**Property name: ExcludedIDList**</span></span>

1. <span data-ttu-id="b9dc8-166">说明： (策略) 的组。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-166">Description: The group(s) that the policy will not be applied to.</span></span>
1. <span data-ttu-id="b9dc8-167">选项：必须在此实例使用组 ID/GUID。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-167">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="b9dc8-168">**属性名称：条目 ID**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-168">**Property name: Entry ID**</span></span>

1. <span data-ttu-id="b9dc8-169">说明：一个 PolicyRule 可以有多个条目;每个具有唯一 GUID 的条目告知设备控件一个限制。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-169">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="b9dc8-170">**属性名称：Type**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-170">**Property name: Type**</span></span>

1. <span data-ttu-id="b9dc8-171">说明：定义 IncludedIDList 中可移动存储组的操作。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-171">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="b9dc8-172">强制：允许或拒绝</span><span class="sxs-lookup"><span data-stu-id="b9dc8-172">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="b9dc8-173">审核：AuditAllowed 或 AuditDenied</span><span class="sxs-lookup"><span data-stu-id="b9dc8-173">Audit: AuditAllowed or AuditDenied</span></span> 
1. <span data-ttu-id="b9dc8-174">选项：</span><span class="sxs-lookup"><span data-stu-id="b9dc8-174">Options:</span></span>
    - <span data-ttu-id="b9dc8-175">允许</span><span class="sxs-lookup"><span data-stu-id="b9dc8-175">Allow</span></span>
    - <span data-ttu-id="b9dc8-176">拒绝</span><span class="sxs-lookup"><span data-stu-id="b9dc8-176">Deny</span></span>
    - <span data-ttu-id="b9dc8-177">AuditAllowed：定义允许访问时的通知和事件</span><span class="sxs-lookup"><span data-stu-id="b9dc8-177">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="b9dc8-178">AuditDenied：定义拒绝访问时的通知和事件;必须配合拒绝 **条目** 一起工作。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-178">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="b9dc8-179">当同一媒体存在冲突类型时，系统将应用策略中的第一个冲突类型。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-179">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="b9dc8-180">冲突类型的一个示例是 **"允许"和**"**拒绝"。**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-180">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="b9dc8-181">**属性名称：Options**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-181">**Property name: Options**</span></span>

1. <span data-ttu-id="b9dc8-182">说明：定义是否显示通知。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-182">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="可在其中查看设备状态的屏幕":::

1. <span data-ttu-id="b9dc8-184">选项：0-4。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-184">Options: 0-4.</span></span> <span data-ttu-id="b9dc8-185">选择"类型允许"或"拒绝"时：</span><span class="sxs-lookup"><span data-stu-id="b9dc8-185">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="b9dc8-186">0：无</span><span class="sxs-lookup"><span data-stu-id="b9dc8-186">0: nothing</span></span>
   - <span data-ttu-id="b9dc8-187">4：对此条目 **禁用 AuditAllowed** **和 AuditDenied。**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-187">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="b9dc8-188">即使 **发生阻止** 且已配置 **AuditDenied** 设置，系统也将不会显示通知。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-188">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="b9dc8-189">选择" **类型 AuditAllowed"** 或 **"AuditDenied"** 时：</span><span class="sxs-lookup"><span data-stu-id="b9dc8-189">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="b9dc8-190">0：无</span><span class="sxs-lookup"><span data-stu-id="b9dc8-190">0: nothing</span></span>
   - <span data-ttu-id="b9dc8-191">1：显示通知</span><span class="sxs-lookup"><span data-stu-id="b9dc8-191">1: show notification</span></span>
   - <span data-ttu-id="b9dc8-192">2：发送事件</span><span class="sxs-lookup"><span data-stu-id="b9dc8-192">2: send event</span></span>
   - <span data-ttu-id="b9dc8-193">3：显示通知和发送事件</span><span class="sxs-lookup"><span data-stu-id="b9dc8-193">3: show notification and send event</span></span>

<span data-ttu-id="b9dc8-194">**属性名称：AccessMask**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-194">**Property name: AccessMask**</span></span>

1. <span data-ttu-id="b9dc8-195">说明：定义访问权限。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-195">Description: Defines the access.</span></span>

1. <span data-ttu-id="b9dc8-196">选项：1-7：</span><span class="sxs-lookup"><span data-stu-id="b9dc8-196">Options: 1-7:</span></span>
    - <span data-ttu-id="b9dc8-197">1：读取</span><span class="sxs-lookup"><span data-stu-id="b9dc8-197">1: Read</span></span>
    - <span data-ttu-id="b9dc8-198">2：写入</span><span class="sxs-lookup"><span data-stu-id="b9dc8-198">2: Write</span></span>
    - <span data-ttu-id="b9dc8-199">3：读取和写入</span><span class="sxs-lookup"><span data-stu-id="b9dc8-199">3: Read and Write</span></span>
    - <span data-ttu-id="b9dc8-200">4：执行</span><span class="sxs-lookup"><span data-stu-id="b9dc8-200">4: Execute</span></span>
    - <span data-ttu-id="b9dc8-201">5：读取和执行</span><span class="sxs-lookup"><span data-stu-id="b9dc8-201">5: Read and Execute</span></span>
    - <span data-ttu-id="b9dc8-202">6：写入和执行</span><span class="sxs-lookup"><span data-stu-id="b9dc8-202">6: Write and Execute</span></span>
    - <span data-ttu-id="b9dc8-203">7：读取、写入和执行</span><span class="sxs-lookup"><span data-stu-id="b9dc8-203">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="b9dc8-204">常见的可移动存储访问控制方案</span><span class="sxs-lookup"><span data-stu-id="b9dc8-204">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="b9dc8-205">为了帮助你熟悉 Microsoft Defender for Endpoint Removable 存储访问控制，我们将一些常见方案放在一起供你遵循。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-205">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="b9dc8-206">方案 1：阻止对全部 USB 执行写入和执行访问，但允许特定批准的 USB</span><span class="sxs-lookup"><span data-stu-id="b9dc8-206">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="b9dc8-207">创建组</span><span class="sxs-lookup"><span data-stu-id="b9dc8-207">Create groups</span></span>
    1. <span data-ttu-id="b9dc8-208">组 1：任何可移动存储和 CD/DVD。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-208">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="b9dc8-209">可移动存储和 CD/DVD 的一个示例是：示例 Any [Removable 存储 and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file中的组 **9b28fae8-72f7-4267-a1a5-685f747a7146。**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-209">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="b9dc8-210">组 2：基于设备属性批准的 USB。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-210">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="b9dc8-211">此用例的一个示例是：示例已批准 [USB Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件中的实例 ID – 组 **65fa649a-a111-4912-9294-fb6337a25038。**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-211">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9dc8-212">您必须在 值 `&` 中 `&amp;` 将 替换为 。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-212">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="b9dc8-213">创建策略</span><span class="sxs-lookup"><span data-stu-id="b9dc8-213">Create policy</span></span>
    1. <span data-ttu-id="b9dc8-214">策略 1：阻止写入和执行访问，但允许批准的 USB。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-214">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="b9dc8-215">此用例的一个示例是：示例方案 1 阻止写入和执行访问，但允许批准的 [USB .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件中的 PolicyRule **c544a991-5786-4402-949e-a032cb790d0e。**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-215">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="b9dc8-216">策略 2：审核对允许的 USB 的写入和执行访问权限。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-216">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="b9dc8-217">此用例的一个示例是：对批准的 [USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件进行审核写入和执行访问示例中的 PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c。**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-217">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="b9dc8-218">方案 2：审核对全部（但阻止特定未批准的 USB）的写入和执行访问权限</span><span class="sxs-lookup"><span data-stu-id="b9dc8-218">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="b9dc8-219">创建组</span><span class="sxs-lookup"><span data-stu-id="b9dc8-219">Create groups</span></span>
    1. <span data-ttu-id="b9dc8-220">组 1：任何可移动存储和 CD/DVD。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-220">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="b9dc8-221">此用例的一个示例是：示例 Any [Removable 存储 and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file中的 Group **9b28fae8-72f7-4267-a1a5-685f747a7146。**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-221">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="b9dc8-222">组 2：基于设备属性（例如，供应商 ID/产品 ID、友好名称 – 组 **65fa649a-a111-4912-9294-fb6337a25038）** 的未批准 USB Group.xml文件中未批准的 [USB。](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="b9dc8-222">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="b9dc8-223">您必须在 值 `&` 中 `&amp;` 将 替换为 。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-223">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="b9dc8-224">创建策略</span><span class="sxs-lookup"><span data-stu-id="b9dc8-224">Create policy</span></span>
    1. <span data-ttu-id="b9dc8-225">策略 1：阻止对全部（但阻止特定未批准的 USB）的写入和执行访问。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-225">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="b9dc8-226">此用例的一个示例是：示例方案 2 审核写入和执行对除阻止特定未批准的 [USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件的访问中的 PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98。**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-226">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="b9dc8-227">策略 2：审核写入和执行对他人的访问。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-227">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="b9dc8-228">此用例的一个示例是：对 [others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件进行审核写入和执行访问示例中的 PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48。**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-228">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="b9dc8-229">通过组策略部署和管理策略</span><span class="sxs-lookup"><span data-stu-id="b9dc8-229">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="b9dc8-230">通过"存储访问控制"功能，可以通过组策略将策略应用于用户或设备，或同时应用于两者。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-230">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="b9dc8-231">许可</span><span class="sxs-lookup"><span data-stu-id="b9dc8-231">Licensing</span></span>

<span data-ttu-id="b9dc8-232">在开始使用"可移动存储访问控制"之前，必须确认Microsoft 365 [订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-232">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="b9dc8-233">若要访问并使用可移动存储访问控制，您必须具有Microsoft 365 E3。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-233">To access and use Removable Storage Access Control, you must have Microsoft 365 E3.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="b9dc8-234">通过组策略部署策略</span><span class="sxs-lookup"><span data-stu-id="b9dc8-234">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="b9dc8-235">将所有组组合到 `<Groups>` `</Groups>` 一个 xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-235">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="b9dc8-236">下图演示了方案 [1：](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)阻止对全部 USB 进行写入和执行访问，但允许特定批准的 USB 的示例。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-236">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="显示允许在设备上允许特定批准的 USB 的配置设置的屏幕":::
    
2. <span data-ttu-id="b9dc8-238">将所有规则合并到 `<PolicyRules>` `</PolicyRules>` 一个 xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-238">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="b9dc8-239">如果要限制特定用户，请使用 Entry 中的 SID 属性。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-239">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="b9dc8-240">如果策略条目中没有任何 SID，则条目将应用于计算机的每一个登录实例。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-240">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="b9dc8-241">下图演示了 SID 属性的用法，以及方案 [1：](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)阻止对全部但允许特定批准的 USB 的写入和执行访问的示例。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-241">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="显示指示 SID 属性属性使用情况的代码的屏幕":::

3. <span data-ttu-id="b9dc8-243">在网络共享文件夹中保存规则和组 XML 文件，将网络共享文件夹路径放入组策略设置：**计算机配置 -> 管理模板 -> Windows 组件 -> Microsoft Defender 防病毒 -> 设备控制："定义设备** 控制策略组"和"定义设备控制策略规则"。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-243">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="b9dc8-244">目标计算机必须能够访问网络共享才能拥有策略。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-244">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="b9dc8-245">但是，读取策略后，不再需要网络连接，即使在计算机重新启动后也不例外。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-245">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="设备控制屏幕":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="b9dc8-247">通过 Intune OMA-URI 部署和管理策略</span><span class="sxs-lookup"><span data-stu-id="b9dc8-247">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="b9dc8-248">通过可移动存储访问控制功能，你可以将策略通过 OMA-URI 应用到用户或设备，或同时应用到两者。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-248">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="b9dc8-249">许可</span><span class="sxs-lookup"><span data-stu-id="b9dc8-249">Licensing</span></span>

<span data-ttu-id="b9dc8-250">在开始使用"可移动存储访问控制"之前，必须确认Microsoft 365 [订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-250">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="b9dc8-251">若要访问并使用可移动存储访问控制，您必须具有Microsoft 365 E3。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-251">To access and use Removable Storage Access Control, you must have Microsoft 365 E3.</span></span>

### <a name="permission"></a><span data-ttu-id="b9dc8-252">权限</span><span class="sxs-lookup"><span data-stu-id="b9dc8-252">Permission</span></span>

<span data-ttu-id="b9dc8-253">对于 Intune 中的策略部署，该帐户必须具有创建、编辑、更新或删除设备配置文件的权限。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-253">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="b9dc8-254">可以创建自定义角色或使用具有这些权限的任何内置角色。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-254">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="b9dc8-255">策略和配置文件管理器角色</span><span class="sxs-lookup"><span data-stu-id="b9dc8-255">Policy and profile Manager role</span></span>
- <span data-ttu-id="b9dc8-256">为设备配置文件启用"创建/编辑/更新/读取/删除/查看报告"权限的自定义角色</span><span class="sxs-lookup"><span data-stu-id="b9dc8-256">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="b9dc8-257">全局管理员</span><span class="sxs-lookup"><span data-stu-id="b9dc8-257">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="b9dc8-258">通过 OMA-URI 部署策略</span><span class="sxs-lookup"><span data-stu-id="b9dc8-258">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="b9dc8-259">**Microsoft Endpoint Manager管理中心 (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform： Windows 10 and later & Profile： Custom**</span><span class="sxs-lookup"><span data-stu-id="b9dc8-259">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="b9dc8-260">对于每个组，创建 OMA-URI 规则：</span><span class="sxs-lookup"><span data-stu-id="b9dc8-260">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="b9dc8-261">OMA-URI： </span><span class="sxs-lookup"><span data-stu-id="b9dc8-261">OMA-URI:</span></span>

      <span data-ttu-id="b9dc8-262">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="b9dc8-262">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="b9dc8-263">例如，对于 **示例中的任何可移动存储和 CD/DVD** 组，该链接必须为：</span><span class="sxs-lookup"><span data-stu-id="b9dc8-263">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="b9dc8-264">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="b9dc8-264">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="b9dc8-265">数据类型：String (XML 文件) </span><span class="sxs-lookup"><span data-stu-id="b9dc8-265">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="STRING 文件的 xml 数据类型":::

2. <span data-ttu-id="b9dc8-267">对于每个策略，还要创建 OMA-URI：</span><span class="sxs-lookup"><span data-stu-id="b9dc8-267">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="b9dc8-268">OMA-URI： </span><span class="sxs-lookup"><span data-stu-id="b9dc8-268">OMA-URI:</span></span>

      <span data-ttu-id="b9dc8-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="b9dc8-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="b9dc8-270">例如，对于示例中 **的"阻止写入和执行访问但允许批准的 USB"** 规则，该链接必须是：</span><span class="sxs-lookup"><span data-stu-id="b9dc8-270">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="b9dc8-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="b9dc8-272">数据类型：String (XML 文件) </span><span class="sxs-lookup"><span data-stu-id="b9dc8-272">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" alt-text="STRING 文件的 XML 文件的数据类型":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="b9dc8-274">使用 Intune 用户界面部署和管理策略</span><span class="sxs-lookup"><span data-stu-id="b9dc8-274">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="b9dc8-275">此功能尚不可用。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-275">This capability is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="b9dc8-276">在 Microsoft Defender for Endpoint 存储设备控件可移动访问控件数据</span><span class="sxs-lookup"><span data-stu-id="b9dc8-276">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="b9dc8-277">安全Microsoft 365门户显示受设备控件可移动控件和访问控制存储的可移动存储。</span><span class="sxs-lookup"><span data-stu-id="b9dc8-277">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="b9dc8-278">若要访问Microsoft 365安全性，您必须具有以下订阅：</span><span class="sxs-lookup"><span data-stu-id="b9dc8-278">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="b9dc8-279">Microsoft 365 E5 报告</span><span class="sxs-lookup"><span data-stu-id="b9dc8-279">Microsoft 365 for E5 reporting</span></span>

```
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
