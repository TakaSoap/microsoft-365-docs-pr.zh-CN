---
title: 打开适用于 Office 365 的 Microsoft Defender - SharePoint、OneDrive、& Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 了解如何为 SharePoint、OneDrive 和 Teams 启用 ATP，包括如何为检测到的文件设置警报。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 44d487810156d5de5ae152e08040e8dccd2a4ee0
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682581"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="59968-103">启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="59968-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="59968-104">Microsoft Defender for Office 365 for SharePoint、OneDrive 和 Microsoft Teams 可保护你的组织避免意外共享恶意文件。</span><span class="sxs-lookup"><span data-stu-id="59968-104">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="59968-105">有关详细信息，请参阅适用于[SharePoint、OneDrive 和 Microsoft Teams 的 ATP。](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="59968-105">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="59968-106">本文包含为 SharePoint、OneDrive 和 Microsoft Teams 启用和配置 ATP 的步骤。</span><span class="sxs-lookup"><span data-stu-id="59968-106">This article contains the steps for enabling and configuring ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="59968-107">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="59968-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="59968-108">安全与合规中心的打开网址为 <https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="59968-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="59968-109">若要直接转到 **ATP 安全附件页，** 请打开 <https://protection.office.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="59968-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="59968-110">若要启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP，你需要是安全与合规中心内组织管理或安全&组的成员。</span><span class="sxs-lookup"><span data-stu-id="59968-110">To turn on ATP for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="59968-111">有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="59968-111">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="59968-112">若要使用 SharePoint Online PowerShell 防止用户下载恶意文件，你需要是 Azure AD 中全局管理员或[SharePoint 管理员](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator)角色的成员。 [](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator)</span><span class="sxs-lookup"><span data-stu-id="59968-112">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="59968-113">验证是否为组织启用了审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="59968-113">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="59968-114">有关详细信息，请参阅[打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="59968-114">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="59968-115">设置最多允许 30 分钟生效。</span><span class="sxs-lookup"><span data-stu-id="59968-115">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="59968-116">步骤 1：使用安全与&中心为 SharePoint、OneDrive 和 Microsoft Teams 启用 ATP</span><span class="sxs-lookup"><span data-stu-id="59968-116">Step 1: Use the Security & Compliance Center to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="59968-117">在安全&，转到 **"威胁管理** 策略 \>  \> **ATP 安全附件**"，然后单击"**全局设置"。**</span><span class="sxs-lookup"><span data-stu-id="59968-117">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="59968-118">在出现的 **"** 全局设置"中，转到"启用 **适用于 SharePoint、OneDrive** 和 Microsoft Teams 的 ATP"设置。</span><span class="sxs-lookup"><span data-stu-id="59968-118">In the **Global settings** fly out that appears, go to the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="59968-119">将开关移到右侧"打开" ![ 以 ](../../media/scc-toggle-on.png) 打开适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP。</span><span class="sxs-lookup"><span data-stu-id="59968-119">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="59968-120">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="59968-120">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="59968-121">使用 Exchange Online PowerShell 为 SharePoint、OneDrive 和 Microsoft Teams 启用 ATP</span><span class="sxs-lookup"><span data-stu-id="59968-121">Use Exchange Online PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="59968-122">如果你希望使用 PowerShell 为 SharePoint、OneDrive 和 Microsoft Teams 启用 ATP，请连接到 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="59968-122">If you'd rather use PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="59968-123">有关语法和参数的详细信息，请参阅[Set-AtpPolicyForO365。](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="59968-123">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="59968-124">步骤 2： (推荐) 使用 SharePoint Online PowerShell 阻止用户下载恶意文件</span><span class="sxs-lookup"><span data-stu-id="59968-124">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="59968-125">默认情况下，用户无法打开、移动、复制或共享 ATP 检测到的恶意文件。</span><span class="sxs-lookup"><span data-stu-id="59968-125">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="59968-126">但是，他们可以删除和下载恶意文件。</span><span class="sxs-lookup"><span data-stu-id="59968-126">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="59968-127">若要阻止用户下载恶意文件， [请连接到 SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="59968-127">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="59968-128">**注意**：</span><span class="sxs-lookup"><span data-stu-id="59968-128">**Notes**:</span></span>

- <span data-ttu-id="59968-129">此设置同时影响用户和管理员。</span><span class="sxs-lookup"><span data-stu-id="59968-129">This setting affects both users and admins.</span></span>
- <span data-ttu-id="59968-130">用户仍可以删除恶意文件。</span><span class="sxs-lookup"><span data-stu-id="59968-130">People can still delete malicious files.</span></span>

<span data-ttu-id="59968-131">有关语法和参数的详细信息，请参阅 [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="59968-131">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="59968-132">步骤 3 (推荐) 使用安全与&中心为检测到的文件创建警报策略</span><span class="sxs-lookup"><span data-stu-id="59968-132">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="59968-133">你可以创建一个警报策略，当 ATP for SharePoint、OneDrive 和 Microsoft Teams 检测到恶意文件时，通知你和其他管理员。</span><span class="sxs-lookup"><span data-stu-id="59968-133">You can create an alert policy that notifies you and other admins when ATP for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="59968-134">若要了解有关警报的更多信息，请参阅安全与合规中心 [&活动警报](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="59968-134">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="59968-135">在 [安全&中心](https://protection.office.com)，转到 **"警报** \> **警报策略"或** 打开 <https://protection.office.com/alertpolicies> 。</span><span class="sxs-lookup"><span data-stu-id="59968-135">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="59968-136">在"**警报策略"** 页上，单击 **"新建警报策略"。**</span><span class="sxs-lookup"><span data-stu-id="59968-136">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="59968-137">" **新建警报策略"** 向导将随即打开。在 **"为警报命名"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="59968-137">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="59968-138">**名称**：键入唯一的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="59968-138">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="59968-139">例如，库中的恶意文件。</span><span class="sxs-lookup"><span data-stu-id="59968-139">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="59968-140">**说明**：键入可选说明。</span><span class="sxs-lookup"><span data-stu-id="59968-140">**Description**: Type an optional description.</span></span> <span data-ttu-id="59968-141">例如，在 SharePoint Online、OneDrive 或 Microsoft Teams 中检测到恶意文件时通知管理员。</span><span class="sxs-lookup"><span data-stu-id="59968-141">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="59968-142">**严重性：** 保留默认值"**低**"为选中状态，或选择"**中等**"或"**高"。**</span><span class="sxs-lookup"><span data-stu-id="59968-142">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="59968-143">**选择类别：** 选择 **威胁管理**。</span><span class="sxs-lookup"><span data-stu-id="59968-143">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="59968-144">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="59968-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="59968-145">在 **"创建警报设置** "页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="59968-145">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="59968-146">**要提醒什么？：活动为**：在文件中 **选择检测到的恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="59968-146">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="59968-147">**您希望如何触发警报？：** 每次活动匹配规则时，保留 **默认值** 。</span><span class="sxs-lookup"><span data-stu-id="59968-147">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="59968-148">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="59968-148">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="59968-149">在 **"设置收件人"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="59968-149">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="59968-150">**发送电子邮件通知**：验证是否选择了此设置。</span><span class="sxs-lookup"><span data-stu-id="59968-150">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="59968-151">在 **"电子邮件收件人** "框中，选择一个或多个在检测到恶意文件时应收到通知的全局管理员、安全管理员或安全读者。</span><span class="sxs-lookup"><span data-stu-id="59968-151">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="59968-152">**每日通知限制**：保留默认值 **"无限制"。**</span><span class="sxs-lookup"><span data-stu-id="59968-152">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="59968-153">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="59968-153">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="59968-154">在 **"查看设置"** 页上，查看设置，然后单击任一部分中的"编辑"进行更改。</span><span class="sxs-lookup"><span data-stu-id="59968-154">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="59968-155">In the **Do you want to turn the policy on right away？** section， leave the default value **Yes， turn it on right away** selected.</span><span class="sxs-lookup"><span data-stu-id="59968-155">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="59968-156">完成后，单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="59968-156">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="59968-157">使用安全&合规性 PowerShell 为检测到的文件创建警报策略</span><span class="sxs-lookup"><span data-stu-id="59968-157">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="59968-158">如果您更希望使用 PowerShell 创建与上一部分中描述的相同的警报策略，请连接到安全与合规中心 [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) &并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="59968-158">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="59968-159">**注意**：默认 _严重性值为_ "低"。</span><span class="sxs-lookup"><span data-stu-id="59968-159">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="59968-160">若要指定"中等"或"高"，在命令中包括 _Severity_ 参数和值。</span><span class="sxs-lookup"><span data-stu-id="59968-160">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="59968-161">有关语法和参数的详细信息，请参阅 [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)。</span><span class="sxs-lookup"><span data-stu-id="59968-161">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="59968-162">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="59968-162">How do you know these procedures worked?</span></span>

- <span data-ttu-id="59968-163">若要验证是否成功开启了适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP，请使用以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="59968-163">To verify that you've successfully turned on ATP for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="59968-164">在安全 [](https://protection.office.com)&中心，转到"威胁管理策略 ATP 安全附件"，选择"全局设置"，并验证"启用 \>  \> 适用于 **SharePoint、OneDrive** 和 Microsoft Teams 的 ATP"设置的值。</span><span class="sxs-lookup"><span data-stu-id="59968-164">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="59968-165">在 Exchange Online PowerShell 中，运行以下命令来验证属性设置：</span><span class="sxs-lookup"><span data-stu-id="59968-165">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="59968-166">有关语法和参数的详细信息，请参阅[Get-AtpPolicyForO365。](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="59968-166">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="59968-167">若要验证您是否已成功阻止用户下载恶意文件，请打开 SharePoint Online PowerShell，然后运行以下命令来验证属性值：</span><span class="sxs-lookup"><span data-stu-id="59968-167">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="59968-168">有关语法和参数的详细信息，请参阅 [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="59968-168">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="59968-169">若要验证是否成功为检测到的文件配置了警报策略，请使用以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="59968-169">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="59968-170">在安全&中心，转到"**警报** 警报策略" \>  \> 选择警报策略并验证设置。</span><span class="sxs-lookup"><span data-stu-id="59968-170">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="59968-171">在安全&合规中心 PowerShell 中，替换为警报策略的名称，运行以下命令并 \<AlertPolicyName\> 验证属性值：</span><span class="sxs-lookup"><span data-stu-id="59968-171">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="59968-172">有关语法和参数的详细信息，请参阅 [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)。</span><span class="sxs-lookup"><span data-stu-id="59968-172">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="59968-173">使用 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report) 查看有关 SharePoint、OneDrive 和 Microsoft Teams 中检测到的文件的信息。</span><span class="sxs-lookup"><span data-stu-id="59968-173">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="59968-174">具体来说，您可以使用"查看 **数据"，具体方法为：内容 \> 恶意软件** 视图。</span><span class="sxs-lookup"><span data-stu-id="59968-174">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
