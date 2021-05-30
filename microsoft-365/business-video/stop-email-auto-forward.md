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
description: 了解如何通过创建邮件流规则来停止自动转发电子邮件，以避免窃取专有信息。
ms.openlocfilehash: 82e4c80b0edc501889e0fc4dc28f1ec1ad703568
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706470"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="4e493-103">停止电子邮件自动转发</span><span class="sxs-lookup"><span data-stu-id="4e493-103">Stop email auto-forward</span></span>

## <a name="watch-stop-auto-forwarding-emails"></a><span data-ttu-id="4e493-104">观看：停止自动转发电子邮件</span><span class="sxs-lookup"><span data-stu-id="4e493-104">Watch: Stop auto-forwarding emails</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="4e493-105">如果黑客获取用户邮箱的访问权限，他们可以将用户的电子邮件自动转发到外部地址并窃取专有信息。</span><span class="sxs-lookup"><span data-stu-id="4e493-105">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="4e493-106">您可以通过创建邮件流规则来停止此操作。</span><span class="sxs-lookup"><span data-stu-id="4e493-106">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="4e493-107">试一试！</span><span class="sxs-lookup"><span data-stu-id="4e493-107">Try it!</span></span>

1. <span data-ttu-id="4e493-108">从Microsoft 365管理中心，选择"Exchange、邮件流"，在"规则"选项卡上，选择加号并选择"**创建新规则"。** </span><span class="sxs-lookup"><span data-stu-id="4e493-108">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="4e493-109">选择“其他选项”。</span><span class="sxs-lookup"><span data-stu-id="4e493-109">Select **More options**.</span></span> <span data-ttu-id="4e493-110">命名新规则。</span><span class="sxs-lookup"><span data-stu-id="4e493-110">Name your new rule.</span></span>
1. <span data-ttu-id="4e493-111">然后打开下拉以应用此规则 **if**，选择发件人 **，然后\*\*\*\*是外部内部**。</span><span class="sxs-lookup"><span data-stu-id="4e493-111">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="4e493-112">选择 **"组织内部"，** 然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="4e493-112">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="4e493-113">选择 **"添加** 条件"，打开下拉列表，选择 **"邮件属性**"， **然后包含邮件类型**。</span><span class="sxs-lookup"><span data-stu-id="4e493-113">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="4e493-114">打开"**选择邮件类型**"下拉列表，选择"**自动转发"，** 然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="4e493-114">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="4e493-115">打开" **执行以下操作"** 下拉列表，选择" **阻止** 邮件"，然后拒绝 **邮件并包含说明**。</span><span class="sxs-lookup"><span data-stu-id="4e493-115">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="4e493-116">输入说明的消息文本，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="4e493-116">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="4e493-117">滚动到底部，**然后选择保存。**</span><span class="sxs-lookup"><span data-stu-id="4e493-117">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="4e493-118">已创建规则，黑客将无法再自动转发邮件。</span><span class="sxs-lookup"><span data-stu-id="4e493-118">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="4e493-119">相关内容</span><span class="sxs-lookup"><span data-stu-id="4e493-119">Related content</span></span>

<span data-ttu-id="4e493-120">[为用户添加另一个电子邮件别名](../admin/email/add-another-email-alias-for-a-user.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="4e493-120">[Add another email alias for a user](../admin/email/add-another-email-alias-for-a-user.md) (article)</span></span>\
<span data-ttu-id="4e493-121">[在 Microsoft 365 中配置电子邮件转发](../admin/email/configure-email-forwarding.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="4e493-121">[Configure email forwarding in Microsoft 365](../admin/email/configure-email-forwarding.md) (article)</span></span>\
<span data-ttu-id="4e493-122">[查找并修复作为企业管理员Office 365的电子邮件](/exchange/troubleshoot/email-delivery/email-delivery-issues) (问题) </span><span class="sxs-lookup"><span data-stu-id="4e493-122">[Find and fix email delivery issues as an Office 365 for business admin](/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>