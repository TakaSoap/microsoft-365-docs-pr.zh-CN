---
title: 步骤 13：监控租户和登录活动
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并配置 Azure AD 访问和使用情况报告。
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865385"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="8fc16-103">步骤 13：监控租户和登录活动</span><span class="sxs-lookup"><span data-stu-id="8fc16-103">Step 13: Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="8fc16-104">\*\* 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本</span><span class="sxs-lookup"><span data-stu-id="8fc16-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="8fc16-p101">在此步骤中，将使用 Azure AD 报告查看审核日志和登录活动。有两种类型的报告可用。</span><span class="sxs-lookup"><span data-stu-id="8fc16-p101">In Step 13, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="8fc16-p102">\*\*\*\* 审核日志活动报告 - 记录在 Azure AD 租户中执行的每项任务的历史记录。此报告可回答如下问题：</span><span class="sxs-lookup"><span data-stu-id="8fc16-p102">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="8fc16-109">谁将某人添加到管理员组？</span><span class="sxs-lookup"><span data-stu-id="8fc16-109">Who added someone to an admin group?</span></span>
- <span data-ttu-id="8fc16-110">哪些用户将登录到特定应用？</span><span class="sxs-lookup"><span data-stu-id="8fc16-110">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="8fc16-111">发生多少密码重置？</span><span class="sxs-lookup"><span data-stu-id="8fc16-111">How many password resets are happening?</span></span>

<span data-ttu-id="8fc16-p103">\*\*\*\* 登录活动报告 - 记录谁执行了审核日志报告所报告的任务。此报告可回答如下问题：</span><span class="sxs-lookup"><span data-stu-id="8fc16-p103">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="8fc16-114">对于调查中的特定用户，其登录模式是什么？</span><span class="sxs-lookup"><span data-stu-id="8fc16-114">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="8fc16-115">我每天、每周或每月的登录量是多少？</span><span class="sxs-lookup"><span data-stu-id="8fc16-115">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="8fc16-116">多少次登录尝试失败及其相关帐户？</span><span class="sxs-lookup"><span data-stu-id="8fc16-116">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="8fc16-117">有关报告以及如何进行访问的详细信息，请参阅 [Azure Active Directory 报告](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="8fc16-117">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="8fc16-118">通过此步骤，你将认识这些报告并了解如何使用它们洞察 Azure AD 事件和活动，以用于规划和安全目的。</span><span class="sxs-lookup"><span data-stu-id="8fc16-118">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>

## <a name="next-step"></a><span data-ttu-id="8fc16-119">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8fc16-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="8fc16-120">允许用户创建和管理自己的组</span><span class="sxs-lookup"><span data-stu-id="8fc16-120">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
