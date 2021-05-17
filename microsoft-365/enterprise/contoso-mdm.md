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
description: 了解 Contoso 如何使用 Microsoft Intune Microsoft 365 企业版来管理其设备以及在其上运行的应用。
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753987"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="194f2-103">Contoso 移动设备管理</span><span class="sxs-lookup"><span data-stu-id="194f2-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="194f2-104">Microsoft 365企业版包括 Intune 和一组支持移动设备和应用程序管理和安全性的 Azure 服务。</span><span class="sxs-lookup"><span data-stu-id="194f2-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="194f2-105">Contoso 有许多支持移动的员工。</span><span class="sxs-lookup"><span data-stu-id="194f2-105">Contoso has many mobile-enabled employees.</span></span> <span data-ttu-id="194f2-106">一些办事处位于 Contoso 位置，有些则没有办公室。</span><span class="sxs-lookup"><span data-stu-id="194f2-106">Some have offices in Contoso locations, and some have no offices.</span></span> <span data-ttu-id="194f2-107">Contoso 需要一种提高员工工作效率的方法，但需确保设备、存储在这些设备上的 Contoso 数据以及应用程序行为安全。</span><span class="sxs-lookup"><span data-stu-id="194f2-107">Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="194f2-108">计划</span><span class="sxs-lookup"><span data-stu-id="194f2-108">Plan</span></span>

<span data-ttu-id="194f2-109">Contoso 标识了以下适用于企业的移动设备管理的 Intune Microsoft 365用例：</span><span class="sxs-lookup"><span data-stu-id="194f2-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="194f2-110">保护Exchange Online和数据，以便移动设备可以安全地访问它。</span><span class="sxs-lookup"><span data-stu-id="194f2-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="194f2-111">为 Contoso 员工实施自带设备办公 (BYOD) 计划。</span><span class="sxs-lookup"><span data-stu-id="194f2-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="194f2-112">向 Contoso 员工发布组织拥有的电话和有限使用的共享平板电脑。</span><span class="sxs-lookup"><span data-stu-id="194f2-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="194f2-113">Contoso 不使用 Intune 来：</span><span class="sxs-lookup"><span data-stu-id="194f2-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="194f2-114">允许员工从非托管Microsoft 365安全访问服务。</span><span class="sxs-lookup"><span data-stu-id="194f2-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="194f2-115">保护本地电子邮件和数据，以便移动设备可以安全地访问它们，因为没有本地 Microsoft Exchange服务器。</span><span class="sxs-lookup"><span data-stu-id="194f2-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="194f2-116">部署</span><span class="sxs-lookup"><span data-stu-id="194f2-116">Deploy</span></span>

<span data-ttu-id="194f2-117">以下是 Contoso 设置其移动设备管理基础结构的方式：</span><span class="sxs-lookup"><span data-stu-id="194f2-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="194f2-118">将 Intune 设置为移动设备管理 (MDM) 颁发机构，并使用 Azure 上的 Intune 管理内容和管理设备</span><span class="sxs-lookup"><span data-stu-id="194f2-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="194f2-119">为设备Azure Active Directory (Azure AD) 组创建，用于 Intune 设置和基于设备的条件访问策略</span><span class="sxs-lookup"><span data-stu-id="194f2-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="194f2-120">有关详细信息，请参阅 [Contoso 条件访问策略](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。</span><span class="sxs-lookup"><span data-stu-id="194f2-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="194f2-121">启用 Apple 设备平台以支持员工使用 iPad、iMac 和 iPhone 以及公司拥有的 iPhone</span><span class="sxs-lookup"><span data-stu-id="194f2-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="194f2-122">创建了特定于 Contoso 的条款和条件策略，在移动设备上安装 Contoso 的公司门户时会看到这些策略</span><span class="sxs-lookup"><span data-stu-id="194f2-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="194f2-123">对于未注册的设备，实施了一组移动应用程序管理 (MAM) 策略，要求身份验证以访问 Microsoft 365 服务</span><span class="sxs-lookup"><span data-stu-id="194f2-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="194f2-124">创建了强制实施以下内容的 Intune 策略：</span><span class="sxs-lookup"><span data-stu-id="194f2-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="194f2-125">允许的应用。</span><span class="sxs-lookup"><span data-stu-id="194f2-125">Allowed apps.</span></span>
  - <span data-ttu-id="194f2-126">设备加密，有助于防止未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="194f2-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="194f2-127">六位数的 PIN 或密码。</span><span class="sxs-lookup"><span data-stu-id="194f2-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="194f2-128">不活动超时时段。</span><span class="sxs-lookup"><span data-stu-id="194f2-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="194f2-129">防病毒和恶意软件保护以及签名更新Windows Defender设备上Windows 10更新。</span><span class="sxs-lookup"><span data-stu-id="194f2-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="194f2-130">在包含Windows 10安全更新的设备上自动更新。</span><span class="sxs-lookup"><span data-stu-id="194f2-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="194f2-131">将证书推送到托管设备。</span><span class="sxs-lookup"><span data-stu-id="194f2-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="194f2-p102">商业与个人数据的明确区分。用户或管理员可以选择性地擦除设备中的公司数据，而将图片、个人电子邮件帐户和个人文件等个人数据保持不变。</span><span class="sxs-lookup"><span data-stu-id="194f2-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="194f2-134">Contoso 通过将已部署的电脑和公司拥有的智能手机和平板电脑添加到相应的 Intune 设备组来注册它们。</span><span class="sxs-lookup"><span data-stu-id="194f2-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="194f2-135">他们还制定了 BYOD 计划，供员工注册其个人设备。</span><span class="sxs-lookup"><span data-stu-id="194f2-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="194f2-136">已注册的设备接收 Intune 策略，这导致设备及其应用程序的托管和安全。</span><span class="sxs-lookup"><span data-stu-id="194f2-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="194f2-137">未注册的设备具有移动应用管理 (MAM) 指定允许的应用程序的策略。</span><span class="sxs-lookup"><span data-stu-id="194f2-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="194f2-138">下面是 Contoso 移动设备管理部署体系结构。</span><span class="sxs-lookup"><span data-stu-id="194f2-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Contoso 移动设备管理部署基础结构](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="194f2-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="194f2-140">Next step</span></span>

<span data-ttu-id="194f2-141">了解 Contoso 如何使用[](contoso-info-protect.md)企业Microsoft 365信息保护功能来分类、标识和保护整个组织的重要数字资产。</span><span class="sxs-lookup"><span data-stu-id="194f2-141">Learn how Contoso uses the [information protection capabilities](contoso-info-protect.md) of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="194f2-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="194f2-142">See also</span></span>

[<span data-ttu-id="194f2-143">设备管理Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="194f2-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="194f2-144">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="194f2-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="194f2-145">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="194f2-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

