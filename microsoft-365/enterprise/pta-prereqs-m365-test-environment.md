---
title: Microsoft 365 测试环境中传递身份验证的标识和设备访问先决条件
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 创建一个 Microsoft 365 环境来测试标识和设备访问情况，其中内附传递身份验证的先决条件。
ms.openlocfilehash: bbaa3fcf2333661f2ff077f80ac617cc0f9090df
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60214149"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a>Microsoft 365 测试环境中传递身份验证的标识和设备访问先决条件

*本测试实验室指南只能用于Microsoft 365测试环境。*

[标识和设备访问](../security/office-365-security/microsoft-365-policies-configurations.md)配置是一组配置和条件访问策略，用于保护对 Microsoft 365 中与 Azure AD Azure Active Directory (集成的所有服务) 。

本文介绍了可以如何配置 Microsoft 365 测试环境，以使其满足标识和设备访问的[传递身份验证先决条件配置](../security/office-365-security/identity-access-prerequisites.md#prerequisites)要求。

设置此测试环境有 10 个阶段：

1. 构建传递身份验证的模拟企业 Microsoft 365 测试环境
2. 配置 Azure AD 无缝单一登录
3. 配置命名位置
4. 配置密码写回服务
5. 配置自助密码重置
6. 配置多重身份验证
7. 启用已加入域的计算机的自动Windows注册
8. 配置 Azure AD 密码保护 
9. 启用 Azure AD Identity Protection
10. 为 Exchange Online 和 Skype for Business Online 启用新式身份验证

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a>阶段 1：构建传递身份验证的模拟企业 Microsoft 365 测试环境

按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明操作。

下面是生成的配置。

![具有传递身份验证测试环境的模拟企业。](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a>阶段 2：配置 Azure AD 无缝单一登录

按照[“Azure AD 无缝单点登录”测试实验室指南的阶段 2](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) 中的说明操作。

## <a name="phase-3-configure-named-locations"></a>阶段 3：配置命名位置

首先，确定组织使用的公共 IP 地址或地址范围。

接下来，按照[在 Azure Active Directory 中配置命名位置](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)中的说明将地址或地址范围添加为命名位置。 

## <a name="phase-4-configure-password-writeback"></a>阶段 4：配置密码写回服务

接下来，按照[“密码写回”测试实验室指南的阶段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的说明进行操作。

## <a name="phase-5-configure-self-service-password-reset"></a>阶段 5：配置自助服务密码重置

接下来，按照[“密码重置”测试实验室指南的阶段 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) 中的说明进行操作。 

为特定 Azure AD 组中的帐户启用密码重置时，请将这些帐户添加到 **密码重置** 组：

- 用户 2
- 用户 3
- 用户 4
- 用户 5

仅为用户 2 帐户测试密码重置。

## <a name="phase-6-configure-multi-factor-authentication"></a>阶段 6：配置多重身份验证

按照以下用户帐户的[“多重身份验证”测试实验室指南的阶段 2 ](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)中的说明操作：

- 用户 2
- 用户 3
- 用户 4
- 用户 5

仅为用户 2 帐户测试多重身份验证。

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a>阶段 7：启用已加入域的计算机的Windows注册 

按照[以下说明](/azure/active-directory/devices/hybrid-azuread-join-plan)启用已加入域的计算机的自动Windows注册。

## <a name="phase-8-configure-azure-ad-password-protection"></a>第 8 阶段：配置 Azure AD 密码保护 

按照 [以下说明](/azure/active-directory/authentication/concept-password-ban-bad) 阻止已知的弱密码及其变体。

## <a name="phase-9-enable-azure-ad-identity-protection"></a>第 9 阶段：启用 Azure AD Identity Protection

按照[“Azure AD Identity Protection”测试实验室指南的阶段 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) 中的说明操作。 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>第 10 阶段：为 Exchange Online 和 Skype for Business Online 启用新式验证

对于 Exchange Online，请按照[这些说明](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later)操作。 

对于 Skype for Business Online：

1. 连接到 [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

2. 运行以下命令。

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. 使用此命令验证更改是否成功。

  ```powershell
  Get-CsOAuthConfiguration
  ```

结果是得到一个符合以下条件的测试环境：满足标识和设备访问的[传递身份验证先决条件配置](../security/office-365-security/identity-access-prerequisites.md#prerequisites)要求。 

## <a name="next-step"></a>后续步骤

使用[常见标识和设备访问策略](../security/office-365-security/identity-access-policies.md)配置基于这些先决条件构建的策略并保护标识和设备。

## <a name="see-also"></a>另请参阅

[其他标识测试实验室指南](m365-enterprise-test-lab-guides.md#identity)

[标识路线图](identity-roadmap-microsoft-365.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](/microsoft-365-enterprise/)
