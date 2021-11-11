---
title: 开始使用基于精确数据匹配的敏感信息类型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 开始创建基于准确数据匹配的敏感信息类型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3621ccdedb5966ae7c70e549c5f0538143df0248
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914741"
---
# <a name="get-started-with-exact-data-match-based-sensitive-information-types"></a>开始使用基于精确数据匹配的敏感信息类型

创建和 (使基于 EDM) 的敏感信息类型 (数据) 匹配是一个多阶段过程。 它们可用于数据丢失防护策略、电子数据展示和某些内容管理任务 本文概述了工作流以及每个阶段的过程链接

## <a name="before-you-begin"></a>开始之前

熟悉以下文章中的概念和术语：

- [了解敏感信息类型](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [了解基于精确数据匹配的敏感信息类型](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)

## <a name="required-licenses-and-permissions"></a>所需的许可证和权限

你必须是全局管理员、合规性管理员或 Exchange Online 管理员才能执行本文中描述的任务。 若要了解有关 DLP 权限的详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。

有关 [完整许可信息，](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business) 请参阅数据丢失防护服务说明

## <a name="portal-links-for-your-subscription"></a>订阅门户链接

|门户|全球/GCC|GCC-High|DOD|
|---|---|---|---|
|Office SCC|compliance.microsoft.com|scc.office365.us|scc.protection.apps.mil|
|Microsoft 365 安全中心|security.microsoft.com|security.microsoft.us|security.apps.mil|
|Microsoft 365 合规中心|compliance.microsoft.com|compliance.microsoft.us|compliance.apps.mil|

## <a name="the-work-flow-at-a-glance"></a>工作流程概览

![精确数据匹配工作流阶段](..\media\swimlane_edm_process.png)


|阶段|所需项|
|---|---|
|[阶段 1：导出基于准确数据匹配的敏感信息类型的源数据](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)|- 敏感数据的读取权限|
|[阶段 2：为基于准确数据匹配的敏感信息类型创建架构](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)|- 访问网站中的敏感信息类型Microsoft 365 管理中心 </br>- 通过安全[Microsoft 365 管理中心合规性 PowerShell &访问安全](/powershell/exchange/connect-to-scc-powershell) |
|[阶段 3：哈希并上载敏感信息源表，以精确匹配敏感信息类型](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)|- 自定义安全组和用户帐户 </br>- **从一台计算机进行** 哈希和上载：本地管理员访问具有直接 Internet 访问权限的计算机和托管 EDM Upload代理 </br>- **从** 单独的计算机进行哈希和上载：本地管理员访问具有直接 Internet 访问权限的计算机，并托管 EDM Upload 代理，用于上传和本地管理员访问安全计算机以托管 EDM Upload 代理以哈希处理敏感信息源表 </br>- 对敏感信息源表文件的读取访问权限 </br> 架构文件 |
|[阶段 4：创建准确数据匹配敏感信息类型/规则包](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package) |- 访问 Microsoft 365 合规中心 |
|[测试准确数据匹配敏感信息类型](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)| - 访问 Microsoft 365 合规中心

## <a name="see-also"></a>另请参阅

- [了解基于精确数据匹配的敏感信息类型](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [导出基于准确数据匹配的敏感信息类型的源数据](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
