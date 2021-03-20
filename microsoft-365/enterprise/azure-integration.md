---
title: Azure 与 Microsoft 365 集成
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: 如果你希望密码同步或单一登录与本地环境集成 Microsoft 365 与 Azure AD。
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905328"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="462ec-103">Azure 与 Microsoft 365 集成</span><span class="sxs-lookup"><span data-stu-id="462ec-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="462ec-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="462ec-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="462ec-105">Microsoft 365 使用 Azure Active Directory (Azure AD) 在后台管理用户标识。</span><span class="sxs-lookup"><span data-stu-id="462ec-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="462ec-106">你的 Microsoft 365 订阅包括免费的 Azure AD 订阅，以便你可以集成本地 Active Directory 域服务 (AD DS) 以同步用户帐户和密码或设置单一登录。</span><span class="sxs-lookup"><span data-stu-id="462ec-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="462ec-107">还可以购买高级功能，以更好地管理帐户。</span><span class="sxs-lookup"><span data-stu-id="462ec-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="462ec-108">Azure AD 还提供了其他功能，如管理集成应用，可用于扩展和自定义 Microsoft 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="462ec-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="462ec-109">可以使用 Azure AD 部署顾问在 Microsoft 365 管理中心获得指导性安装和配置体验 (必须登录到 Microsoft 365) ：</span><span class="sxs-lookup"><span data-stu-id="462ec-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="462ec-110">Azure AD Connect 顾问</span><span class="sxs-lookup"><span data-stu-id="462ec-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="462ec-111">AD FS 部署顾问</span><span class="sxs-lookup"><span data-stu-id="462ec-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="462ec-112">Azure AD 设置指南</span><span class="sxs-lookup"><span data-stu-id="462ec-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="462ec-113">Azure AD 版本和 Microsoft 365 身份管理</span><span class="sxs-lookup"><span data-stu-id="462ec-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="462ec-114">如果你有 Microsoft 365 的付费订阅，则还有免费的 Azure AD 订阅。</span><span class="sxs-lookup"><span data-stu-id="462ec-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="462ec-115">可以使用 Azure AD 创建和管理用户和组帐户。</span><span class="sxs-lookup"><span data-stu-id="462ec-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="462ec-116">若要激活此订阅，必须完成一次注册。</span><span class="sxs-lookup"><span data-stu-id="462ec-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="462ec-117">之后，你可以从 Microsoft 365 管理中心访问 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="462ec-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="462ec-118">有关注册免费 Azure AD 订阅的说明，请参阅 [使用免费的 Azure AD 订阅](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="462ec-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="462ec-119">不要直接转到 azure.microsoft.com 注册，否则你最终会获得 Microsoft Azure 的试用版或付费订阅，该订阅独立于 Microsoft 365 的免费 Azure AD 订阅。</span><span class="sxs-lookup"><span data-stu-id="462ec-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="462ec-120">借助免费订阅，你可以与本地目录同步、设置单一登录，以及将许多软件作为服务应用程序（如 Salesforce、DropBox 等）进行同步。</span><span class="sxs-lookup"><span data-stu-id="462ec-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="462ec-121">如果需要增强的 AD DS 功能、双向同步和其他管理功能，可以将免费订阅升级到付费付费订阅。</span><span class="sxs-lookup"><span data-stu-id="462ec-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="462ec-122">有关详细信息，请参阅 [Azure Active Directory 版本](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="462ec-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="462ec-123">有关 Microsoft 365 和 Azure AD 详细信息，请参阅 [Microsoft 365 标识模型](about-microsoft-365-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="462ec-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="462ec-124">扩展 Microsoft 365 租户的功能</span><span class="sxs-lookup"><span data-stu-id="462ec-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="462ec-125">**功能**</span><span class="sxs-lookup"><span data-stu-id="462ec-125">**Feature**</span></span>|<span data-ttu-id="462ec-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="462ec-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="462ec-127">集成应用</span><span class="sxs-lookup"><span data-stu-id="462ec-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="462ec-128">你可以向个别应用授予对 Microsoft 365 数据（如邮件、日历、联系人、用户、组、文件和文件夹）的访问权限。</span><span class="sxs-lookup"><span data-stu-id="462ec-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="462ec-129">还可以在全局管理员级别授权这些应用，并可在 Azure AD 中注册应用，使其可供整个公司使用。</span><span class="sxs-lookup"><span data-stu-id="462ec-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="462ec-130">有关详细信息，请参阅适用于[Microsoft 365 管理员的集成应用和 Azure AD。](integrated-apps-and-azure-ads.md)</span><span class="sxs-lookup"><span data-stu-id="462ec-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="462ec-131">另请参阅 [单一登录](/azure/active-directory/manage-apps/what-is-single-sign-on)。</span><span class="sxs-lookup"><span data-stu-id="462ec-131">Also see [Single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>  <br/> |
|<span data-ttu-id="462ec-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="462ec-132">PowerApps</span></span>  <br/> | <span data-ttu-id="462ec-133">Power Apps 是适用于可连接到现有数据源（如 SharePoint 列表和其他数据应用程序）的移动设备的聚焦应用。</span><span class="sxs-lookup"><span data-stu-id="462ec-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="462ec-134">有关详细信息[，请参阅在 SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab)和[PowerApps 页面中为列表创建 PowerApp。](https://powerapps.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="462ec-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="462ec-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="462ec-135">See also</span></span>

[<span data-ttu-id="462ec-136">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="462ec-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)