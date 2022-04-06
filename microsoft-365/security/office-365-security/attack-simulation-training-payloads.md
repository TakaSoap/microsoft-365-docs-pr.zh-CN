---
title: 创建用于攻击模拟训练的自定义负载
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: 管理员可以了解如何在 Microsoft Defender for Office 365 计划 2 中为攻击模拟培训创建自定义负载。
ms.technology: mdo
ms.openlocfilehash: d670236aa81f4b5086263a75bbeceb8ca7e1e25f
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63679755"
---
# <a name="create-custom-payloads-for-attack-simulation-training-in-defender-for-office-365"></a>在 Defender for Office 365 中为攻击模拟培训创建自定义负载

**适用于 Microsoft** [Defender for Office 365计划 2](defender-for-office-365.md)

在攻击模拟培训中， _有效_ 负载是向模拟用户呈现的网络钓鱼电子邮件和网页。 Microsoft 365 E5或 Microsoft Defender for Office 365 计划 2 中的攻击模拟培训为可用的社交工程技术提供了可靠的内置有效负载目录。 但是，你可能希望创建更适用于你的组织的自定义有效负载。

本文介绍如何在攻击模拟培训中创建自己的有效负载。 可以在以下位置创建自定义有效负载：

- "**有效负载"** 选项卡：<https://security.microsoft.com>在 Microsoft 365 Defender门户中，转到"电子邮件&**协作** \> **攻击模拟培训** \> **有效负载"** 选项卡。若要直接转到"**有效负载"** 选项卡，请使用 <https://security.microsoft.com/attacksimulator?viewid=payload>。
- 创建模拟期间：可以在模拟创建向导的第三 (选择有效负载) 创建自定义负载。 有关详细信息，请参阅在 [Defender for Office 365 中模拟网络钓鱼Office 365](attack-simulation-training.md)。

有关攻击模拟培训的入门信息，请参阅使用 [攻击模拟培训入门](attack-simulation-training-get-started.md)。

> [!NOTE]
> 某些商标、徽标、符号、签名和其他源标识符受到当地、州、联邦法规和法律的保护。 未经授权使用此类指示器可能会使用户遭受处罚，包括罚款。 虽然这不是一个广泛列表，但其中包括"百科百科"、"Vice Vice"和"一流"（该名称为"一家"）、"社会保险局"、"一家"和"Medicaid"、美国国内收入服务和"美国商务部"。 除了这些类别的商标之外，使用和修改任何第三方商标会带来固有风险。 在有效负载中使用自己的商标和徽标的风险较低，尤其是在组织允许使用的情况下。 如果对创建或配置负载时适合使用或不适合使用的任何进一步问题，请咨询法律顾问。

## <a name="create-a-payload"></a>创建有效负载

单击"创建 ![有效负载"图标后。](../../media/m365-cc-sc-create-icon.png) **从攻击模拟** 培训的"**有效** 负载"选项卡或模拟创建向导的 **[](attack-simulation-training.md#select-a-payload)**"选择有效负载"页上创建有效负载，有效负载创建向导将启动并在此部分中进行介绍。

### <a name="select-a-payload-type"></a>选择有效负载类型

在 **"选择类型** "页上，当前可以选择的唯一值是 **"电子邮件"**。

单击“**下一步**”。

### <a name="select-a-social-engineering-technique"></a>选择社交工程技术

在 **"选择技术**"页上，可用的选项与模拟创建向导中的"[](attack-simulation-training.md#select-a-social-engineering-technique)选择技术"页上的选项相同：

- **凭据获取**
- **恶意软件附件**
- **附件中的链接**
- **链接到恶意软件**
- **按 URL 的驱动器**

完成后，单击“**下一步**”。

### <a name="name-and-describe-the-payload"></a>命名和描述有效负载

在" **有效负载名称** "页上，配置以下设置：

- **名称**：输入有效负载的唯一描述性名称。
- **说明**：输入有效负载的可选详细说明。

完成后，单击“**下一步**”。

## <a name="configure-the-payload"></a>配置有效负载

在 **"配置有效负载** "页上，可以生成有效负载了。 许多可用设置由你在"选择技术"页上选择的内容决定 (例如，链接与附件) 。

- **发件人详细信息** 部分：配置以下设置：
  - **From name**
  - **Use first name as 显示名称**： By default， this setting is not selected.
  - **From email**： If you choose an internal email address for your payload's sender， the payload will appear to come from a fellow employee. 此发件人电子邮件地址将提高用户对有效负载的敏感性，并帮助员工了解内部威胁的风险。
  - **电子邮件主题**

- **附件详细信息** 部分：仅在"选择技术"页上选择了"恶意软件附件"、"附件中的链接"或"链接到恶意软件"**时，****此部分才** 可用。 配置以下设置：
  - **命名附件**
  - **选择附件类型**：目前，唯一可用的值为 **Docx**。

- **"附件链接**"部分：仅在"选择技术"页上选择了"链接到恶意软件"**时，****此部分才** 可用。 在 **"选择** 您希望成为恶意软件附件的 URL"链接框中，选择一个可用的 URL (与"网络钓鱼链接"部分所述的相同 URL) 。

  稍后，你将在邮件正文中嵌入 URL。

- **网络钓鱼链接** 部分：只有选择了"选择技术"页面上的"凭据获取"、附件中的链接或"路路 **URL**"时，此部分 **才** 可用。

  对于 **"凭据** 获取"或"驱动器到 **URL**"，框名称为"选择您希望成为网络钓鱼链接 **的 URL"**。 稍后，你将在邮件正文中嵌入 URL。

  对于 **"附件中** 的链接"，框的名称为"在此附件中选择您希望成为网络钓鱼链接 **的 URL"**。 稍后，你将在附件中嵌入 URL。

  选择一个可用的 URL 值：
  
  - <https://www.mcsharepoint.com>
  - <https://www.attemplate.com>
  - <https://www.doctricant.com>
  - <https://www.mesharepoint.com>
  - <https://www.officence.com>
  - <https://www.officenced.com>
  - <https://www.officences.com>
  - <https://www.officentry.com>
  - <https://www.officested.com>
  - <https://www.prizegives.com>
  - <https://www.prizemons.com>
  - <https://www.prizewel.com>
  - <https://www.prizewings.com>
  - <https://www.shareholds.com>
  - <https://www.sharepointen.com>
  - <https://www.sharepointin.com>
  - <https://www.sharepointle.com>
  - <https://www.sharesbyte.com>
  - <https://www.sharession.com>
  - <https://www.sharestion.com>
  - <https://www.templateau.com>
  - <https://www.templatent.com>
  - <https://www.templatern.com>
  - <https://www.windocyte.com>

  > [!NOTE]
  > URL 信誉服务可能会将其中一个或多个 URL 标识为不安全。 在模拟中使用该 URL 之前，请检查 URL 在支持的 Web 浏览器中的可用性。 有关详细信息，请参阅 Google 网页浏览阻止的网络钓鱼[保险箱 URL](attack-simulation-training-faq.md#phishing-simulation-urls-blocked-by-google-safe-browsing)。

- **附件内容** 部分：仅在"选择技术"页上选择了"附件中的 **链接** " **时，此部分才** 可用。

  可以使用格式文本编辑器在文件附件有效负载中创建内容。

  使用 **网络钓鱼链接控件** 将以前选择的网络钓鱼 URL 添加到附件中。

- 常见设置：
  - **添加 (标记)**
  - **主题**：可用值为：**帐户** 激活、帐户验证、计费、清理 **邮件**、**已接收文档**、**费用**、**传真**、财务 **报告**、**传入邮件**、**发票**、**项目** 接收、登录 **通知****、已接收** 邮件 **、其他**、**密码**、**付款**、工资单、**个性化优惠**、**隔离**、**Remote Work**、**Review Message**、**Security Update**、**Service Suspended**、**Signature Required**、**Upgrade Mailbox 存储**、**Verify mailbox** 或 **Voicemail**。
  - **品牌**：可用值为：**American Express**、**Capital One**、**DHL**、**DocuSign**、**Dropbox、****Facebook**、**First American**、**Microsoft**、**Netflix**、**Scotiabank**、**SendGrid**、**Stewart Title**、**Tesco**、**Wells Fargo**、**Syrinx Cloud** **或其他**。
  - **行业**：可用值包括：**银行**、商业服务、**消费者** 服务、**教育**、**能源**、**建筑**、**咨询**、**金融服务**、**政府**、医疗、**保险**、**法律**、**Courier 服务**、**IT**、**医疗保健、****制造**、**零** 售、**电信**、**房地产****或其他**。
  - **当前事件**：可用值为 **Yes** 或 **No**。
  - **中国**：可用值为 **"是** "或" **否"**。

- **语言** 部分：选择有效负载的语言。 可用值包括：**英语**、**西班牙语**、**德语**、**日语**、**法语**、葡萄牙语、**荷兰语**、**意大利语**、瑞典语、中文 **(简体)**、挪威 **语 Bokmål**、**波兰** 语、**俄语**、**芬兰语**、**朝鲜** 语、**土耳其** 语 **、匈牙利语**、**希伯来** 语、**泰** 语、**阿拉伯语****、越南语****、斯洛伐克** 语， **希腊语**、**印度尼西亚****语、罗马尼亚****语、斯洛文尼亚语**、**克罗地亚** 语、**加泰罗尼亚** 语或其他 **语**。

- **电子邮件** 部分：

  - 可以单击" **导入电子邮件** "，然后单击" **选择文件** "导入现有的纯文本邮件文件。

  - 在 **"文本** "选项卡上，可以使用格式文本编辑器创建电子邮件有效负载。

    - 使用 **动态标记** 控件通过插入可用标记来个性化设置每个用户的电子邮件：
      - **插入** 名称：在邮件正文中添加的值为 `${userName}`。
      - **插入** 电子邮件：在邮件正文中添加的值为 `${emailAddress}`。

      ![Microsoft Defender for Office 365 攻击模拟培训中有效负载创建向导中的配置有效负载页面上的电子邮件Office 365。](../../media/attack-sim-training-payloads-configure-payload-email-message.png)

      **网络钓鱼链接** 控制：只有在"选择技术"页上选择了"凭据获取"、附件中的链接或"按 **URL**"时，此 **控件才** 可用。 使用此控件插入之前在"网络钓鱼链接" **部分选择的 URL** 。

      **恶意软件附件链接** 控件：只有在"选择技术"页上选择了"链接到恶意软件"时，此 **控件才** 可用。 使用此控件插入之前在"附件链接" **部分选择的** URL。

      如果单击" **网络钓鱼链接"** 或" **恶意软件附件** 链接"，将打开一个对话框，要求您命名该链接。 完成后，单击"确认 **"**。

      在邮件正文中添加的值 ("代码"选项卡上) 为 。 `<a href="${phishingUrl}" target="_blank">Name value you specified</a>`

  - 在" **代码** "选项卡上，您可以直接查看和修改 HTML 代码。 格式设置和其他控件（ **如动态标记** 和 **网络钓鱼链接** 或恶意软件 **附件链接）** 不可用。

  - 只有在 **"选择技术**"页上选择了"凭据获取"、"链接到恶意软件"或"按 **URL**"时，"将电子邮件中所有链接替换为网络钓鱼链接"**开关才可用**。 此切换可通过将邮件中所有链接替换为以前选定的网络钓鱼链接或附件 URL  的链接 **来节省时间**。 为此，将设置切换为打开图标![上的切换。](../../media/scc-toggle-on.png)

完成后，单击“**下一步**”。

## <a name="add-indicators-to-phishing-clues"></a>向网络钓鱼线索添加指示器

> [!NOTE]
> 如果在"选择技术"页上选择了"恶意软件附件"或 **"链接到恶意软件"，** 则 **指示器** 不可用。

指示器可帮助员工完成攻击模拟，以识别网络钓鱼邮件的告知信号。

在" **添加指示器"** 页上，单击" **添加指示器"**。 在出现的飞出菜单上，配置以下设置：

- **指示器名称和****指示器位置**：这些值相互关联。 可以将指示器放置在何处取决于指示器本身。 下表介绍了可用值：

  |指示器名称|指示器位置|
  |---|---|
  |**附件类型**|邮件正文|
  |**分散注意力的详细信息**|邮件正文|
  |**域欺骗**|邮件正文 <p> 从电子邮件地址|
  |**通用问候语**|邮件正文|
  |**百万人次吸引力**|邮件正文|
  |**不一致**|邮件正文|
  |**缺少发件人详细信息**|邮件正文|
  |**法律语言**|邮件正文|
  |**有限时间优惠**|邮件正文|
  |**徽标品牌或过时品牌**|邮件正文|
  |**模拟工作或业务流程**|邮件正文|
  |**无/最小品牌打造**|邮件正文|
  |**以好友、同事、主管或权威图显示**|邮件正文|
  |**请求敏感信息**|邮件正文|
  |**安全指示器和图标**|邮件正文 <p> 邮件主题|
  |**发件人显示名称电子邮件地址**|From name <p> 从电子邮件地址|
  |**紧急感**|邮件正文 <p> 邮件主题|
  |**拼写和语法错误**|邮件正文 <p> 邮件主题|
  |**威胁语言**|邮件正文 <p> 邮件主题|
  |**太好，无法成为真正的产品/服务**|邮件正文|
  |**非专业设计或格式**|邮件正文|
  |**URL 超链接**|邮件正文|
  |**你特别**|邮件正文|
  
  此列表是为包含网络钓鱼邮件中最常见的线索而提供的。

  如果您选择电子邮件主题或邮件正文作为指示器的位置，则" **选择** 文本"按钮可用。 单击此按钮可选择您希望指示器显示的邮件主题或邮件正文中的文本。 完成后，单击"选择 **"**。

  ![要添加到攻击模拟培训的有效负载创建向导中的指示器的邮件正文中的所选文本位置。](../../media/attack-sim-training-payloads-add-indicators-select-location.png)

  - **指示器** 描述：可以接受指示器的默认说明，也可以自定义它。

  - **指示器预览**：若要了解当前指示器的外观，请单击此部分。

  完成后，单击"添加 **"**

重复本节中的步骤以添加多个指示器。

若要编辑现有指示器，请从列表中选择它，然后单击"编辑指示器 ![图标"。](../../media/m365-cc-sc-edit-icon.png) **编辑有效负载**。

若要删除现有指示器，请从列表中选择它，然后单击"删除 ![图标"。](../../media/m365-cc-sc-delete-icon.png) **删除**。

完成后，单击“**下一步**”。

## <a name="review-payload"></a>查看有效负载

在 **"查看有效** 负载"页上，你可以查看有效负载的详细信息。

单击" ![发送测试"图标。](../../media/m365-cc-sc-send-icon.png) **发送测试** 按钮，向自己发送有效负载电子邮件 (当前登录的用户) 检查。

单击预览 ![指示器图标。](../../media/m365-cc-sc-open-icon.png) **预览指示器** 按钮在预览飞出控件中打开有效负载。 预览包括你创建的所有有效负载指示器。

在主 **"审阅有效** 负载"页上，可以选择每个部分中的"编辑"以修改部分中的设置。 或者，可以单击“**返回**”或选择向导中的特定页面。

完成后，请单击“**提交**”。 在出现的确认页面上，单击“**完成**”。

![查看攻击门户中攻击模拟培训中的Microsoft 365 Defender页面。](../../media/attack-sim-training-payloads-review-payload.png)

> [!IMPORTANT]
> 你创建的负载将具有 **Source 属性的值 Tenant**。 创建模拟并选择负载时，请确保不筛选掉源 **值** **Tenant**。

## <a name="related-links"></a>相关链接

[开始使用攻击模拟培训](attack-simulation-training-get-started.md)

[创建网络钓鱼攻击模拟](attack-simulation-training.md)

[通过攻击模拟培训获得见解](attack-simulation-training-insights.md)
