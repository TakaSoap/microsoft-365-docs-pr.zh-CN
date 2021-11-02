---
title: 连接 GoDaddy 将 DNS 记录Microsoft 365
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: 了解如何在 GoDaddy for Microsoft 中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: ac71bbe1c57e1471e1ff343df75f034cc15c5901
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60647780"
---
# <a name="connect-your-dns-records-at-godaddy-to-microsoft-365"></a>连接 GoDaddy 将 DNS 记录Microsoft 365

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。

如果 GoDaddy 是 DNS 托管提供商，请按照本文中的步骤验证域，并设置电子邮件、Skype for Business Online 等的 DNS 记录。

## <a name="before-you-begin"></a>准备工作

有两个选项可以设置域的 DNS 记录：

- [**使用域连接**](#use-domain-connect-to-verify-and-set-up-your-domain)如果您尚未设置其他电子邮件服务提供商的域，请使用 Domain 连接 步骤自动验证和设置要与 Microsoft 365 一Microsoft 365。

   或

- [**使用手动步骤**](#create-dns-records-with-manual-setup) 使用下面的手动步骤验证域，然后选择何时以及向域注册机构添加哪些记录。 这样，您便能够设置新的 MX (邮件) 记录，例如，在方便时。

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>使用域连接验证和设置域

按照以下步骤自动验证和设置 GoDaddy 域，并Microsoft 365：

1. 在"Microsoft 365 管理中心"中 **，设置"** 域  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a>"，然后选择要设置的域。

1. 选择三个点 (更多) >选择"开始 **设置"。**

   :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="选择&quot;开始设置&quot;。":::

1. On the How do you want to connect your domain？页面，选择"**继续"。**

1. 在"添加 DNS 记录"页上，选择"**添加 DNS 记录"。**

1. 在 GoDaddy 登录页面上，登录到你的帐户， **然后选择授权**。

    这将完成域的域Microsoft 365。

## <a name="create-dns-records-with-manual-setup"></a>使用手动设置创建 DNS 记录

在 GoDaddy 添加这些记录后，域将设置为使用Microsoft 服务。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

### <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。

> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。

1. To get started， go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).

   如果系统提示您登录，请使用登录凭据，选择右上角的登录名，然后选择"**我的产品"。**

1. 在 **"域**"下，选择要验证的域旁边的三个点，然后选择"管理 **DNS"。**

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="从下拉列表中选择&quot;管理 DNS&quot;。":::

1. 在 **"****记录"下**， ("添加""您可能必须向下滚动) "。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="选择&quot;添加&quot;。":::

1. 从 **下拉列表中选择"TXT"。**

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="从&quot;类型&quot;下拉列表中选择&quot;TXT&quot;。":::

1. 在新记录的框中，键入或复制并粘贴表中的值。

   |**类型** |**Host**|**TXT 值**|**TTL** |
   |:-----|:-----|:-----|:-----|
   |TXT |@|MS=ms *XXXXXXXX*<br>**注意**：这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|1 小时  <br>|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-TXT-values.png" alt-text="填写 TXT 记录的表中的值。":::

1. 选择“**保存**”。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-TXTSave.png" alt-text="选择&quot;保存&quot;。":::

   请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。

在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。 Microsof 找到正确的 TXT 记录表明域已通过验证。
  
若要验证记录是否Microsoft 365：
  
1. 在管理中心中，转到 **"设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**域"。**</a>

1. On the Domains page， select the domain that you're verifying， and select **Start setup**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="选择&quot;开始设置&quot;。":::

1. 选择 **继续**。
  
1. 在“**验证域**”页面上，选择“**验证**”。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft

1. To get started， go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).

   如果系统提示您登录，请使用登录凭据，选择右上角的登录名，然后选择"**我的产品"。**

2. 在 **"域**"下，选择要验证的域旁边的三个点，然后选择"管理 **DNS"。**

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="从下拉列表中选择&quot;管理 DNS&quot;。":::

3. 在"**记录"** 下，选择 **"添加"。**

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="选择&quot;添加&quot;。":::

4. 从 **下拉列表中选择"MX"。**

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="从&quot;类型&quot;下拉列表中选择&quot;MX&quot;。":::

5. 在新记录的框中，键入或复制并粘贴下表中的值。

     (从下拉列表 **中选择 Type** 和 **TTL** 值。) 

    |**类型**|**主机**|**指向**|**优先级**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **注意：** 从  *\<domain-key\>*  Microsoft 帐户获取你的帐户。           如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml) <br/> |1 小时  <br/> |

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="填写 MX 记录的表中的值。":::

6. 选择“**保存**”。

### <a name="add-the-cname-record-required-for-microsoft"></a>添加 Microsoft 所需的 CNAME 记录

1. To get started， go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).

   如果系统提示您登录，请使用登录凭据，选择右上角的登录名，然后选择"**我的产品"。**

2. 在 **"域**"下，选择要验证的域旁边的三个点，然后选择"管理 **DNS"。**

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="从下拉列表中选择&quot;管理 DNS&quot;。":::

3. 在"**记录"** 下，选择 **"添加"。**

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="选择&quot;添加&quot;。":::

4. 从 **下拉列表中选择"CNAME"。**

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="从&quot;类型&quot;下拉列表中选择&quot;CNAME&quot;。":::

5. 创建 CNAME 记录。

    在新记录的框中，键入或复制并粘贴下表中第一行的值。

     (从下拉列表中选择 **TTL** 值。) 

    |**类型**|**主机**|**指向**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |自动发现 <br/> |autodiscover.outlook.com  <br/> |1 小时  <br/> |

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-CNAME-values.png" alt-text="填写 CNAME 记录的表中的值。":::

6. 选择“**保存**”。

### <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 相反，将所需的 Microsoft 值添加到当前记录，以便你有一个  *包含这*  两组值的 SPF 记录。

1. To get started， go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).

   如果系统提示您登录，请使用登录凭据，选择右上角的登录名，然后选择"**我的产品"。**

2. 在 **"域**"下，选择要验证的域旁边的三个点，然后选择"管理 **DNS"。**

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="从下拉列表中选择&quot;管理 DNS&quot;。":::

3. 在"**记录"** 下，选择 **"添加"。**

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="选择&quot;添加&quot;。":::

4. 从 **下拉列表中选择"TXT"。**

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="从&quot;类型&quot;下拉列表中选择&quot;TXT&quot;。":::

5. In the boxes for the new record, type or copy and paste the following values.

     (从下拉列表中选择 **TTL** 值。) 

    |**类型**|**Host**|**TXT 值**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。 |1 小时  <br/> |

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-TXT-values.png" alt-text="填写 TXT 记录的表中的值。":::

6. 选择“**保存**”。

## <a name="advanced-option-skype-for-business"></a>高级选项：Skype for Business

只有当您的组织将 Skype for Business用于聊天、电话会议和视频呼叫等联机通信服务时，以及使用 Microsoft Teams。 Skype 4 条记录：2 条 SRV 记录用于用户到用户的通信，2 条 CNAME 记录用于登录和将用户连接到服务。

### <a name="add-the-two-required-srv-records"></a>添加两条必需的 SRV 记录

1. To get started， go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).

   如果系统提示您登录，请使用登录凭据，选择右上角的登录名，然后选择"**我的产品"。**

1. 在 **"域**"下，选择要验证的域旁边的三个点，然后选择"管理 **DNS"。**

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="从下拉列表中选择&quot;管理 DNS&quot;。":::

1. 在"**记录"** 下，选择 **"添加"。**

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="选择&quot;添加&quot;。":::

1. 从 **下拉列表中选择 SRV。**

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="从类型下拉列表中选择 SRV。":::

1. 创建第一条 SRV 记录。

    在新记录的框中，键入或复制并粘贴下表中第一行的值。

     (从下拉列表 **中选择 Type** 和 **TTL** 值。) 

    |**类型**|**服务**|**协议**| **名称** | **目标**|**优先级**|**权重**|**端口**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV   <br/> |_sip  <br/> |_tls  <br/> |@  <br/> |sipdir.online.lync.com  <br/> |100 <br/> | 1  <br/> |443  <br/> |1 Hour  <br/> |
    |SRV  <br/> |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> | sipfed.online.lync.com  <br/> | 100  <br/> |1  <br/> |5061  <br/> |1 Hour  <br/> |

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-SRV-values.png" alt-text="填写 SRV 记录的表中的值。":::

1. 选择“**保存**”。

1. 通过从表的第二行选择值添加其他 SRV 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

### <a name="add-the-two-required-cname-records"></a>添加两个必需的 CNAME 记录
  
1. To get started， go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).

   如果系统提示您登录，请使用登录凭据，选择右上角的登录名，然后选择"**我的产品"。**

2. 在 **"域**"下，选择要验证的域旁边的三个点，然后选择"管理 **DNS"。**

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="从下拉列表中选择&quot;管理 DNS&quot;。":::

1. 在"**记录"** 下，选择 **"添加"。**

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="选择&quot;添加&quot;。":::

1. 从 **下拉列表中选择"CNAME"。**

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="从&quot;类型&quot;下拉列表中选择&quot;CNAME&quot;。":::

1. 在新记录的空框中，键入或复制并粘贴下表中第一行的值。

    |**类型**|**主机**|**指向**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |1 小时  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |1 Hour  <br/> |

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-CNAME-values.png" alt-text="填写 CNAME 记录的表中的值。":::
  
1. 选择“**保存**”。
  
1. 通过从表的第二行选择值添加其他 CNAME 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高级选项：Intune 和移动设备管理 for Microsoft 365

此服务可帮助你保护并远程管理连接到域的移动设备。 移动设备管理需要 2 条 CNAME 记录，以便用户可以将设备注册到服务。

### <a name="add-the-two-required-cname-records"></a>添加两个必需的 CNAME 记录

1. To get started， go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled).

   如果系统提示您登录，请使用登录凭据，选择右上角的登录名，然后选择"**我的产品"。**

1. 在 **"域**"下，选择要验证的域旁边的三个点，然后选择"管理 **DNS"。**

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="从下拉列表中选择&quot;管理 DNS&quot;。":::

1. 在"**记录"** 下，选择 **"添加"。**

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="选择&quot;添加&quot;。":::

1. 从 **下拉列表中选择"CNAME"。**

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="从&quot;类型&quot;下拉列表中选择&quot;CNAME&quot;。":::

1. 在新记录的空框中，键入或复制并粘贴下表中第一行的值。

    |**类型**|**主机**|**指向**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **此值必须以句点 (.) 结尾。** <br/> |1 小时  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **此值必须以句点 (.) 结尾。** <br/> |1 Hour  <br/> |

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-CNAME-values.png" alt-text="填写 CNAME 记录的表中的值。":::
  
1. 选择“**保存**”。
  
1. 通过从表的第二行选择值添加其他 CNAME 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。
