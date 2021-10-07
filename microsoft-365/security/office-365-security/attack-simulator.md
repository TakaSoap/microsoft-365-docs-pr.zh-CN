---
title: 安全与合规中心&模拟器
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & Complance 中心的攻击模拟器在 Microsoft 365 E5 或 Microsoft Defender for Office 365 计划 2 组织中运行模拟网络钓鱼和密码攻击。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 73dcc3c8fbe121ee18f16d1d806718b3bb60923e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60149786"
---
# <a name="attack-simulator-in-the-security--compliance-center"></a>安全与合规中心&模拟器

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于 Microsoft** [Defender for Office 365计划 2](defender-for-office-365.md)

如果你的组织拥有 Microsoft Defender for Office 365 Plan 2（[](office-365-ti.md)包括威胁调查和响应功能）。可以使用安全 & 合规中心中的攻击模拟器在组织中运行真实的攻击方案。 这些模拟攻击可以帮助你在真实攻击影响你的最后一线之前识别和查找易受攻击的用户。 阅读本文可了解更多信息。

> [!NOTE]
>
> 攻击模拟器（如本文中所述）现在是只读的，已替换为位于 的Microsoft 365 Defender 门户中电子邮件&**协作** 节点中的攻击模拟培训 <https://security.microsoft.com> 。 有关详细信息，请参阅使用攻击 [模拟培训入门](attack-simulation-training-get-started.md)。
>
> 已禁用从此版本的攻击模拟器启动新模拟的能力。 但是，您仍可以访问报告，直到 2021 年 4 月 24 日。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要打开安全与合规中心，请转到 <https://protection.office.com/>。 攻击模拟器位于威胁管理 **攻击** \> **模拟器 中**。 若要直接转到攻击模拟器，请打开 <https://protection.office.com/attacksimulator> 。

- 有关跨不同用户订阅提供攻击模拟器Microsoft 365，请参阅[Microsoft Defender for Office 365服务说明](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

- 您必须是组织管理或 **安全管理员****角色组** 的成员。 若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。

- 你的帐户需要配置为使用 MFA (多重) ，以在攻击模拟器中创建和管理市场活动。 有关说明，请参阅 [设置多重身份验证](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。

- 攻击模拟器仅适用于基于云的邮箱。

- 网络钓鱼活动将在 30 天内收集和处理事件。 历史市场活动数据将在你启动市场活动后最多 90 天内可用。

- 攻击模拟和培训相关的数据与其他客户数据一起存储，Microsoft 365服务。 有关详细信息，请参阅[Microsoft 365位置](../../enterprise/o365-data-locations.md)。

- 攻击模拟器没有对应的 PowerShell cmdlet。

## <a name="spear-phishing-campaigns"></a>Pear phishing campaigns

*网络钓鱼* 是电子邮件攻击的一个通用术语，它尝试窃取看起来来自合法或受信任的发件人的邮件中的敏感信息。 网络网络钓鱼是一种有针对性的网络钓鱼攻击，它使用专为目标收件人定制的重点和自定义内容 (通常发生在攻击者对收件人重新进行) 之后。

在攻击模拟器中，提供了两种不同类型的钓鱼活动：

- **Spear phishing (credentials harvest)**： the attack tries to tries the recipients to click a URL in the message. 如果用户单击该链接，则要求他们输入其凭据。 如果这样做，他们会被带至以下位置之一：

  - 说明这只是一个测试的默认页面，并提供了识别网络钓鱼邮件的提示。

    ![用户单击网络钓鱼链接并输入其凭据时会看到什么。](../../media/attack-simulator-phishing-result.png)

  - 自定义页面 (指定的) URL。

- **Spear phishing (attachment)**： The attack tries to tries the recipients to open a .docx or .pdf attachment in the message. 附件包含来自默认网络钓鱼链接的相同内容，但第一句以" 开头，你将看到此邮件为打开 \<Display Name\> 的最近电子邮件..."。

> [!NOTE]
> 目前，攻击模拟器中的钓鱼活动不会到期。

### <a name="create-a-spear-phishing-campaign"></a>创建钓鱼活动

任何网络钓鱼活动的一个重要部分是发送给目标收件人的电子邮件的外观。 若要创建和配置电子邮件，有以下选项：

- **使用内置电子邮件模板**：有两个内置模板可用 **：Giveaway 和** **Payroll Update**。 创建和启动市场活动时，可以进一步自定义模板中的一些、全部或全部电子邮件属性，或没有任何电子邮件属性。

- **创建可重用的电子邮件模板**：创建并保存电子邮件模板后，可以在将来的网络钓鱼活动中再次使用它。 创建和启动市场活动时，可以进一步自定义模板中的一些、全部或全部电子邮件属性，或没有任何电子邮件属性。

- **在向导中创建** 电子邮件：可以在创建和启动网络钓鱼活动时直接在向导中创建电子邮件。

#### <a name="step-1-optional-create-a-custom-email-template"></a>步骤 1 (可选) ：创建自定义电子邮件模板

如果要使用其中一个内置模板或直接在向导中创建电子邮件，可以跳过此步骤。

1. 在安全与&中心，转到威胁 **管理** \> **攻击模拟器**。

2. 在"**模拟** 攻击"页面上，**在"Spear Phishing (Credentials Harvest) "** 或 **"Spear Phishing (Attachment) "** 部分中，单击"**攻击详细信息"。**

   在哪里创建模板并不重要。 模板中的可用选项对于这两种类型的网络钓鱼攻击是相同的。

3. 在打开 **的"** 攻击详细信息"页的"网络钓鱼模板"部分，**在"创建** 模板"区域中，单击"新建 **模板"。**

4. " **配置网络钓鱼模板"** 向导将启动一个新的飞出控件。 在"**开始**"步骤中，为模板显示名称一个唯一模板，然后单击"下一步 **"。**

5. 在" **配置电子邮件详细信息** "步骤中，配置以下设置：

   - **From (Name)**： the 显示名称 that's used for the message sender.

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
     > URL 信誉服务可能会将其中一个或多个 URL 标识为不安全。 在网络钓鱼活动中使用该 URL 之前，请检查 URL 在受支持的 Web 浏览器中的可用性。

   - **自定义登陆页面 URL：** 输入可选登陆页面，如果用户单击网络钓鱼链接并输入其凭据，将在此进行登录。 此链接将替换默认登陆页面。 例如，如果你有内部意识培训，可以在此处指定该 URL。

   - **类别**：当前，此设置不用于 (输入的项都) 。

   - **主题**： **电子邮件** 的主题字段。

   完成后，单击“**下一步**”。

6. 在 **"撰写电子邮件** "步骤中，创建电子邮件的邮件正文。 You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code) .

   HTML 格式可以像您所需的一样简单或复杂。 您可以插入图像和文本，以增强收件人的电子邮件客户端中邮件的可信度。

   - `${username}` 插入收件人的姓名。

   - `${loginserverurl}` 插入上 **一步中的网络钓鱼登录服务器 URL** 值。

   完成后，单击“**下一步**”。

7. 在"**确认"** 步骤中，单击"完成 **"。**

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>步骤 2：创建和启动网络钓鱼活动

1. 在安全与&中心，转到威胁 **管理** \> **攻击模拟器**。

2. 在 **"模拟攻击** "页上，根据要创建的市场活动类型进行以下选择之一：

   - 在 **"Spear 网络钓鱼 (凭据** 获取) 部分中，单击"启动攻击"或单击"攻击详细信息启动攻击 \> **"。**

   - 在 **"Spear Phishing (Attachment) "** 部分中，单击"启动攻击"或 **单击"****攻击详细信息** 启动攻击 \> **"。**

3. " **配置网络钓鱼攻击"** 向导从新的飞出控件开始。 在 **"开始** "步骤中，执行以下步骤之一：

   - 在" **名称** "框中，为显示名称输入唯一的名称。 不要单击" **使用模板"，** 因为稍后您将在向导中创建电子邮件。

   - 单击 **"使用** 模板"，然后选择内置或自定义电子邮件模板。 选择模板后，"名称"框将基于模板自动填充，但您可以更改名称。

   > [!div class="mx-imgBorder"]
   > ![网络钓鱼起始页。](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   完成后，单击“**下一步**”。

4. 在 **"目标收件人"** 步骤中，执行下列步骤之一：

   - 单击 **"通讯簿** "以选择 (活动) 或组的收件人。 每个目标收件人必须具有一个Exchange Online邮箱。 如果在 **未输入搜索****条件** 的情况下单击"筛选"和"应用"，将返回所有收件人并添加到活动。

   - 单击 **"** 导入 **"，** 然后单击"文件导入"以 (CSV) 或以行分隔的电子邮件地址文件导入逗号分隔值。 每行必须包含收件人的电子邮件地址。

   完成后，单击“**下一步**”。

5. 在" **配置电子邮件详细信息** "步骤中，配置以下设置：

   如果在"开始"步骤 **中** 选择了模板，则大部分这些值已配置，但您可以更改它们。

   - **From (Name)**： the 显示名称 that's used for the message sender.

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
     > - 所有 URL 都是有意的 http，而不是 https。
     >
     > - URL 信誉服务可能会将其中一个或多个 URL 标识为不安全。 在网络钓鱼活动中使用该 URL 之前，请检查 URL 在受支持的 Web 浏览器中的可用性。
     >
     > - 您需要选择 URL。 对于 **"Spear Phishing (Attachment) "** 市场活动，您可以在下一步 (中删除邮件正文中的链接，否则邮件将包含链接和附件) 。 

   - **附件类型**：此设置仅在网络网络钓鱼和附件 (**活动中)** 可用。 单击下拉列表， **然后从**.DOCX.PDF **选择** "选项"。

   - **附件名称**：此设置仅在网络网络钓鱼和附件 (**活动中)** 可用。 输入附件或附件.docx.pdf文件名。

   - **自定义登陆页面 URL：** 输入可选登陆页面，如果用户单击网络钓鱼链接并输入其凭据，将在此进行登录。 此链接将替换默认登陆页面。 例如，如果你有内部意识培训，可以在此处指定该 URL。

   - **主题**： **电子邮件** 的主题字段。

   完成后，单击“**下一步**”。

6. 在 **"撰写电子邮件** "步骤中，创建电子邮件的邮件正文。 如果在"开始"步骤 **中** 选择了模板，则消息正文已配置，但您可以对其进行自定义。 You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code) .

   HTML 格式可以像您所需的一样简单或复杂。 您可以插入图像和文本，以增强收件人的电子邮件客户端中邮件的可信度。

   - `${username}` 插入收件人的姓名。

   - `${loginserverurl}` 插入 **网络钓鱼登录服务器 URL** 值。

   对于 **Pear Phishing (Attachment)** campaign， you should remove the link from the body of the message (otherwise， the message will contain both a link **and** an attachment， and link clicks aren't tracked in an attachment campaign) .

   > [!div class="mx-imgBorder"]
   > ![撰写电子邮件正文。](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   完成后，单击“**下一步**”。

7. 在" **确认"** 步骤中，单击 **"完成** "以启动市场活动。 网络钓鱼邮件将传递到目标收件人。

## <a name="password-attack-campaigns"></a>密码攻击活动

*密码攻击* 通常会在攻击者标识一个或多个有效用户帐户后，尝试猜测组织中用户帐户的密码。

在攻击模拟器中，有两种不同类型的密码攻击活动可供你测试用户密码的复杂性：

- 暴力密码 (字典攻击 **) ：** 暴力或字典攻击在用户帐户上使用一个大型密码字典文件，希望其中一个可以针对一个帐户 (多个密码) 。 不正确的密码锁定有助于阻止暴力密码攻击。

  对于字典攻击，你可以指定一个或多个密码来尝试手动输入 (或上传的文件) ，你可以指定一个或多个用户。

- **密码攻击**：密码 *攻击* 针对用户帐户列表使用同一个仔细考虑的密码， (一个密码针对许多) 。 密码感染攻击比暴力密码攻击更难检测 (攻击者在数十个或数百个帐户上尝试一个密码时，成功的可能性会增大，而不会消除用户错误的密码锁定) 。

  对于密码攻击，你只能指定一个要尝试的密码，并且可以指定一个或多个用户。

> [!NOTE]
> 攻击模拟器中的密码攻击将用户名和密码基本身份验证请求传递到终结点，因此它们还与其他身份验证方法 (AD FS、密码哈希同步、传递、PingFederate 等) 。 对于启用了 MFA 的用户，即使密码攻击尝试其实际密码，尝试将始终注册为失败 (换句话说，MFA 用户永远不会显示在活动) 的成功尝试计数中。  这是预期结果。 MFA 是帮助防止密码攻击的主要方法。

### <a name="create-and-launch-a-password-attack-campaign"></a>创建并启动密码攻击活动

1. 在安全与&中心，转到威胁 **管理** \> **攻击模拟器**。

2. 在 **"模拟攻击** "页上，根据要创建的市场活动类型进行以下选择之一：

   - 在 **"暴力密码和** 字典 (攻击) ，单击"启动攻击"**或单击"** 攻击 **详细信息** 启动攻击 \> **"。**

   - 在"**密码攻击"部分**，单击 **"启动攻击"** 或单击"**攻击详细信息** \> **启动攻击"。**

3. 配置 **密码攻击** 向导将启动一个新的飞出控件。 在"**开始**"步骤中，为显示名称输入唯一名称，然后单击"下一 **步"。**

4. 在 **"目标用户"** 步骤中，执行下列步骤之一：

   - 单击 **"通讯簿** "以选择 (活动) 或组的收件人。 每个目标收件人必须具有一个Exchange Online邮箱。 如果在未输入 **搜索****条件** 的情况下单击"筛选"和"应用"，将返回所有收件人并添加到活动。

   - 单击 **"** 导入 **"，** 然后单击"文件导入"，以 (CSV) 或电子邮件地址的行分隔文件导入逗号分隔值。 每行必须包含收件人的电子邮件地址。

   完成后，单击“**下一步**”。

5. 在 **"选择攻击设置"** 步骤中，根据市场活动类型选择要执行哪些操作：

   - **暴力密码 (字典) ：** 执行以下步骤之一：

     - **手动输入密码**：在 **"按 Enter 添加密码"框中** ，键入密码，然后按 Enter。 根据需要重复执行此步骤（次数不限）。

     - **Upload词典文件添加** 密码：单击"Upload"导入现有文本文件，其中包含每行一个密码和一个空最后一行。 文本文件的大小必须小于或小于 10 MB，并且不能超过 30000 个密码。

   - **密码攻击**：在 **密码 () 攻击框中使用** 的密码，输入一个密码。

   完成后，单击“**下一步**”。

6. 在" **确认"** 步骤中，单击 **"完成** "以启动市场活动。 指定的密码将尝试用于指定的用户。

## <a name="view-campaign-results"></a>查看市场活动结果

启动市场活动后，可以在主"模拟攻击"页面上查看 **进度和** 结果。

活动市场活动将显示状态栏、完成的百分比值和"已完成 (用户数)  (用户数) "计数。 单击 **"刷新** "按钮将更新任何活动市场活动的进度。 还可以单击"终止 **"** 停止活动市场活动。

市场活动完成后，状态将更改为 **"攻击已完成"。** 可以通过执行以下操作之一查看市场活动的结果：

- 在主" **模拟攻击"** 页上， **单击活动** 名称下的"查看报告"。

- 在主" **模拟攻击"** 页面上，单击 **部分中的"** 攻击详细信息"，了解攻击类型。 在打开 **的"** 攻击详细信息"页面上，选择"攻击 **历史记录"部分中的** 活动。

以上任一操作都会将你带至名为"攻击详细信息 **"的页面**。 以下各节介绍了此页面上提供的每种市场活动类型的信息。

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Spear Phishing (Credentials Harvest) campaign results

每个市场活动的"攻击 **详细信息** "页面上提供了以下信息：

- 市场活动 (/时间和结束日期/时间) 持续时间。

- **目标用户总数**

- **成功尝试**：单击链接并输入其凭据的用户 (*用户名和密码* 值) 。

- **总体成功** 率：成功尝试总目标用户数  /  **计算出的百分比**。

- **最快单击**：启动市场活动后，第一个用户单击链接所用时间。

- **平均单击** 次数：单击链接所用时间与单击链接的用户数之和。

- **单击成功率**：单击链接的用户数 (用户数/目标用户总数) 计算 **得出的百分比**。

- **最快凭据**：启动市场活动后，第一个用户输入其凭据所用时间。

- **平均凭据**：每个人输入其凭据所用时间与输入凭据的用户数之和。

- **凭据成功** 率：由 (凭据的用户数/目标) 计算 **得出的百分比**。

- 显示单击的链接 **和****凭据提供的号码** 每天的条形图。

- 一个圆形图，显示活动的 **单击链接**、**提供凭据** 和无百分比。

- " **遭到入侵的用户** "部分列出了单击链接的用户的详细信息：

  - 用户的电子邮件地址

  - 用户单击链接时的日期/时间。

  - 客户端 IP 地址。

  - 有关用户版本的 web 浏览器Windows的详细信息。

  可以单击 **"导出** "将结果导出到 CSV 文件。

### <a name="spear-phishing-attachment-campaign-results"></a>Spear Phishing (Attachment) campaign results

每个市场活动的"攻击 **详细信息** "页面上提供了以下信息：

- 市场活动 (/时间和结束日期/时间) 持续时间。

- **目标用户总数**

- **成功尝试**：在预览版中打开或下载并打开 (用户数) 。

- **总体成功** 率：成功尝试总目标用户数  /  **计算出的百分比**。

- **最快附件打开时间**：启动市场活动后第一个用户打开附件所花时间。

- **平均附件打开时间**：每个人打开附件所花时间与打开附件的用户数之和。

- **附件打开成功率**：由打开附件 (的用户数/目标) 用户 **总数计算得出的百分比**。

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>暴力密码 (字典) 攻击"市场活动结果

每个市场活动的"攻击 **详细信息** "页面上提供了以下信息：

- 市场活动 (/时间和结束日期/时间) 持续时间。

- **目标用户总数**

- **成功尝试**：发现使用指定密码之一的用户数。

- **总体成功** 率：成功尝试总目标用户数  /  **计算出的百分比**。

- " **遭到入侵的用户** "部分列出了受影响用户的电子邮件地址。 可以单击 **"导出** "将结果导出到 CSV 文件。

### <a name="password-spray-attack-campaign-results"></a>密码化攻击活动结果

每个市场活动的"攻击 **详细信息** "页面上提供了以下信息：

- 市场活动 (/时间和结束日期/时间) 持续时间。

- **目标用户总数**

- **成功尝试**：发现使用指定密码的用户数。

- **总体成功** 率：成功尝试总目标用户数  /  **计算出的百分比**。
