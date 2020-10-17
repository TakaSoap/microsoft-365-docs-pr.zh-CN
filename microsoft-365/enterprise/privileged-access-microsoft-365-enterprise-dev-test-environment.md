---
title: 适用于企业测试环境的 Microsoft 365 的特权访问管理
f1.keywords:
- NOCSH
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
description: 使用此测试实验室指南可为 Microsoft 365 企业版测试环境启用特权访问管理。
ms.openlocfilehash: 24ca7a6408a4290c54dd2bcd7c3f6061eb8f6c05
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487584"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="00b68-103">适用于企业测试环境的 Microsoft 365 的特权访问管理</span><span class="sxs-lookup"><span data-stu-id="00b68-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="00b68-104">*此测试实验室指南可用于适用于企业和 Office 365 企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="00b68-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="00b68-105">本文介绍如何配置特权访问管理以提高 Microsoft 365 企业版测试环境中的安全性。</span><span class="sxs-lookup"><span data-stu-id="00b68-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="00b68-106">配置 priviledged 访问管理涉及三个阶段：</span><span class="sxs-lookup"><span data-stu-id="00b68-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="00b68-107">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="00b68-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="00b68-108">阶段2：配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="00b68-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="00b68-109">第3阶段：验证提升权限和特权任务是否都需要审批</span><span class="sxs-lookup"><span data-stu-id="00b68-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="00b68-111">若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="00b68-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="00b68-112">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="00b68-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="00b68-113">如果要使用最低要求以轻型方式配置特权访问管理，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="00b68-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="00b68-114">如果要在模拟的企业中配置特权访问管理，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="00b68-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="00b68-115">测试特权访问管理不需要模拟企业测试环境，其中包括连接到 internet 的模拟 intranet 和 Active Directory 域服务林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="00b68-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="00b68-116">它作为选项提供，以便您可以测试特权访问管理，并在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="00b68-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="00b68-117">阶段2：配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="00b68-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="00b68-118">在这一阶段，为 Microsoft 365 配置 "审批者" 组并启用适用于企业测试环境的 "特权访问管理"。</span><span class="sxs-lookup"><span data-stu-id="00b68-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="00b68-119">有关其他详细信息和权限访问管理的概述，请参阅 [特权访问管理](../compliance/privileged-access-management-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="00b68-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="00b68-120">若要设置和使用组织中的特权访问，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="00b68-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="00b68-121">步骤1：创建审批者的组</span><span class="sxs-lookup"><span data-stu-id="00b68-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="00b68-122">在开始使用特权访问之前，请确定谁将拥有对已提升和特权任务的传入请求的审批权限。</span><span class="sxs-lookup"><span data-stu-id="00b68-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="00b68-123">作为审批者组一部分的所有用户都可以批准访问请求。</span><span class="sxs-lookup"><span data-stu-id="00b68-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="00b68-124">若要使用特权访问，必须在 Microsoft 365 中创建启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="00b68-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="00b68-125">在您的测试环境中，将新安全组命名为 "特权访问审批者"，并添加先前在之前的测试实验室指南中的步骤中创建的 "用户 3"。</span><span class="sxs-lookup"><span data-stu-id="00b68-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="00b68-126">步骤2：启用特权访问</span><span class="sxs-lookup"><span data-stu-id="00b68-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="00b68-127">需要在 Microsoft 365 中显式打开具有默认审批者组的特权访问权限，并且必须包含要从特权访问管理访问控制中排除的一组系统帐户。</span><span class="sxs-lookup"><span data-stu-id="00b68-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="00b68-128">在开始本指南的第3阶段之前，请务必在你的组织中启用访问权限。</span><span class="sxs-lookup"><span data-stu-id="00b68-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="00b68-129">第3阶段：验证提升权限和特权任务是否都需要审批</span><span class="sxs-lookup"><span data-stu-id="00b68-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="00b68-130">在此阶段中，验证特权访问策略是否正常运行，以及用户是否需要批准以执行定义的提升和特权任务。</span><span class="sxs-lookup"><span data-stu-id="00b68-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="00b68-131">测试执行未在特权访问策略中定义的任务的能力</span><span class="sxs-lookup"><span data-stu-id="00b68-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="00b68-132">首先，使用在测试环境中配置为全局管理员的用户的凭据连接到 Exchange 管理 PowerShell，并尝试创建新的日记规则。</span><span class="sxs-lookup"><span data-stu-id="00b68-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="00b68-133">尚未在组织的特权访问策略中定义 [新的-new-journalrule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) 任务。</span><span class="sxs-lookup"><span data-stu-id="00b68-133">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="00b68-134">在您的本地计算机上， **Microsoft Corporation**  >  使用您的测试环境的全局管理员帐户在 microsoft Corporation**microsoft Exchange online 远程 powershell 模块**中打开并登录到 Exchange online 远程 powershell 模块。</span><span class="sxs-lookup"><span data-stu-id="00b68-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="00b68-135">在 Exchange 管理 PowerShell 中，为您的组织创建新的日记规则：</span><span class="sxs-lookup"><span data-stu-id="00b68-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="00b68-136">查看在 Exchange 管理 PowerShell 中已成功创建新日记规则。</span><span class="sxs-lookup"><span data-stu-id="00b68-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="00b68-137">为 New-JournalRule 任务创建新的特权访问策略</span><span class="sxs-lookup"><span data-stu-id="00b68-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="00b68-138">如果您尚未从本指南的第2阶段完成步骤1和步骤2，请务必按照创建名为 "权限访问审批者" 的审批者组中的步骤，在测试环境中启用权限访问。</span><span class="sxs-lookup"><span data-stu-id="00b68-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="00b68-139">使用凭据登录到 [Microsoft 365 管理中心](https://admin.microsoft.com) 您的测试环境的全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="00b68-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="00b68-140">在管理中心中，转到 "**设置**  >  **安全 & 隐私**"  >  **特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="00b68-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="00b68-141">选择 " **管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="00b68-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="00b68-142">选择 " **配置策略**"，然后选择 " **添加策略**"。</span><span class="sxs-lookup"><span data-stu-id="00b68-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="00b68-143">从下拉字段中，选择或输入以下值：</span><span class="sxs-lookup"><span data-stu-id="00b68-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="00b68-144">**策略类型**：任务</span><span class="sxs-lookup"><span data-stu-id="00b68-144">**Policy type**: Task</span></span>

    <span data-ttu-id="00b68-145">**策略作用域**： Exchange</span><span class="sxs-lookup"><span data-stu-id="00b68-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="00b68-146">**策略名称**：新日记规则</span><span class="sxs-lookup"><span data-stu-id="00b68-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="00b68-147">**审批类型**：手动</span><span class="sxs-lookup"><span data-stu-id="00b68-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="00b68-148">**审批组**：特权访问审批者</span><span class="sxs-lookup"><span data-stu-id="00b68-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="00b68-149">选择 " **创建**"，然后选择 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="00b68-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="00b68-150">为策略完全配置和启用可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="00b68-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="00b68-151">在测试下一步中的审批要求之前，请务必为策略完全启用时间。</span><span class="sxs-lookup"><span data-stu-id="00b68-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="00b68-152">在特权访问策略中定义的 New-JournalRule 任务的测试批准要求</span><span class="sxs-lookup"><span data-stu-id="00b68-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="00b68-153">在您的本地计算机上，在**microsoft Corporation**  >  **microsoft Exchange online powershell 模块**中打开并登录到 exchange online 远程 powershell 模块，使用您的测试环境的全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="00b68-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="00b68-154">在 Exchange 管理 PowerShell 中，为您的组织创建新的日记规则：</span><span class="sxs-lookup"><span data-stu-id="00b68-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="00b68-155">在 Exchange 管理 PowerShell 中查看 "权限不足" 错误：</span><span class="sxs-lookup"><span data-stu-id="00b68-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="00b68-156">请求访问权限以使用 New-JournalRule 任务创建新的日记规则</span><span class="sxs-lookup"><span data-stu-id="00b68-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="00b68-157">使用您的测试环境的全局管理员帐户登录到 [Microsoft 365 管理中心](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="00b68-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="00b68-158">在管理中心中，转到 "**设置**  >  **安全 & 隐私**"  >  **特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="00b68-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="00b68-159">选择 " **管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="00b68-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="00b68-160">选择 " **新建请求**"。</span><span class="sxs-lookup"><span data-stu-id="00b68-160">Select **New request**.</span></span> <span data-ttu-id="00b68-161">从下拉字段中，为您的组织选择适当的值：</span><span class="sxs-lookup"><span data-stu-id="00b68-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="00b68-162">**请求类型**：任务</span><span class="sxs-lookup"><span data-stu-id="00b68-162">**Request type**: Task</span></span>

    <span data-ttu-id="00b68-163">**请求范围**： Exchange</span><span class="sxs-lookup"><span data-stu-id="00b68-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="00b68-164">**请求**：新日记规则</span><span class="sxs-lookup"><span data-stu-id="00b68-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="00b68-165">\*\*持续时间 (小时) \*\*：2</span><span class="sxs-lookup"><span data-stu-id="00b68-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="00b68-166">**注释**：请求创建新日记规则的权限</span><span class="sxs-lookup"><span data-stu-id="00b68-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="00b68-167">选择 " **保存**"，然后选择 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="00b68-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="00b68-168">您的请求将通过电子邮件发送给审批者的组。</span><span class="sxs-lookup"><span data-stu-id="00b68-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="00b68-169">批准创建新日记规则的特权访问请求</span><span class="sxs-lookup"><span data-stu-id="00b68-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="00b68-170">使用测试环境中用户3的凭据登录到 [Microsoft 365 管理中心](https://admin.microsoft.com) ， (测试环境中 "特权访问审批者" 安全组的成员) 。</span><span class="sxs-lookup"><span data-stu-id="00b68-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="00b68-171">在管理中心中，转到 "**设置**  >  **安全 & 隐私**"  >  **特权访问权限**。</span><span class="sxs-lookup"><span data-stu-id="00b68-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="00b68-172">选择 " **管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="00b68-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="00b68-173">选择 "挂起的请求"，然后选择 " **批准** " 以授予对全局管理员帐户的访问权限，以创建新的日记规则。</span><span class="sxs-lookup"><span data-stu-id="00b68-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="00b68-174"> (请求用户) 的全局管理员帐户将收到已授予审批的电子邮件确认。</span><span class="sxs-lookup"><span data-stu-id="00b68-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="00b68-175">测试创建新的日记规则，并为 New-JournalRule 任务批准权限访问</span><span class="sxs-lookup"><span data-stu-id="00b68-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="00b68-176">在您的本地计算机上， **Microsoft Corporation**  >  使用您的测试环境的全局管理员帐户在 microsoft Corporation**microsoft Exchange online 远程 powershell 模块**中打开并登录到 Exchange online 远程 powershell 模块。</span><span class="sxs-lookup"><span data-stu-id="00b68-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="00b68-177">在 Exchange 管理 PowerShell 中，为您的组织创建新的日记规则：</span><span class="sxs-lookup"><span data-stu-id="00b68-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="00b68-178">查看在 Exchange 管理 PowerShell 中已成功创建新日记规则。</span><span class="sxs-lookup"><span data-stu-id="00b68-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="00b68-179">后续步骤</span><span class="sxs-lookup"><span data-stu-id="00b68-179">Next step</span></span>

<span data-ttu-id="00b68-180">在您的测试环境中浏览其他 [信息保护](m365-enterprise-test-lab-guides.md#information-protection) 特性和功能。</span><span class="sxs-lookup"><span data-stu-id="00b68-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="00b68-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00b68-181">See also</span></span>

[<span data-ttu-id="00b68-182">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="00b68-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="00b68-183">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="00b68-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="00b68-184">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="00b68-184">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
