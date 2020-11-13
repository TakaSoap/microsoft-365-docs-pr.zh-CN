---
title: 合作伙伴注册设备的步骤
description: 合作伙伴如何注册设备以便 Microsoft 托管桌面可以管理它们
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 7e40a5eb7144fef3d330e0e8fc3c711af15d4c49
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071439"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="35a47-103">合作伙伴注册设备的步骤</span><span class="sxs-lookup"><span data-stu-id="35a47-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="35a47-104">本主题介绍了合作伙伴在注册设备时应遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="35a47-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="35a47-105">您自己注册设备的过程记录在 [Microsoft 托管桌面的注册设备](register-devices-self.md)中。</span><span class="sxs-lookup"><span data-stu-id="35a47-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="35a47-106">准备注册</span><span class="sxs-lookup"><span data-stu-id="35a47-106">Prepare for registration</span></span> 
<span data-ttu-id="35a47-107">在完成客户注册之前，必须首先在 [合作伙伴中心](https://partner.microsoft.com/dashboard)建立与它们的关系。</span><span class="sxs-lookup"><span data-stu-id="35a47-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="35a47-108">有关该过程的更多详细信息，请参阅 [许可文档](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) 。</span><span class="sxs-lookup"><span data-stu-id="35a47-108">See the [consent documentation](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="35a47-109">任何 CSP 合作伙伴都可以代表任何客户添加设备，只要客户同意。</span><span class="sxs-lookup"><span data-stu-id="35a47-109">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="35a47-110">您还可以在 [合作伙伴中心帮助](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot)中了解有关合作伙伴关系和 Autopilot 权限的详细信息。</span><span class="sxs-lookup"><span data-stu-id="35a47-110">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="35a47-111">本文档仅适用于合作伙伴和 Oem。</span><span class="sxs-lookup"><span data-stu-id="35a47-111">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="35a47-112">自行注册的过程在 [Microsoft 托管桌面的注册设备](register-devices-self.md)中进行了记录。</span><span class="sxs-lookup"><span data-stu-id="35a47-112">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="35a47-113">使用合作伙伴中心注册设备</span><span class="sxs-lookup"><span data-stu-id="35a47-113">Register devices by using Partner Center</span></span>

<span data-ttu-id="35a47-114">建立与客户的关系后，您可以通过执行以下步骤，利用合作伙伴中心将设备添加到与您有关系的任何客户的 Autopilot 中。</span><span class="sxs-lookup"><span data-stu-id="35a47-114">Once you have established the relationship with your customers, you can leverage Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="35a47-115">导航到 "[合作伙伴中心](https://partner.microsoft.com/dashboard)"</span><span class="sxs-lookup"><span data-stu-id="35a47-115">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="35a47-116">从 "合作伙伴中心" 菜单中选择 " **客户** "，然后选择要管理其设备的客户。</span><span class="sxs-lookup"><span data-stu-id="35a47-116">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="35a47-117">在客户的详细信息页上，选择 " **设备** "。</span><span class="sxs-lookup"><span data-stu-id="35a47-117">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="35a47-118">在 " **将配置文件应用** 到设备" 下，选择 " **添加设备** "。</span><span class="sxs-lookup"><span data-stu-id="35a47-118">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="35a47-119">输入组名称 **Microsoft365Managed_Autopilot** ，然后选择 " **浏览** " 将客户列表 (以 .csv 文件格式上传) 到合作伙伴中心。</span><span class="sxs-lookup"><span data-stu-id="35a47-119">Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="35a47-120">组名称必须完全匹配 **Microsoft365Managed_Autopilot** ，包括大小写和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="35a47-120">The Group Name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="35a47-121">这将允许将新注册的设备分配给 Microsoft 托管桌面 Autopilot 配置文件。</span><span class="sxs-lookup"><span data-stu-id="35a47-121">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="35a47-122">你应该已收到此 .csv 文件并购买了你的设备。</span><span class="sxs-lookup"><span data-stu-id="35a47-122">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="35a47-123">如果您没有收到 .csv 文件，则可以按照 [向 Windows Autopilot 中添加设备](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)中的步骤创建一个。</span><span class="sxs-lookup"><span data-stu-id="35a47-123">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="35a47-124">Windows PowerShell 脚本与用于 [Microsoft 托管桌面管理门户](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash)的脚本不同。</span><span class="sxs-lookup"><span data-stu-id="35a47-124">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash).</span></span> <span data-ttu-id="35a47-125">合作伙伴应使用 [g-et-windowsautopilotinfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 在合作伙伴中心为 Microsoft 托管桌面设备注册设备。</span><span class="sxs-lookup"><span data-stu-id="35a47-125">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="35a47-126">如果在尝试上载 .csv 文件时收到错误消息，请检查该文件的格式。</span><span class="sxs-lookup"><span data-stu-id="35a47-126">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="35a47-127">请确保列顺序与在 [新设备上使用 Windows Autopilot 配置文件中描述的内容相匹配，以自定义客户的全新体验](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)。</span><span class="sxs-lookup"><span data-stu-id="35a47-127">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="35a47-128">您还可以使用 " **添加设备** " 下的链接中提供的示例 .csv 文件来创建设备列表。</span><span class="sxs-lookup"><span data-stu-id="35a47-128">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="35a47-129">有关合作伙伴应用场景中的 Autopilot 的详细信息，请参阅 [将设备添加到客户的帐户](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)。</span><span class="sxs-lookup"><span data-stu-id="35a47-129">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="35a47-130">使用 OEM API 注册设备</span><span class="sxs-lookup"><span data-stu-id="35a47-130">Register devices by using the OEM API</span></span>

<span data-ttu-id="35a47-131">在完成客户注册之前，必须首先建立与他们的关系。</span><span class="sxs-lookup"><span data-stu-id="35a47-131">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="35a47-132">你应具有可向你的各个客户提供的唯一链接。</span><span class="sxs-lookup"><span data-stu-id="35a47-132">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="35a47-133">请参阅 [如何建立 OEM 关系](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。</span><span class="sxs-lookup"><span data-stu-id="35a47-133">See [How to establish OEM relationship](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="35a47-134">建立关系后，即可开始使用 Group 标记 **Microsoft365Managed_Autopilot** 为客户注册设备。</span><span class="sxs-lookup"><span data-stu-id="35a47-134">Once you've established the relationship, you can start registering devices for customers using the Group Tag **Microsoft365Managed_Autopilot**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35a47-135">组名称必须完全匹配 **Microsoft365Managed_Autopilot** ，包括大小写和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="35a47-135">The group name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="35a47-136">这将允许将新注册的设备分配给 Microsoft 托管桌面 Autopilot 配置文件。</span><span class="sxs-lookup"><span data-stu-id="35a47-136">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>
