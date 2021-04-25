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
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="d82b0-103">基本移动性和安全性的功能</span><span class="sxs-lookup"><span data-stu-id="d82b0-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="d82b0-104">基本移动性和安全性可帮助你保护和管理组织中授权 Microsoft 365 用户使用的移动设备，如 iPhone、iPad、Android 和 Windows Phones。</span><span class="sxs-lookup"><span data-stu-id="d82b0-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="d82b0-105">可以使用可帮助控制对组织的 Microsoft 365 电子邮件和文档的访问（对于受支持的移动设备和应用）的设置创建移动设备管理策略。</span><span class="sxs-lookup"><span data-stu-id="d82b0-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="d82b0-106">如果设备丢失或被盗，你可以远程擦除设备以删除敏感的组织信息。</span><span class="sxs-lookup"><span data-stu-id="d82b0-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="d82b0-107">支持的设备</span><span class="sxs-lookup"><span data-stu-id="d82b0-107">Supported devices</span></span>

<span data-ttu-id="d82b0-108">您可以使用基本移动性和安全性保护和管理以下设备。</span><span class="sxs-lookup"><span data-stu-id="d82b0-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="d82b0-109">iOS 11.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d82b0-109">iOS 11.0 or later versions</span></span>

- <span data-ttu-id="d82b0-110">Android 5.0 或更高版本<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d82b0-110">Android 5.0 or later versions<sup>3</sup></span></span>

- <span data-ttu-id="d82b0-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d82b0-111">Windows 8.1<sup>1</sup></span></span>

- <span data-ttu-id="d82b0-112">Windows 8.1 RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d82b0-112">Windows 8.1 RT<sup>1</sup></span></span>

- <span data-ttu-id="d82b0-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d82b0-113">Windows 10<sup>2</sup></span></span>

- <span data-ttu-id="d82b0-114">Windows 10 移动<sup>版 2</sup></span><span class="sxs-lookup"><span data-stu-id="d82b0-114">Windows 10 Mobile<sup>2</sup></span></span>

<span data-ttu-id="d82b0-115"><sup>1</sup>Windows 8.1 RT 设备的访问控制仅限于Exchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="d82b0-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="d82b0-116"><sup>2</sup>Windows 10 的访问控制需要包含 Azure AD Premium 的订阅，并且设备需要加入到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="d82b0-116"><sup>2</sup>Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="d82b0-117"><sup>3</sup>2020 年 6 月之后，超过 9 的 Android 版本无法管理密码设置，但 Samsung Knox 设备上除外。</span><span class="sxs-lookup"><span data-stu-id="d82b0-117"><sup>3</sup>After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

>[!NOTE]
><span data-ttu-id="d82b0-118">已注册较早操作系统版本的设备仍可以继续运行，尽管这些功能可能会在不另行通知的情况下更改。</span><span class="sxs-lookup"><span data-stu-id="d82b0-118">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="d82b0-119">如果你的组织中人员使用的移动设备不受基本移动性和安全性支持，你可能希望阻止 Exchange ActiveSync 应用访问这些设备的 Microsoft 365 电子邮件，以帮助使组织的数据更安全。</span><span class="sxs-lookup"><span data-stu-id="d82b0-119">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="d82b0-120">有关阻止访问Exchange ActiveSync，请参阅基本移动性和安全性中的管理 [设备访问设置](manage-device-access-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="d82b0-120">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="d82b0-121">Microsoft 365 电子邮件和文档的访问控制</span><span class="sxs-lookup"><span data-stu-id="d82b0-121">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="d82b0-122">下表中支持的不同类型的移动设备的应用提示用户注册基本移动性和安全性，其中存在适用于用户设备且用户之前尚未注册该设备的新移动设备管理策略。</span><span class="sxs-lookup"><span data-stu-id="d82b0-122">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="d82b0-123">如果用户的设备不符合策略，具体取决于策略的设置方式，用户可能会被阻止访问这些应用中的 Microsoft 365 资源，或者他们可能具有访问权限，但 Microsoft 365 报告违反策略。</span><span class="sxs-lookup"><span data-stu-id="d82b0-123">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="d82b0-124">**Product**</span><span class="sxs-lookup"><span data-stu-id="d82b0-124">**Product**</span></span>|<span data-ttu-id="d82b0-125">**iOS 10.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-125">**iOS 10.0 or later**</span></span>|<span data-ttu-id="d82b0-126">**Android 5.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-126">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d82b0-127">**Exchange** Exchange ActiveSync内置电子邮件和第三方应用（如 TouchDown）使用 Exchange ActiveSync 14.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d82b0-127">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="d82b0-128">邮件</span><span class="sxs-lookup"><span data-stu-id="d82b0-128">Mail</span></span> |<span data-ttu-id="d82b0-129">电子邮件</span><span class="sxs-lookup"><span data-stu-id="d82b0-129">Email</span></span> |
|<span data-ttu-id="d82b0-130">**Office**  和  **OneDrive for Business**</span><span class="sxs-lookup"><span data-stu-id="d82b0-130">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="d82b0-131">Outlook</span><span class="sxs-lookup"><span data-stu-id="d82b0-131">Outlook</span></span> </br><span data-ttu-id="d82b0-132">OneDrive</span><span class="sxs-lookup"><span data-stu-id="d82b0-132">OneDrive</span></span> </br><span data-ttu-id="d82b0-133">Word</span><span class="sxs-lookup"><span data-stu-id="d82b0-133">Word</span></span> </br><span data-ttu-id="d82b0-134">Excel</span><span class="sxs-lookup"><span data-stu-id="d82b0-134">Excel</span></span> </br><span data-ttu-id="d82b0-135">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d82b0-135">PowerPoint</span></span>|<span data-ttu-id="d82b0-136">**在手机和平板电脑上**：</span><span class="sxs-lookup"><span data-stu-id="d82b0-136">**On phones and tablets**:</span></span><br/><span data-ttu-id="d82b0-137">Outlook</span><span class="sxs-lookup"><span data-stu-id="d82b0-137">Outlook</span></span> <br/> <span data-ttu-id="d82b0-138">OneDrive</span><span class="sxs-lookup"><span data-stu-id="d82b0-138">OneDrive</span></span> <br/> <span data-ttu-id="d82b0-139">Word</span><span class="sxs-lookup"><span data-stu-id="d82b0-139">Word</span></span> <br/> <span data-ttu-id="d82b0-140">Excel</span><span class="sxs-lookup"><span data-stu-id="d82b0-140">Excel</span></span> <br/> <span data-ttu-id="d82b0-141">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d82b0-141">PowerPoint</span></span> <br/> <span data-ttu-id="d82b0-142">**仅在电话上：**</span><span class="sxs-lookup"><span data-stu-id="d82b0-142">**On phones only:**</span></span> <br/> <span data-ttu-id="d82b0-143">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="d82b0-143">Office Mobile</span></span> |

>[!NOTE]
- ><span data-ttu-id="d82b0-144">支持 iOS 10.0 及更高版本包括 iPhone 和 iPad 设备。</span><span class="sxs-lookup"><span data-stu-id="d82b0-144">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
- ><span data-ttu-id="d82b0-145">基本安全性和移动性不支持管理 BlackBerry 操作系统设备。</span><span class="sxs-lookup"><span data-stu-id="d82b0-145">Management of BlackBerry OS devices isn’t supported by Basic Security and Mobility.</span></span> <span data-ttu-id="d82b0-146">使用 BlackBerry 商业云服务 (BBCS) 管理 BlackBerry 操作系统设备。</span><span class="sxs-lookup"><span data-stu-id="d82b0-146">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="d82b0-147">运行 Android 操作系统的 Blackberry 设备作为标准 Android 设备受到支持</span><span class="sxs-lookup"><span data-stu-id="d82b0-147">Blackberry devices running Android OS are supported as standard Android devices</span></span>
- ><span data-ttu-id="d82b0-148">如果用户使用移动浏览器访问 Microsoft 365 SharePoint 网站、Office Online 中的文档或 Outlook Web App 中的电子邮件，将不会提示用户注册，也不会被阻止或报告违反策略。</span><span class="sxs-lookup"><span data-stu-id="d82b0-148">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>

<span data-ttu-id="d82b0-149">下图显示了当具有新设备的用户登录支持具有基本移动性和安全性的访问控制的应用时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="d82b0-149">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="d82b0-150">用户被阻止访问应用中的 Microsoft 365 资源，直到用户注册其设备。</span><span class="sxs-lookup"><span data-stu-id="d82b0-150">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本移动性和安全性访问控制":::

> [!NOTE]
> <span data-ttu-id="d82b0-152">在 Microsoft 365 商业标准的基本移动性和安全性中创建的策略和访问规则将Exchange ActiveSync Exchange 管理中心中创建的移动设备邮箱策略和设备访问规则。</span><span class="sxs-lookup"><span data-stu-id="d82b0-152">Policies and access rules created in Basic Mobility and Security for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="d82b0-153">在 Microsoft 365 商业标准版的基本移动性和安全性中注册设备后，将忽略应用于该设备的任何 Exchange ActiveSync 移动设备邮箱策略或设备访问规则。</span><span class="sxs-lookup"><span data-stu-id="d82b0-153">After a device is enrolled in Basic Mobility and Security for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="d82b0-154">若要了解有关 exchange online Exchange ActiveSync，请参阅 [Exchange ActiveSync Exchange Online。](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)</span><span class="sxs-lookup"><span data-stu-id="d82b0-154">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="d82b0-155">移动设备的策略设置</span><span class="sxs-lookup"><span data-stu-id="d82b0-155">Policy settings for mobile devices</span></span>

<span data-ttu-id="d82b0-156">如果创建阻止访问的策略，但某些设置已打开，则当用户使用 Microsoft 365 电子邮件和文档的访问控制中列出的受支持应用时，将阻止用户访问 [Microsoft 365 资源](capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="d82b0-156">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](capabilities.md).</span></span> 

<span data-ttu-id="d82b0-157">以下部分包含可阻止用户访问 Microsoft 365 资源的设置：</span><span class="sxs-lookup"><span data-stu-id="d82b0-157">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="d82b0-158">安全性</span><span class="sxs-lookup"><span data-stu-id="d82b0-158">Security</span></span>

- <span data-ttu-id="d82b0-159">加密</span><span class="sxs-lookup"><span data-stu-id="d82b0-159">Encryption</span></span>

- <span data-ttu-id="d82b0-160">已越狱</span><span class="sxs-lookup"><span data-stu-id="d82b0-160">Jail broken</span></span>

- <span data-ttu-id="d82b0-161">托管电子邮件配置文件</span><span class="sxs-lookup"><span data-stu-id="d82b0-161">Managed email profile</span></span>  

<span data-ttu-id="d82b0-162">例如，下图显示了当已注册设备的用户不符合适用于其设备的移动设备管理策略中的安全设置时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="d82b0-162">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="d82b0-163">用户登录支持具有基本移动性和安全性的访问控制的应用。</span><span class="sxs-lookup"><span data-stu-id="d82b0-163">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="d82b0-164">在设备符合安全设置之前，将阻止他们访问应用中的 Microsoft 365 资源。</span><span class="sxs-lookup"><span data-stu-id="d82b0-164">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本移动性和安全性合规性消息":::

<span data-ttu-id="d82b0-166">以下部分列出了可用于帮助保护和管理连接到 Microsoft 365 组织资源的移动设备的策略设置。</span><span class="sxs-lookup"><span data-stu-id="d82b0-166">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="d82b0-167">安全设置</span><span class="sxs-lookup"><span data-stu-id="d82b0-167">Security settings</span></span>

|<span data-ttu-id="d82b0-168">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="d82b0-168">**Setting name**</span></span>|<span data-ttu-id="d82b0-169">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-169">**iOS 7.1 and later**</span></span>|<span data-ttu-id="d82b0-170">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-170">**Android 5 and later**</span></span>|<span data-ttu-id="d82b0-171">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="d82b0-171">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d82b0-172">要求使用密码</span><span class="sxs-lookup"><span data-stu-id="d82b0-172">Require a password</span></span>|<span data-ttu-id="d82b0-173">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-173">Yes</span></span>|<span data-ttu-id="d82b0-174">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-174">Yes</span></span>|<span data-ttu-id="d82b0-175">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-175">Yes</span></span>|
|<span data-ttu-id="d82b0-176">阻止简单密码</span><span class="sxs-lookup"><span data-stu-id="d82b0-176">Prevent simple password</span></span>|<span data-ttu-id="d82b0-177">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-177">Yes</span></span>|<span data-ttu-id="d82b0-178">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-178">No</span></span>|<span data-ttu-id="d82b0-179">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-179">No</span></span>|
|<span data-ttu-id="d82b0-180">需要字母数字密码</span><span class="sxs-lookup"><span data-stu-id="d82b0-180">Require an alphanumeric password</span></span>|<span data-ttu-id="d82b0-181">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-181">Yes</span></span>|<span data-ttu-id="d82b0-182">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-182">No</span></span>|<span data-ttu-id="d82b0-183">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-183">No</span></span>|
|<span data-ttu-id="d82b0-184">最短密码长度</span><span class="sxs-lookup"><span data-stu-id="d82b0-184">Minimum password length</span></span> |<span data-ttu-id="d82b0-185">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-185">Yes</span></span>|<span data-ttu-id="d82b0-186">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-186">Yes</span></span>|<span data-ttu-id="d82b0-187">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-187">Yes</span></span>|
|<span data-ttu-id="d82b0-188">擦除设备之前登录失败次数</span><span class="sxs-lookup"><span data-stu-id="d82b0-188">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="d82b0-189">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-189">Yes</span></span>|<span data-ttu-id="d82b0-190">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-190">Yes</span></span>|<span data-ttu-id="d82b0-191">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-191">Yes</span></span>|
|<span data-ttu-id="d82b0-192">设备锁定前不活动分钟数</span><span class="sxs-lookup"><span data-stu-id="d82b0-192">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="d82b0-193">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-193">Yes</span></span>|<span data-ttu-id="d82b0-194">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-194">Yes</span></span>|<span data-ttu-id="d82b0-195">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-195">Yes</span></span>|
|<span data-ttu-id="d82b0-196">密码过期 (天数) </span><span class="sxs-lookup"><span data-stu-id="d82b0-196">Password expiration (days)</span></span> |<span data-ttu-id="d82b0-197">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-197">Yes</span></span>|<span data-ttu-id="d82b0-198">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-198">Yes</span></span>|<span data-ttu-id="d82b0-199">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-199">Yes</span></span>|
|<span data-ttu-id="d82b0-200">记住密码历史记录并阻止重复使用</span><span class="sxs-lookup"><span data-stu-id="d82b0-200">Remember password history and prevent reuse</span></span> |<span data-ttu-id="d82b0-201">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-201">Yes</span></span>|<span data-ttu-id="d82b0-202">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-202">Yes</span></span>|<span data-ttu-id="d82b0-203">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-203">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="d82b0-204">加密设置</span><span class="sxs-lookup"><span data-stu-id="d82b0-204">Encryption settings</span></span>

|<span data-ttu-id="d82b0-205">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="d82b0-205">**Setting name**</span></span>|<span data-ttu-id="d82b0-206">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-206">**iOS 7.1 and later**</span></span>|<span data-ttu-id="d82b0-207">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-207">**Android 5 and later**</span></span>|<span data-ttu-id="d82b0-208">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="d82b0-208">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d82b0-209">要求对设备<sup>1 进行数据加密</sup></span><span class="sxs-lookup"><span data-stu-id="d82b0-209">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="d82b0-210">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-210">No</span></span>|<span data-ttu-id="d82b0-211">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-211">Yes</span></span>|<span data-ttu-id="d82b0-212">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-212">Yes</span></span>|

<span data-ttu-id="d82b0-213"><sup>1</sup>使用 Samsung Knox，还可以要求对存储卡进行加密。</span><span class="sxs-lookup"><span data-stu-id="d82b0-213"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span> 

## <a name="jail-broken-setting"></a><span data-ttu-id="d82b0-214">已越狱设置</span><span class="sxs-lookup"><span data-stu-id="d82b0-214">Jail broken setting</span></span> 

|<span data-ttu-id="d82b0-215">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="d82b0-215">**Setting name**</span></span>|<span data-ttu-id="d82b0-216">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-216">**iOS 7.1 and later**</span></span>|<span data-ttu-id="d82b0-217">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-217">**Android 5 and later**</span></span>|<span data-ttu-id="d82b0-218">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="d82b0-218">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d82b0-219">设备无法越狱或具有 root 权限</span><span class="sxs-lookup"><span data-stu-id="d82b0-219">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="d82b0-220">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-220">Yes</span></span>|<span data-ttu-id="d82b0-221">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-221">Yes</span></span>|<span data-ttu-id="d82b0-222">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-222">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="d82b0-223">托管电子邮件配置文件选项</span><span class="sxs-lookup"><span data-stu-id="d82b0-223">Managed email profile option</span></span> 

<span data-ttu-id="d82b0-224">以下选项可以阻止用户使用手动创建的电子邮件配置文件访问其 Microsoft 365 电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d82b0-224">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="d82b0-225">iOS 设备上的用户必须先删除手动创建的电子邮件配置文件，然后才能访问电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d82b0-225">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="d82b0-226">删除配置文件后，将在设备上自动创建一个新配置文件。</span><span class="sxs-lookup"><span data-stu-id="d82b0-226">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="d82b0-227">有关最终用户如何合规的说明，请参阅已找到现有 [电子邮件帐户](/intune-user-help/existing-company-email-account-found)。</span><span class="sxs-lookup"><span data-stu-id="d82b0-227">For instructions on how end users can get compliant, see [An existing email account was found](/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="d82b0-228">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="d82b0-228">**Setting name**</span></span>|<span data-ttu-id="d82b0-229">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-229">**iOS 7.1 and later**</span></span>|<span data-ttu-id="d82b0-230">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-230">**Android 5 and later**</span></span>|<span data-ttu-id="d82b0-231">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="d82b0-231">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d82b0-232">管理电子邮件配置文件</span><span class="sxs-lookup"><span data-stu-id="d82b0-232">Email profile is managed</span></span> |<span data-ttu-id="d82b0-233">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-233">Yes</span></span>|<span data-ttu-id="d82b0-234">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-234">No</span></span>|<span data-ttu-id="d82b0-235">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-235">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="d82b0-236">云设置</span><span class="sxs-lookup"><span data-stu-id="d82b0-236">Cloud settings</span></span>

|<span data-ttu-id="d82b0-237">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="d82b0-237">**Setting name**</span></span>|<span data-ttu-id="d82b0-238">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-238">**iOS 7.1 and later**</span></span>|<span data-ttu-id="d82b0-239">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-239">**Android 5 and later**</span></span>|<span data-ttu-id="d82b0-240">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="d82b0-240">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d82b0-241">需要加密备份</span><span class="sxs-lookup"><span data-stu-id="d82b0-241">Require encrypted backup</span></span> |<span data-ttu-id="d82b0-242">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-242">Yes</span></span>|<span data-ttu-id="d82b0-243">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-243">No</span></span>|<span data-ttu-id="d82b0-244">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-244">No</span></span>|
|<span data-ttu-id="d82b0-245">阻止云备份</span><span class="sxs-lookup"><span data-stu-id="d82b0-245">Block cloud backup</span></span> |<span data-ttu-id="d82b0-246">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-246">Yes</span></span>|<span data-ttu-id="d82b0-247">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-247">No</span></span>|<span data-ttu-id="d82b0-248">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-248">No</span></span>|
|<span data-ttu-id="d82b0-249">阻止文档同步</span><span class="sxs-lookup"><span data-stu-id="d82b0-249">Block document synchronization</span></span> |<span data-ttu-id="d82b0-250">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-250">Yes</span></span>|<span data-ttu-id="d82b0-251">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-251">No</span></span>|<span data-ttu-id="d82b0-252">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-252">No</span></span>|
|<span data-ttu-id="d82b0-253">阻止照片同步</span><span class="sxs-lookup"><span data-stu-id="d82b0-253">Block photo synchronization</span></span>  |<span data-ttu-id="d82b0-254">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-254">Yes</span></span>|<span data-ttu-id="d82b0-255">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-255">No</span></span>|<span data-ttu-id="d82b0-256">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-256">No</span></span>|
|<span data-ttu-id="d82b0-257">允许 Google 备份</span><span class="sxs-lookup"><span data-stu-id="d82b0-257">Allow Google backup</span></span>  |<span data-ttu-id="d82b0-258">不适用</span><span class="sxs-lookup"><span data-stu-id="d82b0-258">N/A</span></span>|<span data-ttu-id="d82b0-259">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-259">No</span></span>|<span data-ttu-id="d82b0-260">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-260">Yes</span></span>|
|<span data-ttu-id="d82b0-261">允许 Google 帐户自动同步</span><span class="sxs-lookup"><span data-stu-id="d82b0-261">Allow Google account auto sync</span></span>  |<span data-ttu-id="d82b0-262">不适用</span><span class="sxs-lookup"><span data-stu-id="d82b0-262">N/A</span></span>|<span data-ttu-id="d82b0-263">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-263">No</span></span>|<span data-ttu-id="d82b0-264">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-264">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="d82b0-265">系统设置</span><span class="sxs-lookup"><span data-stu-id="d82b0-265">System settings</span></span>

|<span data-ttu-id="d82b0-266">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="d82b0-266">**Setting name**</span></span>|<span data-ttu-id="d82b0-267">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-267">**iOS 7.1 and later**</span></span>|<span data-ttu-id="d82b0-268">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-268">**Android 5 and later**</span></span>|<span data-ttu-id="d82b0-269">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="d82b0-269">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d82b0-270">阻止屏幕捕获</span><span class="sxs-lookup"><span data-stu-id="d82b0-270">Block screen capture</span></span> |<span data-ttu-id="d82b0-271">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-271">Yes</span></span>|<span data-ttu-id="d82b0-272">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-272">No</span></span>|<span data-ttu-id="d82b0-273">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-273">Yes</span></span>|
|<span data-ttu-id="d82b0-274">阻止从设备发送诊断数据</span><span class="sxs-lookup"><span data-stu-id="d82b0-274">Block sending diagnostic data from device</span></span> |<span data-ttu-id="d82b0-275">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-275">Yes</span></span>|<span data-ttu-id="d82b0-276">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-276">No</span></span>|<span data-ttu-id="d82b0-277">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-277">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="d82b0-278">应用程序设置</span><span class="sxs-lookup"><span data-stu-id="d82b0-278">Application settings</span></span>

|<span data-ttu-id="d82b0-279">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="d82b0-279">**Setting name**</span></span>|<span data-ttu-id="d82b0-280">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-280">**iOS 7.1 and later**</span></span>|<span data-ttu-id="d82b0-281">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-281">**Android 5 and later**</span></span>|<span data-ttu-id="d82b0-282">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="d82b0-282">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d82b0-283">在设备上阻止视频会议</span><span class="sxs-lookup"><span data-stu-id="d82b0-283">Block video conferences on device</span></span> |<span data-ttu-id="d82b0-284">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-284">Yes</span></span>|<span data-ttu-id="d82b0-285">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-285">No</span></span>|<span data-ttu-id="d82b0-286">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-286">No</span></span>|
|<span data-ttu-id="d82b0-287">阻止访问应用程序存储</span><span class="sxs-lookup"><span data-stu-id="d82b0-287">Block access to application store</span></span> |<span data-ttu-id="d82b0-288">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-288">Yes</span></span>|<span data-ttu-id="d82b0-289">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-289">No</span></span>|<span data-ttu-id="d82b0-290">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-290">Yes</span></span>|
|<span data-ttu-id="d82b0-291">访问应用程序存储时需要密码</span><span class="sxs-lookup"><span data-stu-id="d82b0-291">Require password when accessing application store</span></span> |<span data-ttu-id="d82b0-292">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-292">No</span></span>|<span data-ttu-id="d82b0-293">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-293">Yes</span></span>|<span data-ttu-id="d82b0-294">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-294">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="d82b0-295">设备功能设置</span><span class="sxs-lookup"><span data-stu-id="d82b0-295">Device capabilities settings</span></span>

|<span data-ttu-id="d82b0-296">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="d82b0-296">**Setting name**</span></span>|<span data-ttu-id="d82b0-297">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-297">**iOS 7.1 and later**</span></span>|<span data-ttu-id="d82b0-298">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-298">**Android 5 and later**</span></span>|<span data-ttu-id="d82b0-299">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="d82b0-299">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d82b0-300">使用可移动存储阻止连接</span><span class="sxs-lookup"><span data-stu-id="d82b0-300">Block connection with removable storage</span></span> |<span data-ttu-id="d82b0-301">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-301">Yes</span></span>|<span data-ttu-id="d82b0-302">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-302">Yes</span></span>|<span data-ttu-id="d82b0-303">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-303">No</span></span>|
|<span data-ttu-id="d82b0-304">阻止蓝牙连接</span><span class="sxs-lookup"><span data-stu-id="d82b0-304">Block Bluetooth connection</span></span> |<span data-ttu-id="d82b0-305">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-305">Yes</span></span>|<span data-ttu-id="d82b0-306">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-306">Yes</span></span>|<span data-ttu-id="d82b0-307">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-307">No</span></span>|

## <a name="additional-settings"></a><span data-ttu-id="d82b0-308">其他设置</span><span class="sxs-lookup"><span data-stu-id="d82b0-308">Additional settings</span></span>

<span data-ttu-id="d82b0-309">您可以使用安全与合规中心 PowerShell cmdlet &其他策略设置。</span><span class="sxs-lookup"><span data-stu-id="d82b0-309">You can set the following additional policy settings by using Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="d82b0-310">有关详细信息，请参阅安全与 [&中心 PowerShell。](/powershell/exchange/scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="d82b0-310">For more information, see [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

|<span data-ttu-id="d82b0-311">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="d82b0-311">**Setting name**</span></span>|<span data-ttu-id="d82b0-312">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-312">**iOS 7.1 and later**</span></span>|<span data-ttu-id="d82b0-313">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="d82b0-313">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d82b0-314">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="d82b0-314">CameraEnabled</span></span>|<span data-ttu-id="d82b0-315">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-315">Yes</span></span>|<span data-ttu-id="d82b0-316">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-316">Yes</span></span>|
|<span data-ttu-id="d82b0-317">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="d82b0-317">RegionRatings</span></span>|<span data-ttu-id="d82b0-318">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-318">Yes</span></span>|<span data-ttu-id="d82b0-319">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-319">No</span></span>|
|<span data-ttu-id="d82b0-320">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="d82b0-320">MoviesRatings</span></span>|<span data-ttu-id="d82b0-321">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-321">Yes</span></span>|<span data-ttu-id="d82b0-322">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-322">No</span></span>|
|<span data-ttu-id="d82b0-323">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="d82b0-323">TVShowsRating</span></span> |<span data-ttu-id="d82b0-324">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-324">Yes</span></span>|<span data-ttu-id="d82b0-325">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-325">No</span></span>|
|<span data-ttu-id="d82b0-326">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="d82b0-326">AppsRatings</span></span> |<span data-ttu-id="d82b0-327">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-327">Yes</span></span>|<span data-ttu-id="d82b0-328">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-328">No</span></span>|
|<span data-ttu-id="d82b0-329">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="d82b0-329">AllowVoiceDialing</span></span> |<span data-ttu-id="d82b0-330">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-330">Yes</span></span>|<span data-ttu-id="d82b0-331">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-331">No</span></span>|
|<span data-ttu-id="d82b0-332">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="d82b0-332">AllowVoiceAssistant</span></span> |<span data-ttu-id="d82b0-333">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-333">Yes</span></span>|<span data-ttu-id="d82b0-334">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-334">No</span></span>|
|<span data-ttu-id="d82b0-335">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="d82b0-335">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="d82b0-336">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-336">Yes</span></span>|<span data-ttu-id="d82b0-337">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-337">No</span></span>|
|<span data-ttu-id="d82b0-338">AllowPassbookWhileLocked</span><span class="sxs-lookup"><span data-stu-id="d82b0-338">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="d82b0-339">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-339">Yes</span></span>|<span data-ttu-id="d82b0-340">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-340">No</span></span>|
|<span data-ttu-id="d82b0-341">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="d82b0-341">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="d82b0-342">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-342">Yes</span></span>|<span data-ttu-id="d82b0-343">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-343">No</span></span>|
|<span data-ttu-id="d82b0-344">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="d82b0-344">PasswordQuality</span></span> |<span data-ttu-id="d82b0-345">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-345">No</span></span>|<span data-ttu-id="d82b0-346">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-346">Yes</span></span>|
|<span data-ttu-id="d82b0-347">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="d82b0-347">SystemSecurityTLS</span></span>  |<span data-ttu-id="d82b0-348">是</span><span class="sxs-lookup"><span data-stu-id="d82b0-348">Yes</span></span>|<span data-ttu-id="d82b0-349">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-349">No</span></span>|
|<span data-ttu-id="d82b0-350">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="d82b0-350">WLANEnabled</span></span>  |<span data-ttu-id="d82b0-351">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-351">No</span></span>|<span data-ttu-id="d82b0-352">否</span><span class="sxs-lookup"><span data-stu-id="d82b0-352">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="d82b0-353">Windows 支持的设置</span><span class="sxs-lookup"><span data-stu-id="d82b0-353">Settings supported by Windows</span></span>

<span data-ttu-id="d82b0-354">可以通过将 Windows 10 设备注册为移动设备来管理它们。</span><span class="sxs-lookup"><span data-stu-id="d82b0-354">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="d82b0-355">部署适用的策略后，使用 Windows 10 设备的用户在首次使用内置电子邮件应用访问其 Microsoft 365 电子邮件 (需要 Azure AD Premium 订阅) 时，需要注册基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="d82b0-355">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="d82b0-356">注册为移动设备的 Windows 10 设备支持以下设置。</span><span class="sxs-lookup"><span data-stu-id="d82b0-356">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="d82b0-357">此设置不会阻止用户访问 Microsoft 365 资源。</span><span class="sxs-lookup"><span data-stu-id="d82b0-357">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="d82b0-358">安全设置</span><span class="sxs-lookup"><span data-stu-id="d82b0-358">Security settings</span></span>

- <span data-ttu-id="d82b0-359">需要字母数字密码</span><span class="sxs-lookup"><span data-stu-id="d82b0-359">Require an alphanumeric password</span></span>

- <span data-ttu-id="d82b0-360">最短密码长度</span><span class="sxs-lookup"><span data-stu-id="d82b0-360">Minimum password length</span></span>

- <span data-ttu-id="d82b0-361">擦除设备之前登录失败次数</span><span class="sxs-lookup"><span data-stu-id="d82b0-361">Number of sign-in failures before device is wiped</span></span>

- <span data-ttu-id="d82b0-362">设备锁定前不活动分钟数</span><span class="sxs-lookup"><span data-stu-id="d82b0-362">Minutes of inactivity before device is locked</span></span>

- <span data-ttu-id="d82b0-363">密码过期 (天数) </span><span class="sxs-lookup"><span data-stu-id="d82b0-363">Password expiration (days)</span></span>

- <span data-ttu-id="d82b0-364">记住密码历史记录并阻止重复使用</span><span class="sxs-lookup"><span data-stu-id="d82b0-364">Remember password history and prevent reuse</span></span>

>[!NOTE]
><span data-ttu-id="d82b0-365">以下设置管理密码仅控制本地 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="d82b0-365">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="d82b0-366">通过加入域或 Azure Active Directory 提供的 Windows 帐户不受这些设置的影响。</span><span class="sxs-lookup"><span data-stu-id="d82b0-366">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="d82b0-367">系统设置</span><span class="sxs-lookup"><span data-stu-id="d82b0-367">System settings</span></span>

<span data-ttu-id="d82b0-368">阻止从设备发送诊断数据。</span><span class="sxs-lookup"><span data-stu-id="d82b0-368">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="d82b0-369">其他设置</span><span class="sxs-lookup"><span data-stu-id="d82b0-369">Additional settings</span></span>

<span data-ttu-id="d82b0-370">可以使用 PowerShell cmdlet 设置这些额外的策略设置：</span><span class="sxs-lookup"><span data-stu-id="d82b0-370">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="d82b0-371">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="d82b0-371">AllowConvenienceLogon</span></span>

- <span data-ttu-id="d82b0-372">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="d82b0-372">UserAccountControlStatus</span></span>

- <span data-ttu-id="d82b0-373">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="d82b0-373">FirewallStatus</span></span>

- <span data-ttu-id="d82b0-374">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="d82b0-374">AutoUpdateStatus</span></span>

- <span data-ttu-id="d82b0-375">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="d82b0-375">AntiVirusStatus</span></span>

- <span data-ttu-id="d82b0-376">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="d82b0-376">AntiVirusSignatureStatus</span></span>

- <span data-ttu-id="d82b0-377">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="d82b0-377">SmartScreenEnabled</span></span>

- <span data-ttu-id="d82b0-378">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="d82b0-378">WorkFoldersSyncUrl</span></span>

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="d82b0-379">远程擦除移动设备</span><span class="sxs-lookup"><span data-stu-id="d82b0-379">Remotely wipe a mobile device</span></span>

<span data-ttu-id="d82b0-380">如果设备丢失或被盗，可以通过从安全与合规中心 > 数据丢失防护设备管理 执行擦除来删除敏感的组织数据，并帮助阻止访问 Microsoft 36 & 5 **组织**  >  **资源**。</span><span class="sxs-lookup"><span data-stu-id="d82b0-380">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="d82b0-381">你可以执行选择性擦除以仅删除组织数据，也可以执行完全擦除，以从设备中删除所有信息，并还原到其出厂设置。</span><span class="sxs-lookup"><span data-stu-id="d82b0-381">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="d82b0-382">有关详细信息，请参阅 [Basic Mobility and Security](wipe-mobile-device.md)中的擦除移动设备。</span><span class="sxs-lookup"><span data-stu-id="d82b0-382">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d82b0-383">相关主题</span><span class="sxs-lookup"><span data-stu-id="d82b0-383">Related topics</span></span>

[<span data-ttu-id="d82b0-384">Microsoft 365 的基本移动性和安全性概述</span><span class="sxs-lookup"><span data-stu-id="d82b0-384">Overview of Basic Mobility and Security for Microsoft 365</span></span>](overview.md)

[<span data-ttu-id="d82b0-385">在基本移动性和安全性中创建设备安全策略</span><span class="sxs-lookup"><span data-stu-id="d82b0-385">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies.md)