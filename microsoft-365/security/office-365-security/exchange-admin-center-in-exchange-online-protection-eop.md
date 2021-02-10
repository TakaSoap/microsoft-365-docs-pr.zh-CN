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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: 了解独立 Exchange Online Protection 中的 Web 管理界面 (EOP) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 81af6c64d2ec3204d0c9d46888bbfe21335955bd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166215"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="523eb-103">独立 EOP 中的 Exchange 管理中心</span><span class="sxs-lookup"><span data-stu-id="523eb-103">Exchange admin center in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="523eb-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="523eb-104">**Applies to**</span></span>
-  [<span data-ttu-id="523eb-105">独立 Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="523eb-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="523eb-106">Exchange 管理中心 (EAC) 是一个基于 Web 的管理控制台，适用于独立 Exchange Online Protection (EOP) 。</span><span class="sxs-lookup"><span data-stu-id="523eb-106">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="523eb-107">正在查找此主题的 Exchange Online 版本？</span><span class="sxs-lookup"><span data-stu-id="523eb-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="523eb-108">请参阅 [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="523eb-108">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="523eb-109">在 EOP 中打开 EAC</span><span class="sxs-lookup"><span data-stu-id="523eb-109">Open the EAC in EOP</span></span>

<span data-ttu-id="523eb-110">独立 EOP 客户可以通过以下方法访问 EAC：</span><span class="sxs-lookup"><span data-stu-id="523eb-110">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="523eb-111">**从 Microsoft 365 管理中心**：</span><span class="sxs-lookup"><span data-stu-id="523eb-111">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="523eb-112">转到并 <https://admin.microsoft.com> 单击"**全部显示"。**</span><span class="sxs-lookup"><span data-stu-id="523eb-112">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![单击"在 Microsoft 365 管理中心中全部显示"](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="523eb-114">在出现的 **"管理中心**"部分，单击 **"所有管理中心"。**</span><span class="sxs-lookup"><span data-stu-id="523eb-114">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![单击 Microsoft 365 管理中心中的"所有管理中心"](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="523eb-116">在出现的 **"所有管理** 中心"页上，单击 **"Exchange Online Protection"。**</span><span class="sxs-lookup"><span data-stu-id="523eb-116">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="523eb-117">直接转到 `https://admin.protection.outlook.com/ecp/` 。</span><span class="sxs-lookup"><span data-stu-id="523eb-117">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="523eb-118">EOP 中 EAC 中的常见用户界面元素</span><span class="sxs-lookup"><span data-stu-id="523eb-118">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="523eb-119">本部分将介绍 EAC 中的用户界面元素。</span><span class="sxs-lookup"><span data-stu-id="523eb-119">This section describes the user interface elements that are found in the EAC.</span></span>

![Exchange Online Protection 中的 Exchange 管理中心](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="523eb-121">功能窗格</span><span class="sxs-lookup"><span data-stu-id="523eb-121">Feature Pane</span></span>

<span data-ttu-id="523eb-p102">这是您要在 EAC 中执行的大部分任务的第一级导航。功能窗格按功能区域组织。</span><span class="sxs-lookup"><span data-stu-id="523eb-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="523eb-124">**收件人**：这是查看组和外部联系人的地方。</span><span class="sxs-lookup"><span data-stu-id="523eb-124">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="523eb-125">**权限**：你将在此管理管理员角色。</span><span class="sxs-lookup"><span data-stu-id="523eb-125">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="523eb-126">**合规性管理**：你可以在这里找到管理员角色组报告和管理审核日志报告。</span><span class="sxs-lookup"><span data-stu-id="523eb-126">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="523eb-127">**保护**：这是你可以管理反恶意软件策略、默认连接筛选器策略和 DKIM 的地方。</span><span class="sxs-lookup"><span data-stu-id="523eb-127">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="523eb-128">您应该在安全与合规中心内管理反恶意软件策略和&筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="523eb-128">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="523eb-129">有关详细信息，请参阅"在 EOP 中配置[反恶意软件](configure-anti-malware-policies.md)策略"和"[在 EOP 中配置连接筛选"。](configure-the-connection-filter-policy.md)</span><span class="sxs-lookup"><span data-stu-id="523eb-129">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="523eb-130">**邮件** 流：这是管理邮件流规则的位置 (也称为传输规则) 、接受域和连接器，以及可以运行邮件跟踪的位置。</span><span class="sxs-lookup"><span data-stu-id="523eb-130">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="523eb-131">**混合**：这是您可以运行混合配置 [向导](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)，并可以安装 [Exchange Online PowerShell 模块的地方](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="523eb-131">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="523eb-132">选项卡</span><span class="sxs-lookup"><span data-stu-id="523eb-132">Tabs</span></span>

<span data-ttu-id="523eb-p104">选项卡是导航的第二级。每个功能区都包含各种选项卡，每种选项卡代表一项功能。</span><span class="sxs-lookup"><span data-stu-id="523eb-p104">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="523eb-135">工具栏</span><span class="sxs-lookup"><span data-stu-id="523eb-135">Toolbar</span></span>

<span data-ttu-id="523eb-p105">单击大多数选项卡时，将看到一个工具栏。工具栏包含执行特定操作的图标。下表介绍图标及其操作。</span><span class="sxs-lookup"><span data-stu-id="523eb-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="523eb-139">图标</span><span class="sxs-lookup"><span data-stu-id="523eb-139">Icon</span></span>|<span data-ttu-id="523eb-140">名称</span><span class="sxs-lookup"><span data-stu-id="523eb-140">Name</span></span>|<span data-ttu-id="523eb-141">Action</span><span class="sxs-lookup"><span data-stu-id="523eb-141">Action</span></span>|
|---|---|---|
|![添加图标](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="523eb-143">添加、新建</span><span class="sxs-lookup"><span data-stu-id="523eb-143">Add, New</span></span>|<span data-ttu-id="523eb-p106">使用此图标可创建一个新对象。其中一些图标有关联的向下箭头，单击该箭头会显示可以创建的其他对象。</span><span class="sxs-lookup"><span data-stu-id="523eb-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![编辑图标](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="523eb-147">编辑</span><span class="sxs-lookup"><span data-stu-id="523eb-147">Edit</span></span>|<span data-ttu-id="523eb-148">使用此图标可编辑对象。</span><span class="sxs-lookup"><span data-stu-id="523eb-148">Use this icon to edit an object.</span></span>|
|![删除图标](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="523eb-150">删除</span><span class="sxs-lookup"><span data-stu-id="523eb-150">Delete</span></span>|<span data-ttu-id="523eb-p107">使用此图标可删除对象。有些删除图标有一个向下箭头，单击该箭头可显示其他选项。</span><span class="sxs-lookup"><span data-stu-id="523eb-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![搜索图标](../../media/ITPro-EAC-.gif)|<span data-ttu-id="523eb-154">搜索</span><span class="sxs-lookup"><span data-stu-id="523eb-154">Search</span></span>|<span data-ttu-id="523eb-155">使用此图标可打开一个搜索框，可在其中键入要查找的对象的搜索短语。</span><span class="sxs-lookup"><span data-stu-id="523eb-155">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![刷新图标](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="523eb-157">刷新</span><span class="sxs-lookup"><span data-stu-id="523eb-157">Refresh</span></span>|<span data-ttu-id="523eb-158">使用此图标可刷新列表视图。</span><span class="sxs-lookup"><span data-stu-id="523eb-158">Use this icon to refresh the list view.</span></span>|
|![更多选项图标](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="523eb-160">更多选项</span><span class="sxs-lookup"><span data-stu-id="523eb-160">More options</span></span>|<span data-ttu-id="523eb-161">使用此图标可以查看可对该选项卡的对象执行的更多操作。</span><span class="sxs-lookup"><span data-stu-id="523eb-161">Use this icon to view more actions you can perform for that tab's objects.</span></span> <span data-ttu-id="523eb-162">例如，在 **"收件人 \> 用户"中** ，单击此图标将显示执行高级 **搜索的选项**。</span><span class="sxs-lookup"><span data-stu-id="523eb-162">For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![向上键图标](../../media/ITPro-EAC-UpArrowIcon.gif)![向下键图标](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="523eb-165">向上箭头和向下箭头</span><span class="sxs-lookup"><span data-stu-id="523eb-165">Up arrow and down arrow</span></span>|<span data-ttu-id="523eb-166">使用这些图标可以将对象的优先级上移或下移。</span><span class="sxs-lookup"><span data-stu-id="523eb-166">Use these icons to move an object's priority up or down.</span></span>|
|![删除图标](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="523eb-168">删除</span><span class="sxs-lookup"><span data-stu-id="523eb-168">Remove</span></span>|<span data-ttu-id="523eb-169">使用此图标可从列表中删除对象。</span><span class="sxs-lookup"><span data-stu-id="523eb-169">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="523eb-170">列表视图</span><span class="sxs-lookup"><span data-stu-id="523eb-170">List View</span></span>

<span data-ttu-id="523eb-p109">选择某个选项卡时，在大多数情况下，将会看到一个列表视图。EAC 列表视图的可查看限制大约为 10,000 个对象。此外还包括了分页功能，因此可以对结果进行分页。</span><span class="sxs-lookup"><span data-stu-id="523eb-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="523eb-174">详细信息窗格</span><span class="sxs-lookup"><span data-stu-id="523eb-174">Details Pane</span></span>

<span data-ttu-id="523eb-p110">从列表视图中选择对象时，有关该对象的信息将在详细信息窗格中显示。在某些情况下，详细信息窗格包括管理任务。</span><span class="sxs-lookup"><span data-stu-id="523eb-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="523eb-177">自有图块和帮助</span><span class="sxs-lookup"><span data-stu-id="523eb-177">Me tile and Help</span></span>

<span data-ttu-id="523eb-178">使用“自有”图块可以注销 EAC，然后以其他用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="523eb-178">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="523eb-179">在 **"** ![ 帮助帮助图标 ](../../media/ITPro-EAC-HelpIcon.gif) "下拉菜单中，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="523eb-179">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can do the following actions:</span></span>

- <span data-ttu-id="523eb-180">**帮助**： ![ 单击"帮助图标 ](../../media/ITPro-EAC-HelpIcon.gif) "查看联机帮助内容。</span><span class="sxs-lookup"><span data-stu-id="523eb-180">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>
- <span data-ttu-id="523eb-181">**反馈**：留下反馈。</span><span class="sxs-lookup"><span data-stu-id="523eb-181">**Feedback**: Leave feedback.</span></span>
- <span data-ttu-id="523eb-182">**社区**：在社区论坛中发布问题以查找答案。</span><span class="sxs-lookup"><span data-stu-id="523eb-182">**Community**: Post a question for find answers in the community forums.</span></span>
- <span data-ttu-id="523eb-183">**禁用帮助气泡**：创建或编辑对象时，帮助气泡显示字段的上下文帮助。</span><span class="sxs-lookup"><span data-stu-id="523eb-183">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="523eb-184">您可以关闭"帮助"气泡，如果已被禁用，也可以打开它。</span><span class="sxs-lookup"><span data-stu-id="523eb-184">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>
- <span data-ttu-id="523eb-185">**显示命令日志记录**：将打开一个新窗口，根据在 EAC 中配置的命令显示等效的 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="523eb-185">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="523eb-186">支持的浏览器</span><span class="sxs-lookup"><span data-stu-id="523eb-186">Supported Browsers</span></span>

<span data-ttu-id="523eb-187">若要获得最佳的 EAC 使用体验，我们建议您始终使用最新的浏览器、Office 客户端和应用程序。</span><span class="sxs-lookup"><span data-stu-id="523eb-187">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="523eb-188">我们还建议您安装可用的软件更新。</span><span class="sxs-lookup"><span data-stu-id="523eb-188">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="523eb-189">有关支持的浏览器和服务的系统要求详细信息，请参阅 [Office 的系统要求](https://products.office.com/office-system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="523eb-189">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="523eb-190">支持的语言</span><span class="sxs-lookup"><span data-stu-id="523eb-190">Supported languages</span></span>

<span data-ttu-id="523eb-191">独立 EOP 中的 EAC 支持并可以使用以下语言。</span><span class="sxs-lookup"><span data-stu-id="523eb-191">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="523eb-192">阿姆哈拉语</span><span class="sxs-lookup"><span data-stu-id="523eb-192">Amharic</span></span>
- <span data-ttu-id="523eb-193">阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="523eb-193">Arabic</span></span>
- <span data-ttu-id="523eb-194">巴斯克语（巴斯克）</span><span class="sxs-lookup"><span data-stu-id="523eb-194">Basque (Basque)</span></span>
- <span data-ttu-id="523eb-195">孟加拉语（印度）</span><span class="sxs-lookup"><span data-stu-id="523eb-195">Bengali (India)</span></span>
- <span data-ttu-id="523eb-196">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="523eb-196">Bulgarian</span></span>
- <span data-ttu-id="523eb-197">加泰罗尼亚语</span><span class="sxs-lookup"><span data-stu-id="523eb-197">Catalan</span></span>
- <span data-ttu-id="523eb-198">中文（简体）</span><span class="sxs-lookup"><span data-stu-id="523eb-198">Chinese (Simplified)</span></span>
- <span data-ttu-id="523eb-199">中文（繁体）</span><span class="sxs-lookup"><span data-stu-id="523eb-199">Chinese (Traditional)</span></span>
- <span data-ttu-id="523eb-200">克罗地亚语</span><span class="sxs-lookup"><span data-stu-id="523eb-200">Croatian</span></span>
- <span data-ttu-id="523eb-201">捷克语</span><span class="sxs-lookup"><span data-stu-id="523eb-201">Czech</span></span>
- <span data-ttu-id="523eb-202">丹麦语</span><span class="sxs-lookup"><span data-stu-id="523eb-202">Danish</span></span>
- <span data-ttu-id="523eb-203">荷兰语</span><span class="sxs-lookup"><span data-stu-id="523eb-203">Dutch</span></span>
- <span data-ttu-id="523eb-204">英语</span><span class="sxs-lookup"><span data-stu-id="523eb-204">English</span></span>
- <span data-ttu-id="523eb-205">爱沙尼亚语</span><span class="sxs-lookup"><span data-stu-id="523eb-205">Estonian</span></span>
- <span data-ttu-id="523eb-206">菲律宾语（菲律宾）</span><span class="sxs-lookup"><span data-stu-id="523eb-206">Filipino (Philippines)</span></span>
- <span data-ttu-id="523eb-207">芬兰语</span><span class="sxs-lookup"><span data-stu-id="523eb-207">Finnish</span></span>
- <span data-ttu-id="523eb-208">法语</span><span class="sxs-lookup"><span data-stu-id="523eb-208">French</span></span>
- <span data-ttu-id="523eb-209">加利西亚语</span><span class="sxs-lookup"><span data-stu-id="523eb-209">Galician</span></span>
- <span data-ttu-id="523eb-210">德语</span><span class="sxs-lookup"><span data-stu-id="523eb-210">German</span></span>
- <span data-ttu-id="523eb-211">希腊语</span><span class="sxs-lookup"><span data-stu-id="523eb-211">Greek</span></span>
- <span data-ttu-id="523eb-212">古吉拉特语</span><span class="sxs-lookup"><span data-stu-id="523eb-212">Gujarati</span></span>
- <span data-ttu-id="523eb-213">希伯来语</span><span class="sxs-lookup"><span data-stu-id="523eb-213">Hebrew</span></span>
- <span data-ttu-id="523eb-214">印地语</span><span class="sxs-lookup"><span data-stu-id="523eb-214">Hindi</span></span>
- <span data-ttu-id="523eb-215">匈牙利语</span><span class="sxs-lookup"><span data-stu-id="523eb-215">Hungarian</span></span>
- <span data-ttu-id="523eb-216">冰岛语</span><span class="sxs-lookup"><span data-stu-id="523eb-216">Icelandic</span></span>
- <span data-ttu-id="523eb-217">印度尼西亚语</span><span class="sxs-lookup"><span data-stu-id="523eb-217">Indonesian</span></span>
- <span data-ttu-id="523eb-218">意大利语</span><span class="sxs-lookup"><span data-stu-id="523eb-218">Italian</span></span>
- <span data-ttu-id="523eb-219">日语</span><span class="sxs-lookup"><span data-stu-id="523eb-219">Japanese</span></span>
- <span data-ttu-id="523eb-220">卡纳达语</span><span class="sxs-lookup"><span data-stu-id="523eb-220">Kannada</span></span>
- <span data-ttu-id="523eb-221">哈萨克斯坦语</span><span class="sxs-lookup"><span data-stu-id="523eb-221">Kazakh</span></span>
- <span data-ttu-id="523eb-222">斯瓦希里语</span><span class="sxs-lookup"><span data-stu-id="523eb-222">Kiswahili</span></span>
- <span data-ttu-id="523eb-223">朝鲜语</span><span class="sxs-lookup"><span data-stu-id="523eb-223">Korean</span></span>
- <span data-ttu-id="523eb-224">拉脱维亚语</span><span class="sxs-lookup"><span data-stu-id="523eb-224">Latvian</span></span>
- <span data-ttu-id="523eb-225">立陶宛语</span><span class="sxs-lookup"><span data-stu-id="523eb-225">Lithuanian</span></span>
- <span data-ttu-id="523eb-226">马来语（文莱达鲁萨兰国）</span><span class="sxs-lookup"><span data-stu-id="523eb-226">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="523eb-227">马来语（马来西亚）</span><span class="sxs-lookup"><span data-stu-id="523eb-227">Malay (Malaysia)</span></span>
- <span data-ttu-id="523eb-228">马拉雅拉姆语</span><span class="sxs-lookup"><span data-stu-id="523eb-228">Malayalam</span></span>
- <span data-ttu-id="523eb-229">马拉地语</span><span class="sxs-lookup"><span data-stu-id="523eb-229">Marathi</span></span>
- <span data-ttu-id="523eb-230">挪威语（博克马尔）</span><span class="sxs-lookup"><span data-stu-id="523eb-230">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="523eb-231">挪威语（尼诺斯克语）</span><span class="sxs-lookup"><span data-stu-id="523eb-231">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="523eb-232">奥里雅语</span><span class="sxs-lookup"><span data-stu-id="523eb-232">Oriya</span></span>
- <span data-ttu-id="523eb-233">波斯语</span><span class="sxs-lookup"><span data-stu-id="523eb-233">Persian</span></span>
- <span data-ttu-id="523eb-234">波兰语</span><span class="sxs-lookup"><span data-stu-id="523eb-234">Polish</span></span>
- <span data-ttu-id="523eb-235">葡萄牙语（巴西）</span><span class="sxs-lookup"><span data-stu-id="523eb-235">Portuguese (Brazil)</span></span>
- <span data-ttu-id="523eb-236">葡萄牙语（葡萄牙）</span><span class="sxs-lookup"><span data-stu-id="523eb-236">Portuguese (Portugal)</span></span>
- <span data-ttu-id="523eb-237">罗马尼亚语</span><span class="sxs-lookup"><span data-stu-id="523eb-237">Romanian</span></span>
- <span data-ttu-id="523eb-238">俄语</span><span class="sxs-lookup"><span data-stu-id="523eb-238">Russian</span></span>
- <span data-ttu-id="523eb-239">塞尔维亚语（西里尔文，塞尔维亚）</span><span class="sxs-lookup"><span data-stu-id="523eb-239">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="523eb-240">塞尔维亚语（拉丁文）</span><span class="sxs-lookup"><span data-stu-id="523eb-240">Serbian (Latin)</span></span>
- <span data-ttu-id="523eb-241">斯洛伐克语</span><span class="sxs-lookup"><span data-stu-id="523eb-241">Slovak</span></span>
- <span data-ttu-id="523eb-242">斯洛文尼亚语</span><span class="sxs-lookup"><span data-stu-id="523eb-242">Slovenian</span></span>
- <span data-ttu-id="523eb-243">西班牙语</span><span class="sxs-lookup"><span data-stu-id="523eb-243">Spanish</span></span>
- <span data-ttu-id="523eb-244">瑞典语</span><span class="sxs-lookup"><span data-stu-id="523eb-244">Swedish</span></span>
- <span data-ttu-id="523eb-245">泰米尔语</span><span class="sxs-lookup"><span data-stu-id="523eb-245">Tamil</span></span>
- <span data-ttu-id="523eb-246">泰卢固语</span><span class="sxs-lookup"><span data-stu-id="523eb-246">Telugu</span></span>
- <span data-ttu-id="523eb-247">泰语</span><span class="sxs-lookup"><span data-stu-id="523eb-247">Thai</span></span>
- <span data-ttu-id="523eb-248">土耳其语</span><span class="sxs-lookup"><span data-stu-id="523eb-248">Turkish</span></span>
- <span data-ttu-id="523eb-249">乌克兰语</span><span class="sxs-lookup"><span data-stu-id="523eb-249">Ukrainian</span></span>
- <span data-ttu-id="523eb-250">乌尔都语</span><span class="sxs-lookup"><span data-stu-id="523eb-250">Urdu</span></span>
- <span data-ttu-id="523eb-251">越南语</span><span class="sxs-lookup"><span data-stu-id="523eb-251">Vietnamese</span></span>
- <span data-ttu-id="523eb-252">威尔士语</span><span class="sxs-lookup"><span data-stu-id="523eb-252">Welsh</span></span>
