---
title: Azure 中的加密
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
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 了解 Azure 中可用的加密，例如 Azure 磁盘加密
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f3672800b6f90277195a63b640911ea1ed24cac9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152943"
---
# <a name="encryption-in-azure"></a>Azure 中的加密

Azure 中的技术安全措施（如加密的通信和运营过程）可帮助确保数据安全。 还可以灵活地实现其他加密功能并管理自己的加密密钥。 无论客户配置如何，Microsoft 都会应用加密来保护 Azure 中的客户数据。 Microsoft 还让你可以通过一系列高级技术来控制 Azure 中托管的数据，以加密、控制和管理加密密钥，以及控制和审核对数据的访问。 此外，Azure 存储提供了一组全面的安全性功能，这些功能共同使开发人员能够构建安全的应用程序。

Azure 提供了许多保护数据的机制，当数据从一个位置移动到另一个位置时。 Microsoft 在云服务与客户之间传输时，使用 TLS 来保护数据。 Microsoft 数据中心与连接到 Azure 服务的客户端系统协商 TLS 连接。 完全向前保密 (PFS) 通过唯一密钥保护客户客户端系统和 Microsoft 云服务之间的连接。 连接还使用基于 RSA 的 2，048 位加密密钥长度。 此组合使某人难以截获和访问传输中的数据。

通过使用客户端加密、HTTPS 或 SMB 3.0，可以在应用程序和 Azure 之间传输数据。 [](/azure/storage/storage-client-side-encryption) 你可以为自己的虚拟机与虚拟机和用户之间的 (启用) 加密。 使用 [Azure 虚拟网络](https://azure.microsoft.com/services/virtual-network/)，可以使用行业标准 IPsec 协议加密企业 VPN 网关与 Azure 之间以及位于虚拟网络上的 VM 之间的流量。

对于静态数据，Azure 提供了许多加密选项，如对 AES-256 的支持，让你能够灵活地选择最能满足你需求的数据存储方案。 当使用服务加密Azure 存储数据存储自动加密，并且 VM[](/azure/storage/storage-service-encryption)使用的操作系统和数据磁盘可以加密。 有关详细信息，请参阅[Azure 中Windows虚拟机的安全建议](/azure/security/azure-security-disk-encryption)。 此外，可以使用共享访问签名授予Azure 存储中数据对象的[委派访问权限](/azure/storage/storage-dotnet-shared-access-signature-part-1)。 Azure 还为静态数据提供加密[，透明数据加密Azure SQL 数据库数据仓库 。](/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql)

有关 Azure 中的加密功能详细信息，请参阅 [Azure 加密概述](/azure/security/security-azure-encryption-overview) 和 [Azure 静态数据加密](/azure/security/azure-security-encryption-atrest)。

## <a name="azure-disk-encryption"></a>Azure 磁盘加密

借助 Azure 磁盘加密，你可以对 IaaS Windows Vm 磁盘中的 (和 Linux 基础结构) 加密。 Azure 磁盘加密利用 Windows 的 BitLocker 功能DM-Crypt Linux 的 DM-Crypt 功能为操作系统和数据磁盘提供卷级加密。 它还可确保 VM 磁盘上的所有数据在 Azure 存储中处于其余状态加密。 Azure 磁盘加密与 Azure 密钥保管库集成，可帮助你控制、管理和审核加密密钥和密钥的使用。

有关详细信息，请参阅[Azure 中Windows虚拟机的安全建议](/azure/virtual-machines/windows/security-recommendations)。

## <a name="azure-storage-service-encryption"></a>Azure 存储服务加密

使用[Azure 存储 加密](/azure/storage/storage-service-encryption)，Azure 存储在将数据保留到存储中之前自动加密数据，并在检索之前解密数据。 加密、解密和密钥管理过程对用户完全透明。 Azure 存储服务加密可用于 Azure [Blob 存储](https://azure.microsoft.com/services/storage/blobs/)和 Azure[文件](https://azure.microsoft.com/services/storage/files/)。 还可以将 Microsoft 管理的加密密钥与 Azure 存储 服务加密一同使用，或者可以使用自己的加密密钥。  (有关使用你自己的密钥的信息，请参阅 存储 Azure Key Vault 中的[客户托管密钥进行服务加密](/azure/storage/common/storage-service-encryption-customer-managed-keys)。 有关使用 Microsoft 管理的密钥的信息，请参阅 存储 Service [Encryption for Data at Rest](/azure/storage/storage-service-encryption).) 此外，您还可以自动使用加密。 例如，可以使用 Azure 存储 资源提供程序[REST API、](/rest/api/storagerp/)适用于[.NET](/dotnet/api/overview/azure/storage)的 存储 资源提供程序客户端库、Azure PowerShell 或[Azure CLI，](/azure/storage/storage-azure-cli)以编程方式对存储帐户启用或[](/powershell/azureps-cmdlets-docs)禁用 存储 服务加密。

某些Microsoft 365服务使用 Azure 存储数据。 例如，SharePoint Online 和 OneDrive for Business 在 Azure Blob 存储中存储数据，Microsoft Teams将聊天服务的数据存储在表、blob 和队列中。 此外，Microsoft 365 合规中心 中的合规性管理器功能将客户输入的数据以加密形式存储在[Azure Cosmos DB（](/azure/cosmos-db/database-encryption-at-rest)即平台即服务 (PaaS) 、全局分布的多模型数据库中）。 Azure 存储服务加密对 Azure Blob 存储和表中存储的数据进行加密，Azure 磁盘加密对队列中的数据以及 Windows 和 IaaS 虚拟机磁盘进行加密，为操作系统和数据磁盘提供卷加密。 该解决方案可确保虚拟机磁盘上的所有数据在 Azure 存储中处于其余状态加密。 [Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest)中的静态加密是通过使用多种安全技术实现的，包括安全密钥存储系统、加密网络和加密 API。

## <a name="azure-key-vault"></a>Azure Key Vault

安全密钥管理不仅仅是加密最佳做法的核心;它对于保护云中的数据也至关重要。 [Azure 密钥保管](/azure/key-vault/key-vault-whatis) 库使你能够加密密钥和小密钥，如密码，这些密钥使用存储在硬件安全模块中的密钥 (HSM) 。 Azure Key Vault 是 Microsoft 推荐的用于管理和控制对云服务使用的加密密钥的访问的解决方案。 可以将访问密钥的权限分配给服务或具有特定帐户Azure Active Directory用户。 Azure Key Vault 使组织无需配置、修补和维护 HSM 和密钥管理软件。 借助 Azure Key Vault，Microsoft 永远不会看到你的密钥和应用程序无法直接访问它们;您维护控件。 还可以在 HSM 中导入或生成密钥。 具有包含 Azure 信息保护的订阅的组织可以配置其 Azure 信息保护租户，以使用客户管理的[](/information-protection/plan-design/byok-price-restrictions)密钥"自带密钥 (BYOK) ) 并[记录其使用情况](/information-protection/deploy-use/log-analyze-usage)。