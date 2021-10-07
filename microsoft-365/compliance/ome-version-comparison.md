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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 本文帮助说明不同版本的 Office 365 邮件加密。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 508a129cd472c8843e2af4a012560b17a44c49aa
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194341"
---
# <a name="compare-versions-of-ome"></a>比较 OME 的版本

> [!IMPORTANT]
> 2021 年 2 月 28 日，Microsoft 已弃用对 Exchange Online 中的 AD RMS 的支持。 如果已部署混合环境，其中 Exchange 邮箱联机，并且在本地将 IRM 与 Active Directory RMS 一同使用，则需要迁移到 Azure。 已部署到中等GCC的组织也会受到影响。 有关信息，请参阅本文中的"Exchange Online中的 AD RMS 弃用概述"。

本文的其余部分将旧版 OME Office 365 邮件加密 (OME) 与新的 OME 功能Office 365 高级邮件加密。 新功能是 IRM 中 OME 和信息权限管理与 OME 的合并 (更新) 。 此外，还概述了部署到 GCC High 的独特特征。 这两者可以在组织中共存。 有关新功能如何工作的信息，请参阅[Office 365 邮件加密 (OME) 。 ](ome.md)

本文是有关本文的更多系列文章的一Office 365 邮件加密。 本文适用于管理员和 ITPros。 如果您只是查找有关发送或接收加密邮件的信息，请参阅[Office 365 邮件加密 (OME](ome.md)) 中的文章列表，并找到最符合您需求的文章。

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>AD RMS 弃用概述Exchange Online

Exchange Online信息权限管理 (IRM) IRM 功能，可提供电子邮件和附件的联机和脱机保护。 默认情况下，Exchange Online Azure 信息保护。 但是，您的组织可能配置了 Exchange Online IRM 以使用本地 Active Directory 权限管理服务 (AD RMS) 。 企业中的 AD RMS Exchange Online即将停用。 相反，Azure 信息保护将完全替换 AD RMS。

若要评估此弃用是否会影响你的组织，请参阅如何在 Exchange Online 中将[AD RMS 迁移到 Azure RMS。](/exchange/troubleshoot/administration/migrate-ad-rms-to-azure) 本文提供有关迁移选项的建议。

## <a name="side-by-side-comparison-of-ome-features-and-capabilities"></a>OME 特性和功能并行比较

|           **情况**           | **旧 OME**    | **AD RMS 中的 IRM**        | **新的 OME 功能** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*发送加密邮件*        |通过Exchange邮件流规则|最终用户从桌面或Outlook Outlook启动;或Exchange邮件流规则|最终用户从 Web 上的桌面Outlook桌面Outlook for Mac Outlook启动的最终用户;通过Exchange DLP (传输规则) 和数据丢失防护 (DLP) |
|*权限管理模板*       |   不适用      |"不要转发"选项和自定义模板|不要转发选项、仅加密选项和自定义模板|
|*收件人类型*                   |内部和外部收件人|仅内部收件人         |内部和外部收件人|
|*内部收件人的体验*|收件人收到一条 HTML 邮件，在 Web 浏览器或移动应用中下载并打开该邮件|客户端中的本机内Outlook体验|使用客户端访问同一组织中收件人的本机Outlook体验。  收件人可以使用客户端从 OME 门户阅读邮件，Outlook (无需下载或应用) 。|
|*外部收件人的体验*|收件人收到一条 HTML 邮件，在 Web 浏览器或移动应用中下载并打开该邮件|不适用|收件人的本机内Microsoft 365体验。 所有其他收件人都可以从 OME 门户阅读 (无需下载或应用) 。|
|*附件权限*           |对附件没有限制|附件受到保护|附件受"不要转发"选项和自定义模板的保护。 管理员可以选择是否保护仅加密选项的附件。|
|*自带密钥 (BYOK) 支持*|无                |无               |BYOK 支持          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>与旧 OME 相比的新 OME 功能的优点

新功能具有以下优点：

- 能够使用仅加密选项 (启用安全协作) 、不要转发选项和自定义限制。
- 发件人可以从桌面客户端、Outlook客户端Outlook for Mac加密Outlook 网页版邮件。
- Microsoft 365在受支持的客户端中，收件人可以使用Outlook体验。 或者，管理员可以选择向Microsoft 365显示品牌体验。
- 组织外部Microsoft 365帐户（如 Gmail、Yahoo 和 Microsoft 帐户）与 OME 门户联合，这将为这些收件人提供更好的用户体验。 所有其他标识都使用一次传递代码访问加密邮件。
- 管理员可以自定义品牌，并创建多个品牌模板。
- 管理员可以吊销使用新功能加密的电子邮件。
- 新功能通过安全与合规中心提供详细的 &amp; 使用情况报告。

## <a name="office-365-advanced-message-encryption-capabilities"></a>Office 365 高级邮件加密功能

Office 365 高级邮件加密 OME 功能外，还提供其他功能。 您必须在组织中Office 365 邮件加密新的邮件加密功能，才能使用高级邮件加密功能。 此外，若要使用这些功能，收件人必须通过 OME 门户查看和回复安全邮件。 高级功能包括：

- 邮件吊销

- 邮件过期

- 多个品牌模板

Office 365 高级邮件加密高中不支持GCC。

有关使用高级邮件加密的信息[，请参阅](ome-advanced-message-encryption.md)Office 365 高级邮件加密。

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>高部署中Office 365 邮件加密部署GCC特征

如果您计划在高Office 365 邮件加密使用GCC，则收件人体验有一些独特特征。

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>High 和 GCC High 收件人GCC加密的电子邮件

发件人可以在 Outlook for PC 和 Mac 及 Outlook 网页版 中手动加密电子邮件，或者组织可以设置策略以使用 Exchange 流规则加密电子邮件。

在 GCC High 内的收件人会收到与所有其他用户相同的Outlook阅读体验，Outlook 网页版 Mac 接收相同的内联阅读体验。

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>高GCC和非GCC收件人之间的加密电子邮件

高GCC中的发件人可以在"高"边界GCC发送加密电子邮件，反之亦然。

高GCC的所有收件人（包括商业 Microsoft 365 用户、Outlook.com 用户和其他电子邮件提供商（如 Gmail 和 Yahoo）的其他用户）将收到包装邮件。 此包装邮件将收件人重定向到 OME 门户，收件人可以在其中阅读和回复邮件。 对于高发送 OME 加密GCC外部的发件人，也是如此GCC高。

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>旧版 OME 与同一租户中的新功能共存

你可以在同一租户中同时使用旧版 OME 和新功能。 作为管理员，通过选择创建邮件流规则时想要使用的 OME 版本来完成此操作。

- 若要指定 OME 的旧版本，请使用 Exchange 邮件流规则操作 **应用以前版本的 OME**。

- 若要指定新功能，请使用"邮件流Exchange **操作"应用Office 365 邮件加密权限保护"。**

用户可以手动发送通过桌面、Outlook 和 Outlook for Mac 中的新功能Outlook 网页版。

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>从旧 OME 迁移到新功能

尽管这两个版本的 OME 可以共存，但我们强烈建议您编辑使用规则操作 **应用以前版本的 OME** 以使用新功能的旧邮件流规则。 更新这些规则以使用邮件流规则操作应用Office 365 邮件加密 **权限保护**。 有关说明，请参阅[Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md)。

## <a name="get-started-with-ome"></a>OME 入门

通常，会自动为组织启用新的 OME 功能。 有关组织中新的 OME 功能的信息，请参阅设置新的 OME Office 365 邮件加密[功能](set-up-new-message-encryption-capabilities.md)。

如果已启用 Azure 信息保护，将自动为组织启用旧版 OME。 过去，即使未启用 Azure 信息保护，旧版 OME 也有效。 但现在不再如此。

若要开始使用旧版 OME，如果已启用 Azure 信息保护，请配置使用规则操作应用以前版本的 **OME** 的邮件流规则。 有关说明，请参阅 [定义用于加密电子邮件的邮件流规则](define-mail-flow-rules-to-encrypt-email.md)。
