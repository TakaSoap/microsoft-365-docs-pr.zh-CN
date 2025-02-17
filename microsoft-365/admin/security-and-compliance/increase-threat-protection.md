---
title: 增强适用于企业Microsoft 365的威胁防护
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
- adminvideo
search.appverid:
- BCS160
- MET150
description: 设置 Microsoft Defender Office 365保护敏感数据免受网络钓鱼、恶意软件和其他威胁的攻击。
ms.openlocfilehash: 8bf954930edc94ccf750bb334a62a4c8a4581f80
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "62321359"
---
# <a name="increase-threat-protection"></a>增强威胁防护

本文可帮助你增强对 Microsoft 365 订阅的保护，以抵御网络钓鱼、恶意软件和其他威胁。 这些建议适用于对安全性需求不断增加的组织，如执法机构和医疗保健机构。

开始之前，请检查安全Office 365分数。 Office 365安全分数根据常规活动和安全设置分析组织的安全性，并分配分数。 首先记下当前分数。 若要增加分数，请完成本文建议的操作。 目标不是达到最高分，而是注意保护环境的机会，这些机会不会对用户的工作效率产生负面影响。

有关详细信息，请参阅 [Microsoft 安全分数](../../security/defender/microsoft-secure-score.md)。

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>提高邮件中恶意软件防护级别

您的Office 365环境Microsoft 365恶意软件防护。 您可以通过阻止具有通常用于恶意软件的文件类型的附件来增强此保护。 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OA7Z?autoplay=false]

1. From the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>， choose **Show more**， **Admin centers**， and then **Security**.

1. 转到电子邮件 **&协作策略** \> **&规则威胁** \> **策略**。

1. 从可用的策略中，选择 **"反恶意软件"**。

增强电子邮件中的恶意软件保护：

1. 在 Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户中</a>\>，转到"策略"&电子邮件&**策略"** \>  \>"威胁策略""反 **恶意软件"。** 

2. 在 **"反恶意软件"** 页上，双击"默认" (**"默认) "**。 将出现一个飞出图。 

3. 选择 **飞出控件** 底部的"编辑保护设置"。 

4. 在 **"保护设置**"下，选中"启用常见附件 **筛选器"旁边的复选框**。 被阻止的文件类型将列在此控件的正下方。 请确保添加以下文件类型：

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   若要添加或删除文件类型，请选择列表末尾 **的** "自定义文件类型"。

6. 选择 **"保存"。**

有关详细信息，请参阅 [EOP 中的反恶意软件保护](../../security/office-365-security/anti-malware-protection.md)。

## <a name="protect-against-ransomware"></a>防范勒索软件

勒索软件通过加密文件或锁定计算机屏幕来限制对数据的访问。 然后，它尝试通过请求"勒索"（通常采用加密货币（如"Itin"）来从犯罪中勒索资金，以交换对数据的访问。

若要防范勒索软件，请创建一个或多个邮件流规则，以阻止通常用于勒索软件的文件扩展名。  (在提高邮件步骤中恶意软件防护级别中添加[](#raise-the-level-of-protection-against-malware-in-mail)了这些规则。) 您还可以警告通过电子邮件接收这些附件的用户。

除了在上一步中阻止的文件之外，最佳做法是创建一个规则，在打开包含宏的 Office 文件附件之前警告用户。 勒索软件可以隐藏在宏内，因此警告用户不要从他们不知道的人打开这些文件。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

1. 在管理中心中 [https://admin.microsoft.com](https://admin.microsoft.com)，选择"**Exchange** 中心 **"下的"管理中心"**。

1. 从左侧的菜单中，选择" **邮件流"**。
 
1. 在"规则"选项卡上，选择加号 (+) 旁边的箭头，然后选择" **创建新规则"**。

1. 在 **"新规则** "页上，输入规则名称，滚动到底部，然后选择"更多 **选项"**。

创建邮件传输规则：

1. 转到 管理中心 ，然后选择 <https://admin.microsoft.com>管理 **中心** \> **Exchange**。

2. 在" **邮件流"** 类别中，选择 **"规则"**。

3. 选择 **+**，然后选择 **"创建新规则"**。

4. 选择 **对话框** 底部的"更多选项"以查看完整的选项集。

5. 为规则应用下表中的设置。 对其余设置使用默认值，除非您要更改它们。

6. 选择 **“保存”**。

|Setting|在打开文件附件之前Office警告|
|---|---|
|名称|反勒索软件规则：警告用户|
|在 中应用此规则。 . .|任何附件 。 . . 文件扩展名匹配 。 . .|
|指定单词或短语|添加以下文件类型：  <br/> dotm、docm、xlsm、sltm、xla、xlam、xll、pptm、potm、ppam、ppsm、sldm|
|执行以下操作。 . .|使用邮件通知收件人|
|提供消息文本|不要从您不知道的人打开这些类型的文件，因为它们可能包含包含恶意代码的宏。|

有关更多信息，请参阅：

- [勒索软件：如何降低风险](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [还原OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a>停止电子邮件的自动转发

获取用户邮箱访问权限的黑客可以通过将邮箱设置为自动转发电子邮件来窃取邮件。 即使没有用户感知，也可能发生此情况。 为了防止发生这种情况，请配置邮件流规则。

若要创建邮件传输规则，请按照以下步骤操作：

1. In the Microsoft 365 管理中心， select **Admin centers** \> **Exchange**.

2. 在" **邮件流"** 类别中，选择 **"规则"**。

3. 选择 **+**，然后选择 **"创建新规则"**。

4. To see all the options， select **More options** at the bottom of the dialog box.

5. 应用下表中的设置。 对其余设置使用默认值，除非您要更改它们。

6. 选择 **“保存”**。

|Setting|在打开文件附件之前Office警告|
|---|---|
|名称|阻止电子邮件自动转发到外部域|
|如果 ...|发件人 。 . . 是外部/内部 。 . . 组织内部|
|添加条件|邮件属性 。 . . 包括邮件类型 。 . . 自动转发|
|执行以下操作...|阻止邮件 。 . . 拒绝邮件并给出说明。|
|提供消息文本|出于安全考虑，阻止在此组织外自动转发电子邮件。|

## <a name="protect-your-email-from-phishing-attacks"></a>保护电子邮件免受网络钓鱼攻击

如果已针对您的 Office 365 或 Microsoft 365 环境配置了一个或多个自定义域，您可以配置目标防钓鱼保护。 防钓鱼保护是 Microsoft Defender Office 365的一部分，可帮助保护你的组织免受基于恶意模拟的网络钓鱼攻击和其他网络钓鱼攻击。 如果尚未配置自定义域，则无需这样做。

我们建议你通过创建一个策略来保护最重要的用户和自定义域来开始使用此保护。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>。

2. 在策略 **&转到电子邮件&** \> **策略"&策略** \> **"**\>"威胁策略 **""防** 钓鱼"。

3. 在" **防钓鱼"页面上** ，选择" **+ 创建"**。 向导将启动，可分步定义防钓鱼策略。

4. 按照下表中的建议指定策略的名称、说明和设置。 有关更多详细信息，请参阅了解 Microsoft Defender 中的反网络钓鱼策略[，了解Office 365选项](../../security/office-365-security/set-up-anti-phishing-policies.md)。

5. 查看设置后，请根据情况选择" **创建此** 策略"或 **"保存"**。

|设置或选项|推荐设置|
|---|---|
|名称|域和最有价值的宣传活动人员|
|说明|确保不会模拟最重要的员工和域。|
|添加要保护的用户|选择 **+ 添加条件，收件人是**。 键入用户名或输入候选人、市场活动经理和其他重要员工成员的电子邮件地址。 您最多可以添加 20 个要防止模拟的内部和外部地址。|
|添加要保护的域|选择 **+ 添加条件，收件人域为**。 如果定义了自定义域，请输入Microsoft 365订阅关联的自定义域。 可以输入多个域。|
|选择操作|如果电子邮件是由模拟用户发送的：选择"将邮件重定向到其他电子邮件地址"，然后键入安全管理员的电子邮件地址;例如，*Alice<span><span>@contoso.com*。 如果电子邮件是由模拟域发送的：请选择“隔离邮件”。|
|邮箱智能|默认情况下，创建新的反钓鱼策略时，将选择邮箱智能。 最好将此设置保留为“打开”。|
|添加受信任的发件人和域|可以在此处添加您自己的域，或任何其他受信任域。|
|应用于|选择“收件人域为”。 在“以下任何项”中，选择“选择”。 选择“+ 添加”。 选中域名称旁边的复选框，例如 *contoso。<span><span>com*，在列表中，然后选择"添加 **"**。 选择“完成”。|

## <a name="watch-protect-against-malicious-attachments-and-files-with-safe-attachments"></a>观看：防范恶意附件和带附件保险箱文件

人们定期发送、接收和共享附件，如文档、演示文稿、电子表格等。 通过查看电子邮件来判断附件是安全还是恶意并不总是那么容易。 Microsoft Defender for Office 365（以前称为 Microsoft 365 ATP 或高级威胁防护）包括 保险箱 附件保护，但默认情况下不会启用此保护。 我们建议您创建一个新规则以开始使用此保护。 此保护扩展到 SharePoint、OneDrive 和 Microsoft Teams。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWtn3I?autoplay=false]

1. 转到管理 [中心，然后选择](https://admin.microsoft.com)"设置 **"**。
1. 向下滚动以 **提升对高级威胁的保护**。 选择 **"查看****、管理**"，然后选择 **"ATP 安全附件"**。
1. 选择安全附件规则，然后选择"编辑 **"** 图标。
1. 选择 **设置**，然后验证是否选择了阻止。
1. 向下滚动。 选择 **"启用** 重定向"，然后输入你的电子邮件地址或你要查看阻止的附件的人的地址。
1. 选择 **"应用于**"，然后选择您的域名。
1. 选择你拥有的任何 (域，onmicrosoft.com 要应用) 的域。 选择 **"添加**"，然后选择" **确定"**。
1. 选择 **“保存”**。

已更新 ATP 安全附件规则。 现在，保护已就位，你将无法从 Outlook、OneDrive、SharePoint 或 Teams 打开恶意Teams。 受影响的文件旁边将具有红色防护。 如果有人尝试打开阻止的文件，他们将收到一条警告消息。

策略实施一段时间后，请访问"报告"页面查看已扫描的内容。

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>，然后使用管理员帐户登录。

2. 转到策略 **&电子邮件&** \> **策略"部分中的** \>  \>"威胁策略"**"反恶意软件****"。**

3. 选择 **+ 创建** 以创建新策略。

4. 应用下表中的设置。

5. 查看设置后，请根据情况选择 **"创建此** 策略 **"或"** 保存"。

|设置或选项|推荐设置|
|---|---|
|名称|使用检测到的恶意软件阻止当前和将来的电子邮件。|
|说明|使用检测到的恶意软件阻止当前和未来的电子邮件和附件。|
|保存附件未知恶意软件响应|选择 **"阻止 - 阻止当前和未来包含检测到的恶意软件的电子邮件和附件"**。|
|检测时重定向附件|启用重定向 (选中此框) 输入要隔离的管理员帐户或邮箱设置。          如果恶意软件扫描附件时间过或出现错误，请应用 (选中此框) 。|
|应用于|收件人域为 。 . . 选择你的域。|

有关详细信息，请参阅在 [Microsoft Defender](../../security/office-365-security/set-up-anti-phishing-policies.md) 中设置防钓鱼策略Office 365。

## <a name="protect-against-phishing-attacks-with-safe-links"></a>使用链接抵御网络钓鱼保险箱攻击

黑客有时会在电子邮件或其他文件中的链接中隐藏恶意网站。 保险箱链接是 Microsoft Defender for Office 365 的一部分，通过提供电子邮件和 Office 文档中的 Web 地址 (URL) 的点击时间验证，可帮助保护你的组织。 保护通过链接保险箱定义。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender for Office 365（以前称为Microsoft 365 ATP 或高级威胁防护）可帮助保护你的企业免受恶意网站的攻击，当用户单击应用中的链接时Office站点。

1. 转到管理 [中心，然后选择](https://admin.microsoft.com)"设置 **"**。

1. 向下滚动以 **提升对高级威胁的保护**。 选择 **"管理**"，然后选择 **保险箱链接"**。

1. 选择 **"全局** 设置"，在"阻止以下 **URL**"中，输入要阻止的 URL。

我们建议您执行以下操作：

- 修改默认策略以提高保护。

- 添加面向域中所有收件人的新策略。

若要设置保险箱链接，请完成以下步骤：

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>，然后使用管理员帐户登录。

2. o to **Email & collaboration Policies** \> **& rules Threat** \> **policies** \> **Anti-malware** in the **Policies** section.

3. 选择 **+ 创建** 以创建新策略，或修改默认策略。

修改默认策略：

1. 双击"默认 **"** 策略。 将出现一个飞出图。 

2. 选择 **飞出控件** 底部的"编辑保护设置"。

3. 修改默认策略后，选择"保存 **"**。

|设置或选项|推荐设置|
|---|---|
|名称|保险箱域中所有收件人的链接策略|
|为邮件中的未知潜在恶意 URL 选择操作|选择打开 - 当用户单击链接时，URL 将被重写，并针对 **已知恶意链接列表进行检查**。|
|使用保险箱附件扫描可下载内容|选中此框。|
|应用于|收件人域为 。 . . 选择你的域。|

有关详细信息，请参阅链接[保险箱链接](../../security/office-365-security/safe-links.md)。

## <a name="go-to-intune-admin-center"></a>转到 Intune 管理中心

1. 登录到 [Azure 门户](https://portal.azure.com/)。

2. 选择 **"所有服务**"，在 *"搜索框"***中键入** Intune。

3. 显示结果后，选择"开始"Microsoft Intune"开始"，使其成为收藏项，并且易于稍后查找。

除了管理中心外，您还可以使用 Intune 注册和管理组织的设备。 有关详细信息，请参阅适用于设备[注册Windows和](/intune/enrollment/enrollment-method-capab) [Intune](/intune/enrollment-options) 管理的设备的注册选项。
