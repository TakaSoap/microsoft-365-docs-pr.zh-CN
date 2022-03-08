---
title: 查找域注册机构
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: 了解如何使用 InterNIC 搜索查找域注册机构和 DNS 托管提供商。
ms.openlocfilehash: c7802067bc3d8397d9f7b7ddf0f6cda4dd57c38b
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316865"
---
# <a name="find-your-domain-registrar"></a>查找域注册机构

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。

## <a name="domain-registrar"></a>域名注册机构

### <a name="find-your-domain-name-registrar"></a>查找域名注册机构

> [!NOTE]
> 只有以 *.COM*、*.NET* 和 *.EDU* 结尾的域才可以使用此工具。

1. 在 [InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770)页面上的 **Whois 搜索** 框中，键入你的域。例如，  *contoso.com。*

2. 选择"**域**"选项，然后选择"**提交**"。

3. 在“**Whois 搜索结果**”页上，查找“**注册机构**”条目。此条目列出了针对您的域提供注册机构服务的组织的名称。

## <a name="dns-hosting-provider"></a>DNS 托管提供商

### <a name="find-your-dns-hosting-provider"></a>查找 DNS 托管提供商

> [!NOTE]
> 只有以 *.COM*、*.NET* 和 *.EDU* 结尾的域才可以使用此工具。

1. 在 [InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770)页面上的 **Whois 搜索** 框中，键入你的域。例如，contoso.com。

2. 选择"**域**"选项，然后选择"**提交**"。

3. 在“**Whois 搜索结果**”页上，查找第一个“**名称服务器**”条目。

4. 复制在冒号 (:) 之后显示的名称服务器 (NS) 信息，然后将其粘贴到页面顶部的“**搜索**”框中。选择“**名称服务器**”，然后单击“**提交**”。

5. 在“**Whois 搜索结果**”页上，查找“**注册机构**”条目。此条目列出了拥有您的域的名称服务器的 DNS 托管提供商。

---

