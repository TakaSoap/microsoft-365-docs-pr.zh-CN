---
title: 更改名称服务器以使用 Google 域设置 Microsoft
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: 了解如何将 Microsoft 设置为在 Google 域管理自定义域的 DNS 记录。
ms.openlocfilehash: 05d77ef4cb78351727870a384f4a28c6e4acc4b0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646423"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a>更改名称服务器以使用 Google 域设置 Microsoft

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
如果希望 Microsoft 为你管理 DNS 记录，请按照以下说明操作。  (如果你愿意，可以 [在 Google 域管理所有 DNS 记录](create-dns-records-at-google-domains.md)。 ) 
  
    
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
>  此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 若要开始，请通过 [此链接](https://domains.google.com/registrar)转到 Google 域中的 "域" 页面。 You'll be prompted to sign in. To do so:
    
1. 选择“**登录**”。
    
2. 输入登录凭据，然后再次选择 **"登录"**。
    
2. 在“**域**”页面上的“**域**”部分中，为要编辑的域选择“**配置 DNS**”。 
    
3. 在“**自定义资源记录**”部分中新记录的框内，键入或复制并粘贴下表中的值。 
    
    （您可能需要向下滚动。）
    
    （从下拉列表中选择“**类型**”值。） 
    
|||||
|:-----|:-----|:-----|:-----|
|**名称** <br/> |**类型** <br/> |**TTL** <br/> |**数据** <br/> |
|@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX* <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. 选择“**添加**”。
    
5. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
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
> 当您将您的域的 NS 记录更改为指向 Microsoft 名称服务器时，当前与您的域相关联的所有服务都将受到影响。 例如，发送到您的域的所有电子邮件 (如 rob@ *your_domain。*  在进行此更改后，com) 将会启动到 Microsoft。 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > 完成本节中的步骤后，应列出的唯一名称服务器为以下四个： 
  
1. 要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：
    
1. 选择“**登录**”。
    
2. 输入登录凭据，然后再次选择“**登录**”。
    
2. 在“**域**”页面上的“**域**”部分中，为要编辑的域选择“**配置 DNS**”。 
    
3. 在" **域**"页面的" **名称服务器**"部分中，选择" **使用自定义名称服务器**"。
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. 根据现在显示的页面上是否已列出名称服务器，继续执行以下两个过程之一：
    
  - 如果 **未** 列出名称服务器，则 [如果未列出名称服务器](#if-there-are-no-nameservers-already-listed)。
    
  - 如果 **已** 列出名称服务器，则 [如果已列出名称服务器](#if-there-are-nameservers-already-listed)。
    
### <a name="if-there-are-no-nameservers-already-listed"></a>如果未列出名称服务器

1. 添加第一个名称服务器。
    
    在" **名称服务器**"部分的" **名称服务器**"框内，键入或复制粘贴下表中的第一个值。 
    
|||
|:-----|:-----|
|**第一个名称服务器** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**第二个名称服务器** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**第三个名称服务器** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**第四个名称服务器** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-域-BP-委派-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. 选择 " **+ (添加) ** " 控件以创建一个空行。 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. 添加其他三个名称服务器记录。
    
    在 " **使用自定义名称服务器** " 部分，使用表中下一行的值创建记录，然后选择 " **+ (添加) ** " 控件以添加另一行。 
    
    重复该过程，直到创建完全部 4 条名称服务器记录。
    
4. 选择“**保存**”。
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> 你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。 然后，你的 Microsoft 电子邮件和其他服务将全部设置为与你的域一起使用。 
  
### <a name="if-there-are-nameservers-already-listed"></a>如果已列出名称服务器

1. 如果列出了任何其他名称服务器，请选择 " **编辑**"。
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers.  (也就是说，仅删除任何  *未*  命名的 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**或 **ns4.bdm.microsoftonline.com**的当前名称服务器。 )  
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. 选择每个服务器，然后按键盘上的 **Delete** 键，可将其删除。 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. 仍在" **名称服务器**"部分的" **名称服务器**"行中，键入或复制并粘贴下表中的值。 
    
|||
|:-----|:-----|
|**第一个名称服务器** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**第二个名称服务器** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**第三个名称服务器** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**第四个名称服务器** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-域-BP-委派-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. 选择 " **+ (添加) ** " 控件以创建一个空行。 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. 添加其他两个名称服务器记录。
    
    在 " **使用自定义名称服务器** " 部分，使用表中下一行的值创建记录，然后选择 " **+ (添加) ** " 控件以添加另一行。 
    
    重复该过程，直到创建完全部 4 条名称服务器记录。
    
6. 选择“**保存**”。
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> 你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。 然后，你的 Microsoft 电子邮件和其他服务将全部设置为与你的域一起使用。 
  
