---
title: 了解客户密钥的可用性密钥
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
description: 了解用于恢复丢失的客户密钥的可用性密钥。
ms.openlocfilehash: 1fd80d23980957402ae7d5e79a91e57d28df38f9
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64761828"
---
# <a name="learn-about-the-availability-key-for-customer-key"></a>了解客户密钥的可用性密钥

可用性密钥是创建数据加密策略时自动生成和预配的根密钥。 Microsoft 365存储和保护可用性密钥。 可用性密钥在功能上类似于使用客户密钥提供用于服务加密的两个根密钥。 可用性密钥将密钥包装在密钥层次结构中较低一层。 与在 Azure 密钥保管库中提供和管理的密钥不同，无法直接访问可用性密钥。 Microsoft 365自动化服务以编程方式管理可用性密钥。 这些服务启动的自动化操作从不涉及对可用性密钥的直接访问。

可用性密钥的主要目的是提供从所管理的根密钥意外丢失的恢复功能。 丢失可能是由于管理不善或恶意操作造成的。 如果无法控制根密钥，请联系Microsoft 支持部门和 Microsoft 将使用可用性密钥帮助你完成恢复过程。 你将使用可用性密钥迁移到新的数据加密策略，并使用预配的新根密钥。

由于以下三个原因，存储和控制可用性密钥与 Azure 密钥保管库密钥有故意不同：

- 如果两个 Azure 密钥保管库密钥的控制丢失，可用性密钥将提供恢复“防碎玻璃”功能。
- 逻辑控件和安全存储位置的分离提供深度防御，并防止从单个攻击或故障点丢失所有密钥和数据。
- 如果Microsoft 365服务由于暂时性错误而无法访问 Azure 密钥保管库中托管的密钥，则可用性密钥提供高可用性功能。 此规则仅适用于Exchange Online和Skype for Business服务加密。 SharePoint联机、OneDrive for Business和Teams文件永远不会使用可用性密钥，除非显式指示 Microsoft 启动恢复过程。

分担保护数据的责任，使用各种保护和过程进行密钥管理，最终可以降低所有密钥 (的风险，因此数据) 将永久丢失或销毁。 Microsoft 为你提供了在离开服务时对可用性密钥的禁用或销毁的唯一权限。 按照设计，Microsoft 没有人可以访问可用性密钥：它只能通过 Microsoft 365 服务代码访问。

有关如何保护密钥的详细信息，请参阅 [Microsoft 信任中心](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) 。
  
## <a name="availability-key-uses"></a>可用性密钥使用

可用性密钥提供恢复功能，以便外部男性化程序或恶意内部成员窃取对密钥保管库的控制，或无意中管理不当导致根密钥丢失的情况。 此恢复功能适用于与客户密钥兼容的所有Microsoft 365服务。 各个服务使用可用性密钥的方式不同。 Microsoft 365仅使用以下方式的可用性密钥。

### <a name="exchange-online-and-skype-for-business-uses"></a>Exchange Online和Skype for Business使用

除了恢复功能之外，Exchange Online和Skype for Business使用可用性密钥来确保与访问根密钥的服务相关的暂时性或间歇性操作问题期间的数据可用性。 当服务由于暂时性错误而无法访问 Azure 密钥保管库中的任一客户密钥时，该服务会自动使用可用性密钥。 服务从不直接转到可用性密钥。

Exchange Online和Skype for Business中的自动化系统可能会在暂时性错误期间使用可用性密钥来支持自动后端服务，例如防病毒、电子发现、数据丢失防护、邮箱移动和数据索引编制。

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-uses"></a>SharePoint联机、OneDrive for Business和Teams文件使用

对于SharePoint联机、OneDrive for Business和Teams文件，可用性密钥永远不会在恢复功能之外使用，客户必须明确指示 Microsoft 在恢复方案中启动使用可用性密钥。 自动化服务操作仅依赖于 Azure 密钥保管库中的客户密钥。 有关密钥层次结构如何适用于这些服务的深入信息，请参阅[SharePoint联机、OneDrive for Business和Teams文件如何使用可用性密钥](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key)。

## <a name="availability-key-security"></a>可用性密钥安全性

Microsoft 通过实例化可用性密钥并采取广泛措施保护数据保护，与你共享数据保护的责任。 Microsoft 不会向客户公开对可用性密钥的直接控制。 例如，只能滚动 () Azure 密钥保管库中拥有的密钥轮换。 有关详细信息，请参阅 [滚动或轮换客户密钥或可用性密钥](customer-key-availability-key-roll.md)。

### <a name="availability-key-secret-stores"></a>可用性密钥机密存储

Microsoft 保护访问控制的内部机密存储（如面向客户的 Azure 密钥保管库）中的可用性密钥。 我们实施访问控制，以防止 Microsoft 管理员直接访问其中包含的机密。 机密存储操作（包括密钥轮换和删除）通过自动命令进行，这些命令从不涉及对可用性密钥的直接访问。 机密存储管理操作仅限于特定工程师，需要通过内部工具 Lockbox 提升特权。 特权提升需要经理批准和理由才能获得授权。 密码箱可确保访问在到期或工程师注销时与自动访问吊销有时间限制。

**Exchange Online和Skype for Business** 可用性密钥存储在 Exchange Online Active Directory 机密存储中。 可用性密钥安全地存储在Active Directory 域控制器内特定于租户的容器中。 此安全存储位置独立于SharePoint联机、OneDrive for Business和Teams文件机密存储。

**SharePoint联机、OneDrive for Business和Teams文件** 可用性密钥存储在服务团队管理的内部机密存储中。 此安全机密存储服务具有前端服务器，其中应用程序终结点和SQL 数据库作为后端。 可用性密钥存储在SQL 数据库中，由使用 AES-256 和 HMAC 组合来加密静态可用性密钥的机密存储加密密钥包装 (加密) 。 机密存储加密密钥存储在同一SQL 数据库的逻辑隔离组件中，并使用 Microsoft 证书颁发机构 (CA) 管理的证书中包含的 RSA-2048 密钥进一步加密。 这些证书存储在对数据库执行操作的机密存储前端服务器中。

### <a name="defense-in-depth"></a>深入防御

Microsoft 采用深入防御策略，防止恶意行为者影响存储在 Microsoft 云中的客户数据的保密性、完整性或可用性。 实施特定的预防和检测控制措施是为了保护机密存储和可用性密钥，作为总体安全策略的一部分。

Microsoft 365是为了防止滥用可用性密钥而构建的。 应用程序层是唯一可用于加密和解密数据的密钥（包括可用性密钥）的方法。 只有Microsoft 365服务代码能够解释和遍历密钥层次结构以进行加密和解密活动。 客户密钥的存储位置、可用性密钥、其他分层密钥和客户数据之间存在逻辑隔离。 如果一个或多个位置遭到入侵，此隔离可降低数据泄露的风险。 层次结构中的每个层都内置了 24x7 入侵检测功能来保护存储的数据和机密。

实施访问控制是为了防止未经授权访问内部系统，包括可用性密钥机密存储。 Microsoft 工程师无法直接访问可用性密钥机密存储。 有关访问控制的其他详细信息，请查看[Microsoft 365中的管理访问控制](/compliance/assurance/assurance-administrative-access-controls-overview)。

技术控制阻止 Microsoft 人员登录到高特权服务帐户，否则攻击者可能会使用这些帐户来模拟Microsoft 服务。 例如，这些控件阻止交互式登录。

安全日志记录和监视控制是实现的另一项深入防御措施，可降低Microsoft 服务和数据的风险。 Microsoft 服务团队已部署用于生成警报和审核日志的活动监视解决方案。 所有服务团队都将其日志上传到中心存储库，在该存储库中聚合和处理日志。 内部工具会自动检查记录，以确认服务是否处于最佳、可复原和安全状态。 标记了异常活动以供进一步查看。

任何指示可能违反 Microsoft 安全策略的日志事件会立即引起 Microsoft 安全团队的注意。 Microsoft 365安全部门已配置警报来检测对可用性密钥密钥存储的尝试访问。 如果 Microsoft 人员尝试以交互方式登录到服务帐户，也会生成警报，而服务帐户受访问控制禁止和保护。 Microsoft 365安全性还会在Microsoft 365服务与正常基线操作的偏差时检测和发出警报。 试图滥用Microsoft 365服务的男性制造者将触发警报，导致罪犯被逐出 Microsoft 云环境。

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>使用可用性密钥从密钥丢失中恢复

如果失去对客户密钥的控制，可用性密钥可让你恢复和重新加密数据。

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Exchange Online和Skype for Business的恢复过程

如果失去对客户密钥的控制，可用性密钥使你能够恢复数据并使受影响的Microsoft 365资源重新联机。 恢复时，可用性密钥将继续保护数据。在高级别上，若要从密钥丢失中完全恢复，需要创建新的 DEP 并将受影响的资源移动到新策略。

若要使用新的客户密钥加密数据，请在 Azure 密钥保管库中创建新密钥，使用新的客户密钥创建新的 DEP，然后将新 DEP 分配给当前使用前一个 DEP 加密的邮箱，其中的密钥丢失或泄露。

此重新加密过程最多可能需要 72 小时。 这是更改 DEP 时的标准持续时间。
  
### <a name="recovery-procedure-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint联机、OneDrive for Business和Teams文件的恢复过程

对于SharePoint联机、OneDrive for Business和Teams文件，在恢复功能之外永远不会使用可用性密钥。 必须在恢复方案中显式指示 Microsoft 启动可用性密钥的使用。 若要启动恢复过程，请联系 Microsoft 激活可用性密钥。 激活后，可用性密钥将自动用于解密数据，以便使用与新客户密钥关联的新创建的 DEP 对数据进行加密。  

此操作与组织中的站点数成正比。 调用 Microsoft 以使用可用性密钥后，应在大约四小时内完全联机。

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>Exchange Online和Skype for Business如何使用可用性密钥

使用客户密钥创建 DEP 时，Microsoft 365生成与该 DEP 关联的数据加密策略密钥 (DEP 密钥) 。 该服务对 DEP 密钥进行三次加密：一次使用每个客户密钥，一次使用可用性密钥。 仅存储 DEP 密钥的加密版本，并且只能使用客户密钥或可用性密钥解密 DEP 密钥。 然后，DEP 密钥用于加密用于加密单个邮箱的邮箱密钥。
  
Microsoft 365遵循此过程在客户使用服务时解密和提供数据：
  
1. 使用客户密钥解密 DEP 密钥。

2. 使用解密的 DEP 密钥解密邮箱密钥。

3. 使用解密的邮箱密钥解密邮箱本身，使你可以访问邮箱中的数据。

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>SharePoint联机、OneDrive for Business和Teams文件如何使用可用性密钥

SharePoint联机和OneDrive for Business体系结构以及客户密钥和可用性密钥的实现不同于Exchange Online和Skype for Business。
  
当组织移动到客户管理的密钥时，Microsoft 365创建特定于组织的中间密钥 (TIK) 。 Microsoft 365使用每个客户密钥加密 TIK 两次，并存储 TIK 的两个加密版本。 仅存储 TIK 的加密版本，并且只能使用客户密钥解密 TIK。 然后，TIK 用于加密站点密钥，然后用于加密 blob 密钥 (也称为文件区块密钥) 。 根据文件大小，服务可能会将文件拆分为多个文件区块，每个区块都有唯一的键。 blob (文件区块本身) 使用 blob 密钥进行加密，并存储在 Microsoft Azure Blob 存储服务中。
  
Microsoft 365遵循此过程在客户使用服务时解密和提供客户文件：

1. 使用客户密钥解密 TIK。

2. 使用解密的 TIK 解密站点密钥。

3. 使用解密的站点密钥解密 Blob 密钥。

4. 使用解密的 Blob 密钥解密 Blob。

Microsoft 365通过向 Azure 密钥保管库发出两个解密请求来解密 TIK，并略有偏移。 第一个完成提供结果，取消另一个请求。
  
如果无法访问客户密钥，Microsoft 365还会使用可用性密钥对 TIK 进行加密，并将此密钥与使用每个客户密钥加密的 TIK 一起存储。 仅当客户在恶意或意外地失去对密钥的访问权限时，才使用可用性密钥的 TIK 来登记恢复路径。
  
出于可用性和缩放原因，解密的 TIK 缓存在受时间限制的内存缓存中。 在 TIK 缓存设置为过期前两小时，Microsoft 365尝试解密每个 TIK。 解密 TIK 会延长缓存的生存期。 如果 TIK 解密在大量时间内失败，Microsoft 365会生成警报，在缓存过期之前通知工程。 只有当客户调用 Microsoft 时，才会Microsoft 365启动恢复操作，这涉及到使用存储在 Microsoft 机密存储中的可用性密钥解密 TIK，并使用解密的 TIK 和一组新的客户提供的 Azure 密钥保管库 密钥再次载入租户。
  
从今天起，客户密钥已涉及 Azure Blob 存储中存储的 SharePoint Online 文件数据的加密和解密链，但未SharePoint存储在SQL 数据库中的联机列表项或元数据。 Microsoft 365不将可用性密钥用于Exchange Online、Skype for Business、SharePoint联机、OneDrive for Business和Teams上述情况以外的文件，即客户发起。 用户对客户数据的访问受客户密码箱保护。

## <a name="availability-key-triggers"></a>可用性密钥触发器

Microsoft 365仅在特定情况下触发可用性密钥。 这些情况因服务而异。

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Exchange Online和Skype for Business的触发器
  
1. Microsoft 365读取邮箱分配到的 DEP，以确定两个客户密钥在 Azure 密钥保管库中的位置。

2. Microsoft 365从 DEP 中随机选择两个客户密钥之一，并向 Azure 密钥保管库发送请求以使用客户密钥解包 DEP 密钥。

3. 如果使用客户密钥解包 DEP 密钥的请求失败，Microsoft 365向 Azure 密钥保管库 发送第二个请求，这次指示它使用备用 (第二) 客户密钥。

4. 如果第二个使用客户密钥解包 DEP 密钥的请求失败，Microsoft 365检查这两个请求的结果。

    - 如果检查确定请求未能返回系统错误：

       - Microsoft 365触发可用性密钥来解密 DEP 密钥。

       - 然后，Microsoft 365使用 DEP 密钥解密邮箱密钥并完成用户请求。 

       - 在这种情况下，Azure 密钥保管库由于暂时性错误而无法响应或无法访问。

    - 如果检查确定请求未能返回 ACCESS DENIED：

       - 这意味着已采取有意、无意或恶意操作，使客户密钥不可用 (例如，在数据清除过程中，作为离开服务) 的一部分。

       - 在这种情况下，可用性密钥将仅用于系统操作，而不用于用户操作，用户请求失败，用户收到错误消息。

> [!IMPORTANT]
> Microsoft 365服务代码始终具有有效的登录令牌，用于推理客户数据以提供增值云服务。 因此，在删除可用性密钥之前，它可以用作由搜索索引创建或移动邮箱等Exchange Online和Skype for Business发起或内部操作的回退。 这适用于对 Azure 密钥保管库的暂时性 ERRORS 和 ACCESS DENIED 请求。

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint联机、OneDrive for Business和Teams文件的触发器

对于SharePoint联机、OneDrive for Business和Teams文件，可用性密钥永远不会在恢复功能之外使用，客户必须明确指示 Microsoft 在恢复方案中启动使用可用性密钥。

## <a name="audit-logs-and-the-availability-key"></a>审核日志和可用性密钥

Microsoft 365中的自动化系统在流经系统时处理所有数据，以提供云服务，例如防病毒、电子发现、数据丢失防护和数据索引编制。 Microsoft 365不会为此活动生成客户可见的日志。 此外，Microsoft 人员不会在正常系统操作中访问数据。

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>Exchange Online和Skype for Business可用性密钥日志记录

Exchange Online和Skype for Business访问可用性密钥以提供服务时，Microsoft 365发布可从安全与合规中心访问的客户可见日志。 每次服务使用可用性密钥时，都会生成可用性密钥操作的审核日志记录。 使用活动类型“回退到可用性密钥”的新记录类型称为“客户密钥服务加密”，管理员可以筛选 [统一审核日志](./search-the-audit-log-in-security-and-compliance.md) 搜索结果以查看可用性密钥记录。

日志记录包括日期、时间、活动、组织 ID 和数据加密策略 ID 等属性。 该记录作为统一审核日志的一部分提供，可从安全&合规中心审核日志搜索选项卡访问。

![审核可用性密钥事件的日志搜索](../media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

Exchange Online和Skype for Business可用性密钥记录将Office 365管理活动[常见架构](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)与添加的自定义参数一起使用：策略 ID、范围密钥版本 ID 和请求 ID。

![可用性密钥自定义参数](../media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>SharePoint联机、OneDrive for Business和Teams文件可用性密钥日志记录

可用性密钥日志记录尚不适用于这些服务。 对于SharePoint联机、OneDrive for Business和Teams文件，仅在你指示的情况下由 Microsoft 激活可用性密钥以进行恢复。 因此，你已知道用于这些服务的可用性密钥的每个事件。

## <a name="availability-key-in-the-customer-key-hierarchy"></a>客户密钥层次结构中的可用性密钥
  
Microsoft 365使用可用性密钥在为客户密钥服务加密建立的密钥层次结构中更低地包装密钥层。 服务之间存在不同的密钥层次结构。 每个适用服务的层次结构中的可用性密钥和其他密钥之间的密钥算法也有所不同。 不同服务使用的可用性密钥算法如下所示：

- Exchange Online和Skype for Business可用性密钥使用 AES-256。

- SharePoint联机、OneDrive for Business和Teams文件可用性密钥使用 RSA-2048。

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>用于加密Exchange Online和Skype for Business密钥的加密密码

![Exchange Online客户密钥的加密密码](../media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>用于加密 SharePoint Online 和 OneDrive for Business 密钥的加密密码

![SharePoint联机客户密钥的加密密码](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>相关文章

- [使用客户密钥执行服务加密](customer-key-overview.md)

- [设置客户密钥](customer-key-set-up.md)

- [管理客户密钥](customer-key-manage.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)
