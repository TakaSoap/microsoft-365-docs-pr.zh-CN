---
title: Azure 与 Microsoft 365 的集成
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
description: 如果要使用本地环境进行密码同步或单一登录，请将 Microsoft 365 与 Azure AD 集成。
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384750"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="33441-103">Azure 与 Microsoft 365 的集成</span><span class="sxs-lookup"><span data-stu-id="33441-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="33441-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="33441-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="33441-105">Microsoft 365 使用 Azure Active Directory (Azure AD) 管理场景背后的用户身份。</span><span class="sxs-lookup"><span data-stu-id="33441-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="33441-106">Microsoft 365 订阅包括免费的 Azure AD 订阅，以便您可以将内部部署 Active Directory 域服务集成 (AD DS) ，以同步用户帐户和密码或设置单一登录。</span><span class="sxs-lookup"><span data-stu-id="33441-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="33441-107">您还可以购买高级功能，以便更好地管理帐户。</span><span class="sxs-lookup"><span data-stu-id="33441-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="33441-108">Azure AD 还提供其他功能，如管理集成的应用程序，可用于扩展和自定义 Microsoft 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="33441-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="33441-109">您可以使用 Azure AD 部署顾问在 Microsoft 365 管理中心中进行引导式设置和配置体验 (您必须登录到 Microsoft 365) ：</span><span class="sxs-lookup"><span data-stu-id="33441-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="33441-110">Azure AD Connect advisor</span><span class="sxs-lookup"><span data-stu-id="33441-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="33441-111">AD FS 部署顾问</span><span class="sxs-lookup"><span data-stu-id="33441-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="33441-112">Azure AD 安装指南</span><span class="sxs-lookup"><span data-stu-id="33441-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="33441-113">Azure AD 版本和 Microsoft 365 身份管理</span><span class="sxs-lookup"><span data-stu-id="33441-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="33441-114">如果你已付费订阅 Microsoft 365，你也会拥有免费的 Azure AD 订阅。</span><span class="sxs-lookup"><span data-stu-id="33441-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="33441-115">您可以使用 Azure AD 创建和管理用户和组帐户。</span><span class="sxs-lookup"><span data-stu-id="33441-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="33441-116">若要激活此订阅，您必须完成一次性注册。</span><span class="sxs-lookup"><span data-stu-id="33441-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="33441-117">之后，你可以从 Microsoft 365 管理中心访问 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="33441-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="33441-118">有关注册免费 Azure AD 订阅的说明，请参阅 [使用免费的 AZURE ad 订阅](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="33441-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="33441-119">请勿直接转到 azure.microsoft.com 进行注册，否则你将结束与 microsoft Azure 的试用版或付费订阅（与 Microsoft 365 的免费 Azure AD 订阅分开）。</span><span class="sxs-lookup"><span data-stu-id="33441-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="33441-120">使用免费订阅，可以与本地目录同步，设置单一登录，并与服务应用程序（如 Salesforce、DropBox 等）进行同步，并将其与许多软件同步。</span><span class="sxs-lookup"><span data-stu-id="33441-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="33441-121">如果需要增强的 AD DS 功能、双向同步和其他管理功能，可以将免费订阅升级到付费的高级订阅。</span><span class="sxs-lookup"><span data-stu-id="33441-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="33441-122">有关详细信息，请参阅 [Azure Active Directory 版本](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="33441-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="33441-123">有关 Microsoft 365 和 Azure AD 的详细信息，请参阅 [microsoft 365 标识模型](about-microsoft-365-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="33441-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="33441-124">扩展 Microsoft 365 租户的功能</span><span class="sxs-lookup"><span data-stu-id="33441-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="33441-125">**功能**</span><span class="sxs-lookup"><span data-stu-id="33441-125">**Feature**</span></span>|<span data-ttu-id="33441-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="33441-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="33441-127">集成应用程序</span><span class="sxs-lookup"><span data-stu-id="33441-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="33441-128">您可以向各个应用授予对您的 Microsoft 365 数据（如邮件、日历、联系人、用户、组、文件和文件夹）的访问权限。</span><span class="sxs-lookup"><span data-stu-id="33441-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="33441-129">你还可以在全局管理员级别授权这些应用，并通过在 Azure AD 中注册应用，使其对你的整个公司可用。</span><span class="sxs-lookup"><span data-stu-id="33441-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="33441-130">Formore 信息，请参阅 [适用于 Microsoft 365 管理员的集成应用和 AZURE AD](integrated-apps-and-azure-ads.md)。</span><span class="sxs-lookup"><span data-stu-id="33441-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="33441-131">另请参阅 [单一登录](https://go.microsoft.com/fwlink/p/?LinkId=698604)。</span><span class="sxs-lookup"><span data-stu-id="33441-131">Also see [Single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="33441-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="33441-132">PowerApps</span></span>  <br/> | <span data-ttu-id="33441-133">Power apps 是可连接到现有数据源（如 SharePoint 列表和其他数据应用程序）的移动设备的重点应用程序。</span><span class="sxs-lookup"><span data-stu-id="33441-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="33441-134">有关详细信息，请参阅 [Create a PowerApp for a list In SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) 和 [PowerApps 页](https://powerapps.microsoft.com/) 。</span><span class="sxs-lookup"><span data-stu-id="33441-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="33441-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33441-135">See also</span></span>

[<span data-ttu-id="33441-136">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="33441-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
