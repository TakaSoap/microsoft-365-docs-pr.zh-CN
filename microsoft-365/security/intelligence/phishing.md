---
title: 如何防范网络钓鱼攻击
ms.reviewer: ''
description: 了解网络钓鱼的工作原理、将恶意软件传送到设备，以及可以采取哪些措施来保护自己
keywords: 安全， 恶意软件， 网络钓鱼， 信息， 骗局， 社会工程， 诱饵， 诱惑， 保护， 趋势， 有针对性的攻击
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 1f414c80d3c0b5478112cd402f8e3839908787d4
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666759"
---
# <a name="how-to-protect-against-phishing-attacks"></a>如何防范网络钓鱼攻击

网络钓鱼攻击试图通过电子邮件、网站、短信或其他形式的电子通信窃取敏感信息。 他们试图看起来像来自合法公司或个人的官方沟通。

网络罪犯经常试图窃取用户名、密码、信用卡详细信息、银行帐户信息或其他凭据。 出于恶意目的，他们使用被盗信息，例如黑客攻击、身份盗窃或直接从银行账户和信用卡偷钱。 这些信息也可以在网络犯罪的地下市场出售。

社交工程攻击旨在利用用户在决策中可能出现的失误。 请注意，切勿通过电子邮件或未知网站或电话提供敏感或个人信息。 请记住，网络钓鱼电子邮件设计为看起来合法。

## <a name="learn-the-signs-of-a-phishing-scam"></a>了解网络钓鱼骗局的迹象

最好的保护是意识和教育。 不要在未经请求的电子邮件中打开附件或链接，即使电子邮件来自已识别的源。 如果电子邮件出乎意料，请注意打开附件并验证 URL。

企业应教育和培训员工，警惕任何要求个人或财务信息的通信。 他们还应指示员工立即向公司的安全运营团队报告威胁。

下面是网络钓鱼骗局的几个迹象：

* 电子邮件中提供的链接或 URL **不指向正确的位置** ，也不指向与电子邮件发件人无关的第三方网站。 例如，在下图中提供的 URL 与要转到的 URL 不匹配。

    ![将鼠标悬停在 URL 上的示例。](../../media/security-intelligence-images/url-hover.png)

* 有人 **要求提供个人信息** ，如社会保障号码、银行或财务信息。 官方通信通常不会以电子邮件的形式向你请求个人信息。

* **将更改电子邮件地址中的项** ，使其与合法的电子邮件地址足够相似，但已添加数字或更改的字母。

* 消息 **意外且未经请求**。 如果你突然收到来自实体或你很少处理的人的电子邮件，请考虑此电子邮件可疑。

* 消息或附件要求你 **启用宏、调整安全设置或安装应用程序**。 普通电子邮件不会要求你执行此操作。

* 消息包含 **错误**。 合法的公司消息不太可能出现拼写或语法错误或包含错误信息。

* **发件人地址与邮件本身上的签名不匹配**。 例如，电子邮件据称来自 Contoso Corp 的 Mary，但发件人地址为 john<span></span>@example.com。

* "收件人"字段中有 **多个收件人** ，它们似乎是随机地址。 公司邮件通常直接发送给单个收件人。

* 邮件本身的问候语 **不会亲自向你讲话**。 除了误用其他人员的邮件外，误用姓名或直接从电子邮件地址拉取姓名的问候语往往是恶意的。

* 网站看起来很熟悉，但有些 **不一致或不太正确**。 警告标志包括过时的徽标、拼写错误或要求用户提供合法登录网站未要求的其他信息。

* 打开的页面 **不是实时页面**，而是设计为类似于你熟悉的网站的图像。 可能会出现请求凭据的弹出窗口。

如果有疑问，请通过已知渠道与业务联系，以验证任何可疑电子邮件实际上是否合法。

## <a name="software-solutions-for-organizations"></a>面向组织的软件解决方案

* [Microsoft Edge](/microsoft-edge/deploy/index)和[Windows Defender 应用程序防护](/windows/security/microsoft-defender-application-guard/md-app-guard-overview.md)使用 Microsoft 行业领先的 Hyper-V 虚拟化技术，防止目标攻击的威胁增加。 如果浏览的网站被视为不受信任，Hyper-V 容器会将该设备与网络的其余部分隔离开来，从而阻止对企业数据的访问。

* [Microsoft Exchange Online保护 (EOP) ](https://products.office.com/exchange/exchange-email-security-spam-protection)提供企业级的可靠性和针对垃圾邮件和恶意软件的保护，同时在紧急情况下和之后保持对电子邮件的访问。  使用各种筛选层，EOP 可以为垃圾邮件筛选提供不同的控件，例如批量邮件控件和国际垃圾邮件，这将进一步加强保护服务。

* 使用[Microsoft Defender for Office 365](https://products.office.com/exchange/online-email-threat-protection?ocid=cx-blog-mmpc)来帮助保护电子邮件、文件和联机存储免受恶意软件的侵害。 它在 Microsoft Teams、Word、Excel、PowerPoint、Visio、SharePoint Online 和 OneDrive for Business 中提供全面保护。 通过防范不安全附件和扩大对恶意链接的保护，它补充了Exchange Online Protection的安全功能，以提供更好的零天保护。

## <a name="what-to-do-if-youve-been-a-victim-of-a-phishing-scam"></a>如果你是网络钓鱼骗局的受害者，该怎么办

如果你觉得自己是网络钓鱼攻击的受害者：

1. 如果你在工作计算机上，请与 IT 管理员联系
2. 立即更改与帐户关联的所有密码
3. 向银行和信用卡公司报告任何欺诈活动

### <a name="reporting-spam"></a>报告垃圾邮件

- **Outlook.com**：如果收到请求个人信息的可疑电子邮件，请选中Outlook收件箱中邮件旁边的复选框。 选择 **"垃圾邮件**"旁边的箭头，然后选择 **"网络钓鱼**"。

- **Microsoft Office Outlook**：在可疑消息中，从功能区中选择 **"报告"消息**，然后选择 **"钓鱼**"。

- **Microsoft 365**：使用 [Microsoft 365 Defender中的提交门户](/microsoft-365/security/office-365-security/report-junk-email-messages-to-microsoft)将垃圾或网络钓鱼示例提交给 Microsoft 进行分析。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](/microsoft-365/security/office-365-security/report-junk-email-messages-to-microsoft)。

- **反网络钓鱼工作组**：phishing-report@us-cert.gov。 该组织使用从发送的电子邮件中生成的报告来打击网络钓鱼诈骗和黑客。 ISP、安全供应商、金融机构和执法机构也参与其中。

### <a name="if-youre-on-a-suspicious-website"></a>如果你在一个可疑的网站上

- **Microsoft Edge**：在可疑网站上时，选择 **"更 (...) iconHelp** >  **和 feedbackReport** >  **Unsafe 网站**。 按照显示的网页上的说明来报告网站。

- **Internet Explorer**：在可疑站点上时，选择齿轮图标，指向 **安全**，然后选择 **"报告不安全网站**"。 按照显示的网页上的说明来报告网站。

## <a name="more-information-about-phishing-attacks"></a>有关网络钓鱼攻击的详细信息

- [保护自己免受网络钓鱼](https://support.microsoft.com/help/4033787/windows-protect-yourself-from-phishing)
- [网络钓鱼趋势](phishing-trends.md)
