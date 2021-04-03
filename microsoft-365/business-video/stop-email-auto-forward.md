---
title: 停止自动转发电子邮件
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
ms.openlocfilehash: b6715cfdf8622521d977e0746cb9a340a8f70a5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578599"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="426bf-103">停止电子邮件自动转发</span><span class="sxs-lookup"><span data-stu-id="426bf-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="426bf-104">如果黑客获取用户邮箱的访问权限，他们可以将用户的电子邮件自动转发到外部地址并窃取专有信息。</span><span class="sxs-lookup"><span data-stu-id="426bf-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="426bf-105">您可以通过创建邮件流规则来停止此操作。</span><span class="sxs-lookup"><span data-stu-id="426bf-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="426bf-106">试一试！</span><span class="sxs-lookup"><span data-stu-id="426bf-106">Try it!</span></span>

1. <span data-ttu-id="426bf-107">从 Microsoft 365 管理中心，选择 **"Exchange"** 和"**邮件** 流"，在"规则"选项卡上，选择加号并选择"**创建新规则"。**</span><span class="sxs-lookup"><span data-stu-id="426bf-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="426bf-108">选择“其他选项”。</span><span class="sxs-lookup"><span data-stu-id="426bf-108">Select **More options**.</span></span> <span data-ttu-id="426bf-109">命名新规则。</span><span class="sxs-lookup"><span data-stu-id="426bf-109">Name your new rule.</span></span>
1. <span data-ttu-id="426bf-110">然后打开下拉以应用此规则 **if**，选择发件人 **，然后\*\*\*\*是外部内部**。</span><span class="sxs-lookup"><span data-stu-id="426bf-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="426bf-111">选择 **"组织内部"，** 然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="426bf-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="426bf-112">选择 **"添加** 条件"，打开下拉列表，选择 **"邮件属性**"， **然后包含邮件类型**。</span><span class="sxs-lookup"><span data-stu-id="426bf-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="426bf-113">打开"**选择邮件类型**"下拉列表，选择"**自动转发"，** 然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="426bf-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="426bf-114">打开" **执行以下操作"** 下拉列表，选择" **阻止** 邮件"，然后拒绝 **邮件并包含说明**。</span><span class="sxs-lookup"><span data-stu-id="426bf-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="426bf-115">输入说明的消息文本，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="426bf-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="426bf-116">滚动到底部，**然后选择保存。**</span><span class="sxs-lookup"><span data-stu-id="426bf-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="426bf-117">已创建规则，黑客将无法再自动转发邮件。</span><span class="sxs-lookup"><span data-stu-id="426bf-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>