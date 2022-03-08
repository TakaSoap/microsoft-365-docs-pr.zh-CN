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
description: 摘要：了解数据恢复能力Microsoft Office 365。
ms.openlocfilehash: 54bae9fa0203d76c598c4dee337ee15f24a2fc24
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63317635"
---
# <a name="service-encryption"></a>服务加密

除了使用卷级加密之外，Exchange Online、Microsoft Teams、SharePoint Online 和 OneDrive for Business 还使用服务加密来加密客户数据。 服务加密允许两种密钥管理选项：

## <a name="microsoft-managed-keys"></a>Microsoft 管理的密钥
Microsoft 管理所有加密密钥，包括用于服务加密的根密钥。 此选项当前默认为 Exchange Online、SharePoint Online OneDrive for Business。 除非决定使用客户密钥载入，否则 Microsoft 托管密钥提供默认服务加密。 如果以后决定停止使用客户密钥，而不遵循数据清除路径，则你的数据会使用 Microsoft 管理的密钥保持加密状态。 你的数据始终至少在此默认级别进行加密。 

## <a name="customer-key"></a>客户密钥
提供用于服务加密的根密钥，然后使用 Azure 密钥保管库管理这些密钥。 Microsoft 管理所有其他密钥。 此选项称为客户密钥，当前可用于 Exchange Online、SharePoint Online 和 OneDrive for Business。  (BYOK 高级加密。 请参阅[增强客户对原始Office 365](https://www.microsoft.com/en-us/microsoft-365/blog/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)的透明度和控制。) 

服务加密具有多种优势：

- 在 BitLocker 顶部提供一层额外的保护。

- 使Windows管理员无法访问操作系统存储或处理的应用程序数据。

- 包括一个"客户密钥"选项，该选项允许多租户服务提供每租户密钥管理。

- 增强用户Microsoft 365满足对加密有特定合规性要求的客户的需求。

使用客户密钥，可以使用本地硬件服务模块 (HSM) 或 Azure Key Vault (AKV) 。 无论您如何生成密钥，您都可使用 AKV 来控制和管理由 Office 365。 一旦密钥存储在 AKV 中，就可以用作加密邮箱数据或文件的密钥链之一的根。

客户密钥的另一个好处是，你可以控制 Microsoft 处理数据的能力。 如果你想要从 Office 365 中删除数据，例如如果你想要终止 Microsoft 服务或删除存储在云中的部分数据，你可以这样做，并使用客户密钥作为技术控制。 删除数据可确保包括 Microsoft 在内的任何人都无法访问或处理数据。 客户密钥是对用于控制 Microsoft 人员访问数据的客户密码箱的补充。

若要了解如何为 Microsoft 365、Exchange Online、Microsoft Teams SharePoint Online（包括团队网站和 OneDrive for Business）设置客户密钥，请参阅以下文章：

- [使用客户密钥执行服务加密](customer-key-overview.md)

- [设置客户密钥](customer-key-set-up.md)

- [管理客户密钥](customer-key-manage.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)
