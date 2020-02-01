---
title: 合作伙伴注册设备的步骤
description: 合作伙伴如何注册设备以便 Microsoft 托管桌面可以管理它们
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: a9a2a0ccb1e0830d674f4b1b1ef5495fafb38ca3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596549"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="d1797-103">合作伙伴注册设备的步骤</span><span class="sxs-lookup"><span data-stu-id="d1797-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="d1797-104">本主题介绍了合作伙伴在注册设备时应遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="d1797-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="d1797-105">您自己注册设备的过程记录在[Microsoft 托管桌面的注册设备](register-devices-self.md)中。</span><span class="sxs-lookup"><span data-stu-id="d1797-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="d1797-106">准备注册</span><span class="sxs-lookup"><span data-stu-id="d1797-106">Prepare for registration</span></span> 
<span data-ttu-id="d1797-107">在完成客户注册之前，必须首先在[合作伙伴中心](https://partner.microsoft.com/dashboard)建立与它们的关系。</span><span class="sxs-lookup"><span data-stu-id="d1797-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="d1797-108">请务必选择 "**包括 Azure Active Directory 和 Office 365 的委派管理权限**"。</span><span class="sxs-lookup"><span data-stu-id="d1797-108">Be sure to select **Include delegated administration privileges for Azure Active Directory and Office 365**.</span></span> <span data-ttu-id="d1797-109">有关详细信息，请参阅[合作伙伴中心帮助](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)。</span><span class="sxs-lookup"><span data-stu-id="d1797-109">Learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span>

<span data-ttu-id="d1797-110">若要完成对客户的注册，请首先创建 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="d1797-110">To complete registration for your customer, first create a CSV file.</span></span>

>[!NOTE]
><span data-ttu-id="d1797-111">为方便起见，可以为此*合作伙伴版本*下载一个[示例 CSV 文件](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv)。</span><span class="sxs-lookup"><span data-stu-id="d1797-111">For your convenience, you can download a [sample CSV file](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv) for this *Partner version*.</span></span>

<span data-ttu-id="d1797-112">您的文件需要包含与示例1（制造商、模型等）**完全相同的列标题**，但您自己的数据用于其他行。</span><span class="sxs-lookup"><span data-stu-id="d1797-112">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="d1797-113">如果使用模板，请在文本编辑工具（如记事本）中打开它，并考虑仅保留第1行中的所有数据，仅在第2行和更低的行中输入数据。</span><span class="sxs-lookup"><span data-stu-id="d1797-113">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```




>[!NOTE]
><span data-ttu-id="d1797-114">此格式仅适用于合作伙伴流程。</span><span class="sxs-lookup"><span data-stu-id="d1797-114">This format is only for the Partner process.</span></span> <span data-ttu-id="d1797-115">自行注册的过程在[Microsoft 托管桌面的注册设备](register-devices-self.md)中进行了记录。</span><span class="sxs-lookup"><span data-stu-id="d1797-115">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="d1797-116">这些值必须与 SMBIOS 中的制造商值完全匹配，包括大小写和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="d1797-116">These values must match the manufacturer values from SMBIOS exactly, including capitalization and special characters.</span></span> 

- <span data-ttu-id="d1797-117">设备制造商（示例： SpiralOrbit）</span><span class="sxs-lookup"><span data-stu-id="d1797-117">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="d1797-118">设备模型（示例： ContosoABC）</span><span class="sxs-lookup"><span data-stu-id="d1797-118">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="d1797-119">设备序列号</span><span class="sxs-lookup"><span data-stu-id="d1797-119">Device serial number</span></span>

## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="d1797-120">使用 Azure 门户注册设备</span><span class="sxs-lookup"><span data-stu-id="d1797-120">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="d1797-121">使用 Azure 门户注册与自助服务相同，不同之处在于，访问门户的方式不同。</span><span class="sxs-lookup"><span data-stu-id="d1797-121">Registering by using the Azure Portal is the same as for self-service, except you access the portal differently.</span></span> <span data-ttu-id="d1797-122">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d1797-122">Follow these steps:</span></span>

1. <span data-ttu-id="d1797-123">导航到 "[合作伙伴中心](https://partner.microsoft.com/dashboard)"</span><span class="sxs-lookup"><span data-stu-id="d1797-123">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="d1797-124">选择 "**客户**"。</span><span class="sxs-lookup"><span data-stu-id="d1797-124">Select **Customers**.</span></span>
3. <span data-ttu-id="d1797-125">选择要管理的客户。</span><span class="sxs-lookup"><span data-stu-id="d1797-125">Select the customer you want to manage.</span></span>
4. <span data-ttu-id="d1797-126">选择 "**服务管理**"。</span><span class="sxs-lookup"><span data-stu-id="d1797-126">Select **Service Administration**.</span></span>
5. <span data-ttu-id="d1797-127">选择 " **Intune**"。</span><span class="sxs-lookup"><span data-stu-id="d1797-127">Select **Intune**.</span></span>
6. <span data-ttu-id="d1797-128">在 Azure 门户的顶部搜索框中搜索 "mmd"。</span><span class="sxs-lookup"><span data-stu-id="d1797-128">Search for "mmd" in the top search box of the Azure portal.</span></span>
7. <span data-ttu-id="d1797-129">选择 "**设备**"。</span><span class="sxs-lookup"><span data-stu-id="d1797-129">Select **Devices**.</span></span>
8. <span data-ttu-id="d1797-130">在 "**文件上载**" 中，提供以前创建的 CSV 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="d1797-130">In **File upload**, provide a path to the CSV file you created previously.</span></span>
9. <span data-ttu-id="d1797-131">（可选）可以出于自己的跟踪目的添加**订单 id**或**购买 ID** 。</span><span class="sxs-lookup"><span data-stu-id="d1797-131">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="d1797-132">这些值没有格式要求。</span><span class="sxs-lookup"><span data-stu-id="d1797-132">There are no format requirements for these values.</span></span>
10. <span data-ttu-id="d1797-133">选择 "**注册设备**"。</span><span class="sxs-lookup"><span data-stu-id="d1797-133">Select **Register devices**.</span></span> <span data-ttu-id="d1797-134">系统会将设备添加到**设备边栏**上的设备列表中，并标记为 "**注册挂起**"。</span><span class="sxs-lookup"><span data-stu-id="d1797-134">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="d1797-135">注册通常需要不到10分钟的时间，如果成功，设备将显示为 "已**准备就绪**，以供用户使用"，表示它已准备就绪，正在等待最终用户开始使用。</span><span class="sxs-lookup"><span data-stu-id="d1797-135">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="d1797-136">你可以在主**Microsoft 托管台式机-设备**页面上监视设备注册的进度。</span><span class="sxs-lookup"><span data-stu-id="d1797-136">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="d1797-137">可能报告的状态包括：</span><span class="sxs-lookup"><span data-stu-id="d1797-137">Possible states reported there include:</span></span>

| <span data-ttu-id="d1797-138">状态</span><span class="sxs-lookup"><span data-stu-id="d1797-138">State</span></span> | <span data-ttu-id="d1797-139">说明</span><span class="sxs-lookup"><span data-stu-id="d1797-139">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="d1797-140">注册挂起</span><span class="sxs-lookup"><span data-stu-id="d1797-140">Registration pending</span></span> | <span data-ttu-id="d1797-141">注册尚未完成。</span><span class="sxs-lookup"><span data-stu-id="d1797-141">Registration is not done yet.</span></span> <span data-ttu-id="d1797-142">稍后再次查看。</span><span class="sxs-lookup"><span data-stu-id="d1797-142">Check back later.</span></span> |
| <span data-ttu-id="d1797-143">注册失败</span><span class="sxs-lookup"><span data-stu-id="d1797-143">Registration failed</span></span> | <span data-ttu-id="d1797-144">无法完成注册。</span><span class="sxs-lookup"><span data-stu-id="d1797-144">Registration could not be completed.</span></span> <span data-ttu-id="d1797-145">有关详细信息，请参阅[设备注册故障排除](register-devices-self.md#troubleshooting-device-registration)。</span><span class="sxs-lookup"><span data-stu-id="d1797-145">Refer to [Troubleshooting device registration](register-devices-self.md#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="d1797-146">为用户准备就绪</span><span class="sxs-lookup"><span data-stu-id="d1797-146">Ready for user</span></span> | <span data-ttu-id="d1797-147">注册成功，现在设备已准备好传递给最终用户。</span><span class="sxs-lookup"><span data-stu-id="d1797-147">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="d1797-148">Microsoft 托管桌面将在首次设置时引导他们，因此无需执行任何进一步的准备。</span><span class="sxs-lookup"><span data-stu-id="d1797-148">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="d1797-149">活动</span><span class="sxs-lookup"><span data-stu-id="d1797-149">Active</span></span> | <span data-ttu-id="d1797-150">设备已传递给最终用户，并且已向其注册了你的租户。</span><span class="sxs-lookup"><span data-stu-id="d1797-150">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="d1797-151">这也表明它们是定期使用设备的。</span><span class="sxs-lookup"><span data-stu-id="d1797-151">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="d1797-152">不再</span><span class="sxs-lookup"><span data-stu-id="d1797-152">Inactive</span></span> | <span data-ttu-id="d1797-153">设备已传递给最终用户，并且已向其注册了你的租户。</span><span class="sxs-lookup"><span data-stu-id="d1797-153">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="d1797-154">但是，他们最近未使用设备（最近7天）。</span><span class="sxs-lookup"><span data-stu-id="d1797-154">However, they have not used the device recently (in the last 7 days).</span></span>  |



## <a name="troubleshooting"></a><span data-ttu-id="d1797-155">故障排除</span><span class="sxs-lookup"><span data-stu-id="d1797-155">Troubleshooting</span></span>

| <span data-ttu-id="d1797-156">错误消息</span><span class="sxs-lookup"><span data-stu-id="d1797-156">Error message</span></span> | <span data-ttu-id="d1797-157">详细信息</span><span class="sxs-lookup"><span data-stu-id="d1797-157">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="d1797-158">找不到设备</span><span class="sxs-lookup"><span data-stu-id="d1797-158">Device not found</span></span> | <span data-ttu-id="d1797-159">无法注册此设备，因为我们找不到提供的制造商、型号或序列号的匹配项。</span><span class="sxs-lookup"><span data-stu-id="d1797-159">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="d1797-160">请与设备供应商确认这些值。</span><span class="sxs-lookup"><span data-stu-id="d1797-160">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="d1797-161">硬件哈希无效</span><span class="sxs-lookup"><span data-stu-id="d1797-161">Hardware hash not valid</span></span> | <span data-ttu-id="d1797-162">为此设备提供的硬件哈希格式不正确。</span><span class="sxs-lookup"><span data-stu-id="d1797-162">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="d1797-163">仔细检查硬件哈希，然后重新提交。</span><span class="sxs-lookup"><span data-stu-id="d1797-163">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="d1797-164">已注册设备</span><span class="sxs-lookup"><span data-stu-id="d1797-164">Device already registered</span></span> | <span data-ttu-id="d1797-165">此设备已注册到你的组织。</span><span class="sxs-lookup"><span data-stu-id="d1797-165">This device is already registered to your organization.</span></span> <span data-ttu-id="d1797-166">无需执行进一步操作。</span><span class="sxs-lookup"><span data-stu-id="d1797-166">No further action required.</span></span> |
| <span data-ttu-id="d1797-167">其他组织声明的设备</span><span class="sxs-lookup"><span data-stu-id="d1797-167">Device claimed by another organization</span></span> | <span data-ttu-id="d1797-168">此设备已由其他组织声明。</span><span class="sxs-lookup"><span data-stu-id="d1797-168">This device has already been claimed by another organization.</span></span> <span data-ttu-id="d1797-169">请与设备供应商联系。</span><span class="sxs-lookup"><span data-stu-id="d1797-169">Check with your device supplier.</span></span> |
| <span data-ttu-id="d1797-170">意外错误</span><span class="sxs-lookup"><span data-stu-id="d1797-170">Unexpected error</span></span> | <span data-ttu-id="d1797-171">无法自动处理你的请求。</span><span class="sxs-lookup"><span data-stu-id="d1797-171">Your request could not be automatically processed.</span></span> <span data-ttu-id="d1797-172">联系支持人员<support link>（）并提供请求 ID：<requestId></span><span class="sxs-lookup"><span data-stu-id="d1797-172">Contact Support (<support link>) and provide the Request ID: <requestId></span></span> |
