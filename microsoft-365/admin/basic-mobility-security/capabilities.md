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
ms.openlocfilehash: 468f06edf16eb6ea00fd4d26c716bc145474dd25
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904272"
---
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="2a9ff-103">基本移动性和安全性的功能</span><span class="sxs-lookup"><span data-stu-id="2a9ff-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="2a9ff-104">基本移动性和安全性可帮助你保护和管理组织中授权 Microsoft 365 用户使用的移动设备，如 iPhone、iPad、Android 和 Windows Phones。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="2a9ff-105">可以使用可帮助控制对组织的 Microsoft 365 电子邮件和文档的访问（对于受支持的移动设备和应用）的设置创建移动设备管理策略。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="2a9ff-106">如果设备丢失或被盗，你可以远程擦除设备以删除敏感的组织信息。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="2a9ff-107">支持的设备</span><span class="sxs-lookup"><span data-stu-id="2a9ff-107">Supported devices</span></span>

<span data-ttu-id="2a9ff-108">您可以使用基本移动性和安全性保护和管理以下设备。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="2a9ff-109">iOS 11.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2a9ff-109">iOS 11.0 or later versions</span></span>

- <span data-ttu-id="2a9ff-110">Android 5.0 或更高版本<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2a9ff-110">Android 5.0 or later versions<sup>3</sup></span></span>

- <span data-ttu-id="2a9ff-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2a9ff-111">Windows 8.1<sup>1</sup></span></span>

- <span data-ttu-id="2a9ff-112">Windows 8.1 RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2a9ff-112">Windows 8.1 RT<sup>1</sup></span></span>

- <span data-ttu-id="2a9ff-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2a9ff-113">Windows 10<sup>2</sup></span></span>

- <span data-ttu-id="2a9ff-114">Windows 10 移动<sup>版 2</sup></span><span class="sxs-lookup"><span data-stu-id="2a9ff-114">Windows 10 Mobile<sup>2</sup></span></span>

<span data-ttu-id="2a9ff-115"><sup>1</sup>Windows 8.1 RT 设备的访问控制仅限于Exchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="2a9ff-116"><sup>2</sup>Windows 8.1 RT 设备的访问控制仅限于Exchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-116"><sup>2</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="2a9ff-117">Windows 10 的访问控制需要包含 Azure AD Premium 的订阅，并且设备需要加入到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-117">Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="2a9ff-118"><sup>3</sup>Windows 8.1 RT 设备的访问控制仅限于Exchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-118"><sup>3</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="2a9ff-119">2020 年 6 月之后，超过 9 的 Android 版本无法管理密码设置，但 Samsung Knox 设备上除外。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-119">After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

>[!NOTE]
><span data-ttu-id="2a9ff-120">已注册较早操作系统版本的设备仍可以继续运行，尽管这些功能可能会在不另行通知的情况下更改。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-120">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="2a9ff-121">如果你的组织中人员使用的移动设备不受基本移动性和安全性支持，你可能希望阻止 Exchange ActiveSync 应用访问这些设备的 Microsoft 365 电子邮件，以帮助使组织的数据更安全。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-121">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="2a9ff-122">有关阻止访问Exchange ActiveSync，请参阅基本移动性和安全性中的管理 [设备访问设置](manage-device-access-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-122">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="2a9ff-123">Microsoft 365 电子邮件和文档的访问控制</span><span class="sxs-lookup"><span data-stu-id="2a9ff-123">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="2a9ff-124">下表中支持的不同类型的移动设备的应用提示用户注册基本移动性和安全性，其中存在适用于用户设备且用户之前尚未注册该设备的新移动设备管理策略。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-124">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="2a9ff-125">如果用户的设备不符合策略，具体取决于策略的设置方式，用户可能会被阻止访问这些应用中的 Microsoft 365 资源，或者他们可能具有访问权限，但 Microsoft 365 报告违反策略。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-125">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="2a9ff-126">**产品**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-126">**Product**</span></span>|<span data-ttu-id="2a9ff-127">**iOS 10.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-127">**iOS 10.0 or later**</span></span>|<span data-ttu-id="2a9ff-128">**Android 5.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-128">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2a9ff-129">**Exchange** Exchange ActiveSync内置电子邮件和第三方应用（如 TouchDown）使用 Exchange ActiveSync 14.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-129">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="2a9ff-130">邮件</span><span class="sxs-lookup"><span data-stu-id="2a9ff-130">Mail</span></span> |<span data-ttu-id="2a9ff-131">电子邮件</span><span class="sxs-lookup"><span data-stu-id="2a9ff-131">Email</span></span> |
|<span data-ttu-id="2a9ff-132">**Office**  和  **OneDrive for Business**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-132">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="2a9ff-133">Outlook</span><span class="sxs-lookup"><span data-stu-id="2a9ff-133">Outlook</span></span> </br><span data-ttu-id="2a9ff-134">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2a9ff-134">OneDrive</span></span> </br><span data-ttu-id="2a9ff-135">Word</span><span class="sxs-lookup"><span data-stu-id="2a9ff-135">Word</span></span> </br><span data-ttu-id="2a9ff-136">Excel</span><span class="sxs-lookup"><span data-stu-id="2a9ff-136">Excel</span></span> </br><span data-ttu-id="2a9ff-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2a9ff-137">PowerPoint</span></span>|<span data-ttu-id="2a9ff-138">**在手机和平板电脑上**：</span><span class="sxs-lookup"><span data-stu-id="2a9ff-138">**On phones and tablets**:</span></span><br/><span data-ttu-id="2a9ff-139">Outlook</span><span class="sxs-lookup"><span data-stu-id="2a9ff-139">Outlook</span></span> <br/> <span data-ttu-id="2a9ff-140">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2a9ff-140">OneDrive</span></span> <br/> <span data-ttu-id="2a9ff-141">Word</span><span class="sxs-lookup"><span data-stu-id="2a9ff-141">Word</span></span> <br/> <span data-ttu-id="2a9ff-142">Excel</span><span class="sxs-lookup"><span data-stu-id="2a9ff-142">Excel</span></span> <br/> <span data-ttu-id="2a9ff-143">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2a9ff-143">PowerPoint</span></span> <br/> <span data-ttu-id="2a9ff-144">**仅在电话上：**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-144">**On phones only:**</span></span> <br/> <span data-ttu-id="2a9ff-145">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="2a9ff-145">Office Mobile</span></span> |

>[!NOTE]
- ><span data-ttu-id="2a9ff-146">支持 iOS 10.0 及更高版本包括 iPhone 和 iPad 设备。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-146">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
- ><span data-ttu-id="2a9ff-147">基本安全性和移动性不支持管理 BlackBerry 操作系统设备。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-147">Management of BlackBerry OS devices isn’t supported by Basic Security and Mobility.</span></span> <span data-ttu-id="2a9ff-148">使用 BlackBerry 商业云服务 (BBCS) 管理 BlackBerry 操作系统设备。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-148">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="2a9ff-149">运行 Android 操作系统的 Blackberry 设备作为标准 Android 设备受到支持</span><span class="sxs-lookup"><span data-stu-id="2a9ff-149">Blackberry devices running Android OS are supported as standard Android devices</span></span>
- ><span data-ttu-id="2a9ff-150">如果用户使用移动浏览器访问 Microsoft 365 SharePoint 网站、Office Online 中的文档或 Outlook Web App 中的电子邮件，将不会提示用户注册，也不会被阻止或报告违反策略。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-150">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>

<span data-ttu-id="2a9ff-151">下图显示了当具有新设备的用户登录支持具有基本移动性和安全性的访问控制的应用时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-151">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="2a9ff-152">用户被阻止访问应用中的 Microsoft 365 资源，直到用户注册其设备。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-152">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本移动性和安全性访问控制":::

> [!NOTE]
> <span data-ttu-id="2a9ff-154">在 Microsoft 365 商业标准的基本移动性和安全性中创建的策略和访问规则将Exchange ActiveSync Exchange 管理中心中创建的移动设备邮箱策略和设备访问规则。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-154">Policies and access rules created in Basic Mobility and Security for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="2a9ff-155">在 Microsoft 365 商业标准版的基本移动性和安全性中注册设备后，将忽略应用于该设备的任何 Exchange ActiveSync 移动设备邮箱策略或设备访问规则。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-155">After a device is enrolled in Basic Mobility and Security for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="2a9ff-156">若要了解有关 exchange online Exchange ActiveSync，请参阅 [Exchange ActiveSync Exchange Online。](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)</span><span class="sxs-lookup"><span data-stu-id="2a9ff-156">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="2a9ff-157">移动设备的策略设置</span><span class="sxs-lookup"><span data-stu-id="2a9ff-157">Policy settings for mobile devices</span></span>

<span data-ttu-id="2a9ff-158">如果创建阻止访问的策略，但某些设置已打开，则当用户使用 Microsoft 365 电子邮件和文档的访问控制中列出的受支持应用时，将阻止用户访问 [Microsoft 365 资源](capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-158">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](capabilities.md).</span></span> 

<span data-ttu-id="2a9ff-159">以下部分包含可阻止用户访问 Microsoft 365 资源的设置：</span><span class="sxs-lookup"><span data-stu-id="2a9ff-159">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="2a9ff-160">安全性</span><span class="sxs-lookup"><span data-stu-id="2a9ff-160">Security</span></span>

- <span data-ttu-id="2a9ff-161">加密</span><span class="sxs-lookup"><span data-stu-id="2a9ff-161">Encryption</span></span>

- <span data-ttu-id="2a9ff-162">已越狱</span><span class="sxs-lookup"><span data-stu-id="2a9ff-162">Jail broken</span></span>

- <span data-ttu-id="2a9ff-163">托管电子邮件配置文件</span><span class="sxs-lookup"><span data-stu-id="2a9ff-163">Managed email profile</span></span>  

<span data-ttu-id="2a9ff-164">例如，下图显示了当已注册设备的用户不符合适用于其设备的移动设备管理策略中的安全设置时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-164">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="2a9ff-165">用户登录支持具有基本移动性和安全性的访问控制的应用。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-165">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="2a9ff-166">在设备符合安全设置之前，将阻止他们访问应用中的 Microsoft 365 资源。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-166">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本移动性和安全性合规性消息":::

<span data-ttu-id="2a9ff-168">以下部分列出了可用于帮助保护和管理连接到 Microsoft 365 组织资源的移动设备的策略设置。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-168">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="2a9ff-169">安全设置</span><span class="sxs-lookup"><span data-stu-id="2a9ff-169">Security settings</span></span>

|<span data-ttu-id="2a9ff-170">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-170">**Setting name**</span></span>|<span data-ttu-id="2a9ff-171">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-171">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2a9ff-172">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-172">**Android 5 and later**</span></span>|<span data-ttu-id="2a9ff-173">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-173">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a9ff-174">要求使用密码</span><span class="sxs-lookup"><span data-stu-id="2a9ff-174">Require a password</span></span>|<span data-ttu-id="2a9ff-175">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-175">Yes</span></span>|<span data-ttu-id="2a9ff-176">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-176">Yes</span></span>|<span data-ttu-id="2a9ff-177">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-177">Yes</span></span>|
|<span data-ttu-id="2a9ff-178">阻止简单密码</span><span class="sxs-lookup"><span data-stu-id="2a9ff-178">Prevent simple password</span></span>|<span data-ttu-id="2a9ff-179">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-179">Yes</span></span>|<span data-ttu-id="2a9ff-180">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-180">No</span></span>|<span data-ttu-id="2a9ff-181">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-181">No</span></span>|
|<span data-ttu-id="2a9ff-182">需要字母数字密码</span><span class="sxs-lookup"><span data-stu-id="2a9ff-182">Require an alphanumeric password</span></span>|<span data-ttu-id="2a9ff-183">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-183">Yes</span></span>|<span data-ttu-id="2a9ff-184">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-184">No</span></span>|<span data-ttu-id="2a9ff-185">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-185">No</span></span>|
|<span data-ttu-id="2a9ff-186">最短密码长度</span><span class="sxs-lookup"><span data-stu-id="2a9ff-186">Minimum password length</span></span> |<span data-ttu-id="2a9ff-187">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-187">Yes</span></span>|<span data-ttu-id="2a9ff-188">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-188">Yes</span></span>|<span data-ttu-id="2a9ff-189">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-189">Yes</span></span>|
|<span data-ttu-id="2a9ff-190">擦除设备之前登录失败次数</span><span class="sxs-lookup"><span data-stu-id="2a9ff-190">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="2a9ff-191">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-191">Yes</span></span>|<span data-ttu-id="2a9ff-192">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-192">Yes</span></span>|<span data-ttu-id="2a9ff-193">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-193">Yes</span></span>|
|<span data-ttu-id="2a9ff-194">设备锁定前不活动分钟数</span><span class="sxs-lookup"><span data-stu-id="2a9ff-194">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="2a9ff-195">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-195">Yes</span></span>|<span data-ttu-id="2a9ff-196">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-196">Yes</span></span>|<span data-ttu-id="2a9ff-197">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-197">Yes</span></span>|
|<span data-ttu-id="2a9ff-198">密码过期 (天数) </span><span class="sxs-lookup"><span data-stu-id="2a9ff-198">Password expiration (days)</span></span> |<span data-ttu-id="2a9ff-199">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-199">Yes</span></span>|<span data-ttu-id="2a9ff-200">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-200">Yes</span></span>|<span data-ttu-id="2a9ff-201">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-201">Yes</span></span>|
|<span data-ttu-id="2a9ff-202">记住密码历史记录并阻止重复使用</span><span class="sxs-lookup"><span data-stu-id="2a9ff-202">Remember password history and prevent reuse</span></span> |<span data-ttu-id="2a9ff-203">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-203">Yes</span></span>|<span data-ttu-id="2a9ff-204">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-204">Yes</span></span>|<span data-ttu-id="2a9ff-205">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-205">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="2a9ff-206">加密设置</span><span class="sxs-lookup"><span data-stu-id="2a9ff-206">Encryption settings</span></span>

|<span data-ttu-id="2a9ff-207">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-207">**Setting name**</span></span>|<span data-ttu-id="2a9ff-208">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-208">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2a9ff-209">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-209">**Android 5 and later**</span></span>|<span data-ttu-id="2a9ff-210">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-210">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a9ff-211">要求对设备<sup>1 进行数据加密</sup></span><span class="sxs-lookup"><span data-stu-id="2a9ff-211">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="2a9ff-212">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-212">No</span></span>|<span data-ttu-id="2a9ff-213">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-213">Yes</span></span>|<span data-ttu-id="2a9ff-214">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-214">Yes</span></span>|

<span data-ttu-id="2a9ff-215"><sup>1</sup>使用 Samsung Knox，还可以要求对存储卡进行加密。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-215"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span> 

## <a name="jail-broken-setting"></a><span data-ttu-id="2a9ff-216">已越狱设置</span><span class="sxs-lookup"><span data-stu-id="2a9ff-216">Jail broken setting</span></span> 

|<span data-ttu-id="2a9ff-217">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-217">**Setting name**</span></span>|<span data-ttu-id="2a9ff-218">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-218">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2a9ff-219">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-219">**Android 5 and later**</span></span>|<span data-ttu-id="2a9ff-220">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-220">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a9ff-221">设备无法越狱或具有 root 权限</span><span class="sxs-lookup"><span data-stu-id="2a9ff-221">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="2a9ff-222">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-222">Yes</span></span>|<span data-ttu-id="2a9ff-223">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-223">Yes</span></span>|<span data-ttu-id="2a9ff-224">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-224">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="2a9ff-225">托管电子邮件配置文件选项</span><span class="sxs-lookup"><span data-stu-id="2a9ff-225">Managed email profile option</span></span> 

<span data-ttu-id="2a9ff-226">以下选项可以阻止用户使用手动创建的电子邮件配置文件访问其 Microsoft 365 电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-226">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="2a9ff-227">iOS 设备上的用户必须先删除手动创建的电子邮件配置文件，然后才能访问电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-227">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="2a9ff-228">删除配置文件后，将在设备上自动创建一个新配置文件。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-228">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="2a9ff-229">有关最终用户如何合规的说明，请参阅已找到现有 [电子邮件帐户](/intune-user-help/existing-company-email-account-found)。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-229">For instructions on how end users can get compliant, see [An existing email account was found](/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="2a9ff-230">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-230">**Setting name**</span></span>|<span data-ttu-id="2a9ff-231">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-231">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2a9ff-232">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-232">**Android 5 and later**</span></span>|<span data-ttu-id="2a9ff-233">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-233">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a9ff-234">管理电子邮件配置文件</span><span class="sxs-lookup"><span data-stu-id="2a9ff-234">Email profile is managed</span></span> |<span data-ttu-id="2a9ff-235">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-235">Yes</span></span>|<span data-ttu-id="2a9ff-236">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-236">No</span></span>|<span data-ttu-id="2a9ff-237">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-237">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="2a9ff-238">云设置</span><span class="sxs-lookup"><span data-stu-id="2a9ff-238">Cloud settings</span></span>

|<span data-ttu-id="2a9ff-239">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-239">**Setting name**</span></span>|<span data-ttu-id="2a9ff-240">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-240">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2a9ff-241">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-241">**Android 5 and later**</span></span>|<span data-ttu-id="2a9ff-242">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-242">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a9ff-243">需要加密备份</span><span class="sxs-lookup"><span data-stu-id="2a9ff-243">Require encrypted backup</span></span> |<span data-ttu-id="2a9ff-244">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-244">Yes</span></span>|<span data-ttu-id="2a9ff-245">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-245">No</span></span>|<span data-ttu-id="2a9ff-246">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-246">No</span></span>|
|<span data-ttu-id="2a9ff-247">阻止云备份</span><span class="sxs-lookup"><span data-stu-id="2a9ff-247">Block cloud backup</span></span> |<span data-ttu-id="2a9ff-248">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-248">Yes</span></span>|<span data-ttu-id="2a9ff-249">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-249">No</span></span>|<span data-ttu-id="2a9ff-250">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-250">No</span></span>|
|<span data-ttu-id="2a9ff-251">阻止文档同步</span><span class="sxs-lookup"><span data-stu-id="2a9ff-251">Block document synchronization</span></span> |<span data-ttu-id="2a9ff-252">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-252">Yes</span></span>|<span data-ttu-id="2a9ff-253">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-253">No</span></span>|<span data-ttu-id="2a9ff-254">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-254">No</span></span>|
|<span data-ttu-id="2a9ff-255">阻止照片同步</span><span class="sxs-lookup"><span data-stu-id="2a9ff-255">Block photo synchronization</span></span>  |<span data-ttu-id="2a9ff-256">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-256">Yes</span></span>|<span data-ttu-id="2a9ff-257">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-257">No</span></span>|<span data-ttu-id="2a9ff-258">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-258">No</span></span>|
|<span data-ttu-id="2a9ff-259">允许 Google 备份</span><span class="sxs-lookup"><span data-stu-id="2a9ff-259">Allow Google backup</span></span>  |<span data-ttu-id="2a9ff-260">不适用</span><span class="sxs-lookup"><span data-stu-id="2a9ff-260">N/A</span></span>|<span data-ttu-id="2a9ff-261">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-261">No</span></span>|<span data-ttu-id="2a9ff-262">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-262">Yes</span></span>|
|<span data-ttu-id="2a9ff-263">允许 Google 帐户自动同步</span><span class="sxs-lookup"><span data-stu-id="2a9ff-263">Allow Google account auto sync</span></span>  |<span data-ttu-id="2a9ff-264">不适用</span><span class="sxs-lookup"><span data-stu-id="2a9ff-264">N/A</span></span>|<span data-ttu-id="2a9ff-265">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-265">No</span></span>|<span data-ttu-id="2a9ff-266">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-266">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="2a9ff-267">系统设置</span><span class="sxs-lookup"><span data-stu-id="2a9ff-267">System settings</span></span>

|<span data-ttu-id="2a9ff-268">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-268">**Setting name**</span></span>|<span data-ttu-id="2a9ff-269">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-269">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2a9ff-270">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-270">**Android 5 and later**</span></span>|<span data-ttu-id="2a9ff-271">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-271">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a9ff-272">阻止屏幕捕获</span><span class="sxs-lookup"><span data-stu-id="2a9ff-272">Block screen capture</span></span> |<span data-ttu-id="2a9ff-273">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-273">Yes</span></span>|<span data-ttu-id="2a9ff-274">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-274">No</span></span>|<span data-ttu-id="2a9ff-275">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-275">Yes</span></span>|
|<span data-ttu-id="2a9ff-276">阻止从设备发送诊断数据</span><span class="sxs-lookup"><span data-stu-id="2a9ff-276">Block sending diagnostic data from device</span></span> |<span data-ttu-id="2a9ff-277">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-277">Yes</span></span>|<span data-ttu-id="2a9ff-278">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-278">No</span></span>|<span data-ttu-id="2a9ff-279">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-279">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="2a9ff-280">应用程序设置</span><span class="sxs-lookup"><span data-stu-id="2a9ff-280">Application settings</span></span>

|<span data-ttu-id="2a9ff-281">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-281">**Setting name**</span></span>|<span data-ttu-id="2a9ff-282">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-282">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2a9ff-283">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-283">**Android 5 and later**</span></span>|<span data-ttu-id="2a9ff-284">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-284">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a9ff-285">在设备上阻止视频会议</span><span class="sxs-lookup"><span data-stu-id="2a9ff-285">Block video conferences on device</span></span> |<span data-ttu-id="2a9ff-286">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-286">Yes</span></span>|<span data-ttu-id="2a9ff-287">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-287">No</span></span>|<span data-ttu-id="2a9ff-288">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-288">No</span></span>|
|<span data-ttu-id="2a9ff-289">阻止访问应用程序存储</span><span class="sxs-lookup"><span data-stu-id="2a9ff-289">Block access to application store</span></span> |<span data-ttu-id="2a9ff-290">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-290">Yes</span></span>|<span data-ttu-id="2a9ff-291">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-291">No</span></span>|<span data-ttu-id="2a9ff-292">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-292">Yes</span></span>|
|<span data-ttu-id="2a9ff-293">访问应用程序存储时需要密码</span><span class="sxs-lookup"><span data-stu-id="2a9ff-293">Require password when accessing application store</span></span> |<span data-ttu-id="2a9ff-294">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-294">No</span></span>|<span data-ttu-id="2a9ff-295">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-295">Yes</span></span>|<span data-ttu-id="2a9ff-296">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-296">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="2a9ff-297">设备功能设置</span><span class="sxs-lookup"><span data-stu-id="2a9ff-297">Device capabilities settings</span></span>

|<span data-ttu-id="2a9ff-298">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-298">**Setting name**</span></span>|<span data-ttu-id="2a9ff-299">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-299">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2a9ff-300">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-300">**Android 5 and later**</span></span>|<span data-ttu-id="2a9ff-301">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-301">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a9ff-302">使用可移动存储阻止连接</span><span class="sxs-lookup"><span data-stu-id="2a9ff-302">Block connection with removable storage</span></span> |<span data-ttu-id="2a9ff-303">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-303">Yes</span></span>|<span data-ttu-id="2a9ff-304">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-304">Yes</span></span>|<span data-ttu-id="2a9ff-305">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-305">No</span></span>|
|<span data-ttu-id="2a9ff-306">阻止蓝牙连接</span><span class="sxs-lookup"><span data-stu-id="2a9ff-306">Block Bluetooth connection</span></span> |<span data-ttu-id="2a9ff-307">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-307">Yes</span></span>|<span data-ttu-id="2a9ff-308">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-308">Yes</span></span>|<span data-ttu-id="2a9ff-309">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-309">No</span></span>|

## <a name="additional-settings"></a><span data-ttu-id="2a9ff-310">其他设置</span><span class="sxs-lookup"><span data-stu-id="2a9ff-310">Additional settings</span></span>

<span data-ttu-id="2a9ff-311">您可以使用安全与合规中心 PowerShell cmdlet &其他策略设置。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-311">You can set the following additional policy settings by using Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="2a9ff-312">有关详细信息，请参阅安全与 [&中心 PowerShell。](/powershell/exchange/scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="2a9ff-312">For more information, see [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

|<span data-ttu-id="2a9ff-313">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-313">**Setting name**</span></span>|<span data-ttu-id="2a9ff-314">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-314">**iOS 7.1 and later**</span></span>|<span data-ttu-id="2a9ff-315">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="2a9ff-315">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2a9ff-316">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="2a9ff-316">CameraEnabled</span></span>|<span data-ttu-id="2a9ff-317">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-317">Yes</span></span>|<span data-ttu-id="2a9ff-318">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-318">Yes</span></span>|
|<span data-ttu-id="2a9ff-319">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="2a9ff-319">RegionRatings</span></span>|<span data-ttu-id="2a9ff-320">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-320">Yes</span></span>|<span data-ttu-id="2a9ff-321">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-321">No</span></span>|
|<span data-ttu-id="2a9ff-322">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="2a9ff-322">MoviesRatings</span></span>|<span data-ttu-id="2a9ff-323">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-323">Yes</span></span>|<span data-ttu-id="2a9ff-324">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-324">No</span></span>|
|<span data-ttu-id="2a9ff-325">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="2a9ff-325">TVShowsRating</span></span> |<span data-ttu-id="2a9ff-326">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-326">Yes</span></span>|<span data-ttu-id="2a9ff-327">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-327">No</span></span>|
|<span data-ttu-id="2a9ff-328">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="2a9ff-328">AppsRatings</span></span> |<span data-ttu-id="2a9ff-329">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-329">Yes</span></span>|<span data-ttu-id="2a9ff-330">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-330">No</span></span>|
|<span data-ttu-id="2a9ff-331">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="2a9ff-331">AllowVoiceDialing</span></span> |<span data-ttu-id="2a9ff-332">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-332">Yes</span></span>|<span data-ttu-id="2a9ff-333">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-333">No</span></span>|
|<span data-ttu-id="2a9ff-334">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="2a9ff-334">AllowVoiceAssistant</span></span> |<span data-ttu-id="2a9ff-335">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-335">Yes</span></span>|<span data-ttu-id="2a9ff-336">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-336">No</span></span>|
|<span data-ttu-id="2a9ff-337">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="2a9ff-337">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="2a9ff-338">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-338">Yes</span></span>|<span data-ttu-id="2a9ff-339">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-339">No</span></span>|
|<span data-ttu-id="2a9ff-340">AllowPassbookWhileLocked</span><span class="sxs-lookup"><span data-stu-id="2a9ff-340">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="2a9ff-341">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-341">Yes</span></span>|<span data-ttu-id="2a9ff-342">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-342">No</span></span>|
|<span data-ttu-id="2a9ff-343">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="2a9ff-343">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="2a9ff-344">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-344">Yes</span></span>|<span data-ttu-id="2a9ff-345">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-345">No</span></span>|
|<span data-ttu-id="2a9ff-346">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="2a9ff-346">PasswordQuality</span></span> |<span data-ttu-id="2a9ff-347">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-347">No</span></span>|<span data-ttu-id="2a9ff-348">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-348">Yes</span></span>|
|<span data-ttu-id="2a9ff-349">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="2a9ff-349">SystemSecurityTLS</span></span>  |<span data-ttu-id="2a9ff-350">是</span><span class="sxs-lookup"><span data-stu-id="2a9ff-350">Yes</span></span>|<span data-ttu-id="2a9ff-351">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-351">No</span></span>|
|<span data-ttu-id="2a9ff-352">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="2a9ff-352">WLANEnabled</span></span>  |<span data-ttu-id="2a9ff-353">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-353">No</span></span>|<span data-ttu-id="2a9ff-354">否</span><span class="sxs-lookup"><span data-stu-id="2a9ff-354">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="2a9ff-355">Windows 支持的设置</span><span class="sxs-lookup"><span data-stu-id="2a9ff-355">Settings supported by Windows</span></span>

<span data-ttu-id="2a9ff-356">可以通过将 Windows 10 设备注册为移动设备来管理它们。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-356">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="2a9ff-357">部署适用的策略后，使用 Windows 10 设备的用户在首次使用内置电子邮件应用访问其 Microsoft 365 电子邮件 (需要 Azure AD Premium 订阅) 时，需要注册基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-357">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="2a9ff-358">注册为移动设备的 Windows 10 设备支持以下设置。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-358">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="2a9ff-359">此设置不会阻止用户访问 Microsoft 365 资源。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-359">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="2a9ff-360">安全设置</span><span class="sxs-lookup"><span data-stu-id="2a9ff-360">Security settings</span></span>

- <span data-ttu-id="2a9ff-361">需要字母数字密码</span><span class="sxs-lookup"><span data-stu-id="2a9ff-361">Require an alphanumeric password</span></span>

- <span data-ttu-id="2a9ff-362">最短密码长度</span><span class="sxs-lookup"><span data-stu-id="2a9ff-362">Minimum password length</span></span>

- <span data-ttu-id="2a9ff-363">擦除设备之前登录失败次数</span><span class="sxs-lookup"><span data-stu-id="2a9ff-363">Number of sign-in failures before device is wiped</span></span>

- <span data-ttu-id="2a9ff-364">设备锁定前不活动分钟数</span><span class="sxs-lookup"><span data-stu-id="2a9ff-364">Minutes of inactivity before device is locked</span></span>

- <span data-ttu-id="2a9ff-365">密码过期 (天数) </span><span class="sxs-lookup"><span data-stu-id="2a9ff-365">Password expiration (days)</span></span>

- <span data-ttu-id="2a9ff-366">记住密码历史记录并阻止重复使用</span><span class="sxs-lookup"><span data-stu-id="2a9ff-366">Remember password history and prevent reuse</span></span>

>[!NOTE]
><span data-ttu-id="2a9ff-367">以下设置管理密码仅控制本地 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-367">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="2a9ff-368">通过加入域或 Azure Active Directory 提供的 Windows 帐户不受这些设置的影响。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-368">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="2a9ff-369">系统设置</span><span class="sxs-lookup"><span data-stu-id="2a9ff-369">System settings</span></span>

<span data-ttu-id="2a9ff-370">阻止从设备发送诊断数据。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-370">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="2a9ff-371">其他设置</span><span class="sxs-lookup"><span data-stu-id="2a9ff-371">Additional settings</span></span>

<span data-ttu-id="2a9ff-372">可以使用 PowerShell cmdlet 设置这些额外的策略设置：</span><span class="sxs-lookup"><span data-stu-id="2a9ff-372">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="2a9ff-373">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="2a9ff-373">AllowConvenienceLogon</span></span>

- <span data-ttu-id="2a9ff-374">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="2a9ff-374">UserAccountControlStatus</span></span>

- <span data-ttu-id="2a9ff-375">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="2a9ff-375">FirewallStatus</span></span>

- <span data-ttu-id="2a9ff-376">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="2a9ff-376">AutoUpdateStatus</span></span>

- <span data-ttu-id="2a9ff-377">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="2a9ff-377">AntiVirusStatus</span></span>

- <span data-ttu-id="2a9ff-378">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="2a9ff-378">AntiVirusSignatureStatus</span></span>

- <span data-ttu-id="2a9ff-379">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="2a9ff-379">SmartScreenEnabled</span></span>

- <span data-ttu-id="2a9ff-380">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="2a9ff-380">WorkFoldersSyncUrl</span></span>

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="2a9ff-381">远程擦除移动设备</span><span class="sxs-lookup"><span data-stu-id="2a9ff-381">Remotely wipe a mobile device</span></span>

<span data-ttu-id="2a9ff-382">如果设备丢失或被盗，可以通过从安全与合规中心 > 数据丢失防护设备管理 执行擦除来删除敏感的组织数据，并帮助阻止访问 Microsoft 36 & 5 **组织**  >  **资源**。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-382">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="2a9ff-383">你可以执行选择性擦除以仅删除组织数据，也可以执行完全擦除，以从设备中删除所有信息，并还原到其出厂设置。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-383">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="2a9ff-384">有关详细信息，请参阅 [Basic Mobility and Security](wipe-mobile-device.md)中的擦除移动设备。</span><span class="sxs-lookup"><span data-stu-id="2a9ff-384">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a9ff-385">相关主题</span><span class="sxs-lookup"><span data-stu-id="2a9ff-385">Related topics</span></span>

[<span data-ttu-id="2a9ff-386">Microsoft 365 的基本移动性和安全性概述</span><span class="sxs-lookup"><span data-stu-id="2a9ff-386">Overview of Basic Mobility and Security for Microsoft 365</span></span>](overview.md)

[<span data-ttu-id="2a9ff-387">在基本移动性和安全性中创建设备安全策略</span><span class="sxs-lookup"><span data-stu-id="2a9ff-387">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies.md)