---
title: EOP 中的邮件流
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解在 Exchange Online Protection 和 EOP 应用程序中配置邮件流 () 。
ms.openlocfilehash: c58981afaadf2c4083b6a6db99c74cf9544715c3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827721"
---
# <a name="mail-flow-in-eop"></a>EOP 中的邮件流

在有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，发送到您的组织的所有邮件都将先通过 EOP，然后工作人员才能看到这些邮件。 你可以选择如何路由邮件，这些邮件通过 EOP 处理，然后才能路由到工作人员收件箱。

## <a name="working-with-messages-and-message-access-options"></a>使用邮件和邮件访问选项

EOP 在您的邮件路由方法上提供了灵活性。 以下主题说明了邮件流过程中的步骤。

[使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) 介绍基于目录的边缘阻止功能，允许您拒绝在服务网络外围向无效收件人发送邮件。

[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)介绍了如何管理与 EOP 服务相关的域。

如果将子域添加到组织，则 EOP 服务也可以帮助您管理这些子域。 在 Exchange Online 中为 [子域启用邮件流，了解有关子域的详细信息](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。

[配置使用连接器的邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 介绍了连接器，并演示如何使用连接器自定义邮件路由。 方案包括确保与合作伙伴组织进行安全通信，并设置智能主机。

[适用于连接器的增强筛选](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 介绍了在 EOP 之前，如果邮件已路由到服务或设备，如何配置连接器。

在独立 EOP 组织中，您需要执行几个配置步骤，以确保垃圾邮件正确路由到每个用户的垃圾邮件文件夹。 这些信息在" [配置独立 EOP"中详细说明了如何向混合环境中的"垃圾邮件"文件夹递送垃圾邮件](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 如果您不想将邮件移至每个用户的垃圾电子邮件文件夹，可以选择其他操作，方法为编辑反垃圾邮件策略 (也称为内容筛选策略) 。 有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="verify-mail-flow"></a>验证邮件流

要验证包括连接器配置在内的 EOP 安装是否正常工作，请参阅[设置 EOP 服务](set-up-your-eop-service.md)中的"您如何知道此任务有效？"部分。

[通过验证 Microsoft 365 连接器来测试邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) ，该说明提供了测试您的邮件流设置正确的说明。
