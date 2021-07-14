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
ms.openlocfilehash: 801d94eb769c6b738a1d4c011b67f8a2a7cf81f1
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430800"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="0380c-104">Microsoft Defender for Endpoint 设备控件可移动存储访问控制</span><span class="sxs-lookup"><span data-stu-id="0380c-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="0380c-105">Microsoft Defender for Endpoint 设备控制可移动存储访问控制使你能够执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="0380c-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>

- <span data-ttu-id="0380c-106">审核，允许或阻止对可移动存储进行读取、写入或执行访问（带排除或不排除）</span><span class="sxs-lookup"><span data-stu-id="0380c-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="0380c-107">Privilege</span><span class="sxs-lookup"><span data-stu-id="0380c-107">Privilege</span></span> |<span data-ttu-id="0380c-108">权限</span><span class="sxs-lookup"><span data-stu-id="0380c-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="0380c-109">Access</span><span class="sxs-lookup"><span data-stu-id="0380c-109">Access</span></span>    |  <span data-ttu-id="0380c-110">读取、写入、执行</span><span class="sxs-lookup"><span data-stu-id="0380c-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="0380c-111">操作模式</span><span class="sxs-lookup"><span data-stu-id="0380c-111">Action Mode</span></span>    |    <span data-ttu-id="0380c-112">审核、允许、阻止</span><span class="sxs-lookup"><span data-stu-id="0380c-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="0380c-113">云解决方案提供商支持</span><span class="sxs-lookup"><span data-stu-id="0380c-113">CSP Support</span></span>   |   <span data-ttu-id="0380c-114">是</span><span class="sxs-lookup"><span data-stu-id="0380c-114">Yes</span></span>      |
|<span data-ttu-id="0380c-115">GPO 支持</span><span class="sxs-lookup"><span data-stu-id="0380c-115">GPO Support</span></span>    |   <span data-ttu-id="0380c-116">是</span><span class="sxs-lookup"><span data-stu-id="0380c-116">Yes</span></span>      |
|<span data-ttu-id="0380c-117">基于用户的支持</span><span class="sxs-lookup"><span data-stu-id="0380c-117">User-based Support</span></span>     |   <span data-ttu-id="0380c-118">是</span><span class="sxs-lookup"><span data-stu-id="0380c-118">Yes</span></span>      |
|<span data-ttu-id="0380c-119">基于计算机的支持</span><span class="sxs-lookup"><span data-stu-id="0380c-119">Machine-based Support</span></span>    |    <span data-ttu-id="0380c-120">是</span><span class="sxs-lookup"><span data-stu-id="0380c-120">Yes</span></span>     |

## <a name="licensing"></a><span data-ttu-id="0380c-121">授权</span><span class="sxs-lookup"><span data-stu-id="0380c-121">Licensing</span></span>

<span data-ttu-id="0380c-122">在开始使用"可移动存储访问控制"之前，应[确认Microsoft 365订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="0380c-122">Before you get started with Removable Storage Access Control, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="0380c-123">若要访问并使用可移动存储访问控制，您必须具有以下权限：</span><span class="sxs-lookup"><span data-stu-id="0380c-123">To access and use Removable Storage Access Control, you must have the following:</span></span>

- <span data-ttu-id="0380c-124">Microsoft 365 E3/策略部署。</span><span class="sxs-lookup"><span data-stu-id="0380c-124">Microsoft 365 E3 for functionality/policy deployment.</span></span>
- <span data-ttu-id="0380c-125">Microsoft 365 E5报告功能。</span><span class="sxs-lookup"><span data-stu-id="0380c-125">Microsoft 365 E5 for reporting.</span></span>

## <a name="prepare-your-endpoints"></a><span data-ttu-id="0380c-126">准备终结点</span><span class="sxs-lookup"><span data-stu-id="0380c-126">Prepare your endpoints</span></span>

<span data-ttu-id="0380c-127">在存储 **4.18.2103.3** 或更高版本的 Windows 10 设备上部署可移动访问控制。</span><span class="sxs-lookup"><span data-stu-id="0380c-127">Deploy Removable Storage Access Control on Windows 10 devices that have antimalware client version **4.18.2103.3 or later**.</span></span>

- <span data-ttu-id="0380c-128">**4.18.2104 或更高版本**：添加 SerialNumberId、VID_PID、基于 filepath 的 GPO 支持、ComputerSid</span><span class="sxs-lookup"><span data-stu-id="0380c-128">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span></span>

- <span data-ttu-id="0380c-129">**4.18.2105** 或更高版本：添加对 HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId 的通配符支持、特定计算机上特定用户的组合、可删除的 SSD (SanDisk 极性 SSD) /USB 附加 SCSI (UAS) 支持</span><span class="sxs-lookup"><span data-stu-id="0380c-129">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

- <span data-ttu-id="0380c-130">**4.18.2107 或** 更高版本：添加 Windows 可移植设备 (WPD) 支持 (移动设备（如平板电脑或) </span><span class="sxs-lookup"><span data-stu-id="0380c-130">**4.18.2107 or later**: Add Windows Portable Device (WPD) support (for mobile devices, such as tablets)</span></span>

:::image type="content" source="images/powershell.png" alt-text="PowerShell 接口":::

> [!NOTE]
> <span data-ttu-id="0380c-132">任何Windows 安全中心组件都不需要处于活动状态，您可以运行"可移动存储访问控制"，而不受Windows 安全中心状态。</span><span class="sxs-lookup"><span data-stu-id="0380c-132">None of Windows Security components need to be active, you can run Removable Storage Access Control independent of Windows Security status.</span></span>

## <a name="policy-properties"></a><span data-ttu-id="0380c-133">策略属性</span><span class="sxs-lookup"><span data-stu-id="0380c-133">Policy properties</span></span>

<span data-ttu-id="0380c-134">可以使用以下属性创建可移动存储组：</span><span class="sxs-lookup"><span data-stu-id="0380c-134">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="0380c-135">**属性名称：组 ID**</span><span class="sxs-lookup"><span data-stu-id="0380c-135">**Property name: Group Id**</span></span>

1. <span data-ttu-id="0380c-136">说明 [：GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)是一个唯一 ID，表示组，将在策略中使用。</span><span class="sxs-lookup"><span data-stu-id="0380c-136">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="0380c-137">**属性名称：DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="0380c-137">**Property name: DescriptorIdList**</span></span>

2. <span data-ttu-id="0380c-138">说明：列出你想要在组中覆盖的设备属性。</span><span class="sxs-lookup"><span data-stu-id="0380c-138">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="0380c-139">有关每个设备属性的详细信息， **请参阅上面的设备** 属性部分。</span><span class="sxs-lookup"><span data-stu-id="0380c-139">For each device property, see **Device Properties** section above for more detail.</span></span>

3. <span data-ttu-id="0380c-140">选项：</span><span class="sxs-lookup"><span data-stu-id="0380c-140">Options:</span></span>
    - <span data-ttu-id="0380c-141">PrimaryId</span><span class="sxs-lookup"><span data-stu-id="0380c-141">PrimaryId</span></span>
        - <span data-ttu-id="0380c-142">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="0380c-142">RemovableMediaDevices</span></span>
        - <span data-ttu-id="0380c-143">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="0380c-143">CdRomDevices</span></span>
        - <span data-ttu-id="0380c-144">WpdDevices</span><span class="sxs-lookup"><span data-stu-id="0380c-144">WpdDevices</span></span>
    - <span data-ttu-id="0380c-145">DeviceId</span><span class="sxs-lookup"><span data-stu-id="0380c-145">DeviceId</span></span>
    - <span data-ttu-id="0380c-146">HardwareId</span><span class="sxs-lookup"><span data-stu-id="0380c-146">HardwareId</span></span>
    - <span data-ttu-id="0380c-147">InstancePathId：InstancePathId 是一个唯一标识系统中设备的字符串，例如 USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0。</span><span class="sxs-lookup"><span data-stu-id="0380c-147">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="0380c-148">末尾的号码 (例如 0&**0**) 表示可用插槽，并且可能会从设备更改为设备。</span><span class="sxs-lookup"><span data-stu-id="0380c-148">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="0380c-149">为获得最佳结果，请结尾使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0380c-149">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="0380c-150">例如，USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="0380c-150">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="0380c-151">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="0380c-151">FriendlyNameId</span></span>
    - <span data-ttu-id="0380c-152">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="0380c-152">SerialNumberId</span></span>
    - <span data-ttu-id="0380c-153">VID</span><span class="sxs-lookup"><span data-stu-id="0380c-153">VID</span></span>
    - <span data-ttu-id="0380c-154">PID</span><span class="sxs-lookup"><span data-stu-id="0380c-154">PID</span></span>
    - <span data-ttu-id="0380c-155">VID_PID</span><span class="sxs-lookup"><span data-stu-id="0380c-155">VID_PID</span></span>
        - <span data-ttu-id="0380c-156">0751_55E0：匹配此精确的 VID/PID 对</span><span class="sxs-lookup"><span data-stu-id="0380c-156">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="0380c-157">_55E0：将任何媒体与 PID=55E0 匹配</span><span class="sxs-lookup"><span data-stu-id="0380c-157">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="0380c-158">0751_：将任何媒体与 VID=0751 匹配</span><span class="sxs-lookup"><span data-stu-id="0380c-158">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="0380c-159">**属性名称：MatchType**</span><span class="sxs-lookup"><span data-stu-id="0380c-159">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="0380c-160">说明：当 DescriptorIDList 中使用多个设备属性时，MatchType 定义关系。</span><span class="sxs-lookup"><span data-stu-id="0380c-160">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

2. <span data-ttu-id="0380c-161">选项：</span><span class="sxs-lookup"><span data-stu-id="0380c-161">Options:</span></span>

    - <span data-ttu-id="0380c-162">MatchAll：DescriptorIdList 下的任何属性将为 **And** 关系;例如，如果管理员将 DeviceID 和 InstancePathID 放在每个连接的 USB 上，系统将检查 USB 是否同时满足这两个值。</span><span class="sxs-lookup"><span data-stu-id="0380c-162">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>
    - <span data-ttu-id="0380c-163">MatchAny：DescriptorIdList 下的属性将为 **Or** 关系;例如，如果管理员将 DeviceID 和 InstancePathID 放在每个连接的 USB 上，只要 USB 具有相同的 **DeviceID** 或 **InstanceID** 值，系统就会执行强制操作。</span><span class="sxs-lookup"><span data-stu-id="0380c-163">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="0380c-164">以下是访问控制策略属性：</span><span class="sxs-lookup"><span data-stu-id="0380c-164">Following are the access control policy properties:</span></span>

<span data-ttu-id="0380c-165">**属性名称：PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="0380c-165">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="0380c-166">说明 [：GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)是一个唯一 ID，表示策略，将用于报告和疑难解答。</span><span class="sxs-lookup"><span data-stu-id="0380c-166">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="0380c-167">**属性名称：IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="0380c-167">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="0380c-168">说明： (策略) 的组。</span><span class="sxs-lookup"><span data-stu-id="0380c-168">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="0380c-169">如果添加了多个组，该策略将应用于所有这些组的任何媒体。</span><span class="sxs-lookup"><span data-stu-id="0380c-169">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

2. <span data-ttu-id="0380c-170">选项：必须在此实例使用组 ID/GUID。</span><span class="sxs-lookup"><span data-stu-id="0380c-170">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="0380c-171">以下示例显示 GroupID 的用法：</span><span class="sxs-lookup"><span data-stu-id="0380c-171">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="0380c-172">**属性名称：ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="0380c-172">**Property name: ExcludedIDList**</span></span>

<span data-ttu-id="0380c-173">说明： (策略) 的组。</span><span class="sxs-lookup"><span data-stu-id="0380c-173">Description: The group(s) that the policy will not be applied to.</span></span>

<span data-ttu-id="0380c-174">选项：必须在此实例使用组 ID/GUID。</span><span class="sxs-lookup"><span data-stu-id="0380c-174">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="0380c-175">**属性名称：条目 ID**</span><span class="sxs-lookup"><span data-stu-id="0380c-175">**Property name: Entry Id**</span></span>

1. <span data-ttu-id="0380c-176">说明：一个 PolicyRule 可以有多个条目;每个具有唯一 GUID 的条目告知设备控件一个限制。</span><span class="sxs-lookup"><span data-stu-id="0380c-176">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="0380c-177">**属性名称：Type**</span><span class="sxs-lookup"><span data-stu-id="0380c-177">**Property name: Type**</span></span>

1. <span data-ttu-id="0380c-178">说明：定义 IncludedIDList 中可移动存储组的操作。</span><span class="sxs-lookup"><span data-stu-id="0380c-178">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="0380c-179">强制：允许或拒绝</span><span class="sxs-lookup"><span data-stu-id="0380c-179">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="0380c-180">审核：AuditAllowed 或 AuditDenied</span><span class="sxs-lookup"><span data-stu-id="0380c-180">Audit: AuditAllowed or AuditDenied</span></span> 

2. <span data-ttu-id="0380c-181">选项：</span><span class="sxs-lookup"><span data-stu-id="0380c-181">Options:</span></span>

    - <span data-ttu-id="0380c-182">允许</span><span class="sxs-lookup"><span data-stu-id="0380c-182">Allow</span></span>
    - <span data-ttu-id="0380c-183">拒绝</span><span class="sxs-lookup"><span data-stu-id="0380c-183">Deny</span></span>
    - <span data-ttu-id="0380c-184">AuditAllowed：定义允许访问时的通知和事件</span><span class="sxs-lookup"><span data-stu-id="0380c-184">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="0380c-185">AuditDenied：定义拒绝访问时的通知和事件;必须配合拒绝 **条目** 一起工作。</span><span class="sxs-lookup"><span data-stu-id="0380c-185">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="0380c-186">当同一媒体存在冲突类型时，系统将应用策略中的第一个冲突类型。</span><span class="sxs-lookup"><span data-stu-id="0380c-186">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="0380c-187">冲突类型的一个示例是 **"允许"和**"**拒绝"。**</span><span class="sxs-lookup"><span data-stu-id="0380c-187">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="0380c-188">**属性名称：Sid**</span><span class="sxs-lookup"><span data-stu-id="0380c-188">**Property name: Sid**</span></span>

<span data-ttu-id="0380c-189">说明：本地计算机 Sid 或 AD 对象的 Sid 定义是否对特定用户或用户组应用此策略;一个条目最多可具有一个 Sid 和一个不带任何 Sid 的条目，这意味着在计算机中应用策略。</span><span class="sxs-lookup"><span data-stu-id="0380c-189">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific user or user group; one entry can have a maximum of one Sid and an entry without any Sid means applying the policy over the machine.</span></span>

<span data-ttu-id="0380c-190">**属性名称：ComputerSid**</span><span class="sxs-lookup"><span data-stu-id="0380c-190">**Property name: ComputerSid**</span></span>

<span data-ttu-id="0380c-191">说明：本地计算机 Sid 或 AD 对象的 Sid 定义是否对特定计算机或计算机组应用此策略;一个条目最多可具有一个 ComputerSid，而一个条目没有任何 ComputerSid 意味着将策略应用到计算机。</span><span class="sxs-lookup"><span data-stu-id="0380c-191">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific machine or machine group; one entry can have a maximum of one ComputerSid and an entry without any ComputerSid means applying the policy over the machine.</span></span> <span data-ttu-id="0380c-192">如果要将条目应用于特定用户和特定计算机，请同时将 Sid 和 ComputerSid 添加到同一条目中。</span><span class="sxs-lookup"><span data-stu-id="0380c-192">If you want to apply an Entry to a specific user and specific machine, add both Sid and ComputerSid into the same Entry.</span></span>

<span data-ttu-id="0380c-193">**属性名称：Options**</span><span class="sxs-lookup"><span data-stu-id="0380c-193">**Property name: Options**</span></span>

<span data-ttu-id="0380c-194">说明：定义是否显示通知。</span><span class="sxs-lookup"><span data-stu-id="0380c-194">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="可在其中查看设备状态的屏幕":::

<span data-ttu-id="0380c-196">选项：0-4。</span><span class="sxs-lookup"><span data-stu-id="0380c-196">Options: 0-4.</span></span> <span data-ttu-id="0380c-197">选择"类型允许"或"拒绝"时：</span><span class="sxs-lookup"><span data-stu-id="0380c-197">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="0380c-198">0：无</span><span class="sxs-lookup"><span data-stu-id="0380c-198">0: nothing</span></span>
   - <span data-ttu-id="0380c-199">4：对此条目 **禁用 AuditAllowed** **和 AuditDenied。**</span><span class="sxs-lookup"><span data-stu-id="0380c-199">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="0380c-200">即使 **发生阻止** 且已配置 **AuditDenied** 设置，系统也将不会显示通知。</span><span class="sxs-lookup"><span data-stu-id="0380c-200">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="0380c-201">选择" **类型 AuditAllowed"** 或 **"AuditDenied"** 时：</span><span class="sxs-lookup"><span data-stu-id="0380c-201">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="0380c-202">0：无</span><span class="sxs-lookup"><span data-stu-id="0380c-202">0: nothing</span></span>
   - <span data-ttu-id="0380c-203">1：显示通知</span><span class="sxs-lookup"><span data-stu-id="0380c-203">1: show notification</span></span>
   - <span data-ttu-id="0380c-204">2：发送事件</span><span class="sxs-lookup"><span data-stu-id="0380c-204">2: send event</span></span>
   - <span data-ttu-id="0380c-205">3：显示通知和发送事件</span><span class="sxs-lookup"><span data-stu-id="0380c-205">3: show notification and send event</span></span>

<span data-ttu-id="0380c-206">**属性名称：AccessMask**</span><span class="sxs-lookup"><span data-stu-id="0380c-206">**Property name: AccessMask**</span></span>

<span data-ttu-id="0380c-207">说明：定义访问权限。</span><span class="sxs-lookup"><span data-stu-id="0380c-207">Description: Defines the access.</span></span>

<span data-ttu-id="0380c-208">选项 1-7：</span><span class="sxs-lookup"><span data-stu-id="0380c-208">Options 1-7:</span></span>
  - <span data-ttu-id="0380c-209">1：读取</span><span class="sxs-lookup"><span data-stu-id="0380c-209">1: Read</span></span>
  - <span data-ttu-id="0380c-210">2：写入</span><span class="sxs-lookup"><span data-stu-id="0380c-210">2: Write</span></span>
  - <span data-ttu-id="0380c-211">3：读取和写入</span><span class="sxs-lookup"><span data-stu-id="0380c-211">3: Read and Write</span></span>
  - <span data-ttu-id="0380c-212">4：执行</span><span class="sxs-lookup"><span data-stu-id="0380c-212">4: Execute</span></span>
  - <span data-ttu-id="0380c-213">5：读取和执行</span><span class="sxs-lookup"><span data-stu-id="0380c-213">5: Read and Execute</span></span>
  - <span data-ttu-id="0380c-214">6：写入和执行</span><span class="sxs-lookup"><span data-stu-id="0380c-214">6: Write and Execute</span></span>
  - <span data-ttu-id="0380c-215">7：读取、写入和执行</span><span class="sxs-lookup"><span data-stu-id="0380c-215">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="0380c-216">常见的可移动存储访问控制方案</span><span class="sxs-lookup"><span data-stu-id="0380c-216">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="0380c-217">为了帮助你熟悉 Microsoft Defender for Endpoint Removable 存储访问控制，我们将一些常见方案放在一起供你遵循。</span><span class="sxs-lookup"><span data-stu-id="0380c-217">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="0380c-218">方案 1：阻止对全部 USB 执行写入和执行访问，但允许特定批准的 USB</span><span class="sxs-lookup"><span data-stu-id="0380c-218">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="0380c-219">创建组</span><span class="sxs-lookup"><span data-stu-id="0380c-219">Create groups</span></span>

    1. <span data-ttu-id="0380c-220">组 1：任何可移动存储和 CD/DVD。</span><span class="sxs-lookup"><span data-stu-id="0380c-220">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="0380c-221">可移动存储和 CD/DVD 的一个示例是：示例 Any [Removable 存储 and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file中的组 **9b28fae8-72f7-4267-a1a5-685f747a7146。**</span><span class="sxs-lookup"><span data-stu-id="0380c-221">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="0380c-222">组 2：基于设备属性批准的 USB。</span><span class="sxs-lookup"><span data-stu-id="0380c-222">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="0380c-223">此用例的一个示例是：示例已批准 [USB Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件中的实例 ID – 组 **65fa649a-a111-4912-9294-fb6337a25038。**</span><span class="sxs-lookup"><span data-stu-id="0380c-223">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0380c-224">您必须在 值 `&` 中 `&amp;` 将 替换为 。</span><span class="sxs-lookup"><span data-stu-id="0380c-224">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="0380c-225">创建策略</span><span class="sxs-lookup"><span data-stu-id="0380c-225">Create policy</span></span>

    1. <span data-ttu-id="0380c-226">策略 1：阻止写入和执行访问，但允许批准的 USB。</span><span class="sxs-lookup"><span data-stu-id="0380c-226">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="0380c-227">此用例的一个示例是：示例方案 [1](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)阻止写入和执行访问但允许批准的 USBs.xml文件中的 PolicyRule **c544a991-5786-4402-949e-a032cb790d0e。**</span><span class="sxs-lookup"><span data-stu-id="0380c-227">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="0380c-228">策略 2：审核对允许的 USB 的写入和执行访问权限。</span><span class="sxs-lookup"><span data-stu-id="0380c-228">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="0380c-229">此用例的一个示例是：对批准的 [USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件进行审核写入和执行访问示例中的 PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c。**</span><span class="sxs-lookup"><span data-stu-id="0380c-229">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="0380c-230">方案 2：审核对全部（但阻止特定未批准的 USB）的写入和执行访问权限</span><span class="sxs-lookup"><span data-stu-id="0380c-230">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="0380c-231">创建组</span><span class="sxs-lookup"><span data-stu-id="0380c-231">Create groups</span></span>

    1. <span data-ttu-id="0380c-232">组 1：任何可移动存储和 CD/DVD。</span><span class="sxs-lookup"><span data-stu-id="0380c-232">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="0380c-233">此用例的一个示例是：示例 Any [Removable 存储 and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file中的 Group **9b28fae8-72f7-4267-a1a5-685f747a7146。**</span><span class="sxs-lookup"><span data-stu-id="0380c-233">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="0380c-234">组 2：基于设备属性（例如，供应商 ID/产品 ID、友好名称 – 组 **65fa649a-a111-4912-9294-fb6337a25038）** 的未批准 USB Group.xml文件中未批准的 [USB。](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="0380c-234">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="0380c-235">您必须在 值 `&` 中 `&amp;` 将 替换为 。</span><span class="sxs-lookup"><span data-stu-id="0380c-235">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="0380c-236">创建策略</span><span class="sxs-lookup"><span data-stu-id="0380c-236">Create policy</span></span>

    1. <span data-ttu-id="0380c-237">策略 1：阻止对全部（但阻止特定未批准的 USB）的写入和执行访问。</span><span class="sxs-lookup"><span data-stu-id="0380c-237">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="0380c-238">此用例的一个示例是：示例方案 2 审核写入和执行对除阻止特定未批准的 [USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件的访问中的 PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98。**</span><span class="sxs-lookup"><span data-stu-id="0380c-238">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="0380c-239">策略 2：审核写入和执行对他人的访问。</span><span class="sxs-lookup"><span data-stu-id="0380c-239">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="0380c-240">此用例的一个示例是：对 [others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)文件进行审核写入和执行访问示例中的 PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48。**</span><span class="sxs-lookup"><span data-stu-id="0380c-240">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="0380c-241">通过组策略部署和管理策略</span><span class="sxs-lookup"><span data-stu-id="0380c-241">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="0380c-242">通过"存储访问控制"功能，可以通过组策略将策略应用于用户或设备，或同时应用于两者。</span><span class="sxs-lookup"><span data-stu-id="0380c-242">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="0380c-243">授权</span><span class="sxs-lookup"><span data-stu-id="0380c-243">Licensing</span></span>

<span data-ttu-id="0380c-244">在开始使用"可移动存储访问控制"之前，必须确认Microsoft 365 [订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。</span><span class="sxs-lookup"><span data-stu-id="0380c-244">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="0380c-245">若要访问和使用可移动存储访问控制，您必须具有Microsoft 365 E3或Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="0380c-245">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="0380c-246">通过组策略部署策略</span><span class="sxs-lookup"><span data-stu-id="0380c-246">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="0380c-247">将所有组组合到 `<Groups>` `</Groups>` 一个 xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="0380c-247">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="0380c-248">下图演示了方案 [1：](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)阻止对全部 USB 进行写入和执行访问，但允许特定批准的 USB 的示例。</span><span class="sxs-lookup"><span data-stu-id="0380c-248">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="显示允许在设备上允许特定批准的 USB 的配置设置的屏幕":::
    
2. <span data-ttu-id="0380c-250">将所有规则合并到 `<PolicyRules>` `</PolicyRules>` 一个 xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="0380c-250">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="0380c-251">如果要限制特定用户，请使用 Entry 中的 SID 属性。</span><span class="sxs-lookup"><span data-stu-id="0380c-251">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="0380c-252">如果策略条目中没有任何 SID，则条目将应用于计算机的每一个登录实例。</span><span class="sxs-lookup"><span data-stu-id="0380c-252">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="0380c-253">下图演示了 SID 属性的用法，以及方案 [1：](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)阻止对全部但允许特定批准的 USB 的写入和执行访问的示例。</span><span class="sxs-lookup"><span data-stu-id="0380c-253">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="显示指示 SID 属性属性使用情况的代码的屏幕":::

3. <span data-ttu-id="0380c-255">在网络共享文件夹中保存规则和组 XML 文件，将网络共享文件夹路径放入组策略设置：**计算机配置 -> 管理模板 -> Windows 组件 -> Microsoft Defender 防病毒 -> 设备控制："定义设备** 控制策略组"和"定义设备控制策略规则"。</span><span class="sxs-lookup"><span data-stu-id="0380c-255">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="0380c-256">目标计算机必须能够访问网络共享才能拥有策略。</span><span class="sxs-lookup"><span data-stu-id="0380c-256">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="0380c-257">但是，读取策略后，不再需要网络连接，即使在计算机重新启动后也不例外。</span><span class="sxs-lookup"><span data-stu-id="0380c-257">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="设备控制屏幕":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="0380c-259">通过 Intune OMA-URI 部署和管理策略</span><span class="sxs-lookup"><span data-stu-id="0380c-259">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="0380c-260">通过可移动存储访问控制功能，你可以将策略通过 OMA-URI 应用到用户或设备，或同时应用到两者。</span><span class="sxs-lookup"><span data-stu-id="0380c-260">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="0380c-261">授权</span><span class="sxs-lookup"><span data-stu-id="0380c-261">Licensing</span></span>

<span data-ttu-id="0380c-262">在开始使用"可移动存储访问控制"之前，必须确认Microsoft 365 [订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。</span><span class="sxs-lookup"><span data-stu-id="0380c-262">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="0380c-263">若要访问和使用可移动存储访问控制，您必须具有Microsoft 365 E3或Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="0380c-263">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="0380c-264">权限</span><span class="sxs-lookup"><span data-stu-id="0380c-264">Permission</span></span>

<span data-ttu-id="0380c-265">对于 Intune 中的策略部署，该帐户必须具有创建、编辑、更新或删除设备配置文件的权限。</span><span class="sxs-lookup"><span data-stu-id="0380c-265">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="0380c-266">可以创建自定义角色或使用具有这些权限的任何内置角色。</span><span class="sxs-lookup"><span data-stu-id="0380c-266">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="0380c-267">策略和配置文件管理器角色</span><span class="sxs-lookup"><span data-stu-id="0380c-267">Policy and profile Manager role</span></span>
- <span data-ttu-id="0380c-268">为设备配置文件启用"创建/编辑/更新/读取/删除/查看报告"权限的自定义角色</span><span class="sxs-lookup"><span data-stu-id="0380c-268">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="0380c-269">全局管理员</span><span class="sxs-lookup"><span data-stu-id="0380c-269">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="0380c-270">通过 OMA-URI 部署策略</span><span class="sxs-lookup"><span data-stu-id="0380c-270">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="0380c-271">**Microsoft Endpoint Manager管理中心 (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform： Windows 10 and later & Profile： Custom**</span><span class="sxs-lookup"><span data-stu-id="0380c-271">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="0380c-272">对于每个组，创建 OMA-URI 规则：</span><span class="sxs-lookup"><span data-stu-id="0380c-272">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="0380c-273">OMA-URI： </span><span class="sxs-lookup"><span data-stu-id="0380c-273">OMA-URI:</span></span>

      <span data-ttu-id="0380c-274">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="0380c-274">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="0380c-275">例如，对于 **示例中的任何可移动存储和 CD/DVD** 组，该链接必须为：</span><span class="sxs-lookup"><span data-stu-id="0380c-275">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="0380c-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="0380c-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="0380c-277">数据类型：String (XML 文件) </span><span class="sxs-lookup"><span data-stu-id="0380c-277">Data Type: String (XML file)</span></span>

2. <span data-ttu-id="0380c-278">对于每个策略，还要创建 OMA-URI：</span><span class="sxs-lookup"><span data-stu-id="0380c-278">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="0380c-279">OMA-URI： </span><span class="sxs-lookup"><span data-stu-id="0380c-279">OMA-URI:</span></span>

      <span data-ttu-id="0380c-280">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="0380c-280">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="0380c-281">例如，对于示例中 **的"阻止写入和执行访问但允许批准的 USB"** 规则，该链接必须是：</span><span class="sxs-lookup"><span data-stu-id="0380c-281">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="0380c-282">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData。</span><span class="sxs-lookup"><span data-stu-id="0380c-282">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="0380c-283">数据类型：String (XML 文件) </span><span class="sxs-lookup"><span data-stu-id="0380c-283">Data Type: String (XML file)</span></span>


## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="0380c-284">使用 Intune 用户界面部署和管理策略</span><span class="sxs-lookup"><span data-stu-id="0380c-284">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="0380c-285">此功能 (Microsoft Endpoint Manager 管理中心 (> 设备 > 配置文件 > 创建配置文件 https://endpoint.microsoft.com/) > 平台：Windows 10 及更高版本 & 配置文件：设备控制) 尚不可用。</span><span class="sxs-lookup"><span data-stu-id="0380c-285">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="0380c-286">在 Microsoft Defender for Endpoint 存储设备控件可移动访问控件数据</span><span class="sxs-lookup"><span data-stu-id="0380c-286">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="0380c-287">安全Microsoft 365门户显示受设备控件可移动控件和访问控制存储的可移动存储。</span><span class="sxs-lookup"><span data-stu-id="0380c-287">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="0380c-288">若要访问Microsoft 365安全性，您必须具有以下订阅：</span><span class="sxs-lookup"><span data-stu-id="0380c-288">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="0380c-289">Microsoft 365 E5 报告</span><span class="sxs-lookup"><span data-stu-id="0380c-289">Microsoft 365 for E5 reporting</span></span>

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

## <a name="frequently-asked-questions"></a><span data-ttu-id="0380c-291">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="0380c-291">Frequently asked questions</span></span>

<span data-ttu-id="0380c-292">**最大 USB 数量的可移动存储媒体限制是什么？**</span><span class="sxs-lookup"><span data-stu-id="0380c-292">**What is the removable storage media limitation for the maximum number of USBs?**</span></span>

<span data-ttu-id="0380c-293">我们已验证一个具有 100，000 个媒体的 USB 组 - 大小最高为 7 MB。</span><span class="sxs-lookup"><span data-stu-id="0380c-293">We have validated one USB group with 100,000 media - up to 7 MB in size.</span></span> <span data-ttu-id="0380c-294">该策略在 Intune 和 GPO 中均有效，而未发生性能问题。</span><span class="sxs-lookup"><span data-stu-id="0380c-294">The policy works in both Intune and GPO without performance issues.</span></span>

<span data-ttu-id="0380c-295">**为什么策略不起作用？**</span><span class="sxs-lookup"><span data-stu-id="0380c-295">**Why does the policy not work?**</span></span>

<span data-ttu-id="0380c-296">最常见的原因是不需要反 [恶意软件客户端版本](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="0380c-296">The most common reason is there is no required [antimalware client version](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints).</span></span>

<span data-ttu-id="0380c-297">另一个原因是 XML 文件格式不正确，例如，未对 XML 文件中"&"字符使用正确的 markdown 格式，或者文本编辑器可能在文件的开头添加字节顺序标记 (BOM) 0xEF 0xBB 0xBF，这会导致 XML 分析不起作用。</span><span class="sxs-lookup"><span data-stu-id="0380c-297">Another reason could be that the XML file is not correctly formatted, for example, not using the correct markdown formatting for the "&" character in the XML file, or the text editor might add a byte order mark (BOM) 0xEF 0xBB 0xBF at the beginning of the files which causes the XML parsing not to work.</span></span> <span data-ttu-id="0380c-298">一个简单的解决方案是下载示例文件 [， ("](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)**原始**"，**然后选择"另** 存为) 然后更新。</span><span class="sxs-lookup"><span data-stu-id="0380c-298">One simple solution is to download the [sample file](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (select **Raw** and then **Save as**) and then update.</span></span>

<span data-ttu-id="0380c-299">如果有值并且策略通过组策略进行管理，请检查客户端设备是否可以访问策略 XML 路径。</span><span class="sxs-lookup"><span data-stu-id="0380c-299">If there is a value and the policy is managed via Group Policy, check whether the client device can access the policy XML path.</span></span>

<span data-ttu-id="0380c-300">**如何知道哪个计算机正在使用组织中过期的反恶意软件客户端版本？**</span><span class="sxs-lookup"><span data-stu-id="0380c-300">**How can I know which machine is using out of date antimalware client version in the organization?**</span></span>

<span data-ttu-id="0380c-301">可以使用以下查询在安全门户上获取反恶意软件Microsoft 365版本：</span><span class="sxs-lookup"><span data-stu-id="0380c-301">You can use following query to get antimalware client version on the Microsoft 365 security portal:</span></span>
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
