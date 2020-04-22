---
title: 设置概述
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 了解 Microsoft 365 商业高级版的安装步骤、订阅、添加域和用户、设置安全策略等。
ms.openlocfilehash: 8b26d423d4f62ee8f9ea4a61eb8f7efa72ee26cb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633347"
---
# <a name="overview-of-setup"></a><span data-ttu-id="a2ae7-103">设置概述</span><span class="sxs-lookup"><span data-stu-id="a2ae7-103">Overview of setup</span></span>

<span data-ttu-id="a2ae7-104">观看有关 Microsoft 365 商业高级版安装程序的简短视频。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-104">Watch a short video about Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

<span data-ttu-id="a2ae7-105">如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

<span data-ttu-id="a2ae7-106">大部分安装步骤可以在安装向导中完成，但也会列出其他选项。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-106">Most of the setup steps can be done in the setup wizard, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="a2ae7-107">步骤1：添加您的域和用户</span><span class="sxs-lookup"><span data-stu-id="a2ae7-107">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="a2ae7-108">**[添加你的域](set-up.md#add-your-domain-to-personalize-sign-in)**（如果你在[注册](sign-up.md)过程中购买了你的域，则此步骤已完成。）</span><span class="sxs-lookup"><span data-stu-id="a2ae7-108">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="a2ae7-109">**添加用户**。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-109">**Add users**.</span></span> <span data-ttu-id="a2ae7-110">可以通过以下三种方式之一添加用户：</span><span class="sxs-lookup"><span data-stu-id="a2ae7-110">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="a2ae7-111">在[向导](set-up.md#add-users-in-the-wizard)中。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-111">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="a2ae7-112">如果你有本地 Active directory，请使用目录同步来[使用 AZURE AD Connect 添加用户](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-112">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="a2ae7-113">您还可以在随后的管理中心[添加用户](add-users-m365b.md)。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="a2ae7-114">步骤2：设置安全策略和配置设备</span><span class="sxs-lookup"><span data-stu-id="a2ae7-114">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="a2ae7-115">使用[安装向导](set-up.md#protect-your-organization)配置设备策略。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-115">Use the [Setup wizard](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="a2ae7-116">您还可以在[管理员中心](view-policies-and-devices.md)和[Intune 门户](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)中添加更多或编辑它们。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-116">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="a2ae7-117">安装向导还会设置基本威胁防护和数据丢失防护设置。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-117">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="a2ae7-118">除了安装向导中的安全设置之外，还可以通过添加以下设置来提高安全性：</span><span class="sxs-lookup"><span data-stu-id="a2ae7-118">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

- <span data-ttu-id="a2ae7-119">**电子邮件恶意软件保护**</span><span class="sxs-lookup"><span data-stu-id="a2ae7-119">**Email malware protection**</span></span>
- <span data-ttu-id="a2ae7-120">**ATP 反网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="a2ae7-120">**ATP anti-phishing**</span></span>
- <span data-ttu-id="a2ae7-121">**Exchange Online Archiving**</span><span class="sxs-lookup"><span data-stu-id="a2ae7-121">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="a2ae7-122">**Azure 信息保护（Plan1**）</span><span class="sxs-lookup"><span data-stu-id="a2ae7-122">**Azure Information Protection (Plan1**)</span></span>

<span data-ttu-id="a2ae7-123">若要开始，请参阅[增加威胁防护](increase-threat-protection.md)和[设置合规性功能](set-up-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-123">To get started, see [increase threat protection](increase-threat-protection.md) and [set up compliance features](set-up-compliance.md).</span></span>

<span data-ttu-id="a2ae7-124">请参阅[保护 Microsoft 365 商业高级版](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)的十大方法，了解最佳安全实践的路线图。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-124">See also [top 10 ways to secure your Microsoft 365 Business Premium](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="a2ae7-125">步骤3：设置和管理 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="a2ae7-125">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="a2ae7-126">运行设置向导后，您需要 proctect 组织中的所有 Windwos 10 台计算机。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-126">After you run the set up wizard, you will want to proctect all the Windwos 10 computers in your organization.</span></span>
  
- <span data-ttu-id="a2ae7-127">Windows 10 专业版是 Microsoft 365 商业高级版的[先决条件](pre-requisites-for-data-protection.md)，但如果你有 Windows 7 Pro、Windows 8 专业版或 Windows 8.1 pro，你的订阅让你能够[升级到 Windows 10 专业](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)版。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-127">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business Premium, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
- <span data-ttu-id="a2ae7-128">按照[安全 windows 10 电脑](secure-win-10-pcs.md)中的步骤设置 windows 10 设备的策略。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-128">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="a2ae7-129">将 Windows 10 设备加入 Azure AD 时，您为 Windows 10 计算机设置的策略将应用于。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-129">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="a2ae7-130">有关详细信息，请参阅[设置 Windows 设备 For Microsoft 365 users](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-130">For more information, see [Set up Windows devices for Microsoft 365 users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-microsoft-365-apps-for-business"></a><span data-ttu-id="a2ae7-131">步骤4：安装 Microsoft 365 的商业应用程序</span><span class="sxs-lookup"><span data-stu-id="a2ae7-131">Step 4: Install Microsoft 365 Apps for business</span></span>
- <span data-ttu-id="a2ae7-132">您可以使用[安装向导](set-up.md#deploy-office-365-client-apps)在 Windows 设备中自动安装 Office。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-132">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="a2ae7-133">允许用户安装适用于 Windows 和设备的[Office 应用程序](https://docs.microsoft.com/office365/admin/setup/install-applications)。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-133">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="a2ae7-134">高级</span><span class="sxs-lookup"><span data-stu-id="a2ae7-134">Advanced</span></span>
- <span data-ttu-id="a2ae7-135">**使用 Autopilot 设置新设备**</span><span class="sxs-lookup"><span data-stu-id="a2ae7-135">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="a2ae7-136">可以使用[Windows Autopilot](add-autopilot-devices-and-profile.md)为用户自动预配置**新**的 Windows 10 设备，但更易于获取可为您执行此操作的[合作伙伴](https://www.microsoft.com/solution-providers/search)。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-136">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="a2ae7-137">你也可以转到[Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)，并请求云技术专家设置你购买的新设备。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-137">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="a2ae7-138">**访问本地资源**</span><span class="sxs-lookup"><span data-stu-id="a2ae7-138">**Access on-premises resources**</span></span>

     - <span data-ttu-id="a2ae7-139">如果您的组织使用的是本地 Windows Server Active Directory，则可以将 Microsoft 365 商业高级版设置为保护您的 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-139">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="a2ae7-140">按照[Microsoft 365 商业高级版中的 "启用加入域的 Windows 10 设备](manage-windows-devices.md)" 中的步骤进行操作，以设置此设置。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-140">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="a2ae7-141">这是首选方法，而此状态的设备称为混合 Azure AD 加入的设备。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-141">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="a2ae7-142">如果你的企业具有包含某些本地资源（如文件共享和打印机）的本地 Active Directory，则可以按照以下步骤为 Azure AD 联接的设备授予对这些资源的访问权限：[从 Microsoft 365 商业高级版中的 AZURE AD 加入设备访问本地资源](access-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="a2ae7-142">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium](access-resources.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a2ae7-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2ae7-143">See also</span></span>

[<span data-ttu-id="a2ae7-144">Microsoft 365 商业培训视频</span><span class="sxs-lookup"><span data-stu-id="a2ae7-144">Microsoft 365 for business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
