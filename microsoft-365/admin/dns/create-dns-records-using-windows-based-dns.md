---
title: 使用基于 Windows 的 DNS 为 Microsoft 创建 DNS 记录
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: 了解如何验证域，并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录Windows Microsoft 基于 DNS。
ms.openlocfilehash: 0349366e1cb3af23de1161a69b9b37305cc1237a
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313477"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>使用基于 Windows 的 DNS 为 Microsoft 创建 DNS 记录

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。 
   
如果使用基于 Windows 的 DNS 托管自己的 DNS 记录，请遵循本文中的步骤为电子邮件、Skype for Business Online 等设置记录。
  
若要开始，你需要在基于 DNS Windows DNS 中查找 [DNS](#find-your-dns-records-in-windows-based-dns) 记录，以便可以更新它们。 此外，如果计划将本地 Active Directory 与 Microsoft 同步，请参阅在本地 [Active Directory 中用作 UPN](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory) 的不可路由电子邮件地址。
  
添加 DNS 记录后遇到邮件流问题或其他问题，请参阅更改域名或 DNS 记录后的问题 [疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>在基于 Windows 的 DNS 中查找 DNS 记录
<a name="BKMK_find_your_dns_1"> </a> 转到包含域的 DNS 记录的页面。 如果您在 Windows Server 2008 中工作，请转到 **StartRun** > 。 如果在 Windows Server 2012 中工作，请按 Windows 徽标键和 **r**。 键入 **dnsmgmnt.msc**，然后选择 **确定**。 在 DNS 管理器中，展开 **"\<DNS server name\>\>前向查找区域"**。 选择域。 现在已准备好创建 DNS 记录。
   
## <a name="add-mx-record"></a>添加 MX 记录
<a name="BKMK_add_MX"> </a>

添加 MX 记录，以便你的域的电子邮件发送到 Microsoft。
- 您将添加的 MX 记录包含 (指向地址值) 的值如下所示：\<MX token\>.mail.protection.outlook.com，\<MX token\>其中 是类似于 MSxxxxxxx 的值。 
- 从 Microsoft"添加 DNS Exchange Online"页面的"地址"部分中的"MX"行中，复制"指向地址"下列出的值。 您将在此任务创建的记录中使用此值。 
- 在域的"DNS 管理器"页面上，转到"**ActionMail** >  **Exchanger (MX) "**。 若要查找域的此页面，请参阅在基于 DNS Windows [DNS 中查找 DNS 记录](#find-your-dns-records-in-windows-based-dns)。  
- 在 **"新建资源记录** "对话框中，确保字段精确地设置为以下值： 
    - 主机名： 
    - @Address：粘贴你刚刚从 Microsoft 复制的"指向地址"值。  
    - Pref： 
- 选择“保存更改”。
- 请删除任何已过时的 MX 记录。 如果此域有任何将电子邮件路由到其他位置的旧 MX 记录，请选中每个旧记录旁边的复选框，然后选择 **DeleteOK** > 。 
   
## <a name="add-cname-records"></a>添加 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

添加 Microsoft 所需的 CNAME 记录。 如果 Microsoft 中列出了其他 CNAME 记录，则按照此处所示的相同常规步骤添加这些记录。
  
> [!IMPORTANT]
> 如果你有适用于 Microsoft 的移动设备 (MDM) ，则必须创建另外两条 CNAME 记录。 创建流程与你用于其他四个 CNAME 记录的流程一样，但需提供下表中的值。  (如果没有 MDM，可以跳过此步骤。)  

- 在域的"DNS 管理器"页面上，转到"**ActionCNAME** >  **(CNAME) "**。
- 在 **"新建资源记录** "对话框中，确保字段精确地设置为以下值：  
    - 主机名：自动发现
    - 类型： 
    - CNAMEAddress：autodiscover.outlook.com
- 选择 **"OK**"。

添加 SIP CNAME 记录。 
- 在域的"DNS 管理器"页面上，转到\>"操作 **""CNAME (CNAME) "**。 
- 在 **"新建资源记录** "对话框中，确保字段精确地设置为以下值：  
    - 主机名：sip
    - 类型：CNAME
    - 地址：sipdir.online.lync.com
- 选择“**确定**”。

添加 Skype for Business Online 自动发现 CNAME 记录。  
- 在域的"DNS 管理器"页面上，转到\>"操作 **""CNAME (CNAME) "**。 在 **"新建资源记录** "对话框中，确保字段精确地设置为以下值：  
    - 主机名：lyncdiscover
    - 类型：CNAME
    - 地址：webdir.online.lync.com
- 选择“**确定**”。
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>为 Microsoft 的移动设备管理 (MDM) 添加两条 CNAME 记录

> [!IMPORTANT]
> 如果你有适用于 Microsoft 的移动设备 (MDM) ，则必须创建另外两条 CNAME 记录。 创建流程与你用于其他四个 CNAME 记录的流程一样，但需提供下表中的值。 > (如果没有 MDM，可以跳过此步骤。)  
  

添加 MDM Enterpriseregistration CNAME 记录。  
- 在域的"DNS 管理器"页面上，转到\>"操作 **""CNAME (CNAME) "**。 
- 在 **"新建资源记录** "对话框中，确保字段精确地设置为以下值：  
- 主机名：enterpriseregistration
- 类型：CNAME
- 地址：enterpriseregistration.windows.net
- 选择“**确定**”。 

添加 MDM Enterpriseenrollment CNAME 记录。 
-  在域的"DNS 管理器"页面上，转到\>"操作 **""CNAME (CNAME) "**。 
-  在 **"新建资源记录** "对话框中，确保字段精确地设置为以下值：  
    - 主机名：enterpriseenrollment
    - 类型：CNAME
    - 地址：enterpriseenrollment-s.manage.microsoft.com
- 选择“**确定**”。
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 相反，将所需的 Microsoft 值添加到当前记录，以便你有一  *个包含这*  两组值的 SPF 记录。 
  
为您的域添加 SPF TXT 记录以帮助防止垃圾邮件。
  
- 您可能已在此记录的"TXT"值中拥有其他字符串（例如，营销电子邮件的字符串），这样没关系。请将那些字符串留在原位并添加此字符串，并在每个字符串两侧加上双引号以将它们隔开。 
- 在域的"DNS 管理器"页面上， **转到"** \> **TXT (操作) "**。 
-  在 **"新建资源记录** "对话框中，确保字段精确地设置为以下值。 
 > [!IMPORTANT]
> 在 DNS 管理器的Windows版本中，域可能已被设置，以便创建 txt 记录时，主页名称默认为父域。 在这种情况下，添加 TXT 记录时，将主机名设置为空（没有值），而不是将其设置为 @ 或域名。 

-  主机类型：@
-  记录类型：TXT
-  地址：v=spf1 include：spf.protection.outlook.com -all 
         
-  选择“**确定**”。
   
## <a name="add-srv-records"></a>添加 SRV 记录
<a name="BKMK_add_SRV"> </a>

添加 Microsoft 所需的两条 SRV 记录。

为 Skype for Business Online Web 会议添加 SIP SRV 记录。  <br/> 
-  在域的"DNS 管理器"页上，转到" **操作** \> **""其他新记录"**。 
-   在" **资源记录类型"** 窗口中，选择" **SRV** (服务) ，然后选择" **创建记录"**。 
-   在 **"新建资源记录** "对话框中，确保字段精确地设置为以下值：  
    -  服务：_sip
    -  协议：_tls
    -  优先级： 100
    -  权重： 1
    -  端口：443
    -  目标 (主机名) ：sipdir.online.lync.com
-  选择“**确定**”。 


为 Skype for Business Online 联盟添加 SIP SRV 记录。  
-  在域的"DNS 管理器"页上，转到" **操作** \> **""其他新记录"**。  
-  在" **资源记录类型"** 窗口中，选择" **SRV** (服务) ，然后选择" **创建记录"**。 
-   在 **"新建资源记录** "对话框中，确保字段精确地设置为以下值：  
    -  服务：_sipfederationtls
    -  协议：_tcp
    -  优先级： 100
    -  权重： 1
    -  端口： 5061
    -  目标 (主机名) ：sipfed.online.lync.com
-  选择“**确定**”。 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>添加记录以验证您拥有该域（如果尚未验证）
<a name="BKMK_verify"> </a>

在添加 DNS 记录以设置Microsoft 服务之前，Microsoft 必须确认你拥有要添加的域。 为此，请按照以下步骤添加记录。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 
  

1. 从 Microsoft 收集信息。  <br/> 
2. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。 
3. On the **Domains** page， in the **Actions** column for the domain that you are verifying， select **Start setup**. 
4. 在" **将域添加到 Microsoft"页上** ，选择" **开始步骤 1"**。 
5. On the **Confirm that you own your domain** page， in the **See instructions for performing this step with** drop-down list， choose **General instructions**. 
6. 从表中，复制"目标地址或指向的地址"值。 您将在下一步骤中需要它。 建议您复制并粘贴此值，以确保所有空格保持正确。

添加 TXT 记录。 
-  在域的"DNS 管理器"页面上， **转到"** \> **TXT (操作) "**。 
-   在" **新建资源记录"** 对话框中，选择"编辑 **"**。  
-  在 **"新建资源** 记录"对话框的"自定义主机名"区域中，确保字段精确地设置为以下值。 

> [!IMPORTANT] 
> 在 DNS 管理器的Windows版本中，域可能已被设置，以便创建 txt 记录时，主页名称默认为父域。 在这种情况下，添加 TXT 记录时，将主机名设置为空（没有值），而不是将其设置为 @ 或域名。 

- 主机名：@
- 类型：TXT
- 地址：粘贴你刚刚从 Microsoft 复制的目标或指向地址值。  
- 选择 **"确定** > **"**。

在 Microsoft 中验证域。  
> [!IMPORTANT]
> 请等待大约 15 分钟，然后你刚刚创建的记录可以通过 Internet 更新。       

- 返回到 Microsoft 并按照以下步骤请求验证检查。 该检查将查找上一步中添加的 TXT 记录。 找到正确的 TXT 记录时，该域通过验证。  
1. 在管理中心，转到"设置 **域"**\>页面。<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a>
2. On the **Domains** page， in the **Action** column for the domain you are verifying， select **Start setup**. 
3. 在" **确认你拥有你的** 域"页上， **选择"完成**，现在验证"，然后在确认对话框中选择"完成 **"**。 
   
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>在本地 Active Directory 中用作 UPN 的不可路由电子邮件地址
<a name="BKMK_ADNote"> </a>

如果计划将本地 Active Directory 与 Microsoft 同步，需要确保 Active Directory 用户主体名称 (UPN) 后缀是有效的域后缀，而不是不支持的域后缀（如 @contoso.local）。 如果需要更改 UPN 后缀，请参阅如何为目录同步准备不可路由 [的域](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)。
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 

## <a name="related-content"></a>相关内容

[将域从 Micrsoft 365](../get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host.md) 转移到其他主机 (文章) \
[从Microsoft 365域管理中](../misc/pilot-microsoft-365-from-my-custom-domain.md)试用 (文章) \
[域常见问题](../setup/domains-faq.yml) （文章）