---
title: Contoso Corporation 概述
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso Corporation 的业务及其全球办事处的分层结构。
ms.openlocfilehash: fd354b4159ee22e65e04afba33af2e90bd49b622
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865749"
---
# <a name="overview-of-the-contoso-corporation"></a>Contoso Corporation 概述

**摘要：** 了解 Contoso Corporation 的业务及其全球办事处的分层结构。

Contoso Corporation 是一家跨国公司，总部设在法国巴黎。这是一家集制造、销售和支持服务为一体的大型组织，提供 100,000 多种产品。

![](./media/contoso-overview/contoso-icon.png)

## <a name="contoso-around-the-world"></a>全球的 Contoso

图 1 显示了在巴黎的总部办公室和在各大洲的区域中心和分支办事处。

![](./media/contoso-overview/contoso-overview-fig1.png)

**图 1：全球的 Contoso 办事处**
 
世界各地的 Contoso 办事处按照三层进行设计。

- 总部

  Contoso Corporation 总部位于巴黎郊外的一个大型企业园区，拥有数十座用于管理、设计和制造设施的建筑物。Contoso 的所有数据中心和 Internet 展示均位于巴黎总部。

  总部拥有 25,000 名工作人员。

- 区域中心

  区域中心办事处拥有 60% 的销售和支持人员，为世界上的特定区域服务。每个区域中心都通过高带宽的 WAN 链接连接到巴黎总部。 

  每个区域中心平均拥有 2,000 名工作人员。

- 分支办事处

  分支办事处包含 80% 的销售和支持人员，并为主要城市或子地区的 Contoso 客户提供现场展示。每个分支办事处通过高带宽 WAN 链接连接到区域中心。

  每个分支办事处平均拥有 250 名工作人员。

25% 的 Contoso 工作人员为仅移动工作人员，区域中心和分支办事处的仅移动工作人员的百分比更高。为仅移动工作人员提供更有力的支持是 Contoso 的重要业务目标。

## <a name="design-considerations-for-microsoft-365-enterprise"></a>有关 Microsoft 365 企业版的设计注意事项

Contoso 的 IT 架构师在部署 Microsoft 365 企业版时确定了以下设计注意事项： 

- 具有本地管理法规和合规性要求的多个地理位置
- 总部办公室的中央 Intranet 数据中心和托管内部业务线应用程序的区域应用程序服务器
- 现有 System Center Configuration Manager 基础结构
- 涉及各种客户端计算设备，包括 Windows、Mac 和 Linux
- 同时涉及个人和公司所拥有的移动设备，包括 iOS（iPhone 和 iPad）和 Android 智能手机和平板电脑
- 许多远程和移动工作人员
- 许多商业合作伙伴
- 大量的客户和个人身份数据
- 以产品设计规格和制造工艺商业机密形式存在的大量高价值知识产权

## <a name="next-step"></a>后续步骤

[了解](contoso-infra-needs.md) Contoso Corporation 的本地 IT 基础结构以及如何通过 Microsoft 365 企业版解决他们的业务需求。

## <a name="see-also"></a>另请参阅

[部署指南](deploy-microsoft-365-enterprise.md)

[测试实验室指南](m365-enterprise-test-lab-guides.md)



