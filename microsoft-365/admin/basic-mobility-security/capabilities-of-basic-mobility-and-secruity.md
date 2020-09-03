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
description: 基本移动性和安全性可帮助您保护和管理移动设备。
ms.openlocfilehash: 32393f39655b81313f6592936c55e36ffe029a27
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336764"
---
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="cfd34-103">基本移动性和安全性的功能</span><span class="sxs-lookup"><span data-stu-id="cfd34-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="cfd34-104">基本移动性和安全性可帮助您保护和管理移动设备，如 Iphone、Ipad、Androids 和 Windows phone （由组织中的许可 Microsoft 365 用户使用）。</span><span class="sxs-lookup"><span data-stu-id="cfd34-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="cfd34-105">您可以使用设置来创建移动设备管理策略，这些策略可帮助控制对受支持的移动设备和应用程序的 Microsoft 365 电子邮件和文档的访问。</span><span class="sxs-lookup"><span data-stu-id="cfd34-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="cfd34-106">如果设备丢失或被盗，可以远程擦除设备以删除敏感的组织信息。</span><span class="sxs-lookup"><span data-stu-id="cfd34-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="cfd34-107">支持的设备</span><span class="sxs-lookup"><span data-stu-id="cfd34-107">Supported devices</span></span>

<span data-ttu-id="cfd34-108">您可以使用基本移动性和安全性来保护和管理以下设备。</span><span class="sxs-lookup"><span data-stu-id="cfd34-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="cfd34-109">iOS 11.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="cfd34-109">iOS 11.0 or later versions</span></span>
    
- <span data-ttu-id="cfd34-110">Android 5.0 或更高版本<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="cfd34-110">Android 5.0 or later versions<sup>3</sup></span></span>
    
- <span data-ttu-id="cfd34-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cfd34-111">Windows 8.1<sup>1</sup></span></span>
    
- <span data-ttu-id="cfd34-112">Windows 8.1 RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cfd34-112">Windows 8.1 RT<sup>1</sup></span></span>
    
- <span data-ttu-id="cfd34-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cfd34-113">Windows 10<sup>2</sup></span></span>
    
- <span data-ttu-id="cfd34-114">Windows 10 移动版<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cfd34-114">Windows 10 Mobile<sup>2</sup></span></span>   

<span data-ttu-id="cfd34-115"><sup>1</sup>Windows 8.1 RT 设备的访问控制仅限于 Exchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="cfd34-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="cfd34-116"><sup>2</sup>Windows 8.1 RT 设备的访问控制仅限于 Exchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="cfd34-116"><sup>2</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="cfd34-117">Windows 10 的访问控制需要一个包含 Azure AD Premium 的订阅，并且该设备需要加入 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="cfd34-117">Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="cfd34-118"><sup>3</sup>Windows 8.1 RT 设备的访问控制仅限于 Exchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="cfd34-118"><sup>3</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="cfd34-119">6月2020日之后，如果 Android 版本低于9，则无法管理除 Samsung Knox 设备之外的密码设置。</span><span class="sxs-lookup"><span data-stu-id="cfd34-119">After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

>[!NOTE]
><span data-ttu-id="cfd34-120">已注册早期 OS 版本的设备将继续正常运行，但功能可能会更改，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="cfd34-120">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="cfd34-121">如果组织中的人员使用的是基本移动性和安全性不支持的移动设备，则可能需要阻止 Exchange ActiveSync 应用程序对这些设备的 Microsoft 365 电子邮件的访问权限，以帮助使组织的数据更加安全。</span><span class="sxs-lookup"><span data-stu-id="cfd34-121">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="cfd34-122">有关阻止 Exchange ActiveSync 的步骤，请参阅 [Manage device access settings In Basic 可移动性 And Security](manage-device-access-settings-in-basic-mobility-and-security.md)。</span><span class="sxs-lookup"><span data-stu-id="cfd34-122">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings-in-basic-mobility-and-security.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="cfd34-123">Microsoft 365 电子邮件和文档的访问控制</span><span class="sxs-lookup"><span data-stu-id="cfd34-123">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="cfd34-124">下表中不同类型的移动设备的受支持的应用程序提示用户注册基本移动性和安全性，其中包含一个新的移动设备管理策略，该策略适用于用户的设备，并且用户以前未注册该设备。</span><span class="sxs-lookup"><span data-stu-id="cfd34-124">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="cfd34-125">如果用户的设备不符合策略，则可能会阻止用户访问这些应用程序中的 Microsoft 365 资源，或者可能会阻止用户访问，但 Microsoft 365 会报告违反策略的情况。</span><span class="sxs-lookup"><span data-stu-id="cfd34-125">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="cfd34-126">**产品**</span><span class="sxs-lookup"><span data-stu-id="cfd34-126">**Product**</span></span>|<span data-ttu-id="cfd34-127">**iOS 10.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-127">**iOS 10.0 or later**</span></span>|<span data-ttu-id="cfd34-128">**Android 5.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-128">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cfd34-129">**Exchange** Exchange ActiveSync 包括内置电子邮件和第三方应用程序（如 TouchDown），后者使用 Exchange ActiveSync 版本14.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="cfd34-129">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="cfd34-130">邮件</span><span class="sxs-lookup"><span data-stu-id="cfd34-130">Mail</span></span> |<span data-ttu-id="cfd34-131">电子邮件</span><span class="sxs-lookup"><span data-stu-id="cfd34-131">Email</span></span> |
|<span data-ttu-id="cfd34-132">**Office**  和 **OneDrive For business**</span><span class="sxs-lookup"><span data-stu-id="cfd34-132">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="cfd34-133">Outlook</span><span class="sxs-lookup"><span data-stu-id="cfd34-133">Outlook</span></span> </br><span data-ttu-id="cfd34-134">OneDrive</span><span class="sxs-lookup"><span data-stu-id="cfd34-134">OneDrive</span></span> </br><span data-ttu-id="cfd34-135">Word</span><span class="sxs-lookup"><span data-stu-id="cfd34-135">Word</span></span> </br><span data-ttu-id="cfd34-136">Excel</span><span class="sxs-lookup"><span data-stu-id="cfd34-136">Excel</span></span> </br><span data-ttu-id="cfd34-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="cfd34-137">PowerPoint</span></span>|<span data-ttu-id="cfd34-138">**在电话和平板电脑上**：</span><span class="sxs-lookup"><span data-stu-id="cfd34-138">**On phones and tablets**:</span></span><br/><span data-ttu-id="cfd34-139">Outlook</span><span class="sxs-lookup"><span data-stu-id="cfd34-139">Outlook</span></span> <br/> <span data-ttu-id="cfd34-140">OneDrive</span><span class="sxs-lookup"><span data-stu-id="cfd34-140">OneDrive</span></span> <br/> <span data-ttu-id="cfd34-141">Word</span><span class="sxs-lookup"><span data-stu-id="cfd34-141">Word</span></span> <br/> <span data-ttu-id="cfd34-142">Excel</span><span class="sxs-lookup"><span data-stu-id="cfd34-142">Excel</span></span> <br/> <span data-ttu-id="cfd34-143">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="cfd34-143">PowerPoint</span></span> <br/> <span data-ttu-id="cfd34-144">**仅电话：**</span><span class="sxs-lookup"><span data-stu-id="cfd34-144">**On phones only:**</span></span> <br/> <span data-ttu-id="cfd34-145">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="cfd34-145">Office Mobile</span></span> |

>[!NOTE]
- ><span data-ttu-id="cfd34-146">对 iOS 10.0 及更高版本的支持包括 iPhone 和 iPad 设备。</span><span class="sxs-lookup"><span data-stu-id="cfd34-146">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
- ><span data-ttu-id="cfd34-147">适用于 Microsoft 365 的移动设备管理不支持 BlackBerry OS 设备的管理。</span><span class="sxs-lookup"><span data-stu-id="cfd34-147">Management of BlackBerry OS devices isn’t supported by Mobile Device Management for Microsoft 365.</span></span> <span data-ttu-id="cfd34-148">使用 BlackBerry Business 云服务 (BBCS) 来自 BlackBerry，以管理 BlackBerry OS 设备。</span><span class="sxs-lookup"><span data-stu-id="cfd34-148">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="cfd34-149">支持运行 Android OS 的 Blackberry 设备作为标准 Android 设备</span><span class="sxs-lookup"><span data-stu-id="cfd34-149">Blackberry devices running Android OS are supported as standard Android devices</span></span>
- ><span data-ttu-id="cfd34-150">如果用户使用移动浏览器访问 Microsoft 365 SharePoint 网站、Office Online 中的文档或 Outlook Web App 中的电子邮件，则不会提示用户进行注册，也不会将其报告为 "违反策略"。</span><span class="sxs-lookup"><span data-stu-id="cfd34-150">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>
    
<span data-ttu-id="cfd34-151">下图显示了具有新设备的用户登录到支持具有基本移动性和安全性的访问控制的应用时，会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="cfd34-151">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="cfd34-152">阻止用户访问应用程序中的 Microsoft 365 资源，直到他们注册其设备。</span><span class="sxs-lookup"><span data-stu-id="cfd34-152">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本移动性和安全访问控制":::

<span data-ttu-id="cfd34-154">注意：在 MDM for Microsoft 365 商业标准中创建的策略和访问规则将替代 exchange ActiveSync 移动设备邮箱策略和在 Exchange 管理中心中创建的设备访问规则。</span><span class="sxs-lookup"><span data-stu-id="cfd34-154">Note:Policies and access rules created in MDM for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="cfd34-155">在 MDM for Microsoft 365 商业标准中注册设备后，应用于该设备的任何 Exchange ActiveSync 移动设备邮箱策略或设备访问规则都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="cfd34-155">After a device is enrolled in MDM for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="cfd34-156">若要了解有关 Exchange ActiveSync 的详细信息，请参阅 exchange [Online 中的 Exchange ActiveSync](https://go.microsoft.com/fwlink/p/?LinkId=524380)。</span><span class="sxs-lookup"><span data-stu-id="cfd34-156">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="cfd34-157">移动设备的策略设置</span><span class="sxs-lookup"><span data-stu-id="cfd34-157">Policy settings for mobile devices</span></span>

<span data-ttu-id="cfd34-158">如果您创建一个策略以阻止打开某些设置的访问，则在使用 [microsoft 365 电子邮件和文档的访问控制](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0?ui=en-us&rs=en-us&ad=us#bkmk_accesscontrol)中列出的受支持的应用程序时，将阻止用户访问 microsoft 365 资源。</span><span class="sxs-lookup"><span data-stu-id="cfd34-158">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0?ui=en-us&rs=en-us&ad=us#bkmk_accesscontrol).</span></span> 

<span data-ttu-id="cfd34-159">可以阻止用户访问 Microsoft 365 资源的设置包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="cfd34-159">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="cfd34-160">安全性</span><span class="sxs-lookup"><span data-stu-id="cfd34-160">Security</span></span>
    
- <span data-ttu-id="cfd34-161">加密</span><span class="sxs-lookup"><span data-stu-id="cfd34-161">Encryption</span></span>
    
- <span data-ttu-id="cfd34-162">越狱断开</span><span class="sxs-lookup"><span data-stu-id="cfd34-162">Jail broken</span></span>
    
- <span data-ttu-id="cfd34-163">托管电子邮件配置文件</span><span class="sxs-lookup"><span data-stu-id="cfd34-163">Managed email profile</span></span>  

<span data-ttu-id="cfd34-164">例如，下图显示了具有已注册设备的用户不符合应用于其设备的移动设备管理策略中的安全设置时会发生的情况。</span><span class="sxs-lookup"><span data-stu-id="cfd34-164">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="cfd34-165">用户使用基本移动性和安全性登录到支持访问控制的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cfd34-165">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="cfd34-166">阻止他们访问应用程序中的 Microsoft 365 资源，直到其设备符合安全设置。</span><span class="sxs-lookup"><span data-stu-id="cfd34-166">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本移动性和安全性合规性邮件":::

<span data-ttu-id="cfd34-168">以下各节列出了可用于帮助保护和管理连接到 Microsoft 365 组织资源的移动设备的策略设置。</span><span class="sxs-lookup"><span data-stu-id="cfd34-168">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="cfd34-169">安全设置</span><span class="sxs-lookup"><span data-stu-id="cfd34-169">Security settings</span></span>

|<span data-ttu-id="cfd34-170">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="cfd34-170">**Setting name**</span></span>|<span data-ttu-id="cfd34-171">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-171">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cfd34-172">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-172">**Android 5 and later**</span></span>|<span data-ttu-id="cfd34-173">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="cfd34-173">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cfd34-174">要求使用密码</span><span class="sxs-lookup"><span data-stu-id="cfd34-174">Require a password</span></span>|<span data-ttu-id="cfd34-175">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-175">Yes</span></span>|<span data-ttu-id="cfd34-176">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-176">Yes</span></span>|<span data-ttu-id="cfd34-177">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-177">Yes</span></span>|
|<span data-ttu-id="cfd34-178">阻止简单密码</span><span class="sxs-lookup"><span data-stu-id="cfd34-178">Prevent simple password</span></span>|<span data-ttu-id="cfd34-179">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-179">Yes</span></span>|<span data-ttu-id="cfd34-180">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-180">No</span></span>|<span data-ttu-id="cfd34-181">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-181">No</span></span>|
|<span data-ttu-id="cfd34-182">需要字母数字密码</span><span class="sxs-lookup"><span data-stu-id="cfd34-182">Require an alphanumeric password</span></span>|<span data-ttu-id="cfd34-183">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-183">Yes</span></span>|<span data-ttu-id="cfd34-184">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-184">No</span></span>|<span data-ttu-id="cfd34-185">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-185">No</span></span>|
|<span data-ttu-id="cfd34-186">最短密码长度</span><span class="sxs-lookup"><span data-stu-id="cfd34-186">Minimum password length</span></span> |<span data-ttu-id="cfd34-187">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-187">Yes</span></span>|<span data-ttu-id="cfd34-188">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-188">Yes</span></span>|<span data-ttu-id="cfd34-189">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-189">Yes</span></span>|
|<span data-ttu-id="cfd34-190">擦除设备之前的登录失败次数</span><span class="sxs-lookup"><span data-stu-id="cfd34-190">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="cfd34-191">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-191">Yes</span></span>|<span data-ttu-id="cfd34-192">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-192">Yes</span></span>|<span data-ttu-id="cfd34-193">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-193">Yes</span></span>|
|<span data-ttu-id="cfd34-194">设备锁定之前的不活动分钟数</span><span class="sxs-lookup"><span data-stu-id="cfd34-194">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="cfd34-195">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-195">Yes</span></span>|<span data-ttu-id="cfd34-196">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-196">Yes</span></span>|<span data-ttu-id="cfd34-197">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-197">Yes</span></span>|
|<span data-ttu-id="cfd34-198">密码过期 (天) </span><span class="sxs-lookup"><span data-stu-id="cfd34-198">Password expiration (days)</span></span> |<span data-ttu-id="cfd34-199">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-199">Yes</span></span>|<span data-ttu-id="cfd34-200">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-200">Yes</span></span>|<span data-ttu-id="cfd34-201">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-201">Yes</span></span>|
|<span data-ttu-id="cfd34-202">记住密码历史记录并防止重复使用</span><span class="sxs-lookup"><span data-stu-id="cfd34-202">Remember password history and prevent reuse</span></span> |<span data-ttu-id="cfd34-203">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-203">Yes</span></span>|<span data-ttu-id="cfd34-204">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-204">Yes</span></span>|<span data-ttu-id="cfd34-205">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-205">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="cfd34-206">加密设置</span><span class="sxs-lookup"><span data-stu-id="cfd34-206">Encryption settings</span></span> 

|<span data-ttu-id="cfd34-207">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="cfd34-207">**Setting name**</span></span>|<span data-ttu-id="cfd34-208">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-208">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cfd34-209">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-209">**Android 5 and later**</span></span>|<span data-ttu-id="cfd34-210">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="cfd34-210">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cfd34-211">要求设备<sup>1</sup>上的数据加密</span><span class="sxs-lookup"><span data-stu-id="cfd34-211">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="cfd34-212">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-212">No</span></span>|<span data-ttu-id="cfd34-213">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-213">Yes</span></span>|<span data-ttu-id="cfd34-214">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-214">Yes</span></span>|

<span data-ttu-id="cfd34-215"><sup>1</sup>使用 Samsung Knox，还可以要求对存储卡加密。</span><span class="sxs-lookup"><span data-stu-id="cfd34-215"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span> 

## <a name="jail-broken-setting"></a><span data-ttu-id="cfd34-216">越狱中断设置</span><span class="sxs-lookup"><span data-stu-id="cfd34-216">Jail broken setting</span></span> 

|<span data-ttu-id="cfd34-217">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="cfd34-217">**Setting name**</span></span>|<span data-ttu-id="cfd34-218">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-218">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cfd34-219">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-219">**Android 5 and later**</span></span>|<span data-ttu-id="cfd34-220">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="cfd34-220">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cfd34-221">设备不能越狱断开或根</span><span class="sxs-lookup"><span data-stu-id="cfd34-221">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="cfd34-222">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-222">Yes</span></span>|<span data-ttu-id="cfd34-223">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-223">Yes</span></span>|<span data-ttu-id="cfd34-224">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-224">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="cfd34-225">托管电子邮件配置文件选项</span><span class="sxs-lookup"><span data-stu-id="cfd34-225">Managed email profile option</span></span> 

<span data-ttu-id="cfd34-226">如果用户使用手动创建的电子邮件配置文件，则可通过以下选项阻止用户访问其 Microsoft 365 电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cfd34-226">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="cfd34-227">IOS 设备上的用户必须先删除其手动创建的电子邮件配置文件，然后才能访问其电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cfd34-227">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="cfd34-228">删除配置文件后，系统会自动在该设备上创建一个新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="cfd34-228">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="cfd34-229">有关最终用户如何符合标准的说明，请参阅 [找到现有的电子邮件帐户](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)。</span><span class="sxs-lookup"><span data-stu-id="cfd34-229">For instructions on how end users can get compliant, see [An existing email account was found](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="cfd34-230">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="cfd34-230">**Setting name**</span></span>|<span data-ttu-id="cfd34-231">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-231">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cfd34-232">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-232">**Android 5 and later**</span></span>|<span data-ttu-id="cfd34-233">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="cfd34-233">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cfd34-234">电子邮件配置文件已管理</span><span class="sxs-lookup"><span data-stu-id="cfd34-234">Email profile is managed</span></span> |<span data-ttu-id="cfd34-235">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-235">Yes</span></span>|<span data-ttu-id="cfd34-236">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-236">No</span></span>|<span data-ttu-id="cfd34-237">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-237">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="cfd34-238">云设置</span><span class="sxs-lookup"><span data-stu-id="cfd34-238">Cloud settings</span></span> 

|<span data-ttu-id="cfd34-239">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="cfd34-239">**Setting name**</span></span>|<span data-ttu-id="cfd34-240">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-240">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cfd34-241">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-241">**Android 5 and later**</span></span>|<span data-ttu-id="cfd34-242">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="cfd34-242">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cfd34-243">需要加密备份</span><span class="sxs-lookup"><span data-stu-id="cfd34-243">Require encrypted backup</span></span> |<span data-ttu-id="cfd34-244">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-244">Yes</span></span>|<span data-ttu-id="cfd34-245">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-245">No</span></span>|<span data-ttu-id="cfd34-246">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-246">No</span></span>|
|<span data-ttu-id="cfd34-247">阻止云备份</span><span class="sxs-lookup"><span data-stu-id="cfd34-247">Block cloud backup</span></span> |<span data-ttu-id="cfd34-248">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-248">Yes</span></span>|<span data-ttu-id="cfd34-249">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-249">No</span></span>|<span data-ttu-id="cfd34-250">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-250">No</span></span>|
|<span data-ttu-id="cfd34-251">阻止文档同步</span><span class="sxs-lookup"><span data-stu-id="cfd34-251">Block document synchronization</span></span> |<span data-ttu-id="cfd34-252">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-252">Yes</span></span>|<span data-ttu-id="cfd34-253">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-253">No</span></span>|<span data-ttu-id="cfd34-254">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-254">No</span></span>|
|<span data-ttu-id="cfd34-255">阻止照片同步</span><span class="sxs-lookup"><span data-stu-id="cfd34-255">Block photo synchronization</span></span>  |<span data-ttu-id="cfd34-256">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-256">Yes</span></span>|<span data-ttu-id="cfd34-257">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-257">No</span></span>|<span data-ttu-id="cfd34-258">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-258">No</span></span>|
|<span data-ttu-id="cfd34-259">允许 Google 备份</span><span class="sxs-lookup"><span data-stu-id="cfd34-259">Allow Google backup</span></span>  |<span data-ttu-id="cfd34-260">不适用</span><span class="sxs-lookup"><span data-stu-id="cfd34-260">N/A</span></span>|<span data-ttu-id="cfd34-261">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-261">No</span></span>|<span data-ttu-id="cfd34-262">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-262">Yes</span></span>|
|<span data-ttu-id="cfd34-263">允许 Google 帐户自动同步</span><span class="sxs-lookup"><span data-stu-id="cfd34-263">Allow Google account auto sync</span></span>  |<span data-ttu-id="cfd34-264">不适用</span><span class="sxs-lookup"><span data-stu-id="cfd34-264">N/A</span></span>|<span data-ttu-id="cfd34-265">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-265">No</span></span>|<span data-ttu-id="cfd34-266">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-266">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="cfd34-267">系统设置</span><span class="sxs-lookup"><span data-stu-id="cfd34-267">System settings</span></span> 

|<span data-ttu-id="cfd34-268">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="cfd34-268">**Setting name**</span></span>|<span data-ttu-id="cfd34-269">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-269">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cfd34-270">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-270">**Android 5 and later**</span></span>|<span data-ttu-id="cfd34-271">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="cfd34-271">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cfd34-272">阻止屏幕捕获</span><span class="sxs-lookup"><span data-stu-id="cfd34-272">Block screen capture</span></span> |<span data-ttu-id="cfd34-273">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-273">Yes</span></span>|<span data-ttu-id="cfd34-274">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-274">No</span></span>|<span data-ttu-id="cfd34-275">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-275">Yes</span></span>|
|<span data-ttu-id="cfd34-276">阻止从设备发送诊断数据</span><span class="sxs-lookup"><span data-stu-id="cfd34-276">Block sending diagnostic data from device</span></span> |<span data-ttu-id="cfd34-277">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-277">Yes</span></span>|<span data-ttu-id="cfd34-278">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-278">No</span></span>|<span data-ttu-id="cfd34-279">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-279">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="cfd34-280">应用程序设置</span><span class="sxs-lookup"><span data-stu-id="cfd34-280">Application settings</span></span> 

|<span data-ttu-id="cfd34-281">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="cfd34-281">**Setting name**</span></span>|<span data-ttu-id="cfd34-282">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-282">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cfd34-283">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-283">**Android 5 and later**</span></span>|<span data-ttu-id="cfd34-284">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="cfd34-284">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cfd34-285">阻止设备上的视频会议</span><span class="sxs-lookup"><span data-stu-id="cfd34-285">Block video conferences on device</span></span> |<span data-ttu-id="cfd34-286">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-286">Yes</span></span>|<span data-ttu-id="cfd34-287">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-287">No</span></span>|<span data-ttu-id="cfd34-288">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-288">No</span></span>|
|<span data-ttu-id="cfd34-289">阻止对应用商店的访问</span><span class="sxs-lookup"><span data-stu-id="cfd34-289">Block access to application store</span></span> |<span data-ttu-id="cfd34-290">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-290">Yes</span></span>|<span data-ttu-id="cfd34-291">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-291">No</span></span>|<span data-ttu-id="cfd34-292">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-292">Yes</span></span>|
|<span data-ttu-id="cfd34-293">在访问应用商店时需要密码</span><span class="sxs-lookup"><span data-stu-id="cfd34-293">Require password when accessing application store</span></span> |<span data-ttu-id="cfd34-294">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-294">No</span></span>|<span data-ttu-id="cfd34-295">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-295">Yes</span></span>|<span data-ttu-id="cfd34-296">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-296">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="cfd34-297">设备功能设置</span><span class="sxs-lookup"><span data-stu-id="cfd34-297">Device capabilities settings</span></span> 

|<span data-ttu-id="cfd34-298">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="cfd34-298">**Setting name**</span></span>|<span data-ttu-id="cfd34-299">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-299">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cfd34-300">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-300">**Android 5 and later**</span></span>|<span data-ttu-id="cfd34-301">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="cfd34-301">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cfd34-302">阻止与可移动存储的连接</span><span class="sxs-lookup"><span data-stu-id="cfd34-302">Block connection with removable storage</span></span> |<span data-ttu-id="cfd34-303">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-303">Yes</span></span>|<span data-ttu-id="cfd34-304">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-304">Yes</span></span>|<span data-ttu-id="cfd34-305">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-305">No</span></span>|
|<span data-ttu-id="cfd34-306">阻止蓝牙连接</span><span class="sxs-lookup"><span data-stu-id="cfd34-306">Block Bluetooth connection</span></span> |<span data-ttu-id="cfd34-307">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-307">Yes</span></span>|<span data-ttu-id="cfd34-308">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-308">Yes</span></span>|<span data-ttu-id="cfd34-309">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-309">No</span></span>|

##  <a name="additional-settings"></a><span data-ttu-id="cfd34-310">其他设置</span><span class="sxs-lookup"><span data-stu-id="cfd34-310">Additional settings</span></span> 

<span data-ttu-id="cfd34-311">您可以使用 PowerShell cmdlet 设置以下附加策略设置。</span><span class="sxs-lookup"><span data-stu-id="cfd34-311">You can set the following additional policy settings by using PowerShell cmdlets.</span></span> <span data-ttu-id="cfd34-312">有关详细信息，请参阅 [Security & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="cfd34-312">For more information, see [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

|<span data-ttu-id="cfd34-313">**设置名称**</span><span class="sxs-lookup"><span data-stu-id="cfd34-313">**Setting name**</span></span>|<span data-ttu-id="cfd34-314">**iOS 7.1 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-314">**iOS 7.1 and later**</span></span>|<span data-ttu-id="cfd34-315">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="cfd34-315">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cfd34-316">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="cfd34-316">CameraEnabled</span></span>|<span data-ttu-id="cfd34-317">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-317">Yes</span></span>|<span data-ttu-id="cfd34-318">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-318">Yes</span></span>|
|<span data-ttu-id="cfd34-319">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="cfd34-319">RegionRatings</span></span>|<span data-ttu-id="cfd34-320">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-320">Yes</span></span>|<span data-ttu-id="cfd34-321">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-321">No</span></span>|
|<span data-ttu-id="cfd34-322">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="cfd34-322">MoviesRatings</span></span>|<span data-ttu-id="cfd34-323">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-323">Yes</span></span>|<span data-ttu-id="cfd34-324">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-324">No</span></span>|
|<span data-ttu-id="cfd34-325">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="cfd34-325">TVShowsRating</span></span> |<span data-ttu-id="cfd34-326">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-326">Yes</span></span>|<span data-ttu-id="cfd34-327">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-327">No</span></span>|
|<span data-ttu-id="cfd34-328">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="cfd34-328">AppsRatings</span></span> |<span data-ttu-id="cfd34-329">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-329">Yes</span></span>|<span data-ttu-id="cfd34-330">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-330">No</span></span>|
|<span data-ttu-id="cfd34-331">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="cfd34-331">AllowVoiceDialing</span></span> |<span data-ttu-id="cfd34-332">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-332">Yes</span></span>|<span data-ttu-id="cfd34-333">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-333">No</span></span>|
|<span data-ttu-id="cfd34-334">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="cfd34-334">AllowVoiceAssistant</span></span> |<span data-ttu-id="cfd34-335">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-335">Yes</span></span>|<span data-ttu-id="cfd34-336">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-336">No</span></span>|
|<span data-ttu-id="cfd34-337">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="cfd34-337">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="cfd34-338">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-338">Yes</span></span>|<span data-ttu-id="cfd34-339">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-339">No</span></span>|
|<span data-ttu-id="cfd34-340">AllowPassbookWhileLocked</span><span class="sxs-lookup"><span data-stu-id="cfd34-340">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="cfd34-341">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-341">Yes</span></span>|<span data-ttu-id="cfd34-342">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-342">No</span></span>|
|<span data-ttu-id="cfd34-343">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="cfd34-343">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="cfd34-344">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-344">Yes</span></span>|<span data-ttu-id="cfd34-345">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-345">No</span></span>|
|<span data-ttu-id="cfd34-346">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="cfd34-346">PasswordQuality</span></span> |<span data-ttu-id="cfd34-347">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-347">No</span></span>|<span data-ttu-id="cfd34-348">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-348">Yes</span></span>|
|<span data-ttu-id="cfd34-349">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="cfd34-349">SystemSecurityTLS</span></span>  |<span data-ttu-id="cfd34-350">是</span><span class="sxs-lookup"><span data-stu-id="cfd34-350">Yes</span></span>|<span data-ttu-id="cfd34-351">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-351">No</span></span>|
|<span data-ttu-id="cfd34-352">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="cfd34-352">WLANEnabled</span></span>  |<span data-ttu-id="cfd34-353">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-353">No</span></span>|<span data-ttu-id="cfd34-354">否</span><span class="sxs-lookup"><span data-stu-id="cfd34-354">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="cfd34-355">Windows 支持的设置</span><span class="sxs-lookup"><span data-stu-id="cfd34-355">Settings supported by Windows</span></span> 

<span data-ttu-id="cfd34-356">你可以通过将 Windows 10 设备注册为移动设备来管理这些设备。</span><span class="sxs-lookup"><span data-stu-id="cfd34-356">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="cfd34-357">部署适用的策略后，在首次使用内置电子邮件应用访问其 Microsoft 365 电子邮件时，将需要具有 Windows 10 设备的用户注册基本移动性和安全性 (需要 Azure AD 高级订阅) 。</span><span class="sxs-lookup"><span data-stu-id="cfd34-357">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="cfd34-358">已注册为移动设备的 Windows 10 设备支持以下设置。</span><span class="sxs-lookup"><span data-stu-id="cfd34-358">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="cfd34-359">这些设置不会阻止用户访问 Microsoft 365 资源。</span><span class="sxs-lookup"><span data-stu-id="cfd34-359">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="cfd34-360">安全设置</span><span class="sxs-lookup"><span data-stu-id="cfd34-360">Security settings</span></span>

- <span data-ttu-id="cfd34-361">需要字母数字密码</span><span class="sxs-lookup"><span data-stu-id="cfd34-361">Require an alphanumeric password</span></span>

- <span data-ttu-id="cfd34-362">最短密码长度</span><span class="sxs-lookup"><span data-stu-id="cfd34-362">Minimum password length</span></span>
    
- <span data-ttu-id="cfd34-363">擦除设备之前的登录失败次数</span><span class="sxs-lookup"><span data-stu-id="cfd34-363">Number of sign-in failures before device is wiped</span></span>
    
- <span data-ttu-id="cfd34-364">设备锁定之前的不活动分钟数</span><span class="sxs-lookup"><span data-stu-id="cfd34-364">Minutes of inactivity before device is locked</span></span>
    
- <span data-ttu-id="cfd34-365">密码过期 (天) </span><span class="sxs-lookup"><span data-stu-id="cfd34-365">Password expiration (days)</span></span>
    
- <span data-ttu-id="cfd34-366">记住密码历史记录并防止重复使用</span><span class="sxs-lookup"><span data-stu-id="cfd34-366">Remember password history and prevent reuse</span></span>   

>[!NOTE]
><span data-ttu-id="cfd34-367">以下设置控制密码仅控制本地 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="cfd34-367">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="cfd34-368">通过加入域或 Azure Active Directory 提供的 Windows 帐户不受这些设置的影响。</span><span class="sxs-lookup"><span data-stu-id="cfd34-368">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="cfd34-369">系统设置</span><span class="sxs-lookup"><span data-stu-id="cfd34-369">System settings</span></span>

<span data-ttu-id="cfd34-370">阻止从设备发送诊断数据。</span><span class="sxs-lookup"><span data-stu-id="cfd34-370">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="cfd34-371">其他设置</span><span class="sxs-lookup"><span data-stu-id="cfd34-371">Additional settings</span></span>

<span data-ttu-id="cfd34-372">您可以使用 PowerShell cmdlet 设置这些附加策略设置：</span><span class="sxs-lookup"><span data-stu-id="cfd34-372">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="cfd34-373">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="cfd34-373">AllowConvenienceLogon</span></span>
    
- <span data-ttu-id="cfd34-374">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="cfd34-374">UserAccountControlStatus</span></span>
    
- <span data-ttu-id="cfd34-375">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="cfd34-375">FirewallStatus</span></span>
    
- <span data-ttu-id="cfd34-376">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="cfd34-376">AutoUpdateStatus</span></span>
    
- <span data-ttu-id="cfd34-377">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="cfd34-377">AntiVirusStatus</span></span>   

- <span data-ttu-id="cfd34-378">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="cfd34-378">AntiVirusSignatureStatus</span></span>
    
- <span data-ttu-id="cfd34-379">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="cfd34-379">SmartScreenEnabled</span></span>
    
- <span data-ttu-id="cfd34-380">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="cfd34-380">WorkFoldersSyncUrl</span></span>
    

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="cfd34-381">远程擦除移动设备</span><span class="sxs-lookup"><span data-stu-id="cfd34-381">Remotely wipe a mobile device</span></span>

<span data-ttu-id="cfd34-382">如果设备丢失或被盗，可以通过执行从 Security & 合规中心 >**数据丢失防护**  >  **设备管理**中的擦除操作，来删除敏感的组织数据并帮助阻止对 Microsoft 365 组织资源的访问。</span><span class="sxs-lookup"><span data-stu-id="cfd34-382">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="cfd34-383">您可以执行选择性擦除以仅删除组织数据或完全擦除以删除设备中的所有信息，并将其还原到其出厂设置。</span><span class="sxs-lookup"><span data-stu-id="cfd34-383">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="cfd34-384">有关详细信息，请参阅 [在基本移动和安全中擦除移动设备](wipe-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="cfd34-384">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cfd34-385">相关主题</span><span class="sxs-lookup"><span data-stu-id="cfd34-385">Related topics</span></span>

[<span data-ttu-id="cfd34-386">Microsoft 365 的基本移动性和安全性概述</span><span class="sxs-lookup"><span data-stu-id="cfd34-386">Overview of Basic Mobility and Security for Microsoft 365</span></span>](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[<span data-ttu-id="cfd34-387">在基本移动性和安全性中创建设备安全策略</span><span class="sxs-lookup"><span data-stu-id="cfd34-387">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies-in-basic-mmobility-and-security.md)