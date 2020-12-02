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
ms.openlocfilehash: 76a73372cc7517c3241390e58c28b0b02bffd664
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527693"
---
# <a name="adjust-settings-after-enrollment"></a><span data-ttu-id="6ebbc-104">注册后调整设置</span><span class="sxs-lookup"><span data-stu-id="6ebbc-104">Adjust settings after enrollment</span></span>

<span data-ttu-id="6ebbc-105">在 Microsoft 托管桌面中完成注册后，需要调整某些 Microsoft Intune 和 Azure Active Directory (Azure AD) 设置，以允许管理和维护安全性。</span><span class="sxs-lookup"><span data-stu-id="6ebbc-105">After you've completed enrollment in Microsoft Managed Desktop, you need to adjust certain Microsoft Intune and Azure Active Directory (Azure AD) settings to allow for management and maintain security.</span></span> <span data-ttu-id="6ebbc-106">设置以下设置以排除包含 Microsoft 托管桌面设备和用户的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="6ebbc-106">Set the following settings to exclude the Azure AD groups that contain Microsoft Managed Desktop devices and users.</span></span> <span data-ttu-id="6ebbc-107">有关排除组的步骤，请参阅 [条件访问：用户和组](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)。</span><span class="sxs-lookup"><span data-stu-id="6ebbc-107">For steps to exclude groups, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users).</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="6ebbc-108">Microsoft Intune 设置</span><span class="sxs-lookup"><span data-stu-id="6ebbc-108">Microsoft Intune settings</span></span>

- <span data-ttu-id="6ebbc-109">Autopilot 部署配置文件：排除 **新式工作区设备-所有**  Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="6ebbc-109">Autopilot deployment profile: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="6ebbc-110">有关步骤，请参阅 [使用 Windows Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="6ebbc-110">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span>
- <span data-ttu-id="6ebbc-111">条件访问策略：排除 **新式的 Workplace Service 帐户** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="6ebbc-111">Conditional Access policies: exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="6ebbc-112">有关步骤，请参阅 [条件访问：用户和组](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。</span><span class="sxs-lookup"><span data-stu-id="6ebbc-112">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>
- <span data-ttu-id="6ebbc-113">多重身份验证：确保需要多重身份验证的任何条件访问策略排除 **新式 Workplace Service 帐户** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="6ebbc-113">Multifactor authentication: make sure any conditional access policies that require multifactor authentication exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="6ebbc-114">有关详细信息，请参阅 [条件访问策略](../get-ready/readiness-assessment-fix.md#conditional-access-policies) 和 [条件访问：要求对所有用户进行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。</span><span class="sxs-lookup"><span data-stu-id="6ebbc-114">For more information, see [Conditional access policies](../get-ready/readiness-assessment-fix.md#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>
- <span data-ttu-id="6ebbc-115">安全基准：排除 **新式工作区设备-所有**  Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="6ebbc-115">Security baseline: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="6ebbc-116">有关步骤，请参阅 [使用安全基准在 Intune 中配置 Windows 10 设备](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="6ebbc-116">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>
- <span data-ttu-id="6ebbc-117">Windows 10 更新环：排除 **新式工作区设备-所有**  Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="6ebbc-117">Windows 10 update ring: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="6ebbc-118">有关步骤，请参阅 [在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="6ebbc-118">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="6ebbc-119">Azure Active Directory 设置</span><span class="sxs-lookup"><span data-stu-id="6ebbc-119">Azure Active Directory settings</span></span>

<span data-ttu-id="6ebbc-120">自助密码重置：选择 " **选择设置"，然后选择 "** **新式工作区设备-所有** Azure AD 组"。</span><span class="sxs-lookup"><span data-stu-id="6ebbc-120">Self-service password reset: choose **Selected** setting, and then select **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="6ebbc-121">有关详细信息，请参阅 [教程：使用户能够解锁其帐户或使用 Azure Active Directory 自助服务密码重置重置密码](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。</span><span class="sxs-lookup"><span data-stu-id="6ebbc-121">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="6ebbc-122">Microsoft 托管桌面入门步骤</span><span class="sxs-lookup"><span data-stu-id="6ebbc-122">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="6ebbc-123">在管理门户中添加和验证管理员联系人</span><span class="sxs-lookup"><span data-stu-id="6ebbc-123">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="6ebbc-124"> (本文注册后调整设置) </span><span class="sxs-lookup"><span data-stu-id="6ebbc-124">Adjust settings after enrollment (this article)</span></span>
3. [<span data-ttu-id="6ebbc-125">分配许可证</span><span class="sxs-lookup"><span data-stu-id="6ebbc-125">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="6ebbc-126">部署 Intune 公司门户</span><span class="sxs-lookup"><span data-stu-id="6ebbc-126">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="6ebbc-127">启用企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="6ebbc-127">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="6ebbc-128">设置设备</span><span class="sxs-lookup"><span data-stu-id="6ebbc-128">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="6ebbc-129">让用户做好使用设备的准备</span><span class="sxs-lookup"><span data-stu-id="6ebbc-129">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="6ebbc-130">部署应用</span><span class="sxs-lookup"><span data-stu-id="6ebbc-130">Deploy apps</span></span>](deploy-apps.md)
