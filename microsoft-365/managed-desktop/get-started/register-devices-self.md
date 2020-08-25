---
title: 自行注册新设备
description: 自己注册设备，以便它们可以由 Microsoft 托管桌面管理
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 470047da0a1902a6076add27a6e7ac516edd3150
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "46869003"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="22493-103">自行注册新设备</span><span class="sxs-lookup"><span data-stu-id="22493-103">Register new devices yourself</span></span>

<span data-ttu-id="22493-104">Microsoft 托管桌面可以与全新设备配合使用，也可以重新使用已有的设备 (这将需要您将其重新映像) 。</span><span class="sxs-lookup"><span data-stu-id="22493-104">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="22493-105">您可以使用 Microsoft 托管桌面管理门户注册设备。</span><span class="sxs-lookup"><span data-stu-id="22493-105">You can register devices by using the Microsoft Managed Desktop Admin Portal.</span></span>

> [!NOTE]
> <span data-ttu-id="22493-106">与合作伙伴合作获取设备？</span><span class="sxs-lookup"><span data-stu-id="22493-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="22493-107">如果是这样，则无需担心获取硬件哈希值。他们将为你负责。</span><span class="sxs-lookup"><span data-stu-id="22493-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="22493-108">请确保您的合作伙伴在 [合作伙伴中心](https://partner.microsoft.com/dashboard)建立与您的关系。</span><span class="sxs-lookup"><span data-stu-id="22493-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="22493-109">你的合作伙伴可以在 [合作伙伴中心帮助](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)中了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="22493-109">Your partner can learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="22493-110">建立此关系后，你的合作伙伴将代表你直接注册设备–无需进一步操作。</span><span class="sxs-lookup"><span data-stu-id="22493-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="22493-111">如果您想要查看详细信息，或者您的合作伙伴有问题，请参阅 [合作伙伴注册设备的步骤](register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="22493-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="22493-112">注册设备后，可以继续 [检查映像](#check-the-image) 并将 [设备传递](#deliver-the-device) 给用户。</span><span class="sxs-lookup"><span data-stu-id="22493-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="22493-113">准备注册全新的设备</span><span class="sxs-lookup"><span data-stu-id="22493-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="22493-114">准备好新设备后，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="22493-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="22493-115">获取每个设备的硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="22493-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="22493-116">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="22493-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="22493-117">[在 Microsoft 托管桌面中注册设备](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="22493-117">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="22493-118">请仔细检查图像是否正确。</span><span class="sxs-lookup"><span data-stu-id="22493-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="22493-119">传递设备</span><span class="sxs-lookup"><span data-stu-id="22493-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="22493-120">获取硬件哈希</span><span class="sxs-lookup"><span data-stu-id="22493-120">Obtain the hardware hash</span></span>

<span data-ttu-id="22493-121">Microsoft 托管桌面通过引用其硬件哈希来唯一标识每个设备。</span><span class="sxs-lookup"><span data-stu-id="22493-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="22493-122">有三个选项可用于获取此信息：</span><span class="sxs-lookup"><span data-stu-id="22493-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="22493-123">向 OEM 提供商咨询 AutoPilot 注册文件，其中将包含硬件哈希值。</span><span class="sxs-lookup"><span data-stu-id="22493-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="22493-124">在每台设备上运行 [Windows PowerShell 脚本](#powershell-script-method) ，并收集文件中的结果。</span><span class="sxs-lookup"><span data-stu-id="22493-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="22493-125">启动每个设备--但不完成 Windows 安装程序体验，并 [收集可移动闪存驱动器上的哈希值](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="22493-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="22493-126">PowerShell script 方法</span><span class="sxs-lookup"><span data-stu-id="22493-126">PowerShell script method</span></span>

<span data-ttu-id="22493-127">您可以使用 PowerShell 库网站上的 [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) powershell 脚本。</span><span class="sxs-lookup"><span data-stu-id="22493-127">You can use the [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell script on the PowerShell Gallery website.</span></span> <span data-ttu-id="22493-128">有关设备标识和硬件哈希的详细信息，请参阅 [将设备添加到 Windows Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification)。</span><span class="sxs-lookup"><span data-stu-id="22493-128">For more information about device identification and hardware hash, see [Adding devices to Windows Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification).</span></span>

1.  <span data-ttu-id="22493-129">打开具有管理权限的 PowerShell 提示。</span><span class="sxs-lookup"><span data-stu-id="22493-129">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="22493-130">以 `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="22493-130">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="22493-131">以 `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="22493-131">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>

#### <a name="flash-drive-method"></a><span data-ttu-id="22493-132">闪存驱动器方法</span><span class="sxs-lookup"><span data-stu-id="22493-132">Flash drive method</span></span>

1. <span data-ttu-id="22493-133">在要注册的设备以外的其他设备上，插入 u 盘。</span><span class="sxs-lookup"><span data-stu-id="22493-133">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="22493-134">打开具有管理权限的 PowerShell 提示。</span><span class="sxs-lookup"><span data-stu-id="22493-134">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="22493-135">以 `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="22493-135">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="22493-136">打开要注册的设备，但 *不要启动安装程序体验*。</span><span class="sxs-lookup"><span data-stu-id="22493-136">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="22493-137">如果您意外启动了设置体验，则必须重置或重新映像设备。</span><span class="sxs-lookup"><span data-stu-id="22493-137">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="22493-138">插入 u 盘，然后按 SHIFT + F10。</span><span class="sxs-lookup"><span data-stu-id="22493-138">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="22493-139">打开具有管理权限的 PowerShell 提示符，然后运行 `cd <pathToUsb>` 。</span><span class="sxs-lookup"><span data-stu-id="22493-139">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="22493-140">以 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="22493-140">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="22493-141">以 `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="22493-141">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="22493-142">删除 USB 驱动器，然后通过运行来关闭设备 `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="22493-142">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="22493-143">在完成注册后，请不要再打开要注册的设备。</span><span class="sxs-lookup"><span data-stu-id="22493-143">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="22493-144">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="22493-144">Merge hash data</span></span>

<span data-ttu-id="22493-145">您需要将 CSV 文件中的数据组合到单个文件中才能完成注册。</span><span class="sxs-lookup"><span data-stu-id="22493-145">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="22493-146">下面是一个示例 PowerShell 脚本，可轻松实现此操作：</span><span class="sxs-lookup"><span data-stu-id="22493-146">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="22493-147">使用管理门户注册设备</span><span class="sxs-lookup"><span data-stu-id="22493-147">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="22493-148">在 Microsoft 托管桌面 [管理门户](https://aka.ms/mmdportal)中，选择左侧导航窗格中的 " **设备** "。</span><span class="sxs-lookup"><span data-stu-id="22493-148">From the Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="22493-149">选择 **+ 注册设备**;将打开 "飞入"：</span><span class="sxs-lookup"><span data-stu-id="22493-149">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="22493-150">[![选择注册设备后飞入，列出分配的用户的列设备、序列号、状态、上次查看日期和期限](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span><span class="sxs-lookup"><span data-stu-id="22493-150">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span></span>


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="22493-151">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="22493-151">Follow these steps:</span></span>

1. <span data-ttu-id="22493-152">在 " **文件上载**" 中，提供以前创建的 CSV 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="22493-152">In **File upload**, provide a path to the CSV file you created previously.</span></span>
3. <span data-ttu-id="22493-153">选择 " **注册设备**"。</span><span class="sxs-lookup"><span data-stu-id="22493-153">Select **Register devices**.</span></span> <span data-ttu-id="22493-154">系统会将设备添加到 **设备**上的设备列表中，并标记为 **AutopilotRegistrationRequested**。</span><span class="sxs-lookup"><span data-stu-id="22493-154">The system will add the devices to your list of devices on the **Devices blade**, marked as **AutopilotRegistrationRequested**.</span></span> <span data-ttu-id="22493-155">注册通常需要不到10分钟的时间，如果成功，设备将显示为 "就绪"，使其可供 **用户** 使用，并等待用户开始使用。</span><span class="sxs-lookup"><span data-stu-id="22493-155">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="22493-156">你可以在主 **Microsoft 托管台式机-设备** 页面上监视设备注册的进度。</span><span class="sxs-lookup"><span data-stu-id="22493-156">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="22493-157">可能报告的状态包括：</span><span class="sxs-lookup"><span data-stu-id="22493-157">Possible states reported there include:</span></span>

| <span data-ttu-id="22493-158">状态</span><span class="sxs-lookup"><span data-stu-id="22493-158">State</span></span> | <span data-ttu-id="22493-159">说明</span><span class="sxs-lookup"><span data-stu-id="22493-159">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="22493-160">AutopilotRegistrationRequested</span><span class="sxs-lookup"><span data-stu-id="22493-160">AutopilotRegistrationRequested</span></span> | <span data-ttu-id="22493-161">注册尚未完成。</span><span class="sxs-lookup"><span data-stu-id="22493-161">Registration is not done yet.</span></span> <span data-ttu-id="22493-162">稍后再次查看。</span><span class="sxs-lookup"><span data-stu-id="22493-162">Check back later.</span></span> |
| <span data-ttu-id="22493-163">注册失败</span><span class="sxs-lookup"><span data-stu-id="22493-163">Registration failed</span></span> | <span data-ttu-id="22493-164">无法完成注册。</span><span class="sxs-lookup"><span data-stu-id="22493-164">Registration could not be completed.</span></span> <span data-ttu-id="22493-165">有关详细信息，请参阅 [设备注册故障排除](#troubleshooting-device-registration) 。</span><span class="sxs-lookup"><span data-stu-id="22493-165">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="22493-166">为用户准备就绪</span><span class="sxs-lookup"><span data-stu-id="22493-166">Ready for user</span></span> | <span data-ttu-id="22493-167">注册成功，现在设备已准备好传递给最终用户。</span><span class="sxs-lookup"><span data-stu-id="22493-167">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="22493-168">Microsoft 托管桌面将在首次设置时引导他们，因此无需执行任何进一步的准备。</span><span class="sxs-lookup"><span data-stu-id="22493-168">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="22493-169">活动</span><span class="sxs-lookup"><span data-stu-id="22493-169">Active</span></span> | <span data-ttu-id="22493-170">设备已传递给最终用户，并且已向其注册了你的租户。</span><span class="sxs-lookup"><span data-stu-id="22493-170">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="22493-171">这也表明它们是定期使用设备的。</span><span class="sxs-lookup"><span data-stu-id="22493-171">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="22493-172">不再</span><span class="sxs-lookup"><span data-stu-id="22493-172">Inactive</span></span> | <span data-ttu-id="22493-173">设备已传递给最终用户，并且已向其注册了你的租户。</span><span class="sxs-lookup"><span data-stu-id="22493-173">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="22493-174">但是，他们在过去7天内未使用最近 (设备) 。</span><span class="sxs-lookup"><span data-stu-id="22493-174">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="22493-175">设备注册故障排除</span><span class="sxs-lookup"><span data-stu-id="22493-175">Troubleshooting device registration</span></span>

| <span data-ttu-id="22493-176">错误消息</span><span class="sxs-lookup"><span data-stu-id="22493-176">Error message</span></span> | <span data-ttu-id="22493-177">详细信息</span><span class="sxs-lookup"><span data-stu-id="22493-177">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="22493-178">找不到设备</span><span class="sxs-lookup"><span data-stu-id="22493-178">Device not found</span></span> | <span data-ttu-id="22493-179">无法注册此设备，因为我们找不到提供的制造商、型号或序列号的匹配项。</span><span class="sxs-lookup"><span data-stu-id="22493-179">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="22493-180">请与设备供应商确认这些值。</span><span class="sxs-lookup"><span data-stu-id="22493-180">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="22493-181">硬件哈希无效</span><span class="sxs-lookup"><span data-stu-id="22493-181">Hardware hash not valid</span></span> | <span data-ttu-id="22493-182">为此设备提供的硬件哈希格式不正确。</span><span class="sxs-lookup"><span data-stu-id="22493-182">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="22493-183">仔细检查硬件哈希，然后重新提交。</span><span class="sxs-lookup"><span data-stu-id="22493-183">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="22493-184">已注册设备</span><span class="sxs-lookup"><span data-stu-id="22493-184">Device already registered</span></span> | <span data-ttu-id="22493-185">此设备已注册到你的组织。</span><span class="sxs-lookup"><span data-stu-id="22493-185">This device is already registered to your organization.</span></span> <span data-ttu-id="22493-186">无需执行进一步操作。</span><span class="sxs-lookup"><span data-stu-id="22493-186">No further action required.</span></span> |
| <span data-ttu-id="22493-187">其他组织声明的设备</span><span class="sxs-lookup"><span data-stu-id="22493-187">Device claimed by another organization</span></span> | <span data-ttu-id="22493-188">此设备已由其他组织声明。</span><span class="sxs-lookup"><span data-stu-id="22493-188">This device has already been claimed by another organization.</span></span> <span data-ttu-id="22493-189">请与设备供应商联系。</span><span class="sxs-lookup"><span data-stu-id="22493-189">Check with your device supplier.</span></span> |
| <span data-ttu-id="22493-190">意外错误</span><span class="sxs-lookup"><span data-stu-id="22493-190">Unexpected error</span></span> | <span data-ttu-id="22493-191">无法自动处理你的请求。</span><span class="sxs-lookup"><span data-stu-id="22493-191">Your request could not be automatically processed.</span></span> <span data-ttu-id="22493-192">联系支持人员并提供请求 ID： <requestId></span><span class="sxs-lookup"><span data-stu-id="22493-192">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="22493-193">检查图像</span><span class="sxs-lookup"><span data-stu-id="22493-193">Check the image</span></span>

<span data-ttu-id="22493-194">如果你的设备来自 Microsoft 托管桌面合作伙伴提供商，则该映像应正确。</span><span class="sxs-lookup"><span data-stu-id="22493-194">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="22493-195">如果你愿意，也可以在自己自己应用图像。</span><span class="sxs-lookup"><span data-stu-id="22493-195">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="22493-196">若要开始，请联系你正在使用的 Microsoft 代表，他们将为你提供应用此图像的位置和步骤。</span><span class="sxs-lookup"><span data-stu-id="22493-196">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="22493-197">传递设备</span><span class="sxs-lookup"><span data-stu-id="22493-197">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22493-198">在将设备交给用户之前，请确保已为该用户获取并应用了 [相应的许可证](../get-ready/prerequisites.md) 。</span><span class="sxs-lookup"><span data-stu-id="22493-198">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="22493-199">如果应用了所有许可证，则可以 [让用户准备好使用设备](get-started-devices.md)，然后你的用户可以启动设备并继续执行 Windows 安装体验。</span><span class="sxs-lookup"><span data-stu-id="22493-199">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>






