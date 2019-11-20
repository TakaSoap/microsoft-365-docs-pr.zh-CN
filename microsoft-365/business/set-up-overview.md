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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 商业版的安装步骤概述。
ms.openlocfilehash: 3447f06d031462a7bebc6f129238de9f0c5dee41
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2019
ms.locfileid: "38721551"
---
# <a name="overview-of-setup"></a><span data-ttu-id="2f30c-103">设置概述</span><span class="sxs-lookup"><span data-stu-id="2f30c-103">Overview of setup</span></span>

<span data-ttu-id="2f30c-104">大部分安装步骤可以在安装向导中完成，但也会列出其他选项。</span><span class="sxs-lookup"><span data-stu-id="2f30c-104">Most of the setup steps can be done in the setup wizard, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="2f30c-105">步骤1：添加您的域和用户</span><span class="sxs-lookup"><span data-stu-id="2f30c-105">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="2f30c-106">**[添加你的域](set-up.md#add-your-domain-to-personalize-sign-in)**（如果你在[注册](sign-up.md)过程中购买了你的域，则此步骤已完成。）</span><span class="sxs-lookup"><span data-stu-id="2f30c-106">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="2f30c-107">**添加用户**。</span><span class="sxs-lookup"><span data-stu-id="2f30c-107">**Add users**.</span></span> <span data-ttu-id="2f30c-108">可以通过以下三种方式之一添加用户：</span><span class="sxs-lookup"><span data-stu-id="2f30c-108">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="2f30c-109">在[向导](set-up.md#add-users-in-the-wizard)中。</span><span class="sxs-lookup"><span data-stu-id="2f30c-109">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="2f30c-110">如果你有本地 Active directory，请使用目录同步来[使用 AZURE AD Connect 添加用户](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="2f30c-110">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="2f30c-111">您还可以在随后的管理中心[添加用户](add-users-m365b.md)。</span><span class="sxs-lookup"><span data-stu-id="2f30c-111">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="2f30c-112">步骤2：设置安全策略和配置设备</span><span class="sxs-lookup"><span data-stu-id="2f30c-112">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="2f30c-113">使用[安装向导](set-up.md#protect-data-and-devices)配置设备和安全策略。</span><span class="sxs-lookup"><span data-stu-id="2f30c-113">Use the [Setup wizard](set-up.md#protect-data-and-devices) to configure device and security policies.</span></span> 
  - <span data-ttu-id="2f30c-114">您还可以在[管理员中心](view-policies-and-devices.md)和[Intune 门户](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)中添加更多或编辑它们。</span><span class="sxs-lookup"><span data-stu-id="2f30c-114">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="2f30c-115">除了安装向导中的安全设置之外，还可以通过添加以下设置来提高安全性：</span><span class="sxs-lookup"><span data-stu-id="2f30c-115">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

      - <span data-ttu-id="2f30c-116">**电子邮件恶意软件保护**</span><span class="sxs-lookup"><span data-stu-id="2f30c-116">**Email malware protection**</span></span>
      - <span data-ttu-id="2f30c-117">**高级威胁防护（ATP）安全链接**</span><span class="sxs-lookup"><span data-stu-id="2f30c-117">**Advanced Threat Protection (ATP) Safe links**</span></span>
      - <span data-ttu-id="2f30c-118">**ATP 安全附件**</span><span class="sxs-lookup"><span data-stu-id="2f30c-118">**ATP Safe Attachments**</span></span>
      - <span data-ttu-id="2f30c-119">**ATP 反网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="2f30c-119">**ATP anti-phishing**</span></span>
      - <span data-ttu-id="2f30c-120">**Exchange Online Archiving**</span><span class="sxs-lookup"><span data-stu-id="2f30c-120">**Exchange Online Archiving**</span></span>
      - <span data-ttu-id="2f30c-121">**Data Loss Prevention (DLP)**</span><span class="sxs-lookup"><span data-stu-id="2f30c-121">**Data Loss Prevention (DLP)**</span></span>
      - <span data-ttu-id="2f30c-122">**Azure 信息保护（Plan1**）</span><span class="sxs-lookup"><span data-stu-id="2f30c-122">**Azure Information Protection (Plan1**)</span></span>

          <span data-ttu-id="2f30c-123">若要开始，请[设置高级安全策略](set-up-advanced-security.md)。</span><span class="sxs-lookup"><span data-stu-id="2f30c-123">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

        <span data-ttu-id="2f30c-124">请参阅[保护 Microsoft 365 业务的十大方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)，以获得最佳安全实践的路线图。</span><span class="sxs-lookup"><span data-stu-id="2f30c-124">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="2f30c-125">步骤3：设置和管理 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="2f30c-125">Step 3: Set up and manage Windows 10 devices</span></span>

   <span data-ttu-id="2f30c-126">将 Windows 10 设备加入 Azure AD 时，将在[步骤 2](#step-2-set-up-security-policies-and-configure-devices)中设置的策略应用于该 AD。</span><span class="sxs-lookup"><span data-stu-id="2f30c-126">When you join a Windows 10 device to Azure AD, the policies you set up in [Step 2](#step-2-set-up-security-policies-and-configure-devices) get applied to it.</span></span>

   - <span data-ttu-id="2f30c-127">Windows 10 专业版是 Microsoft 365 商业版的[先决条件](pre-requisites-for-data-protection.md)，但如果你有 Windows 7 Pro、Windows 8 专业版或 Windows 8.1 pro，你的订阅让你能够[升级到 Windows 10 专业](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)版。</span><span class="sxs-lookup"><span data-stu-id="2f30c-127">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
    - <span data-ttu-id="2f30c-128">使用[安装向导](set-up.md#protect-data-and-devices)为 Windows 10 设备配置策略。</span><span class="sxs-lookup"><span data-stu-id="2f30c-128">Use the [Setup wizard](set-up.md#protect-data-and-devices) to configure policies for Windows 10 devices.</span></span>

## <a name="step-4-install-office-365-business"></a><span data-ttu-id="2f30c-129">步骤4：安装 Office 365 商业版</span><span class="sxs-lookup"><span data-stu-id="2f30c-129">Step 4: Install Office 365 Business</span></span>
- <span data-ttu-id="2f30c-130">您可以使用[安装向导](set-up.md#deploy-office-365-client-apps)在 Windows 设备中自动安装 Office。</span><span class="sxs-lookup"><span data-stu-id="2f30c-130">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="2f30c-131">允许用户安装适用于 Windows 和设备的[Office 应用程序](https://docs.microsoft.com/office365/admin/setup/install-applications)。</span><span class="sxs-lookup"><span data-stu-id="2f30c-131">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="2f30c-132">高级</span><span class="sxs-lookup"><span data-stu-id="2f30c-132">Advanced</span></span>
- <span data-ttu-id="2f30c-133">**使用 Autopilot 设置新设备**</span><span class="sxs-lookup"><span data-stu-id="2f30c-133">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="2f30c-134">可以使用[Windows Autopilot](add-autopilot-devices-and-profile.md)为用户自动预配置**新**的 Windows 10 设备，但更易于获取可为您执行此操作的[合作伙伴](https://www.microsoft.com/solution-providers/search)。</span><span class="sxs-lookup"><span data-stu-id="2f30c-134">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="2f30c-135">你也可以转到[Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)，并请求云技术专家设置你购买的新设备。</span><span class="sxs-lookup"><span data-stu-id="2f30c-135">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="2f30c-136">**访问本地资源**</span><span class="sxs-lookup"><span data-stu-id="2f30c-136">**Access on-premises resources**</span></span>

     - <span data-ttu-id="2f30c-137">如果您的组织使用的是本地 Windows Server Active Directory，则可以将 Microsoft 365 商业版设置为保护 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2f30c-137">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="2f30c-138">按照 Microsoft 365 商业版中的 "[启用加入域的 Windows 10 设备](manage-windows-devices.md)" 中的步骤进行操作，以便对此进行设置。</span><span class="sxs-lookup"><span data-stu-id="2f30c-138">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="2f30c-139">这是首选方法，而此状态的设备称为混合 Azure AD 加入的设备。</span><span class="sxs-lookup"><span data-stu-id="2f30c-139">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="2f30c-140">如果你的企业具有包含某些本地资源（如文件共享和打印机）的本地 Active Directory，则可以按照以下步骤为 Azure AD 联接的设备授予对这些资源的访问权限：[从 Microsoft 365 商业版中的 AZURE AD 加入设备访问本地资源](access-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="2f30c-140">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

  