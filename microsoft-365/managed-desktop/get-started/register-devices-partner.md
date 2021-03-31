---
title: 合作伙伴注册设备的步骤
description: 合作伙伴如何注册设备，以便由 Microsoft 托管桌面管理设备
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
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
ms.openlocfilehash: baf15ca4b83052af84d2b22b3d2604c6022ac900
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445586"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="9524f-104">合作伙伴注册设备的步骤</span><span class="sxs-lookup"><span data-stu-id="9524f-104">Steps for Partners to register devices</span></span>


<span data-ttu-id="9524f-105">本主题介绍合作伙伴注册设备要遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="9524f-105">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="9524f-106">为自己注册设备的过程记录在"在 Microsoft 托管桌面中注册设备 ["中](register-devices-self.md)。</span><span class="sxs-lookup"><span data-stu-id="9524f-106">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="9524f-107">准备注册</span><span class="sxs-lookup"><span data-stu-id="9524f-107">Prepare for registration</span></span> 
<span data-ttu-id="9524f-108">完成客户注册之前，你必须先在合作伙伴中心与它们 [建立关系](https://partner.microsoft.com/dashboard)。</span><span class="sxs-lookup"><span data-stu-id="9524f-108">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="9524f-109">有关 [该过程的更多详细信息](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) ，请参阅许可文档。</span><span class="sxs-lookup"><span data-stu-id="9524f-109">See the [consent documentation](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="9524f-110">只要客户同意，任何云解决方案提供商合作伙伴都可以代表任何客户添加设备。</span><span class="sxs-lookup"><span data-stu-id="9524f-110">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="9524f-111">还可以在合作伙伴中心帮助 中了解有关合作伙伴关系和 Autopilot [权限的更多信息](/partner-center/customers_revoke_admin_privileges#windows-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="9524f-111">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="9524f-112">本文档仅适用于合作伙伴和 OEM。</span><span class="sxs-lookup"><span data-stu-id="9524f-112">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="9524f-113">自行注册的过程记录在自行注册 Microsoft [托管桌面中的设备中](register-devices-self.md)。</span><span class="sxs-lookup"><span data-stu-id="9524f-113">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="9524f-114">使用合作伙伴中心注册设备</span><span class="sxs-lookup"><span data-stu-id="9524f-114">Register devices by using Partner Center</span></span>

<span data-ttu-id="9524f-115">在与客户建立关系后，你可以按照以下步骤利用合作伙伴中心为有关系的任何客户将设备添加到 Autopilot：</span><span class="sxs-lookup"><span data-stu-id="9524f-115">Once you have established the relationship with your customers, you can leverage Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="9524f-116">导航到 [合作伙伴中心](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="9524f-116">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="9524f-117">从 **合作伙伴** 中心菜单中选择客户，然后选择你想要管理其设备的客户。</span><span class="sxs-lookup"><span data-stu-id="9524f-117">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="9524f-118">在客户的详细信息页面上，选择 **设备**。</span><span class="sxs-lookup"><span data-stu-id="9524f-118">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="9524f-119">在 **"将配置文件** 应用到设备"下，选择 **"添加设备"。**</span><span class="sxs-lookup"><span data-stu-id="9524f-119">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="9524f-120">Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span><span class="sxs-lookup"><span data-stu-id="9524f-120">Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="9524f-121">组名称 **必须完全** Microsoft365Managed_Autopilot，包括大写字符和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="9524f-121">The Group Name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="9524f-122">这将允许使用 Microsoft 托管桌面 Autopilot 配置文件分配新注册的设备。</span><span class="sxs-lookup"><span data-stu-id="9524f-122">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="9524f-123">你应该已使用设备购买收到此 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="9524f-123">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="9524f-124">如果未收到 .csv 文件，可以按照将设备添加到 Windows Autopilot 中的步骤操作 [，自己创建一个文件](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9524f-124">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="9524f-125">the Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash).</span><span class="sxs-lookup"><span data-stu-id="9524f-125">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash).</span></span> <span data-ttu-id="9524f-126">合作伙伴应在合作伙伴 [中心使用 Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 为 Microsoft 托管桌面设备注册设备。</span><span class="sxs-lookup"><span data-stu-id="9524f-126">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="9524f-127">如果在尝试上载 .csv 文件时收到错误消息，请检查该文件的格式。</span><span class="sxs-lookup"><span data-stu-id="9524f-127">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="9524f-128">确保列顺序与使用新设备的 [Windows Autopilot](/partner-center/autopilot#add-devices-to-a-customers-account)配置文件自定义客户的全新体验中所述相匹配。</span><span class="sxs-lookup"><span data-stu-id="9524f-128">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="9524f-129">您还可以使用添加设备旁边的链接中提供的示例 .csv **文件** 来创建设备列表。</span><span class="sxs-lookup"><span data-stu-id="9524f-129">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="9524f-130">有关合作伙伴方案中的 Autopilot 详细信息，请参阅 [将设备添加到客户的帐户](/partner-center/autopilot#add-devices-to-a-customers-account)。</span><span class="sxs-lookup"><span data-stu-id="9524f-130">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="9524f-131">使用 OEM API 注册设备</span><span class="sxs-lookup"><span data-stu-id="9524f-131">Register devices by using the OEM API</span></span>

<span data-ttu-id="9524f-132">完成客户注册之前，必须先与客户建立关系。</span><span class="sxs-lookup"><span data-stu-id="9524f-132">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="9524f-133">你应该有一个唯一的链接来向各自的客户提供。</span><span class="sxs-lookup"><span data-stu-id="9524f-133">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="9524f-134">请参阅 [如何建立 OEM 关系](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。</span><span class="sxs-lookup"><span data-stu-id="9524f-134">See [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="9524f-135">建立关系后，可以使用组标记属性开始为客户注册 **Microsoft365Managed_Autopilot。**</span><span class="sxs-lookup"><span data-stu-id="9524f-135">Once you've established the relationship, you can start registering devices for customers using the Group Tag **Microsoft365Managed_Autopilot**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9524f-136">组名称 **必须完全** Microsoft365Managed_Autopilot，包括大写字符和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="9524f-136">The group name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="9524f-137">这将允许使用 Microsoft 托管桌面 Autopilot 配置文件分配新注册的设备。</span><span class="sxs-lookup"><span data-stu-id="9524f-137">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>