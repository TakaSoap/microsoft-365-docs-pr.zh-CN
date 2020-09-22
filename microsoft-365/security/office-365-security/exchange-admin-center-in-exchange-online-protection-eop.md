---
title: 独立 EOP 中的 Exchange 管理中心
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: 了解独立 Exchange Online Protection (EOP) 中的 web 管理界面。
ms.openlocfilehash: 732991befa9084b62c152295d10a2bbf94bc36ec
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202947"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="c173a-103">独立 EOP 中的 Exchange 管理中心</span><span class="sxs-lookup"><span data-stu-id="c173a-103">Exchange admin center in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c173a-104">Exchange 管理中心 (EAC) 是一个基于 web 的管理控制台，用于 (EOP) 的独立 Exchange Online Protection。</span><span class="sxs-lookup"><span data-stu-id="c173a-104">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="c173a-105">正在查找此主题的 Exchange Online 版本？</span><span class="sxs-lookup"><span data-stu-id="c173a-105">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="c173a-106">请参阅 [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="c173a-106">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="c173a-107">在 EOP 中打开 EAC</span><span class="sxs-lookup"><span data-stu-id="c173a-107">Open the EAC in EOP</span></span>

<span data-ttu-id="c173a-108">独立 EOP 客户可以使用以下方法访问 EAC：</span><span class="sxs-lookup"><span data-stu-id="c173a-108">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="c173a-109">**从 Microsoft 365 管理中心**：</span><span class="sxs-lookup"><span data-stu-id="c173a-109">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="c173a-110">转到 <https://admin.microsoft.com> 并单击 " **全部显示**"。</span><span class="sxs-lookup"><span data-stu-id="c173a-110">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![单击 Microsoft 365 管理中心中的 "全部显示"](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="c173a-112">在出现的 " **管理中心** " 部分中，单击 " **所有管理中心**"。</span><span class="sxs-lookup"><span data-stu-id="c173a-112">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![单击 Microsoft 365 管理中心内的 "所有管理中心"](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="c173a-114">在出现的 " **所有管理中心** " 页上，单击 " **Exchange Online Protection**"。</span><span class="sxs-lookup"><span data-stu-id="c173a-114">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="c173a-115">直接转到 `https://admin.protection.outlook.com/ecp/` 。</span><span class="sxs-lookup"><span data-stu-id="c173a-115">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="c173a-116">EOP 中 EAC 中的常见用户界面元素</span><span class="sxs-lookup"><span data-stu-id="c173a-116">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="c173a-117">本部分将介绍 EAC 中的用户界面元素。</span><span class="sxs-lookup"><span data-stu-id="c173a-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP-AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="c173a-119">功能窗格</span><span class="sxs-lookup"><span data-stu-id="c173a-119">Feature Pane</span></span>

<span data-ttu-id="c173a-p102">这是您要在 EAC 中执行的大部分任务的第一级导航。功能窗格按功能区域组织。</span><span class="sxs-lookup"><span data-stu-id="c173a-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="c173a-122">**收件人**：可以在其中查看组和外部联系人。</span><span class="sxs-lookup"><span data-stu-id="c173a-122">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="c173a-123">**权限**：这将管理管理员角色。</span><span class="sxs-lookup"><span data-stu-id="c173a-123">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="c173a-124">**合规性管理**：您可以在此处找到管理员角色组报告和管理员审核日志报告。</span><span class="sxs-lookup"><span data-stu-id="c173a-124">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="c173a-125">**保护**：您可以在这里管理反恶意软件策略、默认连接筛选器策略和 DKIM。</span><span class="sxs-lookup"><span data-stu-id="c173a-125">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c173a-126">应在安全 & 合规性中心管理反恶意软件策略和默认连接筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="c173a-126">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="c173a-127">有关详细信息，请参阅 [在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md) 和 [在 EOP 中配置连接筛选](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="c173a-127">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="c173a-128">**邮件流**：这是管理邮件流规则的地方， (也称为传输规则) 、接受域和连接器，以及可以转到运行邮件跟踪的位置。</span><span class="sxs-lookup"><span data-stu-id="c173a-128">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="c173a-129">**混合**：您可以在这里运行 " [混合配置" 向导](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)，以及可以在其中安装 [Exchange Online PowerShell 模块](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c173a-129">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="c173a-130">选项卡</span><span class="sxs-lookup"><span data-stu-id="c173a-130">Tabs</span></span>

<span data-ttu-id="c173a-p104">选项卡是导航的第二级。每个功能区都包含各种选项卡，每种选项卡代表一项功能。</span><span class="sxs-lookup"><span data-stu-id="c173a-p104">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="c173a-133">工具栏</span><span class="sxs-lookup"><span data-stu-id="c173a-133">Toolbar</span></span>

<span data-ttu-id="c173a-p105">单击大多数选项卡时，将看到一个工具栏。工具栏包含执行特定操作的图标。下表介绍图标及其操作。</span><span class="sxs-lookup"><span data-stu-id="c173a-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="c173a-137">图标</span><span class="sxs-lookup"><span data-stu-id="c173a-137">Icon</span></span>|<span data-ttu-id="c173a-138">名称</span><span class="sxs-lookup"><span data-stu-id="c173a-138">Name</span></span>|<span data-ttu-id="c173a-139">Action</span><span class="sxs-lookup"><span data-stu-id="c173a-139">Action</span></span>|
|---|---|---|
|![添加图标](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="c173a-141">添加、新建</span><span class="sxs-lookup"><span data-stu-id="c173a-141">Add, New</span></span>|<span data-ttu-id="c173a-p106">使用此图标可创建一个新对象。其中一些图标有关联的向下箭头，单击该箭头会显示可以创建的其他对象。</span><span class="sxs-lookup"><span data-stu-id="c173a-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![编辑图标](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="c173a-145">编辑</span><span class="sxs-lookup"><span data-stu-id="c173a-145">Edit</span></span>|<span data-ttu-id="c173a-146">使用此图标可编辑对象。</span><span class="sxs-lookup"><span data-stu-id="c173a-146">Use this icon to edit an object.</span></span>|
|![删除图标](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="c173a-148">删除</span><span class="sxs-lookup"><span data-stu-id="c173a-148">Delete</span></span>|<span data-ttu-id="c173a-p107">使用此图标可删除对象。有些删除图标有一个向下箭头，单击该箭头可显示其他选项。</span><span class="sxs-lookup"><span data-stu-id="c173a-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![搜索图标](../../media/ITPro-EAC-.gif)|<span data-ttu-id="c173a-152">搜索</span><span class="sxs-lookup"><span data-stu-id="c173a-152">Search</span></span>|<span data-ttu-id="c173a-153">使用此图标可打开一个搜索框，可在其中键入要查找的对象的搜索短语。</span><span class="sxs-lookup"><span data-stu-id="c173a-153">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![刷新图标](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="c173a-155">刷新</span><span class="sxs-lookup"><span data-stu-id="c173a-155">Refresh</span></span>|<span data-ttu-id="c173a-156">使用此图标可刷新列表视图。</span><span class="sxs-lookup"><span data-stu-id="c173a-156">Use this icon to refresh the list view.</span></span>|
|![更多选项图标](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="c173a-158">更多选项</span><span class="sxs-lookup"><span data-stu-id="c173a-158">More options</span></span>|<span data-ttu-id="c173a-159">使用此图标可以查看可对该选项卡的对象执行的更多操作。</span><span class="sxs-lookup"><span data-stu-id="c173a-159">Use this icon to view more actions you can perform for that tab's objects.</span></span> <span data-ttu-id="c173a-160">例如，在 " **收件人" \> 用户** 单击此图标时，将显示用于执行 **高级搜索**的选项。</span><span class="sxs-lookup"><span data-stu-id="c173a-160">For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![向上键图标](../../media/ITPro-EAC-UpArrowIcon.gif)![向下键图标](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="c173a-163">向上箭头和向下箭头</span><span class="sxs-lookup"><span data-stu-id="c173a-163">Up arrow and down arrow</span></span>|<span data-ttu-id="c173a-164">使用这些图标可以将对象的优先级上移或下移。</span><span class="sxs-lookup"><span data-stu-id="c173a-164">Use these icons to move an object's priority up or down.</span></span>|
|![删除图标](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="c173a-166">删除</span><span class="sxs-lookup"><span data-stu-id="c173a-166">Remove</span></span>|<span data-ttu-id="c173a-167">使用此图标可从列表中删除对象。</span><span class="sxs-lookup"><span data-stu-id="c173a-167">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="c173a-168">列表视图</span><span class="sxs-lookup"><span data-stu-id="c173a-168">List View</span></span>

<span data-ttu-id="c173a-p109">选择某个选项卡时，在大多数情况下，将会看到一个列表视图。EAC 列表视图的可查看限制大约为 10,000 个对象。此外还包括了分页功能，因此可以对结果进行分页。</span><span class="sxs-lookup"><span data-stu-id="c173a-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="c173a-172">详细信息窗格</span><span class="sxs-lookup"><span data-stu-id="c173a-172">Details Pane</span></span>

<span data-ttu-id="c173a-p110">从列表视图中选择对象时，有关该对象的信息将在详细信息窗格中显示。在某些情况下，详细信息窗格包括管理任务。</span><span class="sxs-lookup"><span data-stu-id="c173a-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="c173a-175">自有图块和帮助</span><span class="sxs-lookup"><span data-stu-id="c173a-175">Me tile and Help</span></span>

<span data-ttu-id="c173a-176">使用“自有”\*\*\*\* 图块可以注销 EAC，然后以其他用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="c173a-176">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="c173a-177">从 "**帮助** ![ 帮助" 图标 ](../../media/ITPro-EAC-HelpIcon.gif) 下拉菜单中，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c173a-177">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

- <span data-ttu-id="c173a-178">**帮助**：单击 " ![ 帮助" 图标 ](../../media/ITPro-EAC-HelpIcon.gif) 可查看联机帮助内容。</span><span class="sxs-lookup"><span data-stu-id="c173a-178">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

- <span data-ttu-id="c173a-179">**反馈**：留下反馈。</span><span class="sxs-lookup"><span data-stu-id="c173a-179">**Feedback**: Leave feedback.</span></span>

- <span data-ttu-id="c173a-180">**社区**：在社区论坛中发布有关查找答案的问题。</span><span class="sxs-lookup"><span data-stu-id="c173a-180">**Community**: Post a question for find answers in the community forums.</span></span>

- <span data-ttu-id="c173a-181">**禁用帮助气泡**：当您创建或编辑对象时，帮助气泡会显示字段的上下文帮助。</span><span class="sxs-lookup"><span data-stu-id="c173a-181">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="c173a-182">您可以关闭"帮助"气泡，如果已被禁用，也可以打开它。</span><span class="sxs-lookup"><span data-stu-id="c173a-182">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

- <span data-ttu-id="c173a-183">**显示命令日志记录**：将打开一个新窗口，其中显示了基于 EAC 中配置的内容的等效 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="c173a-183">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="c173a-184">支持的浏览器</span><span class="sxs-lookup"><span data-stu-id="c173a-184">Supported Browsers</span></span>

<span data-ttu-id="c173a-185">若要获得最佳的 EAC 使用体验，我们建议您始终使用最新的浏览器、Office 客户端和应用程序。</span><span class="sxs-lookup"><span data-stu-id="c173a-185">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="c173a-186">我们还建议您安装可用的软件更新。</span><span class="sxs-lookup"><span data-stu-id="c173a-186">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="c173a-187">有关支持的服务的浏览器和系统要求的详细信息，请参阅 [Office 的系统要求](https://products.office.com/office-system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="c173a-187">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="c173a-188">支持的语言</span><span class="sxs-lookup"><span data-stu-id="c173a-188">Supported languages</span></span>

<span data-ttu-id="c173a-189">在独立 EOP 中，EAC 支持并可使用以下语言。</span><span class="sxs-lookup"><span data-stu-id="c173a-189">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="c173a-190">阿姆哈拉语</span><span class="sxs-lookup"><span data-stu-id="c173a-190">Amharic</span></span>
- <span data-ttu-id="c173a-191">阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="c173a-191">Arabic</span></span>
- <span data-ttu-id="c173a-192">巴斯克语（巴斯克）</span><span class="sxs-lookup"><span data-stu-id="c173a-192">Basque (Basque)</span></span>
- <span data-ttu-id="c173a-193">孟加拉语（印度）</span><span class="sxs-lookup"><span data-stu-id="c173a-193">Bengali (India)</span></span>
- <span data-ttu-id="c173a-194">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="c173a-194">Bulgarian</span></span>
- <span data-ttu-id="c173a-195">加泰罗尼亚语</span><span class="sxs-lookup"><span data-stu-id="c173a-195">Catalan</span></span>
- <span data-ttu-id="c173a-196">中文（简体）</span><span class="sxs-lookup"><span data-stu-id="c173a-196">Chinese (Simplified)</span></span>
- <span data-ttu-id="c173a-197">中文（繁体）</span><span class="sxs-lookup"><span data-stu-id="c173a-197">Chinese (Traditional)</span></span>
- <span data-ttu-id="c173a-198">克罗地亚语</span><span class="sxs-lookup"><span data-stu-id="c173a-198">Croatian</span></span>
- <span data-ttu-id="c173a-199">捷克语</span><span class="sxs-lookup"><span data-stu-id="c173a-199">Czech</span></span>
- <span data-ttu-id="c173a-200">丹麦语</span><span class="sxs-lookup"><span data-stu-id="c173a-200">Danish</span></span>
- <span data-ttu-id="c173a-201">荷兰语</span><span class="sxs-lookup"><span data-stu-id="c173a-201">Dutch</span></span>
- <span data-ttu-id="c173a-202">英语</span><span class="sxs-lookup"><span data-stu-id="c173a-202">English</span></span>
- <span data-ttu-id="c173a-203">爱沙尼亚语</span><span class="sxs-lookup"><span data-stu-id="c173a-203">Estonian</span></span>
- <span data-ttu-id="c173a-204">菲律宾语（菲律宾）</span><span class="sxs-lookup"><span data-stu-id="c173a-204">Filipino (Philippines)</span></span>
- <span data-ttu-id="c173a-205">芬兰语</span><span class="sxs-lookup"><span data-stu-id="c173a-205">Finnish</span></span>
- <span data-ttu-id="c173a-206">法语</span><span class="sxs-lookup"><span data-stu-id="c173a-206">French</span></span>
- <span data-ttu-id="c173a-207">加利西亚语</span><span class="sxs-lookup"><span data-stu-id="c173a-207">Galician</span></span>
- <span data-ttu-id="c173a-208">德语</span><span class="sxs-lookup"><span data-stu-id="c173a-208">German</span></span>
- <span data-ttu-id="c173a-209">希腊语</span><span class="sxs-lookup"><span data-stu-id="c173a-209">Greek</span></span>
- <span data-ttu-id="c173a-210">古吉拉特语</span><span class="sxs-lookup"><span data-stu-id="c173a-210">Gujarati</span></span>
- <span data-ttu-id="c173a-211">希伯来语</span><span class="sxs-lookup"><span data-stu-id="c173a-211">Hebrew</span></span>
- <span data-ttu-id="c173a-212">印地语</span><span class="sxs-lookup"><span data-stu-id="c173a-212">Hindi</span></span>
- <span data-ttu-id="c173a-213">匈牙利语</span><span class="sxs-lookup"><span data-stu-id="c173a-213">Hungarian</span></span>
- <span data-ttu-id="c173a-214">冰岛语</span><span class="sxs-lookup"><span data-stu-id="c173a-214">Icelandic</span></span>
- <span data-ttu-id="c173a-215">印度尼西亚语</span><span class="sxs-lookup"><span data-stu-id="c173a-215">Indonesian</span></span>
- <span data-ttu-id="c173a-216">意大利语</span><span class="sxs-lookup"><span data-stu-id="c173a-216">Italian</span></span>
- <span data-ttu-id="c173a-217">日语</span><span class="sxs-lookup"><span data-stu-id="c173a-217">Japanese</span></span>
- <span data-ttu-id="c173a-218">卡纳达语</span><span class="sxs-lookup"><span data-stu-id="c173a-218">Kannada</span></span>
- <span data-ttu-id="c173a-219">哈萨克斯坦语</span><span class="sxs-lookup"><span data-stu-id="c173a-219">Kazakh</span></span>
- <span data-ttu-id="c173a-220">斯瓦希里语</span><span class="sxs-lookup"><span data-stu-id="c173a-220">Kiswahili</span></span>
- <span data-ttu-id="c173a-221">朝鲜语</span><span class="sxs-lookup"><span data-stu-id="c173a-221">Korean</span></span>
- <span data-ttu-id="c173a-222">拉脱维亚语</span><span class="sxs-lookup"><span data-stu-id="c173a-222">Latvian</span></span>
- <span data-ttu-id="c173a-223">立陶宛语</span><span class="sxs-lookup"><span data-stu-id="c173a-223">Lithuanian</span></span>
- <span data-ttu-id="c173a-224">马来语（文莱达鲁萨兰国）</span><span class="sxs-lookup"><span data-stu-id="c173a-224">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="c173a-225">马来语（马来西亚）</span><span class="sxs-lookup"><span data-stu-id="c173a-225">Malay (Malaysia)</span></span>
- <span data-ttu-id="c173a-226">马拉雅拉姆语</span><span class="sxs-lookup"><span data-stu-id="c173a-226">Malayalam</span></span>
- <span data-ttu-id="c173a-227">马拉地语</span><span class="sxs-lookup"><span data-stu-id="c173a-227">Marathi</span></span>
- <span data-ttu-id="c173a-228">挪威语（博克马尔）</span><span class="sxs-lookup"><span data-stu-id="c173a-228">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="c173a-229">挪威语（尼诺斯克语）</span><span class="sxs-lookup"><span data-stu-id="c173a-229">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="c173a-230">奥里雅语</span><span class="sxs-lookup"><span data-stu-id="c173a-230">Oriya</span></span>
- <span data-ttu-id="c173a-231">波斯语</span><span class="sxs-lookup"><span data-stu-id="c173a-231">Persian</span></span>
- <span data-ttu-id="c173a-232">波兰语</span><span class="sxs-lookup"><span data-stu-id="c173a-232">Polish</span></span>
- <span data-ttu-id="c173a-233">葡萄牙语（巴西）</span><span class="sxs-lookup"><span data-stu-id="c173a-233">Portuguese (Brazil)</span></span>
- <span data-ttu-id="c173a-234">葡萄牙语（葡萄牙）</span><span class="sxs-lookup"><span data-stu-id="c173a-234">Portuguese (Portugal)</span></span>
- <span data-ttu-id="c173a-235">罗马尼亚语</span><span class="sxs-lookup"><span data-stu-id="c173a-235">Romanian</span></span>
- <span data-ttu-id="c173a-236">俄语</span><span class="sxs-lookup"><span data-stu-id="c173a-236">Russian</span></span>
- <span data-ttu-id="c173a-237">塞尔维亚语（西里尔文，塞尔维亚）</span><span class="sxs-lookup"><span data-stu-id="c173a-237">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="c173a-238">塞尔维亚语（拉丁文）</span><span class="sxs-lookup"><span data-stu-id="c173a-238">Serbian (Latin)</span></span>
- <span data-ttu-id="c173a-239">斯洛伐克语</span><span class="sxs-lookup"><span data-stu-id="c173a-239">Slovak</span></span>
- <span data-ttu-id="c173a-240">斯洛文尼亚语</span><span class="sxs-lookup"><span data-stu-id="c173a-240">Slovenian</span></span>
- <span data-ttu-id="c173a-241">西班牙语</span><span class="sxs-lookup"><span data-stu-id="c173a-241">Spanish</span></span>
- <span data-ttu-id="c173a-242">瑞典语</span><span class="sxs-lookup"><span data-stu-id="c173a-242">Swedish</span></span>
- <span data-ttu-id="c173a-243">泰米尔语</span><span class="sxs-lookup"><span data-stu-id="c173a-243">Tamil</span></span>
- <span data-ttu-id="c173a-244">泰卢固语</span><span class="sxs-lookup"><span data-stu-id="c173a-244">Telugu</span></span>
- <span data-ttu-id="c173a-245">泰语</span><span class="sxs-lookup"><span data-stu-id="c173a-245">Thai</span></span>
- <span data-ttu-id="c173a-246">土耳其语</span><span class="sxs-lookup"><span data-stu-id="c173a-246">Turkish</span></span>
- <span data-ttu-id="c173a-247">乌克兰语</span><span class="sxs-lookup"><span data-stu-id="c173a-247">Ukrainian</span></span>
- <span data-ttu-id="c173a-248">乌尔都语</span><span class="sxs-lookup"><span data-stu-id="c173a-248">Urdu</span></span>
- <span data-ttu-id="c173a-249">越南语</span><span class="sxs-lookup"><span data-stu-id="c173a-249">Vietnamese</span></span>
- <span data-ttu-id="c173a-250">威尔士语</span><span class="sxs-lookup"><span data-stu-id="c173a-250">Welsh</span></span>
