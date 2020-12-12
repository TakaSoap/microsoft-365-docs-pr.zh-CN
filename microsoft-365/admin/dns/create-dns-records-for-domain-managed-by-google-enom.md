---
title: '当你的域由 Google 管理时创建 DNS (eNom) '
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
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: 了解如何通过 Google Domains 页面访问 eNom 并创建 DNS。
ms.openlocfilehash: 3294be667653c568fbbd1a911bcfab9b6ea7788b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656851"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>当你的域由 Google 管理时创建 DNS (eNom) 

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。 
  
若要将邮件帐户迁移到 Microsoft，需要在域注册机构创建 DNS 记录。
  
如果你在注册 Google 工作应用帐户时通过 Google购买了域，DNS 记录由 Google 管理，但使用 eNom 注册。 
  
可以通过 Google 域页访问 eNom 并创建 **DNS。** 按本文中的步骤操作即可。 
  
## <a name="create-the-dns-record"></a>创建 DNS 记录

1. 在 [Google 管理控制台中，](https://www.google.com/work/apps/business)选择 **"登录"。**
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. 输入你的域名，然后选择"**转到"。**
    
    ![Google-Apps-Configure-1-1-1](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. 在页面底部，选择"更多 **控件"。**
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. 选择" **域**"。
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. 在"**域"** 页上，选择 **"添加/删除域"。**
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. 在"**域"** 页上，**选择"高级 DNS 设置"。**
    
    > [!NOTE]
    > 如果在注册 **Google Apps for Work** 帐户时未通过 Google 购买域名，则" **域**"页面上不会有" **高级 DNS 设置**"。 相反，必须直接访问域主机的 Web 网站，以访问 DNS 设置，并执行以下步骤和后续步骤。 有关详细信息 [，请参阅"访问 G Suite 域](https://support.google.com/a/answer/54693?hl=en) 设置"。 
  
    ![Google-Apps-eNom-Configure-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. 在"**高级 DNS 设置**"页上，选择 **"登录 DNS 控制台"。** 请注意" **登录名**"和" **密码**"信息。 会在下一步中用到它。 
    
    ![Google-Apps-eNom-Configure-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. 使用" **高级 DNS 设置**"页上的" **登录名**"和" **密码**"登录 Google" **域管理器**"。 
    
    ![Google-Apps-eNom-Configure-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. 在 **_domain_name_*_ 页上的 _* Host Records** 部分，选择"**编辑"。**
    
    ![Google-Apps-eNom-Configure-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. 在"**主机记录"** 部分，选择 **"添加新"。**
    
    ![Google-Apps-eNom-Configure-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. 在新记录的框中，键入或复制并粘贴下表中的值。
    
    |**HOST**|**TXT VALUE**|**记录类型**|
    |:-----|:-----|:-----|
    |@  <br/> ||TXT  <br/> |

    > [!NOTE]
    > This is an example. 在这里使用表中的特定“**目标地址或指向的地址**”值。 
  
    [如何查找此项？](../get-help-with-domains/information-for-dns-records.md)
  
12. 选择“**保存**”。
    
    ![Google-Apps-eNom-Configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. 选择 **"保存更改"。**
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。 
  
