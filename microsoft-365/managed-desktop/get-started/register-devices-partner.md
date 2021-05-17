---
title: 合作伙伴注册设备的步骤
description: 合作伙伴如何注册设备，以便由 Microsoft 托管桌面管理设备
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
ms.openlocfilehash: 227786fdcf1e490be1e3ce74bbc1be1c5f21acfe
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689229"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="66b2f-103">合作伙伴注册设备的步骤</span><span class="sxs-lookup"><span data-stu-id="66b2f-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="66b2f-104">本文介绍了合作伙伴注册设备要遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="66b2f-104">This article describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="66b2f-105">为自己注册设备的过程记录在"在 Microsoft 托管桌面中注册设备 ["中](register-devices-self.md)。</span><span class="sxs-lookup"><span data-stu-id="66b2f-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="66b2f-106">准备注册</span><span class="sxs-lookup"><span data-stu-id="66b2f-106">Prepare for registration</span></span> 
<span data-ttu-id="66b2f-107">完成客户注册之前，你必须先在合作伙伴中心与它们 [建立关系](https://partner.microsoft.com/dashboard)。</span><span class="sxs-lookup"><span data-stu-id="66b2f-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="66b2f-108">有关 [该过程的更多详细信息](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) ，请参阅许可文档。</span><span class="sxs-lookup"><span data-stu-id="66b2f-108">See the [consent documentation](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="66b2f-109">只要客户同意，任何云解决方案提供商合作伙伴都可以代表任何客户添加设备。</span><span class="sxs-lookup"><span data-stu-id="66b2f-109">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="66b2f-110">还可以在合作伙伴中心帮助 中了解有关合作伙伴关系和 Autopilot [权限的更多信息](/partner-center/customers_revoke_admin_privileges#windows-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="66b2f-110">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="66b2f-111">本文档仅适用于合作伙伴和 OEM。</span><span class="sxs-lookup"><span data-stu-id="66b2f-111">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="66b2f-112">自行注册的过程记录在自行注册 Microsoft [托管桌面中的设备中](register-devices-self.md)。</span><span class="sxs-lookup"><span data-stu-id="66b2f-112">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="66b2f-113">使用合作伙伴中心注册设备</span><span class="sxs-lookup"><span data-stu-id="66b2f-113">Register devices by using Partner Center</span></span>

<span data-ttu-id="66b2f-114">在与客户建立关系后，可以通过执行以下步骤，使用合作伙伴中心为有关系的任何客户将设备添加到 Autopilot：</span><span class="sxs-lookup"><span data-stu-id="66b2f-114">Once you have established the relationship with your customers, you can use Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="66b2f-115">导航到 [合作伙伴中心](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="66b2f-115">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="66b2f-116">从 **合作伙伴** 中心菜单中选择客户，然后选择你想要管理其设备的客户。</span><span class="sxs-lookup"><span data-stu-id="66b2f-116">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="66b2f-117">在客户的详细信息页面上，选择 **设备**。</span><span class="sxs-lookup"><span data-stu-id="66b2f-117">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="66b2f-118">在 **"将配置文件** 应用到设备"下，选择 **"添加设备"。**</span><span class="sxs-lookup"><span data-stu-id="66b2f-118">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="66b2f-119">为所选的设备配置文件输入相应的组标记 (如下表) 所示，然后选择"浏览"将 .csv) 文件格式的客户列表 (上载到合作伙伴中心。</span><span class="sxs-lookup"><span data-stu-id="66b2f-119">Enter the appropriate Group Tag for the device profile you've selected (as shown in the following table) and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>

|[<span data-ttu-id="66b2f-120">设备配置文件</span><span class="sxs-lookup"><span data-stu-id="66b2f-120">Device profile</span></span>](../service-description/profiles.md)  |<span data-ttu-id="66b2f-121">组标记</span><span class="sxs-lookup"><span data-stu-id="66b2f-121">Group Tag</span></span>  |
|---------|---------|
|<span data-ttu-id="66b2f-122">敏感数据</span><span class="sxs-lookup"><span data-stu-id="66b2f-122">Sensitive data</span></span>     |<span data-ttu-id="66b2f-123">**Microsoft365Managed \_ SensitiveData**</span><span class="sxs-lookup"><span data-stu-id="66b2f-123">**Microsoft365Managed\_SensitiveData**</span></span>    |
|<span data-ttu-id="66b2f-124">Power user</span><span class="sxs-lookup"><span data-stu-id="66b2f-124">Power user</span></span>     | <span data-ttu-id="66b2f-125">**Microsoft365Managed \_ PowerUser**</span><span class="sxs-lookup"><span data-stu-id="66b2f-125">**Microsoft365Managed\_PowerUser**</span></span>          |
|<span data-ttu-id="66b2f-126">标准</span><span class="sxs-lookup"><span data-stu-id="66b2f-126">Standard</span></span>     | <span data-ttu-id="66b2f-127">**Microsoft365Managed \_ Standard**</span><span class="sxs-lookup"><span data-stu-id="66b2f-127">**Microsoft365Managed\_Standard**</span></span>        |

> [!IMPORTANT]
> <span data-ttu-id="66b2f-128">组名称必须与表中列出的名称完全匹配，包括大写和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="66b2f-128">The Group Name must match those listed in the table exactly, including capitalization and special characters.</span></span> <span data-ttu-id="66b2f-129">这将允许使用 Microsoft 托管桌面 Autopilot 配置文件分配新注册的设备。</span><span class="sxs-lookup"><span data-stu-id="66b2f-129">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="66b2f-130">你应该已经收到此.csv购买的文件。</span><span class="sxs-lookup"><span data-stu-id="66b2f-130">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="66b2f-131">如果你未收到.csv文件，可以按照将设备添加到 Windows Autopilot 中的步骤操作 [，自己创建一个](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)。</span><span class="sxs-lookup"><span data-stu-id="66b2f-131">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="66b2f-132">the Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md#obtain-the-hardware-hash).</span><span class="sxs-lookup"><span data-stu-id="66b2f-132">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md#obtain-the-hardware-hash).</span></span> <span data-ttu-id="66b2f-133">合作伙伴应在合作伙伴 [中心使用 Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 为 Microsoft 托管桌面设备注册设备。</span><span class="sxs-lookup"><span data-stu-id="66b2f-133">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="66b2f-134">如果在尝试上载文件时收到.csv错误消息，请检查该文件的格式。</span><span class="sxs-lookup"><span data-stu-id="66b2f-134">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="66b2f-135">确保列顺序与使用新设备的 [Windows Autopilot](/partner-center/autopilot#add-devices-to-a-customers-account)配置文件自定义客户的全新体验中所述相匹配。</span><span class="sxs-lookup"><span data-stu-id="66b2f-135">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="66b2f-136">您还可以使用添加设备.csv旁边链接提供的示例文件创建设备列表。 </span><span class="sxs-lookup"><span data-stu-id="66b2f-136">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="66b2f-137">有关合作伙伴方案中的 Autopilot 详细信息，请参阅 [将设备添加到客户的帐户](/partner-center/autopilot#add-devices-to-a-customers-account)。</span><span class="sxs-lookup"><span data-stu-id="66b2f-137">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="66b2f-138">使用 OEM API 注册设备</span><span class="sxs-lookup"><span data-stu-id="66b2f-138">Register devices by using the OEM API</span></span>

<span data-ttu-id="66b2f-139">完成客户注册之前，必须先与客户建立关系。</span><span class="sxs-lookup"><span data-stu-id="66b2f-139">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="66b2f-140">你应该有一个唯一的链接来向各自的客户提供。</span><span class="sxs-lookup"><span data-stu-id="66b2f-140">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="66b2f-141">请参阅 [如何建立 OEM 关系](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。</span><span class="sxs-lookup"><span data-stu-id="66b2f-141">See [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="66b2f-142">建立关系后，你可以开始为已选择的每个设备配置文件使用相应的组标记为客户注册设备：</span><span class="sxs-lookup"><span data-stu-id="66b2f-142">Once you've established the relationship, you can start registering devices for customers using the appropriate Group Tag for each device profile they've selected:</span></span>


|<span data-ttu-id="66b2f-143">设备配置文件</span><span class="sxs-lookup"><span data-stu-id="66b2f-143">Device profile</span></span>  |<span data-ttu-id="66b2f-144">组标记</span><span class="sxs-lookup"><span data-stu-id="66b2f-144">Group Tag</span></span>  |
|---------|---------|
|<span data-ttu-id="66b2f-145">敏感数据</span><span class="sxs-lookup"><span data-stu-id="66b2f-145">Sensitive data</span></span>     | <span data-ttu-id="66b2f-146">**Microsoft365Managed \_ SensitiveData**</span><span class="sxs-lookup"><span data-stu-id="66b2f-146">**Microsoft365Managed\_SensitiveData**</span></span>     |
|<span data-ttu-id="66b2f-147">Power user</span><span class="sxs-lookup"><span data-stu-id="66b2f-147">Power user</span></span>     | <span data-ttu-id="66b2f-148">**Microsoft365Managed \_ PowerUser**</span><span class="sxs-lookup"><span data-stu-id="66b2f-148">**Microsoft365Managed\_PowerUser**</span></span>          |
|<span data-ttu-id="66b2f-149">标准</span><span class="sxs-lookup"><span data-stu-id="66b2f-149">Standard</span></span>     | <span data-ttu-id="66b2f-150">**Microsoft365Managed \_ Standard**</span><span class="sxs-lookup"><span data-stu-id="66b2f-150">**Microsoft365Managed\_Standard**</span></span>      |

> [!IMPORTANT]
> <span data-ttu-id="66b2f-151">组标记必须与表中列出的标记完全匹配，包括大写字符和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="66b2f-151">The Group Tags must match those listed in the table exactly, including capitalization and special characters.</span></span> <span data-ttu-id="66b2f-152">这将允许使用 Microsoft 托管桌面 Autopilot 配置文件分配新注册的设备。</span><span class="sxs-lookup"><span data-stu-id="66b2f-152">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>