---
title: 以通讯组列表的形式发送电子邮件
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
description: 了解如何在 Microsoft 365 中将电子邮件作为通讯组列表发送。
ms.openlocfilehash: a917e59bbac40846fa289a97465f6d6e065b87ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399586"
---
# <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="f2b50-103">以通讯组列表的形式发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="f2b50-103">Send email as a distribution list</span></span>

<span data-ttu-id="f2b50-104">在 Microsoft 365 中，可以将电子邮件作为通讯组列表发送。</span><span class="sxs-lookup"><span data-stu-id="f2b50-104">In Microsoft 365, you can send email as a distribution list.</span></span> <span data-ttu-id="f2b50-105">当通讯组列表的成员答复发送到通讯组列表的邮件时，该电子邮件似乎来自通讯组列表，而不是来自单个用户。</span><span class="sxs-lookup"><span data-stu-id="f2b50-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="f2b50-106">本主题介绍如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f2b50-106">This topic shows you how to do this.</span></span>
  
## <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="f2b50-107">以通讯组列表的形式发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="f2b50-107">Send email as a distribution list</span></span>

<span data-ttu-id="f2b50-108">在执行这些步骤之前，请确保已将您添加到 Microsoft 365 通讯组列表，并且已向您授予 "代理发送" 权限。</span><span class="sxs-lookup"><span data-stu-id="f2b50-108">Before you perform these steps, make sure you've been added to a Microsoft 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="f2b50-109">**管理员**：确保已按照 "[向列表中添加 Microsoft 365 用户或联系人](../email/add-user-or-contact-to-distribution-list.md)" 中的步骤操作，并[允许成员以 Microsoft 365 组主题的形式发送电子邮件](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group)，并向通讯组列表添加了正确的人员。</span><span class="sxs-lookup"><span data-stu-id="f2b50-109">**Admins**: Make sure you've followed the steps in the [Add a Microsoft 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as a Microsoft 365 Group](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
1. <span data-ttu-id="f2b50-110">打开 web 上的 Outlook 并转到 "收件箱"。</span><span class="sxs-lookup"><span data-stu-id="f2b50-110">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="f2b50-111">打开发送到通讯组列表的邮件。</span><span class="sxs-lookup"><span data-stu-id="f2b50-111">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="f2b50-112">选择 "**答复**"。</span><span class="sxs-lookup"><span data-stu-id="f2b50-112">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="f2b50-113">在邮件底部，选择 "**更多** \> **显示来自**"。</span><span class="sxs-lookup"><span data-stu-id="f2b50-113">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="f2b50-114">![选择 "更多"，然后选择 "显示来源"](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="f2b50-114">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="f2b50-115">右键单击 "发件人地址-例如 `Ina@weewalter.me` -"，然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="f2b50-115">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="f2b50-116">![删除 FROM 别名](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="f2b50-116">![Remove the FROM alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="f2b50-117">然后键入通讯组列表地址，如 support@contoso.com，并发送邮件。</span><span class="sxs-lookup"><span data-stu-id="f2b50-117">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="f2b50-118">下次从通讯组列表中答复时，其地址将显示为 "**发件**人" 列表中的一个选项。</span><span class="sxs-lookup"><span data-stu-id="f2b50-118">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="f2b50-119">![共享邮箱的别名显示](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="f2b50-119">![Alias of the shared mailbox appears](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>
  

