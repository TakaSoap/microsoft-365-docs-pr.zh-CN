---
title: 了解 Microsoft 365 合规性中心的存档邮箱
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 了解存档邮箱以提供其他邮箱存储。
ms.openlocfilehash: a863df7be1b73d6a50d818bca5948f3017e3d373
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2022
ms.locfileid: "62242126"
---
# <a name="learn-about-archive-mailboxes"></a>了解存档邮箱

Microsoft 365 中的邮箱存档（又称为 *就地存档*）为用户提供额外的邮箱存储空间。 启用存档邮箱后，用户的当前邮箱将变为其 *主邮箱* 并创建了一个名为“*存档邮箱*”的邮箱。 这两个邮箱都被视为符合性功能的用户邮箱，例如从Microsoft 365 合规中心搜索内容、Microsoft 365 保留和诉讼保留。

用户可以使用 Outlook 和 Outlook 网页版访问邮件并将其存储在存档邮箱中。 用户可以在其主邮箱和存档邮箱之间移动或复制邮件。 他们还可以使用“恢复已删除邮件”工具恢复存档邮箱中“可恢复的项目”文件夹下的已删除邮件。

## <a name="managing-archive-mailboxes-with-messaging-records-management-mrm"></a>使用消息记录管理 (MRM) 管理存档邮箱

邮件也可以通过消息记录管理 (MRM) 中的[默认 Exchange 保留策略](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)移动到存档邮箱。 此默认策略会自动分配给每个邮箱，并执行以下操作：

  - 将两年或以上的邮件从用户主邮箱移动到存档邮箱。

  - 将 14 天或以上的邮件从用户主邮箱的“可恢复的项目”文件夹移动到存档邮箱中的“可恢复的项目”文件夹。

可以使用[保留标记](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)自定义组织的 MRM 策略。 有关示例配置，请参阅[为组织中的邮箱设置存档和删除策略](set-up-an-archive-and-deletion-policy-for-mailboxes.md)。

> [!NOTE]
> MRM（如 Microsoft 365 保留策略和保留标签）还可以在指定的时间段后自动删除电子邮件。 作为比 Microsoft 365 保留更旧的技术，MRM 继续与 Microsoft 365 合规性的保留策略和保留标签并行工作。 有关详细信息，请参阅[使用保留策略和保留标签，而非旧功能](retention.md#use-retention-policies-and-retention-labels-instead-of-older-features)。

## <a name="auto-expanding-archiving"></a>自动扩展存档 

在启用了用户的存档邮箱后，最多可获得 100 GB 的额外存储空间。 如果用户需要更多存储空间，请启用自动扩展存档，以便在存档邮箱中提供高达 1.5 TB 的额外存储空间。 有关详细信息，请参阅[了解自动扩展存档](autoexpanding-archiving.md)。

## <a name="licensing"></a>授权

有关支持存档邮箱的 Outlook 许可证列表，请在[针对 Exchange 功能的 Outlook 许可要求](https://support.microsoft.com/office/46b6b7c5-c3ca-43e5-8424-1e2807917c99)中参阅就地存档的相关信息。

## <a name="next-steps"></a>后续步骤

请参阅[在合规性中心中启用存档邮箱](enable-archive-mailboxes.md)。