---
title: 在 Office 365 中配置特权访问管理
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
description: 使用本主题可了解有关在 Office 365 中配置特权访问管理的详细信息
ms.openlocfilehash: 36a473369ba539230bc4bbb2a630d74830844fc7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601729"
---
# <a name="configuring-privileged-access-management-in-office-365"></a><span data-ttu-id="052d3-103">在 Office 365 中配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="052d3-103">Configuring privileged access management in Office 365</span></span>

>[!IMPORTANT]
><span data-ttu-id="052d3-104">本主题介绍了 Office 365 E5 和高级合规 Sku 中目前仅提供的功能的部署和配置指南。</span><span class="sxs-lookup"><span data-stu-id="052d3-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="052d3-105">本主题指导您在 Office 365 组织中启用和配置特权访问管理。</span><span class="sxs-lookup"><span data-stu-id="052d3-105">This topic guides you through enabling and configuring privileged access management in your Office 365 organization.</span></span> <span data-ttu-id="052d3-106">您可以使用 Microsoft 365 管理中心或 Exchange 管理 PowerShell 管理和使用特权访问。</span><span class="sxs-lookup"><span data-stu-id="052d3-106">You can use either the Microsoft 365 Admin Center or Exchange Management PowerShell to manage and use privileged access.</span></span> 

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="052d3-107">启用和配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="052d3-107">Enable and configure privileged access management</span></span>

<span data-ttu-id="052d3-108">按照以下步骤设置和使用 Office 365 组织中的特权访问：</span><span class="sxs-lookup"><span data-stu-id="052d3-108">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="052d3-109">步骤1：创建审批者的组</span><span class="sxs-lookup"><span data-stu-id="052d3-109">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="052d3-110">在开始使用权限访问之前，请确定哪些用户需要获得对提升的权限和特权的任务的传入请求的审批授权。</span><span class="sxs-lookup"><span data-stu-id="052d3-110">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="052d3-111">作为审批者组的一部分的任何用户都可以批准访问请求。</span><span class="sxs-lookup"><span data-stu-id="052d3-111">Any user who is part of the Approvers’ group is able to approve access requests.</span></span> <span data-ttu-id="052d3-112">通过在 Office 365 中创建已启用邮件的安全组来启用此组。</span><span class="sxs-lookup"><span data-stu-id="052d3-112">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="052d3-113">步骤2：启用特权访问</span><span class="sxs-lookup"><span data-stu-id="052d3-113">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="052d3-114">必须在使用默认审批者组的 Office 365 中显式启用特权访问，包括要从特权访问管理访问控制中排除的一组系统帐户。</span><span class="sxs-lookup"><span data-stu-id="052d3-114">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="052d3-115">步骤3：创建访问策略</span><span class="sxs-lookup"><span data-stu-id="052d3-115">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="052d3-116">通过创建审批策略，可以定义各个任务范围内的特定审批要求。</span><span class="sxs-lookup"><span data-stu-id="052d3-116">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="052d3-117">审批类型选项为 "**自动**" 或 "**手动**"。</span><span class="sxs-lookup"><span data-stu-id="052d3-117">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="052d3-118">步骤4：提交/批准权限访问请求</span><span class="sxs-lookup"><span data-stu-id="052d3-118">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="052d3-119">启用后，权限访问需要已定义关联审批策略的任何任务的审批。</span><span class="sxs-lookup"><span data-stu-id="052d3-119">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="052d3-120">对于审批策略中包含的任务，用户必须请求并授予访问权限，以获得执行任务所必需的权限。</span><span class="sxs-lookup"><span data-stu-id="052d3-120">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="052d3-121">授予批准后，请求用户可以执行预期的任务，而特权访问将代表用户授权和执行任务。</span><span class="sxs-lookup"><span data-stu-id="052d3-121">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="052d3-122">审批在请求的持续时间（默认持续时间为4小时）内保持有效，在此期间，请求者可以多次执行预期任务。</span><span class="sxs-lookup"><span data-stu-id="052d3-122">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="052d3-123">将记录所有此类执行情况，并提供安全和合规性审核。</span><span class="sxs-lookup"><span data-stu-id="052d3-123">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="052d3-124">如果要使用 Exchange 管理 PowerShell 启用和配置特权访问，请按照[使用多重身份验证](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)连接到 Exchange online Powershell 与 Office 365 凭据连接到 Exchange online powershell 中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="052d3-124">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="052d3-125">您无需为 Office 365 组织启用多重身份验证，即可使用在连接到 Exchange Online PowerShell 时启用特权访问的步骤。</span><span class="sxs-lookup"><span data-stu-id="052d3-125">You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="052d3-126">使用多重身份验证进行连接将创建一个 OAuth 令牌，该令牌由用于对您的请求进行签名的特权访问使用。</span><span class="sxs-lookup"><span data-stu-id="052d3-126">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="052d3-127"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="052d3-127"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="052d3-128">步骤1：创建审批者的组</span><span class="sxs-lookup"><span data-stu-id="052d3-128">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="052d3-129">使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="052d3-129">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="052d3-130">在管理中心中，转到 "**组** > " "**添加组**"。</span><span class="sxs-lookup"><span data-stu-id="052d3-130">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="052d3-131">选择 "**已启用邮件的安全组**"，然后完成 "**名称**"、"**组电子邮件地址**" 和 "新组的**说明**" 字段。</span><span class="sxs-lookup"><span data-stu-id="052d3-131">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="052d3-132">保存组。</span><span class="sxs-lookup"><span data-stu-id="052d3-132">Save the group.</span></span> <span data-ttu-id="052d3-133">可能需要几分钟的时间才能完全配置组并将其显示在 Microsoft 365 管理中心中。</span><span class="sxs-lookup"><span data-stu-id="052d3-133">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="052d3-134">选择新的审批者组，然后选择 "**编辑**" 将用户添加到组中。</span><span class="sxs-lookup"><span data-stu-id="052d3-134">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="052d3-135">保存组。</span><span class="sxs-lookup"><span data-stu-id="052d3-135">Save the group.</span></span>

<span data-ttu-id="052d3-136"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="052d3-136"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="052d3-137">步骤2：启用特权访问</span><span class="sxs-lookup"><span data-stu-id="052d3-137">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="052d3-138">在 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="052d3-138">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="052d3-139">使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="052d3-139">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="052d3-140">在管理中心中，转到 "**设置" > 设置 > 安全性 & 隐私** > 权限**访问**。</span><span class="sxs-lookup"><span data-stu-id="052d3-140">In the Admin Center, go to **Settings > Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="052d3-141">启用 "**需要批准以获取特权任务**" 控件。</span><span class="sxs-lookup"><span data-stu-id="052d3-141">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="052d3-142">将您在步骤1中创建的审批者组分配为默认的 "**审批者" 组**。</span><span class="sxs-lookup"><span data-stu-id="052d3-142">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="052d3-143">**保存**并**关闭**。</span><span class="sxs-lookup"><span data-stu-id="052d3-143">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="052d3-144">在 Exchange 管理 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="052d3-144">In Exchange Management PowerShell</span></span>

<span data-ttu-id="052d3-145">若要启用特权访问并分配审批者的组，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="052d3-145">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="052d3-146">示例：</span><span class="sxs-lookup"><span data-stu-id="052d3-146">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="052d3-147">系统帐户功能可用于确保组织内的某些自动脚本可以正常工作，而无需对特权访问进行依赖性，但建议将此类排除条件设为例外，并且应批准和审核这些排除条件保持.</span><span class="sxs-lookup"><span data-stu-id="052d3-147">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="052d3-148"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="052d3-148"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="052d3-149">步骤3：创建访问策略</span><span class="sxs-lookup"><span data-stu-id="052d3-149">Step 3: Create an access policy</span></span>

<span data-ttu-id="052d3-150">您可以为 Office 365 组织创建和配置最高30个权限访问策略。</span><span class="sxs-lookup"><span data-stu-id="052d3-150">You can create and configure up to 30 privileged access policies for your Office 365 organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="052d3-151">在 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="052d3-151">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="052d3-152">使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="052d3-152">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="052d3-153">在管理中心中，转到 "**设置** > **安全 & 隐私** > "**特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="052d3-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="052d3-154">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="052d3-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="052d3-155">选择 "**配置策略**"，然后选择 "**添加策略**"。</span><span class="sxs-lookup"><span data-stu-id="052d3-155">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="052d3-156">从下拉字段中，为您的组织选择适当的值：</span><span class="sxs-lookup"><span data-stu-id="052d3-156">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="052d3-157">**策略类型**：任务、角色或角色组</span><span class="sxs-lookup"><span data-stu-id="052d3-157">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="052d3-158">**策略作用域**： Exchange</span><span class="sxs-lookup"><span data-stu-id="052d3-158">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="052d3-159">**策略名称**：从可用策略中进行选择</span><span class="sxs-lookup"><span data-stu-id="052d3-159">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="052d3-160">**审批类型**：手动或自动</span><span class="sxs-lookup"><span data-stu-id="052d3-160">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="052d3-161">**审批组**：选择在步骤1中创建的 "审批者" 组</span><span class="sxs-lookup"><span data-stu-id="052d3-161">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="052d3-162">选择 "**创建**"，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="052d3-162">Select **Create** and then **Close**.</span></span> <span data-ttu-id="052d3-163">为策略完全配置和启用可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="052d3-163">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="052d3-164">在 Exchange 管理 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="052d3-164">In Exchange Management PowerShell</span></span>

<span data-ttu-id="052d3-165">若要创建和定义审批策略，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="052d3-165">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="052d3-166">示例：</span><span class="sxs-lookup"><span data-stu-id="052d3-166">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="052d3-167"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="052d3-167"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="052d3-168">步骤4：提交/批准权限访问请求</span><span class="sxs-lookup"><span data-stu-id="052d3-168">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="052d3-169">请求提升授权以执行特权任务</span><span class="sxs-lookup"><span data-stu-id="052d3-169">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="052d3-170">特权访问请求在提交请求后最长24小时有效。</span><span class="sxs-lookup"><span data-stu-id="052d3-170">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="052d3-171">如果未批准或被拒绝，请求将过期，并且不会获得访问权限。</span><span class="sxs-lookup"><span data-stu-id="052d3-171">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="052d3-172">在 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="052d3-172">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="052d3-173">使用您的凭据登录到[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="052d3-173">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="052d3-174">在管理中心中，转到 "**设置** > **安全 & 隐私** > "**特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="052d3-174">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="052d3-175">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="052d3-175">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="052d3-176">选择 "**新建请求**"。</span><span class="sxs-lookup"><span data-stu-id="052d3-176">Select **New request**.</span></span> <span data-ttu-id="052d3-177">从下拉字段中，为您的组织选择适当的值：</span><span class="sxs-lookup"><span data-stu-id="052d3-177">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="052d3-178">**请求类型**：任务、角色或角色组</span><span class="sxs-lookup"><span data-stu-id="052d3-178">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="052d3-179">**请求范围**： Exchange</span><span class="sxs-lookup"><span data-stu-id="052d3-179">**Request scope**: Exchange</span></span>

    <span data-ttu-id="052d3-180">**请求**：从可用策略中选择</span><span class="sxs-lookup"><span data-stu-id="052d3-180">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="052d3-181">**持续时间（小时）**：请求的访问的小时数。</span><span class="sxs-lookup"><span data-stu-id="052d3-181">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="052d3-182">对于可以请求的小时数没有限制。</span><span class="sxs-lookup"><span data-stu-id="052d3-182">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="052d3-183">**注释**：与您的访问请求相关的注释的文本字段</span><span class="sxs-lookup"><span data-stu-id="052d3-183">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="052d3-184">依次选择 "**保存**" 和 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="052d3-184">Select **Save** and then **Close**.</span></span> <span data-ttu-id="052d3-185">您的请求将通过电子邮件发送给审批者的组。</span><span class="sxs-lookup"><span data-stu-id="052d3-185">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="052d3-186">在 Exchange 管理 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="052d3-186">In Exchange Management PowerShell</span></span>

<span data-ttu-id="052d3-187">在 Exchange Online PowerShell 中运行以下命令，以创建批准请求并将其提交给审批者的组：</span><span class="sxs-lookup"><span data-stu-id="052d3-187">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="052d3-188">示例：</span><span class="sxs-lookup"><span data-stu-id="052d3-188">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="052d3-189">查看提升请求的状态</span><span class="sxs-lookup"><span data-stu-id="052d3-189">View status of elevation requests</span></span>

<span data-ttu-id="052d3-190">在创建审批请求后，可以在管理中心或 Exchange Management PowerShell 中使用与请求 ID 关联的权限来查看提升请求状态。</span><span class="sxs-lookup"><span data-stu-id="052d3-190">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="052d3-191">在 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="052d3-191">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="052d3-192">使用你的凭据登录[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="052d3-192">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="052d3-193">在管理中心中，转到 "**设置** > **安全 & 隐私** > "**特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="052d3-193">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="052d3-194">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="052d3-194">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="052d3-195">选择 "**查看**" 以按**待定**、**批准**、**拒绝**或**客户密码箱**状态筛选提交的请求。</span><span class="sxs-lookup"><span data-stu-id="052d3-195">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="052d3-196">在 Exchange 管理 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="052d3-196">In Exchange Management PowerShell</span></span>

<span data-ttu-id="052d3-197">在 Exchange Online PowerShell 中运行以下命令，以查看特定请求 ID 的审批请求状态：</span><span class="sxs-lookup"><span data-stu-id="052d3-197">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="052d3-198">示例：</span><span class="sxs-lookup"><span data-stu-id="052d3-198">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="052d3-199">批准提升授权请求</span><span class="sxs-lookup"><span data-stu-id="052d3-199">Approving an elevation authorization request</span></span>

<span data-ttu-id="052d3-200">在创建审批请求时，相关审批者组的成员会收到电子邮件通知，并且可以批准与请求 ID 关联的请求。</span><span class="sxs-lookup"><span data-stu-id="052d3-200">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="052d3-201">请求者会收到请求审批或通过电子邮件的拒绝通知请求者。</span><span class="sxs-lookup"><span data-stu-id="052d3-201">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="052d3-202">在 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="052d3-202">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="052d3-203">使用你的凭据登录[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="052d3-203">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="052d3-204">在管理中心中，转到 "**设置** > **安全 & 隐私** > "**特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="052d3-204">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="052d3-205">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="052d3-205">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="052d3-206">选择一个列出的请求以查看详细信息，并对请求执行操作。</span><span class="sxs-lookup"><span data-stu-id="052d3-206">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="052d3-207">选择 "**批准**" 以批准请求，或选择 "**拒绝**" 以拒绝该请求。</span><span class="sxs-lookup"><span data-stu-id="052d3-207">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="052d3-208">以前批准的请求可以通过选择 "**吊销**" 来撤销访问权限。</span><span class="sxs-lookup"><span data-stu-id="052d3-208">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="052d3-209">在 Exchange 管理 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="052d3-209">In Exchange Management PowerShell</span></span>

<span data-ttu-id="052d3-210">若要批准提升授权请求，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="052d3-210">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="052d3-211">示例：</span><span class="sxs-lookup"><span data-stu-id="052d3-211">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="052d3-212">若要拒绝提升授权请求，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="052d3-212">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="052d3-213">示例：</span><span class="sxs-lookup"><span data-stu-id="052d3-213">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="052d3-214">删除 Office 365 中的特权访问策略</span><span class="sxs-lookup"><span data-stu-id="052d3-214">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="052d3-215">如果您的组织不再需要它，则可以删除特权访问策略。</span><span class="sxs-lookup"><span data-stu-id="052d3-215">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="052d3-216">在 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="052d3-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="052d3-217">使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="052d3-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="052d3-218">在管理中心中，转到 "**设置** > **安全 & 隐私** > "**特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="052d3-218">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="052d3-219">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="052d3-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="052d3-220">选择 "**配置策略**"。</span><span class="sxs-lookup"><span data-stu-id="052d3-220">Select **Configure policies**.</span></span>

5. <span data-ttu-id="052d3-221">选择要删除的策略，然后选择 "**删除策略**"。</span><span class="sxs-lookup"><span data-stu-id="052d3-221">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="052d3-222">选择“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="052d3-222">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="052d3-223">在 Exchange 管理 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="052d3-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="052d3-224">若要删除特权访问策略，请在 Exchange Online Powershell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="052d3-224">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="052d3-225">禁用 Office 365 中的特权访问</span><span class="sxs-lookup"><span data-stu-id="052d3-225">Disable privileged access in Office 365</span></span>

<span data-ttu-id="052d3-226">如果需要，您可以为您的组织禁用特权访问管理。</span><span class="sxs-lookup"><span data-stu-id="052d3-226">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="052d3-227">禁用特权访问不会删除任何关联的审批策略或审批者组。</span><span class="sxs-lookup"><span data-stu-id="052d3-227">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="052d3-228">在 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="052d3-228">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="052d3-229">使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="052d3-229">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="052d3-230">在管理中心中，转到 "**设置** > **安全 & 隐私** > "**特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="052d3-230">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="052d3-231">启用 "**需要批准以进行特权访问**控制"。</span><span class="sxs-lookup"><span data-stu-id="052d3-231">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="052d3-232">在 Exchange 管理 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="052d3-232">In Exchange Management PowerShell</span></span>

<span data-ttu-id="052d3-233">若要禁用特权访问，请在 Exchange Online Powershell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="052d3-233">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
