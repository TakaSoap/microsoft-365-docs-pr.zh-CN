---
title: Microsoft 托管桌面技术
description: 本主题列出了 Microsoft 托管桌面中使用的技术和应用。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 914a90b4267132c9cb942740ceb974b084bcdf82
ms.sourcegitcommit: 2f4a61f02ea90102ded8e5d71c9b78a1f7f6b789
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2019
ms.locfileid: "35778087"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="c6c74-104">Microsoft 托管桌面技术</span><span class="sxs-lookup"><span data-stu-id="c6c74-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="c6c74-105">本主题列出了 Microsoft 托管桌面中使用的技术和应用。</span><span class="sxs-lookup"><span data-stu-id="c6c74-105">This topic lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="c6c74-106">所有 Microsoft 托管桌面用户都需要 microsoft 365 企业版许可。</span><span class="sxs-lookup"><span data-stu-id="c6c74-106">Microsoft 365 Enterprise licensing is required for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="c6c74-107">有关服务的许可要求的详细信息, 请参阅[Microsoft 托管桌面的先决条件](../get-ready/prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="c6c74-107">For more information on licensing requirements for the service, see [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).</span></span>

<span data-ttu-id="c6c74-108">以下是所需企业版许可证中包含的所有组件, 以及服务如何将每个组件与 Microsoft 托管桌面设备一起使用。</span><span class="sxs-lookup"><span data-stu-id="c6c74-108">The following are all components that are included in the required Enterprise licenses and how the service uses each component with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="c6c74-109">在整个 Microsoft 托管桌面主题中详细介绍了每个领域的特定角色和职责。</span><span class="sxs-lookup"><span data-stu-id="c6c74-109">Specific roles and responsibilities for each area are detailed throughout the Microsoft Managed Desktop topic.</span></span> 

## <a name="office-365-e3"></a><span data-ttu-id="c6c74-110">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="c6c74-110">Office 365 E3</span></span>
 |
 --- | ---
<span data-ttu-id="c6c74-111">Office 365 Standard Suite (64 位) \*</span><span class="sxs-lookup"><span data-stu-id="c6c74-111">Office 365 Standard Suite (64bit)\*</span></span> | <span data-ttu-id="c6c74-112">标准 Office 套件应用程序将随设备一起附带: Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote。</span><span class="sxs-lookup"><span data-stu-id="c6c74-112">The standard Office Suite of applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="c6c74-113">64位单击可运行 (C2R) 完整版本的 Microsoft Project 和 Microsoft Visio 不包含在 Office 365 Standard Suite 中。</span><span class="sxs-lookup"><span data-stu-id="c6c74-113">The 64bit Click to Run (C2R) full versions of Microsoft Project and Microsoft Visio are not included in the Office 365 Standard Suite.</span></span>  <span data-ttu-id="c6c74-114">但是, 由于安装这些应用程序依赖于标准 Office 套件安装, Microsoft 托管桌面已创建默认的 Intune 部署和安全组, 客户将使用这些部署和安全组将这些应用程序部署到许可的最终用户。</span><span class="sxs-lookup"><span data-stu-id="c6c74-114">However, since the installation of these applications are dependent on the standard Office Suite installation, Microsoft Managed Desktop has created default Intune deployments and Security groups that the customer will use to deploy these applications to licensed end users.</span></span>  
<span data-ttu-id="c6c74-115">应用商店应用</span><span class="sxs-lookup"><span data-stu-id="c6c74-115">Store Apps</span></span> |    <span data-ttu-id="c6c74-116">Microsoft Sway, Power BI Desktop 不随设备附带。</span><span class="sxs-lookup"><span data-stu-id="c6c74-116">Microsoft Sway, Power BI Desktop are not shipped with device.</span></span> <span data-ttu-id="c6c74-117">这些应用程序可从 Microsoft Store 下载。</span><span class="sxs-lookup"><span data-stu-id="c6c74-117">These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="c6c74-118">Win32 应用程序</span><span class="sxs-lookup"><span data-stu-id="c6c74-118">Win32 Applications</span></span> |    <span data-ttu-id="c6c74-119">Power BI Pro、Azure 信息保护客户端和 Microsoft Planner 不随设备一起提供, 可以打包以供客户部署。</span><span class="sxs-lookup"><span data-stu-id="c6c74-119">Power BI Pro, Azure Information Protection Client, and Microsoft Planner are not shipped with device and can be packaged for deployment by the customer.</span></span> 
<span data-ttu-id="c6c74-120">Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="c6c74-120">Web Applications</span></span> |  <span data-ttu-id="c6c74-121">Yammer、Office 在浏览器、Delve、流、StaffHub、PowerApps 不随设备一起附带。</span><span class="sxs-lookup"><span data-stu-id="c6c74-121">Yammer, Office in a browser, Delve, Flow, StaffHub, PowerApps are not shipped with the device.</span></span> <span data-ttu-id="c6c74-122">用户可以通过浏览器访问这些应用程序的 web 版本。</span><span class="sxs-lookup"><span data-stu-id="c6c74-122">Users can access the web version of these applications with a browser.</span></span>
<span data-ttu-id="c6c74-123">Skype for Business Online 云 PBX</span><span class="sxs-lookup"><span data-stu-id="c6c74-123">Skype for Business Online Cloud PBX</span></span> | <span data-ttu-id="c6c74-124">可通过 Office 365 获取此功能。</span><span class="sxs-lookup"><span data-stu-id="c6c74-124">This feature is available via Office 365.</span></span> <span data-ttu-id="c6c74-125">Microsoft 托管桌面不会配置此服务的任何方面</span><span class="sxs-lookup"><span data-stu-id="c6c74-125">Microsoft Managed Desktop will not configure any aspect of this service</span></span>

## <a name="windows-10-enterprise-e5"></a><span data-ttu-id="c6c74-126">Windows 10 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="c6c74-126">Windows 10 Enterprise E5</span></span>

 |
 --- | ---
<span data-ttu-id="c6c74-127">Credential Guard</span><span class="sxs-lookup"><span data-stu-id="c6c74-127">Credential Guard</span></span> |  <span data-ttu-id="c6c74-128">Microsoft 将提供指导并管理此功能的云方面。</span><span class="sxs-lookup"><span data-stu-id="c6c74-128">Microsoft will provide guidance and manage cloud aspects of this feature.</span></span>
<span data-ttu-id="c6c74-129">Application Virtualization (app-v)</span><span class="sxs-lookup"><span data-stu-id="c6c74-129">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="c6c74-130">Microsoft 托管桌面不支持此类型的部署, 因为 Intune 不支持此类型的部署。</span><span class="sxs-lookup"><span data-stu-id="c6c74-130">Microsoft Managed Desktop does not support this type of deployment as it is not supported on Intune.</span></span>
<span data-ttu-id="c6c74-131">用户体验虚拟化 (UE-V)</span><span class="sxs-lookup"><span data-stu-id="c6c74-131">User Experience Virtualization (UE-V)</span></span> | <span data-ttu-id="c6c74-132">这不与 Microsoft 托管桌面托管设备一起使用。</span><span class="sxs-lookup"><span data-stu-id="c6c74-132">This is not used with Microsoft Managed Desktop managed devices.</span></span>
<span data-ttu-id="c6c74-133">托管用户体验</span><span class="sxs-lookup"><span data-stu-id="c6c74-133">Managed User Experience</span></span>  | <span data-ttu-id="c6c74-134">这不与 Microsoft 托管桌面托管设备一起使用。</span><span class="sxs-lookup"><span data-stu-id="c6c74-134">This is not used with Microsoft Managed Desktop managed devices.</span></span> <span data-ttu-id="c6c74-135">MDM 用作设备管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="c6c74-135">MDM is used as a solution for device management.</span></span>
<span data-ttu-id="c6c74-136">Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="c6c74-136">Microsoft Defender Advanced Threat Protection</span></span> | <span data-ttu-id="c6c74-137">Microsoft 托管桌面使用它来管理设备安全策略。</span><span class="sxs-lookup"><span data-stu-id="c6c74-137">This is used by Microsoft Managed Desktop to manage device security policies.</span></span> 

## <a name="enterprise-mobility--security-e5"></a><span data-ttu-id="c6c74-138">企业移动性 + 安全性 E5</span><span class="sxs-lookup"><span data-stu-id="c6c74-138">Enterprise Mobility + Security E5</span></span>

 |
 --- | ---
<span data-ttu-id="c6c74-139">企业移动性 + 安全 E3</span><span class="sxs-lookup"><span data-stu-id="c6c74-139">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="c6c74-140">Azure Active Directory 高级 P2</span><span class="sxs-lookup"><span data-stu-id="c6c74-140">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="c6c74-141">企业移动性 + 安全 E3 和 AADP 的各个方面均可用于管理 MDM 设备。</span><span class="sxs-lookup"><span data-stu-id="c6c74-141">All aspects of the Enterprise Mobility + Security E3 and AADP may be used to manage MDM devices.</span></span>
<span data-ttu-id="c6c74-142">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c6c74-142">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="c6c74-143">这是客户可用于 Microsoft 托管桌面服务的一项可选功能。</span><span class="sxs-lookup"><span data-stu-id="c6c74-143">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>
<span data-ttu-id="c6c74-144">Azure 信息保护 P2</span><span class="sxs-lookup"><span data-stu-id="c6c74-144">Azure Information Protection P2</span></span>  |<span data-ttu-id="c6c74-145">这是客户可用于 Microsoft 托管桌面服务的一项可选功能。</span><span class="sxs-lookup"><span data-stu-id="c6c74-145">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>
