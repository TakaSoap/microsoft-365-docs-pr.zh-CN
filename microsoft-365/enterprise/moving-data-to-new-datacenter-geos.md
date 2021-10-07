---
title: 将核心数据移动到新的数据中心Microsoft 365地理位置
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 0a35176a-e585-4dec-a90b-36be8314667f
f1.keywords:
- NOCSH
description: 了解新的Office 365数据中心地理位置，以及如何使用数据驻留选项请求将核心数据移动到新地理位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 724021bc3fb5fd8a0946bcf5f460e4848c44bf9f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209641"
---
# <a name="moving-core-data-to-new-microsoft-365-datacenter-geos"></a>将核心数据移动到新的数据中心Microsoft 365地理位置

我们将继续打开新的数据中心地理位置，Microsoft 365服务。 这些新数据中心地理位置可增加容量和计算资源，以支持我们的持续客户需求和使用增长。 此外，新的数据中心地理位置为核心客户数据提供地理位置内数据驻留。 

核心客户数据是指客户数据的子集，包括： 
- Exchange Online邮箱 (电子邮件正文、日历条目以及电子邮件附件内容) 
- SharePoint联机网站内容和存储在该网站中的文件
- 上载到OneDrive for Business
- Teams聊天消息，包括私人消息、频道消息和聊天中使用的图像
  
其核心客户数据存储在已存在的数据中心地理位置中的现有客户不会受新数据中心地理位置的启动影响。 我们对新的数据中心地理位置没有独特的功能、功能或合规性认证。 作为这两个地理位置中的任意一个的客户，你将体验与之前相同的服务质量、性能和安全控制。 我们提供了下表中列出的现有客户，可请求将组织的核心客户数据提前迁移到新的数据中心地理位置。
  
|**具有租户注册国家/地区的客户**|**以前的数据中心地理位置**|**新的数据中心地理位置**|**自此后可用的地理位置**|
|:-----|:-----|:-----|:-----|
|**日本**| 亚洲/太平洋 | 日本 | 2014 年 12 月 |
|**澳大利亚、新西兰、斐济**| 亚洲/太平洋 | 澳大利亚 | 2015 年 3 月 |
|**India（印度）**| 亚洲/太平洋 | 印度 | 2015 年 10 月 |
|**加拿大**| 美国 | 加拿大 | 2016 年 5 月 |
|**英国**| 欧盟 | 英国 | 2016 年 9 月 |
|**韩国**| 亚洲/太平洋 | 韩国 | 2017 年 4 月 |
|**France（法国）**| 欧盟 | 法国 | 2018 年 3 月 |
|**阿拉伯联合酋长国**| 欧盟 | 阿拉伯联合酋长国 | 2019 年 6 月 |
|**南非**| 欧盟 | 南非 | 2019 年 7 月 |
|**瑞士、列支敦士登**| 欧盟 | Switzerland（瑞士） | 2019 年 12 月 |
|**Germany（德国）**| 欧盟 | 德国 | 2019 年 12 月 |
|**挪威**| 欧盟 | 挪威 | 2020 年 4 月 |
|**巴西**| 美洲 | 巴西 | 2020 年 11 月 |

自 2020 年 10 月 1 日起，租户Office 365 教育版订阅的客户不符合迁移条件。

所有数据中心地理位置、数据中心和客户静止位置的完整列表都作为交互式数据中心地图的一 [部分提供](https://office.com/datamaps)。 
  
## <a name="data-residency-option"></a>数据驻留选项

我们提供数据驻留选项，Microsoft 365上表中列出的数据中心地理位置覆盖的符合条件的客户。 使用此选项，具有数据驻留要求的符合条件的客户可以请求将组织的核心客户数据静止迁移到其新的数据中心地理位置。  Microsoft 将在注册窗口期间向请求迁移的所有符合条件的客户提供承诺的截止时间。  查看 [如何请求数据移动](request-your-data-move.md) 页面，了解有关数据中心地理位置的开放式注册窗口以及注册计划的步骤的更多详细信息。  数据移动可能需要在请求期结束后最多 24 个月才能完成。

我们对新的数据中心地理位置没有独特的功能、功能或合规性认证。
    
当预计租户或其他任何单个租户完成数据移动时，我们需要在全局运营和自动化环境中执行数据移动的复杂性、精度和规模会禁止我们共享数据。 完成数据移动后，客户将在每个参与服务的消息中心收到一个确认。 
    
数据移动是后端服务操作，对最终用户的影响最小。 "数据移动期间"页和"数据移动后" [页上列出了可影响的功能](during-and-after-your-data-move.md) 。 我们遵守 Microsoft Online Services [服务级别协议 (SLA ](https://go.microsoft.com/fwlink/p/?LinkId=523897)) ，因此在移动过程中客户无需准备或监视任何内容。 将根据需要通知任何服务维护。 

数据移动到新数据中心地理位置已完成，客户无需额外付费。
    
## <a name="related-topics"></a>相关主题 
 
[如何请求数据移动](request-your-data-move.md)
    
[数据移动常见问题解答](data-move-faq.yml)
  
[新的数据中心地理位置Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[按区域表示的 Azure 服务](https://azure.microsoft.com/regions/)

[Teams多地理位置Microsoft 365租户中的体验](/microsoftteams/teams-experience-o365odb-spo-multi-geo)
