---
title: 在 OVH 上为 Office 365 创建 DNS 记录
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: 了解如何在 OVH for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 3ba4e61c875f74a0a6cf76c8b7cd82ea88e0221b
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211106"
---
# <a name="create-dns-records-at-ovh-for-office-365"></a>在 OVH 上为 Office 365 创建 DNS 记录

如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)。 
  
如果 OVH 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。
  
下面是要添加的主要记录。 
  
- [在 OVH 上为 Office 365 创建 DNS 记录](#create-dns-records-at-ovh-for-office-365)
    
- [添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [添加 Office 365 所需的 CNAME 记录](#add-the-cname-records-that-are-required-for-office-365)
    
- [为 SPF 添加 TXT 记录以帮助防止垃圾邮件](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [添加 Office 365 所需的两条 SRV 记录](#add-the-two-srv-records-that-are-required-for-office-365)
    
在 OVH 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。
  
若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="bkmk_txt"> </a>

在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 若要开始，请使用[此链接](https://www.ovh.com/manager/)转到 OVH 中的 "域" 页面。 You'll be prompted to log in.
    
    ![OVH 登录名](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. 在 "**域**" 下，选择要编辑的域的名称。
    
    ![OVH 选择域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. 选择 " **DNS 区域**"。
    
    ![OVH 选择 DNS 区域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. 选择 "**添加条目**"。
    
    ![OVH 添加条目](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. 选择 " **TXT** "
    
    ![OVH 选择 TXT 条目](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. 在新记录的框中，键入或复制并粘贴下表中的值。 若要分配 TTL 值，请从下拉列表中选择 "**个性化**"，然后在文本框中键入值。 
    
    |**记录类型**|**子域**|**TTL**|**值**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |（保留为空白）  <br/> |3600（秒）  <br/> |MS = msxxxxxxxx  <br/> **注意：** 此为示例。 在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。           [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
   
7. 选择 "**确认**"。 
    
    ![OVH 确认 TXT 以进行验证](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。
  
Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。
  
1. 在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。
    
2. 在“**域**”页面上，选择要验证的域。 
    
    
  
3. 在“**设置**”页面上，选择“**开始设置**”。
    
    
  
4. 在“**验证域**”页面上，选择“**验证**”。
    
    
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365
<a name="bkmk_mx"> </a>

1. 若要开始，请使用[此链接](https://www.ovh.com/manager/)转到 OVH 中的 "域" 页面。 You'll be prompted to log in.
    
    ![OVH 登录名](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. 在 "**域**" 下，选择要编辑的域的名称。
    
    ![OVH 选择域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. 选择 " **DNS 区域**"。
    
    ![OVH 选择 DNS 区域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. 选择 "**添加条目**"。
    
    ![OVH 添加条目](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. 选择 " **MX**"。
    
    ![OVH MX 记录类型](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. 在新记录的框中，键入或复制并粘贴下表中的值。 若要分配 TTL 值，请从下拉列表中选择 "**个性化**"，然后在文本框中键入值。 
    
    > [!NOTE]
    > 默认情况下，OVH 对目标使用相对表示法，这会将域名添加到目标记录的末尾。 若要改为使用绝对表示法，请在目标记录中添加一个点，如下表所示。 
  
    |**记录类型**|**子域**|**TTL**|**Priority**|**目标**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |（保留为空白）  <br/> |3600（秒）  <br/> |10   <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |\<\>mail.protection.outlook.com。  <br/> **注意：** 从 Office 365 帐户中获取你* \<的域密钥\> * 。  [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![邮件的 OVH MX 记录](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. 选择“**下一步**”。
    
    ![OVH MX 记录选择 "下一步"](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. 选择 "**确认**"。
    
    ![OVH MX 记录选择 "确认"](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. 如果有任何其他 MX 记录，请在 " **DNS 区域**" 页上的列表中将它们全部删除。 选择每个记录，然后在 "**操作**" 列中选择 "垃圾桶**删除**" 图标。 
    
    ![OVH 删除 MX 记录](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. 选择 "**确认**"。
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>添加 Office 365 所需的 CNAME 记录
<a name="bkmk_cname"> </a>

1. 若要开始，请使用[此链接](https://www.ovh.com/manager/)转到 OVH 中的 "域" 页面。 You'll be prompted to log in.
    
    ![OVH 登录名](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. 在 "**域**" 下，选择要编辑的域的名称。
    
    ![OVH 选择域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. 选择 " **DNS 区域**"。
    
    ![OVH 选择 DNS 区域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. 选择 "**添加条目**"。
    
    ![OVH 添加条目](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. 选择 " **CNAME**"。
    
    ![OVH 添加 CNAME 记录类型](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. 创建第一个 CNAME 记录。
    
    在新记录的框中，键入或复制并粘贴下表中第一行的值。 若要分配 TTL 值，请从下拉列表中选择 "**个性化**"，然后在文本框中键入值。 
    
    |**记录类型**|**子域**|**目标**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com。  <br/> |3600秒  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com。  <br/> |3600秒  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com。  <br/> |3600秒  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net。  <br/> |3600秒  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> |3600秒  <br/> |
   
    ![OVH CNAME 记录](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. 选择“**下一步**”。
    
    ![OVH 添加 CNAME 值并选择 "下一步"](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. 选择 "**确认**"。
    
9. 重复前面的步骤以创建其他五个 CNAME 记录。
    
    对于每个记录，键入或复制并将上表中下一行的值粘贴到该记录的框中。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 If you already have an SPF record for your domain, don't create a new one for Office 365. 可以将所需的 Office 365 添加到当前记录，这样就拥有包含两组值的*单个*SPF 记录。 
  
1. 若要开始，请使用[此链接](https://www.ovh.com/manager/)转到 OVH 中的 "域" 页面。 You'll be prompted to log in.
    
    ![OVH 登录名](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. 在 "**域**" 下，选择要编辑的域的名称。
    
    ![OVH 选择域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. 选择 " **DNS 区域**"。
    
    ![OVH 选择 DNS 区域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. 选择 "**添加条目**"。
    
    ![OVH 添加条目](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. 选择 " **TXT**"。
    
6. In the boxes for the new record, type or copy and paste the following values.
    
    |**记录类型**|**子域**|**TTL**|**TXT 值**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |（保留为空白）  <br/> |3600（秒）  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。           |
   
    ![OVH 为 SPF 添加 TXT 记录](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. 选择“**下一步**”。
    
    ![OVH 为 SPF 添加 TXT 记录，然后选择 "下一步"](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. 选择 "**确认**"。
    
    ![OVH 为 SPF 和确认添加 TXT 记录](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>添加 Office 365 所需的两条 SRV 记录
<a name="bkmk_srv"> </a>

1. 若要开始，请使用[此链接](https://www.ovh.com/manager/)转到 OVH 中的 "域" 页面。 You'll be prompted to log in.
    
    ![OVH 登录名](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. 在 "**域**" 下，选择要编辑的域的名称。
    
    ![OVH 选择域](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. 选择 " **DNS 区域**"。
    
    ![OVH 选择 DNS 区域](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. 选择 "**添加条目**"。
    
    ![OVH 添加条目](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. 选择 " **SRV**"。
    
    ![OVH 选择 SRV 记录类型](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. 创建第一个 SRV 记录。
    
    在新记录的框中，键入或复制并粘贴下表中第一行的值。 若要分配 TTL 值，请从下拉列表中选择 "**个性化**"，然后在文本框中键入值。 
    
    |**记录类型**|**子域**|**优先级**|**权重**|**端口**|**TTL**|**目标**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV（服务）  <br/> |_sip _tls  <br/> |100  <br/> |1  <br/> |443  <br/> |3600（秒）  <br/> |sipdir.online.lync.com。  <br/> |
    |SRV（服务）  <br/> |_sipfederationtls _tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |3600（秒）  <br/> |sipfed.online.lync.com。  <br/> |
       
    ![OVH SRV 记录](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. 选择“**下一步**”。
    
    ![OVH SRV 记录选择 "下一步"](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. 选择 "**确认**"。
    
9. 重复前面的步骤以创建其他 SRV 记录。 将上表中第二行的值键入或复制并粘贴到第二条记录的框中。
    
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
