---
title: 设置概述
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 了解 Microsoft 365 商业高级版（从订阅到添加域和用户、设置安全策略等）的设置步骤。
ms.openlocfilehash: 749acbfdbde92ad97b09dc720c85dd850b76c9cf
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579926"
---
# <a name="overview-of-setup"></a><span data-ttu-id="d4a99-103">设置概述</span><span class="sxs-lookup"><span data-stu-id="d4a99-103">Overview of setup</span></span>

<span data-ttu-id="d4a99-104">观看有关 Microsoft 365 商业高级版设置的简短视频。</span><span class="sxs-lookup"><span data-stu-id="d4a99-104">Watch a short video about Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

<span data-ttu-id="d4a99-105">如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="d4a99-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

<span data-ttu-id="d4a99-106">大多数设置步骤都可以在引导式设置中完成，但还会列出其他选项。</span><span class="sxs-lookup"><span data-stu-id="d4a99-106">Most of the setup steps can be done in the guided setup, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="d4a99-107">步骤 1：添加域和用户</span><span class="sxs-lookup"><span data-stu-id="d4a99-107">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="d4a99-108">**[如果在注册](set-up.md#add-your-domain-to-personalize-sign-in)** (购买了域，请添加域策略，此步骤 [](sign-up.md)已完成。) </span><span class="sxs-lookup"><span data-stu-id="d4a99-108">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

   - <span data-ttu-id="d4a99-109">**添加用户**。</span><span class="sxs-lookup"><span data-stu-id="d4a99-109">**Add users**.</span></span> <span data-ttu-id="d4a99-110">您可以通过以下三种方法之一添加用户：</span><span class="sxs-lookup"><span data-stu-id="d4a99-110">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="d4a99-111">在引导 [式设置中](set-up.md#add-users-in-the-wizard)。</span><span class="sxs-lookup"><span data-stu-id="d4a99-111">In the [guided setup](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="d4a99-112">如果你有本地 Active Directory，请使用目录同步通过 [Azure AD Connect](../enterprise/set-up-directory-synchronization.md) 添加用户。</span><span class="sxs-lookup"><span data-stu-id="d4a99-112">Use directory synchronization to [add users by using Azure AD Connect](../enterprise/set-up-directory-synchronization.md) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="d4a99-113">还可以稍后 [在管理中心](../admin/add-users/add-users.md) 中添加用户。</span><span class="sxs-lookup"><span data-stu-id="d4a99-113">You can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="d4a99-114">步骤 2：设置安全策略和配置设备</span><span class="sxs-lookup"><span data-stu-id="d4a99-114">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="d4a99-115">使用 [引导式设置](set-up.md#protect-your-organization) 配置设备策略。</span><span class="sxs-lookup"><span data-stu-id="d4a99-115">Use the [guided setup](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="d4a99-116">还可以在管理中心和 Intune 门户中稍后[](view-policies-and-devices.md)添加更多或[编辑它们](/intune/tutorial-walkthrough-intune-portal)。</span><span class="sxs-lookup"><span data-stu-id="d4a99-116">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="d4a99-117">安装向导还将设置基本威胁防护和数据丢失防护设置。</span><span class="sxs-lookup"><span data-stu-id="d4a99-117">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="d4a99-118">除了安装向导中的安全设置之外，您还可以通过添加以下设置来增强安全性：</span><span class="sxs-lookup"><span data-stu-id="d4a99-118">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

- <span data-ttu-id="d4a99-119">**电子邮件恶意软件保护**</span><span class="sxs-lookup"><span data-stu-id="d4a99-119">**Email malware protection**</span></span>
- <span data-ttu-id="d4a99-120">**Office 365 Defender 中的防钓鱼**</span><span class="sxs-lookup"><span data-stu-id="d4a99-120">**Anti-phishing in Defender for Office 365**</span></span>
- <span data-ttu-id="d4a99-121">**Exchange Online Archiving**</span><span class="sxs-lookup"><span data-stu-id="d4a99-121">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="d4a99-122">**Azure 信息保护 (计划 1**) </span><span class="sxs-lookup"><span data-stu-id="d4a99-122">**Azure Information Protection (Plan1**)</span></span>

<span data-ttu-id="d4a99-123">若要开始，请参阅[增加威胁防护](increase-threat-protection.md)[和设置合规性功能](set-up-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="d4a99-123">To get started, see [increase threat protection](increase-threat-protection.md) and [set up compliance features](set-up-compliance.md).</span></span>

<span data-ttu-id="d4a99-124">另请参阅 [保护 Microsoft 365](/office365/admin/security-and-compliance/secure-your-business-data) 商业高级版前 10 种方法，了解最佳安全做法路线图。</span><span class="sxs-lookup"><span data-stu-id="d4a99-124">See also [top 10 ways to secure your Microsoft 365 Business Premium](/office365/admin/security-and-compliance/secure-your-business-data) for a road-map of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="d4a99-125">步骤 3：设置和管理 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="d4a99-125">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="d4a99-126">完成引导式设置后，你将希望保护组织的所有 Windows 10 计算机。</span><span class="sxs-lookup"><span data-stu-id="d4a99-126">After you complete the guided setup, you will want to protect all the Windows 10 computers in your organization.</span></span>
  
- <span data-ttu-id="d4a99-127">Windows 10 专业[](pre-requisites-for-data-protection.md)版是 Microsoft 365 商业高级版的先决条件，但如果你拥有 Windows 7 专业版、Windows 8 专业版 或 Windows 8.1 专业版，你的订阅将授权你升级到[Windows 10 专业版](./upgrade-to-windows-pro-creators-update.md)。</span><span class="sxs-lookup"><span data-stu-id="d4a99-127">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business Premium, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](./upgrade-to-windows-pro-creators-update.md).</span></span>
- <span data-ttu-id="d4a99-128">按照安全 [Windows 10 电脑](secure-win-10-pcs.md) 中的步骤为 Windows 10 设备设置策略。</span><span class="sxs-lookup"><span data-stu-id="d4a99-128">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="d4a99-129">将 Windows 10 设备加入 Azure AD 时，你为 Windows 10 计算机设置的策略将应用于该设备。</span><span class="sxs-lookup"><span data-stu-id="d4a99-129">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="d4a99-130">有关详细信息，请参阅为 [Microsoft 365 用户设置 Windows 设备](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="d4a99-130">For more information, see [Set up Windows devices for Microsoft 365 users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-microsoft-365-apps-for-business"></a><span data-ttu-id="d4a99-131">步骤 4：安装 Microsoft 365 商业应用版</span><span class="sxs-lookup"><span data-stu-id="d4a99-131">Step 4: Install Microsoft 365 Apps for business</span></span>
- <span data-ttu-id="d4a99-132">可以使用安装向导在 Windows 设备中自动[安装 Office。](set-up.md#deploy-office-365-client-apps)</span><span class="sxs-lookup"><span data-stu-id="d4a99-132">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="d4a99-133">让用户 [安装适用于](/office365/admin/setup/install-applications) Windows 和设备的 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="d4a99-133">Let users [install Office apps](/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="d4a99-134">高级</span><span class="sxs-lookup"><span data-stu-id="d4a99-134">Advanced</span></span>
- <span data-ttu-id="d4a99-135">**使用 Autopilot 设置新设备**</span><span class="sxs-lookup"><span data-stu-id="d4a99-135">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="d4a99-136">可以使用 [Windows Autopilot](add-autopilot-devices-and-profile.md)为用户自动预配置新的 **Windows** 10 设备，但可能更易于获取可为此操作的合作伙伴 [](https://www.microsoft.com/solution-providers/search)。</span><span class="sxs-lookup"><span data-stu-id="d4a99-136">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="d4a99-137">还可以转到 Microsoft [Store，](https://go.microsoft.com/fwlink/?linkid=874598)让云技术专家设置你购买的新设备。</span><span class="sxs-lookup"><span data-stu-id="d4a99-137">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="d4a99-138">**访问本地资源**</span><span class="sxs-lookup"><span data-stu-id="d4a99-138">**Access on-premises resources**</span></span>

     - <span data-ttu-id="d4a99-139">如果你的组织使用本地 Windows Server Active Directory，你可以设置 Microsoft 365 商业高级版来保护你的 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d4a99-139">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="d4a99-140">请按照允许 [Microsoft 365](manage-windows-devices.md) 商业高级版管理已加入域的 Windows 10 设备中的步骤进行设置。</span><span class="sxs-lookup"><span data-stu-id="d4a99-140">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="d4a99-141">这是首选方法，并且此状态中的设备称为加入混合 Azure AD 的设备。</span><span class="sxs-lookup"><span data-stu-id="d4a99-141">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="d4a99-142">如果你的企业有一个本地 Active Directory，其中包含一些本地资源 (例如文件共享和打印机) ，你可以按照以下步骤为加入 Azure AD 的设备提供对这些资源的访问权限：在 [Microsoft 365](access-resources.md)商业高级版 中从加入 Azure AD 的设备访问本地资源。</span><span class="sxs-lookup"><span data-stu-id="d4a99-142">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium](access-resources.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d4a99-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4a99-143">See also</span></span>

[<span data-ttu-id="d4a99-144">Microsoft 365 商业版培训视频</span><span class="sxs-lookup"><span data-stu-id="d4a99-144">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)