---
title: 为 Office 365 ATP 中的安全链接设置配置全局设置
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
description: 管理员可以了解如何在 Office 365 高级威胁防护 (ATP) 中查看和配置全局设置 ("阻止以下 Url" 列表和 Office 365 应用的保护) 以获取安全链接。
ms.openlocfilehash: 50bef8a1edad50540c7212eb4259e17e2368a56c
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350873"
---
# <a name="configure-global-settings-for-safe-links-in-office-365-atp"></a><span data-ttu-id="bcb46-103">在 Office 365 ATP 中配置安全链接的全局设置</span><span class="sxs-lookup"><span data-stu-id="bcb46-103">Configure global settings for Safe Links in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="bcb46-104">本文适用于拥有 [Office 365 高级威胁防护](office-365-atp.md)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="bcb46-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="bcb46-105">如果您是在 Outlook 中查找有关 Safelinks 的信息的家庭用户，请参阅 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="bcb46-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="bcb46-106">安全链接是 [Office 365 高级威胁防护 ](office-365-atp.md) 中的一项功能，它提供了在邮件流中对入站电子邮件进行 URL 扫描的 (ATP) ，以及单击电子邮件中的 url 和链接以及在其他位置的验证时间。</span><span class="sxs-lookup"><span data-stu-id="bcb46-106">Safe Links is a feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="bcb46-107">有关详细信息，请参阅 [Office 365 ATP 中的安全链接](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="bcb46-107">For more information, see [Safe Links in Office 365 ATP](atp-safe-links.md).</span></span>

<span data-ttu-id="bcb46-108">在安全链接策略中配置最安全的链接设置。</span><span class="sxs-lookup"><span data-stu-id="bcb46-108">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="bcb46-109">有关说明，请参阅 [在 Office 365 ATP 中设置安全链接策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bcb46-109">For instructions, see [Set up Safe Links policies in Office 365 ATP](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="bcb46-110">但是，安全链接还使用适用于所有活动安全链接策略中包含的所有用户的全局设置。</span><span class="sxs-lookup"><span data-stu-id="bcb46-110">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="bcb46-111">以下全局设置区域：</span><span class="sxs-lookup"><span data-stu-id="bcb46-111">These global settings area:</span></span>

- <span data-ttu-id="bcb46-112">**阻止以下 url**列表。</span><span class="sxs-lookup"><span data-stu-id="bcb46-112">The **Block the following URLs** list.</span></span> <span data-ttu-id="bcb46-113">有关详细信息，请参阅 [安全链接的 "阻止以下 url" 列表](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="bcb46-113">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="bcb46-114">Office 365 应用的安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="bcb46-114">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="bcb46-115">有关详细信息，请参阅 [Office 365 应用程序的安全链接设置](atp-safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="bcb46-115">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="bcb46-116">您可以使用 Exchange Online 中的邮箱在安全 & 合规性中心或 PowerShell (Exchange Online PowerShell 中配置全局安全链接设置，以获取符合 Exchange Online 中邮箱的符合条件的 Microsoft 365 组织;独立 EOP PowerShell for 不含 Exchange Online 邮箱的组织，但使用 Office 365 ATP 附加订阅) 。</span><span class="sxs-lookup"><span data-stu-id="bcb46-116">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Office 365 ATP add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bcb46-117">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="bcb46-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bcb46-118">安全链接的全局设置提供的功能仅适用于包含在活动安全链接策略中的用户。</span><span class="sxs-lookup"><span data-stu-id="bcb46-118">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="bcb46-119">没有内置的或默认的安全链接策略，因此您需要至少创建一个安全链接策略，以便这些全局设置处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="bcb46-119">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="bcb46-120">有关说明，请参阅 [在 Office 365 ATP 中设置安全链接策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bcb46-120">For instructions, see [Set up Safe Links policies in Office 365 ATP](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="bcb46-121">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="bcb46-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="bcb46-122">若要直接转到 " **ATP 安全链接** " 页面，请使用 <https://protection.office.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="bcb46-122">To go directly to the **ATP Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="bcb46-123">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bcb46-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="bcb46-124">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bcb46-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="bcb46-125">若要查看和配置安全链接的全局设置，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="bcb46-125">To view and configure the global settings for Safe Links, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="bcb46-126">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="bcb46-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="bcb46-127">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的**组织管理**。</span><span class="sxs-lookup"><span data-stu-id="bcb46-127">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="bcb46-128">有关安全链接的全局设置的建议值，请参阅 [安全链接设置](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)。</span><span class="sxs-lookup"><span data-stu-id="bcb46-128">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="bcb46-129">允许使用最长30分钟的时间来应用新的或更新的策略。</span><span class="sxs-lookup"><span data-stu-id="bcb46-129">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="bcb46-130">[将新功能连续添加到 ATP](office-365-atp.md#new-features-in-office-365-atp)。</span><span class="sxs-lookup"><span data-stu-id="bcb46-130">[New features are continually being added to ATP](office-365-atp.md#new-features-in-office-365-atp).</span></span> <span data-ttu-id="bcb46-131">添加新功能时，您可能需要对现有安全链接策略进行调整。</span><span class="sxs-lookup"><span data-stu-id="bcb46-131">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="bcb46-132">在安全 & 合规性中心中配置 "阻止以下 Url" 列表</span><span class="sxs-lookup"><span data-stu-id="bcb46-132">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="bcb46-133">**Block：以下 url**列表标识了应始终被受支持的应用程序中的安全链接扫描所阻止的链接。</span><span class="sxs-lookup"><span data-stu-id="bcb46-133">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="bcb46-134">有关详细信息，请参阅 [安全链接的 "阻止以下 url" 列表](atp-safe-links.md#block-the-following-urls-list-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="bcb46-134">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="bcb46-135">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"，然后单击 " **全局设置**"。</span><span class="sxs-lookup"><span data-stu-id="bcb46-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="bcb46-136">在您的组织的 " **安全链接策略** " 飞出时，请转到 " **阻止以下 url** " 框。</span><span class="sxs-lookup"><span data-stu-id="bcb46-136">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="bcb46-137">配置一个或多个条目，如 ["阻止以下 url 的条目语法" 列表](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)中所述。</span><span class="sxs-lookup"><span data-stu-id="bcb46-137">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="bcb46-138">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bcb46-138">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="bcb46-139">在 PowerShell 中配置 "阻止以下 Url" 列表</span><span class="sxs-lookup"><span data-stu-id="bcb46-139">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="bcb46-140">有关输入语法的详细信息，请参阅 ["阻止以下 url 的条目语法" 列表](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="bcb46-140">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="bcb46-141">您可以使用 **AtpPolicyForO365** Cmdlet 查看 _BlockURLs_ 属性中的现有条目。</span><span class="sxs-lookup"><span data-stu-id="bcb46-141">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="bcb46-142">若要添加将替换任何现有条目的值，请在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bcb46-142">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="bcb46-143">本示例将以下项添加到列表中：</span><span class="sxs-lookup"><span data-stu-id="bcb46-143">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="bcb46-144">阻止 fabrikam.com 的域、子域和路径。</span><span class="sxs-lookup"><span data-stu-id="bcb46-144">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="bcb46-145">阻止子域搜索，但不阻止父域或 tailspintoys.com 中的其他子域</span><span class="sxs-lookup"><span data-stu-id="bcb46-145">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="bcb46-146">若要在不影响其他现有条目的情况下添加或删除值，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bcb46-146">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="bcb46-147">本示例为 adatum.com 添加一个新条目，并删除 fabrikam.com 的条目。</span><span class="sxs-lookup"><span data-stu-id="bcb46-147">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="bcb46-148">在安全 & 合规中心中为 Office 365 应用程序配置安全链接保护</span><span class="sxs-lookup"><span data-stu-id="bcb46-148">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="bcb46-149">Office 365 应用程序的安全链接保护适用于受支持的 Office 桌面、移动设备和 web 应用程序中的文档。</span><span class="sxs-lookup"><span data-stu-id="bcb46-149">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="bcb46-150">有关详细信息，请参阅 [Office 365 应用程序的安全链接设置](atp-safe-links.md#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="bcb46-150">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="bcb46-151">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"，然后单击 " **全局设置**"。</span><span class="sxs-lookup"><span data-stu-id="bcb46-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="bcb46-152">在您的组织的 " **安全链接策略** " 飞出时，将在 "应用于以下内容的设置" 部分中配置以下设置： " **电子邮件除电子邮件** " 部分：</span><span class="sxs-lookup"><span data-stu-id="bcb46-152">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="bcb46-153">**Office 365 应用程序**：验证是否右侧的切换为支持的 Office 365 应用程序启用安全链接： ![ 开启 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。</span><span class="sxs-lookup"><span data-stu-id="bcb46-153">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="bcb46-154">**在用户单击安全链接时不进行跟踪**：将切换向左移动，以跟踪与受支持的 Office 365 应用程序中的阻止 url 相关的用户单击： ![ 关闭 ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="bcb46-154">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="bcb46-155">**不允许用户单击到原始 URL 的安全链接**：验证切换是否向右以阻止用户在受支持的 Office 365 应用程序中单击原始阻止的 URL： ![ 开启 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。</span><span class="sxs-lookup"><span data-stu-id="bcb46-155">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   <span data-ttu-id="bcb46-156">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bcb46-156">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="bcb46-157">为 PowerShell 中的 Office 365 应用程序配置安全链接保护</span><span class="sxs-lookup"><span data-stu-id="bcb46-157">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="bcb46-158">如果您更愿意使用 PowerShell 为 Office 365 应用程序配置安全链接保护，请在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bcb46-158">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="bcb46-159">此示例为 Office 365 应用中的安全链接保护配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="bcb46-159">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="bcb46-160">Office 365 应用的安全链接已打开 (我们不使用 _EnableSafeLinksForO365Clients_ 参数，默认值为) $true。</span><span class="sxs-lookup"><span data-stu-id="bcb46-160">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="bcb46-161">跟踪与受支持的 Office 365 应用程序中的阻止 Url 相关的用户单击。</span><span class="sxs-lookup"><span data-stu-id="bcb46-161">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="bcb46-162">不允许用户在受支持的 Office 365 应用程序中点击到原始阻止的 URL (我们不使用 _AllowClickThrough_ 参数，默认值为 $false) 。</span><span class="sxs-lookup"><span data-stu-id="bcb46-162">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="bcb46-163">有关语法和参数的详细信息，请参阅 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="bcb46-163">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="bcb46-164">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="bcb46-164">How do you know these procedures worked?</span></span>

<span data-ttu-id="bcb46-165">若要验证是否已成功配置安全链接的全局设置 (**阻止以下 url** 列表和 Office 365 应用保护设置) ，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="bcb46-165">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="bcb46-166">在 "安全性 & 合规性中心" 中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"，单击 " **全局设置**"，然后验证出现的 "飞出" 中的设置。</span><span class="sxs-lookup"><span data-stu-id="bcb46-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="bcb46-167">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，运行以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="bcb46-167">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="bcb46-168">有关语法和参数的详细信息，请参阅 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="bcb46-168">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
