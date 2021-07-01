---
title: 将用户从 Office 365 安全与合规中心重定向到Microsoft 365 合规中心
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: 了解如何自动Office 365安全与合规中心用户重定向到Microsoft 365 合规中心。
ms.collection: M365-security-compliance
ms.openlocfilehash: 83d6a08d5c189c08c8f7d25daa3af39f28cbf8f1
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226271"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="8af27-103">将用户从 Office 365 安全与合规中心重定向到Microsoft 365 合规中心</span><span class="sxs-lookup"><span data-stu-id="8af27-103">Redirect users from the Office 365 Security and Compliance center to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="8af27-104">本文介绍了自动重定向如何适用于从安全与合规中心Office 365合规性解决方案 (protection.office.com) 到Microsoft 365 合规中心 (compliance.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="8af27-104">This article explains how automatic redirection works for users accessing compliance solutions from the Office 365 Security and Compliance Center (protection.office.com) to the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="8af27-105">预期结果</span><span class="sxs-lookup"><span data-stu-id="8af27-105">What to expect</span></span>

<span data-ttu-id="8af27-106">默认情况下，在安全与合规策略中访问以下合规性相关解决方案的所有用户Office 365自动 (protection.office.com) ：</span><span class="sxs-lookup"><span data-stu-id="8af27-106">Automatic redirection is enabled by default for all users accessing the following compliance-related solutions in Office 365 Security and Compliance (protection.office.com):</span></span>

- <span data-ttu-id="8af27-107">数据丢失防护 (DLP)</span><span class="sxs-lookup"><span data-stu-id="8af27-107">Data loss prevention (DLP)</span></span>
- <span data-ttu-id="8af27-108">分类</span><span class="sxs-lookup"><span data-stu-id="8af27-108">Classification</span></span>
- <span data-ttu-id="8af27-109">信息治理</span><span class="sxs-lookup"><span data-stu-id="8af27-109">Information governance</span></span>
- <span data-ttu-id="8af27-110">记录管理</span><span class="sxs-lookup"><span data-stu-id="8af27-110">Records management</span></span>
- <span data-ttu-id="8af27-111">通信合规性 (以前是"监督") </span><span class="sxs-lookup"><span data-stu-id="8af27-111">Communication compliance (formerly 'Supervision')</span></span>

<span data-ttu-id="8af27-112">用户将自动路由到 Microsoft 365 合规中心 (compliance.microsoft.com) 中的相同合规性解决方案。</span><span class="sxs-lookup"><span data-stu-id="8af27-112">Users are automatically routed to the same compliance solutions in the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="8af27-113">对于安全与合规Office 365中包含的其他合规性解决方案，用户将继续在 Microsoft 365 合规中心 或 Office 365 安全与合规中心管理这些解决方案。</span><span class="sxs-lookup"><span data-stu-id="8af27-113">For other compliance solutions included in the Office 365 Security and Compliance Center, users will continue to manage these solutions in either the Microsoft 365 compliance center or the Office 365 Security and Compliance Center.</span></span> <span data-ttu-id="8af27-114">这些合规性解决方案的自动重定向即将推出。\*</span><span class="sxs-lookup"><span data-stu-id="8af27-114">The automatic redirection for these compliance solutions will be available soon.\*</span></span>

<span data-ttu-id="8af27-115">此功能和相关控件不支持自动重定向 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="8af27-115">This feature and associated controls does not enable the automatic redirection of Security features for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="8af27-116">若要启用安全功能重定向，请参阅将帐户从[Microsoft Defender](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) for Office 365重定向到 Microsoft 365 安全中心了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="8af27-116">To enable the redirection for security features, see [Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) for details.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="8af27-117">我能否返回到使用以前的门户？</span><span class="sxs-lookup"><span data-stu-id="8af27-117">Can I go back to using the former portal?</span></span>

<span data-ttu-id="8af27-118">如果无法通过 Microsoft 365 合规中心 门户完成某些操作或无法完成某些操作，可以暂时禁用所有用户的自动重定向。</span><span class="sxs-lookup"><span data-stu-id="8af27-118">If something isn't working for you or if there's anything you're unable to complete through the Microsoft 365 compliance center portal, you can temporarily disable the automatic redirection for all users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8af27-119">The Microsoft 365 合规中心 is the replacement management portal for compliance solutions currently managed in the Office 365 Security and Compliance center.</span><span class="sxs-lookup"><span data-stu-id="8af27-119">The Microsoft 365 compliance center is the replacement management portal for compliance solutions currently managed in the Office 365 Security and Compliance center.</span></span> <span data-ttu-id="8af27-120">所有Microsoft 365合规性解决方案将仅在 Microsoft 365 合规中心 中进行管理。</span><span class="sxs-lookup"><span data-stu-id="8af27-120">All Microsoft 365 compliance solutions will be managed solely in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="8af27-121">禁用重定向到Microsoft 365 合规中心应该是一个短期解决方案。\*</span><span class="sxs-lookup"><span data-stu-id="8af27-121">Disabling redirection to the Microsoft 365 compliance center should be a short-term solution.\*</span></span>

<span data-ttu-id="8af27-122">若要切换回Office 365安全与合规 (protection.microsoft.com) ，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8af27-122">To switch back to the Office 365 Security and Compliance center (protection.microsoft.com) for all users, complete the following steps:</span></span>

1. <span data-ttu-id="8af27-123">以全局管理员[Microsoft 365 合规中心](https://compliance.microsoft.com)Azure Active directory 中具有合规性管理员权限的任何帐户登录帐户。</span><span class="sxs-lookup"><span data-stu-id="8af27-123">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com) as a global administrator or using any account with compliance administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="8af27-124">导航到 **设置**  >  **合规中心重定向。**</span><span class="sxs-lookup"><span data-stu-id="8af27-124">Navigate to **Settings** > **Compliance center redirection**.</span></span>
3. <span data-ttu-id="8af27-125">将"自动重定向"设置切换为 **"关"。**</span><span class="sxs-lookup"><span data-stu-id="8af27-125">Toggle the Automatic redirection setting to **Off**.</span></span>
4. <span data-ttu-id="8af27-126">选择 **"关闭** "，在系统提示时共享反馈。</span><span class="sxs-lookup"><span data-stu-id="8af27-126">Select **Turn off** and share feedback when prompted.</span></span>

<span data-ttu-id="8af27-127">禁用后，用户将不再被路由到 compliance.microsoft.com 他们将被定向到 Office 365 安全与合规中心 (protection.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="8af27-127">Once disabled, users will no longer be routed to compliance.microsoft.com and they will be directed to the Office 365 Security and Compliance center (protection.microsoft.com).</span></span> <span data-ttu-id="8af27-128">全局管理员或合规性管理员可以随时再次启用此设置。</span><span class="sxs-lookup"><span data-stu-id="8af27-128">This setting can be enabled again at any time by Global or Compliance admins.</span></span>

## <a name="related-information"></a><span data-ttu-id="8af27-129">相关信息</span><span class="sxs-lookup"><span data-stu-id="8af27-129">Related information</span></span>

- [<span data-ttu-id="8af27-130">Microsoft 365 合规中心概述</span><span class="sxs-lookup"><span data-stu-id="8af27-130">Microsoft 365 compliance center overview</span></span>](/microsoft-365/compliance/microsoft-365-compliance-center)
