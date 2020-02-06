---
title: Office 365 服务加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要：了解 Microsoft Office 365 中的数据恢复能力。
ms.openlocfilehash: 5b22584e677dd4815b991b4e95b5ad59feb2fbc2
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799542"
---
# <a name="office-365-service-encryption"></a>Office 365 服务加密

除了使用卷级加密之外，Exchange Online、Skype for business、SharePoint Online 和 OneDrive for business 还使用服务加密来加密客户数据。 服务加密允许两个密钥管理选项：

- Microsoft 管理所有加密密钥。 （此选项目前在 SharePoint Online、OneDrive for business 和 Skype for Business 中可用。）

- 客户提供用于服务加密的根键，并且客户使用 Azure Key Vault 管理这些密钥。 Microsoft 管理所有其他密钥。 此选项称为 "客户密钥"，目前适用于 Exchange Online、SharePoint Online 和 OneDrive for Business。 （以前称为使用 BYOK 的高级加密。 请参阅增强针对原始公告的[Office 365 客户的透明度和控制](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)。

服务加密提供了多项优势。 例如，客户密钥：

- 在强加密保护之上提供权限保护和管理功能。

- 包括一个 "客户密钥" 选项，该选项使多租户服务能够提供每租户密钥管理。

- 提供 Windows 操作系统管理员的分离，以访问由操作系统存储或处理的客户数据。

- 增强了 Office 365 满足有关加密合规性要求的客户需求的能力。

## <a name="customer-key"></a>客户密钥

使用 "客户密钥"，可以使用本地硬件服务模块（HSM）或 Azure Key Vault （AKV）生成自己的加密密钥。 无论生成密钥的方式如何，都可以使用 AKV 来控制和管理 Office 365 使用的加密密钥。 密钥存储在 AKV 中后，可以将其用作加密邮箱数据的 keychains 之一的根。

客户密钥的另一个好处是，您可以控制 Microsoft 处理数据的能力。 如果要从 Office 365 中删除数据（例如，如果要使用 Microsoft 终止服务或删除云中存储的部分数据），则可以执行此操作，并将客户密钥用作技术控制。 这可确保任何人（包括 Microsoft）都不能访问或处理数据。 客户密钥补充并补充了用于控制 Microsoft 人员对数据的访问权限的客户密码箱的补充。

若要了解如何为 Exchange Online、Skype for Business、SharePoint Online （包括工作组网站和 OneDrive for Business）设置适用于 Office 365 的客户密钥，请参阅以下文章：

- [Office 365 中的客户密钥的服务加密](customer-key-overview.md)

- [设置适用于 Office 的客户密钥365](customer-key-set-up.md)

- [管理 Office 365 的客户密钥](customer-key-manage.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)
 