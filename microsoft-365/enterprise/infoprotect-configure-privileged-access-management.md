---
title: 步骤7：配置特权访问管理
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
ms.custom: ''
description: 了解并配置特权访问管理。
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636984"
---
# <a name="step-7-configure-privileged-access-management"></a><span data-ttu-id="922c8-103">步骤7：配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="922c8-103">Step 7: Configure privileged access management</span></span>

<span data-ttu-id="922c8-104">*此步骤是可选的，仅适用于 Microsoft 365 企业版的 E5 版和高级合规版*</span><span class="sxs-lookup"><span data-stu-id="922c8-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![第 6 阶段：信息保护](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="922c8-106">通过配置在租户中为基于任务的活动指定实时访问的策略，启用了特权访问管理。</span><span class="sxs-lookup"><span data-stu-id="922c8-106">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant.</span></span> <span data-ttu-id="922c8-107">它可以帮助保护您的组织免受可能使用具有敏感数据访问权限的现有特权管理员帐户的危害，或访问关键配置设置。</span><span class="sxs-lookup"><span data-stu-id="922c8-107">It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="922c8-108">例如，您可以配置需要明确批准访问和更改租户中的组织邮箱设置的特权访问管理策略。</span><span class="sxs-lookup"><span data-stu-id="922c8-108">For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="922c8-109">在此步骤中，您将在租户中启用特权访问管理，并配置可为组织的数据和配置设置提供额外安全性的特权访问策略。</span><span class="sxs-lookup"><span data-stu-id="922c8-109">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization.</span></span> <span data-ttu-id="922c8-110">有三个基本步骤可开始使用组织中的特权访问：</span><span class="sxs-lookup"><span data-stu-id="922c8-110">There are three basic steps to get started with privileged access in your organization:</span></span>
- <span data-ttu-id="922c8-111">创建审批者的组</span><span class="sxs-lookup"><span data-stu-id="922c8-111">Creating an approver's group</span></span>
- <span data-ttu-id="922c8-112">启用特权访问</span><span class="sxs-lookup"><span data-stu-id="922c8-112">Enabling privileged access</span></span>
- <span data-ttu-id="922c8-113">创建审批策略</span><span class="sxs-lookup"><span data-stu-id="922c8-113">Creating approval policies</span></span>

<span data-ttu-id="922c8-p103">配置完成后，特权访问管理可帮助组织实现零长期特权并针对这类长期管理访问权限造成的漏洞提供一个防御层。特权访问要求必须经过审批才能执行定义了相关审批策略的任务。用户如果需要执行某个审批策略中包含的任务，则必须提出请求并成功通过访问权限审批，以便获得执行该策略中定义的任务所需的权限。</span><span class="sxs-lookup"><span data-stu-id="922c8-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="922c8-117">若要启用特权访问管理，请参阅[配置特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主题。</span><span class="sxs-lookup"><span data-stu-id="922c8-117">To enable privileged access management, see the [Configure privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="922c8-118">有关详细信息，请参阅[特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)主题。</span><span class="sxs-lookup"><span data-stu-id="922c8-118">For more information, see the [Privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="922c8-120">若要在测试实验室环境中练习此配置，请参阅[特权访问管理测试实验室指南](privileged-access-microsoft-365-enterprise-dev-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="922c8-120">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="922c8-121">作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step7)。</span><span class="sxs-lookup"><span data-stu-id="922c8-121">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="922c8-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="922c8-122">Next Step</span></span>

[<span data-ttu-id="922c8-123">信息保护基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="922c8-123">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)
