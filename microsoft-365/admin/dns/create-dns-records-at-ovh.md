---
title: 连接 OVH 中的 DNS 记录Microsoft 365
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: 了解如何在适用于 Microsoft 的 OVH 中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: 3b3174860a65d13d68b2d5f7773f927dd706f1a0
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780398"
---
# <a name="connect-your-dns-records-at-ovh-to-microsoft-365"></a>连接 OVH 中的 DNS 记录Microsoft 365

如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.yml)。

如果 OVH 是 DNS 托管提供商，请按照本文中的步骤验证域，并为电子邮件、Skype for Business Online 等设置 DNS 记录。

在 OVH 中添加这些记录后，域将设置为使用Microsoft 服务。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="add-a-txt-record-for-verification"></a>添加 TXT 记录进行验证

在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。

> [!NOTE]
> 此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。

1. 若要开始，请使用 [此链接](https://www.ovh.com/manager/)转到 OVH 中的域页。 You'll be prompted to log in.

    ![OVH 登录名。](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)

1. 在仪表板登陆页上，在 **“查看我的所有活动**”下，选择要编辑的域的名称。

1. 选择 **DNS 区域**。

    ![OVH 选择 DNS 区域。](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)

1. 选择 **“添加条目**”。

    ![OVH 添加条目。](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)

1. 选择 **TXT**

    ![OVH 选择 TXT 条目。](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)

1. 在新记录的框中，键入或复制并粘贴下表中的值。 若要分配 TTL 值，请从下拉列表中选择 **“自定义** ”，然后在文本框中键入该值。

   |记录类型|子域|TTL|值|
   |---|---|---|---|
   |TXT|（保留为空白）|3600 (秒) |MS=msxxxxxxxx  <br/> **注意：** 这是一个示例。 在这里使用表中的特定“**目标地址或指向的地址**”值。  [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|

1. 选择 **下一步**。

1. 选择“**确认**”。

    ![OVH 确认 TXT 进行验证。](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)

1. 请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。

在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。 Microsof 找到正确的 TXT 记录表明域已通过验证。

若要验证Microsoft 365中的记录，

1. 在管理中心，转到 **设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**域**</a>。

1. 在“域”页上，选择要验证的域，然后选择 **“开始设置**”。

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="选择“开始”设置。":::

1. 选择 **继续**。

1. 在“**验证域**”页面上，选择“**验证**”。

> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft

1. 若要开始，请使用 [此链接](https://www.ovh.com/manager/)转到 OVH 中的域页。 You'll be prompted to log in.

    ![OVH 登录名。](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)

1. 在仪表板登陆页上，在 **“查看我的所有活动**”下，选择要编辑的域的名称。

1. 选择 **DNS 区域**。

    ![OVH 选择 DNS 区域。](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)

1. 选择 **“添加条目**”。

    ![OVH 添加条目。](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)

1. 选择 **MX**。

    ![OVH MX 记录类型。](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)

1. 在新记录的框中，键入或复制并粘贴下表中的值。 若要分配 TTL 值，请从下拉列表中选择 **“自定义** ”，然后在文本框中键入该值。

    > [!NOTE]
    > 默认情况下，OVH 对目标使用相对表示法，这会将域名添加到目标记录的末尾。 若要改用绝对表示法，请将一个点添加到目标记录，如下表所示。

   |子域|TTL|优先级|Target|
   |---|---|---|---|
   |（保留为空白）|3600 (秒) |0  <br/> 有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml)|\<domain-key\>.mail.protection.outlook.com.  <br/> **注意：** 从 Microsoft 帐户获取你 *\<domain-key\>* 。 [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)|

    ![邮件的 OVH MX 记录。](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)

1. 选择 **下一步**。

    ![OVH MX 记录选择“下一步”。](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)

1. 选择“**确认**”。

    ![OVH MX 记录选择“确认”。](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)

1. 删除 **DNS 区域** 页上列表中的任何其他 MX 记录。 选择每个记录，并在 **“操作”** 列中选择“垃圾桶 **删除”** 图标。

    ![OVH 删除 MX 记录。](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)

1. 选择“**确认**”。

## <a name="add-the-cname-record-required-for-microsoft"></a>添加 Microsoft 所需的 CNAME 记录

1. 若要开始，请使用 [此链接](https://www.ovh.com/manager/)转到 OVH 中的域页。 You'll be prompted to log in.

    ![OVH 登录名。](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)

1. 在仪表板登陆页上，在 **“查看我的所有活动**”下，选择要编辑的域的名称。

1. 选择 **DNS 区域**。

    ![OVH 选择 DNS 区域。](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)

1. 选择 **“添加条目**”。

    ![OVH 添加条目。](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)

1. 选择 **CNAME**。

    ![OVH 添加 CNAME 记录类型。](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)

1. 在新记录的框中，键入或复制并粘贴下表中第一行的值。 若要分配 TTL 值，请从下拉列表中选择 **“自定义** ”，然后在文本框中键入该值。

   |子域|TTL|Target|
   |---|---|---|
   |自动发现|3600 (秒) |autodiscover.outlook.com.|

    ![OVH CNAME 记录。](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)

1. 选择 **下一步**。

    ![OVH 添加 CNAME 值并选择“下一步”。](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)

1. 选择“**确认**”。

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件

> [!IMPORTANT]
> 一个域所拥有的 SPF 的 TXT 记录不能超过一个。 如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。 如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。 而是将所需的 Microsoft 值添加到当前记录，以便具有包含这两组值的  *单*  个 SPF 记录。

1. 若要开始，请使用 [此链接](https://www.ovh.com/manager/)转到 OVH 中的域页。 You'll be prompted to log in.

    ![OVH 登录名。](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)

1. 在仪表板登陆页上，在 **“查看我的所有活动**”下，选择要编辑的域的名称。

1. 选择 **DNS 区域**。

    ![OVH 选择 DNS 区域。](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)

1. 选择 **“添加条目**”。

    ![OVH 添加条目。](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)

1. 选择 **TXT**。

1. In the boxes for the new record, type or copy and paste the following values. 若要分配 TTL 值，请从下拉列表中选择 **“自定义** ”，然后在文本框中键入该值。

   |子域|TTL|值|
   |---|---|---|
   |（保留为空白）|3600 (秒) |v=spf1 include：spf.protection.outlook.com -all <br/**Note：** 我们建议复制和粘贴此条目，以便所有间距保持正确。|

    ![OVH 为 SPF 添加 TXT 记录。](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)

1. 选择 **下一步**。

    ![为 SPF 添加 TXT 记录并选择“下一步”。](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)

1. 选择“**确认**”。

    ![OVH 为 SPF 和 Confirm 添加 TXT 记录。](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)

## <a name="advanced-option-skype-for-business"></a>高级选项：Skype for Business

仅当组织对联机通信服务（例如聊天、电话会议和视频呼叫）使用Skype for Business时，除了Microsoft Teams，才选择此选项。 Skype需要 4 条记录：2 条用于用户到用户通信的 SRV 记录，以及 2 条用于登录和将用户连接到服务的 CNAME 记录。

### <a name="add-the-two-required-srv-records"></a>添加两个必需的 SRV 记录

1. 若要开始，请使用 [此链接](https://www.ovh.com/manager/)转到 OVH 中的域页。 You'll be prompted to log in.

    ![OVH 登录名。](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)

1. 在仪表板登陆页上，在 **“查看我的所有活动**”下，选择要编辑的域的名称。

1. 选择 **DNS 区域**。

    ![OVH 选择 DNS 区域。](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)

1. 选择 **“添加条目**”。

    ![OVH 添加条目。](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)

1. 选择 **SRV**。

1. In the boxes for the new record, type or copy and paste the following values. 若要分配 TTL 值，请从下拉列表中选择 **“自定义** ”，然后在文本框中键入该值。

   |子域|TTL (Seconds)|优先级|粗细|端口|Target|
   |---|---|---|---|---|---|
   |_sip._tls|3600 (s.) |100|1|443|sipdir.online.lync.com. **此值必须以句点 (.) 结尾**><br> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。|
   |_sipfederationtls._tcp|3600 (s.) |100|1|5061|sipfed.online.lync.com。 **此值必须以句点 (.) 结尾。**<br> **注意：** 建议复制粘贴此条目，以保证正确保留所有空格。|

1. 若要添加其他 SRV 记录，请选择 **“添加另** 一条记录”，使用表中下一行中的值创建记录，然后选择 **“创建记录**”。

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果在添加 DNS 记录后遇到邮件流问题或其他问题，请参阅[查找在添加域或 DNS 记录后遇到的问题并进行修复](../get-help-with-domains/find-and-fix-issues.md)。

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>为Skype for Business添加两条所需的 CNAME 记录

1. 若要开始，请使用 [此链接](https://www.ovh.com/manager/)转到 OVH 中的域页。 You'll be prompted to log in.

    ![OVH 登录名。](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)

1. 在仪表板登陆页上，在 **“查看我的所有活动**”下，选择要编辑的域的名称。

1. 选择 **DNS 区域**。

    ![OVH 选择 DNS 区域。](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)

1. 选择 **“添加条目**”。

    ![OVH 添加条目。](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)

1. 选择 **CNAME**。

    ![OVH 添加 CNAME 记录类型。](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)

1. 在新记录的框中，键入或复制并粘贴下表中第一行的值。 若要分配 TTL 值，请从下拉列表中选择 **“自定义** ”，然后在文本框中键入该值。

   |子域|TTL|Target|
   |---|---|---|
   |sip|3600 (s.) |sipdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。**|
   |lyncdiscover|3600 (s.) |webdir.online.lync.com.  <br/> **此值必须以句点 (.) 结尾。**|

1. 选择 **下一步**。

    ![OVH 添加 CNAME 值并选择“下一步”。](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)

1. 选择“**确认**”。

1. 添加其他 CNAME 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>高级选项：适用于Microsoft 365的Intune和移动设备管理

此服务可帮助保护和远程管理连接到域的移动设备。 移动设备管理需要两条 CNAME 记录，以便用户可以将设备注册到服务。

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>添加移动设备管理所需的两条 CNAME 记录

1. 若要开始，请使用 [此链接](https://www.ovh.com/manager/)转到 OVH 中的域页。 You'll be prompted to log in.

    ![OVH 登录名。](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)

1. 在仪表板登陆页上，在 **“查看我的所有活动**”下，选择要编辑的域的名称。

1. 选择 **DNS 区域**。

    ![OVH 选择 DNS 区域。](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)

1. 选择 **“添加条目**”。

    ![OVH 添加条目。](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)

1. 选择 **CNAME**。

    ![OVH 添加 CNAME 记录类型。](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)

1. 在新记录的框中，键入或复制并粘贴下表中第一行的值。 若要分配 TTL 值，请从下拉列表中选择 **“自定义** ”，然后在文本框中键入该值。

   |子域|TTL|Target|
   |---|---|---|
   |enterpriseregistration  <br/>|3600 (s.) |enterpriseregistration.windows.net.  <br/> **此值必须以句点 (.) 结尾。**|
   |enterpriseenrollment|3600 (s.) |enterpriseenrollment-s.manage.microsoft.com.  <br/> **此值必须以句点 (.) 结尾。**|

1. 选择 **下一步**。

    ![OVH 添加 CNAME 值并选择“下一步”。](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)

1. 选择“**确认**”。

1. 添加其他 CNAME 记录。

> [!NOTE]
> DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。