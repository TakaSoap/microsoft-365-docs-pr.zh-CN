---
title: 在 easyDNS 上为 Office 365 创建 DNS 记录
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: 了解如何在 easyDNS for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: f55f39f36b8abaee2d500c87ccf1e0089caecc9d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251212"
---
# <a name="create-dns-records-at-easydns-for-office-365"></a>在 easyDNS 上为 Office 365 创建 DNS 记录

如果找不到您要查找的内容，[请检查域 FAQ](../setup/domains-faq.md) 。 
  
您需要在注册机构的网站上添加以下所有 DNS 记录以将邮件路由到 Office 365，并将您的域用于团队和 Skype for Business 等。
  
注意：所有 easyDNS service 程序包中当前都不提供 SRV 记录。 您可能需要使用 easyDNS 升级到较高的服务级别，以添加 Office 365 Skype for Business 所需的 SRV 记录。
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>验证您是否拥有包含 TXT 记录的域

1. 转到[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)并使用你的凭据登录。 
    
2. 在 "**所有域**" 标题下，选择 " **dns"。**
    
3. 在 " **TXT 记录**" 标题下，选择 "编辑" 按钮（扳手图标）。 
    
4. 在 "文本" 字段中输入以下记录：
    
    |**主机**|**Text**|
    |:-----|:-----|
    |@  <br/> |MS = msXXXXXXXX （在管理中心域页面上使用提供给你的值）  <br/> |
   
5. 选择 "**下一步**"。 
    
6. 请进行检查以确保记录正确，然后选择 "**确认**"。 
    
7. 在继续之前，请等待几分钟，以便您刚刚创建的记录可以通过 Internet 传播并在 Office 365 中检测到。
    
8. Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
    
9. 在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。
    
10. 在 "**域**" 页上，选择要验证的域。 
    
11. 在 "**设置**" 页上，选择 "**启动安装程序"。**
    
12. 在 "**验证域**" 页上，选择 "**验证**"。 
    
## <a name="add-an-mx-record-to-route-email-to-office-365"></a>添加 MX 记录以将电子邮件路由到 Office 365

1. 转到[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)并使用你的凭据登录。 
    
2. 在 "**所有域**" 标题下，选择 " **dns"。**
    
3. 在 " **MX 记录**" 标题下，选择 "编辑" 按钮（扳手图标）。 
    
4. 在 "文本" 字段中输入以下记录：
    
    |**区域邮件**|**邮件服务器**|**PREF**|
    |:-----|:-----|:-----|
    |@  <br/> |\<\>mail.protection.outlook.com （从管理中心域页面获取\<你的域\>密钥值）  <br/> |0  <br/> |
   
2. 如果要保存其他 MX 记录以进行备份，请将它们复制到某处。 在继续之前，请在此处删除所有其他 MX 记录。
    
5. 选择 "**下一步**"。 
    
6. 请进行检查以确保记录正确，然后选择 "**确认**"。 
    
## <a name="add-the-required-cname-records"></a>添加所需的 CNAME 记录

1. 转到[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)并使用你的凭据登录。 
    
2. 在 "**所有域**" 标题下，选择 " **dns"。**
    
3. 在 " **CNAME/别名记录**" 标题下，选择 "编辑" 按钮（扳手图标）。 
    
4. 在 "文本" 字段中输入以下记录：


    |**HOST**|**Address （必须以 "." 结尾）**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com。  <br/> |
    |sip  <br/> |sipdir.online.lync.com。  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com。  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net。  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com。  <br/> |
   
5. 选择 "**下一步**"。 
    
6. 请进行检查以确保记录正确，然后选择 "**确认**"。 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件

1. 转到[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)并使用你的凭据登录。 
    
2. 在 "**所有域**" 标题下，选择 " **dns"。**
    
3. 在 " **TXT 记录**" 标题下，选择 "编辑" 按钮（扳手图标）。 
    
4. 在 "文本" 字段中输入以下记录：
    
    |**主机**|**Text**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. 选择 "**下一步**"。 
    
6. 请进行检查以确保记录正确，然后选择 "**确认**"。 
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>添加 Office 365 所需的两条 SRV 记录

注意： easyDNS ' Domain Plus service 级别下当前不提供 SRV 记录。 您可能需要使用 easyDNS 升级到更高的服务级别，以添加 SRV 记录 
  
1. 转到[https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/)并使用你的凭据登录。 
    
2. 在 "**所有域**" 标题下，选择 " **dns"。**
    
3. 在 " **SRV 记录**" 标题下，选择 "编辑" 按钮（扳手图标）。 
    
4. 在 "文本" 字段中输入以下记录：
    
    |**服务台**|**协议**|**HOST**|**PRI**|**WGT**|**端口**|**目标（必须以 "." 结尾）**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com。  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com。  <br/> |1800  <br/> |
   
5. 选择 "**下一步**"。 
    
6. 请进行检查以确保记录正确，然后选择 "**确认**"。 
    

