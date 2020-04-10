---
title: 使用基于 Windows 的 DNS 为 Office 365 创建 DNS 记录
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: 了解如何验证您的域并为 Office 365 的基于 Windows 的 DNS 中的电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: d33a2f79111f8951c3ec31ca5680877ad2e7d570
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210560"
---
# <a name="create-dns-records-for-office-365-using-windows-based-dns"></a>使用基于 Windows 的 DNS 为 Office 365 创建 DNS 记录

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
   
如果使用基于 Windows 的 DNS 托管自己的 DNS 记录，请遵循本文中的步骤为电子邮件、Skype for Business Online 等设置记录。
  
若要开始，您需要[在基于 Windows 的 dns 中查找 dns 记录](#find-your-dns-records-in-windows-based-dns)，以便您可以对其进行更新。 此外，如果您计划将本地 Active Directory 与 Office 365 同步，请参阅[在本地 Active directory 中用作 UPN 的不可路由电子邮件地址](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)。
  
添加 DNS 记录后出现邮件流或其他问题的问题，请参阅[在更改域名或 DNS 记录后解决问题](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>在基于 Windows 的 DNS 中查找 DNS 记录
<a name="BKMK_find_your_dns_1"> </a>转到包含您的域的 DNS 记录的页面。 如果是在 Windows Server 2008 中工作，请转到 "**开始** > " "**运行**"。 如果使用的是 Windows Server 2012，请按 Windows 键和**r**键。 键入 " **Dnsmgmnt**"，然后选择 **"确定"**。 在 dns 管理器中，展开** \<"\> \> DNS 服务器名称" 正向查找区域  **"。 选择域。 现在已准备好创建 DNS 记录。
   
## <a name="add-mx-record"></a>添加 MX 记录
<a name="BKMK_add_MX"> </a>

添加 MX 记录，以便您的域的电子邮件将发往 Office 365。
- 您添加的 MX 记录包括以下类似值（" **指向地址**"值）：\<MX token\>.mail.protection.outlook.com，其中，\<MX 令牌\> 是类似于 MSxxxxxxx 的值。 
- 从 Office 365 的 "添加 DNS 记录" 页的 "Exchange Online" 部分的 "MX" 行中，复制 "磅到地址" 下方列出的值。 你将在此任务中创建的记录中使用此值。 
- 在域的 "DNS 管理器" 页上，转到 "**操作** > **邮件交换器（MX）**"。 若要在此域中查找此页面，请参阅[在基于 Windows 的 dns 中查找 DNS 记录](#find-your-dns-records-in-windows-based-dns)。  
- 在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"： 
    - 主机名： 
    - @Address：将 "磅" 粘贴到您刚刚从 Office 365 中复制的地址值。  
    - Pref: 
- 选择 "**保存更改**"。
- 请删除任何已过时的 MX 记录。 如果此域的任何旧 MX 记录将电子邮件路由到其他位置，则选中每个旧记录旁边的复选框，然后选择 "**删除** > **" 确定 "**。 
   
## <a name="add-cname-records"></a>添加 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

添加 Office 365 所需的 CNAME 记录。 如果 Office 365 中列出了其他 CNAME 记录，则按照此处所示的相同常规步骤进行添加。
  
> [!IMPORTANT]
> 如果您有 Office 365 的 Mobile Device Manager (MDM)，则必须创建另外两个 CNAME 记录。 创建流程与你用于其他四个 CNAME 记录的流程一样，但需提供下表中的值。 （如果没有 MDM，则可以跳过此步骤。） 

- 在域的 "DNS 管理器" 页上，转到 "**操作** > **CNAME （cname）**"。
- 在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"：  
    - 主机名称：自动发现
    - 类型： 
    - Cname 地址： autodiscover.outlook.com
- 选择 " **O**K"。

添加 SIP CNAME 记录。 
- 在域的 "DNS 管理器" 页上，转到 "**操作** \> **CNAME （cname）**"。 
- 在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"：  
    - 主机名： sip
    - 类型： CNAME
    - 地址： sipdir.online.lync.com
- 选择“确定”****。

添加 Skype for Business Online 自动发现 CNAME 记录。  
- 在域的 "DNS 管理器" 页上，转到 "**操作** \> **CNAME （cname）**"。 在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"：  
    - 主机名： lyncdiscover。
    - 类型： CNAME
    - 地址： webdir.online.lync.com
- 选择“确定”****。
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-office-365"></a>为适用于 Office 365 的移动设备管理 (MDM) 添加两个 CNAME 记录

> [!IMPORTANT]
> 如果您有 Office 365 的 Mobile Device Manager (MDM)，则必须创建另外两个 CNAME 记录。 创建流程与你用于其他四个 CNAME 记录的流程一样，但需提供下表中的值。 > （如果没有 MDM，可以跳过此步骤。） 
  

添加 MDM Enterpriseregistration CNAME 记录。  
- 在域的 "DNS 管理器" 页上，转到 "**操作** \> **CNAME （cname）**"。 
- 在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"：  
- 主机名： enterpriseregistration
- 类型： CNAME
- 地址： enterpriseregistration.windows.net
- 选择“确定”****。 

添加 MDM Enterpriseenrollment CNAME 记录。 
-  在域的 "DNS 管理器" 页上，转到 "**操作** \> **CNAME （cname）**"。 
-  在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"：  
    - 主机名： enterpriseenrollment
    - 类型： CNAME
    - 地址： enterpriseenrollment-s.manage.microsoft.com
- 选择“确定”****。
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 If you already have an SPF record for your domain, don't create a new one for Office 365. 可以将所需的 Office 365 添加到当前记录，这样就拥有包含两组值的*单个*SPF 记录。 
  
为您的域添加 SPF TXT 记录以帮助防止垃圾邮件。
  
- 您可能已在此记录的"TXT"值中拥有其他字符串（例如，营销电子邮件的字符串），这样没关系。请将那些字符串留在原位并添加此字符串，并在每个字符串两侧加上双引号以将它们隔开。 
- 在您的域的 "DNS 管理器" 页上，转到 "**操作** \> **文本（TXT）**"。 
-  在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"。 
 > [!IMPORTANT]
> 在某些版本的 Windows DNS 管理器中，可能已对域进行了设置，以便在创建 txt 记录时，主页名称默认为父域。 在这种情况下，添加 TXT 记录时，将主机名设置为空（没有值），而不是将其设置为 @ 或域名。 

-  主机类型：@
-  记录类型： TXT
-  Address： v = spf1 包括 include spf.protection.outlook.com-all 
         
-  选择“确定”****。
   
## <a name="add-srv-records"></a>添加 SRV 记录
<a name="BKMK_add_SRV"> </a>

添加 Office 365 所需的两个 SRV 记录。

为 Skype for Business Online Web 会议添加 SIP SRV 记录。  <br/> 
-  在您的域的 "DNS 管理器" 页上，转到 "**操作** \> **其他新记录**"。 
-   在 "**资源记录类型**" 窗口中，选择 "**服务位置（SRV）**"，然后选择 "**创建记录**"。 
-   在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"：  
    -  服务： _sip
    -  协议： _tls
    -  优先级： 100
    -  权重： 1
    -  端口： 443
    -  目标（Hostname）： sipdir.online.lync.com
-  选择“确定”****。 


为 Skype for Business Online 联盟添加 SIP SRV 记录。  
-  在您的域的 "DNS 管理器" 页上，转到 "**操作** \> **其他新记录**"。  
-  在 "**资源记录类型**" 窗口中，选择 "**服务位置（SRV）**"，然后选择 "**创建记录**"。 
-   在 "**新建资源记录**" 对话框中，确保字段已设置为 "正好为以下值"：  
    -  服务： _sipfederationtls
    -  协议： _tcp
    -  优先级： 100
    -  权重： 1
    -  端口： 5061
    -  目标（Hostname）： sipfed.online.lync.com
-  选择“确定”****。 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>添加记录以验证您拥有该域（如果尚未验证）
<a name="BKMK_verify"> </a>

添加 DNS 记录以设置您的 Office 365 服务之前，Office 365 必须确认您拥有正在添加的域。为此，请按照以下步骤添加记录。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 
  

1. 从 Office 365 收集信息。  <br/> 
2. 在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。 
3. 在 "**域**" 页上，在要验证的域的 "**操作**" 列中，选择 "**启动安装程序**"。 
4. 在 "**将域添加到 Office 365** " 页上，选择 "**开始步骤 1**"。 
5. 在 "**确认您是否拥有**您的域" 页上的 "**请参阅有关使用此步骤执行此步骤的说明**" 下拉列表中，选择 "**常规说明**"。 
6. 从表中，复制"目标地址或指向的地址"值。 您将在下一步骤中需要它。 建议您复制并粘贴此值，以确保所有空格保持正确。

添加 TXT 记录。 
-  在您的域的 "DNS 管理器" 页上，转到 "**操作** \> **文本（TXT）**"。 
-   在 "**新建资源记录**" 对话框中，选择 "**编辑**"。  
-  在 "**新建资源记录**" 对话框的 "**自定义主机名称**" 区域中，请确保字段已设置为以下值。 

> [!IMPORTANT] 
> 在某些版本的 Windows DNS 管理器中，可能已对域进行了设置，以便在创建 txt 记录时，主页名称默认为父域。 在这种情况下，添加 TXT 记录时，将主机名设置为空（没有值），而不是将其设置为 @ 或域名。 

- 主机名：@
- 类型： TXT
- Address：将目标或指向您刚刚从 Office 365 中复制的地址值粘贴到此处。  
- 选择 **"确定** > **完成**"。

在 Office 365 中验证您的域。  
> [!IMPORTANT]
> 在执行此操作之前，请等待大约15分钟，以便您刚刚创建的记录可以通过 Internet 进行更新。       

- 返回到 Office 365 并按照下面的步骤请求验证检查。 该检查将查找上一步中添加的 TXT 记录。 找到正确的 TXT 记录时，该域通过验证。  
1. 在管理中心中，转到 "**安装** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。
2. 在 "**域**" 页上，在要验证的域的 "**操作**" 列中，选择 "**启动安装程序**"。 
3. 在 "**确认你是否拥有域**" 页面上，选择 **"已完成，立即验证**"，然后在确认对话框中选择 "**完成**"。 
   
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>在本地 Active Directory 中用作 UPN 的不可路由电子邮件地址
<a name="BKMK_ADNote"> </a>

如果计划使用 Office 365 同步本地 Active Directory，请确保 Active Directory 用户主体名称 (UPN) 后缀为有效域后缀，而不是不受支持的域后缀，如 @contoso.local。 如果需要更改 UPN 后缀，请参阅 how [to prepare a 不可路由的域以进行目录同步](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7)。
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
