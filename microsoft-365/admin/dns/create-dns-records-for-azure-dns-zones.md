---
title: 为 Azure DNS 区域创建 DNS 记录
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: 了解如何验证您的域并为 Microsoft 的 Azure DNS 区域中的电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: fcc3ea42b7414cdd5fc0c34bfae91104287d2379
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400264"
---
# <a name="create-dns-records-for-azure-dns-zones"></a>为 Azure DNS 区域创建 DNS 记录

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
如果 Azure 是你的 DNS 托管提供商，请按照本文中的步骤验证你的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。
  
下面是要添加的主要记录。 
  
- [更改域的名称服务器 (NS) 记录](#change-your-domains-nameserver-ns-records)
    
- [添加 TXT 记录进行验证](#add-a-txt-record-for-verification)

- [添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [添加 Microsoft 所需的四个 CNAME 记录](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [为 SPF 添加 TXT 记录以帮助防止垃圾邮件](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [添加 Microsoft 所需的两条 SRV 记录](#add-the-two-srv-records-that-are-required-for-microsoft)
    
在 Azure 中添加这些记录后，您的域将设置为与 Microsoft 服务配合使用。
  
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="change-your-domains-nameserver-ns-records"></a>更改域的名称服务器 (NS) 记录
<a name="BKMK_NS"> </a>

> [!IMPORTANT]
> 必须在购买和注册域的域注册机构中执行此过程。 
  
注册 Azure 时，您在 DNS 区域中创建了一个资源组，然后将您的域名分配给该资源组。 该域名注册到外部域注册机构;Azure 不提供域注册服务。
  
若要在 Microsoft 中验证和创建域的 DNS 记录，首先需要更改域注册机构中的名称服务器，以便它们使用分配给资源组的 Azure 名称服务器。
  
若要在域注册机构的网站上更改域的名称服务器，请执行以下步骤。
  
1. 在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。
    
2. 通过使用下表中的值创建两个名称服务器记录，或编辑现有的名称服务器记录以使其与这些值匹配。 下面显示了 Azure 分配的名称服务器的示例。
    


**第一个**名称服务器：使用 Azure 分配的名称服务器值。  
**第二个 nameserver：** 使用 Azure 分配的名称服务器值。  

![Azure-BP-委派-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> You should use at least two name server records. 如果在域注册机构的网站上列出了任何其他名称服务器，则应将其删除。 
  
3. 保存所做的更改。
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. 然后，你的 Microsoft 电子邮件和其他服务将全部设置为与你的域一起使用。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. 若要开始，请使用[此链接](https://portal.azure.com )转到 Azure 上的 "域" 页面。 系统将会提示您先登录。
    
    ![Azure-BP-配置-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. 在**仪表板**页面上使用**搜索栏**，在 " **DNS 区域**" 中键入。 在 "结果显示" 中，选择 "**服务**" 部分下的 " **DNS 区域**"。 重定向后，选择要更新的域。
    
    ![Azure-BP-配置-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. 在您的域的 "**设置**" 页上的 " **DNS 区域**" 区域中，选择 " **+ 记录集**"。
    
    ![Azure-BP-配置-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. 在 "**添加记录集**" 区域中新记录集对应的框中，选择下表中的值。 
    
    （从下拉列表中选择 "**类型**" 和 " **TTL 单位**" 值。） 
    
    |**名称**|**Type**|**TTL**|**TTL 单位**|**值**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |1   <br/> |工作时间  <br/> |MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。           [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-最佳验证-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. 选择“确定”****。
  
6. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。
  
Microsof 找到正确的 TXT 记录表明域已通过验证。
  
1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。
    
2. 在“**域**”页面上，选择要验证的域。 
    
    
  
3. 在“**设置**”页面上，选择“**开始设置**”。
    
    
  
4. 在“**验证域**”页面上，选择“**验证**”。
    
    
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft
<a name="BKMK_add_MX"> </a>

1. 若要开始，请使用[此链接](https://portal.azure.com )转到 Azure 上的 "域" 页面。 系统将会提示您先登录。
    
    ![Azure-BP-配置-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. 在 "**仪表板**" 页上的 "**所有资源**" 区域中，选择要更新的域。 
    
    ![Azure-BP-配置-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. 在您的域的 "**设置**" 页上的 " **DNS 区域**" 区域中，选择 " **+ 记录集**"。
    
    ![Azure-BP-配置-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. 在 "**添加记录集**" 区域中新记录集对应的框中，选择下表中的值。 
    
    （从下拉列表中选择 "**类型**" 和 " **TTL 单位**" 值。） 
    
    |**名称**|**Type**|**TTL**|**TTL 单位**|**首选项**|**邮件交换**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1   <br/> |工作时间  <br/> |10    <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<domain-key\>*。 mail.protection.outlook.com  <br/> **注意：***\<domain-key\>* 从你的 Microsoft 帐户获取你的。   [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-配置-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. 选择“确定”****。
    
    ![Azure-BP-配置-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. 如果 " **Mx 记录**" 一节中列出了任何其他 MX 记录，则必须将其删除。 
    
    首先，在 " **DNS 区域**" 区域中，选择**MX 记录集**。
    
    ![Azure-BP-配置-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    接下来，选择要删除的 MX 记录。
    
    ![Azure-BP-配置-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. 选择**上下文菜单（**"..."），然后选择 "**删除**"。
    
    ![Azure-BP-配置-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. 选择“保存”****。
    
    ![Azure-BP-配置-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的四个 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

1. 若要开始，请使用[此链接](https://portal.azure.com )转到 Azure 上的 "域" 页面。 系统将会提示您先登录。
    
    ![Azure-BP-配置-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. 在 "**仪表板**" 页上的 "**所有资源**" 区域中，选择要更新的域。 
    
    ![Azure-BP-配置-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. 在您的域的 "**设置**" 页上的 " **DNS 区域**" 区域中，选择 " **+ 记录集**"。
    
    ![Azure-BP-配置-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. 添加四个 CNAME 记录中的第一个。
    
    在 "**添加记录集**" 区域中新记录集对应的框中，键入或复制并粘贴下表中第一行的值。 
    
    （从下拉列表中选择 "**类型**" 和 " **TTL 单位**" 值。） 
    
    |**名称**|**Type**|**TTL**|**TTL 单位**|**Alias**|
    |:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1   <br/> |工作时间  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |1   <br/> |工作时间  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1   <br/> |工作时间  <br/> |webdir.online.lync.com  <br/> |
    
   
    ![Azure-BP-配置-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. 选择“确定”****。
    
    ![Azure-BP-配置-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. 添加其他三个 CNAME 记录中的每一个。
    
    在 " **DNS 区域**" 区域中，选择 " **+ 记录集**"。 然后，在空记录集中，使用表中下一行的值创建记录，然后再次选择 **"确定"** 以完成该记录。 
    
    重复此过程，直到创建了全部四个 CNAME 记录。
    
7.  Optional为 MDM 添加2个 CNAME 记录。

> [!IMPORTANT]
> 如果你具有适用于 Microsoft 的移动设备管理（MDM），则必须创建两个附加的 CNAME 记录。 创建流程与你用于其他四个 CNAME 记录的流程一样，但需提供下表中的值。 （如果没有 MDM，则可以跳过此步骤。） 
  
|**名称**|**Type**|**TTL**|**TTL 单位**|**Alias**|
|:-----|:-----|:-----|:-----|:-----|
|enterpriseregistration  <br/> |CNAME  <br/> |1   <br/> |工作时间  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |CNAME  <br/> |1   <br/> |工作时间  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。 
  
1. 若要开始，请使用[此链接](https://portal.azure.com )转到 Azure 上的 "域" 页面。 系统将会提示您先登录。
    
    ![Azure-BP-配置-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. 在 "**仪表板**" 页上的 "**所有资源**" 区域中，选择要更新的域。 
    
    ![Azure-BP-配置-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. 在 " **DNS 区域**" 区域中，选择 " **TXT" 记录集**。
    
    ![Azure-BP-配置-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. 在 "**记录集属性**" 区域中新记录集对应的框中，选择下表中的值。 
    
    （从下拉列表中选择 "**类型**" 和 " **TTL 单位**" 值。） 
    
    |**名称**|**Type**|**TTL**|**TTL 单位**|**值**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |1   <br/> |工作时间  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。           

    ![Azure-BP-配置-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. 选择“保存”****。
    
    ![Azure-BP-配置-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

1. 若要开始，请使用[此链接](https://portal.azure.com )转到 Azure 上的 "域" 页面。 系统将会提示您先登录。
    
    ![Azure-BP-配置-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. 在 "**仪表板**" 页上的 "**所有资源**" 区域中，选择要更新的域。 
    
    ![Azure-BP-配置-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. 在您的域的 "**设置**" 页上的 " **DNS 区域**" 区域中，选择 " **+ 记录集**"。
    
    ![Azure-BP-配置-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. 添加两条 SRV 记录中的第一条记录。
    
    在 "**添加记录集**" 区域中新记录集对应的框中，选择下表中第一行的值。 
    
    （从下拉列表中选择 "**类型**" 和 " **TTL 单位**" 值。） 
    
    |**名称**|**Type**|**TTL**|**TTL 单位**|**优先级**|**权重**|**端口**|**目标**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip _tls  <br/> |SRV  <br/> |1   <br/> |工作时间  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls _tcp  <br/> |SRV  <br/> |1   <br/> |工作时间  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> 

    ![Azure-BP-配置-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. 选择“确定”****。
    
    ![Azure-BP-配置-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. 添加另一条 SRV 记录。
    
    在新记录的框中，键入或复制并粘贴表中第二行的值。
    
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
