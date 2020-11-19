---
title: 安全附件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- seo-marvel-apr2020
description: 管理员可以了解 Microsoft Defender for Office 365 中的安全附件功能。
ms.openlocfilehash: da3949a4520c52c7f5685efd109f8c976305ea06
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357198"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的安全附件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender For Office 365](office-365-atp.md)中的安全附件为已通过[Exchange ONLINE protection (EOP) 中的反恶意软件保护](anti-malware-protection.md)扫描过的电子邮件附件提供了额外的保护层。 具体来说，安全附件使用虚拟环境来检查电子邮件中的附件，然后再传递给收件人 (称为 _沙箱_) 的过程。

电子邮件的安全附件保护由安全附件策略控制。 没有默认安全附件策略，因此， **若要获得安全附件的保护，您需要创建一个或多个安全附件策略**。 有关说明，请参阅 [在 Defender For Office 365 中设置安全附件策略](set-up-atp-safe-attachments-policies.md)。

下表介绍了 Microsoft 365 和 Office 365 组织中的安全附件的方案，其中包括 Microsoft Defender for Office 365 (换句话说，缺乏许可不是示例) 中的一个问题。

****

|应用场景|结果|
|---|---|
|Pat 的 Microsoft 365 E5 组织没有配置安全附件策略。|Pat 不受安全附件保护。 <p> 管理员必须至少创建一个安全附件策略，才能使安全附件保护处于活动状态。 此外，如果安全附件保护了 Pat，则策略的条件必须包括 Pat。|
|先生/她的组织有一个仅适用于财务员工的安全附件策略。 "工作表示" 是销售部门的成员。|先生不受安全附件保护。 <p> 财务员工受安全附件保护，但销售员工 (和其他员工) 不受保护。|
|昨天，Jean 组织中的管理员创建了一个适用于所有员工的安全附件策略。 在今天的早期，Jean 收到包含附件的电子邮件。|Jean 受安全附件保护。 <p> 通常，新策略大约需要30分钟的时间才能生效。|
|丽丽的组织为组织中的每个人提供了长期安全附件策略。 Chris 收到包含附件的电子邮件，然后将邮件转发给外部收件人。|Chis 受安全附件保护。 <p> 如果外部收件人在其组织中也有安全附件策略，则转发的邮件将服从这些策略。|
|

安全附件扫描发生在 Microsoft 365 数据所在的同一个区域中。 有关数据中心地理位置的详细信息，请参阅 [您的数据位于何处？](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> 全局设置中的以下功能位于安全 & 合规中心中的安全附件策略中，但这些设置在全局范围内启用或禁用，并且不需要安全附件策略：
>
> - [SharePoint、OneDrive 和 Microsoft 团队的 ATP](atp-for-spo-odb-and-teams.md)。
>
> - [Microsoft 365 E5 中的安全文档](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>安全附件策略设置

本节介绍安全附件策略中的设置：

- **安全附件未知的恶意软件响应**：此设置控制安全附件在电子邮件中进行恶意扫描的操作。 下表中介绍了可用选项：

  ****

  |选项|效果|在需要执行以下操作时使用：|
  |---|---|---|
  |**停**|不会通过安全附件扫描附件中的恶意软件。 在 EOP 中，邮件仍通过 [反恶意软件保护](anti-malware-protection.md)进行病毒扫描。|为选定的收件人关闭 "扫描"。 <p> 避免路由内部邮件中不必要的延迟。 <p> **对于大多数用户，不建议使用此选项。仅应使用此选项来对仅接收来自受信任发件人的邮件的收件人执行安全附件扫描。**|
  |**监视器**|传递包含附件的邮件，然后跟踪检测到的恶意软件所发生的情况。 <p> 安全邮件的传递可能由于安全附件扫描而延迟。|查看在您的组织中检测到的恶意软件的位置。|
  |**阻止**|阻止传递包含检测到的恶意软件附件的邮件。 <p> 仅在管理员 (不是最终用户) 可以查看、释放或删除邮件的情况下 [隔离](manage-quarantined-messages-and-files.md) 邮件。 <p> 自动阻止后续的邮件和附件实例。 <p> 安全邮件的传递可能由于安全附件扫描而延迟。|使用相同的恶意软件附件保护您的组织免受重复攻击。 <p> 这是默认值，以及标准和严格的 [预设安全策略](preset-security-policies.md)中建议的值。|
  |**Replace**|删除检测到的恶意软件附件。 <p> 通知收件人附件已被删除。 <p>  仅在管理员 (不是最终用户) 可以查看、释放或删除邮件的情况下 [隔离](manage-quarantined-messages-and-files.md) 邮件。 <p> 安全邮件的传递可能由于安全附件扫描而延迟。|对收件人的可见性提高由于检测到的恶意软件而导致附件被删除。|
  |**动态传递**|立即传递邮件，但将附件替换为占位符，直到安全附件扫描完成。 <p> 有关详细信息，请参阅本主题后面的 " [安全附件策略中的动态传递](#dynamic-delivery-in-safe-attachments-policies) " 一节。|避免邮件延迟，同时防止收件人受到恶意文件的攻击。 <p> 使收件人能够在扫描发生时以安全模式预览附件。|
  |

- **在检测时重定向附件：启用重定向** ，并 **将附件发送到以下电子邮件地址**：对于 **阻止**、 **监视** 或 **替换** 操作，请将包含恶意软件附件的邮件发送到指定的内部或外部电子邮件地址进行分析和调查。

  标准策略设置和严格策略设置的建议是启用重定向。 有关详细信息，请参阅 [安全附件设置](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。

- **如果恶意软件扫描附件超时或发生错误，则应用上述选择**：安全附件指定的操作对邮件执行 **未知恶意软件响应** ，即使安全附件扫描无法完成也是如此。 如果选择 " **启用重定向**"，请始终选择此选项。 否则，邮件可能会丢失。

- **收件人筛选器**：需要指定用于确定策略适用于的收件人条件和例外。 您可以将这些属性用于条件和例外：

  - **收件人为**
  - **收件人域为**
  - **收件人为以下组的成员**

  只能使用条件或例外一次，但条件或例外可以包含多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

- **优先级**：如果创建多个策略，则可以指定它们的应用顺序。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

  有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>安全附件策略中的动态传递

> [!NOTE]
> 动态传递仅适用于 Exchange Online 邮箱。

安全附件策略中的动态传递操作旨在消除安全附件扫描可能导致的任何电子邮件传递延迟。 电子邮件的正文将传递给收件人，每个附件占一个占位符。 占位符将一直保持到找到安全的附件，然后附件才可用于打开或下载。

如果发现附件是恶意的，则会隔离邮件。 仅管理员 (不是最终用户) 可以查看、释放或删除通过安全附件扫描隔离的邮件。 有关详细信息，请参阅 [以管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)。

大多数 Pdf 和 Office 文档可以在安全模式下进行预览，而安全附件扫描正在进行。 如果附件与动态传递预览器不兼容，则在安全附件扫描完成之前，收件人将看到附件的占位符。

如果您使用的是移动设备，并且 Pdf 不在移动设备上的动态传递预览器中呈现，请尝试使用移动浏览器在 web 上打开 Outlook Web App)  (以前称为 Outlook Web App 的邮件。

以下是有关动态传递和转发邮件的一些注意事项：

- 如果转发的收件人受使用动态传递选项的安全附件策略保护，则收件人将看到该占位符，并能够预览兼容文件。

- 如果转发的收件人不受安全附件策略保护，则会在不使用任何安全附件扫描或附件占位符的情况下传递邮件和附件。

在某些情况下，动态传递无法替换邮件中的附件。 这些情况包括：

- 公用文件夹中的邮件。

- 使用自定义规则从用户的邮箱中路由的邮件，然后再返回到该用户的邮箱中。

- 将从云邮箱)  (自动或手动移动到其他位置（包括存档文件夹）的邮件。

- 已删除邮件。

- 用户的邮箱搜索文件夹处于错误状态。

- 启用 Exclaimer 的 Exchange Online 组织。 若要解决此问题，请参阅 [KB4014438](https://support.microsoft.com/help/4014438)。

- [S/MIME) ](s-mime-for-message-signing-and-encryption.md) 加密邮件。

- 您在安全附件策略中配置了动态传递操作，但收件人不支持动态传递 (例如，收件人是本地 Exchange 组织中的邮箱) 。 但是， [Microsoft Defender For Office 365 中的安全链接](set-up-atp-safe-links-policies.md) 可以扫描包含 Url 的 office 文件附件 (具体取决于 [安全链接的全局设置](configure-global-settings-for-safe-links.md) 是如何) 配置的。

## <a name="submitting-files-for-malware-analysis"></a>提交文件以进行恶意软件分析

- 如果您收到要发送给 Microsoft 进行分析的文件，请参阅 [将恶意软件和非恶意软件提交给 microsoft 进行分析](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)。

- 如果您收到一封电子邮件 (要提交给 Microsoft 进行分析的附件) ，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。
