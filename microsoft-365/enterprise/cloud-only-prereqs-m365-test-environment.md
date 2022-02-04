---
title: Microsoft 365 测试环境中仅限云的标识和设备访问先决条件
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
ms.custom: null
description: 创建一个 Microsoft 365 环境来测试标识和设备访问情况，其中内附仅限云的身份验证的先决条件。
---

# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a>Microsoft 365 测试环境中仅限云的标识和设备访问先决条件

*本测试实验室指南只能用于Microsoft 365测试环境。*

[标识和设备访问配置](../security/office-365-security/microsoft-365-policies-configurations.md)是一组建议配置和条件访问策略，用于保护对与设备集成的所有服务Azure Active Directory (Azure AD) 。

本文介绍了如何配置 Microsoft 365 测试环境，使其满足标识和设备访问[仅限云的先决条件配置](../security/office-365-security/identity-access-prerequisites.md#prerequisites)的要求。

此测试环境的设置分为以下八个阶段：

1. 构建轻量级测试环境
2. 配置命名位置
3. 配置自助密码重置
4. 配置多重身份验证
5. 启用已加入域的计算机的Windows注册
6. 配置Azure AD密码保护 
7. 启用 Azure AD Identity Protection
8. 为 Exchange Online 和 Skype for Business Online 启用新式身份验证

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a>阶段 1：构建轻量级的 Microsoft 365 测试环境

按照[轻量级基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明操作。
下面是生成的配置。

![轻型 Microsoft 3656 Enterprise测试环境。](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a>阶段 2：配置命名位置

首先，确定组织使用的公共 IP 地址或地址范围。

接下来，按照[在 Azure Active Directory 中配置命名位置](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)中的说明将地址或地址范围添加为命名位置。 

## <a name="phase-3-configure-self-service-password-reset"></a>阶段 3：配置自助服务密码重置

接下来，按照[“密码重置”测试实验室指南的阶段 3](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) 中的说明进行操作。 

为特定 Azure AD 组中的帐户启用密码重置时，请将这些帐户添加到 **密码重置** 组：

- 用户 2
- 用户 3
- 用户 4
- 用户 5

仅为用户 2 帐户测试密码重置。

## <a name="phase-4-configure-multi-factor-authentication"></a>阶段 4：配置多重身份验证

按照以下用户帐户的[“多重身份验证”测试实验室指南的阶段 2 ](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)中的说明操作：

- 用户 2
- 用户 3
- 用户 4
- 用户 5

仅为用户 2 帐户测试多重身份验证。

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a>阶段 5：启用已加入域的计算机的Windows注册 

按照[以下说明](/azure/active-directory/devices/hybrid-azuread-join-plan)启用已加入域的计算机的自动Windows注册。

## <a name="phase-6-configure-azure-ad-password-protection"></a>第 6 阶段：Azure AD密码保护 

按照 [以下说明](/azure/active-directory/authentication/concept-password-ban-bad) 阻止已知的弱密码及其变体。

## <a name="phase-7-enable-azure-ad-identity-protection"></a>阶段 7：启用 Azure AD Identity Protection

按照[“Azure AD Identity Protection”测试实验室指南的阶段 2](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) 中的说明操作。 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>阶段 8：启用 Exchange Online 和 Skype for Business Online 的新式身份验证

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

结果是测试环境满足标识和设备访问的仅云 [先决条件](../security/office-365-security/identity-access-prerequisites.md#prerequisites) 配置的要求。 

## <a name="next-step"></a>后续步骤

使用[常见标识和设备访问策略](../security/office-365-security/identity-access-policies.md)配置基于这些先决条件构建的策略并保护标识和设备。

## <a name="see-also"></a>另请参阅

[其他标识测试实验室指南](m365-enterprise-test-lab-guides.md#identity)

[部署标识](deploy-identity-solution-overview.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](/microsoft-365-enterprise/)
