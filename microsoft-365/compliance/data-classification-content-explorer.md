---
title: 内容资源管理器入门
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 内容资源管理器可用于在本机查看标记的项目。
ms.openlocfilehash: 731ae51a02e4a6fbd35b5be7c0bf083c814ddfd3
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327848"
---
# <a name="get-started-with-content-explorer"></a><span data-ttu-id="abe96-103">内容资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="abe96-103">Get started with content explorer</span></span>

<span data-ttu-id="abe96-104">数据分类内容资源管理器可以在本机查看“概述”页上汇总的项目。</span><span class="sxs-lookup"><span data-stu-id="abe96-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

![内容资源管理器折叠的屏幕截图](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a><span data-ttu-id="abe96-106">必备条件</span><span class="sxs-lookup"><span data-stu-id="abe96-106">Prerequisites</span></span>

<span data-ttu-id="abe96-107">访问和使用数据分类的每个帐户，都必须拥有从以下其中一个订阅向其分配的许可证：</span><span class="sxs-lookup"><span data-stu-id="abe96-107">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="abe96-108">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="abe96-108">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="abe96-109">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="abe96-109">Office 365 (E5)</span></span>
- <span data-ttu-id="abe96-110">高级合规性（E5）加载项</span><span class="sxs-lookup"><span data-stu-id="abe96-110">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="abe96-111">高级威胁智能（E5）加载项</span><span class="sxs-lookup"><span data-stu-id="abe96-111">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="abe96-112">权限</span><span class="sxs-lookup"><span data-stu-id="abe96-112">Permissions</span></span>

<span data-ttu-id="abe96-113">若要访问“内容资源管理器”选项卡，必须在其中任一角色或角色组中向帐户分配成员身份。</span><span class="sxs-lookup"><span data-stu-id="abe96-113">In order to get access to the content explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span> 

<span data-ttu-id="abe96-114">[DLP 策略](data-loss-prevention-policies.md)可帮助保护定义为**敏感信息类型**的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="abe96-114">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="abe96-115">Microsoft 365 在多个不同区域包含[适用于众多常用敏感信息类型的定义](sensitive-information-type-entity-definitions.md)它们已准备就绪可供使用。</span><span class="sxs-lookup"><span data-stu-id="abe96-115">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="abe96-116">例如，信用卡号、银行帐号、国民身份证号码和 Windows Live ID 服务编号。</span><span class="sxs-lookup"><span data-stu-id="abe96-116">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

<span data-ttu-id="abe96-117">**Microsoft 365 角色组**</span><span class="sxs-lookup"><span data-stu-id="abe96-117">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="abe96-118">全局管理员</span><span class="sxs-lookup"><span data-stu-id="abe96-118">Global administrator</span></span>
- <span data-ttu-id="abe96-119">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="abe96-119">Compliance administrator</span></span>
- <span data-ttu-id="abe96-120">安全管理员</span><span class="sxs-lookup"><span data-stu-id="abe96-120">Security administrator</span></span>
- <span data-ttu-id="abe96-121">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="abe96-121">Compliance data administrator</span></span>

> [!IMPORTANT]
> <span data-ttu-id="abe96-122">这些角色组中的成员身份不允许你查看内容资源管理器中项目的列表，或查看内容资源管理器中项目的内容。</span><span class="sxs-lookup"><span data-stu-id="abe96-122">Membership in these role groups does not allow you to view the list of items in content explorer or to view the contents of the items in content explorer.</span></span>

### <a name="required-permissions-to-access-items-in-content-explorer"></a><span data-ttu-id="abe96-123">在内容资源管理器中访问项目所需的权限</span><span class="sxs-lookup"><span data-stu-id="abe96-123">Required permissions to access items in content explorer</span></span>

<span data-ttu-id="abe96-124">对内容资源管理器的访问权限受到高度限制，因为它允许你读取已扫描文件的内容。</span><span class="sxs-lookup"><span data-stu-id="abe96-124">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="abe96-125">这些权限会替代本地分配给项目的权限，后者允许查看内容。</span><span class="sxs-lookup"><span data-stu-id="abe96-125">These permissions supercede permissions that are locally assigned to the items, which allows viewing of the content.</span></span> 

<span data-ttu-id="abe96-126">有两个角色可授予对内容资源管理器的访问权限：</span><span class="sxs-lookup"><span data-stu-id="abe96-126">There are two roles that grant access to content explorer:</span></span>

- <span data-ttu-id="abe96-127">**内容资源管理器列表查看员**：此角色组的成员资格允许你在列表视图中查看每个项目及其位置。</span><span class="sxs-lookup"><span data-stu-id="abe96-127">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location in list view.</span></span> <span data-ttu-id="abe96-128">已为此角色组预分配 `data classification list viewer` 角色。</span><span class="sxs-lookup"><span data-stu-id="abe96-128">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="abe96-129">**内容资源管理器内容查看器**：此角色组的成员资格允许你查看列表中每个项目的内容。</span><span class="sxs-lookup"><span data-stu-id="abe96-129">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="abe96-130">已为此角色组预分配 `data classification content viewer` 角色。</span><span class="sxs-lookup"><span data-stu-id="abe96-130">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="abe96-131">用于访问内容资源管理器的帐户必须具有其中一个或两个角色组。</span><span class="sxs-lookup"><span data-stu-id="abe96-131">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="abe96-132">这些角色组是独立角色组，不具有累积性。</span><span class="sxs-lookup"><span data-stu-id="abe96-132">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="abe96-133">例如，如果要向帐户授予仅查看项目及其位置的权限，则授予内容资源管理器列表查看器的权限。</span><span class="sxs-lookup"><span data-stu-id="abe96-133">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="abe96-134">如果你希望同一帐户也能够查看列表中项目的内容，另请授予内容资源管理器内容查看器权限。</span><span class="sxs-lookup"><span data-stu-id="abe96-134">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="abe96-135">你还可以将任一个角色或全部两个角色都分配到自定义角色组，以便对内容资源管理器的访问权限进行量身定制。</span><span class="sxs-lookup"><span data-stu-id="abe96-135">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="abe96-136">全局管理员、合规性管理员或数据管理员可以分配必要的  内容资源管理器列表查看器  和  内容资源管理器内容查看器  角色组成员身份。</span><span class="sxs-lookup"><span data-stu-id="abe96-136">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="abe96-137">内容资源管理器</span><span class="sxs-lookup"><span data-stu-id="abe96-137">Content explorer</span></span>

<span data-ttu-id="abe96-138">内容资源管理器可显示具有敏感度标签、保留标签或在你的组织中被归类为敏感信息类型的项目的当前快照。</span><span class="sxs-lookup"><span data-stu-id="abe96-138">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="abe96-139">敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="abe96-139">Sensitive information types</span></span>

<span data-ttu-id="abe96-140">[DLP 策略](data-loss-prevention-policies.md)可帮助保护定义为**敏感信息类型**的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="abe96-140">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="abe96-141">Microsoft 365 在多个不同区域包含[适用于众多常用敏感信息类型的定义](sensitive-information-type-entity-definitions.md)，它们随时可供使用。</span><span class="sxs-lookup"><span data-stu-id="abe96-141">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) from across many different regions that are ready for you to use.</span></span> <span data-ttu-id="abe96-142">例如，信用卡号、银行帐号、国民身份证号码和 Windows Live ID 服务编号。</span><span class="sxs-lookup"><span data-stu-id="abe96-142">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

> [!NOTE]
> <span data-ttu-id="abe96-143">内容资源管理器当前不会扫描 Exchange Online 中的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="abe96-143">Content explorer doesn't currently scan for sensitive information types in Exchange Online.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="abe96-144">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="abe96-144">Sensitivity labels</span></span>

<span data-ttu-id="abe96-145">[灵敏度标签](sensitivity-labels.md)只是一个标记，指出项目对你的组织的价值。</span><span class="sxs-lookup"><span data-stu-id="abe96-145">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="abe96-146">该标签可手动应用，也可自动应用。</span><span class="sxs-lookup"><span data-stu-id="abe96-146">It can be applied manually, or automatically.</span></span> <span data-ttu-id="abe96-147">应用后，它将嵌入到文档中并始终保留在文档上。</span><span class="sxs-lookup"><span data-stu-id="abe96-147">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="abe96-148">可通过敏感度标签实现各种保护行为，例如强制水印或加密。</span><span class="sxs-lookup"><span data-stu-id="abe96-148">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span>

<span data-ttu-id="abe96-149">必须为 SharePoint 和 OneDrive 中的文件启用灵敏度标签，以使相应的数据出现在数据分类页面中。</span><span class="sxs-lookup"><span data-stu-id="abe96-149">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="abe96-150">有关详细信息，请参阅[启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="abe96-150">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="abe96-151">保留标签</span><span class="sxs-lookup"><span data-stu-id="abe96-151">Retention labels</span></span>

<span data-ttu-id="abe96-152">[保留标签](labels.md)可用于定义带标记的项目将保留多长时间以及删除项目前要采取哪些操作。</span><span class="sxs-lookup"><span data-stu-id="abe96-152">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="abe96-153">这些标签可手动应用，也可通过策略自动应用。</span><span class="sxs-lookup"><span data-stu-id="abe96-153">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="abe96-154">它们在帮助组织持续遵守法律法规要求方面发挥着作用。</span><span class="sxs-lookup"><span data-stu-id="abe96-154">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="abe96-155">如何使用内容资源管理器</span><span class="sxs-lookup"><span data-stu-id="abe96-155">How to use content explorer</span></span>

1. <span data-ttu-id="abe96-156">打开“**Microsoft 365 合规中心**”  > “**数据分类**” > “**内容资源管理器**”。</span><span class="sxs-lookup"><span data-stu-id="abe96-156">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="abe96-157">如果知道标签的名称或敏感信息类型，可将其键入筛选框。</span><span class="sxs-lookup"><span data-stu-id="abe96-157">If you know the name of the label, or the sensitive information type, you can type that into the filter box.</span></span>
3. <span data-ttu-id="abe96-158">或者，你可以通过展开标签类型并从列表中选择标签来浏览该项目。</span><span class="sxs-lookup"><span data-stu-id="abe96-158">Alternately, you can browse for the item by expanding the label type and selecting the label from the list.</span></span>
4. <span data-ttu-id="abe96-159">选择“**所有**”位置下的某个位置，然后向下钻取文件夹结构到该项目。</span><span class="sxs-lookup"><span data-stu-id="abe96-159">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="abe96-160">双击以在本机上打开内容资源管理器中的项目。</span><span class="sxs-lookup"><span data-stu-id="abe96-160">Double-click to open the item natively in content explorer.</span></span>

### <a name="export"></a><span data-ttu-id="abe96-161">导出</span><span class="sxs-lookup"><span data-stu-id="abe96-161">Export</span></span>
<span data-ttu-id="abe96-162">**导出**控件将创建一个 .csv 文件，其中包含“**所有位置**”窗格中显示的所有内容的列表。</span><span class="sxs-lookup"><span data-stu-id="abe96-162">The **export** control will create a .csv file that contains a listing of whatever is showing in the **All locations** pane.</span></span>

![数据分类导出控件](../media/data_classification_export_control.png)


### <a name="search"></a><span data-ttu-id="abe96-164">搜索</span><span class="sxs-lookup"><span data-stu-id="abe96-164">Search</span></span>

<span data-ttu-id="abe96-165">向下钻取到某个位置（例如 Exchange 文件夹，或者 SharePoint 或 OneDrive 网站）时，将显示**搜索**工具。</span><span class="sxs-lookup"><span data-stu-id="abe96-165">When you drill down into a location, such as an Exchange folder, or a SharePoint or OneDrive site, the **search** tool appears.</span></span>

![内容浏览器搜索工具](../media/data_classification_search_tool.png)


<span data-ttu-id="abe96-167">搜索工具的范围是“**所有位置**”窗格中显示的内容和可搜索的内容，具体取决于所选位置。</span><span class="sxs-lookup"><span data-stu-id="abe96-167">The scope of the search tool is what is displaying in the **All locations** pane and what you can search on varies depending on the selected location.</span></span> 

<span data-ttu-id="abe96-168">如果所选位置为 **Exchange**，则可搜索邮箱的完整电子邮件地址，例如 `user@domainname.com`。</span><span class="sxs-lookup"><span data-stu-id="abe96-168">When **Exchange** is the selected location, you can search on the full email address of the mailbox, for example `user@domainname.com`.</span></span>

<span data-ttu-id="abe96-169">如果所选位置为 **SharePoint** 或 **OneDrive**，当你向下钻取到网站名称、文件夹和文件时，将显示搜索工具。</span><span class="sxs-lookup"><span data-stu-id="abe96-169">When either **SharePoint** or **OneDrive** are selected location, the search tool will appear when you drill down to site names, folders and files.</span></span> 

> [!NOTE]
> <span data-ttu-id="abe96-170">**OneDrive** 我们在预览计划中听取了有关 OneDrive 集成的宝贵反馈。</span><span class="sxs-lookup"><span data-stu-id="abe96-170">**OneDrive** We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="abe96-171">根据这些反馈，OneDrive 功能将保留在预览中，直到所有修补程序均已就位。</span><span class="sxs-lookup"><span data-stu-id="abe96-171">Based on that feedback, the OneDrive functionality will remain in preview till all fixes are in place.</span></span> <span data-ttu-id="abe96-172">根据你的租户，某些客户可能无法将 OneDrive 视为位置。</span><span class="sxs-lookup"><span data-stu-id="abe96-172">Depending on your tenant, some customers may not see OneDrive as a location.</span></span> <span data-ttu-id="abe96-173">非常感谢你在这方面的持续支持。</span><span class="sxs-lookup"><span data-stu-id="abe96-173">We appreciate your continued support on this.</span></span>

<span data-ttu-id="abe96-174">可搜索：</span><span class="sxs-lookup"><span data-stu-id="abe96-174">You can search on:</span></span>


|<span data-ttu-id="abe96-175">值</span><span class="sxs-lookup"><span data-stu-id="abe96-175">value</span></span>|<span data-ttu-id="abe96-176">示例</span><span class="sxs-lookup"><span data-stu-id="abe96-176">example</span></span>  |
|---------|---------|
|<span data-ttu-id="abe96-177">完整网站名称</span><span class="sxs-lookup"><span data-stu-id="abe96-177">full site name</span></span>    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|<span data-ttu-id="abe96-178">根文件夹名称 - 获取所有子文件夹</span><span class="sxs-lookup"><span data-stu-id="abe96-178">root folder name - gets all subfolders</span></span>    | `/sites`        |
|<span data-ttu-id="abe96-179">文件名</span><span class="sxs-lookup"><span data-stu-id="abe96-179">file name</span></span>    |    `RES_Resume_1234.txt`     |
|<span data-ttu-id="abe96-180">文件名开头的文本</span><span class="sxs-lookup"><span data-stu-id="abe96-180">text at the beginning of file name</span></span>| `RES`|
|<span data-ttu-id="abe96-181">文件名中下划线字符 ( _ ) 后面的文本</span><span class="sxs-lookup"><span data-stu-id="abe96-181">text after an underscore character ( _ ) in file name</span></span>|<span data-ttu-id="abe96-182">`Resume` 或 `1234`</span><span class="sxs-lookup"><span data-stu-id="abe96-182">`Resume` or `1234`</span></span>| 
|<span data-ttu-id="abe96-183">文件扩展名</span><span class="sxs-lookup"><span data-stu-id="abe96-183">file extension</span></span>|`txt`|


## <a name="see-also"></a><span data-ttu-id="abe96-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="abe96-184">See also</span></span>

- [<span data-ttu-id="abe96-185">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="abe96-185">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="abe96-186">保留标签</span><span class="sxs-lookup"><span data-stu-id="abe96-186">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="abe96-187">敏感信息类型实体定义.md</span><span class="sxs-lookup"><span data-stu-id="abe96-187">Sensitive information type entity definitions.md</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="abe96-188">保留策略概述</span><span class="sxs-lookup"><span data-stu-id="abe96-188">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="abe96-189">数据丢失防护概述</span><span class="sxs-lookup"><span data-stu-id="abe96-189">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
