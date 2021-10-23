---
title: 连接 Namecheap 将 DNS 记录Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: 了解在 Namecheap for Microsoft 中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: 5cc3a961e30e482b35c1646791eec9e03a065fbc
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60556445"
---
# <a name="connect-your-dns-records-at-namecheap-to-microsoft-365"></a>连接 Namecheap 将 DNS 记录Microsoft 365

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。 
  
如果 Namecheap 是 DNS 托管提供商，请按照本文中的步骤验证域，并设置电子邮件、Skype for Business Online 等的 DNS 记录。
  
在 Namecheap 添加这些记录后，您的域将设置为使用 Microsoft 服务。
  
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。
  
> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。 
  
1. To get started， go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). 系统将提示你登录并继续。

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="登录到 Namecheap。":::

1. 在登录页面上的"帐户 **"下**， **从** 下拉列表中选择"域列表"。 

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="从下拉列表中选择&quot;域列表&quot;。":::

1. 在"域列表"页上，选择要编辑的域，然后选择"管理 **"。**

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="选择&quot;管理&quot;。":::

1. 选择 **"高级 DNS"。**

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="选择&quot;高级 DNS&quot;。":::

1. 在"**主机记录"** 部分，选择"**添加新记录"。**

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="选择&quot;添加新记录&quot;。":::

1. 在"**类型"** 下拉列表中，选择 **"TXT 记录"。**
    
    > [!NOTE]
    > 选择 **"添加新** 记录"时，将自动显示"类型 **"下拉列表**。 

     :::image type="content" source="../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png" alt-text="选择&quot;TXT 记录&quot;。":::

1. 在新记录的框中，键入或复制并粘贴下表中的值。
    
     (从下拉列表中选择 **TTL** 值。)  
    
    |**类型**|**主机**|**值**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/>**注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。  [如何查找此项？](../get-help-with-domains/information-for-dns-records.md) |30 分钟  <br/> |

     :::image type="content" source="../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png" alt-text="复制并粘贴表中的值。":::

1. Select the **Save Changes** (check mark) control. 

     :::image type="content" source="../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png" alt-text="选择&quot;保存更改&quot;控件。":::

1. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。
    
在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。 Microsof 找到正确的 TXT 记录表明域已通过验证。 

若要验证记录，Microsoft 365：
  
1. 在管理中心中，转到 **"设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**域"。**</a>
    
2. On the Domains page， select the domain that you're verifying， and select **Start setup**.   
  
3. 在“**验证域**”页面上，选择“**验证**”。
    
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft
  
1. To get started， go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). 系统将提示你登录并继续。

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="登录到 Namecheap。":::

1. 在登录页面上的"帐户 **"下**， **从** 下拉列表中选择"域列表"。 

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="从下拉列表中选择&quot;域列表&quot;。":::

1. 在"**域列表"** 页上，选择要编辑的域，然后选择"管理 **"。**

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="选择&quot;管理&quot;。":::

1. 选择 **"高级 DNS"。**

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="选择&quot;高级 DNS&quot;。":::

1. 在"**邮件设置"** 部分，从"电子邮件转发"下拉列表 **中选择**"自定义 **MX"。** 
    
    （您可能需要向下滚动。）

     :::image type="content" source="../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png" alt-text="选择&quot;自定义 MX&quot;。"::: 

1. 选择 **"添加新记录"。**

     :::image type="content" source="../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png" alt-text="添加新记录。":::

1. 在新记录的框中，键入或复制并粘贴下表中的值。
    
    **("优先级"** 框是"值"框右边的 **未命名框**。 从 **下拉列表中选择 TTL** 值。)  
    
    |**类型**|**主机**|**值**|**优先级**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX 记录  <br/> |@  <br/> |\<*domain-key*\>.mail.protection.outlook.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> **注意：** 从  *\<domain-key\>*  Microsoft 帐户获取你的帐户。  如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)          |0  <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml) <br/> |30 分钟  <br/> |

     :::image type="content" source="../../media/f3b76d62-5022-48c1-901b-8615a8571309.png" alt-text="复制并粘贴表中的值。":::

1. Select the **Save Changes** (check mark) control. 

     :::image type="content" source="../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png" alt-text="选择&quot;保存更改&quot;控件。":::

1. 如果存在任何其他 MX 记录，请使用以下两步过程删除其中每个记录：
    
    首先，选择 (删除) 可删除的记录。 

     :::image type="content" source="../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png" alt-text="选择&quot;删除&quot;。":::

    第二步 **，选择"** 是"以确认删除。 

     :::image type="content" source="../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png" alt-text="选择&quot;是&quot;。":::

    删除除之前在此过程中添加的 MX 记录之外的所有 MX 记录。
  
## <a name="add-the-cname-record-required-for-microsoft"></a>添加 Microsoft 所需的 CNAME 记录

1. To get started， go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). 系统将提示你登录并继续。

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="登录到 Namecheap。":::

1. 在登录页面上的"帐户 **"下**， **从** 下拉列表中选择"域列表"。 

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="选择&quot;域列表&quot;。":::

1. 在"**域列表"** 页上，选择要编辑的域，然后选择"管理 **"。**

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="选择&quot;管理&quot;。":::

1. 选择 **"高级 DNS"。**

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="选择&quot;高级 DNS&quot;。":::

1. 在"**主机记录"** 部分，选择"**添加新记录"。**

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="选择&quot;添加新记录&quot;。":::

1. 在"**类型"** 下拉列表中，选择 **"CNAME 记录"。**
    
    > [!NOTE]
    > 选择 **"添加新** 记录"时，将自动显示"类型 **"下拉列表**。 

     :::image type="content" source="../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png" alt-text="选择&quot;CNAME 记录&quot;。":::

1. In the empty boxes for the new record， select **CNAME** for the **Record Type**， and then type or copy and paste the values from the first row in the following table.
    
    |**类型**|**主机**|**值**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |自动  <br/> |

     :::image type="content" source="../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png" alt-text="复制并粘贴表中的值。":::

1. Select the **Save Changes** (check mark) control. 

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="选择&quot;保存更改&quot;控件。":::

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 相反，将所需的 Microsoft 值添加到当前记录，以便你有一个 *包含这*  两组值的 SPF 记录。 

1. To get started， go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). 系统将提示你登录并继续。
    
1. 在登录页面上的"帐户 **"下**， **从** 下拉列表中选择"域列表"。 

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="选择&quot;域列表&quot;。":::

1. 在"**域列表"** 页上，选择要编辑的域，然后选择"管理 **"。**

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="选择&quot;管理&quot;。":::

1. 选择 **"高级 DNS"。**

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="选择&quot;高级 DNS&quot;。":::

1. 在"**主机记录"** 部分，选择"**添加新记录"。**

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="选择&quot;添加新记录&quot;。":::

1. 在"**类型"** 下拉列表中，选择 **"TXT 记录"。**
    
    > [!NOTE]
    > 选择 **"添加新** 记录"时，将自动显示"类型 **"下拉列表**。 

     :::image type="content" source="../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png" alt-text="选择&quot;TXT 记录&quot;。":::

1. 在新记录的框中，键入或复制并粘贴下表中的以下值。
    
     (从下拉列表中选择 **TTL** 值。)  
    
    |**类型**|**主机**|**值**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。 |30 分钟  <br/> |

     :::image type="content" source="../../media/ea0829f1-990b-424b-b26e-9859468318dd.png" alt-text="复制并粘贴表中的值。":::

1. Select the **Save Changes** (check mark) control. 

     :::image type="content" source="../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png" alt-text="选择&quot;保存更改&quot;控件。":::

## <a name="advanced-option-skype-for-business"></a>高级选项：Skype for Business

只有组织将 Skype for Business 用于联机通信服务（如聊天、电话会议和视频呼叫）以及 Microsoft Teams。 Skype 4 条记录：2 条 SRV 记录用于用户到用户的通信，2 条 CNAME 记录用于登录和将用户连接到服务。

### <a name="add-the-two-required-srv-records"></a>添加两条必需的 SRV 记录

1. To get started， go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to sign in.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="登录到 Namecheap。":::

1. 在登录页面上的"帐户 **"下**， **从** 下拉列表中选择"域列表"。 

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="选择&quot;域列表&quot;。":::

1. 在"**域列表"** 页上，选择要编辑的域，然后选择"管理 **"。**

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="选择&quot;管理&quot;。":::

1. 选择 **"高级 DNS"。**

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="选择&quot;高级 DNS&quot;。":::

1. 在"**主机记录"** 部分，选择"**添加新记录"。**

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="选择&quot;添加新记录&quot;。":::

1. 在"**类型"** 下拉列表中，选择 **"SRV 记录"。**
    
    > [!NOTE]
    > 选择 **"添加新** 记录"时，将自动显示"类型 **"下拉列表**。 

     :::image type="content" source="../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png" alt-text="选择 SRV 记录类型。":::

1. 在新记录的空框中，键入或复制并粘贴下表中第一行的值。
    
    |**服务**|**协议**|**优先级**|**权重**|**端口**|**目标**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |自动  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> |自动  <br/> |
       
     :::image type="content" source="../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png" alt-text="复制并粘贴表中的值。":::

1. Select the **Save Changes** (check mark) control. 

     :::image type="content" source="../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png" alt-text="选择&quot;保存更改&quot;控件。":::

1. 通过从表的第二行选择值添加其他 SRV 记录。
    
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 

### <a name="add-the-two-required-cname-records"></a>添加两个必需的 CNAME 记录 
  
1. 在"**主机记录"** 部分，选择"**添加新记录"。**
    
     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="选择&quot;添加新名称&quot;。":::

1. 在"**类型"** 下拉列表中，选择 **"CNAME"。**
    
    > [!NOTE]
    > 选择 **"添加新** 记录"时，将自动显示"类型 **"下拉列表**。 

     :::image type="content" source="../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png" alt-text="选择&quot;CNAME&quot;。":::

1. 在新记录的空框中，键入或复制并粘贴表中第一行的值。
    
    |**类型**|**主机**|**值**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |自动  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |自动  <br/> |

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="复制并粘贴表中的 CNAME 值。":::

1. Select the **Save Changes** (check mark) control. 

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="选择&quot;保存更改&quot;控件。":::

1. 通过从表的第二行选择值添加其他 CNAME 记录。
    
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高级选项：Intune 和移动设备管理 for Microsoft 365

此服务可帮助你保护并远程管理连接到域的移动设备。 移动设备管理需要两条 CNAME 记录，以便用户可以将设备注册到服务。

### <a name="add-the-two-required-cname-records"></a>添加两个必需的 CNAME 记录

1. To get started， go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to sign in.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="登录到 Namecheap。":::

1. 在登录页面上的"帐户 **"下**， **从** 下拉列表中选择"域列表"。 

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="选择&quot;域列表&quot;。":::

1. 在"**域列表"** 页上，选择要编辑的域，然后选择"管理 **"。**
    
     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="选择&quot;管理&quot;。":::

1. 选择 **"高级 DNS"。**

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="从下拉列表中选择&quot;管理 DNS 记录&quot;。":::

1. 在"**主机记录"** 部分，选择"**添加新记录"。**
    
     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="选择&quot;添加新记录&quot;。":::

1. 在"**类型"** 下拉列表中，选择 **"CNAME 记录"。**
    
    > [!NOTE]
    > 选择 **"添加新** 记录"时，将自动显示"类型 **"下拉列表**。 
  
     :::image type="content" source="../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png" alt-text="选择&quot;CNAME 记录&quot;。":::

1. 在新记录的空框中，键入或复制并粘贴表中第一行的值。
    
    |**类型**|**主机**|**值**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **此值必须以句点 (.) 结尾。** <br/> |自动  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |自动  <br/> |
       
     :::image type="content" source="../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png" alt-text="复制并粘贴表中的值。":::

1. 选择" **保存更改"** 控件。 

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="选择&quot;保存更改&quot;控件。":::

1. 通过从表的第二行选择值添加其他 CNAME 记录。
    
> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 


