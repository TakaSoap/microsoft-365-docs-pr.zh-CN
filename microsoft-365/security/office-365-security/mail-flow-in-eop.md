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
ms.localizationpriority: medium
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解在 EOP 服务中配置邮件流和Exchange Online Protection () 。
ms.technology: mdo
ms.prod: m365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: 296cd8aaa92005f094de2ee7d1c9f8bb9427df16
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63681009"
---
# <a name="mail-flow-in-eop"></a>EOP 中的邮件流

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在Microsoft 365具有 Exchange Online 邮箱的组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，发送到组织的所有邮件都先通过 EOP，然后工作人员才能看到这些邮件。 在邮件路由到工作线程收件箱之前，可以通过 EOP 路由邮件进行处理，有一些选项可供选择。

## <a name="working-with-messages-and-message-access-options"></a>使用邮件和邮件访问选项

EOP 提供了邮件路由方式的灵活性。 以下主题说明了邮件流过程中的步骤。

[使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) 介绍基于目录的边缘阻止功能，该功能允许您拒绝在服务网络外围向无效收件人发送的邮件。

[View or edit accepted domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 介绍如何管理与 EOP 服务关联的域。

如果将子域添加到组织，则 EOP 服务也可以帮助您管理这些子域。 有关子域的更多信息，请[通过为 Exchange Online 中的子域启用邮件流](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。

[使用连接器配置邮件流](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 介绍了连接器，并展示了如何使用连接器自定义邮件路由。 方案包括确保与合作伙伴组织进行安全通信，并设置智能主机。

[Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 介绍如何在邮件路由到 EOP 之前的服务或设备时配置连接器。

在 EOP 保护内部部署 Exchange 邮箱的混合环境中，您需要配置邮件流规则 (也称为) 传输规则Exchange。 这些邮件流规则转换 EOP 垃圾邮件筛选裁定，以便邮箱中的垃圾邮件规则可以将邮件移动到"垃圾邮件"文件夹。 有关详细信息，请参阅[在混合环境中将 EOP 配置为向“垃圾邮件”文件夹递送垃圾邮件](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)。 如果您不想将邮件移动到每个用户的"垃圾邮件"文件夹，您可以选择其他操作，通过编辑反垃圾邮件策略 (也称为内容筛选器策略) 。 有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="verify-mail-flow"></a>验证邮件流

要验证包括连接器配置在内的 EOP 安装是否正常工作，请参阅[设置 EOP 服务](/exchange/standalone-eop/set-up-your-eop-service)中的"您如何知道此任务有效？"部分。

[通过验证您的邮件Microsoft 365连接器](/exchange/mail-flow-best-practices/test-mail-flow)提供了有关测试您的邮件流是否正确设置的说明。
