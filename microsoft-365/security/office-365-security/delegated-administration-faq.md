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
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: 管理员可以查看有关 Microsoft 365 中针对 Microsoft 合作伙伴和经销商的委派管理任务的常见问题和解答。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 82fa70a8025f67610032ba59368bc74789b60f84
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203663"
---
# <a name="delegated-administration-faq"></a>委派管理常见问题解答

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


本文提供有关 Microsoft 365 中针对 Microsoft 合作伙伴和经销商的委派管理任务的常见问题和解答。 委派管理包括管理 Exchange Online Protection (EOP) 公司的其他租户 (EOP) 。

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>我是经销商，需要管理我的客户租户。 这如何工作？

如果你是 Microsoft 合作伙伴或经销商，并且已注册成为 Microsoft 顾问，可以在客户的 Microsoft 365 组织中请求委派管理功能。 

委派管理允许你管理 Microsoft 365 (包括 EOP 设置) 就像你是该组织内的管理员一样。 下面列出了配置委派管理的步骤：

1. 注册成为 [Microsoft Office 365 顾问](https://partner.microsoft.com/?cloudbenefits)。

2. 注册委派管理。 在你开始管理客户的租户之前，他们必须授权你成为委派管理员。 若要获得其批准，您 [首先会向这些用户发送委派管理产品/服务](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e)。 还可以在以后为客户提供委派管理。

3. 使用添加、更改或删除订阅顾问合作伙伴 中的步骤创建 [委派管理员帐户](../../admin/misc/add-partner.md)。

访问 [合作伙伴：建立业务和管理合作伙伴订阅](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) ，详细了解如何设置委派管理。

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>我是客户，不是经销商。 如何为我的子模板设置委派管理员？

委派管理仅适用于经销商和合作伙伴。 但是，有一个示例 PowerShell 脚本可帮助您将策略应用到公司或 (的) 。 有关详细信息，请参阅将 [EOP 设置应用到多个租户的示例脚本](sample-script-for-applying-eop-settings-to-multiple-tenants.md)。

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>能否阻止下级管理员修改我的策略？

不正确。 Microsoft 365 当前没有此功能。

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>我能否获得我的所有子模板的合并报告？

Microsoft 365 管理中心报告中未提供你管理的公司的合并报告。 但是，可以使用 [Microsoft Graph](/graph/overview)获取报告。