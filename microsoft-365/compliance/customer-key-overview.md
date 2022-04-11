---
title: 使用客户密钥执行服务加密
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: seo-marvel-apr2020
description: 本文介绍服务加密在Microsoft 365中如何与客户密钥配合使用。
ms.openlocfilehash: 65098994a6883fdadd3106b74b25a2251239fb3a
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64761078"
---
# <a name="service-encryption-with-customer-key"></a>使用客户密钥执行服务加密

Microsoft 365提供通过 BitLocker 和 Distributed Key Manager (DKM) 启用的基线卷级加密。 Microsoft 365为内容提供额外的加密层。 此内容包括来自 Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和 Microsoft Teams 的数据。

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>服务加密、BitLocker 和 Customer Key 如何协同工作

数据始终使用 BitLocker 和 DKM 在Microsoft 365服务中进行静态加密。 有关详细信息，请参阅[Exchange Online如何保护电子邮件机密](exchange-online-secures-email-secrets.md)。 客户密钥提供额外的保护，防止未经授权的系统或人员查看数据，并补充 Microsoft 数据中心中的 BitLocker 磁盘加密。 服务加密并不是为了阻止 Microsoft 人员访问数据。 相反，客户密钥可帮助你履行控制根密钥的法规或合规性义务。 显式授权Microsoft 365服务使用加密密钥提供增值云服务，如电子数据展示、反恶意软件、反垃圾邮件、搜索索引等。

客户密钥是建立在服务加密之上的，允许你提供和控制加密密钥。 然后，Microsoft 365使用这些密钥来加密静态数据，如[在线服务条款 (OST) ](https://www.microsoft.com/licensing/product-licensing/products.aspx)中所述。 客户密钥可帮助你履行合规性义务，因为你控制Microsoft 365用于加密和解密数据的加密密钥。
  
客户密钥增强了组织满足与云服务提供商指定关键安排的符合性要求的能力。 借助客户密钥，可以在应用程序级别为静态Microsoft 365数据提供和控制根加密密钥。 因此，可以控制组织的密钥。

## <a name="customer-key-with-hybrid-deployments"></a>使用混合部署的客户密钥

客户密钥仅加密云中的静态数据。 客户密钥不适用于保护本地邮箱和文件。 可以使用另一种方法（如 BitLocker）加密本地数据。

## <a name="about-data-encryption-policies"></a>关于数据加密策略

数据加密策略 (DEP) 定义加密层次结构。 此层次结构由服务使用你管理的每个密钥和受 Microsoft 保护的可用性密钥来加密数据。 使用 PowerShell cmdlet 创建 DEP，然后分配这些 DEP 来加密应用程序数据。 客户密钥Microsoft 365支持三种类型的 DEP，每个策略类型使用不同的 cmdlet 并为不同类型的数据提供覆盖范围。 可以定义的 DEP 包括：

**针对多个Microsoft 365工作负荷的 DEP** 这些 DEP 跨多个 M365 工作负荷为租户内的所有用户加密数据。 这些工作负荷包括：

- Teams聊天消息 (1：1 聊天、群聊、会议聊天和频道对话) 
-  (图像、代码片段、视频消息、音频消息、wiki 图像) Teams媒体消息
- Teams存储在 Teams 存储中的呼叫和会议录制
- Teams聊天通知
- 通过Cortana Teams聊天建议
- Teams状态消息
- Exchange Online的用户和信号信息
- Exchange Online邮箱 DEP 尚未加密的邮箱
- Microsoft 信息保护：

  - EDM) 数据（包括数据文件架构、规则包和用于哈希敏感数据的盐）的精确数据匹配 (数据。 对于 EDM 和Microsoft Teams，多工作负载 DEP 会从将 DEP 分配到租户时加密新数据。 对于Exchange Online，客户密钥会加密所有现有数据和新数据。

  - 敏感度标签的标签配置

多工作负荷 DEP 不会加密以下类型的数据。 相反，Microsoft 365使用其他类型的加密来保护此数据。

- SharePoint和OneDrive for Business数据。
- OneDrive for Business和联机SharePoint中保存的Microsoft Teams文件以及一些Teams呼叫和会议录制使用 SharePoint Online DEP 进行加密。
- 其他Microsoft 365工作负荷，例如客户密钥当前不支持的Yammer和 Planner。
- Teams实时事件数据。

可以为每个租户创建多个 DEP，但一次只能分配一个 DEP。 分配 DEP 时，加密会自动开始，但需要一些时间才能完成，具体取决于租户的大小。

**Exchange Online邮箱** DEP 的 DEP 可更精确地控制Exchange Online内的各个邮箱。 使用邮箱 DEP 加密存储在不同类型的 EXO 邮箱中的数据，例如 UserMailbox、MailUser、Group、PublicFolder 和共享邮箱。 每个租户最多可以有 50 个活动 DEP，并将这些 DEP 分配给单个邮箱。 可以将一个 DEP 分配给多个邮箱。

默认情况下，邮箱使用 Microsoft 托管的密钥进行加密。 将客户密钥 DEP 分配到邮箱时：

- 如果邮箱是使用多工作负荷 DEP 加密的，则只要用户或系统操作访问邮箱数据，该服务就使用新的邮箱 DEP 重新绘制邮箱。

- 如果邮箱已使用 Microsoft 托管的密钥进行加密，则只要用户或系统操作访问邮箱数据，该服务将使用新的邮箱 DEP 重新创建邮箱。

- 如果尚未使用默认加密对邮箱进行加密，则服务将邮箱标记为移动。 一旦移动完成，就会进行加密。 邮箱移动根据为所有Microsoft 365设置的优先级进行控制。 有关详细信息，请参阅[Microsoft 365服务中的移动请求](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-microsoft-365-or-office-365-service)。 如果邮箱未在指定时间内加密，请联系 Microsoft。

稍后，可以刷新 DEP 或将不同的 DEP 分配给邮箱，如“[管理客户密钥Office 365](customer-key-manage.md)中所述。 每个邮箱必须具有适当的许可证才能分配 DEP。 有关许可的详细信息，请参阅 [设置客户密钥之前](customer-key-set-up.md#before-you-set-up-customer-key)。

可以将 DEP 分配给满足用户邮箱许可要求的租户的共享邮箱、公用文件夹邮箱和Microsoft 365组邮箱。 不需要针对非用户特定邮箱单独的许可证即可分配客户密钥 DEP。

对于分配给各个邮箱的客户密钥 DEP，你可以在离开服务时请求 Microsoft 清除特定的 DEP。 有关数据清除过程和密钥吊销的信息，请参阅 [撤销密钥并启动数据清除路径过程](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。

在退出服务时撤消对密钥的访问权限时，可用性密钥将被删除，从而导致数据的加密删除。 加密删除可降低数据还原的风险，这对于满足安全性和合规性义务非常重要。

**DEP for SharePoint Online 和 OneDrive for Business** 此 DEP 用于加密存储在 SPO 和 OneDrive for Business 中的内容，包括存储在 SPO 中的Microsoft Teams文件。 如果使用的是多地理位置功能，则可以为组织创建每个地理位置的一个 DEP。 如果不使用多地理位置功能，则每个租户只能创建一个 DEP。 请参阅 [“设置客户密钥”](customer-key-set-up.md)中的详细信息。

### <a name="encryption-ciphers-used-by-customer-key"></a>客户密钥使用的加密密码

客户密钥使用各种加密密码来加密密钥，如下图所示。

用于加密多个Microsoft 365工作负荷的数据的 DEP 的密钥层次结构类似于用于单个Exchange Online邮箱的 DEP 的层次结构。 唯一的区别是将邮箱密钥替换为相应的Microsoft 365工作负荷密钥。

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>用于加密Exchange Online和Skype for Business密钥的加密密码

![Exchange Online客户密钥的加密密码。](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>用于加密SharePoint联机、OneDrive for Business和Teams文件的密钥的加密密码

![SharePoint联机客户密钥的加密密码。](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>相关文章

- [设置客户密钥](customer-key-set-up.md)

- [管理客户密钥](customer-key-manage.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)

- [客户密码箱](customer-lockbox-requests.md)

- [服务加密](office-365-service-encryption.md)
