---
title: Microsoft 托管桌面技术
description: 本主题列出的技术和 Microsoft 托管桌面中使用的应用程序。
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: da0268c6b0eddbd44cf62de2a95b963a443c3278
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865604"
---
# <a name="microsoft-managed-desktop-technologies"></a><span data-ttu-id="ef385-104">Microsoft 托管桌面技术</span><span class="sxs-lookup"><span data-stu-id="ef385-104">Microsoft Managed Desktop technologies</span></span>

<span data-ttu-id="ef385-105">本主题列出的技术和 Microsoft 托管桌面中使用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ef385-105">This topic lists the technologies and apps used in Microsoft Managed Desktop.</span></span>

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

<span data-ttu-id="ef385-p101">Microsoft 托管桌面服务需要安装 Microsoft 365 E5 许可证 （或等效身份）。以下是包含在此许可证和 Microsoft 托管桌面如何使用 Microsoft 托管桌面设备使用的每个组件中的所有组件。 整个 Microsoft 托管桌面主题详细介绍了每个区域的特定的角色和职责。</span><span class="sxs-lookup"><span data-stu-id="ef385-p101">Microsoft 365 E5 License (or equivalent) is required for Microsoft Managed Desktop service. The following are all components that are included in this license and how Microsoft Managed Desktop uses each component with Microsoft Managed Desktop devices.  Specific roles and responsibilities for each area are detailed throughout Microsoft Managed Desktop topics.</span></span> 

<span data-ttu-id="ef385-109">Microsoft 365 E5 由 3 个组件组成： Office 365 E5、 Windows 10 Enterprise 和 E5、 企业移动 + 安全 E5。</span><span class="sxs-lookup"><span data-stu-id="ef385-109">Microsoft 365 E5 is comprised of 3 components: Office 365 E5, Windows 10 Enterprise and E5, Enterprise Mobility + Security E5.</span></span>  

## <a name="office-365-e5"></a><span data-ttu-id="ef385-110">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="ef385-110">Office 365 E5</span></span>
 |
 --- | ---
<span data-ttu-id="ef385-111">Office 365 标准套件 （64 位） \*</span><span class="sxs-lookup"><span data-stu-id="ef385-111">Office 365 Standard Suite (64bit)\*</span></span> | <span data-ttu-id="ef385-112">标准的 Office 套件应用程序将附带设备： Word、 Excel、 PowerPoint、 Outlook、 Publisher、 Access、 业务，OneNote 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="ef385-112">The standard Office Suite of applications will be shipped with the device: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.</span></span><br><br><span data-ttu-id="ef385-p102">64 位单击以运行 Office 365 标准套件中不包含 (C2R) 完整版本的 Microsoft Project 和 Microsoft Visio。 但是，由于取决于标准的 Office 套件安装这些应用程序的安装，Microsoft 托管桌面已创建默认 Intune 部署和客户将用于部署到这些应用程序的安全组许可的最终用户。</span><span class="sxs-lookup"><span data-stu-id="ef385-p102">The 64bit Click to Run (C2R) full versions of Microsoft Project and Microsoft Visio are not included in the Office 365 Standard Suite.  However, since the installation of these applications are dependent on the standard Office Suite installation, Microsoft Managed Desktop has created default Intune deployments and Security groups that the customer will use to deploy these applications to licensed end users.</span></span>  
<span data-ttu-id="ef385-115">应用商店应用程序</span><span class="sxs-lookup"><span data-stu-id="ef385-115">Store Apps</span></span> |    <span data-ttu-id="ef385-p103">Microsoft Sway、 Microsoft 工作组和 Power BI 桌面 （不专业人员） 都不附带了设备。这些应用程序可供下载 Microsoft 存储中。</span><span class="sxs-lookup"><span data-stu-id="ef385-p103">Microsoft Sway, Microsoft Teams, Power BI Desktop (not Pro) are not shipped with device. These apps are available for download from Microsoft Store.</span></span>
<span data-ttu-id="ef385-118">Win32 应用程序</span><span class="sxs-lookup"><span data-stu-id="ef385-118">Win32 Applications</span></span> |    <span data-ttu-id="ef385-119">Power BI Pro、 Azure 信息保护客户端和 Microsoft 计划程序不附带设备，并可以由客户打包部署。</span><span class="sxs-lookup"><span data-stu-id="ef385-119">Power BI Pro, Azure Information Protection Client, and Microsoft Planner are not shipped with device and can be packaged for deployment by the customer.</span></span> 
<span data-ttu-id="ef385-120">Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="ef385-120">Web Applications</span></span> |  <span data-ttu-id="ef385-p104">Yammer，Office Online，Delve，流 StaffHub、 PowerApps 都不附带了该设备。用户可以访问这些浏览器中使用的应用程序的 web 版本。</span><span class="sxs-lookup"><span data-stu-id="ef385-p104">Yammer, Office Online, Delve, Flow, StaffHub, PowerApps are not shipped with the device. Users can access the web version of these applications with a browser.</span></span>
<span data-ttu-id="ef385-123">业务在线云和 PBX 的 Skype</span><span class="sxs-lookup"><span data-stu-id="ef385-123">Skype for Business Online Cloud PBX</span></span> | <span data-ttu-id="ef385-p105">可通过 Office 365 E5 获得此功能。Microsoft 托管桌面将不配置此服务的任何方面</span><span class="sxs-lookup"><span data-stu-id="ef385-p105">This feature is available via Office 365 E5. Microsoft Managed Desktop will not configure any aspect of this service</span></span>

## <a name="windows-10-enterprise-e5"></a><span data-ttu-id="ef385-126">Windows 10 企业 E5</span><span class="sxs-lookup"><span data-stu-id="ef385-126">Windows 10 Enterprise E5</span></span>

 |
 --- | ---
<span data-ttu-id="ef385-127">凭据 Guard</span><span class="sxs-lookup"><span data-stu-id="ef385-127">Credential Guard</span></span> |  <span data-ttu-id="ef385-128">Microsoft 托管桌面将所提供的指导和管理此功能的云方面</span><span class="sxs-lookup"><span data-stu-id="ef385-128">Microsoft Managed Desktop will provide guidance and manage cloud aspects of this feature</span></span>
<span data-ttu-id="ef385-129">设备 Guard （Windows Defender 应用程序控制）</span><span class="sxs-lookup"><span data-stu-id="ef385-129">Device Guard ( Windows Defender Application Control )</span></span>   | <span data-ttu-id="ef385-p106">Microsoft 托管桌面将创建策略。客户将管理签名</span><span class="sxs-lookup"><span data-stu-id="ef385-p106">Microsoft Managed Desktop will create the policy. Customer will manage signatures</span></span>
<span data-ttu-id="ef385-132">AppLocker 管理</span><span class="sxs-lookup"><span data-stu-id="ef385-132">AppLocker management</span></span> |  <span data-ttu-id="ef385-p107">Microsoft 托管桌面将创建策略。客户将管理签名</span><span class="sxs-lookup"><span data-stu-id="ef385-p107">Microsoft Managed Desktop will create the policy. Customer will manage signatures</span></span>
<span data-ttu-id="ef385-135">Application Virtualization (APP-V)</span><span class="sxs-lookup"><span data-stu-id="ef385-135">Application Virtualization (App-V)</span></span> |    <span data-ttu-id="ef385-136">Microsoft 托管桌面不支持这种部署，如 Intune 上不支持。</span><span class="sxs-lookup"><span data-stu-id="ef385-136">Microsoft Managed Desktop does not support this type of deployment as it is not supported on Intune.</span></span>
<span data-ttu-id="ef385-137">用户体验虚拟化 (UE-V)</span><span class="sxs-lookup"><span data-stu-id="ef385-137">User Experience Virtualization (UE-V)</span></span> | <span data-ttu-id="ef385-138">未使用此属性与托管的 Microsoft 托管桌面设备</span><span class="sxs-lookup"><span data-stu-id="ef385-138">This is not used with Microsoft Managed Desktop managed devices</span></span>
<span data-ttu-id="ef385-139">托管的用户体验</span><span class="sxs-lookup"><span data-stu-id="ef385-139">Managed User Experience</span></span>  | <span data-ttu-id="ef385-p108">这不用于托管的 Microsoft 托管桌面设备。MDM 用作设备管理解决方案</span><span class="sxs-lookup"><span data-stu-id="ef385-p108">This is not used with Microsoft Managed Desktop managed devices. MDM is used as a solution for device management</span></span>
<span data-ttu-id="ef385-142">Windows Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="ef385-142">Windows Defender Advanced Threat Protection</span></span> |   <span data-ttu-id="ef385-143">这用于通过 Microsoft 托管桌面管理设备安全策略。</span><span class="sxs-lookup"><span data-stu-id="ef385-143">This is used by Microsoft Managed Desktop to manage device security policies.</span></span> 

## <a name="enterprise-mobility--security"></a><span data-ttu-id="ef385-144">企业移动性 + 安全性</span><span class="sxs-lookup"><span data-stu-id="ef385-144">Enterprise Mobility + Security</span></span> 

 |
 --- | ---
<span data-ttu-id="ef385-145">企业移动 + 安全 E3</span><span class="sxs-lookup"><span data-stu-id="ef385-145">Enterprise Mobility + Security E3</span></span><br><span data-ttu-id="ef385-146">Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="ef385-146">Azure Active Directory Premium P2</span></span> |    <span data-ttu-id="ef385-147">企业移动 + 安全 E3 和 AADP 的所有方面可能都用于管理 MDM 设备</span><span class="sxs-lookup"><span data-stu-id="ef385-147">All aspects of the Enterprise Mobility + Security E3 and AADP may be used to manage MDM devices</span></span>
<span data-ttu-id="ef385-148">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ef385-148">Microsoft Cloud App Security</span></span> |  <span data-ttu-id="ef385-149">这是一项可选功能，客户可以使用与 Microsoft 托管桌面服务。</span><span class="sxs-lookup"><span data-stu-id="ef385-149">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>
<span data-ttu-id="ef385-150">Azure 信息保护 P2</span><span class="sxs-lookup"><span data-stu-id="ef385-150">Azure Information Protection P2</span></span>  |<span data-ttu-id="ef385-151">这是一项可选功能，客户可以使用与 Microsoft 托管桌面服务。</span><span class="sxs-lookup"><span data-stu-id="ef385-151">This is an optional feature that customers can use with the Microsoft Managed Desktop service.</span></span>