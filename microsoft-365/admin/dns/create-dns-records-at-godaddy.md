---
title: 在 GoDaddy 处为 Office 365 创建 DNS 记录
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: 了解如何在 GoDaddy for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.custom: okr_smb
ms.openlocfilehash: e037e989a51a95b16077d1edfcdff4b341ee3b80
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349233"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a>在 GoDaddy 处为 Office 365 创建 DNS 记录

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。

如果 GoDaddy 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。

在 GoDaddy 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。

若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。

> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。

按照下面的步骤操作。

1. 若要开始，请使用[此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 上的 "域" 页面。 You'll be prompted to log in.

    ![GoDaddy-配置-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. 在 "**域**" 下，选择要编辑的域下的 "DNS"。

    ![GoDaddy-配置-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. 选择“**添加**”。

    ![GoDaddy-配置-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Choose **TXT (Text)** from the drop-down list. 在新记录的框中，键入或复制并粘贴下表中的值。

    |**记录类型** |**Host**|**TXT 值**|**TTL** |
    |:-----|:-----|:-----|:-----|
    |TXT（文本）|@|MS=ms *XXXXXXXX*<br>**注意**：这是一个示例。 在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|1 小时  <br>（从下拉列表中选择一个值。）|

      ![GoDaddy-验证-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. 选择“**保存**”。

6. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。

现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。

Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。
  
1. 在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。

    
2. 在“**域**”页面上，选择要验证的域。 
    
    
  
3. 在“**设置**”页面上，选择“**开始设置**”。



4. 在“**验证域**”页面上，选择“**验证**”。



> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365
<a name="BKMK_add_MX"> </a>

按照下面的步骤操作。

1. 若要开始，请使用[此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 上的 "域" 页面。 You'll be prompted to log in.

    ![GoDaddy-配置-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. 在 "**域**" 下，选择要编辑的域下的 "DNS"。

    ![GoDaddy-配置-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. 选择“**添加**”。

    ![GoDaddy-配置-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. 从下拉列表中选择 " **MX （邮件交换器）** "。

    ![GoDaddy-配置-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. 在新记录的框中，键入或复制并粘贴下表中的值。

    （从下拉列表中选择 " **TTL** " 值。）

    |**记录类型**|**主机**|**指向**|**优先级**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX （邮件交换器）  <br/> |@  <br/> | *\<域密钥\>*  .mail.protection.outlook.com  <br/> **注意：** 从 Office 365 帐户中获取你* \<的域密钥\> * 。           如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |1 小时  <br/> |

6. 选择“**保存**”。

## <a name="add-the-cname-records-that-are-required-for-office-365"></a>添加 Office 365 所需的 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

按照下面的步骤操作。

1. 若要开始，请使用[此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 上的 "域" 页面。 You'll be prompted to log in.

    ![GoDaddy-配置-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. 在 "**域**" 下，选择要编辑的域下的 "DNS"。

    ![GoDaddy-配置-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. 选择“**添加**”。

    ![GoDaddy-配置-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. 从下拉列表中选择 " **CNAME （别名）** "。

    ![GoDaddy-配置-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. 创建第一个 CNAME 记录。

    在新记录的框中，键入或复制并粘贴下表中第一行的值。

    （从下拉列表中选择 " **TTL** " 值。）

    |**记录类型**|**主机**|**指向**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME (Alias)  <br/> |自动发现  <br/> |autodiscover.outlook.com  <br/> |1 小时  <br/> |
    |CNAME（别名）  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 小时  <br/> |
    |CNAME（别名）  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 小时  <br/> |
    |CNAME（别名）  <br/> |enterpriseregistration  <br/> |EnterpriseRegistration.windows.net  <br/> |1 小时  <br/> |
    |CNAME（别名）  <br/> |EnterpriseEnrollment  <br/> |EnterpriseEnrollment.manage.microsoft.com  <br/> |1 小时  <br/> |



6. 重复这些步骤以添加下一条 CNAME 记录，直到您已创建所有六个 CNAME 记录。

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 If you already have an SPF record for your domain, don't create a new one for Office 365. 可以将所需的 Office 365 添加到当前记录，这样就拥有包含两组值的*单个*SPF 记录。

按照下面的步骤操作。

1. 若要开始，请使用[此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 上的 "域" 页面。 You'll be prompted to log in.

    ![GoDaddy-配置-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. 在 "**域**" 下，选择要编辑的域下的 "DNS"。

    ![GoDaddy-配置-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. 选择“**添加**”。

    ![GoDaddy-配置-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Choose **TXT (Text)** from the drop-down list.

    ![GoDaddy-配置-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. In the boxes for the new record, type or copy and paste the following values.

    （从下拉列表中选择 " **TTL** " 值。）

    |**记录类型**|**Host**|**TXT 值**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT（文本）  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。           |1 小时  <br/> |

    ![GoDaddy-配置-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. 选择“**保存**”。


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>添加 Office 365 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

按照下面的步骤操作。

1. 若要开始，请使用[此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 上的 "域" 页面。 You'll be prompted to log in.

    ![GoDaddy-配置-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. 在 "**域**" 下，选择要编辑的域下的 "DNS"。

    ![GoDaddy-配置-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. 选择“**添加**”。

    ![GoDaddy-配置-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. 从下拉列表中选择 " **SRV （服务）** "。

    ![GoDaddy-配置-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. 创建第一个 SRV 记录。

    在新记录的框中，键入或复制并粘贴下表中第一行的值。

    （从下拉列表中选择 "**记录类型**" 和 " **TTL** " 值。）

    |**记录类型**|**名称**|**目标**|**协议**|**服务**|**优先级**|**权重**|**端口**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV（服务）  <br/> |@  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 小时  <br/> |
    |SRV（服务）  <br/> |@  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 小时  <br/> |

    ![GoDaddy-配置-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. 重复**步骤 5**以创建另一条 SRV 记录。

7. 选择“**保存**”。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。
