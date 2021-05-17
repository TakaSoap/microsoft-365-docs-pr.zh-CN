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
ms.openlocfilehash: 60de4e3f36427a69ecf0bf52e5dfd34f089991f3
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994969"
---
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="e524c-103">基本移动性和安全性的功能</span><span class="sxs-lookup"><span data-stu-id="e524c-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="e524c-104">基本移动性和安全性可帮助你保护和管理组织中授权 Microsoft 365 用户使用的移动设备，如 iPhone、iPad、Android 和 Windows Phones。</span><span class="sxs-lookup"><span data-stu-id="e524c-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="e524c-105">可以使用可帮助控制对组织的 Microsoft 365 电子邮件和文档的访问（对于受支持的移动设备和应用）的设置创建移动设备管理策略。</span><span class="sxs-lookup"><span data-stu-id="e524c-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="e524c-106">如果设备丢失或被盗，你可以远程擦除设备以删除敏感的组织信息。</span><span class="sxs-lookup"><span data-stu-id="e524c-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="e524c-107">支持的设备</span><span class="sxs-lookup"><span data-stu-id="e524c-107">Supported devices</span></span>

<span data-ttu-id="e524c-108">您可以使用基本移动性和安全性保护和管理以下设备。</span><span class="sxs-lookup"><span data-stu-id="e524c-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="e524c-109">iOS 11.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e524c-109">iOS 11.0 or later versions</span></span>

- <span data-ttu-id="e524c-110">Android 5.0 或更高版本<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e524c-110">Android 5.0 or later versions<sup>3</sup></span></span>

- <span data-ttu-id="e524c-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e524c-111">Windows 8.1<sup>1</sup></span></span>

- <span data-ttu-id="e524c-112">Windows 8.1 RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e524c-112">Windows 8.1 RT<sup>1</sup></span></span>

- <span data-ttu-id="e524c-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e524c-113">Windows 10<sup>2</sup></span></span>

- <span data-ttu-id="e524c-114">Windows 10 移动<sup>版 2</sup></span><span class="sxs-lookup"><span data-stu-id="e524c-114">Windows 10 Mobile<sup>2</sup></span></span>

<span data-ttu-id="e524c-115"><sup>1</sup>Windows 8.1 RT 设备的访问控制仅限于Exchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="e524c-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="e524c-116"><sup>2</sup>Windows 10 的访问控制需要包含 Azure AD Premium 的订阅，并且设备需要加入到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="e524c-116"><sup>2</sup>Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="e524c-117"><sup>3</sup>2020 年 6 月之后，超过 9 的 Android 版本无法管理密码设置，但 Samsung Knox 设备上除外。</span><span class="sxs-lookup"><span data-stu-id="e524c-117"><sup>3</sup>After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

>[!NOTE]
><span data-ttu-id="e524c-118">已注册较早操作系统版本的设备仍可以继续运行，尽管这些功能可能会在不另行通知的情况下更改。</span><span class="sxs-lookup"><span data-stu-id="e524c-118">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="e524c-119">如果你的组织中人员使用的移动设备不受基本移动性和安全性支持，你可能希望阻止 Exchange ActiveSync 应用访问这些设备的 Microsoft 365 电子邮件，以帮助使组织的数据更安全。</span><span class="sxs-lookup"><span data-stu-id="e524c-119">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="e524c-120">有关阻止访问Exchange ActiveSync，请参阅基本移动性和安全性中的管理 [设备访问设置](manage-device-access-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="e524c-120">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="e524c-121">Microsoft 365 电子邮件和文档的访问控制</span><span class="sxs-lookup"><span data-stu-id="e524c-121">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="e524c-122">下表中支持的不同类型的移动设备的应用提示用户注册基本移动性和安全性，其中存在适用于用户设备且用户之前尚未注册该设备的新移动设备管理策略。</span><span class="sxs-lookup"><span data-stu-id="e524c-122">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="e524c-123">如果用户的设备不符合策略，具体取决于策略的设置方式，用户可能会被阻止访问这些应用中的 Microsoft 365 资源，或者他们可能具有访问权限，但 Microsoft 365 报告违反策略。</span><span class="sxs-lookup"><span data-stu-id="e524c-123">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="e524c-124">**产品**</span><span class="sxs-lookup"><span data-stu-id="e524c-124">**Product**</span></span>|<span data-ttu-id="e524c-125">**iOS 10.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-125">**iOS 10.0 or later**</span></span>|<span data-ttu-id="e524c-126">**Android 5.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-126">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e524c-127">**Exchange** Exchange ActiveSync内置电子邮件和第三方应用（如 TouchDown）使用 Exchange ActiveSync 14.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="e524c-127">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="e524c-128">邮件</span><span class="sxs-lookup"><span data-stu-id="e524c-128">Mail</span></span> |<span data-ttu-id="e524c-129">电子邮件</span><span class="sxs-lookup"><span data-stu-id="e524c-129">Email</span></span> |
|<span data-ttu-id="e524c-130">**Office**  和  **OneDrive for Business**</span><span class="sxs-lookup"><span data-stu-id="e524c-130">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="e524c-131">Outlook</span><span class="sxs-lookup"><span data-stu-id="e524c-131">Outlook</span></span> </br><span data-ttu-id="e524c-132">OneDrive</span><span class="sxs-lookup"><span data-stu-id="e524c-132">OneDrive</span></span> </br><span data-ttu-id="e524c-133">Word</span><span class="sxs-lookup"><span data-stu-id="e524c-133">Word</span></span> </br><span data-ttu-id="e524c-134">Excel</span><span class="sxs-lookup"><span data-stu-id="e524c-134">Excel</span></span> </br><span data-ttu-id="e524c-135">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="e524c-135">PowerPoint</span></span>|<span data-ttu-id="e524c-136">**在手机和平板电脑上**：</span><span class="sxs-lookup"><span data-stu-id="e524c-136">**On phones and tablets**:</span></span><br/><span data-ttu-id="e524c-137">Outlook</span><span class="sxs-lookup"><span data-stu-id="e524c-137">Outlook</span></span> <br/> <span data-ttu-id="e524c-138">OneDrive</span><span class="sxs-lookup"><span data-stu-id="e524c-138">OneDrive</span></span> <br/> <span data-ttu-id="e524c-139">Word</span><span class="sxs-lookup"><span data-stu-id="e524c-139">Word</span></span> <br/> <span data-ttu-id="e524c-140">Excel</span><span class="sxs-lookup"><span data-stu-id="e524c-140">Excel</span></span> <br/> <span data-ttu-id="e524c-141">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="e524c-141">PowerPoint</span></span> <br/> <span data-ttu-id="e524c-142">**仅在电话上：**</span><span class="sxs-lookup"><span data-stu-id="e524c-142">**On phones only:**</span></span> <br/> <span data-ttu-id="e524c-143">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="e524c-143">Office Mobile</span></span> |

>[!NOTE]
- ><span data-ttu-id="e524c-144">支持 iOS 10.0 及更高版本包括 iPhone 和 iPad 设备。</span><span class="sxs-lookup"><span data-stu-id="e524c-144">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
- ><span data-ttu-id="e524c-145">基本安全性和移动性不支持管理 BlackBerry 操作系统设备。</span><span class="sxs-lookup"><span data-stu-id="e524c-145">Management of BlackBerry OS devices isn’t supported by Basic Security and Mobility.</span></span> <span data-ttu-id="e524c-146">使用 BlackBerry 商业云服务 (BBCS) 管理 BlackBerry 操作系统设备。</span><span class="sxs-lookup"><span data-stu-id="e524c-146">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="e524c-147">运行 Android 操作系统的 Blackberry 设备作为标准 Android 设备受到支持</span><span class="sxs-lookup"><span data-stu-id="e524c-147">Blackberry devices running Android OS are supported as standard Android devices</span></span>
- ><span data-ttu-id="e524c-148">如果用户使用移动浏览器访问 Microsoft 365 SharePoint 网站、Office Online 中的文档或 Outlook Web App 中的电子邮件，将不会提示用户注册，也不会被阻止或报告违反策略。</span><span class="sxs-lookup"><span data-stu-id="e524c-148">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>

<span data-ttu-id="e524c-149">下图显示了当具有新设备的用户登录支持具有基本移动性和安全性的访问控制的应用时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="e524c-149">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="e524c-150">用户被阻止访问应用中的 Microsoft 365 资源，直到用户注册其设备。</span><span class="sxs-lookup"><span data-stu-id="e524c-150">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本移动性和安全性访问控制":::

> [!NOTE]
> <span data-ttu-id="e524c-152">在 Microsoft 365 商业标准的基本移动性和安全性中创建的策略和访问规则将Exchange ActiveSync Exchange 管理中心中创建的移动设备邮箱策略和设备访问规则。</span><span class="sxs-lookup"><span data-stu-id="e524c-152">Policies and access rules created in Basic Mobility and Security for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="e524c-153">在 Microsoft 365 商业标准版的基本移动性和安全性中注册设备后，将忽略应用于该设备的任何 Exchange ActiveSync 移动设备邮箱策略或设备访问规则。</span><span class="sxs-lookup"><span data-stu-id="e524c-153">After a device is enrolled in Basic Mobility and Security for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="e524c-154">若要了解有关 exchange online Exchange ActiveSync，请参阅 [Exchange ActiveSync Exchange Online。](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)</span><span class="sxs-lookup"><span data-stu-id="e524c-154">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="e524c-155">移动设备的策略设置</span><span class="sxs-lookup"><span data-stu-id="e524c-155">Policy settings for mobile devices</span></span>

<span data-ttu-id="e524c-156">如果创建阻止访问的策略，但某些设置已打开，则当用户使用 Microsoft 365 电子邮件和文档的访问控制中列出的受支持应用时，将阻止用户访问 [Microsoft 365 资源](capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="e524c-156">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](capabilities.md).</span></span> 

<span data-ttu-id="e524c-157">以下部分包含可阻止用户访问 Microsoft 365 资源的设置：</span><span class="sxs-lookup"><span data-stu-id="e524c-157">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="e524c-158">安全性</span><span class="sxs-lookup"><span data-stu-id="e524c-158">Security</span></span>

- <span data-ttu-id="e524c-159">加密</span><span class="sxs-lookup"><span data-stu-id="e524c-159">Encryption</span></span>

- <span data-ttu-id="e524c-160">已越狱</span><span class="sxs-lookup"><span data-stu-id="e524c-160">Jail broken</span></span>

- <span data-ttu-id="e524c-161">托管电子邮件配置文件</span><span class="sxs-lookup"><span data-stu-id="e524c-161">Managed email profile</span></span>  

<span data-ttu-id="e524c-162">例如，下图显示了当已注册设备的用户不符合适用于其设备的移动设备管理策略中的安全设置时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="e524c-162">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="e524c-163">用户登录支持具有基本移动性和安全性的访问控制的应用。</span><span class="sxs-lookup"><span data-stu-id="e524c-163">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="e524c-164">在设备符合安全设置之前，将阻止他们访问应用中的 Microsoft 365 资源。</span><span class="sxs-lookup"><span data-stu-id="e524c-164">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本移动性和安全性合规性消息":::

<span data-ttu-id="e524c-166">以下部分列出了可用于帮助保护和管理连接到 Microsoft 365 组织资源的移动设备的策略设置。</span><span class="sxs-lookup"><span data-stu-id="e524c-166">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="e524c-167">安全设置</span><span class="sxs-lookup"><span data-stu-id="e524c-167">Security settings</span></span>

|<span data-ttu-id="e524c-168">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="e524c-168">**Setting name**</span></span>|<span data-ttu-id="e524c-169">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-169">**iOS 7.1 and later**</span></span>|<span data-ttu-id="e524c-170">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-170">**Android 5 and later**</span></span>|<span data-ttu-id="e524c-171">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="e524c-171">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e524c-172">要求使用密码</span><span class="sxs-lookup"><span data-stu-id="e524c-172">Require a password</span></span>|<span data-ttu-id="e524c-173">是</span><span class="sxs-lookup"><span data-stu-id="e524c-173">Yes</span></span>|<span data-ttu-id="e524c-174">是</span><span class="sxs-lookup"><span data-stu-id="e524c-174">Yes</span></span>|<span data-ttu-id="e524c-175">是</span><span class="sxs-lookup"><span data-stu-id="e524c-175">Yes</span></span>|
|<span data-ttu-id="e524c-176">阻止简单密码</span><span class="sxs-lookup"><span data-stu-id="e524c-176">Prevent simple password</span></span>|<span data-ttu-id="e524c-177">是</span><span class="sxs-lookup"><span data-stu-id="e524c-177">Yes</span></span>|<span data-ttu-id="e524c-178">否</span><span class="sxs-lookup"><span data-stu-id="e524c-178">No</span></span>|<span data-ttu-id="e524c-179">否</span><span class="sxs-lookup"><span data-stu-id="e524c-179">No</span></span>|
|<span data-ttu-id="e524c-180">需要字母数字密码</span><span class="sxs-lookup"><span data-stu-id="e524c-180">Require an alphanumeric password</span></span>|<span data-ttu-id="e524c-181">是</span><span class="sxs-lookup"><span data-stu-id="e524c-181">Yes</span></span>|<span data-ttu-id="e524c-182">否</span><span class="sxs-lookup"><span data-stu-id="e524c-182">No</span></span>|<span data-ttu-id="e524c-183">否</span><span class="sxs-lookup"><span data-stu-id="e524c-183">No</span></span>|
|<span data-ttu-id="e524c-184">最短密码长度</span><span class="sxs-lookup"><span data-stu-id="e524c-184">Minimum password length</span></span> |<span data-ttu-id="e524c-185">是</span><span class="sxs-lookup"><span data-stu-id="e524c-185">Yes</span></span>|<span data-ttu-id="e524c-186">是</span><span class="sxs-lookup"><span data-stu-id="e524c-186">Yes</span></span>|<span data-ttu-id="e524c-187">是</span><span class="sxs-lookup"><span data-stu-id="e524c-187">Yes</span></span>|
|<span data-ttu-id="e524c-188">擦除设备之前登录失败次数</span><span class="sxs-lookup"><span data-stu-id="e524c-188">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="e524c-189">是</span><span class="sxs-lookup"><span data-stu-id="e524c-189">Yes</span></span>|<span data-ttu-id="e524c-190">是</span><span class="sxs-lookup"><span data-stu-id="e524c-190">Yes</span></span>|<span data-ttu-id="e524c-191">是</span><span class="sxs-lookup"><span data-stu-id="e524c-191">Yes</span></span>|
|<span data-ttu-id="e524c-192">设备锁定前不活动分钟数</span><span class="sxs-lookup"><span data-stu-id="e524c-192">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="e524c-193">是</span><span class="sxs-lookup"><span data-stu-id="e524c-193">Yes</span></span>|<span data-ttu-id="e524c-194">是</span><span class="sxs-lookup"><span data-stu-id="e524c-194">Yes</span></span>|<span data-ttu-id="e524c-195">是</span><span class="sxs-lookup"><span data-stu-id="e524c-195">Yes</span></span>|
|<span data-ttu-id="e524c-196">密码过期 (天数) </span><span class="sxs-lookup"><span data-stu-id="e524c-196">Password expiration (days)</span></span> |<span data-ttu-id="e524c-197">是</span><span class="sxs-lookup"><span data-stu-id="e524c-197">Yes</span></span>|<span data-ttu-id="e524c-198">是</span><span class="sxs-lookup"><span data-stu-id="e524c-198">Yes</span></span>|<span data-ttu-id="e524c-199">是</span><span class="sxs-lookup"><span data-stu-id="e524c-199">Yes</span></span>|
|<span data-ttu-id="e524c-200">记住密码历史记录并阻止重复使用</span><span class="sxs-lookup"><span data-stu-id="e524c-200">Remember password history and prevent reuse</span></span> |<span data-ttu-id="e524c-201">是</span><span class="sxs-lookup"><span data-stu-id="e524c-201">Yes</span></span>|<span data-ttu-id="e524c-202">是</span><span class="sxs-lookup"><span data-stu-id="e524c-202">Yes</span></span>|<span data-ttu-id="e524c-203">是</span><span class="sxs-lookup"><span data-stu-id="e524c-203">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="e524c-204">加密设置</span><span class="sxs-lookup"><span data-stu-id="e524c-204">Encryption settings</span></span>

|<span data-ttu-id="e524c-205">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="e524c-205">**Setting name**</span></span>|<span data-ttu-id="e524c-206">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-206">**iOS 7.1 and later**</span></span>|<span data-ttu-id="e524c-207">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-207">**Android 5 and later**</span></span>|<span data-ttu-id="e524c-208">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="e524c-208">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e524c-209">要求对设备<sup>1 进行数据加密</sup></span><span class="sxs-lookup"><span data-stu-id="e524c-209">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="e524c-210">否</span><span class="sxs-lookup"><span data-stu-id="e524c-210">No</span></span>|<span data-ttu-id="e524c-211">是</span><span class="sxs-lookup"><span data-stu-id="e524c-211">Yes</span></span>|<span data-ttu-id="e524c-212">是</span><span class="sxs-lookup"><span data-stu-id="e524c-212">Yes</span></span>|

<span data-ttu-id="e524c-213"><sup>1</sup>使用 Samsung Knox，还可以要求对存储卡进行加密。</span><span class="sxs-lookup"><span data-stu-id="e524c-213"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span> 

## <a name="jail-broken-setting"></a><span data-ttu-id="e524c-214">已越狱设置</span><span class="sxs-lookup"><span data-stu-id="e524c-214">Jail broken setting</span></span> 

|<span data-ttu-id="e524c-215">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="e524c-215">**Setting name**</span></span>|<span data-ttu-id="e524c-216">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-216">**iOS 7.1 and later**</span></span>|<span data-ttu-id="e524c-217">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-217">**Android 5 and later**</span></span>|<span data-ttu-id="e524c-218">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="e524c-218">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e524c-219">设备无法越狱或具有 root 权限</span><span class="sxs-lookup"><span data-stu-id="e524c-219">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="e524c-220">是</span><span class="sxs-lookup"><span data-stu-id="e524c-220">Yes</span></span>|<span data-ttu-id="e524c-221">是</span><span class="sxs-lookup"><span data-stu-id="e524c-221">Yes</span></span>|<span data-ttu-id="e524c-222">是</span><span class="sxs-lookup"><span data-stu-id="e524c-222">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="e524c-223">托管电子邮件配置文件选项</span><span class="sxs-lookup"><span data-stu-id="e524c-223">Managed email profile option</span></span> 

<span data-ttu-id="e524c-224">以下选项可以阻止用户使用手动创建的电子邮件Microsoft 365访问他们的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e524c-224">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="e524c-225">iOS 设备上的用户必须先删除手动创建的电子邮件配置文件，然后才能访问电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e524c-225">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="e524c-226">删除配置文件后，将在设备上自动创建一个新配置文件。</span><span class="sxs-lookup"><span data-stu-id="e524c-226">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="e524c-227">有关最终用户如何合规的说明，请参阅已找到现有 [电子邮件帐户](/intune-user-help/existing-company-email-account-found)。</span><span class="sxs-lookup"><span data-stu-id="e524c-227">For instructions on how end users can get compliant, see [An existing email account was found](/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="e524c-228">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="e524c-228">**Setting name**</span></span>|<span data-ttu-id="e524c-229">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-229">**iOS 7.1 and later**</span></span>|<span data-ttu-id="e524c-230">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-230">**Android 5 and later**</span></span>|<span data-ttu-id="e524c-231">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="e524c-231">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e524c-232">管理电子邮件配置文件</span><span class="sxs-lookup"><span data-stu-id="e524c-232">Email profile is managed</span></span> |<span data-ttu-id="e524c-233">是</span><span class="sxs-lookup"><span data-stu-id="e524c-233">Yes</span></span>|<span data-ttu-id="e524c-234">否</span><span class="sxs-lookup"><span data-stu-id="e524c-234">No</span></span>|<span data-ttu-id="e524c-235">否</span><span class="sxs-lookup"><span data-stu-id="e524c-235">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="e524c-236">云设置</span><span class="sxs-lookup"><span data-stu-id="e524c-236">Cloud settings</span></span>

|<span data-ttu-id="e524c-237">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="e524c-237">**Setting name**</span></span>|<span data-ttu-id="e524c-238">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-238">**iOS 7.1 and later**</span></span>|<span data-ttu-id="e524c-239">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-239">**Android 5 and later**</span></span>|<span data-ttu-id="e524c-240">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="e524c-240">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e524c-241">需要加密备份</span><span class="sxs-lookup"><span data-stu-id="e524c-241">Require encrypted backup</span></span> |<span data-ttu-id="e524c-242">是</span><span class="sxs-lookup"><span data-stu-id="e524c-242">Yes</span></span>|<span data-ttu-id="e524c-243">否</span><span class="sxs-lookup"><span data-stu-id="e524c-243">No</span></span>|<span data-ttu-id="e524c-244">否</span><span class="sxs-lookup"><span data-stu-id="e524c-244">No</span></span>|
|<span data-ttu-id="e524c-245">阻止云备份</span><span class="sxs-lookup"><span data-stu-id="e524c-245">Block cloud backup</span></span> |<span data-ttu-id="e524c-246">是</span><span class="sxs-lookup"><span data-stu-id="e524c-246">Yes</span></span>|<span data-ttu-id="e524c-247">否</span><span class="sxs-lookup"><span data-stu-id="e524c-247">No</span></span>|<span data-ttu-id="e524c-248">否</span><span class="sxs-lookup"><span data-stu-id="e524c-248">No</span></span>|
|<span data-ttu-id="e524c-249">阻止文档同步</span><span class="sxs-lookup"><span data-stu-id="e524c-249">Block document synchronization</span></span> |<span data-ttu-id="e524c-250">是</span><span class="sxs-lookup"><span data-stu-id="e524c-250">Yes</span></span>|<span data-ttu-id="e524c-251">否</span><span class="sxs-lookup"><span data-stu-id="e524c-251">No</span></span>|<span data-ttu-id="e524c-252">否</span><span class="sxs-lookup"><span data-stu-id="e524c-252">No</span></span>|
|<span data-ttu-id="e524c-253">阻止照片同步</span><span class="sxs-lookup"><span data-stu-id="e524c-253">Block photo synchronization</span></span>  |<span data-ttu-id="e524c-254">是</span><span class="sxs-lookup"><span data-stu-id="e524c-254">Yes</span></span>|<span data-ttu-id="e524c-255">否</span><span class="sxs-lookup"><span data-stu-id="e524c-255">No</span></span>|<span data-ttu-id="e524c-256">否</span><span class="sxs-lookup"><span data-stu-id="e524c-256">No</span></span>|
|<span data-ttu-id="e524c-257">允许 Google 备份</span><span class="sxs-lookup"><span data-stu-id="e524c-257">Allow Google backup</span></span>  |<span data-ttu-id="e524c-258">不适用</span><span class="sxs-lookup"><span data-stu-id="e524c-258">N/A</span></span>|<span data-ttu-id="e524c-259">否</span><span class="sxs-lookup"><span data-stu-id="e524c-259">No</span></span>|<span data-ttu-id="e524c-260">是</span><span class="sxs-lookup"><span data-stu-id="e524c-260">Yes</span></span>|
|<span data-ttu-id="e524c-261">允许 Google 帐户自动同步</span><span class="sxs-lookup"><span data-stu-id="e524c-261">Allow Google account auto sync</span></span>  |<span data-ttu-id="e524c-262">不适用</span><span class="sxs-lookup"><span data-stu-id="e524c-262">N/A</span></span>|<span data-ttu-id="e524c-263">否</span><span class="sxs-lookup"><span data-stu-id="e524c-263">No</span></span>|<span data-ttu-id="e524c-264">是</span><span class="sxs-lookup"><span data-stu-id="e524c-264">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="e524c-265">系统设置</span><span class="sxs-lookup"><span data-stu-id="e524c-265">System settings</span></span>

|<span data-ttu-id="e524c-266">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="e524c-266">**Setting name**</span></span>|<span data-ttu-id="e524c-267">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-267">**iOS 7.1 and later**</span></span>|<span data-ttu-id="e524c-268">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-268">**Android 5 and later**</span></span>|<span data-ttu-id="e524c-269">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="e524c-269">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e524c-270">阻止屏幕捕获</span><span class="sxs-lookup"><span data-stu-id="e524c-270">Block screen capture</span></span> |<span data-ttu-id="e524c-271">是</span><span class="sxs-lookup"><span data-stu-id="e524c-271">Yes</span></span>|<span data-ttu-id="e524c-272">否</span><span class="sxs-lookup"><span data-stu-id="e524c-272">No</span></span>|<span data-ttu-id="e524c-273">是</span><span class="sxs-lookup"><span data-stu-id="e524c-273">Yes</span></span>|
|<span data-ttu-id="e524c-274">阻止从设备发送诊断数据</span><span class="sxs-lookup"><span data-stu-id="e524c-274">Block sending diagnostic data from device</span></span> |<span data-ttu-id="e524c-275">是</span><span class="sxs-lookup"><span data-stu-id="e524c-275">Yes</span></span>|<span data-ttu-id="e524c-276">否</span><span class="sxs-lookup"><span data-stu-id="e524c-276">No</span></span>|<span data-ttu-id="e524c-277">是</span><span class="sxs-lookup"><span data-stu-id="e524c-277">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="e524c-278">应用程序设置</span><span class="sxs-lookup"><span data-stu-id="e524c-278">Application settings</span></span>

|<span data-ttu-id="e524c-279">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="e524c-279">**Setting name**</span></span>|<span data-ttu-id="e524c-280">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-280">**iOS 7.1 and later**</span></span>|<span data-ttu-id="e524c-281">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-281">**Android 5 and later**</span></span>|<span data-ttu-id="e524c-282">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="e524c-282">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e524c-283">在设备上阻止视频会议</span><span class="sxs-lookup"><span data-stu-id="e524c-283">Block video conferences on device</span></span> |<span data-ttu-id="e524c-284">是</span><span class="sxs-lookup"><span data-stu-id="e524c-284">Yes</span></span>|<span data-ttu-id="e524c-285">否</span><span class="sxs-lookup"><span data-stu-id="e524c-285">No</span></span>|<span data-ttu-id="e524c-286">否</span><span class="sxs-lookup"><span data-stu-id="e524c-286">No</span></span>|
|<span data-ttu-id="e524c-287">阻止访问应用程序存储</span><span class="sxs-lookup"><span data-stu-id="e524c-287">Block access to application store</span></span> |<span data-ttu-id="e524c-288">是</span><span class="sxs-lookup"><span data-stu-id="e524c-288">Yes</span></span>|<span data-ttu-id="e524c-289">否</span><span class="sxs-lookup"><span data-stu-id="e524c-289">No</span></span>|<span data-ttu-id="e524c-290">是</span><span class="sxs-lookup"><span data-stu-id="e524c-290">Yes</span></span>|
|<span data-ttu-id="e524c-291">访问应用程序存储时需要密码</span><span class="sxs-lookup"><span data-stu-id="e524c-291">Require password when accessing application store</span></span> |<span data-ttu-id="e524c-292">否</span><span class="sxs-lookup"><span data-stu-id="e524c-292">No</span></span>|<span data-ttu-id="e524c-293">是</span><span class="sxs-lookup"><span data-stu-id="e524c-293">Yes</span></span>|<span data-ttu-id="e524c-294">是</span><span class="sxs-lookup"><span data-stu-id="e524c-294">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="e524c-295">设备功能设置</span><span class="sxs-lookup"><span data-stu-id="e524c-295">Device capabilities settings</span></span>

|<span data-ttu-id="e524c-296">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="e524c-296">**Setting name**</span></span>|<span data-ttu-id="e524c-297">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-297">**iOS 7.1 and later**</span></span>|<span data-ttu-id="e524c-298">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-298">**Android 5 and later**</span></span>|<span data-ttu-id="e524c-299">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="e524c-299">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e524c-300">使用可移动存储阻止连接</span><span class="sxs-lookup"><span data-stu-id="e524c-300">Block connection with removable storage</span></span> |<span data-ttu-id="e524c-301">是</span><span class="sxs-lookup"><span data-stu-id="e524c-301">Yes</span></span>|<span data-ttu-id="e524c-302">是</span><span class="sxs-lookup"><span data-stu-id="e524c-302">Yes</span></span>|<span data-ttu-id="e524c-303">否</span><span class="sxs-lookup"><span data-stu-id="e524c-303">No</span></span>|
|<span data-ttu-id="e524c-304">阻止蓝牙连接</span><span class="sxs-lookup"><span data-stu-id="e524c-304">Block Bluetooth connection</span></span> |<span data-ttu-id="e524c-305">是</span><span class="sxs-lookup"><span data-stu-id="e524c-305">Yes</span></span>|<span data-ttu-id="e524c-306">是</span><span class="sxs-lookup"><span data-stu-id="e524c-306">Yes</span></span>|<span data-ttu-id="e524c-307">否</span><span class="sxs-lookup"><span data-stu-id="e524c-307">No</span></span>|

## <a name="additional-settings"></a><span data-ttu-id="e524c-308">其他设置</span><span class="sxs-lookup"><span data-stu-id="e524c-308">Additional settings</span></span>

<span data-ttu-id="e524c-309">您可以使用安全与合规中心 PowerShell cmdlet &其他策略设置。</span><span class="sxs-lookup"><span data-stu-id="e524c-309">You can set the following additional policy settings by using Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="e524c-310">有关详细信息，请参阅安全与 [&中心 PowerShell。](/powershell/exchange/scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="e524c-310">For more information, see [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

|<span data-ttu-id="e524c-311">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="e524c-311">**Setting name**</span></span>|<span data-ttu-id="e524c-312">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-312">**iOS 7.1 and later**</span></span>|<span data-ttu-id="e524c-313">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="e524c-313">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e524c-314">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="e524c-314">CameraEnabled</span></span>|<span data-ttu-id="e524c-315">是</span><span class="sxs-lookup"><span data-stu-id="e524c-315">Yes</span></span>|<span data-ttu-id="e524c-316">是</span><span class="sxs-lookup"><span data-stu-id="e524c-316">Yes</span></span>|
|<span data-ttu-id="e524c-317">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="e524c-317">RegionRatings</span></span>|<span data-ttu-id="e524c-318">是</span><span class="sxs-lookup"><span data-stu-id="e524c-318">Yes</span></span>|<span data-ttu-id="e524c-319">否</span><span class="sxs-lookup"><span data-stu-id="e524c-319">No</span></span>|
|<span data-ttu-id="e524c-320">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="e524c-320">MoviesRatings</span></span>|<span data-ttu-id="e524c-321">是</span><span class="sxs-lookup"><span data-stu-id="e524c-321">Yes</span></span>|<span data-ttu-id="e524c-322">否</span><span class="sxs-lookup"><span data-stu-id="e524c-322">No</span></span>|
|<span data-ttu-id="e524c-323">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="e524c-323">TVShowsRating</span></span> |<span data-ttu-id="e524c-324">是</span><span class="sxs-lookup"><span data-stu-id="e524c-324">Yes</span></span>|<span data-ttu-id="e524c-325">否</span><span class="sxs-lookup"><span data-stu-id="e524c-325">No</span></span>|
|<span data-ttu-id="e524c-326">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="e524c-326">AppsRatings</span></span> |<span data-ttu-id="e524c-327">是</span><span class="sxs-lookup"><span data-stu-id="e524c-327">Yes</span></span>|<span data-ttu-id="e524c-328">否</span><span class="sxs-lookup"><span data-stu-id="e524c-328">No</span></span>|
|<span data-ttu-id="e524c-329">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="e524c-329">AllowVoiceDialing</span></span> |<span data-ttu-id="e524c-330">是</span><span class="sxs-lookup"><span data-stu-id="e524c-330">Yes</span></span>|<span data-ttu-id="e524c-331">否</span><span class="sxs-lookup"><span data-stu-id="e524c-331">No</span></span>|
|<span data-ttu-id="e524c-332">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="e524c-332">AllowVoiceAssistant</span></span> |<span data-ttu-id="e524c-333">是</span><span class="sxs-lookup"><span data-stu-id="e524c-333">Yes</span></span>|<span data-ttu-id="e524c-334">否</span><span class="sxs-lookup"><span data-stu-id="e524c-334">No</span></span>|
|<span data-ttu-id="e524c-335">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="e524c-335">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="e524c-336">是</span><span class="sxs-lookup"><span data-stu-id="e524c-336">Yes</span></span>|<span data-ttu-id="e524c-337">否</span><span class="sxs-lookup"><span data-stu-id="e524c-337">No</span></span>|
|<span data-ttu-id="e524c-338">AllowPassbookWhileLocked</span><span class="sxs-lookup"><span data-stu-id="e524c-338">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="e524c-339">是</span><span class="sxs-lookup"><span data-stu-id="e524c-339">Yes</span></span>|<span data-ttu-id="e524c-340">否</span><span class="sxs-lookup"><span data-stu-id="e524c-340">No</span></span>|
|<span data-ttu-id="e524c-341">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="e524c-341">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="e524c-342">是</span><span class="sxs-lookup"><span data-stu-id="e524c-342">Yes</span></span>|<span data-ttu-id="e524c-343">否</span><span class="sxs-lookup"><span data-stu-id="e524c-343">No</span></span>|
|<span data-ttu-id="e524c-344">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="e524c-344">PasswordQuality</span></span> |<span data-ttu-id="e524c-345">否</span><span class="sxs-lookup"><span data-stu-id="e524c-345">No</span></span>|<span data-ttu-id="e524c-346">是</span><span class="sxs-lookup"><span data-stu-id="e524c-346">Yes</span></span>|
|<span data-ttu-id="e524c-347">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="e524c-347">SystemSecurityTLS</span></span>  |<span data-ttu-id="e524c-348">是</span><span class="sxs-lookup"><span data-stu-id="e524c-348">Yes</span></span>|<span data-ttu-id="e524c-349">否</span><span class="sxs-lookup"><span data-stu-id="e524c-349">No</span></span>|
|<span data-ttu-id="e524c-350">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="e524c-350">WLANEnabled</span></span>  |<span data-ttu-id="e524c-351">否</span><span class="sxs-lookup"><span data-stu-id="e524c-351">No</span></span>|<span data-ttu-id="e524c-352">否</span><span class="sxs-lookup"><span data-stu-id="e524c-352">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="e524c-353">Windows 支持的设置</span><span class="sxs-lookup"><span data-stu-id="e524c-353">Settings supported by Windows</span></span>

<span data-ttu-id="e524c-354">可以通过将 Windows 10 设备注册为移动设备来管理它们。</span><span class="sxs-lookup"><span data-stu-id="e524c-354">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="e524c-355">部署适用的策略后，使用 Windows 10 设备的用户在首次使用内置电子邮件应用访问其 Microsoft 365 电子邮件 (需要 Azure AD Premium 订阅) 时，需要注册基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="e524c-355">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="e524c-356">注册为移动设备的 Windows 10 设备支持以下设置。</span><span class="sxs-lookup"><span data-stu-id="e524c-356">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="e524c-357">此设置不会阻止用户访问 Microsoft 365 资源。</span><span class="sxs-lookup"><span data-stu-id="e524c-357">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="e524c-358">安全设置</span><span class="sxs-lookup"><span data-stu-id="e524c-358">Security settings</span></span>

- <span data-ttu-id="e524c-359">需要字母数字密码</span><span class="sxs-lookup"><span data-stu-id="e524c-359">Require an alphanumeric password</span></span>

- <span data-ttu-id="e524c-360">最短密码长度</span><span class="sxs-lookup"><span data-stu-id="e524c-360">Minimum password length</span></span>

- <span data-ttu-id="e524c-361">擦除设备之前登录失败次数</span><span class="sxs-lookup"><span data-stu-id="e524c-361">Number of sign-in failures before device is wiped</span></span>

- <span data-ttu-id="e524c-362">设备锁定前不活动分钟数</span><span class="sxs-lookup"><span data-stu-id="e524c-362">Minutes of inactivity before device is locked</span></span>

- <span data-ttu-id="e524c-363">密码过期 (天数) </span><span class="sxs-lookup"><span data-stu-id="e524c-363">Password expiration (days)</span></span>

- <span data-ttu-id="e524c-364">记住密码历史记录并阻止重复使用</span><span class="sxs-lookup"><span data-stu-id="e524c-364">Remember password history and prevent reuse</span></span>

>[!NOTE]
><span data-ttu-id="e524c-365">以下设置管理密码仅控制本地 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="e524c-365">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="e524c-366">通过加入域或 Azure Active Directory 提供的 Windows 帐户不受这些设置的影响。</span><span class="sxs-lookup"><span data-stu-id="e524c-366">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="e524c-367">系统设置</span><span class="sxs-lookup"><span data-stu-id="e524c-367">System settings</span></span>

<span data-ttu-id="e524c-368">阻止从设备发送诊断数据。</span><span class="sxs-lookup"><span data-stu-id="e524c-368">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="e524c-369">其他设置</span><span class="sxs-lookup"><span data-stu-id="e524c-369">Additional settings</span></span>

<span data-ttu-id="e524c-370">可以使用 PowerShell cmdlet 设置这些额外的策略设置：</span><span class="sxs-lookup"><span data-stu-id="e524c-370">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="e524c-371">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="e524c-371">AllowConvenienceLogon</span></span>

- <span data-ttu-id="e524c-372">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="e524c-372">UserAccountControlStatus</span></span>

- <span data-ttu-id="e524c-373">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="e524c-373">FirewallStatus</span></span>

- <span data-ttu-id="e524c-374">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="e524c-374">AutoUpdateStatus</span></span>

- <span data-ttu-id="e524c-375">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="e524c-375">AntiVirusStatus</span></span>

- <span data-ttu-id="e524c-376">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="e524c-376">AntiVirusSignatureStatus</span></span>

- <span data-ttu-id="e524c-377">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="e524c-377">SmartScreenEnabled</span></span>

- <span data-ttu-id="e524c-378">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="e524c-378">WorkFoldersSyncUrl</span></span>

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="e524c-379">远程擦除移动设备</span><span class="sxs-lookup"><span data-stu-id="e524c-379">Remotely wipe a mobile device</span></span>

<span data-ttu-id="e524c-380">如果设备丢失或被盗，可以通过从安全与合规中心 > 数据丢失防护设备管理 执行擦除来删除敏感的组织数据，并帮助阻止访问 Microsoft 36 & 5 **组织**  >  **资源**。</span><span class="sxs-lookup"><span data-stu-id="e524c-380">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="e524c-381">你可以执行选择性擦除以仅删除组织数据，也可以执行完全擦除，以从设备中删除所有信息，并还原到其出厂设置。</span><span class="sxs-lookup"><span data-stu-id="e524c-381">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="e524c-382">有关详细信息，请参阅 [Basic Mobility and Security](wipe-mobile-device.md)中的擦除移动设备。</span><span class="sxs-lookup"><span data-stu-id="e524c-382">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e524c-383">相关主题</span><span class="sxs-lookup"><span data-stu-id="e524c-383">Related topics</span></span>

[<span data-ttu-id="e524c-384">Microsoft 365 的基本移动性和安全性概述</span><span class="sxs-lookup"><span data-stu-id="e524c-384">Overview of Basic Mobility and Security for Microsoft 365</span></span>](overview.md)

[<span data-ttu-id="e524c-385">在基本移动性和安全性中创建设备安全策略</span><span class="sxs-lookup"><span data-stu-id="e524c-385">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies.md)