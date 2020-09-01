---
title: To identity and 超越-一个架构师的视点
description: 说明。
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 7c83d3f202851008e93c3f3e9d0c7bc89c49bf20
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308363"
---
# <a name="to-identity-and-beyond--one-architects-viewpoint"></a>To identity and 超越-一个架构师的视点

在本文中， [Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/)，Principal Technical 建筑师 for microsoft，讨论了采用 Microsoft 365 和其他 Microsoft 云服务的企业组织的热门设计策略。

## <a name="about-the-author"></a>作者简介

![Alex Shteynberg 照片](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

我是位于纽约 [Microsoft 技术中心](https://www.microsoft.com/mtc?rtc=1)的主要技术架构师。 我主要处理大型客户和复杂要求。 我的视点和观点基于这些交互，可能不适用于每种情况。 但是，在我的经验中，如果我们能够帮助客户解决最复杂的难题，我们可以帮助所有客户。 

我通常每年与100个以上的客户合作。 虽然每个组织都有独特的特征，但看趋势和共同之处是很有意义的。 例如，一项趋势是针对许多客户的跨行业兴趣。 毕竟，银行分支也可以是咖啡店和社区中心。 

在我的角色中，我将重点放在帮助客户获得最佳技术解决方案，以解决其独特的业务目标集。 正式，我将重点放在身份、安全性、隐私和合规性方面。 我喜欢这一事实，这就是我们所要做的一切。 它让我有机会参与大多数项目。 这将使我非常忙碌且享受此角色。 

我居住在纽约城市 (最好的！ ) 并真正享受其文化、食物和人员 (不) 流量的多样性。 我喜欢在我和希望在我的生命周期中看到世界范围内的大多数世界时进行旅行。 我目前正在研究到非洲的旅行，了解 wildlife。

## <a name="guiding-principles"></a>指导原则 

- **简单的操作通常更好** ，可以 (几乎) 任何技术。 这并不意味着您应该这样做。 尤其是在安全空间中，许多客户 overengineer 解决方案。 我喜欢来自 Google 的条带会议的 [此视频](https://www.youtube.com/watch?v=SOQgABDSYZE) ，这一点。
- **人员、流程、技术** — [为人们提供设计](https://en.wikipedia.org/wiki/Human-centered_design) ，以增强过程，而不是技术优先。 没有 "完美" 解决方案。 我们需要权衡不同的风险因素，而决策将因每个业务而异。 太多客户设计了其用户稍后避免的方法。
- **重点关注 "为什么第一和 ' 为什么** ？" 是令人讨厌的7年老孩子，有万万个问题。 如果我们不知道要问的正确问题，我们无法获得正确的答案。 许多客户都假设需要如何工作，而不是定义业务问题。 始终可以采用多个路径。
- **过去的最佳实践的长结尾** -认识到最佳实践是以轻型速度变化。 如果你已在3个月前查看过 Azure AD，则可能已过期。 在发布后，此处的所有内容都可能会发生更改。 今天的 "最佳" 选项可能不是从现在开始的6个月。

## <a name="baseline-concepts"></a>基准概念

请勿跳过此部分。 我经常发现，我必须逐步介绍这些主题，即使客户已使用云服务多年。
唉，语言不是精确的工具。 我们经常使用同一个词来表示不同的概念或不同的词语，这也意味着相同的概念。 我经常使用下面的关系图来建立一些基准术语和 "层次结构模型"。
<br><br>

![租户、订阅、服务和数据的插图](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

当您学习提高性能时，最好从池中启动，而不是在海洋的中间。 我不会尝试在技术上与此关系图不精确。 它是一个讨论一些基本概念的模型。 

本图示内容：
- 租户 = Azure AD 的实例。 它位于层次结构的 "top" 中，或位于关系图中的级别1。 我们可以将其视为 "[边界](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-directory-independence)"，以使其他人在) 之前 ([Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) 。 所有 Microsoft 企业云服务都属于其中一个租户。 使用者服务是独立的。 "租户" 在文档中显示为 Office 365 租户、Azure 租户、WVD 租户等。我经常发现这些变体会给客户带来困惑。
- 服务/订阅（图中的级别2）属于一个且只有一个租户。 大多数 SaaS 服务为1:1，不能在不迁移的情况下移动。 Azure 是不同的，你可以 [将帐单](https://docs.microsoft.com/azure/cost-management-billing/manage/billing-subscription-transfer) 和/或 [订阅](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) 移到另一个租户。 有很多客户需要移动 Azure 订阅。 这具有各种含义。 订阅外部的对象 (例如，RBAC 和 Azure AD 对象，包括组、应用、策略等 ) 不会移动。 此外，某些服务 (Azure Key Vault、数据砖块等 ) 在非功能性状态下移动。 如果没有充分的业务需求，请不要迁移服务。 [在 GitHub 上共享](https://github.com/lwajswaj/azure-tenant-migration)一些可能对迁移有用的脚本。 
- 给定服务通常具有某种类型的 "子层" 边界，或级别 3 (L3) 。 这有助于了解安全、策略、治理等的划分。遗憾的是，没有我知道的统一名称。 L3 的一些示例名称为： Azure 订阅 = [resource](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resources-portal);Dynamics 365 CE = [实例](https://docs.microsoft.com/dynamics365/admin/new-instance-management);Power BI = [workspace](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces);Power Apps = [环境](https://docs.microsoft.com/power-platform/admin/environments-overview);如此.
- 级别4是实际数据生存的位置。 此 "数据平面" 是一个复杂的主题。 某些服务使用 Azure AD 进行 RBAC，而其他服务不使用。 当我们转到 "委派" 主题时，我将对此进行讨论。

我发现许多客户 (和 Microsoft) 的一些其他概念与 Microsoft 员工混淆，或者有关于以下内容的问题：


- 任何人都可以 [创建](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) 多个租户，而 [无需付费](https://azure.microsoft.com/pricing/details/active-directory/)。 您不需要在其中设置服务。 我有几十个。 每个租户名称在 Microsoft 的全球云服务中是唯一的 (也就是说，任何两个租户都不能具有相同的名称) 。 它们都采用 TenantName.onmicrosoft.com 的格式。 此外，还提供了 ([非托管租户](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup)) 自动创建租户的过程。 例如，当用户注册企业服务时，如果电子邮件域不存在于任何其他租户中，则会发生这种情况。 
- 在托管租户中，可以在其中注册许多 [DNS 域](https://docs.microsoft.com/azure/active-directory/fundamentals/add-custom-domain) 。 这不会更改原始租户名称。 目前尚无简单的方法来重命名除迁移) 之外的租户 (。 虽然租户名称在技术上是不重要的，但有些人可能会发现这是限制的。
- 您应该为您的组织保留租户名称，即使您尚不打算部署任何服务也是如此。 否则，任何人都可以从你那里获取它，并且没有一个简单的过程来将其返回 (与 DNS 名称) 相同的问题。 我从客户中经常听到这种情况。 您的租户名称也应该是辩论主题。
- 如果您拥有 (s) 的 DNS 命名空间，则应将所有这些都添加到租户 (s) 中。 否则，可以使用此名称创建一个 [非托管租户](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) ，这将导致中断以 [使其受管理](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)。
- DNS 命名空间 (例如，contoso.com) 可以属于一个且只有一个租户。 这对各种方案都有含义 (例如，在合并或获取过程中共享电子邮件域等 ) 有一种方法可以在不同的租户中注册 DNS 子 (（例如 div.contoso.com) ），但应避免这样做。 通过注册顶级域名，假定所有子域都属于同一个租户。 在多租户方案中 (请参阅下面) 我通常建议使用另一个顶级域名 (例如，contoso.ch 或 ch-contoso.com) 。
- 谁应 "拥有" 租户？ 我经常会看到那些不知道谁当前拥有其租户的客户。 这是一个红色的大标志。 尽快致电 Microsoft 支持人员。 正如有问题的是，服务所有者 (通常是 Exchange 管理员) 被指定为管理租户。 租户将包含你将来可能需要的所有服务。 租户所有者应是一个可以决定是否启用组织中的所有云服务的组。 另一个问题是，要求租户所有者组管理所有服务。 对于大型组织，这不会扩展。
- Sub/super 租户没有任何概念。 由于某种原因，此 myth 将保留重复本身。 这也适用于 [AZURE AD B2C](https://docs.microsoft.com/azure/active-directory-b2c/) 租户。 我听到的次数过多，"我的 B2C 环境在我的 XYZ 租户中" 或 "如何将我的 Azure 租户移动到我的 Office 365 租户？"
- 本文档主要侧重于商业全球云，因为这是大多数客户正在使用的。 了解 [sovereign 云](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud)有时很有用。 Sovereign 云有额外的影响，可讨论哪些超出了此讨论的范围。


## <a name="baseline-identity-topics"></a>基准标识主题

有关 Microsoft 的标识平台的大量文档（Azure Active Directory (Azure AD) 。 对于刚开始的人，它通常感觉得很困难。 即使了解 it，持续不断的创新和更改也可能会非常困难。 在我的客户交互中，我通常会发现自己在业务目标和 "良好、更好的最佳" 方法之间提供 "翻译员"，以解决这些 (以及这些主题) 的人 cliff 说明。 很少会有一个完美答案，"正确" 决定是各种风险因素的平衡。 下面列出了我通常与客户讨论的一些常见问题和混乱区域。

### <a name="provisioning"></a>预配
Azure AD 不能解决你的身份全球的治理不足！ [身份治理](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) 应是独立于任何云决策的关键元素。 管理要求随着时间的推移而变化，这就是为什么它是一个程序而不是一个工具的原因。 

[AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect) 与 [Microsoft IDENTITY Manager](https://docs.microsoft.com/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) 与第三方 (第三方或自定义) 其他内容？ 现在和未来使用 Azure AD Connect，为自己节省很多麻烦。 此工具中的所有类型的 smarts 都可解决 peculiar 客户配置和持续创新的需要。 

可能导致更复杂的体系结构的一些边缘情况：
- 我有多个 AD 林，但两者之间没有网络连接。 有一个名为 [云预配](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning)的新选项。
- 我没有 Active Directory，也不需要安装它。 可以将 Azure AD Connect 配置为 [从 LDAP 同步](https://docs.microsoft.com/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) ， (可能需要) 合作伙伴。
- 我需要将相同的对象设置为多个租户。 这在技术上并不受支持，但具体取决于 "相同" 的定义。

我应该自定义默认同步规则 ([筛选对象](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering)、 [更改属性](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)、 [备用登录 ID](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-userprincipalname)等 ) 吗？ 避免！ 标识平台只与使用它的服务一样有用。 虽然您可以执行各种类型的 nutty 配置，但若要回答此问题，您需要查看应用程序的影响。 如果对已启用邮件的对象进行筛选，则联机服务的 GAL 将不完整;如果应用程序依赖于特定的属性，则筛选这些属性将产生不可预知的影响;如此.这不是一个标识团队决策。

XYZ SaaS 支持实时 (JIT) 设置，为什么需要同步？ 具体步骤请见上文。 许多应用程序需要用于功能的 "配置文件" 信息。 如果所有启用邮件的对象均不可用，则不能具有 GAL。 同样适用于与 Azure AD 集成的应用程序中的 [用户预配](https://docs.microsoft.com/azure/active-directory/app-provisioning/user-provisioning) 。


### <a name="authentication"></a>身份验证

 (PHS) 与[传递身份验证](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) 与[联合](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility)身份验证的[密码哈希同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。

通常在联盟周围有一个关心的 [辩论](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) 。 更简单的通常是更好的，因此使用 PHS，除非您有充分的理由不这样做。 此外，还可以为同一个租户中的不同 DNS 域配置不同的身份验证方法。 

有些客户启用联盟 + PHS，主要用于：
- 如果联合身份验证服务不可 [用，则回退到 (](https://docs.microsoft.com/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) 的灾难恢复) 的选项。
- 其他功能 (ex： [AZURE AD DS](https://docs.microsoft.com/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)) 和安全服务 (ex：泄露的 [凭据](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials)) 
- 支持 Azure 中不理解联合身份验证 (ex （例如 [Azure 文件](https://docs.microsoft.com/azure/storage/files/storage-files-active-directory-overview)) ）的服务。

我经常会通过客户端身份验证流向客户阐明一些 misconceptions。 结果如下图所示，它不像获取的交互过程那样好。


![示例白板对话](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

这种类型的白板绘图说明了在身份验证请求流中应用安全策略的位置。 在此示例中，通过 Active Directory 联合身份验证服务强制实施的策略 (AD FS) 应用于第一个服务请求，但不是后续的服务请求。 这至少是将安全控件尽可能移动到云的一个原因。

只要我能记住，我们就会在 (SSO) 中追踪 [单一登录](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) 的梦想。 有些客户认为他们可以通过选择 "右侧" 联合 (STS) 提供程序来实现此目的。 Azure AD 有助于显著帮助 [实现 SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-sso-deployment) 功能，但不神奇 STS。 对于关键应用程序，仍使用过多的 "旧版" 身份验证方法。 使用 [合作伙伴解决方案](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) 扩展 Azure AD 可解决这些方案中的许多情况。 SSO 是一种策略和旅程。 如果没有向 [应用程序的标准](https://docs.microsoft.com/azure/active-directory/develop/v2-app-types)转到此处，则无法获取。 与本主题相关的是 [passwordless](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless) 身份验证的旅程，它也没有神奇的答案。 

 (MFA) 的[多重身份验证](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)目前对 ([此处](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984)的) 更重要。 将添加到 it [用户行为分析](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) 中，并且您有一个可阻止大多数常见网络攻击的解决方案。 即使消费者服务正在迁移，也需要进行 MFA。 然而，我仍在很多不想迁移到 [新式身份验证](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview) 方法的客户会面。 我听到的最大参数是，它会影响用户和旧版应用程序。 有时，良好的启动可能会帮助客户随 Exchange 在线而 [公布更改](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282)。 现在有许多 Azure AD [报告](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) 可帮助客户进行此转换。



### <a name="authorization"></a>授权

根据 [维基百科](https://en.wikipedia.org/wiki/Authorization)，"授权" 是定义访问策略。 许多人将其视为定义对对象 (文件、服务等 ) 的访问控制的能力。 在当前的网络威胁世界中，此概念快速发展为动态策略，该策略可以对各种威胁向量做出反应并快速调整访问控制以响应这些威胁。 例如，如果我从异常位置访问我的银行帐户，我将获得其他确认步骤。 为实现这一点，我们不仅需要考虑策略本身，还需要考虑威胁检测和信号相关方法体系的生态系统。

Azure AD 的策略引擎是使用 [条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)实现的。 此系统依赖各种其他威胁检测系统中的信息来做出动态决策。 一个简单的视图就是如下图所示的内容。

![Azure AD 中的策略引擎](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

将所有这些信号结合在一起可实现类似如下的动态策略：
- 如果在您的设备上检测到威胁，则您对数据的访问权限将仅在没有下载能力的情况下才会减少到 web 上。
- 如果要下载异常量较大的数据，下载的任何内容都将被加密并受限制。
- 如果从非托管设备访问服务，则将阻止来自高度敏感的数据，但允许访问不受限制的数据，但不能将其复制到其他位置。

如果你同意此已扩展的授权定义，则需要实现其他解决方案。 您所实施的解决方案取决于您希望策略的动态程度以及您要设置优先级的威胁。 此类系统的一些示例如下：
- [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/) 
- Azure (Azure ATP) 的[Azure 高级威胁防护](https://docs.microsoft.com/azure-advanced-threat-protection/)
- Microsoft defender (Microsoft Defender ATP) 的[高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- Office [365 高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (OFFICE 365 ATP) 
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) (MCAS) 
-  (MTP) 的[Microsoft 威胁防护](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/mem/intune/)
- Microsoft (MIP) 的[信息保护](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide)
- [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/) 

当然，除了 Azure AD 之外，各种服务和应用程序都有自己的特定授权模型。 在后面的 "委派" 部分中将对其中的一些内容进行讨论。

### <a name="audit"></a>Audit
Azure AD 具有详细的 [审核和报告](https://docs.microsoft.com/azure/active-directory/reports-monitoring/) 功能。 但是，这通常并不是做出安全决策所需的唯一信息源。 请参阅 "委派" 部分中有关此内容的更多讨论。

## <a name="there-is-no-exchange"></a>没有 Exchange

不要惊慌！ 这并不意味着 Exchange 不会被弃用 (或 SharePoint 等，) 它仍是核心服务。 我的意思是，在很长的时间内，技术提供商已在将用户体验 (UX) 转换为包含多个服务的组件。 在 Microsoft 365 中，一个简单的示例是 "[新式附件](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)"，其中电子邮件附件存储在 SharePoint Online 或 OneDrive for business 中。 

![将文件附加到电子邮件](../media/solutions-architecture-center/modern-attachments.png)

查看 Outlook 客户端可以看到许多作为此体验一部分的 "已连接" 服务，而不仅仅是 Exchange。 这包括 Azure AD、Microsoft Search、应用、配置文件、合规性和 Office 365 组。 

![带有标注的 Outlook 界面](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

阅读有关即将推出的功能的预览版的 [Microsoft 流体框架](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) 。 在 "预览" 中，我可以直接在 Outlook 中阅读和回复团队对话。 事实上， [团队客户端](https://products.office.com/microsoft-teams/download-app) 是此策略的更突出的示例之一。 

总而言之，在 Microsoft 云中的 Office 365 和其他服务之间绘制清楚的线条变得越来越困难。 我将其视为对客户非常有益的好处，因为他们可以从整体创新中受益，即使他们使用一个组件也是如此。 非常酷，为许多客户带来了深远的影响。

今天，我发现许多客户 IT 组都围绕 "产品" 进行了构建。 由于您需要针对每个特定产品的专家，因此本地环境的逻辑。 但是，在这些服务移到云中时，我完全感到不需要再次调试 Active Directory 或 Exchange 数据库。 自动化 () 的云类型可删除某些重复的手动作业 (查看工厂) 所发生的操作。 但是，这些都是用更复杂的要求取代的，以了解跨服务交互、影响、业务需求等。如果你愿意 [学习](https://docs.microsoft.com/learn/)，云转换会提供极大的机会。 在转到技术之前，我经常与客户讨论如何管理 IT 技能和团队结构中的变化。

对于所有 SharePoint 风扇-人员和开发人员，请停止询问 "如何才能在 SharePoint online 中执行 XYZ？" 使用 [Power](https://docs.microsoft.com/power-automate/) (表示工作流的流) 的功能，它是功能更加强大的平台。 使用 [Azure Bot 框架](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0) 为你的500,000 名项目列表创建更好的 UX。 开始使用 [Microsoft Graph](https://developer.microsoft.com/graph/) 而不是 CSOM。 [Microsoft 团队](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) 包括 SharePoint，但还有更多。 我可以列出许多其他示例。 这里有一个巨大且有魅力的宇宙。 打开门， [开始探索](https://docs.microsoft.com)。

另一个常见的影响是合规性区域。 这种跨服务方法似乎完全混淆了许多合规性策略。 我一直在查看 "我需要将所有电子邮件通信记录到电子数据展示系统" 的组织状态。 如果电子邮件不再只是电子邮件，而是其他服务的窗口，这实际上是什么意思？ Office 365 具有全面的 [合规性](https://docs.microsoft.com/microsoft-365/compliance/)方法，但更改人员和过程通常要比技术困难得多。

还有许多其他人和过程影响。 在我看来，这是一个关键且下方讨论的区域。 在另一篇文章中可能会更多。

## <a name="tenant-structure-options"></a>租户结构选项

### <a name="single-tenant-vs-multi-tenant"></a>单个租户与多租户

通常情况下，大多数客户应只有一个生产租户。 有许多原因会导致多个租户受到挑战 (为其指定 [必应搜索](https://www.bing.com/search?q=office%20365%20multiple%20tenants)) 或阅读本 [白皮书](https://aka.ms/multi-tenant-user)。 同时，我与我合作的许多企业客户都有另一个 (小型) 租户，用于 IT 学习、测试和实验。 通过 [Azure Lighthouse](https://azure.microsoft.com/services/azure-lighthouse/)使跨租户 azure 访问变得更加轻松。 Office 365 和其他许多 SaaS 服务对跨租户方案有限制。 [AZURE AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)方案中有很多需要考虑的事项。

在合并和收购 (M&) 后，许多客户会在多个生产租户中结束，并需要进行整合。 目前，这并不简单，需要 Microsoft 咨询服务 (MCS) 或合作伙伴和第三方软件。 将来，有一项正在进行的工程工作用于解决多个应用场景的各种情况。 

一些客户选择使用多个租户。 这应是一个非常小心的决策，并且几乎总是业务原因驱动因素！ 一些示例包括以下内容：
- 不需要在不同实体之间实现轻松协作的控股类型公司结构，并且存在强大的管理和其他隔离需求。
- 在收购之后，将进行业务决策以使两个实体相互独立。
- 客户环境的模拟，不会更改客户的生产环境。 
- 开发面向客户的软件。

在这些多租户方案中，客户通常希望在租户中保持某些配置相同，或报告配置更改和 drifts。 这通常意味着将手动更改作为代码移动到配置中。 Microsoft 面向支持为基于此公共 IP 的以下类型的要求提供研讨会： [https://Microsoft365dsc.com](https://Microsoft365dsc.com) 。


### <a name="multi-geo"></a>多地理位置 

到 [多地理](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo) 位置或不到多地理位置，这就是问题所在。 使用 Office 365 多地理位置，您可以在您选择用于满足 [数据驻留](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations) 要求的地理位置设置和存储静态数据。 此功能有许多 misconceptions。 请注意下列事项： 
- 它不提供性能优势。 如果 [网络设计](https://aka.ms/office365networking) 不正确，则性能会更差。 获取与 Microsoft 网络的设备 "关闭"，而不一定是您的数据。
- 它不是用于 [GDPR 合规性](https://www.microsoft.com/trust-center/privacy/gdpr-overview)的解决方案。 GDPR 不会重点关注数据主权或存储位置。 还有其他合规性框架。
- 它不会解决管理委派 (请参阅以下) 或 [信息障碍](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)。
- 它与多租户不同，需要额外的 [用户预配](https:/docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) 工作流。
- 它不会 [将租户](https://docs.microsoft.com/microsoft-365/enterprise/moving-data-to-new-datacenter-geos) (Azure AD) 移到其他地理位置。 

## <a name="delegation-of-administration"></a>管理委派

在大多数大型组织中，职责分离和基于角色的访问控制 (RBAC) 是必需的现实。 我将提前为你深表歉意。 这并不像一些客户希望的那样简单。 客户、法律、法规遵从性和其他要求各不相同，并且有时在全球发生冲突。 简单和灵活性通常在彼此相反的一侧。 不要让我误，我们可以在此处做更好的工作。 已 (，并且将在一段时间内) 重大改进。 访问本地 [Microsoft 技术中心](https://www.microsoft.com/mtc) ，以在不阅读379230文档的情况下满足业务需求的模型！ 在这里，我将重点介绍您应考虑的事项，并不是为什么这样做的原因。 以下是要规划的五个不同的领域以及我遇到的一些常见问题。

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure AD 和 Microsoft 365 管理中心

[内置角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)的列表很长且越来越多。 每个角色都包含一组组合在一起的角色权限，以允许执行特定操作。 您可以在每个角色内的 "说明" 选项卡中查看这些权限。 此外，您还可以在 Microsoft 365 管理中心查看更多可读版本的用户。 无法修改内置角色的定义。 我通常会将它们分为三类：

- **全局管理员** —就像在其他系统中那样，这种 "所有强大的" 角色应受到 [高度保护](https://docs.microsoft.com/microsoft-365/enterprise/protect-your-global-administrator-accounts) 。 典型的建议包括：不永久分配并使用 Azure AD 特权标识管理 (PIM) ;强身份验证;如此.有趣的是，在默认情况下，此角色不允许你访问所有内容。 通常情况下，我看到关于合规性访问和 Azure 访问的困惑，稍后对此进行了讨论。 但是，此角色始终可以将访问权限分配给租户中的其他服务。 
- **特定服务管理员** -某些服务 (Exchange、SharePoint、Power BI 等，) 使用 Azure AD 中的高级别管理角色。 这在所有服务中不一致，后面还讨论了更多特定于服务的角色。
- **功能** —有一个较长的 () 的角色的列表，这些角色重点关注 (来宾 ) 邀请者等特定操作的角色。 根据客户的需要，会定期添加更多的。

虽然差距降低) （这意味着有时需要使用全局管理员角色），但不能委派 (的所有内容。 应考虑配置为代码和自动化，而不是此角色的人员成员身份。

**注意**： Microsoft 365 管理中心具有用户友好的更友好界面，但具有与 Azure AD 管理员体验相比的功能子集。 这两个门户都使用相同的 Azure AD 角色，因此更改发生在同一位置。 提示：如果您希望在没有所有 Azure 混乱的情况下以标识管理为中心的管理 UI，请使用 [https://aad.portal.azure.com](https://aad.portal.azure.com) 。 

名称中有什么？ 请勿从角色名称中进行假设。 语言不是非常精确的工具。 目标应是在查看所需的角色之前定义需要委派的操作。 向 "安全读者" 角色添加人员并不会使其在所有内容中都能看到安全设置。 

创建 [自定义角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/roles-custom-overview) 的能力是一个常见的问题。 这在 Azure AD 今天受到限制 (请参阅下文) ，但随着时间的推移将随功能增长。 我认为这些函数适用于 Azure AD 中的函数，可能不会跨越上面讨论的层次结构模型 () 。 当我处理 "自定义" 时，我倾向于回到我的 "简单越好" 主体。

另一个常见的问题是能够将角色范围限定为目录的子集。 一个示例就是 "仅支持欧盟的用户的 ' 支持人员管理员 '"。 旨在解决此 (AU) 的[管理单元](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-administrative-units)。 就像上面的情况，我认为这些功能适用于 Azure AD 中的功能，可能不会跨越 "down"。 当然，某些角色对范围 (全局管理员、服务管理员等没有意义 ) 

目前，如果使用 [AZURE AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/)) ，所有这些角色都需要直接成员身份 (或动态分配。 这意味着客户必须直接在 Azure AD 中管理它们，并且这些客户无法基于安全组成员身份。 我不是创建脚本来管理这些脚本的风扇，因为它需要提升的权限运行。 通常情况下，我建议使用 API 与 ServiceNow 等进程系统集成，或使用合作伙伴治理工具（如 Saviynt）。 根据时间的推移，我们将提供工程工作来解决这一情况。

我提到了 [AZURE AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) 几次。 对于本地控件，有一个对应的 Microsoft Identity Manager (MIM) [特权访问管理](https://docs.microsoft.com/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) (PAM) 解决方案。 您可能还需要查看 [特权访问工作站](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) 和 [Azure AD 标识管理](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)。 此外，还有许多第三方工具可以同时启用实时、足够且动态的角色提升。 这通常是用于保护环境的更大讨论的一部分。 

有时用于向角色添加外部用户的方案 (请参阅) 上的 "多租户" 部分。 这只是正常工作。 [AZURE AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/) 是帮助客户完成的另一个大有趣主题，可能在另一篇文章中。

### <a name="security-and-compliance-center-scc"></a> (SCC) 的安全与合规中心

[Office 365 安全 & 合规中心中的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) 是 "角色组" 的集合，这些组与 Azure AD 角色是相互独立和不同的。 这可能会令人困惑，因为其中一些角色组的名称与 Azure AD 角色相同 (例如，Security Reader) ，但它们可以具有不同的成员身份。 我更喜欢使用 Azure AD 角色。 每个角色组都包含一个或多个 "roles" (请参阅我为什么要重复使用同一个词？ ) 并拥有来自 Azure AD 的成员，这些成员是启用电子邮件的对象。 此外，还可以创建与角色具有相同名称的角色组，该角色组可能包含也可能不包含该角色 (避免) 的混乱。

在某种意义上，这些是 Exchange 角色组模型的演变。 但是，Exchange Online 拥有自己的 [角色组管理](https://docs.microsoft.com/exchange/permissions-exo) 界面。 Exchange Online 中的某些角色组是通过 Azure AD 或 Security & 合规性中心进行锁定和管理的，但其他人可能具有相同或类似的名称，并且在 Exchange Online 中进行管理 (添加到混淆) 。 建议您避免使用 Exchange Online 用户界面，除非您需要 Exchange management 的作用域。

您不能创建自定义角色。 角色由 Microsoft 创建的服务定义，并将随着新服务的引入而增长。 这在概念上类似于 Azure AD 中 [的应用程序定义的角色](https://docs.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) 。 启用新服务时，通常需要创建新角色组，以便授予或委派对这些 (的访问权限，例如， [内幕风险管理](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure?view=o365-worldwide#step-1-required-enable-permissions-for-insider-risk-management)) 。

这些角色组还需要直接成员身份，且不能包含 Azure AD 组。 遗憾的是，今天的 Azure AD PIM 不支持这些角色组。 与 Azure AD 角色一样，我倾向于通过 Api 或合作伙伴治理产品（如 Saviynt 或其他用户）来管理这些角色。

Security & 合规性中心角色跨 Microsoft 365，您无法将这些角色组的作用域与环境 (的子集进行作用域，就像您在 Azure AD) 中使用管理单元一样。 许多客户会询问他们如何进行子委派。 例如，"仅为 EU 用户创建 DLP 策略"。 目前，如果您对安全 & 合规中心中的特定功能有权限，则您对租户中此函数所涵盖的所有内容具有权限。 但是，许多策略都具有针对环境子集的功能 (例如，"将这些 [标签](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy) 仅供这些用户使用" ) 。 适当的治理和通信是避免冲突的关键组件。 有些客户选择实施 "配置为代码" 方法来解决安全性 & 合规性中心中的子委派问题。 某些特定服务支持子委派 (请参阅以下) 。 

值得注意的是，当前通过 Security & 合规性中心管理的控件 (protection.office.com) 正处于迁移到两个单独的管理门户： security.microsoft.com 和 compliance.microsoft.com 的过程中。 更改是唯一的常量！

### <a name="service-specific"></a>特定于服务

如前所述，许多客户都希望获得更精细的委派模型。 一个常见的示例是： "仅管理分部 X 用户和位置的 XYZ 服务" (或某个其他维度) 。 执行此操作的能力取决于每个服务，并且在服务和功能上不一致。 此外，每个服务可能具有单独且唯一的 RBAC 模型。 为每个服务添加相关链接，而不是讨论所有这些 (将永远不会) 。 这不是完整列表，但会启动。

- **Exchange Online** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators) 
- **Microsoft 团队**  - [https://docs.microsoft.com/microsoftteams/itadmin-readiness ](https://docs.microsoft.com/microsoftteams/itadmin-readiness )
- **发现** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](https://docs.microsoft.com/microsoft-365/compliance/) 
  + **权限筛选**  - [https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search ](https://docs.microsoft.com/microsoft-365/compliance/)
  + **合规性边界**  - [https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries ](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries )
  + **高级电子数据展示**  - [https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 ](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 )
- **Yammer** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins) 
- **多地理位置** - [https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin](https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin) 
- **Dynamics 365** – [https://docs.microsoft.com/dynamics365/](https://docs.microsoft.com/dynamics365/) <br>
  注意：此链接指向文档的根。 有多种类型的服务，在管理/委派模型中有变体。
- **Power Platform**  - [https://docs.microsoft.com/power-platform/admin/admin-documentation ](https://docs.microsoft.com/power-platform/admin/admin-documentation )
  + **Power Apps**  - [https://docs.microsoft.com/power-platform/admin/wp-security ](https://docs.microsoft.com/power-platform/admin/wp-security ) <br>
    注意：在管理/委派模型中有多个类型具有变体。
  + **电源自动化**  - [https://docs.microsoft.com/power-automate/environments-overview-admin ](https://docs.microsoft.com/power-automate/environments-overview-admin )
  + **PowerBI**  - [https://docs.microsoft.com/power-bi/service-admin-governance ](https://docs.microsoft.com/power-bi/service-admin-governance ) <br>
注意：数据平台安全性和委派 (Power BI 是一个复杂区域) 组件。
- **MEM/Intune**  - [https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control ](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control )
- **Microsoft DEFENDER ATP**  - [https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles )
- **Microsoft 威胁防护** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions)
- **Microsoft 云应用安全** - [https://docs.microsoft.com/cloud-app-security/manage-admins](https://docs.microsoft.com/cloud-app-security/manage-admins)
- **流**  - [https://docs.microsoft.com/stream/assign-administrator-user-role ](https://docs.microsoft.com/stream/assign-administrator-user-role )
- **信息障碍**  - [https://docs.microsoft.com/microsoft-365/compliance/information-barriers ](https://docs.microsoft.com/microsoft-365/compliance/information-barriers )

对于 rest，文档在文档中的最近意义上非常出色 [https://docs.microsoft.com/](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) 。 


### <a name="activity-logs"></a>活动日志
Office 365 具有 [统一的审核日志](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。 这是一个非常 [详细的日志](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)，但不能在名称中读取太多。 它可能不包含您需要的所有内容，也不包含需要满足您的安全和合规性需求。 此外，有些客户确实对 [高级审核](https://docs.microsoft.com/microsoft-365/compliance/advanced-audit)感兴趣。 

通过其他 API 访问的 Microsoft 365 日志示例包括以下内容：
- 与 Office 365 不相关的[AZURE AD](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings) (活动) 
- [Exchange 邮件跟踪](https://docs.microsoft.com/powershell/module/exchange/get-messagetrace?view=exchange-ps)
- 上面讨论的威胁/UEBA 系统 (例如，Azure AD Identity Protection、Microsoft 云应用安全性、Microsoft Defender ATP 等 ) 
- [Microsoft 信息保护](https://docs.microsoft.com/microsoft-365/compliance/data-classification-activity-explorer?view=o365-worldwide)
- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

首先确定安全与合规性计划所需的所有日志源，这一点非常重要。 另请注意，不同的日志具有不同的在线保留限制。 

从管理委派的角度来看，大多数 Microsoft 365 活动日志没有内置的 RBAC 模型。 如果您具有查看日志的权限，则可以查看其中的所有内容。 客户要求的一个常见示例是： "我希望能够仅查询欧盟用户的活动" (或某个其他维度) 。 若要实现此要求，我们需要将日志传送到另一个服务。 在 Microsoft 云中，我们建议将其转移到 [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview) 或 [Log Analytics](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)。 

高级别图表：

![日志流的高级别关系图](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

上图表示将日志发送到事件中心和/或 azure 存储和/或 Azure 日志分析的内置功能。 并非所有系统都包含此现成的。 但也可以通过其他方法将这些日志发送到同一个存储库。 例如，请参阅 [使用 Azure Sentinel 保护你的团队](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761)。

将所有日志合并到一个存储位置包括增加的优势，如交叉关联、自定义保留时间、使用支持 RBAC 模型所需的数据进行扩充等。一旦数据位于此存储系统中，您就可以使用适当的 RBAC 模型创建 PowerBI 仪表板 (或其他类型的可视化) 。

日志无需定向到一个位置。 将 [Office 365 日志与 Microsoft 云应用安全性](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) 或自定义 RBAC 模型集成在 [Power BI](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics?view=o365-worldwide)中也可能会有好处。 不同的库具有不同的优势和受众。

值得一提的是，在称为 [Microsoft 威胁防护](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)的服务中有一个非常丰富的内置分析系统，用于安全性、威胁、漏洞等。

许多大型客户希望将此日志数据传输到第三方系统 (例如，SIEM) 。 这种方法有不同的方法，但在常规 [Azure 事件中心](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) 和 [图形](https://docs.microsoft.com/graph/security-integration) 中是良好的起始点。


### <a name="azure"></a>Azure 
我经常会问，如果有一种方法可以在 Azure AD、Azure 和 SaaS (（例如，全局365管理员，而非 Azure) ）中分隔高权限角色。  没有。  如果需要完全管理分离，则需要多租户体系结构，但这会增加大量 [复杂性](https://aka.ms/multi-tenant-user) (请参阅以上) 。 所有这些服务都是同一安全/身份边界的一部分 (查看上面) 的层次结构模型。  

了解同一个租户中各种服务之间的关系非常重要。 我正在与许多客户合作构建业务解决方案，这些解决方案跨 Azure、Office 365 和电源平台 (，并且通常也是本地和第三方云服务) 。 一个常见的示例： 
-   我想要协作处理一组文档/图像/etc (Office 365) 
-   通过 (电源平台) 的审批流程发送每个用户
-   在所有组件获得批准后，将它们组合到统一的可交付结果 (s 中)  (Azure) [Microsoft GRAPH API](https://docs.microsoft.com/azure/active-directory/develop/microsoft-graph-intro) 是您最适合这样做的。  不可能，但设计跨越 [多个租户](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)的解决方案要复杂得多。

基于 azure 角色的访问控制 (RBAC) 为 Azure 启用细化访问管理。 通过使用 RBAC，可以通过向用户授予执行其工作所需的最少权限来管理对资源的访问。 详细信息超出了本文档的范围，但有关 RBAC 的详细信息，请参阅 [什么是基于角色的访问控制 (RBAC) 在 Azure 中？](https://docs.microsoft.com/azure/role-based-access-control/overview) RBAC 是重要的，但只是 Azure 的监管注意事项的一部分。 [云采用框架](https://docs.microsoft.com/azure/cloud-adoption-framework/govern/) 是了解详细信息的一个很好的起点。 我喜欢我的好友，Andres Ravinet 指导客户分步介绍了各种组件以决定方法。 各种元素的高级视图 (不像要获取实际客户模型) 的过程一样好，如下所示：

![用于委派管理的 Azure 组件的高级视图](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

正如您可以从上图中看到的，许多其他服务应被视为设计 (例如， [Azure 策略](https://docs.microsoft.com/azure/governance/policy/overview)、 [azure 蓝图](https://docs.microsoft.com/azure/governance/blueprints/overview)、 [管理组](https://docs.microsoft.com/azure/governance/management-groups/)等）的一部分 ) 

## <a name="conclusion"></a>结束语
作为简短摘要启动，结束时间超过了预期时间。  我希望你现在可以深入了解如何为你的组织创建委派模型。  此对话对客户非常常见。 没有一个适用于每个人的模型。 在记录我们跨客户看到的常见模式之前，请先等待 Microsoft 工程部门的几个计划改进。 同时，你可以与 Microsoft 帐户团队合作，安排对最接近 [Microsoft 技术中心](https://www.microsoft.com/mtc)的访问。  向你显示！


