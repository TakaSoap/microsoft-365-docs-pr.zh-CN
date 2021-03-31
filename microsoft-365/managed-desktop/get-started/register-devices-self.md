---
title: 自行注册新设备
description: 自己注册设备，以便它们可以通过 Microsoft 托管桌面进行管理
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 3aff3bdc1260e9aa2a23760020aeabd71d6b28fd
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445574"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="1360f-104">自行注册新设备</span><span class="sxs-lookup"><span data-stu-id="1360f-104">Register new devices yourself</span></span>

<span data-ttu-id="1360f-105">Microsoft 托管桌面可以与全新的设备一起工作，或者你可以重复使用你可能已有的设备 (这将要求你重新映像它们) 。</span><span class="sxs-lookup"><span data-stu-id="1360f-105">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="1360f-106">可以在 Microsoft Endpoint Manager 门户中向 Microsoft 托管桌面注册设备。</span><span class="sxs-lookup"><span data-stu-id="1360f-106">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

> [!NOTE]
> <span data-ttu-id="1360f-107">与合作伙伴合作获取设备</span><span class="sxs-lookup"><span data-stu-id="1360f-107">Working with a partner to obtain devices?</span></span> <span data-ttu-id="1360f-108">如果是这样，你无需担心获取硬件哈希;他们会负责你。</span><span class="sxs-lookup"><span data-stu-id="1360f-108">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="1360f-109">请确保你的合作伙伴与你在合作伙伴中心 [建立了关系](https://partner.microsoft.com/dashboard)。</span><span class="sxs-lookup"><span data-stu-id="1360f-109">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="1360f-110">你的合作伙伴可以在合作伙伴中心 [帮助 中了解更多信息](/partner-center/request-a-relationship-with-a-customer)。</span><span class="sxs-lookup"><span data-stu-id="1360f-110">Your partner can learn more at [Partner Center help](/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="1360f-111">建立此关系后，你的合作伙伴将仅代表你注册设备，无需你执行任何进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="1360f-111">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="1360f-112">如果你希望查看详细信息，或者你的合作伙伴有疑问，请参阅合作伙伴注册 [设备的步骤](register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="1360f-112">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="1360f-113">注册设备后，你可以继续 [检查](#check-the-image) 映像，将设备 [传送](#deliver-the-device) 给用户。</span><span class="sxs-lookup"><span data-stu-id="1360f-113">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="1360f-114">准备注册全新的设备</span><span class="sxs-lookup"><span data-stu-id="1360f-114">Prepare to register brand-new devices</span></span>


<span data-ttu-id="1360f-115">拥有新设备后，你将按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="1360f-115">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="1360f-116">获取每台设备的硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="1360f-116">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="1360f-117">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="1360f-117">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="1360f-118">[在 Microsoft 托管桌面中注册设备](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="1360f-118">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="1360f-119">仔细检查图像是否正确。</span><span class="sxs-lookup"><span data-stu-id="1360f-119">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="1360f-120">交付设备</span><span class="sxs-lookup"><span data-stu-id="1360f-120">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="1360f-121">获取硬件哈希</span><span class="sxs-lookup"><span data-stu-id="1360f-121">Obtain the hardware hash</span></span>

<span data-ttu-id="1360f-122">Microsoft 托管桌面通过引用其硬件哈希来唯一标识每台设备。</span><span class="sxs-lookup"><span data-stu-id="1360f-122">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="1360f-123">有三个选项可获取此信息：</span><span class="sxs-lookup"><span data-stu-id="1360f-123">You have three options for getting this information:</span></span>

- <span data-ttu-id="1360f-124">请你的 OEM 供应商提供 AutoPilot 注册文件，该文件将包含硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="1360f-124">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="1360f-125">在每个 [Windows PowerShell](#powershell-script-method) 运行一个脚本，并收集文件中的结果。</span><span class="sxs-lookup"><span data-stu-id="1360f-125">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="1360f-126">启动每台设备（但不完成 Windows 设置体验）并收集可移动闪存 [驱动器上的哈希](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="1360f-126">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="1360f-127">PowerShell 脚本方法</span><span class="sxs-lookup"><span data-stu-id="1360f-127">PowerShell script method</span></span>

<span data-ttu-id="1360f-128">可以在 PowerShell [ 库Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="1360f-128">You can use the [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell script on the PowerShell Gallery website.</span></span> <span data-ttu-id="1360f-129">有关设备标识和硬件哈希的信息，请参阅 [将设备添加到 Windows Autopilot](/mem/autopilot/add-devices#device-identification)。</span><span class="sxs-lookup"><span data-stu-id="1360f-129">For more information about device identification and hardware hash, see [Adding devices to Windows Autopilot](/mem/autopilot/add-devices#device-identification).</span></span>

1.  <span data-ttu-id="1360f-130">使用管理权限打开 PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="1360f-130">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="1360f-131">运行 `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="1360f-131">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="1360f-132">运行 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="1360f-132">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4.  <span data-ttu-id="1360f-133">运行 `powershell -ExecutionPolicy restricted` 以防止后续不受限制的脚本运行。</span><span class="sxs-lookup"><span data-stu-id="1360f-133">Run `powershell -ExecutionPolicy restricted` to prevent subsequent unrestricted scripts from running.</span></span>


#### <a name="flash-drive-method"></a><span data-ttu-id="1360f-134">Flash drive 方法</span><span class="sxs-lookup"><span data-stu-id="1360f-134">Flash drive method</span></span>

1. <span data-ttu-id="1360f-135">在注册设备外的其他设备上，插入 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="1360f-135">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="1360f-136">使用管理权限打开 PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="1360f-136">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="1360f-137">运行 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="1360f-137">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="1360f-138">打开你要注册的设备， *但不启动设置体验*。</span><span class="sxs-lookup"><span data-stu-id="1360f-138">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="1360f-139">如果意外启动设置体验，必须重置或重置设备映像。</span><span class="sxs-lookup"><span data-stu-id="1360f-139">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="1360f-140">插入 USB 驱动器，然后按 Shift + F10。</span><span class="sxs-lookup"><span data-stu-id="1360f-140">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="1360f-141">使用管理权限打开 PowerShell 提示符，然后运行 `cd <pathToUsb>` 。</span><span class="sxs-lookup"><span data-stu-id="1360f-141">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="1360f-142">运行 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="1360f-142">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="1360f-143">运行 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="1360f-143">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="1360f-144">删除 USB 驱动器，然后通过运行来关闭设备 `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="1360f-144">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="1360f-145">完成注册之前，请勿再次打开要注册的设备。</span><span class="sxs-lookup"><span data-stu-id="1360f-145">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="1360f-146">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="1360f-146">Merge hash data</span></span>

<span data-ttu-id="1360f-147">你需要将 CSV 文件中的数据合并到单个文件中才能完成注册。</span><span class="sxs-lookup"><span data-stu-id="1360f-147">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="1360f-148">下面是一个简单易行的示例 PowerShell 脚本：</span><span class="sxs-lookup"><span data-stu-id="1360f-148">Here's a sample PowerShell script to make it easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="1360f-149">使用管理门户注册设备</span><span class="sxs-lookup"><span data-stu-id="1360f-149">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="1360f-150">在[Microsoft Endpoint Manager](https://endpoint.microsoft.com/)中，选择左侧导航窗格中的"设备"。 </span><span class="sxs-lookup"><span data-stu-id="1360f-150">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="1360f-151">查找菜单的"Microsoft 托管桌面"部分，然后选择"**设备"。**</span><span class="sxs-lookup"><span data-stu-id="1360f-151">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="1360f-152">在 Microsoft 托管桌面设备工作区中，选择 **+ 注册设备**，这将打开一个飞入以注册新设备。</span><span class="sxs-lookup"><span data-stu-id="1360f-152">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="1360f-153">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="1360f-153">Follow these steps:</span></span>

1. <span data-ttu-id="1360f-154">在 **"文件** 上载"中，提供之前创建的 CSV 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="1360f-154">In **File upload**, provide a path to the CSV file you created previously.</span></span>
3. <span data-ttu-id="1360f-155">选择 **注册设备**。</span><span class="sxs-lookup"><span data-stu-id="1360f-155">Select **Register devices**.</span></span> <span data-ttu-id="1360f-156">系统将设备添加到设备上设备列表，标记为注册 **挂起。** </span><span class="sxs-lookup"><span data-stu-id="1360f-156">The system will add the devices to your list of devices on **Devices**, marked as **Registration Pending**.</span></span> <span data-ttu-id="1360f-157">注册通常少于 10 分钟，并且成功后，设备将显示为"为用户准备就绪"，这意味着它已准备好并等待用户开始使用。</span><span class="sxs-lookup"><span data-stu-id="1360f-157">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="1360f-158">你可以监视主页上的设备注册进度。</span><span class="sxs-lookup"><span data-stu-id="1360f-158">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="1360f-159">其中报告的可能状态包括：</span><span class="sxs-lookup"><span data-stu-id="1360f-159">Possible states reported there include:</span></span>

| <span data-ttu-id="1360f-160">状态</span><span class="sxs-lookup"><span data-stu-id="1360f-160">State</span></span> | <span data-ttu-id="1360f-161">说明</span><span class="sxs-lookup"><span data-stu-id="1360f-161">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="1360f-162">Registration Pending</span><span class="sxs-lookup"><span data-stu-id="1360f-162">Registration Pending</span></span> | <span data-ttu-id="1360f-163">注册尚未完成。</span><span class="sxs-lookup"><span data-stu-id="1360f-163">Registration is not done yet.</span></span> <span data-ttu-id="1360f-164">请稍后再查看。</span><span class="sxs-lookup"><span data-stu-id="1360f-164">Check back later.</span></span> |
| <span data-ttu-id="1360f-165">注册失败</span><span class="sxs-lookup"><span data-stu-id="1360f-165">Registration failed</span></span> | <span data-ttu-id="1360f-166">无法完成注册。</span><span class="sxs-lookup"><span data-stu-id="1360f-166">Registration could not be completed.</span></span> <span data-ttu-id="1360f-167">有关详细信息 [，请参阅设备](#troubleshooting-device-registration) 注册疑难解答。</span><span class="sxs-lookup"><span data-stu-id="1360f-167">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="1360f-168">为用户准备就绪</span><span class="sxs-lookup"><span data-stu-id="1360f-168">Ready for user</span></span> | <span data-ttu-id="1360f-169">注册成功，设备现在已准备好传递给用户。</span><span class="sxs-lookup"><span data-stu-id="1360f-169">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="1360f-170">Microsoft 托管桌面将指导用户完成首次设置，因此无需执行任何进一步准备。</span><span class="sxs-lookup"><span data-stu-id="1360f-170">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="1360f-171">活动</span><span class="sxs-lookup"><span data-stu-id="1360f-171">Active</span></span> | <span data-ttu-id="1360f-172">设备已传递给用户，并且他们已在租户中注册。</span><span class="sxs-lookup"><span data-stu-id="1360f-172">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="1360f-173">此状态还指示他们定期使用设备。</span><span class="sxs-lookup"><span data-stu-id="1360f-173">This state also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="1360f-174">非活动</span><span class="sxs-lookup"><span data-stu-id="1360f-174">Inactive</span></span> | <span data-ttu-id="1360f-175">设备已传递给用户，并且他们已在租户中注册。</span><span class="sxs-lookup"><span data-stu-id="1360f-175">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="1360f-176">但是，他们在最近 7 天内 (使用过该设备) 。</span><span class="sxs-lookup"><span data-stu-id="1360f-176">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="1360f-177">设备注册疑难解答</span><span class="sxs-lookup"><span data-stu-id="1360f-177">Troubleshooting device registration</span></span>

| <span data-ttu-id="1360f-178">错误消息</span><span class="sxs-lookup"><span data-stu-id="1360f-178">Error message</span></span> | <span data-ttu-id="1360f-179">详细信息</span><span class="sxs-lookup"><span data-stu-id="1360f-179">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="1360f-180">未找到设备</span><span class="sxs-lookup"><span data-stu-id="1360f-180">Device not found</span></span> | <span data-ttu-id="1360f-181">我们无法注册此设备，因为找不到提供的制造商、型号或序列号的匹配项。</span><span class="sxs-lookup"><span data-stu-id="1360f-181">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="1360f-182">与设备供应商确认这些值。</span><span class="sxs-lookup"><span data-stu-id="1360f-182">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="1360f-183">硬件哈希无效</span><span class="sxs-lookup"><span data-stu-id="1360f-183">Hardware hash not valid</span></span> | <span data-ttu-id="1360f-184">你为此设备提供的硬件哈希格式不正确。</span><span class="sxs-lookup"><span data-stu-id="1360f-184">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="1360f-185">仔细检查硬件哈希，然后重新提交。</span><span class="sxs-lookup"><span data-stu-id="1360f-185">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="1360f-186">设备已注册</span><span class="sxs-lookup"><span data-stu-id="1360f-186">Device already registered</span></span> | <span data-ttu-id="1360f-187">此设备已注册到你的组织。</span><span class="sxs-lookup"><span data-stu-id="1360f-187">This device is already registered to your organization.</span></span> <span data-ttu-id="1360f-188">无需执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="1360f-188">No further action required.</span></span> |
| <span data-ttu-id="1360f-189">由另一个组织声明的设备</span><span class="sxs-lookup"><span data-stu-id="1360f-189">Device claimed by another organization</span></span> | <span data-ttu-id="1360f-190">此设备已被另一个组织声明。</span><span class="sxs-lookup"><span data-stu-id="1360f-190">This device has already been claimed by another organization.</span></span> <span data-ttu-id="1360f-191">请与设备供应商联系。</span><span class="sxs-lookup"><span data-stu-id="1360f-191">Check with your device supplier.</span></span> |
| <span data-ttu-id="1360f-192">意外错误</span><span class="sxs-lookup"><span data-stu-id="1360f-192">Unexpected error</span></span> | <span data-ttu-id="1360f-193">您的请求无法自动处理。</span><span class="sxs-lookup"><span data-stu-id="1360f-193">Your request could not be automatically processed.</span></span> <span data-ttu-id="1360f-194">联系支持人员并提供请求 ID： <requestId></span><span class="sxs-lookup"><span data-stu-id="1360f-194">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="1360f-195">检查图像</span><span class="sxs-lookup"><span data-stu-id="1360f-195">Check the image</span></span>

<span data-ttu-id="1360f-196">如果你的设备来自 Microsoft 托管桌面合作伙伴供应商，则映像应该正确。</span><span class="sxs-lookup"><span data-stu-id="1360f-196">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="1360f-197">如果愿意，也欢迎您自行应用该图像。</span><span class="sxs-lookup"><span data-stu-id="1360f-197">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="1360f-198">To get started， contact the Microsoft representative you're working with and they will provide you the location and steps for applying the image.</span><span class="sxs-lookup"><span data-stu-id="1360f-198">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="1360f-199">交付设备</span><span class="sxs-lookup"><span data-stu-id="1360f-199">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1360f-200">在将设备交还给用户之前，请确保你已获取并应用了 [该用户的适当许可证](../get-ready/prerequisites.md) 。</span><span class="sxs-lookup"><span data-stu-id="1360f-200">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="1360f-201">如果应用所有许可证，你可以让用户准备好使用[](get-started-devices.md)设备，然后你的用户可以启动设备并继续 Windows 安装体验。</span><span class="sxs-lookup"><span data-stu-id="1360f-201">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>