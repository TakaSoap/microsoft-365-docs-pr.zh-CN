---
title: 更改名称服务器以使用 Bluehost 设置 Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: '了解如何设置 Office 365 以管理 Bluehost 上的 DNS 记录。 '
ms.openlocfilehash: 27d73071a08477b0adc372d8a88db2c805fecacf
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237995"
---
# <a name="change-nameservers-to-set-up-office-365-with-bluehost"></a>更改名称服务器以使用 Bluehost 设置 Office 365

 **如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。 
  
如果希望 Office 365 管理 Office 365 DNS 记录，请按以下说明操作。（如果愿意，可[在 Bluehost 处管理所有 Office 365 DNS 记录](create-dns-records-at-bluehost.md)。）
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。 You'll be prompted to log in first.
    
2. 在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。 
    
    （您可能需要向下滚动。） 
    
3. 在 " **domain_name** " 区域的 " **DNS 区域编辑器**" 行中，选择 "**管理 DNS 记录**"。
    
4. On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Host Record** <br/> |**TTL** <br/> |**类型** <br/> |**TXT Value** <br/> |
|@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX* <br/> **注意：** 这是一个示例。 在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。 [如何查找此内容？](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. 选择 "**添加记录**"。
    
6. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。

    
2. 在 "**域**" 页上，选择要验证的域。 
    
3. 在 "**设置**" 页上，选择 "**启动安装程序**"。
    
4. 在 "**验证域**" 页上，选择 "**验证**"。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[在 Office 365 中添加域或 DNS 记录后，查找并修复问题](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>更改域的名称服务器 (NS) 记录

要使用 Office 365 完成域的设置，请在域注册机构处将你的域的 NS 记录更改为指向 Office 365 主要名称服务器和次要名称服务器。这将设置 Office 365 以更新域的 DNS 记录。我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。
  
> [!CAUTION]
> 将你的域的 NS 记录更改为指向 Office 365 名称服务器时，当前与你的域相关联的所有服务都会受影响。例如，在你进行此更改之后，发送到你的域（例如 rob@ *your_domain*  .com）的所有电子邮件都将开始传送到 Office 365。 
  
> [!IMPORTANT]
>  下面的过程将向您介绍如何从列表中删除任何其他不需要的名称服务器，以及如何添加正确的名称服务器（如果尚未列出）。 > 完成本节中的步骤后，应列出的唯一名称服务器为以下四个： > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. 要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。 You'll be prompted to log in first.
    
2. 在 "**域**" 页上的 " **domain_name** " 区域中，选中您的域的复选框，然后选择 "**名称服务器**"。
    
    ![Bluehost-BP-Redelegate-1-1](../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. 在 " **domain_name** " 区域中，选择 "**使用自定义名称服务器**"。
    
    ![Bluehost-BP-Redelegate-1-2](../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. 根据现在显示的页面上是否已列出名称服务器，继续执行以下两个过程之一：
    
  - 如果 **未** 列出名称服务器，则 [如果未列出名称服务器](#if-there-are-no-nameservers-already-listed)。
    
  - 如果 **已** 列出名称服务器，则 [如果已列出名称服务器](#if-there-are-nameservers-already-listed)。
    
### <a name="if-there-are-no-nameservers-already-listed"></a>如果未列出名称服务器

1. 在" **使用自定义名称服务器**"部分中，键入或复制并粘贴下表中的值。 
    
|||
|:-----|:-----|
|**第一个空行** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**第二个空行** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-委派-1-3-1](../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. 选择 "**添加行**"。
    
    ![Bluehost-BP-Redelegate-1-3-2](../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. 在" **使用自定义名称服务器**"部分中，键入或将下表第一行中的值复制并粘贴到新的空行中。 
    
|||
|:-----|:-----|
|**第三个空行** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**第四个空行** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![Bluehost-BP-Redelegate-1-3-3](../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
4. 若要添加第四个 Nameserver 记录，请再次选择 "**添加行**"，并使用上表中最后一行的值创建记录。 
    
5. 选择 "**保存 nameserver 设置**"。
    
    ![Bluehost-BP-Redelegate-1-4](../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> 你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。 
  
### <a name="if-there-are-nameservers-already-listed"></a>如果已列出名称服务器

> [!CAUTION]
> Follow these steps only if you have existing nameservers other than the four correct nameservers. （也就是说，仅删除任何*未*命名为**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**的当前名称服务器。） 
  
1. 如果列有任何其他名称服务器，删除每个服务器，具体方法是将其选中，然后按键盘上的 **Delete** 键。 
    
    ![Bluehost-BP-Redelegate-1-5](../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. 在" **使用自定义名称服务器**"部分中，键入或复制并粘贴下表中的值。 
    
|||
|:-----|:-----|
|**第一个空行** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**第二个空行** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-委派-1-3](../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. 选择 "**添加行**"。
    
    ![Bluehost-BP-Redelegate-1-3-2](../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. 在" **使用自定义名称服务器**"部分中，键入或将下表第一行中的值复制并粘贴到新的空行中。 
    
|||
|:-----|:-----|
|**第三个空行** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**第四个空行** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-委派-1-3-3](../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. 若要添加第四个 Nameserver 记录，请再次选择 "**添加行**"，并使用上表中最后一行的值创建记录。 
    
6. 选择 "**保存 nameserver 设置**"。
    
    ![Bluehost-BP-Redelegate-1-4](../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> 你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。 
  
