---
title: 步骤 4：配置安全的用户身份验证
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/17/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并为用户帐户配置多重身份验证。
ms.openlocfilehash: 44d878a347e7b01263f9ba3a82f6443f5710dc43
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285460"
---
# <a name="step-4-configure-secure-user-authentication"></a>步骤 4：配置安全的用户身份验证

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a>设置多重身份验证

*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

在此步骤中，你将设置多重身份验证 (MFA)，以将第二层安全添加到用户登录和交易。用户正确输入其密码后，MFA 需要其他验证方法。如果没有 MFA，密码就是唯一的验证方法。密码的问题是许多密码容易被攻击者猜出，或者在不知情的情况共享给不受信任方。

使用 MFA，第二层安全可以是：

- 不易被欺骗或者复制的个人和受信任设备，如智能手机。
- 生物识别属性，如指纹。

将基于每个用户帐户启用 MFA 并配置辅助身份验证方法。请确保用户知道已启用 MFA，以便他们理解（如强制使用智能手机进行登录）要求并可以成功登录。

有关详细信息，请参阅[多重身份验证规划](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)。

>[!Note]
>在某些应用程序（如 Microsoft Office 2010 或更低版本和 Apple Mail）中，不能使用 MFA。若要使用这些应用，则需要使用“应用密码”代替传统密码。应用密码可使应用绕过 MFA 并继续工作。若要了解有关应用密码的详细信息，请参阅[为 Office 365 创建应用密码](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)。
>

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：多重身份验证](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-mfa)。



<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>防止凭据泄露

*这是可选的，仅适用于 Microsoft 365 企业版的 E5 版本*

在此部分中，将了解如何配置策略，以防止凭据泄露（攻击者可以通过确定用户帐户名称和密码来获取访问组织的云服务和数据的权限）。 Azure AD Identity Protection 可提供多种方式来帮助阻止攻击者在帐户和组中横向移动以最终移至最有价值的数据。

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

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-ident-prot)。

## <a name="monitor-tenant-and-sign-in-activity"></a>监控租户和登录活动

*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

在此步骤中，将使用 Azure AD 报告查看审核日志和登录活动。有两种类型的报告可用。

**** 审核日志活动报告 - 记录在 Azure AD 租户中执行的每项任务的历史记录。此报告可回答如下问题：

- 谁将某人添加到管理员组？
- 哪些用户将登录到特定应用？
- 发生多少密码重置？

**** 登录活动报告 - 记录谁执行了审核日志报告所报告的任务。此报告可回答如下问题：

- 对于调查中的特定用户，其登录模式是什么？
- 我每天、每周或每月的登录量是多少？
- 多少次登录尝试失败及其相关帐户？

有关报告以及如何进行访问的详细信息，请参阅 [Azure Active Directory 报告](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)。

通过此步骤，你将认识这些报告并了解如何使用它们洞察 Azure AD 事件和活动，以用于规划和安全目的。



## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [简化用户访问权限](identity-password-reset.md) |

