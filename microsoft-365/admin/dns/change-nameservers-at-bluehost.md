---
title: 更改名称服务器以使用 Bluehost 设置 Office 365
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: '了解如何设置 Office 365 以管理 Bluehost 上的 DNS 记录。 '
ms.openlocfilehash: dbd06791df2e7f8e6ca085b82dc880e9626c065c
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212337"
---
# <a name="change-nameservers-to-set-up-office-365-with-bluehost"></a>更改名称服务器以使用 Bluehost 设置 Office 365

 **如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。 
  
如果希望 Office 365 管理 Office 365 DNS 记录，请按以下说明操作。（如果愿意，可[在 Bluehost 处管理所有 Office 365 DNS 记录](create-dns-records-at-bluehost.md)。）
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。 系统将会提示您先登录。
    
2. 在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。 
    
    （您可能需要向下滚动。） 
    
3. 在 " **domain_name** " 区域的 " **DNS 区域编辑器**" 行中，选择 "**管理 DNS 记录**"。
    
4. On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Host Record** <br/> |**TTL** <br/> |**类型** <br/> |**TXT Value** <br/> |
|@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX* <br/> **注意：** 此为示例。 在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. 选择 "**添加记录**"。
    
6. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。
  
Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。
  
1. 在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。

    
2. 在“**域**”页面上，选择要验证的域。 
    
3. 在“**设置**”页面上，选择“**开始设置**”。
    
4. 在“**验证域**”页面上，选择“**验证**”。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在将域或 DNS 记录添加到 Office 365 后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>更改域的名称服务器 (NS) 记录

要使用 Office 365 完成域的设置，请在域注册机构处将你的域的 NS 记录更改为指向 Office 365 主要名称服务器和次要名称服务器。这将设置 Office 365 以更新域的 DNS 记录。我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。
  
> [!CAUTION]
> 将你的域的 NS 记录更改为指向 Office 365 名称服务器时，当前与你的域相关联的所有服务都会受影响。例如，在你进行此更改之后，发送到你的域（例如 rob@ *your_domain*  .com）的所有电子邮件都将开始传送到 Office 365。 
  
> [!IMPORTANT]
>  下面的过程将向您介绍如何从列表中删除任何其他不需要的名称服务器，以及如何添加正确的名称服务器（如果尚未列出）。 > 完成本节中的步骤后，应列出的唯一名称服务器为以下四个： > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. 要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。 系统将会提示您先登录。
    
2. 在 "**域**" 页上的 " **domain_name** " 区域中，选中您的域的复选框，然后选择 "**名称服务器**"。
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. 在 " **domain_name** " 区域中，选择 "**使用自定义名称服务器**"。
    
    ![Bluehost-BP-Redelegate-1-2](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. 根据现在显示的页面上是否已列出名称服务器，继续执行以下两个过程之一：
    
  - 如果 **未** 列出名称服务器，则 [如果未列出名称服务器](#if-there-are-no-nameservers-already-listed)。
    
  - 如果 **已** 列出名称服务器，则 [如果已列出名称服务器](#if-there-are-nameservers-already-listed)。
    
### <a name="if-there-are-no-nameservers-already-listed"></a>如果未列出名称服务器

1. 在" **使用自定义名称服务器**"部分中，键入或复制并粘贴下表中的值。 
    
|||
|:-----|:-----|
|**第一个空行** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**第二个空行** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-委派-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. 选择 "**添加行**"。
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. 在" **使用自定义名称服务器**"部分中，键入或将下表第一行中的值复制并粘贴到新的空行中。 
    
|||
|:-----|:-----|
|**第三个空行** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**第四个空行** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
4. 若要添加第四个 Nameserver 记录，请再次选择 "**添加行**"，并使用上表中最后一行的值创建记录。 
    
5. 选择 "**保存 nameserver 设置**"。
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> 你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。 
  
### <a name="if-there-are-nameservers-already-listed"></a>如果已列出名称服务器

> [!CAUTION]
> Follow these steps only if you have existing nameservers other than the four correct nameservers. （也就是说，仅删除任何*未*命名为**ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或**ns4.bdm.microsoftonline.com**的当前名称服务器。） 
  
1. 如果列有任何其他名称服务器，删除每个服务器，具体方法是将其选中，然后按键盘上的 **Delete** 键。 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. 在" **使用自定义名称服务器**"部分中，键入或复制并粘贴下表中的值。 
    
|||
|:-----|:-----|
|**第一个空行** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**第二个空行** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-委派-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. 选择 "**添加行**"。
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. 在" **使用自定义名称服务器**"部分中，键入或将下表第一行中的值复制并粘贴到新的空行中。 
    
|||
|:-----|:-----|
|**第三个空行** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**第四个空行** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-委派-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. 若要添加第四个 Nameserver 记录，请再次选择 "**添加行**"，并使用上表中最后一行的值创建记录。 
    
6. 选择 "**保存 nameserver 设置**"。
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> 你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。 
  
