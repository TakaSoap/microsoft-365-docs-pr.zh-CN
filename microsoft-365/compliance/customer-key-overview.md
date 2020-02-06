---
title: Office 365 中的客户密钥的服务加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 使用 "客户密钥"，可以控制组织的加密密钥，然后配置 Office 365 以使用它们在 Microsoft 数据中心中对静态数据进行加密。
ms.openlocfilehash: ee62065542ea50091d73362dd8d05f2e4e7dc337
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804757"
---
# <a name="service-encryption-with-customer-key-in-office-365"></a>Office 365 中的客户密钥的服务加密

Office 365 提供了通过 BitLocker 和分布式密钥管理器（DKM）启用的基准、卷级加密。 Office 365 在应用程序级别为你的内容提供了额外的加密层。 此内容包含来自 Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和团队文件的数据。 这一添加的加密层称为 "服务加密"。

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>服务加密、BitLocker 和客户密钥如何协同工作

服务加密可确保在应用程序层对 rest 上的内容进行加密。 **Office 365 服务中的静态数据始终在 BitLocker 和 DKM 中进行加密**。 有关详细信息，请参阅 "Office 365 的安全性、隐私和合规性信息"，以及[Exchange Online 如何保护您的电子邮件密码](exchange-online-secures-email-secrets.md)。 客户密钥可提供其他保护，以防止未经授权的系统或人员查看数据，并补充 Microsoft 数据中心中的 BitLocker 磁盘加密。 服务加密并不意味着阻止 Microsoft 人员访问客户数据。 主要目的是帮助客户满足控制根键的管理法规或合规性义务。 客户显式授权 O365 服务使用其加密密钥来提供增值云服务，如电子数据展示、反恶意软件、反垃圾邮件、搜索索引等。

客户密钥是基于服务加密构建的，允许你提供和控制加密密钥。 然后，Office 365 将使用这些密钥来加密 rest 上的数据，如[联机服务条款（OST）](https://www.microsoft.com/licensing/product-licensing/products.aspx)中所述。 客户密钥可帮助您满足合规性义务，因为您控制 Office 365 用于加密和解密数据的加密密钥。
  
客户密钥增强了贵组织满足符合性要求的能力，这些要求通过云服务提供商指定关键安排。 使用 "客户密钥"，可以在应用程序级别为 Office 365 数据提供和控制根加密密钥。 因此，您可以控制组织的键。 如果决定退出该服务，请撤消对您的组织的根密钥的访问。 对于所有 Office 365 服务，吊销密钥的访问权限是路径中的第一步，用于数据删除。 通过撤销对密钥的访问权限，该服务无法读取数据。

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>客户密钥在 Office 365 中对静态数据进行加密

使用您提供的密钥，Office 365 的客户密钥加密：

- SharePoint Online、OneDrive for Business 和团队文件。
- 上载到 OneDrive for business 的文件。
- Exchange Online 邮箱内容，包括电子邮件正文内容、日历条目和电子邮件附件中的内容。
- Skype for Business 中的文本对话。

目前，我们并不提供对 Skype 会议直播和 Skype 会议内容上载的加密密钥的客户控制。 而是将此内容与 Office 365 中的其他所有内容一起加密。

### <a name="customer-key-with-hybrid-deployments"></a>包含混合部署的客户密钥

客户密钥仅对云中的静态数据进行加密。 客户密钥不能保护您的内部部署邮箱和文件。 您可以使用其他方法（例如 BitLocker）对本地数据进行加密。

## <a name="about-the-data-encryption-policy-dep"></a>关于数据加密策略（DEP）

数据加密策略定义加密层次结构，以使用您提供的每个密钥以及由 Microsoft 保护的可用性密钥来加密数据。 使用 PowerShell cmdlet 创建 DEPs，这些 cmdlet 因每个服务而异，并将其分配给加密应用程序数据。 例如：

**Exchange Online 和 Skype For business**最高可为每个租户创建 50 DEPs。 将 DEPs 关联到 Azure Key Vault 中的客户密钥，然后将 DEPs 分配给各个邮箱。 将 DEP 分配到邮箱时：

- 为邮箱移动标记邮箱。 根据此处在[office 365 服务中的移动请求中](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)所述的 office 365 中的优先级。

- 移动邮箱时，会进行加密。 允许使用新的 DEP 对邮箱进行加密，以72小时为单位。 如果邮箱在你分配 DEP 之后等待72小时后未加密，请与 Microsoft 联系。

稍后，您可以刷新 DEP 或根据 "[管理 Office 365 的客户密钥](customer-key-manage.md)" 中所述，为邮箱指定一个不同的 dep。 每个邮箱必须具有适当的许可证，才能分配 DEP。 有关许可的详细信息，请参阅[设置客户密钥之前](customer-key-set-up.md#before-you-set-up-customer-key)。

**SharePoint Online、OneDrive For business 和团队文件**如果您使用的是多地理位置功能，则可以为您的组织为每个地理位置创建一个 DEP。 您可以为每个地理位置使用不同的客户密钥。 如果不使用多地理位置功能，则只能为每个租户创建一个 DEP。 分配 DEP 时，加密会自动开始，但可能需要一些时间才能完成。 请参阅[设置适用于 Office 365 的客户密钥](customer-key-set-up.md)中的详细信息。

## <a name="leaving-the-service"></a>离开服务

客户密钥允许你在离开 Office 365 服务时撤销你的密钥，从而帮助你满足合规性义务。 在退出服务的过程中吊销密钥时，将删除可用性密钥，从而导致加密删除了数据。 加密删除降低了数据 remanence 的风险，这对于满足安全和合规性义务来说非常重要。 有关数据清除过程和密钥吊销的信息，请参阅[废除您的密钥并启动数据清除路径过程](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。

### <a name="encryption-ciphers-used-by-customer-key"></a>客户密钥使用的加密密码

"客户密钥" 使用各种加密密码来加密密钥，如下图所示。

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>用于加密 Exchange Online 和 Skype for business 的密钥的加密密码

![Exchange Online 客户密钥的加密密码](media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>用于加密 SharePoint Online、OneDrive for Business 和团队文件的密钥的加密密码

![SharePoint Online 客户密钥的加密密码](media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>相关文章

- [设置适用于 Office 的客户密钥365](customer-key-set-up.md)

- [管理 Office 365 的客户密钥](customer-key-manage.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)

- [Office 365 中的客户密码箱](customer-lockbox-requests.md)

- [Office 365 服务加密](office-365-service-encryption.md)
