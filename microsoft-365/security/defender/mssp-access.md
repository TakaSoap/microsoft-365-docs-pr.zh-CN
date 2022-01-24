---
title: 提供托管安全服务提供程序 (MSSP) 访问权限
description: 了解从网站Microsoft Defender 安全中心到 Microsoft 365 Defender 门户的更改
keywords: 入门：Microsoft 365 Defender门户、适用于 Office 365 的 Microsoft Defender、Microsoft Defender for Endpoint、MDO、MDE、单窗格的门户、聚合门户、安全门户、Defender 安全门户
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 641636528d35c148ceaa41827721e841dfafd4ec
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2022
ms.locfileid: "62171043"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>提供托管安全服务提供程序 (MSSP) 访问权限 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**适用于：**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

若要实现多租户委派访问解决方案，请执行以下步骤：

1. 通过[Microsoft 365 Defender](/windows/security/threat-protection/microsoft-defender-atp/rbac)门户为 Defender for Endpoint 启用基于角色的访问控制，并与Azure Active Directory (Azure AD) 连接。

2. 配置 [用于访问请求](/azure/active-directory/governance/identity-governance-overview) 和预配的治理访问包。

3. 在 [Microsoft Myaccess 中管理访问请求和审核](/azure/active-directory/governance/entitlement-management-request-approve)。

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-defender-portal"></a>在 Microsoft Defender for Endpoint 中启用基于角色的访问控制（Microsoft 365 Defender门户）

1. **在 Customer AAD： Groups 中为 MSSP 资源创建访问组**

    这些组将链接到你在安全门户的 Defender for Endpoint Microsoft 365 Defender角色。 为此，在客户 AD 租户中，创建三个组。 在我们的示例方法中，我们将创建以下组：

    - 第 1 层分析员
    - 第 2 层分析员
    - MSSP 分析员审批者  

2. 在客户 Defender for Endpoint 中的相应访问级别创建适用于终结点的 Defender Microsoft 365 Defender门户角色和组。

    若要在客户门户Microsoft 365 Defender RBAC，>具有全局管理员或安全管理员权限的用户帐户&组 >**角色**"访问"权限">终结点角色"。

    ![MSSP 访问的图像。](../../media/mssp-access.png)

    然后，创建 RBAC 角色以满足 MSSP SOC 层需求。 通过"分配的用户组"将这些角色链接到已创建的用户组。

    两个可能的角色：

    - **第 1 层分析员** <br>
      执行除实时响应以外的所有操作并管理安全设置。

    - **第 2 层分析员** <br>
      第 1 层功能以及实时 [响应](/windows/security/threat-protection/microsoft-defender-atp/live-response)

    有关详细信息，请参阅使用 [基于角色的访问控制](/windows/security/threat-protection/microsoft-defender-atp/rbac)。

## <a name="configure-governance-access-packages"></a>配置治理访问包

1. **在 Customer AAD： Identity Governance 中将 MSSP 添加为连接组织**

    将 MSSP 添加为连接的组织将允许 MSSP 请求并设置访问权限。 

    为此，在客户 AD 租户中，访问标识治理：已连接组织。 添加新组织，然后通过租户 ID 或域搜索 MSSP 分析员租户。 建议为 MSSP 分析员创建单独的 AD 租户。

2. **在 Customer AAD： Identity Governance 中创建资源目录**

    资源目录是在客户 AD 租户中创建的访问包的逻辑集合。

    为此，在客户 AD 租户中，访问 Identity Governance： Catalogs，并添加新 **目录**。 在我们的示例中，我们将它称为 **MSSP Accesses**。

    ![新目录的图像。](../../media/goverance-catalog.png)

    有关详细信息，请参阅创建 [资源目录](/azure/active-directory/governance/entitlement-management-catalog-create)。

3. **为 MSSP 资源创建访问包客户AAD：标识治理**

    访问包是请求者在审批时将授予的权限和访问权限的集合。 

    为此，在客户 AD 租户中，访问标识治理：访问程序包，并添加新 **的访问包**。 为 MSSP 审批者以及每个分析员层创建一个访问包。 例如，以下第 1 层分析员配置将创建一个访问包：

    - 需要 AD 组 **MSSP 分析员审批者** 的成员来授权新请求
    - 每年进行一次访问评审，SOC 分析师可在其中请求访问扩展
    - 只能由 MSSP SOC 租户中的用户请求
    - Access 自动在 365 天后过期

    ![新访问包的图像。](../../media/new-access-package.png)

    有关详细信息，请参阅 [创建新的访问包](/azure/active-directory/governance/entitlement-management-access-package-create)。

4. **提供从 Customer AAD：Identity Governance 访问 MSSP 资源的访问请求链接**

    MSSP SOC 分析员使用"我的访问门户"链接通过创建的访问包请求访问。 该链接是持久链接，这意味着随着时间的推移，新分析师可能会使用相同的链接。 分析员请求进入一个队列，等待 **MSSP 分析员审批者审批**。

    ![访问属性的图像。](../../media/access-properties.png)

    链接位于每个访问包的概述页面上。

## <a name="manage-access"></a>管理访问权限

1. 查看和授权客户和/或 MSSP myaccess 中的访问请求。

    访问请求在客户 My Access 中由 MSSP 分析员审批者组的成员进行管理。

    为此，请通过使用：访问客户的 myaccess。 `https://myaccess.microsoft.com/@<Customer Domain>`

    例如：`https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`

2. 在 UI 的" **审批"部分批准** 或拒绝请求。

     此时，已预配分析师访问权限，并且每个分析师应能够访问客户的Microsoft 365 Defender门户：

    `https://security.microsoft.com/?tid=<CustomerTenantId>` 具有分配的权限和角色。

> [!IMPORTANT]
> Microsoft Defender for Endpoint 在 Microsoft 365 Defender 门户中的委派访问权限当前允许每个浏览器窗口访问单个租户。
