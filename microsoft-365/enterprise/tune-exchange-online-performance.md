---
title: 优化 Exchange Online 性能
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: 本文包含一些常规提示和指向其他资源的链接，可告诉你如何提高Exchange Online。
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59170579"
---
# <a name="tune-exchange-online-performance"></a>优化 Exchange Online 性能

本文包含一些常规提示和指向其他资源的链接，可告诉你如何提高Exchange Online性能，尤其是在迁移前。 本文是 Network [planning and performance tuning for Office 365的一](./network-planning-and-performance.md)部分。
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>为了改进性能而要考虑Exchange Online内容

若要提高迁移速度并降低组织的带宽限制，Exchange Online以下事项：
  
- **减小邮箱大小。** 较小的邮箱大小可提高迁移速度。 
    
- **将邮箱移动功能与Exchange部署一同使用。** 使用Exchange混合部署，脱机邮件 (采用 的形式。迁移到) 操作系统时，无需重新下载 OST Exchange Online。 这大大减少了下载带宽要求。 
    
- **将邮箱移动安排在 Internet 流量较低和内部部署部署使用Exchange期间。** 当计划移动时，迁移请求将提交到邮箱复制代理，并且可能不会立即发生。 
    
- **使用斜弹出式Outlook 网页版。** 通过在服务器上呈现某些组件，斜弹出式弹出窗口提供 Microsoft Edge 或 Internet Explorer 中某些电子邮件的较小、占用较少内存的版本。 有关详细信息，请参阅使用斜弹出式 [弹出窗口减少阅读邮件时所使用的内存](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)。


## <a name="general-advice"></a>一般建议

- 请确保 DNS 查找 outlook.office.com 在位置的逻辑输入位置进入 MS-datacenter。

- 研究邮箱缓存，然后选择相应的 (选项。 缓存期、共享邮箱缓存等) 。

- 在Outlook Internet 之前， (数据通过 VPN 连接) 传递到中央办公室服务器。

- 请确保邮箱数据符合文件夹和项目数量限制。
    
有关迁移性能Exchange，请参阅Office 365[性能和最佳做法](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)。
