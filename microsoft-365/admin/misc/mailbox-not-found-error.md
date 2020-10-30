---
title: 在 web 上的 Outlook 中获取 "找不到邮箱" 错误
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
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 了解如何向未授权用户添加许可证以修复 "找不到邮箱" 错误。
ms.openlocfilehash: bf8ff57704b97c8ef278938675113f5de11849de
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804855"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a><span data-ttu-id="66a22-103">在 web 上的 Outlook 中获取 "找不到邮箱" 错误？</span><span class="sxs-lookup"><span data-stu-id="66a22-103">Getting a mailbox not found error in Outlook on the web?</span></span>

<span data-ttu-id="66a22-104">如果您使用的是 web 上的 Outlook，但  **无法找到错误的邮箱**  ，则用于连接到 web 上的 outlook 的帐户没有 Exchange Online 许可证，因此没有邮箱与该帐户相关联。</span><span class="sxs-lookup"><span data-stu-id="66a22-104">If you're using Outlook on the web and you get a  **Mailbox couldn't be found for**  error, the account that you used to connect to Outlook on the web doesn't have an Exchange Online license and therefore, no mailbox is associated with the account.</span></span> <span data-ttu-id="66a22-105">您的管理员可以通过执行以下步骤，将许可证分配给您的帐户：</span><span class="sxs-lookup"><span data-stu-id="66a22-105">Your admin can assign a license to your account by following these steps:</span></span>

1. <span data-ttu-id="66a22-106">打开 [Microsoft 365 管理中心](https://portal.office.com/adminportal/home#/homepage)并转到 " **用户** " 部分下的 " **活动用户** "，然后选择查看错误的用户。</span><span class="sxs-lookup"><span data-stu-id="66a22-106">Open the  [Microsoft 365 admin center](https://portal.office.com/adminportal/home#/homepage)  and go to  **Active users**  under the  **Users**  section, and select the user who is seeing the error.</span></span>
2. <span data-ttu-id="66a22-107">在打开的用户页中，转到 "  **许可证和应用**  " 部分，选择适当的 "  **位置**  " 值，然后分配包含 Exchange Online (的许可证。展开许可证以查看其详细信息) 。</span><span class="sxs-lookup"><span data-stu-id="66a22-107">In the user page that opens, go to the  **Licenses and Apps**  section, select the appropriate  **Location**  value, and assign a license that contains Exchange Online (expand the license to see its details).</span></span> <span data-ttu-id="66a22-108">完成后，单击 "  **保存更改** "。</span><span class="sxs-lookup"><span data-stu-id="66a22-108">When you're finished, click  **Save changes** .</span></span>
