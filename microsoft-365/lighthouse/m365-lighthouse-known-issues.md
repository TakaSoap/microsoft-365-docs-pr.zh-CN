---
title: Microsoft 365 Lighthouse的已知问题
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
- M365-Lighthous
search.appverid: MET150
description: 有关托管服务提供商 (使用Microsoft 365 Lighthouse) MSP，请参阅 Lighthouse 的已知问题列表（按功能区域列出）。
ms.openlocfilehash: 3be71d225f1aa9974bb73e3b2e9d421ea81e16fa
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824335"
---
# <a name="known-issues-with-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouse的已知问题

本文列出了按功能区域Microsoft 365 Lighthouse的已知问题。 有关 Lighthouse 的详细信息，请参阅[Microsoft 365 Lighthouse概述](m365-lighthouse-overview.md)。

## <a name="users"></a>用户

| 问题 | 说明 | 解决方案 |
| ---------------- | ---------------- | ---------------- |
| **Helpdesk 代理无法重置用户密码** | 托管服务提供商 (MSP) 支持代理组成员的技术人员无法为客户租户中的用户重置密码。 当他们尝试重置用户的密码时，他们会收到以下错误消息：“你无权执行此操作。 [了解详细信息](m365-lighthouse-configure-portal-security.md)” | 若要解决权限问题，Helpdesk 代理应使用Microsoft 365 管理中心或Azure Active Directory重置密码。 |

## <a name="devices"></a>设备

| 问题 | 说明 | 解决方案 |
| ---------------- | ---------------- | ---------------- |
| **将显示已删除的策略** | 从Intune中删除设备符合性策略后，它将暂时在 Lighthouse 中继续可见。 如果 MSP 技术人员尝试执行包含已删除策略的策略比较，技术人员会收到以下错误：“出现问题。 请刷新页面，然后重试。 | 若要解决此错误，请从策略比较中清除已删除的策略，并仅比较现有策略。 |

## <a name="threat-management"></a>威胁管理

| 问题 | 说明 | 解决方案 |
| ---------------- | ---------------- | ---------------- |
| **缺少威胁名称** | 当 MSP 技术人员从威胁管理页查看威胁列表时，某些威胁可能缺少威胁的名称。 当最近从Intune中删除检测到威胁的设备时，将发生这种情况。 | 此问题将在 48 小时内解决。 无需执行其他步骤。 |

## <a name="baselines"></a>基线

| 问题 | 说明 | 解决方案 |
| ---------------- | ---------------- | ---------------- |
| **比较块旧式身份验证和 MFA 部署步骤时出现冲突的设置** | 如果客户租户已部署阻止旧式身份验证和 MFA 部署步骤之一，则比较测试会错误地将这些设置描述为冲突。 | 无需解决方法。 这些设置实际上不会发生冲突，客户租户中的用户也不会受到影响。 |

## <a name="windows-365"></a>Windows 365

| 问题 | 说明 | 解决方案 |
| ---------------- | ---------------- | ---------------- |
| **重试预配错误** | 尝试重试云电脑预配时，MSP 技术人员会收到“你无权执行此操作”错误消息。 | 若要解决此问题，请登录到客户租户，然后从 Microsoft Endpoint Manger 管理中心重新预配云电脑。 有关说明，请参阅 [重新预配云电脑](/windows-365/enterprise/reprovision-cloud-pc)。 |

## <a name="audit-logs"></a>审核日志


| 问题 | 说明 | 解决方案 |
|--|--|--|
| **审核日志中未列出停用和重新激活操作** | Lighthouse 中的“审核日志”页当前未报告以下活动： <ul><li>名称：offboardTenant \| 操作：停用客户</li> <li>名称：resetTenantOnboardingStatus \| 操作：反应客户</li></ul> | 没有解决方法，但我们正在努力修复。 在服务中部署修补程序后，这些活动将显示在审核日志中。 |
| **筛选器未显示所有用户** | 当 MSP 技术人员尝试使用 **“发起** 者”进行筛选时，筛选器下不会完全显示所有用户主体名称 (UPN) （与发起生成审核日志的操作的技术人员的电子邮件 ID 相对应）的列表。<br><br>请注意，审核日志本身将完全显示;仅影响使用 **“发起** 者”筛选它们的功能。 | 没有解决方法，但我们正在努力修复。 在服务中部署修补程序后，筛选器将还原为其预期行为 - 显示要筛选的 UPN 的完整列表。 |

## <a name="delegated-admin-privileges-dap"></a>委派的管理员权限 (DAP) 

| 问题 | 说明 | 解决方案 |
| ---------------- | ---------------- | ---------------- |
| **更改 DAP 角色时的权限延迟** | 如果将 MSP 技术人员添加到管理员代理或 Helpdesk 代理组或从中删除，则在 Lighthouse 中反映相应权限可能会出现延迟。 | 此问题将在 30 分钟内解决。 无需执行其他步骤。 |

## <a name="granular-delegated-admin-privileges-gdap"></a>GDAP)  (粒度委派的管理员权限

> [!NOTE]
> GDAP 目前处于 [技术预览](/partner-center/announcements/2022-february#6) (公共预览版) 允许合作伙伴在 GDAP 正式发布之前分配精细权限。

目前，需要 DAP 才能将客户加入 Lighthouse。 我们还建议与客户建立 GDAP，以实现更安全的委派访问。 虽然 DAP 和 GDAP 共存，但 GDAP 将优先于两个模型所在的客户。 很快，只有 GDAP (且没有 DAP) 的客户将能够加入 Lighthouse。<br><br>

| 问题 | 说明 | 解决方案 |
| ---------------- | ---------------- | ---------------- |
| **Lighthouse 中的各种 GDAP 权限问题** | 某些 GDAP 角色本身不会像在单租户体验中那样授予对 Lighthouse 中客户数据的相同级别的访问权限。 如果将以下任一角色单独分配 (，则这些角色不是与其他 GDAP 角色结合使用，) 给 MSP 技术人员，则可能会遇到错误，包括：<ul><li>GDAP 安全管理员无法查看风险用户、消除风险或确认 Lighthouse 中遭到入侵的用户。</li><li>GDAP 安全读取器无法在 Lighthouse 中查看有风险的用户。</li><li>在 Lighthouse 中尝试查看服务运行状况时，GDAP 全局管理员会看到错误消息。</li><li>GDAP 全局管理员在 Lighthouse 中部署部署计划步骤时遇到问题。</li></ul> | 解决方法是根据对客户数据的访问级别，将 GDAP 角色的组合分配给 MSP 技术人员。 有关建议使用 Lighthouse 的 GDAP 角色的列表，请参阅[Microsoft 365 Lighthouse中的权限概述](m365-lighthouse-overview-of-permissions.md)。<br><br>对于即使 GDAP 全局管理员权限也不允许在 Lighthouse 中使用功能的问题，解决方法是从客户租户访问相应的管理中心来管理客户 (例如，从客户租户访问Microsoft 365 管理中心以检查服务运行状况) 。 有关如何修改 GDAP 关系的说明，请参阅 [获取管理客户服务的精细管理员权限 - 合作伙伴中心](/partner-center/gdap-obtain-admin-permissions-to-manage-customer)。 |

## <a name="localization"></a>本地化

| 问题 | 说明 | 解决方案 |
| ---------------- | ---------------- | ---------------- |
| **翻译问题** | 当浏览器的语言或 Lighthouse 中的语言选择是英语以外的任何内容时，用户可能会遇到语言翻译问题。 | 若要最大程度地减少 Lighthouse 中的翻译问题，请确保浏览器的语言选择与 Lighthouse 门户中的语言设置匹配。 若要更改 Lighthouse 中的语言选择，请登录 Lighthouse，然后选择页面顶部的齿轮图标以打开门户设置页，选择 **“语言 + 区域**”，然后选择适当的语言和区域格式。 |

## <a name="related-content"></a>相关内容

[Microsoft 365 Lighthouse常见问题解](m365-lighthouse-faq.yml)答 (文章) \
[排查和解决Microsoft 365 Lighthouse (文章) \ 中的问题和错误消息](m365-lighthouse-troubleshoot.md)
[获取Microsoft 365 Lighthouse (文章的帮助和支持](m365-lighthouse-get-help-and-support.md)) 
