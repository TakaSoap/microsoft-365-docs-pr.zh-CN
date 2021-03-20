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
description: 本文包含一些常规提示和指向其他资源的链接，可告诉你如何提高 Exchange Online 的性能。
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909438"
---
# <a name="tune-exchange-online-performance"></a>优化 Exchange Online 性能

本文包含一些常规提示和指向其他资源的链接，可告诉你如何提高 Exchange Online 的性能，尤其是在迁移前。 本文是 Office [365 项目的网络规划和性能调整的一](./network-planning-and-performance.md) 部分。
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>提高 Exchange Online 性能需要考虑的问题

若要提高迁移速度并降低组织的 Exchange Online 带宽限制，请考虑以下事项：
  
- **减小邮箱大小。** 较小的邮箱大小可提高迁移速度。 
    
- **将邮箱移动功能与 Exchange 混合部署一同使用。** 使用 Exchange 混合部署，脱机 (采用 的形式。迁移到 Exchange Online) OST 文件，则无需重新下载。 这大大减少了下载带宽要求。 
    
- **计划邮箱移动在 Internet 流量较低和本地 Exchange 使用较低期间发生。** 当计划移动时，迁移请求将提交到邮箱复制代理，并且可能不会立即发生。 
    
- **使用 Outlook 网页的精简弹出窗口。** 精简弹出窗口通过在服务器上呈现某些组件，在 Microsoft Edge 或 Internet Explorer提供较小、占用较少内存的电子邮件版本。 有关详细信息，请参阅使用斜弹出式 [弹出窗口减少阅读邮件时所使用的内存](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)。


## <a name="general-advice"></a>一般建议

- 请确保 DNS 查找 outlook.office.com 在位置的逻辑输入位置进入 MS-datacenter。

- 研究邮箱缓存，然后选择相应的 (选项。 缓存期、共享邮箱缓存等) 。

- 在通过 Internet 之前， (Outlook 数据) 通过 VPN 连接传递到中央办公室服务器。

- 请确保邮箱数据符合文件夹和项目数量限制。
    
有关 Exchange 迁移性能详细信息，请参阅 [Office 365 迁移性能和最佳做法](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)。
