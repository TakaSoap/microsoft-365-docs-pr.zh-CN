---
title: 调查异常检测警报
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 调查异常检测警报。
ms.openlocfilehash: 6797cdcbfd2a2d3c32768a158a5f8cd0fc579d56
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420117"
---
# <a name="investigate-anomaly-detection-alerts"></a>调查异常检测警报

 Microsoft 应用治理提供针对恶意活动的安全检测和警报。 本指南旨在为你提供有关每个警报的一般和实用信息，以帮助你完成调查和修正任务。 本指南包含有关触发警报的条件的一般信息。 由于异常检测本质上不可确定，因此只有当存在偏离规范的行为时，才会触发异常检测。 最后，由于一些警报可能处于预览状态，因此请定期查看官方文档以了解更新的警报状态。

## <a name="mitre-attck"></a>MITRE ATT&CK

为了更轻松地映射 Microsoft 应用治理警报和熟悉的 MITRE ATT&CK 矩阵之间的关系，我们已按其相应的 MITRE ATT&CK 策略对警报进行了分类。 借助此附加参考，可以更轻松地了解触发 Microsoft 应用程序安全和治理警报时可能使用的可疑攻击技术。

本指南提供有关调查和修正以下类别中的 Microsoft 应用治理警报的信息。

- 初始访问
- 执行
- 持久性
- 特权提升
- 防御规避
- 凭据访问
- 集合
- 外泄
- 影响

## <a name="security-alert-classifications"></a>安全警报分类

经过适当调查后，所有 Microsoft 应用治理警报都可以归类为以下活动类型之一:

- 真阳性(TP): 针对确认为恶意活动的警报。
- 良性真阳性(B-TP): 针对可疑但非恶意活动的警报，例如渗透测试或其他授权的可疑操作。
- 假阳性(FP): 针对非恶意活动的警报。

## <a name="general-investigation-steps"></a>一般调查步骤

在调查任何类型的警报时，请使用以下一般准则，从而在应用推荐操作之前更清楚地了解潜在威胁。

- 查看应用严重性级别，并与租户中的其余应用进行比较。 这样的查看将帮助识别租户中会带来更大风险的应用。
- 如果识别出 TP，请查看所有应用活动以了解影响。 例如，查看以下应用信息:

  - 授予访问权限的范围
  - 异常行为  
  - IP 地址和位置

## <a name="initial-access-alerts"></a>初始访问警报

本部分介绍了表明恶意应用可能试图保持其在组织中的立足点的警报。  

### <a name="encoded-app-name-with-suspicious-consent-scopes"></a>具有可疑同意范围的已编码应用名称

**严重性:** 中等

**说明**: 此检测会识别具有字符(例如 Unicode 或已编码字符)的 OAuth 应用，其针对可疑同意范围进行请求并通过图形 API 访问用户邮件文件夹。 此警报可能表明试图将恶意应用伪装成已知且受信任的应用的行为，以便攻击者可以误导用户同意恶意应用。

**TP 还是 FP?**

- **TP**: 如果你可以确认 OAuth 应用已使用从未知源传递的可疑范围对显示名称进行编码，则表明为真阳性。  

  **推荐操作**: 查看此应用请求的权限级别以及授予访问权限的用户。 根据调查，你可以选择禁止访问此应用。

  要禁止访问应用，请在 OAuth 应用页面中，在要禁止应用显示的行中，选择禁用图标。 你可以选择是否希望告知用户其安装和授权的应用已被禁用。 此通知会告知用户应用将被禁用，且他们将无法访问已连接应用。 如果不希望告知用户，请取消选择“在对话框中通知授予此禁止应用访问权限的用户”。 我们建议你告知应用用户其应用即将被禁止使用。

- **FP**: 如果你要确认应用具有已编码名称，但在组织中却具有合法的商业用途。

  **推荐操作**: 关闭警报。

#### <a name="understand-the-scope-of-the-breach"></a>了解泄露范围

请遵循如何 [调查危险的 OAuth 应用](/cloud-app-security/investigate-risky-oauth) 的教程。

### <a name="oauth-app-with-read-scopes-have-suspicious-reply-url"></a>具有读取范围的 OAuth 应用具有可疑的“回复”URL

**严重性:** 中等

**说明**: 此检测会识别只具有“读取”范围(例如 User.Read、People.Read、Contacts.Read、Mail.Read、Contacts.Read.Shared)、通过图形 API 重定向到可疑的“回复”URL 的 OAuth 应用。 此活动试图表明具有较低权限(例如“读取”范围)的恶意应用可能被用于进行用户帐户侦查。

**TP 还是 FP?**

- **TP**: 如果你能够确认具有读取范围的 OAuth 应用从未知源传递并重定向到可疑 URL，则表明为真阳性。

  **推荐操作**: 查看应用请求的“回复”URL 和范围。 根据调查，你可以选择禁止访问此应用。 查看此应用请求的权限级别以及授予访问权限的用户。

  要禁止访问应用，请在 OAuth 应用页面中，在要禁止应用显示的行中，选择禁用图标。 你可以选择是否希望告知用户其安装和授权的应用已被禁用。 此通知会告知用户应用将被禁用，且他们将无法访问已连接应用。 如果不希望告知用户，请取消选择“在对话框中通知授予此禁止应用访问权限的用户”。 我们建议你告知应用用户其应用即将被禁止使用。

- **B-TP**: 如果经过调查，你可以确认此应用在组织中具有合法的商业用途。

  **推荐操作**: 关闭警报。

#### <a name="understand-the-scope-of-the-breach"></a>了解泄露范围 

1. 查看应用完成的所有活动。
1. 如果你怀疑某个应用可疑，我们建议你调查该应用在不同应用商店中的名称和“回复”URL。 在检查应用商店时，请重点关注以下类型的应用:
   - 最近创建的应用。
   - 具有可疑“回复”URL 的应用
   - 最近未更新的应用。 缺少更新可能表明该应用不再获得支持。
1. 如果你仍然怀疑某个应用可疑，可以联机研究应用名称、发布者名称以及“回复”URL  

## <a name="persistence-alerts"></a>持久性警报

本部分介绍了表明恶意行动者可能试图保持其在组织中的立足点的警报。

### <a name="app-with-suspicious-oauth-scope-creates-inbox-rule"></a>具有可疑 OAuth 范围的应用创建收件箱规则  

**严重性:** 中等

**MITRE ID 的**: T1137.005、T1114  

此检测会识别同意可疑范围、创建可疑的收件箱规则，然后通过图形 API 访问用户邮件文件夹和邮件的 OAuth 应用。 收件箱规则(例如将所有或特定电子邮件转发到另一电子邮件帐户)以及访问电子邮件并发送到另一电子邮件帐户的图形调用可能会试图泄露组织中的信息。  

**TP 还是 FP?**

- **TP**: 如果你可以确认收件箱规则由具有从未知源传递的可疑范围的 OAuth 第三方应用创建，则表明为真阳性。

  **推荐操作**: 禁用和删除应用，重置密码，并删除收件箱规则。

  请遵循如何使用 Azure Active Directory 重置密码的教程以及如何删除收件箱规则的教程。

- **FP**: 如果你可以确认应用出于合法原因为新的或个人外部电子邮件帐户创建收件箱规则。

  **推荐操作**: 关闭警报。

#### <a name="understand-the-scope-of-the-breach"></a>了解泄露范围

1. 查看应用完成的所有活动。
1. 查看应用授予的范围。
1. 查看应用创建的收件箱规则操作和条件。

## <a name="collection-alerts"></a>集合警报

本部分介绍了表明恶意行动者可能试图从组织收集与其目标相关的数据的警报。

### <a name="app-made-anomalous-graph-calls-to-read-e-mail"></a>应用执行异常图形调用以读取电子邮件

**严重性:** 中等

**MITRE ID**: T1114

此检测会识别业务线(LOB) OAuth 应用通过图形 API 访问异常大量用户的邮件文件夹和邮件的时间，这可能表明试图泄露组织信息的行为。

**TP 还是 FP?**

- **TP**: 如果你可以确认异常图形活动由业务线(LOB) OAuth 应用执行，则表明为正阳性。

  **推荐操作**: 暂时禁用应用并重置密码，然后重启应用。

  请遵循如何使用 Azure Active Directory 重置密码的教程。

- **FP**： 如果你可以确认应用旨在执行异常大量的图形调用。

  **推荐操作**: 关闭警报。

#### <a name="understand-the-scope-of-the-breach"></a>了解泄露范围

1. 查看此应用执行的事件的活动日志，从而更好地了解其他读取电子邮件并尝试收集用户敏感电子邮件信息的图形活动。
1. 监视向应用添加的意外凭据。
