---
title: 启用 Office 365 ATP-SharePoint、OneDrive、& 团队
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 了解如何为 SharePoint、OneDrive 和团队打开 ATP，包括如何为检测到的文件设置通知。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1cd345ae74b81c23f92b9e9b7d712efa8b875503
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326897"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="07f72-103">启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="07f72-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="07f72-104">Office 365 高级威胁防护 (适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP) 保护您的组织不会在无意中共享恶意文件。</span><span class="sxs-lookup"><span data-stu-id="07f72-104">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="07f72-105">有关详细信息，请参阅 [适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="07f72-105">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="07f72-106">本文包含为 SharePoint、OneDrive 和 Microsoft 团队启用和配置 ATP 的步骤。</span><span class="sxs-lookup"><span data-stu-id="07f72-106">This article contains the steps for enabling and configuring ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="07f72-107">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="07f72-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="07f72-108">安全与合规中心的打开网址为 <https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="07f72-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="07f72-109">若要直接转到 " **ATP 安全附件** " 页面，请打开 <https://protection.office.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="07f72-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="07f72-110">若要打开 SharePoint、OneDrive 和 Microsoft 团队的 ATP，您需要是安全 & 合规性中心中的 " **组织管理** " 或 " **安全管理员** " 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="07f72-110">To turn on ATP for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="07f72-111">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="07f72-111">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="07f72-112">若要使用 SharePoint Online PowerShell 阻止用户下载恶意文件，您必须是 Azure AD 中 [全局管理员](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 或 [SharePoint 管理员](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="07f72-112">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="07f72-113">验证是否已为您的组织启用审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="07f72-113">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="07f72-114">有关详细信息，请参阅[打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="07f72-114">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="07f72-115">允许最长30分钟的设置生效。</span><span class="sxs-lookup"><span data-stu-id="07f72-115">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="07f72-116">步骤1：使用安全 & 合规中心打开 SharePoint、OneDrive 和 Microsoft 团队的 ATP</span><span class="sxs-lookup"><span data-stu-id="07f72-116">Step 1: Use the Security & Compliance Center to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="07f72-117">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全附件**"，然后单击 " **全局设置**"。</span><span class="sxs-lookup"><span data-stu-id="07f72-117">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="07f72-118">在 " **全局设置** " 飞出时，转到 " **启用 SharePoint、OneDrive 和 MICROSOFT 团队的 ATP** " 设置。</span><span class="sxs-lookup"><span data-stu-id="07f72-118">In the **Global settings** fly out that appears, go to the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="07f72-119">将切换切换到右侧 ![ 切换，以 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 打开 SharePoint、OneDrive 和 Microsoft 团队的 ATP。</span><span class="sxs-lookup"><span data-stu-id="07f72-119">Move the toggle to the right ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) to turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="07f72-120">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="07f72-120">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="07f72-121">使用 Exchange Online PowerShell 打开 SharePoint、OneDrive 和 Microsoft 团队的 ATP</span><span class="sxs-lookup"><span data-stu-id="07f72-121">Use Exchange Online PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="07f72-122">如果你更愿意使用 PowerShell 打开 SharePoint、OneDrive 和 Microsoft 团队的 ATP，请 [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="07f72-122">If you'd rather use PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="07f72-123">有关语法和参数的详细信息，请参阅 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="07f72-123">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="07f72-124">步骤2：建议 () 使用 SharePoint Online PowerShell 以防止用户下载恶意文件</span><span class="sxs-lookup"><span data-stu-id="07f72-124">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="07f72-125">默认情况下，用户无法打开、移动、复制或共享由 ATP 检测到的恶意文件。</span><span class="sxs-lookup"><span data-stu-id="07f72-125">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="07f72-126">但是，他们可以删除和下载恶意文件。</span><span class="sxs-lookup"><span data-stu-id="07f72-126">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="07f72-127">若要阻止用户下载恶意文件，请 [连接到 SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="07f72-127">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="07f72-128">**注意**：</span><span class="sxs-lookup"><span data-stu-id="07f72-128">**Notes**:</span></span>

- <span data-ttu-id="07f72-129">此设置会影响用户和管理员。</span><span class="sxs-lookup"><span data-stu-id="07f72-129">This setting affects both users and admins.</span></span>
- <span data-ttu-id="07f72-130">用户仍可以删除恶意文件。</span><span class="sxs-lookup"><span data-stu-id="07f72-130">People can still delete malicious files.</span></span>

<span data-ttu-id="07f72-131">有关语法和参数的详细信息，请参阅 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="07f72-131">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="07f72-132">建议的步骤 3 () 使用安全 & 合规中心为检测到的文件创建通知策略</span><span class="sxs-lookup"><span data-stu-id="07f72-132">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="07f72-133">当 SharePoint、OneDrive 和 Microsoft 团队的 ATP 检测到恶意文件时，可以创建通知您和其他管理员的通知策略。</span><span class="sxs-lookup"><span data-stu-id="07f72-133">You can create an alert policy that notifies you and other admins when ATP for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="07f72-134">若要了解有关通知的详细信息，请参阅 [在安全 & 合规性中心中创建活动通知](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="07f72-134">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="07f72-135">在 [安全 & 合规性中心](https://protection.office.com)中，转到 " **通知**" "通知 \> **策略** " 或 "打开" <https://protection.office.com/alertpolicies> 。</span><span class="sxs-lookup"><span data-stu-id="07f72-135">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="07f72-136">在 " **通知策略** " 页上，单击 " **新建通知策略**"。</span><span class="sxs-lookup"><span data-stu-id="07f72-136">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="07f72-137">" **新建通知策略** " 向导将在飞出时打开。在 "将 **通知命名** 为" 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="07f72-137">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="07f72-138">**名称**：键入唯一的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="07f72-138">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="07f72-139">例如，库中的恶意文件。</span><span class="sxs-lookup"><span data-stu-id="07f72-139">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="07f72-140">**说明**：键入可选的说明。</span><span class="sxs-lookup"><span data-stu-id="07f72-140">**Description**: Type an optional description.</span></span> <span data-ttu-id="07f72-141">例如，当在 SharePoint Online、OneDrive 或 Microsoft 团队中检测到恶意文件时，会通知管理员。</span><span class="sxs-lookup"><span data-stu-id="07f72-141">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="07f72-142">**严重性**：保持选定的默认值为 " **低** "，或选择 " **中** " 或 " **高**"。</span><span class="sxs-lookup"><span data-stu-id="07f72-142">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="07f72-143">**选择一个类别**：选择 **威胁管理**。</span><span class="sxs-lookup"><span data-stu-id="07f72-143">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="07f72-144">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="07f72-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="07f72-145">在 " **创建通知设置** " 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="07f72-145">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="07f72-146">**你希望在什么情况上提醒？：活动为**：在 **文件中选择检测到的恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="07f72-146">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="07f72-147">**您希望如何触发警报？**： **每次活动匹配选定的规则时** ，保留默认值。</span><span class="sxs-lookup"><span data-stu-id="07f72-147">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="07f72-148">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="07f72-148">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="07f72-149">在 " **设置收件人** " 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="07f72-149">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="07f72-150">**发送电子邮件通知**：确认已选中此设置。</span><span class="sxs-lookup"><span data-stu-id="07f72-150">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="07f72-151">在 " **电子邮件收件人** " 框中，选择一个或多个全局管理员、安全管理员或在检测到恶意文件时应收到通知的安全阅读者。</span><span class="sxs-lookup"><span data-stu-id="07f72-151">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="07f72-152">**每日通知限制**：保留默认值 " **无限制** " 处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="07f72-152">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="07f72-153">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="07f72-153">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="07f72-154">在 " **查看您的设置** " 页上，查看设置，然后单击任何部分中的 " **编辑** " 以进行更改。</span><span class="sxs-lookup"><span data-stu-id="07f72-154">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="07f72-155">在 " **是否要立即启用策略？** " 部分，保留默认值 **"是"，然后将其立即打开** 。</span><span class="sxs-lookup"><span data-stu-id="07f72-155">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="07f72-156">完成后，单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="07f72-156">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="07f72-157">使用 Security & 合规性 PowerShell 为检测到的文件创建通知策略</span><span class="sxs-lookup"><span data-stu-id="07f72-157">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="07f72-158">如果您希望使用 PowerShell 创建与上一节中所述相同的警报策略，请 [连接到 Security & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) ，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="07f72-158">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="07f72-159">**注意**：默认 _严重性_ 值为 "低"。</span><span class="sxs-lookup"><span data-stu-id="07f72-159">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="07f72-160">若要指定 "中" 或 "高"，请在命令中包含 _严重性_ 参数和值。</span><span class="sxs-lookup"><span data-stu-id="07f72-160">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="07f72-161">有关语法和参数的详细信息，请参阅 [set-activityalert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)。</span><span class="sxs-lookup"><span data-stu-id="07f72-161">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="07f72-162">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="07f72-162">How do you know these procedures worked?</span></span>

- <span data-ttu-id="07f72-163">若要验证是否成功启用了 SharePoint、OneDrive 和 Microsoft 团队的 ATP，请使用以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="07f72-163">To verify that you've successfully turned on ATP for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="07f72-164">在 " [安全性 & 合规性中心](https://protection.office.com)" 中，转到 " **威胁管理** \> **策略** \> **ATP 安全附件**"，选择 " **全局设置**"，然后验证 " **启用 SharePoint、OneDrive 和 Microsoft 团队的 ATP** 的值" 设置的值。</span><span class="sxs-lookup"><span data-stu-id="07f72-164">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="07f72-165">在 Exchange Online PowerShell 中，运行以下命令以验证属性设置：</span><span class="sxs-lookup"><span data-stu-id="07f72-165">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="07f72-166">有关语法和参数的详细信息，请参阅 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="07f72-166">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="07f72-167">若要验证是否已成功阻止用户下载恶意文件，请打开 SharePoint Online PowerShell，然后运行以下命令来验证属性值：</span><span class="sxs-lookup"><span data-stu-id="07f72-167">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="07f72-168">有关语法和参数的详细信息，请参阅 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="07f72-168">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="07f72-169">若要验证是否已成功为检测到的文件配置了通知策略，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="07f72-169">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="07f72-170">在安全 & 合规性中心中，转到 " **通知** \> " "通知 **策略**"， \> 选择 "通知策略" 并验证设置。</span><span class="sxs-lookup"><span data-stu-id="07f72-170">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="07f72-171">在安全 & 合规性中心 PowerShell 中，将替换 \<AlertPolicyName\> 为警报策略的名称，运行以下命令，并验证属性值：</span><span class="sxs-lookup"><span data-stu-id="07f72-171">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="07f72-172">有关语法和参数的详细信息，请参阅 [set-activityalert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)。</span><span class="sxs-lookup"><span data-stu-id="07f72-172">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="07f72-173">使用 " [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report) " 查看 SharePoint、OneDrive 和 Microsoft 团队中检测到的文件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="07f72-173">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="07f72-174">具体来说，可以使用 " **查看数据的方式：内容 \> 恶意软件** " 视图。</span><span class="sxs-lookup"><span data-stu-id="07f72-174">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
