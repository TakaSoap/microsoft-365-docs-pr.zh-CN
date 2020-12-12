---
title: 在 eNomCentral 为 Microsoft 创建 DNS 记录
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: 了解如何在 eNomCentral for Microsoft 上验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: e6e05b987a893da582ea7fb062eafe421861b970
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658107"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a>在 eNomCentral 为 Microsoft 创建 DNS 记录

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。

如果 eNomCentral 是 DNS 托管提供商，请按照本文中的步骤验证域并设置电子邮件、Skype for Business Online 等的 DNS 记录。

在 eNomCentral 添加这些记录后，域将设置为使用 Microsoft 服务。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证
<a name="BKMK_verify"> </a>

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。

> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。

请按下列步骤操作或[观看视频（从 0:46 开始）](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)。

1. 若要开始，请使用[此链接](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)转到 eNom Central 上您的域页面。系统将会提示您登录。

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. 在我的 **域** 下，选择要编辑的域的名称。

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. 在" **管理域**"下拉列表中，选择" **主机记录**"。

   ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)

4. 在新记录的框中，键入或复制并粘贴下表中的值。

   从 **下拉列表中选择** "记录类型"值。

   |主机名|Record Type|地址|
   |---|---|---|
   |@|TXT|MS=ms *XXXXXXXX*  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|

   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)

5. 选择 **"保存"。**

   ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)

6. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。

在域注册机构网站添加了记录后，你将返回到 Microsoft 365 并请求 Microsoft 365 查找记录。

Microsof 找到正确的 TXT 记录表明域已通过验证。

1. 在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

2. 在“**域**”页面上，选择要验证的域。

3. 在“**设置**”页面上，选择“**开始设置**”。

4. 在“**验证域**”页面上，选择“**验证**”。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft
<a name="BKMK_add_MX"> </a>

按照下面的步骤操作或 [观看视频， (3：40 ](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)开始) 。

1. 若要开始，请使用[此链接](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)转到 eNom Central 上您的域页面。系统将会提示您登录。

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. 在我的 **域** 下，选择要编辑的域的名称。

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. 在"**管理域**"下拉列表中，选择"**电子邮件设置"。**

   ![eNom-BP-Configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)

4. 在"**服务选择**"下拉列表中，选择"用户 (**MX) 。**

   ![eNom-BP-Configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)

5. In the boxes for the new record, type or copy and paste the values from the following table.

   |主机名|地址|Pref|
   |---|---|---|
   |@| *\<domain-key\>*  .mail.protection.outlook.com。  <br/> **此值必须以句点 (.) 结尾。** <br/> **注意：** 从  *\<domain-key\>*  Microsoft 帐户获取你的帐户。 如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)|10   <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)|

   ![eNom-BP-Configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)

6. 选择 **"保存"。**

   ![eNom-BP-Configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)

7. 如果存在任何其他现有 MX 记录，请选中这些记录的复选框以选中它们。

   ![eNom-BP-Configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)

8. 选中 **"删除已选中"。**

   ![eNom-BP-Configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的 CNAME 记录
<a name="BKMK_add_CNAME"> </a>

按照下面的步骤操作或 [观看视频， (4：24 开始 ](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)) 。

1. 若要开始，请使用[此链接](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)转到 eNom Central 上您的域页面。系统将会提示您登录。

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. 在我的 **域** 下，选择要编辑的域的名称。

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. 在" **管理域**"下拉列表中，选择" **主机记录**"。

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. 选择 **新行**。

   ![eNom-BP-Configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)

5. 在六条新记录的框中，键入或复制并粘贴以下值。

   从 **下拉列表中选择** "记录类型"值。

   |主机名|Record Type|地址|
   |---|---|---|
   |自动发现|CNAME（别名）|autodiscover.outlook.com.  <br/> **此值必须以句点 (.) 结尾。**|
   |sip|CNAME（别名）|sipdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。**|
   |lyncdiscover|CNAME（别名）|webdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。**|
   |enterpriseregistration|CNAME（别名）|enterpriseregistration.windows.net.  <br/> **此值必须以句点 (.) 结尾。**|
   |enterpriseenrollment|CNAME（别名）|enterpriseenrollment-s.manage.microsoft.com.  <br/> **此值必须以句点 (.) 结尾。**|

   ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)

6. 选择 **"保存"。**

   ![eNom-BP-Configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 相反，将所需的 Microsoft 值添加到当前记录，以便具有一个  *包含这*  两组值的 SPF 记录。

按照以下步骤操作，或观看视频 ([5：12 开始 ](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)) 。

1. 若要开始，请使用[此链接](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)转到 eNom Central 上您的域页面。系统将会提示您登录。

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. 在我的 **域** 下，选择要编辑的域的名称。

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. 在" **管理域**"下拉列表中，选择" **主机记录**"。

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. 在新记录的框中，键入或复制并粘贴下表中的值。

   从 **下拉列表中选择** "记录类型"值。

   |主机名|Record Type|地址|
   |---|---|---|
   |@|TXT|v=spf1 include:spf.protection.outlook.com -all  <br/>**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。|

   ![eNom-BP-Configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)

5. 选择 **"保存"。**

   ![eNom-BP-Configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)

## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的两条 SRV 记录
<a name="BKMK_add_SRV"> </a>

按照下面的步骤操作或 [观看视频， (5：50 ](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d)开始) 。

1. 若要开始，请使用[此链接](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)转到 eNom Central 上您的域页面。系统将会提示您登录。

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. 在我的 **域** 下，选择要编辑的域的名称。

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. 在" **管理域**"下拉列表中，选择" **主机记录**"。

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. 在新建行 **的右侧，** 选择 **添加 SRV 或 SPF 记录**。

   ![eNom-BP-Configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)

5. 在两条新记录的框中，键入或复制并粘贴下表中的值。

   |服务|协议|Priority|粗细|端口|目标 (主机名) |
   |---|---|---|---|---|---|
   |_sip|_tls|100|1 |443|sipdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。**|
   |_sipfederationtls|_tcp|100|1 |5061|sipfed.online.lync.com。  <br/> **此值必须以句点 (.) 结尾。**|

   ![eNom-BP-Configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)

6. 选择 **"保存"**

   ![eNom-BP-Configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。
