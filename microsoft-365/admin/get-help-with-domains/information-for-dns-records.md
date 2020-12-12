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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: '了解如何查找为 Microsoft 365 创建 DNS 记录所需的值/信息。 '
ms.openlocfilehash: db9aff1fdcd9fa52c90cc96b1a32cd3908c30edb
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658503"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>收集创建 DNS 记录所需的信息

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>步骤 1：查找 TXT 记录值并验证

::: moniker range="o365-worldwide"

1. 在 Microsoft 365 管理中心中，转到"设置 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>"页。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到"设置域 **"** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"></a>页。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到"设置域 **"** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"></a>页。

::: moniker-end
    
2. 在"**域**"页上，选择你的域，然后选择"**开始设置"。** 你将返回域设置向导，查看需要添加的特定值。
    
3. 在"**验证域"** 页上，改为选择 **"添加 TXT 记录"，** 然后选择"下 **一步"。**
    
4. 复制 **显示的 TXT** 值。 它如下所示 **：MS=msXXXXXXXX**。 
    
5. 转到 [在任何 DNS](create-dns-records-at-any-dns-hosting-provider.md)托管提供商处创建 DNS 记录，然后从注册机构列表中选择 DNS 主机以查看分步说明。
    
6. 按照在 DNS 主机上 (TXT 记录或 MX) 的步骤操作，然后在 Microsoft 365 中重新验证域。

7. 在 Microsoft 365 中 (域后，从 DNS) 中删除 TXT 记录或 MX 记录。
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>步骤 2：查找电子邮件等的 MX 记录值

::: moniker range="o365-worldwide"

1. 在 Microsoft 365 管理中心中，转到"设置 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>"页。

::: moniker-end
    
::: moniker range="o365-germany"

1. 在管理中心，转到"设置域 **"** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"></a>页。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到"设置域 **"** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"></a>页。

::: moniker-end
    
2. 在" **域**"页面上，选择你的域。 
    
3. " **所需的 DNS 设置**"下将显示要添加的 DNS 记录。
    
    更改 DNS 主机时，需要保持此信息可用，以便复制粘贴这些值。
    
    页面上列出的 DNS 记录组取决于" **域用途**"下列出的选项。
    
4. 转到 [在任何 DNS](create-dns-records-at-any-dns-hosting-provider.md)托管提供商处创建 DNS 记录，然后从注册机构列表中选择 DNS 主机，以查看有关在 DNS 主机网站上添加记录的分步说明。
    
5. 按照在您的 DNS 主机上创建记录的步骤执行操作。
