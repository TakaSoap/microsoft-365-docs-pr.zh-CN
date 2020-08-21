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
description: 本主题为希望执行委派 Microsoft 365 管理任务的 Microsoft 合作伙伴和经销商提供常见问题解答。
ms.openlocfilehash: 01781437bbc7e8fe5c035ea23e4392e734e0231f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827083"
---
# <a name="delegated-administration-faq"></a>委派管理常见问题解答

本主题为想要执行委派管理任务的 Microsoft 合作伙伴和经销商（包括能够为其他租户 (公司管理 Exchange Online Protection (EOP) 的功能）提供了常见问题) 。

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a>我是经销商，我需要管理客户的租户;这是如何工作的？

如果你是 Microsoft 合作伙伴或经销商，并且已注册为 Microsoft 顾问，你可以请求在管理中心中管理其租户的权限。 这称为委派管理，它让您能够管理其 Microsoft 365 租户 (包括 EOP 设置) 就如同其组织内的管理员一起。 执行委派管理的步骤如下所示：

1. 注册成为 [Microsoft Office 365 顾问](https://aka.ms/cloudbenefits)。

2. 注册委派管理。 在开始管理客户帐户之前，客户必须将您授权为委派管理员。 要获得这些批准，首先 [向他们发送委派管理的相关服务](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e)。  (您也可以稍后向你的客户提供委派管理) 

3. 使用添加、更改或删除订阅顾 [问合作伙伴中的步骤创建委派管理员帐户](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)。

访问 [合作伙伴：建立您的企业和管理合作伙伴订阅](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) ，获取有关如何设置委派管理的详细信息。

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a>我是客户，而不是经销商，我如何为我的子租户设置委派管理员？

委派管理目前仅对经销商和合作伙伴可用。 但是，我们提供了示例脚本Windows PowerShell帮助你向子租户和公司公司 () 。 有关详细信息，请参阅将 [EOP 设置应用到多个租户的示例脚本](sample-script-for-applying-eop-settings-to-multiple-tenants.md)。

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a>能否防止子租户管理员修改我的策略？

Microsoft 365 目前不具有此功能。

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a>能否将报告合并到我的所有子租户中？

您管理的公司之间的合并报告目前不适用于 Microsoft 365 管理中心报告。 不过，可以使用 [Microsoft Graph](https://docs.microsoft.com/graph/overview)执行此操作。
