---
title: 将帐户从 Microsoft Defender for Office 365 重定向到新的 Microsoft 365 安全中心
description: 如何从 Defender for Office 365 重定向到 Microsoft 365 安全中心。
keywords: Microsoft 365 安全中心，Microsoft 365 安全中心入门，安全中心重定向
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
ms.openlocfilehash: ce8c178b4c46a00b83833f008080b776f4dc7e60
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055553"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a><span data-ttu-id="b8cd8-104">将帐户从 Microsoft Defender for Office 365 重定向到 Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="b8cd8-104">Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b8cd8-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b8cd8-105">**Applies to:**</span></span>

- <span data-ttu-id="b8cd8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8cd8-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="b8cd8-107">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b8cd8-107">Defender for Office 365</span></span>

<span data-ttu-id="b8cd8-108">本文介绍如何通过启用从以前的 Microsoft 安全与合规中心 (protection.office.com 或 securitycenter.microsoft.com) 到 Microsoft 365 安全中心 (security.microsoft.com) 的自动重定向，将帐户路由到 Microsoft 365 安全中心。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-108">This article explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Security and Compliance Center (protection.office.com or securitycenter.microsoft.com), to the Microsoft 365 security center (security.microsoft.com).</span></span>

>[!NOTE]
> <span data-ttu-id="b8cd8-109">门户重定向功能仅适用于 Office 365 E5 和 Microsoft Defender for Office P2 客户</span><span class="sxs-lookup"><span data-stu-id="b8cd8-109">Portal redirection capability is available for Office 365 E5 and Microsoft Defender for Office P2 customers only</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="b8cd8-110">预期结果</span><span class="sxs-lookup"><span data-stu-id="b8cd8-110">What to expect</span></span>
<span data-ttu-id="b8cd8-111">启用和激活自动重定向后，访问 Office 365 安全与合规中心 (protection.office.com) 中与安全相关的功能的用户将自动路由到 Microsoft 365 安全中心 (https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-111">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to the Microsoft 365 security center (https://security.microsoft.com).</span></span>  

<span data-ttu-id="b8cd8-112">详细了解更改了哪些功能[：Microsoft 365 安全中心中的 Microsoft Defender for Office 365。](microsoft-365-security-center-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="b8cd8-112">Learn more about what’s changed: [Microsoft Defender for Office 365 in the Microsoft 365 security center](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="b8cd8-113">启用自动重定向后，当用户使用 Office 365 安全与合规中心中的安全功能时，他们将被路由到 Microsoft 365 安全中心。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-113">With automatic redirection turned on, users will be routed to Microsoft 365 security center when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="b8cd8-114">其中包括威胁管理部分以及威胁管理仪表板和报告的功能。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-114">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="b8cd8-115">Office 365 安全与合规中心中与安全不相关的项目不会重定向到 Microsoft 365 安全中心。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-115">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to the Microsoft 365 security center.</span></span>

<span data-ttu-id="b8cd8-116">合规性相关项目可在 Microsoft 365 合规中心内找到，与邮件流相关的项目可在 Exchange 管理中心找到。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-116">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="b8cd8-117">重定向不会影响所有其他功能，无论合规性相关还是同时提供这两项功能。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-117">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="b8cd8-118">Office 365 安全警报显示在 Microsoft 365 安全中心和 Office 365 安全与合规中心中，无需重定向。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-118">Office 365 security alerts appear in both the Microsoft 365 security center and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="b8cd8-119">设置门户重定向</span><span class="sxs-lookup"><span data-stu-id="b8cd8-119">Set up portal redirection</span></span>
<span data-ttu-id="b8cd8-120">若要开始将帐户路由到 Microsoft 365 安全中心，security.microsoft.com：</span><span class="sxs-lookup"><span data-stu-id="b8cd8-120">To start routing accounts to the Microsoft 365 security center at security.microsoft.com:</span></span>

1. <span data-ttu-id="b8cd8-121">请确保你是全局管理员或在 Azure Active directory 中具有安全管理员权限。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-121">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="b8cd8-122">[登录到](https://security.microsoft.com/) Microsoft 365 安全中心。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-122">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>
3. <span data-ttu-id="b8cd8-123">导航到 **设置**  >  **电子邮件&协作**  >  **门户重定向**。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-123">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="b8cd8-124">将"自动重定向"设置切换为 **"打开"。**</span><span class="sxs-lookup"><span data-stu-id="b8cd8-124">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="b8cd8-125">单击 **"** 启用"以将自动重定向应用到 Microsoft 365 安全中心门户。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-125">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

> [!NOTE]
> <span data-ttu-id="b8cd8-126">启用重定向后，应用此设置时的活动会话中的帐户不会从会话弹出，并且仅在结束当前会话并再次登录后路由到 Microsoft 365 安全中心。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-126">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="b8cd8-127">我能否返回到使用以前的门户？</span><span class="sxs-lookup"><span data-stu-id="b8cd8-127">Can I go back to using the former portal?</span></span>
<span data-ttu-id="b8cd8-128">如果无法通过 Microsoft 365 安全中心门户完成某些操作或无法完成某些操作，我们希望使用门户反馈选项来收听。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-128">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="b8cd8-129">如果遇到任何重定向问题，我们鼓励你通过私人预览版直接与你的 PM 好友联系，或者通过"提供反馈提交"表单告诉我们。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-129">If you’ve encountered any issues with redirection, we encourage you to reach out to your PM buddy directly through private preview or let us know via the Give feedback submission form.</span></span>

<span data-ttu-id="b8cd8-130">还原到以前的门户：</span><span class="sxs-lookup"><span data-stu-id="b8cd8-130">To revert to the former portal:</span></span>

1. <span data-ttu-id="b8cd8-131">[以全局](https://security.microsoft.com/) 管理员或 Azure Active Directory 中的安全管理员权限使用 和 帐户登录 Microsoft 365 安全中心。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-131">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="b8cd8-132">导航到 **设置**  >  **终结点**  >  **常规**  >  **门户重定向**。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-132">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection**.</span></span>  

3. <span data-ttu-id="b8cd8-133">将"自动重定向"设置切换为 **"关"。**</span><span class="sxs-lookup"><span data-stu-id="b8cd8-133">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="b8cd8-134">当 **系统&** 时，单击"禁用共享反馈"。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-134">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="b8cd8-135">可以随时再次启用此设置。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-135">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="b8cd8-136">禁用后，帐户将不再路由到 security.microsoft.com，并且你将再次有权访问以前的门户 -securitycenter.windows.com 或 securitycenter.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="b8cd8-136">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="b8cd8-137">相关信息</span><span class="sxs-lookup"><span data-stu-id="b8cd8-137">Related information</span></span>
- [<span data-ttu-id="b8cd8-138">Microsoft 365 安全中心概述</span><span class="sxs-lookup"><span data-stu-id="b8cd8-138">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="b8cd8-139">Microsoft 365 安全中心中的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b8cd8-139">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="b8cd8-140">Microsoft 提供统一的 SIEM 和 XDR 以现代化安全操作</span><span class="sxs-lookup"><span data-stu-id="b8cd8-140">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="b8cd8-141">XDR 与 SIEM 信息图</span><span class="sxs-lookup"><span data-stu-id="b8cd8-141">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="b8cd8-142">新 Defender</span><span class="sxs-lookup"><span data-stu-id="b8cd8-142">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="b8cd8-143">关于 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8cd8-143">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="b8cd8-144">Microsoft 安全门户和管理中心</span><span class="sxs-lookup"><span data-stu-id="b8cd8-144">Microsoft security portals and admin centers</span></span>](portals.md)