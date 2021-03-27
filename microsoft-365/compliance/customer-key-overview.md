---
title: 使用客户密钥执行服务加密
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
- m365solution-mip
- m365initiative-compliance
ms.custom: seo-marvel-apr2020
description: 本文将介绍服务加密在 Microsoft 365 中如何使用客户密钥。
ms.openlocfilehash: 21291dc45cd634cd5b6a88c4e58972c17486724f
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394720"
---
# <a name="service-encryption-with-customer-key"></a>使用客户密钥执行服务加密

Microsoft 365 提供通过 BitLocker 和分布式密钥管理器和 DKM (启用的基线) 。 Microsoft 365 在内容的应用程序层添加了一层加密。 此内容包括来自 Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和 Teams 文件的数据。 这一添加的加密层称为服务加密。

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>服务加密、BitLocker 和客户密钥如何协同工作

服务加密可确保静态内容在服务层加密。 **你的数据在 Microsoft 365** 服务中始终使用 BitLocker 和 DKM 进行加密。 有关详细信息，请参阅"安全、隐私和合规性信息"和 Exchange Online 如何 [保护您的电子邮件密码](exchange-online-secures-email-secrets.md)。 客户密钥提供了防止未经授权的系统或人员查看数据的额外保护，并补充了 Microsoft 数据中心中的 BitLocker 磁盘加密。 服务加密并非旨在阻止 Microsoft 人员访问客户数据。 主要目的是帮助客户履行控制根密钥的法规或合规性义务。 客户明确授权 O365 服务使用其加密密钥来提供增值云服务，如电子数据展示、反恶意软件、反垃圾邮件、搜索索引等。

客户密钥基于服务加密构建，可让你提供和控制加密密钥。 然后，Microsoft 365 使用这些密钥加密你的其余数据，如联机服务条款 ([OST) 。 ](https://www.microsoft.com/licensing/product-licensing/products.aspx) 客户密钥有助于你履行合规性义务，因为你控制 Microsoft 365 用于加密和解密数据的加密密钥。
  
客户密钥增强了组织满足合规性要求的能力，这些要求指定了与云服务提供商的关键安排。 使用客户密钥，你在应用程序级别提供和控制 Microsoft 365 静态数据的根加密密钥。 因此，你可以对组织的密钥进行控制。 如果决定退出服务，则撤消对组织的根密钥的访问权限。 对于所有 Microsoft 365 服务，撤销对密钥的访问是删除数据的第一步。 通过撤销对密钥的访问，数据对服务不可读。

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>客户密钥对 Office 365 中的其余数据进行加密

使用你提供的密钥，应用程序级别的客户密钥将进行加密：

- SharePoint Online、OneDrive for Business 和 Teams 文件。
- 上传到 OneDrive for Business 的文件。
- Exchange Online 邮箱内容，包括电子邮件正文内容、日历条目和电子邮件附件中的内容。
- 来自 Skype for Business 的文本对话。

我们目前不为客户提供对 Skype 会议直播和 Skype 会议内容上载加密密钥的控制。 相反，此内容与 Office 365 中的所有其他内容一起加密。

### <a name="customer-key-with-hybrid-deployments"></a>混合部署的客户密钥

客户密钥仅加密云中的其余数据。 客户密钥无法保护本地邮箱和文件。 可以使用另一种方法（如 BitLocker）加密本地数据。

## <a name="about-the-data-encryption-policy-dep"></a>关于 DEP 策略 (策略) 

数据加密策略定义加密层次结构，以使用你提供的每个密钥以及受 Microsoft 保护的可用性密钥加密数据。 使用 PowerShell cmdlet 创建 DEP（每个服务有所不同），并分配这些 DESP 以加密应用程序数据。 例如：

**Exchange Online 和 Skype for Business** 每个租户可以创建最多 50 个 DESP。 将 DEP 关联到 Azure 密钥保管库中的客户密钥，然后将 DEPS 分配给各个邮箱。 将 DEP 分配给邮箱时：

- 邮箱标记为进行邮箱移动。 根据 Microsoft 365 中优先级，如此处所述 [在 Microsoft 365](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)服务中移动请求。

- 邮箱移动时进行加密。 允许使用新的 DEP 加密邮箱 72 小时。 如果邮箱在您分配 DEP 后等待 72 小时后未加密，请与 Microsoft 联系。

稍后，您可以刷新 DEP 或为邮箱分配不同的 DEP，如 [管理 Office 365 的客户密钥中所述](customer-key-manage.md)。 每个邮箱必须具有适当的许可证才能分配 DEP。 有关许可详细信息，请参阅 [设置客户密钥之前](customer-key-set-up.md#before-you-set-up-customer-key)。

> [!NOTE]
> DEP 可以应用于符合用户邮箱许可要求的租户的共享邮箱、公用文件夹邮箱和 Microsoft 365 组邮箱，即使其中某些邮箱类型无法分配许可证 (公用文件夹邮箱和 Microsoft 365 组邮箱) 或需要用于增加存储 (共享邮箱) 的许可证。

**SharePoint Online、OneDrive for Business 和 Teams 文件** 如果你使用的是多地理位置功能，则每个地理位置最多为组织创建一个 DEP。 你可以针对每个地理位置使用不同的客户密钥。 如果未使用多地理位置功能，则只能为每个租户创建一个 DEP。 分配 DEP 时，加密将自动开始，但可能需要一段时间才能完成。 请参阅设置客户 [密钥中的详细信息](customer-key-set-up.md)。

## <a name="leaving-the-service"></a>离开服务

客户密钥通过允许在离开 Microsoft 365 服务时吊销密钥来帮助你履行合规性义务。 在离开服务时吊销密钥时，可用性密钥将被删除，从而导致数据的加密删除。 加密删除可以减少数据重新管理的风险，这一点对于履行安全和合规义务非常重要。 有关数据清除过程和密钥吊销的信息，请参阅 [撤销密钥并开始数据清除路径过程](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。

### <a name="encryption-ciphers-used-by-customer-key"></a>客户密钥使用的加密密码

客户密钥使用各种加密密码来加密密钥，如下图所示。

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>用于加密 Exchange Online 和 Skype for Business 的密钥的加密密码

![Exchange Online 客户密钥的加密密码](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>用于加密 SharePoint Online、OneDrive for Business 和 Teams 文件的密钥的加密密码

![SharePoint Online 客户密钥的加密密码](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>相关文章

- [设置客户密钥](customer-key-set-up.md)

- [管理客户密钥](customer-key-manage.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)

- [客户密码箱](customer-lockbox-requests.md)

- [服务加密](office-365-service-encryption.md)