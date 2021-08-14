---
title: 云解决方案提供商的其他信息
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：与从德国 Microsoft 云迁移相关的云解决方案提供商的其他信息。
ms.openlocfilehash: af437995566332679a06cf21803d2a5cb1e98008e49d6c7ff6927cf106abb2a9
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53848611"
---
# <a name="additional-information-for-cloud-solution-providers"></a>云解决方案提供商的其他信息

云解决方案 (支持) 的云解决方案提供商需要执行其他步骤，从德国 Microsoft 云迁移到新的德国数据中心区域。

## <a name="partner-tenant-migration"></a>合作伙伴租户迁移

不会迁移德国 Microsoft 云合作伙伴租户。 相反，将为新的德国Office 365区域的每个 Microsoft 合作伙伴创建一个新的服务租户。

云解决方案提供商客户租户将迁移到新的德国数据中心区域，并链接到同一合作伙伴的新 Office 365 服务租户。 在客户转换后，合作伙伴可以使用德国数据中心区域的新 Office 365 服务租户管理客户。

## <a name="missing-subscriptions-in-azure"></a>Azure 中缺少订阅

完成 [订阅和许可证 (阶段 3) ， ](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) 云解决方案提供商将无法访问 Azure 订阅。

若要恢复访问权限，请按照以下步骤 [提升访问权限，以管理所有 Azure 订阅和管理组](/azure/role-based-access-control/elevate-access-global-admin)。
