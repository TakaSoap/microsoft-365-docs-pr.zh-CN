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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
description: 使用这些过程可利用数据丢失防护策略中的命名实体
ms.openlocfilehash: 9b3a8899ef4b64c682289e29df19648a00d4f048
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665153"
---
# <a name="use-named-entities-in-your-data-loss-prevention-policies-preview"></a>在数据丢失防护策略中使用命名实体（预览版）

> [!IMPORTANT]
> 命名实体功能正在推出，并在可供你使用时显示在租户中。 在内容资源管理器和数据丢失防护 (DLP) 策略创作流中检查它们。 

在开始使用 [命名实体之前，请阅读有关命名实体 (预览) ](named-entities-learn.md) 。

## <a name="before-you-begin"></a>准备工作

### <a name="skusubscriptions-licensing"></a>SKU/订阅许可

必须拥有其中一个订阅

- 信息保护和治理
- Microsoft 365 E5 合规
- Office 365 E5
- Microsoft 365 E5

有关完整的许可详细信息，请参阅 [服务说明](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-classification-analytics-overview-content--activity-explorer)。

### <a name="permissions"></a>权限

用于创建和编辑 DLP) 策略 (数据丢失防护的帐户必须具有 **DLP 合规性管理** 角色权限。 有关详细信息，请参阅[向用户授予对Office 365合规中心的访问权限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)


## <a name="supported-locations"></a>支持的位置

可以使用命名实体 SIT 和增强的策略来检测和保护这些位置中的敏感项：

- SharePoint 网站
- OneDrive 账户
- Teams 聊天和通道消息
-  (Windows 10终结点设备的设备) 

命名实体 SIT 和增强型策略不支持：


- 本地存储库
- Power BI

## <a name="create-and-edit-enhanced-policies"></a>创建和编辑增强的策略

若要创建或编辑 DLP 策略，请使用 [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)中的过程。

## <a name="workloads-and-services-that-support-named-entities"></a>支持命名实体的工作负荷和服务


- **Microsoft 3655 电子数据展示** 支持在 Substrate 服务中使用命名实体。
- **Microsoft Defender for Cloud Apps** 支持在Defender for Cloud应用策略中使用命名实体。
- **预览体验成员风险管理** 支持在 Substrate 服务中使用命名实体。
<!--- **Communication Compliance** doesn't support the use of named entities in Exchange transport rules and data-at-rest.
- **Microsoft Information Governance** (MIG) doesn't support the use of named entities in Exchange transport rules and data-at-rest.-->
 
### <a name="unified-dlp"></a>统一 DLP

|工作负荷/服务  |对命名实体的公共预览版支持  |
|---------|---------|
|Office Win32 客户端策略提示    |不支持  |
|Office WAC 客户端策略提示    |支持         |
|OWA 策略提示     |不支持         |
|Outlook策略提示     |不支持 |
| (Windows 10设备) 终结点     |支持  |
|Exchange传输规则     |不支持 |
|OneDrive for Business静态数据     |支持         |
|SharePoint联机静态数据     |支持         |
|Teams静态数据     |支持         |
|静态电子邮件数据     |不支持         |
|Microsoft Defender for Cloud Apps     |支持         |

### <a name="autolabeling"></a>自动标记

|工作负荷/服务 |对命名实体的公共预览版支持  |
|---------|---------|
|Office Win32 客户端脱机   |受支持，用户必须选择标签并手动应用 |
|联机Office Win32 客户端|支持旧置信度方案 |
|联机Outlook   |支持旧置信度方案  |
|Office WAC 客户端     |支持 |
|OWA     |支持 |
|Exchange传输     |不支持 |
|OneDrive for Business静态数据     |支持 |
|SharePoint联机静态数据|支持|
|Azure 信息保护 (AIP) 扫描程序|不支持|

## <a name="known-issues"></a>已知问题

|问题  |影响  |
|---------|---------|
| (OWA、Outlook、Office Win32 客户端的 DLP 策略提示)      |   具有实体条件的策略提示将导致"不匹配"      |
| 中文、日语、韩语 (人名的亚洲语言支持)     | 仅 (，仅支持基于拉丁语的字符集的命名实体，即不支持) 人名的汉字        |
|本地存储库    | 不支持作为工作负载|

<!--|Devices workload (Endpoint)     | Not supported as a workload – authoring policy with named entities will not be allowed        |-->

## <a name="for-further-information"></a>有关详细信息
<!-- - [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)-->
- [了解命名实体 (预览) ](named-entities-learn.md)。
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [根据模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
