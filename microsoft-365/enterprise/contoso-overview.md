---
title: Contoso Corporation 概述
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso Corporation 的业务及其全球办事处的分层结构。
ms.openlocfilehash: b0c00ed5657d914851f28278a2f4cf80660b53b0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754264"
---
# <a name="overview-of-contoso-corporation"></a>Contoso Corporation 概述

Contoso Corporation 是其总部在巴黎的跨国企业。 公司是包含100000以上产品的制造、销售和支持组织。

## <a name="contoso-around-the-world"></a>全球的 Contoso

图1显示了位于巴黎和各个洲的地区中心和卫星办公室中的总部办公室。

![世界各地的 Contoso 办事处](../media/contoso-overview/contoso-overview-fig1.png)

**图1：世界各地的 Contoso 办事处**
 
Contoso 拥有三个层的办公室：

- 总部

  Contoso 总部是在巴黎 outskirts 的公司校园，拥有数十个用于管理、工程和制造设施的办公楼。 所有 Contoso 数据中心及其 internet 状态均驻留在巴黎总部中。

  总部拥有 25,000 名工作人员。

- 区域中心

  中心办公室为世界各地的特定区域提供了60% 的销售和支持人员。 每个区域集线器通过高带宽 WAN 链路连接到巴黎总部。

  区域中心的平均工作者数为2000。

- 分支办事处

  卫星办公室包含80% 的销售和支持人员。 它们为 Contoso 客户提供了关键城市或 subregions 的现场状态。 通过高带宽 WAN 链路将每个卫星办公室连接到一个区域中心。

  卫星办公室平均为250个工作人员。

大约25% 的 Contoso 劳动力是仅移动设备。 区域中心和卫星办公室的工作人员占的百分比越高。 为仅移动工作人员提供有力的支持是 Contoso 的重要业务目标。

## <a name="design-considerations-for-microsoft-365-for-enterprise"></a>适用于企业的 Microsoft 365 的设计注意事项

Contoso IT 架构师确定了以下用于部署适用于企业的 Microsoft 365 的设计要求因素：

- 具有本地管理法规和合规性要求的多个地理位置
- 驻留内部业务线应用程序的总部办公室和区域应用程序服务器中的中央 intranet 数据中心
- 现有 Microsoft Endpoint Configuration Manager 基础结构
- 运行 Windows、Mac 和 Linux 的客户端计算设备的混合
- 同时涉及个人和公司所拥有的移动设备，包括 iOS（iPhone 和 iPad）和 Android 智能手机和平板电脑
- 许多远程和移动工作人员
- 许多商业合作伙伴
- 需要大量客户和其他机密个人信息来管理和保护
- 以产品设计规格和制造工艺商业机密形式存在的大量高价值知识产权

## <a name="next-step"></a>后续步骤

了解 Contoso Corporation [本地 IT 基础结构](contoso-infra-needs.md) ，以及公司的业务需求如何与 Microsoft 365 for enterprise 一起解决。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[测试实验室指南](m365-enterprise-test-lab-guides.md)
