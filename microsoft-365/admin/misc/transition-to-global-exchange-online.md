---
title: 更新 MX 记录以转换到全局 Exchange Online 服务
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何从 Microsoft 云德国 Exchange Online 转换到全局 Exchange Online 服务
ms.openlocfilehash: 41628b3032f5b268d5e32501b393fef31663dfc3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399226"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="718b7-103">更新 MX 记录以转换到全局 Exchange Online 服务</span><span class="sxs-lookup"><span data-stu-id="718b7-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="718b7-104">登录到[Microsoft 365 管理门户](https://admin.microsoft.com)，然后转到**设置**  >  **域**</span><span class="sxs-lookup"><span data-stu-id="718b7-104">Sign in to [Microsoft 365 admin portal](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="718b7-105">状态将显示在每个域的右侧。</span><span class="sxs-lookup"><span data-stu-id="718b7-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="718b7-106">如果你的组织的域指向 Microsoft 云德国 Exchange Online，你将需要更新你的 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="718b7-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="718b7-107">单击域，然后单击 "**检测到 DNS 错误"，单击此处查看**。</span><span class="sxs-lookup"><span data-stu-id="718b7-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="718b7-108">此页面将提供说明如何修复 MX 记录的说明。</span><span class="sxs-lookup"><span data-stu-id="718b7-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="718b7-109">如果你的域注册机构使用[域连接](../setup/add-domain.md#registrars-with-domain-connect)，则可以单击顶部的 "修复我的记录"。</span><span class="sxs-lookup"><span data-stu-id="718b7-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="718b7-110">否则，可以按照向导中的链接，获取注册器的分步**说明**。</span><span class="sxs-lookup"><span data-stu-id="718b7-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>