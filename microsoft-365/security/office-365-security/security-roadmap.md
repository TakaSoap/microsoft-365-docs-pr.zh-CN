---
title: Microsoft 365 安全路线图 - 首要任务
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 来自 Microsoft 网络安全团队的顶级建议，用于实施用于保护 Microsoft 365 环境的管理功能。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 728519b4285cf9345052540a0207948f80c18cd2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407404"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>安全路线图 - 前 30 天、90 天及之后的主要优先级

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


本文包含来自 Microsoft 网络安全团队的顶级建议，这些建议用于实施安全性功能来保护 Microsoft 365 环境。 本文改编自 Microsoft Ignite 会话 — 像网络安全专业人员一样保护 [Microsoft 365：前 30 天、前 90](https://www.youtube.com/watch?v=luignzNyR-o)天及以后的首要任务。 此课程由 Mark Simos 和企业网络安全架构师 Matt Ke一har 开发并呈现。

本文内容：

- [路线图结果](security-roadmap.md#Roadmap)
- [30 天 - 强大的快速成功](security-roadmap.md#Thirdaydays)
- [90 天 — 增强的保护](security-roadmap.md#Ninetydays)
- [超出范围](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>路线图结果
<a name="Roadmap"> </a>

这些路线图建议按逻辑顺序分三个阶段进行，目标如下。

****

|时间范围|结果|
|---|---|
|30 天|快速配置： <ul><li>基本管理员保护。</li><li>日志记录和分析。</li><li>基本标识保护。</li></ul> <p> 租户配置。 <p> 准备利益干系人。|
|90 天|高级保护： <ul><li>管理员帐户。</li><li>数据和用户帐户。</li></ul> <p> 了解合规性、威胁和用户需求。 <p> 调整并实施默认策略和保护。|
|超出范围|调整和优化关键策略和控件。 <p> 将保护扩展到本地依赖项。 <p> 与业务和安全流程集成 (法律、内部威胁等) 。|
|

## <a name="30-days--powerful-quick-wins"></a>30 天 - 强大的快速成功
<a name="Thirdaydays"> </a>

这些任务可快速完成，对用户产生的影响很小。

****

|区域|任务|
|---|---|
|安全管理|<ul><li>检查安全分数，并记下当前 <https://securescore.office.com> () 。</li><li>打开 Office 365 的审核日志记录。 请参阅 ["搜索审核日志](../../compliance/search-the-audit-log-in-security-and-compliance.md)。</li><li>[配置 Microsoft 365 以提升安全性](tenant-wide-setup-for-increased-security.md)。</li><li>定期查看 Microsoft 365 安全中心和云应用安全中的仪表板和报告。</li></ul>|
|威胁防护|[将 Microsoft 365 连接到 Microsoft Cloud App Security，](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) 以开始使用针对异常行为的默认威胁检测策略进行监视。 需要 7 天来建立异常检测的基线。 <p>  为管理员帐户实施保护：<ul><li>将专用管理员帐户用于管理员活动。</li><li>强制对管理员帐户使用 MFA (多重) 身份验证。</li><li>使用 [高度安全的 Windows 10 设备](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) 进行管理员活动。</li></ul>|
|标识和访问管理|<ul><li>[启用 Azure Active Directory 标识保护](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。</li><li>对于联合身份环境， (密码长度、年龄、复杂性等强制实施帐户) 。</li></ul>|
|信息保护|查看示例信息保护建议。 信息保护需要在整个组织中进行协调。 开始使用这些资源：<ul><li>[针对 GDPR 的 Office 365 信息保护](https://docs.microsoft.com/compliance/regulatory/gdpr)</li><li>[使用三层保护配置 Teams](../../solutions/configure-teams-three-tiers-protection.md) (包括共享、分类、数据丢失防护和 Azure 信息保护) </li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 天 — 增强的保护
<a name="Ninetydays"> </a>

虽然这些任务需要多花一点时间来计划和实现，但会显著改善安全态势。

****

|区域|任务|
|---|---|
|安全管理|<ul><li>检查安全分数，了解针对您的环境安全 <https://securescore.office.com> () 。</li><li>继续定期查看 Microsoft 365 安全中心、云应用安全和 SIEM 工具中的仪表板和报告。</li><li>查找和实施软件更新。</li><li>使用[Office 365](office-365-ti.md)威胁情报中心中包含的攻击模拟器[ (](attack-simulator.md)执行针对网络钓鱼、密码加密和暴力密码攻击的攻击模拟) 。</li><li>通过查看"调查"选项卡上的"云应用安全" (中的内置报告来查找) 。</li><li>检查 [合规性管理器](../../compliance/compliance-manager.md) ，查看适用于组织法规 (如 GDPR、NIST 800-171) 。</li></ul>|
|威胁防护|为管理员帐户实施增强保护： <ul><li>配置 [Privileged Access Workstation (](https://docs.microsoft.com/security/compass/privileged-access-devices) PAW) 管理员活动。</li><li>配置 [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。</li><li>使用 SIEM) 工具配置安全信息和事件管理 (，以收集 Office 365、Cloud App Security 和其他服务（包括 AD FS）中的日志记录数据。 该审核日志数据存储 90 天。 通过在 SIEM 工具中捕获此数据，你可以将数据存储较长时间。</li></ul>|
|标识和访问管理|<ul><li>为所有用户启用和强制执行 MFA。</li><li>实现一组 [条件访问和相关策略](microsoft-365-policies-configurations.md)。</li></ul>|
|信息保护| 调整和实施信息保护策略。 这些资源包括示例： <ul><li>[针对 GDPR 的 Office 365 信息保护](https://docs.microsoft.com/compliance/regulatory/gdpr)</li><li>[配置具有三层保护的 Teams](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> 将 Microsoft 365 中的数据丢失防护策略和监视工具用于存储在 Microsoft 365 (而不是云应用安全) 。 <p> 将 Cloud App Security 与 Microsoft 365 一起用于除数据丢失防护 (其他高级警报) 。|
|

## <a name="beyond"></a>超出范围
<a name="Beyond"> </a>

这些是基于以前工作构建的重要安全措施。

****

|区域|任务|
|---|---|
|安全管理|<ul><li>使用安全分数管理方法继续规划下一 <https://securescore.office.com> () 。</li><li>继续定期查看 Microsoft 365 安全中心、云应用安全和 SIEM 工具中的仪表板和报告。</li><li>继续查找和实施软件更新。</li><li>将电子数据展示集成到法律和威胁响应流程中。</li></ul>|
|威胁防护|<ul><li>为[](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)AD、AD (FS) 本地标识组件 (安全特权访问) 。</li><li>使用云应用安全监视内部威胁。</li><li>使用 Cloud App Security 发现卷影 IT SaaS 使用情况。</li></ul>|
|标识和访问管理|<ul><li>优化策略和操作过程。</li><li>使用 Azure AD Identity Protection 识别内部威胁。</li></ul>|
|信息保护|优化信息保护策略： <ul><li>MICROSOFT 365 和 Office 365 敏感度标签和数据丢失防护 (DLP) 或 Azure 信息保护。</li><li>云应用安全策略和警报。</li></ul>|
|

另请参阅[：如何缓解快速的网络攻击，如"小娜"和"WannaCrypt"。](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)
