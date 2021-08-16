---
title: 通过 DAP 合作伙伴的 Windows PowerShell检索客户租户报告数据
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: 摘要：使用适用于 Microsoft Exchange Online 的远程 Windows PowerShell 从各个客户租户中检索报表。
ms.openlocfilehash: ee9639ae8d5b77443dcfc119f34bc378992920ae
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2021
ms.locfileid: "58355888"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>通过 Windows PowerShell 为委派访问权限 (DAP) 合作伙伴检索客户报告数据

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

使用远程Windows PowerShell Microsoft Exchange Online从单个客户租户检索报告。

联合和云解决方案提供商 (CSP) 合作伙伴可以直接通过远程云解决方案提供商报告访问由 Exchange Online PowerShell Windows PowerShell客户租户报告Exchange Online数据。 这样，合作伙伴可以收集并保存报告数据，然后对其执行其他操作。 打开远程连接后，检索有关客户租赁的报告数据与在客户租赁中运行任何 cmdlet 的效果是一样的。

本文使用远程租户Windows PowerShell Exchange Online连接到单个客户租赁并检索报告。 默认情况下，Windows PowerShell 不支持聚合多个客户租赁中的报告数据。 通过此过程检索的报告仅适用于您连接到的  _DelegatedOrg_。

## <a name="before-you-begin"></a>准备工作

- 您需要使用远程 Windows PowerShell 连接到您的 Exchange Online 租户。有关说明，请参阅[通过远程 Windows PowerShell 为委派访问权限 (DAP) 合作伙伴连接到 Exchange Online 租户](/powershell/exchange/connect-to-exchange-online-powershell)。

## <a name="run-the-get-stalemailboxreport-sample"></a>运行 Get-StaleMailboxReport 示例

打开到 Exchange Online 的远程会话后，运行此命令可检索日期范围 03/25/2015 到 03/31/2015 的 **Get-StaleMailboxReport** 。

```powershell
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

有许多其他报告 cmdlet 可用于 Exchange Online、Lync Online 和 SharePoint Online，还有其他报告 cmdlet 可用于您可以使用的邮件跟踪。若要了解有关可用的报告 cmdlet 和 Office 365 报告 Web 服务的详细信息，请参阅下一节中的主题。

## <a name="see-also"></a>另请参阅

[Office 365 报告 Web 服务](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))

[Exchange Online 中的报告 cmdlet](/powershell/module/exchange/get-csclientdevicedetailreport)

[适于合作伙伴的帮助](https://go.microsoft.com/fwlink/p/?LinkID=533477)
