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
ms.openlocfilehash: 72e66e9deb74400944c6ea65ea3ac167a703da26
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170783"
---
# <a name="learn-about-the-availability-key-for-customer-key"></a>了解客户密钥的可用性密钥

可用性密钥是在您创建数据加密策略时自动生成和预配的根密钥。 Microsoft 365存储和保护可用性密钥。 可用性密钥在功能上与使用客户密钥进行服务加密的两个根密钥类似。 可用性密钥将密钥包装在密钥层次结构中下一层。 与你在 Azure 密钥保管库中提供和管理的密钥不同，你无法直接访问可用性密钥。 Microsoft 365自动服务以编程方式管理可用性密钥。 这些服务启动自动化操作，这些操作从不涉及直接访问可用性密钥。

可用性密钥的主要目的是提供恢复功能，以从您管理的根密钥意外丢失中恢复。 丢失可能是由于管理不当或恶意操作导致。 如果你失去对根密钥的控制，请联系 Microsoft 支持部门，Microsoft 将帮助你使用可用性密钥完成恢复过程。 你将使用可用性密钥迁移到新的数据加密策略，并设置新的根密钥。

存储控制可用性密钥有意与 Azure 密钥保管库密钥不同，原因有三：

- 如果失去对 Azure 密钥保管库密钥的控制，可用性密钥将提供恢复（即"中断式"功能）。
- 逻辑控件和安全存储位置的分离可提供深度防御，并防范从单个攻击或故障点中丢失所有密钥和数据。
- 如果服务由于暂时性错误Microsoft 365无法访问 Azure Key Vault 中托管的密钥，可用性密钥将提供高可用性功能。 此规则仅适用于Exchange Online Skype for Business加密。 SharePoint联机OneDrive for Business和Teams文件永远不会使用可用性密钥，除非你明确指示 Microsoft 启动恢复过程。

共享保护数据的责任，使用各种保护和过程进行密钥管理，最终可降低所有密钥 (因此你的数据) 丢失或销毁的风险。 当你离开服务时，Microsoft 会为您提供对禁用或销毁可用性密钥的唯一授权。 按照设计，Microsoft 没有人可以访问可用性密钥：它只能通过 Microsoft 365 服务代码访问。

请参阅 [Microsoft 信任中心](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) ，详细了解如何保护密钥。
  
## <a name="availability-key-uses"></a>可用性密钥使用

可用性密钥为以下情形提供恢复功能：外部恶意恶意内部人员窃取密钥保管库的控制权，或意外管理不当导致根密钥丢失的情况。 此恢复功能适用于所有Microsoft 365客户密钥的服务。 各个服务使用可用性密钥的方式不同。 Microsoft 365方法仅使用可用性密钥。

### <a name="exchange-online-and-skype-for-business-uses"></a>Exchange Online和Skype for Business使用

除了恢复功能之外，Exchange Online和 Skype for Business 还使用可用性密钥来确保与访问根密钥的服务相关的暂时性或间歇性操作问题期间的数据可用性。 当服务由于暂时性错误而无法访问 Azure 密钥保管库中的任一客户密钥时，该服务将自动使用可用性密钥。 服务 NEVER 直接转到可用性密钥。

Exchange Online 和 Skype for Business 中的自动系统可能在暂时性错误期间使用可用性密钥来支持自动后端服务，如防病毒、电子数据发现、数据丢失防护、邮箱移动和数据索引。

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-uses"></a>SharePoint联机、OneDrive for Business和Teams文件使用

对于 SharePoint Online、OneDrive for Business 和 Teams 文件，从不在恢复功能之外使用可用性密钥，客户必须明确指示 Microsoft 在恢复方案期间启动可用性密钥的使用。 自动服务操作仅依赖于 Azure 密钥保管库中的客户密钥。 有关密钥层次结构如何用于这些服务的深入信息，请参阅[SharePoint Online、OneDrive for Business](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key)和 Teams 文件如何使用可用性密钥。

## <a name="availability-key-security"></a>可用性密钥安全性

Microsoft 通过实例化可用性密钥并采取广泛的措施来保护它，来承担数据保护的责任。 Microsoft 不会将可用性密钥的直接控制公开给客户。 例如，你只能滚动 (旋转) 你在 Azure Key Vault 中拥有密钥。 有关详细信息，请参阅滚动 [或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)。

### <a name="availability-key-secret-stores"></a>可用性密钥密钥存储

Microsoft 在访问控制的内部密码存储（如面向客户的 Azure 密钥保管库）中保护可用性密钥。 我们实施访问控制以防止 Microsoft 管理员直接访问其中包含的机密。 密钥存储操作（包括密钥轮换和删除）通过自动命令执行，这些命令从不涉及直接访问可用性密钥。 密码存储管理操作仅限于特定工程师，并且需要通过内部工具 Lockbox 进行特权提升。 特权提升需要在授予之前获得经理批准和理由。 密码箱确保在过期或工程师注销时访问权限与自动访问权限吊销绑定在一起。

**Exchange Online和Skype for Business** 可用性密钥存储在 active Directory Exchange Online存储中。 可用性密钥安全存储在 Active Directory 域控制器内的租户特定容器内。 此安全存储位置独立于 SharePoint Online、OneDrive for Business 和 Teams 文件密码存储。

**SharePoint Online、OneDrive for Business** 和 Teams 文件可用性密钥存储在由服务团队管理的内部密码存储中。 此安全密钥存储服务具有具有应用程序终结点的前端服务器，SQL 数据库服务器作为后端。 可用性密钥存储在 SQL 数据库中， (加密的) 由密钥存储加密密钥包装，这些加密密钥使用 AES-256 和 HMAC 的组合对静态可用性密钥进行加密。 密钥存储加密密钥存储在同一 SQL 数据库 的逻辑隔离组件中，并且使用包含在由 Microsoft 证书颁发机构 (CA) 管理的证书中的 RSA-2048 密钥进一步加密。 这些证书存储在对数据库执行操作机密存储前端服务器中。

### <a name="defense-in-depth"></a>深度防御

Microsoft 采用深度防御策略来防止恶意参与者影响存储在 Microsoft 云中的客户数据的机密性、完整性或可用性。 实施特定的预防性和检测性控制措施来保护作为总体安全策略一部分的机密存储和可用性密钥。

Microsoft 365是为了防止误用可用性密钥。 应用程序层是可以使用密钥（包括可用性密钥）加密和解密数据的唯一方法。 只有Microsoft 365代码能够解释和遍历密钥层次结构进行加密和解密活动。 客户密钥、可用性密钥、其他分层密钥和客户数据的存储位置之间存在逻辑隔离。 此隔离在一个或多个位置受到威胁时降低了数据泄露的风险。 层次结构中的每个层都内置了 24x7 入侵检测功能，以保护存储的数据和机密。

实施访问控制是为了防止对内部系统（包括可用性密钥密钥存储）进行未经授权的访问。 Microsoft 工程师不能直接访问可用性密钥密钥存储。 有关访问控制的其他详细信息，请查看管理[访问控制Microsoft 365。](/compliance/assurance/assurance-administrative-access-controls-overview)

技术控制可防止 Microsoft 人员登录到高度特权的服务帐户，否则攻击者可能会使用这些帐户来模拟Microsoft 服务。 例如，这些控件阻止交互式登录。

安全日志记录和监控控件是另一项深度防御措施，用于降低Microsoft 服务和数据的风险。 Microsoft 服务团队已部署可生成警报和审核日志的活动监视解决方案。 所有服务团队将其日志上载到聚合和处理日志的中央存储库。 内部工具会自动检查记录，以确认服务是否以最佳、可恢复和安全状态运行。 异常活动将被标记为进一步审查。

任何指示潜在违反 Microsoft 安全策略的日志事件会立即引起 Microsoft 安全团队的注意。 Microsoft 365配置警报以检测尝试访问可用性密钥密钥存储。 如果 Microsoft 人员尝试交互式登录服务帐户（访问控制禁止并保护此帐户）也会生成警报。 Microsoft 365安全还会检测服务与正常基线Microsoft 365偏差并发出警报。 试图滥用服务的Microsoft 365会触发警报，从而导致被误用者从 Microsoft 云环境受到冒犯。

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>使用可用性密钥从密钥丢失中恢复

如果你失去对客户密钥的控制，可用性密钥将让你能够恢复和重新加密你的数据。

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Exchange Online 和 Skype for Business

如果失去对客户密钥的控制，可用性密钥将让你恢复数据，并恢复Microsoft 365资源。 恢复时，可用性密钥将继续保护数据。在高级别上，若要完全从密钥丢失中恢复，你需要创建新的 DEP，将影响的资源移动到新策略。

若要使用新的客户密钥加密数据，在 Azure 密钥保管库中创建新密钥，使用新的客户密钥创建新的 DEP，然后将新 DEP 分配给当前使用以前的 DEP 加密的邮箱，这些邮箱的密钥丢失或受到威胁。

此重新加密过程最多可能需要 72 小时。 这是更改 DEP 时的标准持续时间。
  
### <a name="recovery-procedure-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business 和 Teams 文件的恢复过程

对于 SharePoint Online、OneDrive for Business 和 Teams 文件，从不在恢复功能之外使用可用性密钥。 您必须明确指示 Microsoft 在恢复方案期间启动可用性密钥的使用。 若要启动恢复过程，请与 Microsoft 联系以激活可用性密钥。 激活后，可用性密钥将自动用于解密数据，从而允许您使用与新客户密钥关联的新创建的 DEP 加密数据。  

此操作与组织中网站的数量成比例。 调用 Microsoft 以使用可用性密钥后，你应在大约四小时内完全联机。

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>如何Exchange Online Skype for Business使用可用性密钥

使用客户密钥创建 DEP 时，Microsoft 365将生成一个数据加密策略密钥 (DEP 密钥) DEP 密钥。 该服务对 DEP 密钥进行三次加密：一次与每个客户密钥一起加密，一次使用可用性密钥加密。 仅存储 DEP 密钥的加密版本，并且只能使用客户密钥或可用性密钥解密 DEP 密钥。 然后，DEP 密钥用于加密邮箱密钥，从而加密各个邮箱。
  
Microsoft 365按照此过程在客户使用该服务时解密和提供数据：
  
1. 使用客户密钥解密 DEP 密钥。

2. 使用解密的 DEP 密钥解密邮箱密钥。

3. 使用解密的邮箱密钥对邮箱本身进行解密，从而允许您访问邮箱内的数据。

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>SharePoint Online、OneDrive for Business 和 Teams 文件如何使用可用性密钥

客户SharePoint和OneDrive for Business密钥和可用性密钥的 SharePoint Online 和 OneDrive for Business 体系结构和实现与 Exchange Online 和 Skype for Business。
  
当组织移动到客户管理的密钥时，Microsoft 365 TIK 策略创建特定于 (中间) 。 Microsoft 365对 TIK 进行两次加密，一次加密每个客户密钥，并存储两个加密版本的 TIK。 仅存储 TIK 的加密版本，并且 TIK 只能使用客户密钥解密。 然后，TIK 用于加密站点密钥，然后使用站点密钥加密 blob 密钥 (也称为文件区块密钥) 。 根据文件大小，该服务可能会将一个文件拆分为多个文件区块，每个文件块中都有一个唯一的密钥。 这些 blob (文件块) blob 密钥进行加密，并存储在 Microsoft Azure Blob 存储服务中。
  
Microsoft 365客户使用该服务时，将按照此过程解密并提供客户文件：

1. 使用客户密钥解密 TIK。

2. 使用解密的 TIK 解密站点密钥。

3. 使用解密的站点密钥解密 blob 密钥。

4. 使用解密的 blob 密钥解密 blob。

Microsoft 365向 Azure 密钥保管库发出两个稍有偏移的解密请求来解密 TIK。 第一个完成的请求会提供结果，同时取消另一个请求。
  
如果你失去对客户密钥的访问权限，Microsoft 365使用可用性密钥加密 TIK，并随使用每个客户密钥加密的 TIK 一起存储它。 使用可用性密钥加密的 TIK 仅在客户恶意或无意丢失对密钥的访问时，调用 Microsoft 加入恢复路径时使用。
  
出于可用性和扩展原因，解密的 TIK 缓存在有时间限制的内存缓存中。 在 TIK 缓存设置为过期的两个小时之前，Microsoft 365尝试解密每个 TIK。 解密 TIK 可延长缓存的生存期。 如果 TIK 解密失败很长时间，Microsoft 365在缓存过期之前生成通知工程的警报。 只有当客户呼叫 Microsoft 时Microsoft 365启动恢复操作，该操作涉及使用 Microsoft 密码存储中存储的可用性密钥解密 TIK，然后使用解密的 TIK 和一组新的客户提供的 Azure 密钥保管库密钥再次载入租户。
  
截至目前，客户密钥已涉及 Azure blob 存储中存储的 SharePoint Online 文件数据的加密和解密链，但不包括 SharePoint Online 列表项或存储在 SQL 数据库 中的元数据。 Microsoft 365不将可用性密钥用于 Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和 Teams 文件，上述情况不是由客户启动的。 对客户数据的人工访问受客户密码箱保护。

## <a name="availability-key-triggers"></a>可用性键触发器

Microsoft 365仅在特定情况下触发可用性密钥。 这些情况因服务不同而不同。

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>事件和Exchange Online Skype for Business
  
1. Microsoft 365读取邮箱分配到的 DEP，以确定 Azure Key Vault 中两个客户密钥的位置。

2. Microsoft 365 DEP 随机选择两个客户密钥中的一个，然后向 Azure Key Vault 发送一个请求，以使用客户密钥解包 DEP 密钥。

3. 如果使用客户密钥解包 DEP 密钥的请求失败，Microsoft 365 会向 Azure Key Vault 发送第二个请求，这次指示它使用备用 (秒) 客户密钥。

4. 如果使用客户密钥解包 DEP 密钥的第二个请求失败，Microsoft 365检查这两个请求的结果。

    - 如果检查确定请求失败，则返回系统错误：

       - Microsoft 365会触发可用性密钥以解密 DEP 密钥。

       - Microsoft 365使用 DEP 密钥解密邮箱密钥并完成用户请求。 

       - 在这种情况下，Azure Key Vault 因暂时性错误无法响应或无法访问。

    - 如果检查确定请求未能返回拒绝访问：

       - 这意味着已采取有意、无意或恶意操作，使客户密钥不可用 (例如，在将数据清除过程中作为离开服务服务的一) 。

       - 在这种情况下，可用性密钥将仅用于系统操作，不用于用户操作，用户请求将失败，并且用户会收到错误消息。

> [!IMPORTANT]
> Microsoft 365代码始终具有有效的登录令牌，用于通过客户数据进行推断以提供增值云服务。 因此，在删除可用性密钥之前，它可用作由 Exchange Online 和 Skype for Business 启动的操作（例如搜索索引创建或移动邮箱）的回退。 这适用于对 Azure 密钥保管库的暂时性错误和访问被拒绝请求。

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business 和 Teams 文件的触发器

对于 SharePoint Online、OneDrive for Business 和 Teams 文件，从不在恢复功能之外使用可用性密钥，客户必须明确指示 Microsoft 在恢复方案期间启动可用性密钥的使用。

## <a name="audit-logs-and-the-availability-key"></a>审核日志和可用性密钥

自动化中的Microsoft 365在数据流经系统时处理所有数据，以提供云服务，例如防病毒、电子数据发现、数据丢失防护和数据索引。 Microsoft 365不为此活动生成客户可见的日志。 此外，Microsoft 人员不会在这些正常系统操作中访问你的数据。

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>Exchange Online和Skype for Business可用性密钥日志记录

当Exchange Online和Skype for Business访问可用性密钥来提供服务时，Microsoft 365安全与合规中心发布客户可见的日志。 每次审核日志使用可用性密钥时，将生成可用性键操作的数据记录。 使用活动类型为"回退到可用性密钥"的名为"客户密钥服务加密"的新记录类型，管理员可以筛选统一 [审核日志](./search-the-audit-log-in-security-and-compliance.md) 搜索结果以查看可用性密钥记录。

日志记录包括诸如日期、时间、活动、组织 ID 和数据加密策略 ID 等属性。 该记录作为统一审核日志的一部分提供，可从安全与合规&中心审核日志搜索"选项卡访问。

![审核日志搜索可用性密钥事件](../media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

Exchange Online和 Skype for Business 可用性密钥记录使用 Office 365 管理活动通用架构，并添加[](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)自定义参数：策略 ID、范围密钥版本 ID 和请求 ID。

![可用性密钥自定义参数](../media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>SharePoint联机、OneDrive for Business和Teams文件可用性密钥日志记录

可用性密钥日志记录尚不可用于这些服务。 For SharePoint Online， OneDrive for Business， and Teams files， the availability key is only activated by Microsoft， when instructed for you， for recovery purposes. 因此，你已知道可用性密钥用于这些服务的每一个事件。

## <a name="availability-key-in-the-customer-key-hierarchy"></a>客户密钥层次结构中的可用性密钥
  
Microsoft 365使用可用性密钥包装为客户密钥服务加密建立的密钥层次结构中较低级别的密钥。 服务之间存在不同的密钥层次结构。 密钥算法在每个适用服务的层次结构中的可用性密钥和其他密钥之间也有所不同。 不同服务使用的可用性密钥算法如下所示：

- Exchange Online Skype for Business使用 AES-256。

- SharePoint Online、OneDrive for Business 和 Teams 文件可用性密钥使用 RSA-2048。

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>加密密码，用于加密Exchange Online和Skype for Business

![客户密钥Exchange Online密码](../media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>加密密码用于加密 SharePoint Online 和 OneDrive for Business

![SharePoint Online 客户密钥的加密密码](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>相关文章

- [使用客户密钥执行服务加密](customer-key-overview.md)

- [设置客户密钥](customer-key-set-up.md)

- [管理客户密钥](customer-key-manage.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)