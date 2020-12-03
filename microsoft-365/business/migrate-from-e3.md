---
title: 从 Office 365 E3 迁移到 Microsoft 365 业务
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 了解如何将企业从 Office 365 E3 移动到 Microsoft 365 商业高级版。
ms.openlocfilehash: eebf78c24ed4bfd1a4fc2d843f37aebbe3d35e31
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558244"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="4f90a-103">从 Office 365 E3 迁移到 Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="4f90a-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span> 

<span data-ttu-id="4f90a-104">Microsoft 365 商业高级版为你的小型企业提供了所需的一切，并通过简单的设备管理和安全性结合了同类最佳的基于云的工作效率应用。</span><span class="sxs-lookup"><span data-stu-id="4f90a-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="4f90a-105">如果你当前有一个 Office 365 E3 订阅，但没有超过300个员工，请考虑切换到 Microsoft 365 商业高级版以添加安全功能。</span><span class="sxs-lookup"><span data-stu-id="4f90a-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="4f90a-106">迁移非常简单：首先切换许可证，并保留当前订阅中的所有数据和用户信息。</span><span class="sxs-lookup"><span data-stu-id="4f90a-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="4f90a-107">迁移完成后，你需要设置在 Microsoft 365 商业高级版中添加的功能。</span><span class="sxs-lookup"><span data-stu-id="4f90a-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="4f90a-108">Office 365 E3 与 Microsoft 365 商业高级版之间的区别</span><span class="sxs-lookup"><span data-stu-id="4f90a-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="4f90a-109">此表显示了 Microsoft 365 商业高级版和 Office 365 E3 之间的差异。</span><span class="sxs-lookup"><span data-stu-id="4f90a-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="4f90a-110">功能</span><span class="sxs-lookup"><span data-stu-id="4f90a-110">Feature</span></span>    | <span data-ttu-id="4f90a-111">Microsoft 365 商业高级版中的支持</span><span class="sxs-lookup"><span data-stu-id="4f90a-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="4f90a-112">Office 365 E3 中的支持</span><span class="sxs-lookup"><span data-stu-id="4f90a-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="4f90a-113">**本地**</span><span class="sxs-lookup"><span data-stu-id="4f90a-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="4f90a-114">Office 应用程序<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4f90a-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="4f90a-115">Microsoft 365 商业应用版</span><span class="sxs-lookup"><span data-stu-id="4f90a-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="4f90a-116">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="4f90a-116">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="4f90a-117">**云生产力应用程序**</span><span class="sxs-lookup"><span data-stu-id="4f90a-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="4f90a-118">Exchange Online 和 Outlook</span><span class="sxs-lookup"><span data-stu-id="4f90a-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="4f90a-119">每个邮箱 50 GB 存储限制和不受限制的 Exchange Online 存档</span><span class="sxs-lookup"><span data-stu-id="4f90a-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="4f90a-120">每个邮箱 100 GB 存储限制和不受限制的 Exchange Online 存档</span><span class="sxs-lookup"><span data-stu-id="4f90a-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="4f90a-121">Teams</span><span class="sxs-lookup"><span data-stu-id="4f90a-121">Teams</span></span>    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Office 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="4f90a-124">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="4f90a-124">OneDrive for Business</span></span>    | <span data-ttu-id="4f90a-125">每个用户 1 TB 存储限制</span><span class="sxs-lookup"><span data-stu-id="4f90a-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="4f90a-126">无限制</span><span class="sxs-lookup"><span data-stu-id="4f90a-126">Unlimited</span></span> | 
| <span data-ttu-id="4f90a-127">Yammer、SharePoint Online、Planner、Stream</span><span class="sxs-lookup"><span data-stu-id="4f90a-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Office 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="4f90a-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="4f90a-130">StaffHub</span></span>    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Office 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="4f90a-133">Outlook 客户管理器，MileIQ</span><span class="sxs-lookup"><span data-stu-id="4f90a-133">Outlook Customer Manager, MileIQ</span></span>    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | | 
| <span data-ttu-id="4f90a-135">**威胁防护**</span><span class="sxs-lookup"><span data-stu-id="4f90a-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="4f90a-136">适用于 Office 的 Defender 365 计划1</span><span class="sxs-lookup"><span data-stu-id="4f90a-136">Defender for Office 365 Plan 1</span></span> | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | <span data-ttu-id="4f90a-138">不包括在内，但可以添加到</span><span class="sxs-lookup"><span data-stu-id="4f90a-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="4f90a-139">**身份管理**</span><span class="sxs-lookup"><span data-stu-id="4f90a-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="4f90a-140">混合 Azure Active Directory 的自助服务密码重置 (Azure AD) 帐户、Azure AD 多重身份验证 (MFA) 、条件访问、本地标识的密码写回</span><span class="sxs-lookup"><span data-stu-id="4f90a-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    |  | 
| <span data-ttu-id="4f90a-142">**设备和应用程序管理**</span><span class="sxs-lookup"><span data-stu-id="4f90a-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="4f90a-143">Microsoft Intune、Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="4f90a-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    |  |
| <span data-ttu-id="4f90a-145">共享计算机激活</span><span class="sxs-lookup"><span data-stu-id="4f90a-145">Shared computer activation</span></span>|     ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Office 365 E3 中](../media/check-mark.png)| 
| <span data-ttu-id="4f90a-148">从 Win 7/8.1 Pro 许可证升级到 Windows 10 专业版的权限</span><span class="sxs-lookup"><span data-stu-id="4f90a-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    || 
| <span data-ttu-id="4f90a-150">**信息保护**</span><span class="sxs-lookup"><span data-stu-id="4f90a-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="4f90a-151">Office 365 数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="4f90a-151">Office 365 Data Loss Prevention</span></span>|    ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)|![包含在 Office 365 E3 中](../media/check-mark.png)|
|<span data-ttu-id="4f90a-154">Azure 信息保护计划1，Bitlocker 强制</span><span class="sxs-lookup"><span data-stu-id="4f90a-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)||
|<span data-ttu-id="4f90a-156">Azure 信息保护计划1，敏感度标签</span><span class="sxs-lookup"><span data-stu-id="4f90a-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)||
|<span data-ttu-id="4f90a-158">**客户端访问许可证 (CAL 权限)**</span><span class="sxs-lookup"><span data-stu-id="4f90a-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="4f90a-159">企业 CAL 套件 (Exchange、SharePoint、Skype) </span><span class="sxs-lookup"><span data-stu-id="4f90a-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![包含在 Office 365 E3 中](../media/check-mark.png)|

<span data-ttu-id="4f90a-161"><sup>1</sup> Microsoft 365 Business Premium 版本的 Office 应用程序不包括通过组策略、应用遥测、更新控件、电子表格比较和查询或商业智能等批量激活。</span><span class="sxs-lookup"><span data-stu-id="4f90a-161"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="4f90a-162">迁移</span><span class="sxs-lookup"><span data-stu-id="4f90a-162">Migration</span></span>

<span data-ttu-id="4f90a-163">若要迁移你的订阅，请参阅 [手动更改计划](../commerce/subscriptions/change-plans-manually.md) ，以了解有关如何仅将少数用户移动到 Microsoft 365 商业高级版的说明。</span><span class="sxs-lookup"><span data-stu-id="4f90a-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="4f90a-164">您还可以 [自动升级每个人](../commerce/subscriptions/upgrade-to-different-plan.md)，或与合作伙伴合作，将您的 E3 订阅和许可证移动到 Microsoft 365 商业高级订阅。</span><span class="sxs-lookup"><span data-stu-id="4f90a-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="4f90a-165">以下各节介绍了需要进行的更改（如果有），以及迁移后可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="4f90a-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="4f90a-166">Office 365 E3 订阅配置和数据</span><span class="sxs-lookup"><span data-stu-id="4f90a-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="4f90a-167">在迁移之前，无需对当前订阅或数据进行任何更改，其中包括：</span><span class="sxs-lookup"><span data-stu-id="4f90a-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="4f90a-168">订阅配置，如 DNS 记录和域名。</span><span class="sxs-lookup"><span data-stu-id="4f90a-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="4f90a-169">用户和组帐户以及身份验证设置，例如多重因素身份验证或条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="4f90a-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="4f90a-170">生产率服务配置及其数据，如团队、Exchange Online 邮箱、SharePoint Online 网站、OneDrive for Business 文件夹和 OneNote 笔记本。</span><span class="sxs-lookup"><span data-stu-id="4f90a-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="4f90a-171">Office 应用程序将自动缩放。</span><span class="sxs-lookup"><span data-stu-id="4f90a-171">Office applications will scale automatically.</span></span> <span data-ttu-id="4f90a-172">Office 365 新式许可将每72小时检查一次用户的许可证分配，并将 Office 应用程序转换为与用户订阅相匹配的版本。</span><span class="sxs-lookup"><span data-stu-id="4f90a-172">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="4f90a-173">Windows 10</span><span class="sxs-lookup"><span data-stu-id="4f90a-173">Windows 10</span></span>

<span data-ttu-id="4f90a-174">如果 windows Pro Creator 更新中还没有你的 Windows，请 [将其升级到 Windows Pro 创意者更新](upgrade-to-windows-pro-creators-update.md)。</span><span class="sxs-lookup"><span data-stu-id="4f90a-174">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="4f90a-175">设置策略以保护用户设备和文件</span><span class="sxs-lookup"><span data-stu-id="4f90a-175">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="4f90a-176">如果设置了 Office 365 MDM 策略和设备，这些设备将在 Microsoft 365 管理中心的 " **设备** " 页上列出。</span><span class="sxs-lookup"><span data-stu-id="4f90a-176">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4f90a-177">你设置的任何策略都将显示在 [Intune 门户](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)中的经典策略列表中。</span><span class="sxs-lookup"><span data-stu-id="4f90a-177">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="4f90a-178">将许可证分配给 Microsoft 365 商业高级版后，可以开始保护用户的设备和文件。</span><span class="sxs-lookup"><span data-stu-id="4f90a-178">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="4f90a-179">如果将组织中的每个人升级到 Microsoft 365 商业高级版，您将在主页上看到 "安装向导"，并且可以按照 [安装向导中的设置 Microsoft 365 商业高级](set-up.md) 步骤来保护文件和移动设备。</span><span class="sxs-lookup"><span data-stu-id="4f90a-179">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="4f90a-180">您还可以在 "设备" 页上完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4f90a-180">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="4f90a-181">在管理中心的左侧导航中，转到 " **设备** \> **策略**"。</span><span class="sxs-lookup"><span data-stu-id="4f90a-181">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="4f90a-182">在 " **设备策略** " 页上，选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="4f90a-182">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="4f90a-183">在 " **添加策略** " 窗格中，为策略指定一个名称，然后从下拉类型中选择一个 **策略类型** 。</span><span class="sxs-lookup"><span data-stu-id="4f90a-183">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="4f90a-184">您可以设置应用程序策略来保护 Android 和 iPhone 设备上的文件以及 Windows 10，还可以为公司拥有的 Windows 10 设备设置设备配置策略。</span><span class="sxs-lookup"><span data-stu-id="4f90a-184">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="4f90a-185">有关详细信息，请参阅以下链接：</span><span class="sxs-lookup"><span data-stu-id="4f90a-185">See the following links for details:</span></span>
    
  - [<span data-ttu-id="4f90a-186">设置 Android 或 iOS 设备的应用保护设置</span><span class="sxs-lookup"><span data-stu-id="4f90a-186">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="4f90a-187">设置 Windows 10 设备的应用程序保护设置</span><span class="sxs-lookup"><span data-stu-id="4f90a-187">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="4f90a-188">设置 Windows 10 电脑的设备保护设置</span><span class="sxs-lookup"><span data-stu-id="4f90a-188">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="4f90a-189">设置策略后，你和你的员工可以设置设备：</span><span class="sxs-lookup"><span data-stu-id="4f90a-189">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="4f90a-190">有关 Windows 设备的步骤，请参阅为 [Microsoft 365 商业高级版用户设置 Windows 设备](set-up-windows-devices.md) 。</span><span class="sxs-lookup"><span data-stu-id="4f90a-190">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="4f90a-191">有关 Android 手机和 Iphone 的步骤，请参阅为 [Microsoft 365 商业高级版用户设置移动设备](set-up-mobile-devices.md) 。</span><span class="sxs-lookup"><span data-stu-id="4f90a-191">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="4f90a-192">邮箱大小</span><span class="sxs-lookup"><span data-stu-id="4f90a-192">Mailbox Size</span></span>

<span data-ttu-id="4f90a-193">Microsoft 365 商业高级版具有 50 GB 的存储限制，因为它使用 Exchange Online 计划1。</span><span class="sxs-lookup"><span data-stu-id="4f90a-193">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="4f90a-194">迁移到 Microsoft 365 商业高级版时，如果你的任何用户超过 50 GB 的邮箱存储，建议你为此用户分配 Exchange Online 计划2并删除 Exchange Online 计划1，因为这两种方法都不可行。</span><span class="sxs-lookup"><span data-stu-id="4f90a-194">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>


### <a name="threat-protection"></a><span data-ttu-id="4f90a-195">威胁防护</span><span class="sxs-lookup"><span data-stu-id="4f90a-195">Threat protection</span></span>

<span data-ttu-id="4f90a-196">迁移到 Microsoft 365 商业高级版后，您可以使用适用于 Office 365 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="4f90a-196">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="4f90a-197">有关概述，请参阅 [Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 。</span><span class="sxs-lookup"><span data-stu-id="4f90a-197">See [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview.</span></span> <span data-ttu-id="4f90a-198">若要设置，请参阅 [设置安全链接](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)、 [设置安全附件](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)以及 [在适用于 Office 365 的 Defender 中设置反网络钓鱼](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)。</span><span class="sxs-lookup"><span data-stu-id="4f90a-198">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="4f90a-199">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="4f90a-199">Sensitivity labels</span></span>

<span data-ttu-id="4f90a-200">若要开始使用敏感度标签，请参阅 [敏感度标签概述](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 和 [创建和管理敏感度标签](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) 视频。</span><span class="sxs-lookup"><span data-stu-id="4f90a-200">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
