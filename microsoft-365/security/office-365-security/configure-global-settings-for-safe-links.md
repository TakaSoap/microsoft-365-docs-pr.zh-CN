---
title: 在 Defender for Office 365 中配置安全链接设置的全局设置
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Microsoft Defender for Office 365 (Office 365 安全链接中查看和配置全局设置) "阻止以下 URL"列表和保护。
ms.openlocfilehash: bc44432d4d9478e4c6a2414a70acc785c5b2c005
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682899"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b59d6-103">在 Microsoft Defender for Office 365 中配置安全链接的全局设置</span><span class="sxs-lookup"><span data-stu-id="b59d6-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="b59d6-104">本文适用于拥有 [Microsoft Defender for Office 365](office-365-atp.md)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="b59d6-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="b59d6-105">如果你是一位家庭用户，正在查找有关 Outlook 中安全链接的信息，请参阅高级Outlook.com [安全](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="b59d6-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="b59d6-106">安全链接是 Microsoft [Defender for Office 365](office-365-atp.md) 中的一项功能，它提供对邮件流中入站电子邮件的 URL 扫描，以及单击验证电子邮件和其他位置中的 URL 和链接的时间。</span><span class="sxs-lookup"><span data-stu-id="b59d6-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="b59d6-107">有关详细信息，请参阅 [Microsoft Defender for Office 365 中的安全链接](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="b59d6-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="b59d6-108">您可以在安全链接策略中配置大多数安全链接设置。</span><span class="sxs-lookup"><span data-stu-id="b59d6-108">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="b59d6-109">有关说明，请参阅 [Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md)中的"设置安全链接策略"。</span><span class="sxs-lookup"><span data-stu-id="b59d6-109">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="b59d6-110">但是，安全链接还使用适用于任何活动安全链接策略中包含的所有用户的全局设置。</span><span class="sxs-lookup"><span data-stu-id="b59d6-110">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="b59d6-111">这些全局设置区域：</span><span class="sxs-lookup"><span data-stu-id="b59d6-111">These global settings area:</span></span>

- <span data-ttu-id="b59d6-112">阻止 **以下 URL** 列表。</span><span class="sxs-lookup"><span data-stu-id="b59d6-112">The **Block the following URLs** list.</span></span> <span data-ttu-id="b59d6-113">有关详细信息，请参阅安全链接的"阻止以下 [URL"列表](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="b59d6-113">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="b59d6-114">Office 365 应用的安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="b59d6-114">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="b59d6-115">有关详细信息，请参阅 [Office 365 应用的安全链接设置](atp-safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="b59d6-115">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="b59d6-116">可以在安全与合规中心或 PowerShell (& Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的符合条件的 Microsoft 365 组织配置全局安全链接设置;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell，但具有适用于 Office 365 附加订阅的 Microsoft Defender) 。</span><span class="sxs-lookup"><span data-stu-id="b59d6-116">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b59d6-117">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="b59d6-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b59d6-118">安全链接的全局设置提供的功能仅应用于活动安全链接策略中包含的用户。</span><span class="sxs-lookup"><span data-stu-id="b59d6-118">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="b59d6-119">没有内置或默认安全链接策略，因此您需要创建至少一个安全链接策略，以便这些全局设置处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="b59d6-119">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="b59d6-120">有关说明，请参阅 [Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md)中的"设置安全链接策略"。</span><span class="sxs-lookup"><span data-stu-id="b59d6-120">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="b59d6-121">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="b59d6-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b59d6-122">若要直接转到" **安全链接"** 页，请使用 <https://protection.office.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="b59d6-122">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="b59d6-123">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b59d6-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b59d6-124">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b59d6-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b59d6-125">必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="b59d6-125">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="b59d6-126">若要配置安全链接的全局设置，您必须是组织管理或 **安全** 管理员角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="b59d6-126">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="b59d6-127">若要对安全链接的全局设置进行只读访问，你需要是全局读者或安全读者 **角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="b59d6-127">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="b59d6-128">有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b59d6-128">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="b59d6-129">**注意**：</span><span class="sxs-lookup"><span data-stu-id="b59d6-129">**Notes**:</span></span>

  - <span data-ttu-id="b59d6-130">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="b59d6-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b59d6-131">有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="b59d6-131">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="b59d6-132">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="b59d6-132">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="b59d6-133">有关安全链接的全局设置的建议值，请参阅 [安全链接设置](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)。</span><span class="sxs-lookup"><span data-stu-id="b59d6-133">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="b59d6-134">最多允许应用新策略或更新策略 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="b59d6-134">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="b59d6-135">[新功能不断添加到 Microsoft Defender for Office 365。](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="b59d6-135">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="b59d6-136">添加新功能时，可能需要对现有安全链接策略进行调整。</span><span class="sxs-lookup"><span data-stu-id="b59d6-136">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="b59d6-137">在安全与合规中心中配置"阻止& URL"列表</span><span class="sxs-lookup"><span data-stu-id="b59d6-137">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="b59d6-138">" **阻止以下 URL"** 列表标识应始终被支持应用中的安全链接扫描阻止的链接。</span><span class="sxs-lookup"><span data-stu-id="b59d6-138">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="b59d6-139">有关详细信息，请参阅安全链接的"阻止 [以下 URL"列表](atp-safe-links.md#block-the-following-urls-list-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="b59d6-139">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="b59d6-140">在安全&，转到 **"威胁管理** 策略 \>  \> **ATP 安全链接**"，然后单击"**全局设置"。**</span><span class="sxs-lookup"><span data-stu-id="b59d6-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="b59d6-141">在 **出现的组织安全** 链接策略中，转到"阻止 **以下 URL"** 框。</span><span class="sxs-lookup"><span data-stu-id="b59d6-141">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="b59d6-142">配置一个或多个条目，如"阻止以下 [URL"列表的条目语法中所述](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="b59d6-142">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="b59d6-143">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="b59d6-143">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="b59d6-144">在 PowerShell 中配置"阻止以下 URL"列表</span><span class="sxs-lookup"><span data-stu-id="b59d6-144">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="b59d6-145">有关条目语法的详细信息，请参阅"阻止以下 [URL"列表的条目语法](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="b59d6-145">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="b59d6-146">您可以使用 **Get-AtpPolicyForO365** cmdlet 查看 _BlockURLs_ 属性中的现有条目。</span><span class="sxs-lookup"><span data-stu-id="b59d6-146">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="b59d6-147">若要添加将替换任何现有条目的值，请使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的以下语法：</span><span class="sxs-lookup"><span data-stu-id="b59d6-147">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="b59d6-148">本示例向列表中添加以下条目：</span><span class="sxs-lookup"><span data-stu-id="b59d6-148">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="b59d6-149">阻止域、子域和fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="b59d6-149">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="b59d6-150">阻止子域研究，但不阻止子域中的父域或其他子tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="b59d6-150">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="b59d6-151">若要在不影响其他现有条目的情况下添加或删除值，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="b59d6-151">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="b59d6-152">本示例为 adatum.com 一个新条目，并删除 fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="b59d6-152">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="b59d6-153">在安全与合规中心中为 Office 365 &保护</span><span class="sxs-lookup"><span data-stu-id="b59d6-153">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="b59d6-154">Office 365 应用的安全链接保护适用于受支持的 Office 桌面、移动和 Web 应用中的文档。</span><span class="sxs-lookup"><span data-stu-id="b59d6-154">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="b59d6-155">有关详细信息，请参阅 [Office 365 应用的安全链接设置](atp-safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="b59d6-155">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="b59d6-156">在安全&，转到 **"威胁管理** 策略 \>  \> **ATP 安全链接**"，然后单击"**全局设置"。**</span><span class="sxs-lookup"><span data-stu-id="b59d6-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="b59d6-157">在 **出现的组织安全** 链接策略中，在"设置"中配置应用于电子邮件除外 **内容的以下** 设置：</span><span class="sxs-lookup"><span data-stu-id="b59d6-157">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="b59d6-158">**Office 365** 应用程序：验证切换是否位于右侧，为受支持的 Office 365 应用启用安全 ![ 链接：打开 ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="b59d6-158">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="b59d6-159">**Do not track when users click Safe Links**： Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps： Toggle off ![ ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="b59d6-159">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="b59d6-160">**不允许用户** 单击到原始 URL 的安全链接：验证切换是否位于右侧，以防止用户单击到受支持的 Office 365 应用中的原始阻止的 URL： ![ 打开 ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="b59d6-160">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="b59d6-161">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="b59d6-161">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="b59d6-162">在 PowerShell 中为 Office 365 应用配置安全链接保护</span><span class="sxs-lookup"><span data-stu-id="b59d6-162">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="b59d6-163">如果你想要使用 PowerShell 为 Office 365 应用配置安全链接保护，请使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的以下语法：</span><span class="sxs-lookup"><span data-stu-id="b59d6-163">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="b59d6-164">本示例为 Office 365 应用中的安全链接保护配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="b59d6-164">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="b59d6-165">Office 365 应用的安全链接已打开 (我们未使用 _EnableSafeLinksForO365Clients_ 参数，默认值为 $true) 。</span><span class="sxs-lookup"><span data-stu-id="b59d6-165">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="b59d6-166">跟踪与支持的 Office 365 应用中阻止的 URL 相关的用户单击。</span><span class="sxs-lookup"><span data-stu-id="b59d6-166">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="b59d6-167">不允许用户在支持的 Office 365 应用中单击到原始阻止的 URL (因为我们没有使用 _AllowClickThrough_ 参数，并且默认值为 $false) 。</span><span class="sxs-lookup"><span data-stu-id="b59d6-167">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="b59d6-168">有关语法和参数的详细信息，请参阅[Set-AtpPolicyForO365。](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="b59d6-168">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b59d6-169">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="b59d6-169">How do you know these procedures worked?</span></span>

<span data-ttu-id="b59d6-170">若要验证是否成功配置了安全链接的全局设置 (阻止以下 **URL** 列表和 Office 365 应用保护设置) ，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="b59d6-170">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="b59d6-171">在安全&中心，转到"**威胁** 管理策略 \>  \> **ATP** 安全链接"，单击"全局设置"，然后验证出现的飞出设置。</span><span class="sxs-lookup"><span data-stu-id="b59d6-171">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="b59d6-172">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，运行以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="b59d6-172">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="b59d6-173">有关语法和参数的详细信息，请参阅[Get-AtpPolicyForO365。](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="b59d6-173">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
