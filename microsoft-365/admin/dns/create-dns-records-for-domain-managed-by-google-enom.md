---
title: 当你的域由 Google （eNom）管理时创建 DNS 记录
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
- BCS160
- MET150
- MOE150
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: 了解如何通过 Google 域页面访问 eNom 和创建 DNS。
ms.openlocfilehash: 7a1de0887b96678fb95372633b621d96f7855225
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237967"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a><span data-ttu-id="bd4ef-103">当你的域由 Google （eNom）管理时创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="bd4ef-103">Create DNS records when your domain is managed by Google (eNom)</span></span>

 <span data-ttu-id="bd4ef-104">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="bd4ef-105">要将邮件帐户迁移到 Office 365，需要在域注册机构处创建 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-105">To migrate your mail accounts to Office 365, you need to create a DNS record at your domain registrar.</span></span>
  
<span data-ttu-id="bd4ef-106">如果你在注册**Google Apps For Work**帐户时通过 Google 购买了你的域，则 DNS 记录由 Google 管理，但在 eNom 中注册。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-106">If you purchased your domain through Google while signing up for your **Google Apps for Work** account, your DNS records are managed by Google but registered with eNom.</span></span> 
  
<span data-ttu-id="bd4ef-107">您可以通过 Google**域**页面访问 eNom 和创建 DNS。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-107">You can access eNom, and create DNS, through the Google **Domains** page.</span></span> <span data-ttu-id="bd4ef-108">按本文中的步骤操作即可。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-108">Just follow the steps in this article.</span></span> 
  
## <a name="create-the-dns-record"></a><span data-ttu-id="bd4ef-109">创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="bd4ef-109">Create the DNS record</span></span>

1. <span data-ttu-id="bd4ef-110">在[Google 管理控制台](https://www.google.com/work/apps/business)中，选择 "**登录**"。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-110">At the [Google Admin console](https://www.google.com/work/apps/business), select **Sign In**.</span></span>
    
    ![Google-Apps-Configure-1-1-0](../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. <span data-ttu-id="bd4ef-112">输入您的域名，然后选择 "**转到**"。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-112">Enter your domain name, and then select **Go**.</span></span>
    
    ![Google-Apps-Configure-1-1-1](../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. <span data-ttu-id="bd4ef-114">在页面底部，选择 "**更多控件**"。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-114">At the bottom of the page, select **More controls**.</span></span>
    
    ![Google-Apps-Configure-1-2-0](../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. <span data-ttu-id="bd4ef-116">选择" **域**"。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-116">Select **Domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-1](../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. <span data-ttu-id="bd4ef-118">在 "**域**" 页上，选择 "**添加/删除域**"。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-118">On the **Domains** page, select **Add/remove domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-2](../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. <span data-ttu-id="bd4ef-120">在 "**域**" 页面上，选择 "**高级 DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-120">On the **Domains** page, select **Advanced DNS settings**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bd4ef-121">如果在注册 **Google Apps for Work** 帐户时未通过 Google 购买域名，则" **域**"页面上不会有" **高级 DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-121">If you didn't purchase a domain name through Google while signing up for your **Google Apps for Work** account, you won't have **Advanced DNS settings** on your **Domains** page.</span></span> <span data-ttu-id="bd4ef-122">相反，必须直接访问域主机的 Web 网站，以访问 DNS 设置，并执行以下步骤和后续步骤。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-122">Instead, you must go directly to your domain host's web site to access your DNS settings and to perform this and the following steps.</span></span> <span data-ttu-id="bd4ef-123">有关详细信息，请参阅[访问你的 G 套件域设置](https://support.google.com/a/answer/54693?hl=en)。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-123">See [Access your G Suite domain settings](https://support.google.com/a/answer/54693?hl=en) for more information.</span></span> 
  
    ![Google-eNom-配置-1-3](../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. <span data-ttu-id="bd4ef-125">在 "**高级 DNS 设置**" 页上，选择 "**登录到 DNS 控制台**"。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-125">On the **Advanced DNS settings** page, select **Sign in to DNS Console**.</span></span> <span data-ttu-id="bd4ef-126">请注意" **登录名**"和" **密码**"信息。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-126">Note the **Sign-in name** and **Password** information.</span></span> <span data-ttu-id="bd4ef-127">会在下一步中用到它。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-127">You'll need it in the next step.</span></span> 
    
    ![Google-eNom-配置-1-4](../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. <span data-ttu-id="bd4ef-129">使用" **高级 DNS 设置**"页上的" **登录名**"和" **密码**"登录 Google" **域管理器**"。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-129">Log in to the Google **Domain Manager** using the **Sign-in name** and **Password** from the **Advanced DNS settings** page.</span></span> 
    
    ![Google-eNom-配置-1-5](../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. <span data-ttu-id="bd4ef-131">在 " ***domain_name*** " 页上的 "**主机记录**" 部分中，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-131">On the ***domain_name*** page, in the **Host Records** section, select **Edit**.</span></span>
    
    ![Google-eNom-配置-1-6](../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. <span data-ttu-id="bd4ef-133">在 "**主机记录**" 部分，选择 "**添加新**"。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-133">In the **Host Records** section, select **Add New**.</span></span>
    
    ![Google-eNom-配置-1-7](../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. <span data-ttu-id="bd4ef-135">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="bd4ef-135">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="bd4ef-136">**HOST**</span><span class="sxs-lookup"><span data-stu-id="bd4ef-136">**HOST**</span></span>|<span data-ttu-id="bd4ef-137">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="bd4ef-137">**TXT VALUE**</span></span>|<span data-ttu-id="bd4ef-138">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="bd4ef-138">**RECORD TYPE**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> ||<span data-ttu-id="bd4ef-139">TXT</span><span class="sxs-lookup"><span data-stu-id="bd4ef-139">TXT</span></span>  <br/> |

    > [!NOTE]
    > <span data-ttu-id="bd4ef-140">This is an example.</span><span class="sxs-lookup"><span data-stu-id="bd4ef-140">This is an example.</span></span> <span data-ttu-id="bd4ef-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd4ef-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> 
  
    [<span data-ttu-id="bd4ef-142">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="bd4ef-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
  
12. <span data-ttu-id="bd4ef-143">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-143">Select **Save**.</span></span>
    
    ![Google-eNom-配置-1-9](../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. <span data-ttu-id="bd4ef-145">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-145">Select **Save Changes**.</span></span>
    
    ![Google-Apps-Configure-1-11](../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  <span data-ttu-id="bd4ef-p105">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="bd4ef-p105">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
