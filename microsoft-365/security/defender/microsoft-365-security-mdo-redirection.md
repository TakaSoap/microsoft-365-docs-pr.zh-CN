---
title: 将帐户从 Office 365 安全与合规中心重定向到新的 Microsoft 365 Defender
description: 如何从 Defender for Office 365 重定向到 Microsoft 365 Defender。
keywords: Microsoft 365Defender， 开始使用 Microsoft 365 Defender， 安全中心重定向
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842514"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a><span data-ttu-id="68737-104">将帐户从安全Office 365中心重定向到 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68737-104">Redirecting accounts from Office 365 Security and Compliance Center to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="68737-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="68737-105">**Applies to:**</span></span>

- <span data-ttu-id="68737-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68737-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="68737-107">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="68737-107">Defender for Office 365</span></span>

<span data-ttu-id="68737-108">本文介绍如何通过启用从以前的 Microsoft 365 Office 365 安全与合规中心 (protection.office.com) 到 Microsoft 365 Defender (security.microsoft.com) 的自动重定向，将帐户路由到 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="68737-108">This article explains how to route accounts to Microsoft 365 Defender by enabling automatic redirection from the former Office 365 Security and Compliance Center (protection.office.com), to Microsoft 365 Defender (security.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="68737-109">预期结果</span><span class="sxs-lookup"><span data-stu-id="68737-109">What to expect</span></span>
<span data-ttu-id="68737-110">启用并激活自动重定向后，访问 Office 365 Security and Compliance (protection.office.com) 中与安全相关的功能的用户将自动路由到 Microsoft 365 Defender (https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="68737-110">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to Microsoft 365 Defender (https://security.microsoft.com).</span></span>  

<span data-ttu-id="68737-111">了解有关更改功能[：Microsoft Defender for Office 365 defender Microsoft 365。](microsoft-365-security-center-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="68737-111">Learn more about what’s changed: [Microsoft Defender for Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="68737-112">启用自动重定向后，当用户使用 Microsoft 365 安全与合规中心中的Office 365时，他们将被路由到 Office 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="68737-112">With automatic redirection turned on, users will be routed to Microsoft 365 Defender when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="68737-113">其中包括威胁管理部分以及威胁管理仪表板和报告的功能。</span><span class="sxs-lookup"><span data-stu-id="68737-113">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="68737-114">安全Office 365安全与合规中心内与安全不相关的项目不会重定向到 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="68737-114">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to Microsoft 365 Defender.</span></span>

<span data-ttu-id="68737-115">合规性相关项目可在合规性Microsoft 365中心内找到，并且可以在管理中心内找到与Exchange项。</span><span class="sxs-lookup"><span data-stu-id="68737-115">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="68737-116">重定向不会影响所有其他功能，无论合规性相关还是同时提供这两项功能。</span><span class="sxs-lookup"><span data-stu-id="68737-116">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="68737-117">Office 365 Defender 和 Microsoft 365 安全与合规中心Office 365安全警报，无需重定向。</span><span class="sxs-lookup"><span data-stu-id="68737-117">Office 365 security alerts appear in both Microsoft 365 Defender and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="68737-118">设置门户重定向</span><span class="sxs-lookup"><span data-stu-id="68737-118">Set up portal redirection</span></span>
<span data-ttu-id="68737-119">若要开始将帐户路由到 Microsoft 365 Defender，security.microsoft.com：</span><span class="sxs-lookup"><span data-stu-id="68737-119">To start routing accounts to Microsoft 365 Defender at security.microsoft.com:</span></span>

1. <span data-ttu-id="68737-120">请确保你是全局管理员或在 Azure Active directory 中具有安全管理员权限。</span><span class="sxs-lookup"><span data-stu-id="68737-120">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="68737-121">[登录到](https://security.microsoft.com/)Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="68737-121">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.</span></span>
3. <span data-ttu-id="68737-122">导航到 **设置**  >  **电子邮件&协作**  >  **门户重定向**。</span><span class="sxs-lookup"><span data-stu-id="68737-122">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="68737-123">将"自动重定向"设置切换为 **"打开"。**</span><span class="sxs-lookup"><span data-stu-id="68737-123">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="68737-124">单击 **"启用**"将自动重定向应用到 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="68737-124">Click **Enable** to apply automatic redirection to Microsoft 365 Defender.</span></span>

> [!NOTE]
> <span data-ttu-id="68737-125">启用重定向后，应用此设置时的活动会话中的帐户不会从会话弹出，并且仅在结束当前会话并再次登录后路由到 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="68737-125">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="68737-126">我能否返回到使用以前的门户？</span><span class="sxs-lookup"><span data-stu-id="68737-126">Can I go back to using the former portal?</span></span>
<span data-ttu-id="68737-127">如果某些内容无法用于你，或者如果你无法通过 Microsoft 365 Defender 完成某些操作，我们希望使用门户反馈选项来收听它。</span><span class="sxs-lookup"><span data-stu-id="68737-127">If something isn’t working for you or if there’s anything you’re unable to complete through Microsoft 365 Defender, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="68737-128">如果遇到重定向问题，请告诉我们。</span><span class="sxs-lookup"><span data-stu-id="68737-128">If you’ve encountered any issues with redirection, please let us know.</span></span>

<span data-ttu-id="68737-129">还原到以前的门户：</span><span class="sxs-lookup"><span data-stu-id="68737-129">To revert to the former portal:</span></span>

1. <span data-ttu-id="68737-130">[以全局](https://security.microsoft.com/)Microsoft 365或 Azure Active directory 中的安全管理员权限使用 和 帐户登录 Defender。</span><span class="sxs-lookup"><span data-stu-id="68737-130">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="68737-131">导航到 **设置**  >  **电子邮件&协作**  >  **门户重定向**。</span><span class="sxs-lookup"><span data-stu-id="68737-131">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>   

3. <span data-ttu-id="68737-132">将"自动重定向"设置切换为 **"关"。**</span><span class="sxs-lookup"><span data-stu-id="68737-132">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="68737-133">当 **系统&** 时，单击"禁用共享反馈"。</span><span class="sxs-lookup"><span data-stu-id="68737-133">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="68737-134">可以随时再次启用此设置。</span><span class="sxs-lookup"><span data-stu-id="68737-134">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="68737-135">禁用后，帐户将不再路由到 security.microsoft.com，并且你将再次有权访问以前的门户-securitycenter.windows.com 或 securitycenter.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="68737-135">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal—securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="68737-136">相关信息</span><span class="sxs-lookup"><span data-stu-id="68737-136">Related information</span></span>
- [<span data-ttu-id="68737-137">Microsoft 365Defender 概述</span><span class="sxs-lookup"><span data-stu-id="68737-137">Microsoft 365 Defender overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="68737-138">Microsoft Defender for Endpoint in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68737-138">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="68737-139">Microsoft 提供统一的 SIEM 和 XDR 以现代化安全操作</span><span class="sxs-lookup"><span data-stu-id="68737-139">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="68737-140">XDR 与 SIEM 信息图</span><span class="sxs-lookup"><span data-stu-id="68737-140">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="68737-141">新 Defender</span><span class="sxs-lookup"><span data-stu-id="68737-141">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="68737-142">关于 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68737-142">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="68737-143">Microsoft 安全门户和管理中心</span><span class="sxs-lookup"><span data-stu-id="68737-143">Microsoft security portals and admin centers</span></span>](portals.md)
