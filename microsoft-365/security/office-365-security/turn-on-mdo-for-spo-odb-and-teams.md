---
title: 为 SharePoint、OneDrive 和 Microsoft Teams 启用安全附件
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 管理员可以了解如何为 保险箱、OneDrive 和 Microsoft Teams 启用 SharePoint 附件，包括如何为检测到的文件设置警报。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a654db40e5dec8d23d07ec7455216fe4e0a8c0e7
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933007"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="44495-103">为 SharePoint、OneDrive 和 Microsoft Teams 启用安全附件</span><span class="sxs-lookup"><span data-stu-id="44495-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="44495-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="44495-104">**Applies to**</span></span>
- [<span data-ttu-id="44495-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="44495-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="44495-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="44495-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="44495-107">Microsoft Defender for Office 365 for SharePoint、OneDrive 和 Microsoft Teams可保护你的组织避免意外共享恶意文件。</span><span class="sxs-lookup"><span data-stu-id="44495-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="44495-108">有关详细信息，请参阅 保险箱[Attachments for SharePoint， OneDrive， and Microsoft Teams](mdo-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="44495-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="44495-109">本文包含为用户、保险箱和SharePoint OneDrive和Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="44495-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="44495-110">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="44495-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="44495-111">访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。</span><span class="sxs-lookup"><span data-stu-id="44495-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="44495-112">若要直接转到"附件 **保险箱"页**，请打开 <https://security.microsoft.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="44495-112">To go directly to the **Safe Attachments** page, open <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="44495-113">若要为 SharePoint、OneDrive 和 Microsoft Teams 启用 保险箱 附件，你需要是 Microsoft 365 Defender 门户中组织管理或安全管理员角色组的成员。 </span><span class="sxs-lookup"><span data-stu-id="44495-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="44495-114">有关详细信息，请参阅 Defender 门户[中Microsoft 365权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="44495-114">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="44495-115">若要SharePoint Online PowerShell 阻止用户下载恶意文件，你需要是 Azure AD 中全局管理员[](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator)或 SharePoint[管理员](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator)角色的成员。</span><span class="sxs-lookup"><span data-stu-id="44495-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="44495-116">验证是否为组织启用了审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="44495-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="44495-117">有关详细信息，请参阅 [打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="44495-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="44495-118">设置最多允许 30 分钟生效。</span><span class="sxs-lookup"><span data-stu-id="44495-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="44495-119">步骤 1：使用 Microsoft 365 Defender 门户为 保险箱、SharePoint 和 OneDrive 启用Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="44495-119">Step 1: Use the Microsoft 365 Defender portal to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="44495-120">在 Microsoft 365 Defender 门户中，转到"策略 **"&"** 威胁策略 \>  \> 策略"部分保险箱 \> **附件"。**</span><span class="sxs-lookup"><span data-stu-id="44495-120">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="44495-121">在 **"保险箱"页上**，单击"**全局设置"。**</span><span class="sxs-lookup"><span data-stu-id="44495-121">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="44495-122">In the **Global settings** fly out that appears， go to the Protect files **in SharePoint， OneDrive， and Microsoft Teams** section.</span><span class="sxs-lookup"><span data-stu-id="44495-122">In the **Global settings** fly out that appears, go to the **Protect files in SharePoint, OneDrive, and Microsoft Teams** section.</span></span>

   <span data-ttu-id="44495-123">将"打开 **Office 365 for SharePoint、OneDrive** 和 Microsoft Teams 的 Defender"切换开关移动到"打开"右""打开"以打开 ![ SharePoint、OneDrive 和 Microsoft Teams 的 ](../../media/scc-toggle-on.png) 保险箱 附件。</span><span class="sxs-lookup"><span data-stu-id="44495-123">Move the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="44495-124">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="44495-124">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="44495-125">使用 Exchange Online PowerShell 为保险箱、SharePoint、OneDrive和Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="44495-125">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="44495-126">如果更希望使用 PowerShell 打开 保险箱 Attachments for SharePoint、OneDrive 和 Microsoft Teams，请连接到[Exchange Online PowerShell 并](/powershell/exchange/connect-to-exchange-online-powershell)运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="44495-126">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="44495-127">有关语法和参数的详细信息，请参阅 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="44495-127">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="44495-128">步骤 2： (推荐) 使用 SharePoint Online PowerShell 阻止用户下载恶意文件</span><span class="sxs-lookup"><span data-stu-id="44495-128">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="44495-129">默认情况下，用户无法打开、移动、复制或共享 保险箱 Attachments 检测到的恶意文件SharePoint、OneDrive和 <sup>\*</sup> Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="44495-129">By default, users can't open, move, copy, or share<sup>\*</sup> malicious files that are detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="44495-130">但是，他们可以删除和下载恶意文件。</span><span class="sxs-lookup"><span data-stu-id="44495-130">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="44495-131"><sup>\*</sup>如果用户转到"**管理访问权限"，"\*\*\*\*共享**"选项仍然可用。</span><span class="sxs-lookup"><span data-stu-id="44495-131"><sup>\*</sup> If users go to **Manage access**, the **Share** option is still available.</span></span>

<span data-ttu-id="44495-132">若要阻止用户下载恶意文件，请连接到[SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="44495-132">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="44495-133">**注意**：</span><span class="sxs-lookup"><span data-stu-id="44495-133">**Notes**:</span></span>

- <span data-ttu-id="44495-134">此设置同时影响用户和管理员。</span><span class="sxs-lookup"><span data-stu-id="44495-134">This setting affects both users and admins.</span></span>
- <span data-ttu-id="44495-135">用户仍可以删除恶意文件。</span><span class="sxs-lookup"><span data-stu-id="44495-135">People can still delete malicious files.</span></span>

<span data-ttu-id="44495-136">有关语法和参数的详细信息，请参阅 [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="44495-136">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="44495-137">步骤 3 (推荐) 使用 Microsoft 365 Defender 门户为检测到的文件创建警报策略</span><span class="sxs-lookup"><span data-stu-id="44495-137">Step 3 (Recommended) Use the Microsoft 365 Defender portal to create an alert policy for detected files</span></span>

<span data-ttu-id="44495-138">你可以创建一个警报策略，当 保险箱 附件SharePoint、OneDrive和Microsoft Teams检测到恶意文件时Microsoft Teams通知你和其他管理员。</span><span class="sxs-lookup"><span data-stu-id="44495-138">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="44495-139">若要了解有关警报的信息，请参阅在 defender 门户Microsoft 365[活动警报](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="44495-139">To learn more about alerts, see [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="44495-140">在 defender Microsoft 365门户中，转到策略 **&规则** \> **警报策略** 或打开 <https://security.microsoft.com/alertpolicies> 。</span><span class="sxs-lookup"><span data-stu-id="44495-140">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** or open <https://security.microsoft.com/alertpolicies>.</span></span>

2. <span data-ttu-id="44495-141">在"**警报策略"** 页上，单击"**新建警报策略"。**</span><span class="sxs-lookup"><span data-stu-id="44495-141">On the **Alert policy** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="44495-142">" **新建警报策略"** 向导将随即打开。在" **命名警报"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="44495-142">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>
   - <span data-ttu-id="44495-143">**名称**：键入唯一的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="44495-143">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="44495-144">例如，库中的恶意文件。</span><span class="sxs-lookup"><span data-stu-id="44495-144">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="44495-145">**说明**：键入可选说明。</span><span class="sxs-lookup"><span data-stu-id="44495-145">**Description**: Type an optional description.</span></span> <span data-ttu-id="44495-146">例如，当在 SharePoint Online、OneDrive 或 Microsoft Teams 中检测到恶意文件时，通知管理员。</span><span class="sxs-lookup"><span data-stu-id="44495-146">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="44495-147">**严重性：** 从 **下拉列表中选择"** 低 **、中"** 或"高"。 </span><span class="sxs-lookup"><span data-stu-id="44495-147">**Severity**: Select **Low**, **Medium**, or **High** from the drop down list.</span></span>
   - <span data-ttu-id="44495-148">**类别**： **从下拉列表中选择** 威胁管理。</span><span class="sxs-lookup"><span data-stu-id="44495-148">**Category**: Select **Threat management** from the drop down list.</span></span>

   <span data-ttu-id="44495-149">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="44495-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="44495-150">在" **创建警报设置"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="44495-150">On the **Create alert settings** page, configure the following settings:</span></span>
   - <span data-ttu-id="44495-151">**要提醒什么？** section \> **Activity is** \> Select Detected malware in **file** from the drop down list.</span><span class="sxs-lookup"><span data-stu-id="44495-151">**What do you want to alert on?** section \> **Activity is** \> Select **Detected malware in file** from the drop down list.</span></span>
   - <span data-ttu-id="44495-152">**您希望如何触发警报？** section：每次活动匹配规则 **时保留默认值** 。</span><span class="sxs-lookup"><span data-stu-id="44495-152">**How do you want the alert to be triggered?** section: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="44495-153">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="44495-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="44495-154">在 **"设置收件人"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="44495-154">On the **Set your recipients** page, configure the following settings:</span></span>
   - <span data-ttu-id="44495-155">验证 **是否选择了"发送电子邮件** 通知"。</span><span class="sxs-lookup"><span data-stu-id="44495-155">Verify **Send email notifications** is selected.</span></span> <span data-ttu-id="44495-156">在" **电子邮件收件人** "框中，选择一个或多个在检测到恶意文件时应收到通知的全局管理员、安全管理员或安全读者。</span><span class="sxs-lookup"><span data-stu-id="44495-156">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="44495-157">**每日通知限制**：保留默认值 **"没有限制"。**</span><span class="sxs-lookup"><span data-stu-id="44495-157">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="44495-158">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="44495-158">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="44495-159">在" **查看设置"** 页上，查看设置。</span><span class="sxs-lookup"><span data-stu-id="44495-159">On the **Review your settings** page, review your settings.</span></span> <span data-ttu-id="44495-160">可以在每个部分中选择“**编辑**”来修改该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="44495-160">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="44495-161">或者，可以单击“**返回**”或选择向导中的特定页面。</span><span class="sxs-lookup"><span data-stu-id="44495-161">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="44495-162">在 **"是否想要马上** 打开策略？"部分中，保留默认值"是， **将其打开"保持选中** 状态。</span><span class="sxs-lookup"><span data-stu-id="44495-162">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="44495-163">完成后，单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="44495-163">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="44495-164">使用安全&合规性 PowerShell 为检测到的文件创建警报策略</span><span class="sxs-lookup"><span data-stu-id="44495-164">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="44495-165">如果您更希望使用 PowerShell 创建与上一节中描述的相同的警报策略，请连接到安全& [合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="44495-165">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="44495-166">**注意**：默认 _严重性值为_ Low。</span><span class="sxs-lookup"><span data-stu-id="44495-166">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="44495-167">若要指定 Medium 或 High，在命令中包括 _Severity_ 参数和值。</span><span class="sxs-lookup"><span data-stu-id="44495-167">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="44495-168">有关语法和参数的详细信息，请参阅 [New-ActivityAlert](/powershell/module/exchange/new-activityalert)。</span><span class="sxs-lookup"><span data-stu-id="44495-168">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="44495-169">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="44495-169">How do you know these procedures worked?</span></span>

- <span data-ttu-id="44495-170">若要验证是否成功为 保险箱、SharePoint、OneDrive 和 Microsoft Teams 启用Microsoft Teams，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="44495-170">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="44495-171">在 Microsoft 365 Defender 门户中，转到策略 **& 规则** 威胁策略部分 保险箱 附件，选择全局设置，并验证启用 \>  \> Office 365 \> for  **SharePoint、OneDrive** 和 Microsoft Teams 设置的 Defender 的值。</span><span class="sxs-lookup"><span data-stu-id="44495-171">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="44495-172">在 Exchange Online PowerShell 中，运行以下命令来验证属性设置：</span><span class="sxs-lookup"><span data-stu-id="44495-172">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="44495-173">有关语法和参数的详细信息，请参阅 [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="44495-173">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="44495-174">若要验证您是否已成功阻止用户下载恶意文件，请打开 SharePoint Online PowerShell，然后运行以下命令来验证属性值：</span><span class="sxs-lookup"><span data-stu-id="44495-174">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="44495-175">有关语法和参数的详细信息，请参阅 [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="44495-175">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="44495-176">若要验证是否成功为检测到的文件配置了警报策略，请使用以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="44495-176">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>
  - <span data-ttu-id="44495-177">在 Microsoft 365 Defender 门户中，转到策略 **&** \> **规则 警报策略** 选择警报策略， \> 并验证设置。</span><span class="sxs-lookup"><span data-stu-id="44495-177">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** \> select the alert policy, and verify the settings.</span></span>
  - <span data-ttu-id="44495-178">在Microsoft 365 Defender 门户 PowerShell 中，将 替换为警报策略的名称 \<AlertPolicyName\> ，运行以下命令并验证属性值：</span><span class="sxs-lookup"><span data-stu-id="44495-178">In Microsoft 365 Defender portal PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="44495-179">有关语法和参数的详细信息，请参阅 [Get-ActivityAlert](/powershell/module/exchange/get-activityalert)。</span><span class="sxs-lookup"><span data-stu-id="44495-179">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="44495-180">使用[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)查看有关已检测到的文件在SharePoint、OneDrive和Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="44495-180">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="44495-181">具体来说，您可以使用"查看 **数据者：内容恶意软件 \> "** 视图。</span><span class="sxs-lookup"><span data-stu-id="44495-181">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
