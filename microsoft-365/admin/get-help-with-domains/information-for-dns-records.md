---
title: 收集创建 DNS 记录所需的信息
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 收集创建 DNS 记录所需的值/信息，以将域连接到 Microsoft 365 订阅。
ms.openlocfilehash: 81a1bd650e507e7f2c15a16cd5a048181ca6c816
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61371120"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>收集创建 DNS 记录所需的信息

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>步骤 1：查找 TXT 记录值并验证

::: moniker range="o365-worldwide"

1. In the Microsoft 365 管理中心， go to the **设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>”页面。

::: moniker-end
    
2. 在"**域**"页面上，选择你的域，然后选择"**开始设置"。** 你将返回域设置向导，查看需要添加的特定值。
    
3. 在"**域验证"** 页上，**选择"将 TXT** 记录添加到域的 DNS 记录"，然后选择"继续 **"。**
    
4. 复制显示的 **TXT** 值。 它如下所示 **：MS=msXXXXXXXX**。 
    
5. 转到 ["添加 DNS 记录"以连接域](create-dns-records-at-any-dns-hosting-provider.md)，然后按照步骤在 DNS 主机的网站上添加记录。
    
6. 按照在 DNS 主机上 (TXT 记录或 MX 记录) 的步骤操作，然后将域验证回Microsoft 365。

7. 在 DNS 主机 (域) 后，从 DNS 主机中删除 TXT 记录或 MX Microsoft 365。
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>步骤 2：查找电子邮件等的 MX 记录值

::: moniker range="o365-worldwide"

1. In the Microsoft 365 管理中心， go to the **设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>”页面。

::: moniker-end
    
2. 在" **域**"页面上，选择你的域。
    
3. 选择 **"管理 DNS"，** 选择 **"更多选项**  >  **""添加你自己的 DNS"，** 然后选择"继续"以查看要添加的 DNS 记录。 
    
    更改 DNS 主机时，需要保持此信息可用，以便复制粘贴这些值。
    
    页面上列出的 DNS 记录组取决于" **域用途**"下列出的选项。
    
4. 转到 ["添加 DNS 记录"以连接域](create-dns-records-at-any-dns-hosting-provider.md)，然后按照步骤在 DNS 主机的网站上添加记录。

5. 按照在您的 DNS 主机上创建记录的步骤执行操作。

## <a name="related-content"></a>相关内容

[域常见问题解答](../setup/domains-faq.yml)（文章）\
[查找并修复添加域或 DNS 记录之后出现的问题](find-and-fix-issues.md)（文章）\
[管理域](/admin)（链接页）