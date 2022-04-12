---
title: 在 GoDaddy 中连接 DNS 记录以Microsoft 365
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
ms.openlocfilehash: 6cf110b55c76ce6c857f13dcd5b0075b309b654f
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780338"
---
# <a name="connect-your-dns-records-at-godaddy-to-microsoft-365"></a>在 GoDaddy 中连接 DNS 记录以Microsoft 365

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。

如果 GoDaddy 是 DNS 托管提供商，请按照本文中的步骤验证域，并为电子邮件、Skype for Business Online 等设置 DNS 记录。

## <a name="before-you-begin"></a>准备工作

有两个选项可用于设置域的 DNS 记录：

- [**使用域连接**](#use-domain-connect-to-verify-and-set-up-your-domain)如果尚未使用其他电子邮件服务提供商设置域，请使用域连接步骤自动验证和设置要与Microsoft 365配合使用的新域。

   或

- [**使用手动步骤**](#create-dns-records-with-manual-setup) 使用以下手动步骤验证域，并选择何时以及向域注册机构添加哪些记录。 这样就可以在方便的时候设置新的 MX (邮件) 记录。

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>使用域连接验证和设置域

按照以下步骤使用Microsoft 365自动验证和设置 GoDaddy 域：

1. 在Microsoft 365 管理中心中，选择 **设置** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**域**</a>，然后选择要设置的域。

1. 选择三个点 (更多操作) >选择 **“开始”设置**。

   :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="选择“开始”设置。":::

1. 在“如何连接域”上？页面，选择 **“继续**”。

1. 在“添加 DNS 记录”页上，选择 **“添加 DNS 记录**”。

1. 在 GoDaddy 登录页上，登录到帐户，然后选择 **“授权**”。

   这会完成Microsoft 365的域设置。

## <a name="create-dns-records-with-manual-setup"></a>使用手动设置创建 DNS 记录

在 GoDaddy 中添加这些记录后，域将设置为使用Microsoft 服务。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

### <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。

> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。

1. 若要开始，请使用 [此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 的域页面。

   如果系统提示登录，请使用登录凭据，在右上角选择登录名，然后选择 **“我的产品**”。

1. 在 **“域”** 下，选择要验证的域旁边的三个点，然后选择 **“管理 DNS**”。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="从下拉列表中选择“管理 DNS”。":::

1. 在 **“记录**”下，选择 **“添加** (可能需要向下滚动) 。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="选择“添加”。":::

1. 从下拉列表中选择 **TXT** 。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="从“类型”下拉列表中选择 TXT。":::

1. 在新记录的框中，键入或复制并粘贴表中的值。

   |类型|主机|TXT Value|TTL|
   |---|---|---|---|
   |TXT|@|MS=ms *XXXXXXXX*<br>**注意**：这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|1 小时  <br>|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-TXT-values.png" alt-text="填写 TXT 记录表中的值。":::

1. 选择“**保存**”。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-TXTSave.png" alt-text="选择“保存”。":::

   请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。

在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。 Microsof 找到正确的 TXT 记录表明域已通过验证。
  
若要验证Microsoft 365中的记录，
  
1. 在管理中心，转到 **设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**域**</a>。

1. 在“域”页上，选择要验证的域，然后选择 **“开始设置**”。

   :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="选择“开始”设置。":::

1. 选择 **继续**。
  
1. 在“**验证域**”页面上，选择“**验证**”。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft

1. 若要开始，请使用 [此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 的域页面。

   如果系统提示登录，请使用登录凭据，在右上角选择登录名，然后选择 **“我的产品**”。

2. 在 **“域”** 下，选择要验证的域旁边的三个点，然后选择 **“管理 DNS**”。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="从下拉列表中选择“管理 DNS”。":::

3. 在 **“记录”** 下，选择 **“添加**”。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="选择“添加”。":::

4. 从下拉列表中选择 **MX** 。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="从“类型”下拉列表中选择 MX。":::

5. 在新记录的框中，键入或复制并粘贴下表中的值。

    (从下拉列表中选择 **Type** 和 **TTL** 值。) 

   |类型|主机|Points to |优先级|TTL|
   |---|---|---|---|---|
   |MX|@| *\<domain-key\>*.mail.protection.outlook.com  <br/> **注意：** 从 Microsoft 帐户获取你 *\<domain-key\>* 。 如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)|10   <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml)|1 小时|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="填写 MX 记录的表中的值。":::

6. 选择“**保存**”。

### <a name="add-the-cname-record-required-for-microsoft"></a>添加 Microsoft 所需的 CNAME 记录

1. 若要开始，请使用 [此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 的域页面。

   如果系统提示登录，请使用登录凭据，在右上角选择登录名，然后选择 **“我的产品**”。

2. 在 **“域”** 下，选择要验证的域旁边的三个点，然后选择 **“管理 DNS**”。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="从下拉列表中选择“管理 DNS”。":::

3. 在 **“记录”** 下，选择 **“添加**”。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="选择“添加”。":::

4. 从下拉列表中选择 **CNAME** 。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="从“类型”下拉列表中选择 CNAME。":::

5. 创建 CNAME 记录。

   在新记录的框中，键入或复制并粘贴下表中第一行的值。

    (从下拉列表中选择 **TTL** 值。) 

   |类型|主机|Points to |TTL|
   |---|---|---|---|
   |CNAME|自动发现|autodiscover.outlook.com|1 小时|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-CNAME-values.png" alt-text="填写 CNAME 记录表中的值。":::

6. 选择“**保存**”。

### <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 而是将所需的 Microsoft 值添加到当前记录，以便具有包含这两组值的  *单*  个 SPF 记录。

1. 若要开始，请使用 [此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 的域页面。

   如果系统提示登录，请使用登录凭据，在右上角选择登录名，然后选择 **“我的产品**”。

2. 在 **“域”** 下，选择要验证的域旁边的三个点，然后选择 **“管理 DNS**”。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="从下拉列表中选择“管理 DNS”。":::

3. 在 **“记录”** 下，选择 **“添加**”。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="选择“添加”。":::

4. 从下拉列表中选择 **TXT** 。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="从“类型”下拉列表中选择 TXT。":::

5. In the boxes for the new record, type or copy and paste the following values.

    (从下拉列表中选择 **TTL** 值。) 

   |类型|主机|TXT Value|TTL|
   |---|---|---|---|
   |TXT|@|v=spf1 include:spf.protection.outlook.com -all  <br/> **注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。|1 小时|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-TXT-values.png" alt-text="填写 TXT 记录表中的值。":::

6. 选择“**保存**”。

## <a name="advanced-option-skype-for-business"></a>高级选项：Skype for Business

仅当组织对联机通信服务（例如聊天、电话会议和视频呼叫）使用Skype for Business时，除了Microsoft Teams，才选择此选项。 Skype需要 4 条记录：2 条用于用户到用户通信的 SRV 记录，以及 2 条用于登录和将用户连接到服务的 CNAME 记录。

### <a name="add-the-two-required-srv-records"></a>添加两个必需的 SRV 记录

1. 若要开始，请使用 [此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 的域页面。

   如果系统提示登录，请使用登录凭据，在右上角选择登录名，然后选择 **“我的产品**”。

1. 在 **“域”** 下，选择要验证的域旁边的三个点，然后选择 **“管理 DNS**”。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="从下拉列表中选择“管理 DNS”。":::

1. 在 **“记录”** 下，选择 **“添加**”。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="选择“添加”。":::

1. 从下拉列表中选择 **SRV** 。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="从“类型”下拉列表中选择 SRV。":::

1. 创建第一条 SRV 记录。

   在新记录的框中，键入或复制并粘贴下表中第一行的值。

    (从下拉列表中选择 **类型** 和 **TTL** 值。) 

   |类型|服务|协议|名称|Target|优先级|粗细|端口|TTL|
   |---|---|---|---|---|---|---|---|---|
   |SRV|_sip|_tls|@|sipdir.online.lync.com|100| 1|443|1 Hour|
   |SRV|_sipfederationtls|_tcp|@| sipfed.online.lync.com| 100|1|5061|1 Hour|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-SRV-values.png" alt-text="填写 SRV 记录表中的值。":::

1. 选择“**保存**”。

1. 通过从表的第二行中选择值来添加其他 SRV 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>为Skype for Business添加两条所需的 CNAME 记录
  
1. 若要开始，请使用 [此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 的域页面。

   如果系统提示登录，请使用登录凭据，在右上角选择登录名，然后选择 **“我的产品**”。

1. 在 **“域”** 下，选择要验证的域旁边的三个点，然后选择 **“管理 DNS**”。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="从下拉列表中选择“管理 DNS”。":::

1. 在 **“记录”** 下，选择 **“添加**”。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="选择“添加”。":::

1. 从下拉列表中选择 **CNAME** 。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="从“类型”下拉列表中选择 CNAME。":::

1. 在新记录的空框中，键入或复制并粘贴下表中第一行中的值。

   |类型|主机|Points to |TTL|
   |---|---|---|---|
   |CNAME|sip|sipdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。**|1 小时|
   |CNAME|lyncdiscover|webdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。**|1 Hour|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-CNAME-values.png" alt-text="填写 CNAME 记录表中的值。":::
  
1. 选择“**保存**”。
  
1. 通过从表的第二行中选择值来添加其他 CNAME 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高级选项：适用于Microsoft 365的Intune和移动设备管理

此服务可帮助保护和远程管理连接到域的移动设备。 移动设备管理需要 2 条 CNAME 记录，以便用户可以将设备注册到服务。

### <a name="add-the-two-required-cname-records-mobile-device-management"></a>添加移动设备管理所需的两条 CNAME 记录

1. 若要开始，请使用 [此链接](https://account.godaddy.com/products/?go_redirect=disabled)转到 GoDaddy 的域页面。

   如果系统提示登录，请使用登录凭据，在右上角选择登录名，然后选择 **“我的产品**”。

1. 在 **“域”** 下，选择要验证的域旁边的三个点，然后选择 **“管理 DNS**”。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="从下拉列表中选择“管理 DNS”。":::

1. 在 **“记录”** 下，选择 **“添加**”。

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="选择“添加”。":::

1. 从下拉列表中选择 **CNAME** 。

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="从“类型”下拉列表中选择 CNAME。":::

1. 在新记录的空框中，键入或复制并粘贴下表中第一行中的值。

   |类型|主机|Points to |TTL|
   |---|---|---|---|
   |CNAME|enterpriseregistration|enterpriseregistration.windows.net.  <br/> **此值必须以句点 (.) 结尾。**|1 小时|
   |CNAME|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com.  <br/> **此值必须以句点 (.) 结尾。**|1 Hour|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-CNAME-values.png" alt-text="填写 CNAME 记录表中的值。":::
  
1. 选择“**保存**”。
  
1. 通过从表的第二行中选择值来添加其他 CNAME 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。
