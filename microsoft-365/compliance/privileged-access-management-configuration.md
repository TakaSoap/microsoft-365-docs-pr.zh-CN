---
title: 特权访问管理入门
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: 使用本主题可了解有关配置特权访问管理的详细信息。
ms.openlocfilehash: 8c5a0a342c9cabf643bff5e20fc3b64f938c61b7
ms.sourcegitcommit: 8edad75338cf74712ca1ab5d6631b9b52ff54410
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2020
ms.locfileid: "43115988"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="23f80-103">特权访问管理入门</span><span class="sxs-lookup"><span data-stu-id="23f80-103">Get started with privileged access management</span></span>

<span data-ttu-id="23f80-104">本主题指导您在 Office 365 组织中启用和配置特权访问管理。</span><span class="sxs-lookup"><span data-stu-id="23f80-104">This topic guides you through enabling and configuring privileged access management in your Office 365 organization.</span></span> <span data-ttu-id="23f80-105">您可以使用 Microsoft 365 管理中心或 Exchange 管理 PowerShell 管理和使用特权访问。</span><span class="sxs-lookup"><span data-stu-id="23f80-105">You can use either the Microsoft 365 Admin Center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="23f80-106">准备工作</span><span class="sxs-lookup"><span data-stu-id="23f80-106">Before you begin</span></span>

<span data-ttu-id="23f80-107">在开始使用特权访问管理之前，应确认你的[Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)和任何加载项。</span><span class="sxs-lookup"><span data-stu-id="23f80-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="23f80-108">若要访问和使用特权访问管理，您的组织必须具有以下订阅或加载项之一：</span><span class="sxs-lookup"><span data-stu-id="23f80-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="23f80-109">Microsoft 365 E5 订阅（付费或试用版）</span><span class="sxs-lookup"><span data-stu-id="23f80-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="23f80-110">Microsoft 365 E3 订阅（或 Office 365 E3 订阅 + 企业移动和安全 E3 订阅） + Microsoft 365 E5 合规性附加项</span><span class="sxs-lookup"><span data-stu-id="23f80-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="23f80-111">任何 Microsoft 365、Office 365、Exchange、SharePoint 或 OneDrive for business 订阅 + Microsoft 365 E5 内幕版风险管理加载项</span><span class="sxs-lookup"><span data-stu-id="23f80-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>  
- <span data-ttu-id="23f80-112">Microsoft 365 A5 订阅（付费或试用版）</span><span class="sxs-lookup"><span data-stu-id="23f80-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="23f80-113">Microsoft 365 A3 订阅（或 Office 365 A3 订阅 + 企业移动和安全性 A3 订阅） + Microsoft A5 合规性加载项</span><span class="sxs-lookup"><span data-stu-id="23f80-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="23f80-114">任何 Microsoft 365、Office 365、Exchange、SharePoint 或 OneDrive for 教育版订阅 + Microsoft 365 A5 内幕会员风险管理加载项</span><span class="sxs-lookup"><span data-stu-id="23f80-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="23f80-115">Office 365 企业版 E5 订阅（付费或试用版）</span><span class="sxs-lookup"><span data-stu-id="23f80-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="23f80-116">Office 365 企业版 E3 订阅 + Office 365 高级合规性外接程序（不再适用于新订阅，请参阅注意）</span><span class="sxs-lookup"><span data-stu-id="23f80-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="23f80-117">必须为用户提交和响应特权访问管理请求分配上述许可证之一。</span><span class="sxs-lookup"><span data-stu-id="23f80-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="23f80-118">Office 365 高级合规性不再作为独立订阅销售。</span><span class="sxs-lookup"><span data-stu-id="23f80-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="23f80-119">当当前订阅过期时，客户应转换为上述订阅之一，其中包含相同或更多的合规性功能。</span><span class="sxs-lookup"><span data-stu-id="23f80-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="23f80-120">如果您没有现有的 Microsoft 365 企业版 E5 计划，并且想要尝试进行特权访问管理，则可以[将 microsoft 365 添加](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)到现有的 Office 365 订阅中，或注册 Microsoft 365 企业[版](https://www.microsoft.com/microsoft-365/enterprise)e5。</span><span class="sxs-lookup"><span data-stu-id="23f80-120">If you don't have an existing Microsoft 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="23f80-121">启用和配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="23f80-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="23f80-122">按照以下步骤设置和使用 Office 365 组织中的特权访问：</span><span class="sxs-lookup"><span data-stu-id="23f80-122">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="23f80-123">步骤1：创建审批者的组</span><span class="sxs-lookup"><span data-stu-id="23f80-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="23f80-124">在开始使用权限访问之前，请确定哪些用户需要获得对提升的权限和特权的任务的传入请求的审批授权。</span><span class="sxs-lookup"><span data-stu-id="23f80-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="23f80-125">作为审批者组的一部分的任何用户都可以批准访问请求。</span><span class="sxs-lookup"><span data-stu-id="23f80-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="23f80-126">通过在 Office 365 中创建已启用邮件的安全组来启用此组。</span><span class="sxs-lookup"><span data-stu-id="23f80-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="23f80-127">步骤2：启用特权访问</span><span class="sxs-lookup"><span data-stu-id="23f80-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="23f80-128">必须在使用默认审批者组的 Office 365 中显式启用特权访问，包括要从特权访问管理访问控制中排除的一组系统帐户。</span><span class="sxs-lookup"><span data-stu-id="23f80-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="23f80-129">步骤3：创建访问策略</span><span class="sxs-lookup"><span data-stu-id="23f80-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="23f80-130">通过创建审批策略，可以定义各个任务范围内的特定审批要求。</span><span class="sxs-lookup"><span data-stu-id="23f80-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="23f80-131">审批类型选项为 "**自动**" 或 "**手动**"。</span><span class="sxs-lookup"><span data-stu-id="23f80-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="23f80-132">步骤4：提交/批准权限访问请求</span><span class="sxs-lookup"><span data-stu-id="23f80-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="23f80-133">启用后，权限访问需要已定义关联审批策略的任何任务的审批。</span><span class="sxs-lookup"><span data-stu-id="23f80-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="23f80-134">对于审批策略中包含的任务，用户必须请求并授予访问权限，以获得执行任务所必需的权限。</span><span class="sxs-lookup"><span data-stu-id="23f80-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="23f80-135">授予批准后，请求用户可以执行预期的任务，而特权访问将代表用户授权和执行任务。</span><span class="sxs-lookup"><span data-stu-id="23f80-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="23f80-136">审批在请求的持续时间（默认持续时间为4小时）内保持有效，在此期间，请求者可以多次执行预期任务。</span><span class="sxs-lookup"><span data-stu-id="23f80-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="23f80-137">将记录所有此类执行情况，并提供安全和合规性审核。</span><span class="sxs-lookup"><span data-stu-id="23f80-137">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="23f80-138">如果要使用 Exchange 管理 PowerShell 启用和配置特权访问，请按照[使用多重身份验证](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)连接到 Exchange online Powershell 与 Office 365 凭据连接到 Exchange online powershell 中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="23f80-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="23f80-139">您无需为 Office 365 组织启用多重身份验证，即可使用在连接到 Exchange Online PowerShell 时启用特权访问的步骤。</span><span class="sxs-lookup"><span data-stu-id="23f80-139">You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="23f80-140">使用多重身份验证进行连接将创建一个 OAuth 令牌，该令牌由用于对您的请求进行签名的特权访问使用。</span><span class="sxs-lookup"><span data-stu-id="23f80-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="23f80-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="23f80-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="23f80-142">步骤1：创建审批者的组</span><span class="sxs-lookup"><span data-stu-id="23f80-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="23f80-143">使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="23f80-143">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="23f80-144">在管理中心中，转到 "**组** > " "**添加组**"。</span><span class="sxs-lookup"><span data-stu-id="23f80-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="23f80-145">选择 "**已启用邮件的安全组**"，然后完成 "**名称**"、"**组电子邮件地址**" 和 "新组的**说明**" 字段。</span><span class="sxs-lookup"><span data-stu-id="23f80-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="23f80-146">保存组。</span><span class="sxs-lookup"><span data-stu-id="23f80-146">Save the group.</span></span> <span data-ttu-id="23f80-147">可能需要几分钟的时间才能完全配置组并将其显示在 Microsoft 365 管理中心中。</span><span class="sxs-lookup"><span data-stu-id="23f80-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="23f80-148">选择新的审批者组，然后选择 "**编辑**" 将用户添加到组中。</span><span class="sxs-lookup"><span data-stu-id="23f80-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="23f80-149">保存组。</span><span class="sxs-lookup"><span data-stu-id="23f80-149">Save the group.</span></span>

<span data-ttu-id="23f80-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="23f80-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="23f80-151">步骤2：启用特权访问</span><span class="sxs-lookup"><span data-stu-id="23f80-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="23f80-152">在 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="23f80-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="23f80-153">使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="23f80-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="23f80-154">在管理中心中，转到 "**设置" > 设置 > 安全性 & 隐私** > 权限**访问**。</span><span class="sxs-lookup"><span data-stu-id="23f80-154">In the Admin Center, go to **Settings > Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="23f80-155">启用 "**需要批准以获取特权任务**" 控件。</span><span class="sxs-lookup"><span data-stu-id="23f80-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="23f80-156">将您在步骤1中创建的审批者组分配为默认的 "**审批者" 组**。</span><span class="sxs-lookup"><span data-stu-id="23f80-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="23f80-157">**保存**并**关闭**。</span><span class="sxs-lookup"><span data-stu-id="23f80-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="23f80-158">在 Exchange 管理 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="23f80-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="23f80-159">若要启用特权访问并分配审批者的组，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="23f80-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="23f80-160">示例：</span><span class="sxs-lookup"><span data-stu-id="23f80-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="23f80-161">系统帐户功能可用于确保组织内的某些自动脚本可以正常工作，而无需对特权访问进行依赖性，但建议将此类排除条件设为例外，应定期批准和审核这些排除项。</span><span class="sxs-lookup"><span data-stu-id="23f80-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="23f80-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="23f80-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="23f80-163">步骤3：创建访问策略</span><span class="sxs-lookup"><span data-stu-id="23f80-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="23f80-164">您可以为 Office 365 组织创建和配置最高30个权限访问策略。</span><span class="sxs-lookup"><span data-stu-id="23f80-164">You can create and configure up to 30 privileged access policies for your Office 365 organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="23f80-165">在 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="23f80-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="23f80-166">使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="23f80-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="23f80-167">在管理中心中，转到 "**设置** > **安全 & 隐私** > "**特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="23f80-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="23f80-168">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="23f80-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="23f80-169">选择 "**配置策略**"，然后选择 "**添加策略**"。</span><span class="sxs-lookup"><span data-stu-id="23f80-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="23f80-170">从下拉字段中，为您的组织选择适当的值：</span><span class="sxs-lookup"><span data-stu-id="23f80-170">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="23f80-171">**策略类型**：任务、角色或角色组</span><span class="sxs-lookup"><span data-stu-id="23f80-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="23f80-172">**策略作用域**： Exchange</span><span class="sxs-lookup"><span data-stu-id="23f80-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="23f80-173">**策略名称**：从可用策略中进行选择</span><span class="sxs-lookup"><span data-stu-id="23f80-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="23f80-174">**审批类型**：手动或自动</span><span class="sxs-lookup"><span data-stu-id="23f80-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="23f80-175">**审批组**：选择在步骤1中创建的 "审批者" 组</span><span class="sxs-lookup"><span data-stu-id="23f80-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="23f80-176">选择 "**创建**"，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="23f80-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="23f80-177">为策略完全配置和启用可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="23f80-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="23f80-178">在 Exchange 管理 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="23f80-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="23f80-179">若要创建和定义审批策略，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="23f80-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="23f80-180">示例：</span><span class="sxs-lookup"><span data-stu-id="23f80-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="23f80-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="23f80-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="23f80-182">步骤4：提交/批准权限访问请求</span><span class="sxs-lookup"><span data-stu-id="23f80-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="23f80-183">请求提升授权以执行特权任务</span><span class="sxs-lookup"><span data-stu-id="23f80-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="23f80-184">特权访问请求在提交请求后最长24小时有效。</span><span class="sxs-lookup"><span data-stu-id="23f80-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="23f80-185">如果未批准或被拒绝，请求将过期，并且不会获得访问权限。</span><span class="sxs-lookup"><span data-stu-id="23f80-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="23f80-186">在 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="23f80-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="23f80-187">使用您的凭据登录到[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="23f80-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="23f80-188">在管理中心中，转到 "**设置** > **安全 & 隐私** > "**特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="23f80-188">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="23f80-189">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="23f80-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="23f80-190">选择 "**新建请求**"。</span><span class="sxs-lookup"><span data-stu-id="23f80-190">Select **New request**.</span></span> <span data-ttu-id="23f80-191">从下拉字段中，为您的组织选择适当的值：</span><span class="sxs-lookup"><span data-stu-id="23f80-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="23f80-192">**请求类型**：任务、角色或角色组</span><span class="sxs-lookup"><span data-stu-id="23f80-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="23f80-193">**请求范围**： Exchange</span><span class="sxs-lookup"><span data-stu-id="23f80-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="23f80-194">**请求**：从可用策略中选择</span><span class="sxs-lookup"><span data-stu-id="23f80-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="23f80-195">**持续时间（小时）**：请求的访问的小时数。</span><span class="sxs-lookup"><span data-stu-id="23f80-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="23f80-196">对于可以请求的小时数没有限制。</span><span class="sxs-lookup"><span data-stu-id="23f80-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="23f80-197">**注释**：与您的访问请求相关的注释的文本字段</span><span class="sxs-lookup"><span data-stu-id="23f80-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="23f80-198">依次选择 "**保存**" 和 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="23f80-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="23f80-199">您的请求将通过电子邮件发送给审批者的组。</span><span class="sxs-lookup"><span data-stu-id="23f80-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="23f80-200">在 Exchange 管理 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="23f80-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="23f80-201">在 Exchange Online PowerShell 中运行以下命令，以创建批准请求并将其提交给审批者的组：</span><span class="sxs-lookup"><span data-stu-id="23f80-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="23f80-202">示例：</span><span class="sxs-lookup"><span data-stu-id="23f80-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="23f80-203">查看提升请求的状态</span><span class="sxs-lookup"><span data-stu-id="23f80-203">View status of elevation requests</span></span>

<span data-ttu-id="23f80-204">在创建审批请求后，可以在管理中心或 Exchange Management PowerShell 中使用与请求 ID 关联的权限来查看提升请求状态。</span><span class="sxs-lookup"><span data-stu-id="23f80-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="23f80-205">在 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="23f80-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="23f80-206">使用你的凭据登录[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="23f80-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="23f80-207">在管理中心中，转到 "**设置** > **安全 & 隐私** > "**特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="23f80-207">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="23f80-208">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="23f80-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="23f80-209">选择 "**查看**" 以按**待定**、**批准**、**拒绝**或**客户密码箱**状态筛选提交的请求。</span><span class="sxs-lookup"><span data-stu-id="23f80-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="23f80-210">在 Exchange 管理 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="23f80-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="23f80-211">在 Exchange Online PowerShell 中运行以下命令，以查看特定请求 ID 的审批请求状态：</span><span class="sxs-lookup"><span data-stu-id="23f80-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="23f80-212">示例：</span><span class="sxs-lookup"><span data-stu-id="23f80-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="23f80-213">批准提升授权请求</span><span class="sxs-lookup"><span data-stu-id="23f80-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="23f80-214">在创建审批请求时，相关审批者组的成员会收到电子邮件通知，并且可以批准与请求 ID 关联的请求。</span><span class="sxs-lookup"><span data-stu-id="23f80-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="23f80-215">请求者会收到请求审批或通过电子邮件的拒绝通知请求者。</span><span class="sxs-lookup"><span data-stu-id="23f80-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="23f80-216">在 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="23f80-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="23f80-217">使用你的凭据登录[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="23f80-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="23f80-218">在管理中心中，转到 "**设置** > **安全 & 隐私** > "**特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="23f80-218">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="23f80-219">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="23f80-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="23f80-220">选择一个列出的请求以查看详细信息，并对请求执行操作。</span><span class="sxs-lookup"><span data-stu-id="23f80-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="23f80-221">选择 "**批准**" 以批准请求，或选择 "**拒绝**" 以拒绝该请求。</span><span class="sxs-lookup"><span data-stu-id="23f80-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="23f80-222">以前批准的请求可以通过选择 "**吊销**" 来撤销访问权限。</span><span class="sxs-lookup"><span data-stu-id="23f80-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="23f80-223">在 Exchange 管理 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="23f80-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="23f80-224">若要批准提升授权请求，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="23f80-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="23f80-225">示例：</span><span class="sxs-lookup"><span data-stu-id="23f80-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="23f80-226">若要拒绝提升授权请求，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="23f80-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="23f80-227">示例：</span><span class="sxs-lookup"><span data-stu-id="23f80-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="23f80-228">删除 Office 365 中的特权访问策略</span><span class="sxs-lookup"><span data-stu-id="23f80-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="23f80-229">如果您的组织不再需要它，则可以删除特权访问策略。</span><span class="sxs-lookup"><span data-stu-id="23f80-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="23f80-230">在 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="23f80-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="23f80-231">使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="23f80-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="23f80-232">在管理中心中，转到 "**设置** > **安全 & 隐私** > "**特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="23f80-232">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="23f80-233">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="23f80-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="23f80-234">选择 "**配置策略**"。</span><span class="sxs-lookup"><span data-stu-id="23f80-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="23f80-235">选择要删除的策略，然后选择 "**删除策略**"。</span><span class="sxs-lookup"><span data-stu-id="23f80-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="23f80-236">选择“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="23f80-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="23f80-237">在 Exchange 管理 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="23f80-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="23f80-238">若要删除特权访问策略，请在 Exchange Online Powershell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="23f80-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="23f80-239">禁用 Office 365 中的特权访问</span><span class="sxs-lookup"><span data-stu-id="23f80-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="23f80-240">如果需要，您可以为您的组织禁用特权访问管理。</span><span class="sxs-lookup"><span data-stu-id="23f80-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="23f80-241">禁用特权访问不会删除任何关联的审批策略或审批者组。</span><span class="sxs-lookup"><span data-stu-id="23f80-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="23f80-242">在 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="23f80-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="23f80-243">使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="23f80-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="23f80-244">在管理中心中，转到 "**设置** > **安全 & 隐私** > "**特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="23f80-244">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="23f80-245">启用 "**需要批准以进行特权访问**控制"。</span><span class="sxs-lookup"><span data-stu-id="23f80-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="23f80-246">在 Exchange 管理 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="23f80-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="23f80-247">若要禁用特权访问，请在 Exchange Online Powershell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="23f80-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
