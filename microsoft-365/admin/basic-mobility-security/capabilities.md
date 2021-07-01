---
title: 基本移动性和安全性的功能
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 基本移动性和安全性可以帮助您保护和管理移动设备。
ms.openlocfilehash: a5f20b2999a1a54070433560904e9535a4d1524a
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228275"
---
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="7510a-103">基本移动性和安全性的功能</span><span class="sxs-lookup"><span data-stu-id="7510a-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="7510a-104">基本移动性和安全性可帮助你保护和管理组织中许可的 Microsoft 365 用户使用的移动设备，如 iPhone、iPad、Android 和 Windows 电话。</span><span class="sxs-lookup"><span data-stu-id="7510a-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="7510a-105">可以使用可帮助控制对组织的电子邮件和文档的访问权限的设置创建移动设备管理策略Microsoft 365受支持的移动设备和应用的文档。</span><span class="sxs-lookup"><span data-stu-id="7510a-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="7510a-106">如果设备丢失或被盗，你可以远程擦除设备以删除敏感的组织信息。</span><span class="sxs-lookup"><span data-stu-id="7510a-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="7510a-107">支持的设备</span><span class="sxs-lookup"><span data-stu-id="7510a-107">Supported devices</span></span>

<span data-ttu-id="7510a-108">您可以使用基本移动性和安全性保护和管理以下设备。</span><span class="sxs-lookup"><span data-stu-id="7510a-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="7510a-109">iOS 11.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="7510a-109">iOS 11.0 or later versions</span></span>

- <span data-ttu-id="7510a-110">Android 5.0 或更高版本<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="7510a-110">Android 5.0 or later versions<sup>3</sup></span></span>

- <span data-ttu-id="7510a-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7510a-111">Windows 8.1<sup>1</sup></span></span>

- <span data-ttu-id="7510a-112">Windows 8.1RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7510a-112">Windows 8.1 RT<sup>1</sup></span></span>

- <span data-ttu-id="7510a-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7510a-113">Windows 10<sup>2</sup></span></span>

- <span data-ttu-id="7510a-114">Windows 10 移动版<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7510a-114">Windows 10 Mobile<sup>2</sup></span></span>

<span data-ttu-id="7510a-115"><sup>1</sup>RT Windows 8.1的访问控制仅限于Exchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="7510a-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="7510a-116"><sup>2</sup>Windows 10访问控制需要订阅，其中包含Azure AD Premium设备需要加入到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="7510a-116"><sup>2</sup>Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="7510a-117"><sup>3</sup>2020 年 6 月之后，超过 9 的 Android 版本无法管理密码设置，但 Samsung Knox 设备上除外。</span><span class="sxs-lookup"><span data-stu-id="7510a-117"><sup>3</sup>After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

> [!NOTE]
> <span data-ttu-id="7510a-118">已注册较早操作系统版本的设备仍可以继续运行，尽管这些功能可能会在不另行通知的情况下更改。</span><span class="sxs-lookup"><span data-stu-id="7510a-118">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="7510a-119">如果组织成员使用的移动设备不受基本移动性和安全性支持，你可能希望阻止 Exchange ActiveSync 应用访问这些设备的 Microsoft 365 电子邮件，以帮助使组织的数据更安全。</span><span class="sxs-lookup"><span data-stu-id="7510a-119">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="7510a-120">有关阻止访问Exchange ActiveSync，请参阅基本移动性和安全性中的管理[设备访问设置](manage-device-access-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="7510a-120">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="7510a-121">电子邮件Microsoft 365文档的访问控制</span><span class="sxs-lookup"><span data-stu-id="7510a-121">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="7510a-122">下表中支持的不同类型的移动设备的应用提示用户注册基本移动性和安全性，其中存在适用于用户设备且用户之前尚未注册该设备的新移动设备管理策略。</span><span class="sxs-lookup"><span data-stu-id="7510a-122">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="7510a-123">如果用户的设备不符合策略，则根据策略的设置方式，可能会阻止用户访问这些应用中的 Microsoft 365 资源，或者他们可能具有访问权限，但 Microsoft 365 报告违反策略。</span><span class="sxs-lookup"><span data-stu-id="7510a-123">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="7510a-124">**Product**</span><span class="sxs-lookup"><span data-stu-id="7510a-124">**Product**</span></span>|<span data-ttu-id="7510a-125">**iOS 10.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-125">**iOS 10.0 or later**</span></span>|<span data-ttu-id="7510a-126">**Android 5.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-126">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7510a-127">**Exchange Exchange ActiveSync** 内置电子邮件和第三方应用（如 TouchDown）使用 Exchange ActiveSync 14.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7510a-127">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="7510a-128">邮件</span><span class="sxs-lookup"><span data-stu-id="7510a-128">Mail</span></span> |<span data-ttu-id="7510a-129">电子邮件</span><span class="sxs-lookup"><span data-stu-id="7510a-129">Email</span></span> |
|<span data-ttu-id="7510a-130">**Office**  和  **OneDrive for Business**</span><span class="sxs-lookup"><span data-stu-id="7510a-130">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="7510a-131">Outlook</span><span class="sxs-lookup"><span data-stu-id="7510a-131">Outlook</span></span> </br><span data-ttu-id="7510a-132">OneDrive</span><span class="sxs-lookup"><span data-stu-id="7510a-132">OneDrive</span></span> </br><span data-ttu-id="7510a-133">Word</span><span class="sxs-lookup"><span data-stu-id="7510a-133">Word</span></span> </br><span data-ttu-id="7510a-134">Excel</span><span class="sxs-lookup"><span data-stu-id="7510a-134">Excel</span></span> </br><span data-ttu-id="7510a-135">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7510a-135">PowerPoint</span></span>|<span data-ttu-id="7510a-136">**在手机和平板电脑上**：</span><span class="sxs-lookup"><span data-stu-id="7510a-136">**On phones and tablets**:</span></span><br/><span data-ttu-id="7510a-137">Outlook</span><span class="sxs-lookup"><span data-stu-id="7510a-137">Outlook</span></span> <br/> <span data-ttu-id="7510a-138">OneDrive</span><span class="sxs-lookup"><span data-stu-id="7510a-138">OneDrive</span></span> <br/> <span data-ttu-id="7510a-139">Word</span><span class="sxs-lookup"><span data-stu-id="7510a-139">Word</span></span> <br/> <span data-ttu-id="7510a-140">Excel</span><span class="sxs-lookup"><span data-stu-id="7510a-140">Excel</span></span> <br/> <span data-ttu-id="7510a-141">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7510a-141">PowerPoint</span></span> <br/> <span data-ttu-id="7510a-142">**仅在电话上：**</span><span class="sxs-lookup"><span data-stu-id="7510a-142">**On phones only:**</span></span> <br/> <span data-ttu-id="7510a-143">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="7510a-143">Office Mobile</span></span> |

> [!NOTE]
>
> - <span data-ttu-id="7510a-144">对 iOS 10.0 及更高版本的支持包括iPhone和iPad设备。</span><span class="sxs-lookup"><span data-stu-id="7510a-144">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
> - <span data-ttu-id="7510a-145">基本安全性和移动性不支持管理 BlackBerry 操作系统设备。</span><span class="sxs-lookup"><span data-stu-id="7510a-145">Management of BlackBerry OS devices isn’t supported by Basic Security and Mobility.</span></span> <span data-ttu-id="7510a-146">使用 BlackBerry 商业云服务 (BBCS) 管理 BlackBerry 操作系统设备。</span><span class="sxs-lookup"><span data-stu-id="7510a-146">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="7510a-147">运行 Android 操作系统的 Blackberry 设备作为标准 Android 设备受到支持</span><span class="sxs-lookup"><span data-stu-id="7510a-147">Blackberry devices running Android OS are supported as standard Android devices</span></span>
> - <span data-ttu-id="7510a-148">如果用户使用移动浏览器访问 Microsoft 365 SharePoint 网站、Office Online 中的文档或 Outlook Web App 中的电子邮件，将不会提示用户注册，也不会被阻止或报告违反策略。</span><span class="sxs-lookup"><span data-stu-id="7510a-148">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>

<span data-ttu-id="7510a-149">下图显示了当具有新设备的用户登录支持具有基本移动性和安全性的访问控制的应用时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="7510a-149">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="7510a-150">阻止用户访问应用中Microsoft 365资源，直到用户注册其设备。</span><span class="sxs-lookup"><span data-stu-id="7510a-150">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本移动性和安全性访问控制":::

> [!NOTE]
> <span data-ttu-id="7510a-152">在基本移动性和安全性 for Microsoft 365 商业标准版 中创建的策略和访问规则Exchange ActiveSync移动设备邮箱策略和在 Exchange 管理中心中创建的设备访问规则。</span><span class="sxs-lookup"><span data-stu-id="7510a-152">Policies and access rules created in Basic Mobility and Security for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="7510a-153">在设备注册基本移动性和安全性 for Microsoft 365 商业标准版 后，Exchange ActiveSync应用于该设备的任何移动设备邮箱策略或设备访问规则都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="7510a-153">After a device is enrolled in Basic Mobility and Security for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="7510a-154">若要详细了解Exchange ActiveSync，请参阅 Exchange ActiveSync [中的Exchange Online。](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)</span><span class="sxs-lookup"><span data-stu-id="7510a-154">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="7510a-155">移动设备的策略设置</span><span class="sxs-lookup"><span data-stu-id="7510a-155">Policy settings for mobile devices</span></span>

<span data-ttu-id="7510a-156">如果创建策略来阻止访问，但某些设置已打开，则当用户使用[Microsoft 365](capabilities.md)电子邮件和文档的访问控制中列出的受支持应用时，将阻止用户访问 Microsoft 365 资源。</span><span class="sxs-lookup"><span data-stu-id="7510a-156">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](capabilities.md).</span></span>

<span data-ttu-id="7510a-157">以下部分包含可阻止用户访问Microsoft 365资源的设置：</span><span class="sxs-lookup"><span data-stu-id="7510a-157">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="7510a-158">安全性</span><span class="sxs-lookup"><span data-stu-id="7510a-158">Security</span></span>

- <span data-ttu-id="7510a-159">加密</span><span class="sxs-lookup"><span data-stu-id="7510a-159">Encryption</span></span>

- <span data-ttu-id="7510a-160">已越狱</span><span class="sxs-lookup"><span data-stu-id="7510a-160">Jail broken</span></span>

- <span data-ttu-id="7510a-161">托管电子邮件配置文件</span><span class="sxs-lookup"><span data-stu-id="7510a-161">Managed email profile</span></span>

<span data-ttu-id="7510a-162">例如，下图显示了当已注册设备的用户不符合适用于其设备的移动设备管理策略中的安全设置时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="7510a-162">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="7510a-163">用户登录支持具有基本移动性和安全性的访问控制的应用。</span><span class="sxs-lookup"><span data-stu-id="7510a-163">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="7510a-164">在设备符合Microsoft 365要求之前，将阻止他们访问应用中的 Microsoft 365 资源。</span><span class="sxs-lookup"><span data-stu-id="7510a-164">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本移动性和安全性合规性消息":::

<span data-ttu-id="7510a-166">以下各节列出了可用于帮助保护和管理连接到组织资源的移动设备Microsoft 365设置。</span><span class="sxs-lookup"><span data-stu-id="7510a-166">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="7510a-167">安全设置</span><span class="sxs-lookup"><span data-stu-id="7510a-167">Security settings</span></span>

|<span data-ttu-id="7510a-168">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="7510a-168">**Setting name**</span></span>|<span data-ttu-id="7510a-169">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-169">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7510a-170">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-170">**Android 5 and later**</span></span>|<span data-ttu-id="7510a-171">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="7510a-171">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7510a-172">要求使用密码</span><span class="sxs-lookup"><span data-stu-id="7510a-172">Require a password</span></span>|<span data-ttu-id="7510a-173">是</span><span class="sxs-lookup"><span data-stu-id="7510a-173">Yes</span></span>|<span data-ttu-id="7510a-174">是</span><span class="sxs-lookup"><span data-stu-id="7510a-174">Yes</span></span>|<span data-ttu-id="7510a-175">是</span><span class="sxs-lookup"><span data-stu-id="7510a-175">Yes</span></span>|
|<span data-ttu-id="7510a-176">阻止简单密码</span><span class="sxs-lookup"><span data-stu-id="7510a-176">Prevent simple password</span></span>|<span data-ttu-id="7510a-177">是</span><span class="sxs-lookup"><span data-stu-id="7510a-177">Yes</span></span>|<span data-ttu-id="7510a-178">否</span><span class="sxs-lookup"><span data-stu-id="7510a-178">No</span></span>|<span data-ttu-id="7510a-179">否</span><span class="sxs-lookup"><span data-stu-id="7510a-179">No</span></span>|
|<span data-ttu-id="7510a-180">需要字母数字密码</span><span class="sxs-lookup"><span data-stu-id="7510a-180">Require an alphanumeric password</span></span>|<span data-ttu-id="7510a-181">是</span><span class="sxs-lookup"><span data-stu-id="7510a-181">Yes</span></span>|<span data-ttu-id="7510a-182">否</span><span class="sxs-lookup"><span data-stu-id="7510a-182">No</span></span>|<span data-ttu-id="7510a-183">否</span><span class="sxs-lookup"><span data-stu-id="7510a-183">No</span></span>|
|<span data-ttu-id="7510a-184">最短密码长度</span><span class="sxs-lookup"><span data-stu-id="7510a-184">Minimum password length</span></span> |<span data-ttu-id="7510a-185">是</span><span class="sxs-lookup"><span data-stu-id="7510a-185">Yes</span></span>|<span data-ttu-id="7510a-186">是</span><span class="sxs-lookup"><span data-stu-id="7510a-186">Yes</span></span>|<span data-ttu-id="7510a-187">是</span><span class="sxs-lookup"><span data-stu-id="7510a-187">Yes</span></span>|
|<span data-ttu-id="7510a-188">擦除设备之前登录失败次数</span><span class="sxs-lookup"><span data-stu-id="7510a-188">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="7510a-189">是</span><span class="sxs-lookup"><span data-stu-id="7510a-189">Yes</span></span>|<span data-ttu-id="7510a-190">是</span><span class="sxs-lookup"><span data-stu-id="7510a-190">Yes</span></span>|<span data-ttu-id="7510a-191">是</span><span class="sxs-lookup"><span data-stu-id="7510a-191">Yes</span></span>|
|<span data-ttu-id="7510a-192">设备锁定前不活动分钟数</span><span class="sxs-lookup"><span data-stu-id="7510a-192">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="7510a-193">是</span><span class="sxs-lookup"><span data-stu-id="7510a-193">Yes</span></span>|<span data-ttu-id="7510a-194">是</span><span class="sxs-lookup"><span data-stu-id="7510a-194">Yes</span></span>|<span data-ttu-id="7510a-195">是</span><span class="sxs-lookup"><span data-stu-id="7510a-195">Yes</span></span>|
|<span data-ttu-id="7510a-196">密码过期 (天数) </span><span class="sxs-lookup"><span data-stu-id="7510a-196">Password expiration (days)</span></span> |<span data-ttu-id="7510a-197">是</span><span class="sxs-lookup"><span data-stu-id="7510a-197">Yes</span></span>|<span data-ttu-id="7510a-198">是</span><span class="sxs-lookup"><span data-stu-id="7510a-198">Yes</span></span>|<span data-ttu-id="7510a-199">是</span><span class="sxs-lookup"><span data-stu-id="7510a-199">Yes</span></span>|
|<span data-ttu-id="7510a-200">记住密码历史记录并阻止重复使用</span><span class="sxs-lookup"><span data-stu-id="7510a-200">Remember password history and prevent reuse</span></span> |<span data-ttu-id="7510a-201">是</span><span class="sxs-lookup"><span data-stu-id="7510a-201">Yes</span></span>|<span data-ttu-id="7510a-202">是</span><span class="sxs-lookup"><span data-stu-id="7510a-202">Yes</span></span>|<span data-ttu-id="7510a-203">是</span><span class="sxs-lookup"><span data-stu-id="7510a-203">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="7510a-204">加密设置</span><span class="sxs-lookup"><span data-stu-id="7510a-204">Encryption settings</span></span>

|<span data-ttu-id="7510a-205">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="7510a-205">**Setting name**</span></span>|<span data-ttu-id="7510a-206">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-206">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7510a-207">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-207">**Android 5 and later**</span></span>|<span data-ttu-id="7510a-208">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="7510a-208">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7510a-209">要求对设备<sup>1 进行数据加密</sup></span><span class="sxs-lookup"><span data-stu-id="7510a-209">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="7510a-210">否</span><span class="sxs-lookup"><span data-stu-id="7510a-210">No</span></span>|<span data-ttu-id="7510a-211">是</span><span class="sxs-lookup"><span data-stu-id="7510a-211">Yes</span></span>|<span data-ttu-id="7510a-212">是</span><span class="sxs-lookup"><span data-stu-id="7510a-212">Yes</span></span>|

<span data-ttu-id="7510a-213"><sup>1</sup>使用 Samsung Knox，还可以要求对存储卡进行加密。</span><span class="sxs-lookup"><span data-stu-id="7510a-213"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span>

## <a name="jail-broken-setting"></a><span data-ttu-id="7510a-214">已越狱设置</span><span class="sxs-lookup"><span data-stu-id="7510a-214">Jail broken setting</span></span>

|<span data-ttu-id="7510a-215">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="7510a-215">**Setting name**</span></span>|<span data-ttu-id="7510a-216">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-216">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7510a-217">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-217">**Android 5 and later**</span></span>|<span data-ttu-id="7510a-218">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="7510a-218">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7510a-219">设备无法越狱或具有 root 权限</span><span class="sxs-lookup"><span data-stu-id="7510a-219">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="7510a-220">是</span><span class="sxs-lookup"><span data-stu-id="7510a-220">Yes</span></span>|<span data-ttu-id="7510a-221">是</span><span class="sxs-lookup"><span data-stu-id="7510a-221">Yes</span></span>|<span data-ttu-id="7510a-222">是</span><span class="sxs-lookup"><span data-stu-id="7510a-222">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="7510a-223">托管电子邮件配置文件选项</span><span class="sxs-lookup"><span data-stu-id="7510a-223">Managed email profile option</span></span>

<span data-ttu-id="7510a-224">以下选项可以阻止用户使用手动创建的电子邮件Microsoft 365访问他们的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7510a-224">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="7510a-225">iOS 设备上的用户必须先删除手动创建的电子邮件配置文件，然后才能访问电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7510a-225">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="7510a-226">删除配置文件后，将在设备上自动创建一个新配置文件。</span><span class="sxs-lookup"><span data-stu-id="7510a-226">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="7510a-227">有关最终用户如何合规的说明，请参阅已找到现有 [电子邮件帐户](/intune-user-help/existing-company-email-account-found)。</span><span class="sxs-lookup"><span data-stu-id="7510a-227">For instructions on how end users can get compliant, see [An existing email account was found](/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="7510a-228">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="7510a-228">**Setting name**</span></span>|<span data-ttu-id="7510a-229">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-229">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7510a-230">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-230">**Android 5 and later**</span></span>|<span data-ttu-id="7510a-231">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="7510a-231">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7510a-232">管理电子邮件配置文件</span><span class="sxs-lookup"><span data-stu-id="7510a-232">Email profile is managed</span></span> |<span data-ttu-id="7510a-233">是</span><span class="sxs-lookup"><span data-stu-id="7510a-233">Yes</span></span>|<span data-ttu-id="7510a-234">否</span><span class="sxs-lookup"><span data-stu-id="7510a-234">No</span></span>|<span data-ttu-id="7510a-235">否</span><span class="sxs-lookup"><span data-stu-id="7510a-235">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="7510a-236">云设置</span><span class="sxs-lookup"><span data-stu-id="7510a-236">Cloud settings</span></span>

|<span data-ttu-id="7510a-237">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="7510a-237">**Setting name**</span></span>|<span data-ttu-id="7510a-238">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-238">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7510a-239">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-239">**Android 5 and later**</span></span>|<span data-ttu-id="7510a-240">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="7510a-240">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7510a-241">需要加密备份</span><span class="sxs-lookup"><span data-stu-id="7510a-241">Require encrypted backup</span></span> |<span data-ttu-id="7510a-242">是</span><span class="sxs-lookup"><span data-stu-id="7510a-242">Yes</span></span>|<span data-ttu-id="7510a-243">否</span><span class="sxs-lookup"><span data-stu-id="7510a-243">No</span></span>|<span data-ttu-id="7510a-244">否</span><span class="sxs-lookup"><span data-stu-id="7510a-244">No</span></span>|
|<span data-ttu-id="7510a-245">阻止云备份</span><span class="sxs-lookup"><span data-stu-id="7510a-245">Block cloud backup</span></span> |<span data-ttu-id="7510a-246">是</span><span class="sxs-lookup"><span data-stu-id="7510a-246">Yes</span></span>|<span data-ttu-id="7510a-247">否</span><span class="sxs-lookup"><span data-stu-id="7510a-247">No</span></span>|<span data-ttu-id="7510a-248">否</span><span class="sxs-lookup"><span data-stu-id="7510a-248">No</span></span>|
|<span data-ttu-id="7510a-249">阻止文档同步</span><span class="sxs-lookup"><span data-stu-id="7510a-249">Block document synchronization</span></span> |<span data-ttu-id="7510a-250">是</span><span class="sxs-lookup"><span data-stu-id="7510a-250">Yes</span></span>|<span data-ttu-id="7510a-251">否</span><span class="sxs-lookup"><span data-stu-id="7510a-251">No</span></span>|<span data-ttu-id="7510a-252">否</span><span class="sxs-lookup"><span data-stu-id="7510a-252">No</span></span>|
|<span data-ttu-id="7510a-253">阻止照片同步</span><span class="sxs-lookup"><span data-stu-id="7510a-253">Block photo synchronization</span></span>  |<span data-ttu-id="7510a-254">是</span><span class="sxs-lookup"><span data-stu-id="7510a-254">Yes</span></span>|<span data-ttu-id="7510a-255">否</span><span class="sxs-lookup"><span data-stu-id="7510a-255">No</span></span>|<span data-ttu-id="7510a-256">否</span><span class="sxs-lookup"><span data-stu-id="7510a-256">No</span></span>|
|<span data-ttu-id="7510a-257">允许 Google 备份</span><span class="sxs-lookup"><span data-stu-id="7510a-257">Allow Google backup</span></span>  |<span data-ttu-id="7510a-258">无</span><span class="sxs-lookup"><span data-stu-id="7510a-258">N/A</span></span>|<span data-ttu-id="7510a-259">否</span><span class="sxs-lookup"><span data-stu-id="7510a-259">No</span></span>|<span data-ttu-id="7510a-260">是</span><span class="sxs-lookup"><span data-stu-id="7510a-260">Yes</span></span>|
|<span data-ttu-id="7510a-261">允许 Google 帐户自动同步</span><span class="sxs-lookup"><span data-stu-id="7510a-261">Allow Google account auto sync</span></span>  |<span data-ttu-id="7510a-262">无</span><span class="sxs-lookup"><span data-stu-id="7510a-262">N/A</span></span>|<span data-ttu-id="7510a-263">否</span><span class="sxs-lookup"><span data-stu-id="7510a-263">No</span></span>|<span data-ttu-id="7510a-264">是</span><span class="sxs-lookup"><span data-stu-id="7510a-264">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="7510a-265">系统设置</span><span class="sxs-lookup"><span data-stu-id="7510a-265">System settings</span></span>

|<span data-ttu-id="7510a-266">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="7510a-266">**Setting name**</span></span>|<span data-ttu-id="7510a-267">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-267">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7510a-268">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-268">**Android 5 and later**</span></span>|<span data-ttu-id="7510a-269">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="7510a-269">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7510a-270">阻止屏幕捕获</span><span class="sxs-lookup"><span data-stu-id="7510a-270">Block screen capture</span></span> |<span data-ttu-id="7510a-271">是</span><span class="sxs-lookup"><span data-stu-id="7510a-271">Yes</span></span>|<span data-ttu-id="7510a-272">否</span><span class="sxs-lookup"><span data-stu-id="7510a-272">No</span></span>|<span data-ttu-id="7510a-273">是</span><span class="sxs-lookup"><span data-stu-id="7510a-273">Yes</span></span>|
|<span data-ttu-id="7510a-274">阻止从设备发送诊断数据</span><span class="sxs-lookup"><span data-stu-id="7510a-274">Block sending diagnostic data from device</span></span> |<span data-ttu-id="7510a-275">是</span><span class="sxs-lookup"><span data-stu-id="7510a-275">Yes</span></span>|<span data-ttu-id="7510a-276">否</span><span class="sxs-lookup"><span data-stu-id="7510a-276">No</span></span>|<span data-ttu-id="7510a-277">是</span><span class="sxs-lookup"><span data-stu-id="7510a-277">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="7510a-278">应用程序设置</span><span class="sxs-lookup"><span data-stu-id="7510a-278">Application settings</span></span>

|<span data-ttu-id="7510a-279">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="7510a-279">**Setting name**</span></span>|<span data-ttu-id="7510a-280">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-280">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7510a-281">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-281">**Android 5 and later**</span></span>|<span data-ttu-id="7510a-282">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="7510a-282">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7510a-283">在设备上阻止视频会议</span><span class="sxs-lookup"><span data-stu-id="7510a-283">Block video conferences on device</span></span> |<span data-ttu-id="7510a-284">是</span><span class="sxs-lookup"><span data-stu-id="7510a-284">Yes</span></span>|<span data-ttu-id="7510a-285">否</span><span class="sxs-lookup"><span data-stu-id="7510a-285">No</span></span>|<span data-ttu-id="7510a-286">否</span><span class="sxs-lookup"><span data-stu-id="7510a-286">No</span></span>|
|<span data-ttu-id="7510a-287">阻止访问应用程序存储</span><span class="sxs-lookup"><span data-stu-id="7510a-287">Block access to application store</span></span> |<span data-ttu-id="7510a-288">是</span><span class="sxs-lookup"><span data-stu-id="7510a-288">Yes</span></span>|<span data-ttu-id="7510a-289">否</span><span class="sxs-lookup"><span data-stu-id="7510a-289">No</span></span>|<span data-ttu-id="7510a-290">是</span><span class="sxs-lookup"><span data-stu-id="7510a-290">Yes</span></span>|
|<span data-ttu-id="7510a-291">访问应用程序存储时需要密码</span><span class="sxs-lookup"><span data-stu-id="7510a-291">Require password when accessing application store</span></span> |<span data-ttu-id="7510a-292">否</span><span class="sxs-lookup"><span data-stu-id="7510a-292">No</span></span>|<span data-ttu-id="7510a-293">是</span><span class="sxs-lookup"><span data-stu-id="7510a-293">Yes</span></span>|<span data-ttu-id="7510a-294">是</span><span class="sxs-lookup"><span data-stu-id="7510a-294">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="7510a-295">设备功能设置</span><span class="sxs-lookup"><span data-stu-id="7510a-295">Device capabilities settings</span></span>

|<span data-ttu-id="7510a-296">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="7510a-296">**Setting name**</span></span>|<span data-ttu-id="7510a-297">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-297">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7510a-298">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-298">**Android 5 and later**</span></span>|<span data-ttu-id="7510a-299">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="7510a-299">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7510a-300">使用可移动存储阻止连接</span><span class="sxs-lookup"><span data-stu-id="7510a-300">Block connection with removable storage</span></span> |<span data-ttu-id="7510a-301">是</span><span class="sxs-lookup"><span data-stu-id="7510a-301">Yes</span></span>|<span data-ttu-id="7510a-302">是</span><span class="sxs-lookup"><span data-stu-id="7510a-302">Yes</span></span>|<span data-ttu-id="7510a-303">否</span><span class="sxs-lookup"><span data-stu-id="7510a-303">No</span></span>|
|<span data-ttu-id="7510a-304">阻止蓝牙连接</span><span class="sxs-lookup"><span data-stu-id="7510a-304">Block Bluetooth connection</span></span> |<span data-ttu-id="7510a-305">是</span><span class="sxs-lookup"><span data-stu-id="7510a-305">Yes</span></span>|<span data-ttu-id="7510a-306">是</span><span class="sxs-lookup"><span data-stu-id="7510a-306">Yes</span></span>|<span data-ttu-id="7510a-307">否</span><span class="sxs-lookup"><span data-stu-id="7510a-307">No</span></span>|

## <a name="additional-settings"></a><span data-ttu-id="7510a-308">其他设置</span><span class="sxs-lookup"><span data-stu-id="7510a-308">Additional settings</span></span>

<span data-ttu-id="7510a-309">您可以使用安全与合规中心 PowerShell cmdlet &其他策略设置。</span><span class="sxs-lookup"><span data-stu-id="7510a-309">You can set the following additional policy settings by using Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="7510a-310">有关详细信息，请参阅安全与 [&中心 PowerShell。](/powershell/exchange/scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="7510a-310">For more information, see [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

|<span data-ttu-id="7510a-311">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="7510a-311">**Setting name**</span></span>|<span data-ttu-id="7510a-312">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-312">**iOS 7.1 and later**</span></span>|<span data-ttu-id="7510a-313">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="7510a-313">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7510a-314">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="7510a-314">CameraEnabled</span></span>|<span data-ttu-id="7510a-315">是</span><span class="sxs-lookup"><span data-stu-id="7510a-315">Yes</span></span>|<span data-ttu-id="7510a-316">是</span><span class="sxs-lookup"><span data-stu-id="7510a-316">Yes</span></span>|
|<span data-ttu-id="7510a-317">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="7510a-317">RegionRatings</span></span>|<span data-ttu-id="7510a-318">是</span><span class="sxs-lookup"><span data-stu-id="7510a-318">Yes</span></span>|<span data-ttu-id="7510a-319">否</span><span class="sxs-lookup"><span data-stu-id="7510a-319">No</span></span>|
|<span data-ttu-id="7510a-320">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="7510a-320">MoviesRatings</span></span>|<span data-ttu-id="7510a-321">是</span><span class="sxs-lookup"><span data-stu-id="7510a-321">Yes</span></span>|<span data-ttu-id="7510a-322">否</span><span class="sxs-lookup"><span data-stu-id="7510a-322">No</span></span>|
|<span data-ttu-id="7510a-323">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="7510a-323">TVShowsRating</span></span> |<span data-ttu-id="7510a-324">是</span><span class="sxs-lookup"><span data-stu-id="7510a-324">Yes</span></span>|<span data-ttu-id="7510a-325">否</span><span class="sxs-lookup"><span data-stu-id="7510a-325">No</span></span>|
|<span data-ttu-id="7510a-326">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="7510a-326">AppsRatings</span></span> |<span data-ttu-id="7510a-327">是</span><span class="sxs-lookup"><span data-stu-id="7510a-327">Yes</span></span>|<span data-ttu-id="7510a-328">否</span><span class="sxs-lookup"><span data-stu-id="7510a-328">No</span></span>|
|<span data-ttu-id="7510a-329">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="7510a-329">AllowVoiceDialing</span></span> |<span data-ttu-id="7510a-330">是</span><span class="sxs-lookup"><span data-stu-id="7510a-330">Yes</span></span>|<span data-ttu-id="7510a-331">否</span><span class="sxs-lookup"><span data-stu-id="7510a-331">No</span></span>|
|<span data-ttu-id="7510a-332">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="7510a-332">AllowVoiceAssistant</span></span> |<span data-ttu-id="7510a-333">是</span><span class="sxs-lookup"><span data-stu-id="7510a-333">Yes</span></span>|<span data-ttu-id="7510a-334">否</span><span class="sxs-lookup"><span data-stu-id="7510a-334">No</span></span>|
|<span data-ttu-id="7510a-335">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="7510a-335">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="7510a-336">是</span><span class="sxs-lookup"><span data-stu-id="7510a-336">Yes</span></span>|<span data-ttu-id="7510a-337">否</span><span class="sxs-lookup"><span data-stu-id="7510a-337">No</span></span>|
|<span data-ttu-id="7510a-338">AllowPassbookWhileLocked</span><span class="sxs-lookup"><span data-stu-id="7510a-338">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="7510a-339">是</span><span class="sxs-lookup"><span data-stu-id="7510a-339">Yes</span></span>|<span data-ttu-id="7510a-340">否</span><span class="sxs-lookup"><span data-stu-id="7510a-340">No</span></span>|
|<span data-ttu-id="7510a-341">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="7510a-341">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="7510a-342">是</span><span class="sxs-lookup"><span data-stu-id="7510a-342">Yes</span></span>|<span data-ttu-id="7510a-343">否</span><span class="sxs-lookup"><span data-stu-id="7510a-343">No</span></span>|
|<span data-ttu-id="7510a-344">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="7510a-344">PasswordQuality</span></span> |<span data-ttu-id="7510a-345">否</span><span class="sxs-lookup"><span data-stu-id="7510a-345">No</span></span>|<span data-ttu-id="7510a-346">是</span><span class="sxs-lookup"><span data-stu-id="7510a-346">Yes</span></span>|
|<span data-ttu-id="7510a-347">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="7510a-347">SystemSecurityTLS</span></span>  |<span data-ttu-id="7510a-348">是</span><span class="sxs-lookup"><span data-stu-id="7510a-348">Yes</span></span>|<span data-ttu-id="7510a-349">否</span><span class="sxs-lookup"><span data-stu-id="7510a-349">No</span></span>|
|<span data-ttu-id="7510a-350">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="7510a-350">WLANEnabled</span></span>  |<span data-ttu-id="7510a-351">否</span><span class="sxs-lookup"><span data-stu-id="7510a-351">No</span></span>|<span data-ttu-id="7510a-352">否</span><span class="sxs-lookup"><span data-stu-id="7510a-352">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="7510a-353">设置支持Windows</span><span class="sxs-lookup"><span data-stu-id="7510a-353">Settings supported by Windows</span></span>

<span data-ttu-id="7510a-354">可以通过将Windows 10注册为移动设备来管理这些设备。</span><span class="sxs-lookup"><span data-stu-id="7510a-354">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="7510a-355">部署适用的策略后，使用 Windows 10 设备的用户在首次使用内置电子邮件应用访问 Microsoft 365 电子邮件 (时，需要注册基本移动性和安全性) 。</span><span class="sxs-lookup"><span data-stu-id="7510a-355">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="7510a-356">注册为移动设备Windows 10设备支持以下设置。</span><span class="sxs-lookup"><span data-stu-id="7510a-356">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="7510a-357">此设置不会阻止用户访问Microsoft 365资源。</span><span class="sxs-lookup"><span data-stu-id="7510a-357">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="7510a-358">安全设置</span><span class="sxs-lookup"><span data-stu-id="7510a-358">Security settings</span></span>

- <span data-ttu-id="7510a-359">需要字母数字密码</span><span class="sxs-lookup"><span data-stu-id="7510a-359">Require an alphanumeric password</span></span>

- <span data-ttu-id="7510a-360">最短密码长度</span><span class="sxs-lookup"><span data-stu-id="7510a-360">Minimum password length</span></span>

- <span data-ttu-id="7510a-361">擦除设备之前登录失败次数</span><span class="sxs-lookup"><span data-stu-id="7510a-361">Number of sign-in failures before device is wiped</span></span>

- <span data-ttu-id="7510a-362">设备锁定前不活动分钟数</span><span class="sxs-lookup"><span data-stu-id="7510a-362">Minutes of inactivity before device is locked</span></span>

- <span data-ttu-id="7510a-363">密码过期 (天数) </span><span class="sxs-lookup"><span data-stu-id="7510a-363">Password expiration (days)</span></span>

- <span data-ttu-id="7510a-364">记住密码历史记录并阻止重复使用</span><span class="sxs-lookup"><span data-stu-id="7510a-364">Remember password history and prevent reuse</span></span>

> [!NOTE]
> <span data-ttu-id="7510a-365">以下设置管理密码仅控制本地Windows帐户。</span><span class="sxs-lookup"><span data-stu-id="7510a-365">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="7510a-366">Windows域或用户提供的Azure Active Directory帐户不受这些设置的影响。</span><span class="sxs-lookup"><span data-stu-id="7510a-366">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="7510a-367">系统设置</span><span class="sxs-lookup"><span data-stu-id="7510a-367">System settings</span></span>

<span data-ttu-id="7510a-368">阻止从设备发送诊断数据。</span><span class="sxs-lookup"><span data-stu-id="7510a-368">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="7510a-369">其他设置</span><span class="sxs-lookup"><span data-stu-id="7510a-369">Additional settings</span></span>

<span data-ttu-id="7510a-370">可以使用 PowerShell cmdlet 设置这些额外的策略设置：</span><span class="sxs-lookup"><span data-stu-id="7510a-370">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="7510a-371">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="7510a-371">AllowConvenienceLogon</span></span>

- <span data-ttu-id="7510a-372">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="7510a-372">UserAccountControlStatus</span></span>

- <span data-ttu-id="7510a-373">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="7510a-373">FirewallStatus</span></span>

- <span data-ttu-id="7510a-374">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="7510a-374">AutoUpdateStatus</span></span>

- <span data-ttu-id="7510a-375">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="7510a-375">AntiVirusStatus</span></span>

- <span data-ttu-id="7510a-376">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="7510a-376">AntiVirusSignatureStatus</span></span>

- <span data-ttu-id="7510a-377">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="7510a-377">SmartScreenEnabled</span></span>

- <span data-ttu-id="7510a-378">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="7510a-378">WorkFoldersSyncUrl</span></span>

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="7510a-379">远程擦除移动设备</span><span class="sxs-lookup"><span data-stu-id="7510a-379">Remotely wipe a mobile device</span></span>

<span data-ttu-id="7510a-380">如果设备丢失或被盗，可以通过从安全与合规中心 > 数据丢失防护设备管理 执行擦除来删除敏感的组织数据，并帮助阻止访问 Microsoft 365 & 组织  >  **资源**。</span><span class="sxs-lookup"><span data-stu-id="7510a-380">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="7510a-381">你可以执行选择性擦除以仅删除组织数据，也可以执行完全擦除，以从设备中删除所有信息，并还原到其出厂设置。</span><span class="sxs-lookup"><span data-stu-id="7510a-381">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="7510a-382">有关详细信息，请参阅 [Basic Mobility and Security](wipe-mobile-device.md)中的擦除移动设备。</span><span class="sxs-lookup"><span data-stu-id="7510a-382">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="7510a-383">相关内容</span><span class="sxs-lookup"><span data-stu-id="7510a-383">Related content</span></span>

<span data-ttu-id="7510a-384">[Microsoft 365 (](overview.md) Overview of Basic Mobility and Security for) </span><span class="sxs-lookup"><span data-stu-id="7510a-384">[Overview of Basic Mobility and Security for Microsoft 365](overview.md) (article)</span></span>\
<span data-ttu-id="7510a-385">[Create device security policies in Basic Mobility and Security](create-device-security-policies.md) (article) </span><span class="sxs-lookup"><span data-stu-id="7510a-385">[Create device security policies in Basic Mobility and Security](create-device-security-policies.md) (article)</span></span>