---
title: 自行在 Microsoft 托管桌面中注册设备
description: 自己注册设备, 以便它们可以由 Microsoft 托管桌面管理
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 217418cfce66baa02b30ae7d8a01b938a1f2366e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289126"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a><span data-ttu-id="30bc4-103">在 Microsoft 托管桌面中注册设备</span><span class="sxs-lookup"><span data-stu-id="30bc4-103">Register devices in Microsoft Managed Desktop</span></span>

>[!NOTE]
><span data-ttu-id="30bc4-104">本主题介绍您自己注册设备的步骤。</span><span class="sxs-lookup"><span data-stu-id="30bc4-104">This topic describes the steps for you to register devices on your own.</span></span> <span data-ttu-id="30bc4-105">在[面向合作伙伴的 Microsoft 托管桌面中的注册设备](register-devices-partner.md)中记录合作伙伴的过程。</span><span class="sxs-lookup"><span data-stu-id="30bc4-105">The process for Partners is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="30bc4-106">Microsoft 托管桌面可以与全新设备配合使用, 也可以重新使用可能已有的设备 (这将需要您对其进行重新映像)。</span><span class="sxs-lookup"><span data-stu-id="30bc4-106">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="30bc4-107">您可以使用 Azure 门户上的 Microsoft 托管桌面注册设备, 也可以通过使用 API 获得灵活性。</span><span class="sxs-lookup"><span data-stu-id="30bc4-107">You can register devices by using Microsoft Managed Desktop on the Azure Portal or gain flexibility by using an API.</span></span>

## <a name="prepare-to-register-devices"></a><span data-ttu-id="30bc4-108">准备注册设备</span><span class="sxs-lookup"><span data-stu-id="30bc4-108">Prepare to register devices</span></span>

<span data-ttu-id="30bc4-109">如果还没有获得要使用的设备, 请检查[Microsoft 托管桌面设备](../service-description/device-list.md), 并与设备合作伙伴合作以购买支持的设备。</span><span class="sxs-lookup"><span data-stu-id="30bc4-109">If you haven't already obtained the devices you want to use, check [Microsoft Managed Desktop devices](../service-description/device-list.md) and work with a device partner to procure supported devices.</span></span>

<span data-ttu-id="30bc4-110">无论您是使用全新的设备还是重新使用现有设备, 若要使用 Microsoft 托管桌面注册它们, 都需要准备一个**逗号分隔 (CSV) 文件**。</span><span class="sxs-lookup"><span data-stu-id="30bc4-110">Whether you're working with completely new devices or re-using existing ones, to register them with Microsoft Managed Desktop, you'll need to prepare a **comma-delimited (CSV) file**.</span></span> <span data-ttu-id="30bc4-111">此文件应包括每个设备的以下信息:</span><span class="sxs-lookup"><span data-stu-id="30bc4-111">This file should include the following information for each device:</span></span>

>[!NOTE]
><span data-ttu-id="30bc4-112">此格式仅用于自助注册。</span><span class="sxs-lookup"><span data-stu-id="30bc4-112">This format is for self-service registration only.</span></span> <span data-ttu-id="30bc4-113">在[面向合作伙伴的 Microsoft 托管桌面中的注册设备](register-devices-partner.md)中记录了合作伙伴应使用的格式。</span><span class="sxs-lookup"><span data-stu-id="30bc4-113">The format Partners should use is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="30bc4-114">这些值用于显示目的, 无需完全匹配设备的属性。</span><span class="sxs-lookup"><span data-stu-id="30bc4-114">These values are used for display purposes, and don't need to match properties from the device exactly.</span></span>
- <span data-ttu-id="30bc4-115">设备制造商 (示例: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="30bc4-115">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="30bc4-116">设备模型 (示例: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="30bc4-116">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="30bc4-117">设备序列号</span><span class="sxs-lookup"><span data-stu-id="30bc4-117">Device serial number</span></span>

<span data-ttu-id="30bc4-118">硬件哈希必须是完全匹配。</span><span class="sxs-lookup"><span data-stu-id="30bc4-118">The hardware hash must be an exact match.</span></span>
- <span data-ttu-id="30bc4-119">硬件哈希</span><span class="sxs-lookup"><span data-stu-id="30bc4-119">Hardware hash</span></span>

<span data-ttu-id="30bc4-120">若要获取硬件哈希, 可以从 OEM 或合作伙伴寻求帮助, 也可以对每个设备执行以下步骤:</span><span class="sxs-lookup"><span data-stu-id="30bc4-120">To obtain the hardware hash you can ask for help from your OEM or Partner, or follow these steps for each device:</span></span>

1.  <span data-ttu-id="30bc4-121">打开具有管理权限的 PowerShell 提示。</span><span class="sxs-lookup"><span data-stu-id="30bc4-121">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="30bc4-122">以`Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="30bc4-122">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="30bc4-123">以`powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="30bc4-123">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>


<span data-ttu-id="30bc4-124">或者, 您可以在全新设备上执行以下步骤 (在第一次进入 OOBE 之前):</span><span class="sxs-lookup"><span data-stu-id="30bc4-124">Alternately, you can follow these steps on a brand-new device (before going through OOBE for the first time):</span></span>

1. <span data-ttu-id="30bc4-125">在其他设备上, 插入 u 盘。</span><span class="sxs-lookup"><span data-stu-id="30bc4-125">On a different device, insert a USB drive.</span></span>
2. <span data-ttu-id="30bc4-126">打开具有管理权限的 PowerShell 提示。</span><span class="sxs-lookup"><span data-stu-id="30bc4-126">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="30bc4-127">以`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="30bc4-127">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="30bc4-128">打开目标设备, 但不要启动安装程序体验。</span><span class="sxs-lookup"><span data-stu-id="30bc4-128">Turn on the target device, but do not start the setup experience.</span></span> <span data-ttu-id="30bc4-129">如果您意外启动了设置体验, 则必须重置或重新映像设备。</span><span class="sxs-lookup"><span data-stu-id="30bc4-129">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="30bc4-130">插入 u 盘, 然后按 SHIFT + F10。</span><span class="sxs-lookup"><span data-stu-id="30bc4-130">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="30bc4-131">打开具有管理权限的 PowerShell 提示符, 然后运行`cd <pathToUsb>`。</span><span class="sxs-lookup"><span data-stu-id="30bc4-131">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="30bc4-132">以`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="30bc4-132">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="30bc4-133">以`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="30bc4-133">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
3. <span data-ttu-id="30bc4-134">删除 USB 驱动器, 然后通过运行来关闭设备`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="30bc4-134">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="30bc4-135">在完成对目标设备的注册之前, 请勿再次打开目标设备。</span><span class="sxs-lookup"><span data-stu-id="30bc4-135">Do not power on the target device again until you've completed registration for it.</span></span> 

>[!NOTE]
><span data-ttu-id="30bc4-136">为方便起见, 可以下载此 CSV 文件的[模板](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/live/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="30bc4-136">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/live/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) for this CSV file.</span></span>

<span data-ttu-id="30bc4-137">您的文件需要包含与示例 1 (制造商、模型等)**完全相同的列标题**, 但您自己的数据用于其他行。</span><span class="sxs-lookup"><span data-stu-id="30bc4-137">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="30bc4-138">如果使用模板, 请在文本编辑工具 (如记事本) 中打开它, 并考虑仅保留第1行中的所有数据, 仅在第2行和更低的行中输入数据。</span><span class="sxs-lookup"><span data-stu-id="30bc4-138">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="30bc4-139">如果您忘记更改任何示例数据, 则注册将失败。</span><span class="sxs-lookup"><span data-stu-id="30bc4-139">If you forget to change any of the sample data, registration will fail.</span></span>   


## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="30bc4-140">使用 Azure 门户注册设备</span><span class="sxs-lookup"><span data-stu-id="30bc4-140">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="30bc4-141">在 Microsoft 托管桌面[Azure 门户](https://aka.ms/mmdportal)中, 在左侧导航窗格中选择 "**设备**"。</span><span class="sxs-lookup"><span data-stu-id="30bc4-141">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="30bc4-142">选择 **+ 注册设备**;将打开 "飞入":</span><span class="sxs-lookup"><span data-stu-id="30bc4-142">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="30bc4-143">[![选择注册设备后飞入](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="30bc4-143">[![Fly-in after selecting Register devices](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (遗憾的是这不成立。我们可以删除此注释-但现在将其保留, 直到我们有机会聊天它。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="30bc4-145">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="30bc4-145">Follow these steps:</span></span>

1. <span data-ttu-id="30bc4-146">在 "**文件上载**" 中, 提供以前创建的 CSV 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="30bc4-146">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="30bc4-147">(可选) 可以出于自己的跟踪目的添加**订单 id**或**购买 ID** 。</span><span class="sxs-lookup"><span data-stu-id="30bc4-147">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="30bc4-148">这些值没有格式要求。</span><span class="sxs-lookup"><span data-stu-id="30bc4-148">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="30bc4-149">选择 "**注册设备**"。</span><span class="sxs-lookup"><span data-stu-id="30bc4-149">Select **Register devices**.</span></span> <span data-ttu-id="30bc4-150">系统会将设备添加到**设备边栏**上的设备列表中, 并标记为 "**注册挂起**"。</span><span class="sxs-lookup"><span data-stu-id="30bc4-150">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="30bc4-151">注册通常需要不到10分钟的时间, 如果成功, 设备将显示为 "已**准备就绪**, 以供用户使用", 表示它已准备就绪, 正在等待最终用户开始使用。</span><span class="sxs-lookup"><span data-stu-id="30bc4-151">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="30bc4-152">你可以在主**Microsoft 托管台式机-设备**页面上监视设备注册的进度。</span><span class="sxs-lookup"><span data-stu-id="30bc4-152">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="30bc4-153">可能报告的状态包括:</span><span class="sxs-lookup"><span data-stu-id="30bc4-153">Possible states reported there include:</span></span>

| <span data-ttu-id="30bc4-154">状态</span><span class="sxs-lookup"><span data-stu-id="30bc4-154">State</span></span> | <span data-ttu-id="30bc4-155">说明</span><span class="sxs-lookup"><span data-stu-id="30bc4-155">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="30bc4-156">注册挂起</span><span class="sxs-lookup"><span data-stu-id="30bc4-156">Registration pending</span></span> | <span data-ttu-id="30bc4-157">注册尚未完成。</span><span class="sxs-lookup"><span data-stu-id="30bc4-157">Registration is not done yet.</span></span> <span data-ttu-id="30bc4-158">稍后再次查看。</span><span class="sxs-lookup"><span data-stu-id="30bc4-158">Check back later.</span></span> |
| <span data-ttu-id="30bc4-159">注册失败</span><span class="sxs-lookup"><span data-stu-id="30bc4-159">Registration failed</span></span> | <span data-ttu-id="30bc4-160">无法完成注册。</span><span class="sxs-lookup"><span data-stu-id="30bc4-160">Registration could not be completed.</span></span> <span data-ttu-id="30bc4-161">有关详细信息, 请参阅[故障排除](register-devices-self.md#troubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="30bc4-161">Refer to [Troubleshooting](register-devices-self.md#troubleshooting) for more information.</span></span> |
| <span data-ttu-id="30bc4-162">为用户准备就绪</span><span class="sxs-lookup"><span data-stu-id="30bc4-162">Ready for user</span></span> | <span data-ttu-id="30bc4-163">注册成功, 现在设备已准备好传递给最终用户。</span><span class="sxs-lookup"><span data-stu-id="30bc4-163">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="30bc4-164">Microsoft 托管桌面将在首次设置时引导他们, 因此无需执行任何进一步的准备。</span><span class="sxs-lookup"><span data-stu-id="30bc4-164">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="30bc4-165">Active</span><span class="sxs-lookup"><span data-stu-id="30bc4-165">Active</span></span> | <span data-ttu-id="30bc4-166">设备已传递给最终用户, 并且已向其注册了你的租户。</span><span class="sxs-lookup"><span data-stu-id="30bc4-166">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="30bc4-167">这也表明它们是定期使用设备的。</span><span class="sxs-lookup"><span data-stu-id="30bc4-167">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="30bc4-168">不再</span><span class="sxs-lookup"><span data-stu-id="30bc4-168">Inactive</span></span> | <span data-ttu-id="30bc4-169">设备已传递给最终用户, 并且已向其注册了你的租户。</span><span class="sxs-lookup"><span data-stu-id="30bc4-169">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="30bc4-170">但是, 他们最近未使用设备 (最近7天)。</span><span class="sxs-lookup"><span data-stu-id="30bc4-170">However, they have not used the device recently (in the last 7 days).</span></span>  | 


## <a name="register-devices-by-using-an-api"></a><span data-ttu-id="30bc4-171">使用 API 注册设备</span><span class="sxs-lookup"><span data-stu-id="30bc4-171">Register devices by using an API</span></span>

<span data-ttu-id="30bc4-172">REST API 可用于实现更大的灵活性和重复频繁单独的设备注册。</span><span class="sxs-lookup"><span data-stu-id="30bc4-172">A REST API is available to allow you greater flexibility and repeatability with frequent separate device registrations.</span></span> <span data-ttu-id="30bc4-173">目前, 若要使用 API, 请询问 Microsoft 联系人的帮助, 以加入此功能的预览。</span><span class="sxs-lookup"><span data-stu-id="30bc4-173">Currently, to use the API, ask for help from your Microsoft contact to join a preview of this capability.</span></span>



## <a name="troubleshooting"></a><span data-ttu-id="30bc4-174">故障排除</span><span class="sxs-lookup"><span data-stu-id="30bc4-174">Troubleshooting</span></span>

| <span data-ttu-id="30bc4-175">错误消息</span><span class="sxs-lookup"><span data-stu-id="30bc4-175">Error message</span></span> | <span data-ttu-id="30bc4-176">详细信息</span><span class="sxs-lookup"><span data-stu-id="30bc4-176">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="30bc4-177">找不到设备</span><span class="sxs-lookup"><span data-stu-id="30bc4-177">Device not found</span></span> | <span data-ttu-id="30bc4-178">无法注册此设备, 因为我们找不到提供的制造商、型号或序列号的匹配项。</span><span class="sxs-lookup"><span data-stu-id="30bc4-178">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="30bc4-179">请与设备供应商确认这些值。</span><span class="sxs-lookup"><span data-stu-id="30bc4-179">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="30bc4-180">找不到设备</span><span class="sxs-lookup"><span data-stu-id="30bc4-180">Device not found</span></span> | <span data-ttu-id="30bc4-181">无法注册此设备, 因为它在你的组织中不存在。</span><span class="sxs-lookup"><span data-stu-id="30bc4-181">We couldn’t de-register this device because it does not exist in your organization.</span></span> <span data-ttu-id="30bc4-182">无需执行进一步操作。</span><span class="sxs-lookup"><span data-stu-id="30bc4-182">No further action required.</span></span> |
| <span data-ttu-id="30bc4-183">硬件哈希无效</span><span class="sxs-lookup"><span data-stu-id="30bc4-183">Hardware hash not valid</span></span> | <span data-ttu-id="30bc4-184">为此设备提供的硬件哈希格式不正确。</span><span class="sxs-lookup"><span data-stu-id="30bc4-184">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="30bc4-185">仔细检查硬件哈希, 然后重新提交。</span><span class="sxs-lookup"><span data-stu-id="30bc4-185">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="30bc4-186">已注册设备</span><span class="sxs-lookup"><span data-stu-id="30bc4-186">Device already registered</span></span> | <span data-ttu-id="30bc4-187">此设备已注册到你的组织。</span><span class="sxs-lookup"><span data-stu-id="30bc4-187">This device is already registered to your organization.</span></span> <span data-ttu-id="30bc4-188">无需执行进一步操作。</span><span class="sxs-lookup"><span data-stu-id="30bc4-188">No further action required.</span></span> |
| <span data-ttu-id="30bc4-189">其他组织声明的设备</span><span class="sxs-lookup"><span data-stu-id="30bc4-189">Device claimed by another organization</span></span> | <span data-ttu-id="30bc4-190">此设备已由其他组织声明。</span><span class="sxs-lookup"><span data-stu-id="30bc4-190">This device has already been claimed by another organization.</span></span> <span data-ttu-id="30bc4-191">请与设备供应商联系。</span><span class="sxs-lookup"><span data-stu-id="30bc4-191">Check with your device supplier.</span></span> |
| <span data-ttu-id="30bc4-192">意外错误</span><span class="sxs-lookup"><span data-stu-id="30bc4-192">Unexpected error</span></span> | <span data-ttu-id="30bc4-193">无法自动处理你的请求。</span><span class="sxs-lookup"><span data-stu-id="30bc4-193">Your request could not be automatically processed.</span></span> <span data-ttu-id="30bc4-194">联系支持人员并提供请求 ID:<requestId></span><span class="sxs-lookup"><span data-stu-id="30bc4-194">Contact Support and provide the Request ID: <requestId></span></span> |




