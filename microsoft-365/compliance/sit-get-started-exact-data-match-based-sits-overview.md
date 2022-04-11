---
title: 基于精确数据匹配的敏感信息类型入门
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 开始创建基于数据匹配的敏感信息类型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0f221ba0521a50f484bfb9a8d5030e33b495c495
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64759736"
---
# <a name="get-started-with-exact-data-match-based-sensitive-information-types"></a>基于精确数据匹配的敏感信息类型入门

创建和使 EDM (完全数据匹配) 基于敏感信息类型 (SIT) 可用是一个多阶段过程。 它们可用于数据丢失防护策略、电子数据展示和某些内容治理任务。本文概述了每个阶段的工作流和过程链接

## <a name="before-you-begin"></a>准备工作

熟悉以下文章中的概念和术语：

- [了解敏感信息类型](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [了解基于确切数据匹配的敏感信息类型](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)

## <a name="required-licenses-and-permissions"></a>所需的许可证和权限

你必须是全局管理员、合规性管理员或 Exchange Online 管理员才能执行本文中描述的任务。 若要了解有关 DLP 权限的详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。

有关完整的许可信息，请参阅[数据丢失防护服务说明](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)

## <a name="portal-links-for-your-subscription"></a>订阅门户链接

|门户|全球/GCC|GCC-High|DOD|
|---|---|---|---|
|Office SCC|compliance.microsoft.com|scc.office365.us|scc.protection.apps.mil|
|Microsoft 365 Defender 门户|security.microsoft.com|security.microsoft.us|security.apps.mil|
|Microsoft 365 合规中心|compliance.microsoft.com|compliance.microsoft.us|compliance.apps.mil|

## <a name="the-work-flow-at-a-glance"></a>工作流程概览

![精确数据匹配工作流阶段](..\media\swimlane_edm_process.png)


|阶段|所需项|
|---|---|
|[阶段 1：导出源数据以获取基于确切数据匹配的敏感信息类型](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)|- 敏感数据的读取权限|
|[阶段 2：为基于数据匹配的敏感信息类型创建架构](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)|- 访问Microsoft 365 管理中心中的敏感信息类型向导 </br>- [通过安全&合规性 PowerShell 访问Microsoft 365 管理中心](/powershell/exchange/connect-to-scc-powershell) |
|[阶段 3：哈希并上传敏感信息源表，以获取与敏感信息类型完全匹配的数据](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)|- 自定义安全组和用户帐户 </br>- **哈希并从一台计算机上传**：对具有直接 Internet 访问的计算机的本地管理员访问权限，以及托管 EDM Upload 代理 </br>- **从单独的计算机进行哈希和上传**：对具有直接 Internet 访问的计算机的本地管理员访问权限，并托管 EDM Upload代理，以便上传安全计算机和本地管理员访问，以托管 EDM Upload代理来哈希敏感信息源表 </br>- 读取对敏感信息源表文件的访问权限 </br> 架构文件 |
|[阶段 4：创建与敏感信息类型/规则包完全匹配的数据](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package) |- 访问Microsoft 365合规中心 |
|[测试基于精确数据匹配的敏感信息类型](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)| - 访问Microsoft 365合规中心

## <a name="see-also"></a>另请参阅

- [了解基于确切数据匹配的敏感信息类型](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [为基于精确数据匹配的敏感信息类型导出源数据](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
