---
title: 在"管理"中设置Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 本文介绍如何设置高级审核，以便可以在用户帐户泄露时执行取证调查或调查其他与安全相关的事件。
ms.openlocfilehash: d1752ee7714056254a6c0e5c009aa9aa79ddff3b
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2021
ms.locfileid: "52314270"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a><span data-ttu-id="a51a2-103">在"管理"中设置Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a51a2-103">Set up Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="a51a2-104">如果组织具有支持高级审核的订阅和最终用户许可，请执行以下步骤来设置和使用高级审核中的附加功能。</span><span class="sxs-lookup"><span data-stu-id="a51a2-104">If your organization has a subscription and end user licensing that supports Advanced Audit, perform the following steps to set up and use the additional capabilities in Advanced Audit.</span></span>

![设置高级审核的工作流](../media/AdvancedAuditWorkflow.png)

## <a name="step1-set-up-advanced-audit-for-users"></a><span data-ttu-id="a51a2-106">步骤 1：为用户设置高级审核</span><span class="sxs-lookup"><span data-stu-id="a51a2-106">Step1: Set up Advanced Audit for users</span></span>

<span data-ttu-id="a51a2-107">“高级审核”功能，如记录重要事件（如 MailItemsAccessed 和 Send）功能，需要为用户分配适当的 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="a51a2-107">Advanced Audit features such as the ability to log crucial events such as MailItemsAccessed and Send require an appropriate E5 license assigned to users.</span></span> <span data-ttu-id="a51a2-108">此外，必须为这些用户启用“高级审核”应用程序/服务计划。</span><span class="sxs-lookup"><span data-stu-id="a51a2-108">Additionally, the Advanced Auditing app/service plan must be enabled for those users.</span></span> <span data-ttu-id="a51a2-109">要验证“高级审核”应用程序是否已分配给用户，请对每个用户执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a51a2-109">To verify that the Advanced Auditing app is assigned to users, perform the following steps for each user:</span></span>

1. <span data-ttu-id="a51a2-110">在 [Microsoft 365 管理中心](https://admin.microsoft.com/Adminportal)中，转到“**用户**” > “**活动用户**”，然后选择用户。</span><span class="sxs-lookup"><span data-stu-id="a51a2-110">In the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal), go to **Users** > **Active users**, and select a user.</span></span>

2. <span data-ttu-id="a51a2-111">在用户属性浮出页面上，单击“**许可证和应用**”。</span><span class="sxs-lookup"><span data-stu-id="a51a2-111">On the user properties flyout page, click **Licenses and apps**.</span></span>

3. <span data-ttu-id="a51a2-112">在 **"许可证** "部分，验证用户是否分配有 E5 许可证或分配有相应的附加许可证。</span><span class="sxs-lookup"><span data-stu-id="a51a2-112">In the **Licenses** section, verify that the user is assigned an E5 license or is assigned an appropriate add-on license.</span></span> <span data-ttu-id="a51a2-113">有关支持高级审核的许可证列表，请参阅 [高级审核许可要求](auditing-solutions-overview.md#advanced-audit-1)。</span><span class="sxs-lookup"><span data-stu-id="a51a2-113">For a list of licenses that support Advanced Audit, see [Advanced Audit licensing requirements](auditing-solutions-overview.md#advanced-audit-1).</span></span>

4. <span data-ttu-id="a51a2-114">展开“**应用程序**”部分，并验证是否选中了“**Microsoft 365 高级审核**”复选框。</span><span class="sxs-lookup"><span data-stu-id="a51a2-114">Expand the **Apps** section, and verify that the **Microsoft 365 Advanced Auditing** checkbox is selected.</span></span>

5. <span data-ttu-id="a51a2-115">如果未选中复选框，请选中它，然后单击"保存 **更改"。**</span><span class="sxs-lookup"><span data-stu-id="a51a2-115">If the checkbox isn't selected, select it, and then click **Save changes.**</span></span>

   <span data-ttu-id="a51a2-116">MailItemsAccessed 和 Send 的审核记录日志记录将在 24 小时内开始。</span><span class="sxs-lookup"><span data-stu-id="a51a2-116">The logging of audit records for MailItemsAccessed and Send will begin within 24 hours.</span></span> <span data-ttu-id="a51a2-117">您必须执行步骤 3 才能开始记录其他两个高级审核关键事件：SearchQueryInitiatedExchange 和 SearchQueryInitiatedSharePoint。</span><span class="sxs-lookup"><span data-stu-id="a51a2-117">You have to perform Step 3 to start logging of two other Advanced Audit crucial events: SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint.</span></span>

<span data-ttu-id="a51a2-118">对于使用基于组的许可将许可证分配给用户组的组织，必须为组禁用 Microsoft 365 高级审核的许可分配。</span><span class="sxs-lookup"><span data-stu-id="a51a2-118">For organizations that assign licenses to groups of users by using group-based licensing, you have to turn off the licensing assignment for Microsoft 365 Advanced Auditing for the group.</span></span> <span data-ttu-id="a51a2-119">保存所做的更改后，请验证是否已为组禁用 Microsoft 365 高级审核。</span><span class="sxs-lookup"><span data-stu-id="a51a2-119">After you save your changes, verify that Microsoft 365 Advanced Auditing is turned off for the group.</span></span> <span data-ttu-id="a51a2-120">然后，重新为组启用许可分配。</span><span class="sxs-lookup"><span data-stu-id="a51a2-120">Then turn the licensing assignment for the group back on.</span></span> <span data-ttu-id="a51a2-121">有关基于组的许可的说明，请参阅[在 Azure Active Directory 中按组成员身份向用户分配许可证](/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="a51a2-121">For instructions about group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="a51a2-122">此外，如果已自定义登录用户邮箱或共享邮箱的邮箱操作，Microsoft 发布的任何新关键事件将不会在这些邮箱上自动审核。</span><span class="sxs-lookup"><span data-stu-id="a51a2-122">Also, if you have customized the mailbox actions that are logged on user mailboxes or shared mailboxes, any new crucial events released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="a51a2-123">有关更改为每个登录类型审核的邮箱操作的信息，请参阅[管理邮箱审核](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default)中的“更改或还原默认记录的邮箱操作”部分。</span><span class="sxs-lookup"><span data-stu-id="a51a2-123">For information about changing the mailbox actions that are audited for each logon type, see the "Change or restore mailbox actions logged by default" section in [Manage mailbox auditing](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span></span>

## <a name="step-2-enable-crucial-events"></a><span data-ttu-id="a51a2-124">步骤 2：启用关键事件</span><span class="sxs-lookup"><span data-stu-id="a51a2-124">Step 2: Enable crucial events</span></span>

<span data-ttu-id="a51a2-125">当用户在 Exchange Online 和 SharePoint Online 中执行搜索时，必须启用 SearchQueryInitiatedExchange 和 SearchQueryInitiatedSharePoint) 这两个关键事件。 (</span><span class="sxs-lookup"><span data-stu-id="a51a2-125">You have to enable two crucial events (SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint) to be logged when users perform searches in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="a51a2-126">若要为用户审核这两个事件，请为 ([PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中的) 运行Exchange Online命令：</span><span class="sxs-lookup"><span data-stu-id="a51a2-126">To enable these two events to be audited for users, run the following command (for each user) in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

<span data-ttu-id="a51a2-127">在多地理位置环境中，必须在用户邮箱所在的林中运行以前的 **Set-Mailbox** 命令。</span><span class="sxs-lookup"><span data-stu-id="a51a2-127">In a multi-geo environment, you must run the previous **Set-Mailbox** command in the forest where the user's mailbox is located.</span></span> <span data-ttu-id="a51a2-128">若要标识用户的邮箱位置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a51a2-128">To identify the user's mailbox location, run the following command:</span></span> 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

<span data-ttu-id="a51a2-129">如果用于启用搜索查询审核的命令之前在不同于用户邮箱所在的林中运行的林中，则必须通过运行 来从用户邮箱中删除 SearchQueryInitiated 值，然后将其添加到用户邮箱所在的林中的用户邮箱中。 `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}`</span><span class="sxs-lookup"><span data-stu-id="a51a2-129">If the command to enable the auditing of search queries was previously run in a forest that's different than the one the user's mailbox is located in, then you must remove the SearchQueryInitiated value from the user's mailbox by running `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` and then add it to the user's mailbox in the forest where the user's mailbox is located.</span></span>

## <a name="step-3-set-up-audit-retention-policies"></a><span data-ttu-id="a51a2-130">步骤 3：设置审核保留策略</span><span class="sxs-lookup"><span data-stu-id="a51a2-130">Step 3: Set up audit retention policies</span></span>

<span data-ttu-id="a51a2-131">除了将 Exchange、SharePoint 和 Azure AD 审核记录保留一年的默认策略外，还可以创建其他 审核日志 保留策略，以满足组织的安全操作、IT 和合规性团队的要求。</span><span class="sxs-lookup"><span data-stu-id="a51a2-131">In additional to the default policy that retains Exchange, SharePoint, and Azure AD audit records for one year, you can create additional audit log retention policies to meet the requirements of your organization's security operations, IT, and compliance teams.</span></span> <span data-ttu-id="a51a2-132">有关详细信息，请参阅[管理审核日志保留策略](audit-log-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a51a2-132">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="step-4-search-for-crucial-events"></a><span data-ttu-id="a51a2-133">步骤 4：搜索关键事件</span><span class="sxs-lookup"><span data-stu-id="a51a2-133">Step 4: Search for crucial events</span></span>

<span data-ttu-id="a51a2-134">现在，你已为组织设置了高级审核，可以在执行取证调查时搜索关键事件和其他活动。</span><span class="sxs-lookup"><span data-stu-id="a51a2-134">Now that you have Advanced Audit set up for your organization, you can search for crucial events and other activities when conducting forensic investigations.</span></span> <span data-ttu-id="a51a2-135">完成步骤 1 和步骤 2 后，可以在调查泄露的帐户和其他类型的安全或合规性调查期间，在 审核日志 中搜索关键事件和其他活动。</span><span class="sxs-lookup"><span data-stu-id="a51a2-135">After completing Step 1 and Step 2, you can search the audit log for crucial events and other activities during forensic investigations of compromised accounts and other types of security or compliance investigations.</span></span> <span data-ttu-id="a51a2-136">有关使用 MailItemsAccessed 关键事件对遭到入侵的用户帐户进行取证调查详细信息，请参阅使用高级审核调查遭到入侵 [的帐户](mailitemsaccessed-forensics-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="a51a2-136">For more information about conducting a forensics investigation of compromised user accounts by using the MailItemsAccessed crucial event, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>
