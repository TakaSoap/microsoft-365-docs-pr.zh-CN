---
title: Microsoft 365 中的应用治理
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: 实施 Microsoft 应用治理功能来治理你的应用。
ms.openlocfilehash: ca1a77c4f5a1543a000b563dde98238136b3115d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189545"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a>Microsoft Cloud App Security（预览版）的应用治理加载项

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

> [!NOTE]
> 要注册应用治理，请参阅 [应用治理入门（预览版）](app-governance-get-started.md)。

网络攻击通过各种日益复杂的方式来利用你部署在本地和云基础设施中的应用，为特权提升、横向移动和数据泄露奠定基础。 若要了解潜在风险并阻止这些类型的攻击，你需要清楚了解组织的应用合规状况，以快速识别应用何时表现出异常行为，并在这些行为对你的环境、数据和用户构成风险时做出响应。

Microsoft Cloud App Security 的应用治理加载项功能是一项安全和策略管理功能，专为通过 Microsoft Graph API 访问 Microsoft 365 数据，且已启用 OAuth 的应用而设计。 应用治理通过可操作的见解和自动化的策略警报和操作，对这些应用及其用户如何访问、使用和共享存储在 Microsoft 365 中的敏感数据提供全面的可见性、修复和治理。

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

应用治理为你提供全面的：

- **见解**：在单个仪表板上查看租户中 Microsoft 365 平台的所有第三方应用的视图。 你可以查看所有应用的状态和警报活动，并对它们做出反应或响应。
- **治理**：为应用和用户模式及行为创建主动或被动策略，防止用户使用不合规或恶意的应用，并限制有风险的应用访问你的数据。
- **检测**：在应用活动出现异常以及使用不合规、恶意或有风险的应用时收到警报和通知。
- **修复**：除了自动修复功能外，还可以及时使用修复控件来响应异常应用活动检测。

应用治理是一种基于平台的解决方案，是 Microsoft 365 应用生态系统不可或缺的一部分。 应用治理可监督和管理在 Azure Active Directory (Azure AD) 中注册、通过 Microsoft Graph API 访问数据，并且已启用 OAuth 的应用。 应用治理为你提供应用行为控件，以帮助增强 IT 基础设施的安全性和合规性状况。

## <a name="a-first-glimpse-at-app-governance"></a>应用治理概览

如需查看应用治理仪表板，请转到 [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance)。请注意，若要查看任何应用治理数据，你的登录帐户必须具有其中一个[管理员角色](app-governance-get-started.md#administrator-roles)。

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a>应用治理与 Azure AD 和 Microsoft Cloud App Security 的集成

应用治理、Azure AD 和 Microsoft Cloud App Security 收集并提供不同的数据集：

- 应用治理提供有关 API 级别应用活动的详细信息。
- Azure AD 提供基础应用元数据和有关登录应用的详细信息。
- Microsoft Cloud App Security 提供应用风险信息。

通过跨应用治理、Azure AD 和 Microsoft Cloud App Security 共享信息，可以在一个门户中显示汇总信息，并轻松链接到另一个门户以获取更多信息。以下是一些示例:

- 应用治理中的应用登录信息：

  从应用治理门户，你可以查看每个应用的聚合登录活动，并链接回 Azure Active Directory 管理中心以获取登录事件的详细信息。

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- Microsoft Cloud App Security 门户中的 API 使用信息：

  从 Microsoft Cloud App Security 门户，你可以查看 API 使用级别和聚合数据传输，并链接到应用治理门户以获取详细信息。

以下是该集成的摘要。

![应用治理与 Azure AD 和 Microsoft Cloud App Security 的集成。](..\media\manage-app-protection-governance\mapg-integration.png)

应用治理将其警报发送到 Microsoft Cloud App Security 和 Microsoft 365 Defender，并接收来自 Microsoft Cloud App Security 的警报，以对基于应用的安全事件进行更详细的分析。
- 应用治理警报在 Microsoft 365 Defender 警报列表中显示为警报，其检测源字段设置为“应用治理”
- 应用治理警报在 MCAS 警报列表中显示为警报，其策略字段设置为下列内容之一：
  - Microsoft 365 OAuth 应用治理
  - Microsoft 365 OAuth 网络钓鱼检测
  - Microsoft 365 OAuth 应用信誉
- MCAS 警报作为警报显示在应用治理警报列表中，其源设置为 MCAS

> [!NOTE]
> 警报状态当前未在应用治理和 Microsoft Cloud App Security 之间同步。
