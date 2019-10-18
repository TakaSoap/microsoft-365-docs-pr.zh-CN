---
title: 自行注册新设备
description: 自己注册设备，以便它们可以由 Microsoft 托管桌面管理
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 952fac18db8ecc31fcd041dbfdf45e6ee8edee75
ms.sourcegitcommit: 9aaedbab11fd1a1d289eeb8f853d321f32cb7edc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37577758"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="bb7c6-103">自行注册新设备</span><span class="sxs-lookup"><span data-stu-id="bb7c6-103">Register new devices yourself</span></span>

<span data-ttu-id="bb7c6-104">Microsoft 托管桌面可以与全新设备配合使用，也可以重新使用可能已有的设备（这将需要您对其进行重新映像）。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-104">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="bb7c6-105">您可以使用 Azure 门户上的 Microsoft 托管桌面注册设备。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-105">You can register devices by using Microsoft Managed Desktop on the Azure Portal.</span></span>

> [!NOTE]
> <span data-ttu-id="bb7c6-106">与合作伙伴合作获取设备？</span><span class="sxs-lookup"><span data-stu-id="bb7c6-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="bb7c6-107">如果是这样，则无需担心获取硬件哈希值。他们将为你负责。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="bb7c6-108">请确保您的合作伙伴在 [合作伙伴中心](https://partner.microsoft.com/dashboard)建立与您的关系，并确保它们包含 Azure Active Directory 和 Office 365 的委派管理权限。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard) and that they include delegated administration privileges for Azure Active Directory and Office 365.</span></span> <span data-ttu-id="bb7c6-109">你的合作伙伴可以在 [合作伙伴中心帮助](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)中了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-109">Your partner can learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="bb7c6-110">建立此关系后，你的合作伙伴将代表你直接注册设备–无需进一步操作。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="bb7c6-111">如果您想要查看详细信息，或者您的合作伙伴有问题，请参阅[合作伙伴注册设备的步骤](register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="bb7c6-112">注册设备后，可以继续[检查映像](#check-the-image)并将[设备传递](#deliver-the-device)给用户。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="bb7c6-113">准备注册全新的设备</span><span class="sxs-lookup"><span data-stu-id="bb7c6-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="bb7c6-114">准备好新设备后，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="bb7c6-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="bb7c6-115">获取每个设备的硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="bb7c6-116">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="bb7c6-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="bb7c6-117">[在 Microsoft 托管桌面中注册设备](#register-devices)。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-117">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="bb7c6-118">请仔细检查图像是否正确。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="bb7c6-119">传递设备</span><span class="sxs-lookup"><span data-stu-id="bb7c6-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="bb7c6-120">获取硬件哈希</span><span class="sxs-lookup"><span data-stu-id="bb7c6-120">Obtain the hardware hash</span></span>

<span data-ttu-id="bb7c6-121">Microsoft 托管桌面通过引用其硬件哈希来唯一标识每个设备。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="bb7c6-122">有三个选项可用于获取此信息：</span><span class="sxs-lookup"><span data-stu-id="bb7c6-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="bb7c6-123">向 OEM 提供商咨询 AutoPilot 注册文件，其中将包含硬件哈希值。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="bb7c6-124">在每台设备上运行[Windows PowerShell 脚本](#powershell-script-method)，并收集文件中的结果。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="bb7c6-125">启动每个设备--但不完成 Windows 安装程序体验，并[收集可移动闪存驱动器上的哈希值](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="bb7c6-126">PowerShell script 方法</span><span class="sxs-lookup"><span data-stu-id="bb7c6-126">PowerShell script method</span></span>

1.  <span data-ttu-id="bb7c6-127">打开具有管理权限的 PowerShell 提示。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-127">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="bb7c6-128">以`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="bb7c6-128">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="bb7c6-129">以`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="bb7c6-129">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>

#### <a name="flash-drive-method"></a><span data-ttu-id="bb7c6-130">闪存驱动器方法</span><span class="sxs-lookup"><span data-stu-id="bb7c6-130">Flash drive method</span></span>

1. <span data-ttu-id="bb7c6-131">在要注册的设备以外的其他设备上，插入 u 盘。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-131">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="bb7c6-132">打开具有管理权限的 PowerShell 提示。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-132">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="bb7c6-133">以`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="bb7c6-133">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="bb7c6-134">打开要注册的设备，但*不要启动安装程序体验*。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-134">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="bb7c6-135">如果您意外启动了设置体验，则必须重置或重新映像设备。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-135">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="bb7c6-136">插入 u 盘，然后按 SHIFT + F10。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-136">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="bb7c6-137">打开具有管理权限的 PowerShell 提示符，然后运行`cd <pathToUsb>`。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-137">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="bb7c6-138">以`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="bb7c6-138">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="bb7c6-139">以`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="bb7c6-139">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="bb7c6-140">删除 USB 驱动器，然后通过运行来关闭设备`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="bb7c6-140">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="bb7c6-141">在完成注册后，请不要再打开要注册的设备。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-141">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="bb7c6-142">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="bb7c6-142">Merge hash data</span></span>

<span data-ttu-id="bb7c6-143">您需要将 CSV 文件中的数据组合到单个文件中才能完成注册。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-143">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="bb7c6-144">下面是一个示例 PowerShell 脚本，可轻松实现此操作：</span><span class="sxs-lookup"><span data-stu-id="bb7c6-144">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

### <a name="register-devices"></a><span data-ttu-id="bb7c6-145">注册设备</span><span class="sxs-lookup"><span data-stu-id="bb7c6-145">Register devices</span></span>

<span data-ttu-id="bb7c6-146">CSV 文件必须为注册的特定格式。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-146">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="bb7c6-147">如果您在前面的步骤中收集数据，则该文件应具有正确的格式;如果从供应商获取文件，则可能需要调整格式。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-147">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="bb7c6-148">为方便起见，可以下载此 CSV 文件的[模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-148">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="bb7c6-149">您的文件需要包含与示例1（制造商、模型等）**完全相同的列标题**，但您自己的数据用于其他行。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-149">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="bb7c6-150">如果使用模板，请在文本编辑工具（如记事本）中打开它，并考虑仅保留第1行中的所有数据，仅在第2行和更低的行中输入数据。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-150">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="bb7c6-151">如果您忘记更改任何示例数据，则注册将失败。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-151">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="bb7c6-152">使用 Azure 门户注册设备</span><span class="sxs-lookup"><span data-stu-id="bb7c6-152">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="bb7c6-153">在 Microsoft 托管桌面[Azure 门户](https://aka.ms/mmdportal)中，在左侧导航窗格中选择 "**设备**"。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-153">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="bb7c6-154">选择 **+ 注册设备**;将打开 "飞入"：</span><span class="sxs-lookup"><span data-stu-id="bb7c6-154">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="bb7c6-155">[![选择注册设备后飞入](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="bb7c6-155">[![Fly-in after selecting Register devices](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (遗憾的是这不成立。我们可以删除此注释-但现在将其保留，直到我们有机会聊天它。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="bb7c6-157">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="bb7c6-157">Follow these steps:</span></span>

1. <span data-ttu-id="bb7c6-158">在 "**文件上载**" 中，提供以前创建的 CSV 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-158">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="bb7c6-159">（可选）可以出于自己的跟踪目的添加**订单 id**或**购买 ID** 。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-159">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="bb7c6-160">这些值没有格式要求。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-160">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="bb7c6-161">选择 "**注册设备**"。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-161">Select **Register devices**.</span></span> <span data-ttu-id="bb7c6-162">系统会将设备添加到**设备边栏**上的设备列表中，并标记为 "**注册挂起**"。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-162">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="bb7c6-163">注册通常需要不到10分钟的时间，如果成功，设备将显示为 "已**准备就绪**，以供用户使用"，表示它已准备就绪，正在等待最终用户开始使用。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-163">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="bb7c6-164">你可以在主**Microsoft 托管台式机-设备**页面上监视设备注册的进度。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-164">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="bb7c6-165">可能报告的状态包括：</span><span class="sxs-lookup"><span data-stu-id="bb7c6-165">Possible states reported there include:</span></span>

| <span data-ttu-id="bb7c6-166">状态</span><span class="sxs-lookup"><span data-stu-id="bb7c6-166">State</span></span> | <span data-ttu-id="bb7c6-167">说明</span><span class="sxs-lookup"><span data-stu-id="bb7c6-167">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="bb7c6-168">注册挂起</span><span class="sxs-lookup"><span data-stu-id="bb7c6-168">Registration pending</span></span> | <span data-ttu-id="bb7c6-169">注册尚未完成。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-169">Registration is not done yet.</span></span> <span data-ttu-id="bb7c6-170">稍后再次查看。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-170">Check back later.</span></span> |
| <span data-ttu-id="bb7c6-171">注册失败</span><span class="sxs-lookup"><span data-stu-id="bb7c6-171">Registration failed</span></span> | <span data-ttu-id="bb7c6-172">无法完成注册。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-172">Registration could not be completed.</span></span> <span data-ttu-id="bb7c6-173">有关详细信息，请参阅[设备注册故障排除](#troubleshooting-device-registration)。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-173">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="bb7c6-174">为用户准备就绪</span><span class="sxs-lookup"><span data-stu-id="bb7c6-174">Ready for user</span></span> | <span data-ttu-id="bb7c6-175">注册成功，现在设备已准备好传递给最终用户。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-175">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="bb7c6-176">Microsoft 托管桌面将在首次设置时引导他们，因此无需执行任何进一步的准备。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-176">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="bb7c6-177">活动</span><span class="sxs-lookup"><span data-stu-id="bb7c6-177">Active</span></span> | <span data-ttu-id="bb7c6-178">设备已传递给最终用户，并且已向其注册了你的租户。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-178">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="bb7c6-179">这也表明它们是定期使用设备的。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-179">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="bb7c6-180">不再</span><span class="sxs-lookup"><span data-stu-id="bb7c6-180">Inactive</span></span> | <span data-ttu-id="bb7c6-181">设备已传递给最终用户，并且已向其注册了你的租户。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-181">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="bb7c6-182">但是，他们最近未使用设备（最近7天）。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-182">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="bb7c6-183">设备注册故障排除</span><span class="sxs-lookup"><span data-stu-id="bb7c6-183">Troubleshooting device registration</span></span>

| <span data-ttu-id="bb7c6-184">错误消息</span><span class="sxs-lookup"><span data-stu-id="bb7c6-184">Error message</span></span> | <span data-ttu-id="bb7c6-185">详细信息</span><span class="sxs-lookup"><span data-stu-id="bb7c6-185">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="bb7c6-186">找不到设备</span><span class="sxs-lookup"><span data-stu-id="bb7c6-186">Device not found</span></span> | <span data-ttu-id="bb7c6-187">无法注册此设备，因为我们找不到提供的制造商、型号或序列号的匹配项。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-187">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="bb7c6-188">请与设备供应商确认这些值。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-188">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="bb7c6-189">硬件哈希无效</span><span class="sxs-lookup"><span data-stu-id="bb7c6-189">Hardware hash not valid</span></span> | <span data-ttu-id="bb7c6-190">为此设备提供的硬件哈希格式不正确。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-190">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="bb7c6-191">仔细检查硬件哈希，然后重新提交。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-191">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="bb7c6-192">已注册设备</span><span class="sxs-lookup"><span data-stu-id="bb7c6-192">Device already registered</span></span> | <span data-ttu-id="bb7c6-193">此设备已注册到你的组织。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-193">This device is already registered to your organization.</span></span> <span data-ttu-id="bb7c6-194">无需执行进一步操作。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-194">No further action required.</span></span> |
| <span data-ttu-id="bb7c6-195">其他组织声明的设备</span><span class="sxs-lookup"><span data-stu-id="bb7c6-195">Device claimed by another organization</span></span> | <span data-ttu-id="bb7c6-196">此设备已由其他组织声明。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-196">This device has already been claimed by another organization.</span></span> <span data-ttu-id="bb7c6-197">请与设备供应商联系。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-197">Check with your device supplier.</span></span> |
| <span data-ttu-id="bb7c6-198">意外错误</span><span class="sxs-lookup"><span data-stu-id="bb7c6-198">Unexpected error</span></span> | <span data-ttu-id="bb7c6-199">无法自动处理你的请求。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-199">Your request could not be automatically processed.</span></span> <span data-ttu-id="bb7c6-200">联系支持人员并提供请求 ID：<requestId></span><span class="sxs-lookup"><span data-stu-id="bb7c6-200">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="bb7c6-201">检查图像</span><span class="sxs-lookup"><span data-stu-id="bb7c6-201">Check the image</span></span>

<span data-ttu-id="bb7c6-202">如果你的设备来自 Microsoft 托管桌面合作伙伴提供商，则该映像应正确。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-202">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="bb7c6-203">如果你愿意，也可以在自己自己应用图像。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-203">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="bb7c6-204">若要开始，请联系你正在使用的 Microsoft 代表，他们将为你提供应用此图像的位置和步骤。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-204">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="bb7c6-205">传递设备</span><span class="sxs-lookup"><span data-stu-id="bb7c6-205">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb7c6-206">在将设备交给用户之前，请确保已为该用户获取并应用了[相应的许可证](../get-ready/prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-206">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="bb7c6-207">如果应用了所有许可证，则可以[让用户准备好使用设备](get-started-devices.md)，然后你的用户可以启动设备并继续执行 Windows 安装体验。</span><span class="sxs-lookup"><span data-stu-id="bb7c6-207">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>






