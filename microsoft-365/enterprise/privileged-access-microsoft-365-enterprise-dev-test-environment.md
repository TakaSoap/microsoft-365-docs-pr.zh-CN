---
title: 适用于企业测试环境Microsoft 365特权访问管理
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
description: 使用此测试实验室指南为企业测试环境启用Microsoft 365访问管理。
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126413"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="fdfef-103">适用于企业测试环境Microsoft 365特权访问管理</span><span class="sxs-lookup"><span data-stu-id="fdfef-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="fdfef-104">*本测试实验室指南可用于企业Microsoft 365和Office 365 企业版环境。*</span><span class="sxs-lookup"><span data-stu-id="fdfef-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="fdfef-105">本文介绍如何配置特权访问管理以提高企业测试Microsoft 365的安全性。</span><span class="sxs-lookup"><span data-stu-id="fdfef-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="fdfef-106">配置特权访问管理包括三个阶段：</span><span class="sxs-lookup"><span data-stu-id="fdfef-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="fdfef-107">第 1 阶段：构建Microsoft 365测试环境</span><span class="sxs-lookup"><span data-stu-id="fdfef-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="fdfef-108">阶段 2：配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="fdfef-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="fdfef-109">阶段 3：验证提升和特权任务需要审批</span><span class="sxs-lookup"><span data-stu-id="fdfef-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="fdfef-111">有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365[企业测试实验室指南堆栈](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="fdfef-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="fdfef-112">第 1 阶段：构建Microsoft 365测试环境</span><span class="sxs-lookup"><span data-stu-id="fdfef-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="fdfef-113">如果要使用最低要求的轻型方式配置特权访问管理，请按照轻型基本配置 [中的说明操作](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="fdfef-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="fdfef-114">如果要在模拟企业中配置特权访问管理，请按照传递身份验证 [中的说明操作](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="fdfef-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="fdfef-115">测试特权访问管理不需要模拟的企业测试环境，该环境中包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="fdfef-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="fdfef-116">它在此处作为一个选项提供，以便你可以测试特权访问管理，在代表典型组织的环境中试验它。</span><span class="sxs-lookup"><span data-stu-id="fdfef-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="fdfef-117">阶段 2：配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="fdfef-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="fdfef-118">在此阶段，配置审批者组，并针对企业测试Microsoft 365启用特权访问管理。</span><span class="sxs-lookup"><span data-stu-id="fdfef-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="fdfef-119">有关其他详细信息和特权访问管理的概述，请参阅 [特权访问管理](../compliance/privileged-access-management-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="fdfef-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="fdfef-120">若要在组织中设置和使用特权访问，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="fdfef-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="fdfef-121">步骤 1：创建审批者组</span><span class="sxs-lookup"><span data-stu-id="fdfef-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="fdfef-122">开始使用特权访问之前，请确定谁将拥有对访问提升和特权任务的传入请求的审批权限。</span><span class="sxs-lookup"><span data-stu-id="fdfef-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="fdfef-123">属于审批者组的所有用户都可以批准访问请求。</span><span class="sxs-lookup"><span data-stu-id="fdfef-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="fdfef-124">若要使用特权访问，必须在安全邮箱中创建启用邮件Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="fdfef-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="fdfef-125">在测试环境中，将新安全组命名为"Privileged Access Approvers"，并添加先前在之前的测试实验室指南步骤中创建的"User 3"。</span><span class="sxs-lookup"><span data-stu-id="fdfef-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="fdfef-126">步骤 2：启用特权访问</span><span class="sxs-lookup"><span data-stu-id="fdfef-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="fdfef-127">需要在具有默认审批者组的 Microsoft 365 中显式启用特权访问，并且它必须包含一组您希望从特权访问管理访问控制中排除的系统帐户。</span><span class="sxs-lookup"><span data-stu-id="fdfef-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="fdfef-128">在启动本指南的第 3 阶段之前，请确保在组织中启用特权访问。</span><span class="sxs-lookup"><span data-stu-id="fdfef-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="fdfef-129">阶段 3：验证提升和特权任务需要审批</span><span class="sxs-lookup"><span data-stu-id="fdfef-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="fdfef-130">在此阶段中，验证特权访问策略是否正常工作，以及用户是否需要批准，以执行已定义的提升特权任务。</span><span class="sxs-lookup"><span data-stu-id="fdfef-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="fdfef-131">测试执行特权访问策略中未定义的任务的能力</span><span class="sxs-lookup"><span data-stu-id="fdfef-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="fdfef-132">首先，使用Exchange环境中配置为全局管理员的用户凭据连接到 Management PowerShell，并尝试创建新的日记规则。</span><span class="sxs-lookup"><span data-stu-id="fdfef-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="fdfef-133">[New-JournalRule](/powershell/module/exchange/new-journalrule)任务当前未在组织的特权访问策略中定义。</span><span class="sxs-lookup"><span data-stu-id="fdfef-133">The [New-JournalRule](/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="fdfef-134">在本地计算机上，使用测试环境的全局管理员帐户打开并Exchange Online **Microsoft Corporation** Microsoft Exchange Online 远程 PowerShell 模块的远程  >  **PowerShell** 模块。</span><span class="sxs-lookup"><span data-stu-id="fdfef-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="fdfef-135">在 Exchange Management PowerShell 中，为组织创建新的日记规则：</span><span class="sxs-lookup"><span data-stu-id="fdfef-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="fdfef-136">查看新日记规则已成功在 Exchange PowerShell 中创建。</span><span class="sxs-lookup"><span data-stu-id="fdfef-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="fdfef-137">为任务创建新的特权访问New-JournalRule策略</span><span class="sxs-lookup"><span data-stu-id="fdfef-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="fdfef-138">如果尚未完成本指南阶段 2 中的步骤 1 和步骤 2，请确保按照步骤创建名为"Privilege Access Approvers"的审批者组，以在测试环境中启用特权访问。</span><span class="sxs-lookup"><span data-stu-id="fdfef-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="fdfef-139">使用适用于测试[Microsoft 365](https://admin.microsoft.com)全局管理员帐户的凭据登录到管理中心。</span><span class="sxs-lookup"><span data-stu-id="fdfef-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="fdfef-140">In the Admin Center， go to **设置**  >  **Security & Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="fdfef-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="fdfef-141">选择 **"管理访问策略和请求"。**</span><span class="sxs-lookup"><span data-stu-id="fdfef-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="fdfef-142">选择 **"配置策略**"，然后选择"**添加策略"。**</span><span class="sxs-lookup"><span data-stu-id="fdfef-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="fdfef-143">从下拉列表字段中，选择或输入以下值：</span><span class="sxs-lookup"><span data-stu-id="fdfef-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="fdfef-144">**策略类型**：任务</span><span class="sxs-lookup"><span data-stu-id="fdfef-144">**Policy type**: Task</span></span>

    <span data-ttu-id="fdfef-145">**策略范围**: Exchange</span><span class="sxs-lookup"><span data-stu-id="fdfef-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="fdfef-146">**策略名称**：新建日记规则</span><span class="sxs-lookup"><span data-stu-id="fdfef-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="fdfef-147">**审批类型**：手动</span><span class="sxs-lookup"><span data-stu-id="fdfef-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="fdfef-148">**审批组**：特权访问审批者</span><span class="sxs-lookup"><span data-stu-id="fdfef-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="fdfef-149">选择“**创建**”，然后选择“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="fdfef-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="fdfef-150">可能需要几分钟时间，策略才能完全配置和启用。</span><span class="sxs-lookup"><span data-stu-id="fdfef-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="fdfef-151">在测试下一步中的审批要求之前，请确保留出时间使策略完全启用。</span><span class="sxs-lookup"><span data-stu-id="fdfef-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="fdfef-152">特权访问策略中定义的New-JournalRule任务的测试审批要求</span><span class="sxs-lookup"><span data-stu-id="fdfef-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="fdfef-153">在本地计算机上，使用测试环境的全局管理员帐户打开并Exchange Online **Microsoft Corporation** Microsoft Exchange Online 远程 PowerShell 模块的远程  >  **PowerShell** 模块。</span><span class="sxs-lookup"><span data-stu-id="fdfef-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="fdfef-154">在 Exchange Management PowerShell 中，为组织创建新的日记规则：</span><span class="sxs-lookup"><span data-stu-id="fdfef-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="fdfef-155">在 Management PowerShell 中查看Exchange权限不足"错误：</span><span class="sxs-lookup"><span data-stu-id="fdfef-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="fdfef-156">请求访问权限以使用"日记"任务创建新的日记New-JournalRule规则</span><span class="sxs-lookup"><span data-stu-id="fdfef-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="fdfef-157">使用测试[Microsoft 365](https://admin.microsoft.com)全局管理员帐户登录到管理中心。</span><span class="sxs-lookup"><span data-stu-id="fdfef-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="fdfef-158">In the Admin Center， go to **设置**  >  **Security & Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="fdfef-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="fdfef-159">选择 **"管理访问策略和请求"。**</span><span class="sxs-lookup"><span data-stu-id="fdfef-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="fdfef-160">选择 **"新建请求"。**</span><span class="sxs-lookup"><span data-stu-id="fdfef-160">Select **New request**.</span></span> <span data-ttu-id="fdfef-161">从下拉字段中，为组织选择适当的值：</span><span class="sxs-lookup"><span data-stu-id="fdfef-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="fdfef-162">**请求类型**： 任务</span><span class="sxs-lookup"><span data-stu-id="fdfef-162">**Request type**: Task</span></span>

    <span data-ttu-id="fdfef-163">**请求范围**: Exchange</span><span class="sxs-lookup"><span data-stu-id="fdfef-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="fdfef-164">**请求：** 新建日记规则</span><span class="sxs-lookup"><span data-stu-id="fdfef-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="fdfef-165">**持续时间 (小时) ：** 2</span><span class="sxs-lookup"><span data-stu-id="fdfef-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="fdfef-166">**注释：** 请求创建新日记规则的权限</span><span class="sxs-lookup"><span data-stu-id="fdfef-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="fdfef-167">选择 **"保存"，** 然后选择"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="fdfef-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="fdfef-168">您的请求将通过电子邮件发送到审批者组。</span><span class="sxs-lookup"><span data-stu-id="fdfef-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="fdfef-169">批准新建日记规则的特权访问请求</span><span class="sxs-lookup"><span data-stu-id="fdfef-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="fdfef-170">使用测试[Microsoft 365](https://admin.microsoft.com)环境中用户 3 的凭据登录 (测试环境中"特权访问审批者"安全组的成员) 。</span><span class="sxs-lookup"><span data-stu-id="fdfef-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="fdfef-171">In the Admin Center， go to **设置**  >  **Security & Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="fdfef-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="fdfef-172">选择 **"管理访问策略和请求"。**</span><span class="sxs-lookup"><span data-stu-id="fdfef-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="fdfef-173">选择挂起的请求，然后选择" **批准** "以授予对全局管理员帐户的访问权限以创建新的日记规则。</span><span class="sxs-lookup"><span data-stu-id="fdfef-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="fdfef-174">请求用户 (全局管理员帐户) 将收到一封电子邮件确认，确认已授予批准。</span><span class="sxs-lookup"><span data-stu-id="fdfef-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="fdfef-175">测试创建新的日记规则，该规则具有已批准用于该任务的特权New-JournalRule规则</span><span class="sxs-lookup"><span data-stu-id="fdfef-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="fdfef-176">在本地计算机上，使用测试环境的全局管理员帐户打开并Exchange Online **Microsoft Corporation** Microsoft Exchange Online 远程 PowerShell 模块的远程  >  **PowerShell** 模块。</span><span class="sxs-lookup"><span data-stu-id="fdfef-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="fdfef-177">在 Exchange Management PowerShell 中，为组织创建新的日记规则：</span><span class="sxs-lookup"><span data-stu-id="fdfef-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="fdfef-178">查看新日记规则已成功在 Exchange PowerShell 中创建。</span><span class="sxs-lookup"><span data-stu-id="fdfef-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="fdfef-179">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fdfef-179">Next step</span></span>

<span data-ttu-id="fdfef-180">探索 [测试环境中](m365-enterprise-test-lab-guides.md#information-protection) 的其他信息保护特性和功能。</span><span class="sxs-lookup"><span data-stu-id="fdfef-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="fdfef-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdfef-181">See also</span></span>

[<span data-ttu-id="fdfef-182">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="fdfef-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="fdfef-183">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="fdfef-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="fdfef-184">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="fdfef-184">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
