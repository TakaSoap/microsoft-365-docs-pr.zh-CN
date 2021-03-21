---
title: 为 Microsoft 365 设置目录同步
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: 了解如何在 Microsoft 365 和本地 Active Directory 之间设置目录同步。
ms.openlocfilehash: 51cf52bd81004157606c884fd4f0b5d3604b877a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924900"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="1c2f1-103">为 Microsoft 365 设置目录同步</span><span class="sxs-lookup"><span data-stu-id="1c2f1-103">Set up directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="1c2f1-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="1c2f1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1c2f1-105">Microsoft 365 使用 Azure (Azure AD) 租户存储和管理身份验证标识以及访问基于云的资源的权限。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-105">Microsoft 365 uses an Azure Active Directory (Azure AD) tenant to store and manage identities for authentication and permissions to access cloud-based resources.</span></span> 

<span data-ttu-id="1c2f1-106">如果你有本地 Active Directory 域服务 (AD DS) 域或林，可以将 AD DS 用户帐户、组和联系人与 Microsoft 365 订阅的 Azure AD 租户同步。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-106">If you have an on-premises Active Directory Domain Services (AD DS) domain or forest, you can synchronize your AD DS user accounts, groups, and contacts with the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="1c2f1-107">这是 Microsoft 365 的混合标识。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-107">This is hybrid identity for Microsoft 365.</span></span> <span data-ttu-id="1c2f1-108">下面是其组件。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-108">Here are its components.</span></span>

![Microsoft 365 的目录同步组件](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="1c2f1-110">Azure AD Connect 在本地服务器上运行，将 AD DS 与 Azure AD 租户同步。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-110">Azure AD Connect runs on an on-premises server and synchronizes your AD DS with the Azure AD tenant.</span></span> <span data-ttu-id="1c2f1-111">除了目录同步，还可以指定以下身份验证选项：</span><span class="sxs-lookup"><span data-stu-id="1c2f1-111">Along with directory synchronization, you can also specify these authentication options:</span></span>

- <span data-ttu-id="1c2f1-112">PHS (密码哈希) </span><span class="sxs-lookup"><span data-stu-id="1c2f1-112">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="1c2f1-113">Azure AD 执行身份验证本身。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-113">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="1c2f1-114">直通身份验证 (PTA)</span><span class="sxs-lookup"><span data-stu-id="1c2f1-114">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="1c2f1-115">Azure AD 具有 AD DS 来执行身份验证。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-115">Azure AD has AD DS perform the authentication.</span></span>

- <span data-ttu-id="1c2f1-116">联合身份验证</span><span class="sxs-lookup"><span data-stu-id="1c2f1-116">Federated authentication</span></span>

  <span data-ttu-id="1c2f1-117">Azure AD 指向另一个标识提供程序请求身份验证的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-117">Azure AD refers the client computer requesting authentication to another identity provider.</span></span>

<span data-ttu-id="1c2f1-118">有关详细信息 [，请参阅](plan-for-directory-synchronization.md) 混合标识。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-118">See [Hybrid identities](plan-for-directory-synchronization.md) for more information.</span></span>
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a><span data-ttu-id="1c2f1-119">1. 查看 Azure AD Connect 的先决条件</span><span class="sxs-lookup"><span data-stu-id="1c2f1-119">1. Review prerequisites for Azure AD Connect</span></span>

<span data-ttu-id="1c2f1-120">通过 Microsoft 365 订阅，可获取免费的 Azure AD 订阅。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-120">You get a free Azure AD subscription with your Microsoft 365 subscription.</span></span> <span data-ttu-id="1c2f1-121">设置目录同步时，将在其中一台本地服务器上安装 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-121">When you set up directory synchronization, you will install Azure AD Connect on one of your on-premises servers.</span></span>
  
<span data-ttu-id="1c2f1-122">对于 Microsoft 365，你需要：</span><span class="sxs-lookup"><span data-stu-id="1c2f1-122">For Microsoft 365 you'll need to:</span></span>
  
- <span data-ttu-id="1c2f1-123">验证本地域。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-123">Verify your on-premises domain.</span></span> <span data-ttu-id="1c2f1-124">Azure AD Connect 向导将指导你完成此操作。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-124">The Azure AD Connect wizard guides you through this.</span></span>
- <span data-ttu-id="1c2f1-125">获取 Microsoft 365 租户和 AD DS 管理员帐户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-125">Obtain the user names and passwords for the admin accounts of your Microsoft 365 tenant and AD DS.</span></span>

<span data-ttu-id="1c2f1-126">对于安装 Azure AD Connect 本地服务器，需要：</span><span class="sxs-lookup"><span data-stu-id="1c2f1-126">For your on-premises server on which you install Azure AD Connect, you'll need:</span></span>
  
|<span data-ttu-id="1c2f1-127">**服务器操作系统**</span><span class="sxs-lookup"><span data-stu-id="1c2f1-127">**Server OS**</span></span>|<span data-ttu-id="1c2f1-128">**其他软件**</span><span class="sxs-lookup"><span data-stu-id="1c2f1-128">**Other software**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1c2f1-129">Windows Server 2012 R2 及更高版本</span><span class="sxs-lookup"><span data-stu-id="1c2f1-129">Windows Server 2012 R2 and later</span></span> | <span data-ttu-id="1c2f1-130">- 默认情况下安装 PowerShell，无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-130">- PowerShell is installed by default, no action is required.</span></span>  <br> <span data-ttu-id="1c2f1-131">- 通过 Windows 更新提供 Net 4.5.1 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-131">- Net 4.5.1 and later releases are offered through Windows Update.</span></span> <span data-ttu-id="1c2f1-132">确保在控制面板中安装了 Windows Server 的最新更新。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-132">Make sure you have installed the latest updates to Windows Server in the Control Panel.</span></span> |
|<span data-ttu-id="1c2f1-133">Windows Server 2008 R2 Service Pack 1 (SP1) \*\* 或 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="1c2f1-133">Windows Server 2008 R2 with Service Pack 1 (SP1)\*\* or Windows Server 2012</span></span> | <span data-ttu-id="1c2f1-134">- 最新版本的 PowerShell 在 Windows 管理框架 4.0 中可用。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-134">- The latest version of PowerShell is available in Windows Management Framework 4.0.</span></span> <span data-ttu-id="1c2f1-135">在 Microsoft 下载中心 [中搜索它](https://go.microsoft.com/fwlink/p/?LinkId=717996)。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-135">Search for it on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="1c2f1-136">- .Net 4.5.1 及更高版本在 [Microsoft 下载中心提供](https://go.microsoft.com/fwlink/p/?LinkId=717996)。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-136">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |
|<span data-ttu-id="1c2f1-137">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="1c2f1-137">Windows Server 2008</span></span> | <span data-ttu-id="1c2f1-138">- 最新支持的 PowerShell 版本在 Windows 管理框架 3.0 中提供，可在 [Microsoft 下载中心获取](https://go.microsoft.com/fwlink/p/?LinkId=717996)。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-138">- The latest supported version of PowerShell is available in Windows Management Framework 3.0, available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="1c2f1-139">- .Net 4.5.1 及更高版本在 [Microsoft 下载中心提供](https://go.microsoft.com/fwlink/p/?LinkId=717996)。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-139">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |

<span data-ttu-id="1c2f1-140">有关 Azure AD Connect 的硬件、软件、帐户和权限要求、SSL 证书要求和对象限制的详细信息，请参阅 Prerequisites for Azure [Active Directory](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) Connect。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-140">See [Prerequisites for Azure Active Directory Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) for the details of hardware, software, account and permissions requirements, SSL certificate requirements, and object limits for Azure AD Connect.</span></span>
  
<span data-ttu-id="1c2f1-141">还可以查看 Azure AD [Connect](/azure/active-directory/hybrid/reference-connect-version-history) 版本版本历史记录，以查看每个版本中包含和修复了哪些内容。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-141">You can also review the Azure AD Connect [version release history](/azure/active-directory/hybrid/reference-connect-version-history) to see what is included and fixed in each release.</span></span>

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a><span data-ttu-id="1c2f1-142">2. 安装 Azure AD Connect 并配置目录同步</span><span class="sxs-lookup"><span data-stu-id="1c2f1-142">2. Install Azure AD Connect and configure directory synchronization</span></span>

<span data-ttu-id="1c2f1-143">在开始之前，请确保你已：</span><span class="sxs-lookup"><span data-stu-id="1c2f1-143">Before you begin, make sure you have:</span></span>

- <span data-ttu-id="1c2f1-144">Microsoft 365 全局管理员的用户名和密码</span><span class="sxs-lookup"><span data-stu-id="1c2f1-144">The user name and password of a Microsoft 365 global admin</span></span>
- <span data-ttu-id="1c2f1-145">AD DS 域管理员的用户名和密码</span><span class="sxs-lookup"><span data-stu-id="1c2f1-145">The user name and password of an AD DS domain administrator</span></span>
- <span data-ttu-id="1c2f1-146">哪一种身份验证 (PHS、PTA、联合身份验证) </span><span class="sxs-lookup"><span data-stu-id="1c2f1-146">Which authentication method (PHS, PTA, federated)</span></span>
- <span data-ttu-id="1c2f1-147">是否要将 Azure [AD 无缝单一登录 (SSO) ](/azure/active-directory/hybrid/how-to-connect-sso)</span><span class="sxs-lookup"><span data-stu-id="1c2f1-147">Whether you want to use [Azure AD Seamless Single Sign-on (SSO)](/azure/active-directory/hybrid/how-to-connect-sso)</span></span>

<span data-ttu-id="1c2f1-148">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="1c2f1-148">Follow these steps:</span></span>

1. <span data-ttu-id="1c2f1-149">登录到 Microsoft [365](https://admin.microsoft.com)管理中心 (左侧导航栏中选择"用户 https://admin.microsoft.com)  \> **""** 活动用户"。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-149">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) (https://admin.microsoft.com) and choose **Users** \> **Active Users** on the left navigation.</span></span>
2. <span data-ttu-id="1c2f1-150">在"**活动用户**"页面上， (三个点) \> **目录同步"。**</span><span class="sxs-lookup"><span data-stu-id="1c2f1-150">On the **Active users** page, choose **More** (three dots) \> **Directory synchronization**.</span></span>
  
3. <span data-ttu-id="1c2f1-151">在 **Azure Active Directory** 准备页面上，选择转到下载中心，获取 **Azure AD Connect** 工具链接以开始使用。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-151">On the **Azure Active Directory preparation** page, select the **Go to the Download center to get the Azure AD Connect tool** link to get started.</span></span> 
4. <span data-ttu-id="1c2f1-152">按照 Azure [AD Connect 和 Azure AD Connect Health 安装路线图 中的步骤操作](/azure/active-directory/hybrid/how-to-connect-install-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-152">Follow the steps in [Azure AD Connect and Azure AD Connect Health installation roadmap](/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span></span>

## <a name="3-finish-setting-up-domains"></a><span data-ttu-id="1c2f1-153">3. 完成域设置</span><span class="sxs-lookup"><span data-stu-id="1c2f1-153">3. Finish setting up domains</span></span>

<span data-ttu-id="1c2f1-154">按照管理 DNS 记录时为 [Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) 创建 DNS 记录中的步骤完成域设置。</span><span class="sxs-lookup"><span data-stu-id="1c2f1-154">Follow the steps in [Create DNS records for Microsoft 365 when you manage your DNS records](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) to finish setting up your domains.</span></span>

## <a name="next-step"></a><span data-ttu-id="1c2f1-155">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1c2f1-155">Next step</span></span>

[<span data-ttu-id="1c2f1-156">向用户帐户分配许可证</span><span class="sxs-lookup"><span data-stu-id="1c2f1-156">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)