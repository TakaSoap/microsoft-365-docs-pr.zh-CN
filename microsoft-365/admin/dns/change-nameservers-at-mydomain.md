---
title: 更改名称服务器以使用 MyDomain 设置 Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: 了解如何设置 Microsoft 以在 MyDomain 中管理自定义域的 DNS 记录。
ms.openlocfilehash: fbfa3c495f54a9890be6d9c9e31a7878b21f12fe
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658412"
---
# <a name="change-nameservers-to-set-up-microsoft-with-mydomain"></a>更改名称服务器以使用 MyDomain 设置 Microsoft

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。
  
如果希望 Microsoft 管理 DNS 记录，请按照以下说明操作。  (，可以在[MyDomain .) ](create-dns-records-at-mydomain.md)
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 若要开始，请使用[此链接](https://www.mydomain.com/controlpanel)转到你在 MyDomain 上的域页面。系统将会提示你先登录。
    
2. 在“**我的收藏夹**”部分，选择则“**域中心**”。
    
3. 在“**域**”下，选择要编辑的域名。
    
4. 在“**概述**”行，选择“**DNS**”。
    
5. 在“**修改**”下拉列表中，选择“**TXT/SPF 记录**”。
    
6. 在" **内容**"下方新记录对应的框中，键入或复制并粘贴下表中的值。
    
||
|:-----|
|**内容** <br/> |
|MS=ms *XXXXXXXX*  <br/> **注意**：这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
   
7. 选择“**添加**”。
    
8. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
在域注册机构网站添加了记录后，你将返回到 Microsoft 365 并请求 Microsoft 365 查找记录。
  
Microsof 找到正确的 TXT 记录表明域已通过验证。
  
1. 在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

    
2. 在“**域**”页面上，选择要验证的域。 
    
3. 在“**设置**”页面上，选择“**开始设置**”。
    
4. 在“**验证域**”页面上，选择“**验证**”。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>更改域的名称服务器 (NS) 记录

若要使用 Microsoft 完成域设置，请更改域注册机构中域的 NS 记录，以指向 Microsoft 主名称服务器和辅助名称服务器。 这会将 Microsoft 设置为更新域的 DNS 记录。 我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。
  
> [!CAUTION]
> 当您将域的 NS 记录更改为指向 Microsoft 名称服务器时，当前与域关联的所有服务都受到影响。 例如，发送到域的所有电子邮件 (如 *rob@your_domain。* com) 将在你进行此更改后开始进入 Microsoft。 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. <br/> When you have completed the steps in this section, the only nameservers that should be listed are these four:
  
1. 若要开始，请使用[此链接](https://www.mydomain.com/controlpanel)转到你在 MyDomain 上的域页面。系统将会提示你先登录。
    
2. 在“**我的收藏夹**”部分，选择则“**域中心**”。
    
3. 在“**域**”下，选择要编辑的域名。
    
4. 在 **"概述** "行中，选择 **名称服务器**。
    
    ![MyDomain-BP-Redelegate-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. 在" **更新名称服务器**"部分中，选择" **使用不同的名称服务器**"。
    
    ![MyDomain-BP-Redelegate-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. 根据页面上是否已列出现在显示的名称服务器，继续执行以下两个过程之一。
    
### <a name="if-the-correct-nameservers-are-already-listed"></a>如果已列出正确的名称服务器

- 如果已列出正确的名称服务器，可跳过此步骤。
    
    ![MyDomain-BP-Redelegate-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a>如果未列出正确的名称服务器

> [!CAUTION]
> Follow these steps only if you have existing nameservers other than the four correct nameservers.  (，即仅删除任何未命名为 **ns1.bdm.microsoftonline.com、ns2.bdm.microsoftonline.com、ns3.bdm.microsoftonline.com** 或 **ns4.bdm.microsoftonline.com**.)   
  
1. 在" **名称服务器:**"字段中选择每个条目，然后按键盘上的 **Delete** 键，删除现有名称服务器。 
    
    ![MyDomain-BP-Redelegate-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. Select **Add More** twice to add two new Nameserver rows. 
    
    ![MyDomain-BP-Redelegate-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. 在记录的框中，键入或复制并粘贴下表中的名称服务器值。
    
|||
|:-----|:-----|
|**名称服务器 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**名称服务器 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**名称服务器 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**名称服务器 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![MyDomain-BP-Redelegate-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. 选择“**保存**”。
    
    ![MyDomain-BP-Redelegate-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> 你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。 然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。 
