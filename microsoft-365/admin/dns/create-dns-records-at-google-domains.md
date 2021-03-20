---
title: 在 Google Domains 为 Microsoft 创建 DNS 记录
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: 了解如何在 Google Domains 验证你的域并为 Microsoft 设置电子邮件、Lync 和其他服务的 DNS 记录。
ms.openlocfilehash: 9a1d0a8513f6071a3c9c686c10f6fd282f1a0e96
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910218"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a>在 Google Domains 为 Microsoft 创建 DNS 记录

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。 
  
如果 DNS 托管提供商是 Google Domains，请按照本文中的步骤验证域并为电子邮件、Lync 等设置 DNS 记录。
  
在 Google Domains 添加这些记录后，你的域将设置为使用 Microsoft 服务。
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在将域或 DNS 记录添加到 Microsoft 后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：
    
1. 选择“**登录**”。
    
2. 输入登录凭据，然后再次选择“**登录**”。
    
2. 在“**我的域**”页面上，找到要与 Microsoft 一起使用的域，然后选择其旁边的“**管理**”链接。 在左侧导航窗格中，选择“**DNS**”。
    
3. 在“**自定义资源记录**”部分中新记录的框内，键入或复制并粘贴下表中的值。 
    
    （您可能需要向下滚动。）
    
    （从下拉列表中选择“**类型**”值。） 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**名称** <br/> |**类型** <br/> |**TTL** <br/> |**数据** <br/> |
    |@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
   
4. 选择“**添加**”。
    
5. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。
  
Microsof 找到正确的 TXT 记录表明域已通过验证。
  
1. 在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

    
2. 在“**域**”页面上，选择要验证的域。 
    
3. 在“**设置**”页面上，选择“**开始设置**”。
    
4. 在“**验证域**”页面上，选择“**验证**”。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft
<a name="BKMK_add_MX"> </a>

1. 要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：
    
2. 选择“**登录**”。
    
3. 输入登录凭据，然后再次选择“**登录**”。
4. 在“**域**”页面上的“**域**”部分中，为要编辑的域选择“**配置 DNS**”。
    
    > [!IMPORTANT]
    > 如果有 G Suite 电子邮件帐户，必须先删除与该帐户关联的 MX 记录。 G Suite 的 MX 记录将导致无法添加任何其他 MX 记录，包括 Microsoft 所需的 MX 记录。 请注意，删除 G 套件记录不会删除 G 套件帐户。 若要删除 G 套件 MX 记录，请使用以下步骤。 
  
5. 首先，在“**综合记录**”部分的“**G Suite**”区域中，选择“**删除**”。
    
    （可能需要向下滚动。）
    
    ![在“综合记录”部分中选择“删除”](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. 选择“**删除**”。
    
    ![选择“删除”](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. 在“**自定义资源记录**”部分中新记录的框内，键入或复制并粘贴下表中的值。 
    
    （您可能需要向下滚动。）
    
    （从下拉列表中选择“**类型**”值。） 
    
    |**名称**|**类型**|**TTL**|**数据**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1H  <br/> |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> **0** 是 MX 优先级值。将其添加到 MX 值的开头，使用一个空格将其与其余部分隔开。  <br/> **注意：** 从 Microsoft 帐户获取 \<*domain-key*\>。  [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml) <br/> |
   
    ![在“自定义资源记录”部分键入或粘贴值](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. 选择“**添加**”。
    
    ![选择“添加”](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. 如果有任何其他自定义 MX 记录，请将其删除。
    
1. 选择相应 MX 记录行中的“**编辑**”。 
    
    ![选择相应 MX 记录行中的“编辑”](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. 针对每条其他自定义 MX 记录，选择“**数据**”框中的条目，然后按键盘上的 **Delete** 键删除该记录。 
    
    继续操作，直到删除所有其他 MX 记录的“**数据**”条目。 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. 删除所有其他 MX 记录的“**数据**”条目后，选择“**保存**”以保存更改。 
    
    ![选择“保存”](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的 5 条 CNAME 记录

1. 若要开始，请转到 [Google Domains 页面] (https://domains.google.com/registrar) 并登录。
    
2. 在“**域**”页面上的“**域**”部分中，为要编辑的域选择“**配置 DNS**”。 
    
3. 添加第一条 CNAME 记录。
    
    在“**自定义资源记录**”部分中新记录的框内，键入或复制粘贴下表第一行中的值。 
    
    （可能需要向下滚动。）
    
    （从下拉列表中选择“**类型**”值。） 
    
    |**名称**|**类型**|**TTL**|**数据**|
    |:-----|:-----|:-----|:-----|
    |自动发现  <br/> |CNAME  <br/> |1H  <br/> |autodiscover.outlook.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
    |sip  <br/> |CNAME  <br/> |1H  <br/> |sipdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1H  <br/> |webdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |1H  <br/> |enterpriseregistration.windows.net.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |1H  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |
   
    ![在“自定义资源记录”部分键入或粘贴值](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. 选择“**添加**”。
    
    ![选择“添加”](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. 添加其他 4 条 CNAME 记录。
    
    在“**自定义资源记录**”部分，使用表中下一行的值创建记录，然后再次选择“**添加**”完成该记录。 
    
    重复该过程，直到创建完所需的所有 CNAME 记录。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 可以将所需的 Microsoft 值添加到当前记录，这样就拥有包含两组值的单个 SPF 记录。 需要示例吗？ 请查看 [Microsoft 的外部域名系统记录](../../enterprise/external-domain-name-system-records.md#bkmk_spfrecords)。 若要验证 SPF 记录，可使用以下任一 [SPF 验证工具](../setup/domains-faq.yml)。 
  
1. 要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：
    
1. 选择“**登录**”。
    
2. 输入登录凭据，然后再次选择“**登录**”。
    
3. 在“**域**”页面上的“**域**”部分中，为要编辑的域选择“**配置 DNS**”。 
    
4. 在“**自定义资源记录**”部分的 TXT 记录行上，选择“**编辑**”。 
    
    > [!IMPORTANT]
    > Google Domains 会将 TXT 记录存储为可能含有多条记录的集。存在至少一条其他 TXT 记录（例如用于验证域的 TXT 记录）时，必须向该记录集添加新的 TXT 记录。如果尝试将其他 TXT 记录作为单独条目进行输入，将始终出现“**记录重复**”错误信息。 
  
    ![选择相应 TXT 记录行中的“编辑”](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. 选择 **(+)** 控件。 
    
    ![选择加号控件](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. 在新记录的框中，键入或复制并粘贴下表中的值。
    
    （可能需要向下滚动。）
    
    |**数据**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> 

    > [!NOTE]
    > 我们建议复制并粘贴此条目，以保证正确保留所有空格。           
   
   ![在“自定义资源记录”部分键入或粘贴值](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. 选择“**保存**”。
    
    ![选择“保存”](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

1. 要开始，请使用[此链接](https://domains.google.com/registrar)转到你在 Google Domains 上的域页面。 系统将会提示您登录。 为此，请执行以下操作：
    
2. 选择“**登录**”。
    
3. 输入登录凭据，然后再次选择“**登录**”。
    
4. 在“**域**”页面上的“**域**”部分中，为要编辑的域选择“**配置 DNS**”。 
    
5. 添加第一条 SRV 记录。
    
    在“**自定义资源记录**”部分中新记录的框内，键入或复制并粘贴下表中的值。 
    
    （您可能需要向下滚动。）
    
    （从下拉列表中选择“**类型**”值。） 
    
    |**名称**|**类型**|**TTL**|**数据**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|SRV|1H|100 1 443 sipdir.online.lync.com. **此值必须以句点 (.) 结尾。** **注意：** 我们建议复制并粘贴此条目，以保证正确保留所有空格。           |
    |_sipfederationtls._tcp|SRV|1H|100 1 5061 sipfed.online.lync.com. **此值必须以句点 (.) 结尾。**

    我们建议复制并粘贴此条目，以保证正确保留所有空格。       
   
    ![在“自定义资源记录”部分键入或粘贴值](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. 选择“**添加**”。
    
    ![选择“添加”](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. 添加另一条 SRV 记录。
    
    在“**自定义资源记录**”部分，使用表中第二行的值创建记录，然后再次选择“**添加**”完成该记录。 
    
    > [!NOTE]
    > Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
