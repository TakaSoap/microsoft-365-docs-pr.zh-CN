---
title: 第 6 步：防范凭据泄漏
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
description: 理解和配置 Azure AD Identity Protection。
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866043"
---
# <a name="step-6-protect-against-credential-compromise"></a><span data-ttu-id="5e4d3-103">第 6 步：防范凭据泄漏</span><span class="sxs-lookup"><span data-stu-id="5e4d3-103">Step 6: Protect against credential compromise</span></span>

<span data-ttu-id="5e4d3-104">\*\* 此步骤是可选的，仅适用于 Microsoft 365 企业版的 E5 版本</span><span class="sxs-lookup"><span data-stu-id="5e4d3-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="5e4d3-p101">在此步骤中，将了解如何配置策略，以防止凭据泄露（攻击者可以通过确定用户帐户名称和密码来获取访问组织的云服务和数据的权限）。Azure AD Identity Protection 可提供多种方式来帮助阻止攻击者在帐户和组中横向移动以最终移至最有价值的数据。</span><span class="sxs-lookup"><span data-stu-id="5e4d3-p101">In Step 15, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data. Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="5e4d3-107">使用 Azure AD Identity Protection，可以：</span><span class="sxs-lookup"><span data-stu-id="5e4d3-107">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="5e4d3-108">确定并解决组织身份中的潜在漏洞</span><span class="sxs-lookup"><span data-stu-id="5e4d3-108">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="5e4d3-p102">Azure AD 使用机器学习来检测异常和可疑活动（如登录和后登录活动）。使用此数据，Identity Protection 将生成报告和警报，用以帮助你评估问题并采取行动。</span><span class="sxs-lookup"><span data-stu-id="5e4d3-p102">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="5e4d3-111">检测与组织身份相关的可疑操作并自动对其响应</span><span class="sxs-lookup"><span data-stu-id="5e4d3-111">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="5e4d3-p103">可以配置基于风险的策略，以在达到指定风险级别时自动响应检测到的问题。这些策略，以及由 Azure Active Directory 和企业移动性 + 安全性 (EMS) 提供的其他条件访问控制，可自动阻止访问或采取纠正措施，包括密码重置以及要求对后续登录进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="5e4d3-p103">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="5e4d3-114">调查可疑事件并使用管理操作加以解决</span><span class="sxs-lookup"><span data-stu-id="5e4d3-114">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="5e4d3-p104">可以使用有关安全事件的信息来调查风险事件。提供的基本工作流可用于跟踪调查和启动修正操作（如密码重置）。</span><span class="sxs-lookup"><span data-stu-id="5e4d3-p104">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="5e4d3-117">请参阅[有关 Azure AD Identity Protection 的详细信息](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)。</span><span class="sxs-lookup"><span data-stu-id="5e4d3-117">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="5e4d3-118">请参阅[启用 Azure AD Identity Protection 的步骤](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。</span><span class="sxs-lookup"><span data-stu-id="5e4d3-118">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="5e4d3-119">此步骤的结果是，启用了 Azure AD Identity Protection 并用它来：</span><span class="sxs-lookup"><span data-stu-id="5e4d3-119">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="5e4d3-120">解决潜在身份漏洞。</span><span class="sxs-lookup"><span data-stu-id="5e4d3-120">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="5e4d3-121">检测可能的凭据泄露尝试。</span><span class="sxs-lookup"><span data-stu-id="5e4d3-121">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="5e4d3-122">调查和解决正在进行的可疑身份活动。</span><span class="sxs-lookup"><span data-stu-id="5e4d3-122">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="5e4d3-124">测试实验室指南：Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="5e4d3-124">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="5e4d3-125">作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-ident-prot)。</span><span class="sxs-lookup"><span data-stu-id="5e4d3-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="5e4d3-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5e4d3-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="5e4d3-127">同步目录</span><span class="sxs-lookup"><span data-stu-id="5e4d3-127">Synchronize directories</span></span>](identity-azure-ad-connect.md) |


