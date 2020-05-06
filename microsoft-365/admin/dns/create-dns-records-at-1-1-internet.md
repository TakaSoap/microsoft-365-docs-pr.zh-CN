---
title: 在 1&1 IONOS 为 Microsoft 创建 DNS 记录
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: 了解如何验证您的域并为电子邮件、Skype for Business Online 和其他服务（1&1 IONOS for Microsoft）设置 DNS 记录。
ms.openlocfilehash: 1c32e15be8bfdf9ea29647af511d0f8ff0ac0b57
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049139"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a>在 1&1 IONOS 为 Microsoft 创建 DNS 记录

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
> [!CAUTION]
> 请注意，1&1 IONOS 不允许域同时具有 MX 记录和顶级自动发现 CNAME 记录。 这将限制为 Microsoft 配置 Exchange Online 的方式。 有一种解决方法，但我们建议您在创建子域的过程 1&1 **IONOS 时使用它。** >[如果您选择在 1](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)&1 IONOS 管理您自己的 Microsoft DNS 记录，请按照本文中的步骤验证您的域，并为电子邮件、Skype For business Online 等设置 DNS 记录。 
  
在 1&1 IONOS 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。
  
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
请按下列步骤操作或[观看视频（从 0:42 开始）](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)。
  
1. 若要开始，请使用[此链接](https://my.1and1.com/)转到域页面 1&1 IONOS。 You'll be prompted to log in.
    
2. 选择 "**管理域**"。
    
3. 在 "**域中心**" 页上，找到要更新的域，然后选择该域的 **"面板"** （ **v**）控制。
    
4. 在 "**域设置**" 区域中，选择 "**编辑 DNS 设置**"。
    
5. 在 " **TXT 和 SRV 记录**" 部分中，选择 "**添加记录**"。
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**类型** <br/> |**前缀** <br/> |**名称值** <br/> |
    |TXT  <br/> |（将此字段留空）  <br/> |MS=ms *XXXXXXXX*  <br/> 注意：这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)          |
   
7. 选择“保存”****。
    
8. 再次选择 "**保存**"。 
    
9. 在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。
    
10. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
在域注册机构网站添加了记录后，你将返回到 Microsoft 365 并请求 Microsoft 365 查找记录。
  
Microsof 找到正确的 TXT 记录表明域已通过验证。
  
1. 在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

    
2. 在“**域**”页面上，选择要验证的域。 
    
3. 在“**设置**”页面上，选择“**开始设置**”。
    
4. 在“**验证域**”页面上，选择“**验证**”。
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft
<a name="BKMK_add_MX"> </a>

请执行以下步骤或[观看视频（从3:22 开始）](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)。
  
> [!NOTE]
> 如果你已向1und1.de 注册，请[在此处登录](https://go.microsoft.com/fwlink/?linkid=859152)。 
  
1. 若要开始，请使用[此链接](https://my.1and1.com/)转到域页面 1&1 IONOS。 You'll be prompted to log in.
    
2. 选择 "**管理域**"。
    
3. 在 "**域中心**" 页上，找到要更新的域，然后选择该域的 **"面板"** （ **v**）控制。
    
4. 在 "**域设置**" 区域中，选择 "**编辑 DNS 设置**"。
    
5. 在 " **MX 记录**" 部分的 "**邮件交换器（MX 记录）** " 区域中，选择 "**其他邮件服务器**"。<br/>(You may have to scroll down.)<br/>![1&amp;1-BP-配置-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png) <br/>
  
6. 如果已列出任何 MX 记录，请选择该记录，然后按键盘上的**delete**键，将其删除。<br/>（如果没有已列出的 MX 记录，请继续执行下一步。）<br/>![1&amp;1-BP-配置-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)<br/>
  
7. 在 " **MX 1** " 记录的框中，键入或复制并粘贴下表中的值。 
    
    |**MX 1**|**优先级**|
    |:-----|:-----|
    | *\<域密钥\>*  .mail.protection.outlook.com  <br/>  注意：从你\<的 Microsoft 帐户\>获取你的域密钥。 如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)          |10    <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | 
    
    ![1和 1-配置2和3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. 选择“保存”****。<br/>(You may have to scroll down.)<br/>![1&amp;1-BP-配置-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)
  
9. 在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。<br/>![在 "编辑 DNS 设置" 对话框中选择 "是"](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的六条 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

1&1 IONOS 需要解决方法，以便您可以将 MX 记录与 Microsoft 电子邮件服务所需的 CNAME 记录结合使用。 此替代方法要求您在 1&1 IONOS 创建一组子域，并将其分配给 CNAME 记录。
  
> [!IMPORTANT]
> 在开始此过程之前，请确保至少有两个可用的子域。 仅当您已经有在 1&1 IONOS 创建子域的经验时，才建议使用此解决方案。 
  
### <a name="basic-cname-records"></a>基本 CNAME 记录

请执行以下步骤或[观看视频（从3:57 开始）](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)。
  
> [!NOTE]
> 如果你已向1und1.de 注册，请[在此处登录](https://go.microsoft.com/fwlink/?linkid=859152)。 
  
1. 若要开始，请使用[此链接](https://my.1and1.com/)转到域页面 1&1 IONOS。 You'll be prompted to log in.
    
2. 选择 "**管理域**"。
    
3. 在 "**域中心**" 页上，找到要更新的域，然后选择 "**管理子域**"。<br/>![1&amp;1-BP-配置-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png) <br/>现在，您将创建两个子域并为每个子域设置一个**别名**值。<br/>（这是必需的，因为 1&1 IONOS 仅支持一个顶级 CNAME 记录，但 Microsoft 需要多个 CNAME 记录。）<br/>首先，创建自动发现子域。
    
4. 在 "**子域概述**" 部分，选择 "**创建子域**"。
    
    ![1&amp;1-BP-配置-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. 在 "为新子域**创建子域**" 框中，键入或复制并仅粘贴下表中的 "**创建子域**" 值。 （将在后续步骤中添加**别名**值。）

    |**创建子域**|**Alias**|
    |:-----|:-----|
    |自动发现  <br/> |autodiscover.outlook.com   | 

    ![1&amp;1-BP-配置-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. 选择 "**创建子域**"。<br/>![1&amp;1-BP-配置-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)
  
7. 在 "**子域概述**" 部分，找到刚创建的 "**自动发现**" 子域，然后为该子域选择 **"面板" （v）** 控件。 <br/>![1&amp;1-BP-配置-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)
  
8. 在 "**子域设置**" 区域中，选择 "**编辑 DNS 设置**"。 <br/>![1&amp;1-BP-配置-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)
  
9. 在 " **A/AAAA 记录（IP 地址）** " 部分的 " **IP 地址（A 记录）** " 区域中，选择 " **CNAME**"。<br/>![1&amp;1-BP-配置-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)
  
10. 在 "**别名：** " 框中，键入或复制并仅粘贴下表中的**别名**值。<br/> 
    
    |**创建子域**|**Alias**|
    |:-----|:-----|
    |自动发现  <br/> |autodiscover.outlook.com   |

    ![1&amp;1-BP-配置-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. 选中 "**我知道的已知**免责声明" 对应的复选框。<br/>![1&amp;1-BP-配置-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)
  
12. 选择“保存”****。<br/>![1&amp;1-BP-配置-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)
  
  
### <a name="additional-cname-records"></a>其他 CNAME 记录

以下过程中创建的其他 CNAME 记录将启用 Skype for Business Online 服务。 您将使用用于创建两个已创建的 CNAME 记录的相同步骤。
  
1. 创建第三个子域（Lyncdiscover.）。<br/>在 "**子域概述**" 部分，选择 "**创建子域**"。
    
2. 在 "为新子域**创建子域**" 框中，键入或复制并仅粘贴下表中的 "**创建子域**" 值。 （将在后续步骤中添加**别名**值。）<br/> 
    
    |**创建子域**|**Alias**|
    |:-----|:-----|
    |lyncdiscover   |webdir.online.lync.com  |
   
3. 选择 "**创建子域**"。
    
4. 在 "**域中心**" 页上，选择 "**管理子域**"。
    
5. 在 "**子域概述**" 部分，找到您刚创建的**lyncdiscover.** 子域，然后为该子域选择 **"面板" （v）** 控件。 <br/>在 "**子域设置**" 区域中，选择 "**编辑 DNS 设置**"。
    
6. 在 " **A/AAAA 记录（IP 地址）** " 部分的 " **IP 地址（A 记录）** " 区域中，选择 " **CNAME**"。
    
7. 在 "**别名：** " 框中，键入或复制并仅粘贴下表中的**别名**值。 <br/>
    
    |**创建子域**|**Alias**|
    |:-----|:-----|
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
   
8. 选中 "**我知道**免责声明" 复选框，然后选择 "**保存**"。
    
9. 在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。
    
10. 创建第四个子域（SIP）： <br/>在 "**子域概述**" 部分，选择 "**创建子域**"。
    
11. 在 "为新子域**创建子域**" 框中，键入或复制并仅粘贴下表中的 "**创建子域**" 值。 （将在后续步骤中添加**别名**值。） <br/>
    
    |**创建子域**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
12. 选择 "**创建子域**"。
    
13. 在 "**域中心**" 页上，选择 "**管理子域**"。
    
14. 在 "**子域概述**" 部分，找到您刚创建的**sip**子域，然后选择该子域的 **"面板" （v）** 控制。 <br/>在 "**子域设置**" 区域中，选择 "**编辑 DNS 设置**"。
    
15. 在 " **A/AAAA 记录（IP 地址）** " 部分的 " **IP 地址（A 记录）** " 区域中，选择 " **CNAME**"。
    
16. 在 "**别名：** " 框中，键入或复制并仅粘贴下表中的**别名**值。 
    
    |**创建子域**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
17. 选中 "**我知道**免责声明" 复选框，然后选择 "**保存**"。
    
18. 在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。
    
### <a name="cname-records-needed-for-mdm"></a>MDM 所需的 CNAME 记录

> [!IMPORTANT]
> 创建流程与你用于其他四个 CNAME 记录的流程一样，但需提供下表中的值。 
  
|**创建子域**|**Alias**|
|:-----|:-----|
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。 需要示例吗？ 请查看 [Microsoft 的外部域名系统记录](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)。 若要验证您的 SPF 记录，您可以使用其中一种[SPF 验证工具](../setup/domains-faq.md)。 
  
请执行以下步骤或[观看视频（从5:09 开始）](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)。
  
> [!NOTE]
> 如果你已向1und1.de 注册，请[在此处登录](https://go.microsoft.com/fwlink/?linkid=859152)。 
  
1. 若要开始，请使用[此链接](https://my.1and1.com/)转到域页面 1&1 IONOS。 You'll be prompted to log in.
    
2. 选择 "**管理域**"。
    
3. 在 "**域中心**" 页上，找到要更新的域，然后选择该域的 **"面板"** （**v**）控制。
    
4. 在 "**域设置**" 区域中，选择 "**编辑 DNS 设置**"。
    
5. 在 " **TXT 和 SRV 记录**" 部分中，选择 "**添加记录**"。 <br/>(You may have to scroll down.)
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. <br/>(Choose the **Type** value from the drop-down list.) <br/>
    
    |**类型**|**前缀**|**名称值**|
    |:-----|:-----|:-----|
    |TXT  <br/> |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。           | 
    
    ![TXT 记录](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. 选择“保存”****。<br/>![添加记录](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)
  
8. 选择“保存”****。<br/>![保存记录](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)
  
9. 在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。<br/>![在 "编辑 DNS 设置" 对话框中选择 "是"](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的两条 SRV 记录

请执行以下步骤或[观看视频（从5:51 开始）](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)。
  
> [!NOTE]
> 如果你已向1und1.de 注册，请[在此处登录](https://go.microsoft.com/fwlink/?linkid=859152)。 
  
1. 若要开始，请使用[此链接](https://my.1and1.com/)转到域页面 1&1 IONOS。 You'll be prompted to log in.
    
2. 选择 "**管理域**"。
    
3. 在 "**域中心**" 页上，找到要更新的域，然后选择该域的 **"面板"** （ **v**）控制。
    
4. 在 "**域设置**" 区域中，选择 "**编辑 DNS 设置**"。
    
5. 在 " **TXT 和 SRV 记录**" 部分中，选择 "**添加记录**"。
    
6. 添加两条 SRV 记录中的第一条记录。<br/>在 "**添加记录**" 区域中新记录的框内，键入或复制并粘贴下表中第一行的值。 <br/>（从下拉列表中选择 "**类型**" 和 " **TTL** " 值。） 
    
    |**类型**|**服务**|**协议**|**名称**|**Host**|**优先级**|**权重**|**端口**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV  <br/> |sip  <br/> |tls  <br/> |(Leave this field empty.)  <br/> |sipdir.online.lync.com  <br/> |100  <br/> |1  <br/> |443  <br/> |3600（1个 h）  <br/> |
    |SRV  <br/> |sipfederationtls  <br/> |tcp  <br/> |(Leave this field empty.)  <br/> |sipfed.online.lync.com  <br/> |100  <br/> |1  <br/> |5061  <br/> |3600（1个 h）  <br/> |  
    
    ![1&amp;1-BP-配置-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. 选择“保存”****。 <br/>![1&amp;1-BP-配置-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)
  
8. 选择“保存”****。 <br/>![1&amp;1-BP-配置-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)
  
9. 在 "**编辑 DNS 设置**" 对话框中，选择 **"是"**。 <br/>![在 "编辑 DNS 设置" 对话框中选择 "是"](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
10. 添加另一条 SRV 记录。 <br/>在 " **TXT 和 SRV 记录**" 部分中，选择 "**添加记录**"。 <br/>在 "**添加记录**" 区域中，使用表中其他行的值创建记录，然后再次选择 "**添加**"、"**保存**" 和 **"是"** 以完成记录。 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。 
  
