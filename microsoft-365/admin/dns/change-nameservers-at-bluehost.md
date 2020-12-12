---
title: 更改名称服务器以使用 Bluehost 设置 Microsoft
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: '了解如何设置 Microsoft 以在 Bluehost 管理 DNS 记录。 '
ms.openlocfilehash: 78b138a501054a573c2b36cc486dda833be7ae35
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658004"
---
# <a name="change-nameservers-to-set-up-microsoft-with-bluehost"></a>更改名称服务器以使用 Bluehost 设置 Microsoft

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。 
  
如果希望 Microsoft 管理 DNS 记录，请按照以下说明操作。  (，可以在 [Bluehost](create-dns-records-at-bluehost.md).) 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。 系统将会提示您先登录。
    
2. 在" **域**"页面上的" **域**"区域中，找到你要更改的域所在的行，然后选中该域对应的复选框。 
    
    （您可能需要向下滚动。） 
    
3. In the **domain_name** area， on the **DNS Zone Editor row，** select Manage DNS **records.**
    
4. On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    （从下拉列表中选择“**类型**”值。） 
    
|||||
|:-----|:-----|:-----|:-----|
|**Host Record** <br/> |**TTL** <br/> |**类型** <br/> |**TXT Value** <br/> |
|@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX* <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. 选择 **"添加记录"。**
    
6. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
现在，你已在你的域注册机构网站添加了记录，你将返回到 Microsoft 并请求搜索该记录。
  
Microsof 找到正确的 TXT 记录表明域已通过验证。
  
1. 在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

    
2. 在“**域**”页面上，选择要验证的域。 
    
3. 在“**设置**”页面上，选择“**开始设置**”。
    
4. 在“**验证域**”页面上，选择“**验证**”。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>更改域的名称服务器 (NS) 记录

若要使用 Microsoft 完成域设置，请更改域注册机构中域的 NS 记录，以指向主名称服务器和辅助名称服务器。 这会将 Microsoft 设置为更新域的 DNS 记录。 我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。
  
> [!CAUTION]
> 当您将域的 NS 记录更改为指向 Microsoft 名称服务器时，当前与域关联的所有服务都受到影响。 例如，发送到域邮箱的所有电子邮件 (如 rob@ *your_domain*  .com) 将在你进行此更改后开始发送给 Microsoft。 
  
> [!IMPORTANT]
>  以下过程将向您展示如何从列表中删除任何其他不需要的名称服务器，以及如何在名称服务器尚未列出时添加正确的名称服务器。 >完成本节中的步骤后，应列出的唯一名称服务器是以下四个：> ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. 要开始，请使用[此链接](https://my.bluehost.com/cgi/dm)转到您在 Bluehost 上的域页面。 系统将会提示您先登录。
    
2. 在 **域** 页面上的 **domain_name区域中，** 选中域的复选框，然后选择 **名称服务器**。
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. 在 **domain_name，** 选择 **"使用自定义名称服务器"。**
    
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
   
   ![Bluehost-BP-Redelegate-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. 选择 **"添加行"。**
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. 在" **使用自定义名称服务器**"部分中，键入或将下表第一行中的值复制并粘贴到新的空行中。 
    
|||
|:-----|:-----|
|**第三个空行** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**第四个空行** <br/> |ns4.bdm.microsoftonline.com  <br/> |
  
4. 若要添加第四个名称机记录，请再次选择"添加行"，然后使用上表中最后一行的值创建记录。 
    
5. 选择 **保存名称机设置**。
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> 你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。 然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。 
  
### <a name="if-there-are-nameservers-already-listed"></a>如果已列出名称服务器

> [!CAUTION]
> Follow these steps only if you have existing nameservers other than the four correct nameservers.  (，即仅删除任何未命名为 **ns1.bdm.microsoftonline.com、ns2.bdm.microsoftonline.com、ns3.bdm.microsoftonline.com** 或 **ns4.bdm.microsoftonline.com**.)   
  
1. 如果列有任何其他名称服务器，删除每个服务器，具体方法是将其选中，然后按键盘上的 **Delete** 键。 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. 在" **使用自定义名称服务器**"部分中，键入或复制并粘贴下表中的值。 
    
|||
|:-----|:-----|
|**第一个空行** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**第二个空行** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. 选择 **"添加行"。**
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. 在" **使用自定义名称服务器**"部分中，键入或将下表第一行中的值复制并粘贴到新的空行中。 
    
|||
|:-----|:-----|
|**第三个空行** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**第四个空行** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. 若要添加第四个名称机记录，请再次选择"添加行"，然后使用上表中最后一行的值创建记录。 
    
6. 选择 **保存名称机设置**。
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> 你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。 然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。 
  
