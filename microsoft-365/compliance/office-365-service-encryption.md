---
title: 服务加密
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
ms.openlocfilehash: 1c31c0d5524370fd417460fbacf3695df4fa0102
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632237"
---
# <a name="service-encryption"></a>服务加密

除了使用卷级加密之外，Exchange Online、Skype for business、SharePoint Online 和 OneDrive for business 还使用服务加密来加密客户数据。 服务加密允许两个密钥管理选项：

- Microsoft 管理所有加密密钥。 （此选项目前在 SharePoint Online、OneDrive for business 和 Skype for Business 中可用。）

- 您的组织提供根键。 您可以使用 Azure Key Vault 管理这些密钥。 此选项称为 "客户密钥"。 目前，客户密钥可用于 Exchange Online、SharePoint Online、OneDrive for business、Skype for business 和团队文件。 如果使用客户密钥，这些密钥将替换 Microsoft 管理的密钥以加密数据。

服务加密提供了多项优势。 例如，客户密钥：

- 在强加密保护之上提供权限保护和管理功能。

- 包括一个 "客户密钥" 选项，该选项使多租户服务能够提供每租户密钥管理。

- 提供 Windows 操作系统管理员的分离，以访问由操作系统存储或处理的客户数据。

- 增强了 Microsoft 365 满足具有有关加密合规性要求的客户需求的能力。

## <a name="customer-key"></a>客户密钥

使用 "客户密钥"，可以使用本地硬件服务模块（HSM）或 Azure Key Vault （AKV）生成自己的加密密钥。 无论生成密钥的方式如何，都可以使用 AKV 来控制和管理 Office 365 使用的加密密钥。 密钥存储在 AKV 中后，可以将其用作加密邮箱数据的 keychains 之一的根。

客户密钥的另一个好处是，您可以控制 Microsoft 处理数据的能力。 如果要从 Office 365 中删除数据（例如，如果要使用 Microsoft 终止服务或删除云中存储的部分数据），则可以执行此操作，并将客户密钥用作技术控制。 这可确保任何人（包括 Microsoft）都不能访问或处理数据。 客户密钥补充并补充了用于控制 Microsoft 人员对数据的访问权限的客户密码箱的补充。

若要了解如何设置用于 Exchange Online、Skype for Business、SharePoint Online （包括工作组网站和 OneDrive for business）的 Microsoft 365 客户密钥，请参阅以下文章：

- [使用客户密钥进行服务加密](customer-key-overview.md)

- [设置客户密钥](customer-key-set-up.md)

- [管理客户密钥](customer-key-manage.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)
 
