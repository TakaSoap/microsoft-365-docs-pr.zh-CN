---
title: 在独立 EOP 中管理邮件用户
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 了解如何在 Exchange Online Protection (EOP) 管理邮件用户，包括使用目录同步、EAC 和 PowerShell 管理用户。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910614"
---
# <a name="manage-mail-users-in-standalone-eop"></a>在独立 EOP 中管理邮件用户

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
-  [独立 Exchange Online Protection](exchange-online-protection-overview.md)

在独立 Exchange Online Protection (EOP) 没有 Exchange Online 邮箱的组织，邮件用户是基本类型的用户帐户。 邮件用户在独立 EOP 组织中具有帐户凭据，并且可以访问 (分配有权限) 。 邮件用户的电子邮件地址是外部 (例如，在本地电子邮件环境中) 。

> [!NOTE]
> 创建邮件用户时，相应的用户帐户在 Microsoft 365 管理中心可用。 在 Microsoft 365 管理中心创建用户帐户时，该帐户不能用于创建邮件用户。

在独立 EOP 中创建和管理邮件用户的推荐方法是使用目录同步，如本文稍后的使用目录同步管理 [邮件](#use-directory-synchronization-to-manage-mail-users) 用户一节中所述。

对于具有少量用户的独立 EOP 组织，您可以在 Exchange 管理中心 (EAC) 或独立 EOP PowerShell 中添加和管理邮件用户，如本文所述。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要打开 Exchange 管理中心 (EAC) ，请参阅独立 [EOP](exchange-admin-center-in-exchange-online-protection-eop.md)中的 Exchange 管理中心。

- 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 在 EOP PowerShell 中创建邮件用户时，可能会遇到限制。 此外，EOP PowerShell cmdlet 使用批处理方法，该方法在命令结果可见之前导致传播延迟几分钟。

- 您需在 Exchange Online Protection 中获得权限，然后才能执行本文中的过程。 具体来说，您需要邮件收件人创建 **(** 创建) 和邮件收件人 **(** 修改) 角色，这些角色默认分配给组织管理 **(** 全局管理员) 和 **收件人** 管理角色组。 有关详细信息，请参阅 [Permissions in standalone EOP](feature-permissions-in-eop.md) 和 [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- 有关可能适用于本文中的过程的键盘快捷方式的信息，请参阅[Keyboard shortcuts for the Exchange admin center in Exchange Online。](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> 是否有任何疑问？ 在 Exchange 论坛中寻求帮助。 请访问 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 论坛。

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>使用 Exchange 管理中心管理邮件用户

### <a name="use-the-eac-to-create-mail-users"></a>使用 EAC 创建邮件用户

1. 在 EAC 中，转到 **"收件人** \> **""联系人"**

2. 单击 **"新建** ![ "图标 ](../../media/ITPro-EAC-AddIcon.png) 。 在打开 **的"新建** 邮件用户"页中，配置以下设置。 标有 的 <sup>\*</sup> 设置是必需的。

   - **名**：使用此框可以键入用户的名。

   - **缩写**：人员中间名首字母。

   - **姓**：使用此框可以键入用户的姓。

   - <sup>\*</sup>**显示名称**：默认情况下，此框显示"名字"、**缩写** 和姓氏 **框中** 的值。 可以接受或更改此值。 该值应是唯一的，并且最大长度为 64 个字符。

   - <sup>\*</sup>**别名**：输入用户的唯一别名（最多使用 64 个字符）

   - **外部电子邮件地址**：输入用户的电子邮件地址。 域应在你的基于云的组织外部。

   - <sup>\*</sup>**用户 ID：** 输入用户将用于登录服务的帐户。 用户 ID 由位于 (@) 符号 (@) 左侧的用户名和右侧域组成。

   - <sup>\*</sup>**新密码** <sup>\*</sup> **和确认密码**：输入并重新输入帐户密码。 验证密码是否符合组织的密码长度、复杂性和历史记录要求。

3. 完成后，请单击“保存”来创建邮件用户。

### <a name="use-the-eac-to-modify-mail-users"></a>使用 EAC 修改邮件用户

1. 在 EAC 中，转到"**收件人** \> **""联系人"。**

2. 选择要修改的邮件用户，然后单击"编辑 **编辑"** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。

3. 在打开的邮件用户属性页上，单击下列选项卡之一以查看或更改属性。

   完成后，单击“**保存**”。

#### <a name="general"></a>常规

使用 **"常规** "选项卡可以查看或更改有关邮件用户的基本信息。

- **名**

- **缩写**

- **姓**

- **显示名称**：此名称出现在组织的通讯簿中、电子邮件的"To："和"From："行以及 EAC 中的联系人列表中。 此姓名不能在显示姓名之前或之后包含空格。

- **用户 ID：** 这是 Microsoft 365 中的用户帐户。 不能在此处修改此值。

#### <a name="contact-information"></a>联系人信息

使用 **"联系人信息** "选项卡可以查看或更改用户的联系信息。 该页上的信息显示在通讯簿中。

- **Street**
- **市/县**
- **省/市/自治区**
- **邮政编码**
- **国家/地区**
- **工作电话**
- **移动电话**
- **Fax**
- **更多选项**

  - **Office**
  - **住宅电话**
  - **网页**
  - **备注**

#### <a name="organization"></a>组织

使用 **"** 组织"选项卡可以记录有关组织中用户角色的详细信息。

- **Title**
- **Department**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>使用 EAC 删除邮件用户

1. 在 EAC 中，转到"**收件人** \> **""联系人"。**

2. 选择要删除的邮件用户，然后单击"删除 **""删除** ![ "图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。

## <a name="use-powershell-to-manage-mail-users"></a>使用 PowerShell 管理邮件用户

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>使用独立 EOP PowerShell 查看邮件用户

若要在独立 EOP PowerShell 中返回所有邮件用户的摘要列表，请运行以下命令：

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

若要查看有关特定邮件用户的详细信息，请将 替换为邮件用户的名称、别名或帐户名，然后 \<MailUserIdentity\> 运行以下命令：

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

有关语法和参数的详细信息，请参阅[Get-Recipient](/powershell/module/exchange/get-recipient)和[Get-User。](/powershell/module/exchange/get-user)

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>使用独立 EOP PowerShell 创建邮件用户

若要在独立 EOP PowerShell 中创建邮件用户，请使用以下语法：

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**注意**：

- _Name_ 参数是必需的，最大长度为 64 个字符，并且必须是唯一的。 如果您不使用 _DisplayName_ 参数，_Name_ 参数的值可用于显示名称。
- 如果不使用 _Alias_ 参数，则 _MicrosoftOnlineServicesID_ 参数的左侧将用于别名。
- 如果不使用 _ExternalEmailAddress_ 参数 _，MicrosoftOnlineServicesID_ 值将用于外部电子邮件地址。

本示例创建一个具有以下设置的邮件用户：

- 姓名为 JeffreyZeng，显示名称 Jeffrey Zeng。
- 名是 Jeffrey，姓是 Zeng。
- 别名是 jeffreyz。
- 外部电子邮件地址是 jzeng@tailspintoys.com。
- 帐户名称 jeffreyz@contoso.onmicrosoft.com。
- 密码为 Pa$$word1。

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

有关语法和参数的详细信息，请参阅 [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser)。

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>使用独立 EOP PowerShell 修改邮件用户

若要在独立 EOP PowerShell 中修改现有邮件用户，请使用以下语法：

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
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

有关语法和参数的详细信息，请参阅 [Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser)。

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>使用独立 EOP PowerShell 删除邮件用户

若要在独立 EOP PowerShell 中删除邮件用户，请将 替换为邮件用户的名称、别名或帐户名，然后 \<MailUserIdentity\> 运行以下命令：

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

本示例删除 Jeffrey Zeng 的邮件用户。

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

有关语法和参数的详细信息，请参阅 [Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证您是否已成功在独立 EOP 中创建、修改或删除邮件用户，请使用以下过程之一：

- 在 EAC 中，转到"**收件人** \> **""联系人"。** 验证邮件用户是否 (列出或未) 。 选择邮件用户，在"详细信息"窗格中查看信息，或单击"编辑 ![ 编辑"图标 ](../../media/ITPro-EAC-AddIcon.png) 查看设置。

- 在独立 EOP PowerShell 中，运行以下命令验证邮件用户是否 (列出或未) ：

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- 将 替换为邮件用户的名称、别名或帐户名，并运行 \<MailUserIdentity\> 以下命令来验证设置：

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>使用目录同步管理邮件用户

在独立 EOP 中，目录同步可用于具有本地 Active Directory 的客户。 可以将这些帐户同步到 Azure AD (Azure AD) Azure Active Directory，其中帐户的副本存储在云中。 将现有用户帐户同步到 Azure Active Directory 时，可以在 Exchange 管理中心 (EAC) 或独立 EOP PowerShell 的"收件人"窗格中查看这些用户。

**注意**：

- 如果使用目录同步管理收件人，仍可以在 Microsoft 365 管理中心中添加和管理用户，但是用户不会与本地 Active Directory 同步。 这是因为目录同步只能将来自本地 Active Directory 的收件人同步到云。

- 建议将目录同步用于以下功能：

  - **Outlook 安全发件人列表和** 阻止发件人列表：当同步到服务时，这些列表将优先于服务中的垃圾邮件筛选。 这使用户可以使用单个发件人和域条目管理其自己的安全发件人列表和阻止发件人列表。 有关详细信息，请参阅[配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

  - **基于目录的边缘阻止 (DBEB) ：** 有关 DBEB 有关详细信息，请参阅使用基于目录的边缘阻止拒绝发送给 [无效收件人的邮件](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。

  - **最终用户访问隔离**：若要访问其隔离邮件，收件人必须在服务中具有有效的用户 ID 和密码。 有关隔离功能详细信息，请参阅以用户模式查找并 [释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)。

  - 邮件流规则 (也称为传输规则 **) ：** 使用目录同步时，现有 Active Directory 用户和组将自动上载到云，然后可以创建面向特定用户和/或组的邮件流规则，而无需手动将它们添加到服务中。 请注意， [动态通讯组](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups)无法通过目录同步进行同步。

获取必要的权限并准备目录同步，如什么是 Azure Active [Directory 混合标识？](/azure/active-directory/hybrid/whatis-hybrid-identity)中所述。

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>将目录与 Azure Active Directory Connect (AAD Connect) 

1. 激活目录同步，如 [Azure AD Connect sync： Understand and customize synchronization 中所述](/azure/active-directory/hybrid/how-to-connect-sync-whatis)。

2. 安装和配置本地计算机以运行 AAD Connect，如 [Prerequisites for Azure AD Connect 中所述](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)。

3. [选择要用于 Azure AD Connect 的安装类型](/azure/active-directory/hybrid/how-to-connect-install-select-installation)：

   - [Express](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [自定义](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [传递身份验证](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> 完成 Azure Active Directory 同步工具配置向导后 **，MSOL_AD_SYNC** Active Directory 林中创建帐户。 此帐户用于读取和同步您的本地 Active Directory 信息。 为了使目录同步正常工作，请确保本地目录同步服务器上的 TCP 443 处于打开状态。

配置同步后，请确保验证 AAD Connect 是否正确同步。 在 EAC 中，转到"**收件人**""联系人"，并查看用户列表是否从本地环境 \> 正确同步。