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
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要：了解 Microsoft Office 365 中服务层的数据加密。
ms.openlocfilehash: a8faded033ade013924eeeab269aa213840430b4
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193458"
---
# <a name="office-365-service-encryption"></a>Office 365 服务加密

除了将 BitLocker 用于卷级加密之外，Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和团队也使用服务加密来加密客户数据。 服务加密允许两个密钥管理选项：

- Microsoft 管理所有加密密钥。 此选项目前在 SharePoint Online、OneDrive for business、Skype for business 和团队聊天版中可用。 默认情况下，使用 Microsoft 托管密钥对数据进行加密。

- 您的组织提供根键。 您可以使用 Azure Key Vault 管理这些密钥。 此选项称为 "客户密钥"。 目前，客户密钥可用于 Exchange Online、SharePoint Online、OneDrive for business、Skype for business 和团队文件。 如果使用客户密钥，这些密钥将替换 Microsoft 托管密钥以加密数据。

无论选择哪个选项，服务加密都会提供多种好处：

- 强制执行用户身份验证以检索和解密授权用户请求的数据。

- 提供 Windows 操作系统管理员的分离，以访问由操作系统存储或处理的客户数据。

- 增强了 Office 365 满足有关加密合规性要求的客户需求的能力。

若要了解如何为 Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和团队文件设置适用于 Office 365 的客户密钥，请参阅以下文章：

- [Office 365 中的客户密钥的服务加密](customer-key-overview.md)

- [设置适用于 Office 的客户密钥365](customer-key-set-up.md)

- [管理 Office 365 的客户密钥](customer-key-manage.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)
