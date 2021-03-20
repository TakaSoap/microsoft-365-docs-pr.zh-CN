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
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解在 Exchange Online Protection 中配置邮件流和路由的选项 (EOP) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 043f093c801725cdf006c7c3afe7672e67d9fcef
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907022"
---
# <a name="mail-flow-in-eop"></a>EOP 中的邮件流

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

在具有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，发送到组织的所有邮件都先通过 EOP，然后工作人员才能看到这些邮件。 在邮件路由到工作线程收件箱之前，可以通过 EOP 路由邮件进行处理，有一些选项可供选择。

## <a name="working-with-messages-and-message-access-options"></a>使用邮件和邮件访问选项

EOP 提供了邮件路由方式的灵活性。 以下主题说明了邮件流过程中的步骤。

[使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) 介绍基于目录的边缘阻止功能，该功能允许您在服务网络外围拒绝针对无效收件人的邮件。

[View or Edit Managed Domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)介绍了如何管理与 EOP 服务相关的域。

如果将子域添加到组织，则 EOP 服务也可以帮助您管理这些子域。 有关子域的更多信息，请 [通过 Enable mail flow for subdomains in Exchange Online 了解](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。

[使用连接器配置邮件流](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 介绍了连接器，并展示了如何使用连接器自定义邮件路由。 方案包括确保与合作伙伴组织进行安全通信，并设置智能主机。

[Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 介绍如何在邮件路由到 EOP 之前的服务或设备时配置连接器。

在独立 EOP 组织中，您需要执行几个配置步骤，以确保垃圾邮件正确路由到每个用户的垃圾邮件文件夹。 这些在配置独立 [EOP 以将垃圾邮件发送到混合环境的垃圾邮件文件夹中详细说明](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 如果您不想将邮件移动到每个用户的垃圾邮件文件夹，您可以选择其他操作，通过编辑反垃圾邮件策略 (也称为内容筛选器策略) 。 有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="verify-mail-flow"></a>验证邮件流

要验证包括连接器配置在内的 EOP 安装是否正常工作，请参阅[设置 EOP 服务](set-up-your-eop-service.md)中的"您如何知道此任务有效？"部分。

[通过验证 Microsoft 365](/exchange/mail-flow-best-practices/test-mail-flow) 连接器测试邮件流提供了有关测试邮件流是否正确设置的说明。