---
title: 自行注册新设备
description: 自己注册设备，以便它们可以通过 Microsoft 托管桌面进行管理
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: df6013f2f7fec32e79557a82f9b56fe4ad487786
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840677"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="3768d-103">自行注册新设备</span><span class="sxs-lookup"><span data-stu-id="3768d-103">Register new devices yourself</span></span>

<span data-ttu-id="3768d-104">Microsoft 托管桌面可以与全新的设备一起使用，或者你可以重复使用你可能已拥有的设备 (这将要求你将它们重新映像) 。</span><span class="sxs-lookup"><span data-stu-id="3768d-104">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="3768d-105">可以在 Microsoft Endpoint Manager 门户中向 Microsoft 托管桌面注册设备。</span><span class="sxs-lookup"><span data-stu-id="3768d-105">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

> [!NOTE]
> <span data-ttu-id="3768d-106">与合作伙伴合作以获取设备？</span><span class="sxs-lookup"><span data-stu-id="3768d-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="3768d-107">如果是这样，则无需担心获取硬件哈希;他们将负责处理这一问题。</span><span class="sxs-lookup"><span data-stu-id="3768d-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="3768d-108">请确保你的合作伙伴在合作伙伴中心与你 [建立关系](https://partner.microsoft.com/dashboard)。</span><span class="sxs-lookup"><span data-stu-id="3768d-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="3768d-109">你的合作伙伴可以在合作伙伴中心 [帮助中了解更多信息](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)。</span><span class="sxs-lookup"><span data-stu-id="3768d-109">Your partner can learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="3768d-110">建立此关系后，你的合作伙伴将仅代表你注册设备 ， 无需你执行任何进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="3768d-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="3768d-111">如果你希望查看详细信息，或者你的合作伙伴有疑问，请参阅"合作伙伴注册[设备的步骤"。](register-devices-partner.md)</span><span class="sxs-lookup"><span data-stu-id="3768d-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="3768d-112">注册设备后，你可以继续[检查](#check-the-image)映像，将设备传送给用户。 [](#deliver-the-device)</span><span class="sxs-lookup"><span data-stu-id="3768d-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="3768d-113">准备注册全新的设备</span><span class="sxs-lookup"><span data-stu-id="3768d-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="3768d-114">获得新设备后，你将按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="3768d-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="3768d-115">获取每个设备的硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="3768d-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="3768d-116">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="3768d-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="3768d-117">[在 Microsoft 托管桌面中注册设备](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="3768d-117">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="3768d-118">仔细检查图像是否正确。</span><span class="sxs-lookup"><span data-stu-id="3768d-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="3768d-119">交付设备</span><span class="sxs-lookup"><span data-stu-id="3768d-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="3768d-120">获取硬件哈希</span><span class="sxs-lookup"><span data-stu-id="3768d-120">Obtain the hardware hash</span></span>

<span data-ttu-id="3768d-121">Microsoft 托管桌面通过引用其硬件哈希来唯一标识每台设备。</span><span class="sxs-lookup"><span data-stu-id="3768d-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="3768d-122">有三个选项可获取此信息：</span><span class="sxs-lookup"><span data-stu-id="3768d-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="3768d-123">向 OEM 供应商询问 AutoPilot 注册文件，该文件将包含硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="3768d-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="3768d-124">在每个 [Windows PowerShell运行](#powershell-script-method) 一个脚本，并收集文件中的结果。</span><span class="sxs-lookup"><span data-stu-id="3768d-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="3768d-125">启动每台设备（但不完成 Windows 设置体验）并收集可移动闪存驱动器 [上的哈希](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="3768d-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="3768d-126">PowerShell 脚本方法</span><span class="sxs-lookup"><span data-stu-id="3768d-126">PowerShell script method</span></span>

<span data-ttu-id="3768d-127">可以在 PowerShell [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 网站上使用 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="3768d-127">You can use the [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell script on the PowerShell Gallery website.</span></span> <span data-ttu-id="3768d-128">有关设备标识和硬件哈希的信息，请参阅"[将设备添加到 Windows Autopilot"。](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification)</span><span class="sxs-lookup"><span data-stu-id="3768d-128">For more information about device identification and hardware hash, see [Adding devices to Windows Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification).</span></span>

1.  <span data-ttu-id="3768d-129">打开具有管理权限的 PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="3768d-129">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="3768d-130">运行 `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="3768d-130">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="3768d-131">运行 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="3768d-131">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4.  <span data-ttu-id="3768d-132">运行 `powershell -ExecutionPolicy restricted` 以防止后续不受限制的脚本运行。</span><span class="sxs-lookup"><span data-stu-id="3768d-132">Run `powershell -ExecutionPolicy restricted` to prevent subsequent unrestricted scripts from running.</span></span>


#### <a name="flash-drive-method"></a><span data-ttu-id="3768d-133">Flash 驱动器方法</span><span class="sxs-lookup"><span data-stu-id="3768d-133">Flash drive method</span></span>

1. <span data-ttu-id="3768d-134">在除要注册的设备外的其他设备上，插入 U 盘。</span><span class="sxs-lookup"><span data-stu-id="3768d-134">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="3768d-135">打开具有管理权限的 PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="3768d-135">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="3768d-136">运行 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="3768d-136">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="3768d-137">打开要注册的设备，但不 *启动安装体验*。</span><span class="sxs-lookup"><span data-stu-id="3768d-137">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="3768d-138">如果意外启动设置体验，必须重置或重置设备映像。</span><span class="sxs-lookup"><span data-stu-id="3768d-138">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="3768d-139">插入 U 盘，然后按 Shift + F10。</span><span class="sxs-lookup"><span data-stu-id="3768d-139">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="3768d-140">打开具有管理权限的 PowerShell 提示符，然后运行 `cd <pathToUsb>` 。</span><span class="sxs-lookup"><span data-stu-id="3768d-140">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="3768d-141">运行 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="3768d-141">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="3768d-142">运行 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="3768d-142">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="3768d-143">删除 U 盘，然后通过运行关闭设备 `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="3768d-143">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="3768d-144">在注册完设备之前，请勿再次打开要注册的设备的电源。</span><span class="sxs-lookup"><span data-stu-id="3768d-144">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="3768d-145">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="3768d-145">Merge hash data</span></span>

<span data-ttu-id="3768d-146">你需要将 CSV 文件中的数据合并到单个文件中才能完成注册。</span><span class="sxs-lookup"><span data-stu-id="3768d-146">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="3768d-147">下面是一个示例 PowerShell 脚本，可轻松实现：</span><span class="sxs-lookup"><span data-stu-id="3768d-147">Here's a sample PowerShell script to make it easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="3768d-148">使用管理门户注册设备</span><span class="sxs-lookup"><span data-stu-id="3768d-148">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="3768d-149">在 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)中， **选择** 左侧导航窗格中的设备。</span><span class="sxs-lookup"><span data-stu-id="3768d-149">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="3768d-150">查找菜单的"Microsoft 托管桌面"部分，然后选择 **"设备"。**</span><span class="sxs-lookup"><span data-stu-id="3768d-150">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="3768d-151">在 Microsoft 托管桌面设备工作区中，选择 **+ 注册** 设备，这将打开一个飞入以注册新设备。</span><span class="sxs-lookup"><span data-stu-id="3768d-151">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="3768d-152">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="3768d-152">Follow these steps:</span></span>

1. <span data-ttu-id="3768d-153">在 **"文件** 上载"中，提供之前创建的 CSV 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="3768d-153">In **File upload**, provide a path to the CSV file you created previously.</span></span>
3. <span data-ttu-id="3768d-154">选择 **"注册设备"。**</span><span class="sxs-lookup"><span data-stu-id="3768d-154">Select **Register devices**.</span></span> <span data-ttu-id="3768d-155">系统会将设备添加到设备上设备列表，标记为 **"注册挂起"。** </span><span class="sxs-lookup"><span data-stu-id="3768d-155">The system will add the devices to your list of devices on **Devices**, marked as **Registration Pending**.</span></span> <span data-ttu-id="3768d-156">注册通常少于 10 分钟，并且当成功时，设备将显示为"为用户准备就绪"，这意味着它已准备好并等待用户开始使用。</span><span class="sxs-lookup"><span data-stu-id="3768d-156">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="3768d-157">你可以监视主页上的设备注册进度。</span><span class="sxs-lookup"><span data-stu-id="3768d-157">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="3768d-158">报告可能状态包括：</span><span class="sxs-lookup"><span data-stu-id="3768d-158">Possible states reported there include:</span></span>

| <span data-ttu-id="3768d-159">状态</span><span class="sxs-lookup"><span data-stu-id="3768d-159">State</span></span> | <span data-ttu-id="3768d-160">说明</span><span class="sxs-lookup"><span data-stu-id="3768d-160">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="3768d-161">注册挂起</span><span class="sxs-lookup"><span data-stu-id="3768d-161">Registration Pending</span></span> | <span data-ttu-id="3768d-162">注册尚未完成。</span><span class="sxs-lookup"><span data-stu-id="3768d-162">Registration is not done yet.</span></span> <span data-ttu-id="3768d-163">请稍后再回来查看。</span><span class="sxs-lookup"><span data-stu-id="3768d-163">Check back later.</span></span> |
| <span data-ttu-id="3768d-164">注册失败</span><span class="sxs-lookup"><span data-stu-id="3768d-164">Registration failed</span></span> | <span data-ttu-id="3768d-165">无法完成注册。</span><span class="sxs-lookup"><span data-stu-id="3768d-165">Registration could not be completed.</span></span> <span data-ttu-id="3768d-166">有关详细信息 [，请参阅设备注册](#troubleshooting-device-registration) 疑难解答。</span><span class="sxs-lookup"><span data-stu-id="3768d-166">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="3768d-167">为用户做好准备</span><span class="sxs-lookup"><span data-stu-id="3768d-167">Ready for user</span></span> | <span data-ttu-id="3768d-168">注册成功，设备现在已准备好传递给用户。</span><span class="sxs-lookup"><span data-stu-id="3768d-168">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="3768d-169">Microsoft 托管桌面将指导用户完成首次设置，因此无需执行任何进一步准备。</span><span class="sxs-lookup"><span data-stu-id="3768d-169">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="3768d-170">活动文件</span><span class="sxs-lookup"><span data-stu-id="3768d-170">Active</span></span> | <span data-ttu-id="3768d-171">设备已传递到用户，并且他们已在租户中注册。</span><span class="sxs-lookup"><span data-stu-id="3768d-171">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="3768d-172">此状态还指示他们定期使用设备。</span><span class="sxs-lookup"><span data-stu-id="3768d-172">This state also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="3768d-173">非活动</span><span class="sxs-lookup"><span data-stu-id="3768d-173">Inactive</span></span> | <span data-ttu-id="3768d-174">设备已传递到用户，并且他们已在租户中注册。</span><span class="sxs-lookup"><span data-stu-id="3768d-174">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="3768d-175">但是，他们最近 7 天内 (使用过) 。</span><span class="sxs-lookup"><span data-stu-id="3768d-175">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="3768d-176">设备注册疑难解答</span><span class="sxs-lookup"><span data-stu-id="3768d-176">Troubleshooting device registration</span></span>

| <span data-ttu-id="3768d-177">错误消息</span><span class="sxs-lookup"><span data-stu-id="3768d-177">Error message</span></span> | <span data-ttu-id="3768d-178">详细信息</span><span class="sxs-lookup"><span data-stu-id="3768d-178">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="3768d-179">未找到设备</span><span class="sxs-lookup"><span data-stu-id="3768d-179">Device not found</span></span> | <span data-ttu-id="3768d-180">我们无法注册此设备，因为找不到提供的制造商、型号或序列号的匹配项。</span><span class="sxs-lookup"><span data-stu-id="3768d-180">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="3768d-181">与设备供应商确认这些值。</span><span class="sxs-lookup"><span data-stu-id="3768d-181">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="3768d-182">硬件哈希无效</span><span class="sxs-lookup"><span data-stu-id="3768d-182">Hardware hash not valid</span></span> | <span data-ttu-id="3768d-183">你为此设备提供的硬件哈希格式不正确。</span><span class="sxs-lookup"><span data-stu-id="3768d-183">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="3768d-184">仔细检查硬件哈希，然后重新提交。</span><span class="sxs-lookup"><span data-stu-id="3768d-184">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="3768d-185">设备已注册</span><span class="sxs-lookup"><span data-stu-id="3768d-185">Device already registered</span></span> | <span data-ttu-id="3768d-186">此设备已注册到组织。</span><span class="sxs-lookup"><span data-stu-id="3768d-186">This device is already registered to your organization.</span></span> <span data-ttu-id="3768d-187">无需执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="3768d-187">No further action required.</span></span> |
| <span data-ttu-id="3768d-188">由另一个组织声明的设备</span><span class="sxs-lookup"><span data-stu-id="3768d-188">Device claimed by another organization</span></span> | <span data-ttu-id="3768d-189">此设备已被另一个组织声明。</span><span class="sxs-lookup"><span data-stu-id="3768d-189">This device has already been claimed by another organization.</span></span> <span data-ttu-id="3768d-190">请与设备供应商联系。</span><span class="sxs-lookup"><span data-stu-id="3768d-190">Check with your device supplier.</span></span> |
| <span data-ttu-id="3768d-191">意外错误</span><span class="sxs-lookup"><span data-stu-id="3768d-191">Unexpected error</span></span> | <span data-ttu-id="3768d-192">您的请求无法自动处理。</span><span class="sxs-lookup"><span data-stu-id="3768d-192">Your request could not be automatically processed.</span></span> <span data-ttu-id="3768d-193">联系支持人员并提供请求 ID： <requestId></span><span class="sxs-lookup"><span data-stu-id="3768d-193">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="3768d-194">检查图像</span><span class="sxs-lookup"><span data-stu-id="3768d-194">Check the image</span></span>

<span data-ttu-id="3768d-195">如果你的设备来自 Microsoft 托管桌面合作伙伴供应商，则映像应该正确。</span><span class="sxs-lookup"><span data-stu-id="3768d-195">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="3768d-196">如果愿意，也欢迎您自行应用该图像。</span><span class="sxs-lookup"><span data-stu-id="3768d-196">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="3768d-197">To get started， contact the Microsoft representative you're working with and they will provide you the location and steps for applying the image.</span><span class="sxs-lookup"><span data-stu-id="3768d-197">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="3768d-198">交付设备</span><span class="sxs-lookup"><span data-stu-id="3768d-198">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3768d-199">在将设备上交给用户之前，请确保你已获取并应用了 [该用户的适当许可证](../get-ready/prerequisites.md) 。</span><span class="sxs-lookup"><span data-stu-id="3768d-199">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="3768d-200">如果应用了所有许可证，你可以让用户准备好[](get-started-devices.md)使用设备，然后你的用户可以启动设备并继续 Windows 安装体验。</span><span class="sxs-lookup"><span data-stu-id="3768d-200">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>





