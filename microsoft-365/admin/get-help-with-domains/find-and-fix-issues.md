---
title: 查找并修复添加域或 DNS 记录之后出现的问题
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: 了解如何通过确保正确设置 DNS 记录来跟踪在设置自定义域时遇到的任何问题。
ms.openlocfilehash: 7fa5a18ff0e4b7f0db8749f5659fefdd89cb3fcd
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316879"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>查找并修复添加域或 DNS 记录之后出现的问题

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。 
  
设置域以使用Microsoft 365可能非常困难。 DNS 系统要求严格，很难使用，并且，你的域的 DNS 设置会影响重要的业务活动，如电子邮件！

> [!NOTE]
> 可以通过检查域的状态来检查域的问题。 转到 **SetupDomains**  >  并查看"状态"**列中** 的通知。 如果看到问题，请选择三个点 (执行) ，然后选择"检查运行状况 **"**。 打开的窗格将描述您的域发生的任何问题。
  
## <a name="whats-going-on"></a>What's going on?

- [无法验证你的域？](#cant-verify-your-domain)
    
- [Outlook运行不工作？](#outlook-isnt-working)
    
- [每个人的电子邮件已切换为Microsoft 365，而您只想切换您的电子邮件？](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [无法确认非营利组织或学校帐户状态？](#cant-confirm-non-profit-or-school-account-status)

- [服务无法与域一起运行？](#services-not-working-with-your-domain)
    
- [访问网站不工作？](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>无法验证你的域？

域验证未按计划方式执行，有几个常见原因：
  
1. **验证记录值不完全正确。** 请在 DNS 主机处仔细检查你已复制确切值并将其粘贴到 TXT 验证记录中。一个常见的问题是未包含记录的 "MS=" 部分。我们也需要的！ 
    
2. **尚未保存记录。** 在一些 DNS 主机上，你需要采取额外步骤来保存区域文件（存储 DNS记录的地方），以便它将通过 Internet 更新。 确保已保存更改，Microsoft 365并验证记录。 
    
3. **记录尚未通过 Internet 更新。** 通常只需几分钟，我们就能看到新记录，但有时可能需要几个小时。 
    
## <a name="outlook-isnt-working"></a>Outlook 无法正常工作？

如果你已为域正确设置了你的 MX 记录和其他 DNS 记录，但邮件不起作用，让我们帮助你 [解决 Outlook 问题](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)。
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>每个人的电子邮件已切换为Microsoft 365，而您只想切换您的电子邮件？
<a name="BKMK_EmailSwitched"> </a>

将域添加到 Microsoft 365 时，你的域的 MX 记录通常由你或 Microsoft 365) 更新 (以指向 Microsoft 365，并且发送到该域的所有电子邮件都将开始发送到 Microsoft 365。 在更改 MX 记录之前，请确保Microsoft 365域中拥有电子邮件的每个人创建邮箱。
  
如果您不想将域中的每个人的电子邮件移动到其他域，Microsoft 365？ 你可以采取一些[步骤来Microsoft 365几个电子邮件地址进行试点](../setup/domains-faq.yml)。
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>无法确认非营利组织或学校帐户状态？
<a name="BKMK_validateAcct"> </a>

当你只需验证组织的域而不需要设置任何服务时，有两种情况。 例如，为了证明Microsoft 365组织有资格使用学校订阅。
  
请查看验证你的Microsoft 365域以证明所有权、非营利组织或教育状态或激活 [Yammer](../setup/domains-faq.yml) 以确保你已完成所有必需的步骤中的指南。 每种情况都有一些不同。 
  
## <a name="services-not-working-with-your-domain"></a>这些服务对你的域不起作用？

我们可帮助你跟踪域的 DNS 设置问题。 Microsoft 365中的域疑难解答将显示任何需要修复的记录，以及记录需要设置为什么。 

> [!TIP]
> 已正确设置你的 DNS，但桌面版 Outlook 的邮件仍然无法工作？ 查看可以使用[邮件流Microsoft 365](/exchange/mail-flow-best-practices/mail-flow-best-practices)，以确保为业务正确设置了一些内容。 或发送电子邮件到下面的地址以获取更多疑难解答帮助：[修复 Outlook 问题](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)。 
  
## <a name="accessing-your-website-isnt-working"></a>无法正常访问你的网站？

如果您已修复任何 DNS 问题，但仍遇到问题，请尝试执行下列操作之一。
  
- 用户无法访问您的网站，网址 *为 contoso.com*： [跟踪网站问题](../setup/add-domain.md)
    
- 无法将 A 记录或 CNAME 记录更新为指向您的网站：更新自定义 [DNS 记录](../setup/add-domain.md)Microsoft 365

## <a name="related-content"></a>相关内容

[疑难解答：审核已验证域更改的数据](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain) (文章) \
[域常见问题](../setup/domains-faq.yml) （文章）

