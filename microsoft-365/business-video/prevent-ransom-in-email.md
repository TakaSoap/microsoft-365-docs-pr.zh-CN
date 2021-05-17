---
title: 创建针对勒索软件的电子邮件规则
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
description: 了解如何创建电子邮件规则以防止勒索软件。
ms.openlocfilehash: 96822916753f2f70d481c213e7e31046f7081446
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580494"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="e08b5-103">创建电子邮件规则以防止勒索软件</span><span class="sxs-lookup"><span data-stu-id="e08b5-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="e08b5-104">Microsoft 365防止 JavaScript、批处理和可执行文件等潜在危险文件在 Outlook 中打开，帮助保护你的企业免受勒索软件Outlook。</span><span class="sxs-lookup"><span data-stu-id="e08b5-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="e08b5-105">若要通过添加阻止或警告其他类型的文件的规则来增强此级别的保护，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="e08b5-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="e08b5-106">试一试！</span><span class="sxs-lookup"><span data-stu-id="e08b5-106">Try it!</span></span>

1. <span data-ttu-id="e08b5-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com) ， choose **Exchange** under **Admin centers**.</span><span class="sxs-lookup"><span data-stu-id="e08b5-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="e08b5-108">从左侧的菜单中，选择"**邮件流"。**</span><span class="sxs-lookup"><span data-stu-id="e08b5-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="e08b5-109">On the rules tab， choose the arrow next to the plus (+) symbol， and then choose **Create a new rule**.</span><span class="sxs-lookup"><span data-stu-id="e08b5-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="e08b5-110">在"**新规则**"页上，输入规则名称，滚动到底部，然后选择"更多 **选项"。**</span><span class="sxs-lookup"><span data-stu-id="e08b5-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="e08b5-111">在 **"在应用此规则时"** 下，选择"**任何附件**"，然后选择"**文件扩展名包含以下词语"。**</span><span class="sxs-lookup"><span data-stu-id="e08b5-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="e08b5-112">在"指定 **单词** 或短语"下的框中，输入您希望应用规则的文件扩展名，例如可以包含宏的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="e08b5-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="e08b5-113">使用加 (+) 符号一次添加一个。</span><span class="sxs-lookup"><span data-stu-id="e08b5-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="e08b5-114">阅读"防范勒索软件 ["，详细了解文件类型](../admin/security-and-compliance/secure-your-business-data.md#ransomware)。</span><span class="sxs-lookup"><span data-stu-id="e08b5-114">Learn more about file types by reading [Protect against ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).</span></span>

1. <span data-ttu-id="e08b5-115">向下滚动查看列表，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="e08b5-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="e08b5-116">在" **新建规则"** 页上，选择" **添加** 条件"，然后选择"执行以下操作 **"下的条件**。</span><span class="sxs-lookup"><span data-stu-id="e08b5-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="e08b5-117">您有很多规则选项可供选择，但本示例中我们将选择"使用邮件 **通知收件人"。**</span><span class="sxs-lookup"><span data-stu-id="e08b5-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="e08b5-118">为通知输入消息文本，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="e08b5-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="e08b5-119">可选：在 **"新规则"** 页面上，选择"添加例外"，然后输入规则例外的任何详细信息，例如来自受信任发件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="e08b5-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="e08b5-120">在"新建规则"页上，选择" **保存"，** 然后查看所提供的规则摘要信息。</span><span class="sxs-lookup"><span data-stu-id="e08b5-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>