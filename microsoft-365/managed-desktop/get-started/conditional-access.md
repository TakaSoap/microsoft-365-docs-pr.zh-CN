---
title: 注册后调整设置
description: 如何排除某些 Microsoft 帐户
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 88a832f6c4e17756bfb25ef5cb7c4c5ecedaf2c0
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794384"
---
# <a name="adjust-settings-after-enrollment"></a><span data-ttu-id="a0895-104">注册后调整设置</span><span class="sxs-lookup"><span data-stu-id="a0895-104">Adjust settings after enrollment</span></span>

<span data-ttu-id="a0895-105">在 Microsoft 托管桌面中完成注册后，可能需要调整某些管理设置。</span><span class="sxs-lookup"><span data-stu-id="a0895-105">After you’ve completed enrollment in Microsoft Managed Desktop, some management settings might need to be adjusted.</span></span> <span data-ttu-id="a0895-106">若要检查和调整（如果需要），请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="a0895-106">To check and adjust if needed, follow these steps:</span></span>

1. <span data-ttu-id="a0895-107">查看下一部分中介绍的 Microsoft Intune 和 Azure Active Directory 设置。</span><span class="sxs-lookup"><span data-stu-id="a0895-107">Review the Microsoft Intune and Azure Active Directory settings described in the next section.</span></span>
2. <span data-ttu-id="a0895-108">如果任何项目适用于您的环境，请进行所述的调整。</span><span class="sxs-lookup"><span data-stu-id="a0895-108">If any of the items apply to your environment, make the adjustments described.</span></span>
3. <span data-ttu-id="a0895-109">如果要仔细检查所有设置是否正确，可以重新运行准备情况评估工具，以确保没有任何与[](https://aka.ms/mmdart)Microsoft 托管桌面冲突的情况。</span><span class="sxs-lookup"><span data-stu-id="a0895-109">If you want to double-check that all settings are correct, you can rerun the [readiness assessment tool](https://aka.ms/mmdart) to make sure nothing conflicts with Microsoft Managed Desktop.</span></span>

> [!NOTE]
> <span data-ttu-id="a0895-110">由于操作将在几个月后继续，如果在 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中注册影响 Microsoft 托管桌面的策略后进行更改，Microsoft 托管桌面可能会停止正常运行。</span><span class="sxs-lookup"><span data-stu-id="a0895-110">As your operations continue in following months, if you make changes after enrollment to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365 that affect Microsoft Managed Desktop, it's possible that Microsoft Managed Desktop could stop operating properly.</span></span> <span data-ttu-id="a0895-111">为避免服务出现问题，请在更改该服务中列出的策略之前，检查"[](../get-ready/readiness-assessment-fix.md)修复准备情况评估工具发现的问题"中所述的特定设置。</span><span class="sxs-lookup"><span data-stu-id="a0895-111">To avoid problems with the service, check the specific settings described in [Fix issues found by the readiness assessment tool](../get-ready/readiness-assessment-fix.md) before you change the policies listed there.</span></span> <span data-ttu-id="a0895-112">您还可以随时重新运行准备情况评估工具。</span><span class="sxs-lookup"><span data-stu-id="a0895-112">You can also rerun the readiness assessment tool at any time.</span></span>


## <a name="microsoft-intune-settings"></a><span data-ttu-id="a0895-113">Microsoft Intune 设置</span><span class="sxs-lookup"><span data-stu-id="a0895-113">Microsoft Intune settings</span></span>

- <span data-ttu-id="a0895-114">Autopilot 部署配置文件：如果你使用任何 Autopilot 策略，请更新每个策略以排除 **现代工作区设备 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="a0895-114">Autopilot deployment profile: if you use any Autopilot policies, update each one to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="a0895-115">若要更新它们，请在"分配"下的"已排除组"部分中，选择在 Microsoft 托管桌面注册期间创建的新式工作区设备 **-** 所有 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="a0895-115">To update them, in the **Excluded groups** section under **Assignments**, select the **Modern Workplace Devices -All** Azure AD group that was created during Microsoft Managed Desktop enrollment.</span></span> <span data-ttu-id="a0895-116">Microsoft 托管桌面还将创建 Autopilot 配置文件，其名称将为"新式工作区" (**Modern Workplace Autopilot 配置文件**) 。</span><span class="sxs-lookup"><span data-stu-id="a0895-116">Microsoft Managed Desktop will also have created an Autopilot profile, which will have "Modern Workplace" in the name (the **Modern Workplace Autopilot Profile**).</span></span> <span data-ttu-id="a0895-117">更新自己的 Autopilot 配置文件时，请确保不要从Microsoft 托管桌面创建的新式 **工作区 Autopilot** 配置文件中排除新式工作区设备 **-** 所有 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="a0895-117">When you update your own Autopilot profiles, make sure that you *do not* exclude the **Modern Workplace Devices -All** Azure AD group from the **Modern Workplace Autopilot Profile** that was created by Microsoft Managed Desktop.</span></span>

- <span data-ttu-id="a0895-118">条件访问策略：对于已创建的条件访问策略，排除 **新式工作区服务帐户** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="a0895-118">Conditional Access policies: for conditional access policies you've created, exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="a0895-119">有关步骤，请参阅 [条件访问：用户和组](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。</span><span class="sxs-lookup"><span data-stu-id="a0895-119">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span> <span data-ttu-id="a0895-120">Microsoft 托管桌面还将创建一些条件访问策略，所有这些策略的名称都将具有"新式工作区" (例如， **新式工作区** 安全工作站) 。</span><span class="sxs-lookup"><span data-stu-id="a0895-120">Microsoft Managed Desktop will also have created some conditional access policies, all of which will have "Modern Workplace" in the name (for example, **Modern Workplace Secure Workstation**).</span></span> <span data-ttu-id="a0895-121">更新自己的条件访问策略时，请确保不要从 Microsoft托管桌面创建的任何策略中排除现代工作区设备 **-** 所有 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="a0895-121">When you update your own conditional access policies, make sure you *do not* exclude the **Modern Workplace Devices -All** Azure AD group from any policies created by Microsoft Managed Desktop.</span></span>

- <span data-ttu-id="a0895-122">多重身份验证：确保任何需要多重身份验证的条件访问策略都排除 **新式工作区服务帐户** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="a0895-122">Multifactor authentication: make sure any of your conditional access policies that require multifactor authentication exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="a0895-123">有关详细信息，请参阅条件[访问策略](../get-ready/readiness-assessment-fix.md#conditional-access-policies)和[条件访问：要求所有用户使用 MFA。](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="a0895-123">For more information, see [Conditional access policies](../get-ready/readiness-assessment-fix.md#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

- <span data-ttu-id="a0895-124">Windows 10 更新圈：对于你创建的任何 Windows 10 更新圈策略，从每个策略中排除 **现代工作区设备 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="a0895-124">Windows 10 update ring: for any Windows 10 update ring policies you've created, exclude the **Modern Workplace Devices -All** Azure AD group from each policy.</span></span> <span data-ttu-id="a0895-125">有关步骤，请参阅["创建并分配更新圈"。](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings)</span><span class="sxs-lookup"><span data-stu-id="a0895-125">For steps, see [Create and assign update rings](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings).</span></span> <span data-ttu-id="a0895-126">Microsoft 托管桌面还将创建一些更新圈策略，所有更新圈策略的名称为 (例如，现代工作区更新策略 **[广泛]**、 现代工作区更新策略 **[快速]**、 现代工作区更新策略 **[第一]** 和现代工作场所更新策略 **[测试]**) 。</span><span class="sxs-lookup"><span data-stu-id="a0895-126">Microsoft Managed Desktop will also have created some update ring policies, all of which will have "Modern Workplace" in the name (for example **Modern Workplace Update Policy [Broad]**, **Modern Workplace Update Policy [Fast]**, **Modern Workplace Update Policy [First]**, and **Modern Workplace Update Policy [Test]**).</span></span> <span data-ttu-id="a0895-127">更新自己的策略时，请确保不会将新式工作区设备 **-所有** Azure AD 组从 Microsoft 托管桌面创建的组中排除。</span><span class="sxs-lookup"><span data-stu-id="a0895-127">When you update your own policies, make sure that you *do not* exclude the **Modern Workplace Devices -All** Azure AD group from those that Microsoft Managed Desktop created.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="a0895-128">Azure Active Directory 设置</span><span class="sxs-lookup"><span data-stu-id="a0895-128">Azure Active Directory settings</span></span>

<span data-ttu-id="a0895-129">自助服务密码重置：如果使用所有用户的自助密码重置，请调整分配以排除 Microsoft 托管桌面服务帐户。</span><span class="sxs-lookup"><span data-stu-id="a0895-129">Self-service password reset: if you use self-service password reset for all users, adjust the assignment to exclude Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="a0895-130">若要调整此分配，请为除 *Microsoft* 托管桌面服务帐户以外的所有用户创建 Azure AD 动态组，然后将该组用于分配，而不是"所有用户"。</span><span class="sxs-lookup"><span data-stu-id="a0895-130">To adjust this assignment, create a Azure AD dynamic group for all users *except* Microsoft Managed Desktop service accounts, and then use that group for assignment instead of "all users."</span></span>

<span data-ttu-id="a0895-131">为了帮助您查找和排除服务帐户，下面是一个可以使用的动态查询示例：</span><span class="sxs-lookup"><span data-stu-id="a0895-131">To help you find and exclude the service accounts, here is an example of a dynamic query you can use:</span></span>

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

<span data-ttu-id="a0895-132">在此查询中，将@TENANT替换为租户域名。</span><span class="sxs-lookup"><span data-stu-id="a0895-132">In this query, replace @TENANT with your tenant domain name.</span></span>



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="a0895-133">Microsoft 托管桌面入门的步骤</span><span class="sxs-lookup"><span data-stu-id="a0895-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="a0895-134">在管理门户中添加和验证管理员联系人</span><span class="sxs-lookup"><span data-stu-id="a0895-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="a0895-135">在本文 (后调整) </span><span class="sxs-lookup"><span data-stu-id="a0895-135">Adjust settings after enrollment (this article)</span></span>
3. [<span data-ttu-id="a0895-136">分配许可证</span><span class="sxs-lookup"><span data-stu-id="a0895-136">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="a0895-137">部署 Intune 公司门户</span><span class="sxs-lookup"><span data-stu-id="a0895-137">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="a0895-138">启用企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="a0895-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="a0895-139">设置设备</span><span class="sxs-lookup"><span data-stu-id="a0895-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="a0895-140">让用户做好使用设备的准备</span><span class="sxs-lookup"><span data-stu-id="a0895-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="a0895-141">部署应用</span><span class="sxs-lookup"><span data-stu-id="a0895-141">Deploy apps</span></span>](deploy-apps.md)
