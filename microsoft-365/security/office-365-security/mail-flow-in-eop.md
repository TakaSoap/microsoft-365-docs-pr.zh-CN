---
title: EOP 中的邮件流
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
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解有关在 Exchange Online Protection （EOP）中配置邮件流和路由的选项。
ms.openlocfilehash: cb2ae7370d50fe32802ad5c279cc2170eb35f581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208326"
---
# <a name="mail-flow-in-eop"></a>EOP 中的邮件流

在具有 Exchange Online 邮箱的 Microsoft 365 组织中，或在没有 Exchange Online 邮箱的独立 Exchange Online Protection （EOP）组织中，发送到您的组织的所有邮件都将通过 EOP，然后您的工作人员才能看到它们。 您可以选择如何路由通过 EOP 进行处理的邮件，然后再将这些邮件路由到您的工作人员收件箱。

## <a name="working-with-messages-and-message-access-options"></a>使用邮件和邮件访问选项

EOP 提供了路由邮件的灵活性。 以下主题说明了邮件流过程中的步骤。

[使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)介绍基于目录的边缘阻止功能，该功能使您可以在服务网络外围拒绝对无效收件人的邮件。

[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)介绍了如何管理与 EOP 服务相关的域。

如果将子域添加到组织，则 EOP 服务也可以帮助您管理这些子域。 有关子域的详细信息，请参阅在[Exchange Online 中为子域启用邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。

[使用连接器配置邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)介绍连接器，并说明如何使用它们来自定义邮件路由。 方案包括确保与合作伙伴组织进行安全通信，并设置智能主机。

[增强的连接器筛选](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)介绍了在 EOP 之前将邮件路由到服务或设备时如何配置连接器。

在独立 EOP 组织中，您需要执行几个配置步骤，以确保将垃圾邮件正确路由到每个用户的垃圾邮件文件夹。 [配置独立 EOP 将垃圾邮件传递到混合环境中的 "垃圾邮件" 文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)中进行了详细介绍。 如果不想将邮件移动到每个用户的垃圾邮件文件夹，则可以通过编辑反垃圾邮件策略（也称为 "内容筛选器策略"）来选择另一个操作。 有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="verify-mail-flow"></a>验证邮件流

要验证包括连接器配置在内的 EOP 安装是否正常工作，请参阅[设置 EOP 服务](set-up-your-eop-service.md)中的"您如何知道此任务有效？"部分。

[通过验证 Microsoft 365 连接器来测试邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)提供了有关测试您的邮件流设置正确的说明。
