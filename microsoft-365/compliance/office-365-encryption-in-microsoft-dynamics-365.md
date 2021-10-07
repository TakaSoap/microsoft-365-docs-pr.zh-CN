---
title: Microsoft Dynamics 365 中的加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 了解 Microsoft 如何使用加密技术在 Microsoft 数据库中和传输过程中静态保护 Microsoft Dynamics 365 中的客户数据。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6fc07bba7ceccdfd2b215e29ef48dbd1f23c0cdf
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206069"
---
# <a name="encryption-in-microsoft-dynamics-365"></a>Microsoft Dynamics 365 中的加密

Microsoft 使用加密技术来保护 Dynamics 365 中的客户数据，同时在 Microsoft 数据库中处于静态状态，并且正在用户设备和我们的数据中心之间传输。 客户与 Microsoft 数据中心建立的连接已加密，所有公共终结点都使用行业标准 TLS 进行保护。 TLS 有效地建立了安全性增强的浏览器到服务器连接，以帮助确保桌面和数据中心之间的数据机密性和完整性。 数据加密激活后，无法将其关闭。 有关详细信息，请参阅字段 [级数据加密](/previous-versions/dynamicscrm-2016/developers-guide/dn481562(v=crm.8))。

Dynamics 365 对一组包含敏感信息（如用户名和电子邮件密码）的默认实体属性Microsoft SQL Server标准单元格级别加密。 此功能可帮助组织满足与 FIPS 140-2 关联的合规性要求。 字段级数据加密在利用[Microsoft Dynamics CRM](/previous-versions/dynamicscrm-2016/administering-dynamics-365/hh699800(v=crm.8))电子邮件路由器的方案中尤为重要，该路由器必须存储用户名和密码，才能在 Dynamics 365 实例和电子邮件服务之间实现集成。

Dynamics 365 的所有实例使用[Microsoft SQL Server 透明数据加密](/sql/relational-databases/security/encryption/transparent-data-encryption) (TDE) 在静态数据写入磁盘时执行数据 (实时) 。 TDE 对SQL Server、Azure SQL 数据库和 Azure SQL数据仓库数据文件进行加密。 默认情况下，Microsoft 存储和管理 Dynamics 365 实例的数据库加密密钥。  (Dynamics 365 for Financials 使用的密钥由 .NET Framework Data Protection API.) 

Dynamics 365 管理中心中的管理密钥功能使管理员能够自行管理与 Dynamics 365 实例关联的数据库加密密钥。  (自管理数据库加密密钥仅适用于 Microsoft Dynamics 365 的 2017 年 1 月更新，可能不会在更高版本中提供。 有关详细信息，请参阅管理 [Dynamics 365 (online) ](/dynamics365/customer-engagement/admin/manage-encryption-keys-instance)实例 .) 密钥管理功能支持 PFX 和 BYOK 加密密钥文件，如 HSM 中存储的文件。  (有关通过 Internet 生成和传输受 HSM 保护的密钥的信息，请参阅如何为 Azure Key Vault 生成和传输 [受 HSM](/azure/key-vault/key-vault-hsm-protected-keys)保护的密钥) 

若要使用上传加密密钥选项，需要公钥和私钥加密密钥。

密钥管理功能通过使用 Azure 密钥保管库安全存储加密密钥来降低加密密钥管理的复杂性。 Azure Key Vault 有助于保护云应用程序和服务使用的加密密钥和密钥。 密钥管理功能不需要你拥有 Azure 密钥保管库订阅，在大多数情况下，无需访问保管库中用于 Dynamics 365 的加密密钥。