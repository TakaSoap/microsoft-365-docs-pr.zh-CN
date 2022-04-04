---
title: 已知问题Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: 有关托管服务提供商 (MSP) 使用Microsoft 365 Lighthouse，请参阅按功能区域列出 Lighthouse 的已知问题。
ms.openlocfilehash: 3151937d4552da09c9cfd6808db2bad8bafbbc46
ms.sourcegitcommit: 33bc25167812b31c51cf096c728e3a5854e94f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2022
ms.locfileid: "64594656"
---
# <a name="known-issues-with-microsoft-365-lighthouse"></a>已知问题Microsoft 365 Lighthouse

本文列出了按功能区域Microsoft 365 Lighthouse已知问题。 有关 Lighthouse 的信息[，请参阅Microsoft 365 Lighthouse](m365-lighthouse-overview.md)。

## <a name="users"></a>用户

| 问题 | Description | 解决方案 |
| ---------------- | ---------------- | ---------------- |
| **支持人员代理无法重置用户密码** | 托管服务提供商 (MSP) 支持代理组的成员的技术人员无法为客户租户中的用户重置密码。 当他们尝试重置用户的密码时，收到以下错误消息："你无权这样做。 [了解更多信息](m365-lighthouse-configure-portal-security.md)" | 若要解决权限问题，支持人员代理应通过使用 Microsoft 365 管理中心 或 Azure Active Directory。 |

## <a name="devices"></a>设备

| 问题 | Description | 解决方案 |
| ---------------- | ---------------- | ---------------- |
| **将显示已删除的策略** | 在设备合规性策略从设备中删除Intune，它将暂时继续在 Lighthouse 中可见。 如果 MSP 技术人员尝试执行包含已删除策略的策略比较，则技术人员将收到以下错误："出现错误。 请刷新页面并重试。" | 若要解决错误，请从策略比较中清除已删除的策略，并仅比较现有策略。 |

## <a name="threat-management"></a>威胁管理

| 问题 | Description | 解决方案 |
| ---------------- | ---------------- | ---------------- |
| **威胁名称缺失** | 当 MSP 技术人员从"威胁管理"页查看威胁列表时，某些威胁可能缺少威胁的名称。 当最近从计算机中删除检测到威胁的设备时，Intune。 | 此问题将在 48 小时内解决。 无需其他步骤。 |

## <a name="baselines"></a>基线

| 问题 | Description | 解决方案 |
| ---------------- | ---------------- | ---------------- |
| **比较阻止旧版身份验证和 MFA 部署步骤时发生冲突的设置** | 如果客户租户已部署阻止旧版身份验证和 MFA 部署步骤之一，则比较测试会错误地将这些设置描述为冲突。 | 无需任何解决方法。 设置实际上不会发生冲突，并且客户租户中的用户不会受到影响。 |

## <a name="windows-365"></a>Windows 365

| 问题 | Description | 解决方案 |
| ---------------- | ---------------- | ---------------- |
| **重试设置错误** | MSP 技术人员在尝试重试预配云电脑时收到"你无权这样做"错误消息。 | 若要解决此问题，请登录到客户租户，然后从 Microsoft Endpoint Manger 管理中心重新预配云电脑。 有关说明，请参阅 [重新设置云电脑](/windows-365/enterprise/reprovision-cloud-pc)。 |

## <a name="audit-logs"></a>审核日志


| 问题 | Description | 解决方案 |
|--|--|--|
| **审核日志中未列出停用和重新激活操作** | 当前在 Lighthouse 的"审核日志"页上未报告以下活动： <ul><li>名称：offboardTenant \| 操作：停用客户</li> <li>名称：resetTenantOnboardingStatus \| 操作：反应客户</li></ul> | 没有解决方法，但我们正在努力修复此问题。 在服务中部署修复后，这些活动将显示在审核日志中。 |
| **筛选器未显示所有用户** | 当 MSP 技术人员尝试使用"启动者"进行筛选时，筛选器下不会完全显示所有用户主体名称 (UPN) （对应于启动生成审核日志的操作的技术人员的电子邮件 ID）的列表。<br><br>请注意，审核日志本身将完全显示;仅影响使用 **Initiated By 筛选** 它们的能力。 | 没有解决方法，但我们正在努力修复此问题。 在服务中部署修复后，筛选器将恢复其预期行为，即显示要筛选的 UPN 的完整列表。 |

## <a name="delegated-admin-privilegesdap"></a>DAP (委派管理员) 

| 问题 | Description | 解决方案 |
| ---------------- | ---------------- | ---------------- |
| **更改 DAP 角色时权限延迟** | 如果将 MSP 技术人员添加到管理员代理组或支持人员代理组，则反映 Lighthouse 内的适当权限可能会存在延迟。 | 该问题将在 30 分钟内解决。 无需其他步骤。 |

## <a name="granular-delegated-admin-privilegesgdap"></a>GDAP 策略的 (委派管理员) 

> [!NOTE]
> GDAP 目前处于公共[](/partner-center/announcements/2022-february#6) (预览版) ，以允许合作伙伴在 GDAP 公开发布之前分配具体权限。

目前，需要 DAP 才能将客户载入到 Lighthouse。 我们还建议与客户建立 GDAP，以实现更安全的委派访问。 虽然 DAP 和 GDAP 共存，但 GDAP 将优先用于这两种模型都适合的客户。 很快，仅具有 GDAP (且没有 DAP) 客户将能够载入 Lighthouse。<br><br>

| 问题 | Description | 解决方案 |
| ---------------- | ---------------- | ---------------- |
| **Lighthouse 中各种 GDAP 权限问题** | 某些 GDAP 角色本身不会像在单租户体验中一样授予对 Lighthouse 中客户数据的访问权限级别。 如果将以下任何角色 (分配给 MSP 技术人员，而不是与分配给 MSP) 的其他 GDAP 角色不一起分配，他们可能会遇到错误，包括：<ul><li>GDAP 安全管理员无法在 Lighthouse 内查看有风险的用户、消除风险或确认受到威胁的用户。</li><li>GDAP 安全读者无法在 Lighthouse 内查看有风险的用户。</li><li>GDAP 全局管理员在尝试在 Lighthouse 内查看服务运行状况时看到一条错误消息。</li><li>GDAP 全局管理员在 Lighthouse 内部署部署计划步骤时遇到问题。</li></ul> | 解决方法是，根据 MSP 技术人员所需的客户数据访问级别，将 GDAP 角色组合分配给他们。 有关使用 Lighthouse 的推荐 GDAP 角色的列表，请参阅 Overview [of permissions in Microsoft 365 Lighthouse](m365-lighthouse-overview-of-permissions.md)。<br><br>对于即使 GDAP 全局管理员权限也不允许在 Lighthouse 中使用功能的问题，解决方法是从客户租户访问相应的管理中心来管理客户 (例如，从客户租户访问 Microsoft 365 管理中心 以检查服务运行状况) 。 有关如何修改 GDAP 关系的说明，请参阅获取管理客户服务的细化管理员 [权限 - 合作伙伴中心](/partner-center/gdap-obtain-admin-permissions-to-manage-customer)。 |

## <a name="localization"></a>本地化

| 问题 | Description | 解决方案 |
| ---------------- | ---------------- | ---------------- |
| **翻译问题** | 当用户的浏览器语言或他们位于 Lighthouse 的语言选择是英语外的任何内容时，用户可能会遇到语言翻译问题。 | 若要最大程度地减少 Lighthouse 中的翻译问题，请确保浏览器的语言选择与 Lighthouse 门户中语言设置的语言选择相匹配。 若要在"灯楼"中更改语言选择，请登录到"Lighthouse"并选择页面顶部的齿轮图标以打开"门户设置"页面，选择"语言 **+** 区域"，然后选择相应的语言和区域格式。 |

## <a name="related-content"></a>相关内容

[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) \
[排查并解决本文](m365-lighthouse-troubleshoot.md)中的问题Microsoft 365 Lighthouse (错误消息) \
[获取本文中有关 Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md) (的帮助) 