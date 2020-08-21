---
title: EOP 中的退信式垃圾邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: '本文将介绍如何使用 Windows SharePoint Microsoft Exchange Online Protection (信息) '
ms.openlocfilehash: f1705fd7fc30c9a8cde5f6acfaf145861de3af08
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827781"
---
# <a name="backscatter-in-eop"></a>EOP 中的退信式垃圾邮件

*退信式垃圾邮件* 是未送达 (也称为 NDR，或是) 您收到未发送的邮件的退回邮件。 垃圾邮件制程序 (伪) 发件人： 地址的发件人：地址，并且通常使用真实的电子邮件地址来将邮件置信。 因此，如果垃圾邮件发送者不可从性上发送邮件 (垃圾邮件是一个高容量操作) ，则目标电子邮件服务器实际上会被阻止，在 NDR 中将未送达的邮件返回到"发件人： 地址"中的"到外部： 到外部： "发件人：

在具有 Exchange Online 邮箱的 Microsoft 365 组织中或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 可借助 EOP 根据双重来源识别并自动删除邮件，而不会生成 NDR。 但是，根据通过服务传输的单单一批量电子邮件，EOP 始终会无意中发送退信式垃圾邮件。

Backscatterer.org保留一个阻止列表 (也称为负责发送退信的) 电子邮件服务器的 DNS 阻止列表或 DNSBL 名称，EOP 服务器可能出现在此列表中。 但是，我们不会尝试将我们自己从 Backscatterer.org 阻止列表中删除，因为它不是垃圾邮件制造者列表， (他们自身) 。

> [!TIP]
> 这Backscatter.org网站 () 建议使用其服务来检查安全模式下的传入电子邮件，而不是使用"拒绝 <http://www.backscatterer.org/?target=usage> "模式 (大的电子邮件服务几乎总是会发送一些退信) 。
