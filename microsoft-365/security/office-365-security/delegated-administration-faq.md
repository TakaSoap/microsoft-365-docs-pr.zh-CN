---
title: 委派管理常见问题解答
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: 管理员可以查看有关 microsoft 合作伙伴和转销商的 Microsoft 365 中委派的管理任务的常见问题和解答。
ms.openlocfilehash: 3efadc8793778bfabe10922e8e29044747d60ad0
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866691"
---
# <a name="delegated-administration-faq"></a>委派管理常见问题解答

本文提供了有关 Microsoft 合作伙伴和转销商的 Microsoft 365 中委派管理任务的常见问题和解答。 委派管理包括管理 Exchange Online Protection (EOP)  (公司) 其他租户的设置的功能。

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>我是转销商，我需要管理我的客户租户。 这是如何工作的？

如果你是 Microsoft 合作伙伴或经销商，并且已注册为 Microsoft advisor，则可以在客户的 Microsoft 365 组织中请求 _委派管理_ 功能。

委派管理允许您管理 Microsoft 365 (包括 EOP 设置) ，就像您是该组织中的管理员一样。 下面的列表介绍了配置委派管理的步骤：

1. 注册成为 [Microsoft Office 365 顾问](https://aka.ms/cloudbenefits)。

2. 注册委派管理。 在开始管理客户的租户之前，他们必须授权你为委派管理员。 若要获取他们的审批，请首先 [向其发送对委派管理的提供](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e)。 您还可以在以后向客户提供委派管理。

3. 使用 [添加、更改或删除订阅顾问合作伙伴](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)中的步骤创建委派的管理员帐户。

访问 [合作伙伴：构建您的业务和管理合作伙伴订阅](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) ，了解有关如何设置委派管理的详细信息。

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>我是客户，而不是转销商。 如何为我的 subtenants 设置委派管理员？

委派管理仅适用于经销商和合作伙伴。 但是，有一个示例 PowerShell 脚本，可帮助您将策略应用于 subtenants (公司) 。 有关详细信息，请参阅 [将 EOP 设置应用于多个租户的示例脚本](sample-script-for-applying-eop-settings-to-multiple-tenants.md)。

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>我是否可以阻止我的 subtenant 管理员修改我的策略？

不正确。 Microsoft 365 当前尚无此功能。

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>我是否可以跨我的所有 subtenants 获取整合报告？

跨你管理的公司的合并报告在 Microsoft 365 管理中心报告中不可用。 但是，可以使用 [Microsoft Graph](https://docs.microsoft.com/graph/overview)获取报告。
