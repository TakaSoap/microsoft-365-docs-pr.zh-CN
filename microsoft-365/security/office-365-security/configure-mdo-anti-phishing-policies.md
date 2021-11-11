---
title: 在 Microsoft Defender for Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何创建、修改和删除 Microsoft Defender for Office 365 中提供的高级防钓鱼策略。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9681f1d110280a99e43283d56a7de3bb11e0f8b3
ms.sourcegitcommit: 7b83e2605895fee5c73cd1d01f4cd16e1457a69f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2021
ms.locfileid: "60907953"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>在 Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender for [Office 365](defender-for-office-365.md)中的反网络钓鱼策略可帮助保护组织免受基于恶意模拟的网络钓鱼攻击和其他类型的网络钓鱼攻击。 有关 Exchange Online Protection (EOP) 中的反网络钓鱼策略与 Microsoft Defender for Office 365 中的反网络钓鱼策略之间的差异，请参阅反网络钓鱼[防护](anti-phishing-protection.md)。

管理员可以查看、编辑和配置 (，但不能) 默认的防钓鱼策略。 更精细地来说，您还可以创建适用于组织中特定用户、组或域的自定义防钓鱼策略。 自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。

可以在 Defender 中配置反网络钓鱼策略，Office 365在 Microsoft 365 Defender 门户或 Exchange Online PowerShell 中配置。

有关在 Exchange Online Protection (中可用的反网络钓鱼策略（即没有 Defender for Office 365) 的组织）中配置更多限制的信息，请参阅在[EOP](configure-anti-phishing-policies-eop.md)中配置反网络钓鱼策略。

防钓鱼策略的基本元素包括：

- **防钓鱼策略**：指定要启用或禁用的网络钓鱼防护，以及要应用选项的操作。
- **反网络钓鱼规则**：指定策略应用于 (策略的收件人筛选器) 策略的优先级和收件人筛选器。

在安全门户中管理防钓鱼策略时，这两个元素Microsoft 365 Defender明显：

- 创建策略时，实际上是同时使用同一名称创建防钓鱼规则和相关防钓鱼策略。
- 修改策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改防钓鱼规则。 所有其他设置修改关联的防钓鱼策略。
- 删除策略时，将删除防钓鱼规则和相关反钓鱼策略。

在 Exchange Online PowerShell 中，单独管理策略和规则。 有关详细信息，请参阅本文Exchange Online[使用 PowerShell](#use-exchange-online-powershell-to-configure-anti-phishing-policies)配置防钓鱼策略一节。

每个 Defender for Office 365 组织都有一个名为"反钓鱼Office 365的内置防钓鱼策略，该策略具有以下属性：

- 即使与策略关联的收件人筛选器没有反网络钓鱼规则， (应用于组织) 所有收件人。
- 该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。 你创建的任何自定义策略始终具有更高的优先级。
- 该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。

若要提高 Office 365 的 Defender 中的防钓鱼保护的有效性，可以使用应用于特定用户或用户组的更严格的设置创建自定义防钓鱼策略。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到" **防钓鱼"页面** ，请使用 <https://security.microsoft.com/antiphishing> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：
  - 若要添加、修改和删除防钓鱼策略，你需要是组织管理或安全 **管理员角色****组** 的成员。
  - 若要对防钓鱼策略进行只读访问，你需要是全局读者或 **安全读者角色****组的成员** <sup>\*</sup> 。

  有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。

  **注意**：

  - 在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的权限。有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

- 有关 Defender for Office 365 中的反网络钓鱼策略建议设置，请参阅 Defender 中的反网络钓鱼策略，Office 365[设置](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。

- 最多允许应用新策略或更新策略 30 分钟。

- 有关反网络钓鱼策略在筛选管道中的应用位置的信息，请参阅电子邮件保护的顺序 [和优先级](how-policies-and-protections-are-combined.md)。

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a>使用Microsoft 365 Defender门户创建防钓鱼策略

在 Microsoft 365 Defender 门户中创建自定义防钓鱼策略可同时创建反网络钓鱼规则和相关反网络钓鱼策略，对二者使用相同的名称。

1. 在 Microsoft 365 Defender 门户中，转到"策略"&中的"电子邮件&协作策略&规则威胁策略 \>  \>  \> **""** 防钓鱼"。 

2. 在" **防钓鱼"页上** ，单击" ![ 创建图标"。](../../media/m365-cc-sc-create-icon.png) **Create**。

3. 将打开策略向导。 在" **策略名称"** 页上，配置这些设置：
   - **名称**：输入策略的唯一描述性名称。
   - **说明**：输入策略的可选说明。

   完成后，单击“**下一步**”。

4. 在出现的“**用户、组和域**”页面上，标识策略应用于的内部收件人（收件人条件）：
   - **用户**：你的组织内指定的邮箱、邮件用户或邮件联系人。
   - **组**：你的组织内指定的通讯组、启用邮件的安全组或 Microsoft 365 组。
   - **域**：你的组织内指定的 [接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件人。

   单击相应的框，开始键入值，然后从结果中选择所需的值。 根据需要多次重复此过程。 若要删除现有值，请单击值旁边的 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) “删除”。

   对于用户或组，可以使用大多数标识符（名称、显示名称、别名、电子邮件地址、帐户名称等），但相应的显示名称则显示在结果中。对于用户，请自行输入星号（\*），以查看所有可用值。

   同一个条件的多个值使用 OR 逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件使用 AND 逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

   - **排除这些用户、组和域**：若要为策略应用于的内部收件人添加例外（收件人例外），请选择此选项并配置例外。 设置和行为与条件完全相同。

   完成后，单击“**下一步**”。

5. 在出现的 **"网络钓鱼&** 保护"页上，配置以下设置：

   - **网络钓鱼电子邮件阈值**：使用滑块选择以下值之一：
     - **1 - 标准** (此值为默认值。) 
     - **2 - 主动**
     - **3 - 更主动**
     - **4 - 最积极**

     有关详细信息，请参阅 Microsoft Defender for Office 365 中的反网络钓鱼[策略中的高级网络钓鱼Office 365。](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

   - **模拟**：这些设置是策略的一个条件，用于标识要单独或按域 (在入站邮件的"发件人"地址) 查找邮件的特定发件人。 有关详细信息，请参阅 Microsoft Defender for Office 365 中的防钓鱼[策略中的模拟Office 365。](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

     > [!NOTE]
     >
     > - 在每个防钓鱼策略中，最多可指定 350 个受保护 (发件人电子邮件地址) 。 不能在多个策略中指定同一受保护的用户。
     > - 如果发件人和收件人之前通过电子邮件进行通信，则用户模拟保护不起作用。 如果发件人和收件人从未通过电子邮件进行通信，则邮件将被标识为模拟尝试。

     - **允许用户保护**：默认值为 off， (未) 。 若要打开它，请选中该复选框，然后单击"管理 (**nn")  (显示**) "链接。

       在 **出现的"管理发件人以执行模拟保护** "飞出中，执行以下步骤：

       - **内部发件人：** 单击 ![ "添加内部图标"。](../../media/m365-cc-sc-add-internal-icon.png) **选择内部**。 In the **Add internal senders** flyout that appears， click in the box and select an internal user from the list. 可以通过键入用户，然后从结果中选择用户来筛选列表。 您可以使用大部分标识符 (、显示名称、别名、电子邮件地址、帐户名等 ) ，但结果显示名称显示相应的标识符。

         根据需要重复执行此步骤（次数不限）。 若要删除现有值，请单击值旁边的 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) “删除”。

         完成后，单击"添加 **"**

       - **外部发件人：** 单击 ![ "添加外部图标"。](../../media/m365-cc-sc-create-icon.png) **选择外部**。 在出现的 **"** 添加外部发件人"飞出框中，在"添加名称"框中输入显示名称 和电子邮件地址，然后单击"添加 **"。** 

         根据需要重复执行此步骤（次数不限）。 若要删除现有值，请单击值旁边的 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) “删除”。

         完成后，单击"添加 **"**

       返回到" **管理发件人进行模拟"** 飞出，您可以通过从列表中选择一个或多个条目来删除条目。 可以使用"搜索"图标搜索 ![ 条目。](../../media/m365-cc-sc-create-icon.png) **搜索** 框。

       至少选择一个条目后，" ![ 删除所选用户"图标。](../../media/m365-cc-sc-remove-selected-users-icon.png) **将显示"删除** 所选用户"图标，可用于删除所选条目。

       完成后，单击“**完成**”。

     - **启用域保护**：默认值为 off， (未) 。 若要打开它，请选中该复选框，然后配置以下一个或两个显示的设置：
       - **包括我拥有的域**：若要启用此设置，请选中复选框。 若要查看您拥有的域，请单击"**查看我的域"。**
       - **包括自定义域**：若要启用此设置，请选中该复选框，然后单击出现的"管理 (**nn) 自定义域 ()** 链接。 在出现的 **"管理用于模拟保护的** 自定义域"飞出控件中，单击" ![ 添加域图标"。](../../media/m365-cc-sc-create-icon.png) **添加域**。

         在出现的 **"添加自定义** 域"飞出控件中，在"域"框中单击，输入值，然后按 Enter 或选择显示在该框下方的值。 根据需要重复执行此步骤（次数不限）。 若要删除现有值，请单击删除 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) 它位于值的旁边。

         完成后，单击"添加 **域"**

         > [!NOTE]
         > 在所有防钓鱼策略中最多可以有 50 个域。

       返回到"管理用于模拟 **的** 自定义域"飞出控件，您可以通过从列表中选择一个或多个条目来删除条目。 可以使用"搜索"图标搜索 ![ 条目。](../../media/m365-cc-sc-create-icon.png) **搜索** 框。

       至少选择一个条目后，" ![ 删除域"图标。](../../media/m365-cc-sc-delete-icon.png) **将显示** "删除"图标，可用于删除所选条目。

   - 添加 **受** 信任发件人和域：单击"管理 **(nn**) 受信任发件人" () 和域 () ，为策略指定模拟保护例外。 在 **出现的"管理用于模拟保护的** 自定义域"飞出控件中，配置以下设置：
      - **发件人：** 验证是否 **选择了"发件人** "选项卡，然后单击" ![ 添加发件人图标 ](../../media/m365-cc-sc-create-icon.png) "。 在出现的 **"添加受信任** 发件人"飞出框中，输入电子邮件地址，然后单击"添加 **"。** 根据需要重复执行此步骤（次数不限）。 若要删除现有条目，请单击 ![ 该条目 ](../../media/m365-cc-sc-close-icon.png) 的"删除图标"。

        完成后，单击“**添加**”。

      - **域**：选择" **域"** 选项卡，然后单击 ![ "添加域图标 ](../../media/m365-cc-sc-create-icon.png) "。

        在出现的 **"添加受信任的** 域"飞出框中，单击"域"框中，输入一个值，然后按 Enter 或选择显示在该框下方的值。 根据需要重复执行此步骤（次数不限）。 若要删除现有值，请单击删除 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) 它位于值的旁边。

        完成后，单击“**添加**”。

     返回到"管理用于模拟 **的** 自定义域"飞出控件，您可以通过从列表中选择一个或多个条目来从"发件人"和"域"选项卡中删除条目。 可以使用"搜索"图标搜索 ![ 条目。](../../media/m365-cc-sc-create-icon.png) **搜索** 框。

     选择至少一个条目后，将显示"删除"图标，可用于删除所选条目。

     完成后，单击“**完成**”。

   - **启用邮箱智能**：默认值在选中 (时) ，建议保留它。 若要将其关闭，请清除该复选框。

     - **启用基于智能的模拟** 保护：仅在选中"启用邮箱智能"时 (此设置) 。 此设置允许邮箱智能对标识为模拟尝试的邮件采取措施。 您可以在下一页的"如果 **邮箱智能检测到模拟** 的用户"设置中指定要执行的操作。

       建议通过选中复选框来打开此设置。 若要关闭此设置，请清除该复选框。

   - **欺骗**：在此部分中，使用" **启用欺骗** 智能"复选框打开或关闭欺骗智能。 默认值在选中 (时) ，建议保留它。 在下一页的"如果邮件被检测为欺骗"设置中，指定对来自被阻止的欺骗发件人的邮件要采取的操作。

     若要关闭欺骗智能，请清除此复选框。

     > [!NOTE]
     > 如果你的 MX 记录没有指向反欺骗保护，则无需Microsoft 365;改为启用连接器的增强筛选。 有关说明，请参阅[增强的连接器筛选Exchange Online。](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

   完成后，单击“**下一步**”。

6. 在出现的“**操作**”页面上，配置下列设置：

   - **邮件操作**：在此部分中配置以下操作：
     - **如果邮件被检测为模拟** 用户：只有在上一页上选择了"允许用户保护"时，此设置才可用。 对于发件人是上一页上指定的受保护用户之一的邮件，在下拉列表中选择下列操作之一：
       - **不应用任何操作**
       - **将邮件重定向到其他电子邮件地址**
       - **将邮件移动到收件人的"垃圾邮件"文件夹**
       - **隔离邮件**：如果选择此操作，则会显示"应用隔离策略"框，选择适用于用户模拟保护隔离的邮件的隔离策略。 隔离策略定义用户可以对隔离邮件执行哪些操作，以及用户是否收到隔离通知。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。

         空白的 **"应用隔离策略** "值意味着默认隔离策略 (DefaultFullAccessPolicy 进行用户模拟检测) 。 以后编辑防钓鱼策略或查看设置时，将显示默认隔离策略名称。
  
       - **传递邮件，将其他地址添加到"Bcc"行**
       - **在邮件传递之前删除邮件**

     - **如果邮件被检测为** 模拟域：只有在上一页上选择了"启用要保护的域"时，此设置才可用。 对于发件人的电子邮件地址位于上一页上指定的其中一个受保护的域的邮件，请在下拉列表中选择以下操作之一：
       - **不应用任何操作**
       - **将邮件重定向到其他电子邮件地址**
       - **将邮件移动到收件人的"垃圾邮件"文件夹**
       - **隔离邮件**：如果选择此操作，则会显示"应用隔离策略"框，选择适用于域模拟保护隔离的邮件的隔离策略。

         空白的 **"应用隔离策略** "值表示默认隔离策略 (DefaultFullAccessPolicy 用于域模拟检测) 。 以后编辑防钓鱼策略或查看设置时，将显示默认隔离策略名称。

       - **传递邮件，将其他地址添加到"Bcc"行**
       - **在邮件传递之前删除邮件**

     - **如果邮箱智能检测到模拟用户**：只有在上一页上选择了"启用智能 **以用于** 模拟保护"时，此设置才可用。 对于被邮箱智能标识为模拟尝试的邮件，请在下拉列表中选择以下操作之一：
       - **不应用任何操作**
       - **将邮件重定向到其他电子邮件地址**
       - **将邮件移动到收件人的"垃圾邮件"文件夹**
       - **隔离邮件**：如果选择此操作，则会显示"应用隔离策略"框，选择适用于由邮箱智能保护隔离的邮件的隔离策略。 隔离策略定义用户可以对隔离邮件执行哪些操作，以及用户是否收到隔离通知。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。

         空白 **的"应用隔离策略** "值意味着默认隔离策略 (DefaultFullAccessPolicy 中用于邮箱智能) 。 以后编辑防钓鱼策略或查看设置时，将显示默认隔离策略名称。

       - **传递邮件，将其他地址添加到"Bcc"行**
       - **在邮件传递之前删除邮件**

     - **如果邮件被检测为欺骗邮件**：只有在上一页上选择了" **启用** 欺骗智能"时，此设置才可用。 在下拉列表中为来自阻止的欺骗性发件人的邮件选择以下操作之一：
       - **将邮件移动到收件人的"垃圾邮件"文件夹**
       - **隔离邮件**：如果选择此操作，则会显示"应用隔离策略"框，选择适用于通过欺骗智能保护隔离的邮件的隔离策略。 隔离策略定义用户可以对隔离邮件执行哪些操作，以及用户是否收到隔离通知。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。

         空白的 **"应用隔离策略** "值意味着默认隔离策略 (DefaultFullAccessPolicy 用于欺骗智能) 。 以后编辑防钓鱼策略或查看设置时，将显示默认隔离策略名称。

   - **安全提示&：** 配置以下设置：
     - **显示第一安全提示** 联系人：有关详细信息，请参阅第一 [个联系人安全提示。](set-up-anti-phishing-policies.md#first-contact-safety-tip)
     - **显示用户模拟安全提示：** 只有在上一页上选择了"**允许用户保护"** 时，此设置才可用。
     - **显示域模拟安全提示：** 只有在上一页上选择了"启用要保护的域"时 **，此设置才** 可用。
     - **显示用户模拟异常字符安全提示** 只有在上一页上选择了"允许用户保护域"或"启用要保护的域"时 **，此设置才** 可用。
     - **显示 (？)** 欺骗的未经身份验证的发件人的信息：仅在上一页上选择了"启用欺骗智能"时，此设置才可用。  如果邮件未通过 SPF 或 DKIM 检查且邮件未通过 DMARC 或复合身份验证，则向Outlook 中的发件人照片添加问[号](email-validation-and-authentication.md#composite-authentication)。
     - **显示"通过"标记**：仅在你在上一页上选择了" **启用** 欺骗智能"时，此设置才可用。 如果 via 标记 (chris@contoso.com 通过 fabrikam.com) 添加到"收件人"地址（如果它不同于 DKIM 签名或 **MAIL FROM** 地址中的域）。 默认值在选定 (时) 。 若要将其关闭，请清除该复选框。

     若要打开某个设置，请选中该复选框。 若要将其关闭，请清除该复选框。

   完成后，单击“**下一步**”。

7. 在出现的“**审阅**”页面上，查看你的设置。 可以在每个部分中选择“**编辑**”来修改该部分中的设置。 或者，可以单击“**返回**”或选择向导中的特定页面。

   完成后，请单击“**提交**”。

8. 在出现的确认页面上，单击“**完成**”。

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a>使用Microsoft 365 Defender查看防钓鱼策略

1. 在 Microsoft 365 Defender 门户中，转到"策略"&中的"电子邮件&协作策略&规则威胁策略 \>  \>  \> **""** 防钓鱼"。 

2. 在 **"防钓鱼"** 页上，反网络钓鱼策略列表中将显示以下属性：

   - **名称**
   - **状态**
   - **优先级**
   - **上次修改时间**

3. 当您通过单击该名称选择策略时，策略设置将显示在一个飞出内容中。

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a>使用Microsoft 365 Defender门户修改防钓鱼策略

1. 在 Microsoft 365 Defender 门户中，转到"策略"&中的"电子邮件&协作策略&规则威胁策略 \>  \>  \> **""** 防钓鱼"。 

2. 在 **"防钓鱼"** 页上，通过单击名称从列表中选择一个策略。

3. 在出现的策略详细信息浮出控件中，选择每个部分中的“**编辑**”以修改该部分中的设置。 有关设置详细信息，请参阅本文前面使用[](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies)Microsoft 365 Defender 门户创建防钓鱼策略一节。

   对于默认的防钓鱼策略，"用户、组和域"部分不可用 (该策略适用于所有) ，并且无法重命名该策略。

若要启用或禁用策略或设置策略优先级顺序，请参阅以下几节。

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>启用或禁用自定义防钓鱼策略

无法禁用默认的防钓鱼策略。

1. 在 Microsoft 365 Defender 门户中，转到"策略"&中的"电子邮件&协作策略&规则威胁策略 \>  \>  \> **""** 防钓鱼"。 

2. 在 **"防钓鱼"** 页上，通过单击名称从列表中选择自定义策略。

3. 在出现的策略详细信息浮出控件顶部，你将看到以下值之一：
   - **策略关闭**：若要打开策略，请单击![“打开”图标。](../../media/m365-cc-sc-turn-on-off-icon.png)**“打开”**。
   - **策略打开**：若要关闭策略，请单击![“关闭”图标。](../../media/m365-cc-sc-turn-on-off-icon.png)**“关闭”**。

4. 在出现的确认对话框中，单击“**打开**”或“**关闭**”。

5. 单击策略详细信息浮出控件中的“**关闭**”。

返回主策略页面，策略的“**状态**”值将为“**打开**”或“**关闭**”。

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>设置自定义防钓鱼策略的优先级

默认情况下，基于反网络钓鱼策略在 (较旧策略中创建的顺序，反网络钓鱼策略的优先级低于较旧策略) 。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

要更改策略的优先级，请在策略属性中单击“**提高优先级**”或“**降低优先级**”（不能在 Microsoft 365 Defender 门户中直接修改 **优先级** 编号）。仅当具有多个策略时，更改策略的优先级才有意义。

 **注意**：

- 在Microsoft 365 Defender门户中，只能在创建后更改反网络钓鱼策略的优先级。 在 PowerShell 中，您可以在创建反网络钓鱼规则策略时替代默认优先级 (这可能会影响现有规则优先级) 。
- 反网络钓鱼策略按照其显示顺序进行处理， (策略的优先级值为 0) 。  默认防钓鱼策略的优先级值为 **"** 最低"，你无法更改它。

1. 在 Microsoft 365 Defender 门户中，转到"策略"&中的"电子邮件&协作策略&规则威胁策略 \>  \>  \> **""** 防钓鱼"。 

2. 在 **"防钓鱼"** 页上，通过单击名称从列表中选择自定义策略。

3. 在出现的策略详细信息浮出控件顶部，你会看到“**提高优先级**”或“**降低优先级**”，具体取决于当前优先级值和自定义策略数量：
   - 优先级值为 **0** **的策略** 只有"**减少优先级"** 选项可用。
   - 优先级值最低的 **策略 (例如****，3**) 只有"增加优先级 **"** 选项可用。
   - 如果你有三个或多个策略，则最高优先级值和最低优先级值之间的策略同时具有"增加 **优先级** "和" **减少优先级"** 选项。

   单击![“提高优先级”图标。](../../media/m365-cc-sc-increase-icon.png) **“提高优先级”** 或![“降低优先级”图标](../../media/m365-cc-sc-decrease-icon.png) **“降低优先级”** 以更改 **“优先级”** 值。

4. 完成后，单击策略详细信息浮出控件中的“**关闭**”。

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a>使用Microsoft 365 Defender门户删除自定义防钓鱼策略

当您使用 Microsoft 365 Defender门户删除自定义防钓鱼策略时，防钓鱼规则及相应的反网络钓鱼策略都将被删除。 无法删除默认的防钓鱼策略。

1. 在 Microsoft 365 Defender 门户中，转到"策略"&中的"电子邮件&协作策略&规则威胁策略 \>  \>  \> **""** 防钓鱼"。 

2. 在 **"防钓鱼"** 页上，通过单击策略的名称从列表中选择自定义策略。

3. 在显示的策略详细信息浮出控件顶部，单击![更多操作图标。](../../media/m365-cc-sc-more-actions-icon.png) **更多操作** \> ![删除策略图标](../../media/m365-cc-sc-delete-icon.png) **删除策略**。

4. 在出现的确认对话框中，单击“**是**”。

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>使用 Exchange Online PowerShell 配置防钓鱼策略

如前所述，反垃圾邮件策略由反网络钓鱼策略和反网络钓鱼规则组成。

在 Exchange Online PowerShell 中，防钓鱼策略和防钓鱼规则的区别显而易见。 您可以使用 **\* -AntiPhishPolicy** cmdlet 管理防钓鱼策略，使用 **\* -AntiPhishRule** cmdlet 管理反钓鱼规则。

- 在 PowerShell 中，首先创建防钓鱼策略，然后创建标识规则所适用的策略的防钓鱼规则。
- 在 PowerShell 中，分别修改反钓鱼策略和反钓鱼规则中的设置。
- 从 PowerShell 删除防钓鱼策略时，不会自动删除相应的防钓鱼规则，反之亦然。

### <a name="use-powershell-to-create-anti-phishing-policies"></a>使用 PowerShell 创建防钓鱼策略

在 PowerShell 中创建防钓鱼策略的过程包括两个步骤：

1. 创建防钓鱼策略。
2. 创建指定该规则所适用的防钓鱼策略的防钓鱼规则。

 **注意**：

- 你可以创建新的防钓鱼规则，并为其分配现有的未关联的反网络钓鱼策略。 反网络钓鱼规则不能与多个防钓鱼策略关联。
- 可以在 PowerShell 中对新的防钓鱼策略配置以下设置，这些设置在 Microsoft 365 Defender 门户中不可用，除非创建策略：
  - 在 `$false` **New-AntiPhishRule** cmdlet (上创建禁用的新策略) 。
  - 在 _\<Number\>_ **New-AntiPhishRule** cmdlet (中) 策略的优先级) 。
- 在 PowerShell 中新建的防钓鱼策略在 Microsoft 365 Defender门户中不可见，除非将策略分配给防钓鱼规则。

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>步骤 1：使用 PowerShell 创建防钓鱼策略

若要创建防钓鱼策略，请使用以下语法：

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

本示例将创建一个名为"Research Quarantine"的防钓鱼策略，并具有以下设置：

- 如果策略 (_Enabled_ 参数，则启用该策略，默认值为 `$true`) 。
- 描述为：研究部门策略。
- 将欺骗检测的默认操作更改为"隔离"，并使用隔离邮件的默认隔离 [](quarantine-policies.md)策略 (我们使用的不是 _SpoofQuarantineTag_ 参数) 。
- 针对所有接受的域启用组织域保护，为组织域启用目标域 fabrikam.com。
- 将 Quarantine 指定为域模拟检测的操作，并使用隔离邮件的默认隔离策略 ([](quarantine-policies.md)我们使用的不是 _TargetedDomainQuarantineTag_ 参数) 。
- 指定一 (mfujito@fabrikam.com) 用户的身份进行保护，防止模拟。
- 将 Quarantine 指定为用户模拟检测的操作，并使用隔离邮件的默认隔离策略 ([](quarantine-policies.md)我们未使用 _TargetedUserQuarantineTag_ 参数) 。
- 启用邮箱智能 (_EnableMailboxIntelligence_) ，允许邮箱智能保护对邮件 (_EnableMailboxIntelligenceProtection_) 采取操作，将隔离指定为检测到的邮件的操作，并使用隔离邮件的默认隔离策略 (我们未使用 _MailboxIntelligenceQuarantineTag_ 参数) 。 [](quarantine-policies.md)
- 启用所有安全提示。

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

有关语法和参数的详细信息，请参阅 [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)。

> [!NOTE]
> 有关指定要用于反网络钓鱼[](quarantine-policies.md)策略的隔离策略的详细说明，请参阅使用 PowerShell 在反网络钓鱼策略中[指定隔离策略](quarantine-policies.md#anti-phishing-policies)。

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>步骤 2：使用 PowerShell 创建防钓鱼规则

若要创建防钓鱼规则，请使用以下语法：

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

本示例创建一个名为"Research Department"的防钓鱼规则，并满足以下条件：

- 该规则与名为"研究隔离"的防钓鱼策略相关联。
- 此规则应用于“研究部门”组中的成员。
- 因为我们没有使用 _Priority_ 参数，所以使用默认优先级。

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

有关语法和参数的详细信息，请参阅 [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)。

### <a name="use-powershell-to-view-anti-phish-policies"></a>使用 PowerShell 查看防钓鱼策略

若要查看现有的防钓鱼策略，请使用以下语法：

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

此示例返回所有防钓鱼策略的摘要列表以及指定的属性。

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

此示例返回名为 Executives 的反网络钓鱼策略的所有属性值。

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

有关语法和参数的详细信息，请参阅 [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy)。

### <a name="use-powershell-to-view-anti-phish-rules"></a>使用 PowerShell 查看防钓鱼规则

若要查看现有的防钓鱼规则，请使用以下语法：

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

此示例返回所有防钓鱼规则的摘要列表以及指定的属性。

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

此示例返回名为 Contoso Executives 的防钓鱼规则的所有属性值。

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

有关语法和参数的详细信息，请参阅 [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)。

### <a name="use-powershell-to-modify-anti-phish-policies"></a>使用 PowerShell 修改防钓鱼策略

除了以下项目外，在 PowerShell 中修改防钓鱼策略时可用的设置与创建策略时相同，如本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) 创建防钓鱼策略一节中所述。

- _MakeDefault_ 开关将指定策略转换为应用于所有人的默认策略 (，优先级始终为最低，并且只有修改 PowerShell 中的防钓鱼策略时) 才能将其删除。

- 如果 **Set-AntiPhishPolicy** cmdlet 没有 Name (，则不能重命名反网络钓鱼) 。  在安全门户中重命名防钓鱼Microsoft 365 Defender，只需重命名防钓鱼 _规则_。

要修改防钓鱼策略，请使用以下语法：

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)。

> [!NOTE]
> 有关指定要用于反网络钓鱼[](quarantine-policies.md)策略的隔离策略的详细说明，请参阅使用 PowerShell 在反网络钓鱼策略中[指定隔离策略](quarantine-policies.md#anti-phishing-policies)。

### <a name="use-powershell-to-modify-anti-phish-rules"></a>使用 PowerShell 修改防钓鱼规则

在 PowerShell 中修改防钓鱼规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。 若要启用或禁用现有防钓鱼规则，请参阅下一节。

否则，在 PowerShell 中修改防钓鱼规则时，其他设置将不可用。 创建规则时可用的设置与本文前面步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) 创建防钓鱼规则一节中所述的设置相同。

要修改防钓鱼规则，请使用以下语法：

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)。

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>使用 PowerShell 启用或禁用防钓鱼规则

在 PowerShell 中启用或禁用反网络钓鱼规则会启用或禁用整个防钓鱼策略 (以及分配的防钓鱼策略策略) 。 无法启用或禁用默认的防钓鱼策略 (它始终应用于所有收件人) 。

若要在 PowerShell 中启用或禁用防钓鱼规则，请使用以下语法：

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

本示例禁用名为"Marketing Department"的防钓鱼规则。

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

下面的示例启用同一规则。

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅[Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule)和[Disable-AntiPhishRule。](/powershell/module/exchange/disable-antiphishrule)

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>使用 PowerShell 设置防钓鱼规则的优先级

可以设置的规则最高优先级值是 0。可以设置的最小优先级值取决于规则的数量。例如，如果有五个规则，则可以使用的优先级值为 0 到 4。更改现有规则的优先级可对其他规则产生级联效应。例如，假设有五个自定义规则（优先级为 0 到 4），如果将某个规则的优先级更改为 2，则优先级为 2 的现有规则将更改为优先级 3，优先级为 3 的规则将更改为优先级 4。

若要在 PowerShell 中设置防钓鱼规则的优先级，请使用以下语法：

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

此示例将名为"Marketing Department"规则的优先级设置为 2：具有小于或等于 2 优先级的所有现有规则的编号将递减 1（它们的优先级编号均递增 1）。

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**注意**：

- 若要在创建新规则的优先级时设置该规则的优先级，请改为使用 **New-AntiPhishRule** cmdlet 上的 _Priority_ 参数。

- 默认防钓鱼策略没有对应的防钓鱼规则，并且始终具有不可修改的优先级值 **Lowest**。

### <a name="use-powershell-to-remove-anti-phish-policies"></a>使用 PowerShell 删除防钓鱼策略

使用 PowerShell 删除防钓鱼策略时，不会删除相应的防钓鱼规则。

若要在 PowerShell 中删除防钓鱼策略，请使用以下语法：

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

此示例删除名为 Marketing Department 的防钓鱼策略。

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy)。

### <a name="use-powershell-to-remove-anti-phish-rules"></a>使用 PowerShell 删除防钓鱼规则

使用 PowerShell 删除防钓鱼规则时，不会删除相应的防钓鱼策略。

若要在 PowerShell 中删除防钓鱼规则，请使用以下语法：

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

此示例删除名为"Marketing Department"的防钓鱼规则。

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证是否成功配置了 Defender for Office 365 中的防钓鱼策略，请执行以下步骤之一：

- 在Microsoft 365 Defender门户中，转到"策略"部分中的&电子邮件&策略&规则威胁策略 \>  \>  \> **""** 防钓鱼"。  验证策略列表、 **策略的 Status** 值及其 **Priority** 值。 若要查看更多详细信息，请从列表中选择策略，方法是单击名称并查看出现的飞出内容中的详细信息。

- 在 Exchange Online PowerShell 中，将 替换为策略或规则的名称，然后运行 \<Name\> 以下命令并验证设置：

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
