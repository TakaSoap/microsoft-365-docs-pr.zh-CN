---
title: 保护业务Microsoft 365的十大方法
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
- admindeeplinkDEFENDER
- adminvideo
- admindeeplinkEXCHANGE
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: 保护你的业务电子邮件和数据免受网络威胁（包括勒索软件、网络钓鱼和恶意附件）的攻击。
ms.openlocfilehash: 2e72ca635269000fe97a555390e7c65d39d2377e
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325693"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>保护业务Microsoft 365的十大方法

如果你是使用 Microsoft 业务计划之一的中小型组织，可以使用本文中的指导来增强组织的安全性。 本指南可帮助你的组织实现《中国国家/地区学校网络安全宣传活动手册》 [中所述的目标](https://go.microsoft.com/fwlink/p/?linkid=2015598)。

> [!TIP]
> 如果需要有关本文中的步骤的帮助，请考虑 [与 Microsoft 小型企业专家合作](https://go.microsoft.com/fwlink/?linkid=2186871)。 借助业务助手，你和你的员工在发展业务时，可以针对从加入到日常使用的各个方面随时访问小型企业专家。

## <a name="watch-overview-of-security"></a>观看：安全性概述

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mzxI?autoplay=false]

Microsoft 365 商业高级版提供了威胁防护、数据保护和设备管理功能，可帮助你保护公司免受联机威胁和未经授权的访问，以及保护和管理手机、平板电脑和计算机上的公司数据。

## <a name="security-tasks-to-complete"></a>要完成的安全任务

Microsoft 建议你完成下表中列出的适用于你的服务计划的任务。

|*Number*|任务|Microsoft 365 商业标准版|Microsoft 365 商业高级版|
|---|---|---|---|
| 1 | [防止密码丢失或被盗](#1-set-up-multi-factor-authentication) | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| 2 | [培训用户](#2-train-your-users) | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| 3 | [使用专用管理员帐户](#3-use-dedicated-admin-accounts)|![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | 
| 4 | [抵御恶意软件](#4-protect-against-malware) | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/> (电子邮件保护)  | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/> (增加了对电子邮件和设备的保护)  |
| 5 | [防范勒索软件](#5-protect-against-ransomware) | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/> (保护电子邮件和云存储)  | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/> (设备、电子邮件和云存储服务增强)  |
| 6  | [停止电子邮件的自动转发](#6-stop-auto-forwarding-for-email) | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| 7  | [使用加密](#7-use-office-message-encryption) | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| 8  | [保护电子邮件免受网络钓鱼攻击](#8-protect-your-email-from-phishing-attacks) | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/> (防)  | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/> (高级防)  |
| 9  | [防范电子邮件和电子邮件文件中恶意附件、文件和OFFICE URL](#9-protect-against-malicious-attachments-files-and-urls) | | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/> (保险箱链接保险箱附件)  |
| 10  | [增强对组织设备的保护](#10-increase-protection-for-your-organizations-devices) | | ![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/> (企业级设备保护)  |

如果你有 Microsoft Business 高级版，则设置安全性并开始安全协作的最快方法就是按照以下库中的指导操作：[Microsoft 365 商业高级版](../../business-premium/index.md)。 本指南是与 Microsoft 防御百年团队合作开发的，可保护所有小型企业客户免受复杂黑客发起的网络威胁。

在开始之前，请查看Microsoft 365[门户](../../security/defender/microsoft-secure-score.md)中的安全Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">分数</a>。 在集中式仪表板中，你可以监视和提高Microsoft 365标识、数据、应用、设备和基础结构的安全性。 你可以获得配置建议安全功能、执行与安全相关的任务 (如查看报告) ，或者使用第三方应用程序或软件解决建议。 通过增加见解并更深入地了解一组更广泛的 Microsoft 产品和服务，你可以确信地报告组织的安全运行状况。

![Microsoft 安全分数的屏幕截图。](../../media/secure-score.png)

## <a name="1-set-up-multi-factor-authentication"></a>1：设置多重身份验证

通过使用多重身份验证和 MFA 身份验证，防止密码丢失 (被盗) 。 设置多重身份验证时，要求用户使用手机上的代码登录Microsoft 365。 如果黑客知道你的密码，这一额外步骤可以防止黑客接管。 

多重身份验证也称为 2 步验证。 个人可以轻松将 2 步验证添加到大多数帐户，例如，添加到其 Google 或 Microsoft 帐户。 下面将了解如何将 [两步验证添加到你的个人 Microsoft 帐户](https://go.microsoft.com/fwlink/p/?linkid=2016403)。

对于使用 Microsoft 365 的企业，添加要求用户使用多重身份验证登录的设置。 进行此更改时，用户下次登录时将提示他们设置手机进行双重身份验证。
若要观看有关如何设置 MFA 以及用户如何完成设置的培训视频，请参阅 [设置 MFA](set-up-multi-factor-authentication.md) 和 [用户设置](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)。

### <a name="to-set-up-multi-factor-authentication-you-turn-on-security-defaults"></a>若要设置多重身份验证，请打开安全默认值

对于大多数组织来说，安全默认值提供了一个级别良好的已添加登录安全性。 有关详细信息，请参阅[什么是安全性默认值？](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

如果你的订阅是新订阅，则可能已经自动启用安全默认值。

可通过 Microsoft Azure 门户中 Azure Active Directory (Azure AD) 的“**属性**”窗格启用或禁用安全性默认值。

1. 使用全局管理员凭据登录 [Microsoft 365 管理中心](https://admin.microsoft.com)。

2. 在左侧导航栏中，选择“**全部显示**”，然后在 **管理中心** 下，选择“**Azure Active Directory**”。

3. In the **Azure Active Directory admin center**， choose **Azure Active Directory** >  **Properties**.

4. 在页面底部，选择“**管理安全性默认值**”。

5. 选择“**是**”启用安全性默认值，或选择“**否**”禁用安全性默认值，然后选择“**保存**”。

为你的组织设置多重身份验证后，你的用户将需要在其设备上设置双重验证。 有关详细信息，请参阅设置[两步验证以验证Microsoft 365](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)。

> [!TIP]
> 有关更多详细信息和建议，请参阅为用户 [设置多重身份验证](set-up-multi-factor-authentication.md)。

## <a name="2-train-your-users"></a>2：培训用户

美国国家/地区学校网络安全 [宣传活动](https://go.microsoft.com/fwlink/p/?linkid=2015598) 手册提供了有关在组织中建立强大的安全意识文化的指导，包括培训用户识别网络钓鱼攻击。

此外，Microsoft 建议用户执行本文中所述的操作：保护帐户和设备免受黑客和 [恶意软件的攻击](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6)。 这些操作包括：

- 使用强密码

- 保护设备

- 在 mac 和 Windows 10 上启用安全功能

Microsoft 还建议用户采取以下文章中建议的操作来保护其个人电子邮件帐户：

- [帮助保护 Outlook.com 电子邮件帐户](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [使用 2 步验证保护 Gmail 帐户](https://go.microsoft.com/fwlink/p/?linkid=2015688&)

## <a name="3-use-dedicated-admin-accounts"></a>3：使用专用管理员帐户

用于管理环境的管理帐户Microsoft 365提升的权限。 这些是黑客和网络攻击的有价值目标。 仅将管理员帐户用于管理。 管理员应具有单独的用户帐户，用于常规的非管理用途，并且仅在必要时使用其管理帐户来完成与其工作职能相关联的任务。 其他建议：

- 请确保管理员帐户还针对多重身份验证进行设置。

- 使用管理员帐户之前，请关闭所有不相关的浏览器会话和应用，包括个人电子邮件帐户。

- 完成管理员任务后，请务必注销浏览器会话。

## <a name="4-protect-against-malware"></a>4：防范恶意软件

你的Microsoft 365环境包括恶意软件防护。 您可以通过：

- 阻止具有特定文件类型的附件
- 在设备上使用防病毒/反恶意软件保护

### <a name="block-attachments-with-certain-file-types"></a>阻止具有特定文件类型的附件

您可以通过阻止具有通常用于恶意软件的文件类型的附件来增强恶意软件保护。 若要在电子邮件中加强恶意软件保护，请观看简短的 [培训视频](increase-threat-protection.md#raise-the-level-of-protection-against-malware-in-mail)，或完成以下步骤：

1. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>， go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Anti-malware** in the **Policies** section.

2. 在 **"反恶意软件"** 页上，双击"默认" (**"默认) "**。 将出现一个飞出图。 

3. 选择 **飞出控件** 底部的"编辑保护设置"。 

4. In the next page， under **Protection settings**， select the checkbox next to **Enable the common attachments filter**. 被阻止的文件类型将列在此选项的正下方。 若要添加或删除文件类型，请选择列表末尾 **的** "自定义文件类型"。 

5. 选择“**保存**”。 

有关详细信息，请参阅 [EOP 中的反恶意软件保护](../../security/office-365-security/anti-malware-protection.md)。

### <a name="use-antivirus-and-antimalware-protection"></a>使用防病毒和反恶意软件保护

Microsoft Defender 防病毒提供强大的防病毒和反恶意软件保护，并内置于Windows操作系统中。

如果你的组织正在使用Microsoft 365 商业高级版，你可获取其他设备保护，其中包括：

- 下一代保护

- 防火墙保护

- Web 内容筛选

这些功能包含在 Microsoft Defender for Business 中，这是一项从 2022 年 3 月 1 Microsoft 365 商业高级版开始向客户推出的产品/服务。 

[详细了解 Microsoft Defender for Business](../../security/defender-business/mdb-overview.md)。

## <a name="5-protect-against-ransomware"></a>5：防范勒索软件

勒索软件通过加密文件或锁定计算机屏幕来限制对数据的访问。 然后，它尝试通过请求"勒索"（通常采用加密货币（如"为"用户"）来勒索资金，以交换对数据的访问权限。

你可以获取托管在 Microsoft 365 中的电子邮件和存储在 OneDrive 中的文件的勒索软件OneDrive。 如果你已Microsoft 365 商业高级版，你可以为组织设备获取额外的勒索软件保护。

您可以通过创建一个或多个邮件流规则来阻止通常用于勒索软件的文件扩展名，或警告通过电子邮件接收这些附件的用户，从而防范勒索软件。 一个很好的起点是创建两个规则：

- 在打开包含宏Office文件附件之前警告用户。 勒索软件可以隐藏在宏内，因此我们将警告用户不要从他们不知道的人打开这些文件。

- 阻止可能包含勒索软件或其他恶意代码的文件类型。 我们将从下表中列出的可执行文件 (一个) 。 如果组织使用这些可执行类型中的任意一种，并且希望通过电子邮件发送它们，请将其添加到上一规则中， (警告用户) 。

若要创建邮件传输规则，请观看简短的 [培训视频](increase-threat-protection.md#protect-against-ransomware)，或完成以下步骤：

1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。

2. 在" **邮件流"** 类别中，选择 **"规则"**。

3. 选择 **+**，然后选择 **"创建新规则"**。

4. 选择对话框底部的****以查看完整的选项集。

5. 针对每个规则应用下表中的设置。 保留其余设置为默认设置，除非您要更改它们。

6. 选择“**保存**”。
    
| Setting | 在打开文件附件之前Office警告 | 阻止可能包含勒索软件或其他恶意代码的文件类型 |
|:-----|:-----|:-----|
|名称  <br/> |反勒索软件规则：警告用户  <br/> |反勒索软件规则：阻止文件类型  <br/> |
|在 中应用此规则。 . .  <br/> |任何附件 。 . . 文件扩展名匹配 。 . .  <br/> |任何附件 。 . . 文件扩展名匹配 。 . .  <br/> |
|指定单词或短语  <br/> |添加以下文件类型：  <br/> dotm、docm、xlsm、sltm、xla、xlam、xll、pptm、potm、ppam、ppsm、sldm  <br/> |添加以下文件类型：  <br/> ade、adp、ani、bas、 bat， chm， cmd， com， cpl， crt， hlp， ht， hta， inf， ins， isp， job， js， jse， lnk， mda， mdb， mde， mdz， msc， msi， msp， mst， pcd， reg， scr， sct， shs， url， vb， vbe， vbs， wsc， wsf， wsh， exe， pif  <br/> |
|执行以下操作。 . .  <br/> |在免责声明前添加  <br/> |阻止邮件 。 . . 拒绝邮件并包含说明  <br/> |
|提供消息文本  <br/> |不要打开这些类型的文件（除非你希望打开它们，因为这些文件可能包含恶意代码，并且知道发件人并不能保证安全）。  <br/> ||
   
> [!TIP]
> 您还可以将要阻止的文件添加到步骤 4：防范恶意软件中的 [反恶意软件列表](#4-protect-against-malware)。

有关详细信息，请参阅：

- [勒索软件：如何降低风险](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [一起更得心防万一：Microsoft Defender 防病毒软件和 Office 365](../../security/defender-endpoint/office-365-microsoft-defender-antivirus.md)

- [还原OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="6-stop-auto-forwarding-for-email"></a>6：停止电子邮件的自动转发

通过配置邮箱以自动转发电子邮件，获得用户邮箱访问权限的黑客可能会窃取邮件。 即使没有用户感知，也可能会发生此问题。 您可以通过配置邮件流规则来防止发生这种情况。

创建邮件传输规则：

1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。

2. 在" **邮件流"** 类别中，选择 **"规则"**。

3. 选择 **+**，然后选择 **"创建新规则"**。

4. 选择 **对话框** 底部的"更多选项"以查看完整的选项集。

5. 应用下表中的设置。 将其余设置保留为默认值，除非您要更改这些设置。

6. 选择“**保存**”。

|Setting|拒绝自动将电子邮件转发到外部域|
|---|---|
|名称|阻止电子邮件自动转发到外部域|
|如果 ...|发件人 。 . . 是外部/内部 。 . . 组织内部|
|添加条件|收件人 。 . . 是外部/内部 。 . . 组织外部|
|添加条件|邮件属性 。 . . 包括邮件类型 。 . . 自动转发|
|执行以下操作...|阻止邮件 。 . . 拒绝邮件并给出说明。|
|提供消息文本|出于安全考虑，阻止在此组织外自动转发电子邮件。|

## <a name="7-use-office-message-encryption"></a>7：使用Office邮件加密

Office邮件加密包含在Microsoft 365。 已设置。 使用Office加密，组织可以在组织内外人员之间发送和接收加密的电子邮件。 Office 365 邮件加密可与 Outlook.com、Yahoo!、Gmail 和其他电子邮件服务搭配使用。 电子邮件加密有助于确保只有预期收件人才能查看邮件内容。

Office邮件加密提供两种邮件保护选项：

- 不要转发

- Encrypt

你的组织可能配置了将标签应用于电子邮件的其他选项，例如"机密"。

### <a name="to-send-protected-email"></a>发送受保护的电子邮件

In Outlook for PC， select **Options** in the email， and then choose **Permissions**.

![电子邮件加密Outlook。](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)

在 Outlook.com 中，选择 **电子邮件** 中的"保护"。 默认保护是 **"不要转发"**。 若要将其更改为加密，请选择" **更改权限加密** \> **"**。

![Outlook.com 中的电子邮件加密。](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)

### <a name="to-receive-encrypted-email"></a>接收加密电子邮件

如果收件人拥有 Outlook 2013 或 Outlook 2016 以及 Microsoft 电子邮件帐户，他们将在阅读窗格中看到有关项目受限权限的警报。 打开邮件后，收件人可以像查看任何其他邮件一样查看邮件。

如果收件人使用的是其他电子邮件客户端或电子邮件帐户（如 Gmail 或 Yahoo），他们将看到一个链接，允许他们登录阅读电子邮件或请求一次密码以在 Web 浏览器中查看邮件。 如果用户未收到电子邮件，请让他们检查其"垃圾邮件"或"垃圾邮件"文件夹。

> [!TIP]
> 有关详细信息，请参阅在适用于电脑的 Outlook 中发送[、查看和回复加密邮件](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980)。

## <a name="8-protect-your-email-from-phishing-attacks"></a>8. 保护您的电子邮件免受网络钓鱼攻击

如果已针对您的环境配置了一个或多个自定义Microsoft 365，您可以配置目标防钓鱼保护。 防钓鱼保护是 Microsoft Defender Office 365的一部分，可帮助保护组织免受基于恶意模拟的网络钓鱼攻击和其他网络钓鱼攻击。 如果您尚未配置自定义域，则无需这样做。

我们建议你通过创建一个策略来保护最重要的用户和自定义域来开始使用此保护。

若要在 Defender for Office 365 创建防钓鱼策略，请观看简短的培训视频，或完成[](increase-threat-protection.md#protect-your-email-from-phishing-attacks)以下步骤：

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>。

2. 转到策略 **&电子邮件&** \> **策略"部分中的** \>  \>"威胁策略"**"防钓鱼****"。**

3. 在"防钓鱼"页面上，选择" **+ 创建"**。 向导将启动，可分步定义防钓鱼策略。

4. 指定策略的名称、说明和设置，如下图所示。 有关详细信息，请参阅[了解 Microsoft Defender for Office 365 策略](../../security/office-365-security/set-up-anti-phishing-policies.md)。

5. 查看设置后，请根据情况选择 **"创建此** 策略 **"或"** 保存"。

|设置或选项|推荐设置|
|---|---|
|名称|域和最有价值的宣传活动人员|
|说明|确保不会模拟最重要的员工和域。|
|添加要保护的用户|选择 **+ 添加条件，收件人是**。 键入用户名或输入候选人、市场活动经理和其他重要员工成员的电子邮件地址。 您最多可以添加 20 个要防止模拟的内部和外部地址。|
|添加要保护的域|选择 **+ 添加条件，收件人域为**。 如果定义了自定义域，请输入Microsoft 365订阅关联的自定义域。 可以输入多个域。|
|选择操作|如果电子邮件由模拟用户发送：选择"将邮件重定向到其他电子邮件地址"，然后键入安全管理员的电子邮件地址;例如，securityadmin@contoso.com。 <br/> 如果电子邮件由模拟域发送：请选择"隔离 **邮件"**。|
|邮箱智能|默认情况下，创建新的反钓鱼策略时，将选择邮箱智能。 最好将此设置保留为“打开”。|
|添加受信任的发件人和域|在此示例中，不要定义任何替代项。|
|应用于|选择“收件人域为”。 在“以下任何项”中，选择“选择”。 选择“+ 添加”。 选中域名称旁边的复选框，例如，contoso.com，在列表中，然后选择"添加 **"**。 选择“完成”。|

> [!TIP]
> 有关详细信息，请参阅在 [Defender for Office 365 中设置防钓鱼Office 365](../../security/office-365-security/configure-atp-anti-phishing-policies.md)。

## <a name="9-protect-against-malicious-attachments-files-and-urls"></a>9：防范恶意附件、文件和 URL

人们定期发送、接收和共享附件，如文档、演示文稿、电子表格等。 通过查看电子邮件来判断附件是安全还是恶意并不总是那么容易。 Microsoft Defender for Office 365包括保险箱附件保护，但默认情况下不会启用此保护。 我们建议您创建一个新规则以开始使用此保护。 此保护扩展到 SharePoint、OneDrive 和 Microsoft Teams 中的文件。

### <a name="set-up-safe-attachments"></a>设置保险箱附件

若要创建保险箱附件策略，请观看简短的[培训视频](increase-threat-protection.md)，或完成以下步骤：

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>门户，然后使用管理员帐户登录。

2. 转到策略 **&电子邮件&** \> **策略"&** \>  \> **策略""反** 恶意软件 **"** 部分。

3. 选择 **+ 创建** 以创建新策略。

4. 应用下表中的设置。

5. 查看设置后，请根据情况选择 **"创建此** 策略 **"或"** 保存"。

|设置或选项|推荐设置|
|---|---|
|名称|使用检测到的恶意软件阻止当前和将来的电子邮件。|
|说明|使用检测到的恶意软件阻止当前和未来的电子邮件和附件。|
|保存附件未知恶意软件响应|选择 **"阻止 - 阻止当前和未来包含检测到的恶意软件的电子邮件和附件"**。|
|检测时重定向附件|启用重定向 (选中此框)  <br/> 输入管理员帐户或邮箱设置以隔离。 <br/> 如果恶意软件扫描附件出现时间过或出现错误，请应用 (选中此框) 。|
|应用于|收件人域为 。 . . 选择你的域。|

> [!TIP]
> 有关详细信息，请参阅在 [Defender for Office 365 中设置防钓鱼Office 365](../../security/office-365-security/configure-atp-anti-phishing-policies.md)。

### <a name="set-up-safe-links"></a>设置保险箱链接

黑客有时会在电子邮件或其他文件中的链接中隐藏恶意网站。 保险箱链接是 Microsoft Defender for Office 365 的一部分，可通过提供电子邮件和 Office 文档中的 Web 地址 (URL) 点击时间验证，帮助保护你的组织。 保护通过链接保险箱定义。

执行以下操作以抵御攻击：

- 修改默认策略以提高保护。

- 添加面向域中所有收件人的新策略。

若要访问保险箱，请观看简短的[培训视频](increase-threat-protection.md#protect-against-phishing-attacks-with-safe-links)，或完成以下步骤：

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>门户，然后使用管理员帐户登录。

2. 转到策略 **&电子邮件&** \> **策略"&** \>  \> **策略""反** 恶意软件 **"** 部分。

3. 选择 **+ 创建** 以创建新策略，或修改默认策略。

修改默认策略：

1. 双击"默认 **"** 策略。 将出现一个飞出图。 

2. 选择 **飞出控件** 底部的"编辑保护设置"。

3. 修改默认策略后，选择"保存 **"**。

|设置或选项|推荐设置|
|---|---|
|名称|保险箱域中所有收件人的链接策略|
|为邮件中的未知潜在恶意 URL 选择操作|选择打开 - 当用户单击链接时，URL 将被重写，并针对 **已知恶意链接列表进行检查**。|
|对指向文件的可疑链接应用实时 URL 扫描|选中此框。|
|应用于|收件人域为 。 . . 选择你的域。|

> [!TIP]
> 有关详细信息，请参阅 [microsoft Defender 保险箱中的链接Office 365](../../security/office-365-security/atp-safe-links.md)。

## <a name="10-increase-protection-for-your-organizations-devices"></a>10：增强对组织设备的保护

Microsoft Defender 防病毒内置于 Windows 操作系统中，并提供了抵御病毒和恶意软件的良好保护。 但是，可以通过将组织设备载入 Microsoft Defender for Business（一种适用于中小型企业（如你这样的新产品）来增强对设备的保护。 使用 Defender for Business，可以更好地保护组织设备免受勒索软件、恶意软件、网络钓鱼和其他威胁的攻击。

**从 2022 年 3 月 1 开始，[Microsoft Defender for Business](../../security/defender-business/index.yml) 功能** 将添加到 Microsoft 365 商业高级版。 


若要了解详细信息，请参阅以下资源：

- [Microsoft Defender for Business 概述](../../security/defender-business/mdb-overview.md)

- [设置和配置 Microsoft Defender for Business](../../security/defender-business/mdb-setup-configuration.md)

- [开始使用 Microsoft 365 Defender 门户](../../security/defender-business/mdb-get-started.md)

## <a name="related-content"></a>相关内容

[Microsoft 365 (](multi-factor-authentication-microsoft-365.md)多重身份验证) \
[管理和监视优先级帐户 (](../setup/priority-accounts.md) 文章) \
[Microsoft 365中心中的报告 (](../activity-reports/activity-reports.md)视频) 