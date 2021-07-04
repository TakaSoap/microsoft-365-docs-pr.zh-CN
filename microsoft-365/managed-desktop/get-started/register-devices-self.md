---
title: 自行注册新设备
description: 自己注册设备，以便由设备Microsoft 托管桌面
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
ms.openlocfilehash: a66ad53faf1b38c3db4ab4446dbc1d175fbd99e4
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289531"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="cb985-103">自行注册新设备</span><span class="sxs-lookup"><span data-stu-id="cb985-103">Register new devices yourself</span></span>

<span data-ttu-id="cb985-104">Microsoft 托管桌面全新的设备，或者你可以重复使用你可能已拥有的设备 (这将要求你重新映像它们) 。</span><span class="sxs-lookup"><span data-stu-id="cb985-104">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="cb985-105">可以在应用门户Microsoft 托管桌面注册Microsoft Endpoint Manager设备。</span><span class="sxs-lookup"><span data-stu-id="cb985-105">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

> [!NOTE]
> <span data-ttu-id="cb985-106">与合作伙伴合作获取设备</span><span class="sxs-lookup"><span data-stu-id="cb985-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="cb985-107">如果是这样，你无需担心获取硬件哈希;他们会负责你。</span><span class="sxs-lookup"><span data-stu-id="cb985-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="cb985-108">请确保你的合作伙伴与你在合作伙伴中心 [建立了关系](https://partner.microsoft.com/dashboard)。</span><span class="sxs-lookup"><span data-stu-id="cb985-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="cb985-109">你的合作伙伴可以在合作伙伴中心 [帮助 中了解更多信息](/partner-center/request-a-relationship-with-a-customer)。</span><span class="sxs-lookup"><span data-stu-id="cb985-109">Your partner can learn more at [Partner Center help](/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="cb985-110">建立此关系后，你的合作伙伴将仅代表你注册设备，无需你执行任何进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="cb985-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="cb985-111">如果你希望查看详细信息，或者你的合作伙伴有疑问，请参阅合作伙伴注册 [设备的步骤](register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="cb985-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="cb985-112">注册设备后，你可以继续 [检查](#check-the-image) 映像，将设备 [传送](#deliver-the-device) 给用户。</span><span class="sxs-lookup"><span data-stu-id="cb985-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>



## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="cb985-113">准备注册全新的设备</span><span class="sxs-lookup"><span data-stu-id="cb985-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="cb985-114">拥有新设备后，你将按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="cb985-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="cb985-115">获取每台设备的硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="cb985-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="cb985-116">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="cb985-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="cb985-117">[在 中注册Microsoft 托管桌面。](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="cb985-117">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="cb985-118">仔细检查图像是否正确。</span><span class="sxs-lookup"><span data-stu-id="cb985-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="cb985-119">交付设备</span><span class="sxs-lookup"><span data-stu-id="cb985-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="cb985-120">获取硬件哈希</span><span class="sxs-lookup"><span data-stu-id="cb985-120">Obtain the hardware hash</span></span>

<span data-ttu-id="cb985-121">Microsoft 托管桌面通过引用其硬件哈希来唯一标识每台设备。</span><span class="sxs-lookup"><span data-stu-id="cb985-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="cb985-122">有三个选项可获取此信息：</span><span class="sxs-lookup"><span data-stu-id="cb985-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="cb985-123">请你的 OEM 供应商提供 AutoPilot 注册文件，该文件将包含硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="cb985-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="cb985-124">在每个[Windows PowerShell运行](#powershell-script-method)一个脚本，并收集文件中的结果。</span><span class="sxs-lookup"><span data-stu-id="cb985-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="cb985-125">启动每台设备（但无法完成Windows安装体验）并收集可移动闪存[驱动器上的哈希](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="cb985-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="cb985-126">PowerShell 脚本方法</span><span class="sxs-lookup"><span data-stu-id="cb985-126">PowerShell script method</span></span>

<span data-ttu-id="cb985-127">可以在 PowerShell [ 库Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="cb985-127">You can use the [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell script on the PowerShell Gallery website.</span></span> <span data-ttu-id="cb985-128">有关设备标识和硬件哈希的信息，请参阅向[Autopilot](/mem/autopilot/add-devices#device-identification)Windows设备。</span><span class="sxs-lookup"><span data-stu-id="cb985-128">For more information about device identification and hardware hash, see [Adding devices to Windows Autopilot](/mem/autopilot/add-devices#device-identification).</span></span>

1. <span data-ttu-id="cb985-129">使用管理权限打开 PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="cb985-129">Open a PowerShell prompt with administrative rights.</span></span>
2. <span data-ttu-id="cb985-130">运行 `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="cb985-130">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3. <span data-ttu-id="cb985-131">运行 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="cb985-131">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. <span data-ttu-id="cb985-132">运行 `powershell -ExecutionPolicy restricted` 以防止后续不受限制的脚本运行。</span><span class="sxs-lookup"><span data-stu-id="cb985-132">Run `powershell -ExecutionPolicy restricted` to prevent subsequent unrestricted scripts from running.</span></span>

#### <a name="flash-drive-method"></a><span data-ttu-id="cb985-133">Flash drive 方法</span><span class="sxs-lookup"><span data-stu-id="cb985-133">Flash drive method</span></span>

1. <span data-ttu-id="cb985-134">在注册设备外的其他设备上，插入 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="cb985-134">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="cb985-135">使用管理权限打开 PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="cb985-135">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="cb985-136">运行 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="cb985-136">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="cb985-137">打开你要注册的设备， *但不启动设置体验*。</span><span class="sxs-lookup"><span data-stu-id="cb985-137">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="cb985-138">如果意外启动设置体验，必须重置或重置设备映像。</span><span class="sxs-lookup"><span data-stu-id="cb985-138">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="cb985-139">插入 USB 驱动器，然后按 Shift + F10。</span><span class="sxs-lookup"><span data-stu-id="cb985-139">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="cb985-140">使用管理权限打开 PowerShell 提示符，然后运行 `cd <pathToUsb>` 。</span><span class="sxs-lookup"><span data-stu-id="cb985-140">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="cb985-141">运行 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="cb985-141">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="cb985-142">运行 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="cb985-142">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="cb985-143">删除 USB 驱动器，然后通过运行来关闭设备 `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="cb985-143">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb985-144">完成注册之前，请勿再次打开要注册的设备。</span><span class="sxs-lookup"><span data-stu-id="cb985-144">Do not power on the device you are registering again until you've completed registration for it.</span></span> 

### <a name="merge-hash-data"></a><span data-ttu-id="cb985-145">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="cb985-145">Merge hash data</span></span>

<span data-ttu-id="cb985-146">你需要将 CSV 文件中的数据合并到单个文件中才能完成注册。</span><span class="sxs-lookup"><span data-stu-id="cb985-146">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="cb985-147">下面是一个简单易行的示例 PowerShell 脚本：</span><span class="sxs-lookup"><span data-stu-id="cb985-147">Here's a sample PowerShell script to make it easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="cb985-148">使用管理门户注册设备</span><span class="sxs-lookup"><span data-stu-id="cb985-148">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="cb985-149">在 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)**中，选择** 左侧导航窗格中的"设备"。</span><span class="sxs-lookup"><span data-stu-id="cb985-149">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="cb985-150">查找菜单Microsoft 托管桌面部分，**然后选择设备。**</span><span class="sxs-lookup"><span data-stu-id="cb985-150">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="cb985-151">在Microsoft 托管桌面设备"工作区中，选择 **" +** 注册设备"，这将打开一个飞入以注册新设备。</span><span class="sxs-lookup"><span data-stu-id="cb985-151">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->

<span data-ttu-id="cb985-152">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="cb985-152">Follow these steps:</span></span>

1. <span data-ttu-id="cb985-153">在 **"文件** 上载"中，提供之前创建的 CSV 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="cb985-153">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="cb985-154">在 [下拉菜单中选择](../service-description/profiles.md) 设备配置文件。</span><span class="sxs-lookup"><span data-stu-id="cb985-154">Select a [device profile](../service-description/profiles.md) in the drop-down menu.</span></span>
3. <span data-ttu-id="cb985-155">选择 **注册设备**。</span><span class="sxs-lookup"><span data-stu-id="cb985-155">Select **Register devices**.</span></span> <span data-ttu-id="cb985-156">系统将设备添加到设备上设备列表，标记为注册 **挂起。** </span><span class="sxs-lookup"><span data-stu-id="cb985-156">The system will add the devices to your list of devices on **Devices**, marked as **Registration Pending**.</span></span> <span data-ttu-id="cb985-157">注册通常少于 10 分钟，并且成功后，设备将显示为"为用户准备就绪"，这意味着它已准备好并等待用户开始使用。</span><span class="sxs-lookup"><span data-stu-id="cb985-157">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>

> [!NOTE]
> <span data-ttu-id="cb985-158">如果手动更改设备Azure Active Directory (AAD) 组成员身份，系统会自动将其重新分配给设备配置文件的组，并删除任何冲突组。</span><span class="sxs-lookup"><span data-stu-id="cb985-158">If you manually change the Azure Active Directory (AAD) group membership of a device, it will be automatically reassigned to the group for its device profile and removed from any conflicting groups.</span></span>

<span data-ttu-id="cb985-159">你可以监视主页上的设备注册进度。</span><span class="sxs-lookup"><span data-stu-id="cb985-159">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="cb985-160">其中报告的可能状态包括：</span><span class="sxs-lookup"><span data-stu-id="cb985-160">Possible states reported there include:</span></span>

| <span data-ttu-id="cb985-161">状态</span><span class="sxs-lookup"><span data-stu-id="cb985-161">State</span></span> | <span data-ttu-id="cb985-162">说明</span><span class="sxs-lookup"><span data-stu-id="cb985-162">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="cb985-163">Registration Pending</span><span class="sxs-lookup"><span data-stu-id="cb985-163">Registration Pending</span></span> | <span data-ttu-id="cb985-164">注册尚未完成。</span><span class="sxs-lookup"><span data-stu-id="cb985-164">Registration is not done yet.</span></span> <span data-ttu-id="cb985-165">请稍后再查看。</span><span class="sxs-lookup"><span data-stu-id="cb985-165">Check back later.</span></span> |
| <span data-ttu-id="cb985-166">注册失败</span><span class="sxs-lookup"><span data-stu-id="cb985-166">Registration failed</span></span> | <span data-ttu-id="cb985-167">无法完成注册。</span><span class="sxs-lookup"><span data-stu-id="cb985-167">Registration could not be completed.</span></span> <span data-ttu-id="cb985-168">有关详细信息 [，请参阅设备](#troubleshooting-device-registration) 注册疑难解答。</span><span class="sxs-lookup"><span data-stu-id="cb985-168">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="cb985-169">为用户准备就绪</span><span class="sxs-lookup"><span data-stu-id="cb985-169">Ready for user</span></span> | <span data-ttu-id="cb985-170">注册成功，设备现在已准备好传递给用户。</span><span class="sxs-lookup"><span data-stu-id="cb985-170">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="cb985-171">Microsoft 托管桌面将指导用户完成首次设置，因此无需执行任何进一步准备。</span><span class="sxs-lookup"><span data-stu-id="cb985-171">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="cb985-172">活动</span><span class="sxs-lookup"><span data-stu-id="cb985-172">Active</span></span> | <span data-ttu-id="cb985-173">设备已传递给用户，并且他们已在租户中注册。</span><span class="sxs-lookup"><span data-stu-id="cb985-173">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="cb985-174">此状态还指示他们定期使用设备。</span><span class="sxs-lookup"><span data-stu-id="cb985-174">This state also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="cb985-175">非活动</span><span class="sxs-lookup"><span data-stu-id="cb985-175">Inactive</span></span> | <span data-ttu-id="cb985-176">设备已传递给用户，并且他们已在租户中注册。</span><span class="sxs-lookup"><span data-stu-id="cb985-176">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="cb985-177">但是，他们在最近 7 天内 (使用过该设备) 。</span><span class="sxs-lookup"><span data-stu-id="cb985-177">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="cb985-178">设备注册疑难解答</span><span class="sxs-lookup"><span data-stu-id="cb985-178">Troubleshooting device registration</span></span>

| <span data-ttu-id="cb985-179">错误消息</span><span class="sxs-lookup"><span data-stu-id="cb985-179">Error message</span></span> | <span data-ttu-id="cb985-180">详细信息</span><span class="sxs-lookup"><span data-stu-id="cb985-180">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="cb985-181">未找到设备</span><span class="sxs-lookup"><span data-stu-id="cb985-181">Device not found</span></span> | <span data-ttu-id="cb985-182">我们无法注册此设备，因为找不到提供的制造商、型号或序列号的匹配项。</span><span class="sxs-lookup"><span data-stu-id="cb985-182">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="cb985-183">与设备供应商确认这些值。</span><span class="sxs-lookup"><span data-stu-id="cb985-183">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="cb985-184">硬件哈希无效</span><span class="sxs-lookup"><span data-stu-id="cb985-184">Hardware hash not valid</span></span> | <span data-ttu-id="cb985-185">你为此设备提供的硬件哈希格式不正确。</span><span class="sxs-lookup"><span data-stu-id="cb985-185">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="cb985-186">仔细检查硬件哈希，然后重新提交。</span><span class="sxs-lookup"><span data-stu-id="cb985-186">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="cb985-187">设备已注册</span><span class="sxs-lookup"><span data-stu-id="cb985-187">Device already registered</span></span> | <span data-ttu-id="cb985-188">此设备已注册到你的组织。</span><span class="sxs-lookup"><span data-stu-id="cb985-188">This device is already registered to your organization.</span></span> <span data-ttu-id="cb985-189">无需执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="cb985-189">No further action required.</span></span> |
| <span data-ttu-id="cb985-190">由另一个组织声明的设备</span><span class="sxs-lookup"><span data-stu-id="cb985-190">Device claimed by another organization</span></span> | <span data-ttu-id="cb985-191">此设备已被另一个组织声明。</span><span class="sxs-lookup"><span data-stu-id="cb985-191">This device has already been claimed by another organization.</span></span> <span data-ttu-id="cb985-192">请与设备供应商联系。</span><span class="sxs-lookup"><span data-stu-id="cb985-192">Check with your device supplier.</span></span> |
| <span data-ttu-id="cb985-193">意外错误</span><span class="sxs-lookup"><span data-stu-id="cb985-193">Unexpected error</span></span> | <span data-ttu-id="cb985-194">您的请求无法自动处理。</span><span class="sxs-lookup"><span data-stu-id="cb985-194">Your request could not be automatically processed.</span></span> <span data-ttu-id="cb985-195">联系支持人员并提供请求 ID： <requestId></span><span class="sxs-lookup"><span data-stu-id="cb985-195">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="cb985-196">检查图像</span><span class="sxs-lookup"><span data-stu-id="cb985-196">Check the image</span></span>

<span data-ttu-id="cb985-197">如果你的设备来自合作伙伴Microsoft 托管桌面，则映像应该正确。</span><span class="sxs-lookup"><span data-stu-id="cb985-197">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="cb985-198">如果愿意，也欢迎您自行应用该图像。</span><span class="sxs-lookup"><span data-stu-id="cb985-198">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="cb985-199">To get started， contact the Microsoft representative you're working with and they will provide you the location and steps for applying the image.</span><span class="sxs-lookup"><span data-stu-id="cb985-199">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="autopilot-group-tag"></a><span data-ttu-id="cb985-200">Autopilot 组标记</span><span class="sxs-lookup"><span data-stu-id="cb985-200">Autopilot group tag</span></span>

<span data-ttu-id="cb985-201">当你使用管理门户注册设备时，我们会自动分配Microsoft365Managed_Autopilot **Autopilot** 组标记。</span><span class="sxs-lookup"><span data-stu-id="cb985-201">When you use the Admin portal to register devices, we automatically assign the **Microsoft365Managed_Autopilot** Autopilot Group Tag.</span></span>
<span data-ttu-id="cb985-202">该服务每天监视Microsoft 托管桌面设备，并将组标记分配给任何尚未安装组标记的设备。</span><span class="sxs-lookup"><span data-stu-id="cb985-202">The service monitors all Microsoft Managed Desktop devices daily and assigns the group tag to any that don't already have it.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="cb985-203">交付设备</span><span class="sxs-lookup"><span data-stu-id="cb985-203">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb985-204">在将设备交还给用户之前，请确保你已获取并应用了 [该用户的适当许可证](../get-ready/prerequisites.md) 。</span><span class="sxs-lookup"><span data-stu-id="cb985-204">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="cb985-205">如果应用了所有许可证，你可以让用户准备好[](get-started-devices.md)使用设备，然后你的用户可以启动设备并继续Windows设置体验。</span><span class="sxs-lookup"><span data-stu-id="cb985-205">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>
