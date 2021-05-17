---
title: 查看目录中的目录Microsoft 365
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
description: 本文将了解如何在 Office 365 中检查目录同步的状态。
ms.openlocfilehash: cbaae8bbd31f6124c2b0f4984b9a625ffbde538f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924656"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="a62b4-103">查看目录中的目录Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a62b4-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="a62b4-104">如果通过将本地环境与 Microsoft 365 同步，将本地 Active Directory 域服务 (AD DS) 与 Azure Active Directory (Azure AD) 集成，则还可以检查同步的状态。</span><span class="sxs-lookup"><span data-stu-id="a62b4-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="a62b4-105">查看目录同步状态</span><span class="sxs-lookup"><span data-stu-id="a62b4-105">View directory synchronization status</span></span>

- <span data-ttu-id="a62b4-106">登录到管理中心 [Microsoft 365](https://admin.microsoft.com)主页上的 **"DirSync** 状态"。</span><span class="sxs-lookup"><span data-stu-id="a62b4-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="a62b4-107">或者，你可以转到"用户 **""** 活动用户"，在"活动用户"页面上， \> 选择"**更多** \> **目录同步"。**</span><span class="sxs-lookup"><span data-stu-id="a62b4-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="a62b4-108">在"**目录同步"窗格中**，选择 **"转到目录同步管理"。**</span><span class="sxs-lookup"><span data-stu-id="a62b4-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="a62b4-109">"管理目录同步"页上的信息</span><span class="sxs-lookup"><span data-stu-id="a62b4-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="a62b4-110">下表列出了可在页面上获取相关信息的功能。</span><span class="sxs-lookup"><span data-stu-id="a62b4-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="a62b4-111">如果您的目录同步出现问题，则此页上也列出了这些错误。</span><span class="sxs-lookup"><span data-stu-id="a62b4-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="a62b4-112">有关可能遇到的不同错误的详细信息，请参阅在 Microsoft 365[中标识目录同步Microsoft 365。](identify-directory-synchronization-errors.md)</span><span class="sxs-lookup"><span data-stu-id="a62b4-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="a62b4-113">项目</span><span class="sxs-lookup"><span data-stu-id="a62b4-113">Item</span></span>|<span data-ttu-id="a62b4-114">它有何用途？</span><span class="sxs-lookup"><span data-stu-id="a62b4-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="a62b4-115">**已验证域**</span><span class="sxs-lookup"><span data-stu-id="a62b4-115">**Domains verified**</span></span> | <span data-ttu-id="a62b4-116">已验证你拥有Microsoft 365租户中的域数。</span><span class="sxs-lookup"><span data-stu-id="a62b4-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="a62b4-117">**未验证域**</span><span class="sxs-lookup"><span data-stu-id="a62b4-117">**Domains not verified**</span></span> | <span data-ttu-id="a62b4-118">已添加但未经验证的域。</span><span class="sxs-lookup"><span data-stu-id="a62b4-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="a62b4-119">**启用目录同步**</span><span class="sxs-lookup"><span data-stu-id="a62b4-119">**Directory sync enabled**</span></span> |<span data-ttu-id="a62b4-120">TRUE 或 FALSE。</span><span class="sxs-lookup"><span data-stu-id="a62b4-120">True or False.</span></span> <span data-ttu-id="a62b4-121">指定是否已启用目录同步。</span><span class="sxs-lookup"><span data-stu-id="a62b4-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="a62b4-122">**最新目录同步**</span><span class="sxs-lookup"><span data-stu-id="a62b4-122">**Latest directory sync**</span></span> | <span data-ttu-id="a62b4-123">上次运行目录同步的时间。</span><span class="sxs-lookup"><span data-stu-id="a62b4-123">Last time directory sync ran.</span></span> <span data-ttu-id="a62b4-124">如果上次同步的时间超过三天，将显示一条警告和一个指向疑难解答工具的链接。</span><span class="sxs-lookup"><span data-stu-id="a62b4-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="a62b4-125">**启用密码同步**</span><span class="sxs-lookup"><span data-stu-id="a62b4-125">**Password sync enabled**</span></span> | <span data-ttu-id="a62b4-126">TRUE 或 FALSE。</span><span class="sxs-lookup"><span data-stu-id="a62b4-126">True or False.</span></span> <span data-ttu-id="a62b4-127">指定本地租户和本地租户之间是否Microsoft 365哈希同步。</span><span class="sxs-lookup"><span data-stu-id="a62b4-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="a62b4-128">**上次密码同步**</span><span class="sxs-lookup"><span data-stu-id="a62b4-128">**Last Password Sync**</span></span> | <span data-ttu-id="a62b4-129">上次运行密码哈希同步的时间。</span><span class="sxs-lookup"><span data-stu-id="a62b4-129">Last time password hash sync ran.</span></span> <span data-ttu-id="a62b4-130">如果上次同步的时间超过三天，将显示一条警告和一个指向疑难解答工具的链接。</span><span class="sxs-lookup"><span data-stu-id="a62b4-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="a62b4-131">**目录同步客户端版本**</span><span class="sxs-lookup"><span data-stu-id="a62b4-131">**Directory sync client version**</span></span> | <span data-ttu-id="a62b4-132">如果已发布新版本的 Azure AD 连接包含下载链接。</span><span class="sxs-lookup"><span data-stu-id="a62b4-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="a62b4-133">**目录同步服务帐户**</span><span class="sxs-lookup"><span data-stu-id="a62b4-133">**Directory sync service account**</span></span> | <span data-ttu-id="a62b4-134">显示你的目录Microsoft 365服务帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="a62b4-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="a62b4-135">监控同步运行状况</span><span class="sxs-lookup"><span data-stu-id="a62b4-135">Monitor synchronization health</span></span>

<span data-ttu-id="a62b4-136">在此部分中，将在每个本地 AD DS 域控制器上安装 Azure AD Connect Health 代理，以监控由 Azure AD Connect 提供的标识基础架构和同步服务。</span><span class="sxs-lookup"><span data-stu-id="a62b4-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="a62b4-137">Azure AD Connect Health 门户提供了监控信息，可以从中查看警报、性能监控、使用情况分析和其他信息。</span><span class="sxs-lookup"><span data-stu-id="a62b4-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="a62b4-138">如何使用 Azure AD Connect Health 的关键设计决策是基于使用 Azure AD Connect 的方式：</span><span class="sxs-lookup"><span data-stu-id="a62b4-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="a62b4-139">如果你使用的是“托管身份验证”选项，请从[使用用于同步的 Azure AD Connect Health](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) 开始，以理解并配置 Azure AD Connect Health。</span><span class="sxs-lookup"><span data-stu-id="a62b4-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="a62b4-140">如果仅使用“联合身份验证”将帐户和组的名称与 Active Directory 联合身份验证服务 (AD FS) 同步，请从[在 AD FS 中使用 Azure AD Connect Health](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) 开始，以理解并配置 Azure AD Connect Health。</span><span class="sxs-lookup"><span data-stu-id="a62b4-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="a62b4-141">完成后，你将拥有：</span><span class="sxs-lookup"><span data-stu-id="a62b4-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="a62b4-142">在本地标识提供者服务器上安装的 Azure AD Connect Health 代理。</span><span class="sxs-lookup"><span data-stu-id="a62b4-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="a62b4-143">显示本地基础结构的当前状态，以及与 Microsoft 365 订阅的 Azure AD 租户同步活动的 Azure AD Connect Health 门户。</span><span class="sxs-lookup"><span data-stu-id="a62b4-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>