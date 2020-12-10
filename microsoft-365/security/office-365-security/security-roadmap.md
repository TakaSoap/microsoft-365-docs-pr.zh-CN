---
title: Microsoft 365 安全路线图-首要优先级
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 'Microsoft cybersecurity 团队提供的用于实施安全功能以保护您的 Microsoft 365 环境的主要建议。 '
ms.openlocfilehash: 452ce2a303f02cadfcdcbe12310f2538d33a24e7
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615800"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>安全路线图-前30天、90天及以上的首要优先级

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


本文包含来自 Microsoft cybersecurity 团队的最佳建议，这些建议可实施安全功能来保护您的 Microsoft 365 环境。 本文适用于 Microsoft Ignite 会话— [安全 microsoft 365，如 cybersecurity pro：前30天、90天和之后的主要优先级](https://www.youtube.com/watch?v=luignzNyR-o)。 此会话是通过标记 Simos 和 Matt Kemelhar （企业 Cybersecurity 架构师）开发和展示的。

本文内容：

- [路线图结果](security-roadmap.md#Roadmap)
- [30天—功能强大的快速 wins](security-roadmap.md#Thirdaydays)
- [90天—增强型保护](security-roadmap.md#Ninetydays)
- [满足](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>路线图结果
<a name="Roadmap"> </a>

这些路线图建议按逻辑顺序在三个阶段之间暂存，具有以下目标。

****

|时间范围|结果|
|---|---|
|30 天|快速配置： <ul><li>基本管理员保护。</li><li>日志记录和分析。</li><li>基本标识保护。</li></ul> <p> 租户配置。 <p> 准备利益干系人。|
|90 天|高级保护： <ul><li>管理员帐户。</li><li>数据和用户帐户。</li></ul> <p> 对合规性、威胁和用户需求的可见性。 <p> 修改和实施默认策略和保护。|
|满足|调整和优化主要策略和控件。 <p> 将保护扩展到本地依赖项。 <p> 与业务和安全流程集成 (法律、内幕威胁等 ) 。|
|

## <a name="30-days--powerful-quick-wins"></a>30天—功能强大的快速 wins
<a name="Thirdaydays"> </a>

这些任务可快速完成，对用户产生的影响很小。

****

|区域|任务|
|---|---|
|安全管理|<ul><li>检查安全得分并记下您当前的分数 (<https://securescore.office.com>) 。</li><li>打开 Office 365 的审核日志记录。 请参阅 [搜索审核日志](../../compliance/search-the-audit-log-in-security-and-compliance.md)。</li><li>[配置 Microsoft 365 以提高安全性](tenant-wide-setup-for-increased-security.md)。</li><li>定期查看 Microsoft 365 安全中心和云应用安全中的仪表板和报告。</li></ul>|
|威胁防护|[将 microsoft 365 连接到 Microsoft 云应用安全](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) ，开始使用默认威胁检测策略对反常行为进行监视。 为异常检测构建基准需要七天时间。 <p>  对管理员帐户实施保护：<ul><li>对管理员活动使用专用的管理员帐户。</li><li>为管理员帐户强制执行多重身份验证 (MFA) 。</li><li>使用 [高度安全的 Windows 10 设备](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) 进行管理活动。</li></ul>|
|标识和访问管理|<ul><li>[启用 Azure Active Directory 标识保护](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。</li><li>对于联合标识环境，强制执行帐户安全 (密码长度、年龄、复杂性等 ) 。</li></ul>|
|信息保护|查看示例信息保护建议。 信息保护需要跨整个组织进行协作。 开始使用这些资源：<ul><li>[针对 GDPR 的 Office 365 信息保护](https://aka.ms/o365gdpr)</li><li>[配置具有三层保护的团队](../../solutions/configure-teams-three-tiers-protection.md) (包括共享、分类、数据丢失防护和 Azure 信息保护) </li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90天—增强型保护
<a name="Ninetydays"> </a>

虽然这些任务需要多花一点时间来计划和实现，但会显著改善安全态势。

****

|区域|任务|
|---|---|
|安全管理|<ul><li>检查安全分数以了解针对你的环境的建议操作 (<https://securescore.office.com>) 。</li><li>继续定期查看 Microsoft 365 安全中心、云应用安全性和 SIEM 工具中的仪表板和报告。</li><li>查找并实施软件更新。</li><li>使用[Office 365 威胁智能](office-365-ti.md))  (包含的[攻击模拟器](attack-simulator.md)进行攻击模拟，以进行 spear 网络钓鱼、密码喷涂和强力密码攻击。</li><li>通过查看 "调查" 选项卡上的 "云应用安全" (中的内置报告来查找共享风险) 。</li><li>检查 [合规性管理器](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager) 以查看适用于您的组织 (的规章的状态，如 GDPR、NIST 800-171) 。</li></ul>|
|威胁防护|为管理员帐户实施增强的保护： <ul><li>为管理员活动配置 (PAWs) 的 [特权访问工作站](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) 。</li><li>配置 [AZURE AD 特权标识管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。</li><li>配置安全信息和事件管理 (SIEM) 工具以收集 Office 365、云应用安全性和其他服务（包括 AD FS）中的日志记录数据。 审核日志仅存储90天的数据。 通过在 SIEM 工具中捕获此数据，可以将数据存储在更长的时间段中。</li></ul>|
|标识和访问管理|<ul><li>为所有用户启用和强制进行 MFA。</li><li>实现一组 [条件访问和相关策略](microsoft-365-policies-configurations.md)。</li></ul>|
|信息保护| 修改和实施信息保护策略。 这些资源包括示例： <ul><li>[针对 GDPR 的 Office 365 信息保护](https://aka.ms/o365gdpr)</li><li>[配置具有三层保护的 Teams](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> 使用 Microsoft 365 中存储的数据丢失防护策略和监视工具来存储在 Microsoft (365 中的数据，而不是云应用安全) 。 <p> 将云应用安全性与 Microsoft 365 结合使用，以获取高级警报 (功能，而不是数据丢失防护) 。|
|

## <a name="beyond"></a>满足
<a name="Beyond"> </a>

这些是在以前的工作上构建的重要安全措施。

****

|区域|任务|
|---|---|
|安全管理|<ul><li>使用安全分数 () 继续规划下一步操作 <https://securescore.office.com> 。</li><li>继续定期查看 Microsoft 365 安全中心、云应用安全性和 SIEM 工具中的仪表板和报告。</li><li>继续查找并实施软件更新。</li><li>将电子数据展示集成到您的法律和威胁响应流程中。</li></ul>|
|威胁防护|<ul><li>对本地 (AD、AD FS) 上的标识组件实施 [安全的特权访问](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) 。</li><li>使用云应用安全来监视内幕威胁。</li><li>使用云应用安全性发现卷影 IT SaaS 使用情况。</li></ul>|
|标识和访问管理|<ul><li>优化策略和操作过程。</li><li>使用 Azure AD 标识保护来确定内幕威胁。</li></ul>|
|信息保护|优化信息保护策略： <ul><li>Microsoft 365 和 Office 365 敏感标签和数据丢失防护 (DLP) 或 Azure 信息保护。</li><li>云应用安全策略和警报。</li></ul>|
|

另请参阅： [如何缓解快速 cyberattacks，如 Petya 和 WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)。
