---
title: 了解 Office 365 客户密钥的可用性密钥
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
description: 了解用于恢复丢失的 Office 365 客户密钥的可用性密钥。
ms.openlocfilehash: b363d3b90c6ea783bd051bea6c44a94689b87ac1
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804755"
---
# <a name="learn-about-the-availability-key-for-office-365-customer-key"></a>了解 Office 365 客户密钥的可用性密钥

可用性密钥是在创建数据加密策略时自动生成和设置的根密钥。 Office 365 存储和保护可用性密钥。 可用性密钥的功能类似于为使用客户密钥的服务加密提供的两个根键。 可用性密钥会将键层次结构中的键向下封装一层。 与在 Azure Key Vault 中提供和管理的密钥不同，您不能直接访问可用性密钥。 Office 365 自动化服务使用 PowerShell cmdlet 管理可用性密钥。 这些 cmdlet 会启动自动化操作，这些操作永远不会涉及直接访问可用性密钥。

可用性密钥的主要用途是通过所管理的根密钥的意外丢失来提供恢复功能。 丢失可能是 mismanagement 或恶意操作的结果。 如果你丢失了对根密钥的控制，请联系 Microsoft 支持部门，Microsoft 将为你提供使用可用性密钥进行恢复的过程。 你将使用可用性密钥迁移到新的数据加密策略，并使用你预配的新根密钥。

由于以下三个原因，可用性密钥的存储和控制特意不同于 Azure 密钥存储库密钥：

- 如果对 Azure Key Vault 密钥的控制丢失，则可用性密钥提供恢复 "中断玻璃" 功能。
- 分离逻辑控件和安全存储位置可提供深入防护，防止因单个攻击或故障点而导致丢失所有密钥和数据。
- 如果 Office 365 服务由于暂时性错误而无法访问 Azure Key Vault 中托管的密钥，则可用性密钥提供了高可用性功能。 此规则仅适用于 Exchange Online 和 Skype for Business 服务加密。 SharePoint Online、OneDrive for Business 和团队文件永远不使用可用性密钥，除非您明确指示 Microsoft 启动恢复过程。

共享责任若要使用各种保护措施和密钥管理流程来保护数据，最终降低了所有密钥（因而您的数据）将永久丢失或损坏的风险。 当你离开服务时，Microsoft 会为你提供禁用或销毁可用性密钥的唯一权限。 根据设计，Microsoft 没有任何人可以访问可用性密钥：它只能通过 Office 365 服务代码访问。

有关我们如何保护密钥的详细信息，请参阅[Microsoft 信任中心](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data)。
  
## <a name="availability-key-uses"></a>可用性密钥使用

可用性密钥为应用场景提供了恢复功能，在这种情况下，在外部 malefactor 或恶意的内部攻击的内部盗取控制密钥存储库，或当无意 mismanagement 导致丢失根密钥时。 此恢复功能适用于所有与客户密钥兼容的 Office 365 服务。 各个服务使用可用性密钥的方式不同。 Office 365 仅使用下文所述的方法中的可用性密钥。

### <a name="exchange-online-and-skype-for-business-uses"></a>Exchange Online 和 Skype for Business 使用

除了恢复功能之外，Exchange Online 和 Skype for business 还可以使用可用性密钥确保暂时性的数据可用性，或与访问根键的服务相关的间歇操作问题。 当服务由于暂时性错误而无法到达 Azure Key Vault 中的任何客户密钥时，该服务将自动使用可用性密钥。 服务永远不会直接转到可用性密钥。

Exchange Online 和 Skype for business 中的自动系统可能会在暂时性错误期间使用可用性密钥，以支持自动化后端服务，如防病毒、电子发现、数据丢失防护、邮箱移动和数据索引。

### <a name="sharepointonlineonedriveforbusinessandteamsfiles-uses"></a>SharePoint Online、OneDrive for Business 和团队文件使用

对于 SharePoint Online、OneDrive for Business 和团队文件，可用性密钥从不在恢复功能的外部使用，客户必须明确指示 Microsoft 在恢复方案中启动使用可用性密钥。 自动化服务操作完全依赖于 Azure Key vault 中的客户密钥。 有关关键层次结构如何适用于这些服务的详细信息，请参阅[SharePoint Online、OneDrive For business 和团队文件如何使用可用性密钥](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key)。

## <a name="availability-key-security"></a>可用性密钥安全性

Microsoft 通过实例化可用性密钥并采取广泛的措施来保护数据保护，从而分担数据保护的责任。 Microsoft 不会向客户公开对可用性密钥的直接控制。 例如，您只能在 Azure Key Vault 中滚动（旋转）您拥有的密钥。 有关详细信息，请参阅[滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)。

### <a name="availability-key-secret-stores"></a>可用性密钥密钥存储

Microsoft 保护受访问控制的内部密钥存储中的可用性密钥，这与面向客户的 Azure 密钥存储库类似。 我们实现了访问控制，以防止 Microsoft 管理员直接访问中包含的密码。 秘密存储操作，包括密钥轮换、删除和检索通过永不涉及直接访问可用性密钥的自动化命令进行。 调整这些命令的访问权限仅限于特定的工程师，并需要通过内部工具密码箱进行权限提升。 权限提升要求在授予前的经理批准和理由。 密码箱可确保在时间到期或工程师注销时，访问时间绑定到自动访问撤销。

**Exchange Online 和 Skype for** business 可用性密钥存储在 Active Directory 机密存储区中。 Exchange Online Active Directory 由路由包含对象、标识和数据的流量和容量林的管理林组成。 容量林由帐户林和资源林组成。 帐户林具有彼此同步的多个容量域控制器。 可用性密钥安全存储在这些容量的域控制器中。 此安全存储位置是独立的，并与 SharePoint Online、OneDrive for Business 和团队文件机密存储区隔离。

**SharePoint Online、OneDrive For business 和团队文件**可用性密钥存储在由服务团队管理的内部机密存储区中。 此安全的机密存储服务具有前端服务器和应用程序终结点，并将 SQL 数据库作为后端。 可用性密钥存储在 SQL 数据库中，并通过使用 AES-256 和 HMAC 组合来加密 rest 上的可用密钥的机密存储加密密钥进行包装（加密）。 机密存储加密密钥存储在同一 SQL 数据库的逻辑隔离组件中，并使用 Microsoft 证书颁发机构（CA）管理的证书中包含的 RSA-2048 密钥进一步加密。 这些证书存储在对数据库执行操作的机密存储前端服务器中。

### <a name="defense-in-depth"></a>深层纵深防御

Microsoft 采用纵深防御策略，以防止恶意参与者影响存储在 Microsoft 云中的客户数据的机密性、完整性或可用性。 实施特定的预防和侦探控制，以保护可用性密钥，作为总体安全策略的一部分。

Office 365 的构建旨在防止对可用性密钥的滥用。 应用程序层是可用于加密和解密数据的键（包括可用性密钥）的唯一方法。 只有 Office 365 服务代码能够解释和遍历加密和解密活动的关键层次结构。 如果恶意 Microsoft 管理员要绕过控件以从机密存储中提取可用性密钥，则密钥将无法访问客户数据。 客户密钥、可用性密钥、其他分层密钥和客户数据的存储位置之间存在逻辑隔离，这样可降低事件中的一个或多个位置受到危害的数据暴露风险。

实现访问控制可防止对内部系统进行未经授权的访问，包括可用性密钥机密存储。 Microsoft 工程师不能直接访问可用性密钥机密存储。 有关访问控制的更多详细信息，请参阅[Office 365 中的管理访问控制](https://docs.microsoft.com/Office365/securitycompliance/office-365-administrative-access-controls-overview)。

技术控制可防止 Microsoft 人员登录到高度特权的服务帐户，攻击者可能会使用这些服务帐户来模拟 Office 365 服务。 例如，这些控件将阻止交互式登录。

安全日志记录和监视控件是实施的另一种纵深防御保护，可降低 Microsoft 服务和数据的风险。 Microsoft 服务团队部署了可生成警报和审核日志的活动监视解决方案。 所有服务团队将其日志上传到一个中央存储库，其中的日志进行了聚合和处理。 内部工具会自动检查记录，以确认服务是否以最佳、可恢复且安全的状态运行。 标记出不正常的活动以供进一步审阅。

任何指示潜在的 Microsoft 安全策略冲突的日志事件将立即进入 Microsoft 安全团队的关注。 Office 365 安全性已配置警报，以检测对可用性密钥密钥存储的尝试访问权限。 如果 Microsoft 人员尝试以交互方式登录到服务帐户（受访问控制禁止和保护），也会生成警报。 Office 365 安全性还检测并通知 Office 365 服务与常规基准操作的偏差。 尝试滥用 Office 365 服务的 Malefactors 将触发警报，从而导致罪犯从 Microsoft 云环境中逐出。

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>使用可用性密钥从密钥丢失中恢复

如果您失去了对客户密钥的控制，则可用性密钥使您能够恢复和重新加密数据。

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Exchange Online 和 Skype for business 的恢复过程

如果您失去了对客户密钥的控制，则在恢复时，可用性密钥仍将向您提供对数据的访问权限。 若要使用新的客户密钥对数据进行加密，请在 Azure Key Vault 中创建新密钥，创建新的 DEP，将新的 DEP 与新的客户密钥关联，然后指示 DEP 对当前使用以前的 DEP 加密的邮箱进行加密，以使这些邮箱的密钥丢失或 compromised. 执行时，可用性密钥将对邮箱进行解密，然后使用新策略对邮箱进行加密。

此过程最长可能需要72个小时，这是更改 DEP 时的标准持续时间。
  
### <a name="recovery-procedure-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>SharePoint Online、OneDrive for Business 和团队文件的恢复过程

对于 SharePoint Online、OneDrive for Business 和团队文件，可用性密钥从不在恢复功能的外部使用。 您必须明确指示 Microsoft 在恢复方案中启动使用可用性密钥。 若要启动恢复过程，请与 Microsoft 联系以激活可用性密钥。 一旦激活，可用性密钥将自动用于解密你的数据，使你能够使用与新的客户密钥关联的新创建的 DEP 对数据进行加密。  

此操作与组织中的网站数成比例。 调用 Microsoft 使用可用性密钥后，应在大约4小时内完全在线。

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>Exchange Online 和 Skype for business 如何使用可用性密钥

当您使用客户密钥创建 DEP 时，Office 365 将生成与该 DEP 相关联的数据加密策略密钥（DEP 密钥）。 该服务将 DEP 密钥加密三次：每个客户密钥一次，并使用可用性密钥。 仅存储加密版本的 DEP 密钥，并且只能使用客户密钥或可用性密钥解密 DEP 密钥。 然后，使用 DEP 密钥来加密邮箱密钥，然后使用它对各个邮箱进行加密。 
  
在客户使用该服务时，Office 365 将执行以下过程来解密和提供数据：
  
1. 使用客户密钥对 DEP 密钥进行解密。

2. 使用解密的 DEP 密钥对邮箱密钥进行解密。

3. 使用解密邮箱密钥对邮箱本身进行解密，从而允许您访问邮箱中的数据。

Office 365 通过向 Azure Key Vault 发出两个解密请求来解密 DEP 密钥，其中包含轻微偏移量。 第一个要完成的提供结果，取消了另一个请求。

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>SharePoint Online、OneDrive for Business 和团队文件如何使用可用性密钥

SharePoint Online 和 OneDrive for business 体系结构以及客户密钥和可用性密钥实现不同于 Exchange Online 和 Skype for business。
  
当组织移动到客户管理的密钥时，Office 365 将创建特定于租户的中间密钥（TIK）。 Office 365 将 TIK 加密两次，每个客户密钥一次，并存储 TIK 的两个加密版本。 仅存储 TIK 的加密版本，并且 TIK 只能使用客户密钥进行解密。 然后，TIK 用于对网站密钥进行加密，然后使用这些密钥对 blob 密钥（也称为 "文件块密钥"）进行加密。 根据文件大小，服务可能会将文件拆分为多个文件块，每个文件块都有一个唯一键。 Blob （文件区块）本身是使用 blob 密钥加密的，并存储在 Microsoft Azure Blob 存储服务中。
  
在客户使用该服务时，Office 365 将执行以下过程来解密和提供客户文件：

1. 使用客户密钥对 TIK 进行解密。

2. 使用解密的 TIK 解密网站密钥。

3. 使用解密的网站密钥对 blob 密钥进行解密。

4. 使用解密的 blob 密钥对 blob 进行解密。

Office 365 通过在具有轻微偏移量的 Azure Key Vault 发出两个解密请求来解密 TIK。 第一个要完成的提供结果，取消了另一个请求。
  
如果你失去了对客户密钥的访问权限，Office 365 还会使用可用性密钥加密 TIK，并将其与使用每个客户密钥加密的 TIKs 存储在一起。 使用 availability 密钥加密的 TIK 仅当客户在失去对其密钥的访问权限（恶意或意外）时，才将 Microsoft 用于登记恢复路径。
  
出于可用性和扩展原因，解密的 TIKs 缓存在一个时间有限的内存缓存中。 在 TIK 缓存设置为过期之前的两个小时，Office 365 将尝试对每个 TIK 进行解密。 对 TIKs 进行解密会延长缓存的生存期。 如果 TIK 解密在很长一段时间后失败，Office 365 将生成一个警报，以在缓存过期之前通知工程。 仅当客户呼叫 Microsoft 时，Office 365 才会启动恢复操作，这涉及使用存储在 Microsoft 机密存储中的可用性密钥对 TIK 进行解密，并使用解密的 TIK 再次载入租户，并使用一组新的客户提供的 Azure Key Vault 密钥。
  
到目前为止，客户密钥包含在 Azure blob 存储中存储的 SharePoint Online 文件数据的加密和解密链中，但不包含在 SQL 数据库中存储的 SharePoint online 列表项或元数据中。 除了客户启动的情况之外，Office 365 不使用 Exchange Online、Skype for Business、SharePoint Online、OneDrive for business 和团队文件之外的其他项。 对客户数据的人对客户数据的访问受客户密码箱保护。

## <a name="availability-key-triggers"></a>可用性密钥触发器

Office 365 仅在特定情况下触发可用性密钥。 这些情况因服务而异。

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Exchange Online 和 Skype for business 的触发器
  
1. Office 365 读取邮箱分配到的 DEP，以便确定两个客户密钥在 Azure Key Vault 中的位置。

2. Office 365 从 DEP 中随机选择两个客户密钥中的一个，并向 Azure Key Vault 发送一个请求，以使用客户密钥解包 DEP 密钥。

3. 如果使用客户密钥对对 DEP 密钥进行解包的请求失败，Office 365 将向 Azure Key Vault 发送第二个请求，这次指示它使用备用（第二）客户密钥。

4. 如果使用客户密钥对 DEP 密钥进行解包的第二个请求失败，则 Office 365 会检查这两个请求的结果。

    - 如果检查确定返回系统错误的请求失败：

       - Office 365 将触发可用性密钥以解密 DEP 密钥。

       - 然后，Office 365 使用 DEP 密钥来解密邮箱密钥，并完成用户请求。 

       - 在这种情况下，由于暂时性错误，Azure Key Vault 无法响应或无法访问。

    - 如果检查确定访问被拒绝的请求失败：

       - 这意味着已采取了故意、无意或恶意操作来呈现客户密钥不可用（例如，在离开服务的过程中，在数据清除过程中）。

       - 在这种情况下，将不会使用可用性密钥，用户请求将失败，并且用户会收到一条错误消息。

>[!IMPORTANT]
>Office 365 服务代码始终具有有效的登录令牌，用于推理客户数据以提供增值云服务。 因此，在删除可用性密钥之前，可将其用作 Exchange Online 和 Skype for business （如搜索索引创建或移动邮箱）启动的操作的回退。 这适用于暂时性错误和访问 Azure Key Vault 拒绝的请求。

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business 和团队文件的触发器

对于 SharePoint Online、OneDrive for Business 和团队文件，可用性密钥从不在恢复功能的外部使用，客户必须明确指示 Microsoft 在恢复方案中启动使用可用性密钥。

## <a name="audit-logs-and-the-availability-key"></a>审核日志和可用性密钥

Office 365 中的自动化系统处理所有数据在系统中流动，以提供云服务，例如，反病毒、电子发现、数据丢失防护和数据索引。 Office 365 不会为此活动生成客户可见的日志。 此外，Microsoft 人员不会作为这些正常系统操作的一部分访问你的数据。

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>Exchange Online 和 Skype for business 可用性密钥日志记录

Exchange Online 和 Skype for business 在暂时性错误期间自动使用可用性密钥。 当此回退发生时，Office 365 将发布从安全与合规中心可访问的客户可见日志。 每次这些服务切换为使用可用性密钥时，都会生成可用性密钥操作的审核日志记录。 名为 "Customer Key Service Encryption" 的新记录类型，活动类型为 "回退到可用性密钥"，允许管理员筛选[统一审核日志](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)搜索结果以查看可用性密钥记录。 仅当使用 Customer 密钥访问数据而不是 Microsoft 服务管理密钥时，才会生成可用性密钥记录。

日志记录包括 "日期"、"时间"、"活动"、"组织 ID" 和 "数据加密策略 ID" 等属性。 该记录可作为 Office 365 统一的审核日志的一部分，并可从 Office 365 安全性和合规性中心审核日志搜索选项卡进行访问。

![审核日志搜索可用性密钥事件](media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

Exchange Online 和 Skype for business 可用性密钥记录使用 Office 365 管理活动[常见架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)和添加的自定义参数： Policy Id、作用域密钥版本 Id 和请求 Id。

![可用性密钥自定义参数](media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>SharePoint Online、OneDrive for Business 和团队文件可用性密钥日志记录

可用性密钥日志记录尚不可用于这些服务。 对于 SharePoint Online、OneDrive for Business 和团队文件，可用性密钥仅在由你指示的情况下由 Microsoft 激活，以供恢复之用。 因此，您已经知道可用性密钥可用于这些服务的每个事件。

## <a name="availability-key-in-the-customer-key-hierarchy"></a>客户密钥层次结构中的可用性密钥
  
Office 365 使用可用性密钥包装在为客户密钥服务加密建立的密钥层次结构中较低的密钥层。 服务之间存在不同的密钥层次结构。 每个适用服务的层次结构中的可用性密钥和其他密钥之间的密钥算法也不同。 不同服务使用的可用性密钥算法如下所示：

- Exchange Online 和 Skype for business 可用性密钥使用 AES-256。

- SharePoint Online、OneDrive for Business 和团队文件可用性密钥使用的是 RSA-2048。

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>用于加密 Exchange Online 和 Skype for business 的密钥的加密密码

![Exchange Online 客户密钥的加密密码](media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>用于对 SharePoint Online 和 OneDrive for Business 的密钥进行加密的加密密码

![SharePoint Online 客户密钥的加密密码](media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>相关文章

- [使用 Office 365 的客户密钥进行服务加密](customer-key-overview.md)

- [设置适用于 Office 的客户密钥365](customer-key-set-up.md)

- [管理 Office 365 的客户密钥](customer-key-manage.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)
