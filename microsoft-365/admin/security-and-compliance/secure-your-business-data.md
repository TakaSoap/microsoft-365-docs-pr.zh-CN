---
title: 保护 Microsoft 365 商业版计划的十大方法
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: '保护您的业务电子邮件和数据免受网络威胁的威胁，包括勒索软件、网络钓鱼和恶意附件。 '
ms.openlocfilehash: 12a8d036a043cfdd162b5aa47e1d6d5023a42c81
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005626"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>保护 Microsoft 365 商业版计划的十大方法

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

如果您是使用 Microsoft 商业版计划的小型组织，并且您的组织类型针对的是网络罪犯和黑客，请按照本文中的指导提高贵组织的安全性。 本指南可帮助您的组织实现 Harvard 肯尼迪学校[Cybersecurity 活动手册](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409)中所述的目标。
  
Microsoft 建议您完成下表中列出的适用于您的服务计划的任务。 
  
||**Task**|**Microsoft 365 商业标准版**|**Microsoft 365 商业高级版**|
|:-----|:-----|:-----|:-----|
|1   <br/> |[设置多重身份验证](secure-your-business-data.md#setup) <br/> |![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|2   <br/> |[培训用户](secure-your-business-data.md#train) <br/> |![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|3   <br/> |[使用专用管理员帐户](secure-your-business-data.md#admin) <br/> |![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|4   <br/> |[提高针对邮件中的恶意软件的保护级别](secure-your-business-data.md#malware) <br/> |![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|5   <br/> |[防范勒索软件](secure-your-business-data.md#ransomware) <br/> |![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|6   <br/> |[停止电子邮件的自动转发](secure-your-business-data.md#forwarding) <br/> |![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|7   <br/> |[使用 Office 邮件加密](secure-your-business-data.md#encryption) <br/> ||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|8   <br/> |[保护你的电子邮件免受网络钓鱼攻击](secure-your-business-data.md#phishing) <br/> ||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|9   <br/> |[使用 ATP 安全附件防止恶意附件和文件](secure-your-business-data.md#atp) <br/> ||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|10   <br/> |[使用 ATP 安全链接防御网络钓鱼攻击](secure-your-business-data.md#phishingatp) <br/> ||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
   
在开始之前，请在 Microsoft 365 安全中心检查[microsoft 365 安全分数](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)。 通过集中式仪表板，可以监视和提高 Microsoft 365 标识、数据、应用程序、设备和基础结构的安全性。 为您提供配置推荐安全功能、执行与安全相关的任务（如查看报告）或使用第三方应用程序或软件解决建议的相关积分。 通过其他见解并更好地了解更广泛的一组 Microsoft 产品和服务，您可以放心地报告您的组织的安全运行状况。
  
![Microsoft 安全分数的屏幕截图](../../media/secure-score.png)
  
## <a name="1-set-up-multi-factor-authentication"></a>1：设置多重身份验证
<a name="setup"> </a>

使用多重身份验证是提高组织安全性的最简单且最有效的方法之一。 它比听起来更容易-当你登录时，多重身份验证意味着你将键入手机中的代码以获取对 Microsoft 365 的访问权限。 这样可以防止黑客在知道你的密码时接管。 多重身份验证也称为2步验证。 个人可以轻松地将双重验证添加到大多数帐户，例如，添加到 Google 或 Microsoft 帐户。 下面介绍如何[将双重验证添加到你的个人 Microsoft 帐户](https://go.microsoft.com/fwlink/?linkid=2016403&amp;clcid=0x409)。
  
对于使用 Microsoft 365 的企业，添加一个设置，要求用户使用多重身份验证登录。 进行此更改后，系统将提示用户在下次登录时设置其电话以进行双重身份验证。
若要查看有关如何设置 MFA 以及用户如何完成设置的培训视频，请参阅[设置 mfa](https://support.microsoft.com/office/e12187b8-216a-4490-9e3b-df34a06fb787)和[用户设置](https://support.microsoft.com/office/a32541df-079c-420d-9395-9d59354f7225)。
  
若要设置多重身份验证，请执行以下操作：

1. 在[管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)内，选择 "**用户**  >  **活动用户**"。

2. 在 "**活动用户**" 部分中，选择 "**多因素身份验证**"。

3. 在 "**多重身份验证**" 页上，如果要为一个用户启用此项，请选择 "**用户**"，或者您可以执行**批量更新**。

4. 在 "**快速步骤**" 下选择 "**启用**"。

5. 在弹出窗口中，选择 "**启用多重身份验证**"。


为你的组织设置多重身份验证后，你的用户将需要在其设备上设置双重验证。 有关详细信息，请参阅[为 Microsoft 365 设置2步验证](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)。
  
有关完整详细信息和完整建议，请参阅为[用户设置多重身份验证](set-up-multi-factor-authentication.md)。
  
## <a name="2-train-your-users"></a>2：培训您的用户
<a name="train"> </a>

Harvard 肯尼迪 School [Cybersecurity 活动手册](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409)提供了有关在组织内建立强大的安全感知文化的最佳指南，包括培训用户以识别网络钓鱼攻击。 
  
除了本指南之外，Microsoft 还建议您的用户执行本文中所述的操作：[保护您的帐户和设备免受黑客和恶意软件的攻击](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6)。 这些操作包括：
  
- 使用强密码
    
- 保护设备
    
- 在 Windows 10 和 Mac 电脑上启用安全功能
    
Microsoft 还建议用户采取以下文章中建议的操作来保护其个人电子邮件帐户：
  
- [帮助保护你的 Outlook.com 电子邮件帐户](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
    
- [通过2步验证保护你的 Gmail 帐户](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
    
## <a name="3-use-dedicated-admin-accounts"></a>3：使用专用管理员帐户
<a name="admin"> </a>

用于管理 Microsoft 365 环境的管理帐户包括提升的权限。 这些是黑客和网络罪犯的有用目标。 仅使用管理员帐户进行管理。 管理员应使用单独的用户帐户进行常规的非管理，并且仅在必要时才使用其管理帐户完成与工作职能相关联的任务。 其他建议：
  
- 确保同时为多因素身份验证设置了管理员帐户。 
    
- 使用管理员帐户之前，请关闭所有不相关的浏览器会话和应用，包括个人电子邮件帐户。
    
- 完成管理任务后，请务必注销浏览器会话。
    
## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a>4：针对邮件中的恶意软件提高保护级别
<a name="malware"> </a>

你的 Microsoft 365 环境包括针对恶意软件的防护，但你可以通过阻止常见恶意软件使用的文件类型的附件来提高此保护。 若要增大电子邮件中的恶意软件保护，请查看[简短的培训视频](https://support.microsoft.com/office/02b5783a-eea0-42e8-8856-62440718c3f0)，或完成以下步骤：
  
1. 转到 [https://protection.office.com](https://protection.office.com) 并使用你的管理员帐户凭据登录。 
    
2. 在安全 &amp; 合规性中心的左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略** \> **反恶意软件**"。
    
3. 双击默认策略以编辑此公司范围的策略。
    
4. 选择“**设置**”。
    
5. 在 "**常用附件类型筛选器**" 下，选择 **"启用"**。 被阻止的文件类型在此控件正下方的窗口中列出。 如果需要，您可以稍后添加或删除文件类型。
    
6. 选择 "**保存"。**
    
有关详细信息，请参阅[反恶意软件保护](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409)。
  
## <a name="5-protect-against-ransomware"></a>5：针对勒索软件进行防护
<a name="ransomware"> </a>

勒索软件通过加密文件或锁定计算机屏幕来限制对数据的访问。 然后，它会通过在 exchange 中请求 "勒索" （通常为 "Bitcoin" 形式）（通常为 ""），在 exchange 中获取数据访问权限，从而从受害人 extort。 
  
您可以通过创建一个或多个邮件流规则来阻止勒索软件通常使用的文件扩展名，或警告用户在电子邮件中接收这些附件，从而防止勒索软件受到侵害。 一个很棒的起点是创建两个规则：
  
- 在打开包含宏的 Office 文件附件之前警告用户。 勒索软件可以隐藏在宏中，因此我们将警告用户不要从他们不知道的人打开这些文件。 
    
- 阻止可能包含勒索软件或其他恶意代码的文件类型。 我们将从可执行文件的常用列表（在下表中列出）开始。 如果您的组织使用这些可执行类型中的任何类型，并且您希望在电子邮件中发送这些类型，请将它们添加到上一规则（警告用户）。
    
若要创建邮件传输规则，请查看[简短的培训视频](https://support.microsoft.com/office/a9ecca03-42a6-4867-b9fd-38e3f6bb06ad)，或完成以下步骤：
  
1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。

2. 在 "**邮件流**" 类别中，选择 "**规则**"。
    
3. 选择 **+** ""，然后**创建一个新规则**。
    
4. 在对话框底部选择 "* * * *" 以查看完整的选项集。 
    
5. 对每个规则应用下表中的设置。 将其余设置保留为默认值，除非您要对其进行更改。
    
6. 选择“**保存**”。
    
|**设置**|**在打开 Office 文件附件之前警告用户**|**阻止可能包含勒索软件或其他恶意代码的文件类型**|
|:-----|:-----|:-----|
|名称  <br/> |反勒索软件规则：警告用户  <br/> |反勒索软件规则：阻止文件类型  <br/> |
|在以下情况应用此规则。 . .  <br/> |任何附件。 . . 文件扩展名匹配。 . .  <br/> |任何附件。 . . 文件扩展名匹配。 . .  <br/> |
|指定字词或短语  <br/> |添加以下文件类型：  <br/> normal.dotm、.docm、xlsm、sltm、xlodbc.xla 加载、.xlam、xll、.pptm、potm、.ppam、ppsm、sldm  <br/> |添加以下文件类型：  <br/> ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、.hlp、超线程、hta、inf、jse、mdz、作业、js、、.lnk、mda、mdb、mde、、msc、msi、msp、mst、vb、vbe、scr、pcd、shs、wsh、  <br/> |
|执行以下操作。 . .  <br/> |使用邮件通知收件人  <br/> |阻止邮件。 . . 拒绝邮件并提供说明  <br/> |
|提供邮件文本  <br/> |请勿打开这些类型的文件（除非您需要它们），因为这些文件可能包含恶意代码，并且知道发件人不能保证安全。  <br/> ||
   
> [!TIP]
> 您还可以将您想要阻止的文件添加到[步骤 4](#4-raise-the-level-of-protection-against-malware-in-mail)中的反恶意软件列表中。

有关详细信息，请参阅：
  
- [如何处理勒索软件](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [还原你的 OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)
    
## <a name="6-stop-auto-forwarding-for-email"></a>6：停止自动转发电子邮件
<a name="forwarding"> </a>

获取对用户邮箱的访问权限的黑客可以通过将邮箱配置为自动转发电子邮件来 exfiltrate 邮件。 即使没有用户的意识，也会发生这种情况。 您可以通过配置邮件流规则来防止这种情况发生。 
  
若要创建邮件传输规则，请执行以下操作：
  
1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。

2. 在 "**邮件流**" 类别中，选择 "**规则**"。
    
3. 选择 **+** ""，然后**创建一个新规则**。
    
4. 选择对话框底部的 "**更多选项**" 可查看完整的选项集。 
    
5. 应用下表中的设置。 将其余设置保留为默认值，除非您要对其进行更改。
    
6. 选择“**保存**”。
    
|**设置**|**拒绝将自动转发电子邮件发送到外部域**|
|:-----|:-----|
|名称  <br/> |阻止电子邮件自动转发到外部域  <br/> |
|在以下情况应用此规则 .。。  <br/> |发件人。 . . 为外部/内部。 . . 组织内部  <br/> |
|添加条件  <br/> |收件人。 . . 为外部/内部。 . . 组织外部  <br/> |
|添加条件  <br/> |邮件属性。 . . 包含邮件类型。 . . 自动转发  <br/> |
|执行以下操作 .。。  <br/> |阻止邮件。 . . 拒绝邮件并提供说明。  <br/> |
|提供邮件文本  <br/> |出于安全考虑，将阻止此组织外部的自动转发电子邮件。  <br/> |
   
## <a name="7-use-office-message-encryption"></a>7：使用 Office 邮件加密
<a name="encryption"> </a>

Office 邮件加密包含在 Microsoft 365 中。 已对其进行设置。 使用 Office 邮件加密，组织可以在组织内部和外部的人员之间发送和接收加密的电子邮件。 Office 365 邮件加密适用于 Outlook.com、Yahoo！、Gmail 和其他电子邮件服务。 电子邮件加密有助于确保只有预期的收件人可以查看邮件内容。
  
"Office 邮件加密" 在发送邮件时提供两个保护选项：
  
- 请勿转发
    
- 对
    
您的组织可能已配置了将标签应用于电子邮件的其他选项，如 "机密"。
  
### <a name="to-send-protected-email"></a>发送受保护的电子邮件

在 "Outlook for PC" 中，选择 "电子邮件中的**选项**"，然后选择 "**权限**"。 
  
![Outlook 中的电子邮件加密](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)
  
在 Outlook.com 中，选择 "在电子邮件中**保护**"。 默认保护不是**转发**。 若要将此更改为 "加密"，请选择 "**更改权限** \> **加密**"。 
  
![Outlook.com 中的电子邮件加密](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)
  
### <a name="to-receive-encrypted-email"></a>接收加密电子邮件

如果收件人具有 Outlook 2013 或 Outlook 2016 和 Microsoft 电子邮件帐户，他们将在阅读窗格中看到有关项目的受限权限的警报。 打开邮件后，收件人可以像其他任何其他方式一样查看邮件。
  
如果收件人使用的是另一个电子邮件客户端或电子邮件帐户（如 Gmail 或 Yahoo），他们将看到一个链接，让他们可以登录以阅读电子邮件，也可以请求一次性密码以在 web 浏览器中查看邮件。 如果用户没有收到电子邮件，请让他们检查其垃圾邮件或垃圾邮件文件夹。 
  
有关详细信息，请参阅[Outlook FOR PC 中的发送、查看和回复加密邮件](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980)。
  
## <a name="8-protect-your-email-from-phishing-attacks"></a>8. 保护你的电子邮件免受网络钓鱼攻击
<a name="phishing"> </a>

如果已为 Microsoft 365 环境配置了一个或多个自定义域，则可以配置目标反网络钓鱼保护。 ATP 反网络钓鱼保护是 Office 365 高级威胁防护的一部分，可帮助保护您的组织免受基于恶意模拟的网络钓鱼攻击和其他网络钓鱼攻击。 如果尚未配置自定义域，则无需执行此操作。
  
我们建议您通过创建策略来保护最重要的用户和您的自定义域，以此来开始保护。 
  
![创建 ATP 反网络钓鱼策略](../../media/security-and-compliance-center.png)
  
若要创建 ATP 反网络钓鱼策略，请查看[简短的培训视频](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)，或完成以下步骤：
  
1. 转到 [https://protection.office.com](https://protection.office.com)。 
    
2. 在安全 &amp; 合规性中心的左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略**"。
    
3. 在 "策略" 页上，选择 " **ATP 反网络钓鱼**"。
    
4. 在 "反钓鱼网站" 页上，选择 " **+ 创建**"。 向导将启动，引导您完成定义您的反网络钓鱼策略。
    
5. 按照下表中的建议，指定策略的名称、说明和设置。 有关详细信息，请参阅[了解 ATP 反网络钓鱼策略选项](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)。 
    
6. 查看设置后，根据需要选择 "**创建此策略**" 或 "**保存**"。


|**设置或选项**|**推荐设置** <br/>|
|:-----|:-----|
|名称  <br/> |域和最有价值的市场活动员工  <br/> |
|说明  <br/> |确保不会模拟大多数重要的人员和我们的域。  <br/> |
|添加要保护的用户  <br/> |选择 **+ 添加条件，收件人为**。 键入用户名称或输入候选人、活动经理和其他重要教职员工成员的电子邮件地址。 您最大可以添加20个要从模拟中保护的内部和外部地址。  <br/> |
|添加要保护的域  <br/> |选择 **"+ 添加条件，收件人域为"**。 输入与 Microsoft 365 订阅关联的自定义域（如果已定义一个）。 您可以输入一个以上的域。  <br/> |
|选择操作  <br/> |如果模拟用户发送电子邮件：选择 "**将邮件重定向到另一个电子邮件地址**"，然后键入安全管理员的电子邮件地址;例如，securityadmin@contoso.com。          如果由模拟域发送电子邮件：选择 "**隔离邮件**"。  <br/> |
|邮箱智能  <br/> |默认情况下，创建新的反钓鱼策略时，将选择邮箱智能。 最好将此设置保留为“打开”****。  <br/> |
|添加受信任的发件人和域  <br/> |在此示例中，不要定义任何替代项。  <br/> |
|应用于  <br/> |选择“收件人域为”****。 在“以下任何项”**** 中，选择“选择”****。 选择“+ 添加”****。 选中域的名称旁边的复选框，例如，contoso.com，在列表中，然后选择 "**添加**"。 选择“完成”****。  <br/> |
|
   
有关详细信息，请参阅[设置 Office 365 ATP 反网络钓鱼策略](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)。
  
## <a name="9-protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>9：使用 ATP 安全附件防止恶意附件和文件
<a name="atp"> </a>

用户定期发送、接收和共享附件，如文档、演示文稿、电子表格等。 只需查看一封电子邮件，就能判断附件是安全还是恶意的，并不总是容易。 Office 365 高级威胁防护包括 ATP 安全附件保护，但默认情况下不启用此保护。 我们建议您创建一个新规则以开始使用此保护。 此保护功能扩展到 SharePoint、OneDrive 和 Microsoft 团队中的文件。
  
若要创建 ATP 安全附件策略，请查看[简短的培训视频](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)，或完成以下步骤：
  
1. 转到 [https://protection.office.com](https://protection.office.com) 并使用管理员帐户登录。 
    
2. 在安全 &amp; 合规性中心的左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略**"。
    
3. 在 "策略" 页上，选择 " **ATP 安全附件**"。
    
4. 在 "安全附件" 页面上，选中 "**启用 SharePoint、OneDrive 和 Microsoft 团队的 ATP** " 复选框，以应用广泛的保护。 
    
5. 选择 **+** 以创建新策略。 
    
6. 应用下表中的设置。 
    
7. 查看设置后，根据需要选择 "**创建此策略**" 或 "**保存**"。
    

|**设置或选项**|**推荐设置** <br/>|
|:-----|:-----|
|名称  <br/> |使用检测到的恶意软件阻止当前和将来的电子邮件。  <br/> |
|说明  <br/> |使用检测到的恶意软件阻止当前和将来的电子邮件和附件。  <br/> |
|保存附件未知的恶意软件响应  <br/> |Select **block-阻止当前和将来的包含检测到的恶意软件的电子邮件和附件**。  <br/> |
|在检测时重定向附件  <br/> |启用重定向（选择此框）输入管理员帐户或邮箱设置进行隔离。          如果恶意软件扫描附件超时或发生错误（选中此框），请应用上面的选择。  <br/> |
|应用于  <br/> |收件人域为。 . . 选择您的域。  <br/> |
|
   
有关详细信息，请参阅[设置 Office 365 ATP 反网络钓鱼策略](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)。
  
## <a name="10-protect-against-phishing-attacks-with-atp-safe-links"></a>10：使用 ATP 安全链接防御网络钓鱼攻击
<a name="phishingatp"> </a>

黑客有时会在电子邮件或其他文件的链接中隐藏恶意网站。 Office 365 ATP 安全链接（ATP 安全链接）是 Office 365 高级威胁防护的一部分，可通过在电子邮件和 Office 文档中提供 web 地址（Url）的单击验证时间来帮助保护您的组织。 通过 ATP 安全链接策略定义保护。
  
我们建议您执行以下操作：
  
- 修改默认策略以提高保护。
    
- 添加目标为域中所有收件人的新策略。
    
若要获取 ATP 安全链接，请查看[简短的培训视频](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)，或完成以下步骤：
  
1. 转到 [https://protection.office.com](https://protection.office.com) 并使用管理员帐户登录。 
    
2. 在安全 &amp; 合规性中心的左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略**"。
    
3. 在 "策略" 页上，选择 " **ATP 安全链接**"。
    
若要修改默认策略，请执行以下操作：
  
1. 在 "安全链接" 页面上，在 "**适用于整个组织的策略**" 下，双击 "**默认**策略"。 
    
2. 在 "**适用于 Office 365 中的内容**" 下，输入要阻止的 URL （如_example.com_），然后选择 "" **+** 。

3. 在 "**适用于除电子邮件以外的内容的设置**" 下，选择 " **Office 365 应用程序**"，**不要在用户单击 "安全链接" 时进行跟踪**，**不要让用户单击 "通过指向原始 URL 的安全链接"**。
    
4. 选择“**保存**”。 
    
创建一个面向域中所有收件人的新策略：
  
1. 在 "安全链接" 页面上，在 "**适用于特定收件人的策略**" 下，选择 " **+** 创建新策略"。 
    
2. 应用下表中列出的设置。
    
3. 选择“**保存**”。 
    
|**设置或选项**|**推荐设置** <br/>|
|:-----|:-----|
|名称  <br/> |域中所有收件人的安全链接策略  <br/> |
|选择邮件中未知的潜在恶意 Url 的操作  <br/> |**当用户单击链接时，将会重写并检查在已知恶意链接列表中的 "按 Url"，并对其进行检查**。  <br/> |
|对指向文件的可疑链接和链接应用实时 URL 扫描  <br/> |选中此框。  <br/> |
|应用于  <br/> |收件人域为。 . . 选择您的域。  <br/> |
|
   
有关详细信息，请参阅[Office 365 ATP 安全链接](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409)。
