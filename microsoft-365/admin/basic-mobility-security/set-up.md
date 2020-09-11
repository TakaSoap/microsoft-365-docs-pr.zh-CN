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
description: 设置基本移动性和安全性以保护和管理用户的移动设备。
ms.openlocfilehash: cb010668d95e51edfbc913caa308ddd830d674e2
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430082"
---
# <a name="set-up-basic-mobility-and-security"></a><span data-ttu-id="8d069-103">设置基本移动性和安全性</span><span class="sxs-lookup"><span data-stu-id="8d069-103">Set up Basic Mobility and Security</span></span>

<span data-ttu-id="8d069-104">Microsoft 365 的内置基本移动性和安全性可帮助您保护和管理用户的移动设备，如 Iphone、Ipad、Androids 和 Windows phone。</span><span class="sxs-lookup"><span data-stu-id="8d069-104">The built-in Basic Mobility and Security for Microsoft 365 helps you secure and manage users' mobile devices such as iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="8d069-105">可以创建和管理设备安全策略，远程擦除设备，以及查看详细的设备报告。</span><span class="sxs-lookup"><span data-stu-id="8d069-105">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

<span data-ttu-id="8d069-106">有问题？</span><span class="sxs-lookup"><span data-stu-id="8d069-106">Have questions?</span></span> <span data-ttu-id="8d069-107">有关解决常见问题的常见问题解答，请参阅 [基本移动性和安全常见问题 (FAQ) ](frequently-asked-questions.md)。</span><span class="sxs-lookup"><span data-stu-id="8d069-107">For a FAQ to help address common questions, see [Basic Mobility and Security Frequently-asked questions (FAQ)](frequently-asked-questions.md).</span></span> <span data-ttu-id="8d069-108">请注意，不能使用委派的管理员帐户来管理基本的移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="8d069-108">Be aware that you cannot use a delegated administrator account to manage Basic Mobility and Security.</span></span> <span data-ttu-id="8d069-109">有关详细信息，请参阅 [合作伙伴：提供委派管理](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)。</span><span class="sxs-lookup"><span data-stu-id="8d069-109">For more info, see [Partners: Offer delegated administration](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> 

<span data-ttu-id="8d069-110">设备管理是安全 & 合规性中心的一部分，因此您需要转到此处以启动 MDM 安装程序。</span><span class="sxs-lookup"><span data-stu-id="8d069-110">Device management is part of the Security & Compliance Center so you'll need to go there to kick off MDM setup.</span></span>

## <a name="activate-the-basic-mobility-and-security-service"></a><span data-ttu-id="8d069-111">激活 "基本移动性和安全服务"</span><span class="sxs-lookup"><span data-stu-id="8d069-111">Activate the Basic Mobility and Security service</span></span>

1. <span data-ttu-id="8d069-112">使用全局管理员帐户登录到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8d069-112">Sign in to Microsoft 365 with your global admin account.</span></span>
    

2. <span data-ttu-id="8d069-113">请转到 [激活基本移动性和安全性](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8d069-113">Go to [Activate Basic Mobility and Security](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span>
    
    <span data-ttu-id="8d069-114">可能需要一段时间来激活基本的移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="8d069-114">It can take some time to activate Basic Mobility and Security.</span></span> <span data-ttu-id="8d069-115">完成后，你将收到一封说明要执行的后续步骤的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8d069-115">When it finishes, you'll receive an email that explains the next steps to take.</span></span>

## <a name="set-up-mobile-device-management"></a><span data-ttu-id="8d069-116">设置移动设备管理</span><span class="sxs-lookup"><span data-stu-id="8d069-116">Set up Mobile Device Management</span></span>

<span data-ttu-id="8d069-117">服务准备就绪后，请完成以下步骤以完成安装。</span><span class="sxs-lookup"><span data-stu-id="8d069-117">When the service is ready, complete the following steps to finish setup.</span></span>

### <a name="step-1-required-configure-domains-for-mdm"></a><span data-ttu-id="8d069-118">步骤1： (必需的) 配置 MDM 域</span><span class="sxs-lookup"><span data-stu-id="8d069-118">Step 1: (Required) Configure domains for MDM</span></span>

<span data-ttu-id="8d069-119">如果没有与 Microsoft 365 关联的自定义域，或者如果你不管理 Windows 设备，则可以跳过此部分。</span><span class="sxs-lookup"><span data-stu-id="8d069-119">If you don't have a custom domain associated with Microsoft 365 or if you're not managing Windows devices, you can skip this section.</span></span> <span data-ttu-id="8d069-120">否则，您将需要在 DNS 主机上添加域的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="8d069-120">Otherwise, you'll need to add DNS records for the domain at your DNS host.</span></span> <span data-ttu-id="8d069-121">如果已添加了记录，则在使用 Microsoft 365 设置域的过程中，你已全部设置。</span><span class="sxs-lookup"><span data-stu-id="8d069-121">If you've added the records already, as part of setting up your domain with Microsoft 365, you're all set.</span></span> <span data-ttu-id="8d069-122">在添加记录后，组织中使用使用您的自定义域的电子邮件地址登录到其 Windows 设备的 Microsoft 365 用户将被重定向，以注册基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="8d069-122">After you add the records, Microsoft 365 users in your organization who sign in on their Windows device with an email address that uses your custom domain are redirected to enroll in Basic Mobility and Security.</span></span>

<span data-ttu-id="8d069-123">需要有关设置记录的帮助吗？</span><span class="sxs-lookup"><span data-stu-id="8d069-123">Need help setting up the records?</span></span> <span data-ttu-id="8d069-124">查找您的域注册机构并选择注册器名称，以转到在 [添加 dns 记录以连接域](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)中提供的列表中创建 DNS 记录的分步帮助。</span><span class="sxs-lookup"><span data-stu-id="8d069-124">Find your domain registrar and select the registrar name to go to step-by-step help for creating DNS record in the list provided in [Add DNS records to connect your domain](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span> <span data-ttu-id="8d069-125">按照这些说明创建在 [简化 Windows 注册（无需 AZURE AD Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)）中描述的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="8d069-125">Use those instructions to create CNAME records described in [Simplify Windows enrollment without Azure AD Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).</span></span>

<span data-ttu-id="8d069-126">在添加两条 CNAME 记录后，请返回到安全 & 合规性中心并转到**数据丢失防护**  >  **设备管理**，   以完成下一步。</span><span class="sxs-lookup"><span data-stu-id="8d069-126">After you add the two CNAME records, go back to the Security & Compliance Center and go to **Data loss prevention** > **Device management** to complete the next step.</span></span>

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="8d069-127">步骤2： (必需的) 为 iOS 设备配置 APNs 证书</span><span class="sxs-lookup"><span data-stu-id="8d069-127">Step 2: (Required) Configure an APNs Certificate for iOS devices</span></span>

<span data-ttu-id="8d069-128">若要管理 iPad 和 Iphone 等 iOS 设备，您需要创建 APNs 证书。</span><span class="sxs-lookup"><span data-stu-id="8d069-128">To manage iOS devices like iPad and iPhones, you need to create an APNs certificate.</span></span>

1. <span data-ttu-id="8d069-129">使用全局管理员帐户登录到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8d069-129">Sign in to  Microsoft 365 with your global admin account.</span></span>   

2. <span data-ttu-id="8d069-130">在浏览器中键入：  [https://protection.office.com](https://protection.office.com/) 。</span><span class="sxs-lookup"><span data-stu-id="8d069-130">In your browser type: [https://protection.office.com](https://protection.office.com/).</span></span>  

3. <span data-ttu-id="8d069-131">选择 " **数据丢失防护**   >  **设备管理**"，并**为 iOS 设备选择 APNs 证书**。</span><span class="sxs-lookup"><span data-stu-id="8d069-131">Select **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>   

4. <span data-ttu-id="8d069-132">在 "Apple 推送通知证书设置" 页上，选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8d069-132">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>  

5. <span data-ttu-id="8d069-133">选择 " **下载你的 CSR 文件**   "，并将证书签名请求保存到你将记住的计算机上的某个位置。</span><span class="sxs-lookup"><span data-stu-id="8d069-133">Select **Download your CSR file** and save the Certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="8d069-134">选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8d069-134">Select **Next**.</span></span>
    
6. <span data-ttu-id="8d069-135">在 "创建 APNs 证书" 页上：</span><span class="sxs-lookup"><span data-stu-id="8d069-135">On the Create an APNs certificate page:</span></span>
    
    - <span data-ttu-id="8d069-136">选择 "Apple APNS 门户" 打开 "Apple 推送证书" 门户。</span><span class="sxs-lookup"><span data-stu-id="8d069-136">Select Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
    - <span data-ttu-id="8d069-137">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="8d069-137">Sign in with an Apple ID.</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="8d069-p107">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="8d069-p107">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    - <span data-ttu-id="8d069-140">选择 "创建证书" 并接受 "使用条款"。</span><span class="sxs-lookup"><span data-stu-id="8d069-140">Select Create a Certificate and accept the Terms of Use.</span></span>
    
    - <span data-ttu-id="8d069-141">Browseto 从 Microsoft 365 和 selectUpload 下载到您的计算机的证书签名请求。</span><span class="sxs-lookup"><span data-stu-id="8d069-141">Browseto the Certificate signing request you downloaded to your computer from Microsoft 365 and selectUpload.</span></span>
    
    - <span data-ttu-id="8d069-142">由 Apple 推送证书门户创建到你的计算机的 Downloadthe APN 证书。</span><span class="sxs-lookup"><span data-stu-id="8d069-142">Downloadthe APN certificate created by the Apple Push Certificate Portal to your computer.</span></span>

    >[!TIP]
    ><span data-ttu-id="8d069-143">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="8d069-143">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="8d069-144">返回到 Microsoft 365，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8d069-144">Go back to Microsoft 365 and select **Next**.</span></span>   

8. <span data-ttu-id="8d069-145"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="8d069-145">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>   

9. <span data-ttu-id="8d069-146">选择 "  **完成**"。</span><span class="sxs-lookup"><span data-stu-id="8d069-146">Select  **Finish**.</span></span>  

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a><span data-ttu-id="8d069-147">步骤3：建议 () 设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="8d069-147">Step 3: (Recommended) Set up multi-factor authentication</span></span>

<span data-ttu-id="8d069-148">通过要求使用第二种形式的身份验证，MFA 可帮助确保登录 Microsoft 365 以进行移动设备注册。</span><span class="sxs-lookup"><span data-stu-id="8d069-148">MFA helps secure the sign in to Microsoft 365 for mobile device enrollment by requiring a second form of authentication.</span></span> <span data-ttu-id="8d069-149">在正确输入工作帐户密码后，用户需要在其移动设备上确认电话呼叫、短信或应用通知。</span><span class="sxs-lookup"><span data-stu-id="8d069-149">Users are required to acknowledge a phone call, text message, or app notification on their mobile device after correctly entering their work account password.</span></span> <span data-ttu-id="8d069-150">只有在此第二种形式的身份验证完成后，他们才能注册其设备。</span><span class="sxs-lookup"><span data-stu-id="8d069-150">They can enroll their device only after this second form of authentication is completed.</span></span> <span data-ttu-id="8d069-151">在基本移动性和安全性中对用户设备进行注册后，用户只能使用其工作帐户访问 Microsoft 365 资源。</span><span class="sxs-lookup"><span data-stu-id="8d069-151">After user devices are enrolled in Basic Mobility and Security, users can access Microsoft 365 resources with only their work account.</span></span>

<span data-ttu-id="8d069-152">若要了解如何在 Azure AD 门户中启用 MFA，请参阅 [设置多因素身份验证](https://go.microsoft.com/fwlink/p/?LinkId=519255)。</span><span class="sxs-lookup"><span data-stu-id="8d069-152">To learn how to turn on MFA in the Azure AD portal, see [Set up multi-factor authentication](https://go.microsoft.com/fwlink/p/?LinkId=519255).</span></span>

<span data-ttu-id="8d069-153">设置 MFA 后，请返回到安全 & 合规中心，并导航到 **数据丢失防护**   >  **设备管理**   >  **设备策略**   ，以完成下一步。</span><span class="sxs-lookup"><span data-stu-id="8d069-153">After you set up MFA, go back to the Security & Compliance Center and navigate to **Data loss prevention** > **Device management** > **Device policies** to complete the next step.</span></span>

### <a name="step-4-recommended-manage-device-security-policies"></a><span data-ttu-id="8d069-154">步骤4： (建议) 管理设备安全策略</span><span class="sxs-lookup"><span data-stu-id="8d069-154">Step 4: (Recommended) Manage device security policies</span></span>

<span data-ttu-id="8d069-155">下一步是创建和部署设备安全策略，以帮助保护 Microsoft 365 组织数据。</span><span class="sxs-lookup"><span data-stu-id="8d069-155">The next step is to create and deploy device security policies to help protect your Microsoft 365 organization data.</span></span> <span data-ttu-id="8d069-156">例如，如果用户通过创建将策略锁定在5分钟无活动状态并在三次登录失败后擦除设备后锁定设备的策略，则可以帮助防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="8d069-156">For example, you can help prevent data loss if a user loses their device by creating a policy to lock devices after five minutes of inactivity and wipe devices after three sign-in failures.</span></span>

1. <span data-ttu-id="8d069-157">使用全局管理员帐户登录到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8d069-157">Sign in to Microsoft 365 with your global admin account.</span></span> 

2. <span data-ttu-id="8d069-158">选择 " [激活移动设备管理](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)"。</span><span class="sxs-lookup"><span data-stu-id="8d069-158">Select [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="8d069-159">如果服务处于激活状态，则激活步骤将会看到用于 [管理设备](https://admin.microsoft.com/adminportal/home#/MifoDevices)的链接   。</span><span class="sxs-lookup"><span data-stu-id="8d069-159">If the service is activated, instead the activation steps you'll see a link to [Manage Devices](https://admin.microsoft.com/adminportal/home#/MifoDevices) .</span></span>
    
3. <span data-ttu-id="8d069-160">转到 " **设备策略**"。</span><span class="sxs-lookup"><span data-stu-id="8d069-160">Go to **Device policies**.</span></span>

     :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本安全性和移动性策略设置":::

4. <span data-ttu-id="8d069-162">按照在 [基本移动性和安全性中创建设备安全策略中](create-device-security-policies.md)的步骤创建和部署适用于您的组织的设备安全策略。</span><span class="sxs-lookup"><span data-stu-id="8d069-162">Create and deploy device security policies appropriate for your organization following the steps in [Create device security policies in Basic Mobility and Security](create-device-security-policies.md).</span></span>

>[!TIP]
    - <span data-ttu-id="8d069-163">当您创建新策略时，您可能希望将策略设置为允许访问和报告策略违规，而用户设备不符合该策略。</span><span class="sxs-lookup"><span data-stu-id="8d069-163">When you create a new policy, you might want to set the policy to allow access and report policy violation where a user device isn't compliant with the policy.</span></span> <span data-ttu-id="8d069-164">这使您可以查看策略影响了多少个移动设备，而不会阻止对 Microsoft 365 的访问。</span><span class="sxs-lookup"><span data-stu-id="8d069-164">This allows you see how many mobile devices are impacted by the policy without blocking access to Microsoft 365 .</span></span><br/><span data-ttu-id="8d069-165">-在将新策略部署到组织中的所有人之前，我们建议您在少量用户使用的设备上对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="8d069-165">- Before you deploy a new policy to everyone in your organization, we recommend you test it on the devices used by a small number of users.</span></span><br/><span data-ttu-id="8d069-166">-此外，在部署策略之前，让你的组织了解在基本移动性和安全性中注册设备的潜在影响。</span><span class="sxs-lookup"><span data-stu-id="8d069-166">- Also, before you deploy policies, let your organization know the potential impacts of enrolling a device in Basic Mobility and Security.</span></span> <span data-ttu-id="8d069-167">根据您设置策略的方式，不符合策略的设备 (不符合的设备) 可能阻止访问 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8d069-167">Depending on how you set up the policies, devices that don't comply with policies (non-compliant devices) could be blocked from accessing Microsoft 365.</span></span> <span data-ttu-id="8d069-168">如果擦除设备，则可能会删除已注册设备上的应用程序、照片和其他个人信息，不兼容的设备也可能会被删除。</span><span class="sxs-lookup"><span data-stu-id="8d069-168">Non-compliant devices might also have apps installed, photos, and other personal information which, on an enrolled device, could be deleted if the device is wiped.</span></span> <span data-ttu-id="8d069-169">有关详细信息，请参阅 [在基本移动和安全中擦除移动设备](wipe-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="8d069-169">For more info, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>
    
## <a name="make-sure-users-enroll-their-devices"></a><span data-ttu-id="8d069-170">确保用户注册其设备</span><span class="sxs-lookup"><span data-stu-id="8d069-170">Make sure users enroll their devices</span></span>

<span data-ttu-id="8d069-171">创建并部署移动设备管理策略后，组织中的每个许可的 Microsoft 365 用户在下一次从其移动设备登录到 Microsoft 365 时都将收到一个注册邮件。</span><span class="sxs-lookup"><span data-stu-id="8d069-171">After you've created and deployed a mobile device management policy, each licensed Microsoft 365 user in your organization that the device policy applies receives an enrollment message the next time they sign into Microsoft 365 from their mobile device.</span></span> <span data-ttu-id="8d069-172">他们必须先完成注册和激活步骤，然后才能访问 Microsoft 365 电子邮件和文档。</span><span class="sxs-lookup"><span data-stu-id="8d069-172">They must complete the enrollment and activation steps before they can access Microsoft 365 email and documents.</span></span> <span data-ttu-id="8d069-173">有关详细信息，请参阅 [使用基本移动性和安全性注册移动设备](enroll-your-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="8d069-173">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="8d069-174">如果注册过程不支持用户的首选语言，则用户可能会在使用其他语言的移动设备上接收注册通知和步骤。</span><span class="sxs-lookup"><span data-stu-id="8d069-174">If a user's preferred language isn't supported by the enrollment process, users might receive enrollment notification and steps on their mobile devices in another language.</span></span> <span data-ttu-id="8d069-175">目前，移动设备上的注册过程不支持 Microsoft 365 中支持的所有语言。</span><span class="sxs-lookup"><span data-stu-id="8d069-175">Not all languages supported in Microsoft 365 are currently supported for the enrollment process on mobile devices.</span></span>

<span data-ttu-id="8d069-176">具有 Android 或 iOS 设备的用户需要在注册过程中安装公司门户应用程序。</span><span class="sxs-lookup"><span data-stu-id="8d069-176">Users with Android or iOS devices are required to install the Company Portal app as part of the enrollment process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8d069-177">相关主题</span><span class="sxs-lookup"><span data-stu-id="8d069-177">Related Topics</span></span>

[<span data-ttu-id="8d069-178">基本移动性和安全性的功能</span><span class="sxs-lookup"><span data-stu-id="8d069-178">Capabilities of Basic Mobility and Security</span></span>](capabilities.md)<br/>
[<span data-ttu-id="8d069-179">在基本移动性和安全性中创建设备安全策略</span><span class="sxs-lookup"><span data-stu-id="8d069-179">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies.md)