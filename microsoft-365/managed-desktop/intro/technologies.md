---
title: Microsoft 托管桌面技术
description: 本主题列出了 Microsoft 托管桌面中使用的技术和应用。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1f82c339e8cbe4426c87eae045107d26201b0025
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530015"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="af47b-104">Microsoft 托管桌面技术</span><span class="sxs-lookup"><span data-stu-id="af47b-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="af47b-105">本主题列出了 Microsoft 托管桌面中使用的技术和应用。</span><span class="sxs-lookup"><span data-stu-id="af47b-105">This topic lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="af47b-106">所有 Microsoft 托管桌面用户都需要 microsoft 365 企业版许可。</span><span class="sxs-lookup"><span data-stu-id="af47b-106">Microsoft 365 Enterprise licensing is required for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="af47b-107">有关服务的许可要求的详细信息，请参阅[Microsoft 托管桌面的先决条件](../get-ready/prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="af47b-107">For more information on licensing requirements for the service, see [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).</span></span>

<span data-ttu-id="af47b-108">本主题汇总了所需的企业许可证中包含的组件，并介绍了服务如何将每个组件与 Microsoft 托管桌面设备一起使用。</span><span class="sxs-lookup"><span data-stu-id="af47b-108">This topic summarizes the components included in the required Enterprise licenses, with a description of how the service uses each component with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="af47b-109">Microsoft 托管桌面文档中详细介绍了每个领域的具体角色和职责。</span><span class="sxs-lookup"><span data-stu-id="af47b-109">Specific roles and responsibilities for each area are detailed throughout Microsoft Managed Desktop documentation.</span></span> 

## <a name="office-365-e3-or-e5"></a><span data-ttu-id="af47b-110">Office 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="af47b-110">Office 365 E3 or E5</span></span>
 |
 --- | ---
<span data-ttu-id="af47b-111">适用于企业的 Microsoft 365 应用（64位）</span><span class="sxs-lookup"><span data-stu-id="af47b-111">Microsoft 365 Apps for enterprise (64-bit)</span></span> | <span data-ttu-id="af47b-112">这些 Office 应用程序将随设备一起提供： Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote。</span><span class="sxs-lookup"><span data-stu-id="af47b-112">These Office applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="af47b-113">Microsoft Project 和 Microsoft Visio 的64位完整版本不包含在内。</span><span class="sxs-lookup"><span data-stu-id="af47b-113">The 64-bit full versions of Microsoft Project and Microsoft Visio are not included.</span></span> <span data-ttu-id="af47b-114">但是，由于安装这些应用程序取决于 Microsoft 365 Apps for enterprise 安装，Microsoft 托管桌面创建了默认的 Microsoft Intune 部署和安全组，然后可以使用这些部署和安全组将这些应用程序部署到许可的最终用户。</span><span class="sxs-lookup"><span data-stu-id="af47b-114">However, since the installation of these applications depends on the Microsoft 365 Apps for enterprise installation, Microsoft Managed Desktop has created default Microsoft Intune deployments and security groups that you can then use to deploy these applications to licensed end users.</span></span> <span data-ttu-id="af47b-115">有关详细信息，请参阅[在 Microsoft 托管桌面设备上安装 Microsoft Project 或 Microsoft Visio](../get-started/project-visio.md)。</span><span class="sxs-lookup"><span data-stu-id="af47b-115">For more information, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>
<span data-ttu-id="af47b-116">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="af47b-116">OneDrive for Business</span></span> |<span data-ttu-id="af47b-117">在首次登录 OneDrive for Business 时，将为最终用户启用 Azure Active Directory 单一登录。</span><span class="sxs-lookup"><span data-stu-id="af47b-117">Azure Active Directory Single Sign On is enabled for end users upon first sign in to OneDrive for Business.</span></span><br><br><span data-ttu-id="af47b-118">包含 "桌面"、"文档" 和 "图片" 文件夹的 "已知文件夹重定向"。由 Microsoft 托管桌面启用和配置。</span><span class="sxs-lookup"><span data-stu-id="af47b-118">Known Folder Redirection for "Desktop", "Document", and "Pictures" folders is included; enabled and configured by Microsoft Managed Desktop.</span></span> 
<span data-ttu-id="af47b-119">应用商店应用</span><span class="sxs-lookup"><span data-stu-id="af47b-119">Store Apps</span></span> |    <span data-ttu-id="af47b-120">Microsoft Sway 和 Power BI 不随设备一起提供。</span><span class="sxs-lookup"><span data-stu-id="af47b-120">Microsoft Sway and Power BI are not shipped with the device.</span></span> <span data-ttu-id="af47b-121">这些应用程序可从 Microsoft Store 下载。</span><span class="sxs-lookup"><span data-stu-id="af47b-121">These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="af47b-122">Win32 应用程序</span><span class="sxs-lookup"><span data-stu-id="af47b-122">Win32 Applications</span></span> |    <span data-ttu-id="af47b-123">团队不随设备一起提供，但会打包并由 Microsoft 为 Microsoft 托管桌面设备提供。</span><span class="sxs-lookup"><span data-stu-id="af47b-123">Teams is not shipped with the device, but is packaged and provided by Microsoft for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="af47b-124">Azure 信息保护客户端不随设备附带，但可以将其打包以进行部署。</span><span class="sxs-lookup"><span data-stu-id="af47b-124">Azure Information Protection Client is not shipped with the device, but you can have this packaged for deployment.</span></span> 
<span data-ttu-id="af47b-125">Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="af47b-125">Web Applications</span></span> |  <span data-ttu-id="af47b-126">Yammer、Office 在浏览器、Delve、流、StaffHub、PowerApps 和计划器中不随设备一起附带。</span><span class="sxs-lookup"><span data-stu-id="af47b-126">Yammer, Office in a browser, Delve, Flow, StaffHub, PowerApps, and Planner are not shipped with the device.</span></span> <span data-ttu-id="af47b-127">用户可以通过浏览器访问这些应用程序的 web 版本。</span><span class="sxs-lookup"><span data-stu-id="af47b-127">Users can access the web version of these applications with a browser.</span></span>


## <a name="windows-10-enterprise-e3-or-e5"></a><span data-ttu-id="af47b-128">Windows 10 企业版 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="af47b-128">Windows 10 Enterprise E3 or E5</span></span>

 |
 --- | ---
<span data-ttu-id="af47b-129">Application Virtualization （app-v）</span><span class="sxs-lookup"><span data-stu-id="af47b-129">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="af47b-130">客户可以使用 Intune Win32 应用管理客户端部署 App-v 程序包。</span><span class="sxs-lookup"><span data-stu-id="af47b-130">Customers can deploy App-V packages using the Intune Win32 app management client.</span></span>
<span data-ttu-id="af47b-131">Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="af47b-131">Microsoft Defender Advanced Threat Protection</span></span> |  <span data-ttu-id="af47b-132">Microsoft 托管桌面使用此来监视设备安全性。</span><span class="sxs-lookup"><span data-stu-id="af47b-132">Microsoft Managed Desktop uses this to monitor device security.</span></span> 

## <a name="enterprise-mobility--security-e5"></a><span data-ttu-id="af47b-133">企业移动性 + 安全性 E5</span><span class="sxs-lookup"><span data-stu-id="af47b-133">Enterprise Mobility + Security E5</span></span>

 |
 --- | ---
<span data-ttu-id="af47b-134">企业移动性 + 安全 E3</span><span class="sxs-lookup"><span data-stu-id="af47b-134">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="af47b-135">Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="af47b-135">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="af47b-136">您可以使用企业移动性 + 安全 E3 和 Azure Active Directory 高级 P2 的所有功能来管理 MDM 设备。</span><span class="sxs-lookup"><span data-stu-id="af47b-136">You can use all features of Enterprise Mobility + Security E3 and Azure Active Directory Premium P2 to manage MDM devices.</span></span>
<span data-ttu-id="af47b-137">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="af47b-137">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="af47b-138">可以将此可选功能与 Microsoft 托管桌面结合使用。</span><span class="sxs-lookup"><span data-stu-id="af47b-138">You can use this optional feature with Microsoft Managed Desktop.</span></span>
<span data-ttu-id="af47b-139">Azure 信息保护 P2</span><span class="sxs-lookup"><span data-stu-id="af47b-139">Azure Information Protection P2</span></span>  | <span data-ttu-id="af47b-140">可以将此可选功能与 Microsoft 托管桌面结合使用。</span><span class="sxs-lookup"><span data-stu-id="af47b-140">You can use this optional feature with Microsoft Managed Desktop.</span></span>
