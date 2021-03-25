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
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a2f097cddce4afe2b3242ae34bbcfa242c3af601
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203844"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的安全附件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[适用于 Office 365 的 Microsoft Defender](defender-for-office-365.md)中的安全附件为已经过 Exchange Online Protection (EOP) 中的反恶意软件保护扫描的电子邮件附件提供了一[层额外保护](anti-malware-protection.md)。 具体而言，安全附件使用虚拟环境在将电子邮件中的附件传递到收件人之前检查 (过程称为触发) 。 

电子邮件的安全附件保护由安全附件策略控制。 没有默认的安全附件策略，因此若要保护安全附件，需要创建一个或多个安全 **附件策略**。 有关说明，请参阅在 [Defender for Office 365](set-up-safe-attachments-policies.md)中设置安全附件策略。

下表介绍了 Microsoft 365 和 Office 365 组织中包含 Microsoft Defender for Office 365 (的安全附件方案，换句话说，示例) 中永远不会出现缺少许可的问题。

****

|方案|结果|
|---|---|
|Pat 的 Microsoft 365 E5 组织未配置安全附件策略。|Pat 不受安全附件保护。 <p> 管理员必须至少创建一个安全附件策略，安全附件保护才能处于活动状态。 此外，如果 Pat 受安全附件保护，则策略的条件必须包括 Pat。|
|Lee 的组织具有仅适用于财务员工的安全附件策略。 Lee 是销售部门的成员。|Lee 不受安全附件保护。 <p> 财务员工受安全附件保护，但销售人员 (，) 员工则不受保护。|
|昨天，一位在都纳的组织的管理员创建了一个适用于所有员工的安全附件策略。 在今天较早的一天，用户收到一封包含附件的电子邮件。|百分之百受安全附件保护。 <p> 通常，新策略需要大约 30 分钟才能生效。|
|Chris 的组织具有针对组织中每个人的长期安全附件策略。 Chris 收到一封包含附件的电子邮件，然后将邮件转发给外部收件人。|Chis 受安全附件保护。 <p> 如果外部收件人的组织中也有安全附件策略，则转发的邮件将受这些策略限制。|
|

安全附件扫描发生在 Microsoft 365 数据所在的同一区域。 有关数据中心地理位置的信息，请参阅 [你的数据位于何处？](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> 以下功能位于安全与合规中心内安全附件策略&设置中。 但是，这些设置在全局启用或禁用，并且不需要安全附件策略：
>
> - [SharePoint、OneDrive](mdo-for-spo-odb-and-teams.md)和 Microsoft Teams 的安全附件。
>
> - [Microsoft 365 E5 中的安全文档](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>安全附件策略设置

本节介绍安全附件策略中的设置：

- **安全附件未知恶意软件响应**：此设置控制电子邮件中安全附件恶意软件扫描的操作。 下表介绍了可用选项：

  ****

  |选项|效果|在需要时使用：|
  |---|---|---|
  |**关闭**|安全附件不会扫描附件是否包含恶意软件。 EOP 中的反恶意软件保护 [仍可扫描邮件是否包含恶意软件](anti-malware-protection.md)。|关闭所选收件人的扫描。 <p> 防止在路由内部邮件时出现不必要的延迟。 <p> **建议大多数用户不要使用此选项。只应使用此选项关闭仅接收来自受信任发件人的邮件的收件人的安全附件扫描。**|
  |**监视器**|传递带有附件的邮件，然后跟踪检测到的恶意软件发生的情况。 <p> 由于安全附件扫描，安全邮件的传递可能会延迟。|查看组织中检测到的恶意软件的去向。|
  |**阻止**|阻止传递包含检测到的恶意软件附件的邮件。 <p> 邮件 [被隔离，](manage-quarantined-messages-and-files.md) 其中只有管理员 (最终用户才能) 、释放或删除邮件。 <p> 自动阻止邮件和附件的未来实例。 <p> 由于安全附件扫描，安全邮件的传递可能会延迟。|保护组织免受使用相同的恶意软件附件的重复攻击。 <p> 这是默认值，以及 Standard 和 Strict 预设安全策略 [中的建议值](preset-security-policies.md)。|
  |**Replace**|删除检测到的恶意软件附件。 <p> 通知收件人附件已删除。 <p>  邮件 [被隔离，](manage-quarantined-messages-and-files.md) 其中只有管理员 (最终用户才能) 、释放或删除邮件。 <p> 由于安全附件扫描，安全邮件的传递可能会延迟。|提高收件人的可见性，即附件因检测到的恶意软件而被删除。|
  |**动态传递**|立即传递邮件，但使用占位符替换附件，直到安全附件扫描完成。 <p> 有关详细信息，请参阅本文 [稍后介绍的动态](#dynamic-delivery-in-safe-attachments-policies) 传递安全附件策略部分。|避免邮件延迟，同时保护收件人免受恶意文件的攻击。 <p> 允许收件人在扫描进行时以安全模式预览附件。|
  |

- 检测时重定向附件 **：启用** 重定向并将附件发送到以下电子邮件地址：对于阻止、监视或 **替换** 操作，将包含恶意软件附件的邮件发送到指定的内部或外部电子邮件地址进行分析和调查。

  对于"标准"和"严格"策略设置，建议启用重定向。 有关详细信息，请参阅安全 [附件设置](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。

- **如果附件的恶意软件** 扫描出现次数或出现错误，则应用上述选择：即使安全附件扫描无法完成，对邮件执行安全附件未知恶意软件响应指定的操作。 如果选择了"启用重定向"，请 **始终选择此选项**。 否则，邮件可能会丢失。

- **收件人** 筛选器：需要指定确定策略适用的收件人条件和例外。 可以将这些属性用于条件和例外：

  - **收件人为**
  - **收件人域为**
  - **收件人为以下组的成员**

  一次只能使用一个条件或例外，但条件或例外可以包含多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

- **优先级**：如果创建多个策略，可以指定策略的应用顺序。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

  有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>安全附件策略中的动态传递

> [!NOTE]
> 动态传递仅适用于 Exchange Online 邮箱。

安全附件策略中的动态传递操作旨在消除可能由安全附件扫描导致的任何电子邮件传递延迟。 电子邮件正文通过每个附件的占位符传递给收件人。 占位符将一直保留，直到发现附件是安全的，然后附件可以打开或下载。

如果发现附件是恶意附件，则隔离邮件。 只有管理员 (最终用户) ，才能查看、释放或删除由安全附件扫描隔离的邮件。 有关详细信息，请参阅 [以管理员角色管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)。

大多数 PDF 和 Office 文档可以在安全模式下预览，同时进行安全附件扫描。 如果附件与动态传递预览程序不兼容，收件人将看到附件的占位符，直到安全附件扫描完成。

如果您使用的是移动设备，并且 PDF 未在移动设备上的动态传递预览器中呈现，请尝试使用移动浏览器在 Outlook 网页版 (以前称为 Outlook Web App) 中打开邮件。

下面是动态传递和转发邮件的一些注意事项：

- 如果转发的收件人受使用"动态传递"选项的安全附件策略保护，则收件人将看到占位符，能够预览兼容文件。

- 如果转发的收件人不受安全附件策略保护，则传递的邮件和附件将没有任何安全附件扫描或附件占位符。

在某些情况下，动态传递无法替换邮件中的附件。 这些情况包括：

- 公用文件夹中的邮件。

- 使用自定义规则从用户邮箱路由出然后返回到用户邮箱的邮件。

- 自动或手动 (移动的邮件) 云邮箱中移动到其他位置，包括存档文件夹。

- 已删除邮件。

- 用户的邮箱搜索文件夹的状态为错误。

- 启用了 Exclaimer 的 Exchange Online 组织。 若要解决此问题，请参阅[KB4014438。](https://support.microsoft.com/help/4014438)

- [S/MIME) ](s-mime-for-message-signing-and-encryption.md) 加密邮件。

- 在安全附件策略中配置了动态传递操作，但收件人不支持动态传递 (例如，收件人是本地 Exchange 组织中邮箱) 。 但是[，Microsoft Defender for Office 365](set-up-safe-links-policies.md)中的安全链接能够扫描包含 URL (的 Office 文件附件，[](configure-global-settings-for-safe-links.md)具体取决于安全链接的全局设置如何) 。

## <a name="submitting-files-for-malware-analysis"></a>提交文件进行恶意软件分析

- 如果收到要发送给 Microsoft 进行分析的文件，请参阅将 [恶意软件和非](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)恶意软件提交给 Microsoft 进行分析。

- 如果收到包含 (附件或没有附件) 要提交给 Microsoft 进行分析的电子邮件，请参阅向 Microsoft 报告邮件 [和文件](report-junk-email-messages-to-microsoft.md)。
