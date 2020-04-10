---
title: 查找并修复在 Office 365 中添加域或 DNS 记录之后出现的问题
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: 了解在设置自定义域时，通过确保正确设置了 DNS 记录来跟踪你遇到的任何问题。
ms.openlocfilehash: 00330dea6b3401bce02779437dc047ce324dcece
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210400"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records-in-office-365"></a>查找并修复在 Office 365 中添加域或 DNS 记录之后出现的问题

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
将你的域设置为使用 Office 365 可能很有难度。 DNS 系统要求严格，很难使用，并且，你的域的 DNS 设置会影响重要的业务活动，如电子邮件！

> [!NOTE]
> 您可以通过检查域的状态检查是否存在问题。 转到 "**设置** > **域**" 并查看 "**状态**" 列中的通知。 如果出现问题，请选择 "更多操作（三个点）"，然后选择 "**检查运行状况**"。 打开的窗格将描述您的域中出现的任何问题。
  
## <a name="whats-going-on"></a>What's going on?

- [无法验证你的域？](#cant-verify-your-domain)
    
- [Outlook 不工作？](#outlook-isnt-working)
    
- [每个人的电子邮件已切换到 Office 365，并且您仅希望您的电子邮件切换？](#everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch)

- [无法确认非盈利或学校帐户状态？](#cant-confirm-non-profit-or-school-account-status)

- [服务不能与您的域一起使用？](#services-not-working-with-your-domain)
    
- [访问你的网站不起作用？](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>无法验证你的域？
<a name="BKMK_verify"> </a>

域验证未按计划方式执行，有几个常见原因：
  
1. **验证记录值不完全正确。** 请在 DNS 主机处仔细检查你已复制确切值并将其粘贴到 TXT 验证记录中。一个常见的问题是未包含记录的 "MS=" 部分。我们也需要的！ 
    
2. **尚未保存记录。** 在一些 DNS 主机上，你需要采取额外步骤来保存区域文件（存储 DNS记录的地方），以便它将通过 Internet 更新。请确保你已保存所做的更改，以便 Office 365 可以查看并验证记录。 
    
3. **该记录未在 Internet 上更新。** 通常只需几分钟，我们才能看到新记录，但偶尔可能需要几个小时的时间。 
    
## <a name="outlook-isnt-working"></a>Outlook 无法正常工作？
<a name="BKMK_OutlookBroken"> </a>

如果你已为域正确设置了你的 MX 记录和其他 DNS 记录，但邮件不起作用，让我们帮助你 [解决 Outlook 问题](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx)。
  
## <a name="everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch"></a>每个人的电子邮件已切换到 Office 365，并且您仅希望您的电子邮件切换？
<a name="BKMK_EmailSwitched"> </a>

将域添加到 Office 365 时，通常会更新365您的域的 MX 记录以指向 Office 365，并且发送到该域的所有电子邮件都将开始进入 Office 365。 在更改 MX 记录之前，请确保已在 Office 365 中为在您的域中有电子邮件的所有人创建了邮箱。
  
如果您不想将域中每个人的电子邮件移到 Office 365，该怎么办？ 你可以采取步骤，[改为仅使用几个电子邮件地址来试点 Office 365](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx)。
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>无法确认非盈利或学校帐户状态？
<a name="BKMK_validateAcct"> </a>

在以下几种情况下，只需验证组织的域，而不会设置任何服务。 例如，若要证明你的组织符合学校订阅的 Office 365。
  
请查看[验证您的 Office 365 域中的指南，以证明所有权、非盈利或教育状态，或激活 Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590)以确保您已完成所有必需的步骤。 这在每种情况下稍有不同。 
  
## <a name="services-not-working-with-your-domain"></a>这些服务对你的域不起作用？
<a name="BKMK_Test"> </a>

我们可帮助你跟踪域的 DNS 设置问题。 Office 365 中的域疑难解答将为你显示需要修复的任何记录，以及具体必须如何设置记录。 

> [!TIP]
> 已正确设置你的 DNS，但桌面版 Outlook 的邮件仍然无法工作？查看 [你可以通过 Office 365 使用的不同邮件流方案](https://go.microsoft.com/fwlink/?LinkId=787530)以确保已正确设置你的公司的内容。或发送电子邮件到下面的地址以获取更多疑难解答帮助：[修复 Outlook 问题](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx)。 
  
## <a name="accessing-your-website-isnt-working"></a>无法正常访问你的网站？
<a name="BKMK_Website"> </a>

如果您已修复任何 DNS 问题，但仍遇到问题，请尝试执行下列操作之一。
  
- 用户无法在 www.mydomain.com 上访问您的网站：[跟踪网站问题](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)
    
- 无法更新您的 A 记录或 CNAME 记录以指向您的网站：[在 Office 365 中更新自定义 DNS 记录](../dns/add-or-edit-custom-dns-records.md)
    
