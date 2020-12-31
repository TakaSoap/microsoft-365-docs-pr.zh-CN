---
title: 将保管人导入高级电子数据展示案例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 使用导入工具 dto 将多个保管人及其关联的数据源快速添加到高级电子数据展示的案例中。
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740299"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="9fa60-103">将保管人导入高级电子数据展示案例</span><span class="sxs-lookup"><span data-stu-id="9fa60-103">Import custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="9fa60-104">对于涉及许多保管人的高级电子数据展示事例，可以使用 CSV 文件一次导入多个保管人，该文件包含将保管人添加到事例所必需的信息。</span><span class="sxs-lookup"><span data-stu-id="9fa60-104">For Advanced eDiscovery cases that involve many custodians, you can import multiple custodians at once by using a CSV file that contains the information necessary to add them to a case.</span></span>

## <a name="import-custodians"></a><span data-ttu-id="9fa60-105">导入保管人</span><span class="sxs-lookup"><span data-stu-id="9fa60-105">Import custodians</span></span>

1. <span data-ttu-id="9fa60-106">打开高级电子数据展示案例并选择 **"数据源"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9fa60-106">Open the Advanced eDiscovery case and select the **Data sources** tab.</span></span>

2. <span data-ttu-id="9fa60-107">单击 **"添加数据源**  >  **导入保管人"。**</span><span class="sxs-lookup"><span data-stu-id="9fa60-107">Click **Add data source** > **Import custodians**.</span></span>

3. <span data-ttu-id="9fa60-108">在" **导入保管人** "飞出页上，单击"下载 **空白** 模板"以下载保管人模板 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="9fa60-108">On the **Import custodians** flyout page, click **Download a blank template** to download a custodian template CSV file.</span></span>

   ![从导入保管人飞出页面下载 CSV 模板](../media/ImportCustodians1.png)

4. <span data-ttu-id="9fa60-110">将信息添加到 CSV 文件，并将其保存到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="9fa60-110">Add the custodial information to the CSV file and save it to your local computer.</span></span> <span data-ttu-id="9fa60-111">有关 [CSV 文件中](#custodian-csv-file) 所需属性的信息，请参阅 Custodian CSV 文件部分。</span><span class="sxs-lookup"><span data-stu-id="9fa60-111">See the [Custodian CSV file](#custodian-csv-file) section for information about the required properties in the CSV file.</span></span>

5. <span data-ttu-id="9fa60-112">准备好包含保管人信息的 CSV 文件后，返回到"数据源 **"选项卡，** 并再次单击"**添加数据源**  >  **导入保管** 人"。</span><span class="sxs-lookup"><span data-stu-id="9fa60-112">After you've prepared the CSV file with the custodian information, go back to the **Data sources** tab, and click **Add data source** > **Import custodians** again.</span></span>

6. <span data-ttu-id="9fa60-113">在"**导入保管人**"飞出页上，单击"浏览"，然后上载包含保管人信息的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="9fa60-113">On the **Import custodians** flyout page, click **Browse** and then upload the CSV file that contains the custodian information.</span></span>

   <span data-ttu-id="9fa60-114">上载 CSV 文件后，将创建名为 **BulkAddCustodian** 的作业，并将其显示在"作业 **"** 选项卡上。作业验证保管人及其关联的数据源，然后将它们添加到案例的"数据源 **"** 页。</span><span class="sxs-lookup"><span data-stu-id="9fa60-114">After the CSV file is uploaded, a job named **BulkAddCustodian** is created and displayed on the **Jobs** tab. The job validates the custodians and their associated data sources and then adds them to the **Data sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="9fa60-115">保管人 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="9fa60-115">Custodian CSV file</span></span>

<span data-ttu-id="9fa60-116">下载 CSV 保管人模板后，可以在每行中添加保管人及其数据源。</span><span class="sxs-lookup"><span data-stu-id="9fa60-116">After you download the CSV custodian template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="9fa60-117">确保不要更改标题行中的列名称。</span><span class="sxs-lookup"><span data-stu-id="9fa60-117">Be sure not to change the column names in the header row.</span></span> <span data-ttu-id="9fa60-118">使用工作负荷类型和工作负荷位置列将其他数据源关联到保管人。</span><span class="sxs-lookup"><span data-stu-id="9fa60-118">Use the workload type and workload location columns to associate other data sources to a custodian.</span></span>

| <span data-ttu-id="9fa60-119">列名称</span><span class="sxs-lookup"><span data-stu-id="9fa60-119">Column name</span></span>|<span data-ttu-id="9fa60-120">说明</span><span class="sxs-lookup"><span data-stu-id="9fa60-120">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="9fa60-121">**保管人 contactEmail**</span><span class="sxs-lookup"><span data-stu-id="9fa60-121">**Custodian contactEmail**</span></span>     |<span data-ttu-id="9fa60-122">保管人 UPN 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9fa60-122">The custodian's UPN email address.</span></span> <span data-ttu-id="9fa60-123">例如，sarad@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="9fa60-123">For example, sarad@contoso.onmicrosoft.com.</span></span>           |
|<span data-ttu-id="9fa60-124">**Exchange 已启用**</span><span class="sxs-lookup"><span data-stu-id="9fa60-124">**Exchange Enabled**</span></span> | <span data-ttu-id="9fa60-125">要包含或不包括保管人邮箱的 TRUE/FALSE 值。</span><span class="sxs-lookup"><span data-stu-id="9fa60-125">TRUE/FALSE value to include or not include the custodian's mailbox.</span></span>      |
|<span data-ttu-id="9fa60-126">**OneDrive 已启用**</span><span class="sxs-lookup"><span data-stu-id="9fa60-126">**OneDrive Enabled**</span></span> | <span data-ttu-id="9fa60-127">要包含或不包含保管人 OneDrive for Business 帐户的 TRUE/FALSE 值。</span><span class="sxs-lookup"><span data-stu-id="9fa60-127">TRUE/FALSE value to include or not included the custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="9fa60-128">**Is OnHold**</span><span class="sxs-lookup"><span data-stu-id="9fa60-128">**Is OnHold**</span></span>        | <span data-ttu-id="9fa60-129">TRUE/FALSE 值，指示是否将保管人数据源放在保留状态。</span><span class="sxs-lookup"><span data-stu-id="9fa60-129">TRUE/FALSE value to indicate whether to place the custodian data sources on hold.</span></span>       |
|<span data-ttu-id="9fa60-130">**Workload1 类型**</span><span class="sxs-lookup"><span data-stu-id="9fa60-130">**Workload1 Type**</span></span>         |<span data-ttu-id="9fa60-131">指示要与保管人关联的数据源类型的字符串值。</span><span class="sxs-lookup"><span data-stu-id="9fa60-131">String value indicating the type of data source to associate with the custodian.</span></span> <span data-ttu-id="9fa60-132">可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="9fa60-132">Possible values include:</span></span> <br/><span data-ttu-id="9fa60-133">- ExchangeMailbox</span><span class="sxs-lookup"><span data-stu-id="9fa60-133">- ExchangeMailbox</span></span><br/> <span data-ttu-id="9fa60-134">- SharePointSite</span><span class="sxs-lookup"><span data-stu-id="9fa60-134">- SharePointSite</span></span><br/><span data-ttu-id="9fa60-135">- TeamsMailbox</span><span class="sxs-lookup"><span data-stu-id="9fa60-135">- TeamsMailbox</span></span><br/><span data-ttu-id="9fa60-136">- TeamsSite</span><span class="sxs-lookup"><span data-stu-id="9fa60-136">- TeamsSite</span></span><br/> <span data-ttu-id="9fa60-137">- YammerMailbox</span><span class="sxs-lookup"><span data-stu-id="9fa60-137">- YammerMailbox</span></span><br/><span data-ttu-id="9fa60-138">- YammerSite</span><span class="sxs-lookup"><span data-stu-id="9fa60-138">- YammerSite</span></span> |
|<span data-ttu-id="9fa60-139">**Workload1 位置**</span><span class="sxs-lookup"><span data-stu-id="9fa60-139">**Workload1 Location**</span></span>     | <span data-ttu-id="9fa60-140">根据您的工作负荷类型，这将是数据源的位置。</span><span class="sxs-lookup"><span data-stu-id="9fa60-140">Depending on your workload type, this would be the location of the data source.</span></span> <span data-ttu-id="9fa60-141">例如，Exchange 邮箱的电子邮件地址或 SharePoint 网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="9fa60-141">For example, the email address for an Exchange mailbox or the URL for a SharePoint site.</span></span> |
|||

<span data-ttu-id="9fa60-142">下面是包含保管人信息的 CSV 文件的示例：</span><span class="sxs-lookup"><span data-stu-id="9fa60-142">Here's an example of a CSV file with custodian information:</span></span><br/><br/>

|<span data-ttu-id="9fa60-143">保管人 contactEmail</span><span class="sxs-lookup"><span data-stu-id="9fa60-143">Custodian contactEmail</span></span>      | <span data-ttu-id="9fa60-144">Exchange 已启用</span><span class="sxs-lookup"><span data-stu-id="9fa60-144">Exchange Enabled</span></span> | <span data-ttu-id="9fa60-145">OneDrive 已启用</span><span class="sxs-lookup"><span data-stu-id="9fa60-145">OneDrive Enabled</span></span> | <span data-ttu-id="9fa60-146">Is OnHold</span><span class="sxs-lookup"><span data-stu-id="9fa60-146">Is OnHold</span></span> | <span data-ttu-id="9fa60-147">Workload1 类型</span><span class="sxs-lookup"><span data-stu-id="9fa60-147">Workload1 Type</span></span> | <span data-ttu-id="9fa60-148">Workload1 位置</span><span class="sxs-lookup"><span data-stu-id="9fa60-148">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="9fa60-149">robinc@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fa60-149">robinc@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="9fa60-150">TRUE</span><span class="sxs-lookup"><span data-stu-id="9fa60-150">TRUE</span></span>             | <span data-ttu-id="9fa60-151">TRUE</span><span class="sxs-lookup"><span data-stu-id="9fa60-151">TRUE</span></span>             | <span data-ttu-id="9fa60-152">TRUE</span><span class="sxs-lookup"><span data-stu-id="9fa60-152">TRUE</span></span>      | <span data-ttu-id="9fa60-153">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="9fa60-153">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="9fa60-154">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9fa60-154">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="9fa60-155">TRUE</span><span class="sxs-lookup"><span data-stu-id="9fa60-155">TRUE</span></span>             | <span data-ttu-id="9fa60-156">TRUE</span><span class="sxs-lookup"><span data-stu-id="9fa60-156">TRUE</span></span>             | <span data-ttu-id="9fa60-157">TRUE</span><span class="sxs-lookup"><span data-stu-id="9fa60-157">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="9fa60-158">保管人和数据源验证</span><span class="sxs-lookup"><span data-stu-id="9fa60-158">Custodian and data source validation</span></span>

<span data-ttu-id="9fa60-159">上传保管人 CSV 文件后，高级电子数据展示将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9fa60-159">After you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="9fa60-160">验证保管人及其数据源。</span><span class="sxs-lookup"><span data-stu-id="9fa60-160">Validates the custodians and their data sources.</span></span>

2. <span data-ttu-id="9fa60-161">索引每个保管人的所有数据源，如果 CSV (**Is OnHold** 属性设置为 TRUE，则将其) 。</span><span class="sxs-lookup"><span data-stu-id="9fa60-161">Indexes all data sources for each custodian and places them on hold (if the **Is OnHold** property in the CSV file is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="9fa60-162">保管人验证</span><span class="sxs-lookup"><span data-stu-id="9fa60-162">Custodian validation</span></span>

<span data-ttu-id="9fa60-163">目前，我们仅支持导入包含在组织的 Azure Active Directory (Azure AD) 。</span><span class="sxs-lookup"><span data-stu-id="9fa60-163">Currently, we only support importing custodians that are included in your organization's Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="9fa60-164">保管人导入工具使用 CSV 文件的 **Custodian contactEmail** 列中的 UPN 值查找并验证保管人。</span><span class="sxs-lookup"><span data-stu-id="9fa60-164">The custodian import tool finds and validates custodians using the UPN value in the **Custodian contactEmail** column in the CSV file.</span></span> <span data-ttu-id="9fa60-165">经验证的保管人将自动添加到案例，并列在案例的"数据源 **"** 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="9fa60-165">Custodians that are validated are automatically added to the case and listed on the **Data sources** tab of the case.</span></span> <span data-ttu-id="9fa60-166">如果无法验证保管人，将在"作业"选项卡上列出的 BulkAddCustodian 作业的错误日志中列出保管人。 </span><span class="sxs-lookup"><span data-stu-id="9fa60-166">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="9fa60-167">未验证保管人不会添加到案例或列在"数据源 **"选项卡** 上。</span><span class="sxs-lookup"><span data-stu-id="9fa60-167">Unvalidated custodians are not added to the case or listed on the **Data sources** tab.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="9fa60-168">数据源验证</span><span class="sxs-lookup"><span data-stu-id="9fa60-168">Data source validation</span></span>

<span data-ttu-id="9fa60-169">验证保管人并添加到案例后，将添加与保管人关联的每个主邮箱和 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="9fa60-169">After custodians are validated and added to the case, each primary mailbox and OneDrive account that's associated with a custodian is added.</span></span>

<span data-ttu-id="9fa60-170">但是，如果找不到与保管人关联的任何其他数据源 (例如 SharePoint 网站、Microsoft Teams、Microsoft 365 组或 Yammer 组) ，则不会将任何数据源分配给保管人，并且未验证的值将显示在"数据源"选项卡上保管人旁边的"状态"列中。 </span><span class="sxs-lookup"><span data-stu-id="9fa60-170">However, if any of the other data sources (such as SharePoint sites, Microsoft Teams, Microsoft 365 Groups, or Yammer groups) associated with a custodian can't be found, none of them are assigned to the custodian and the value **Not validated** is displayed in the **Status** column next to the custodian on the **Data sources** tab.</span></span>

<span data-ttu-id="9fa60-171">为保管人添加经过验证的数据源：</span><span class="sxs-lookup"><span data-stu-id="9fa60-171">To add validated data sources for a custodian:</span></span>

1. <span data-ttu-id="9fa60-172">在 **"数据源"** 选项卡上，选择包含未验证的数据源的保管人。</span><span class="sxs-lookup"><span data-stu-id="9fa60-172">On the **Data sources** tab, select a custodian that contains data sources that aren't validated.</span></span>

2. <span data-ttu-id="9fa60-173">在保管人飞出页面上，滚动到 **"保管** 人位置"部分以查看与保管人关联的已验证和未验证数据源。</span><span class="sxs-lookup"><span data-stu-id="9fa60-173">On the custodian flyout page, scroll to the **Custodial locations** section to view both validated and unvalidated data sources that are associated with custodian.</span></span>

3. <span data-ttu-id="9fa60-174">单击 **飞** 出页面顶部的"编辑"以删除无效数据源或添加新数据源。</span><span class="sxs-lookup"><span data-stu-id="9fa60-174">Click **Edit** at the top of the flyout page to remove invalid data sources or add new ones.</span></span>

4. <span data-ttu-id="9fa60-175">删除未验证的数据源或添加新数据源后，"数据源"选项卡上保管人的状态列中将显示"**活动\*\*\*\*"** 值。若要添加之前似乎无效的源，请按照下面的修正步骤手动将它们添加到保管人。</span><span class="sxs-lookup"><span data-stu-id="9fa60-175">After you remove unvalidated data sources or add a new one, the value **Active** is displayed in **Status** column for the custodian on the **Data sources** tab. To add sources that previously appeared to be invalid, follow the remediation steps below to manually add them to a custodian.</span></span>

### <a name="remediating-invalid-data-sources"></a><span data-ttu-id="9fa60-176">修正无效数据源</span><span class="sxs-lookup"><span data-stu-id="9fa60-176">Remediating invalid data sources</span></span>

<span data-ttu-id="9fa60-177">若要手动添加和关联以前无效的数据源：</span><span class="sxs-lookup"><span data-stu-id="9fa60-177">To manually add and associate a data source that was previously invalid:</span></span>

1. <span data-ttu-id="9fa60-178">在 **"数据源"** 选项卡上，选择要手动添加和关联以前无效的数据源的保管人。</span><span class="sxs-lookup"><span data-stu-id="9fa60-178">On the **Data sources** tab, select a custodian to manually add and associate a data source that was previously invalid.</span></span>

2. <span data-ttu-id="9fa60-179">单击 **飞** 出页面顶部的"编辑"，将邮箱、网站、Teams 或 Yammer 组关联到保管人。</span><span class="sxs-lookup"><span data-stu-id="9fa60-179">Click **Edit** at the top of the flyout page to associate mailboxes, sites, Teams, or Yammer groups to the custodian.</span></span> <span data-ttu-id="9fa60-180">为此 **，单击相应** 数据位置类型旁边的"编辑"。</span><span class="sxs-lookup"><span data-stu-id="9fa60-180">Do this by clicking **Edit** next to the appropriate data location type.</span></span>

3. <span data-ttu-id="9fa60-181">单击 **"** 下一步 **"显示"** 保留设置"页，并配置您添加的数据源的保留设置。</span><span class="sxs-lookup"><span data-stu-id="9fa60-181">Click **Next** to display the **Hold settings** page and configure the hold setting for the data sources you added.</span></span>

4. <span data-ttu-id="9fa60-182">单击 **"** 下一步"显示 **"审阅** 保管人"页，然后单击" **提交"保存** 更改。</span><span class="sxs-lookup"><span data-stu-id="9fa60-182">Click **Next** to display the **Review custodians** page, and then click **Submit** to save your changes.</span></span>
