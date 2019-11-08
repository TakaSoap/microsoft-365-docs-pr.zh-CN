---
title: 用于 Microsoft 365 企业版测试环境的 Privileged Access Management
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: 使用此测试实验室指南可启用 Microsoft 365 企业版测试环境的特权访问管理。
ms.openlocfilehash: f701f3f8f74036966de2c516d662ef77341f4842
ms.sourcegitcommit: b424ea039c5915975f3efce8793bfc8dd2fdf906
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "38033607"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="121e9-103">用于 Microsoft 365 企业版测试环境的 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="121e9-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="121e9-104">使用本文中的说明，可以配置特权访问管理以提高 Microsoft 365 企业版测试环境中的安全性。</span><span class="sxs-lookup"><span data-stu-id="121e9-104">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="121e9-106">单击[此处](https://aka.ms/m365etlgstack)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="121e9-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="121e9-107">阶段 1：构建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="121e9-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="121e9-108">如果只想使用最低要求以轻型方式配置特权访问管理，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="121e9-108">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="121e9-109">如果要在模拟的企业中配置特权访问管理，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="121e9-109">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="121e9-110">测试特权访问管理不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 AD DS 林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="121e9-110">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="121e9-111">此处提供它作为选项，以便您可以测试特权访问管理并在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="121e9-111">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="121e9-112">阶段2：配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="121e9-112">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="121e9-113">在此阶段中，您将为 Microsoft 365 企业版测试环境配置 "审批者" 组并启用 "特权访问管理"。</span><span class="sxs-lookup"><span data-stu-id="121e9-113">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="121e9-114">有关其他详细信息和权限访问管理的概述，请参阅[Office 365 中的 "特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)"。</span><span class="sxs-lookup"><span data-stu-id="121e9-114">For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="121e9-115">按照以下步骤设置和使用 Office 365 组织中的特权访问：</span><span class="sxs-lookup"><span data-stu-id="121e9-115">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="121e9-116">步骤1：创建审批者的组</span><span class="sxs-lookup"><span data-stu-id="121e9-116">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    <span data-ttu-id="121e9-117">在开始使用权限访问之前，请确定谁将拥有对已提升和特权任务的传入请求的审批权限。</span><span class="sxs-lookup"><span data-stu-id="121e9-117">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="121e9-118">作为审批者组的一部分的任何用户都将能够批准访问请求。</span><span class="sxs-lookup"><span data-stu-id="121e9-118">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="121e9-119">这是通过在 Office 365 中创建启用邮件的安全组来启用的。</span><span class="sxs-lookup"><span data-stu-id="121e9-119">This is enabled by creating a mail-enabled security group in Office 365.</span></span> <span data-ttu-id="121e9-120">在测试环境中创建一个名为 "特权访问审批者" 的新安全组，并添加先前在之前的测试实验室指南步骤中创建的 "用户 3"。</span><span class="sxs-lookup"><span data-stu-id="121e9-120">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="121e9-121">步骤2：启用特权访问</span><span class="sxs-lookup"><span data-stu-id="121e9-121">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    <span data-ttu-id="121e9-122">需要在 Office 365 中显式打开具有默认审批者组的特权访问权限，并包含要从特权访问管理访问控制中排除的一组系统帐户。</span><span class="sxs-lookup"><span data-stu-id="121e9-122">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="121e9-123">在开始本指南的第3阶段之前，请务必在 Office 365 组织中启用特权访问。</span><span class="sxs-lookup"><span data-stu-id="121e9-123">Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="121e9-124">第3阶段：验证提升权限和特权任务是否都需要审批</span><span class="sxs-lookup"><span data-stu-id="121e9-124">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="121e9-125">在此阶段中，您将验证特权访问策略是否正常工作，以及用户是否需要批准以执行定义的提升和特权任务。</span><span class="sxs-lookup"><span data-stu-id="121e9-125">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="121e9-126">测试执行未在特权访问策略中定义的任务的能力</span><span class="sxs-lookup"><span data-stu-id="121e9-126">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="121e9-127">首先，使用在测试环境中配置为全局管理员的用户的凭据连接到 Exchange 管理 PowerShell，并尝试创建新的日记规则。</span><span class="sxs-lookup"><span data-stu-id="121e9-127">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="121e9-128">尚未在组织的特权访问策略中定义[新的-new-journalrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps)任务。</span><span class="sxs-lookup"><span data-stu-id="121e9-128">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="121e9-129">在本地计算机上，使用您的测试环境的全局管理员帐户在**microsoft Corporation** > **microsoft Exchange online 远程 powershell 模块**中打开并登录到 Exchange online 远程 powershell 模块。</span><span class="sxs-lookup"><span data-stu-id="121e9-129">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="121e9-130">在 Exchange 管理 Powershell 中，为您的组织创建新的日记规则：</span><span class="sxs-lookup"><span data-stu-id="121e9-130">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="121e9-131">查看在 Exchange 管理 PowerShell 中已成功创建新日记规则。</span><span class="sxs-lookup"><span data-stu-id="121e9-131">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="121e9-132">为新的-New-journalrule 任务创建新的特权访问策略</span><span class="sxs-lookup"><span data-stu-id="121e9-132">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="121e9-133">如果您尚未从本指南的第2阶段完成步骤1和步骤2，请确保按照步骤创建名为 "权限访问审批者" 的审批者组，并在您的测试环境中启用特权访问。</span><span class="sxs-lookup"><span data-stu-id="121e9-133">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="121e9-134">使用凭据登录到[Microsoft 365 管理中心](https://admin.microsoft.com)您的测试环境的全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="121e9-134">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="121e9-135">在管理中心中，转到 "**设置** > **安全 & 隐私** > "**特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="121e9-135">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="121e9-136">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="121e9-136">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="121e9-137">选择 "**配置策略**"，然后选择 "**添加策略**"。</span><span class="sxs-lookup"><span data-stu-id="121e9-137">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="121e9-138">从下拉字段中，选择或输入以下值：</span><span class="sxs-lookup"><span data-stu-id="121e9-138">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="121e9-139">**策略类型**：任务</span><span class="sxs-lookup"><span data-stu-id="121e9-139">**Policy type**: Task</span></span>

    <span data-ttu-id="121e9-140">**策略作用域**： Exchange</span><span class="sxs-lookup"><span data-stu-id="121e9-140">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="121e9-141">**策略名称**：新日记规则</span><span class="sxs-lookup"><span data-stu-id="121e9-141">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="121e9-142">**审批类型**：手动</span><span class="sxs-lookup"><span data-stu-id="121e9-142">**Approval type**: Manual</span></span>

    <span data-ttu-id="121e9-143">**审批组**：特权访问审批者</span><span class="sxs-lookup"><span data-stu-id="121e9-143">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="121e9-144">选择 "**创建**"，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="121e9-144">Select **Create** and then **Close**.</span></span> <span data-ttu-id="121e9-145">为策略完全配置和启用可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="121e9-145">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="121e9-146">在测试下一步中的审批要求之前，请务必为策略完全启用时间。</span><span class="sxs-lookup"><span data-stu-id="121e9-146">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="121e9-147">在特权访问策略中定义的 New-journalrule 任务的测试批准要求</span><span class="sxs-lookup"><span data-stu-id="121e9-147">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="121e9-148">在您的本地计算机上，在**microsoft Corporation** > **microsoft Exchange online powershell 模块**中打开并登录到 exchange online 远程 powershell 模块，使用您的测试环境的全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="121e9-148">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="121e9-149">在 Exchange 管理 Powershell 中，为您的组织创建新的日记规则：</span><span class="sxs-lookup"><span data-stu-id="121e9-149">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="121e9-150">在 Exchange 管理 PowerShell 中查看 "Insuffient 权限" 错误：</span><span class="sxs-lookup"><span data-stu-id="121e9-150">View "Insuffient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="121e9-151">请求访问权限以使用 New-journalrule 任务创建新的日记规则</span><span class="sxs-lookup"><span data-stu-id="121e9-151">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="121e9-152">使用您的测试环境的全局管理员帐户登录[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="121e9-152">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="121e9-153">在管理中心中，转到 "**设置** > **安全 & 隐私** > "**特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="121e9-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="121e9-154">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="121e9-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="121e9-155">选择 "**新建请求**"。</span><span class="sxs-lookup"><span data-stu-id="121e9-155">Select **New request**.</span></span> <span data-ttu-id="121e9-156">从下拉字段中，为您的组织选择适当的值：</span><span class="sxs-lookup"><span data-stu-id="121e9-156">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="121e9-157">**请求类型**：任务</span><span class="sxs-lookup"><span data-stu-id="121e9-157">**Request type**: Task</span></span>

    <span data-ttu-id="121e9-158">**请求范围**： Exchange</span><span class="sxs-lookup"><span data-stu-id="121e9-158">**Request scope**: Exchange</span></span>

    <span data-ttu-id="121e9-159">**请求**：新日记规则</span><span class="sxs-lookup"><span data-stu-id="121e9-159">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="121e9-160">**持续时间（小时）**：2</span><span class="sxs-lookup"><span data-stu-id="121e9-160">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="121e9-161">**注释**：请求创建新日记规则的权限</span><span class="sxs-lookup"><span data-stu-id="121e9-161">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="121e9-162">依次选择 "**保存**" 和 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="121e9-162">Select **Save** and then **Close**.</span></span> <span data-ttu-id="121e9-163">您的请求将通过电子邮件发送给审批者的组。</span><span class="sxs-lookup"><span data-stu-id="121e9-163">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="121e9-164">批准创建新日记规则的特权访问请求</span><span class="sxs-lookup"><span data-stu-id="121e9-164">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="121e9-165">使用测试环境中用户3的凭据登录到[Microsoft 365 管理中心](https://admin.microsoft.com)（测试环境中的 "特权访问审批者" 安全组的成员）。</span><span class="sxs-lookup"><span data-stu-id="121e9-165">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="121e9-166">在管理中心中，转到 "**设置** > **安全 & 隐私** > "**特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="121e9-166">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="121e9-167">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="121e9-167">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="121e9-168">选择 "挂起的请求"，然后选择 "**批准**" 以授予对全局管理员帐户的访问权限，以创建新的日记规则。</span><span class="sxs-lookup"><span data-stu-id="121e9-168">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="121e9-169">将向全局管理员帐户（发出请求的用户）发送确认已授予审批的通知电子邮件。</span><span class="sxs-lookup"><span data-stu-id="121e9-169">An notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="121e9-170">测试创建新的日记规则，该规则具有针对 New-journalrule 任务审批的特权访问权限</span><span class="sxs-lookup"><span data-stu-id="121e9-170">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="121e9-171">在本地计算机上，使用您的测试环境的全局管理员帐户在**microsoft Corporation** > **microsoft Exchange online 远程 powershell 模块**中打开并登录到 Exchange online 远程 powershell 模块。</span><span class="sxs-lookup"><span data-stu-id="121e9-171">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="121e9-172">在 Exchange 管理 Powershell 中，为您的组织创建新的日记规则：</span><span class="sxs-lookup"><span data-stu-id="121e9-172">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="121e9-173">查看在 Exchange 管理 PowerShell 中已成功创建新日记规则。</span><span class="sxs-lookup"><span data-stu-id="121e9-173">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="121e9-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="121e9-174">Next step</span></span>

<span data-ttu-id="121e9-175">在您的测试环境中浏览其他[信息保护](m365-enterprise-test-lab-guides.md#information-protection)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="121e9-175">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="121e9-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="121e9-176">See also</span></span>

[<span data-ttu-id="121e9-177">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="121e9-177">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="121e9-178">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="121e9-178">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="121e9-179">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="121e9-179">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)