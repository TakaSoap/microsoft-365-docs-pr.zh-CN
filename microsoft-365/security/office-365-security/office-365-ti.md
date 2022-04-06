---
title: 威胁调查和&功能 - Microsoft Defender for Office 365 计划 2
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 了解 Microsoft Defender for Office 365 计划中的威胁调查和响应功能。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 53f1077d4ef32c6dc5698aae74de51dd5a421510
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474896"
---
# <a name="threat-investigation-and-response"></a>威胁调查和响应

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**应用于**
- [适用于 Office 365 计划 2 的 Microsoft Defender](defender-for-office-365.md)


[Microsoft Defender for Office 365](defender-for-office-365.md)威胁调查和响应功能可帮助安全分析员和管理员通过执行Microsoft 365来保护其组织的安全策略：

- 轻松识别、监视和了解网络攻击。
- 帮助快速解决 Exchange Online、SharePoint Online、OneDrive for Business 和 Microsoft Teams 中的威胁。
- 提供见解和知识以帮助安全操作防止网络攻击其组织。
- 针对[基于电子邮件的关键威胁Office 365](automated-investigation-response-office.md)自动调查和响应。

威胁调查和响应功能提供威胁和可用响应门户中相关响应Microsoft 365 Defender见解。 这些见解可帮助组织的安全团队保护用户免受基于电子邮件或文件的攻击。 这些功能有助于监视信号并收集来自多个源的数据，例如用户活动、身份验证、电子邮件、被入侵电脑和安全事件。 业务决策者和安全运营团队可以使用此信息来了解并响应对组织的威胁，并保护知识产权。

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>熟悉威胁调查和响应工具

<https://security.microsoft.com> Microsoft 365 Defender 门户中的威胁调查和响应功能是一组工具和响应工作流，其中包括：

- [资源管理器](#explorer)
- [事件](#incidents)
- [攻击模拟培训](attack-simulation-training.md)
- [自动调查和响应](automated-investigation-response-office.md)

### <a name="explorer"></a>资源管理器

使用 [资源管理器 (](threat-explorer.md) 实时检测功能) 威胁、查看攻击量以及按威胁系列、攻击者基础结构等分析数据。 资源管理器 (也称为威胁资源管理器) 是任何安全分析师调查工作流的起点。

:::image type="content" source="../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png" alt-text="&quot;威胁资源管理器&quot;页" lightbox="../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png":::

To view and use this report in the Microsoft 365 Defender portal at <https://security.microsoft.com>， go to **Email & collaboration** \> **Explorer**. 或者，若要直接转到资源管理器 **页面** ，请使用 <https://security.microsoft.com/threatexplorer>。

## <a name="office-365-threat-intelligence-connection"></a>Office 365威胁智能连接

此功能仅在你拥有有效的 Office 365 E5 或威胁智能加载项时可用。 有关详细信息，请参阅 Office 365 企业版 E5 产品页。

启用此功能后，你将能够将 Microsoft Defender for Office 365 数据合并到 Microsoft 365 Defender 中，以便跨 Office 365 邮箱和 Windows 设备进行全面安全调查。

> [!NOTE]
> 你需要具有相应的许可证才能启用此功能。

若要在威胁情报中Office 365上下文设备集成，你需要在安全与合规中心仪表板中启用 Defender for Endpoint &设置。

### <a name="incidents"></a>事件

使用事件列表 (也称为调查) 查看正在飞行的安全事件列表。 事件用于跟踪威胁（如可疑电子邮件）以及执行进一步调查和修正。

:::image type="content" source="../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png" alt-text="当前威胁事件列表Office 365" lightbox="../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png":::

To view the list of current incidents for your organization in the Microsoft 365 Defender portal at <https://security.microsoft.com>， go to **Incidents & alerts** \> **Incidents**. 或者，若要直接转到" **事件"** 页面，请使用 <https://security.microsoft.com/incidents>。

:::image type="content" source="../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png" alt-text="安全与合规中心&审阅页面" lightbox="../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png":::

### <a name="attack-simulation-training"></a>攻击模拟培训

使用攻击模拟培训在组织中设置和运行真实的网络攻击，并识别在真实网络攻击影响你的业务之前易受攻击的人。 若要了解更多信息，请参阅 [模拟网络钓鱼攻击](attack-simulation-training.md)。

To view and use this feature in the Microsoft 365 Defender portal at <https://security.microsoft.com>， go to **Email & collaborationAttack** >  **simulation training**. 或者，若要直接转到 **攻击模拟培训** 页面，请使用 <https://security.microsoft.com/attacksimulator?viewid=overview>。

### <a name="automated-investigation-and-response"></a>自动调查和响应

使用 AIR (自动调查和) 功能，节省将内容、设备和组织中面临威胁的人关联在一起的时间和工作量。 只要触发某些警报，或者由安全运营团队启动，AIR 进程就可以开始。 若要了解更多信息，请参阅 Office 365 中的自动[调查和Office 365](automated-investigation-response-office.md)。

## <a name="threat-intelligence-widgets"></a>威胁智能小组件

作为 Microsoft Defender for Office 365 2 产品/服务一部分，安全分析师可以审阅有关已知威胁的详细信息。 这可用于确定是否可以采取其他预防措施/步骤来保证用户安全。

:::image type="content" source="../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png" alt-text="显示最近威胁信息的&quot;安全趋势&quot;窗格" lightbox="../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png":::

## <a name="how-do-we-get-these-capabilities"></a>我们如何获取这些功能？

Microsoft 365威胁调查和响应功能包含在 Microsoft Defender for Office 365 计划 2 中，该计划包含在 Enterprise E5 中或作为特定订阅的加载项。 若要了解更多信息，请参阅 [Defender for Office 365 Plan 1 和 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)。

## <a name="required-roles-and-permissions"></a>所需角色和权限

Microsoft Defender for Office 365使用基于角色的访问控制。 权限通过 Azure Active Directory、Microsoft 365 管理中心 或 Microsoft 365 Defender 门户中的特定角色分配。

> [!TIP]
> 尽管某些角色（如安全管理员）可以在 Microsoft 365 Defender门户中分配，但请考虑使用 Microsoft 365 管理中心 或 Azure Active Directory。 有关角色、角色组和权限的信息，请参阅以下资源：
>
> - [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)
> - [Azure AD内置角色](/azure/active-directory/roles/permissions-reference)

|活动|角色和权限|
|---|---|
|使用威胁&漏洞管理仪表板 (或新 [安全仪表板](security-dashboard.md) <p> 查看有关最近威胁或当前威胁的信息|以下各项之一： <ul><li>**全局管理员**</li><li>**安全管理员**</li><li>**安全读者**</li></ul> <p> 这些角色可以在角色分配Azure Active Directory () <https://portal.azure.com> 或Microsoft 365 管理中心 () <https://admin.microsoft.com> 。|
|使用 [资源管理器 (实时检测功能) ](threat-explorer.md) 分析威胁|以下各项之一： <ul><li>**全局管理员**</li><li>**安全管理员**</li><li>**安全读者**</li></ul> <p> 这些角色可以在角色分配Azure Active Directory () <https://portal.azure.com> 或Microsoft 365 管理中心 () <https://admin.microsoft.com> 。|
|查看事件 (也称为调查)  <p> 向事件添加电子邮件|以下各项之一： <ul><li>**全局管理员**</li><li>**安全管理员**</li><li>**安全读者**</li></ul> <p> 这些角色可以在角色分配Azure Active Directory () <https://portal.azure.com> 或Microsoft 365 管理中心 () <https://admin.microsoft.com> 。|
|在事件中触发电子邮件操作 <p> 查找并删除可疑电子邮件|以下各项之一： <ul><li>**全局管理员**</li><li>**安全管理员** 以及 **搜索和清除** 角色</li></ul> <p> 全局 **管理员****和安全管理员** 角色可以分配给全局管理员Azure Active Directory () <https://portal.azure.com> 或<https://admin.microsoft.com>Microsoft 365 管理中心 () 。 <p> 必须在 **Microsoft** 36 Defender 门户和 Microsoft 36 Defender  &电子邮件和协作角色中分配搜索和清除 () <https://security.microsoft.com> 。|
|将 Microsoft Defender for Office 365 计划 2 与 Microsoft Defender for Endpoint 集成 <p> 将 Microsoft Defender for Office 365 计划 2 与 SIEM 服务器集成|全局 **管理员或** 安全管理员角色在 Azure Active Directory () 或 <https://portal.azure.com> <https://admin.microsoft.com> Microsoft 365 管理中心 () 。 <p> --- **加号** --- <p> 在其他应用程序（如 (或 SIEM Microsoft Defender 安全中心）中分配的适当) [](/windows/security/threat-protection/microsoft-defender-atp/user-roles)。|

## <a name="next-steps"></a>后续步骤

- [了解威胁跟踪器 - 新增和值得注意的功能](threat-trackers.md)
- [查找并调查通过威胁调查和响应 (Office 365传递的恶意) ](investigate-malicious-email-that-was-delivered.md)
- [将Office 365威胁调查和响应与 Microsoft Defender for Endpoint 集成](integrate-office-365-ti-with-mde.md)
- [模拟网络钓鱼攻击](attack-simulation-training.md)
