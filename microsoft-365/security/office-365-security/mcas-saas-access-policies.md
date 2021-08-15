---
title: SaaS Microsoft Cloud App Security的建议策略 - Microsoft 365 企业版 |Microsoft Docs
description: 介绍用于与 Microsoft Cloud App Security 集成的建议策略。
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: Admin
ms.author: bcarter
ms.date: 03/22/2021
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 0051b138d155ed4bdf41786f4a73439bba22c738ba7d2a73da44341437ba5c0c
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53838557"
---
# <a name="recommended-microsoft-cloud-app-security-policies-for-saas-apps"></a>SaaS Microsoft Cloud App Security的建议策略
Microsoft Cloud App Security基于 Azure AD 条件访问策略构建，支持使用 SaaS 应用实时监视和控制粒度操作，例如阻止下载、上传、复制和粘贴以及打印。 此功能为具有固有风险的会话添加安全性，例如，当非托管设备或来宾用户访问公司资源时。

Microsoft Cloud App Security与 Microsoft 信息保护 集成，提供实时内容检查，以根据敏感信息类型和敏感度标签查找敏感数据，并采取适当的措施。

本指南包括针对以下方案的建议：

- 将 SaaS 应用引入 IT 管理
- 优化对特定 SaaS 应用的保护
- 配置 DLP (数据丢失) 以帮助遵守数据保护法规

## <a name="bring-saas-apps-into-it-management"></a>将 SaaS 应用引入 IT 管理

使用 Microsoft Cloud App Security管理 SaaS 应用的第一步是发现它们，然后将其添加到 Azure AD 租户。 如果需要发现帮助，请参阅 [发现和管理网络中 SaaS 应用](/cloud-app-security/tutorial-shadow-it)。 发现应用后， [将其添加到 Azure AD 租户](/azure/active-directory/manage-apps/add-application-portal)。

可以通过执行以下操作开始管理这些操作：

1. 首先，在 Azure AD 中，创建新的条件访问策略，并配置为"使用条件访问应用控制"。 这会将请求重定向到云应用安全。 你可以创建一个策略，并添加所有 SaaS 应用到此策略。
1. 接下来，在云应用安全，创建会话策略。 为要应用的每个控件创建一个策略。

对 SaaS 应用的权限通常基于对应用的访问权限的业务需求。 这些权限可以是高度动态的。 使用云应用安全策略可确保保护应用数据，无论用户被分配到与基线、敏感或高度管控保护相关联的 Azure AD 组。

为了跨 SaaS 应用集合保护数据，下图说明了必要的 Azure AD 条件访问策略，以及可在 云应用安全 创建的建议策略。 此示例中，在 云应用安全 创建的策略将应用于你正在管理的所有 SaaS 应用。 这些控件旨在根据设备是否受管理以及已应用于文件的敏感度标签来应用适当的控件。

![用于管理 SaaS 应用中云应用安全](../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png)

下表列出了必须在 Azure AD 中创建的新条件访问策略。

|保护级别|Policy|更多信息|
|---|---|---|
|所有保护级别|[在应用程序中使用条件访问云应用安全](/cloud-app-security/proxy-deployment-aad#configure-integration-with-azure-ad)|这将配置你的 IdP (Azure AD) 以使用 云应用安全。|
||||

下表列出了上面说明的示例策略，你可以创建这些策略来保护所有 SaaS 应用。 请务必评估自己的业务、安全性和合规性目标，然后创建为环境提供最合适的保护的策略。

|保护级别|Policy|
|---|---|
|基线|监视来自非托管设备的流量 <p> 向从非托管设备下载文件添加保护|
|敏感|阻止从非托管设备下载标记为敏感或分类的文件 (这将仅提供浏览器) |
|高度管控|阻止从所有设备下载标记为已分类 (这将提供浏览器仅) |
|||

有关设置条件访问应用控件的端到端说明，请参阅为特色应用部署条件 [访问应用控制](/cloud-app-security/proxy-deployment-aad)。 本文将引导你完成在 Azure AD 中创建必要的条件访问策略和测试 SaaS 应用的过程。

有关详细信息，请参阅使用条件[访问应用Microsoft Cloud App Security保护应用](/cloud-app-security/proxy-intro-aad)。

## <a name="tune-protection-for-specific-saas-apps"></a>优化对特定 SaaS 应用的保护

你可能想要将其他监视和控件应用到环境中的特定 SaaS 应用。 云应用安全可完成此操作。 例如，如果你的环境中大量使用 Box 等应用，则应用其他控件是有意义的。 或者，如果你的法律或财务部门将特定 SaaS 应用用于敏感业务数据，你可以针对这些应用提供额外保护。

例如，可以使用以下类型的内置异常检测策略模板保护 Box 环境：

- 来自匿名 IP 地址的活动
- 来自不常见国家/地区的活动
- 来自可疑 IP 地址的活动
- 不可能旅行
- 终止用户用户执行的活动 (AAD 作为 IdP) 
- 恶意软件检测
- 多个失败登录尝试
- 勒索软件活动
- Risky Oauth App
- 异常的文件共享活动

这些就是示例。 定期添加其他策略模板。 有关如何将其他保护应用于特定应用的示例，请参阅 [保护已连接的应用](/cloud-app-security/protect-connected-apps)。

[如何云应用安全](/cloud-app-security/protect-box)Box 环境的保护演示了可帮助你在 Box 和其他应用（包含敏感数据）中保护业务数据的控件类型。

## <a name="configure-data-loss-prevention-dlp-to-help-comply-with-data-protection-regulations"></a>配置 DLP (数据丢失) 以帮助遵守数据保护法规

云应用安全配置合规性法规保护的有用工具。 在这种情况下，您可以创建特定策略来查找法规适用的特定数据，并配置每个策略以采取适当措施。

下图和表提供了一些策略示例，可配置这些策略以帮助遵守 GDPR 一般 (条例) 。 在这些示例中，策略查找特定数据。 根据数据的敏感度，每个策略都配置为采取相应的操作。

![数据丢失云应用安全策略示例](../../media/microsoft-365-policies-configurations/mcas-dlp.png)

|保护级别|示例策略|
|---|---|
|基线|当包含此敏感信息类型的文件 ("信用卡号"时) 组织外部共享时发出警报 <p> >阻止将包含此敏感信息类型的文件 ("信用卡号") 到非托管设备|
|敏感|保护包含此敏感信息类型的文件下载 ("信用卡号") 托管设备 <p> 阻止下载包含此敏感信息类型的文件 ("信用卡号") 非托管设备 <p> 当包含这些标签的文件上载到 OneDrive for Business 或 Box (客户数据、人力资源：工资数据、人力资源、员工数据) |
|高度管控|当具有此标签的文件 ("高度分类") 下载到托管设备时发出警报 <p> 阻止下载具有此标签的文件 ("高度分类") 非托管设备|
|||

## <a name="next-steps"></a>后续步骤

有关使用应用程序云应用安全，请参阅Microsoft Cloud App Security[文档](//cloud-app-security/)。
