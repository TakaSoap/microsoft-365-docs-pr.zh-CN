---
title: 在 Microsoft 365 中查看目录同步状态
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: 在本文中，您将了解如何在 Office 365 中检查目录同步的状态。
ms.openlocfilehash: 7577ed358a262d5b0ef2932bc73cf61941bec31b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326945"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="0c8f8-103">在 Microsoft 365 中查看目录同步状态</span><span class="sxs-lookup"><span data-stu-id="0c8f8-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="0c8f8-104">如果已将本地 Active Directory 域服务集成 (AD DS) Azure Active Directory (Azure AD) 通过将本地环境与 Microsoft 365 同步，您还可以检查同步的状态。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="0c8f8-105">查看目录同步状态</span><span class="sxs-lookup"><span data-stu-id="0c8f8-105">View directory synchronization status</span></span>

- <span data-ttu-id="0c8f8-106">登录到 [Microsoft 365 管理中心](https://admin.microsoft.com) ，并在主页上选择 " **DirSync Status** "。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="0c8f8-107">或者，您可以转到 **用户** \> **活动用户**，并在 " **活动用户** " 页上选择 " **更多** \> **目录同步**"。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="0c8f8-108">在 " **目录同步** " 窗格中，选择 " **转到 DirSync management**"。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="0c8f8-109">"管理目录同步" 页上的信息</span><span class="sxs-lookup"><span data-stu-id="0c8f8-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="0c8f8-110">下表列出了可以在页面上获取相关信息的功能。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="0c8f8-111">如果目录同步存在问题，则还会在此页面上列出这些错误。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="0c8f8-112">有关可能遇到的不同错误的详细信息，请参阅 [确定 Microsoft 365 中的目录同步错误](identify-directory-synchronization-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="0c8f8-113">Item</span><span class="sxs-lookup"><span data-stu-id="0c8f8-113">Item</span></span>|<span data-ttu-id="0c8f8-114">它有何用途？</span><span class="sxs-lookup"><span data-stu-id="0c8f8-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="0c8f8-115">**已验证域**</span><span class="sxs-lookup"><span data-stu-id="0c8f8-115">**Domains verified**</span></span> | <span data-ttu-id="0c8f8-116">你已验证的 Microsoft 365 租户中的域的数量。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="0c8f8-117">**未验证域**</span><span class="sxs-lookup"><span data-stu-id="0c8f8-117">**Domains not verified**</span></span> | <span data-ttu-id="0c8f8-118">已添加但未验证的域。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="0c8f8-119">**目录同步已启用**</span><span class="sxs-lookup"><span data-stu-id="0c8f8-119">**Directory sync enabled**</span></span> |<span data-ttu-id="0c8f8-120">True 或 False。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-120">True or False.</span></span> <span data-ttu-id="0c8f8-121">指定是否已启用目录同步。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="0c8f8-122">**最新目录同步**</span><span class="sxs-lookup"><span data-stu-id="0c8f8-122">**Latest directory sync**</span></span> | <span data-ttu-id="0c8f8-123">上次运行目录同步的时间。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-123">Last time directory sync ran.</span></span> <span data-ttu-id="0c8f8-124">如果上一次同步的时间已超过三天，将显示一条警告和指向故障排除工具的链接。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="0c8f8-125">**启用密码同步**</span><span class="sxs-lookup"><span data-stu-id="0c8f8-125">**Password sync enabled**</span></span> | <span data-ttu-id="0c8f8-126">True 或 False。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-126">True or False.</span></span> <span data-ttu-id="0c8f8-127">指定在内部部署和 Microsoft 365 租户之间是否有密码哈希同步。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="0c8f8-128">**上次密码同步**</span><span class="sxs-lookup"><span data-stu-id="0c8f8-128">**Last Password Sync**</span></span> | <span data-ttu-id="0c8f8-129">上次运行密码哈希同步的时间。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-129">Last time password hash sync ran.</span></span> <span data-ttu-id="0c8f8-130">如果上一次同步的时间已超过三天，将显示一条警告和指向故障排除工具的链接。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="0c8f8-131">**目录同步客户端版本**</span><span class="sxs-lookup"><span data-stu-id="0c8f8-131">**Directory sync client version**</span></span> | <span data-ttu-id="0c8f8-132">如果已发布新版本的 Azure AD Connect，则包含下载链接。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="0c8f8-133">**目录同步服务帐户**</span><span class="sxs-lookup"><span data-stu-id="0c8f8-133">**Directory sync service account**</span></span> | <span data-ttu-id="0c8f8-134">显示 Microsoft 365 目录同步服务帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="0c8f8-135">监控同步运行状况</span><span class="sxs-lookup"><span data-stu-id="0c8f8-135">Monitor synchronization health</span></span>

<span data-ttu-id="0c8f8-136">在此部分中，将在每个本地 AD DS 域控制器上安装 Azure AD Connect Health 代理，以监控由 Azure AD Connect 提供的标识基础架构和同步服务。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="0c8f8-137">Azure AD Connect Health 门户提供了监控信息，可以从中查看警报、性能监控、使用情况分析和其他信息。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="0c8f8-138">如何使用 Azure AD Connect Health 的关键设计决策是基于使用 Azure AD Connect 的方式：</span><span class="sxs-lookup"><span data-stu-id="0c8f8-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="0c8f8-139">如果你使用的是\*\*\*\*“托管身份验证”选项，请从[使用用于同步的 Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) 开始，以理解并配置 Azure AD Connect Health。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="0c8f8-140">如果仅使用\*\*\*\*“联合身份验证”将帐户和组的名称与 Active Directory 联合身份验证服务 (AD FS) 同步，请从[在 AD FS 中使用 Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) 开始，以理解并配置 Azure AD Connect Health。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="0c8f8-141">完成后，你将拥有：</span><span class="sxs-lookup"><span data-stu-id="0c8f8-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="0c8f8-142">在本地标识提供者服务器上安装的 Azure AD Connect Health 代理。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="0c8f8-143">显示本地基础结构的当前状态，以及与 Microsoft 365 订阅的 Azure AD 租户同步活动的 Azure AD Connect Health 门户。</span><span class="sxs-lookup"><span data-stu-id="0c8f8-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>

