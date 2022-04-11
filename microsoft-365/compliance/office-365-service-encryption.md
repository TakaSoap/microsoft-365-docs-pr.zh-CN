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
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要：了解Microsoft Office 365中的数据复原能力。
ms.openlocfilehash: 9b569bc30a9d7d8485fe0004cf46ba39277c47ae
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760792"
---
# <a name="service-encryption"></a>服务加密

除了使用卷级加密外，Exchange Online、Microsoft Teams、SharePoint联机和OneDrive for Business还使用服务加密来加密客户数据。 服务加密允许使用两个密钥管理选项：

## <a name="microsoft-managed-keys"></a>Microsoft 管理的密钥
Microsoft 管理所有加密密钥，包括服务加密的根密钥。 此选项目前默认启用Exchange Online、SharePoint联机、OneDrive for Business。 Microsoft 托管的密钥提供默认服务加密，除非你决定使用客户密钥加入。 如果稍后决定在不遵循数据清除路径的情况下停止使用客户密钥，则数据将使用 Microsoft 托管的密钥保持加密状态。 数据始终至少在此默认级别加密。 

## <a name="customer-key"></a>客户密钥
提供与服务加密一起使用的根密钥，并使用 Azure 密钥保管库 管理这些密钥。 Microsoft 管理所有其他密钥。 此选项称为“客户密钥”，目前可用于Exchange Online、SharePoint联机和OneDrive for Business。  (以前称为 BYOK 的高级加密。 有关原始公告，请参阅[增强Office 365客户的透明度和控制](https://www.microsoft.com/en-us/microsoft-365/blog/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)。) 

服务加密具有多种优势：

- 在 BitLocker 上提供额外的保护层。

- 提供Windows操作系统管理员对操作系统存储或处理的应用程序数据的访问权限的分离。

- 包括一个客户密钥选项，该选项允许多租户服务提供每租户密钥管理。

- 增强了Microsoft 365满足对加密有特定合规性要求的客户的需求的能力。

使用客户密钥，可以使用本地硬件服务模块 (HSM) 或 Azure 密钥保管库 (AKV) 生成自己的加密密钥。 无论如何生成密钥，都可使用 AKV 来控制和管理Office 365使用的加密密钥。 将密钥存储在 AKV 中后，可以将其用作加密邮箱数据或文件的密钥链之一的根。

客户密钥的另一个好处是控制 Microsoft 处理数据的能力。 如果要从Office 365中删除数据，例如，如果要终止 Microsoft 服务或删除存储在云中的一部分数据，则可以执行此操作，并使用客户密钥作为技术控制。 删除数据可确保包括 Microsoft 在内的任何人都无法访问或处理数据。 客户密钥是客户密码箱的补充，用于控制 Microsoft 人员对数据的访问。

若要了解如何为Exchange Online、Microsoft Teams、SharePoint联机（包括团队网站和OneDrive for Business）设置Microsoft 365的客户密钥，请参阅以下文章：

- [使用客户密钥执行服务加密](customer-key-overview.md)

- [设置客户密钥](customer-key-set-up.md)

- [管理客户密钥](customer-key-manage.md)

- [滚动或轮换客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)
