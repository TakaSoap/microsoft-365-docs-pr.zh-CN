---
title: 撤销由高级邮件加密加密的电子邮件
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 03/04/2022
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 作为管理员和邮件发件人，可以撤消使用Office 365 高级邮件加密加密的某些电子邮件。
ms.openlocfilehash: 313cbe990e322285fc81465329fa5e19b52e2701
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64759382"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>撤销由高级邮件加密加密的电子邮件

电子邮件吊销作为Office 365 高级邮件加密的一部分提供。 Office 365 高级邮件加密 Microsoft 365 企业版 [E5、Office 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、Microsoft 365 E5 (非营利性员工定价) 、Office 365 企业版 E5 (非营利性员工定价) 以及Office 365 教育版 A5。 如果你的组织有一个不包括Office 365 高级邮件加密的订阅，则可以使用适用于Microsoft 365 E3的Microsoft 365 E5 合规 SKU 加载项、Microsoft 365 E3 (非营利性员工定价) 或Office 365 高级合规版适用于Microsoft 365 E3、Microsoft 365 E3 (非营利性员工定价) 或Office 365 SKU 的 SKU 加载项。

本文是一系列有关[Office 365消息加密](ome.md)的文章的一部分。

如果消息是使用Office 365 高级邮件加密加密的，而你是Microsoft 365管理员，或者你是邮件的发件人，则可以在特定条件下撤销该消息。 管理员使用 PowerShell 撤销消息。 作为发件人，你将撤销直接从Outlook 网页版发送的消息。 本文介绍可能撤销的情况以及如何执行此操作。

> [!NOTE]
> 若要保证能够跟踪和撤销 OME 消息，必须添加自定义品牌模板。 请参阅 [将组织的品牌添加到加密的消息](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="encrypted-emails-that-you-can-revoke"></a>可以撤消的加密电子邮件

如果收件人收到基于链接的品牌加密电子邮件，管理员和邮件发件人可以撤销加密的电子邮件。 如果收件人在受支持的Outlook客户端中收到了本机内联体验，则无法撤消该消息。

收件人是接收基于链接的体验还是内联体验取决于收件人标识类型：例如， (Office 365和 Microsoft 帐户收件人，outlook.com 用户) 在受支持的Outlook客户端中获得内联体验。 所有其他收件人类型（如 Gmail 和 Yahoo 收件人）都可获得基于链接的体验。

管理员和消息发件人可以使用直接从Outlook 网页版应用的加密来撤消加密的消息。 例如，使用“仅加密”选项加密的消息。

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="显示Outlook 网页版中“仅加密”选项的屏幕截图。":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>已撤销的加密电子邮件的收件人体验

撤销电子邮件后，收件人通过Office 365邮件加密门户访问加密电子邮件时收到错误：“发件人已撤销邮件”。

![显示已撤销的加密电子邮件的屏幕截图。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>如何撤销已发送的加密消息

可以撤销发送给使用社交帐户（如 gmail.com 或 yahoo.com）的单个收件人的邮件。 换句话说，可以撤消发送给单个接收基于链接体验的收件人的电子邮件。

您无法撤消发送给使用工作或学校帐户的收件人、Office 365、Microsoft 365或使用 Microsoft 帐户的用户（例如 outlook.com 帐户）的邮件。 

若要撤销已发送的加密消息，请完成以下步骤

1. 在Outlook 网页版中，在 **“已发送**”文件夹中，浏览到要撤销的消息。

   如果邮件可转用，则会在邮件顶部看到“删除外部访问权限”链接。

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="显示要在Outlook 网页版中撤消的加密邮件的屏幕截图。":::

2. 单击 **“删除外部访问权限** ”以撤销邮件。

   消息显示其状态已撤销。

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="显示Outlook 网页版中已撤销的加密消息的屏幕截图。":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>如何撤消以管理员身份加密的消息

Microsoft 365管理员按照以下常规步骤撤销符合条件的加密电子邮件：

- 获取电子邮件的邮件 ID。
- 验证是否可以撤消消息。
- 撤销邮件。

### <a name="step-1-obtain-the-message-id-of-the-email"></a>步骤 1. 获取电子邮件的邮件 ID

在撤销加密邮件之前，请收集邮件的消息 ID。 MessageId 通常采用以下格式：

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

可通过多种方式查找要撤销的电子邮件的邮件 ID。 本部分介绍几个选项，但可以使用任何提供 ID 的方法。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>若要通过在安全 &amp; 合规中心使用消息跟踪来标识要撤销的电子邮件的邮件 ID

1. 使用 [安全&合规中心中的新邮件跟踪](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)，通过发件人或收件人搜索电子邮件。

2. 找到电子邮件后，选择它以显示 **“邮件跟踪详细信息** ”窗格。 展开 **详细信息** 以查找消息 ID。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>若要通过在安全&amp;合规中心使用Office消息加密报告来标识要撤销的电子邮件的邮件 ID

1. 在安全 &amp; 合规中心，导航到 **消息加密报表**。 有关此报告的信息，请参 [阅安全 &amp; 合规中心中的电子邮件安全报告](../security/office-365-security/view-email-security-reports.md)。

2. 选择 **“视图详细信息** ”表并标识要撤销的消息。

3. 双击邮件以查看包含消息 ID 的详细信息。

### <a name="step-2-verify-that-the-mail-is-revocable"></a>步骤 2. 验证邮件是否可转用

若要验证是否可以撤消消息，请检查“加密”报表中“安全&amp;合规性中心”的 **“详细信息**”表中是否显示“吊销状态”字段。

若要验证是否可以使用Windows PowerShell撤销特定的电子邮件，请完成以下步骤。

1. 使用组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 按如下所示运行Get-OMEMessageStatus cmdlet：

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   此命令返回消息的主题以及消息是否可恢复。 例如，

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>步骤 3. 撤销邮件

知道要吊销的电子邮件的邮件 ID，并且验证邮件是否可撤销后，可以使用安全&amp;合规中心或Windows PowerShell撤消电子邮件。

使用安全 &amp; 合规中心撤消消息

1. 使用组织中具有全局管理员权限的工作或学校帐户，连接到安全&合规中心。

2. 在加密 **报表** 中，在邮件的 **“详细信息** ”表中，选择 **“撤销”消息**。

若要使用Windows PowerShell撤消电子邮件，请使用Set-OMEMessageRevocation cmdlet。

1. 使用组织中具有全局管理员权限的工作或学校帐户[，连接Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 按如下所示运行Set-OMEMessageRevocation cmdlet：

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. 若要检查电子邮件是否被撤销，请按如下所示运行Get-OMEMessageStatus cmdlet：

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    如果吊销成功，cmdlet 将返回以下结果：  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>有关Office 365 高级邮件加密的详细信息

- [Office 365 高级邮件加密](ome-advanced-message-encryption.md)

- [Office 365 高级邮件加密 - 电子邮件过期](ome-advanced-expiration.md)

- [消息策略和合规性服务说明](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)