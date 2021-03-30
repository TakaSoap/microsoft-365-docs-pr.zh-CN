---
title: 邮件加密 (OME) 版本比较
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 本文帮助说明不同版本的 Office 365 邮件加密之间的差异。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5c8b0852220b2144c4ab92ec9b692299c9d2c860
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408565"
---
# <a name="compare-versions-of-ome"></a>比较 OME 的版本

> [!IMPORTANT]
> 2021 年 2 月 28 日，Microsoft 将弃用对 Exchange Online 中 AD RMS 的支持。 如果已部署 Exchange 邮箱联机的混合环境，并且将 IRM 与本地 Active Directory RMS 一同使用，则需要迁移到 Azure。 已部署到 GCC 中等环境的组织也会受到影响。 有关信息，请参阅本文中的"Exchange Online 中的 AD RMS 弃用概述"。

本文的其余部分将旧版 Office 365 邮件加密 (OME) 与新的 OME 功能和 Office 365 高级邮件加密进行比较。 新功能是 OME 和信息权限管理与 IRM (合并和) 。 还概述了部署到 GCC High 中的独特特征。 这两者可以在组织中共存。 有关新功能如何工作的信息，请参阅[Office 365 邮件加密 (OME) 。 ](ome.md)

本文是有关 Office 365 邮件加密的一系列较大文章的一部分。 本文适用于管理员和 ITPros。 如果您只是查找有关发送或接收加密邮件的信息，请参阅 [Office 365 ](ome.md) 邮件加密 (OME) 中的文章列表，并找到最符合您需求的文章。

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Exchange Online 中的 AD RMS 弃用概述

Exchange Online 包括信息权限管理 (IRM) 功能，可为电子邮件和附件提供联机和脱机保护。 默认情况下，Exchange Online 使用 Azure 信息保护。 但是，您的组织可能将 Exchange Online IRM 配置为使用内部部署 Active Directory 权限管理服务 (AD RMS) 。 Exchange Online 中的 AD RMS 支持即将停用。 相反，Azure 信息保护将完全替换 AD RMS。

若要评估此弃用是否会影响组织，请参阅如何在 Exchange Online 中将[AD RMS 迁移到 Azure RMS。](https://support.microsoft.com/help/5001237) 本文提供有关迁移选项的建议。

## <a name="side-by-side-comparison-of-ome-features-and-capabilities"></a>OME 特性和功能并行比较

|           **情况**           | **旧 OME**    | **AD RMS 中的 IRM**        | **新的 OME 功能** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*发送加密邮件*        |通过 Exchange 邮件流规则|最终用户从 Outlook 桌面或 Outlook 网页版启动;或通过 Exchange 邮件流规则|最终用户从 Outlook 桌面、Outlook for Mac 或 Outlook 网页版启动;通过 Exchange 邮件流规则 (传输规则) DLP (数据丢失防护) |
|*权限管理模板*       |   不适用      |"不要转发"选项和自定义模板|不要转发选项、仅加密选项和自定义模板|
|*收件人类型*                   |内部和外部收件人|仅内部收件人         |内部和外部收件人|
|*内部收件人的体验*|收件人收到一条 HTML 邮件，该消息将在 Web 浏览器或移动应用中下载并打开|Outlook 客户端中的本机内联体验|使用 Outlook 客户端的同一组织中收件人的本机内联体验。  收件人可以使用 Outlook 客户端（而非 Outlook）从 OME 门户 (无需下载或应用) 。|
|*外部收件人的体验*|收件人收到一条 HTML 邮件，该消息将在 Web 浏览器或移动应用中下载并打开|不适用|Microsoft 365 收件人的本机内联体验。 所有其他收件人都可以从 OME 门户阅读 (无需下载或应用) 。|
|*附件权限*           |对附件没有限制|附件受到保护|附件受"不要转发"选项和自定义模板的保护。 管理员可以选择是否保护仅加密选项的附件。|
|*自带密钥 (BYOK) 支持*|无                |无               |BYOK 支持          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>新 OME 功能与旧版 OME 相比的优势

新功能具有以下优点：

- 能够使用仅加密选项 (启用安全协作) 、不要转发选项和自定义限制。
- 发件人可以从 Outlook 桌面、Outlook for Mac 和 Web 上的 Outlook 客户端手动发送使用新功能加密的邮件。
- Microsoft 365 收件人可以使用受支持的 Outlook 客户端中的内联体验。 或者，管理员可以选择向 Microsoft 365 收件人显示品牌体验。
- Microsoft 365 之外的帐户（如 Gmail、Yahoo 和 Microsoft 帐户）与 OME 门户联合，这将为这些收件人提供更好的用户体验。 所有其他标识都使用一次传递代码访问加密邮件。
- 管理员可以自定义品牌，并创建多个品牌模板。
- 管理员可以吊销使用新功能加密的电子邮件。
- 新功能通过安全与合规中心提供详细的 &amp; 使用情况报告。

## <a name="office-365-advanced-message-encryption-capabilities"></a>Office 365 高级邮件加密功能

Office 365 高级邮件加密提供了新的 OME 功能外的其他功能。 必须在组织中设置新的 Office 365 邮件加密功能，才能使用高级邮件加密功能。 此外，若要使用这些功能，收件人必须通过 OME 门户查看和回复安全邮件。 高级功能包括：

- 邮件吊销

- 邮件过期

- 多个品牌模板

GCC High 不支持 Office 365 高级邮件加密。

有关使用高级邮件加密的信息，请参阅 [Office 365 高级邮件加密](ome-advanced-message-encryption.md)。

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>GCC 高部署中 Office 365 邮件加密的唯一特征

如果计划在 GCC High 环境中使用 Office 365 邮件加密，则收件人体验有一些独特特征。

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>GCC High 和 GCC High 收件人之间的加密电子邮件

发件人可以手动加密 Outlook for PC 和 Mac 以及 Outlook 网页中的电子邮件，或者组织可以设置策略以使用 Exchange 邮件流规则加密电子邮件。

GCC High 内的收件人在 Outlook for PC 和 Mac 以及 Web 上的 Outlook 中接收与所有其他用户相同的内联阅读体验。

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>GCC High 与 Non-GCC High 收件人之间的加密电子邮件

GCC High 内的发件人可以在 GCC High 边界外发送加密电子邮件，反之亦然。

GCC High 外部的所有收件人（包括商业 Microsoft 365 用户、Outlook.com 用户和其他电子邮件提供商（如 Gmail 和 Yahoo）的其他用户）将收到包装邮件。 此包装邮件将收件人重定向到 OME 门户，收件人可以在其中阅读和回复邮件。 GCC High sending OME encrypted mail to GCC High 外部的发件人也是如此。

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>旧版 OME 与同一租户中的新功能共存

你可以在同一租户中同时使用旧版 OME 和新功能。 作为管理员，通过选择创建邮件流规则时想要使用的 OME 版本来完成此操作。

- 若要指定 OME 的旧版本，请使用 Exchange 邮件流规则操作 **应用以前版本的 OME**。

- 若要指定新功能，请使用 Exchange 邮件流规则操作应用 **Office 365 邮件加密和权限保护**。

用户可以手动发送使用 Outlook 桌面、Outlook for Mac 和 Outlook 网页版中的新功能加密的邮件。

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>从旧 OME 迁移到新功能

尽管这两个版本的 OME 可以共存，但我们强烈建议您编辑使用规则操作 **应用以前版本的 OME** 以使用新功能的旧邮件流规则。 更新这些规则以使用邮件流规则操作应用 **Office 365 邮件加密和权限保护**。 有关说明，请参阅 [在 Office 365](define-mail-flow-rules-to-encrypt-email.md)中定义用于加密电子邮件的邮件流规则。

## <a name="get-started-with-ome"></a>OME 入门

通常，会自动为组织启用新的 OME 功能。 有关组织中新的 OME 功能详细信息，请参阅设置 [新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。

如果已启用 Azure 信息保护，将自动为组织启用旧版 OME。 过去，即使未启用 Azure 信息保护，旧版 OME 也有效。 但现在不再如此。

若要开始使用旧版 OME，如果已启用 Azure 信息保护，请配置使用规则操作应用以前版本的 **OME** 的邮件流规则。 有关说明，请参阅 [定义用于加密电子邮件的邮件流规则](define-mail-flow-rules-to-encrypt-email.md)。