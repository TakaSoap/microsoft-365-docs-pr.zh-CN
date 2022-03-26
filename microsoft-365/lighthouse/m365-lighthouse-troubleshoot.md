---
title: 排查并解决邮件中的问题和Microsoft 365 Lighthouse
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
description: 对于托管服务提供商 (使用) ，Microsoft 365 Lighthouse帮助排查并解决错误消息和问题。
ms.openlocfilehash: 49e6657815ed71476a3dc79d778f7e1fbacfa1f4
ms.sourcegitcommit: 9c8eca862a2f0fdca7a66c641e382e37fcaefa10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2022
ms.locfileid: "63775447"
---
# <a name="troubleshoot-and-resolve-problems-and-error-messages-in-microsoft-365-lighthouse"></a>排查并解决邮件中的问题和Microsoft 365 Lighthouse

本文介绍在使用本文时可能遇到的错误消息和Microsoft 365 Lighthouse并提供可采取故障排除步骤来解决这些问题。

## <a name="partner-onboarding"></a>合作伙伴载入

### <a name="message-when-trying-to-access-lighthouse-microsoft-365-lighthouse-doesnt-support-indirect-providers-at-this-time-you-must-be-an-indirect-reseller-or-direct-bill-partner-to-use-this-service"></a>尝试访问 Lighthouse 时显示的消息："Microsoft 365 Lighthouse目前不支持间接提供商，你必须是间接经销商或直接计费合作伙伴，使用此服务"

**原因：** 你尝试以间接帐单合作伙伴的方式访问 Lighthouse。 目前，Lighthouse 仅支持间接经销商和直接计费合作伙伴。

**解决方法：** 有关资格和要求的完整列表，请参阅 Requirements [for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md)。 如果你不是间接提供商，并且认为你收到此消息有误，请联系支持人员。 有关详细信息，请参阅获取[有关 Microsoft 365 Lighthouse 的帮助和支持](m365-lighthouse-get-help-and-support.md)。

### <a name="message-when-trying-to-access-lighthouse-you-must-be-an-indirect-reseller-or-direct-bill-partner-to-use-this-service"></a>尝试访问 Lighthouse 时的消息："你必须是间接经销商或直接计费合作伙伴，使用此服务"

**原因：** 你尝试访问 Lighthouse，并且不是 Microsoft 合作伙伴。 你必须以间接经销商或直接帐单合作伙伴云解决方案提供商 (云解决方案提供商计划) 注册，以使用 Lighthouse。

**解决方法：** 有关资格和要求的完整列表，请参阅 Requirements [for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md)。 如果符合访问 Lighthouse 的资格，并且认为你收到错误消息，请联系支持人员。 有关详细信息，请参阅获取[有关 Microsoft 365 Lighthouse 的帮助和支持](m365-lighthouse-get-help-and-support.md)。

### <a name="message-when-signing-in-to-lighthouse-accept-the-partner-amendment"></a>登录 Lighthouse 时的消息："接受合作伙伴修正"

**原因：** 在合作伙伴租户中的全局管理员签署合作伙伴修正之前，你尝试访问 Lighthouse。

**解决方法：** 全局管理员必须登录到 Lighthouse 并接受合作伙伴修正，然后才能访问和工作于 Lighthouse。 如果错误在全局管理员签署修正后仍然存在，请联系支持人员。 有关详细信息，请参阅获取[有关 Microsoft 365 Lighthouse 的帮助和支持](m365-lighthouse-get-help-and-support.md)。

## <a name="customer-tenant-onboarding"></a>客户租户载入  

### <a name="customer-tenants-show-a-status-other-than-active-in-the-tenant-list"></a>客户租户在租户列表中显示除"活动"外的状态  

**原因：** 你的客户租户不符合以下条件：

  - 必须为 Managed Service Provider (MSP) 设置委派的 DAP () 才能管理客户安全*
  - 必须至少有一个 Microsoft 365 商业高级版、Microsoft 365 E3 或 Windows 365 商业版许可证
  - 授权用户不能超过 1000 个 

**解决方法：** 下表介绍了需要操作的不同租户状态，并说明了如何解决这些问题。

*将客户 (到) 需要委派的 DAP 管理员权限。 我们还建议与客户建立粒度委派 (GDAP) ，以实现更安全的委派访问。 虽然 DAP 和 GDAP 共存，但 GDAP 将优先用于这两种模型都适合的客户。 很快，仅具有 GDAP (且没有 DAP) 客户将能够载入 Lighthouse。<br><br>


| 状态 | 说明 | 解决方案 |
|--|--|--|
| 非活动 | 应 MSP 的请求，租户已离开，不再在 Lighthouse 中进行管理。 | 需要重新激活租户。 在 **"租户"** 页面上，选择三个点 (要) 激活的租户旁边的其他操作，然后选择"激活 **租户"**。 初始客户数据可能需要 24–48 小时才能显示在 Lighthouse 中。 |
| 不符合 - 未设置 DAP 或 GDAP | 你没有设置租户的 DAP 或 GDAP 管理员权限，这是 Lighthouse 所需的。 | 在 Microsoft 合作伙伴中心设置 DAP 或 GDAP 管理员权限。 |
| 不符合资格 - 缺少所需的许可证 | 租户缺少所需的许可证。 他们至少需要一个Microsoft 365 商业高级版或Microsoft 365 E3许可证。 | 确保租户至少分配有一Microsoft 365 商业高级版或Microsoft 365 E3许可证。 |
| 不符合标准 - 已超出用户计数 | 该租户允许的许可证用户数超过 Lighthouse 允许的最多 1000 个。 | 验证租户拥有的许可用户数是否不超过 1000。 |
| 不符合资格 - 地理位置检查失败 | 你和客户不在同一地理区域，而该地理区域是 Lighthouse 所要求的。 | 验证客户是否驻留在地理区域。 如果没有，则你无法管理 Lighthouse 中的租户。 |
| 进程内 | Lighthouse 发现了租户，但仍在载入租户的过程中。 | 允许 Lighthouse 48 小时完成租户载入。 |

如果你确认你的客户租户符合载入条件，并且他们仍然未在 Lighthouse 中显示为活动租户，请联系支持人员。 有关详细信息，请参阅获取[有关 Microsoft 365 Lighthouse 的帮助和支持](m365-lighthouse-get-help-and-support.md)。

## <a name="access-and-permissions"></a>访问和权限

### <a name="message-when-trying-to-access-lighthouse-not-authorized-or-insufficient-privileges-or-access-restriction-insufficient-or-lack-of-permissions-is-causing-access-restriction"></a>尝试访问 Lighthouse 时的消息："未授权"、"权限不足"或"访问限制：权限不足或缺少权限导致访问限制" 

**原因：** 你不属于 Azure AD 中正确的安全组，或者你尚未在合作伙伴中心中分配正确的角色才能访问 Lighthouse。

**解决方法：** 请确保具有适当权限的合作伙伴租户中的管理员已分配给 Azure AD 中正确的 GDAP 安全组，并且你在合作伙伴中心中分配了正确的角色。 此外，请记住，Lighthouse 中的某些操作需要你成为全局管理员。若要了解有关 GDAP 角色以及每个角色可以执行哪些操作Microsoft 365 Lighthouse[门户安全性](m365-lighthouse-configure-portal-security.md)。 有关 GDAP 的所有Azure AD角色和权限的详细说明，请参阅Azure AD[角色](/azure/active-directory/roles/permissions-reference)。

对于具有 DAP 关系的客户，合作伙伴管理员将需要将你分配到合作伙伴中心中的管理员代理或支持代理角色。 有关所有合作伙伴中心角色和权限的详细说明，请参阅向用户分配 [角色和权限](/partner-center/permissions-overview)。

### <a name="i-dont-see-complete-data-in-certain-areas-of-lighthouse-or-i-cant-perform-certain-tasks-or-i-cant-access-certain-tenants"></a>我在 Lighthouse 的某些区域看不到完整数据，或者无法执行某些任务，或者无法访问某些租户

**原因：** 根据分配给你Azure AD安全组的角色，你拥有有限的 GDAP 访问权限。

**解决方法：** 请确保具有适当权限的合作伙伴租户中的管理员已将你分配到 Azure AD 中正确的 GDAP 安全Azure AD。 此外，请记住，Lighthouse 中的某些操作需要你成为全局管理员。若要了解有关 GDAP 角色以及每个角色可以执行哪些操作Microsoft 365 Lighthouse[门户安全性](m365-lighthouse-configure-portal-security.md)。 有关 GDAP 的所有Azure AD角色和权限的详细说明，请参阅Azure AD[角色](/azure/active-directory/roles/permissions-reference)。

## <a name="customer-tenant-management"></a>客户租户管理  

### <a name="customer-tenant-has-no-data-showing-in-lighthouse"></a>客户租户在 Lighthouse 中未显示任何数据

**原因：** 你正在尝试在租户载入完成之前在 Lighthouse 中查看数据。

**解决方法：** 初始客户数据可能需要 24–48 小时才能显示在 Lighthouse 中。 如果自载入租户以来已过 48 小时，但仍无法查看或加载租户数据，或者无法查看或加载之前能够查看的数据，请联系支持人员。 有关详细信息，请参阅获取[有关 Microsoft 365 Lighthouse 的帮助和支持](m365-lighthouse-get-help-and-support.md)。 准备提供相关网络日志和可能已修改的任何选项的列表。

### <a name="customer-tenant-data-isnt-updating-after-making-changes-in-the-customer-tenant"></a>客户租户数据在客户租户中进行更改后未更新

**原因：** 在客户租户内所做的更改可能需要 4 小时才能与 Lighthouse 中的客户租户数据同步。

**解决方法：** 如果已过 4 小时，但位于 Lighthouse 中的客户租户数据仍未更新，请联系支持人员。 有关详细信息，请参阅获取[有关 Microsoft 365 Lighthouse 的帮助和支持](m365-lighthouse-get-help-and-support.md)。 准备提供客户租户信息。

### <a name="message-when-applying-a-baseline-to-a-customer-tenant-process-error-occurred"></a>将基线应用于客户租户时显示的消息："发生进程错误"  

**原因：** 你未成功完成客户租户Microsoft Intune配置。

**解决方法：** 确认你已完成客户租户内 Intune 的基本配置步骤。 如果在确认客户租户的 Intune 配置已完成后问题仍然存在，请联系支持人员。 有关详细信息，请参阅获取[有关 Microsoft 365 Lighthouse 的帮助和支持](m365-lighthouse-get-help-and-support.md)。

### <a name="cant-access-partner-tenant-data-in-lighthouse"></a>无法访问 Lighthouse 中的合作伙伴租户数据

**原因**：Lighthouse 仅支持查看 *和管理客户* 租户。 它当前不支持查看和管理 *合作伙伴* 租户。

**解决方法：** 继续使用你用于查看和管理合作伙伴租户的任何方法。

## <a name="device-and-threat-management"></a>设备和威胁管理 

### <a name="i-dont-see-any-customer-tenant-data-on-the-device-compliance-and-threat-management-pages-of-lighthouse"></a>我在 Lighthouse 的设备合规性和威胁管理页面上看不到任何客户租户数据

**原因 1：** 客户租户尚未完成 Intune 载入。 客户租户数据在 Lighthouse 的设备合规性或威胁管理页面上不可用，直到客户租户完成载入到 Intune。

**解决方法：** 验证你尝试查看其数据的客户租户是否已完成载入 Intune。 Intune 中载入完成后，允许设备数据在 4 小时内显示在 Lighthouse 中。

**原因 2：** 客户租户最近已载入 Lighthouse，数据仍在 Lighthouse 中加载。

**解决方法：** 客户租户载入到 Lighthouse 后，允许 24–48 小时显示初始客户数据。

**原因 3：** 客户租户设备是新设备，并且设备数据仍在 Lighthouse 中加载。

**解决方法：** 添加租户设备后，允许设备数据在 4 小时后显示在 Lighthouse 中。

如果在按照解决方案说明操作后，数据仍不显示在设备合规性和威胁管理页面上，请联系支持人员。 有关详细信息，请参阅获取[有关 Microsoft 365 Lighthouse 的帮助和支持](m365-lighthouse-get-help-and-support.md)。

## <a name="related-content"></a>相关内容

[本文Microsoft 365 Lighthouse (](m365-lighthouse-known-issues.md)已知) \
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) \
[获取本文中有关 Microsoft 365 Lighthouse](m365-lighthouse-get-help-and-support.md) (的帮助) 