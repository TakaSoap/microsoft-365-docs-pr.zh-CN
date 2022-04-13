---
title: 排查和解决Microsoft 365 Lighthouse中的问题和错误消息
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
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (使用Microsoft 365 Lighthouse) 的 MSP，请获取有关排查和解决错误消息和问题的帮助。
ms.openlocfilehash: 1126db76129a0f3cf6b65921a6e731f02d7311d3
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824061"
---
# <a name="troubleshoot-and-resolve-problems-and-error-messages-in-microsoft-365-lighthouse"></a>排查和解决Microsoft 365 Lighthouse中的问题和错误消息

本文介绍在使用Microsoft 365 Lighthouse时可能遇到的错误消息和问题，并提供解决这些错误消息的疑难解答步骤。

## <a name="partner-onboarding"></a>合作伙伴加入

### <a name="message-when-trying-to-access-lighthouse-microsoft-365-lighthouse-doesnt-support-indirect-providers-at-this-time-you-must-be-an-indirect-reseller-or-direct-bill-partner-to-use-this-service"></a>尝试访问 Lighthouse 时的消息：“Microsoft 365 Lighthouse目前不支持间接提供商，必须是间接经销商或直接账单合作伙伴才能使用此服务”

**原因：** 你试图以间接计费合作伙伴的身份访问 Lighthouse。 目前，Lighthouse 仅支持间接经销商和直接计费合作伙伴。

**分辨率：** 有关资格和要求的完整列表，请参阅 [Microsoft 365 Lighthouse的要求](m365-lighthouse-requirements.md)。 如果你不是间接提供商，并且认为收到此消息时出错，请联系支持部门。 有关详细信息，请参阅[获取Microsoft 365 Lighthouse的帮助和支持](m365-lighthouse-get-help-and-support.md)。

### <a name="message-when-trying-to-access-lighthouse-you-must-be-an-indirect-reseller-or-direct-bill-partner-to-use-this-service"></a>尝试访问 Lighthouse 时的消息：“必须是间接经销商或直接计费合作伙伴才能使用此服务”

**原因：** 你试图访问 Lighthouse，但不是 Microsoft 合作伙伴。 必须以间接经销商或直接计费合作伙伴的身份注册云解决方案提供商 (CSP) 计划，才能使用 Lighthouse。

**分辨率：** 有关资格和要求的完整列表，请参阅 [Microsoft 365 Lighthouse的要求](m365-lighthouse-requirements.md)。 如果有资格访问 Lighthouse，并且认为收到此消息时出错，请联系支持部门。 有关详细信息，请参阅[获取Microsoft 365 Lighthouse的帮助和支持](m365-lighthouse-get-help-and-support.md)。

### <a name="message-when-signing-in-to-lighthouse-accept-the-partner-amendment"></a>登录 Lighthouse 时的消息：“接受合作伙伴修正案”

**原因：** 在合作伙伴租户中的全局管理员签署合作伙伴修正案之前，你曾尝试访问 Lighthouse。

**分辨率：** 全局管理员必须登录 Lighthouse 并接受合作伙伴修订，然后才能在 Lighthouse 中访问和工作。 如果此错误在全局管理员签署修订后仍然存在，请联系支持人员。 有关详细信息，请参阅[获取Microsoft 365 Lighthouse的帮助和支持](m365-lighthouse-get-help-and-support.md)。

## <a name="customer-tenant-onboarding"></a>客户租户载入  

### <a name="customer-tenants-show-a-status-other-than-active-in-the-tenant-list"></a>客户租户在租户列表中显示“活动”以外的状态  

**原因：** 客户租户不符合以下条件：

- 必须为托管服务提供程序设置委派的访问权限 (MSP) 才能管理客户租户*
- 必须至少有一个Microsoft 365 商业高级版、Microsoft 365 E3或Windows 365 商业版许可证
- 必须拥有不超过 1000 个许可用户 

**分辨率：** 下表描述了需要操作的不同租户状态，并说明了如何解决这些状态。

*委派的管理员权限 (DAP) 需要将客户载入 Lighthouse。 我们还建议与客户建立 GDAP)  (粒度委派的管理员权限，以实现更安全的委派访问。 虽然 DAP 和 GDAP 共存，但 GDAP 将优先于两个模型所在的客户。 很快，只有 GDAP (且没有 DAP) 的客户将能够加入 Lighthouse。

| 状态 | 说明 | 解决方案 |
|--|--|--|
| 无效 | 租户是应 MSP 的要求卸载的，并且不再在 Lighthouse 中进行管理。 | 需要重新激活租户。 在 **“租户”** 页上，选择要重新激活的租户旁边)  (更多操作的三个点，然后选择 **“激活租户**”。 初始客户数据可能需要 24-48 小时才能显示在 Lighthouse 中。 |
| 不符合条件 - 未设置 DAP 或 GDAP | 没有使用 Lighthouse 所需的租户设置 DAP 或 GDAP 管理员权限。 | 在 Microsoft 合作伙伴中心设置 DAP 或 GDAP 管理员权限。 |
| 不符合条件 - 缺少所需的许可证 | 租户缺少所需的许可证。 他们至少需要一个Microsoft 365 商业高级版、Microsoft 365 E3或Windows 365 商业版许可证。 | 确保租户至少分配了一个Microsoft 365 商业高级版、Microsoft 365 E3或Windows 365 商业版许可证。 |
| 不符合条件 - 超出用户计数 | 该租户最多有 1000 个 Lighthouse 允许的许可用户。 | 验证租户的许可用户不超过 1000 个。 |
| 不符合条件 - 异地检查失败 | 你和你的客户不驻留在同一地理区域，这是 Lighthouse 所必需的。 | 验证客户是否驻留在地理区域中。 如果没有，则无法在 Lighthouse 中管理租户。 |
| 正在处理中 | Lighthouse 发现了该租户，但仍在载入租户的过程中。 | 允许 Lighthouse 48 小时完成租户的载入。 |

如果确认客户租户符合载入条件，并且它们在 Lighthouse 中仍未显示为 **“活动”** ，请联系支持部门。 有关详细信息，请参阅[获取Microsoft 365 Lighthouse的帮助和支持](m365-lighthouse-get-help-and-support.md)。

## <a name="access-and-permissions"></a>访问权限和权限

### <a name="message-when-trying-to-access-lighthouse-not-authorized-or-insufficient-privileges-or-access-restriction-insufficient-or-lack-of-permissions-is-causing-access-restriction"></a>尝试访问 Lighthouse 时的消息：“未授权”或“权限不足”或“访问限制：权限不足或缺乏权限导致访问限制” 

**原因：** 你不属于Azure AD中正确的安全组，或者尚未在合作伙伴中心中分配正确的角色来访问 Lighthouse。

**分辨率：** 确保具有适当权限的合作伙伴租户的管理员已将你分配到Azure AD中正确的 GDAP 安全组，并在合作伙伴中心中为你分配了正确的角色。 此外，请记住，Lighthouse 中的某些操作要求你成为全局管理员。若要详细了解 GDAP 角色以及每个角色可以执行哪些操作，请参阅[Microsoft 365 Lighthouse中的权限概述](m365-lighthouse-overview-of-permissions.md)。 有关 GDAP 的所有Azure AD内置角色和权限的详细说明，请[参阅Azure AD内置角色](/azure/active-directory/roles/permissions-reference)。

对于具有 DAP 关系的客户，合作伙伴管理员需要将你分配给合作伙伴中心的管理员代理或 Helpdesk 代理角色。 有关所有合作伙伴中心角色和权限的详细说明，请参阅 [向用户分配角色和权限](/partner-center/permissions-overview)。

### <a name="i-dont-see-complete-data-in-certain-areas-of-lighthouse-or-i-cant-perform-certain-tasks-or-i-cant-access-certain-tenants"></a>我在 Lighthouse 的某些区域看不到完整数据，或者无法执行某些任务，或者无法访问某些租户

**原因：** 根据分配给所处Azure AD安全组的角色，GDAP 访问受到限制。

**分辨率：** 确保具有相应权限的合作伙伴租户的管理员已将你分配到Azure AD中正确的 GDAP 安全组。 此外，请记住，Lighthouse 中的某些操作要求你成为全局管理员。若要详细了解 GDAP 角色以及每个角色可以执行哪些操作，请参阅[Microsoft 365 Lighthouse中的权限概述](m365-lighthouse-overview-of-permissions.md)。 有关 GDAP 的所有Azure AD内置角色和权限的详细说明，请[参阅Azure AD内置角色](/azure/active-directory/roles/permissions-reference)。

## <a name="customer-tenant-management"></a>客户租户管理  

### <a name="customer-tenant-has-no-data-showing-in-lighthouse"></a>客户租户没有在 Lighthouse 中显示的数据

**原因：** 在租户载入完成之前，你正在尝试在 Lighthouse 中查看数据。

**分辨率：** 初始客户数据可能需要 24-48 小时才能显示在 Lighthouse 中。 如果载入租户超过 48 小时，但仍无法查看或加载租户数据，或者无法查看或加载以前能够查看或加载的数据，请联系支持部门。 有关详细信息，请参阅[获取Microsoft 365 Lighthouse的帮助和支持](m365-lighthouse-get-help-and-support.md)。 准备好提供相关的网络日志和可能已修改的任何选项的列表。

### <a name="customer-tenant-data-isnt-updating-after-making-changes-in-the-customer-tenant"></a>客户租户数据在客户租户中进行更改后未更新

**原因：** 在客户租户中所做的更改可能需要长达 4 小时才能与 Lighthouse 中的客户租户数据同步。

**分辨率：** 如果超过 4 小时，并且 Lighthouse 中的客户租户数据仍未更新，请联系支持部门。 有关详细信息，请参阅[获取Microsoft 365 Lighthouse的帮助和支持](m365-lighthouse-get-help-and-support.md)。 准备好提供客户租户信息。

### <a name="message-when-applying-a-baseline-to-a-customer-tenant-process-error-occurred"></a>向客户租户应用基线时的消息：“发生进程错误”  

**原因：** 未成功完成客户租户中Microsoft Intune的配置。

**分辨率：** 验证是否已完成客户租户中Intune的基本配置步骤。 如果在验证客户租户的Intune配置是否已完成后，问题仍然存在，请联系支持部门。 有关详细信息，请参阅[获取Microsoft 365 Lighthouse的帮助和支持](m365-lighthouse-get-help-and-support.md)。

### <a name="cant-access-partner-tenant-data-in-lighthouse"></a>无法访问 Lighthouse 中的合作伙伴租户数据

**原因**：Lighthouse 仅支持查看和管理 *客户* 租户。 它目前不支持查看和管理 *合作伙伴* 租户。

**分辨率：** 继续使用你一直使用的任何方法来查看和管理合作伙伴租户。

## <a name="device-and-threat-management"></a>设备和威胁管理 

### <a name="i-dont-see-any-customer-tenant-data-on-the-device-compliance-and-threat-management-pages-of-lighthouse"></a>在 Lighthouse 的设备符合性和威胁管理页上看不到任何客户租户数据

**原因 1：** 客户租户尚未完成加入Intune。 客户租户数据在 Lighthouse 的设备符合性或威胁管理页上不可用，除非客户租户已完成加入到Intune。

**分辨率：** 验证您尝试查看数据的客户租户是否已完成加入Intune。 Intune完成载入后，允许 4 小时设备数据显示在 Lighthouse 中。

**原因 2：** 客户租户最近已载入 Lighthouse，数据仍在 Lighthouse 中加载。

**分辨率：** 将客户租户载入 Lighthouse 后，允许 24-48 小时显示初始客户数据。

**原因 3：** 客户租户设备是新的，设备数据仍在 Lighthouse 中加载。

**分辨率：** 添加租户设备时，允许在 Lighthouse 中显示设备数据 4 小时。

如果按照解决说明操作后，设备符合性和威胁管理页上仍未显示数据，请联系支持部门。 有关详细信息，请参阅[获取Microsoft 365 Lighthouse的帮助和支持](m365-lighthouse-get-help-and-support.md)。

## <a name="related-content"></a>相关内容

[Microsoft 365 Lighthouse (](m365-lighthouse-known-issues.md)文章) \ 的已知问题
[Microsoft 365 Lighthouse常见问题解](m365-lighthouse-faq.yml)答 (文章) \
[获取Microsoft 365 Lighthouse (文章的帮助和支持](m365-lighthouse-get-help-and-support.md)) 
