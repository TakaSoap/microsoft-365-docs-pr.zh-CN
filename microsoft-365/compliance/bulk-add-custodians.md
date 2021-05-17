---
title: 将保管人导入Advanced eDiscovery案例
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
description: 使用导入工具 d 快速将多个保管人及其关联的数据源添加到Advanced eDiscovery。
ms.openlocfilehash: 98ff3690fe7fd8c956fce436585014ef0db82a26
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421609"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="6cc48-103">将保管人导入Advanced eDiscovery案例</span><span class="sxs-lookup"><span data-stu-id="6cc48-103">Import custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="6cc48-104">对于Advanced eDiscovery多个保管人的情况，可以使用 CSV 文件一次导入多个保管人，该文件包含将保管人添加到事例所必需的信息。</span><span class="sxs-lookup"><span data-stu-id="6cc48-104">For Advanced eDiscovery cases that involve many custodians, you can import multiple custodians at once by using a CSV file that contains the information necessary to add them to a case.</span></span>

## <a name="import-custodians"></a><span data-ttu-id="6cc48-105">导入保管人</span><span class="sxs-lookup"><span data-stu-id="6cc48-105">Import custodians</span></span>

1. <span data-ttu-id="6cc48-106">打开Advanced eDiscovery，然后选择"**数据源"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="6cc48-106">Open the Advanced eDiscovery case and select the **Data sources** tab.</span></span>

2. <span data-ttu-id="6cc48-107">单击 **"添加数据源**  >  **导入保管人"。**</span><span class="sxs-lookup"><span data-stu-id="6cc48-107">Click **Add data source** > **Import custodians**.</span></span>

3. <span data-ttu-id="6cc48-108">在" **导入保管人** "飞出页面上，单击 **"下载空白模板** "以下载保管人模板 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="6cc48-108">On the **Import custodians** flyout page, click **Download a blank template** to download a custodian template CSV file.</span></span>

   ![从导入保管人飞出页面下载 CSV 模板](../media/ImportCustodians1.png)

4. <span data-ttu-id="6cc48-110">将信息添加到 CSV 文件，并将其保存到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="6cc48-110">Add the custodial information to the CSV file and save it to your local computer.</span></span> <span data-ttu-id="6cc48-111">有关 [CSV 文件中所需](#custodian-csv-file) 属性的信息，请参阅 Custodian CSV 文件部分。</span><span class="sxs-lookup"><span data-stu-id="6cc48-111">See the [Custodian CSV file](#custodian-csv-file) section for information about the required properties in the CSV file.</span></span>

5. <span data-ttu-id="6cc48-112">准备好包含保管人信息的 CSV 文件后，返回到"数据源"选项卡，并再次单击"添加数据源  >  **导入保管** 人"。</span><span class="sxs-lookup"><span data-stu-id="6cc48-112">After you've prepared the CSV file with the custodian information, go back to the **Data sources** tab, and click **Add data source** > **Import custodians** again.</span></span>

6. <span data-ttu-id="6cc48-113">在"**导入保管人**"飞出页面上，单击"浏览"，然后上载包含保管人信息的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="6cc48-113">On the **Import custodians** flyout page, click **Browse** and then upload the CSV file that contains the custodian information.</span></span>

   <span data-ttu-id="6cc48-114">上载 CSV 文件后，将创建名为 **BulkAddCustodian** 的作业，并将其显示在"作业 **"** 选项卡上。作业验证保管人及其关联的数据源，然后将它们添加到案例的" **数据源** "页。</span><span class="sxs-lookup"><span data-stu-id="6cc48-114">After the CSV file is uploaded, a job named **BulkAddCustodian** is created and displayed on the **Jobs** tab. The job validates the custodians and their associated data sources and then adds them to the **Data sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="6cc48-115">保管人 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="6cc48-115">Custodian CSV file</span></span>

<span data-ttu-id="6cc48-116">下载 CSV 保管人模板后，您可以在每行中添加保管人及其数据源。</span><span class="sxs-lookup"><span data-stu-id="6cc48-116">After you download the CSV custodian template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="6cc48-117">确保不要更改标题行中的列名称。</span><span class="sxs-lookup"><span data-stu-id="6cc48-117">Be sure not to change the column names in the header row.</span></span> <span data-ttu-id="6cc48-118">使用工作负荷类型和工作负荷位置列将其他数据源关联到保管人。</span><span class="sxs-lookup"><span data-stu-id="6cc48-118">Use the workload type and workload location columns to associate other data sources to a custodian.</span></span>

| <span data-ttu-id="6cc48-119">列名称</span><span class="sxs-lookup"><span data-stu-id="6cc48-119">Column name</span></span>|<span data-ttu-id="6cc48-120">说明</span><span class="sxs-lookup"><span data-stu-id="6cc48-120">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="6cc48-121">**Custodian contactEmail**</span><span class="sxs-lookup"><span data-stu-id="6cc48-121">**Custodian contactEmail**</span></span>     |<span data-ttu-id="6cc48-122">保管人 UPN 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6cc48-122">The custodian's UPN email address.</span></span> <span data-ttu-id="6cc48-123">例如，sarad@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="6cc48-123">For example, sarad@contoso.onmicrosoft.com.</span></span>           |
|<span data-ttu-id="6cc48-124">**Exchange已启用**</span><span class="sxs-lookup"><span data-stu-id="6cc48-124">**Exchange Enabled**</span></span> | <span data-ttu-id="6cc48-125">要包含或不包含保管人邮箱的 TRUE/FALSE 值。</span><span class="sxs-lookup"><span data-stu-id="6cc48-125">TRUE/FALSE value to include or not include the custodian's mailbox.</span></span>      |
|<span data-ttu-id="6cc48-126">**OneDrive已启用**</span><span class="sxs-lookup"><span data-stu-id="6cc48-126">**OneDrive Enabled**</span></span> | <span data-ttu-id="6cc48-127">要包含或不包含保管人帐户的 TRUE/FALSE OneDrive for Business帐户。</span><span class="sxs-lookup"><span data-stu-id="6cc48-127">TRUE/FALSE value to include or not included the custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="6cc48-128">**Is OnHold**</span><span class="sxs-lookup"><span data-stu-id="6cc48-128">**Is OnHold**</span></span>        | <span data-ttu-id="6cc48-129">TRUE/FALSE 值，指示是否将保管人数据源放在保留状态。</span><span class="sxs-lookup"><span data-stu-id="6cc48-129">TRUE/FALSE value to indicate whether to place the custodian data sources on hold.</span></span> <span data-ttu-id="6cc48-130"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="6cc48-130"><sup>1</sup></span></span>     |
|<span data-ttu-id="6cc48-131">**Workload1 类型**</span><span class="sxs-lookup"><span data-stu-id="6cc48-131">**Workload1 Type**</span></span>         |<span data-ttu-id="6cc48-132">指示要与保管人关联的数据源类型的字符串值。</span><span class="sxs-lookup"><span data-stu-id="6cc48-132">String value indicating the type of data source to associate with the custodian.</span></span> <span data-ttu-id="6cc48-133">可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="6cc48-133">Possible values include:</span></span> <br/><span data-ttu-id="6cc48-134">- ExchangeMailbox</span><span class="sxs-lookup"><span data-stu-id="6cc48-134">- ExchangeMailbox</span></span><br/> <span data-ttu-id="6cc48-135">- SharePointSite</span><span class="sxs-lookup"><span data-stu-id="6cc48-135">- SharePointSite</span></span><br/><span data-ttu-id="6cc48-136">- TeamsMailbox</span><span class="sxs-lookup"><span data-stu-id="6cc48-136">- TeamsMailbox</span></span><br/><span data-ttu-id="6cc48-137">- TeamsSite</span><span class="sxs-lookup"><span data-stu-id="6cc48-137">- TeamsSite</span></span><br/> <span data-ttu-id="6cc48-138">- YammerMailbox</span><span class="sxs-lookup"><span data-stu-id="6cc48-138">- YammerMailbox</span></span><br/><span data-ttu-id="6cc48-139">- YammerSite</span><span class="sxs-lookup"><span data-stu-id="6cc48-139">- YammerSite</span></span> |
|<span data-ttu-id="6cc48-140">**Workload1 位置**</span><span class="sxs-lookup"><span data-stu-id="6cc48-140">**Workload1 Location**</span></span>     | <span data-ttu-id="6cc48-141">根据您的工作负荷类型，这将是数据源的位置。</span><span class="sxs-lookup"><span data-stu-id="6cc48-141">Depending on your workload type, this would be the location of the data source.</span></span> <span data-ttu-id="6cc48-142">例如，用户邮箱Exchange URL 或网站SharePoint URL。</span><span class="sxs-lookup"><span data-stu-id="6cc48-142">For example, the email address for an Exchange mailbox or the URL for a SharePoint site.</span></span> |
|||

> [!NOTE]
> <span data-ttu-id="6cc48-143"><sup>1</sup> 您可以使用保管人导入过程和 CSV 文件将最多 1，000 个邮箱和 100 个网站置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="6cc48-143"><sup>1</sup> You can place a maximum of 1,000 mailboxes and 100 sites on hold by using the custodian import process and CSV file.</span></span> <span data-ttu-id="6cc48-144">您可以使用此过程向案例添加超过 1，000 个保管人，但保留限制仍然适用。</span><span class="sxs-lookup"><span data-stu-id="6cc48-144">You can use this process to add more than 1,000 custodians to a case, but the hold limits still apply.</span></span> <span data-ttu-id="6cc48-145">有关保留限制详细信息，请参阅 Advanced eDiscovery[中的限制](limits-ediscovery20.md#hold-limits)。</span><span class="sxs-lookup"><span data-stu-id="6cc48-145">For more information about hold limits, see [Limits in Advanced eDiscovery](limits-ediscovery20.md#hold-limits).</span></span>

<span data-ttu-id="6cc48-146">下面是包含保管人信息的 CSV 文件的示例：</span><span class="sxs-lookup"><span data-stu-id="6cc48-146">Here's an example of a CSV file with custodian information:</span></span><br/><br/>

|<span data-ttu-id="6cc48-147">Custodian contactEmail</span><span class="sxs-lookup"><span data-stu-id="6cc48-147">Custodian contactEmail</span></span>      | <span data-ttu-id="6cc48-148">Exchange已启用</span><span class="sxs-lookup"><span data-stu-id="6cc48-148">Exchange Enabled</span></span> | <span data-ttu-id="6cc48-149">OneDrive已启用</span><span class="sxs-lookup"><span data-stu-id="6cc48-149">OneDrive Enabled</span></span> | <span data-ttu-id="6cc48-150">Is OnHold</span><span class="sxs-lookup"><span data-stu-id="6cc48-150">Is OnHold</span></span> | <span data-ttu-id="6cc48-151">Workload1 类型</span><span class="sxs-lookup"><span data-stu-id="6cc48-151">Workload1 Type</span></span> | <span data-ttu-id="6cc48-152">Workload1 位置</span><span class="sxs-lookup"><span data-stu-id="6cc48-152">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="6cc48-153">robinc@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6cc48-153">robinc@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="6cc48-154">TRUE</span><span class="sxs-lookup"><span data-stu-id="6cc48-154">TRUE</span></span>             | <span data-ttu-id="6cc48-155">TRUE</span><span class="sxs-lookup"><span data-stu-id="6cc48-155">TRUE</span></span>             | <span data-ttu-id="6cc48-156">TRUE</span><span class="sxs-lookup"><span data-stu-id="6cc48-156">TRUE</span></span>      | <span data-ttu-id="6cc48-157">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="6cc48-157">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="6cc48-158">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6cc48-158">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="6cc48-159">TRUE</span><span class="sxs-lookup"><span data-stu-id="6cc48-159">TRUE</span></span>             | <span data-ttu-id="6cc48-160">TRUE</span><span class="sxs-lookup"><span data-stu-id="6cc48-160">TRUE</span></span>             | <span data-ttu-id="6cc48-161">TRUE</span><span class="sxs-lookup"><span data-stu-id="6cc48-161">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="6cc48-162">保管人和数据源验证</span><span class="sxs-lookup"><span data-stu-id="6cc48-162">Custodian and data source validation</span></span>

<span data-ttu-id="6cc48-163">上传保管人 CSV 文件后，Advanced eDiscovery执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6cc48-163">After you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="6cc48-164">验证保管人及其数据源。</span><span class="sxs-lookup"><span data-stu-id="6cc48-164">Validates the custodians and their data sources.</span></span>

2. <span data-ttu-id="6cc48-165">索引每个保管人的所有数据源，如果 CSV 文件中 **Is OnHold** 属性设置为 TRUE (则将其保留) 。</span><span class="sxs-lookup"><span data-stu-id="6cc48-165">Indexes all data sources for each custodian and places them on hold (if the **Is OnHold** property in the CSV file is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="6cc48-166">保管人验证</span><span class="sxs-lookup"><span data-stu-id="6cc48-166">Custodian validation</span></span>

<span data-ttu-id="6cc48-167">目前，我们仅支持导入包含在组织的 Azure AD Azure Active Directory (中的保管) 。</span><span class="sxs-lookup"><span data-stu-id="6cc48-167">Currently, we only support importing custodians that are included in your organization's Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="6cc48-168">保管人导入工具使用 CSV 文件的 **Custodian contactEmail** 列中的 UPN 值查找并验证保管人。</span><span class="sxs-lookup"><span data-stu-id="6cc48-168">The custodian import tool finds and validates custodians using the UPN value in the **Custodian contactEmail** column in the CSV file.</span></span> <span data-ttu-id="6cc48-169">经验证的保管人将自动添加到案例，并列在案例的" **数据源** "选项卡上。</span><span class="sxs-lookup"><span data-stu-id="6cc48-169">Custodians that are validated are automatically added to the case and listed on the **Data sources** tab of the case.</span></span> <span data-ttu-id="6cc48-170">如果无法验证保管人，将在"作业"选项卡上列出的 BulkAddCustodian 作业的错误日志中列出保管人。 </span><span class="sxs-lookup"><span data-stu-id="6cc48-170">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="6cc48-171">未验证保管人不会添加到案例或列在"数据源 **"选项卡** 上。</span><span class="sxs-lookup"><span data-stu-id="6cc48-171">Unvalidated custodians are not added to the case or listed on the **Data sources** tab.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="6cc48-172">数据源验证</span><span class="sxs-lookup"><span data-stu-id="6cc48-172">Data source validation</span></span>

<span data-ttu-id="6cc48-173">验证保管人并添加到案例后，OneDrive添加与保管人关联的每个主邮箱和邮箱帐户。</span><span class="sxs-lookup"><span data-stu-id="6cc48-173">After custodians are validated and added to the case, each primary mailbox and OneDrive account that's associated with a custodian is added.</span></span>

<span data-ttu-id="6cc48-174">但是，如果找不到与保管人关联的任何其他数据源 (例如 SharePoint 网站、Microsoft Teams、Microsoft 365 组或 Yammer 组) ，则没有一个分配给保管人，且"未验证"值显示在"数据源"选项卡上保管人旁边的"状态"列中。   </span><span class="sxs-lookup"><span data-stu-id="6cc48-174">However, if any of the other data sources (such as SharePoint sites, Microsoft Teams, Microsoft 365 Groups, or Yammer groups) associated with a custodian can't be found, none of them are assigned to the custodian and the value **Not validated** is displayed in the **Status** column next to the custodian on the **Data sources** tab.</span></span>

<span data-ttu-id="6cc48-175">为保管人添加经过验证的数据源：</span><span class="sxs-lookup"><span data-stu-id="6cc48-175">To add validated data sources for a custodian:</span></span>

1. <span data-ttu-id="6cc48-176">在 **"数据源"** 选项卡上，选择包含未验证的数据源的保管人。</span><span class="sxs-lookup"><span data-stu-id="6cc48-176">On the **Data sources** tab, select a custodian that contains data sources that aren't validated.</span></span>

2. <span data-ttu-id="6cc48-177">在保管人飞出页面上，滚动到 **"显示** 位置"部分以查看与保管人关联的已验证和未验证的数据源。</span><span class="sxs-lookup"><span data-stu-id="6cc48-177">On the custodian flyout page, scroll to the **Custodial locations** section to view both validated and unvalidated data sources that are associated with custodian.</span></span>

3. <span data-ttu-id="6cc48-178">单击 **飞** 出页面顶部的"编辑"以删除无效数据源或添加新数据源。</span><span class="sxs-lookup"><span data-stu-id="6cc48-178">Click **Edit** at the top of the flyout page to remove invalid data sources or add new ones.</span></span>

4. <span data-ttu-id="6cc48-179">删除未验证的数据源或添加新数据源后，值 **Active** 将显示在"数据源"选项卡上保管人 **的状态列中。** 若要添加之前似乎无效的源，请按照下面的修正步骤手动将它们添加到保管人。</span><span class="sxs-lookup"><span data-stu-id="6cc48-179">After you remove unvalidated data sources or add a new one, the value **Active** is displayed in **Status** column for the custodian on the **Data sources** tab. To add sources that previously appeared to be invalid, follow the remediation steps below to manually add them to a custodian.</span></span>

### <a name="remediating-invalid-data-sources"></a><span data-ttu-id="6cc48-180">修正无效的数据源</span><span class="sxs-lookup"><span data-stu-id="6cc48-180">Remediating invalid data sources</span></span>

<span data-ttu-id="6cc48-181">若要手动添加和关联之前无效的数据源，</span><span class="sxs-lookup"><span data-stu-id="6cc48-181">To manually add and associate a data source that was previously invalid:</span></span>

1. <span data-ttu-id="6cc48-182">在 **"数据源"** 选项卡上，选择要手动添加和关联之前无效的数据源的保管人。</span><span class="sxs-lookup"><span data-stu-id="6cc48-182">On the **Data sources** tab, select a custodian to manually add and associate a data source that was previously invalid.</span></span>

2. <span data-ttu-id="6cc48-183">单击 **飞** 出页面顶部的"编辑"，将邮箱、站点、Teams或Yammer组关联到保管人。</span><span class="sxs-lookup"><span data-stu-id="6cc48-183">Click **Edit** at the top of the flyout page to associate mailboxes, sites, Teams, or Yammer groups to the custodian.</span></span> <span data-ttu-id="6cc48-184">为此 **，单击相应** 数据位置类型旁边的"编辑"。</span><span class="sxs-lookup"><span data-stu-id="6cc48-184">Do this by clicking **Edit** next to the appropriate data location type.</span></span>

3. <span data-ttu-id="6cc48-185">单击 **"** 下一步"以显示"保留设置"页，并配置您添加的数据源的保留设置。</span><span class="sxs-lookup"><span data-stu-id="6cc48-185">Click **Next** to display the **Hold settings** page and configure the hold setting for the data sources you added.</span></span>

4. <span data-ttu-id="6cc48-186">单击 **"下** 一步"显示 **"审阅** 保管人"页，然后单击" **提交** "以保存更改。</span><span class="sxs-lookup"><span data-stu-id="6cc48-186">Click **Next** to display the **Review custodians** page, and then click **Submit** to save your changes.</span></span>
