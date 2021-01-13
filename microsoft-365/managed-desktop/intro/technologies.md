---
title: Microsoft 托管桌面技术
description: 本文列出了 Microsoft 托管桌面中使用的技术和应用。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: cb368939e87ddbbfc8f5386c6fc5d6bff110a7ec
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840897"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="381f6-104">Microsoft 托管桌面技术</span><span class="sxs-lookup"><span data-stu-id="381f6-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="381f6-105">本文列出了 Microsoft 托管桌面中使用的技术和应用。</span><span class="sxs-lookup"><span data-stu-id="381f6-105">This article lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="381f6-106">所有 Microsoft 托管桌面用户都需要 Microsoft 365 企业版许可。</span><span class="sxs-lookup"><span data-stu-id="381f6-106">Microsoft 365 Enterprise licensing is required for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="381f6-107">有关服务的许可要求详细信息，请参阅["Microsoft 托管桌面的先决条件"。](../get-ready/prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="381f6-107">For more information on licensing requirements for the service, see [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).</span></span>

<span data-ttu-id="381f6-108">本文总结了所需企业版许可证中包含的组件，并介绍了该服务如何将每个组件与 Microsoft 托管桌面设备一同使用。</span><span class="sxs-lookup"><span data-stu-id="381f6-108">This article summarizes the components included in the required Enterprise licenses, with a description of how the service uses each component with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="381f6-109">Microsoft 托管桌面文档中详细介绍了每个区域的特定角色和职责。</span><span class="sxs-lookup"><span data-stu-id="381f6-109">Specific roles and responsibilities for each area are detailed throughout Microsoft Managed Desktop documentation.</span></span> 

## <a name="office-365-e3-or-e5"></a><span data-ttu-id="381f6-110">Office 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="381f6-110">Office 365 E3 or E5</span></span>
 |
 --- | ---
<span data-ttu-id="381f6-111">Microsoft 365 企业应用版 (64 位) </span><span class="sxs-lookup"><span data-stu-id="381f6-111">Microsoft 365 Apps for enterprise (64-bit)</span></span> | <span data-ttu-id="381f6-112">这些 Office 应用程序将随设备一起提供：Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote。</span><span class="sxs-lookup"><span data-stu-id="381f6-112">These Office applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="381f6-113">不包括 64 位完整版本的 Microsoft Project 和 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="381f6-113">The 64-bit full versions of Microsoft Project and Microsoft Visio aren't included.</span></span> <span data-ttu-id="381f6-114">但是，由于这些应用程序的安装取决于 Microsoft 365 企业应用版安装，因此 Microsoft 托管桌面已创建默认的 Microsoft Intune 部署和安全组，然后可以使用它们向许可用户部署这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="381f6-114">However, since the installation of these applications depends on the Microsoft 365 Apps for enterprise installation, Microsoft Managed Desktop has created default Microsoft Intune deployments and security groups that you can then use to deploy these applications to licensed users.</span></span> <span data-ttu-id="381f6-115">有关详细信息，请参阅在 Microsoft 托管桌面设备上安装 Microsoft Project 或[Microsoft Visio。](../get-started/project-visio.md)</span><span class="sxs-lookup"><span data-stu-id="381f6-115">For more information, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>
<span data-ttu-id="381f6-116">OneDrive</span><span class="sxs-lookup"><span data-stu-id="381f6-116">OneDrive</span></span> |<span data-ttu-id="381f6-117">当用户首次登录 OneDrive 时，会为用户启用 Azure Active Directory 单一登录。</span><span class="sxs-lookup"><span data-stu-id="381f6-117">Azure Active Directory Single Sign On is enabled for users when they first sign in to OneDrive.</span></span><br><br><span data-ttu-id="381f6-118">包含"桌面"、"文档"和"图片"文件夹的已知文件夹重定向;由 Microsoft 托管桌面启用和配置。</span><span class="sxs-lookup"><span data-stu-id="381f6-118">Known Folder Redirection for "Desktop", "Document", and "Pictures" folders is included; enabled and configured by Microsoft Managed Desktop.</span></span>
<span data-ttu-id="381f6-119">应用商店应用</span><span class="sxs-lookup"><span data-stu-id="381f6-119">Store Apps</span></span> |    <span data-ttu-id="381f6-120">Microsoft Sway 和 Power BI 未随设备一起提供。</span><span class="sxs-lookup"><span data-stu-id="381f6-120">Microsoft Sway and Power BI aren't shipped with the device.</span></span> <span data-ttu-id="381f6-121">这些应用可从 Microsoft Store 下载。</span><span class="sxs-lookup"><span data-stu-id="381f6-121">These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="381f6-122">Win32 应用程序</span><span class="sxs-lookup"><span data-stu-id="381f6-122">Win32 Applications</span></span> |    <span data-ttu-id="381f6-123">Teams 不是随设备一起提供的，而是由 Microsoft 为 Microsoft 托管桌面设备打包和提供。</span><span class="sxs-lookup"><span data-stu-id="381f6-123">Teams isn't shipped with the device, but is packaged and provided by Microsoft for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="381f6-124">Azure 信息保护客户端未随设备一起提供，但你可以打包它进行部署。</span><span class="sxs-lookup"><span data-stu-id="381f6-124">Azure Information Protection Client isn't shipped with the device, but you can have it packaged for deployment.</span></span>
<span data-ttu-id="381f6-125">Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="381f6-125">Web Applications</span></span> |  <span data-ttu-id="381f6-126">Yammer、浏览器中的 Office、Delve、Flow、StaffHub、PowerApps 和 Planner 未随设备一起提供。</span><span class="sxs-lookup"><span data-stu-id="381f6-126">Yammer, Office in a browser, Delve, Flow, StaffHub, PowerApps, and Planner aren't shipped with the device.</span></span> <span data-ttu-id="381f6-127">用户可以使用浏览器访问这些应用程序的 Web 版本。</span><span class="sxs-lookup"><span data-stu-id="381f6-127">Users can access the web version of these applications with a browser.</span></span>


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="381f6-128">带 Microsoft Defender for Endpoint 的 Windows 10 企业版 E5 或 E3</span><span class="sxs-lookup"><span data-stu-id="381f6-128">Windows 10 Enterprise E5 or E3 with Microsoft Defender for Endpoint</span></span>

 |
 --- | ---
<span data-ttu-id="381f6-129">Application Virtualization (App-V) </span><span class="sxs-lookup"><span data-stu-id="381f6-129">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="381f6-130">客户可以使用 Intune Win32 应用管理客户端部署 App-V 程序包。</span><span class="sxs-lookup"><span data-stu-id="381f6-130">Customers can deploy App-V packages using the Intune Win32 app management client.</span></span>
<span data-ttu-id="381f6-131">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="381f6-131">Microsoft Defender for Endpoint</span></span> |    <span data-ttu-id="381f6-132">Microsoft 托管桌面使用此产品监视设备安全。</span><span class="sxs-lookup"><span data-stu-id="381f6-132">Microsoft Managed Desktop uses this product to monitor device security.</span></span> 

## <a name="enterprise-mobility--security-e5"></a><span data-ttu-id="381f6-133">企业移动性 + 安全性 E5</span><span class="sxs-lookup"><span data-stu-id="381f6-133">Enterprise Mobility + Security E5</span></span>

 |
 --- | ---
<span data-ttu-id="381f6-134">企业移动性 + 安全性 E3</span><span class="sxs-lookup"><span data-stu-id="381f6-134">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="381f6-135">Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="381f6-135">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="381f6-136">可以使用企业移动性 + 安全性 E3 和 Azure Active Directory Premium P2 的所有功能来管理 MDM 设备。</span><span class="sxs-lookup"><span data-stu-id="381f6-136">You can use all features of Enterprise Mobility + Security E3 and Azure Active Directory Premium P2 to manage MDM devices.</span></span>
<span data-ttu-id="381f6-137">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="381f6-137">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="381f6-138">可以将此可选功能与 Microsoft 托管桌面一同使用。</span><span class="sxs-lookup"><span data-stu-id="381f6-138">You can use this optional feature with Microsoft Managed Desktop.</span></span>
<span data-ttu-id="381f6-139">Azure 信息保护 P2</span><span class="sxs-lookup"><span data-stu-id="381f6-139">Azure Information Protection P2</span></span>  | <span data-ttu-id="381f6-140">可以将此可选功能与 Microsoft 托管桌面一同使用。</span><span class="sxs-lookup"><span data-stu-id="381f6-140">You can use this optional feature with Microsoft Managed Desktop.</span></span>
