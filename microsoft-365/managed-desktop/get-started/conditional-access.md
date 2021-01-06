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
ms.openlocfilehash: d7fe410f114d43d4f6c983aaf23d949298635318
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760099"
---
# <a name="adjust-settings-after-enrollment"></a><span data-ttu-id="98318-104">注册后调整设置</span><span class="sxs-lookup"><span data-stu-id="98318-104">Adjust settings after enrollment</span></span>

<span data-ttu-id="98318-105">完成 Microsoft 托管桌面的注册后，你需要调整某些 Microsoft Intune 和 Azure Active Directory (Azure AD) 设置，以允许管理和维护安全性。</span><span class="sxs-lookup"><span data-stu-id="98318-105">After you've completed enrollment in Microsoft Managed Desktop, you need to adjust certain Microsoft Intune and Azure Active Directory (Azure AD) settings to allow for management and maintain security.</span></span> <span data-ttu-id="98318-106">设置以下设置以排除包含 Microsoft 托管桌面设备和用户的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="98318-106">Set the following settings to exclude the Azure AD groups that contain Microsoft Managed Desktop devices and users.</span></span> <span data-ttu-id="98318-107">有关排除组的步骤，请参阅条件 [访问：用户和组](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)。</span><span class="sxs-lookup"><span data-stu-id="98318-107">For steps to exclude groups, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users).</span></span>

> [!NOTE]
> <span data-ttu-id="98318-108">如果在 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中注册策略后做出任何更改，Microsoft 托管桌面可能会停止正常运行。</span><span class="sxs-lookup"><span data-stu-id="98318-108">If you make any changes after enrollment to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, it's possible that Microsoft Managed Desktop could stop operating properly.</span></span> <span data-ttu-id="98318-109">若要避免 Microsoft 托管桌面操作出现问题，请在更改任何策略之前[](../get-ready/readiness-assessment-fix.md)检查修复准备情况评估工具发现的问题中描述的特定设置。</span><span class="sxs-lookup"><span data-stu-id="98318-109">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in [Fix issues found by the readiness assessment tool](../get-ready/readiness-assessment-fix.md) before you change any policies.</span></span>


## <a name="microsoft-intune-settings"></a><span data-ttu-id="98318-110">Microsoft Intune 设置</span><span class="sxs-lookup"><span data-stu-id="98318-110">Microsoft Intune settings</span></span>

- <span data-ttu-id="98318-111">Autopilot 部署配置文件：排除 **现代工作区设备 -所有**  Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="98318-111">Autopilot deployment profile: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="98318-112">有关步骤，请参阅 [使用 Windows Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="98318-112">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span>
- <span data-ttu-id="98318-113">条件访问策略：排除 **新式工作区服务帐户** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="98318-113">Conditional Access policies: exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="98318-114">有关步骤，请参阅 [条件访问：用户和组](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。</span><span class="sxs-lookup"><span data-stu-id="98318-114">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>
- <span data-ttu-id="98318-115">多重身份验证：确保任何需要多重身份验证的条件访问策略都排除 **Modern Workplace Service Accounts** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="98318-115">Multifactor authentication: make sure any conditional access policies that require multifactor authentication exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="98318-116">有关详细信息，请参阅条件[访问策略](../get-ready/readiness-assessment-fix.md#conditional-access-policies)和[条件访问：要求所有用户使用 MFA。](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="98318-116">For more information, see [Conditional access policies](../get-ready/readiness-assessment-fix.md#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>
- <span data-ttu-id="98318-117">安全基线：排除 **现代工作区设备 -所有**  Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="98318-117">Security baseline: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="98318-118">有关步骤，请参阅 [使用安全基线在 Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)中配置 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="98318-118">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>
- <span data-ttu-id="98318-119">Windows 10 更新圈：排除 **现代工作区设备 -所有**  Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="98318-119">Windows 10 update ring: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="98318-120">有关步骤，请参阅 [在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="98318-120">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="98318-121">Azure Active Directory 设置</span><span class="sxs-lookup"><span data-stu-id="98318-121">Azure Active Directory settings</span></span>

<span data-ttu-id="98318-122">自助服务密码重置：选择 **"已选择** "设置，然后选择" **现代工作区设备 - 所有** Azure AD 组"。</span><span class="sxs-lookup"><span data-stu-id="98318-122">Self-service password reset: choose **Selected** setting, and then select **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="98318-123">有关详细信息，请参阅 [教程：允许用户使用 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)自助服务密码重置解锁其帐户或重置密码。</span><span class="sxs-lookup"><span data-stu-id="98318-123">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="98318-124">Microsoft 托管桌面入门的步骤</span><span class="sxs-lookup"><span data-stu-id="98318-124">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="98318-125">在管理门户中添加和验证管理员联系人</span><span class="sxs-lookup"><span data-stu-id="98318-125">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="98318-126">在本文 (后调整) </span><span class="sxs-lookup"><span data-stu-id="98318-126">Adjust settings after enrollment (this article)</span></span>
3. [<span data-ttu-id="98318-127">分配许可证</span><span class="sxs-lookup"><span data-stu-id="98318-127">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="98318-128">部署 Intune 公司门户</span><span class="sxs-lookup"><span data-stu-id="98318-128">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="98318-129">启用企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="98318-129">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="98318-130">设置设备</span><span class="sxs-lookup"><span data-stu-id="98318-130">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="98318-131">让用户做好使用设备的准备</span><span class="sxs-lookup"><span data-stu-id="98318-131">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="98318-132">部署应用</span><span class="sxs-lookup"><span data-stu-id="98318-132">Deploy apps</span></span>](deploy-apps.md)
