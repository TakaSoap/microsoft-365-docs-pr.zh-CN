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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 内容资源管理器可用于在本机查看标记的项目。
ms.openlocfilehash: 19ad68d3c32046754e366919e8c4e66336945624
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080721"
---
# <a name="get-started-with-content-explorer"></a><span data-ttu-id="70d9a-103">内容资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="70d9a-103">Get started with content explorer</span></span>

<span data-ttu-id="70d9a-104">数据分类内容资源管理器可以在本机查看“概述”页上汇总的项目。</span><span class="sxs-lookup"><span data-stu-id="70d9a-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

![内容资源管理器折叠的屏幕截图](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a><span data-ttu-id="70d9a-106">必备条件</span><span class="sxs-lookup"><span data-stu-id="70d9a-106">Prerequisites</span></span>

<span data-ttu-id="70d9a-107">访问和使用数据分类的每个帐户，都必须拥有从以下其中一个订阅向其分配的许可证：</span><span class="sxs-lookup"><span data-stu-id="70d9a-107">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="70d9a-108">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="70d9a-108">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="70d9a-109">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="70d9a-109">Office 365 (E5)</span></span>
- <span data-ttu-id="70d9a-110">高级合规性（E5）加载项</span><span class="sxs-lookup"><span data-stu-id="70d9a-110">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="70d9a-111">高级威胁智能（E5）加载项</span><span class="sxs-lookup"><span data-stu-id="70d9a-111">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="70d9a-112">Microsoft 365 E5/A5 信息保护和管控</span><span class="sxs-lookup"><span data-stu-id="70d9a-112">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="70d9a-113">Microsoft 365 E5/A5 合规</span><span class="sxs-lookup"><span data-stu-id="70d9a-113">Microsoft 365 E5/A5 Compliance</span></span>


### <a name="permissions"></a><span data-ttu-id="70d9a-114">权限</span><span class="sxs-lookup"><span data-stu-id="70d9a-114">Permissions</span></span>

<span data-ttu-id="70d9a-115">若要访问“内容资源管理器”选项卡，必须在其中任一角色或角色组中向帐户分配成员身份。</span><span class="sxs-lookup"><span data-stu-id="70d9a-115">In order to get access to the content explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span> 

<span data-ttu-id="70d9a-116">**Microsoft 365 角色组**</span><span class="sxs-lookup"><span data-stu-id="70d9a-116">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="70d9a-117">全局管理员</span><span class="sxs-lookup"><span data-stu-id="70d9a-117">Global administrator</span></span>
- <span data-ttu-id="70d9a-118">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="70d9a-118">Compliance administrator</span></span>
- <span data-ttu-id="70d9a-119">安全管理员</span><span class="sxs-lookup"><span data-stu-id="70d9a-119">Security administrator</span></span>
- <span data-ttu-id="70d9a-120">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="70d9a-120">Compliance data administrator</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70d9a-121">这些角色组中的成员身份不允许你查看内容资源管理器中项目的列表，或查看内容资源管理器中项目的内容。</span><span class="sxs-lookup"><span data-stu-id="70d9a-121">Membership in these role groups does not allow you to view the list of items in content explorer or to view the contents of the items in content explorer.</span></span>

### <a name="required-permissions-to-access-items-in-content-explorer"></a><span data-ttu-id="70d9a-122">在内容资源管理器中访问项目所需的权限</span><span class="sxs-lookup"><span data-stu-id="70d9a-122">Required permissions to access items in content explorer</span></span>

<span data-ttu-id="70d9a-123">对内容资源管理器的访问权限受到高度限制，因为它允许你读取已扫描文件的内容。</span><span class="sxs-lookup"><span data-stu-id="70d9a-123">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70d9a-124">这些权限会替代本地分配给项目的权限，后者允许查看内容。</span><span class="sxs-lookup"><span data-stu-id="70d9a-124">These permissions supercede permissions that are locally assigned to the items, which allows viewing of the content.</span></span> 

<span data-ttu-id="70d9a-125">有两个角色已授予内容资源管理器的访问权限，并且使用 [microsoft 安全与合规中心](https://protection.office.com/permissions) 授予：</span><span class="sxs-lookup"><span data-stu-id="70d9a-125">There are two roles that grant access to content explorer and it is granted using the [Microsoft Security & Compliance Center](https://protection.office.com/permissions):</span></span>

- <span data-ttu-id="70d9a-126">**内容资源管理器列表查看员**：此角色组的成员资格允许你在列表视图中查看每个项目及其位置。</span><span class="sxs-lookup"><span data-stu-id="70d9a-126">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location in list view.</span></span> <span data-ttu-id="70d9a-127">已为此角色组预分配 `data classification list viewer` 角色。</span><span class="sxs-lookup"><span data-stu-id="70d9a-127">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="70d9a-128">**内容资源管理器内容查看器**：此角色组的成员资格允许你查看列表中每个项目的内容。</span><span class="sxs-lookup"><span data-stu-id="70d9a-128">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="70d9a-129">已为此角色组预分配 `data classification content viewer` 角色。</span><span class="sxs-lookup"><span data-stu-id="70d9a-129">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="70d9a-130">用于访问内容资源管理器的帐户必须具有其中一个或两个角色组。</span><span class="sxs-lookup"><span data-stu-id="70d9a-130">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="70d9a-131">这些角色组是独立角色组，不具有累积性。</span><span class="sxs-lookup"><span data-stu-id="70d9a-131">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="70d9a-132">例如，如果要向帐户授予仅查看项目及其位置的权限，则授予内容资源管理器列表查看器的权限。</span><span class="sxs-lookup"><span data-stu-id="70d9a-132">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="70d9a-133">如果你希望同一帐户也能够查看列表中项目的内容，另请授予内容资源管理器内容查看器权限。</span><span class="sxs-lookup"><span data-stu-id="70d9a-133">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="70d9a-134">你还可以将任一个角色或全部两个角色都分配到自定义角色组，以便对内容资源管理器的访问权限进行量身定制。</span><span class="sxs-lookup"><span data-stu-id="70d9a-134">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="70d9a-135">全局管理员、合规性管理员或数据管理员可以分配必要的  内容资源管理器列表查看器  和  内容资源管理器内容查看器  角色组成员身份。</span><span class="sxs-lookup"><span data-stu-id="70d9a-135">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="70d9a-136">内容资源管理器</span><span class="sxs-lookup"><span data-stu-id="70d9a-136">Content explorer</span></span>

<span data-ttu-id="70d9a-137">内容资源管理器可显示具有敏感度标签、保留标签或在你的组织中被归类为敏感信息类型的项目的当前快照。</span><span class="sxs-lookup"><span data-stu-id="70d9a-137">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="70d9a-138">敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="70d9a-138">Sensitive information types</span></span>

<span data-ttu-id="70d9a-139">[DLP 策略](data-loss-prevention-policies.md)可帮助保护定义为 **敏感信息类型** 的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="70d9a-139">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="70d9a-140">Microsoft 365 在多个不同区域包含[适用于众多常用敏感信息类型的定义](sensitive-information-type-entity-definitions.md)，它们随时可供使用。</span><span class="sxs-lookup"><span data-stu-id="70d9a-140">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) from across many different regions that are ready for you to use.</span></span> <span data-ttu-id="70d9a-141">例如，信用卡号、银行帐号、国民身份证号码和 Windows Live ID 服务编号。</span><span class="sxs-lookup"><span data-stu-id="70d9a-141">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

> [!NOTE]
> <span data-ttu-id="70d9a-142">内容资源管理器当前不会扫描 Exchange Online 中的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="70d9a-142">Content explorer doesn't currently scan for sensitive information types in Exchange Online.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="70d9a-143">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="70d9a-143">Sensitivity labels</span></span>

<span data-ttu-id="70d9a-144">[灵敏度标签](sensitivity-labels.md)只是一个标记，指出项目对你的组织的价值。</span><span class="sxs-lookup"><span data-stu-id="70d9a-144">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="70d9a-145">该标签可手动应用，也可自动应用。</span><span class="sxs-lookup"><span data-stu-id="70d9a-145">It can be applied manually, or automatically.</span></span> <span data-ttu-id="70d9a-146">应用后，它将嵌入到文档中并始终保留在文档上。</span><span class="sxs-lookup"><span data-stu-id="70d9a-146">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="70d9a-147">可通过敏感度标签实现各种保护行为，例如强制水印或加密。</span><span class="sxs-lookup"><span data-stu-id="70d9a-147">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span>

<span data-ttu-id="70d9a-148">必须为 SharePoint 和 OneDrive 中的文件启用灵敏度标签，以使相应的数据出现在数据分类页面中。</span><span class="sxs-lookup"><span data-stu-id="70d9a-148">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="70d9a-149">有关详细信息，请参阅[启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="70d9a-149">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="70d9a-150">保留标签</span><span class="sxs-lookup"><span data-stu-id="70d9a-150">Retention labels</span></span>

<span data-ttu-id="70d9a-151">[保留标签](retention.md)可用于定义带标记的项目将保留多长时间以及删除项目前要采取哪些操作。</span><span class="sxs-lookup"><span data-stu-id="70d9a-151">A [retention label](retention.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="70d9a-152">这些标签可手动应用，也可通过策略自动应用。</span><span class="sxs-lookup"><span data-stu-id="70d9a-152">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="70d9a-153">它们在帮助组织持续遵守法律法规要求方面发挥着作用。</span><span class="sxs-lookup"><span data-stu-id="70d9a-153">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="70d9a-154">如何使用内容资源管理器</span><span class="sxs-lookup"><span data-stu-id="70d9a-154">How to use content explorer</span></span>

1. <span data-ttu-id="70d9a-155">打开“**Microsoft 365 合规中心**”  > “**数据分类**” > “**内容资源管理器**”。</span><span class="sxs-lookup"><span data-stu-id="70d9a-155">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="70d9a-156">如果知道标签的名称或敏感信息类型，可将其键入筛选框。</span><span class="sxs-lookup"><span data-stu-id="70d9a-156">If you know the name of the label, or the sensitive information type, you can type that into the filter box.</span></span>
3. <span data-ttu-id="70d9a-157">或者，你可以通过展开标签类型并从列表中选择标签来浏览该项目。</span><span class="sxs-lookup"><span data-stu-id="70d9a-157">Alternately, you can browse for the item by expanding the label type and selecting the label from the list.</span></span>
4. <span data-ttu-id="70d9a-158">选择“**所有**”位置下的某个位置，然后向下钻取文件夹结构到该项目。</span><span class="sxs-lookup"><span data-stu-id="70d9a-158">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="70d9a-159">双击以在本机上打开内容资源管理器中的项目。</span><span class="sxs-lookup"><span data-stu-id="70d9a-159">Double-click to open the item natively in content explorer.</span></span>

### <a name="export"></a><span data-ttu-id="70d9a-160">导出</span><span class="sxs-lookup"><span data-stu-id="70d9a-160">Export</span></span>
<span data-ttu-id="70d9a-161">**导出** 控件将创建一个 .csv 文件，其中包含“**所有位置**”窗格中显示的所有内容的列表。</span><span class="sxs-lookup"><span data-stu-id="70d9a-161">The **export** control will create a .csv file that contains a listing of whatever is showing in the **All locations** pane.</span></span>

![数据分类导出控件](../media/data_classification_export_control.png)


### <a name="search"></a><span data-ttu-id="70d9a-163">搜索</span><span class="sxs-lookup"><span data-stu-id="70d9a-163">Search</span></span>

<span data-ttu-id="70d9a-164">向下钻取到某个位置（例如 Exchange 文件夹，或者 SharePoint 或 OneDrive 网站）时，将显示 **搜索** 工具。</span><span class="sxs-lookup"><span data-stu-id="70d9a-164">When you drill down into a location, such as an Exchange folder, or a SharePoint or OneDrive site, the **search** tool appears.</span></span>

![内容浏览器搜索工具](../media/data_classification_search_tool.png)


<span data-ttu-id="70d9a-166">搜索工具的范围是“**所有位置**”窗格中显示的内容和可搜索的内容，具体取决于所选位置。</span><span class="sxs-lookup"><span data-stu-id="70d9a-166">The scope of the search tool is what is displaying in the **All locations** pane and what you can search on varies depending on the selected location.</span></span> 

<span data-ttu-id="70d9a-167">如果所选位置为 **Exchange**，则可搜索邮箱的完整电子邮件地址，例如 `user@domainname.com`。</span><span class="sxs-lookup"><span data-stu-id="70d9a-167">When **Exchange** is the selected location, you can search on the full email address of the mailbox, for example `user@domainname.com`.</span></span>

<span data-ttu-id="70d9a-168">如果所选位置为 **SharePoint** 或 **OneDrive**，当你向下钻取到网站名称、文件夹和文件时，将显示搜索工具。</span><span class="sxs-lookup"><span data-stu-id="70d9a-168">When either **SharePoint** or **OneDrive** are selected location, the search tool will appear when you drill down to site names, folders and files.</span></span> 

> [!NOTE]
> <span data-ttu-id="70d9a-169">**OneDrive** 我们在预览计划中听取了有关 OneDrive 集成的宝贵反馈。</span><span class="sxs-lookup"><span data-stu-id="70d9a-169">**OneDrive** We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="70d9a-170">根据这些反馈，OneDrive 功能将保留在预览中，直到所有修补程序均已就位。</span><span class="sxs-lookup"><span data-stu-id="70d9a-170">Based on that feedback, the OneDrive functionality will remain in preview till all fixes are in place.</span></span> <span data-ttu-id="70d9a-171">根据你的租户，某些客户可能无法将 OneDrive 视为位置。</span><span class="sxs-lookup"><span data-stu-id="70d9a-171">Depending on your tenant, some customers may not see OneDrive as a location.</span></span> <span data-ttu-id="70d9a-172">非常感谢你在这方面的持续支持。</span><span class="sxs-lookup"><span data-stu-id="70d9a-172">We appreciate your continued support on this.</span></span>

<span data-ttu-id="70d9a-173">可搜索：</span><span class="sxs-lookup"><span data-stu-id="70d9a-173">You can search on:</span></span>


|<span data-ttu-id="70d9a-174">值</span><span class="sxs-lookup"><span data-stu-id="70d9a-174">value</span></span>|<span data-ttu-id="70d9a-175">示例</span><span class="sxs-lookup"><span data-stu-id="70d9a-175">example</span></span>  |
|---------|---------|
|<span data-ttu-id="70d9a-176">完整网站名称</span><span class="sxs-lookup"><span data-stu-id="70d9a-176">full site name</span></span>    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|<span data-ttu-id="70d9a-177">根文件夹名称 - 获取所有子文件夹</span><span class="sxs-lookup"><span data-stu-id="70d9a-177">root folder name - gets all subfolders</span></span>    | `/sites`        |
|<span data-ttu-id="70d9a-178">文件名</span><span class="sxs-lookup"><span data-stu-id="70d9a-178">file name</span></span>    |    `RES_Resume_1234.txt`     |
|<span data-ttu-id="70d9a-179">文件名开头的文本</span><span class="sxs-lookup"><span data-stu-id="70d9a-179">text at the beginning of file name</span></span>| `RES`|
|<span data-ttu-id="70d9a-180">文件名中下划线字符 ( _ ) 后面的文本</span><span class="sxs-lookup"><span data-stu-id="70d9a-180">text after an underscore character ( _ ) in file name</span></span>|<span data-ttu-id="70d9a-181">`Resume` 或 `1234`</span><span class="sxs-lookup"><span data-stu-id="70d9a-181">`Resume` or `1234`</span></span>| 
|<span data-ttu-id="70d9a-182">文件扩展名</span><span class="sxs-lookup"><span data-stu-id="70d9a-182">file extension</span></span>|`txt`|


## <a name="see-also"></a><span data-ttu-id="70d9a-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70d9a-183">See also</span></span>

- [<span data-ttu-id="70d9a-184">了解敏感度标签</span><span class="sxs-lookup"><span data-stu-id="70d9a-184">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="70d9a-185">了解保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="70d9a-185">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="70d9a-186">敏感信息类型实体定义.md</span><span class="sxs-lookup"><span data-stu-id="70d9a-186">Sensitive information type entity definitions.md</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="70d9a-187">数据丢失防护概述</span><span class="sxs-lookup"><span data-stu-id="70d9a-187">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
