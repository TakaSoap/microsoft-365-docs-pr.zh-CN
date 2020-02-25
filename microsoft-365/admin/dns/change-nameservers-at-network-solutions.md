---
title: 更改名称服务器以使用 Network Solutions 设置 Office 365
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: '如果您希望 Office 365 管理您的 DNS 记录，请了解如何设置带网络解决方案的 Office 365 自定义域。 '
ms.openlocfilehash: c9465da507e6b4dea35f9ead50b5bc7c14a1b38f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238442"
---
# <a name="change-nameservers-to-set-up-office-365-with-network-solutions"></a>更改名称服务器以使用 Network Solutions 设置 Office 365

 **如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。
  
如果希望 Office 365 管理 Office 365 DNS 记录，请按以下说明操作。（如果愿意，可[在 Network Solutions 处管理所有 Office 365 DNS 记录](create-dns-records-at-network-solutions.md)。）
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a>在 Network Solutions 处添加 TXT 记录以验证是否拥有该域

在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
请按下列步骤操作或[观看视频（从 0:47 开始）](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
1. 若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。系统将会提示您登录。
    
    > [!IMPORTANT]
    > 在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。
  
    ![选择'管理我的域名'并登录到 Network Solutions](../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. 选择要修改的域名称旁边的复选框。
    
    ![选择域的复选框](../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. 选择 "**编辑 DNS**"。
    
    ![选择 "编辑 DNS"](../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. 选择 "**管理高级 DNS 记录**"。
    
    (You may have to scroll down.)
    
    ![选择 "管理高级 DNS 记录"](../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. 向下滚动到 "**文本（TXT 记录）** " 部分，然后选择 "**编辑 TXT 记录**"。
    
    ![选择 "编辑 TXT 记录"](../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. 在新记录的框中，键入或复制并粘贴下表中的值。
    
|**主机**|**TTL**|**文本**|
|:-----|:-----|:-----|
|@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **注意**：这是一个示例。 在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。           [如何查找此内容？](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![在新记录的框中键入或粘贴值](../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. 选择 "**继续**"。
    
    ![选择 "继续"](../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. 选择 "**保存更改**"。
    
    ![选择 "保存更改"](../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. 在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。

    
2. 在 "**域**" 页上，选择要验证的域。 
    
    
  
3. 在 "**设置**" 页上，选择 "**启动安装程序**"。
    
    
  
4. 在 "**验证域**" 页上，选择 "**验证**"。
    
    
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>更改域的名称服务器 (NS) 记录

要使用 Office 365 完成域的设置，请在域注册机构处将你的域的 NS 记录更改为指向 Office 365 主要名称服务器和次要名称服务器。这将设置 Office 365 以更新域的 DNS 记录。我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。
  
> [!CAUTION]
> 将你的域的 NS 记录更改为指向 Office 365 名称服务器时，当前与你的域相关联的所有服务都会受影响。例如，在你进行此更改之后，发送到你的域（例如 rob@ *your_domain*  .com）的所有电子邮件都将开始传送到 Office 365。
  
准备好更改 NS 记录以便 Office 365 可以设置域了吗？请按下列步骤操作或[观看视频（从 2:23 开始）](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
> [!IMPORTANT]
>  完成本节中的步骤后，应列出的*唯一*名称服务器为以下四个： **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**和**ns4.bdm.microsoftonline.com**。 以下过程将演示如何从列表中删除任何其他不需要的名称服务器，以及如何添加 *正确*  的名称服务器（如果它们尚未显示在列表中）。 
  
1. 若要开始，请使用[此链接](https://www.networksolutions.com/manage-it)转到 Network Solutions 上你的域页面。 系统将会提示您登录。
    
    > [!IMPORTANT]
    > 在选择 "**登录**" 按钮之前，先在 "**登录到：** " 下拉列表中选择 **"管理我的域名**"。 
  
    ![选择'管理我的域名'并登录到 Network Solutions](../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. 选择要修改的域名称旁边的复选框。
    
    ![选择域的复选框](../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. 选择 "**编辑 DNS**"。
    
    ![选择 "编辑 DNS"](../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. 选择 "**移动 DNS**"。
    
    ![NetworkSolutionsBP-委派-1-1](../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. 根据现在显示的页面上是否已列出名称服务器，继续执行以下两个过程之一：
    
  - 如果 **未** 列出名称服务器，则 [如果未列出名称服务器](#if-there-are-no-nameservers-already-listed)。
    
  - 如果 **已** 列出名称服务器，则 [如果已列出名称服务器](#if-there-are-nameservers-already-listed)。
    
### <a name="if-there-are-no-nameservers-already-listed"></a>如果未列出名称服务器

1. 在 "**域**" 页上的 "**指定域名服务器**" 部分，选择 "**添加更多名称服务器**"。
    
    ![NetworkSolutionsBP-委派-1-2-1](../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. 在" **域名**"页面中，键入或复制并粘贴下表中的名称服务器值。 
    
|||
|:-----|:-----|
|**名称服务器 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**名称服务器 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**名称服务器 2** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**名称服务器 2** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    
![NetworkSolutionsBP-委派-1-2-2](../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. 选择 "**移动 DNS**"。
    
    ![NetworkSolutionsBP-委派-1-2-3](../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. 选择 "**保存更改**"。
    
    ![NetworkSolutionsBP-委派-1-2-4](../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> 你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。 
  
### <a name="if-there-are-nameservers-already-listed"></a>如果已列出名称服务器

> [!CAUTION]
> *仅*  当具有这四个  *正确*  的名称服务器以外的现有名称服务器时，执行以下步骤。（即，  *仅*  删除名称  *不是* **ns1.bdm.microsoftonline.com** 、 **ns2.bdm.microsoftonline.com** 、 **ns3.bdm.microsoftonline.com** 或 **ns4.bdm.microsoftonline.com** 的任何当前名称服务器。）
  
1. 如果列有任何其他名称服务器，选择服务器，然后按键盘上的 **Delete** 键，将其删除。
    
    ![NetworkSolutions-委派-1-5](../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. 选择 "**添加更多名称服务器**"。
    
    ![NetworkSolutionsBP-委派-1-2-1](../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. 在" **域名**"页面中，键入或复制并粘贴下表中的名称服务器值。
 
    
|||
|:-----|:-----|
|**名称服务器 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**名称服务器 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**名称服务器 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**名称服务器 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    
![NetworkSolutionsBP-委派-1-2-2](../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. 选择 "**移动 DNS**"。
    
    ![NetworkSolutionsBP-委派-1-2-3](../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. 选择 "**保存更改"。**
    
    ![NetworkSolutionsBP-委派-1-2-4](../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> 你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。