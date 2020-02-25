---
title: 更改名称服务器以将 Office 365 设置为 1&1 IONOS
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: 了解如何设置由世纪互联运营的 Office 365 以管理 DNS 记录，当 1&1 Internet 是 DNS 托管提供商时。
ms.openlocfilehash: 907e4fe097634d28ad44e4d44ba8c6ff2da9164d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238522"
---
# <a name="change-nameservers-to-set-up-office-365-with-11-ionos"></a>更改名称服务器以将 Office 365 设置为 1&1 IONOS

 **如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。 
  
如果希望 Office 365 管理 Office 365 DNS 记录，请按以下说明操作。 （如果愿意，您可以[在 1&1 IONOS 管理所有的 Office 365 DNS 记录](create-dns-records-at-1-1-internet.md)。 
  

    
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证


在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
请按下列步骤操作或[观看视频（从 0:42 开始）](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
1. 若要开始，请转到域页面 1&1 IONOS 通过[此链接](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)。 You'll be prompted to log in. 
    
2. 在 **"我的域**" 下，选择 "**管理域**"。
    
3. 在 "**域中心**" 页上，找到要更新的域;然后，选择该域的 **"面板"** （ **v**）控件。
    
4. 在 "**域设置**" 区域中，选择 "**编辑 DNS 设置**"。
    
5. 在 " **TXT 和 SRV 记录**" 部分中，选择 "**添加记录**"。
    
    (You may have to scroll down.) 
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
||||
|:-----|:-----|:-----|
|**类型** <br/> |**前缀** <br/> |**名称值** <br/> |
|TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX* <br/> **注意**：这是一个示例。 在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。 [如何查找此内容？](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. 选择 "**保存**"，然后重新**保存**。 
    
8. 在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。
    
9. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
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
  
准备好更改 NS 记录以便 Office 365 可以设置域了吗？请按下列步骤操作或[观看视频（从 2:47 开始）](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
> [!IMPORTANT]
>  下面的过程将向您介绍如何从列表中删除任何其他不需要的名称服务器，以及如何添加正确的名称服务器（如果尚未列出）。 > 完成本节中的步骤后，应列出的唯一名称服务器为以下四个： > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. 若要开始，请使用[此链接](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)转到域页面 1&1 IONOS。 You'll be prompted to log in. 
    
2. 在 **"我的域**" 下，选择 "**管理域**"。
    
3. 在 "**域中心**" 页上，找到要更新的域，然后选择该域的 **"面板"** （ **v**）控制。
    
4. 在 "**域设置**" 区域中，选择 "**编辑 DNS 设置**"。
    
5. 在" **名称服务器设置**"部分中，选择" **其他名称服务器**"。
    
    （您可能需要向下滚动。）
    
6. 根据现在显示的页面上是否已列出名称服务器，继续执行以下两个过程之一：
    
  - 如果 **未** 列出名称服务器，则 [如果未列出名称服务器](#if-there-are-no-nameservers-already-listed)。
    
  - 如果 **已** 列出名称服务器，则 [如果已列出名称服务器](#if-there-are-nameservers-already-listed)。
    
### <a name="if-there-are-no-nameservers-already-listed"></a>如果未列出名称服务器

1. 在" **名称服务器 1**"框内，键入或复制并粘贴下表中的值。 
    
|||
|:-----|:-----|
|**名称服务器 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
   
   ![在 "名称服务器 1" 框中输入值](../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. 在" **其他名称服务器**"下拉列表中，选择" **我的辅助名称服务器**"。
    
    ![Choosing My secondary name servers in the list](../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. 在" **名称服务器 2、3 和 4**"框内，键入或复制并粘贴下表中的值。 
    
|||
|:-----|:-----|
|**名称服务器 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**名称服务器 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**名称服务器 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![Entering name server values](../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. 选择“**保存**”。
    
    ![在 "名称服务器设置" 页上选择 "保存"](../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. 在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。
    
    ![在 "编辑 DNS 设置" 对话框中选择 "保存"](../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> 你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。 
  
### <a name="if-there-are-nameservers-already-listed"></a>如果已列出名称服务器

> [!CAUTION]
> *仅*  当具有这四个  *正确*  的名称服务器以外的现有名称服务器时，执行以下步骤。（即，  *仅*  删除名称  *不是* **ns1.bdm.microsoftonline.com** 、 **ns2.bdm.microsoftonline.com** 、 **ns3.bdm.microsoftonline.com** 或 **ns4.bdm.microsoftonline.com** 的任何当前名称服务器。） 
  
1. 如果" **名称服务器**"框中已列有名称服务器，通过选择每一项，然后按键盘上的 **Delete** 键，将其删除。 
    
    ![Deleting name servers](../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. 在" **名称服务器 1、2、3 和 4**"框内，键入或复制并粘贴下表中的值。 
    
|||
|:-----|:-----|
|**名称服务器 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**名称服务器 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**名称服务器 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**名称服务器 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![输入名称服务器值](../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. 选择“**保存**”。
    
    ![在 "名称服务器设置" 页上选择 "保存"](../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. 在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。
    
    ![在 "编辑 DNS 设置" 对话框中选择 "保存"](../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> 你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。 
  


