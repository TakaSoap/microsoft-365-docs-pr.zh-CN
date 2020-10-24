---
title: Contoso 移动设备管理
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft 365 for enterprise 中的 Microsoft Intune 来管理其设备以及在其上运行的应用程序。
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753987"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="2bc9c-103">Contoso 移动设备管理</span><span class="sxs-lookup"><span data-stu-id="2bc9c-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="2bc9c-104">适用于企业的 Microsoft 365 包括 Intune 和一组支持移动设备和应用程序管理和安全性的 Azure 服务。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="2bc9c-p101">Contoso 拥有许多启用了移动的员工。有些办公室在 Contoso 位置，有些则没有办事处。Contoso 需要一种方法来实现员工工作效率，但保留设备、存储在这些设备上的 Contoso 数据以及应用程序行为的安全性。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-p101">Contoso has many mobile-enabled employees. Some have offices in Contoso locations, and some have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="2bc9c-108">套餐</span><span class="sxs-lookup"><span data-stu-id="2bc9c-108">Plan</span></span>

<span data-ttu-id="2bc9c-109">Contoso 确定了适用于企业的 Microsoft 365 移动设备管理的以下 Intune 使用案例：</span><span class="sxs-lookup"><span data-stu-id="2bc9c-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="2bc9c-110">保护 Exchange Online 电子邮件和数据，以便移动设备可以安全地访问这些电子邮件和数据。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="2bc9c-111">为 Contoso 员工实施现成的设备 (BYOD) 计划。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="2bc9c-112">颁发组织拥有的电话，并将共享平板电脑限制为 Contoso 员工。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="2bc9c-113">Contoso 不使用 Intune 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2bc9c-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="2bc9c-114">允许员工从非托管的公共展台安全访问 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="2bc9c-115">保护本地电子邮件和数据，以便移动设备可以安全地访问它，因为没有本地 Microsoft Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="2bc9c-116">部署</span><span class="sxs-lookup"><span data-stu-id="2bc9c-116">Deploy</span></span>

<span data-ttu-id="2bc9c-117">以下是 Contoso 设置其移动设备管理基础结构的方式：</span><span class="sxs-lookup"><span data-stu-id="2bc9c-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="2bc9c-118">将 Intune 设置为移动设备管理 (MDM) 颁发机构，并在 Azure 上使用 Intune 管理内容并管理设备</span><span class="sxs-lookup"><span data-stu-id="2bc9c-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="2bc9c-119">为用于注册和 Intune 设置的设备的 azure AD) 组和基于设备的条件访问策略创建了 Azure Active Directory (的 Azure AD</span><span class="sxs-lookup"><span data-stu-id="2bc9c-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="2bc9c-120">有关详细信息，请参阅 [Contoso 条件访问策略](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="2bc9c-121">启用 Apple 设备平台以支持员工使用 Ipad、Imac 和 Iphone 以及公司拥有的 Iphone</span><span class="sxs-lookup"><span data-stu-id="2bc9c-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="2bc9c-122">创建了特定于 Contoso 的条款和条件策略，在移动设备上安装 Contoso 的公司门户时会看到这些策略</span><span class="sxs-lookup"><span data-stu-id="2bc9c-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="2bc9c-123">对于未注册的设备，实现一组移动应用程序管理 (MAM) 策略，以要求对 Microsoft 365 服务的访问进行身份验证</span><span class="sxs-lookup"><span data-stu-id="2bc9c-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="2bc9c-124">创建了强制实施以下内容的 Intune 策略：</span><span class="sxs-lookup"><span data-stu-id="2bc9c-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="2bc9c-125">允许的应用。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-125">Allowed apps.</span></span>
  - <span data-ttu-id="2bc9c-126">设备加密以帮助防止未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="2bc9c-127">6位数的 PIN 或密码。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="2bc9c-128">非活动超时时间。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="2bc9c-129">Windows 10 设备上的 Windows Defender 的防病毒和恶意软件防护以及签名更新。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="2bc9c-130">Windows 10 设备上的自动更新，其中包括最新的安全更新。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="2bc9c-131">将证书推送到托管设备。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="2bc9c-p102">商业与个人数据的明确区分。用户或管理员可以选择性地擦除设备中的公司数据，而将图片、个人电子邮件帐户和个人文件等个人数据保持不变。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="2bc9c-134">Contoso 通过将 Pc 和公司拥有的智能手机和平板电脑添加到相应的 Intune 设备组来注册它们。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="2bc9c-135">他们还为员工建立了用于注册其个人设备的 BYOD 计划。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="2bc9c-136">已注册的设备接收 Intune 策略，这将导致受管理和安全的设备及其应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="2bc9c-137">未注册的设备具有指定允许的应用程序 (MAM) 策略中的移动应用程序管理。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="2bc9c-138">下面是 Contoso 移动设备管理部署体系结构。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Contoso 移动设备管理部署基础结构](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="2bc9c-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2bc9c-140">Next step</span></span>

<span data-ttu-id="2bc9c-141">了解 Contoso 如何使用 Microsoft 365 for enterprise 的 [信息保护功能](contoso-info-protect.md) 来分类、识别和保护整个组织中的重要数字资产。</span><span class="sxs-lookup"><span data-stu-id="2bc9c-141">Learn how Contoso uses the [information protection capabilities](contoso-info-protect.md) of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="2bc9c-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bc9c-142">See also</span></span>

[<span data-ttu-id="2bc9c-143">适用于 Microsoft 365 的设备管理</span><span class="sxs-lookup"><span data-stu-id="2bc9c-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="2bc9c-144">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="2bc9c-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2bc9c-145">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="2bc9c-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

