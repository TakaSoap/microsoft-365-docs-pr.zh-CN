---
title: 增强威胁防护
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5abfef7b-5957-484a-b06b-a7c55e013e44
description: 获取有关在 Microsoft 365 商业版中提高保护级别的帮助
ms.openlocfilehash: 9b17af7f6dde321fb8da758f0cc8223e5f488121
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "38676100"
---
# <a name="increase-threat-protection"></a>增强威胁防护

本文可帮助你提高 Microsoft 365 订阅中的保护，以防止出现网络钓鱼、恶意软件和其他威胁。 这些建议适用于具有更高安全性需求的组织，如政治市场、法律办事处和卫生保健诊所。 

在开始之前，请检查您的 Office 365 安全分数。 Office 365 安全分数根据您的常规活动和安全设置来分析 Office 365 组织的安全性，并给出分数。 首先记录你的当前分数。 采取本文中建议的操作可提高您的成绩。 目标不能达到最大分数，但请注意保护您的环境不会对用户的工作效率造成负面影响的机会。 

有关详细信息，请参阅[Microsoft 安全分数](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)。


## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>提高针对邮件中的恶意软件的保护级别

你的 Office 365 或 Microsoft 365 环境包括针对恶意软件的防护，但你可以通过阻止常见恶意软件使用的文件类型的附件来提高此保护。 若要增大电子邮件的恶意软件保护，请执行以下操作：
  
1. 转到[https://protection.office.com](https://protection.office.com)并使用你的管理员帐户凭据登录。 
    
2. 在 "Office 365 安全&amp;合规中心" 的左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略** \> **反恶意软件**"。
    
3. 双击默认策略以编辑此公司范围的策略。
    
4. 单击 "**设置**"。
    
5. 在 "**常用附件类型筛选器**" 下，选择 **"启用"**。 被阻止的文件类型在此控件正下方的窗口中列出。  请确保添加以下 filetypes：
   - ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、.hlp、超线程、hta、inf、jse、mdz、作业、js、、.lnk、mda、mdb、mde、、msc、msi、msp、mst、vb、vbe、scr、pcd、shs、wsh、  <br/> 如果需要，您可以稍后添加或删除文件类型。
    
6. 单击“保存”。****
    
有关详细信息，请参阅[反恶意软件保护](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409)。
  


## <a name="protect-against-ransomware"></a>防御勒索软件

勒索软件通过加密文件或锁定计算机屏幕来限制对数据的访问。 然后，它会通过在 exchange 中请求 "勒索" （通常为 "Bitcoin" 形式）（通常为 ""），在 exchange 中获取数据访问权限，从而从受害人 extort。 
  
您可以通过创建一个或多个邮件流规则来阻止勒索软件常用的文件扩展名（在 "在[邮件中提高保护级别](#raise-the-level-of-protection-against-malware-in-mail)" 一步骤中添加的），或警告用户在电子邮件中接收这些附件，从而防止勒索软件受到侵害。

除了在上一步中阻止的文件，在打开包含宏的 Office 文件附件之前，创建规则来警告用户也是一种很好的做法。 勒索软件可以隐藏在宏中，因此我们将警告用户不要从他们不知道的人打开这些文件。

若要创建邮件传输规则，请执行以下操作：
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>转到 "管理中心"，然后选择 "**管理中心** \> **Exchange**"。
    
2. 在 "**邮件流**" 类别中，单击 "**规则**"。
    
3. 单击**+**""，然后单击 "**创建新规则**"。
    
4. 单击对话框底部的 "**更多选项**" 以查看完整的选项集。 
    
5. 对规则应用下表中的设置。 将其余设置保留为默认值，除非您要对其进行更改。
    
6. 单击“保存”****。
    
|**设置**|**在打开 Office 文件附件之前警告用户**||
|:-----|:-----|:-----|
|名称  <br/> |反勒索软件规则：警告用户  <br/>  |
|在以下情况应用此规则。 . .  <br/> |任何附件。 . . 文件扩展名匹配。 . .  <br/> |
|指定字词或短语  <br/> |添加以下文件类型：  <br/> normal.dotm、.docm、xlsm、sltm、xlodbc.xla 加载、.xlam、xll、.pptm、potm、.ppam、ppsm、sldm  <br/>|
|执行以下操作。 . .  <br/> |使用邮件通知收件人  <br/> |
|提供邮件文本  <br/> |请勿从不知道的人打开这些类型的文件，因为它们可能包含恶意代码的宏。  <br/> |
   
有关详细信息，请参阅：
  
- [如何处理勒索软件](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [还原你的 OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)
    


## <a name="stop-auto-forwarding-for-email"></a>停止电子邮件的自动转发

通过将邮箱设置为自动转发电子邮件，获取对用户邮箱的访问权限的黑客可以盗取您的邮件。 即使没有用户的意识，也会发生这种情况。 您可以通过配置邮件流规则来防止这种情况发生。 
  
若要创建邮件传输规则，请观看[此简短视频](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7)或按照以下步骤操作：
  
1. 在 Microsoft 365 管理中心，单击 "**管理中心** \> **Exchange**"。
    
2. 在 "**邮件流**" 类别中，单击 "**规则**"。
    
3. 单击**+**""，然后单击 "**创建新规则**"。
    
4. 单击对话框底部的 "**更多选项**" 以查看完整的选项集。 
    
5. 应用下表中的设置。 将其余设置保留为默认值，除非您要对其进行更改。
    
6. 单击“保存”****。
    
|**设置**|**在打开 Office 文件附件之前警告用户**|
|:-----|:-----|
|名称  <br/> |阻止电子邮件自动转发到外部域  <br/> |
|在以下情况应用此规则 .。。  <br/> |发件人。 . . 为外部/内部。 . . 组织内部  <br/> |
|添加条件  <br/> |邮件属性。 . . 包含邮件类型。 . . 自动转发  <br/> |
|执行以下操作 .。。  <br/> |阻止邮件。 . . 拒绝邮件并提供说明。  <br/> |
|提供邮件文本  <br/> |出于安全考虑，将阻止此组织外部的自动转发电子邮件。  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a>保护你的电子邮件免受网络钓鱼攻击

如果您为 Office 365 或 Microsoft 365 环境配置了一个或多个自定义域，则可以配置目标的反网络钓鱼保护。 ATP 反网络钓鱼保护是 Office 365 高级威胁防护的一部分，可帮助保护您的组织免受基于恶意模拟的网络钓鱼攻击和其他网络钓鱼攻击。 如果尚未配置自定义域，则无需执行此操作。
  
我们建议您通过创建策略来保护最重要的用户和您的自定义域，以此来开始保护。 

  
若要创建 ATP 反网络钓鱼策略，请观看[此简短的培训视频](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)，或完成以下步骤：
  
1. 转到 [https://protection.office.com](https://protection.office.com)。 
    
2. 在 "Office 365 安全&amp;合规中心" 的左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略**"。
    
3. 在 "**策略**" 页上，选择 " **ATP 反网络钓鱼**"。
    
4. 在 "**反钓鱼网站**" 页上，选择 " **+ 创建**"。 向导将启动，引导您完成定义您的反网络钓鱼策略。
    
5. 按照下表中的建议，指定策略的名称、说明和设置。 有关详细信息，请参阅[了解 ATP 反网络钓鱼策略选项](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)。 
    
6. 查看设置后，根据需要选择 "**创建此策略**" 或 "**保存**"。
    

|**设置或选项**<br/>|**推荐设置** <br/>|
|:-----|:-----|
|名称  <br/> |域和最有价值的市场活动员工  <br/> |
|说明  <br/> |确保不会模拟大多数重要的人员和我们的域。  <br/> |
|添加要保护的用户  <br/> |选择 **+ 添加条件，收件人为**。 键入用户名称或输入候选人、活动经理和其他重要教职员工成员的电子邮件地址。 您最大可以添加20个要从模拟中保护的内部和外部地址。  <br/> |
|添加要保护的域  <br/> |选择 **"+ 添加条件，收件人域为"**。 输入与 Microsoft 365 订阅关联的自定义域（如果已定义一个）。 您可以输入一个以上的域。  <br/> |
|选择操作  <br/> |如果模拟用户发送电子邮件：选择 "**将邮件重定向到另一个电子邮件地址**"，然后键入安全管理员的电子邮件地址;例如，*刘爱琳<span><span>@contoso .com*。          如果由模拟域发送电子邮件：选择 "**隔离邮件**"。  <br/> |
|邮箱智能  <br/> |默认情况下，当您创建新的反网络钓鱼策略时，将选择邮箱智能。 将此设置保留为 **"开"** 以获得最佳效果。  <br/> |
|添加受信任的发件人和域  <br/> |你可以在此处添加你自己的域或任何其他受信任域。  <br/> |
|应用于  <br/> |选择 **"收件人域"**。 在**以下任一情况**下，选择 "**选择**"。 选择 " **+ 添加**"。 选中域名称旁边的复选框，例如 " *contoso"。<span>com <span>*，请在列表中，然后选择 "**添加**"。 选择 "**完成**"。  <br/> |
   
有关详细信息，请参阅[设置 Office 365 ATP 反网络钓鱼策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)。
  
## <a name="protect-against-malicious-attachments-files-and-links-with-advanced-threat-protection-atp"></a>使用高级威胁防护（ATP）防止恶意附件、文件和链接

![指向的标题https://aka.ms/aboutM365preview。](../business/media/m365admincenterchanging.png)

首先，请确保在管理中心<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>启用新的管理中心预览。打开**新管理中心**的文本旁边的切换。

   ![上的新管理中心预览。](media/previewon.png)

如果你的租户中未显示 "**设置**" 页面，请参阅如何在 Office 365 安全&amp;合规中心中完成这些步骤。 请参阅[在安全 & 合规性中心中设置 atp 安全附件](#set-up-atp-safe-attachments-in-the-security--compliance-center)，并[在安全 & 合规性中心中设置 atp 安全链接](#set-up-atp-safe-links-in-the-security--compliance-center)。

1.  在左侧导航中，选择 "**设置**"。
2. 在 "**设置**" 页面上，选择 "**增加对来自高级威胁的保护**" 卡片的 "**查看**"。</br></br>
    ![选择 "从高级威胁提高保护" 上的 "查看"。](media/startatp.png) 

3. 在 "**提高来自高级威胁的保护**" 页上，选择 "**已启动**"。
4. 在打开的窗格中，选中 "**电子邮件中的链接和附件**" 旁边的复选框，**扫描 SharePoint、OneDrive 和团队**中的文件，并在 "扫描项目" 下的 Office **Online 应用中扫描链接**以**查找恶意内容**。

      - **在 "电子邮件中的链接和附件**" 下，键入所有用户或要扫描其电子邮件的特定用户。

    ![选中 "增加 protestion 中的所有复选框，并从高级威胁"。](media/setatp.png)
5. 选择 "**创建策略**" 以打开 ATP 安全附件和 atp 安全链接。

### <a name="set-up-atp-safe-attachments-in-the-security--compliance-center"></a>在安全 & 合规中心中设置 ATP 安全附件

用户定期发送、接收和共享附件，如文档、演示文稿、电子表格等。 只需查看一封电子邮件，就能判断附件是安全还是恶意的，并不总是容易。 Office 365 高级威胁防护包括 ATP 安全附件保护，但默认情况下不启用此保护。 我们建议您创建一个新规则以开始使用此保护。 此保护功能扩展到 SharePoint、OneDrive 和 Microsoft 团队中的文件。
  
若要创建 ATP 安全附件策略，请观看[此简短视频](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)，或完成以下步骤：
  
1. 转到[https://protection.office.com](https://protection.office.com)并使用管理员帐户登录。 
    
2. 在 "Office 365 安全&amp;合规中心" 的左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略**"。
    
3. 在 "策略" 页上，选择 " **ATP 安全附件**"。
    
4. 在 "安全附件" 页面上，选中 "**启用 SharePoint、OneDrive 和 Microsoft 团队的 ATP** " 复选框，以应用广泛的保护。 
    
5. 选择**+** 以创建新策略。 
    
6. 应用下表中的设置。 
    
7. 查看设置后，根据需要选择 "**创建此策略**" 或 "**保存**"。
    

|**设置或选项**|**推荐设置** <br/>|
|:-----|:-----|
|名称  <br/> |使用检测到的恶意软件阻止当前和将来的电子邮件。  <br/> |
|说明  <br/> |使用检测到的恶意软件阻止当前和将来的电子邮件和附件。  <br/> |
|保存附件未知的恶意软件响应  <br/> |Select **block-阻止当前和将来的包含检测到的恶意软件的电子邮件和附件**。  <br/> |
|在检测时重定向附件  <br/> |启用重定向（选择此框）输入管理员帐户或邮箱设置进行隔离。          如果恶意软件扫描附件超时或发生错误（选中此框），请应用上面的选择。  <br/> |
|应用于  <br/> |收件人域为。 . . 选择您的域。  <br/> |
   
有关详细信息，请参阅[设置 Office 365 ATP 反网络钓鱼策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)。
  
### <a name="set-up-atp-safe-links-in-the-security--compliance-center"></a>在安全 & 合规中心中设置 ATP 安全链接

黑客有时会在电子邮件或其他文件的链接中隐藏恶意网站。 Office 365 ATP 安全链接（ATP 安全链接）是 Office 365 高级威胁防护的一部分，可通过在电子邮件和 Office 文档中提供 web 地址（Url）的单击验证时间来帮助保护您的组织。 通过 ATP 安全链接策略定义保护。
  
我们建议您执行以下操作：
  
- 修改默认策略以提高保护。
    
- 添加目标为域中所有收件人的新策略。
    
若要设置 ATP 安全链接，请观看[此简短的培训视频](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)，或完成以下步骤：
  
1. 转到[https://protection.office.com](https://protection.office.com)并使用管理员帐户登录。 
    
2. 在 "Office 365 安全&amp;合规中心" 的左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略**"。
    
3. 在 "策略" 页上，选择 " **ATP 安全链接**"。
    
若要修改默认策略，请执行以下操作：
  
1. 在 "安全链接" 页面上，在 "**适用于整个组织的策略**" 下，选择 "**默认**策略"。 
    
2. 在 "**适用于除电子邮件以外的内容的设置**" 下，选择 " **office 365 专业增强版，office For iOS 和 Android**"。
    
3. 单击“保存”****。 
    
创建一个面向域中所有收件人的新策略：
  
1. 在 "安全链接" 页面上，在 "**适用于整个组织**的策略**+** " 下，单击 "创建新策略"。 
    
2. 应用下表中列出的设置。
    
3. 单击“保存”****。 

|**设置或选项**|**推荐设置** <br/>|
|:-----|:-----|
|名称  <br/> |域中所有收件人的安全链接策略  <br/> |
|选择邮件中未知的潜在恶意 Url 的操作  <br/> |**当用户单击链接时，将会重写并检查在已知恶意链接列表中的 "按 Url"，并对其进行检查**。  <br/> |
|使用安全附件扫描可下载的内容  <br/> |选中此框。  <br/> |
|应用于  <br/> |收件人域为。 . . 选择您的域。  <br/> |
   
有关详细信息，请参阅[Office 365 ATP 安全链接](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409)。
  
## <a name="turn-on-the-unified-audit-log"></a>打开统一审核日志

在安全&amp;合规中心中打开审核日志搜索后，可以将管理员和其他用户活动保留在日志中并进行搜索。 

您必须在 Exchange Online 中向您分配 "审核日志" 角色，以便在 Microsoft 365 商业版订阅中打开或关闭审核日志搜索。 默认情况下，此角色在 Exchange 管理中心中的 "权限" 页上分配给合规性管理和组织管理角色组。 默认情况下，Microsoft 365 中的全局管理员是此组的成员。

1. 若要启用审核日志搜索，请转到管理中心<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> ，然后在左侧导航中的 "**管理中心**" 下选择 "**合规性**"。 
2. 在 " **Microsoft 365 合规性**" 页面上，选择 "**更多资源**"，然后**打开**" **Office 365 安全&amp;中心**卡"。

    ![在 Office 365 安全 & 合规性轿车上选择 "打开"。](media/gotosecandcomp.png)
3. 在 "安全性和合规性" 页上，依次选择 "**搜索**" 和 "**审核日志搜索**"。
1. 在 "**审核日志搜索**" 页的顶部，选择 "**启用审核**"。

打开该功能后，您可以搜索文件、文件夹和多个活动。 有关详细信息，请参阅[搜索审核日志](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance)。

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>优化 SharePoint 和 OneDrive 文件和文件夹的匿名共享设置

（将默认匿名链接过期时间更改为14天，将默认共享类型更改为 "特定人员"）若要更改 OneDrive 和 SharePoint 的共享设置，请执行以下操作：
1. 转到 "管理中心" <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> ，然后在左侧导航中选择 "**管理中心**" 下的 " **SharePoint** "。 
2. 在 SharePoint 管理中心中，转到 "**策略** \> **共享**"。
3. 在 "**共享**" 页面的 "**文件和文件夹链接**" 下，选择 "**特定人员**"，在 **"任何人" 链接的 "高级设置**" 下，选择 "**这些链接必须在此天数内过期**"，并键入 "14" （或希望限制链接生存期的其他天数）。

    ![选择 "特定人员"，并将 "链接过期" 设置为14天。](media/anyonelinks.png)

## <a name="activity-alerts"></a>活动通知

您可以使用活动警报跟踪管理员和用户活动，并检测组织中的恶意软件和数据丢失防护事件。 你的订阅包含一组默认策略，但你也可以创建自定义策略。 有关详细信息，请参阅[警报策略](https://docs.microsoft.com/office365/securitycompliance/alert-policies)。 例如，如果您在 SharePoint 中存储不希望任何人在外部共享的重要文件，则可以创建通知，以便在用户确实共享时通知您。

下图显示了 Microsoft 365 商业版中包含的默认策略。 <br/><br/>
    ![Microsoft 365 商业版中包含的默认通知策略。](media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>禁用或管理日历共享

您可以阻止组织中的人员共享其日历，也可以管理他们可以共享的内容。 例如，您可以将共享限制为仅限共享忙/闲时间。

1. 转到管理中心<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> ，然后选择 "**设置** \> **服务" & 外接程序**
2. 在 "**服务" & "外接程序**" 页上，选择 "**日历**"，并选择组织中的人员是否可以与拥有 Office 365 或 Exchange 或任何人的用户共享其日历。 
    如果选择 "与任何人共享"，则可以决定只共享忙/闲信息。

3. 在页面底部选择 "**保存更改**"。

    下图显示了不允许的日历共享。 </br></br>
    ![显示不允许的外部日历共享的屏幕截图。](media/nocalendarsharing.png)

    下图显示了允许使用仅忙/闲信息的电子邮件链接进行日历共享时的设置。

   ![与任何人共享日历忙/闲信息的屏幕截图。](media/sharefreebusy.png)

如果允许您的用户共享其日历，请参阅[这些说明](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5)了解如何从 web 上的 Outlook 共享。