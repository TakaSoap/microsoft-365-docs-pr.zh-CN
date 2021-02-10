---
title: Microsoft Defender for Office 365 中的攻击模拟器
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用攻击模拟器在 Microsoft 365 E5 或 Microsoft Defender for Office 365 计划 2 组织中运行模拟网络钓鱼和密码攻击。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 824ee04e2fcf0757a7eb32b48246bf1a1c638926
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175879"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的攻击模拟器

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于** [Microsoft Defender for Office 365 计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)

如果你的组织具有 Microsoft Defender for Office 365 计划 2（包括威胁调查和响应 & [功能](office-365-ti.md)），可以使用安全与合规中心中的攻击模拟器在组织中运行真实的攻击方案。 这些模拟攻击可以帮助你在真正的攻击影响你的最后一线之前识别和查找易受攻击的用户。 阅读本文可了解更多信息。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要打开安全与合规中心，请转到 <https://protection.office.com/>。 攻击模拟器在 **威胁管理攻击** \> **模拟器中可用**。 转到直接进入攻击模拟器，打开 <https://protection.office.com/attacksimulator> 。

- 有关不同 Microsoft 365 订阅中攻击模拟器的可用性详细信息，请参阅 [Microsoft Defender for Office 365 服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

- 您必须是组织管理或 **安全管理员角色组** 的成员。  若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。

- 你的帐户需要配置为使用 MFA (多重身份验证) 在攻击模拟器中创建和管理市场活动。 有关说明，请参阅["设置多重身份验证"。](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)

- 网络钓鱼活动将在 30 天内收集和处理事件。 历史市场活动数据将在你启动市场活动后最多 90 天内可用。

- 攻击模拟和培训相关的数据存储在 Microsoft 365 服务的其他客户数据中。 有关详细信息，请参阅 [Microsoft 365 数据位置](/microsoft-365/enterprise/o365-data-locations)。

- 攻击模拟器没有对应的 PowerShell cmdlet。

## <a name="spear-phishing-campaigns"></a>网络钓鱼活动

*网络钓鱼* 是电子邮件攻击的一个通用术语，它尝试窃取看起来来自合法或受信任的发件人的邮件中的敏感信息。 *网络钓鱼* 是一种目标网络钓鱼攻击，它使用专门针对目标收件人定制的重点和自定义内容 (通常，在攻击者重新识别收件人后) 。

在攻击模拟器中，提供了两种不同类型的网络钓鱼活动：

- **Spear phishing (credentials harvest) ：** the attack tries to tries the recipients to click a URL in the message. 如果用户单击该链接，将要求他们输入其凭据。 如果已设置，则他们被带至以下位置之一：

  - 一个默认页面，说明这只是一个测试，并提供了识别网络钓鱼邮件的提示。

    ![用户单击网络钓鱼链接并输入其凭据时所看到的内容](../../media/attack-simulator-phishing-result.png)

  - 您指定的 (URL) 自定义页面。

- **Spear phishing (attachment)**： the attack tries to tries the recipients to open a .docx or .pdf attachment in the message. 附件包含来自默认网络钓鱼链接的相同内容，但第一句以"开头，你将看到此邮件是打开的最近电子邮件 \<Display Name\> ..."。

> [!NOTE]
> 目前，攻击模拟器中的网络钓鱼活动不会过期。

### <a name="create-a-spear-phishing-campaign"></a>创建网络钓鱼活动

任何钓鱼活动的重要组成部分是发送给目标收件人的电子邮件的外观。 若要创建和配置电子邮件，可以使用以下选项：

- **使用内置电子邮件模板：** 有两个内置模板可用 **：Give Giveaway** 和 Payroll **Update。** 创建和启动市场活动时，可以进一步自定义模板中的部分、所有或无电子邮件属性。

- **创建可重用的电子邮件模板**：创建并保存电子邮件模板后，可以在将来的网络钓鱼活动中再次使用它。 创建和启动市场活动时，可以进一步自定义模板中的部分、所有或无电子邮件属性。

- **在向导中** 创建电子邮件：可以在创建和启动网络钓鱼活动时直接在向导中创建电子邮件。

#### <a name="step-1-optional-create-a-custom-email-template"></a>步骤 1 (可选) ：创建自定义电子邮件模板

如果要使用内置模板之一或直接在向导中创建电子邮件，可以跳过此步骤。

1. 在安全&中心，转到 **威胁管理** \> **攻击模拟器**。

2. 在"模拟攻击"页上的 **"Spear Phishing (Credentials Harvest)** 或 **Spear Phish (Attachment)** 部分中，单击"攻击 **详细信息**"。

   从何处创建模板并不重要。 模板中的可用选项对于这两种类型的网络钓鱼攻击是相同的。

3. 在打开 **的**"攻击详细信息"页的"网络钓鱼模板"部分，**在"创建** 模板"区域中，单击 **"新建模板"。**

4. " **配置网络钓鱼模板"** 向导将启动一个新的飞出控件。 在 **"开始**"步骤中，显示名称模板的唯一名称，然后单击"下一 **步"。**

5. 在 **"配置电子邮件详细信息** "步骤中，配置以下设置：

   - **From (Name)**： the 显示名称 the 显示名称 that's used for the message sender.

   - **发件人 (电子邮件) ：** 发件人的电子邮件地址。

   - **网络钓鱼登录服务器 URL：** 单击下拉列表，然后从列表中选择一个可用的 URL。 这是用户将尝试单击的 URL。 ）这三个选项包括：

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > URL 信誉服务可能会将其中一个或多个 URL 标识为不安全。 在网络钓鱼活动中使用 URL 之前，请检查受支持的 Web 浏览器中 URL 的可用性。

   - **自定义登** 陆页面 URL：输入可选登录页面，如果用户单击网络钓鱼链接并输入其凭据，将在此页面进行登录。 此链接将替换默认登录页面。 例如，如果你有内部意识培训，你可以在此处指定该 URL。

   - **类别**：当前，此设置不会用于 (输入的项都被忽略) 。

   - **主题**： **电子邮件** 的主题字段。

   完成后，单击“下一步”。

6. 在 **"撰写电子邮件** "步骤中，创建电子邮件的邮件正文。 You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code) .

   HTML 格式可以像需要一样简单或复杂。 您可以插入图像和文本，以增强收件人的电子邮件客户端中邮件的可信度。

   - `${username}` 插入收件人的姓名。

   - `${loginserverurl}` 插入上 **一步中的网络钓鱼登录服务器 URL** 值。

   完成后，单击“下一步”。

7. 在"**确认"** 步骤中，单击"**完成"。**

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>步骤 2：创建和启动网络钓鱼活动

1. 在安全&中心，转到 **威胁管理** \> **攻击模拟器**。

2. 在 **"模拟** 攻击"页上，根据要创建的市场活动类型进行以下选择之一：

   - 在 **"网络钓鱼凭据 (** 获取) 部分，单击"启动攻击"**或"攻击** 详细信息启动攻击 \> **"。**

   - 在 **"网络钓鱼 (附件**) ，单击"启动攻击"或"攻击详细信息启动攻击 \> **"。**

3. " **配置网络钓鱼攻击"** 向导从新的飞出控件开始。 在 **"开始** "步骤中，执行以下步骤之一：

   - 在 **"名称** "框中，为显示名称一个唯一名称。 请勿单击 **"使用模板"，** 因为稍后您将在向导中创建电子邮件。

   - 单击 **"使用** 模板"，然后选择内置或自定义电子邮件模板。 选择模板后，根据模板自动填充"名称"框，但可以更改名称。

   > [!div class="mx-imgBorder"]
   > ![网络钓鱼起始页](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   完成后，单击“下一步”。

4. 在 **"目标收件人"** 步骤中，执行下列步骤之一：

   - 单击 **"通讯簿** "以选择 (活动) 或组的收件人。 每个目标收件人都必须有一个 Exchange Online 邮箱。 如果在 **未输入搜索****条件** 的情况下单击"筛选和应用"，将返回所有收件人并添加到活动。

   - 单击 **"** 导入然后文件 **导入** "以将逗号分隔值 (CSV) 或电子邮件地址的行分隔文件中。 每行必须包含收件人的电子邮件地址。

   完成后，单击“下一步”。

5. 在 **"配置电子邮件详细信息** "步骤中，配置以下设置：

   如果在"开始"步骤中选择了模板，则其中大多数值已配置，但您可以更改它们。

   - **From (Name)**： the 显示名称 the 显示名称 that's used for the message sender.

   - **发件人 (电子邮件) ：** 发件人的电子邮件地址。 你可以从组织的电子邮件域输入真实或假的电子邮件地址，也可以输入真实或假的外部电子邮件地址。 您组织的有效发件人电子邮件地址实际上将在收件人的电子邮件客户端中解析。

   - **网络钓鱼登录服务器 URL：** 单击下拉列表，然后从列表中选择一个可用的 URL。 这是用户将尝试单击的 URL。 ）这三个选项包括：

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - 所有 URL 都是有意 http，而不是 https。
     >
     > - URL 信誉服务可能会将其中一个或多个 URL 标识为不安全。 在网络钓鱼活动中使用 URL 之前，请检查受支持的 Web 浏览器中 URL 的可用性。
     >
     > - 您需要选择 URL。 对于 **网络钓鱼** (附件) 活动，可以在下一步骤中删除邮件正文中的链接 (否则，邮件将同时包含链接和附件) 。 

   - **附件类型**：此设置仅在网络钓鱼和附件 (**活动)** 可用。 单击下拉列表并选择 **。DOCX** **或 。列表中的 PDF。**

   - **附件名称**：此设置仅适用于网络钓鱼 (**活动**) 活动。 输入 .docx 或 .pdf 附件的文件名。

   - **自定义登** 陆页面 URL：输入可选登录页面，如果用户单击网络钓鱼链接并输入其凭据，将在此页面进行登录。 此链接将替换默认登录页面。 例如，如果你有内部意识培训，你可以在此处指定该 URL。

   - **主题**： **电子邮件** 的主题字段。

   完成后，单击“下一步”。

6. 在 **"撰写电子邮件** "步骤中，创建电子邮件的邮件正文。 如果在"开始"步骤 **中** 选择了模板，则邮件正文已配置，但您可以对其进行自定义。 You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code) .

   HTML 格式可以像需要一样简单或复杂。 您可以插入图像和文本，以增强收件人的电子邮件客户端中邮件的可信度。

   - `${username}` 插入收件人的姓名。

   - `${loginserverurl}` 插入 **网络钓鱼登录服务器 URL** 值。

   对于 **网络钓鱼 (** 附件) 活动，应删除邮件正文中的链接 (否则，邮件将同时包含链接和附件，并且不会在附件市场活动) 中跟踪链接单击。 

   > [!div class="mx-imgBorder"]
   > ![撰写电子邮件正文](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   完成后，单击“下一步”。

7. 在 **"确认** "步骤中， **单击"完成** "以启动市场活动。 网络钓鱼邮件将传递给目标收件人。

## <a name="password-attack-campaigns"></a>密码攻击活动

*密码攻击* 通常会在攻击者识别一个或多个有效用户帐户后，尝试猜测组织中用户帐户的密码。

在攻击模拟器中，有两种不同类型的密码攻击活动可供你测试用户密码的复杂性：

- 暴力密码 (字典攻击 **) ：** 暴力或字典攻击对用户帐户使用较大的字典密码文件，希望其中一个可以针对一个帐户 (多个密码) 。 错误的密码锁定有助于阻止暴力密码攻击。

  对于字典攻击，你可以指定一个或多个密码来尝试 (手动输入或在上载的文件中) ，也可以指定一个或多个用户。

- **密码攻击***：密码攻击* 对用户帐户列表使用同一个经过仔细考虑的密码， (多个帐户使用一) 。 密码感染攻击比暴力密码攻击更难检测 (当攻击者在数十个或数百个帐户上尝试一个密码时，成功的可能性会提高，而不会降低用户密码锁定错误) 。

  对于密码攻击，只能指定一个要尝试的密码，也可以指定一个或多个用户。

> [!NOTE]
> 攻击模拟器中的密码攻击将用户名和密码基本身份验证请求传递到终结点，因此它们还与其他身份验证方法 (AD FS、密码哈希同步、传递、PingFederate 等) 。 对于启用了 MFA 的用户，即使密码攻击尝试其实际密码，尝试将始终注册为失败 (换句话说，MFA 用户永远不会显示在活动成功尝试计数中) 。  这是预期结果。 MFA 是帮助防止密码攻击的主要方法。

### <a name="create-and-launch-a-password-attack-campaign"></a>创建和启动密码攻击活动

1. 在安全&中心，转到 **威胁管理** \> **攻击模拟器**。

2. 在 **"模拟** 攻击"页上，根据要创建的市场活动类型进行以下选择之一：

   - 在 **"暴力密码 (字典**) 部分，单击"启动攻击"或"攻击详细信息启动攻击 \> **"。**

   - 在"**密码攻击"部分**，单击 **"启动攻击"** 或"**攻击详细信息** \> **启动攻击"。**

3. 配置 **密码攻击** 向导将启动一个新的飞出控件。 在 **"开始**"步骤中，为显示名称输入唯一名称，然后单击"下一 **步"。**

4. 在 **"目标用户"** 步骤中，执行以下步骤之一：

   - 单击 **"通讯簿** "以选择 (活动) 或组的收件人。 每个目标收件人都必须有一个 Exchange Online 邮箱。 如果在 **未输入搜索****条件** 的情况下单击"筛选和应用"，将返回所有收件人并添加到活动。

   - 单击 **"** 导入然后文件 **导入** "以将逗号分隔值 (CSV) 或电子邮件地址的行分隔文件中。 每行必须包含收件人的电子邮件地址。

   完成后，单击“下一步”。

5. 在 **"选择攻击设置** "步骤中，根据市场活动类型选择要执行哪些操作：

   - **暴力密码 (字典)** 攻击：执行下列任一步骤：

     - **手动输入密码**：在 **按 Enter** 添加密码框中，键入密码，然后按 Enter。 根据需要重复执行此步骤（次数不限）。

     - **从字典文件** 上载密码 **：单击"** 上载"以导入每行包含一个密码和一个空最后一行的现有文本文件。 文本文件的大小必须小于或小于 10 MB，并且不能包含超过 30000 个密码。

   - **密码攻击**：在 **密码 () ，输入一** 个密码。

   完成后，单击“下一步”。

6. 在 **"确认** "步骤中， **单击"完成** "以启动市场活动。 您指定的密码将尝试用于指定的用户。

## <a name="view-campaign-results"></a>查看市场活动结果

启动市场活动后，可以在主"模拟攻击"页上检查进度 **和** 结果。

活动市场活动将显示状态栏、已完成百分比值和"已完成 (用户数) 占 (用户数) "计数。 单击 **"刷新** "按钮将更新任何活动市场活动的进度。 还可以单击" **终止"** 停止活动市场活动。

活动完成后，状态将更改为 **攻击已完成**。 可以通过执行以下操作之一查看市场活动的结果：

- 在主 **"模拟攻击"** 页上 **，单击** 活动名称下的"查看报告"。

- 在主 **"模拟攻击"** 页上，单击部分中有关攻击类型的"攻击详细信息"。 在打开 **的** "攻击详细信息"页上，在"攻击历史记录"部分 **选择** 活动。

以上任一操作都会将你带至一个名为"攻击详细信息 **"的页面**。 以下各节介绍了此页上提供的每种市场活动类型的信息。

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Spear Phishing (Credentials Harvest) campaign results

每个市场活动的"攻击详细信息 **"** 页上提供了以下信息：

- 市场活动 (开始日期/时间和结束日期/时间) 持续时间。

- **目标用户总数**

- **成功尝试**：单击链接并输入其凭据 (*用户名和密码* 值的用户) 。

- **总体成功率**：由目标用户总数 **成功尝试**  /  **计算得出的百分比**。

- **最快单击**：启动市场活动后，第一个用户单击链接需要多久。

- **Average Click**： The sum of how long of everyone to click the link divided by the number of users who clicked the link.

- **单击"** 成功率：由单击链接 (/目标用户总数) 计算 **得出的百分比**。

- **最快凭据**：启动市场活动后，第一个用户输入其凭据需要多久。

- **平均凭据**：每个人输入其凭据所用时间的总和除以输入其凭据的用户数。

- **凭据成功** 率：一个百分比， (输入其凭据的用户数/目标) 用户 **总数**。

- 显示每天单击的链接 **和****凭据提供的号码** 的条形图。

- 一个圆形图 **，显示活动** 单击的链接 **、提供的凭据****和** 无百分比。

- " **遭到入侵的用户** "部分列出了单击链接的用户的详细信息：

  - 用户的电子邮件地址

  - 他们单击链接的日期/时间。

  - 客户端 IP 地址。

  - 有关用户版本的 Windows 和 Web 浏览器的详细信息。

  可以单击 **"导出** "将结果导出到 CSV 文件。

### <a name="spear-phishing-attachment-campaign-results"></a>网络钓鱼 (活动) 附件

每个市场活动的"攻击详细信息 **"** 页上提供了以下信息：

- 市场活动 (开始日期/时间和结束日期/时间) 持续时间。

- **目标用户总数**

- **成功尝试**：在预览版中打开或下载并打开 (用户数) 。

- **总体成功率**：由目标用户总数 **成功尝试**  /  **计算得出的百分比**。

- **最快附件打开时间**：启动活动后第一个用户打开附件所花时间。

- **平均附件打开** 时间：每个人打开附件所花时间的总和除以打开附件的用户数。

- **附件打开成功率**：由打开附件 (用户数/目标) 用户总数计算 **得出的百分比**。

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>暴力密码 (字典攻击) 结果

每个市场活动的"攻击详细信息 **"** 页上提供了以下信息：

- 市场活动 (开始日期/时间和结束日期/时间) 持续时间。

- **目标用户总数**

- **成功尝试**：发现正在使用指定密码之一的用户数。

- **总体成功率**：由目标用户总数 **成功尝试**  /  **计算得出的百分比**。

- " **受到威胁的用户"** 部分列出了受影响用户的电子邮件地址。 可以单击 **"导出** "将结果导出到 CSV 文件。

### <a name="password-spray-attack-campaign-results"></a>密码攻击活动结果

每个市场活动的"攻击详细信息 **"** 页上提供了以下信息：

- 市场活动 (开始日期/时间和结束日期/时间) 持续时间。

- **目标用户总数**

- **成功尝试**：找到使用指定密码的用户数。

- **总体成功率**：由目标用户总数 **成功尝试**  /  **计算得出的百分比**。
