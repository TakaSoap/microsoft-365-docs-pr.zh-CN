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
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 作为管理员和邮件发件人，可以撤销某些使用 Office 365 高级邮件加密加密的电子邮件。
ms.openlocfilehash: 67582917dd483f6090f5cd369af8faf6cf8a4ea8
ms.sourcegitcommit: b88ffaf3409e02a9847f030f8468f96d36efa398
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "50105137"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>撤销由高级邮件加密加密的电子邮件

电子邮件吊销作为 Office 365 高级邮件加密的一部分提供。 Office 365 高级邮件加密包含在 [Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/home)企业版 E5、Office 365 E5、Microsoft 365 E5 (非营利组织员工定价) 、Office 365 企业版 E5 (非营利组织版员工定价) 和 Office 365 教育版 A5 中。 如果组织具有不包括 Office 365 高级邮件加密的订阅， 可以使用 Microsoft 365 E3 的 Microsoft 365 E5 合规性 SKU 加载项、Microsoft 365 E3 (非盈利性员工定价) 或 Microsoft 365 E3、Microsoft 365 E3 (非营利组织版员工定价) 或 Office 365 SKU 的 Office 365 高级合规性 SKU 加载项购买。

本文是有关 [Office 365](ome.md)邮件加密的较大系列文章的一部分。

如果使用 Office 365 高级邮件加密对邮件进行加密，并且你是 Microsoft 365 管理员，或者你是邮件的发件人，则在某些情况下可以撤销邮件。 管理员使用 PowerShell 撤销邮件。 作为发件人，您可以撤销直接从 Outlook 网页邮件发送的邮件。 本文介绍可能吊销的情况以及如何进行吊销。
  
## <a name="encrypted-emails-that-you-can-revoke"></a>可以撤销的加密电子邮件

如果收件人收到基于链接的品牌加密电子邮件，则管理员和邮件发件人可以吊销加密电子邮件。 如果收件人在受支持的 Outlook 客户端中收到了本机内联体验，则不能撤销邮件。

收件人是否收到基于链接的体验或内联体验取决于收件人标识类型：Office 365 和 Microsoft 帐户收件人 (例如，outlook.com 用户) 在受支持的 Outlook 客户端中获得内联体验。 所有其他收件人类型（如 Gmail 和 Yahoo 收件人）都获得基于链接的体验。

管理员和邮件发件人可以撤销使用直接从 Outlook 网页应用加密加密的邮件。 例如，使用"仅加密"选项加密的邮件。

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="显示 Outlook 网页中的&quot;仅加密&quot;选项的屏幕截图。":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>已吊销加密电子邮件的收件人体验

撤销电子邮件后，收件人通过 Office 365 邮件加密门户访问加密电子邮件时收到错误："发件人已吊销邮件"。

![显示已吊销的加密电子邮件的屏幕截图。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>如何撤销已发送的加密邮件

您可以撤消发送给使用社交帐户（如用户或gmail.com）的单个yahoo.com。 换句话说，您可以撤消发送给接收基于链接的体验的单个收件人的电子邮件。

无法撤消发送给使用 Office 365 或 Microsoft 365 工作或学校帐户的收件人或使用 Microsoft 帐户的用户（例如，outlook.com帐户）的邮件。 

若要撤销已发送的加密邮件，请完成这些步骤

1. 在 Outlook 网页 **中的"已** 发送"文件夹中，浏览到要撤销的邮件。

   如果邮件是可撤销的，你将在邮件顶部看到"删除外部访问"链接。

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Screenshot showing encrypted mail that you want to revoke in Outlook on the web.":::

2. 单击 **"删除外部访问** "以撤销邮件。

   该消息显示其状态已被吊销。

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Screenshot showing revoked encrypted message in Outlook on the web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>如何以管理员角色撤销加密邮件

Microsoft 365 管理员按照以下常规步骤撤销符合条件的加密电子邮件：

- 获取电子邮件的邮件 ID。
- 验证您是否可以撤销邮件。
- 撤销邮件。

### <a name="step-1-obtain-the-message-id-of-the-email"></a>步骤 1. 获取电子邮件的邮件 ID

在可以撤销加密邮件之前，请收集邮件的邮件 ID。 MessageId 通常采用以下格式：

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

有多种方法可查找要撤销的电子邮件的邮件 ID。 本节介绍几个选项，但您可以使用任何提供 ID 的方法。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>使用安全合规中心中的邮件跟踪标识要撤销的电子邮件 &amp; 的邮件 ID

1. 使用安全与合规中心中的"新建邮件跟踪"按发件人& [电子邮件](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)。

2. 找到电子邮件后，选择它可显示"邮件跟踪 **详细信息"** 窗格。 展开 **"详细信息** "以查找邮件 ID。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>使用安全合规中心中的 Office 邮件加密报告标识要撤销的电子邮件 &amp; 的邮件 ID

1. 在安全 &amp; 合规中心，导航到邮件 **加密报告**。 有关此报告的信息，请参阅 [安全合规中心查看 &amp; 电子邮件安全报告](../security/office-365-security/view-email-security-reports.md)。

2. 选择 **"查看详细信息** "表并标识要撤销的邮件。

3. 双击邮件以查看包含邮件 ID 的详细信息。

### <a name="step-2-verify-that-the-mail-is-revocable"></a>步骤 2. 验证邮件是否可撤销

若要验证是否可以吊销邮件，请检查安全合规中心详细信息表中的"加密"报告中是否显示"吊销状态" &amp; 字段。

若要验证是否可以通过使用密码来撤销特定Windows PowerShell，请完成这些步骤。

1. 使用组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到 Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。

2. 运行 Get-OMEMessageStatus cmdlet，如下所示：

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   此命令返回邮件的主题以及邮件是否可撤销。 例如，

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>步骤 3. 撤销邮件

一旦知道要撤销的电子邮件的邮件 ID，并且已验证该邮件是可撤销的，可以使用安全合规中心或安全中心 &amp; Windows PowerShell。

使用安全合规中心 &amp; 撤销邮件

1. 使用组织中具有全局管理员权限的工作或学校帐户连接到安全与合规&中心。

2. 在加密 **报告中**，在邮件的详细信息 **表中，** 选择"**撤销邮件"。**

若要使用 Windows PowerShell 撤销Set-OMEMessageRevocation cmdlet。

1. 使用在组织中具有全局管理员权限的工作或学校帐户，连接到 Exchange [Online PowerShell。](https://aka.ms/exopowershell)

2. 运行 Set-OMEMessageRevocation cmdlet，如下所示：

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. 若要检查电子邮件是否已吊销，请运行 Get-OMEMessageStatus cmdlet，如下所示：

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    如果吊销成功，该 cmdlet 将返回以下结果：  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>有关 Office 365 高级邮件加密详细信息

- [Office 365 高级邮件加密](ome-advanced-message-encryption.md)

- [Office 365 高级邮件加密 - 电子邮件过期](ome-advanced-expiration.md)

- [邮件策略和合规性服务说明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
