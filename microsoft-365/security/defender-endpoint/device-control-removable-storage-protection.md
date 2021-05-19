---
title: Microsoft Defender for Endpoint 设备控制可移动存储保护
description: 了解有助于防止用户或计算机或两者使用未经授权的可移动存储媒体的功能
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
ms.openlocfilehash: c9b97c2157ba8090628af23b2ab54cf38f04d8c6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538383"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a><span data-ttu-id="ab8f8-104">Microsoft Defender for Endpoint 设备控制可移动存储保护</span><span class="sxs-lookup"><span data-stu-id="ab8f8-104">Microsoft Defender for Endpoint Device Control Removable Storage Protection</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="ab8f8-105">Microsoft Defender for Endpoint 设备控制可移动存储保护可防止用户或计算机使用未经授权的可移动存储媒体。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-105">Microsoft Defender for Endpoint Device Control Removable Storage Protection prevents user or machine or both from using unauthorized removable storage media.</span></span>

## <a name="protection-policies"></a><span data-ttu-id="ab8f8-106">保护策略</span><span class="sxs-lookup"><span data-stu-id="ab8f8-106">Protection policies</span></span>

### <a name="device-installation"></a><span data-ttu-id="ab8f8-107">设备安装</span><span class="sxs-lookup"><span data-stu-id="ab8f8-107">Device installation</span></span>

<span data-ttu-id="ab8f8-108">**功能** - 根据各种设备属性阻止安装（包括或不排除）。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-108">**Capabilities** - Prevent installation with or without exclusion based on various device properties.</span></span>

<span data-ttu-id="ab8f8-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="ab8f8-109">**Description**</span></span>
- <span data-ttu-id="ab8f8-110">在计算机级别应用：同一策略适用于任何登录的用户。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-110">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="ab8f8-111">支持 MEM 和 GPO。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-111">Supports MEM and GPO.</span></span>
- <span data-ttu-id="ab8f8-112">支持的'[设备属性](#device-properties)'，如所列。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-112">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="ab8f8-113">有关此Windows，请参阅如何使用 Microsoft Defender for Endpoint 控制 USB 设备和其他[可移动媒体](control-usb-devices-using-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-113">For more information on Windows, see [How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).</span></span>

<span data-ttu-id="ab8f8-114">**支持的平台**- Windows 10</span><span class="sxs-lookup"><span data-stu-id="ab8f8-114">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="ab8f8-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="ab8f8-115">**Description**</span></span>
- <span data-ttu-id="ab8f8-116">在计算机级别应用：相同的策略适用于任何登录的用户</span><span class="sxs-lookup"><span data-stu-id="ab8f8-116">Applied at machine level: the same policy applies for any logged on user</span></span>
- <span data-ttu-id="ab8f8-117">有关 macOS 特定的信息，请参阅 [macOS 的设备控件](mac-device-control-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-117">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="ab8f8-118">**支持的平台** - macOS Catalina 10.15.4+ (启用了系统扩展) </span><span class="sxs-lookup"><span data-stu-id="ab8f8-118">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="removable-storage-access-control"></a><span data-ttu-id="ab8f8-119">可移动存储访问控制</span><span class="sxs-lookup"><span data-stu-id="ab8f8-119">Removable storage Access Control</span></span>

<span data-ttu-id="ab8f8-120">**Capabilities**</span><span class="sxs-lookup"><span data-stu-id="ab8f8-120">**Capabilities**</span></span>
- <span data-ttu-id="ab8f8-121">*审核* 基于各种设备属性对可移动存储的读取、写入或执行访问（带排除或不排除）。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-121">*Audit* Read or Write or Execute access to removable storage based on various device properties, with or without an exclusion.</span></span>
- <span data-ttu-id="ab8f8-122">*阻止* 读取或写入或执行访问（带排除或不排除） - 允许基于各种设备属性的特定设备。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-122">*Prevent* Read or Write or Execute access with or without an exclusion - Allow specific device based on various device properties.</span></span>

<span data-ttu-id="ab8f8-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="ab8f8-123">**Description**</span></span>
- <span data-ttu-id="ab8f8-124">在计算机或用户或两者中应用 – 仅允许对特定计算机上特定可移动存储执行读/写/执行访问的特定人员。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-124">Applied at either machine or user or both – only allow specific people performing Read/Write/Execute access to specific removable storage on specific machine.</span></span>
- <span data-ttu-id="ab8f8-125">支持 MEM OMA-URI 和 GPO。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-125">Support MEM OMA-URI and GPO.</span></span>
- <span data-ttu-id="ab8f8-126">支持的'[设备属性](#device-properties)'，如所列。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-126">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="ab8f8-127">有关 Windows 中的功能，请参阅[可移动存储访问控制](device-control-removable-storage-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-127">For feature in Windows, see [Removable storage Access Control](device-control-removable-storage-access-control.md).</span></span>

<span data-ttu-id="ab8f8-128">**支持的平台**- Windows 10</span><span class="sxs-lookup"><span data-stu-id="ab8f8-128">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="ab8f8-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="ab8f8-129">**Description**</span></span>
- <span data-ttu-id="ab8f8-130">在计算机级别应用：同一策略适用于任何登录的用户。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-130">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="ab8f8-131">有关 macOS 特定的信息，请参阅 [macOS 的设备控件](mac-device-control-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-131">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="ab8f8-132">**支持的平台** - macOS Catalina 10.15.4+ (启用了系统扩展) </span><span class="sxs-lookup"><span data-stu-id="ab8f8-132">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="windows-portable-device-access-control"></a><span data-ttu-id="ab8f8-133">Windows便携设备访问控制</span><span class="sxs-lookup"><span data-stu-id="ab8f8-133">Windows Portable Device Access Control</span></span>

<span data-ttu-id="ab8f8-134">**功能**- 拒绝对可移植设备Windows [](/windows-hardware/drivers/portable/)读取或写入访问，例如：平板电脑、iPhone。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-134">**Capabilities** - Deny Read or Write access to any [Windows Portable Device](/windows-hardware/drivers/portable/), for example: Tablet, iPhone.</span></span>

<span data-ttu-id="ab8f8-135">**说明**</span><span class="sxs-lookup"><span data-stu-id="ab8f8-135">**Description**</span></span>
- <span data-ttu-id="ab8f8-136">在计算机或用户或两者中应用。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-136">Applied at either machine or user or both.</span></span>
- <span data-ttu-id="ab8f8-137">支持 MEM OMA-URI 和 GPO。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-137">Support MEM OMA-URI and GPO.</span></span>

<span data-ttu-id="ab8f8-138">**支持的平台**- Windows 10</span><span class="sxs-lookup"><span data-stu-id="ab8f8-138">**Supported Platform** - Windows 10</span></span>

### <a name="endpoint-dlp-removable-storage"></a><span data-ttu-id="ab8f8-139">终结点 DLP 可移动存储</span><span class="sxs-lookup"><span data-stu-id="ab8f8-139">Endpoint DLP Removable storage</span></span>

<span data-ttu-id="ab8f8-140">**功能** - 审核或警告或阻止用户将项目或信息复制到可移动媒体或 USB 设备。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-140">**Capabilities** - Audit or Warn or Prevent a user from copying an item or information to removable media or USB device.</span></span>

<span data-ttu-id="ab8f8-141">**说明**- 若要详细了解Windows，请参阅了解Microsoft 365 [终结点数据丢失防护](../../compliance/endpoint-dlp-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-141">**Description** - For more information on Windows, see [Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).</span></span>

<span data-ttu-id="ab8f8-142">**支持的平台**- Windows 10</span><span class="sxs-lookup"><span data-stu-id="ab8f8-142">**Supported Platform** - Windows 10</span></span>

### <a name="bitlocker"></a><span data-ttu-id="ab8f8-143">BitLocker</span><span class="sxs-lookup"><span data-stu-id="ab8f8-143">BitLocker</span></span> 

<span data-ttu-id="ab8f8-144">**Capabilities**</span><span class="sxs-lookup"><span data-stu-id="ab8f8-144">**Capabilities**</span></span>
- <span data-ttu-id="ab8f8-145">阻止将数据写入到不受保护的BitLocker驱动器。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-145">Block data to be written to removable drives that aren't BitLocker protected.</span></span>
- <span data-ttu-id="ab8f8-146">除非在组织拥有的计算机上对可移动驱动器进行了加密，否则阻止访问可移动驱动器</span><span class="sxs-lookup"><span data-stu-id="ab8f8-146">Block access to removable drives unless they were encrypted on a computer owned by your organization</span></span>
 
<span data-ttu-id="ab8f8-147">**说明**- 有关此Windows，请参阅BitLocker [– 可移动驱动器设置。](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings)</span><span class="sxs-lookup"><span data-stu-id="ab8f8-147">**Description** - For more information on Windows, see [BitLocker – Removable Drive Settings](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span></span>

<span data-ttu-id="ab8f8-148">**支持的平台**- Windows 10</span><span class="sxs-lookup"><span data-stu-id="ab8f8-148">**Supported Platform** - Windows 10</span></span>

## <a name="device-properties"></a><span data-ttu-id="ab8f8-149">设备属性</span><span class="sxs-lookup"><span data-stu-id="ab8f8-149">Device properties</span></span>

<span data-ttu-id="ab8f8-150">Microsoft Defender for Endpoint Device Control Removable 存储 Protection 允许你根据下表中描述的属性限制可移动存储访问：</span><span class="sxs-lookup"><span data-stu-id="ab8f8-150">Microsoft Defender for Endpoint Device Control Removable Storage Protection allows you to restrict the removable storage access based on the properties described in the table below:</span></span>


|<span data-ttu-id="ab8f8-151">属性名</span><span class="sxs-lookup"><span data-stu-id="ab8f8-151">Property Name</span></span>  |<span data-ttu-id="ab8f8-152">适用的策略</span><span class="sxs-lookup"><span data-stu-id="ab8f8-152">Applicable Policies</span></span>  |<span data-ttu-id="ab8f8-153">适用于操作系统</span><span class="sxs-lookup"><span data-stu-id="ab8f8-153">Applies to Operating Systems</span></span>  |<span data-ttu-id="ab8f8-154">说明</span><span class="sxs-lookup"><span data-stu-id="ab8f8-154">Description</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="ab8f8-155">设备类</span><span class="sxs-lookup"><span data-stu-id="ab8f8-155">Device Class</span></span>    |     [<span data-ttu-id="ab8f8-156">如何使用 Microsoft Defender for Endpoint 控制 USB 设备和其他可移动媒体</span><span class="sxs-lookup"><span data-stu-id="ab8f8-156">How to control USB devices and other removable media using Microsoft Defender for Endpoint</span></span>](control-usb-devices-using-intune.md)     |   <span data-ttu-id="ab8f8-157">Windows</span><span class="sxs-lookup"><span data-stu-id="ab8f8-157">Windows</span></span>      |  <span data-ttu-id="ab8f8-158">有关设备 ID 格式的信息，请参阅 [设备设置类](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-158">For information about Device ID formats, see [device setup class](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span></span> <span data-ttu-id="ab8f8-159">**注意**：设备安装可以应用于任何设备，而不仅是可移动存储。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-159">**Note**: Device Installation can be applied to any devices, not only Removable storage.</span></span>       |
|<span data-ttu-id="ab8f8-160">主 ID</span><span class="sxs-lookup"><span data-stu-id="ab8f8-160">Primary ID</span></span>   |     <span data-ttu-id="ab8f8-161">可移动存储访问控制</span><span class="sxs-lookup"><span data-stu-id="ab8f8-161">Removable storage Access Control</span></span>    |   <span data-ttu-id="ab8f8-162">Windows</span><span class="sxs-lookup"><span data-stu-id="ab8f8-162">Windows</span></span>      |      <span data-ttu-id="ab8f8-163">主 ID 包括可移动存储和 CD/DVD。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-163">The Primary ID includes removable storage and CD/DVD.</span></span>   |
|<span data-ttu-id="ab8f8-164">设备 ID</span><span class="sxs-lookup"><span data-stu-id="ab8f8-164">Device ID</span></span>     |  <span data-ttu-id="ab8f8-165">如何使用 Microsoft Defender for Endpoint 控制[USB 设备和其他可移动媒体](control-usb-devices-using-intune.md);可移动存储访问控制</span><span class="sxs-lookup"><span data-stu-id="ab8f8-165">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>       |      <span data-ttu-id="ab8f8-166">Windows</span><span class="sxs-lookup"><span data-stu-id="ab8f8-166">Windows</span></span>   |    <span data-ttu-id="ab8f8-167">有关设备 ID 格式的信息，请参阅标准 [USB](/windows-hardware/drivers/install/standard-usb-identifiers)标识符，例如 USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span><span class="sxs-lookup"><span data-stu-id="ab8f8-167">For information about Device ID formats, see [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span></span>      |
|<span data-ttu-id="ab8f8-168">硬件 ID</span><span class="sxs-lookup"><span data-stu-id="ab8f8-168">Hardware ID</span></span>     |     <span data-ttu-id="ab8f8-169">如何使用 Microsoft Defender for Endpoint 控制[USB 设备和其他可移动媒体](control-usb-devices-using-intune.md);可移动存储访问控制</span><span class="sxs-lookup"><span data-stu-id="ab8f8-169">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>    |     <span data-ttu-id="ab8f8-170">Windows</span><span class="sxs-lookup"><span data-stu-id="ab8f8-170">Windows</span></span>    |    <span data-ttu-id="ab8f8-171">一个标识系统中设备的字符串，例如 USBSTOR\DiskGeneric_Flash_Disk______8.07; **注意**：硬件 ID 不是唯一的;不同设备可能共享相同的值。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-171">A string identified the device in the system, for example, USBSTOR\DiskGeneric_Flash_Disk______8.07; **Note**: Hardware ID is not unique; different devices may share same value.</span></span>|
|<span data-ttu-id="ab8f8-172">实例 ID</span><span class="sxs-lookup"><span data-stu-id="ab8f8-172">Instance ID</span></span>    | <span data-ttu-id="ab8f8-173">设备安装;可移动存储访问控制</span><span class="sxs-lookup"><span data-stu-id="ab8f8-173">Device Installation; Removable storage Access Control</span></span>     |     <span data-ttu-id="ab8f8-174">Windows</span><span class="sxs-lookup"><span data-stu-id="ab8f8-174">Windows</span></span>    |   <span data-ttu-id="ab8f8-175">唯一标识系统中设备的字符串，例如 USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span><span class="sxs-lookup"><span data-stu-id="ab8f8-175">A string uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span></span>      |
|<span data-ttu-id="ab8f8-176">友好名称</span><span class="sxs-lookup"><span data-stu-id="ab8f8-176">Friendly Name</span></span>     |     <span data-ttu-id="ab8f8-177">可移动存储访问控制</span><span class="sxs-lookup"><span data-stu-id="ab8f8-177">Removable storage Access Control</span></span>    |   <span data-ttu-id="ab8f8-178">Windows</span><span class="sxs-lookup"><span data-stu-id="ab8f8-178">Windows</span></span>      |    <span data-ttu-id="ab8f8-179">附加到设备的字符串，例如通用闪存磁盘 USB 设备</span><span class="sxs-lookup"><span data-stu-id="ab8f8-179">A string attached to the device, for example, Generic Flash Disk USB Device</span></span>     |
|<span data-ttu-id="ab8f8-180">供应商 ID/产品 ID</span><span class="sxs-lookup"><span data-stu-id="ab8f8-180">Vendor ID / Product ID</span></span>     |  <span data-ttu-id="ab8f8-181">可移动存储访问控制</span><span class="sxs-lookup"><span data-stu-id="ab8f8-181">Removable storage Access Control</span></span>       |   <span data-ttu-id="ab8f8-182">WindowsMac</span><span class="sxs-lookup"><span data-stu-id="ab8f8-182">Windows Mac</span></span>      |     <span data-ttu-id="ab8f8-183">供应商 ID 是 USB 委员会分配给供应商的四位数供应商代码。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-183">Vendor ID is the four-digit vendor code that the USB committee assigns to the vendor.</span></span> <span data-ttu-id="ab8f8-184">产品 ID 是供应商分配给设备的四位数产品代码;支持通配符。</span><span class="sxs-lookup"><span data-stu-id="ab8f8-184">Product ID is the four-digit product code that the vendor assigns to the device; Support wildcard.</span></span>    |
|<span data-ttu-id="ab8f8-185">Serial NumberId</span><span class="sxs-lookup"><span data-stu-id="ab8f8-185">Serial NumberId</span></span>     |     <span data-ttu-id="ab8f8-186">可移动存储访问控制</span><span class="sxs-lookup"><span data-stu-id="ab8f8-186">Removable storage Access Control</span></span>    |      <span data-ttu-id="ab8f8-187">WindowsMac</span><span class="sxs-lookup"><span data-stu-id="ab8f8-187">Windows Mac</span></span>   |     <span data-ttu-id="ab8f8-188">例如 <SerialNumberId>，002324B534BCB431B000058A</SerialNumberId></span><span class="sxs-lookup"><span data-stu-id="ab8f8-188">For example, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span></span>    |

## <a name="related-topic"></a><span data-ttu-id="ab8f8-189">相关主题</span><span class="sxs-lookup"><span data-stu-id="ab8f8-189">Related topic</span></span>

- [<span data-ttu-id="ab8f8-190">Microsoft Defender for Endpoint 设备控件可移动存储访问控制</span><span class="sxs-lookup"><span data-stu-id="ab8f8-190">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>](device-control-removable-storage-access-control.md)

