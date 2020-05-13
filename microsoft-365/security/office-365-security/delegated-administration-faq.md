---
title: 委派管理常见问题解答
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: 本主题提供了要执行委派 Microsoft 365 管理任务的 Microsoft 合作伙伴和经销商的常见问题解答和解答。
ms.openlocfilehash: d1522973292b290fd9f66f534ca23aeaa55ee756
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209519"
---
# <a name="delegated-administration-faq"></a>委派管理常见问题解答

本主题针对要执行委派管理任务（包括管理其他租户（公司）的 Exchange Online Protection （EOP）的功能）的 Microsoft 合作伙伴和经销商提供常见问题和解答。

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a>我是转销商，我需要管理我的客户的租户;这是如何工作的？

如果你是 Microsoft 合作伙伴或经销商，并且已注册为 Microsoft advisor，则可以请求在管理中心内管理其租户的权限。 这称为 "委派管理"，它允许您管理其 Microsoft 365 租户（包括 EOP 设置），就像您是组织内的管理员一样。 执行委派管理的步骤如下所示：

1. 注册成为 [Microsoft Office 365 顾问](https://aka.ms/cloudbenefits)。

2. 注册委派管理。 在开始管理客户帐户之前，他们必须授权你为委派管理员。 若要获取他们的审批，请首先[向其发送对委派管理的提供](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e)。 （你也可以稍后向客户提供委派管理。）

3. 使用[添加、更改或删除订阅顾问合作伙伴](https://docs.microsoft.com/office365/admin/misc/add-partner)中的步骤创建委派的管理员帐户。

访问[合作伙伴：构建您的业务和管理合作伙伴订阅](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319)，了解有关如何设置委派管理的详细信息。

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a>我是客户，而不是转销商，如何为我的子租户设置委派管理员？

委派管理目前仅适用于经销商和合作伙伴。 但是，我们提供了一个示例 Windows PowerShell 脚本，可帮助您将策略应用于子租户（公司）。 有关详细信息，请参阅[将 EOP 设置应用于多个租户的示例脚本](sample-script-for-applying-eop-settings-to-multiple-tenants.md)。

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a>我是否可以阻止子租户管理员修改我的策略？

Microsoft 365 当前尚无此功能。

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a>我是否可以跨所有子租户获取整合报告？

目前，跨你管理的公司的合并报告不适用于 Microsoft 365 管理中心报告。 但是，可以使用[Microsoft Graph](https://docs.microsoft.com/graph/overview)执行此操作。
