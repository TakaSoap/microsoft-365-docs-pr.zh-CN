---
title: 配置 ATP 防钓鱼策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何创建、修改和删除 Office 365 高级威胁防护（Office 365 ATP）的组织中提供的高级反网络钓鱼策略。
ms.openlocfilehash: 458a4eac348598d1b752267ed7d79b97bc594580
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726764"
---
# <a name="configure-atp-anti-phishing-policies"></a>配置 ATP 防钓鱼策略

ATP 反网络钓鱼策略是[Office 365 高级威胁防护](office-365-atp.md)的一部分。 ATP 反网络钓鱼策略可帮助保护您的组织免受恶意的基于模拟的网络钓鱼攻击和其他类型的网络钓鱼攻击。 有关 Exchange Online Protection （EOP）和 ATP 反网络钓鱼策略之间的反网络钓鱼策略之间的差异的详细信息，请参阅[反钓鱼保护](anti-phishing-protection.md)。

管理员可以查看、编辑和配置（但不能删除）默认的 ATP 反网络钓鱼策略。 为了获得更多的粒度，您还可以创建适用于组织中的特定用户、组或域的自定义 ATP 反网络钓鱼策略。 自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。

您可以在安全 & 合规性中心或 Exchange Online PowerShell 中配置 ATP 反网络钓鱼策略。

有关在 Exchange Online Protection 组织（即没有 Office 365 ATP 的 Microsoft 365 组织）中提供的更多限制的防网络钓鱼策略的信息，请参阅[在 EOP 中配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)。

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a>Security & 合规性中心 vs PowerShell 中的 ATP 反网络钓鱼策略

ATP 反网络钓鱼策略的基本要素为：

- **反网络钓鱼策略**：指定要启用或禁用的网络钓鱼防护，以及要应用选项的操作。

- **反网络钓鱼规则**：为反网络钓鱼策略指定优先级和收件人筛选器（策略应用于的人）。

在安全 & 合规中心中管理 ATP 反网络钓鱼策略时，这两个元素之间的差异并不明显：

- 在安全 & 合规中心创建 ATP 反网络钓鱼策略时，实际上是创建反网络钓鱼规则和关联的反网络钓鱼策略，同时为两者使用相同的名称。

- 当您在安全 & 合规中心中修改 ATP 反网络钓鱼策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改反网络钓鱼规则。 所有其他设置将修改关联的反网络钓鱼策略。

- 从安全 & 合规中心删除 ATP 反网络钓鱼策略时，将删除反钓鱼诈骗规则和关联的反网络钓鱼策略。

在 Exchange Online PowerShell 中，反网络钓鱼策略和反网络钓鱼规则之间的区别显而易见。 您可以使用** \* -AntiPhishPolicy** cmdlet 管理反网络钓鱼策略，并使用** \* -AntiPhishRule** cmdlet 管理反网络钓鱼规则。

- 在 PowerShell 中，首先创建反网络钓鱼策略，然后创建反网络钓鱼规则来标识应用该规则的策略。

- 在 PowerShell 中，可以单独修改反网络钓鱼策略和反钓鱼诈骗规则中的设置。

- 从 PowerShell 中删除反网络钓鱼策略时，不会自动删除相应的反网络钓鱼规则，反之亦然。

### <a name="default-atp-anti-phishing-policy"></a>默认 ATP 反网络钓鱼策略

每个 ATP 组织都有一个名为 Office365 AntiPhish 的内置 ATP 反网络钓鱼策略，该策略具有以下属性：

- 名为 Office365 AntiPhish 的反网络钓鱼策略默认应用于组织中的所有收件人，即使没有与该策略相关联的反网络钓鱼规则（收件人筛选器）也是如此。

- 名为 Office365 AntiPhish 的策略默认具有您无法修改的自定义优先级值**最低**（该策略总是最后应用）。 您创建的任何自定义策略的优先级始终高于名为 Office365 AntiPhish 的策略的默认优先级。

- 名为 Office365 AntiPhish 的策略默认为默认策略（ **IsDefault**属性具有值 `True` ），无法删除默认策略。

若要提高反钓鱼保护的有效性，可以使用应用于特定用户或用户组的更严格的设置来创建自定义 ATP 反网络钓鱼策略。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 " **ATP 反钓鱼**" 页面，请使用 <https://protection.office.com/antiphishing> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

- 您需要先分配权限，然后才能执行本主题中的过程：

  - 若要添加、修改和删除 ATP 反网络钓鱼策略，您必须是下列角色组之一的成员：

    - [Security & 合规性中心](permissions-in-the-security-and-compliance-center.md)中的 "**组织管理**" 或 "**安全管理员**"。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的 "**组织管理**" 或 "**卫生管理**"。

  - 若要对 ATP 反网络钓鱼策略进行只读访问，您必须是下列角色组之一的成员：

    - Security [& 合规性中心](permissions-in-the-security-and-compliance-center.md)中的**安全阅读**。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中**的仅查看组织管理**。

- 有关 ATP 反网络钓鱼策略的建议设置，请参阅[OFFICE ATP 反网络钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)。

- 允许使用最长30分钟的时间来应用新的或更新的策略。

- 有关在筛选管道中应用反网络钓鱼策略的位置的信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a>使用安全 & 合规性中心创建 ATP 反网络钓鱼策略

在安全 & 合规中心中创建自定义 ATP 反网络钓鱼策略，将同时为两者创建反钓鱼规则和关联的反网络钓鱼策略，同时为二者使用相同的名称。

创建 ATP 反网络钓鱼策略时，您只能指定策略名称、说明以及标识该策略适用于的收件人筛选器。 创建策略后，您可以修改策略以更改或查看默认的反网络钓鱼设置。

1. 在 "安全性 & 合规性中心中，转到"**威胁管理** \> **策略** \> **ATP 反网络钓鱼**"。

2. 在 "**反钓鱼网站**" 页上，单击 "**创建**"。

3. 将打开 "**新建反网络钓鱼策略**" 向导。 在 "**命名策略**" 页上，配置以下设置：

   - **名称**：输入策略的唯一描述性名称。

   - **说明**：输入策略的可选说明。

   完成后，单击“下一步”****。

4. 在显示的 "**应用于**" 页上，确定该策略应用于的内部收件人。

   只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

   单击 "**添加条件**"。 在出现的下拉列表中，选择 "**应用**条件：

   - **收件人为**：指定组织中的一个或多个邮箱、邮件用户或邮件联系人。
   - **收件人是的成员**：指定组织中的一个或多个组。
   - **收件人域为**：指定组织中已配置的一个或多个接受的域中的收件人。

   选择条件后，将显示相应的下拉框，其中包含**其中的任何**框。

   - 在框中单击并滚动到要选择的值列表。
   - 在框中单击，然后开始键入以筛选列表并选择一个值。
   - 若要添加其他值，请单击框中的空白区域。
   - 若要删除单个条目， **Remove**请单击 ![ ](../../media/scc-remove-icon.png) 值上的 "删除删除" 图标。
   - 若要删除整个条件，请**Remove**单击 ![ ](../../media/scc-remove-icon.png) 条件上的 "删除删除" 图标。

   若要添加其他条件，请单击 "**添加条件**"，然后选择 "**应用于**" 下的其他值。

   若要添加例外，请单击 "**添加条件**"，并在 "**除非**" 下选择例外。 设置和行为与条件完全相同。

   完成后，单击“下一步”****。

5. 在显示的 "**查看您的设置**" 页上，查看您的设置。 您可以在每个设置上单击 "**编辑**" 以修改它。

   完成后，单击 "**创建此策略**"。

6. 在出现的确认对话框中，单击 **"确定"** 。

在使用这些常规策略设置创建 ATP 反网络钓鱼策略后，请按照下一节中的说明操作，在策略中配置保护设置。

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a>使用安全 & 合规性中心修改 ATP 反网络钓鱼策略

使用以下过程可修改 ATP 反网络钓鱼策略：创建的新策略或已自定义的现有策略。

1. 如果尚不存在，请打开安全 & 合规中心，并转到**威胁管理** \> **策略** \> **ATP 反网络钓鱼**。

2. 选择要修改的自定义 ATP 反网络钓鱼策略。 如果已被选中，请取消选择并再次选择它。

3. 将出现 "**编辑 \<name\> 您的策略**" 浮出控件。 单击任意部分中的 "**编辑**" 可访问该部分中的设置。

   - 以下步骤按各节的显示顺序显示，但它们不是连续的（您可以按任何顺序选择和修改节）。

   - 在分区中单击 "**编辑**" 后，可用的设置将以向导格式显示，但您可以按任意顺序在页面中进行跳转，也可以单击任意页面上的 "**保存**" （或 "**取消**" 或 "**关闭** ![ 关闭" 图标， ](../../media/scc-remove-icon.png) 以返回到 "**编辑策略 \<name\> ** " 页（无需访问向导的最后一页即可保存或保留）。

4. **策略设置**：单击 "**编辑**" 可修改在上一节中[创建策略](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies)时可用的相同设置：

   - **名称**
   - **说明**
   - **应用于**
   - **查看设置**

   完成后，请单击任意页面上的 "**保存**"。

5. **模拟**：单击 "**编辑**" 以修改策略中的受保护的发件人和受保护的域。 这些设置是策略的一个条件，用于标识欺骗性发件人在入站邮件的 "发件人" 地址中查找（单独或按域）。 有关详细信息，请参阅[ATP 反网络钓鱼策略中的模拟设置](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)。

   - **添加要保护的用户**：默认值为**Off**。 若要打开它，请将切换滑到 **"开**"，然后单击出现的 "**添加用户**" 按钮。

     在出现的 "**添加用户**浮出控件" 中，配置以下值：

     - **电子邮件地址**：

        - 在框中单击并滚动到要选择的用户列表。
        - 在框中单击，然后开始键入以筛选列表并选择用户。
        - 若要删除条目，请**Remove**单击 ![ ](../../media/scc-remove-icon.png) "用户" 上的 "删除删除图标"。

     - **名称**：根据您选择的电子邮件地址填充此值，但您可以对其进行更改。

     完成后，请单击任意页面上的 "**保存**"。

    若要编辑现有条目，请在列表中选择受保护的用户。

   - **添加要保护的域**：配置以下一个或两个设置：

     - **自动包括我拥有的域**：默认值为**Off**。 若要打开它，请将开关滑到 **"开**"。
     - **包含自定义域**：默认值为**Off**。 若要打开它，请将开关滑到 **"开**"，在 "**添加域**" 框中，输入域名（例如，CONTOSO.COM），按 enter，并在必要时重复此操作。

   - **操作**：单击 "**编辑**"

     - **如果由模拟用户发送电子邮件**：为欺骗性发件人是在 "**添加用户以保护**" 中指定的受保护用户之一的邮件配置下列操作之一：

       - **不应用任何操作**
       - **将邮件重定向到其他电子邮件地址**
       - **将邮件移动到 "垃圾邮件" 文件夹**
       - **隔离邮件**
       - **传递邮件并向 "密件抄送" 行添加其他地址**
       - **邮件传递前删除邮件**

     - **如果由模拟域发送电子邮件**：为欺骗性发件人位于在 "**添加域以保护**" 中指定的受保护域之一的邮件配置下列操作之一：

     - **不应用任何操作**
     - **将邮件重定向到其他电子邮件地址**
     - **将邮件移动到 "垃圾邮件" 文件夹**
     - **隔离邮件**
     - **传递邮件并向 "密件抄送" 行添加其他地址**
     - **邮件传递前删除邮件**

   - 单击 "**打开模拟安全提示**"，并配置以下任何设置：

     - **为模拟用户显示提示**：默认值为**Off**。 若要打开它，请将开关滑到 **"开**"。
     - **显示模拟域的提示**：默认值为**Off**。 若要打开它，请将开关滑到 **"开**"。
     - **显示不正常字符的提示**：默认值为**Off**。 若要打开它，请将开关滑到 **"开**"。

     完成后，单击 **“保存”**。

   - **邮箱智能**：

     - 是否**启用邮箱智能？**：默认值为 **"开**"。 若要将其关闭，请将开关滑动到 "**关闭**"。

     - 是否**启用基于邮箱智能的模拟保护？**：此设置仅**在**"**启用邮箱智能" 时可用？处于启用状态**。

       在**模拟用户发送电子邮件时**，可以指定下列操作之一对邮箱智能失败的邮件执行操作（对受保护的用户和受保护的域可用的相同操作）：

       - **不应用任何操作**
       - **将邮件重定向到其他电子邮件地址**
       - **将邮件移动到 "垃圾邮件" 文件夹**
       - **隔离邮件**
       - **传递邮件并向 "密件抄送" 行添加其他地址**
       - **邮件传递前删除邮件**

   - **添加受信任的发件人和域**：指定策略的例外项：

     - **受信任的发件人**：

       - 在框中单击并滚动到要选择的用户列表。
       - 在框中单击，然后开始键入以筛选列表并选择用户。
       - 若要删除条目，请**Remove**单击 ![ ](../../media/scc-remove-icon.png) "用户" 上的 "删除删除图标"。

     - **受信任域**：输入域名（例如，contoso.com），按 enter，并在必要时重复此操作。

   - **查看设置**：不是单击每个单独的步骤，而是在摘要中显示设置。

     - 您可以单击每个部分中的 "**编辑**" 以跳回到相关页面。
     - 您可以在此页面**上****直接切换**以下设置：

       - **受保护的用户**
       - **受保护域** \>**包含我自己的域**
       - **受保护域** \>**受保护的域**（自定义域）
       - **邮箱智能**

   完成后，请单击任意页面上的 "**保存**"。

6. **哄骗**：单击 "**编辑**" 以打开或关闭欺骗情报，在 Outlook 中打开或关闭未经身份验证的发件人标识，并将操作配置为应用于阻止的欺骗性发件人的邮件。 有关详细信息，请参阅[反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。

   请注意，EOP 中的反网络钓鱼策略中也提供了这些相同的设置。

   - **哄骗筛选器设置**：默认值为 **"开**"，我们建议您将其保留在中。 若要将其关闭，请将开关滑动到 "**关闭**"。 有关详细信息，请参阅[在 EOP 中配置欺骗智能](learn-about-spoof-intelligence.md)。

     > [!NOTE]
     > 如果你的 MX 记录不指向 Microsoft 365，则无需禁用反欺骗保护;可以改为对连接器启用增强的筛选。 有关说明，请参阅[增强的对 Exchange Online 中的连接器的筛选](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

   - **启用未经身份验证的发件人功能**：默认值为**打开**。 若要将其关闭，请将开关滑动到 "**关闭**"。

   - **操作**：指定对欺骗性智能邮件失败的邮件执行的操作：

     **如果电子邮件由不允许欺骗您的域的人发送**：

     - **将邮件移到收件人的 "垃圾邮件" 文件夹**
     - **隔离邮件**

   - **查看设置**：不是单击每个单独的步骤，而是在摘要中显示设置。

     - 您可以单击每个部分中的 "**编辑**" 以跳回到相关页面。
     - 您可以在此页面**上****直接切换**以下设置：

       - **启用 antispoofing 保护**
       - **启用未经身份验证的发件人功能**

   完成后，请单击任意页面上的 "**保存**"。

7. **高级设置**：单击 "**编辑**" 以配置高级网络钓鱼阈值。 有关详细信息，请参阅[ATP 反网络钓鱼策略中的高级网络钓鱼阈值](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)。

   - **高级网络钓鱼阈值**：选择下列值之一：

   - **1-标准**（这是默认值。）
   - **2-主动**
   - **3-更主动**
   - **4-最主动**

   - **查看设置**：单击 "**编辑**" 以跳回到 "**高级网络钓鱼阈值**" 页面。

   完成后，单击任意页面上的 "**保存**"。

8. 返回到 "**编辑你的 \<Name\> 策略**" 页，查看你的设置，然后单击 "**关闭**"。

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a>使用安全 & 合规性中心修改默认的 ATP 反网络钓鱼策略

默认的 ATP 反网络钓鱼策略名为 Office365 AntiPhish Default，且不会出现在策略列表中。 若要修改默认的 ATP 反网络钓鱼策略，请执行以下步骤：

1. 在 "安全性 & 合规性中心中，转到"**威胁管理** \> **策略** \> **ATP 反网络钓鱼**"。

2. 在 "**反钓鱼网站**" 页上，单击 "**默认策略**"。

3. 将显示 "**编辑您的策略 Office365 AntiPhish 默认**页"。 以下各节均可用，其中包含[修改自定义策略](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)时的相同设置：

   - **模拟**
   - **哄骗**
   - **高级设置**

   修改默认策略时，以下设置不可用：

   - 您可以看到 "**策略设置**" 部分和值，但没有 "**编辑**" 链接，因此不能修改设置（策略名称、说明和策略应用于的用户（它适用于所有收件人））。
   - 您不能删除默认策略。
   - 您不能更改默认策略的优先级（总是最后应用）。

4. 在 "**编辑策略 Office365 AntiPhish 默认**页面上，查看您的设置，然后单击"**关闭**"。

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a>启用或禁用自定义 ATP 反网络钓鱼策略

1. 在 "安全性 & 合规性中心中，转到"**威胁管理** \> **策略** \> **ATP 反网络钓鱼**"。

2. 请注意 "**状态**" 列中的值：

   - 将开关滑到 "**关闭**" 以禁用该策略。

   - 将切换滑到**打开**以启用该策略。

您不能禁用默认的反网络钓鱼策略。

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a>设置自定义 ATP 反网络钓鱼策略的优先级

默认情况下，ATP 反网络钓鱼策略的优先级将取决于它们的创建顺序（较旧策略的优先级较低）。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以有相同的优先级。

自定义 ATP 反网络钓鱼策略按其处理顺序显示（第一个策略的**优先级**值为0）。 名为 Office365 AntiPhish 的默认反网络钓鱼策略默认的自定义优先级值为**最低**，无法更改。

 **注意**：在安全 & 合规性中心中，您只能在创建 ATP 反网络钓鱼策略时更改其优先级。 在 PowerShell 中，您可以在创建反网络钓鱼规则（可能会影响现有规则的优先级）时替代默认优先级。

若要更改策略的优先级，请单击策略属性中的 "**增加优先级**" 或 "**降低优先级**" （您不能直接修改 Security & 合规性中心中的**优先级**号码）。 如果有多个策略，则更改策略的优先级仅是有意义的。

1. 在 "安全性 & 合规性中心中，转到"**威胁管理** \> **策略** \> **ATP 反网络钓鱼**"。

2. 选择要修改的策略。 如果已被选中，请取消选择并再次选择它。

3. 将出现 "**编辑 \<name\> 您的策略**" 浮出控件。

   - **优先级**值为**0**的自定义 ATP 反网络钓鱼策略只有 "**降低优先级**" 按钮可用。

   - 具有最低**优先级**值（例如， **3**）的自定义 ATP 反网络钓鱼策略仅有 "**增加优先级**" 按钮可用。

   - 如果您具有三个或更多自定义的反网络钓鱼策略，则在最高和最低优先级值之间的策略将具有 "**增加优先级**" 和 "**降低优先级**" 按钮。

4. 单击 "**提高优先级**" 或 "**降低优先级**" 以更改**优先级**值。

5. 完成后，单击“关闭”****。

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a>使用安全 & 合规中心查看 ATP 反网络钓鱼策略

1. 在安全 & 合规性中心，并转到**威胁管理** \> **策略** \> **ATP 反网络钓鱼**。

2. 采取以下步骤之一：

   - 选择要查看的自定义 ATP 反网络钓鱼策略。 如果已被选中，请取消选择并再次选择它。

   - 单击 "**默认策略**" 以查看默认的反网络钓鱼策略。

3. 将出现 "**编辑 \<name\> 策略**" 浮出控件，您可以在其中查看设置和值。

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a>使用安全 & 合规性中心删除 ATP 反网络钓鱼策略

1. 在 "安全性 & 合规性中心中，转到"**威胁管理** \> **策略** \> **ATP 反网络钓鱼**"。

2. 选择要删除的策略。 如果已被选中，请取消选择并再次选择它。

3. 在出现的 "**编辑 \<name\> 策略**" 浮出控件中，单击 "**删除策略**"，然后在出现的警告对话框中单击 **"是"** 。

无法删除默认策略。

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a>使用 Exchange Online PowerShell 配置 ATP 反网络钓鱼策略

### <a name="use-powershell-to-create-anti-phishing-policies"></a>使用 PowerShell 创建反网络钓鱼策略

在 PowerShell 中创建反网络钓鱼策略的过程分为两个步骤：

1. 创建反网络钓鱼策略。

2. 创建反网络钓鱼规则，该规则指定应用该规则的反网络钓鱼策略。

 **注意**：

- 您可以创建新的反网络钓鱼规则并向其分配现有的未关联的反网络钓鱼策略。 反网络钓鱼规则不能与多个反网络钓鱼策略相关联。

- 您可以在 PowerShell 中的新反网络钓鱼策略中配置以下设置，这些设置在安全 & 合规性中心中不可用，直到您创建了策略：

  - 将新策略创建为禁用（_Enabled_ `$false` 在**AntiPhishRule** cmdlet 上启用）。

  - _Priority_ _\<Number\>_ 在**AntiPhishRule** cmdlet 上创建（优先级）过程中设置策略的优先级。

- 在 PowerShell 中创建的新反网络钓鱼策略在安全 & 合规性中心中不可见，除非您将策略分配给反网络钓鱼规则。

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>步骤1：使用 PowerShell 创建反网络钓鱼策略

若要创建反网络钓鱼策略，请使用以下语法：

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

本示例使用以下设置创建名为 "调研隔离" 的反网络钓鱼策略：

- 策略已启用（我们没有使用_enabled_参数，默认值为 `$true` ）。
- 说明是：研究部门策略。
- 为所有接受域启用组织域保护，并对 fabrikam.com 的目标域提供保护。
- 将 Mai Fujito （mfujito@fabrikam.com）指定为要从模拟中保护的用户。
- 启用邮箱智能。
- 启用邮箱智能保护，并指定隔离操作。
- 启用安全提示。

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

有关语法和参数的详细信息，请参阅[AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)。

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>步骤2：使用 PowerShell 创建反网络钓鱼规则

若要创建反网络钓鱼规则，请使用以下语法：

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

本示例将创建一个名为 "研究部门" 的反网络钓鱼规则，条件如下：

- 该规则与名为 "研究隔离" 的反网络钓鱼策略相关联。
- 此规则应用于“研究部门”组中的成员。
- 由于我们不使用_Priority_参数，因此使用默认的优先级。

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

有关语法和参数的详细信息，请参阅[AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。

### <a name="use-powershell-to-view-anti-phish-policies"></a>使用 PowerShell 查看反网络钓鱼策略

若要查看现有的反网络钓鱼策略，请使用以下语法：

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

本示例返回所有反网络钓鱼策略的摘要列表以及指定的属性。

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

本示例将返回名为 "主管" 的反网络钓鱼策略的所有属性值。

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

有关语法和参数的详细信息，请参阅[AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)。

### <a name="use-powershell-to-view-anti-phish-rules"></a>使用 PowerShell 查看反网络钓鱼规则

若要查看现有的反网络钓鱼规则，请使用以下语法：

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

本示例返回所有反网络钓鱼规则的摘要列表以及指定的属性。

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

若要按已启用或已禁用规则筛选列表，请运行以下命令：

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

本示例将返回名为 "Contoso 行政主管" 的反网络钓鱼规则的所有属性值。

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

有关语法和参数的详细信息，请参阅[AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。

### <a name="use-powershell-to-modify-anti-phish-policies"></a>使用 PowerShell 修改反网络钓鱼策略

除了以下项目之外，当您在 PowerShell 中按照 "[步骤1：使用 PowerShell 创建反网络钓鱼策略](#step-1-use-powershell-to-create-an-anti-phish-policy)" 一节中所述，在 PowerShell 中修改反网络钓鱼策略时，可以使用相同的设置。

- 将指定策略转换为默认策略的_MakeDefault_开关（适用于每个人、始终**最低**的优先级以及您无法删除它）仅当您在 PowerShell 中修改反网络钓鱼策略时才可用。

- 无法重命名反网络钓鱼策略（ **AntiPhishPolicy** Cmdlet 没有_Name_参数）。 重命名安全 & 合规中心中的反网络钓鱼策略时，只是重命名反网络钓鱼_规则_。

若要修改反网络钓鱼策略，请使用以下语法：

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

有关语法和参数的详细信息，请参阅[AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)。

### <a name="use-powershell-to-modify-anti-phish-rules"></a>使用 PowerShell 修改反网络钓鱼规则

在 PowerShell 中修改反网络钓鱼规则时，唯一不可用的设置是允许您创建禁用规则的_启用_参数。 若要启用或禁用现有的反网络钓鱼规则，请参阅下一节。

否则，在 PowerShell 中修改反网络钓鱼规则时，不提供其他任何设置。 按照本主题前面的 "[步骤2：使用 PowerShell 创建反钓鱼诈骗规则](#step-2-use-powershell-to-create-an-anti-phish-rule)" 一节中所述，创建规则时，可以使用相同的设置。

若要修改反网络钓鱼规则，请使用以下语法：

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

有关语法和参数的详细信息，请参阅[AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>使用 PowerShell 启用或禁用反网络钓鱼规则

若要启用或禁用 PowerShell 中的反网络钓鱼规则，可以启用或禁用整个反网络钓鱼策略（反钓鱼诈骗规则和分配的反网络钓鱼策略）。 您不能启用或禁用默认的反网络钓鱼策略（它始终应用于所有收件人）。

若要在 PowerShell 中启用或禁用反网络钓鱼规则，请使用以下语法：

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

本示例禁用名为 "Marketing 部门" 的反网络钓鱼规则。

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

下面的示例启用同一规则。

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅[Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule)和[Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)。

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>使用 PowerShell 设置反网络钓鱼规则的优先级

可以设置的规则最高优先级值是 0。 可以设置的最小优先级值取决于规则的数量。 例如，如果有五个规则，则可以使用的优先级值为 0 到 4。 更改现有规则的优先级可对其他规则产生级联效应。 例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。

若要在 PowerShell 中设置反网络钓鱼规则的优先级，请使用以下语法：

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

下面的示例将名为“Marketing Department”的规则的优先级设置为 2。 优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**注意**：

- 若要在创建时设置新规则的优先级，请改用**AntiPhishRule** cmdlet 上的_priority_参数。

- 默认反网络钓鱼策略不具有相应的反网络钓鱼规则，并且它始终具有 "不可修改的优先级" 值（**最低**）。

### <a name="use-powershell-to-remove-anti-phish-policies"></a>使用 PowerShell 删除反网络钓鱼策略

当您使用 PowerShell 删除反网络钓鱼策略时，不会删除相应的反网络钓鱼规则。

若要删除 PowerShell 中的反网络钓鱼策略，请使用以下语法：

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

本示例将删除名为 "Marketing 部门" 的反网络钓鱼策略。

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅[AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)。

### <a name="use-powershell-to-remove-anti-phish-rules"></a>使用 PowerShell 删除反网络钓鱼规则

当您使用 PowerShell 删除反网络钓鱼规则时，不会删除相应的反网络钓鱼策略。

若要删除 PowerShell 中的反网络钓鱼规则，请使用以下语法：

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

本示例将删除名为 "Marketing 部门" 的反钓鱼诈骗规则。

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅[AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证是否已成功配置 ATP 反网络钓鱼策略，请执行以下任一步骤：

- 在 "安全性 & 合规性中心中，转到"**威胁管理** \> **策略** \> **ATP 反网络钓鱼**"。 验证策略列表、策略的**状态**值及其**优先级**值。 若要查看更多详细信息，请执行以下步骤之一：

  - 从列表中选择策略，并在浮出控件中查看详细信息。
  - 单击 "**默认策略**" 并在浮出控件中查看详细信息。

- 在 Exchange Online PowerShell 中，将替换 \<Name\> 为策略或规则的名称，然后运行以下命令并验证设置：

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
