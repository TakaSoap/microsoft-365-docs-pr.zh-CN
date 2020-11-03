---
title: 提高 Microsoft 365 for Business 的威胁防护
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 设置 Microsoft Defender for Office 365 并针对网络钓鱼、恶意软件和其他威胁保护敏感数据。
ms.openlocfilehash: 2f1a26b5a2c5678871502d441b6ba64c9b011e1c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842248"
---
# <a name="increase-threat-protection"></a>增强威胁防护

本文可帮助你提高 Microsoft 365 订阅中的保护，以防止出现网络钓鱼、恶意软件和其他威胁。 这些建议适用于具有更高安全性需求的组织，如法律办公室和卫生保健诊所。

在开始之前，请检查您的 Office 365 安全分数。 Office 365 安全分数根据您的常规活动和安全设置来分析组织的安全性，并分配分数。 首先记录你的当前分数。 若要增加成绩，请完成本文中建议的操作。 目标不能达到最大分数，但请注意保护您的环境不会对用户的工作效率造成负面影响的机会。

有关详细信息，请参阅 [Microsoft 安全分数](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)。

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>提高针对邮件中的恶意软件的保护级别

您的 Office 365 或 Microsoft 365 环境包括针对恶意软件的防护。 您可以通过阻止经常用于恶意软件的文件类型来阻止附件，从而提高此保护。 若要提高电子邮件的恶意软件保护：

1. 转到 [https://protection.office.com](https://protection.office.com) 并使用你的管理员帐户凭据登录。

2. 在安全 &amp; 合规性中心的左侧导航窗格中的 " **威胁管理** " 下，选择 " **策略** \> **反恶意软件** "。

3. 双击默认策略以编辑此公司范围的策略。

4. 选择“ **设置** ”。

5. 在 " **常用附件类型筛选器** " 下，选择 **"启用"** 。 被阻止的文件类型在此控件正下方的窗口中列出。 请确保添加以下文件类型：

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   如有必要，您可以稍后添加或删除文件类型。

6. 选择 " **保存"。**

有关详细信息，请参阅 [EOP 中的反恶意软件保护](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection)。

## <a name="protect-against-ransomware"></a>防范勒索软件

勒索软件通过加密文件或锁定计算机屏幕来限制对数据的访问。 然后，它会通过在 exchange 中请求 "勒索" （通常为 "cryptocurrencies" 的形式为 "Bitcoin"），从受害者处 extort 钱，以供 exchange 访问数据。

若要针对勒索软件进行保护，请创建一个或多个邮件流规则，以阻止用于勒索软件的文件扩展名。  (您在 "邮件" 步骤中添加了这些规则以 [防止恶意软件的保护级别](#raise-the-level-of-protection-against-malware-in-mail) 。 ) 您还可以在电子邮件中警告收到这些附件的用户。

除了在上一步中阻止的文件，在打开包含宏的 Office 文件附件之前，最好先创建一个规则来警告用户。 勒索软件可以隐藏在宏中，因此警告用户不要从他们不知道的人那里打开这些文件。

若要创建邮件传输规则，请执行以下操作：

1. 转到 "管理中心" <https://admin.microsoft.com> ，然后选择 " **管理中心** " " \> **Exchange** "。

2. 在 " **邮件流** " 类别中，选择 " **规则** "。

3. 选择 **+** ""，然后选择 " **创建新规则** "。

4. 选择对话框底部的 " **更多选项** " 可查看完整的选项集。

5. 对规则应用下表中的设置。 对其余设置使用默认值，除非您要对其进行更改。

6. 选择“ **保存** ”。

|设置|在打开 Office 文件附件之前警告用户||
|---|---|---|
|名称|反勒索软件规则：警告用户|
|在以下情况应用此规则。 . .|任何附件。 . . 文件扩展名匹配。 . .|
|指定字词或短语|添加以下文件类型：  <br/> normal.dotm、.docm、xlsm、sltm、xlodbc.xla 加载、.xlam、xll、.pptm、potm、.ppam、ppsm、sldm|
|执行以下操作。 . .|使用邮件通知收件人|
|提供邮件文本|请勿从不知道的人打开这些类型的文件，因为它们可能包含恶意代码的宏。|

有关详细信息，请参阅：

- [勒索软件：如何降低风险](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [还原你的 OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>停止电子邮件的自动转发

获取对用户邮箱的访问权限的黑客可以通过将邮箱设置为自动转发电子邮件来盗取邮件。 即使没有用户的意识，也会发生这种情况。 若要防止这种情况发生，请配置邮件流规则。

若要创建邮件传输规则，请观看 [此简短视频](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) 或按照以下步骤操作：

1. 在 Microsoft 365 管理中心，选择 " **管理中心** " " \> **Exchange** "。

2. 在 " **邮件流** " 类别中，选择 " **规则** "。

3. 选择 **+** ""，然后选择 " **创建新规则** "。

4. 若要查看所有选项，请在对话框底部选择 " **更多选项** "。

5. 应用下表中的设置。 对其余设置使用默认值，除非您要对其进行更改。

6. 选择“ **保存** ”。

|设置|在打开 Office 文件附件之前警告用户|
|---|---|
|名称|阻止电子邮件自动转发到外部域|
|在以下情况应用此规则 .。。|发件人。 . . 为外部/内部。 . . 组织内部|
|添加条件|邮件属性。 . . 包含邮件类型。 . . 自动转发|
|执行以下操作 .。。|阻止邮件。 . . 拒绝邮件并提供说明。|
|提供邮件文本|出于安全考虑，将阻止此组织外部的自动转发电子邮件。|


## <a name="protect-your-email-from-phishing-attacks"></a>保护你的电子邮件免受网络钓鱼攻击

如果您为 Office 365 或 Microsoft 365 环境配置了一个或多个自定义域，则可以配置目标的反网络钓鱼保护。 反网络钓鱼保护是 Microsoft Defender for Office 365 中的一部分，可帮助保护您的组织免受基于恶意模拟的网络钓鱼攻击和其他网络钓鱼攻击。 如果尚未配置自定义域，则无需执行此操作。

我们建议您通过创建策略来保护最重要的用户和您的自定义域，以此来开始保护。

若要在 Microsoft Defender for Office 365 中创建反网络钓鱼策略，请观看  [此简短的培训视频](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)，或完成以下步骤：

1. 转到 [https://protection.office.com](https://protection.office.com)。

2. 在安全 &amp; 合规性中心的左侧导航窗格中的 " **威胁管理** " 下，选择 " **策略** "。

3. 在 " **策略** " 页上，选择 " **反网络钓鱼** "。

4. 在 " **反钓鱼网站** " 页上，选择 " **+ 创建** "。 向导将启动，引导您完成定义您的反网络钓鱼策略。

5. 按下表中的建议指定策略的名称、说明和设置。 有关更多详细信息，请参阅 [Microsoft Defender For Office 365 选项中的了解反网络钓鱼策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)。

6. 查看设置后，根据需要选择 " **创建此策略** " 或 " **保存** "。

|设置或选项|推荐设置|
|---|---|
|名称|域和最有价值的市场活动员工|
|说明|确保不会模拟大多数重要的人员和我们的域。|
|添加要保护的用户|选择 **+ 添加条件，收件人为** 。 键入用户名称或输入候选人、活动经理和其他重要教职员工成员的电子邮件地址。 您最大可以添加20个要从模拟中保护的内部和外部地址。|
|添加要保护的域|选择 **"+ 添加条件，收件人域为"** 。 输入与 Microsoft 365 订阅关联的自定义域（如果已定义一个）。 您可以输入一个以上的域。|
|选择操作|如果模拟用户发送电子邮件：选择 " **将邮件重定向到另一个电子邮件地址** "，然后键入安全管理员的电子邮件地址;例如， *刘爱琳 <span> <span> @contoso .com* 。 如果电子邮件是由模拟域发送的：请选择“隔离邮件”。|
|邮箱智能|默认情况下，创建新的反钓鱼策略时，将选择邮箱智能。 最好将此设置保留为“打开”。|
|添加受信任的发件人和域|你可以在此处添加你自己的域或任何其他受信任域。|
|应用于|选择“收件人域为”。 在“以下任何项”中，选择“选择”。 选择“+ 添加”。 选中域名称旁边的复选框，例如 " *contoso"。 <span> <span>com* ，请在列表中，然后选择 " **添加** "。 选择“ **完成** ”。|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a>使用安全附件防止恶意附件和文件

用户定期发送、接收和共享附件，如文档、演示文稿、电子表格等。 只需查看一封电子邮件，就能判断附件是安全还是恶意的，并不总是容易。 Microsoft Defender for Office 365 包括安全附件保护，但默认情况下不启用此保护。 我们建议您创建一个新规则以开始使用此保护。 此保护功能扩展到 SharePoint、OneDrive 和 Microsoft 团队中的文件。

若要创建安全附件策略，请观看 [此简短视频](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)，或完成以下步骤：

1. 转到 [https://protection.office.com](https://protection.office.com) ，然后使用你的管理员帐户登录。

2. 在安全 &amp; 合规性中心的左侧导航窗格中的 " **威胁管理** " 下，选择 " **策略** "。

3. 在 "策略" 页上，选择 " **安全附件** "。

4. 在 "安全附件" 页面上，选中 " **启用 SharePoint、OneDrive 和 Microsoft 团队的 ATP** " 复选框，以应用广泛的保护。

5. 选择 **+** 以创建新策略。

6. 应用下表中的设置。

7. 查看设置后，根据需要选择 " **创建此策略** " 或 " **保存** "。

|设置或选项|推荐设置|
|---|---|
|名称|使用检测到的恶意软件阻止当前和将来的电子邮件。|
|说明|使用检测到的恶意软件阻止当前和将来的电子邮件和附件。|
|保存附件未知的恶意软件响应|Select **block-阻止当前和将来的包含检测到的恶意软件的电子邮件和附件** 。|
|在检测时重定向附件|启用重定向 (选中此框) 输入管理员帐户或邮箱设置进行隔离。          如果恶意软件扫描附件超时或发生错误，则应用上述选择) 。 (选中该框。|
|应用于|收件人域为。 . . 选择您的域。|

有关详细信息，请参阅 [在 Microsoft Defender For Office 365 中设置反网络钓鱼策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)。

## <a name="protect-against-phishing-attacks-with-safe-links"></a>使用安全链接防御网络钓鱼攻击

黑客有时会在电子邮件或其他文件的链接中隐藏恶意网站。 Microsoft Defender for Office 365 中的 "安全链接" 可通过在电子邮件和 Office 文档中对 web 地址 (Url) 进行验证，从而帮助保护您的组织。 通过安全链接策略定义保护。

我们建议您执行以下操作：

- 修改默认策略以提高保护。

- 添加目标为域中所有收件人的新策略。

若要设置安全链接，请观看 [此简短的培训视频](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)，或完成以下步骤：

1. 转到 [https://protection.office.com](https://protection.office.com) ，然后使用你的管理员帐户登录。

2. 在安全 &amp; 合规性中心的左侧导航窗格中的 " **威胁管理** " 下，选择 " **策略** "。

3. 在 "策略" 页上，选择 " **安全链接** "。

若要修改默认策略，请执行以下操作：

1. 在 "安全链接" 页面上，在 " **适用于整个组织的策略** " 下，选择 " **默认** 策略"。

2. 在 " **适用于除电子邮件以外的内容的设置** " 下，选择 "适用于 **企业的 Microsoft 365 应用，Office For iOS 和 Android** "。

3. 选择“ **保存** ”。

创建一个面向域中所有收件人的新策略：

1. 在 "安全链接" 页面上，在 " **适用于整个组织的策略** " 下，选择 " **+** 创建新策略"。

2. 应用下表中列出的设置。

3. 选择“ **保存** ”。

|设置或选项|推荐设置|
|---|---|
|名称|域中所有收件人的安全链接策略|
|选择邮件中未知的潜在恶意 Url 的操作|**当用户单击链接时，将会重写并检查在已知恶意链接列表中的 "按 Url"，并对其进行检查** 。|
|使用安全附件扫描可下载的内容|选中此框。|
|应用于|收件人域为。 . . 选择您的域。|

有关详细信息，请参阅 [安全链接](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)。

## <a name="go-to-intune-admin-center"></a>转到 Intune 管理中心

1. 登录到 [Azure 门户](https://portal.azure.com/)。

2. 在 " **搜索" 框** 中选择 " **所有服务** "，然后键入 *Intune* 。

3. 在结果出现后，选择 " **Microsoft Intune** " 旁边的 "开始"，使其成为收藏且易于查找。

除了管理中心之外，你还可以使用 Intune 注册和管理你的组织的设备。 有关详细信息，请参阅 [Windows 设备注册方法](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) 和由 [Intune 管理的设备的注册选项](https://docs.microsoft.com/intune/enrollment-options)的功能。
