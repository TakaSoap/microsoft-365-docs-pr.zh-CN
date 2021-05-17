---
title: Microsoft 365 网络计划和性能优化
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/19/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_Enterprise
f1.keywords:
- CSH
search.appverid:
- MET150
ms.assetid: e5f1228c-da3c-4654-bf16-d163daee8848
ms.custom:
- seo-marvel-apr2020
- Adm_O365
description: 本文将帮助你规划网络带宽要求，Microsoft 365性能微调和故障排除。
ms.openlocfilehash: bf05e4128f8ba5ddecce76cb00dc945f43c9c59a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923596"
---
# <a name="network-planning-and-performance-tuning-for-microsoft-365"></a>Microsoft 365 网络计划和性能优化
在首次部署或迁移到 Microsoft 365 之前，可以使用这些主题中的信息估计所需的带宽，然后测试和验证您是否有足够的带宽来部署或迁移到 Microsoft 365。 有关概述，请参阅[：Network and migration planning for Microsoft 365](network-and-migration-planning.md)。
  
|||||
|:-----|:-----|:-----|:-----|
|**网络规划** <br/> ![网络](../media/5e9dcd06-601b-4b28-88dc-f524e7548794.png)           <br/> |需要快速连接和快速加载的页面？  <br/> 请阅读[在 Microsoft 365 中获得最佳连接和性能](https://aka.ms/o365perfprinciples)。<br/>请阅读[Microsoft 365网络连接概述](microsoft-365-networking-overview.md)"以了解概念。<br/> |**测量网络** <br/> ![计算器](../media/d690a132-4884-40eb-a918-526bb3dff3cc.png)           <br/> |请阅读[Microsoft 365基线和性能历史记录](performance-tuning-using-baselines-and-history.md)以及性能疑难解答计划来优化[Microsoft 365。](performance-troubleshooting-plan.md)  <br/> 使用这些工具 [评估现有网络](network-and-migration-planning.md#calculators)。  <br/> |
|**最佳做法** <br/> ![最佳做法](../media/2a659a5c-1007-47d3-a6c6-a19e018ab29b.png)           <br/> |[网络规划和提高迁移性能的最佳实践Microsoft 365。](network-and-migration-planning.md#BestPractices) 想要开始帮助你的用户吗？ 请参阅[在慢速网络上Office 365的最佳实践](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)。  <br/> [Microsoft 365网络连接](./microsoft-365-network-connectivity-principles.md)原则将帮助你了解安全优化网络连接的最新Microsoft 365指南。  <br/> |**Reference** <br/> ![书籍或日记](../media/56dff3c1-f605-48d8-811f-7d13ce639ecd.png)           <br/> |需要详细信息，如 IP 地址和端口列表？ 请参阅[Network planning reference for Microsoft 365](network-and-migration-planning.md#NetReference)。  <br/> |
|![请参阅 Microsoft 云网络Enterprise架构师海报](../media/3094be9f-2407-4fa5-896d-aa66ef7b9bb9.png)           <br/> |有关优化网络以针对 Microsoft 365 和其他 Microsoft 云平台和服务的步骤，请参阅[Microsoft Cloud Networking for Enterprise Poster。](../solutions/cloud-architecture-models.md)  <br/> |
   
## <a name="performance-tuning-and-troubleshooting-resources-for-microsoft-365"></a>性能优化和疑难解答资源Microsoft 365
<a name="apptuning"> </a>

部署Microsoft 365后，可以使用本节中的主题优化性能。 如果您遇到性能下降，您还可以使用这些主题来解决问题。
  
 **[优化Office 365性能](tune-microsoft-365-performance.md)**：有关将网络地址转换与Office 365的信息，请参阅 [NAT 支持与Office 365。](nat-support-with-microsoft-365.md) 此外，请看一下有关优化和排查网络连接问题前[10](/archive/blogs/onthewire/top-10-tips-for-optimising-troubleshooting-your-office-365-network-connectivity)Office 365提示。 
  
 **[优化Exchange Online性能](tune-exchange-online-performance.md)**：使用这些文章可微调性能Exchange Online性能。 
  
 **[优化Skype for Business在线](tune-skype-for-business-online-performance.md)** 性能：使用这些文章微调联机Skype for Business性能。 
  
 **[优化SharePoint在线](tune-sharepoint-online-performance.md)** 性能：使用这些文章微调SharePoint联机性能。 
  
 **[优化Project Online](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)** 性能：使用本文微调性能Project Online性能。