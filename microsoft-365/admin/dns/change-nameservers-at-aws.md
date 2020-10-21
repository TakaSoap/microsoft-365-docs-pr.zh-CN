---
title: '更改名称服务器以使用 Amazon Web 服务 (AWS 设置 Microsoft) '
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: '了解如何将 Microsoft 设置为管理 Amazon Web 服务 (AWS) 中的 DNS 记录。 '
ms.openlocfilehash: 9f5bfd54020dfb793bbaad9aa8e081e87abc5ce8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646483"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a>更改名称服务器以使用 Amazon Web 服务 (AWS 设置 Microsoft) 

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
如果希望 Microsoft 为你管理 DNS 记录，请按照以下说明操作。  (如果你愿意，可以 [在 AWS 管理所有 MICROSOFT DNS 记录](create-dns-records-at-aws.md)。 ) 
  
    
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。 系统将会提示您先登录。
    
2. 在 " **资源** " 页上，选择 " **托管区域**"。
    
3. 在 " **托管区域** " 页上的 " **域名** " 列中，选择要编辑的域的名称。 
    
4. 选择 " **创建记录集**"。
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**名称** <br/> |**类型** <br/> |**别名** <br/> |**TTL（秒）** <br/> |**值** <br/> |**路由策略** <br/> |
| (将此字段留空)   <br/> |TXT - Text  <br/> |否  <br/> |300  <br/> |MS=ms *XXXXXXXX* <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)  <br/>  |简单 <br/> |
   
6. 选择“**创建**”。
    
7. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
现在您已在域注册机构的网站上添加了记录，您将返回到 Microsoft 并请求搜索该记录。
  
Microsof 找到正确的 TXT 记录表明域已通过验证。
  
1. 在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

    
2. 在“**域**”页面上，选择要验证的域。 
    
3. 在“**设置**”页面上，选择“**开始设置**”。
    
4. 在“**验证域**”页面上，选择“**验证**”。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>更改域的名称服务器 (NS) 记录

若要使用 Microsoft 完成域的设置，请在域注册机构更改您的域的 NS 记录以指向 Microsoft 主名称服务器和辅助名称服务器。 这将设置 Microsoft 为您更新域的 DNS 记录。 我们将添加所有记录，以便电子邮件、Skype for Business Online 和你的公共网站全部设置为使用你的域。
  
> [!CAUTION]
> 当您将您的域的 NS 记录更改为指向 Microsoft 名称服务器时，当前与您的域相关联的所有服务都将受到影响。 例如，在进行此更改后，发送到您的域的所有电子邮件 (如 rob@ *your_domain*  .com) 将启动到 Microsoft。 
  
> [!IMPORTANT]
>  下面的过程将向您介绍如何从列表中删除任何其他不需要的名称服务器，以及如何添加正确的名称服务器（如果尚未列出）。 > 完成本节中的步骤后，应列出的唯一名称服务器为以下四个： > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. 要开始，请使用[此链接](https://console.aws.amazon.com/route53/home)转到你在 AWS 上的域页面。 系统将会提示您先登录。
    
2. 在 " **资源** " 页上，选择 " **托管区域**"。
    
3. 在 " **托管区域** " 页上的 " **域名** " 列中，选择要编辑的域的名称。 
    
4. 选择" **名称服务器**"记录集。 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. 在" **值**"框中的" **NS - 名称服务器**"记录集中，通过将它们全部选中并按键盘上的 **Delete** 键来删除所有名称服务器。 
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers.  (也就是说，仅删除任何  *未*  命名的 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或 **ns4.bdm.microsoftonline.com**的当前名称服务器。 )  
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. 在 **TTL (秒) ：** "区域中，选择" **1H** (1 小时) "。 
    
    ![选择1H 一小时](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. 仍在" **NS - 名称服务器**"记录集的" **值**"框中，键入或复制粘贴下表" **第一行**"的值，然后按键盘上的 **Enter** 键，键入或复制粘贴" **下一行**"的值。 
    
    > [!IMPORTANT]
    > 每个名称服务器值 *必须*  位于" **值** "框中其自己单独的行上，如下图所示。 
  
|||
|:-----|:-----|
|**第一行** <br/> |ns1.bdm.microsoftonline.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> |
|**第二行** <br/> |ns2.bdm.microsoftonline.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> |
|**第三行** <br/> |ns3.bdm.microsoftonline.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> |
|**第四行** <br/> |ns4.bdm.microsoftonline.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> |
   
   ![在 "值" 框中键入或粘贴第一行值](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. 选择 " **保存记录集**"。
    
    ![选择 "保存记录集"](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 然后，你的 Microsoft 电子邮件和其他服务将全部设置为与你的域一起使用。 
