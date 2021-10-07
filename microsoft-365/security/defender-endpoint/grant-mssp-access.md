---
title: '向 MSSP 应用程序授予对托管 (提供程序) '
description: 执行必要步骤以配置 MSSP 与 Microsoft Defender for Endpoint 的集成
keywords: 托管安全服务提供程序， mssp， 配置， 集成
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 59d4fd4fa2582b925668adc7eb65d37e8f336da6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208513"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a>向 MSSP (托管安全) 访问 (预览) 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)。

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

若要实现多租户委派访问解决方案，请执行以下步骤：

1. 在 [Defender for](rbac.md) Endpoint 中启用基于角色的访问控制，并与 Active Directory (AD) 连接。

2. 配置 [用于访问请求](/azure/active-directory/governance/identity-governance-overview) 和预配的治理访问包。

3. 在 [Microsoft Myaccess 中管理访问请求和审核](/azure/active-directory/governance/entitlement-management-request-approve)。

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中启用基于角色的访问控制

1. **为客户 AAD 中的 MSSP 资源创建访问组：组**

    这些组将链接到你在 Defender for Endpoint 中创建的角色。 为此，在客户 AD 租户中，创建三个组。 在我们的示例方法中，我们将创建以下组：

    - 第 1 层分析员
    - 第 2 层分析员
    - MSSP 分析员审批者

2. 在 Customer Defender for Endpoint 中为相应的访问级别创建适用于终结点的 Defender 角色。

    若要在客户服务中启用 RBAC Microsoft Defender 安全中心，请设置 >全局管理员或安全管理员权限的用户帐户访问 > **Permissions > Roles** 和"Turn on roles"。

    ![MSSP 访问的图像。](images/mssp-access.png)

    然后，创建 RBAC 角色以满足 MSSP SOC 层需求。 通过"分配的用户组"将这些角色链接到已创建的用户组。

    两个可能的角色：

    - **第 1 层分析员**

      执行除实时响应以外的所有操作并管理安全设置。

    - **第 2 层分析员**

      第 1 层功能以及实时 [响应](live-response.md)

    有关详细信息，请参阅使用 [基于角色的访问控制](rbac.md)。

## <a name="configure-governance-access-packages"></a>配置治理访问包

1. **在客户 AAD 中添加 MSSP 作为连接组织：标识治理**

    将 MSSP 添加为连接的组织将允许 MSSP 请求并设置访问权限。

    为此，在客户 AD 租户中，访问标识治理：已连接组织。 添加新组织，然后通过租户 ID 或域搜索 MSSP 分析员租户。 建议为 MSSP 分析员创建单独的 AD 租户。

2. **在客户 AAD：标识治理中创建资源目录**

    资源目录是在客户 AD 租户中创建的访问包的逻辑集合。

    为此，在客户 AD 租户中，访问 Identity Governance： Catalogs，并添加新 **目录**。 在我们的示例中，我们将它称为 **MSSP Accesses**。

    ![新目录的图像。](images/goverance-catalog.png)

    有关详细信息，请参阅创建 [资源目录](/azure/active-directory/governance/entitlement-management-catalog-create)。

3. **为 MSSP 资源创建访问包客户 AAD：标识治理**

    访问包是请求者在审批时将授予的权限和访问权限的集合。

    为此，在客户 AD 租户中，访问标识治理：访问程序包，并添加新 **的访问包**。 为 MSSP 审批者以及每个分析员层创建一个访问包。 例如，以下第 1 层分析员配置将创建一个访问包：

    - 需要 AD 组 **MSSP 分析员审批者** 的成员来授权新请求
    - 每年进行一次访问评审，SOC 分析师可在其中请求访问扩展
    - 只能由 MSSP SOC 租户中的用户请求
    - Access 自动在 365 天后过期

    > [!div class="mx-imgBorder"]
    > ![新访问包的图像。](images/new-access-package.png)

    有关详细信息，请参阅 [创建新的访问包](/azure/active-directory/governance/entitlement-management-access-package-create)。

4. **提供客户 AAD 中 MSSP 资源的访问请求链接：标识治理**

    MSSP SOC 分析员使用"我的访问门户"链接通过创建的访问包请求访问。 该链接是持久链接，这意味着随着时间的推移，新分析师可能会使用相同的链接。 分析员请求进入一个队列，等待 **MSSP 分析员审批者审批**。

    > [!div class="mx-imgBorder"]
    > ![访问属性的图像。](images/access-properties.png)

    链接位于每个访问包的概述页面上。

## <a name="manage-access"></a>管理访问权限

1. 查看和授权客户和/或 MSSP myaccess 中的访问请求。

    访问请求在客户 My Access 中由 MSSP 分析员审批者组的成员进行管理。

    为此，请通过使用：访问客户的 myaccess。 `https://myaccess.microsoft.com/@<Customer Domain>`

    例如：`https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`

2. 在 UI 的" **审批"部分批准** 或拒绝请求。

    此时，已预配分析师访问权限，并且每个分析师应能够访问客户的Microsoft Defender 安全中心：`https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`

## <a name="related-topics"></a>相关主题

- [访问 MSSP 客户门户](access-mssp-portal.md)
- [配置警报通知](configure-mssp-notifications.md)
- [从客户租户获取警报](fetch-alerts-mssp.md)
