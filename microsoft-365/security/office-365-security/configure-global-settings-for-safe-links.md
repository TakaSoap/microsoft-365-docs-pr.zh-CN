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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何查看和配置全局设置 (阻止以下 URL"列表和保护 Office 365 应用) for Safe Links in Microsoft Defender for Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 390177a24648cf860a78ab831d5dfe334b2c9590
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203164"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="989e7-103">在 Microsoft Defender for Office 365 中配置安全链接的全局设置</span><span class="sxs-lookup"><span data-stu-id="989e7-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="989e7-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="989e7-104">**Applies to**</span></span>
- [<span data-ttu-id="989e7-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="989e7-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="989e7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="989e7-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="989e7-107">本文适用于拥有 [Microsoft Defender for Office 365](defender-for-office-365.md)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="989e7-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="989e7-108">如果您是一位家庭用户，正在查找有关 Outlook 中安全链接的信息，请参阅高级安全 Outlook.com [信息](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="989e7-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="989e7-109">安全链接是 Microsoft [Defender for Office 365](defender-for-office-365.md) 中的一项功能，它提供对邮件流中入站电子邮件的 URL 扫描，以及电子邮件和其他位置中 URL 和链接的单击验证时间。</span><span class="sxs-lookup"><span data-stu-id="989e7-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="989e7-110">有关详细信息，请参阅 [Microsoft Defender for Office 365 中的安全链接](safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="989e7-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="989e7-111">您可以在安全链接策略中配置大多数安全链接设置。</span><span class="sxs-lookup"><span data-stu-id="989e7-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="989e7-112">有关说明，请参阅在 [Microsoft Defender for Office 365](set-up-safe-links-policies.md)中设置安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="989e7-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

<span data-ttu-id="989e7-113">但是，安全链接还使用适用于任何活动安全链接策略中包含的所有用户的全局设置。</span><span class="sxs-lookup"><span data-stu-id="989e7-113">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="989e7-114">这些全局设置区域：</span><span class="sxs-lookup"><span data-stu-id="989e7-114">These global settings area:</span></span>

- <span data-ttu-id="989e7-115">" **阻止以下 URL"** 列表。</span><span class="sxs-lookup"><span data-stu-id="989e7-115">The **Block the following URLs** list.</span></span> <span data-ttu-id="989e7-116">有关详细信息，请参阅安全链接的"阻止以下 [URL"列表](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="989e7-116">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="989e7-117">Office 365 应用的安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="989e7-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="989e7-118">有关详细信息，请参阅 Office [365 应用的安全链接设置](safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="989e7-118">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="989e7-119">您可以在安全与合规中心或 PowerShell (& Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的符合条件的 Microsoft 365 组织配置全局安全链接设置;适用于没有 Exchange Online 邮箱，但具有 Microsoft Defender for Office 365 附加订阅的组织的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="989e7-119">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="989e7-120">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="989e7-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="989e7-121">安全链接的全局设置提供的功能仅适用于活动安全链接策略中包含的用户。</span><span class="sxs-lookup"><span data-stu-id="989e7-121">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="989e7-122">没有内置或默认安全链接策略，因此您需要创建至少一个安全链接策略，以便这些全局设置处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="989e7-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="989e7-123">有关说明，请参阅在 [Microsoft Defender for Office 365](set-up-safe-links-policies.md)中设置安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="989e7-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

- <span data-ttu-id="989e7-124">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="989e7-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="989e7-125">若要直接转到安全 **链接页面** ，请使用 <https://protection.office.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="989e7-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="989e7-126">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="989e7-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="989e7-127">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="989e7-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="989e7-128">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="989e7-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="989e7-129">若要配置安全链接的全局设置，您必须是组织管理或 **安全管理员角色组** 的成员。 </span><span class="sxs-lookup"><span data-stu-id="989e7-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="989e7-130">若要对安全链接的全局设置进行只读访问，你需要是全局读取 **者** 或安全读者 **角色组的成员** 。</span><span class="sxs-lookup"><span data-stu-id="989e7-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="989e7-131">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="989e7-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="989e7-132">**注意**：</span><span class="sxs-lookup"><span data-stu-id="989e7-132">**Notes**:</span></span>

  - <span data-ttu-id="989e7-133">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="989e7-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="989e7-134">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="989e7-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="989e7-135">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="989e7-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="989e7-136">有关安全链接的全局设置的建议值，请参阅 [安全链接设置](recommended-settings-for-eop-and-office365.md#safe-links-settings)。</span><span class="sxs-lookup"><span data-stu-id="989e7-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

- <span data-ttu-id="989e7-137">最多允许应用新策略或更新策略 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="989e7-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="989e7-138">[新功能不断添加到 Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)中。</span><span class="sxs-lookup"><span data-stu-id="989e7-138">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="989e7-139">添加新功能时，可能需要对现有安全链接策略进行调整。</span><span class="sxs-lookup"><span data-stu-id="989e7-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="989e7-140">在安全与合规中心中配置"阻止& URL"列表</span><span class="sxs-lookup"><span data-stu-id="989e7-140">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="989e7-141">" **阻止以下 URL"** 列表标识应始终被支持应用中的安全链接扫描阻止的链接。</span><span class="sxs-lookup"><span data-stu-id="989e7-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="989e7-142">有关详细信息，请参阅安全链接的"阻止 [以下 URL"列表](safe-links.md#block-the-following-urls-list-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="989e7-142">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="989e7-143">在安全与&中心，转到"威胁管理策略 \>  \> **ATP 安全** 链接"，然后单击"全局 **设置"。**</span><span class="sxs-lookup"><span data-stu-id="989e7-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="989e7-144">在出现的 **"组织的安全链接** 策略"飞出中，转到" **阻止以下 URL"** 框。</span><span class="sxs-lookup"><span data-stu-id="989e7-144">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="989e7-145">配置一个或多个条目，如"阻止以下 URL"列表的条目 [语法中所述](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="989e7-145">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="989e7-146">完成后，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="989e7-146">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="989e7-147">在 PowerShell 中配置"阻止以下 URL"列表</span><span class="sxs-lookup"><span data-stu-id="989e7-147">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="989e7-148">有关条目语法的详细信息，请参阅"阻止以下 [URL"列表的条目语法](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="989e7-148">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="989e7-149">您可以使用 **Get-AtpPolicyForO365** cmdlet 查看 _BlockURLs_ 属性中的现有条目。</span><span class="sxs-lookup"><span data-stu-id="989e7-149">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="989e7-150">若要添加将替换任何现有条目的值，请使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的以下语法：</span><span class="sxs-lookup"><span data-stu-id="989e7-150">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="989e7-151">本示例向列表中添加以下条目：</span><span class="sxs-lookup"><span data-stu-id="989e7-151">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="989e7-152">阻止域、子域和域 fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="989e7-152">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="989e7-153">阻止子域研究，但不能阻止子域中的父域或其他子 tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="989e7-153">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="989e7-154">若要在不影响其他现有条目的情况下添加或删除值，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="989e7-154">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="989e7-155">本示例为 adatum.com 一个新条目，并删除 fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="989e7-155">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="989e7-156">在安全与合规中心为 Office 365 &安全链接保护</span><span class="sxs-lookup"><span data-stu-id="989e7-156">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="989e7-157">Office 365 应用的安全链接保护适用于受支持的 Office 桌面、移动和 Web 应用中的文档。</span><span class="sxs-lookup"><span data-stu-id="989e7-157">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="989e7-158">有关详细信息，请参阅 Office [365 应用的安全链接设置](safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="989e7-158">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="989e7-159">在安全与&中心，转到"威胁管理策略 \>  \> **ATP 安全** 链接"，然后单击"全局 **设置"。**</span><span class="sxs-lookup"><span data-stu-id="989e7-159">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="989e7-160">在出现的"组织 **的安全** 链接策略"飞出中，在"设置"中配置应用于电子邮件 **以外的内容的以下** 设置：</span><span class="sxs-lookup"><span data-stu-id="989e7-160">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="989e7-161">**Office 365 应用程序**：验证切换是否位于右侧，为受支持的 Office 365 应用启用安全 ![ 链接：切换为打开 ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="989e7-161">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="989e7-162">**Do not track when users click Safe Links**： Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps： Toggle off ![ ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="989e7-162">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="989e7-163">**不允许用户单击"** 指向原始 URL 的安全链接"：验证切换是否位于右侧，以防止用户单击到受支持的 Office 365 应用中的原始阻止 URL： ![ 切换为打开 ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="989e7-163">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="989e7-164">完成后，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="989e7-164">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="989e7-165">在 PowerShell 中为 Office 365 应用配置安全链接保护</span><span class="sxs-lookup"><span data-stu-id="989e7-165">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="989e7-166">如果你希望使用 PowerShell 为 Office 365 应用配置安全链接保护，请使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的以下语法：</span><span class="sxs-lookup"><span data-stu-id="989e7-166">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="989e7-167">此示例为 Office 365 应用中的安全链接保护配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="989e7-167">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="989e7-168">Office 365 应用的安全链接 (我们未使用 _EnableSafeLinksForO365Clients_ 参数，默认值为 $true) 。</span><span class="sxs-lookup"><span data-stu-id="989e7-168">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="989e7-169">将跟踪与受支持的 Office 365 应用中阻止的 URL 相关的用户单击次数。</span><span class="sxs-lookup"><span data-stu-id="989e7-169">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="989e7-170">不允许用户单击访问受支持的 Office 365 应用中阻止的原始 URL (我们未使用 _AllowClickThrough_ 参数，默认值为 $false) 。</span><span class="sxs-lookup"><span data-stu-id="989e7-170">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="989e7-171">有关语法和参数的详细信息，请参阅 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="989e7-171">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="989e7-172">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="989e7-172">How do you know these procedures worked?</span></span>

<span data-ttu-id="989e7-173">若要验证您是否已成功配置安全链接的全局设置 (阻止以下 **URL** 列表和 Office 365 应用保护设置) ，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="989e7-173">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="989e7-174">在安全&中心，转到"威胁管理策略ATP 安全链接"，单击"全局设置"，然后验证出现的飞出屏幕 \>  \> 中的设置。 </span><span class="sxs-lookup"><span data-stu-id="989e7-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="989e7-175">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，运行以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="989e7-175">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="989e7-176">有关语法和参数的详细信息，请参阅 [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="989e7-176">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>