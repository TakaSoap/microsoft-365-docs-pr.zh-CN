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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: 将电子邮件作为通讯组列表Microsoft 365以便当成员回复邮件时，邮件看起来好像来自通讯组列表。
ms.openlocfilehash: c77455b5b990a9c35fc7e47ee81cc9ddef4d0a23
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392511"
---
# <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="41fcc-103">以通讯组列表方式发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="41fcc-103">Send email as a distribution list</span></span>

<span data-ttu-id="41fcc-104">在Microsoft 365中，你可以以通讯组列表方式发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="41fcc-104">In Microsoft 365, you can send email as a distribution list.</span></span> <span data-ttu-id="41fcc-105">当通讯组列表成员答复发送到通讯组列表的邮件时，电子邮件看起来好像来自通讯组列表，而不是来自单个用户。</span><span class="sxs-lookup"><span data-stu-id="41fcc-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="41fcc-106">本主题演示如何执行此工作。</span><span class="sxs-lookup"><span data-stu-id="41fcc-106">This topic shows you how to do this.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="41fcc-107">准备工作</span><span class="sxs-lookup"><span data-stu-id="41fcc-107">Before you begin</span></span>

<span data-ttu-id="41fcc-108">执行这些步骤之前，请确保你已添加到Microsoft 365通讯组列表，并且你已被授予以发送方式发送权限。</span><span class="sxs-lookup"><span data-stu-id="41fcc-108">Before you perform these steps, make sure you've been added to a Microsoft 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="41fcc-109">**管理员**：确保你已按照将 [Microsoft 365](../email/add-user-or-contact-to-distribution-list.md)用户或联系人添加到列表和允许成员以 [Microsoft 365 组](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group)组方式发送电子邮件主题中的步骤操作，并将正确的人员添加到通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="41fcc-109">**Admins**: Make sure you've followed the steps in the [Add a Microsoft 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as a Microsoft 365 Group](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
## <a name="outlook-on-the-web"></a><span data-ttu-id="41fcc-110">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="41fcc-110">Outlook on the web</span></span>

1. <span data-ttu-id="41fcc-111">打开Outlook 网页版并转到收件箱。</span><span class="sxs-lookup"><span data-stu-id="41fcc-111">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="41fcc-112">打开发送到通讯组列表的邮件。</span><span class="sxs-lookup"><span data-stu-id="41fcc-112">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="41fcc-113">选择 **"答复"。**</span><span class="sxs-lookup"><span data-stu-id="41fcc-113">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="41fcc-114">在邮件底部，从 中选择 **"** \> **更多显示"。**</span><span class="sxs-lookup"><span data-stu-id="41fcc-114">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="41fcc-115">![选择"更多"，然后选择"显示自"](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="41fcc-115">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="41fcc-116">右键单击"From"地址（如 ） `Ina@weewalter.me` 并选择"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="41fcc-116">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="41fcc-117">![删除 FROM 别名](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="41fcc-117">![Remove the FROM alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="41fcc-118">然后键入通讯组列表地址（如 support@contoso.com 地址）并发送邮件。</span><span class="sxs-lookup"><span data-stu-id="41fcc-118">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="41fcc-119">下次您从通讯组列表答复时，其地址将显示为"自"列表中的 **一** 个选项。</span><span class="sxs-lookup"><span data-stu-id="41fcc-119">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="41fcc-120">![显示共享邮箱的别名](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="41fcc-120">![Alias of the shared mailbox appears](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>

## <a name="outlook"></a><span data-ttu-id="41fcc-121">Outlook</span><span class="sxs-lookup"><span data-stu-id="41fcc-121">Outlook</span></span>

1. <span data-ttu-id="41fcc-122">打开Outlook桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="41fcc-122">Open Outlook desktop client.</span></span>

2. <span data-ttu-id="41fcc-123">撰写新电子邮件。</span><span class="sxs-lookup"><span data-stu-id="41fcc-123">Compose a New Email.</span></span> <span data-ttu-id="41fcc-124">单击"**自"** 字段，然后选择 **"其他电子邮件地址"。**</span><span class="sxs-lookup"><span data-stu-id="41fcc-124">Click the **From** field and select **Other email address**.</span></span> <span data-ttu-id="41fcc-125">如果看不到"自"字段，请导航到 **"选项** "，然后选择" **显示** 字段"部分中的"自"。</span><span class="sxs-lookup"><span data-stu-id="41fcc-125">If you do not see the From field, navigate to **Options** and select **From** in the Show fields section.</span></span>

3. <span data-ttu-id="41fcc-126">从全局 **地址列表中选择** 通讯组列表地址。</span><span class="sxs-lookup"><span data-stu-id="41fcc-126">Select the **Distribution List** address from the Global Address List.</span></span>

4. <span data-ttu-id="41fcc-127">发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="41fcc-127">Send the email.</span></span>

## <a name="related-content"></a><span data-ttu-id="41fcc-128">相关内容</span><span class="sxs-lookup"><span data-stu-id="41fcc-128">Related content</span></span>

<span data-ttu-id="41fcc-129">[创建、编辑或删除](../email/create-edit-or-delete-a-security-group.md)安全组，Microsoft 365 管理中心 (文章) </span><span class="sxs-lookup"><span data-stu-id="41fcc-129">[Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md) (article)</span></span>\
<span data-ttu-id="41fcc-130">[电子邮件协作](../email/email-collaboration.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="41fcc-130">[Email collaboration](../email/email-collaboration.md) (article)</span></span>\
<span data-ttu-id="41fcc-131">[向通讯组添加用户或联系人 (](../email/add-user-or-contact-to-distribution-list.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="41fcc-131">[Add a user or contact to a distribution group](../email/add-user-or-contact-to-distribution-list.md) (article)</span></span>