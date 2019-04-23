---
title: 在 Microsoft 托管桌面中为合作伙伴注册设备
description: 合作伙伴如何注册设备以便 Microsoft 托管桌面可以管理它们
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 23a2eae6435f5ce234cf6406f2753ec54f675bce
ms.sourcegitcommit: 7af6350fb5a6d37934c1b6bfdc38acd09b2d5d86
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "31988418"
---
# <a name="register-devices-in-microsoft-managed-desktop-for-partners"></a><span data-ttu-id="35aa5-103">在 Microsoft 托管桌面中为合作伙伴注册设备</span><span class="sxs-lookup"><span data-stu-id="35aa5-103">Register devices in Microsoft Managed Desktop for Partners</span></span>


<span data-ttu-id="35aa5-104">本主题介绍了合作伙伴在注册设备时应遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="35aa5-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="35aa5-105">您自己注册设备的过程记录在[Microsoft 托管桌面的注册设备](register-devices-self.md)中。</span><span class="sxs-lookup"><span data-stu-id="35aa5-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="35aa5-106">准备注册</span><span class="sxs-lookup"><span data-stu-id="35aa5-106">Prepare for registration</span></span> 
<span data-ttu-id="35aa5-107">在完成客户注册之前, 必须首先在[合作伙伴中心](https://partner.microsoft.com/dashboard)建立与它们的关系。</span><span class="sxs-lookup"><span data-stu-id="35aa5-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="35aa5-108">有关详细信息, 请参阅[合作伙伴中心帮助](https://docs.microsoft.com/en-us/partner-center/request-a-relationship-with-a-customer)。</span><span class="sxs-lookup"><span data-stu-id="35aa5-108">Learn more at [Partner Center help](https://docs.microsoft.com/en-us/partner-center/request-a-relationship-with-a-customer).</span></span>

<span data-ttu-id="35aa5-109">若要完成对客户的注册, 请首先创建 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="35aa5-109">To complete registration for your customer, first create a CSV file.</span></span>

>[!NOTE]
><span data-ttu-id="35aa5-110">为方便起见, 可以下载 CSV 文件的此*合作伙伴版本*的[模板](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/live/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="35aa5-110">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/live/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this *Partner version* of the CSV file.</span></span>

<span data-ttu-id="35aa5-111">您的文件需要包含与示例 1 (制造商、模型等)**完全相同的列标题**, 但您自己的数据用于其他行。</span><span class="sxs-lookup"><span data-stu-id="35aa5-111">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="35aa5-112">如果使用模板, 请在文本编辑工具 (如记事本) 中打开它, 并考虑仅保留第1行中的所有数据, 仅在第2行和更低的行中输入数据。</span><span class="sxs-lookup"><span data-stu-id="35aa5-112">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,
  
  
  ```


>[!NOTE]
><span data-ttu-id="35aa5-113">此格式仅适用于合作伙伴流程。</span><span class="sxs-lookup"><span data-stu-id="35aa5-113">This format is only for the Partner process.</span></span> <span data-ttu-id="35aa5-114">自行注册的过程在[Microsoft 托管桌面的注册设备](register-devices-self.md)中进行了记录。</span><span class="sxs-lookup"><span data-stu-id="35aa5-114">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="35aa5-115">这些值必须与 SMBIOS 中的制造商值完全匹配。</span><span class="sxs-lookup"><span data-stu-id="35aa5-115">These values must match the manufacturer values from SMBIOS exactly.</span></span> <span data-ttu-id="35aa5-116">还必须在第一行中包含*硬件哈希*(但在第二行中没有它的值), 在第二行中的*序列号*值后面的尾部逗号。</span><span class="sxs-lookup"><span data-stu-id="35aa5-116">You must also include *Hardware Hash* in the first row (but no value for it in the second row) the trailing comma after the *Serial Number* value in the second row.</span></span>

- <span data-ttu-id="35aa5-117">设备制造商 (示例: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="35aa5-117">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="35aa5-118">设备模型 (示例: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="35aa5-118">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="35aa5-119">设备序列号</span><span class="sxs-lookup"><span data-stu-id="35aa5-119">Device serial number</span></span>

## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="35aa5-120">使用 Azure 门户注册设备</span><span class="sxs-lookup"><span data-stu-id="35aa5-120">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="35aa5-121">使用 Azure 门户注册与自助服务相同, 不同之处在于, 访问门户的方式不同。</span><span class="sxs-lookup"><span data-stu-id="35aa5-121">Registering by using the Azure Portal is the same as for self-service, except you access the portal differently.</span></span> <span data-ttu-id="35aa5-122">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="35aa5-122">Follow these steps:</span></span>

1. <span data-ttu-id="35aa5-123">导航到 "[合作伙伴中心](https://partner.microsoft.com/dashboard)"</span><span class="sxs-lookup"><span data-stu-id="35aa5-123">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="35aa5-124">选择 "**客户**"。</span><span class="sxs-lookup"><span data-stu-id="35aa5-124">Select **Customers**.</span></span>
3. <span data-ttu-id="35aa5-125">选择要管理的客户。</span><span class="sxs-lookup"><span data-stu-id="35aa5-125">Select the customer you want to manage.</span></span>
4. <span data-ttu-id="35aa5-126">选择 "**服务管理**"。</span><span class="sxs-lookup"><span data-stu-id="35aa5-126">Select **Service Administration**.</span></span>
5. <span data-ttu-id="35aa5-127">选择 " **Intune**"。</span><span class="sxs-lookup"><span data-stu-id="35aa5-127">Select **Intune**.</span></span>
6. <span data-ttu-id="35aa5-128">在 Azure 门户的顶部搜索框中搜索 "mmd"。</span><span class="sxs-lookup"><span data-stu-id="35aa5-128">Search for "mmd" in the top search box of the Azure portal.</span></span>
7. <span data-ttu-id="35aa5-129">选择 "**设备**"。</span><span class="sxs-lookup"><span data-stu-id="35aa5-129">Select **Devices**.</span></span>
8. <span data-ttu-id="35aa5-130">在 "**文件上载**" 中, 提供以前创建的 CSV 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="35aa5-130">In **File upload**, provide a path to the CSV file you created previously.</span></span>
9. <span data-ttu-id="35aa5-131">(可选) 可以出于自己的跟踪目的添加**订单 id**或**购买 ID** 。</span><span class="sxs-lookup"><span data-stu-id="35aa5-131">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="35aa5-132">这些值没有格式要求。</span><span class="sxs-lookup"><span data-stu-id="35aa5-132">There are no format requirements for these values.</span></span>
10. <span data-ttu-id="35aa5-133">选择 "**注册设备**"。</span><span class="sxs-lookup"><span data-stu-id="35aa5-133">Select **Register devices**.</span></span> <span data-ttu-id="35aa5-134">系统会将设备添加到**设备边栏**上的设备列表中, 并标记为 "**注册挂起**"。</span><span class="sxs-lookup"><span data-stu-id="35aa5-134">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="35aa5-135">注册通常需要不到10分钟的时间, 如果成功, 设备将显示为 "已**准备就绪**, 以供用户使用", 表示它已准备就绪, 正在等待最终用户开始使用。</span><span class="sxs-lookup"><span data-stu-id="35aa5-135">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="35aa5-136">你可以在主**Microsoft 托管台式机-设备**页面上监视设备注册的进度。</span><span class="sxs-lookup"><span data-stu-id="35aa5-136">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="35aa5-137">可能报告的状态包括:</span><span class="sxs-lookup"><span data-stu-id="35aa5-137">Possible states reported there include:</span></span>

| <span data-ttu-id="35aa5-138">状态</span><span class="sxs-lookup"><span data-stu-id="35aa5-138">State</span></span> | <span data-ttu-id="35aa5-139">说明</span><span class="sxs-lookup"><span data-stu-id="35aa5-139">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="35aa5-140">注册挂起</span><span class="sxs-lookup"><span data-stu-id="35aa5-140">Registration pending</span></span> | <span data-ttu-id="35aa5-141">注册尚未完成。</span><span class="sxs-lookup"><span data-stu-id="35aa5-141">Registration is not done yet.</span></span> <span data-ttu-id="35aa5-142">稍后再次查看。</span><span class="sxs-lookup"><span data-stu-id="35aa5-142">Check back later.</span></span> |
| <span data-ttu-id="35aa5-143">注册失败</span><span class="sxs-lookup"><span data-stu-id="35aa5-143">Registration failed</span></span> | <span data-ttu-id="35aa5-144">无法完成注册。</span><span class="sxs-lookup"><span data-stu-id="35aa5-144">Registration could not be completed.</span></span> <span data-ttu-id="35aa5-145">有关详细信息, 请参阅[故障排除](register-devices-self.md#troubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="35aa5-145">Refer to [Troubleshooting](register-devices-self.md#troubleshooting) for more information.</span></span> |
| <span data-ttu-id="35aa5-146">为用户准备就绪</span><span class="sxs-lookup"><span data-stu-id="35aa5-146">Ready for user</span></span> | <span data-ttu-id="35aa5-147">注册成功, 现在设备已准备好传递给最终用户。</span><span class="sxs-lookup"><span data-stu-id="35aa5-147">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="35aa5-148">Microsoft 托管桌面将在首次设置时引导他们, 因此无需执行任何进一步的准备。</span><span class="sxs-lookup"><span data-stu-id="35aa5-148">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="35aa5-149">Active</span><span class="sxs-lookup"><span data-stu-id="35aa5-149">Active</span></span> | <span data-ttu-id="35aa5-150">设备已传递给最终用户, 并且已向其注册了你的租户。</span><span class="sxs-lookup"><span data-stu-id="35aa5-150">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="35aa5-151">这也表明它们是定期使用设备的。</span><span class="sxs-lookup"><span data-stu-id="35aa5-151">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="35aa5-152">不再</span><span class="sxs-lookup"><span data-stu-id="35aa5-152">Inactive</span></span> | <span data-ttu-id="35aa5-153">设备已传递给最终用户, 并且已向其注册了你的租户。</span><span class="sxs-lookup"><span data-stu-id="35aa5-153">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="35aa5-154">但是, 他们最近未使用设备 (最近7天)。</span><span class="sxs-lookup"><span data-stu-id="35aa5-154">However, they have not used the device recently (in the last 7 days).</span></span>  |

## <a name="register-devices-by-using-an-api"></a><span data-ttu-id="35aa5-155">使用 API 注册设备</span><span class="sxs-lookup"><span data-stu-id="35aa5-155">Register devices by using an API</span></span>

<span data-ttu-id="35aa5-156">通过 API 注册与自助服务相同, 不同之处在于, 设备集合的硬件哈希属性是可选的, 如 CSV 部分中所述。</span><span class="sxs-lookup"><span data-stu-id="35aa5-156">Registering by API is the same as self-service, except that the hardware hash property of the device collection is optional as described in the CSV section.</span></span> 

## <a name="troubleshooting"></a><span data-ttu-id="35aa5-157">故障排除</span><span class="sxs-lookup"><span data-stu-id="35aa5-157">Troubleshooting</span></span>

| <span data-ttu-id="35aa5-158">错误消息</span><span class="sxs-lookup"><span data-stu-id="35aa5-158">Error message</span></span> | <span data-ttu-id="35aa5-159">详细信息</span><span class="sxs-lookup"><span data-stu-id="35aa5-159">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="35aa5-160">找不到设备</span><span class="sxs-lookup"><span data-stu-id="35aa5-160">Device not found</span></span> | <span data-ttu-id="35aa5-161">无法注册此设备, 因为我们找不到提供的制造商、型号或序列号的匹配项。</span><span class="sxs-lookup"><span data-stu-id="35aa5-161">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="35aa5-162">请与设备供应商确认这些值。</span><span class="sxs-lookup"><span data-stu-id="35aa5-162">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="35aa5-163">找不到设备</span><span class="sxs-lookup"><span data-stu-id="35aa5-163">Device not found</span></span> | <span data-ttu-id="35aa5-164">无法注册此设备, 因为它在你的组织中不存在。</span><span class="sxs-lookup"><span data-stu-id="35aa5-164">We couldn’t de-register this device because it does not exist in your organization.</span></span> <span data-ttu-id="35aa5-165">无需执行进一步操作。</span><span class="sxs-lookup"><span data-stu-id="35aa5-165">No further action required.</span></span> |
| <span data-ttu-id="35aa5-166">硬件哈希无效</span><span class="sxs-lookup"><span data-stu-id="35aa5-166">Hardware hash not valid</span></span> | <span data-ttu-id="35aa5-167">为此设备提供的硬件哈希格式不正确。</span><span class="sxs-lookup"><span data-stu-id="35aa5-167">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="35aa5-168">仔细检查硬件哈希, 然后重新提交。</span><span class="sxs-lookup"><span data-stu-id="35aa5-168">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="35aa5-169">已注册设备</span><span class="sxs-lookup"><span data-stu-id="35aa5-169">Device already registered</span></span> | <span data-ttu-id="35aa5-170">此设备已注册到你的组织。</span><span class="sxs-lookup"><span data-stu-id="35aa5-170">This device is already registered to your organization.</span></span> <span data-ttu-id="35aa5-171">无需执行进一步操作。</span><span class="sxs-lookup"><span data-stu-id="35aa5-171">No further action required.</span></span> |
| <span data-ttu-id="35aa5-172">其他组织声明的设备</span><span class="sxs-lookup"><span data-stu-id="35aa5-172">Device claimed by another organization</span></span> | <span data-ttu-id="35aa5-173">此设备已由其他组织声明。</span><span class="sxs-lookup"><span data-stu-id="35aa5-173">This device has already been claimed by another organization.</span></span> <span data-ttu-id="35aa5-174">请与设备供应商联系。</span><span class="sxs-lookup"><span data-stu-id="35aa5-174">Check with your device supplier.</span></span> |
| <span data-ttu-id="35aa5-175">意外错误</span><span class="sxs-lookup"><span data-stu-id="35aa5-175">Unexpected error</span></span> | <span data-ttu-id="35aa5-176">无法自动处理你的请求。</span><span class="sxs-lookup"><span data-stu-id="35aa5-176">Your request could not be automatically processed.</span></span> <span data-ttu-id="35aa5-177">联系支持人员<support link>() 并提供请求 ID:<requestId></span><span class="sxs-lookup"><span data-stu-id="35aa5-177">Contact Support (<support link>) and provide the Request ID: <requestId></span></span> |