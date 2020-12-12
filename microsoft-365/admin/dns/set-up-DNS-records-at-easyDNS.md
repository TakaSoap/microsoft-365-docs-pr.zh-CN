---
title: 在 EasyDNS 为 Microsoft 创建 DNS 记录
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: 了解如何在 EasyDNS for Microsoft 中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: a971a722f071ef5df9ce0fba387cfacfeb409f5b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656815"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a>在 EasyDNS 为 Microsoft 创建 DNS 记录

[如果找不到 ](../setup/domains-faq.yml) 要查找的内容，请查看域常见问题解答。 
  
你需要在注册机构网站上添加以下所有 DNS 记录，将邮件路由到 Microsoft，将域用于 Teams 和 Skype for Business，等等。
  
注意：SRV 记录当前在所有 easyDNS 服务包下不可用。 你可能需要使用 easyDNS 升级到更高的服务级别，以添加 Skype for Business 所需的 SRV 记录。
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>验证是否拥有具有 TXT 记录的域

1. 转到 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 凭据并登录。 
    
2. 在所有 **域标题** 下，选择 **dns。**
    
3. 在 **TXT 记录** 标题下，选择编辑按钮 (扳手图标) 。 
    
4. 在文本字段中输入以下记录：
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |MS=msXXXXXXXX (使用管理中心"域"页上提供的值)   <br/> |
   
5. 选择 **"下一步"。** 
    
6. 检查以确保记录正确，然后选择"确认 **"。** 
    
7. 请等待几分钟，然后再继续，以便你刚刚创建的记录可以传播到 Internet 中，并且 Microsoft 会检测到该记录。
    
8. 在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。
    
9. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。
    
10. 在“**域**”页面上，选择要验证的域。 
    
11. 在" **设置"** 页上，选择 **"开始设置"。**
    
12. 在“**验证域**”页面上，选择“**验证**”。 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a>添加 MX 记录以将电子邮件路由到 Microsoft

1. 转到 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 凭据并登录。 
    
2. 在所有 **域标题** 下，选择 **dns。**
    
3. 在 **MX 记录标题** 下，选择编辑按钮 (扳手图标) 。 
    
4. 在文本字段中输入以下记录：
    
    |**区域邮件**|**邮件服务器**|**PREF**|
    |:-----|:-----|:-----|
    |@  <br/> |\<domain-key\>.mail.protection.outlook.com (从管理中心 \<domain-key\> "域"页面获取)   <br/> |0  <br/> |
   
2. 如果要保存其他 MX 记录以用于备份，请将其复制到某处。 在继续之前，请在此处删除所有其他 MX 记录。
    
5. 选择 **"下一步"。** 
    
6. 检查以确保记录正确，然后选择"确认 **"。** 
    
## <a name="add-the-required-cname-records"></a>添加所需的 CNAME 记录

1. 转到 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 凭据并登录。 
    
2. 在所有 **域标题** 下，选择 **dns。**
    
3. 在 **CNAME/别名** 记录标题下，选择 (扳手图标) 。 
    
4. 在文本字段中输入以下记录：


    |**HOST**|**地址 (必须以"."结尾。)**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. 选择 **"下一步"。** 
    
6. 检查以确保记录正确，然后选择"确认 **"。** 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>为 SPF 添加 TXT 记录以帮助防止垃圾邮件

1. 转到 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 凭据并登录。 
    
2. 在所有 **域标题** 下，选择 **dns。**
    
3. 在 **TXT 记录** 标题下，选择编辑按钮 (扳手图标) 。 
    
4. 在文本字段中输入以下记录：
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. 选择 **"下一步"。** 
    
6. 检查以确保记录正确，然后选择"确认 **"。** 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>添加 Microsoft 所需的两条 SRV 记录

注意：SRV 记录当前在 easyDNS 的 Domain Plus 服务级别下不可用。 您可能需要使用 easyDNS 升级到更高的服务级别，以添加 SRV 记录 
  
1. 转到 [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) 凭据并登录。 
    
2. 在所有 **域标题** 下，选择 **dns。**
    
3. 在 **SRV 记录标题** 下，选择编辑按钮 (扳手图标) 。 
    
4. 在文本字段中输入以下记录：
    
    |**服务**|**PROTO**|**HOST**|**PRI**|**WGT**|**端口**|**TARGET (必须以"."结尾。)**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com。  <br/> |1800  <br/> |
   
5. 选择 **"下一步"。** 
    
6. 检查以确保记录正确，然后选择"确认 **"。** 
    

