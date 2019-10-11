---
title: 设置概述
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 商业版的设置步骤概述。
ms.openlocfilehash: 4be0a8aa1b050ee3e20a045eb2c07666765118ed
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2019
ms.locfileid: "37440529"
---
# <a name="overview-of-setup"></a><span data-ttu-id="78f40-103">设置概述</span><span class="sxs-lookup"><span data-stu-id="78f40-103">Overview of setup</span></span>

<span data-ttu-id="78f40-104">大部分设置步骤可以在安装向导中完成，但也会列出其他选项。</span><span class="sxs-lookup"><span data-stu-id="78f40-104">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>


## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="78f40-105">步骤1：添加您的域和用户</span><span class="sxs-lookup"><span data-stu-id="78f40-105">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="78f40-106">**[添加你的域](set-up.md#add-your-domain-to-personalize-sign-in)**（如果你在[注册](sign-up.md)过程中购买了你的域，则此步骤已完成。）</span><span class="sxs-lookup"><span data-stu-id="78f40-106">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="78f40-107">**添加用户**。</span><span class="sxs-lookup"><span data-stu-id="78f40-107">**Add users**.</span></span> <span data-ttu-id="78f40-108">可以通过以下三种方式之一执行此操作：</span><span class="sxs-lookup"><span data-stu-id="78f40-108">You can do this in any of the three ways:</span></span>
        - <span data-ttu-id="78f40-109">在[向导](set-up.md#add-users-in-the-wizard)中。</span><span class="sxs-lookup"><span data-stu-id="78f40-109">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="78f40-110">如果你有本地 Active directory，请使用目录同步来[使用 AZURE AD Connect 添加用户](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="78f40-110">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="78f40-111">您还可以在随后的管理中心[添加用户](add-users-m365b.md)。</span><span class="sxs-lookup"><span data-stu-id="78f40-111">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="78f40-112">步骤2：设置安全策略和配置设备</span><span class="sxs-lookup"><span data-stu-id="78f40-112">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="78f40-113">使用[安装向导](set-up.md#protect-data-and-devices)配置设备和安全策略。</span><span class="sxs-lookup"><span data-stu-id="78f40-113">Use the [Setup wizard](set-up.md#protect-data-and-devices) to configure device and security policies.</span></span> 
  - <span data-ttu-id="78f40-114">您还可以在[管理员中心](view-policies-and-devices.md)和[Intune 门户](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)中添加更多或编辑它们。</span><span class="sxs-lookup"><span data-stu-id="78f40-114">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="78f40-115">除了安装向导中的安全设置之外，还可以通过添加以下设置来提高安全性：</span><span class="sxs-lookup"><span data-stu-id="78f40-115">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

      - <span data-ttu-id="78f40-116">**电子邮件恶意软件保护**</span><span class="sxs-lookup"><span data-stu-id="78f40-116">**Email malware protection**</span></span>
      - <span data-ttu-id="78f40-117">**高级威胁防护（ATP）安全链接**</span><span class="sxs-lookup"><span data-stu-id="78f40-117">**Advanced Threat Protection (ATP) Safe links**</span></span>
      - <span data-ttu-id="78f40-118">**ATP 安全附件**</span><span class="sxs-lookup"><span data-stu-id="78f40-118">**ATP Safe Attachments**</span></span>
      - <span data-ttu-id="78f40-119">**ATP 反网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="78f40-119">**ATP anti-phishing**</span></span>
      - <span data-ttu-id="78f40-120">**Exchange Online Archiving**</span><span class="sxs-lookup"><span data-stu-id="78f40-120">**Exchange Online Archiving**</span></span>
      - <span data-ttu-id="78f40-121">**Data Loss Prevention (DLP)**</span><span class="sxs-lookup"><span data-stu-id="78f40-121">**Data Loss Prevention (DLP)**</span></span>
      - <span data-ttu-id="78f40-122">**Azure 信息保护（Plan1**）</span><span class="sxs-lookup"><span data-stu-id="78f40-122">**Azure Information Protection (Plan1**)</span></span>

          <span data-ttu-id="78f40-123">若要开始，请[设置高级安全策略](set-up-advanced-security.md)。</span><span class="sxs-lookup"><span data-stu-id="78f40-123">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

        <span data-ttu-id="78f40-124">请参阅[保护 Microsoft 365 业务的十大方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)，以获得最佳安全实践的路线图。</span><span class="sxs-lookup"><span data-stu-id="78f40-124">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="78f40-125">步骤3：设置和管理 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="78f40-125">Step 3: Set up and manage Windows 10 devices</span></span>

   <span data-ttu-id="78f40-126">将 Windows 10 设备加入 Azure AD 时，将在[步骤 2](#step-2-set-up-security-policies-and-configure-devices)中设置的策略应用于该 AD。</span><span class="sxs-lookup"><span data-stu-id="78f40-126">When you join a Windows 10 device to Azure AD, the policies you set up in [Step 2](#step-2-set-up-security-policies-and-configure-devices) get applied to it.</span></span>

   - <span data-ttu-id="78f40-127">Windows 10 专业版是 Microsoft 365 商业版的[先决条件](pre-requisites-for-data-protection.md)，但如果你有 Windows 7 Pro、Windows 8 专业版或 Windows 8.1 专业版，你的订阅使你能够[升级到 Windows 10 专业](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)版。</span><span class="sxs-lookup"><span data-stu-id="78f40-127">Windows 10 Pro is a [pre-requisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
    - <span data-ttu-id="78f40-128">使用[安装向导](set-up.md#protect-data-and-devices)为 Windows 10 设备配置策略。</span><span class="sxs-lookup"><span data-stu-id="78f40-128">Use the [Setup wizard](set-up.md#protect-data-and-devices) to configure policies for Windows 10 devices.</span></span>

## <a name="stes-4-install-office-365-business"></a><span data-ttu-id="78f40-129">Stes 4：安装 Office 365 商业版</span><span class="sxs-lookup"><span data-stu-id="78f40-129">Stes 4: Install Office 365 Business</span></span>
- <span data-ttu-id="78f40-130">您可以使用[安装向导](set-up.md#deploy-office-365-client-apps)在 Windows 设备中自动安装 Office。</span><span class="sxs-lookup"><span data-stu-id="78f40-130">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="78f40-131">从管理中心自动[安装 Office](auto-install-or-uninstall-office.md) 。</span><span class="sxs-lookup"><span data-stu-id="78f40-131">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
- <span data-ttu-id="78f40-132">允许用户安装适用于 Windows 和设备的[Office 应用程序](https://docs.microsoft.com/office365/admin/setup/install-applications)。</span><span class="sxs-lookup"><span data-stu-id="78f40-132">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="78f40-133">高级</span><span class="sxs-lookup"><span data-stu-id="78f40-133">Advanced</span></span>
- <span data-ttu-id="78f40-134">**使用 Autopilot 设置新设备**</span><span class="sxs-lookup"><span data-stu-id="78f40-134">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="78f40-135">可以使用[Windows Autopilot](add-autopilot-devices-and-profile.md)为用户自动预配置**新**的 Windows 10 设备，但更易于获取可为您执行此操作的[合作伙伴](https://www.microsoft.com/solution-providers/search)。</span><span class="sxs-lookup"><span data-stu-id="78f40-135">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="78f40-136">你也可以转到[Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)并咨询云技术专家，以设置你购买的新设备。</span><span class="sxs-lookup"><span data-stu-id="78f40-136">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

- <span data-ttu-id="78f40-137">**访问本地资源**</span><span class="sxs-lookup"><span data-stu-id="78f40-137">**Access on-premises resources**</span></span>

     - <span data-ttu-id="78f40-138">如果您的组织使用的是本地 Windows Server Active Directory，则可以将 Microsoft 365 商业版设置为保护 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="78f40-138">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="78f40-139">按照 Microsoft 365 商业版中的 "[启用加入域的 Windows 10 设备](manage-windows-devices.md)" 中的步骤进行操作，以便对此进行设置。</span><span class="sxs-lookup"><span data-stu-id="78f40-139">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="78f40-140">这是此状态的首选方法，称为混合 Azure AD 加入的设备。</span><span class="sxs-lookup"><span data-stu-id="78f40-140">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="78f40-141">如果你的企业有包含某些本地资源（如文件共享和打印机）的本地 Active Directory，则可以执行以下步骤，为 Azure AD 联接的设备提供对这些资源的访问权限：[从访问本地资源Microsoft 365 商业版中的 Azure AD 加入设备](access-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="78f40-141">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

  