---
title: Contoso 移动设备管理
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft 365 企业版中的 EMS 来管理其设备以及上面运行的应用。
ms.openlocfilehash: f47d6a1ee608d33802f1c523d3b954af3771f212
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278038"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="de416-103">Contoso 移动设备管理</span><span class="sxs-lookup"><span data-stu-id="de416-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="de416-104">**摘要**：了解 Contoso 如何使用 Microsoft 365 企业版中的 EMS 来管理其设备以及上面运行的应用。</span><span class="sxs-lookup"><span data-stu-id="de416-104">**Summary:** Understand how Contoso uses EMS in Microsoft 365 Enterprise to manage its devices and the apps that run on them.</span></span>

<span data-ttu-id="de416-105">Microsoft 365 企业版中的“企业移动性 + 安全性”(EMS) 由 Microsoft Intune 和一组 Azure 服务组成，旨在支持移动设备和应用程序的管理和安全性。</span><span class="sxs-lookup"><span data-stu-id="de416-105">Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise consists of Microsoft Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="de416-p101">Contoso 拥有许多使用移动设备的员工，其中一些人在 Contoso 办公室有办公位，另一些则没有。Contoso 需要通过一种方法来支持员工高效工作，同时确保设备、存储在这些设备上的 Contoso 数据和应用程序行为的安全性。</span><span class="sxs-lookup"><span data-stu-id="de416-p101">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="de416-108">计划</span><span class="sxs-lookup"><span data-stu-id="de416-108">Plan</span></span>

<span data-ttu-id="de416-109">在刚开始分析 Microsoft 365 企业版的移动设备管理时，Contoso 确定了以下 Intune 用例：</span><span class="sxs-lookup"><span data-stu-id="de416-109">Early in the analysis of mobile device management for Microsoft 365 Enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="de416-110">保护 Exchange Online 电子邮件和数据，以便通过移动设备安全地访问这些内容</span><span class="sxs-lookup"><span data-stu-id="de416-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="de416-111">为 Contoso 员工实施自带设备 (BYOD) 计划</span><span class="sxs-lookup"><span data-stu-id="de416-111">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="de416-112">向 Contoso 员工发放组织所拥有的手机和使用受限的共享平板电脑</span><span class="sxs-lookup"><span data-stu-id="de416-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="de416-113">Contoso 并未使用 Intune 来达到以下目的：</span><span class="sxs-lookup"><span data-stu-id="de416-113">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="de416-114">允许员工从非托管公共网亭安全访问 Office 365</span><span class="sxs-lookup"><span data-stu-id="de416-114">Allow employees to securely access Office 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="de416-115">保护本地电子邮件和数据，以便通过移动设备安全地访问这些内容，因为他们已不再使用本地 Microsoft Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="de416-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="de416-116">部署</span><span class="sxs-lookup"><span data-stu-id="de416-116">Deploy</span></span>

<span data-ttu-id="de416-117">以下是 Contoso 设置其移动设备管理基础结构的方式：</span><span class="sxs-lookup"><span data-stu-id="de416-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="de416-118">将 Intune 设置为移动设备管理 (MDM) 主管应用，并将在 Azure 上使用 Intune 来管理内容和设备</span><span class="sxs-lookup"><span data-stu-id="de416-118">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="de416-119">创建了用于进行设备注册的 Azure AD 组以及 Intune 设置和基于设备的条件访问策略</span><span class="sxs-lookup"><span data-stu-id="de416-119">Created Azure AD groups for device groups for enrollment and Intune settings and conditional access policies</span></span>

  <span data-ttu-id="de416-120">有关详细信息，请参阅 [Contoso 的配置条件访问策略](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。</span><span class="sxs-lookup"><span data-stu-id="de416-120">See [Contoso's conditional access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) for more information.</span></span>

- <span data-ttu-id="de416-121">启用了 Apple 设备平台以支持员工使用 ipad、iMac、iPhone 和基于 iPhone 的企业所拥有的手机</span><span class="sxs-lookup"><span data-stu-id="de416-121">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="de416-122">创建了特定于 Contoso 的条款和条件策略，在移动设备上安装 Contoso 的公司门户时会看到这些策略</span><span class="sxs-lookup"><span data-stu-id="de416-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="de416-123">对于未注册的设备，在用户访问 Office 365 服务时，会有一组移动应用程序管理 (MAM) 策略要求进行身份验证</span><span class="sxs-lookup"><span data-stu-id="de416-123">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Office 365 services</span></span>
- <span data-ttu-id="de416-124">创建了强制实施以下内容的 Intune 策略：</span><span class="sxs-lookup"><span data-stu-id="de416-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="de416-125">允许的应用</span><span class="sxs-lookup"><span data-stu-id="de416-125">Allowed apps</span></span>
  - <span data-ttu-id="de416-126">设备加密，以帮助防止未经授权的访问</span><span class="sxs-lookup"><span data-stu-id="de416-126">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="de416-127">六位数的 PIN 或密码</span><span class="sxs-lookup"><span data-stu-id="de416-127">A six-digit PIN or password</span></span>
  - <span data-ttu-id="de416-128">不活动超时时间</span><span class="sxs-lookup"><span data-stu-id="de416-128">An inactivity timeout period</span></span>
  - <span data-ttu-id="de416-129">防病毒和恶意软件保护以及通过 Windows Defender 在 Windows 10 设备上的签名更新</span><span class="sxs-lookup"><span data-stu-id="de416-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="de416-130">Windows 10 设备上的自动更新，其中包含最新安全更新</span><span class="sxs-lookup"><span data-stu-id="de416-130">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="de416-131">向管理的设备推送证书</span><span class="sxs-lookup"><span data-stu-id="de416-131">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="de416-p102">商业与个人数据的明确区分。用户或管理员可以选择性地擦除设备中的公司数据，而将图片、个人电子邮件帐户和个人文件等个人数据保持不变。</span><span class="sxs-lookup"><span data-stu-id="de416-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="de416-p103">部署后，Contoso 通过将相应设备添加到适当的 Intune 设备组注册了电脑和公司所拥有的智能手机和平板电脑，然后为员工推出了 BYOD 计划，以注册他们的私人设备。已注册的设备均收到了 Intune 策略，因而可实现对设备及其应用程序的托管和保护。而对于未注册的设备，则会由移动应用程序管理 (MAM) 策略来指定允许的应用程序。</span><span class="sxs-lookup"><span data-stu-id="de416-p103">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices. Enrolled devices received Intune policies, resulting in managed and secured devices and their applications. Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

## <a name="next-step"></a><span data-ttu-id="de416-137">后续步骤</span><span class="sxs-lookup"><span data-stu-id="de416-137">Next step</span></span>

<span data-ttu-id="de416-138">[了解](contoso-info-protect.md) Contoso 如何使用 Microsoft 365 企业版的信息保护功能来分类、标识和保护其整个组织内的重要数字资产。</span><span class="sxs-lookup"><span data-stu-id="de416-138">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 Enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="de416-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de416-139">See also</span></span>

[<span data-ttu-id="de416-140">Microsoft 365 企业版移动设备管理</span><span class="sxs-lookup"><span data-stu-id="de416-140">Mobile device management for Microsoft 365 Enterprise</span></span>](mobility-infrastructure.md)

[<span data-ttu-id="de416-141">部署指南</span><span class="sxs-lookup"><span data-stu-id="de416-141">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="de416-142">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="de416-142">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

