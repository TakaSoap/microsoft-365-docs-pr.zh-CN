---
title: 合作伙伴注册设备的步骤
description: 合作伙伴如何注册设备，以便由 Microsoft 托管桌面管理设备
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: be314b20573cecfdb020caf778e51a684a9b6df8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909066"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="a827d-103">合作伙伴注册设备的步骤</span><span class="sxs-lookup"><span data-stu-id="a827d-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="a827d-104">本主题介绍合作伙伴注册设备要遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="a827d-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="a827d-105">为自己注册设备的过程记录在"在 Microsoft 托管桌面中注册设备 ["中](register-devices-self.md)。</span><span class="sxs-lookup"><span data-stu-id="a827d-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="a827d-106">准备注册</span><span class="sxs-lookup"><span data-stu-id="a827d-106">Prepare for registration</span></span> 
<span data-ttu-id="a827d-107">完成客户注册之前，你必须先在合作伙伴中心与它们 [建立关系](https://partner.microsoft.com/dashboard)。</span><span class="sxs-lookup"><span data-stu-id="a827d-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="a827d-108">有关 [该过程的更多详细信息](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) ，请参阅许可文档。</span><span class="sxs-lookup"><span data-stu-id="a827d-108">See the [consent documentation](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="a827d-109">只要客户同意，任何云解决方案提供商合作伙伴都可以代表任何客户添加设备。</span><span class="sxs-lookup"><span data-stu-id="a827d-109">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="a827d-110">还可以在合作伙伴中心帮助 中了解有关合作伙伴关系和 Autopilot [权限的更多信息](/partner-center/customers_revoke_admin_privileges#windows-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="a827d-110">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="a827d-111">本文档仅适用于合作伙伴和 OEM。</span><span class="sxs-lookup"><span data-stu-id="a827d-111">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="a827d-112">自行注册的过程记录在自行注册 Microsoft [托管桌面中的设备中](register-devices-self.md)。</span><span class="sxs-lookup"><span data-stu-id="a827d-112">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="a827d-113">使用合作伙伴中心注册设备</span><span class="sxs-lookup"><span data-stu-id="a827d-113">Register devices by using Partner Center</span></span>

<span data-ttu-id="a827d-114">在与客户建立关系后，你可以按照以下步骤利用合作伙伴中心为有关系的任何客户将设备添加到 Autopilot：</span><span class="sxs-lookup"><span data-stu-id="a827d-114">Once you have established the relationship with your customers, you can leverage Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="a827d-115">导航到 [合作伙伴中心](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="a827d-115">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="a827d-116">从 **合作伙伴** 中心菜单中选择客户，然后选择你想要管理其设备的客户。</span><span class="sxs-lookup"><span data-stu-id="a827d-116">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="a827d-117">在客户的详细信息页面上，选择 **设备**。</span><span class="sxs-lookup"><span data-stu-id="a827d-117">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="a827d-118">在 **"将配置文件** 应用到设备"下，选择 **"添加设备"。**</span><span class="sxs-lookup"><span data-stu-id="a827d-118">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="a827d-119">Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span><span class="sxs-lookup"><span data-stu-id="a827d-119">Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a827d-120">组名称 **必须完全** Microsoft365Managed_Autopilot，包括大写字符和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="a827d-120">The Group Name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="a827d-121">这将允许使用 Microsoft 托管桌面 Autopilot 配置文件分配新注册的设备。</span><span class="sxs-lookup"><span data-stu-id="a827d-121">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="a827d-122">你应该已使用设备购买收到此 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="a827d-122">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="a827d-123">如果未收到 .csv 文件，可以按照将设备添加到 Windows Autopilot 中的步骤操作 [，自己创建一个文件](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a827d-123">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="a827d-124">the Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash).</span><span class="sxs-lookup"><span data-stu-id="a827d-124">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash).</span></span> <span data-ttu-id="a827d-125">合作伙伴应在合作伙伴 [中心使用 Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 为 Microsoft 托管桌面设备注册设备。</span><span class="sxs-lookup"><span data-stu-id="a827d-125">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="a827d-126">如果在尝试上载 .csv 文件时收到错误消息，请检查该文件的格式。</span><span class="sxs-lookup"><span data-stu-id="a827d-126">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="a827d-127">确保列顺序与使用新设备的 [Windows Autopilot](/partner-center/autopilot#add-devices-to-a-customers-account)配置文件自定义客户的全新体验中所述相匹配。</span><span class="sxs-lookup"><span data-stu-id="a827d-127">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="a827d-128">您还可以使用添加设备旁边的链接中提供的示例 .csv **文件** 来创建设备列表。</span><span class="sxs-lookup"><span data-stu-id="a827d-128">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="a827d-129">有关合作伙伴方案中的 Autopilot 详细信息，请参阅 [将设备添加到客户的帐户](/partner-center/autopilot#add-devices-to-a-customers-account)。</span><span class="sxs-lookup"><span data-stu-id="a827d-129">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="a827d-130">使用 OEM API 注册设备</span><span class="sxs-lookup"><span data-stu-id="a827d-130">Register devices by using the OEM API</span></span>

<span data-ttu-id="a827d-131">完成客户注册之前，必须先与客户建立关系。</span><span class="sxs-lookup"><span data-stu-id="a827d-131">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="a827d-132">你应该有一个唯一的链接来向各自的客户提供。</span><span class="sxs-lookup"><span data-stu-id="a827d-132">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="a827d-133">请参阅 [如何建立 OEM 关系](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。</span><span class="sxs-lookup"><span data-stu-id="a827d-133">See [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="a827d-134">建立关系后，可以使用组标记属性开始为客户注册 **Microsoft365Managed_Autopilot。**</span><span class="sxs-lookup"><span data-stu-id="a827d-134">Once you've established the relationship, you can start registering devices for customers using the Group Tag **Microsoft365Managed_Autopilot**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a827d-135">组名称 **必须完全** Microsoft365Managed_Autopilot，包括大写字符和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="a827d-135">The group name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="a827d-136">这将允许使用 Microsoft 托管桌面 Autopilot 配置文件分配新注册的设备。</span><span class="sxs-lookup"><span data-stu-id="a827d-136">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>