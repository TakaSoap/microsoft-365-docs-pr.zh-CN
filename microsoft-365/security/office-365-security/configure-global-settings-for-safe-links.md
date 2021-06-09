---
title: 在 Defender for 保险箱 中配置链接设置的全局Office 365
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
description: 管理员可以了解如何查看和配置全局设置 (阻止以下 URL"列表和保护 Office 365 应用) for 保险箱 Links in Microsoft Defender for Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4e77373657d3167ca8f5bafa544923ab3a2320ce
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821979"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0ae44-103">在 Microsoft Defender 中配置保险箱链接的全局Office 365</span><span class="sxs-lookup"><span data-stu-id="0ae44-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0ae44-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="0ae44-104">**Applies to**</span></span>
- [<span data-ttu-id="0ae44-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="0ae44-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0ae44-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ae44-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="0ae44-107">本文适用于拥有 [Microsoft Defender for Office 365](defender-for-office-365.md)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="0ae44-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="0ae44-108">如果你是一位家庭用户，正在查找有关 Outlook 中的安全链接的信息，请参阅 Advanced [Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="0ae44-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="0ae44-109">保险箱链接是 Microsoft [Defender for Office 365](defender-for-office-365.md)中的一项功能，它提供对邮件流中入站电子邮件的 URL 扫描，以及电子邮件和其他位置中 URL 和链接的单击验证时间。</span><span class="sxs-lookup"><span data-stu-id="0ae44-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="0ae44-110">有关详细信息，请参阅 microsoft Defender 保险箱[中的链接Office 365。](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="0ae44-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="0ae44-111">您可以在"链接保险箱中配置大多数保险箱链接设置。</span><span class="sxs-lookup"><span data-stu-id="0ae44-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="0ae44-112">有关说明，请参阅在[Microsoft Defender 保险箱设置链接策略Office 365。](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0ae44-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

<span data-ttu-id="0ae44-113">但是，保险箱链接也使用在链接策略本身之外配置的保险箱全局设置：</span><span class="sxs-lookup"><span data-stu-id="0ae44-113">But, Safe Links also uses the following global settings that you configure outside of the Safe Links policies themselves:</span></span>

- <span data-ttu-id="0ae44-114">" **阻止以下 URL"** 列表。</span><span class="sxs-lookup"><span data-stu-id="0ae44-114">The **Block the following URLs** list.</span></span> <span data-ttu-id="0ae44-115">此设置适用于任何活动"链接"策略中包含的保险箱用户。</span><span class="sxs-lookup"><span data-stu-id="0ae44-115">This setting applies to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="0ae44-116">有关详细信息，请参阅[链接链接的"阻止以下 URL"保险箱列表](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="0ae44-116">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="0ae44-117">保险箱链接应用Office 365保护。</span><span class="sxs-lookup"><span data-stu-id="0ae44-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="0ae44-118">这些设置适用于组织中获得 Defender for Office 365 许可的所有用户，而不管这些用户是否包含在活动的 保险箱 链接策略中。</span><span class="sxs-lookup"><span data-stu-id="0ae44-118">These settings apply to all users in the organization who are licensed for Defender for Office 365, regardless of whether the users are included in active Safe Links policies or not.</span></span> <span data-ttu-id="0ae44-119">有关详细信息，请参阅保险箱[应用的链接Office 365设置](safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="0ae44-119">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="0ae44-120">您可以在 保险箱 Microsoft 365 安全中心或 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的符合条件的 Microsoft 365 组织配置全局 Microsoft 365 链接Exchange Online;独立 EOP PowerShell，适用于Exchange Online邮箱，但使用 Microsoft Defender for Office 365 加载项订阅的组织) 。</span><span class="sxs-lookup"><span data-stu-id="0ae44-120">You can configure the global Safe Links settings in the Microsoft 365 security center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0ae44-121">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="0ae44-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0ae44-122">没有内置或默认 保险箱 链接策略，因此您需要创建至少一个 保险箱 链接策略，以便"阻止以下 **URL"** 列表处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="0ae44-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for the **Block the following URLs** list to be active.</span></span> <span data-ttu-id="0ae44-123">有关说明，请参阅在[Microsoft Defender 保险箱设置链接策略Office 365。](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0ae44-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

- <span data-ttu-id="0ae44-124">在 <https://security.microsoft.com> 打开安全中心。</span><span class="sxs-lookup"><span data-stu-id="0ae44-124">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="0ae44-125">若要直接转到"链接 **保险箱，** 请使用 <https://security.microsoft.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="0ae44-125">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="0ae44-126">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0ae44-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0ae44-127">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0ae44-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0ae44-128">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="0ae44-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="0ae44-129">若要为链接保险箱全局设置，您必须是组织管理或 **安全管理员角色组** 的成员。 </span><span class="sxs-lookup"><span data-stu-id="0ae44-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="0ae44-130">若要对链接的全局设置进行只读保险箱，您需要是全局读取 **者** 或安全读者 **角色组的成员**。</span><span class="sxs-lookup"><span data-stu-id="0ae44-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="0ae44-131">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="0ae44-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="0ae44-132">**注意**：</span><span class="sxs-lookup"><span data-stu-id="0ae44-132">**Notes**:</span></span>

  - <span data-ttu-id="0ae44-133">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="0ae44-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="0ae44-134">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="0ae44-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="0ae44-135">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="0ae44-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="0ae44-136">有关我们推荐的用于链接的全局保险箱值，请参阅保险箱[链接设置。](recommended-settings-for-eop-and-office365.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="0ae44-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

- <span data-ttu-id="0ae44-137">最多允许应用新策略或更新策略 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="0ae44-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="0ae44-138">[新功能不断添加到 Microsoft Defender for Office 365。](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="0ae44-138">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="0ae44-139">添加新功能时，可能需要对现有"链接"策略保险箱调整。</span><span class="sxs-lookup"><span data-stu-id="0ae44-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security-center"></a><span data-ttu-id="0ae44-140">在安全中心配置"阻止以下 URL"列表</span><span class="sxs-lookup"><span data-stu-id="0ae44-140">Configure the "Block the following URLs" list in the security center</span></span>

<span data-ttu-id="0ae44-141">"**阻止以下 URL"** 列表标识应始终被支持应用中的"链接保险箱阻止的链接。</span><span class="sxs-lookup"><span data-stu-id="0ae44-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="0ae44-142">有关详细信息，请参阅链接[的"阻止以下 URL"保险箱列表](safe-links.md#block-the-following-urls-list-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="0ae44-142">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="0ae44-143">在安全中心，转到电子邮件&**协作策略** \> **&规则** \> **威胁策略** \> **策略**"部分保险箱 \> **链接"。**</span><span class="sxs-lookup"><span data-stu-id="0ae44-143">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="0ae44-144">在 **"保险箱"页上**，单击"**全局设置"。**</span><span class="sxs-lookup"><span data-stu-id="0ae44-144">On the **Safe Links** page, click **Global settings**.</span></span> <span data-ttu-id="0ae44-145">In the **保险箱 Links policy for your organization** fly out that appears， go to the Block the following **URLs** box.</span><span class="sxs-lookup"><span data-stu-id="0ae44-145">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="0ae44-146">配置一个或多个条目，如"阻止以下 URL"列表的条目 [语法中所述](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="0ae44-146">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="0ae44-147">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="0ae44-147">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="0ae44-148">在 PowerShell 中配置"阻止以下 URL"列表</span><span class="sxs-lookup"><span data-stu-id="0ae44-148">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="0ae44-149">有关条目语法的详细信息，请参阅"阻止以下 [URL"列表的条目语法](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="0ae44-149">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="0ae44-150">您可以使用 **Get-AtpPolicyForO365** cmdlet 查看 _BlockURLs_ 属性中的现有条目。</span><span class="sxs-lookup"><span data-stu-id="0ae44-150">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="0ae44-151">若要添加将替换任何现有条目的值，请使用 PowerShell 或 PowerShell Exchange Online以下Exchange Online Protection语法：</span><span class="sxs-lookup"><span data-stu-id="0ae44-151">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="0ae44-152">本示例向列表中添加以下条目：</span><span class="sxs-lookup"><span data-stu-id="0ae44-152">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="0ae44-153">阻止域、子域和域 fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="0ae44-153">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="0ae44-154">阻止子域研究，但不能阻止子域中的父域或其他子 tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="0ae44-154">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="0ae44-155">若要在不影响其他现有条目的情况下添加或删除值，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="0ae44-155">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="0ae44-156">本示例为 adatum.com 一个新条目，并删除 fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="0ae44-156">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security-center"></a><span data-ttu-id="0ae44-157">在保险箱中心为Office 365应用配置链接保护</span><span class="sxs-lookup"><span data-stu-id="0ae44-157">Configure Safe Links protection for Office 365 apps in the security center</span></span>

<span data-ttu-id="0ae44-158">保险箱适用于应用Office 365的链接保护适用于支持的文档Office桌面、移动和 Web 应用中的文档。</span><span class="sxs-lookup"><span data-stu-id="0ae44-158">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="0ae44-159">有关详细信息，请参阅保险箱[应用的链接Office 365设置](safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="0ae44-159">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="0ae44-160">在安全中心，转到电子邮件&**协作策略** \> **&规则** \> **威胁策略** \> **策略**"部分保险箱 \> **链接"。**</span><span class="sxs-lookup"><span data-stu-id="0ae44-160">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="0ae44-161">在 **"保险箱"页上**，单击"**全局设置"。**</span><span class="sxs-lookup"><span data-stu-id="0ae44-161">On the **Safe Links** page, click **Global settings**.</span></span> <span data-ttu-id="0ae44-162">在 **保险箱"** 组织的链接策略"飞出部分，配置 设置 中适用于受支持的 Office 365 **应用中的内容的以下** 设置：</span><span class="sxs-lookup"><span data-stu-id="0ae44-162">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content in supported Office 365 apps** section:</span></span>

   - <span data-ttu-id="0ae44-163">**Use 保险箱 Links in Office 365 apps**： Verify the toggle is to the right to enable 保险箱 Links for supported Office 365 apps： Toggle on ![ ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="0ae44-163">**Use Safe Links in Office 365 apps**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="0ae44-164">**Do not track when users click protected links in Office 365 apps**： Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps： Toggle off ![ ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="0ae44-164">**Do not track when users click protected links in Office 365 apps**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="0ae44-165">**不允许用户在 Office 365** 应用中单击到原始 URL：验证切换是否位于右侧，以防止用户单击到受支持的 Office 365 应用中的原始阻止 ![ URL：打开。 ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="0ae44-165">**Do not let users click through to the original URL in Office 365 apps**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="0ae44-166">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="0ae44-166">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="0ae44-167">在 PowerShell 保险箱为 Office 365 应用配置链接保护</span><span class="sxs-lookup"><span data-stu-id="0ae44-167">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="0ae44-168">如果你希望使用 PowerShell 为 保险箱 应用配置 保险箱 Office 365 链接保护，请使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的以下语法：</span><span class="sxs-lookup"><span data-stu-id="0ae44-168">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="0ae44-169">此示例为应用中的链接保险箱配置Office 365设置：</span><span class="sxs-lookup"><span data-stu-id="0ae44-169">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="0ae44-170">保险箱我们Office 365 _EnableSafeLinksForO365Clients_ 参数时， (应用的链接将打开，默认值为 $true) 。</span><span class="sxs-lookup"><span data-stu-id="0ae44-170">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="0ae44-171">跟踪与受支持的应用中阻止的 URL Office 365用户单击。</span><span class="sxs-lookup"><span data-stu-id="0ae44-171">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="0ae44-172">不允许用户单击访问受支持的 Office 365 应用中阻止的原始 URL (我们未使用 _AllowClickThrough_ 参数，默认值为 $false) 。</span><span class="sxs-lookup"><span data-stu-id="0ae44-172">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="0ae44-173">有关语法和参数的详细信息，请参阅 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="0ae44-173">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0ae44-174">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="0ae44-174">How do you know these procedures worked?</span></span>

<span data-ttu-id="0ae44-175">若要验证是否成功配置了 保险箱 链接的全局设置 (阻止以下 **URL** 列表和 Office 365 应用保护设置) ，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="0ae44-175">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="0ae44-176">在安全中心中，转到电子邮件&协作策略 \> **&规则** 威胁策略"部分 \>  \> 保险箱链接单击"全局设置 \> **"，** \> 然后验证显示在飞出中的设置。</span><span class="sxs-lookup"><span data-stu-id="0ae44-176">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links** \> click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="0ae44-177">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，运行以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="0ae44-177">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="0ae44-178">有关语法和参数的详细信息，请参阅 [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="0ae44-178">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>
