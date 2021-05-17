---
title: 在混合环境中将 EOP 配置为垃圾邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何将垃圾邮件路由到混合环境中用户Exchange Online Protection文件夹。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae6ee551d04b242891c9638d6d99d79240480d27
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203274"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>配置独立 EOP 以将垃圾邮件发送到混合环境中垃圾邮件文件夹

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
-  [Exchange Online Protection独立](exchange-online-protection-overview.md)

> [!IMPORTANT]
> 本主题仅适用于混合环境中的独立 EOP 客户。 本主题不适用于拥有Microsoft 365邮箱Exchange Online客户。

如果您是混合环境中的独立 Exchange Online Protection (EOP) 客户，则需要将内部部署 Exchange 组织配置为识别和转换 EOP 的垃圾邮件筛选裁定，以便内部部署邮箱中的垃圾邮件规则可以将邮件移动到"垃圾邮件"文件夹。

具体来说，您需要在本地 Exchange 组织中创建邮件流规则 (也称为传输规则) ，其中的条件是查找具有以下任何 EOP 反垃圾邮件标头和值的邮件，以及将这些邮件的垃圾邮件可信度 (SCL) 设置为 6 的操作：

- `X-Forefront-Antispam-Report: SFV:SPM` (垃圾邮件筛选系统标记为垃圾邮件) 

- `X-Forefront-Antispam-Report: SFV:SKS` (EOP 中的邮件流规则标记为垃圾邮件的邮件，然后再筛选) 

- `X-Forefront-Antispam-Report: SFV:SKB` (发件人的电子邮件地址或电子邮件域位于 EOP 邮件阻止的发件人列表或阻止的域列表中，因此被垃圾邮件筛选标记为垃圾邮件) 

有关这些邮件头值的信息，请参阅 [反垃圾邮件邮件头](anti-spam-message-headers.md)。

本主题介绍如何在 Exchange 管理中心 (EAC) 和本地 Exchange 组织的 Exchange 命令行管理程序 (Exchange PowerShell) 中创建这些邮件流规则。

> [!TIP]
> 您可以在 EOP 中配置反垃圾邮件策略以隔离 EOP 中的垃圾邮件，而不是将邮件发送到本地用户的"垃圾邮件"文件夹。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 您需在内部部署部署环境中Exchange权限，然后才能执行这些过程。 具体来说，您需要分配有传输规则角色，该角色默认分配给组织管理、合规性管理和 **记录管理** 角色。   有关详细信息，请参阅向 [角色组添加成员](/Exchange/permissions/role-group-members#add-members-to-a-role-group)。

- 如果将邮件传递到内部部署组织的"垃圾邮件"文件夹，Exchange以下设置的组合控制：

  - 命令行管理程序中 [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet 上的 _SCLJunkThreshold_ Exchange值。 默认值为 4，这意味着 SCL 为 5 或更高值时，应该将邮件发送到用户的"垃圾邮件"文件夹。

  - 命令行管理程序中 [Set-Mailbox](/powershell/module/exchange/set-mailbox) cmdlet 上的 _SCLJunkThreshold_ Exchange值。 默认值为空值 ($null) ，这意味着使用组织设置。

  有关详细信息，请参阅Exchange[垃圾邮件可信度 (SCL) 阈值。](/Exchange/antispam-and-antimalware/antispam-protection/scl)

  - 是否对邮箱启用了垃圾邮件规则 (_命令行_ 管理程序$true命令行管理程序中的 [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet Exchange Enabled 参数) 。 垃圾邮件规则实际上是在邮件传递后将邮件移动到"垃圾邮件"文件夹。 默认情况下，对邮箱启用垃圾邮件规则。 有关详细信息，请参阅 Configure [Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)。

- 若要打开 EAC 上的 Exchange Server，请参阅 Exchange[中的 Exchange Server。](/Exchange/architecture/client-access/exchange-admin-center) 若要打开 EAC，请参阅 Exchange Server 中的 Exchange 管理中心中。若要打开 Exchange 命令行管理程序，请参阅[打开 Exchange 命令行管理程序](/powershell/exchange/open-the-exchange-management-shell)。

- 有关本地部署中的邮件流规则Exchange，请参阅下列主题：

  - [邮件流规则Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [邮件流规则条件和例外 (中) 的Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [邮件流规则操作Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>使用 EAC 创建设置 EOP 垃圾邮件 SCL 的邮件流规则

1. In the EAC, go to **Mail flow** \> **Rules**.

2. 单击 **"添加** ![ ](../../media/ITPro-EAC-AddIcon.png) 添加"图标，然后选择出现的下拉列表中的"创建新规则"。

3. 在打开的" **新规则**"窗口中，配置以下设置：

   - **名称**：输入规则的唯一描述性名称。 例如：

     - EOP SFV：SPM 到 SCL 6

     - EOP SFV：SKS 到 SCL 6

     - EOP SFV：SKB 到 SCL 6

   - 单击“其他选项”。

   - **在 ：选择邮件****头包含** 以下任何词语 \> **时应用此规则**。

     在 **"Enter text header includes Enter words** sentence that appears" 中，执行以下步骤：

     - 单击 **"输入文本"。** 在出现的 **"指定标头** 名称"对话框中，输入 **X-Forefront-Antispam-Report，** 然后单击"确定 **"。**

     - 单击 **"输入单词"。** 在出现的 **"** 指定词语或短语"对话框中，输入 EOP 垃圾邮件头值 (**SFV：SPM、SFV：SKS** 或 **SFV：SKB**) ，单击"添加添加图标"，然后单击" ![ ](../../media/ITPro-EAC-AddIcon.png) 确定"。

   - **执行以下操作：选择****"修改邮件属性** \> **设置垃圾邮件可信度 (SCL) "。**

     在出现的 **"指定 SCL"** 对话框中，选择 **"6 (** 默认值为 **5**) 。

   完成后，单击"保存 **"**

对 **SFV：SPM、SFV：SKS** 或 **SFV：SKB** (剩余 EOP 垃圾邮件裁定值重复) 。 

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>使用 Exchange命令行管理程序创建设置 EOP 垃圾邮件 SCL 的邮件流规则

使用以下语法创建三个邮件流规则：

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

例如：

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

有关语法和参数的详细信息，请参阅 [New-TransportRule](/powershell/module/exchange/new-transportrule)。

## <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证您是否已成功配置独立 EOP 以将垃圾邮件发送到混合环境的"垃圾邮件"文件夹，请执行以下步骤之一：

- 在 EAC 中，**转到"邮件** 流""规则"，选择规则， \> 然后单击"编辑 ![ 编辑"图标 ](../../media/ITPro-EAC-EditIcon.png) 以验证设置。

- 在Exchange命令行管理程序中，将 替换为邮件流规则的名称， \<RuleName\> 并运行以下命令来验证设置：

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- 在未扫描出站邮件是否包含垃圾邮件的外部电子邮件系统中，向受影响的收件人发送未经请求的批量电子邮件 (GTUBE) 邮件的通用测试，并确认邮件已传递到其"垃圾邮件"文件夹。 GTUBE 邮件类似于用于测试恶意软件设置的欧洲反计算机病毒协会 (EICAR) 文本文件。

  若要发送 GTUBE 邮件，请将以下文本包括在单行电子邮件的正文中，没有任何空格或换行符：

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```