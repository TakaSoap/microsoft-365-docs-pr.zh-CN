---
title: 创建勒索软件的电子邮件规则
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
description: 了解如何创建电子邮件规则以防止勒索软件。
ms.openlocfilehash: 85898480438225848fc09db9a9c507045f8a182c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701546"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="d56af-103">创建电子邮件规则以防止勒索软件</span><span class="sxs-lookup"><span data-stu-id="d56af-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="d56af-104">Microsoft 365 通过阻止在 Outlook 中打开具有潜在危险的文件（如 JavaScript、批处理和可执行文件）来帮助保护你的企业免受勒索软件攻击。</span><span class="sxs-lookup"><span data-stu-id="d56af-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="d56af-105">若要通过添加阻止或警告您其他类型的文件的规则来增强此级别的保护，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="d56af-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="d56af-106">试一试！</span><span class="sxs-lookup"><span data-stu-id="d56af-106">Try it!</span></span>

1. <span data-ttu-id="d56af-107">From the admin center [https://admin.microsoft.com](https://admin.microsoft.com) at， choose **Exchange** under **Admin centers.**</span><span class="sxs-lookup"><span data-stu-id="d56af-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="d56af-108">从左侧的菜单中，选择 **邮件流**。</span><span class="sxs-lookup"><span data-stu-id="d56af-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="d56af-109">在"规则"选项卡上，选择加号 (+) 旁边的箭头，然后选择"新建 **规则"。**</span><span class="sxs-lookup"><span data-stu-id="d56af-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="d56af-110">在 **"新建规则"** 页上，输入规则的名称，滚动到底部，然后选择"更多 **选项"。**</span><span class="sxs-lookup"><span data-stu-id="d56af-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="d56af-111">Under **Apply this rule if**， select Any **attachment，** and then select **file extension includes these words.**</span><span class="sxs-lookup"><span data-stu-id="d56af-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="d56af-112">在 **"指定单词** 或短语"下的框中，输入您希望应用规则的文件扩展名，例如可以包含宏的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="d56af-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="d56af-113">使用加 (+) 符号一次添加一个。</span><span class="sxs-lookup"><span data-stu-id="d56af-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="d56af-114">通过阅读"防范勒索软件 ["了解有关文件类型的更多信息](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)。</span><span class="sxs-lookup"><span data-stu-id="d56af-114">Learn more about file types by reading [Protect against ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).</span></span>

1. <span data-ttu-id="d56af-115">向下滚动查看列表，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="d56af-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="d56af-116">在新 **规则页面上** ，选择 **"添加** 条件"，然后选择"执行以下操作 **"下的条件**。</span><span class="sxs-lookup"><span data-stu-id="d56af-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="d56af-117">您有很多规则选项可供选择，但本示例中，我们将选择"使用邮件 **通知收件人"。**</span><span class="sxs-lookup"><span data-stu-id="d56af-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="d56af-118">输入通知的消息文本，然后选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="d56af-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="d56af-119">可选：在 **"新建规则**"页上，选择"添加例外"，然后输入规则例外（如来自受信任发件人的邮件）的任何详细信息。</span><span class="sxs-lookup"><span data-stu-id="d56af-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="d56af-120">在"新建规则" **页上，选择**"保存"，然后查看所提供的规则摘要信息。</span><span class="sxs-lookup"><span data-stu-id="d56af-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>