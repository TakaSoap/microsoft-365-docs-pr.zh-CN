---
title: 步骤 7：同步身份
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/09/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解身份选项并配置 Azure AD Connect，以将本地 Windows Server AD 与 Azure AD 同步。
ms.openlocfilehash: 2391ee11a1706bbbfdeb248c5967822d3ea68f72
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865473"
---
# <a name="step-7-synchronize-identities"></a>步骤 7：同步身份

** 此步骤对于混合环境来说是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在此步骤中，将本地 Windows Server Active Directory (AD) 与 Office 365 和企业移动性 + 安全性 (EMS) 订阅所使用的 Azure Active Directory (AD) 租户同步。

Azure AD Connect 是受支持的 Microsoft 工具，可引导你只将真正需要的身份从单林或多林 Windows Server AD 环境同步到 Azure AD 租户。

![Azure AD Connect 如何将本地目录同步到 Azure AD](./media/identity-azure-ad-connect/azure-ad-connect.png)

*Azure AD Connect 如何将本地目录同步到 Azure AD*

在混合身份解决方案中首先要决定的是身份验证要求。以下是可供选择的选项：

- 使用“托管身份验证”****，Azure AD 将处理用户登录的身份验证过程。有两种托管身份验证的方法： 
    - **密码哈希同步 (PHS)** [推荐使用，且对于某些高级功能是必选方法]。这是针对 Azure AD 中的本地目录对象启用身份验证的最简单方法。Azure AD Connect 从 Windows Server AD 中提取哈希密码，对密码执行额外的安全处理，然后将其保存在 Azure AD 中。有关详细信息，请参阅[通过 Azure AD Connect 同步实现密码哈希同步](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)。
    - **传递身份验证 (PTA)** 为基于 Azure AD 的服务提供简单的密码验证解决方案。PTA 使用在一个或多个本地服务器上运行的代理直接在本地 Windows Server AD 中验证用户身份验证。有关详细信息，请参阅[使用 Azure Active Directory 传递身份验证的用户登录](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)。
- 通过**联合身份验证**，身份验证过程会通过身份联合服务器被重定向到其他标识提供者（例如，Active Directory 联合身份验证服务 (AD FS)），以用于用户登录。该标识提供者可提供其他身份验证方法（例如，基于智能卡的身份验证）。有关详细信息，请参阅[为你的 Azure Active Directory 混合身份解决方案提供正确的身份验证方法](https://docs.microsoft.com/azure/security/azure-ad-choose-authn)。

确定混合身份解决方案后，下载并运行 [IdFix 目录同步错误修正工具](https://www.microsoft.com/download/details.aspx?id=36832)，以分析 Windows Server AD 中存在的问题。

解决了由 IdFix 工具标识的所有问题后，请参阅[实施密码哈希同步](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization)，了解如何为 Office 365 和 EMS 订阅安装 Azure AD Connect 工具，以及在本地 Windows Server AD 和 Azure AD 租户之间配置目录同步。同步启动后，你将使用本地标识提供者（如 Windows Server AD）维护用户帐户和组。

Microsoft 提供了一组有关[身份和设备访问](microsoft-365-policies-configurations.md)的建议，以确保全体员工安全且高效地工作。 
- 有关混合环境的推荐要求，请参阅[先决条件](identity-access-prerequisites.md#prerequisites)中的**支持密码哈希同步的 Active Directory**列。 

- 有关仅限云环境的推荐要求，请参阅[先决条件](identity-access-prerequisites.md#prerequisites)中的**仅限云**列。

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：密码哈希同步](password-hash-sync-m365-ent-test-environment.md)<br> [测试实验室指南：传递身份验证](pass-through-auth-m365-ent-test-environment.md) |
|||

作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-sync)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step8.png)| [监控同步运行状况](identity-azure-ad-connect-health.md) |

