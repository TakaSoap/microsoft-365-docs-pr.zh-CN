---
title: 停止自动转发电子邮件
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何停止自动转发电子邮件。
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701575"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="abe5e-103">停止电子邮件自动转发</span><span class="sxs-lookup"><span data-stu-id="abe5e-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="abe5e-104">如果黑客获取用户邮箱的访问权限，他们可以将用户的电子邮件自动转发到外部地址并窃取专有信息。</span><span class="sxs-lookup"><span data-stu-id="abe5e-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="abe5e-105">您可以通过创建邮件流规则来停止此操作。</span><span class="sxs-lookup"><span data-stu-id="abe5e-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="abe5e-106">试一试！</span><span class="sxs-lookup"><span data-stu-id="abe5e-106">Try it!</span></span>

1. <span data-ttu-id="abe5e-107">从 Microsoft 365 管理中心，选择 **"Exchange"、"** 邮件流"，在"规则"选项卡上，选择加号并选择 **"创建新规则"。**</span><span class="sxs-lookup"><span data-stu-id="abe5e-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="abe5e-108">选择“其他选项”。</span><span class="sxs-lookup"><span data-stu-id="abe5e-108">Select **More options**.</span></span> <span data-ttu-id="abe5e-109">命名新规则。</span><span class="sxs-lookup"><span data-stu-id="abe5e-109">Name your new rule.</span></span>
1. <span data-ttu-id="abe5e-110">然后打开下拉以在选择发件人时应用此规则，然后 **是外部内部。**</span><span class="sxs-lookup"><span data-stu-id="abe5e-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="abe5e-111">选择 **"组织内部"，** 然后 **确定**。</span><span class="sxs-lookup"><span data-stu-id="abe5e-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="abe5e-112">选择 **添加条件**，打开下拉列表，选择邮件 **属性**， **然后包含邮件类型**。</span><span class="sxs-lookup"><span data-stu-id="abe5e-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="abe5e-113">打开 **"选择邮件类型**"下拉列表，选择"**自动转发"，** 然后单击 **"确定"。**</span><span class="sxs-lookup"><span data-stu-id="abe5e-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="abe5e-114">打开" **执行以下操作"** 下拉列表，选择" **阻止** 邮件"， **然后拒绝邮件并包含说明**。</span><span class="sxs-lookup"><span data-stu-id="abe5e-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="abe5e-115">输入说明的消息文本，然后选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="abe5e-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="abe5e-116">滚动到底部，然后选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="abe5e-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="abe5e-117">已创建规则，黑客将不再能够自动转发邮件。</span><span class="sxs-lookup"><span data-stu-id="abe5e-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>