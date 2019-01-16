---
title: 用于 Microsoft 365 企业版测试环境的 Privileged Access Management
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 09/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
description: 使用此测试实验室指南启用特权的访问管理 Microsoft 365 企业版测试环境。
ms.openlocfilehash: 5f1a416a12171504af110ec62b9a7882143263e6
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865407"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f44a9-103">用于 Microsoft 365 企业版测试环境的 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="f44a9-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f44a9-104">本文中的说明，您配置访问权限的管理，以提高 Microsoft 365 企业版测试环境中的安全性。</span><span class="sxs-lookup"><span data-stu-id="f44a9-104">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="f44a9-106">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="f44a9-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f44a9-107">第 1 阶段： 构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="f44a9-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f44a9-108">如果您只想要配置的最低硬件要求与轻型方式访问权限的管理，按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="f44a9-108">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f44a9-109">如果您想要配置模拟企业中的访问权限的管理，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="f44a9-109">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f44a9-p101">测试访问权限的管理不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。此处提供了作为一个选项，以便可以测试特权访问管理和代表典型组织的环境中试验它。</span><span class="sxs-lookup"><span data-stu-id="f44a9-p101">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="f44a9-112">第 2 阶段： 配置访问权限的管理</span><span class="sxs-lookup"><span data-stu-id="f44a9-112">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="f44a9-p102">在此阶段中，可以配置审批者组和 Microsoft 365 企业版测试环境中启用访问权限的管理。有关其他详细信息和概述特权访问管理，请参阅[Office 365 中的访问权限的管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)。</span><span class="sxs-lookup"><span data-stu-id="f44a9-p102">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment. For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="f44a9-115">请按照下列步骤设置和使用 Office 365 组织中的访问权限：</span><span class="sxs-lookup"><span data-stu-id="f44a9-115">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="f44a9-116">步骤 1： 创建审批者组</span><span class="sxs-lookup"><span data-stu-id="f44a9-116">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    <span data-ttu-id="f44a9-p103">在开始使用最小特权 access 之前，决定谁将具有审批授权的传入请求访问提升特权的任务。审批者的组的一部分的任何用户都将能够批准访问请求。这被启用的 Office 365 中创建启用邮件的安全组。创建新的安全组测试环境中名为"特权访问审批者"，并添加"User 3" 以前在早期测试实验室指南步骤中创建。</span><span class="sxs-lookup"><span data-stu-id="f44a9-p103">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365. Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="f44a9-121">步骤 2： 启用访问权限</span><span class="sxs-lookup"><span data-stu-id="f44a9-121">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    <span data-ttu-id="f44a9-p104">需要显式打开 Office 365 中使用的默认审批者组和包括要排除的访问权限的管理访问控制从系统帐户的一组访问权限。请务必启用您在开始本指南的第 3 阶段之前的 Office 365 组织中的授权访问权限。</span><span class="sxs-lookup"><span data-stu-id="f44a9-p104">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control. Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="f44a9-124">第 3 阶段： 验证进行审批的提升特权的任务</span><span class="sxs-lookup"><span data-stu-id="f44a9-124">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>
<span data-ttu-id="f44a9-125">在此阶段中，您将验证使用特权的访问策略和用户需要审批执行定义的提升和特权任务。</span><span class="sxs-lookup"><span data-stu-id="f44a9-125">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="f44a9-126">测试能够执行未授权访问权限策略中定义的任务</span><span class="sxs-lookup"><span data-stu-id="f44a9-126">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="f44a9-p105">首先，使用配置为您的测试环境中的全局管理员的用户的凭据连接到 Exchange Management PowerShell 并尝试创建新的日记规则。[New-journalrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps)任务当前不在您的组织的访问权限的策略中定义。</span><span class="sxs-lookup"><span data-stu-id="f44a9-p105">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule. The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="f44a9-129">在本地计算机上打开并登录到 Exchange Online 远程 PowerShell 模块， **Microsoft Corporation** > **Microsoft Exchange Online 远程 PowerShell 模块**使用全局管理员帐户的测试环境。</span><span class="sxs-lookup"><span data-stu-id="f44a9-129">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="f44a9-130">在 Exchange Management Powershell 中，创建您的组织的新日记规则：</span><span class="sxs-lookup"><span data-stu-id="f44a9-130">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. <span data-ttu-id="f44a9-131">在 Exchange Management PowerShell 创建的视图的新的日记规则已成功。</span><span class="sxs-lookup"><span data-stu-id="f44a9-131">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="f44a9-132">创建新的访问权限的策略 New-journalrule 任务</span><span class="sxs-lookup"><span data-stu-id="f44a9-132">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="f44a9-133">如果您没有已完成步骤 1 和 2，自本指南的第 2 阶段，为确保遵循的步骤创建名为"最小特权访问审批者"审批者组以及启用测试环境中的授权访问权限。</span><span class="sxs-lookup"><span data-stu-id="f44a9-133">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="f44a9-134">测试环境的全局管理员帐户登录到[Microsoft 365 Admin Center](https://portal.office.com)使用凭据。</span><span class="sxs-lookup"><span data-stu-id="f44a9-134">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="f44a9-135">在管理中心，转到**设置** > **安全性和隐私** > **访问权限**。</span><span class="sxs-lookup"><span data-stu-id="f44a9-135">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="f44a9-136">选择**管理访问策略和请求**。</span><span class="sxs-lookup"><span data-stu-id="f44a9-136">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="f44a9-137">选择**配置策略**，然后选择**添加策略**。</span><span class="sxs-lookup"><span data-stu-id="f44a9-137">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="f44a9-138">从下拉列表的字段中，选择或输入以下值：</span><span class="sxs-lookup"><span data-stu-id="f44a9-138">From the drop-down fields, select or enter the following values:</span></span>
    
    <span data-ttu-id="f44a9-139">**策略类型**： 任务</span><span class="sxs-lookup"><span data-stu-id="f44a9-139">**Policy type**: Task</span></span>

    <span data-ttu-id="f44a9-140">**策略作用域**： Exchange</span><span class="sxs-lookup"><span data-stu-id="f44a9-140">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="f44a9-141">**策略名称**： 新日记规则</span><span class="sxs-lookup"><span data-stu-id="f44a9-141">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="f44a9-142">**审批类型**： 手动</span><span class="sxs-lookup"><span data-stu-id="f44a9-142">**Approval type**: Manual</span></span>

    <span data-ttu-id="f44a9-143">**审核组**： 特权访问审批者</span><span class="sxs-lookup"><span data-stu-id="f44a9-143">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="f44a9-p106">选择**创建**，然后**关闭**。可能需要几分钟，要完全配置并启用的策略。请务必允许将策略应用之前在下一步中测试审批要求完全启用的时间。</span><span class="sxs-lookup"><span data-stu-id="f44a9-p106">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled. Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="f44a9-147">测试 New-journalrule 任务的访问权限的策略中定义的审批要求</span><span class="sxs-lookup"><span data-stu-id="f44a9-147">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="f44a9-148">在本地计算机上打开并登录到 Exchange Online 远程 PowerShell 模块， **Microsoft Corporation** > **Microsoft Exchange Online 远程 PowerShell 模块**使用使用全局管理员帐户为测试环境。</span><span class="sxs-lookup"><span data-stu-id="f44a9-148">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="f44a9-149">在 Exchange Management Powershell 中，创建您的组织的新日记规则：</span><span class="sxs-lookup"><span data-stu-id="f44a9-149">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="f44a9-150">在 Exchange Management PowerShell 中查看"Insuffient 权限"错误：</span><span class="sxs-lookup"><span data-stu-id="f44a9-150">View "Insuffient permissions" error in Exchange Management PowerShell:</span></span>

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="f44a9-151">请求创建一个新的日记规则使用 New-journalrule 任务的访问</span><span class="sxs-lookup"><span data-stu-id="f44a9-151">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="f44a9-152">登录到[Microsoft 365 Admin Center](https://portal.office.com)的测试环境中使用的全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="f44a9-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="f44a9-153">在管理中心，转到**设置** > **安全性和隐私** > **访问权限**。</span><span class="sxs-lookup"><span data-stu-id="f44a9-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="f44a9-154">选择**管理访问策略和请求**。</span><span class="sxs-lookup"><span data-stu-id="f44a9-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="f44a9-p107">选择**新的请求**。从下拉列表字段中，选择您的组织的相应值：</span><span class="sxs-lookup"><span data-stu-id="f44a9-p107">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="f44a9-157">**请求类型**： 任务</span><span class="sxs-lookup"><span data-stu-id="f44a9-157">**Request type**: Task</span></span>

    <span data-ttu-id="f44a9-158">**请求作用域**： Exchange</span><span class="sxs-lookup"><span data-stu-id="f44a9-158">**Request scope**: Exchange</span></span>

    <span data-ttu-id="f44a9-159">**请求**： 新日记规则</span><span class="sxs-lookup"><span data-stu-id="f44a9-159">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="f44a9-160">**持续时间 （小时）**: 2</span><span class="sxs-lookup"><span data-stu-id="f44a9-160">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="f44a9-161">**注释**： 请求权限以创建新的日记规则</span><span class="sxs-lookup"><span data-stu-id="f44a9-161">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="f44a9-p108">选择**保存**和**关闭**。您的请求将发送到通过电子邮件的审批者的组。</span><span class="sxs-lookup"><span data-stu-id="f44a9-p108">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="f44a9-164">批准创建新的日记规则的访问权限的请求</span><span class="sxs-lookup"><span data-stu-id="f44a9-164">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="f44a9-165">登录到[Microsoft 365 Admin Center](https://portal.office.com)用户 3 的测试环境 （在测试环境中的"特权访问审批者"安全组的成员） 中使用的凭据。</span><span class="sxs-lookup"><span data-stu-id="f44a9-165">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="f44a9-166">在管理中心，转到**设置** > **安全性和隐私** > **访问权限**。</span><span class="sxs-lookup"><span data-stu-id="f44a9-166">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="f44a9-167">选择**管理访问策略和请求**。</span><span class="sxs-lookup"><span data-stu-id="f44a9-167">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="f44a9-p109">选择待处理的请求并选择**批准**向要创建新的日记规则的全局管理员帐户授予访问权限。确认已授予审批通知电子邮件将发送到的全局管理员帐户 （发出请求的用户）。</span><span class="sxs-lookup"><span data-stu-id="f44a9-p109">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule. An notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="f44a9-170">测试与批准 New-journalrule 任务的访问权限创建一个新的日记规则</span><span class="sxs-lookup"><span data-stu-id="f44a9-170">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="f44a9-171">在本地计算机上打开并登录到 Exchange Online 远程 PowerShell 模块， **Microsoft Corporation** > **Microsoft Exchange Online 远程 PowerShell 模块**使用全局管理员帐户的测试环境。</span><span class="sxs-lookup"><span data-stu-id="f44a9-171">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="f44a9-172">在 Exchange Management Powershell 中，创建您的组织的新日记规则：</span><span class="sxs-lookup"><span data-stu-id="f44a9-172">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="f44a9-173">在 Exchange Management PowerShell 创建的视图的新的日记规则已成功。</span><span class="sxs-lookup"><span data-stu-id="f44a9-173">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="f44a9-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f44a9-174">Next step</span></span>

<span data-ttu-id="f44a9-175">浏览您的测试环境中其他[信息保护](m365-enterprise-test-lab-guides.md#information-protection)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="f44a9-175">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f44a9-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f44a9-176">See also</span></span>

[<span data-ttu-id="f44a9-177">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="f44a9-177">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f44a9-178">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="f44a9-178">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f44a9-179">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="f44a9-179">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)