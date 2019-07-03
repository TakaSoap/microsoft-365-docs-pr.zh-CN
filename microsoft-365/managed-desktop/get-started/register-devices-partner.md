---
title: 在 Microsoft 托管桌面中为合作伙伴注册设备
description: 合作伙伴如何注册设备以便 Microsoft 托管桌面可以管理它们
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 06ec98ebc7ea44a1bf3d8039e3a3ab7102521d3e
ms.sourcegitcommit: ef749c44d72b5258706be86a4af1aeca4154ead2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35447524"
---
# <a name="register-devices-in-microsoft-managed-desktop-for-partners"></a><span data-ttu-id="0ce23-103">在 Microsoft 托管桌面中为合作伙伴注册设备</span><span class="sxs-lookup"><span data-stu-id="0ce23-103">Register devices in Microsoft Managed Desktop for Partners</span></span>


<span data-ttu-id="0ce23-104">本主题介绍了合作伙伴在注册设备时应遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="0ce23-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="0ce23-105">您自己注册设备的过程记录在[Microsoft 托管桌面的注册设备](register-devices-self.md)中。</span><span class="sxs-lookup"><span data-stu-id="0ce23-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="0ce23-106">准备注册</span><span class="sxs-lookup"><span data-stu-id="0ce23-106">Prepare for registration</span></span> 
<span data-ttu-id="0ce23-107">在完成客户注册之前, 必须首先在[合作伙伴中心](https://partner.microsoft.com/dashboard)建立与它们的关系。</span><span class="sxs-lookup"><span data-stu-id="0ce23-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="0ce23-108">请务必选择 "**包括 Azure Active Directory 和 Office 365 的委派管理权限**"。</span><span class="sxs-lookup"><span data-stu-id="0ce23-108">Be sure to select **Include delegated administration privileges for Azure Active Directory and Office 365**.</span></span> <span data-ttu-id="0ce23-109">有关详细信息, 请参阅[合作伙伴中心帮助](https://docs.microsoft.com/en-us/partner-center/request-a-relationship-with-a-customer)。</span><span class="sxs-lookup"><span data-stu-id="0ce23-109">Learn more at [Partner Center help](https://docs.microsoft.com/en-us/partner-center/request-a-relationship-with-a-customer).</span></span>

<span data-ttu-id="0ce23-110">若要完成对客户的注册, 请首先创建 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="0ce23-110">To complete registration for your customer, first create a CSV file.</span></span>

>[!NOTE]
><span data-ttu-id="0ce23-111">为方便起见, 可以下载 CSV 文件的此*合作伙伴版本*的[模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="0ce23-111">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) for this *Partner version* of the CSV file.</span></span>

<span data-ttu-id="0ce23-112">您的文件需要包含与示例 1 (制造商、模型等)**完全相同的列标题**, 但您自己的数据用于其他行。</span><span class="sxs-lookup"><span data-stu-id="0ce23-112">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="0ce23-113">如果使用模板, 请在文本编辑工具 (如记事本) 中打开它, 并考虑仅保留第1行中的所有数据, 仅在第2行和更低的行中输入数据。</span><span class="sxs-lookup"><span data-stu-id="0ce23-113">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```


>[!NOTE]
><span data-ttu-id="0ce23-114">此格式仅适用于合作伙伴流程。</span><span class="sxs-lookup"><span data-stu-id="0ce23-114">This format is only for the Partner process.</span></span> <span data-ttu-id="0ce23-115">自行注册的过程在[Microsoft 托管桌面的注册设备](register-devices-self.md)中进行了记录。</span><span class="sxs-lookup"><span data-stu-id="0ce23-115">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="0ce23-116">这些值必须与 SMBIOS 中的制造商值完全匹配。</span><span class="sxs-lookup"><span data-stu-id="0ce23-116">These values must match the manufacturer values from SMBIOS exactly.</span></span> <span data-ttu-id="0ce23-117">还必须在第一行中包含*硬件哈希*(但在第二行中没有它的值), 在第二行中的*序列号*值后面的尾部逗号。</span><span class="sxs-lookup"><span data-stu-id="0ce23-117">You must also include *Hardware Hash* in the first row (but no value for it in the second row) the trailing comma after the *Serial Number* value in the second row.</span></span>

- <span data-ttu-id="0ce23-118">设备制造商 (示例: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="0ce23-118">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="0ce23-119">设备模型 (示例: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="0ce23-119">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="0ce23-120">设备序列号</span><span class="sxs-lookup"><span data-stu-id="0ce23-120">Device serial number</span></span>

## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="0ce23-121">使用 Azure 门户注册设备</span><span class="sxs-lookup"><span data-stu-id="0ce23-121">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="0ce23-122">使用 Azure 门户注册与自助服务相同, 不同之处在于, 访问门户的方式不同。</span><span class="sxs-lookup"><span data-stu-id="0ce23-122">Registering by using the Azure Portal is the same as for self-service, except you access the portal differently.</span></span> <span data-ttu-id="0ce23-123">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="0ce23-123">Follow these steps:</span></span>

1. <span data-ttu-id="0ce23-124">导航到 "[合作伙伴中心](https://partner.microsoft.com/dashboard)"</span><span class="sxs-lookup"><span data-stu-id="0ce23-124">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="0ce23-125">选择 "**客户**"。</span><span class="sxs-lookup"><span data-stu-id="0ce23-125">Select **Customers**.</span></span>
3. <span data-ttu-id="0ce23-126">选择要管理的客户。</span><span class="sxs-lookup"><span data-stu-id="0ce23-126">Select the customer you want to manage.</span></span>
4. <span data-ttu-id="0ce23-127">选择 "**服务管理**"。</span><span class="sxs-lookup"><span data-stu-id="0ce23-127">Select **Service Administration**.</span></span>
5. <span data-ttu-id="0ce23-128">选择 " **Intune**"。</span><span class="sxs-lookup"><span data-stu-id="0ce23-128">Select **Intune**.</span></span>
6. <span data-ttu-id="0ce23-129">在 Azure 门户的顶部搜索框中搜索 "mmd"。</span><span class="sxs-lookup"><span data-stu-id="0ce23-129">Search for "mmd" in the top search box of the Azure portal.</span></span>
7. <span data-ttu-id="0ce23-130">选择 "**设备**"。</span><span class="sxs-lookup"><span data-stu-id="0ce23-130">Select **Devices**.</span></span>
8. <span data-ttu-id="0ce23-131">在 "**文件上载**" 中, 提供以前创建的 CSV 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="0ce23-131">In **File upload**, provide a path to the CSV file you created previously.</span></span>
9. <span data-ttu-id="0ce23-132">(可选) 可以出于自己的跟踪目的添加**订单 id**或**购买 ID** 。</span><span class="sxs-lookup"><span data-stu-id="0ce23-132">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="0ce23-133">这些值没有格式要求。</span><span class="sxs-lookup"><span data-stu-id="0ce23-133">There are no format requirements for these values.</span></span>
10. <span data-ttu-id="0ce23-134">选择 "**注册设备**"。</span><span class="sxs-lookup"><span data-stu-id="0ce23-134">Select **Register devices**.</span></span> <span data-ttu-id="0ce23-135">系统会将设备添加到**设备边栏**上的设备列表中, 并标记为 "**注册挂起**"。</span><span class="sxs-lookup"><span data-stu-id="0ce23-135">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="0ce23-136">注册通常需要不到10分钟的时间, 如果成功, 设备将显示为 "已**准备就绪**, 以供用户使用", 表示它已准备就绪, 正在等待最终用户开始使用。</span><span class="sxs-lookup"><span data-stu-id="0ce23-136">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="0ce23-137">你可以在主**Microsoft 托管台式机-设备**页面上监视设备注册的进度。</span><span class="sxs-lookup"><span data-stu-id="0ce23-137">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="0ce23-138">可能报告的状态包括:</span><span class="sxs-lookup"><span data-stu-id="0ce23-138">Possible states reported there include:</span></span>

| <span data-ttu-id="0ce23-139">状态</span><span class="sxs-lookup"><span data-stu-id="0ce23-139">State</span></span> | <span data-ttu-id="0ce23-140">说明</span><span class="sxs-lookup"><span data-stu-id="0ce23-140">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="0ce23-141">注册挂起</span><span class="sxs-lookup"><span data-stu-id="0ce23-141">Registration pending</span></span> | <span data-ttu-id="0ce23-142">注册尚未完成。</span><span class="sxs-lookup"><span data-stu-id="0ce23-142">Registration is not done yet.</span></span> <span data-ttu-id="0ce23-143">稍后再次查看。</span><span class="sxs-lookup"><span data-stu-id="0ce23-143">Check back later.</span></span> |
| <span data-ttu-id="0ce23-144">注册失败</span><span class="sxs-lookup"><span data-stu-id="0ce23-144">Registration failed</span></span> | <span data-ttu-id="0ce23-145">无法完成注册。</span><span class="sxs-lookup"><span data-stu-id="0ce23-145">Registration could not be completed.</span></span> <span data-ttu-id="0ce23-146">有关详细信息, 请参阅[故障排除](register-devices-self.md#troubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="0ce23-146">Refer to [Troubleshooting](register-devices-self.md#troubleshooting) for more information.</span></span> |
| <span data-ttu-id="0ce23-147">为用户准备就绪</span><span class="sxs-lookup"><span data-stu-id="0ce23-147">Ready for user</span></span> | <span data-ttu-id="0ce23-148">注册成功, 现在设备已准备好传递给最终用户。</span><span class="sxs-lookup"><span data-stu-id="0ce23-148">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="0ce23-149">Microsoft 托管桌面将在首次设置时引导他们, 因此无需执行任何进一步的准备。</span><span class="sxs-lookup"><span data-stu-id="0ce23-149">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="0ce23-150">活动</span><span class="sxs-lookup"><span data-stu-id="0ce23-150">Active</span></span> | <span data-ttu-id="0ce23-151">设备已传递给最终用户, 并且已向其注册了你的租户。</span><span class="sxs-lookup"><span data-stu-id="0ce23-151">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="0ce23-152">这也表明它们是定期使用设备的。</span><span class="sxs-lookup"><span data-stu-id="0ce23-152">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="0ce23-153">不再</span><span class="sxs-lookup"><span data-stu-id="0ce23-153">Inactive</span></span> | <span data-ttu-id="0ce23-154">设备已传递给最终用户, 并且已向其注册了你的租户。</span><span class="sxs-lookup"><span data-stu-id="0ce23-154">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="0ce23-155">但是, 他们最近未使用设备 (最近7天)。</span><span class="sxs-lookup"><span data-stu-id="0ce23-155">However, they have not used the device recently (in the last 7 days).</span></span>  |

## <a name="register-devices-by-using-an-api"></a><span data-ttu-id="0ce23-156">使用 API 注册设备</span><span class="sxs-lookup"><span data-stu-id="0ce23-156">Register devices by using an API</span></span>

<span data-ttu-id="0ce23-157">通过 API 注册与自助服务相同, 不同之处在于, 设备集合的硬件哈希属性是可选的, 如 CSV 部分中所述。</span><span class="sxs-lookup"><span data-stu-id="0ce23-157">Registering by API is the same as self-service, except that the hardware hash property of the device collection is optional as described in the CSV section.</span></span> 

## <a name="troubleshooting"></a><span data-ttu-id="0ce23-158">疑难解答</span><span class="sxs-lookup"><span data-stu-id="0ce23-158">Troubleshooting</span></span>

| <span data-ttu-id="0ce23-159">错误消息</span><span class="sxs-lookup"><span data-stu-id="0ce23-159">Error message</span></span> | <span data-ttu-id="0ce23-160">详细信息</span><span class="sxs-lookup"><span data-stu-id="0ce23-160">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="0ce23-161">找不到设备</span><span class="sxs-lookup"><span data-stu-id="0ce23-161">Device not found</span></span> | <span data-ttu-id="0ce23-162">无法注册此设备, 因为我们找不到提供的制造商、型号或序列号的匹配项。</span><span class="sxs-lookup"><span data-stu-id="0ce23-162">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="0ce23-163">请与设备供应商确认这些值。</span><span class="sxs-lookup"><span data-stu-id="0ce23-163">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="0ce23-164">找不到设备</span><span class="sxs-lookup"><span data-stu-id="0ce23-164">Device not found</span></span> | <span data-ttu-id="0ce23-165">无法注册此设备, 因为它在你的组织中不存在。</span><span class="sxs-lookup"><span data-stu-id="0ce23-165">We couldn’t de-register this device because it does not exist in your organization.</span></span> <span data-ttu-id="0ce23-166">无需执行进一步操作。</span><span class="sxs-lookup"><span data-stu-id="0ce23-166">No further action required.</span></span> |
| <span data-ttu-id="0ce23-167">硬件哈希无效</span><span class="sxs-lookup"><span data-stu-id="0ce23-167">Hardware hash not valid</span></span> | <span data-ttu-id="0ce23-168">为此设备提供的硬件哈希格式不正确。</span><span class="sxs-lookup"><span data-stu-id="0ce23-168">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="0ce23-169">仔细检查硬件哈希, 然后重新提交。</span><span class="sxs-lookup"><span data-stu-id="0ce23-169">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="0ce23-170">已注册设备</span><span class="sxs-lookup"><span data-stu-id="0ce23-170">Device already registered</span></span> | <span data-ttu-id="0ce23-171">此设备已注册到你的组织。</span><span class="sxs-lookup"><span data-stu-id="0ce23-171">This device is already registered to your organization.</span></span> <span data-ttu-id="0ce23-172">无需执行进一步操作。</span><span class="sxs-lookup"><span data-stu-id="0ce23-172">No further action required.</span></span> |
| <span data-ttu-id="0ce23-173">其他组织声明的设备</span><span class="sxs-lookup"><span data-stu-id="0ce23-173">Device claimed by another organization</span></span> | <span data-ttu-id="0ce23-174">此设备已由其他组织声明。</span><span class="sxs-lookup"><span data-stu-id="0ce23-174">This device has already been claimed by another organization.</span></span> <span data-ttu-id="0ce23-175">请与设备供应商联系。</span><span class="sxs-lookup"><span data-stu-id="0ce23-175">Check with your device supplier.</span></span> |
| <span data-ttu-id="0ce23-176">意外错误</span><span class="sxs-lookup"><span data-stu-id="0ce23-176">Unexpected error</span></span> | <span data-ttu-id="0ce23-177">无法自动处理你的请求。</span><span class="sxs-lookup"><span data-stu-id="0ce23-177">Your request could not be automatically processed.</span></span> <span data-ttu-id="0ce23-178">联系支持人员<support link>() 并提供请求 ID:<requestId></span><span class="sxs-lookup"><span data-stu-id="0ce23-178">Contact Support (<support link>) and provide the Request ID: <requestId></span></span> |
