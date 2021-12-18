---
title: 在数据丢失防护策略中使用命名实体（预览版）
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 使用这些过程可以利用数据丢失防护策略中的命名实体
ms.openlocfilehash: 75a203b578217c5bbc1e8f67cf04b8d564735bd0
ms.sourcegitcommit: 282f3a58b8e11615b3e53328e6b89a6ac52008e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2021
ms.locfileid: "61560428"
---
# <a name="use-named-entities-in-your-data-loss-prevention-policies-preview"></a>在数据丢失防护策略中使用命名实体（预览版）

> [!IMPORTANT]
> 命名实体功能正在推出，并且将在可供你使用时显示在租户中。 在内容资源管理器和 DLP 策略创作流的数据丢失 (检查) 检查它们。 

在开始使用 [命名实体之前 ](named-entities-learn.md) ， (预览) 了解这些实体。

## <a name="before-you-begin"></a>准备工作

### <a name="skusubscriptions-licensing"></a>SKU/订阅许可

你必须拥有其中一个订阅

- 信息保护和治理
- Microsoft 365 E5 合规
- Office 365 E5
- Microsoft 365 E5

有关完整许可的详细信息，请参阅服务 [说明](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-classification-analytics-overview-content--activity-explorer)。

### <a name="permissions"></a>Permissions

在 DLP 策略中用于创建和编辑数据丢失防护 (的帐户) **DLP 合规性管理** 角色权限。 有关详细信息，请参阅向[用户授予对 Office 365 合规中心的访问权限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)


## <a name="supported-locations"></a>支持的位置

可以使用命名实体 SIT 和增强策略检测和保护以下位置中的敏感项目：

- SharePoint 网站
- OneDrive 账户
- Teams 聊天和通道消息
- 终结点 (Windows 10的设备) 

命名实体 SIT 和增强策略不支持用于：


- 本地存储库

## <a name="create-and-edit-enhanced-policies"></a>创建和编辑增强策略

若要创建或编辑 DLP 策略，请使用创建、测试和调整 [DLP 策略 中的过程](create-test-tune-dlp-policy.md)。

## <a name="workloads-and-services-that-support-named-entities"></a>支持命名实体的工作负载和服务


- **Microsoft 3655 电子数据** 展示支持在视区服务中使用命名实体。
- **Microsoft Defender for Cloud Apps** 支持在 Defender for Cloud Apps 策略中使用命名实体。
- **内部风险管理** 支持在"基元服务"中使用命名实体。
- **通信** 合规性不支持在传输规则和Exchange数据中使用命名实体。
- **Microsoft 信息** (MIG) 不支持在传输规则和Exchange数据中使用命名实体。
 
### <a name="unified-dlp"></a>统一 DLP

|工作负载/服务  |对命名实体的公共预览支持  |
|---------|---------|
|Office Win32 客户端策略提示    |不支持  |
|Office WAC 客户端策略提示    |支持         |
|OWA 策略提示     |不支持         |
|Outlook策略提示     |不支持 |
|终结点 (Windows 10设备)      |不支持  |
|Exchange传输规则     |不支持 |
|OneDrive for Business处于其余时间的数据     |支持         |
|SharePoint联机数据-rest     |支持         |
|Teams处于其余时间的数据     |支持         |
|电子邮件数据处于其余时间     |不支持         |
|Microsoft Defender for Cloud Apps     |支持         |

### <a name="autolabeling"></a>自动标记

|工作负载/服务 |对命名实体的公共预览支持  |
|---------|---------|
|Office Win32 客户端脱机   |支持，用户必须选择标签并手动应用 |
|联机Office Win32 客户端联机|支持旧可信度方案 |
|Outlook联机   |支持旧可信度方案  |
|Office WAC 客户端     |支持 |
|OWA     |支持 |
|Exchange传输     |不支持 |
|OneDrive for Business处于其余时间的数据     |支持 |
|SharePoint联机数据-rest|支持|
|Azure 信息保护 (AIP) 扫描程序|不支持|

## <a name="known-issues"></a>已知问题

|问题  |影响  |
|---------|---------|
|OWA、Outlook、Office Win32 客户端 (DLP 策略)      |   具有实体条件的策略提示将导致"不匹配"      |
| 中文、日语、朝鲜语 (对人名的亚洲语言)     | 仅支持基于拉丁语的字符集的命名实体 (即，人名不支持) 日文汉字        |
|本地存储库    | 不支持作为工作负荷|

<!--|Devices workload (Endpoint)     | Not supported as a workload – authoring policy with named entities will not be allowed        |-->

## <a name="for-further-information"></a>有关详细信息
<!-- - [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)-->
- [了解预览版 (命名) 。 ](named-entities-learn.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [从模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
