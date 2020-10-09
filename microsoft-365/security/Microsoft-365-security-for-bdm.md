---
title: 适用于业务决策者 (Bdm) 的 Microsoft 365 安全性
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 组织在其 Microsoft 365 环境中目前面临的最常见的威胁和攻击方案，以及缓解这些风险的建议操作。
ms.openlocfilehash: 4181feeed97313ec1e8d916df994cc880cbffdf1
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399451"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>适用于业务决策者 (Bdm) 的 Microsoft 365 安全性

本文讨论当前组织针对其 Microsoft 365 环境所面临的一些最常见的威胁和攻击方案，以及用于缓解这些风险的建议操作。 虽然 Microsoft 365 提供了一系列预配置的安全功能，但也要求您作为客户负责保护您自己的身份、数据和用于访问云服务的设备。 本指南由 Microsoft 云安全架构师) 和 Thiagaraj Sundararajan (Microsoft 高级顾问) 的 Kozeta (开发。

本文按工作优先级进行组织，从保护用于管理最关键服务和资产（如租户、电子邮件和 SharePoint）的帐户开始。 它为接近安全性和使用以下电子表格一起工作提供了一种方法，以便您可以跟踪组织中的利益干系人和团队的进度： [Microsoft 365 bdm 电子表格的安全性](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)。 

[![缩略图 Microsoft 365 BDM 安全建议电子表格](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

Microsoft 向你提供租户中的安全分数工具，以根据你的常规活动自动分析安全状态、分配分数并提供安全改进建议。 在执行本文中建议的操作之前，请注意你当前的分数和建议。 本文中建议的操作将增加你的成绩。 目标不能达到最大分数，但要了解以不会对用户的工作效率产生负面影响的方式来保护您的环境的机会。 请参阅 [Microsoft 安全分数](mtp/microsoft-secure-score.md)。

在开始之前，还需要做一点准备。 . . [请务必打开审核日志](../compliance/search-the-audit-log-in-security-and-compliance.md)。 稍后你将需要此数据，如果你需要调查事件或泄露。 

## <a name="protect-privileged-accounts"></a>保护特权帐户

作为第一步，我们建议确保环境中的关键帐户被授予额外的保护层，因为这些帐户具有管理和更改关键服务和资源的权限，这些帐户会对整个组织造成负面影响（如果受到威胁）。 保护特权帐户是对寻找将受影响的帐户的权限提升到管理帐户的攻击者最有效的方法之一。 

|建议  |E3 |E5  |
|---------|---------|---------|
|对所有管理帐户强制执行多重身份验证 (MFA) 。|![绿色复选标记](../media/green-check-mark.png)|![绿色复选标记](../media/green-check-mark.png)| 
|将 Azure Active Directory (Azure AD) 的特权标识管理 (PIM) 应用到 Azure AD 和 Azure 资源的实时权限访问权限。 您还可以发现谁有权访问并查看有权限的访问权限。|         | ![绿色复选标记](../media/green-check-mark.png)|
|实施特权访问管理来管理 Office 365 中的特权管理任务的粒度访问控制。 |         | ![绿色复选标记](../media/green-check-mark.png)|
|配置和使用特权访问工作站 (PAW) 管理服务。 请勿使用相同的工作站浏览 Internet 和检查与您的管理帐户无关的电子邮件。|  ![绿色复选标记](../media/green-check-mark.png)|![绿色复选标记](../media/green-check-mark.png) | 

下图说明了这些功能。
![用于保护特权帐户的推荐功能](../media/m365-security-bdm-illustrations-privileged-accounts.png)

其他建议：
- 确保不会为云服务的管理员角色分配从本地同步的帐户。 这有助于防止攻击者利用本地帐户获取云服务的管理访问权限。 
- 确保不会为服务帐户分配管理员角色。 这些帐户通常不会通过不过期的密码进行监视和设置。 首先，确保 AADConnect 和 ADFS 服务帐户在默认情况下不是全局管理员。
- 从管理员帐户中删除许可证。 除非有特定用例将许可证分配给特定的管理员帐户，否则请从这些帐户中删除许可证。 

## <a name="reduce-the-surface-of-attack"></a>降低攻击的表面

下一个重点领域是减少攻击的表面。 这样可以实现对用户和服务的最小努力和影响。 通过减少攻击的外围区域，攻击者可以使用更少的方法发起对组织的攻击。

下面是一些示例：
- 禁用 POP3、IMAP 和 SMTP 协议。 大多数新式组织不再使用这些旧协议。 您可以安全地禁用这些异常，并在需要时仅允许例外。 
- 将租户中的全局管理员数减少，并将其保留为所需的绝对最小值。 这将直接降低所有云应用程序的攻击面。 
- 停用在您的环境中不再使用的服务器和应用程序。 
- 实施用于禁用和删除不再使用的帐户的过程。 

## <a name="protect-against-known-threats"></a>抵御已知威胁

已知威胁包括恶意软件、受损帐户和网络钓鱼。 某些针对这些威胁的保护可以快速实施，而不会对用户造成直接影响，而其他则需要更多的规划和用户培训。 

|建议  |E3  |E5  |
|---------|---------|---------|
|**设置多重身份验证并使用建议的条件访问策略，包括登录风险策略**。 Microsoft 建议并测试了一组协同工作的策略，以保护所有云应用，包括 Office 365 和 Microsoft 365 服务。 请参阅 [标识和设备访问配置](./office-365-security/microsoft-365-policies-configurations.md)。 | |![绿色复选标记](../media/green-check-mark.png)|
|**对所有用户要求多因素身份验证**。 如果您没有实现建议的条件访问策略所需的许可，则至少需要对所有用户进行多重身份验证。|![绿色复选标记](../media/green-check-mark.png)|![绿色复选标记](../media/green-check-mark.png)|
|**提高针对邮件中的恶意软件的保护级别**。 你的 Office 365 或 Microsoft 365 环境包括针对恶意软件的防护，但你可以通过阻止常见恶意软件使用的文件类型的附件来提高此保护。|![绿色复选标记](../media/green-check-mark.png)|![绿色复选标记](../media/green-check-mark.png)|
|**保护你的电子邮件免受目标钓鱼攻击**。 如果您为 Office 365 或 Microsoft 365 环境配置了一个或多个自定义域，则可以配置目标的反网络钓鱼保护。 ATP 反网络钓鱼保护是 Office 365 高级威胁防护的一部分，可帮助保护您的组织免受基于恶意模拟的网络钓鱼攻击和其他网络钓鱼攻击。 如果尚未配置自定义域，则无需执行此操作。| |![绿色复选标记](../media/green-check-mark.png)|
|**在电子邮件中防御勒索软件攻击**。 勒索软件通过加密文件或锁定计算机屏幕来接管对数据的访问。 然后，它会通过在 exchange 中请求 "勒索" （通常为 "Bitcoin" 形式）来返回对您的数据的访问权限，从而试图 extort 来自受害者的钱。 您可以通过创建一个或多个邮件流规则来阻止勒索软件通常使用的文件扩展名，或警告用户在电子邮件中接收这些附件，从而帮助抵御勒索软件。|![绿色复选标记](../media/green-check-mark.png)|![绿色复选标记](../media/green-check-mark.png)|
|**阻止来自你不与之有业务往来的国家/地区的连接**。 创建 Azure AD 条件访问策略以阻止来自这些国家/地区的任何连接，在你的租户周围有效创建 geo 防火墙。| |![绿色复选标记](../media/green-check-mark.png)|

下图说明了这些功能。
![针对已知威胁进行保护的建议功能](../media/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>抵御未知威胁

向特权帐户添加了额外的保护，并针对已知的攻击进行保护后，请将您的注意力转移以防止出现未知威胁。 更确定和高级的 adversaries 使用创新的、新的、未知的方法来攻击组织。 使用 Microsoft 通过数十亿的设备、应用程序和服务收集的大量数据遥测数据，我们可以在 Windows、Office 365 和 Azure 上执行高级威胁防护，以防止零天攻击、利用沙滩 box 环境以及在允许访问内容之前检查有效性。 


|建议  |E3  |E5  |
|---------|---------|---------|
|**将 Office 365 高级威胁防护配置 (ATP) **：<br>* ATP 安全附件<br>* ATP 安全链接<br>* 适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP<br>* ATP 反网络钓鱼防护|         |![绿色复选标记](../media/green-check-mark.png) |
|**配置 Microsoft Defender 高级威胁防护功能**：<br>* Windows Defender 防病毒 <br>* 攻击保护 <br> * 攻击面减少 <br> * 基于硬件的隔离 <br>* 受控制的文件夹访问     |         |![绿色复选标记](../media/green-check-mark.png) |
|**使用 Microsoft 云应用安全** 来发现 SaaS 应用程序，并开始使用行为分析和异常检测。 |         |![绿色复选标记](../media/green-check-mark.png) |

下图说明了这些功能。
![针对防止未知威胁的建议功能](../media/m365-security-bdm-illustrations-unknown-threats.png)

其他建议：
- 安全的合作伙伴通道通信，如使用 TLS 的电子邮件。
- 仅打开与您与之通信的合作伙伴的团队联盟。
- 不要将发件人域、单个发件人或源 Ip 添加到允许列表中，因为这样可以绕过垃圾邮件和恶意软件检查—通常情况下，客户会将其自己的接受域或许多其他域添加到允许列表中，其中可能会报告电子邮件流问题。 请勿在垃圾邮件和连接筛选列表中添加域，因为这可能会绕过所有垃圾邮件检查。 
- 启用出站垃圾邮件通知—对位于 "支持人员" 或 IT 管理员团队内部的通讯组启用出站垃圾邮件通知，以报告是否有任何内部用户在外部发送垃圾邮件。 这可能表示帐户已泄露。
- 对所有用户禁用远程 PowerShell —远程 PowerShell 主要供管理员用来访问服务，以实现管理目的或编程 API 访问。 我们建议为非管理员用户禁用此选项，以避免侦测，除非他们有业务要求对其进行访问。 
- 阻止对所有非管理员的 Microsoft Azure 管理门户的访问。 若要实现此目的，可以创建一个条件访问规则来阻止所有用户，但管理员除外。 


## <a name="assume-breach"></a>承担破坏

尽管 Microsoft 采取每种可能的措施来防止威胁和攻击，但我们建议您始终在 "假定泄露" 思维方式下工作。 即使攻击者已管理到环境中的 intrude，我们也需要确保他们无法 exfiltrate 数据或环境中的标识信息。 出于此原因，我们建议对敏感数据泄露（如社会保险号、信用卡号码、其他个人信息和其他组织级别的机密信息）启用保护。 

"假定违规" 思维方式需要实现零信任网络策略，这意味着用户不能完全信任，这是因为它们是网络内部的。 相反，在授权用户可以执行的操作时，将指定条件集，并且在满足此类条件时，将强制实施某些控件。 条件可能包括设备运行状况状态、要访问的应用程序、正在执行的操作以及用户风险。 例如，设备注册操作应始终触发 MFA 身份验证，以确保不会将任何 rouge 设备添加到您的环境中。 

零信任网络策略还要求您知道信息的存储位置，并为分类、保护和保留应用适当的控件。 若要有效保护您最关键和敏感的资产，您需要首先确定这些资产的位置并进行清点，这可能是一个挑战。 接下来，与您的组织合作以定义调控策略。 为组织定义分类架构并配置策略、标签和条件需要仔细规划和准备。 一定要意识到这不是 IT 驱动的过程。 请务必与法律和合规性团队合作，为组织的数据开发适当的分类和标签架构。

Microsoft 365 信息保护功能可帮助您发现您拥有的信息、存储的位置以及哪些信息需要额外的保护。 信息保护是一个持续的过程，Microsoft 365 功能为您提供了用户使用和分发敏感信息的方式，以及信息当前存储在何处以及在何处流动。 您还可以查看用户如何处理受管制的信息，以确保应用适当的标签和保护。


|建议 |E3|E5 |
|---------|---------|---------|
|**查看并优化你的条件访问和相关策略，以适应零信任网络的目标**。 防范已知威胁包括实施一组建议的 [策略](./office-365-security/microsoft-365-policies-configurations.md)。 检查这些策略的实现，以确保您正在保护您的应用程序和数据免受已访问您的网络的黑客的攻击。 请注意，推荐的适用于 Windows 10 的 Intune 应用保护策略启用 Windows 信息保护 (WIP) 。 WIP 可防止通过应用和服务（如电子邮件、社交媒体和公共云）意外泄漏组织数据。 |         |![绿色复选标记](../media/green-check-mark.png)|
|**禁用外部电子邮件转发**。 通过将邮箱设置为自动转发电子邮件，获取对用户邮箱的访问权限的黑客可以盗取您的邮件。 即使没有用户的意识，也会发生这种情况。 您可以通过配置邮件流规则来防止这种情况发生。|![绿色复选标记](../media/green-check-mark.png) |![绿色复选标记](../media/green-check-mark.png)|
|**禁用匿名外部日历共享**。 默认情况下，允许外部匿名日历共享。 [禁用日历共享](https://docs.microsoft.com/exchange/sharing/sharing-policies/modify-a-sharing-policy) ，以减少敏感信息的可能泄漏。|![绿色复选标记](../media/green-check-mark.png) |![绿色复选标记](../media/green-check-mark.png)|
|**配置敏感数据的数据丢失防护策略**。 在安全合规中心中创建数据丢失防护策略 &amp; ，以发现和保护敏感数据，如信用卡号、社会保险号码和银行帐户号码。 Microsoft 365 包括许多可在数据丢失防护策略中使用的预定义敏感信息类型。 您还可以为您的环境自定义的敏感数据创建您自己的敏感信息类型。 |![绿色复选标记](../media/green-check-mark.png)|![绿色复选标记](../media/green-check-mark.png)|
|**实施数据分类和信息保护策略**。 实施灵敏度标签并使用它们对敏感数据进行分类和应用保护。 您还可以在数据丢失防护策略中使用这些标签。 如果使用的是 Azure 信息保护标签，我们建议您避免在其他管理中心创建新标签。|         |![绿色复选标记](../media/green-check-mark.png)|
|**使用云应用安全性保护第三方应用程序和服务中的数据**。 配置云应用安全策略以保护跨第三方云应用（如 Salesforce、Box 或 Dropbox）的敏感信息。 您可以使用您在云应用安全策略中创建的敏感信息类型和敏感度标签，并在您的 SaaS 应用程序中应用它们。 <br><br>Microsoft 云应用安全性使您能够强制实施各种自动化的过程。 可以将策略设置为提供连续合规性扫描、法律电子数据展示任务、DLP 对公开共享的敏感内容等。 云应用安全可以根据20个以上的元数据筛选器监视任何文件类型 (例如，访问级别、文件类型) 。 |         |![绿色复选标记](../media/green-check-mark.png)|
|**使用 [MICROSOFT Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview) 来确定用户是否将敏感信息存储在其 Windows 设备上**。 |         |![绿色复选标记](../media/green-check-mark.png)|
|**使用 [AIP 扫描程序](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) 可在服务器和文件共享中标识和分类信息**。 使用 AIP 报告工具查看结果并采取适当的操作。|         |![绿色复选标记](../media/green-check-mark.png)|

下图说明了这些功能。
![针对防止泄露的建议功能](../media/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>持续监控和审核

最后，但不是对 Microsoft 365 环境和 Windows 和设备的连续监控和审核并不少，这一点对确保你能够快速检测并修正任何入侵至关重要。 安全得分、安全中心和 Microsoft 智能图高级分析等工具可向租户提供宝贵的信息，并链接大量威胁智能和安全数据，从而为您提供无与伦比的威胁保护和检测。


|建议 |E3 |E5 |
|---------|---------|---------|
|确保 **审核日志** 已打开。|![绿色复选标记](../media/green-check-mark.png)|![绿色复选标记](../media/green-check-mark.png)|
|**每周查看安全分数** -安全分数是访问公司安全状态并根据安全得分建议采取行动的中心位置。 建议每周执行此检查。|![绿色复选标记](../media/green-check-mark.png)|![绿色复选标记](../media/green-check-mark.png)|
|使用 **Office 365 ATP** 工具：<br>* 威胁调查和响应功能<br> * 自动化调查和响应 |         |![绿色复选标记](../media/green-check-mark.png)|
|使用 **Microsoft DEFENDER ATP**：<br> *    [终结点检测和响应](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> * 自动化调查和修正安全分数 <br>*    [高级搜寻](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![绿色复选标记](../media/green-check-mark.png)|
|使用 **Microsoft 云应用安全** 来检测各云应用程序之间的异常行为，以确定勒索软件、受损用户或恶意应用程序、分析高风险使用率并自动修正以限制组织的风险。|         |![绿色复选标记](../media/green-check-mark.png)|
|使用 **Microsoft Azure Sentinel** 或你的当前 SIEM 工具监视整个环境中的威胁。 |         |![绿色复选标记](../media/green-check-mark.png)|
|**部署[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) **以监视和保护针对本地 Active Directory 环境的威胁。   |         |![绿色复选标记](../media/green-check-mark.png) |
|使用 **Azure 安全中心** 监视跨混合和云工作负载的威胁。 Azure 安全中心包含一层免费的功能和标准功能层，这些功能根据资源时间或交易情况支付。|         |         |

下图说明了这些功能。
![持续监控和审核的建议功能](../media/m365-security-bdm-illustrations-monitoring-auditing.png)

推荐的最佳监视操作：
- **每周查看 Microsoft 安全分数** -安全分数是访问租户安全状态并根据顶级建议采取行动的中心位置。 建议每周执行此检查。 安全得分包括跨 Azure AD、Intune、云应用安全性和 Microsoft Defender 高级威胁防护以及 Office 365 的建议。 
- **每周查看有风险的登录名** —使用 Azure AD 管理中心查看每周有风险的登录项。 推荐的标识和设备访问规则集包括一个策略，用于强制对有风险的登录项进行密码更改。  
- **每周查看主要的恶意软件和 phished 用户** —使用 Office 高级威胁防护威胁资源管理器查看针对恶意软件和网络钓鱼的主要用户，并找出这些用户受到影响的根本原因。
