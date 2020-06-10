---
title: 在混合环境中配置 EOP 到垃圾邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何将垃圾邮件路由到 Exchange Online Protection 混合环境中的用户垃圾邮件文件夹。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5d8ba6aae599ee4dd327bd1ec82b46e8f3ee3ca8
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679116"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>将独立 EOP 配置为将垃圾邮件传递到混合环境中的 "垃圾邮件" 文件夹

> [!IMPORTANT]
> 本主题仅适用于混合环境中的独立 EOP 客户。 本主题不适用于使用 Exchange Online 邮箱的 Microsoft 365 客户。

如果您是混合环境中的独立 Exchange Online Protection （EOP）客户，您需要将内部部署 Exchange 组织配置为识别和翻译 EOP 的垃圾邮件筛选 verdicts，以便内部部署邮箱中的垃圾邮件规则可以将邮件移动到 "垃圾邮件" 文件夹。

具体来说，您需要在内部部署 Exchange 组织中创建邮件流规则（也称为传输规则），条件是查找带有以下任一 EOP 反垃圾邮件头和值的邮件，以及将这些邮件的垃圾邮件可信度（SCL）设置为6的操作：

- `X-Forefront-Antispam-Report: SFV:SPM`（通过垃圾邮件筛选功能标记为垃圾邮件）

- `X-Forefront-Antispam-Report: SFV:SKS`（通过垃圾邮件筛选前 EOP 中的邮件流规则标记为垃圾邮件的邮件）

- `X-Forefront-Antispam-Report: SFV:SKB`（由于发件人的电子邮件地址或电子邮件域位于阻止的发件人列表或 EOP 中的阻止域列表中，由垃圾邮件筛选标记为垃圾邮件的邮件）

有关这些标头值的详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。

本主题介绍如何在内部部署 Exchange 组织中的 exchange 管理中心（EAC）和 Exchange 命令行管理程序（Exchange PowerShell）中创建这些邮件流规则。

> [!TIP]
> 您可以在 EOP 中配置反垃圾邮件策略以隔离 EOP 中的垃圾邮件，而不是将邮件传递到本地用户的 "垃圾邮件" 文件夹。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 您需要在本地 Exchange 环境中分配权限，然后才能执行这些过程。 具体来说，您需要分配 "**传输规则**" 角色，默认情况下会将其分配给 "**组织管理**"、"**合规性管理**" 和 "**记录管理**" 角色。 有关详细信息，请参阅[向角色组添加成员](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group)。

- 如果将邮件传递到本地 Exchange 组织中的 "垃圾邮件" 文件夹，则将通过以下设置的组合来控制邮件：

  - Exchange 命令行管理程序中的[set-organizationconfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet 上的_SCLJunkThreshold_参数值。 默认值为4，表示 SCL 为5或更高应将邮件传递到用户的 "垃圾邮件" 文件夹。

  - Exchange 命令行管理程序中的[设置邮箱](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)cmdlet 上的_SCLJunkThreshold_参数值。 默认值为空（$null），这意味着使用组织设置。

  有关详细信息，请参阅[Exchange 垃圾邮件可信度级别（SCL）阈值](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)。

  - 是否在邮箱上启用垃圾邮件规则（_启用_的参数值将在 Exchange 命令行管理[程序的 set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet 中 $true）。 它是传递邮件后实际将邮件移动到 "垃圾邮件" 文件夹的垃圾邮件规则。 默认情况下，在邮箱上启用垃圾邮件规则。 有关详细信息，请参阅[在邮箱上配置 Exchange 反垃圾邮件设置](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)。
  
- 若要在 Exchange 服务器上打开 EAC，请参阅 exchange [administration center In Exchange server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)。 若要打开 Exchange 命令行管理程序，请参阅[打开 Exchange 命令行管理](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell)程序。

- 有关本地 Exchange 中的邮件流规则的详细信息，请参阅下列主题：

  - [Exchange Server 中的邮件流规则](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Server 中的邮件流规则条件和例外（谓词）](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Server 中的邮件流规则操作](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>使用 EAC 创建邮件流规则，以设置 EOP 垃圾邮件的 SCL

1. In the EAC, go to **Mail flow** \> **Rules**.

2. 单击 "**添加**" "添加" ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) ，然后在出现的下拉对话框中选择 "**创建新规则**"。

3. 在打开的" **新规则**"窗口中，配置以下设置：

   - **名称**：输入规则的唯一描述性名称。 例如：

     - EOP SFV： SPM 至 SCL 6

     - EOP SFV： SKS 到 SCL 6

     - EOP SFV： SKB 到 SCL 6

   - 单击“其他选项”****。

   - **在以下情况应用此规则**：选择**邮件标头** \> 中**包含这些词语中的任何一个**。

     在 "**输入文本头包含**所显示的输入词" 句子中，执行下列步骤：

     - 单击 "**输入文本**"。 在出现的 "**指定头名称**" 对话框中，输入**X-Forefront-反垃圾邮件报告**，然后单击 **"确定"**。

     - 单击 "**输入词**"。 在出现的 "**指定字词或短语**" 对话框中，输入一个 EOP 垃圾邮件标头值（**SFV： SPM**， **SFV： SKS**，或**SFV： SKB**），单击 "**添加**" ![ "添加 ](../../media/ITPro-EAC-AddIcon.png) " 图标，然后单击 **"确定"**。

   - **执行以下**操作：选择 "**修改邮件属性** \> **" 设置垃圾邮件可信度（SCL）**。

     在出现的 "**指定 SCL** " 对话框中，选择 " **6** " （默认值为**5**）。

   完成后，请单击 "**保存**"

对余下的 EOP 垃圾邮件结论值（**SFV： SPM**、 **SFV： SKS**或**SFV： SKB**）重复这些步骤。

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>使用 Exchange 命令行管理程序创建邮件流规则，以设置 EOP 垃圾邮件的 SCL

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

有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)。

## <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证是否已成功将独立 EOP 配置为将垃圾邮件传递到混合环境中的 "垃圾邮件" 文件夹，请执行以下任一步骤：

- 在 EAC 中，转到 "**邮件流** \> **规则**"，选择规则，然后单击 "**编辑** ![ 编辑图标 ](../../media/ITPro-EAC-EditIcon.png) " 以验证设置。

- 在 Exchange 命令行管理程序中，将替换 \<RuleName\> 为邮件流规则的名称，并 rul 以下命令来验证设置：

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- 在**不扫描出站邮件中的垃圾**邮件的外部电子邮件系统中，向受影响的收件人发送未经请求的批量电子邮件（GTUBE）邮件的一般测试，并确认它已传递到其 "垃圾邮件" 文件夹。 GTUBE 邮件类似于用于测试恶意软件设置的欧洲反计算机病毒协会 (EICAR) 文本文件。

  若要发送 GTUBE 邮件，请将电子邮件正文中的以下文本包含在一行中，不含空格或换行符：

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
