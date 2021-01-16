---
title: 设置基本移动性和安全性
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
description: 设置基本移动性和安全性，以保护和管理用户的移动设备。
ms.openlocfilehash: 38f122141b370468bc591df49b3e1891a8a66a43
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876860"
---
# <a name="set-up-basic-mobility-and-security"></a><span data-ttu-id="757b1-103">设置基本移动性和安全性</span><span class="sxs-lookup"><span data-stu-id="757b1-103">Set up Basic Mobility and Security</span></span>

<span data-ttu-id="757b1-104">内置的 Microsoft 365 基本移动性和安全性可帮助你保护和管理用户的移动设备，如 iPhone、iPad、Android 和 Windows 手机。</span><span class="sxs-lookup"><span data-stu-id="757b1-104">The built-in Basic Mobility and Security for Microsoft 365 helps you secure and manage users' mobile devices such as iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="757b1-105">可以创建和管理设备安全策略，远程擦除设备，以及查看详细的设备报告。</span><span class="sxs-lookup"><span data-stu-id="757b1-105">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

<span data-ttu-id="757b1-106">有问题？</span><span class="sxs-lookup"><span data-stu-id="757b1-106">Have questions?</span></span> <span data-ttu-id="757b1-107">有关帮助解决常见问题的常见问题解答，请参阅" [基本 ](frequently-asked-questions.md)移动性和安全性常见问题解答" (常见问题) 。</span><span class="sxs-lookup"><span data-stu-id="757b1-107">For a FAQ to help address common questions, see [Basic Mobility and Security Frequently-asked questions (FAQ)](frequently-asked-questions.md).</span></span> <span data-ttu-id="757b1-108">请注意，不能使用委派管理员帐户管理基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="757b1-108">Be aware that you cannot use a delegated administrator account to manage Basic Mobility and Security.</span></span> <span data-ttu-id="757b1-109">有关详细信息，请参阅合作伙伴 [：提供委派管理](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)。</span><span class="sxs-lookup"><span data-stu-id="757b1-109">For more info, see [Partners: Offer delegated administration](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> 

<span data-ttu-id="757b1-110">设备管理是安全与合规&的一部分，因此你需要前往那里启动基本移动性和安全性设置。</span><span class="sxs-lookup"><span data-stu-id="757b1-110">Device management is part of the Security & Compliance Center so you'll need to go there to kick off Basic Mobility and Security setup.</span></span>

## <a name="activate-the-basic-mobility-and-security-service"></a><span data-ttu-id="757b1-111">激活基本移动和安全服务</span><span class="sxs-lookup"><span data-stu-id="757b1-111">Activate the Basic Mobility and Security service</span></span>

1. <span data-ttu-id="757b1-112">使用全局管理员帐户登录 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="757b1-112">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="757b1-113">转到["激活基本移动性和安全性"。](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)</span><span class="sxs-lookup"><span data-stu-id="757b1-113">Go to [Activate Basic Mobility and Security](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span>

   <span data-ttu-id="757b1-114">激活基本移动性和安全性可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="757b1-114">It can take some time to activate Basic Mobility and Security.</span></span> <span data-ttu-id="757b1-115">完成后，你将收到一封电子邮件，说明要执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="757b1-115">When it finishes, you'll receive an email that explains the next steps to take.</span></span>

## <a name="set-up-mobile-device-management"></a><span data-ttu-id="757b1-116">设置移动设备管理</span><span class="sxs-lookup"><span data-stu-id="757b1-116">Set up Mobile Device Management</span></span>

<span data-ttu-id="757b1-117">服务准备就绪后，请完成以下步骤以完成设置。</span><span class="sxs-lookup"><span data-stu-id="757b1-117">When the service is ready, complete the following steps to finish setup.</span></span>

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a><span data-ttu-id="757b1-118">步骤 1： (配置) 移动性和安全性的域的必需步骤</span><span class="sxs-lookup"><span data-stu-id="757b1-118">Step 1: (Required) Configure domains for Basic Mobility and Security</span></span>

<span data-ttu-id="757b1-119">如果你没有与 Microsoft 365 关联的自定义域，或者没有管理 Windows 设备，可以跳过此部分。</span><span class="sxs-lookup"><span data-stu-id="757b1-119">If you don't have a custom domain associated with Microsoft 365 or if you're not managing Windows devices, you can skip this section.</span></span> <span data-ttu-id="757b1-120">否则，您需要在 DNS 主机上为域添加 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="757b1-120">Otherwise, you'll need to add DNS records for the domain at your DNS host.</span></span> <span data-ttu-id="757b1-121">如果你已添加记录，作为使用 Microsoft 365 设置域的一部分，你已全部设置。</span><span class="sxs-lookup"><span data-stu-id="757b1-121">If you've added the records already, as part of setting up your domain with Microsoft 365, you're all set.</span></span> <span data-ttu-id="757b1-122">添加记录后，组织中使用使用自定义域的电子邮件地址登录 Windows 设备的 Microsoft 365 用户将被重定向以注册基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="757b1-122">After you add the records, Microsoft 365 users in your organization who sign in on their Windows device with an email address that uses your custom domain are redirected to enroll in Basic Mobility and Security.</span></span>

<span data-ttu-id="757b1-123">需要设置记录的帮助？</span><span class="sxs-lookup"><span data-stu-id="757b1-123">Need help setting up the records?</span></span> <span data-ttu-id="757b1-124">查找你的域注册机构，然后选择注册机构名称以转到有关在"添加 DNS 记录"中提供的列表中创建 DNS 记录的分步帮助以 [连接你的域](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。</span><span class="sxs-lookup"><span data-stu-id="757b1-124">Find your domain registrar and select the registrar name to go to step-by-step help for creating DNS record in the list provided in [Add DNS records to connect your domain](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span> <span data-ttu-id="757b1-125">使用这些说明创建在不使用 [Azure AD Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)的情况下简化 Windows 注册中所述的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="757b1-125">Use those instructions to create CNAME records described in [Simplify Windows enrollment without Azure AD Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).</span></span>

<span data-ttu-id="757b1-126">添加这两条 CNAME 记录后，返回到安全&合规中心，然后转到数据丢失防护设备管理以完成下一  >     步。</span><span class="sxs-lookup"><span data-stu-id="757b1-126">After you add the two CNAME records, go back to the Security & Compliance Center and go to **Data loss prevention** > **Device management** to complete the next step.</span></span>

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="757b1-127">步骤 2： (为 iOS) 配置 APNs 证书所需的步骤</span><span class="sxs-lookup"><span data-stu-id="757b1-127">Step 2: (Required) Configure an APNs Certificate for iOS devices</span></span>

<span data-ttu-id="757b1-128">若要管理 iOS 设备（如 iPad 和 iPhone），需要创建 APN 证书。</span><span class="sxs-lookup"><span data-stu-id="757b1-128">To manage iOS devices like iPad and iPhones, you need to create an APNs certificate.</span></span>

1. <span data-ttu-id="757b1-129">使用全局管理员帐户登录 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="757b1-129">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="757b1-130">在浏览器类型中  [https://protection.office.com](https://protection.office.com/) ：。</span><span class="sxs-lookup"><span data-stu-id="757b1-130">In your browser type: [https://protection.office.com](https://protection.office.com/).</span></span>

3. <span data-ttu-id="757b1-131">选择  **数据丢失防护**   >  **设备管理**，然后选择适用于 **iOS 设备的 APNs 证书**。</span><span class="sxs-lookup"><span data-stu-id="757b1-131">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="757b1-132">在"Apple 推送通知证书设置"页上，选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="757b1-132">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="757b1-133">选择 **"下载 CSR 文件**"，将证书签名请求保存到计算机上你记住   的某个位置。</span><span class="sxs-lookup"><span data-stu-id="757b1-133">Select **Download your CSR file** and save the Certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="757b1-134">选择 **"下一步"。**</span><span class="sxs-lookup"><span data-stu-id="757b1-134">Select **Next**.</span></span>

6. <span data-ttu-id="757b1-135">在"创建 APNs 证书"页上：</span><span class="sxs-lookup"><span data-stu-id="757b1-135">On the Create an APNs certificate page:</span></span>

   - <span data-ttu-id="757b1-136">选择 Apple APNS 门户以打开 Apple 推送证书门户。</span><span class="sxs-lookup"><span data-stu-id="757b1-136">Select Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
   - <span data-ttu-id="757b1-137">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="757b1-137">Sign in with an Apple ID.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="757b1-p107">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="757b1-p107">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

   - <span data-ttu-id="757b1-140">选择"创建证书"并接受使用条款。</span><span class="sxs-lookup"><span data-stu-id="757b1-140">Select Create a Certificate and accept the Terms of Use.</span></span>
   - <span data-ttu-id="757b1-141">浏览到从 Microsoft 365 下载到计算机的证书签名请求，然后选择Upload。</span><span class="sxs-lookup"><span data-stu-id="757b1-141">Browse to the Certificate signing request you downloaded to your computer from Microsoft 365 and selectUpload.</span></span>
   - <span data-ttu-id="757b1-142">Download the APN certificate created by the Apple Push Certificate Portal to your computer.</span><span class="sxs-lookup"><span data-stu-id="757b1-142">Download the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span>

     > [!TIP]
     > <span data-ttu-id="757b1-143">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="757b1-143">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="757b1-144">返回到 Microsoft 365，然后选择"下 **一步"。**</span><span class="sxs-lookup"><span data-stu-id="757b1-144">Go back to Microsoft 365 and select **Next**.</span></span>

8. <span data-ttu-id="757b1-145"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="757b1-145">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="757b1-146">选择  **"完成"。**</span><span class="sxs-lookup"><span data-stu-id="757b1-146">Select  **Finish**.</span></span>

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a><span data-ttu-id="757b1-147">步骤 3： (建议) 设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="757b1-147">Step 3: (Recommended) Set up multi-factor authentication</span></span>

<span data-ttu-id="757b1-148">MFA 通过要求第二种形式的身份验证来帮助确保登录到 Microsoft 365 进行移动设备注册。</span><span class="sxs-lookup"><span data-stu-id="757b1-148">MFA helps secure the sign in to Microsoft 365 for mobile device enrollment by requiring a second form of authentication.</span></span> <span data-ttu-id="757b1-149">在正确输入工作帐户密码后，用户必须确认其移动设备上的电话呼叫、短信或应用通知。</span><span class="sxs-lookup"><span data-stu-id="757b1-149">Users are required to acknowledge a phone call, text message, or app notification on their mobile device after correctly entering their work account password.</span></span> <span data-ttu-id="757b1-150">他们只能在完成第二种形式的身份验证后注册设备。</span><span class="sxs-lookup"><span data-stu-id="757b1-150">They can enroll their device only after this second form of authentication is completed.</span></span> <span data-ttu-id="757b1-151">在基本移动性和安全性中注册用户设备后，用户只能使用工作帐户访问 Microsoft 365 资源。</span><span class="sxs-lookup"><span data-stu-id="757b1-151">After user devices are enrolled in Basic Mobility and Security, users can access Microsoft 365 resources with only their work account.</span></span>

<span data-ttu-id="757b1-152">若要了解如何在 Azure AD 门户中打开 MFA，请参阅 ["设置多重身份验证"。](https://go.microsoft.com/fwlink/p/?LinkId=519255)</span><span class="sxs-lookup"><span data-stu-id="757b1-152">To learn how to turn on MFA in the Azure AD portal, see [Set up multi-factor authentication](https://go.microsoft.com/fwlink/p/?LinkId=519255).</span></span>

<span data-ttu-id="757b1-153">设置 MFA 后，返回到安全与合规&并导航到数据丢失防护  \*\*\*\*   >  **设备管理** 设备策略以   >  \*\*\*\*   完成下一步。</span><span class="sxs-lookup"><span data-stu-id="757b1-153">After you set up MFA, go back to the Security & Compliance Center and navigate to  **Data loss prevention** > **Device management** > **Device policies** to complete the next step.</span></span>

### <a name="step-4-recommended-manage-device-security-policies"></a><span data-ttu-id="757b1-154">步骤 4： (建议) 管理设备安全策略</span><span class="sxs-lookup"><span data-stu-id="757b1-154">Step 4: (Recommended) Manage device security policies</span></span>

<span data-ttu-id="757b1-155">下一步是创建和部署设备安全策略，以帮助保护 Microsoft 365 组织数据。</span><span class="sxs-lookup"><span data-stu-id="757b1-155">The next step is to create and deploy device security policies to help protect your Microsoft 365 organization data.</span></span> <span data-ttu-id="757b1-156">例如，如果用户丢失设备，可以通过创建一个策略，在 5 分钟不活动后锁定设备，在三次登录失败后擦除设备，以帮助防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="757b1-156">For example, you can help prevent data loss if a user loses their device by creating a policy to lock devices after five minutes of inactivity and wipe devices after three sign-in failures.</span></span>

1. <span data-ttu-id="757b1-157">使用全局管理员帐户登录 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="757b1-157">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="757b1-158">选择 ["激活移动设备管理"。](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)</span><span class="sxs-lookup"><span data-stu-id="757b1-158">Select [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="757b1-159">如果服务已激活，则改为激活步骤，你将看到一个指向"管理设备 ["的链接](https://admin.microsoft.com/adminportal/home#/MifoDevices)   。</span><span class="sxs-lookup"><span data-stu-id="757b1-159">If the service is activated, instead the activation steps you'll see a link to [Manage Devices](https://admin.microsoft.com/adminportal/home#/MifoDevices) .</span></span>

3. <span data-ttu-id="757b1-160">转到 **设备策略**。</span><span class="sxs-lookup"><span data-stu-id="757b1-160">Go to **Device policies**.</span></span>

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本安全和移动策略设置":::

4. <span data-ttu-id="757b1-162">按照基本移动性和安全性中的"创建设备安全策略"中的步骤，创建和部署适合组织 [的设备安全策略](create-device-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="757b1-162">Create and deploy device security policies appropriate for your organization following the steps in [Create device security policies in Basic Mobility and Security](create-device-security-policies.md).</span></span>

> [!TIP]
>
> - <span data-ttu-id="757b1-163">创建新策略时，可能需要设置该策略以在用户设备不符合策略时允许访问并报告策略违反。</span><span class="sxs-lookup"><span data-stu-id="757b1-163">When you create a new policy, you might want to set the policy to allow access and report policy violation where a user device isn't compliant with the policy.</span></span> <span data-ttu-id="757b1-164">这允许你查看受策略影响的移动设备数，而不会阻止对 Microsoft 365 的访问。</span><span class="sxs-lookup"><span data-stu-id="757b1-164">This allows you see how many mobile devices are impacted by the policy without blocking access to Microsoft 365.</span></span>
>
> - <span data-ttu-id="757b1-165">在向组织中的每个人部署新策略之前，我们建议在少数用户使用的设备上测试新策略。</span><span class="sxs-lookup"><span data-stu-id="757b1-165">Before you deploy a new policy to everyone in your organization, we recommend you test it on the devices used by a small number of users.</span></span>
>
> - <span data-ttu-id="757b1-166">此外，在部署策略之前，请让组织了解在基本移动性和安全性中注册设备的潜在影响。</span><span class="sxs-lookup"><span data-stu-id="757b1-166">Also, before you deploy policies, let your organization know the potential impacts of enrolling a device in Basic Mobility and Security.</span></span> <span data-ttu-id="757b1-167">根据策略设置方式，不符合策略 (设备可能会) Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="757b1-167">Depending on how you set up the policies, devices that don't comply with policies (non-compliant devices) could be blocked from accessing Microsoft 365.</span></span> <span data-ttu-id="757b1-168">不兼容的设备可能还安装了应用、照片和其他个人信息，如果擦除设备，在已注册的设备上可能会删除这些信息。</span><span class="sxs-lookup"><span data-stu-id="757b1-168">Non-compliant devices might also have apps installed, photos, and other personal information which, on an enrolled device, could be deleted if the device is wiped.</span></span> <span data-ttu-id="757b1-169">有关详细信息，请参阅"基本移动性和安全性"中的"[擦除移动设备"。](wipe-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="757b1-169">For more info, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="make-sure-users-enroll-their-devices"></a><span data-ttu-id="757b1-170">确保用户注册其设备</span><span class="sxs-lookup"><span data-stu-id="757b1-170">Make sure users enroll their devices</span></span>

<span data-ttu-id="757b1-171">创建和部署移动设备管理策略后，组织中应用设备策略的每个许可 Microsoft 365 用户下次从移动设备登录 Microsoft 365 时会收到一条注册消息。</span><span class="sxs-lookup"><span data-stu-id="757b1-171">After you've created and deployed a mobile device management policy, each licensed Microsoft 365 user in your organization that the device policy applies receives an enrollment message the next time they sign into Microsoft 365 from their mobile device.</span></span> <span data-ttu-id="757b1-172">他们必须完成注册和激活步骤，然后才能访问 Microsoft 365 电子邮件和文档。</span><span class="sxs-lookup"><span data-stu-id="757b1-172">They must complete the enrollment and activation steps before they can access Microsoft 365 email and documents.</span></span> <span data-ttu-id="757b1-173">有关详细信息，请参阅使用基本移动性和安全性 [注册移动设备](enroll-your-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="757b1-173">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="757b1-174">如果注册过程不支持用户的首选语言，则用户可能会以另一种语言在移动设备上收到注册通知和步骤。</span><span class="sxs-lookup"><span data-stu-id="757b1-174">If a user's preferred language isn't supported by the enrollment process, users might receive enrollment notification and steps on their mobile devices in another language.</span></span> <span data-ttu-id="757b1-175">目前，并非所有 Microsoft 365 支持的语言都支持在移动设备上进行注册过程。</span><span class="sxs-lookup"><span data-stu-id="757b1-175">Not all languages supported in Microsoft 365 are currently supported for the enrollment process on mobile devices.</span></span>

<span data-ttu-id="757b1-176">使用 Android 或 iOS 设备的用户需要安装公司门户应用，这是注册过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="757b1-176">Users with Android or iOS devices are required to install the Company Portal app as part of the enrollment process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="757b1-177">相关主题</span><span class="sxs-lookup"><span data-stu-id="757b1-177">Related Topics</span></span>

[<span data-ttu-id="757b1-178">基本移动性和安全性的功能</span><span class="sxs-lookup"><span data-stu-id="757b1-178">Capabilities of Basic Mobility and Security</span></span>](capabilities.md)<br/>
[<span data-ttu-id="757b1-179">在基本移动性和安全性中创建设备安全策略</span><span class="sxs-lookup"><span data-stu-id="757b1-179">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies.md)