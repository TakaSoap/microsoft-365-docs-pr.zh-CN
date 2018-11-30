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
# <a name="step-6-protect-against-credential-compromise"></a>第 6 步：防范凭据泄漏

** 此步骤是可选的，仅适用于 Microsoft 365 企业版的 E5 版本

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在此步骤中，将了解如何配置策略，以防止凭据泄露（攻击者可以通过确定用户帐户名称和密码来获取访问组织的云服务和数据的权限）。Azure AD Identity Protection 可提供多种方式来帮助阻止攻击者在帐户和组中横向移动以最终移至最有价值的数据。

使用 Azure AD Identity Protection，可以：

|||
|:---------|:---------|
|确定并解决组织身份中的潜在漏洞|Azure AD 使用机器学习来检测异常和可疑活动（如登录和后登录活动）。使用此数据，Identity Protection 将生成报告和警报，用以帮助你评估问题并采取行动。|
|检测与组织身份相关的可疑操作并自动对其响应|可以配置基于风险的策略，以在达到指定风险级别时自动响应检测到的问题。这些策略，以及由 Azure Active Directory 和企业移动性 + 安全性 (EMS) 提供的其他条件访问控制，可自动阻止访问或采取纠正措施，包括密码重置以及要求对后续登录进行多重身份验证。|
|调查可疑事件并使用管理操作加以解决|可以使用有关安全事件的信息来调查风险事件。提供的基本工作流可用于跟踪调查和启动修正操作（如密码重置）。|

请参阅[有关 Azure AD Identity Protection 的详细信息](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)。

请参阅[启用 Azure AD Identity Protection 的步骤](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。

此步骤的结果是，启用了 Azure AD Identity Protection 并用它来：

- 解决潜在身份漏洞。
- 检测可能的凭据泄露尝试。
- 调查和解决正在进行的可疑身份活动。

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-ident-prot)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [同步目录](identity-azure-ad-connect.md) |


