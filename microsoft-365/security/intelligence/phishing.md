---
title: 如何抵御网络钓鱼攻击
ms.reviewer: ''
description: 了解网络钓鱼如何工作、传送恶意软件以及你可以如何保护自己
keywords: 安全， 恶意软件， 网络钓鱼， 信息， 欺诈， 社交工程， 攻击， 攻击， 保护， 趋势， 目标攻击
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
ms.openlocfilehash: 39b998b69b62a8c927ff26c1325d8a88812e0be6
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63683367"
---
# <a name="how-to-protect-against-phishing-attacks"></a>如何抵御网络钓鱼攻击

网络钓鱼攻击尝试通过电子邮件、网站、短信或其他形式的电子通信窃取敏感信息。 他们尝试看起来像来自合法公司或个人的正式通信。

网络犯罪通常尝试窃取用户名、密码、信用卡详细信息、银行帐户信息或其他凭据。 他们将被盗信息用于恶意目的，例如黑客攻击、身份盗窃或直接从银行帐户和信用卡窃取资金。 此信息还可以在网络犯罪犯罪市场中出售。

社交工程攻击旨在利用用户在决策方面可能失效。 请注意，切勿通过电子邮件或未知网站或通过电话提供敏感或个人信息。 请记住，网络钓鱼电子邮件旨在显示为合法邮件。

## <a name="learn-the-signs-of-a-phishing-scam"></a>了解网络钓鱼诈骗的迹象

最好的保护是认知和教育。 不要打开未经请求的电子邮件中的附件或链接，即使这些电子邮件来自已识别的来源。 如果电子邮件是意外的，请对打开附件并验证 URL 时要多做考虑。

企业应教育员工并培训其员工，以对请求个人或财务信息的任何通信进行保护。 他们还应指示员工立即向公司的安全运营团队报告威胁。

以下是网络钓鱼欺诈的一些判断信号：

* 电子邮件中提供的链接或 URL 未指向正确的位置，或指向与电子邮件发件人没有关联的第三方网站。 例如，在图像下方的 URL 中，提供的 URL 与您将去向的 URL 不匹配。

    ![将鼠标悬停在 url 上的示例。](../../media/security-intelligence-images/url-hover.png)

* 请求获取个人信息 **，** 如社会保险号码、银行或财务信息。 正式通信通常不会以电子邮件的形式请求你提供个人信息。

* **电子邮件地址中的项目将发生更改** ，以便其足够类似于合法电子邮件地址，但已添加数字或已更改的字母。

* 邮件是 **意外的且未经请求的**。 如果你突然收到来自你很少处理的实体或人员的电子邮件，请考虑此电子邮件可疑。

* 邮件或附件要求您启用 **宏、调整安全设置或安装应用程序**。 普通电子邮件不会要求你这样做。

* 邮件包含 **错误**。 合法的公司邮件不太可能出现拼写或语法错误或包含错误的信息。

* 发件人 **地址与邮件本身的签名** 不匹配。 例如，一封电子邮件被声称来自 Contoso Corp 的 Mary，但发件人地址是 john<span></span>@example.com。

* " **收件人"字段中** 有多个收件人，它们显示为随机地址。 公司邮件通常直接发送给各个收件人。

* 邮件本身上的问候 **语不会亲自处理您。** 除了错误地向另一个人发送的消息之外，滥用你的姓名或直接从电子邮件地址拉取姓名的问候语往往是恶意问候语。

* 网站看起来很熟悉，但有些不一致 **或内容并不完全正确**。 警告标志包括过时的徽标、拼写错误或要求用户提供合法登录网站未要求的其他信息。

* 打开的页面 **不是实时页面**，而是设计为看起来像您熟悉的网站的图像。 可能会出现请求凭据的弹出窗口。

如果有疑问，请通过已知渠道联系企业，以验证任何可疑电子邮件实际上是否合法。

## <a name="software-solutions-for-organizations"></a>适用于组织的软件解决方案

* [Microsoft Edge](/microsoft-edge/deploy/index) [Windows Defender 应用程序防护 Microsoft](/windows/security/microsoft-defender-application-guard/md-app-guard-overview.md) 行业领先的虚拟化技术，提供针对目标攻击的不断增加威胁Hyper-V防护。 如果浏览的网站被视为不受信任，Hyper-V容器将该设备与网络的其余部分隔离，从而阻止访问企业数据。

* [Microsoft Exchange Online EOP (EOP) ](https://products.office.com/exchange/exchange-email-security-spam-protection) 提供了企业级可靠性和针对垃圾邮件和恶意软件的保护，同时在紧急情况期间和之后保持对电子邮件的访问。  使用各种筛选层，EOP 可以为垃圾邮件筛选提供不同的控制，如批量邮件控制和国际垃圾邮件，这将进一步增强保护服务。

* 使用 [Microsoft Defender for Office 365](https://products.office.com/exchange/online-email-threat-protection?ocid=cx-blog-mmpc)保护你的电子邮件、文件和联机存储免受恶意软件的攻击。 它在 Microsoft Teams、Word、Excel、PowerPoint、Visio、SharePoint Online 和 OneDrive for Business 中提供全面OneDrive for Business。 通过防范不安全的附件并扩展对恶意链接的保护，它补充了 Exchange Online Protection安全功能，以提供更好的零日保护。

## <a name="what-to-do-if-youve-been-a-victim-of-a-phishing-scam"></a>如果您是网络钓鱼诈骗的的受害者，该怎么办

如果你感觉自己遭受网络钓鱼攻击：

1. 如果你在工作计算机上，请与 IT 管理员联系
2. 立即更改与帐户关联的所有密码
3. 向你的信用卡公司报告任何欺诈活动

### <a name="reporting-spam"></a>报告垃圾邮件

- **Outlook.com**：如果收到询问个人信息的可疑电子邮件，请选中"邮件"收件箱中邮件旁边的Outlook复选框。 选择"垃圾邮件"旁边的 **箭头**，然后选择" **网络钓鱼"**。

- **Microsoft Office Outlook**：在可疑邮件中，从功能 **区** 中选择"报告邮件"，然后选择"**网络钓鱼"**。

- **Microsoft 365**：使用 Microsoft 365 Defender 中的提交门户 [](/microsoft-365/security/office-365-security/report-junk-email-messages-to-microsoft)将垃圾邮件或网络钓鱼示例提交给 Microsoft 进行分析。 有关详细信息，请参见[向 Microsoft 报告邮件和文件](/microsoft-365/security/office-365-security/report-junk-email-messages-to-microsoft)。

- **防钓鱼工作组：** phishing-report@us-cert.gov。 该组使用从发送的电子邮件生成的报告来防范网络钓鱼欺诈和黑客。 涉及 ISP、安全供应商、金融机构和执法机构。

### <a name="if-youre-on-a-suspicious-website"></a>如果位于可疑网站上

- **Microsoft Edge**：当你位于可疑网站上时，选择"更多网站 (**...) 图标** >  > "帮助"和"反馈""报告不安全 **网站"**。 按照网页上显示的说明报告网站。

- **Internet Explorer**：在可疑网站上时，选择齿轮图标，指向"安全"，然后选择"**报告不安全网站"**。 按照网页上显示的说明报告网站。

## <a name="more-information-about-phishing-attacks"></a>有关网络钓鱼攻击详细信息

- [保护自己免受网络钓鱼攻击](https://support.microsoft.com/help/4033787/windows-protect-yourself-from-phishing)
- [网络钓鱼趋势](phishing-trends.md)
