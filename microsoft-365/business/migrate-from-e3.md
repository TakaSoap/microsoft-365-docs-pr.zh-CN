---
title: 从 E3 Microsoft 365 商业版Office 365迁移
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
description: 如果你拥有 Office 365 E3 订阅，但员工不超过 300 人，请考虑切换到 Microsoft 365 商业高级版。
ms.openlocfilehash: d139d07c946ff3efed3db3a73eb5e1a4ae66c190
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623597"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="7f1b9-103">从 Office 365 E3 迁移到 Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="7f1b9-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span>

<span data-ttu-id="7f1b9-104">Microsoft 365 商业高级版你的小型企业所需的一切，将一流的基于云的生产力应用与简单的设备管理和安全性相结合。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="7f1b9-105">如果你当前拥有 Office 365 E3 订阅，但员工不超过 300 人，请考虑切换到 Microsoft 365 商业高级版 添加的安全功能。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="7f1b9-106">迁移非常简单：首先切换许可证，并保留当前订阅中所有数据和用户信息。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="7f1b9-107">迁移后，你需要设置在迁移过程中添加Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="7f1b9-108">E3 Office 365 E3 和 Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="7f1b9-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="7f1b9-109">此表显示了 Microsoft 365 商业高级版 和 Office 365 E3 之间的差异。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="7f1b9-110">功能</span><span class="sxs-lookup"><span data-stu-id="7f1b9-110">Feature</span></span>    | <span data-ttu-id="7f1b9-111">支持Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="7f1b9-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="7f1b9-112">在 E3 Office 365支持</span><span class="sxs-lookup"><span data-stu-id="7f1b9-112">Support in Office 365 E3</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="7f1b9-113">**本地**</span><span class="sxs-lookup"><span data-stu-id="7f1b9-113">**On-premises**</span></span>        | | |
| <span data-ttu-id="7f1b9-114">Office应用<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7f1b9-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="7f1b9-115">Microsoft 365 商业应用版</span><span class="sxs-lookup"><span data-stu-id="7f1b9-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="7f1b9-116">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="7f1b9-116">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="7f1b9-117">**云生产力应用**</span><span class="sxs-lookup"><span data-stu-id="7f1b9-117">**Cloud productivity apps**</span></span>        | | |
| <span data-ttu-id="7f1b9-118">Exchange Online 和 Outlook</span><span class="sxs-lookup"><span data-stu-id="7f1b9-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="7f1b9-119">每个邮箱 50 GB 存储限制和无限Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="7f1b9-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="7f1b9-120">每个邮箱 100 GB 存储限制和无限制Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="7f1b9-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> |
| <span data-ttu-id="7f1b9-121">Teams</span><span class="sxs-lookup"><span data-stu-id="7f1b9-121">Teams</span></span>    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在 Office 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="7f1b9-124">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="7f1b9-124">OneDrive for Business</span></span>    | <span data-ttu-id="7f1b9-125">每个用户 1 TB 存储限制</span><span class="sxs-lookup"><span data-stu-id="7f1b9-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="7f1b9-126">无限制</span><span class="sxs-lookup"><span data-stu-id="7f1b9-126">Unlimited</span></span> | 
| <span data-ttu-id="7f1b9-127">Yammer、SharePoint Online、Planner、Stream</span><span class="sxs-lookup"><span data-stu-id="7f1b9-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在 Office 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="7f1b9-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="7f1b9-130">StaffHub</span></span>    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在 Office 365 E3 中](../media/check-mark.png) |
| <span data-ttu-id="7f1b9-133">**威胁防护**</span><span class="sxs-lookup"><span data-stu-id="7f1b9-133">**Threat Protection**</span></span>        | | |
| <span data-ttu-id="7f1b9-134">Defender for Office 365 计划 1</span><span class="sxs-lookup"><span data-stu-id="7f1b9-134">Defender for Office 365 Plan 1</span></span> | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | <span data-ttu-id="7f1b9-136">不包含，但可添加到</span><span class="sxs-lookup"><span data-stu-id="7f1b9-136">Not included, but can be added on</span></span> |
| <span data-ttu-id="7f1b9-137">**身份管理**</span><span class="sxs-lookup"><span data-stu-id="7f1b9-137">**Identity management**</span></span>        | | |
| <span data-ttu-id="7f1b9-138">Azure AD) 帐户的混合 Azure Active Directory (自助服务密码重置、Azure AD 多重身份验证 (MFA) 、条件访问、本地标识的密码写回</span><span class="sxs-lookup"><span data-stu-id="7f1b9-138">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    |  |
| <span data-ttu-id="7f1b9-140">**设备和应用管理**</span><span class="sxs-lookup"><span data-stu-id="7f1b9-140">**Device and app management**</span></span>        | | |
| <span data-ttu-id="7f1b9-141">Microsoft Intune、Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="7f1b9-141">Microsoft Intune, Windows AutoPilot</span></span>|     ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    |  |
| <span data-ttu-id="7f1b9-143">共享计算机激活</span><span class="sxs-lookup"><span data-stu-id="7f1b9-143">Shared computer activation</span></span>|     ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在 Office 365 E3 中](../media/check-mark.png)| 
| <span data-ttu-id="7f1b9-146">从 Win 7/8.1 Windows 10 专业版许可证升级Pro权限</span><span class="sxs-lookup"><span data-stu-id="7f1b9-146">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    ||
| <span data-ttu-id="7f1b9-148">**信息保护**</span><span class="sxs-lookup"><span data-stu-id="7f1b9-148">**Information protection**</span></span>        | | |
|<span data-ttu-id="7f1b9-149">Office 365 数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="7f1b9-149">Office 365 Data Loss Prevention</span></span>|    ![包含在Microsoft 365 商业高级版](../media/check-mark.png)|![包含在 Office 365 E3 中](../media/check-mark.png)|
|<span data-ttu-id="7f1b9-152">Azure 信息保护计划 1，BitLocker实施</span><span class="sxs-lookup"><span data-stu-id="7f1b9-152">Azure Information Protection Plan 1, BitLocker enforcement</span></span>|![包含在Microsoft 365 商业高级版](../media/check-mark.png)||
|<span data-ttu-id="7f1b9-154">Azure 信息保护计划 1，敏感度标签</span><span class="sxs-lookup"><span data-stu-id="7f1b9-154">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![包含在Microsoft 365 商业高级版](../media/check-mark.png)||
|<span data-ttu-id="7f1b9-156">**客户端访问许可证 (CAL 权限)**</span><span class="sxs-lookup"><span data-stu-id="7f1b9-156">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="7f1b9-157">EnterpriseCAL Suite (Exchange、SharePoint、Skype) </span><span class="sxs-lookup"><span data-stu-id="7f1b9-157">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![包含在 Office 365 E3 中](../media/check-mark.png)|

<span data-ttu-id="7f1b9-159"><sup>1</sup> Microsoft 365 商业高级版应用的 Office 版本不包括通过组策略、应用遥测、更新控件、电子表格比较和查询或商业智能进行批量激活。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-159"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="7f1b9-160">迁移</span><span class="sxs-lookup"><span data-stu-id="7f1b9-160">Migration</span></span>

<span data-ttu-id="7f1b9-161">若要迁移订阅[，请参阅手动](../commerce/subscriptions/change-plans-manually.md)更改计划，了解只需迁移几个人员以迁移Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-161">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="7f1b9-162">还可以自动[升级所有人](../commerce/subscriptions/upgrade-to-different-plan.md)，或与合作伙伴合作将 E3 订阅和许可证移动到 Microsoft 365 商业高级版 订阅。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-162">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="7f1b9-163">以下各节介绍您需要所做的更改（如果有）以及您可以在迁移后执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-163">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="7f1b9-164">Office 365E3 订阅配置和数据</span><span class="sxs-lookup"><span data-stu-id="7f1b9-164">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="7f1b9-165">在迁移之前，无需对当前订阅或数据执行任何更改，其中包括：</span><span class="sxs-lookup"><span data-stu-id="7f1b9-165">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="7f1b9-166">订阅配置，例如 DNS 记录和域名。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-166">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="7f1b9-167">用户和组帐户以及身份验证设置，如多重身份验证或条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-167">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="7f1b9-168">生产力服务配置及其数据，例如Teams、Exchange Online邮箱、SharePoint Online 网站、OneDrive for Business文件夹OneNote笔记本。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-168">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="7f1b9-169">Office应用程序将自动缩放。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-169">Office applications will scale automatically.</span></span> <span data-ttu-id="7f1b9-170">Office 365新式许可将每 72 小时检查一次用户的许可证分配，并将Office应用程序转换为与用户订阅匹配的版本。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-170">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="7f1b9-171">Windows 10</span><span class="sxs-lookup"><span data-stu-id="7f1b9-171">Windows 10</span></span>

<span data-ttu-id="7f1b9-172">如果你Windows创意者更新Windows Pro，请[将其升级到Windows Pro创意者更新。](upgrade-to-windows-pro-creators-update.md)</span><span class="sxs-lookup"><span data-stu-id="7f1b9-172">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="7f1b9-173">设置策略以保护用户设备和文件</span><span class="sxs-lookup"><span data-stu-id="7f1b9-173">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="7f1b9-174">如果你设置 mdm Office 365和设备，这些设备将列在管理中心的"设备"Microsoft 365页面上。 </span><span class="sxs-lookup"><span data-stu-id="7f1b9-174">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7f1b9-175">你设置的任何策略都将显示在 [Intune](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)门户的经典策略列表中。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-175">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="7f1b9-176">向用户分配许可证Microsoft 365 商业高级版，可以开始保护用户的设备和文件。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-176">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="7f1b9-177">如果你将组织中所有人升级到 Microsoft 365 商业高级版，你将在主页上看到安装向导，并可以按照安装向导步骤中的设置[Microsoft 365 商业高级版](set-up.md)来保护文件和移动设备。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-177">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="7f1b9-178">还可以在"设备"页上完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7f1b9-178">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="7f1b9-179">在管理中心的左侧导航中，转到 **"设备策略** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="7f1b9-179">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>

2. <span data-ttu-id="7f1b9-180">在"**设备策略"页上**，选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="7f1b9-180">On the **Device policies** page, choose **Add**.</span></span>

3. <span data-ttu-id="7f1b9-181">在 **"添加策略** "窗格中，为策略命名，然后从下拉列表中选择 **策略类型** 。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-181">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span>

     <span data-ttu-id="7f1b9-182">你可以设置应用程序策略来保护 Android 和 iPhone 设备上的文件以及 Windows 10，还可以为公司拥有的 Windows 10 设备设置设备配置策略。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-182">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="7f1b9-183">有关详细信息，请参阅以下链接：</span><span class="sxs-lookup"><span data-stu-id="7f1b9-183">See the following links for details:</span></span>

  - [<span data-ttu-id="7f1b9-184">设置 Android 或 iOS 设备的应用保护设置</span><span class="sxs-lookup"><span data-stu-id="7f1b9-184">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)

  - [<span data-ttu-id="7f1b9-185">设置 Windows 10 设备的应用程序保护设置</span><span class="sxs-lookup"><span data-stu-id="7f1b9-185">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)

  - [<span data-ttu-id="7f1b9-186">为电脑设置Windows 10保护设置</span><span class="sxs-lookup"><span data-stu-id="7f1b9-186">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="7f1b9-187">设置策略后，你和员工可以设置设备：</span><span class="sxs-lookup"><span data-stu-id="7f1b9-187">Once you set up policies, you and your employees can set up devices:</span></span>

  - <span data-ttu-id="7f1b9-188">请参阅[为Windows用户设置Microsoft 365 商业高级版，](set-up-windows-devices.md)了解设备Windows步骤。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-188">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 

  - <span data-ttu-id="7f1b9-189">有关[Android 手机和](set-up-mobile-devices.md)iPhone Microsoft 365 商业高级版，请参阅为用户设置移动设备。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-189">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="7f1b9-190">邮箱大小</span><span class="sxs-lookup"><span data-stu-id="7f1b9-190">Mailbox Size</span></span>

<span data-ttu-id="7f1b9-191">Microsoft 365 商业高级版计划 1 使用的存储空间上限为 50 GB Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-191">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="7f1b9-192">迁移到 Microsoft 365 商业高级版 时，如果任何用户超过 50 GB 的邮箱存储，建议您为此用户分配 Exchange Online 计划 2 并删除 Exchange Online 计划 1，因为分配这两者不可行。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-192">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>

### <a name="threat-protection"></a><span data-ttu-id="7f1b9-193">威胁防护</span><span class="sxs-lookup"><span data-stu-id="7f1b9-193">Threat protection</span></span>

<span data-ttu-id="7f1b9-194">迁移到 Microsoft 365 商业高级版 后，你拥有 Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-194">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="7f1b9-195">有关[概述，Office 365](../security/office-365-security/defender-for-office-365.md) Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-195">See [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for an overview.</span></span> <span data-ttu-id="7f1b9-196">若要设置，[请参阅设置保险箱](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)链接、设置保险箱附件和[](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)在 Defender 中设置防钓鱼[Office 365。](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)</span><span class="sxs-lookup"><span data-stu-id="7f1b9-196">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="7f1b9-197">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="7f1b9-197">Sensitivity labels</span></span>

<span data-ttu-id="7f1b9-198">若要开始使用敏感度标签，请参阅敏感度标签概述[以及](../compliance/sensitivity-labels.md)[创建和管理敏感度标签](../business-video/create-sensitivity-labels.md)视频。</span><span class="sxs-lookup"><span data-stu-id="7f1b9-198">To start using sensitivity labels, see [Overview of sensitivity labels](../compliance/sensitivity-labels.md) and [create and manage sensitivity labels](../business-video/create-sensitivity-labels.md) video.</span></span>

## <a name="related-content"></a><span data-ttu-id="7f1b9-199">相关内容</span><span class="sxs-lookup"><span data-stu-id="7f1b9-199">Related content</span></span>

<span data-ttu-id="7f1b9-200">[手动更改计划](../commerce/subscriptions/change-plans-manually.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="7f1b9-200">[Change plans manually](../commerce/subscriptions/change-plans-manually.md) (article)</span></span>\
<span data-ttu-id="7f1b9-201">[将Windows设备升级到Windows 10 专业版 (](upgrade-to-windows-pro-creators-update.md)视频) </span><span class="sxs-lookup"><span data-stu-id="7f1b9-201">[Upgrade Windows devices to Windows 10 Pro](upgrade-to-windows-pro-creators-update.md) (video)</span></span>\
<span data-ttu-id="7f1b9-202">[设置 Android 或 iOS](app-protection-settings-for-android-and-ios.md) 设备的应用保护设置 (文章) </span><span class="sxs-lookup"><span data-stu-id="7f1b9-202">[Set app protection settings for Android or iOS devices](app-protection-settings-for-android-and-ios.md) (article)</span></span>\
<span data-ttu-id="7f1b9-203">[设置或编辑设备的应用程序保护Windows 10， (](protection-settings-for-windows-10-devices.md)文章) </span><span class="sxs-lookup"><span data-stu-id="7f1b9-203">[Set or edit application protection settings for Windows 10 devices](protection-settings-for-windows-10-devices.md) (article)</span></span>\
<span data-ttu-id="7f1b9-204">[]</span><span class="sxs-lookup"><span data-stu-id="7f1b9-204">[]</span></span>

