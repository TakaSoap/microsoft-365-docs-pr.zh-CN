---
title: 以通讯组列表方式发送电子邮件
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: 了解如何在 Microsoft 365 中以通讯组列表方式发送电子邮件。
ms.openlocfilehash: 379f2471fd38da5098bf8f2ca82f4f76ee82bd8e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915154"
---
# <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="346a6-103">以通讯组列表方式发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="346a6-103">Send email as a distribution list</span></span>

<span data-ttu-id="346a6-104">在 Microsoft 365 中，你可以以通讯组列表方式发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="346a6-104">In Microsoft 365, you can send email as a distribution list.</span></span> <span data-ttu-id="346a6-105">当通讯组列表成员答复发送到通讯组列表的邮件时，电子邮件看起来好像来自通讯组列表，而不是来自单个用户。</span><span class="sxs-lookup"><span data-stu-id="346a6-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="346a6-106">本主题演示如何执行此工作。</span><span class="sxs-lookup"><span data-stu-id="346a6-106">This topic shows you how to do this.</span></span>
  
## <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="346a6-107">以通讯组列表方式发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="346a6-107">Send email as a distribution list</span></span>

<span data-ttu-id="346a6-108">执行这些步骤之前，请确保你已添加到 Microsoft 365 通讯组列表，并且你已被授予以发送方式发送权限。</span><span class="sxs-lookup"><span data-stu-id="346a6-108">Before you perform these steps, make sure you've been added to a Microsoft 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="346a6-109">**管理员**：确保你已按照将 [Microsoft 365](../email/add-user-or-contact-to-distribution-list.md) 用户或联系人添加到列表和允许成员以 Microsoft [365](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) 组组方式发送电子邮件主题中的步骤操作，并将正确的人员添加到通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="346a6-109">**Admins**: Make sure you've followed the steps in the [Add a Microsoft 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as a Microsoft 365 Group](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
1. <span data-ttu-id="346a6-110">打开 Outlook 网页，然后转到收件箱。</span><span class="sxs-lookup"><span data-stu-id="346a6-110">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="346a6-111">打开发送到通讯组列表的邮件。</span><span class="sxs-lookup"><span data-stu-id="346a6-111">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="346a6-112">选择 **"答复"。**</span><span class="sxs-lookup"><span data-stu-id="346a6-112">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="346a6-113">在邮件底部，从 中选择 **"** \> **更多显示"。**</span><span class="sxs-lookup"><span data-stu-id="346a6-113">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="346a6-114">![选择"更多"，然后选择"显示自"](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="346a6-114">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="346a6-115">右键单击"From"地址（如 ） `Ina@weewalter.me` 并选择"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="346a6-115">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="346a6-116">![删除 FROM 别名](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="346a6-116">![Remove the FROM alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="346a6-117">然后键入通讯组列表地址（如 support@contoso.com 地址）并发送邮件。</span><span class="sxs-lookup"><span data-stu-id="346a6-117">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="346a6-118">下次您从通讯组列表答复时，其地址将显示为"自"列表中的 **一** 个选项。</span><span class="sxs-lookup"><span data-stu-id="346a6-118">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="346a6-119">![显示共享邮箱的别名](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="346a6-119">![Alias of the shared mailbox appears](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>
