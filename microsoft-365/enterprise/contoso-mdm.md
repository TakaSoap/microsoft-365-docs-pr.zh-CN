---
title: Contoso 移动设备管理
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft 365 企业版中的 Microsoft Intune 来管理其设备及其上运行的应用。
ms.openlocfilehash: 7232c89cc105525cc57facd5a1b9de06426adbca
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068360"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="fcdee-103">Contoso 移动设备管理</span><span class="sxs-lookup"><span data-stu-id="fcdee-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="fcdee-104">Microsoft 365 企业版包含 Intune 和一组 Azure 服务，可对移动设备和应用程序的管理和安全性进行支持。</span><span class="sxs-lookup"><span data-stu-id="fcdee-104">Microsoft 365 Enterprise includes Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="fcdee-p101">Contoso 拥有许多使用移动设备的员工，其中一些人在 Contoso 办公室有办公位，另一些则没有。Contoso 需要通过一种方法来支持员工高效工作，同时确保设备、存储在这些设备上的 Contoso 数据和应用程序行为的安全性。</span><span class="sxs-lookup"><span data-stu-id="fcdee-p101">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="fcdee-107">计划</span><span class="sxs-lookup"><span data-stu-id="fcdee-107">Plan</span></span>

<span data-ttu-id="fcdee-108">在刚开始分析 Microsoft 365 企业版的移动设备管理时，Contoso 确定了以下 Intune 用例：</span><span class="sxs-lookup"><span data-stu-id="fcdee-108">Early in the analysis of mobile device management for Microsoft 365 Enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="fcdee-109">保护 Exchange Online 电子邮件和数据，以便通过移动设备安全地访问这些内容</span><span class="sxs-lookup"><span data-stu-id="fcdee-109">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="fcdee-110">为 Contoso 员工实施自带设备 (BYOD) 计划</span><span class="sxs-lookup"><span data-stu-id="fcdee-110">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="fcdee-111">向 Contoso 员工发放组织所拥有的手机和使用受限的共享平板电脑</span><span class="sxs-lookup"><span data-stu-id="fcdee-111">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="fcdee-112">Contoso 并未使用 Intune 来达到以下目的：</span><span class="sxs-lookup"><span data-stu-id="fcdee-112">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="fcdee-113">允许员工从非托管公共网亭安全访问 Office 365</span><span class="sxs-lookup"><span data-stu-id="fcdee-113">Allow employees to securely access Office 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="fcdee-114">保护本地电子邮件和数据，以便通过移动设备安全地访问这些内容，因为他们已不再使用本地 Microsoft Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="fcdee-114">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="fcdee-115">部署</span><span class="sxs-lookup"><span data-stu-id="fcdee-115">Deploy</span></span>

<span data-ttu-id="fcdee-116">以下是 Contoso 设置其移动设备管理基础结构的方式：</span><span class="sxs-lookup"><span data-stu-id="fcdee-116">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="fcdee-117">将 Intune 设置为移动设备管理 (MDM) 主管应用，并将在 Azure 上使用 Intune 来管理内容和设备</span><span class="sxs-lookup"><span data-stu-id="fcdee-117">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="fcdee-118">创建了用于进行设备注册的 Azure AD 组以及 Intune 设置和基于设备的条件访问策略</span><span class="sxs-lookup"><span data-stu-id="fcdee-118">Created Azure AD groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="fcdee-119">有关详细信息，请参阅 [Contoso 的条件访问策略](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。</span><span class="sxs-lookup"><span data-stu-id="fcdee-119">See [Contoso's Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) for more information.</span></span>

- <span data-ttu-id="fcdee-120">启用了 Apple 设备平台以支持员工使用 ipad、iMac、iPhone 和基于 iPhone 的企业所拥有的手机</span><span class="sxs-lookup"><span data-stu-id="fcdee-120">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="fcdee-121">创建了特定于 Contoso 的条款和条件策略，在移动设备上安装 Contoso 的公司门户时会看到这些策略</span><span class="sxs-lookup"><span data-stu-id="fcdee-121">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="fcdee-122">对于未注册的设备，在用户访问 Office 365 服务时，会有一组移动应用程序管理 (MAM) 策略要求进行身份验证</span><span class="sxs-lookup"><span data-stu-id="fcdee-122">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Office 365 services</span></span>
- <span data-ttu-id="fcdee-123">创建了强制实施以下内容的 Intune 策略：</span><span class="sxs-lookup"><span data-stu-id="fcdee-123">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="fcdee-124">允许的应用</span><span class="sxs-lookup"><span data-stu-id="fcdee-124">Allowed apps</span></span>
  - <span data-ttu-id="fcdee-125">设备加密，以帮助防止未经授权的访问</span><span class="sxs-lookup"><span data-stu-id="fcdee-125">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="fcdee-126">六位数的 PIN 或密码</span><span class="sxs-lookup"><span data-stu-id="fcdee-126">A six-digit PIN or password</span></span>
  - <span data-ttu-id="fcdee-127">不活动超时时间</span><span class="sxs-lookup"><span data-stu-id="fcdee-127">An inactivity timeout period</span></span>
  - <span data-ttu-id="fcdee-128">防病毒和恶意软件保护以及通过 Windows Defender 在 Windows 10 设备上的签名更新</span><span class="sxs-lookup"><span data-stu-id="fcdee-128">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="fcdee-129">Windows 10 设备上的自动更新，其中包含最新安全更新</span><span class="sxs-lookup"><span data-stu-id="fcdee-129">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="fcdee-130">向管理的设备推送证书</span><span class="sxs-lookup"><span data-stu-id="fcdee-130">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="fcdee-p102">商业与个人数据的明确区分。用户或管理员可以选择性地擦除设备中的公司数据，而将图片、个人电子邮件帐户和个人文件等个人数据保持不变。</span><span class="sxs-lookup"><span data-stu-id="fcdee-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="fcdee-p103">部署后，Contoso 通过将相应设备添加到适当的 Intune 设备组注册了电脑和公司所拥有的智能手机和平板电脑，然后为员工推出了 BYOD 计划，以注册他们的私人设备。已注册的设备均收到了 Intune 策略，因而可实现对设备及其应用程序的托管和保护。而对于未注册的设备，则会由移动应用程序管理 (MAM) 策略来指定允许的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fcdee-p103">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices. Enrolled devices received Intune policies, resulting in managed and secured devices and their applications. Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="fcdee-136">下面是 Contoso 的移动设备管理部署体系结构。</span><span class="sxs-lookup"><span data-stu-id="fcdee-136">Here is Contoso's mobile device management deployment architecture.</span></span>

![Contoso 的移动设备管理部署基础结构](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="fcdee-138">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fcdee-138">Next step</span></span>

<span data-ttu-id="fcdee-139">[了解](contoso-info-protect.md) Contoso 如何使用 Microsoft 365 企业版的信息保护功能来分类、标识和保护其整个组织内的重要数字资产。</span><span class="sxs-lookup"><span data-stu-id="fcdee-139">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 Enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcdee-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fcdee-140">See also</span></span>

[<span data-ttu-id="fcdee-141">Microsoft 365 企业版移动设备管理</span><span class="sxs-lookup"><span data-stu-id="fcdee-141">Mobile device management for Microsoft 365 Enterprise</span></span>](mobility-infrastructure.md)

[<span data-ttu-id="fcdee-142">部署指南</span><span class="sxs-lookup"><span data-stu-id="fcdee-142">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="fcdee-143">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="fcdee-143">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

