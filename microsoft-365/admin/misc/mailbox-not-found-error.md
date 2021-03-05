---
title: 在 Outlook 网页中未找到邮箱错误
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 了解如何向未授权用户添加许可证，以修复未找到邮箱的错误。
ms.openlocfilehash: e5cdb7b48f3634d51dfe1862d07d58a23e125135
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454321"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a><span data-ttu-id="ba97c-103">在 Outlook 网页中找不到邮箱错误？</span><span class="sxs-lookup"><span data-stu-id="ba97c-103">Getting a mailbox not found error in Outlook on the web?</span></span>

<span data-ttu-id="ba97c-104">如果使用的是 Outlook 网页版，但因错误而找不到邮箱，则用于连接到 Web 上的 Outlook 的帐户没有 Exchange Online 许可证，因此没有与该帐户关联的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ba97c-104">If you're using Outlook on the web and you get a  **Mailbox couldn't be found for**  error, the account that you used to connect to Outlook on the web doesn't have an Exchange Online license and therefore, no mailbox is associated with the account.</span></span> <span data-ttu-id="ba97c-105">管理员可以按照以下步骤将许可证分配给你的帐户：</span><span class="sxs-lookup"><span data-stu-id="ba97c-105">Your admin can assign a license to your account by following these steps:</span></span>

1. <span data-ttu-id="ba97c-106">打开 [Microsoft 365](https://portal.office.com/adminportal/home#/homepage)管理中心，转到"用户"部分下的 **"活动** 用户"，然后选择看到错误的用户。</span><span class="sxs-lookup"><span data-stu-id="ba97c-106">Open the  [Microsoft 365 admin center](https://portal.office.com/adminportal/home#/homepage)  and go to  **Active users**  under the  **Users**  section, and select the user who is seeing the error.</span></span>
2. <span data-ttu-id="ba97c-107">在打开的用户页中，转到"许可证和应用"部分，选择相应的位置值，并分配包含 Exchange Online (的许可证，以查看其详细信息) 。</span><span class="sxs-lookup"><span data-stu-id="ba97c-107">In the user page that opens, go to the  **Licenses and Apps**  section, select the appropriate  **Location**  value, and assign a license that contains Exchange Online (expand the license to see its details).</span></span> <span data-ttu-id="ba97c-108">完成后，单击"保存 **更改"。**</span><span class="sxs-lookup"><span data-stu-id="ba97c-108">When you're finished, click  **Save changes**.</span></span>
