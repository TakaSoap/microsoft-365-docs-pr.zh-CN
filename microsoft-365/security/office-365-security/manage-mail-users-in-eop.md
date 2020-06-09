---
title: 在独立 EOP 中管理邮件用户
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 了解如何管理 Exchange Online Protection （EOP）中的邮件用户，包括使用目录同步、EAC 和 PowerShell 管理用户。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d82170499bcfa6465164ca2644eea43c2558ad18
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616830"
---
# <a name="manage-mail-users-in-standalone-eop"></a>在独立 EOP 中管理邮件用户

在独立的 Exchange Online Protection （EOP）组织中，如果组织没有 Exchange Online 邮箱，则邮件用户是用户帐户的基本类型。 邮件用户在独立 EOP 组织中具有帐户凭据，并且可以访问资源（已分配权限）。 邮件用户的电子邮件地址是外部的（例如，在您的本地电子邮件环境中）。

> [!NOTE]
> 当您创建邮件用户时，相应的用户帐户在 Microsoft 365 管理中心中可用。 在 Microsoft 365 管理中心创建用户帐户时，不能使用该帐户来创建邮件用户。

在独立 EOP 中创建和管理邮件用户的建议方法是使用目录同步，如本主题后面的[使用目录同步管理邮件用户](#use-directory-synchronization-to-manage-mail-users)一节中所述。

对于具有少量用户的独立 EOP 组织，可以在 Exchange 管理中心（EAC）或独立 EOP PowerShell 中添加和管理邮件用户，如本主题中所述。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要打开 Exchange 管理中心（EAC），请参阅[独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要连接到独立的 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 当您在 EOP PowerShell 中创建邮件用户时，您可能会遇到限制。 此外，EOP PowerShell cmdlet 使用一种批处理方法，该方法会导致几分钟的传播延迟，然后才会显示命令的结果。

- 必须先分配有权限，然后才能执行这些过程。 具体来说，您需要 "邮件收件人创建（创建）" 和 "邮件收件人（修改）" 角色，默认情况下这些角色分配给 OrganizationManagement （全局管理员）和 RecipientManagement 角色组。 有关详细信息，请参阅[独立 EOP 中的权限](feature-permissions-in-eop.md)和[使用 EAC 修改角色组中的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- 有关可能适用于本主题中的过程的键盘快捷方式的信息，请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 是否有任何疑问？ 在 Exchange 论坛中寻求帮助。 访问[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)论坛。

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>使用 Exchange 管理中心管理邮件用户

### <a name="use-the-eac-to-create-mail-users"></a>使用 EAC 创建邮件用户

1. 在 EAC 中，转到 "**收件人**" " \> **联系人**"

2. 单击 "**新建** ![ 新图标" ](../../media/ITPro-EAC-AddIcon.png) 。 在打开的 "**新建邮件用户**" 页上，配置以下设置。 使用标记为的设置 <sup>\*</sup> 是必需的。

   - **名**：使用此框可以键入用户的名。

   - **缩写**：人员的中间名首字母。

   - **姓**：使用此框可以键入用户的姓。

   - <sup>\*</sup>**显示名称**：默认情况下，此框显示 "**名字**"、"**缩写**" 和 "**姓氏**" 框中的值。 您可以接受此值，也可以对其进行更改。 该值应是唯一的，并且最大长度为64个字符。

   - <sup>\*</sup>**别名**：为用户输入一个唯一的别名，最长为64个字符

   - **外部电子邮件地址**：输入用户的电子邮件地址。 域应位于基于云的组织外部。

   - <sup>\*</sup>**用户 ID**：输入此人将用于登录服务的帐户。 用户 ID 由左侧（@）符号（@）和右侧的域的用户名组成。

   - <sup>\*</sup>"**新密码**" 和 " <sup>\*</sup> **确认密码**"：输入并重新输入帐户密码。 验证密码是否符合组织的密码长度、复杂性和历史要求。

3. 完成后，请单击“保存”**** 来创建邮件用户。

### <a name="use-the-eac-to-modify-mail-users"></a>使用 EAC 修改邮件用户

1. 在 EAC 中，转到 "**收件人**" " \> **联系人**"。

2. 选择要修改的邮件用户，然后单击 "**编辑** ![ 编辑图标" ](../../media/ITPro-EAC-AddIcon.png) 。

3. 在打开的 "邮件用户属性" 页上，单击下列选项卡之一以查看或更改属性。

   完成时，请单击“保存”****。

#### <a name="general"></a>概要

使用 "**常规**" 选项卡可以查看或更改有关邮件用户的基本信息。

- **名**

- **缩写**

- **姓**

- **显示名称**：此名称显示在组织的通讯簿中、电子邮件的 "To：" 和 "发件人：" 行和 EAC 中的联系人列表中。 此姓名不能在显示姓名之前或之后包含空格。

- **用户 ID**：这是 Microsoft 365 中的用户帐户。 您不能在此处修改此值。

#### <a name="contact-information"></a>联系人信息

使用 "**联系人信息**" 选项卡查看或更改用户的联系信息。 该页上的信息显示在通讯簿中。

- **Street**
- **市/县**
- **省/市/自治区**
- **邮政编码**
- **国家/地区**
- **工作电话**
- **移动电话**
- **传真**
- **更多选项**

  - **Office**
  - **住宅电话**
  - **网页**
  - **备注**

#### <a name="organization"></a>组织

使用 "**组织**" 选项卡可以记录有关组织中用户角色的详细信息。

- **Title**
- **Department**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>使用 EAC 删除邮件用户

1. 在 EAC 中，转到 "**收件人**" " \> **联系人**"。

2. 选择要删除的邮件用户，然后单击 "**删除** ![ 删除图标" ](../../media/ITPro-EAC-RemoveIcon.gif) 。

## <a name="use-powershell-to-manage-mail-users"></a>使用 PowerShell 管理邮件用户

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>使用独立 EOP PowerShell 查看邮件用户

若要返回独立 EOP PowerShell 中所有邮件用户的摘要列表，请运行以下命令：

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

若要查看有关特定邮件用户的详细信息，请将 \<MailUserIdentity\> 其替换为邮件用户的名称、别名或帐户名称，并运行以下命令：

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

有关语法和参数的详细信息，请参阅 "[获取-收件人](https://docs.microsoft.com/powershell/module/exchange/get-recipient)" 和 "[获取用户](https://docs.microsoft.com/powershell/module/exchange/get-user)"。

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>使用独立的 EOP PowerShell 创建邮件用户

若要在独立 EOP PowerShell 中创建邮件用户，请使用以下语法：

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**注意**：

- _Name_参数是必需的，最大长度为64个字符，并且必须是唯一的。 如果您不使用 _DisplayName_ 参数，_Name_ 参数的值可用于显示名称。
- 如果不使用_alias_参数，则_MicrosoftOnlneServicesID_参数的左侧将用于别名。
- 如果不使用_ExternalEmailAddress_参数，则_MicrosoftOnlineServicesID_值将用于外部电子邮件地址。

本示例将创建具有下列设置的邮件用户：

- 名称为 JeffreyZeng，显示名称为 Jeffrey Zeng。
- 名是 Jeffrey，姓是 Zeng。
- 别名是 jeffreyz。
- 外部电子邮件地址是 jzeng@tailspintoys.com。
- 帐户名称为 jeffreyz@contoso.onmicrosoft.com。
- 密码为 Pa$$word1。

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

有关语法和参数的详细信息，请参阅[new-eopmailuser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)。

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>使用独立 EOP PowerShell 修改邮件用户

若要修改独立 EOP PowerShell 中的现有邮件用户，请使用以下语法：

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Textg>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

此示例将设置 Pilar Pinilla 的外部电子邮件地址。

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

此示例将所有邮件用户的"公司"属性设置为 Contoso。

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

有关语法和参数的详细信息，请参阅[new-eopmailuser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)。

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>使用独立 EOP PowerShell 删除邮件用户

若要删除独立 EOP PowerShell 中的邮件用户，请将 \<MailUserIdentity\> 其替换为邮件用户的名称、别名或帐户名称，然后运行以下命令：

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

本示例删除 Jeffrey Zeng 的邮件用户。

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

有关语法和参数的详细信息，请参阅[new-eopmailuser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证您是否已成功创建、修改或删除了独立 EOP 中的邮件用户，请使用以下任一过程：

- 在 EAC 中，转到 "**收件人**" " \> **联系人**"。 验证是否列出了邮件用户（或未列出）。 选择邮件用户并查看详细信息窗格中的信息，或单击 "**编辑** ![ 编辑图标 ](../../media/ITPro-EAC-AddIcon.png) " 以查看设置。

- 在独立 EOP PowerShell 中，运行以下命令来验证是否列出了邮件用户（或未列出）：

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- 将替换 \<MailUserIdentity\> 为邮件用户的名称、别名或帐户名称，然后运行以下命令来验证设置：

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>使用目录同步管理邮件用户

在独立 EOP 中，目录同步适用于具有本地 Active Directory 的客户。 你可以将这些帐户同步到 Azure Active Directory （Azure AD），其中，帐户的副本存储在云中。 将现有用户帐户同步到 Azure Active Directory 时，可以在 Exchange 管理中心（EAC）或独立 EOP PowerShell 的 "**收件人**" 窗格中查看这些用户。

**注意**：

- 如果使用目录同步来管理收件人，您仍可以在 Microsoft 365 管理中心中添加和管理用户，但不会将其与本地 Active Directory 同步。 这是因为目录同步只能将来自本地 Active Directory 的收件人同步到云。

- 建议将目录同步用于以下功能：

  - **Outlook 安全发件人列表和阻止的发件人列表**：当同步到服务时，这些列表将优先于服务中的垃圾邮件筛选。 这使用户可以管理其自己的安全发件人列表和阻止的发件人列表和单个发件人和域条目。 有关详细信息，请参阅[配置 Exchange Online 邮箱上的垃圾邮件设置](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes)。

  - **基于目录的边缘阻止（DBEB）**：有关 DBEB 的详细信息，请参阅[使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。

  - **最终用户对隔离的访问权限**：若要访问其隔离邮件，收件人必须在服务中具有有效的用户 ID 和密码。 有关隔离的详细信息，请参阅[以用户的方式查找和释放隔离的邮件](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user)。

  - **邮件流规则（也称为传输规则）**：使用目录同步时，会自动将现有的 Active directory 用户和组上载到云，然后您可以创建针对特定用户和/或组的邮件流规则，而无需手动将其添加到服务中。 请注意， [动态通讯组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups)无法通过目录同步进行同步。

获取必要的权限并准备目录同步，如["使用 Azure Active directory 的混合标识是什么？"](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)中所述。

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>将目录与 Azure Active Directory Connect （AAD Connect）同步

1. 按照 Azure AD Connect 同步中所述激活目录同步[：了解和自定义同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。

2. 按照[AZURE AD connect 的先决条件](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)中所述，安装和配置内部部署计算机以运行 AAD Connect。

3. [选择要用于 AZURE AD Connect 的安装类型](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)：

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [自定义](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [传递身份验证](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> 当您完成 Azure Active Directory 同步工具配置向导时，将在 Active Directory 林中创建**MSOL_AD_SYNC**帐户。 此帐户用于读取和同步您的本地 Active Directory 信息。 为了使目录同步正常工作，请确保本地目录同步服务器上的 TCP 443 处于打开状态。

配置同步之后，请务必验证 AAD 连接是否正确同步。 在 EAC 中，转到 "**收件人** \> " "**联系人**"，并查看从您的本地环境中正确同步的用户列表。
