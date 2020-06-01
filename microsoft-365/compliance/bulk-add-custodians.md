---
title: 向高级电子数据展示案例批量添加保管人
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 9331e45619f549ea31adcfdd9316eea20e43efef
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432435"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case-preview"></a><span data-ttu-id="a33a1-102">向高级电子数据展示案例批量添加保管人（预览）</span><span class="sxs-lookup"><span data-stu-id="a33a1-102">Bulk-add custodians to an Advanced eDiscovery case (preview)</span></span>

<span data-ttu-id="a33a1-103">对于涉及大量保管人的高级电子数据展示事例，您可以一次导入多个保管人（包含将其添加到事例所需的所有信息的 CSV 文件）。</span><span class="sxs-lookup"><span data-stu-id="a33a1-103">For Advanced eDiscovery cases that involve a lot of custodians, you can import multiple custodians at once by a CSV file that contains all the information necessary to add them to a case.</span></span>

## <a name="bulk-add-custodians"></a><span data-ttu-id="a33a1-104">批量添加保管人</span><span class="sxs-lookup"><span data-stu-id="a33a1-104">Bulk-add custodians</span></span>

1. <span data-ttu-id="a33a1-105">输入大小写并导航到 "**源**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a33a1-105">Enter case and navigate to the **Sources** tab.</span></span>

2. <span data-ttu-id="a33a1-106">单击 "**导入保管人**"</span><span class="sxs-lookup"><span data-stu-id="a33a1-106">Click **Import custodians**</span></span>

3. <span data-ttu-id="a33a1-107">在弹出页面上，单击 "**下载空白模板**" 以下载 CSV 保管人模板文件。</span><span class="sxs-lookup"><span data-stu-id="a33a1-107">On the flyout page, click **Download a blank template** to download a CSV custodian template file.</span></span>

4. <span data-ttu-id="a33a1-108">将 custodial 信息添加到 CSV 文件，并将其保存在您的本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="a33a1-108">Add the custodial information to the CSV file and save it on your local computer.</span></span> <span data-ttu-id="a33a1-109">有关 CSV 文件中的属性的信息，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="a33a1-109">See the next section for information about the properties in the CSV file.</span></span>

5. <span data-ttu-id="a33a1-110">在 "**源**" 选项卡上，再次单击 "**导入保管人**"。</span><span class="sxs-lookup"><span data-stu-id="a33a1-110">On the **Sources** tab, click **Import Custodians** again.</span></span> 
6. <span data-ttu-id="a33a1-111">在弹出页面上，单击 "**浏览**"，然后上传 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="a33a1-111">On flyout page, click **Browse** and the upload your CSV file.</span></span>

   <span data-ttu-id="a33a1-112">在上传 CSV 文件后，将创建一个 BulkAddCustodian 作业并将其显示在 "**作业**" 选项卡上。该作业将验证保管人及其相应的数据源，然后将其添加到事例的 "**源**" 页上的 "**保管人**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="a33a1-112">After the CSV file is uploaded, a BulkAddCustodian job is created and displayed on the **Jobs** tab. The job validates the custodians and their corresponding data sources and then adds them to the **Custodians** tab on the **Sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="a33a1-113">保管人 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="a33a1-113">Custodian CSV file</span></span>

<span data-ttu-id="a33a1-114">下载 CSV 模板后，可以在每行中添加保管人及其数据源。</span><span class="sxs-lookup"><span data-stu-id="a33a1-114">After you download the CSV template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="a33a1-115">请务必不要更改标题行中的列名称。</span><span class="sxs-lookup"><span data-stu-id="a33a1-115">Be sure not to change the column names in the the header row.</span></span>

| <span data-ttu-id="a33a1-116">列名称</span><span class="sxs-lookup"><span data-stu-id="a33a1-116">Column name</span></span>|<span data-ttu-id="a33a1-117">说明</span><span class="sxs-lookup"><span data-stu-id="a33a1-117">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="a33a1-118">**保管人 ContactEmail**</span><span class="sxs-lookup"><span data-stu-id="a33a1-118">**Custodian ContactEmail**</span></span>     | <span data-ttu-id="a33a1-119">保管人的 UPN 电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a33a1-119">UPN email of custodian.</span></span> <span data-ttu-id="a33a1-120">示例： sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a33a1-120">Example: sarad@onmicrosoft.contoso.com</span></span>           |
|<span data-ttu-id="a33a1-121">**已启用 Exchange**</span><span class="sxs-lookup"><span data-stu-id="a33a1-121">**Exchange Enabled**</span></span> | <span data-ttu-id="a33a1-122">TRUE/FALSE 值，指示是否添加保管人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a33a1-122">TRUE/FALSE value on whether to add custodian's mailbox.</span></span>      |
|<span data-ttu-id="a33a1-123">**已启用 OneDrive**</span><span class="sxs-lookup"><span data-stu-id="a33a1-123">**OneDrive Enabled**</span></span> | <span data-ttu-id="a33a1-124">TRUE/FALSE 值，该值指示是否添加保管人的 OneDrive for business 帐户。</span><span class="sxs-lookup"><span data-stu-id="a33a1-124">TRUE/FALSE value on whether to add custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="a33a1-125">**为 OnHold**</span><span class="sxs-lookup"><span data-stu-id="a33a1-125">**Is OnHold**</span></span>        | <span data-ttu-id="a33a1-126">TRUE/FALSE 值，指示是否将保管人置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="a33a1-126">TRUE/FALSE value on whether to place custodian on hold.</span></span>       |
|<span data-ttu-id="a33a1-127">**Workload1 类型**</span><span class="sxs-lookup"><span data-stu-id="a33a1-127">**Workload1 Type**</span></span>         | <span data-ttu-id="a33a1-128">指示要与保管人关联的数据源的类型的字符串值。</span><span class="sxs-lookup"><span data-stu-id="a33a1-128">String value indicating the type of data source to associate with the custodian.</span></span> <br /><span data-ttu-id="a33a1-129">可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="a33a1-129">Possible values include:</span></span> <br /><span data-ttu-id="a33a1-130">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span><span class="sxs-lookup"><span data-stu-id="a33a1-130">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span></span> |
|<span data-ttu-id="a33a1-131">**Workload1 位置**</span><span class="sxs-lookup"><span data-stu-id="a33a1-131">**Workload1 Location**</span></span>     | <span data-ttu-id="a33a1-132">根据您的工作负载类型，这将是工作负荷的数据位置（例如，Exchange 邮箱的电子邮件地址或 SharePoint 网站的 URL）。</span><span class="sxs-lookup"><span data-stu-id="a33a1-132">Depending on your workload type, this would be the data location of your workload (for example, the email address of an Exchange mailbox or the URL for a SharePoint site).</span></span> |
|||

<span data-ttu-id="a33a1-133">以下是包含保管人信息的 CSV 文件的示例：</span><span class="sxs-lookup"><span data-stu-id="a33a1-133">Here's an example of a CSV file with custodian information:</span></span>  

| <span data-ttu-id="a33a1-134">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="a33a1-134">ContactEmail</span></span>      | <span data-ttu-id="a33a1-135">已启用 Exchange</span><span class="sxs-lookup"><span data-stu-id="a33a1-135">Exchange Enabled</span></span> | <span data-ttu-id="a33a1-136">已启用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="a33a1-136">OneDrive Enabled</span></span> | <span data-ttu-id="a33a1-137">为 OnHold</span><span class="sxs-lookup"><span data-stu-id="a33a1-137">Is OnHold</span></span> | <span data-ttu-id="a33a1-138">Workload1 类型</span><span class="sxs-lookup"><span data-stu-id="a33a1-138">Workload1 Type</span></span> | <span data-ttu-id="a33a1-139">Workload1 位置</span><span class="sxs-lookup"><span data-stu-id="a33a1-139">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="a33a1-140">sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a33a1-140">sarad@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="a33a1-141">TRUE</span><span class="sxs-lookup"><span data-stu-id="a33a1-141">TRUE</span></span>             | <span data-ttu-id="a33a1-142">TRUE</span><span class="sxs-lookup"><span data-stu-id="a33a1-142">TRUE</span></span>             | <span data-ttu-id="a33a1-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="a33a1-143">TRUE</span></span>      | <span data-ttu-id="a33a1-144">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="a33a1-144">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="a33a1-145">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a33a1-145">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="a33a1-146">TRUE</span><span class="sxs-lookup"><span data-stu-id="a33a1-146">TRUE</span></span>             | <span data-ttu-id="a33a1-147">TRUE</span><span class="sxs-lookup"><span data-stu-id="a33a1-147">TRUE</span></span>             | <span data-ttu-id="a33a1-148">TRUE</span><span class="sxs-lookup"><span data-stu-id="a33a1-148">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="a33a1-149">保管人和数据源验证</span><span class="sxs-lookup"><span data-stu-id="a33a1-149">Custodian and data source validation</span></span>

<span data-ttu-id="a33a1-150">当您上载保管人 CSV 文件时，高级电子数据展示将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a33a1-150">When you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="a33a1-151">验证保管人及其数据源。</span><span class="sxs-lookup"><span data-stu-id="a33a1-151">Validates the custodians and their data sources.</span></span> 

2. <span data-ttu-id="a33a1-152">为每个保管人的所有数据源编制索引，并将其置于保留状态（如果 "OnHold" 属性设置为 TRUE）。</span><span class="sxs-lookup"><span data-stu-id="a33a1-152">Indexes all data sources for each custodian and places them on hold (if the Is OnHold property is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="a33a1-153">保管人验证</span><span class="sxs-lookup"><span data-stu-id="a33a1-153">Custodian validation</span></span>

<span data-ttu-id="a33a1-154">目前，我们仅支持在 Azure Active Directory （AAD）中导入保管人。</span><span class="sxs-lookup"><span data-stu-id="a33a1-154">Currently, we only support importing custodians that are in Azure Active Directory (AAD).</span></span>

<span data-ttu-id="a33a1-155">我们使用 CSV 文件的 "**联系人电子邮件**" 列中的 UPN 值验证和查找保管人。</span><span class="sxs-lookup"><span data-stu-id="a33a1-155">We validate and find custodians using the UPN value in the **Contact Email** column in the CSV file.</span></span> <span data-ttu-id="a33a1-156">已验证的保管人将自动添加到事例中，并在案例的 "**源**" 页上的 "**保管人**" 选项卡上列出。</span><span class="sxs-lookup"><span data-stu-id="a33a1-156">Custodians that are validated are automatically added to the case and listed on the **Custodian** tab on the **Sources** page of the case.</span></span> <span data-ttu-id="a33a1-157">如果无法验证某个保管人，则会在该事例的 "**作业**" 选项卡上列出的 BulkAddCustodian 作业的错误日志中列出。</span><span class="sxs-lookup"><span data-stu-id="a33a1-157">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="a33a1-158">Unvalidated 保管人不会添加到事例中。</span><span class="sxs-lookup"><span data-stu-id="a33a1-158">Unvalidated custodians are not added to the case.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="a33a1-159">数据源验证</span><span class="sxs-lookup"><span data-stu-id="a33a1-159">Data source validation</span></span>

<span data-ttu-id="a33a1-160">在对保管人进行验证并将其添加到事例之后，将验证与保管人关联的每个数据源。</span><span class="sxs-lookup"><span data-stu-id="a33a1-160">After custodians are validated and added to the case, each data source that's associated with a custodian is validated.</span></span> <span data-ttu-id="a33a1-161">如果找不到某个保管人的任何数据源，则**未验证**的值将显示在该保管人的 "**保管人**" 选项卡上的 "已**验证**" 列中。</span><span class="sxs-lookup"><span data-stu-id="a33a1-161">If any data source for a custodian can't be found, the value **Not validated** would be displayed in the **Validated** column on the **Custodian** tab for that custodian.</span></span>

### <a name="remediating-unvalidated-data-sources"></a><span data-ttu-id="a33a1-162">修正 unvalidated 数据源</span><span class="sxs-lookup"><span data-stu-id="a33a1-162">Remediating unvalidated data sources</span></span>

<span data-ttu-id="a33a1-163">使用 unvalidated 数据源修正保管人：</span><span class="sxs-lookup"><span data-stu-id="a33a1-163">To remediate custodians with unvalidated data sources:</span></span> 

1. <span data-ttu-id="a33a1-164">在 "**管理员**" 选项卡上，选择未验证的管理员。</span><span class="sxs-lookup"><span data-stu-id="a33a1-164">On the **Custodian** tab, select a custodian who isn't validated.</span></span>

2. <span data-ttu-id="a33a1-165">在 "保管人" 弹出页面上，滚动到 "**数据源**" 部分以查看与保管人关联的数据源。</span><span class="sxs-lookup"><span data-stu-id="a33a1-165">On the custodian flyout page, scroll to the **Data sources** section to view the data sources that are associated with custodian.</span></span> <span data-ttu-id="a33a1-166">已列出经过验证和 unvalidated 的数据源。</span><span class="sxs-lookup"><span data-stu-id="a33a1-166">Both validated and unvalidated data sources are listed.</span></span>

3. <span data-ttu-id="a33a1-167">在 "**数据源**" 部分，单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="a33a1-167">In the **Data sources** section, click **Edit**.</span></span>

4. <span data-ttu-id="a33a1-168">在 "**选择 custodial 位置**" 页上，删除 "unvalidated" 数据源。</span><span class="sxs-lookup"><span data-stu-id="a33a1-168">On the **Choose custodial locations** page, remove an unvalidated data source.</span></span>

5. <span data-ttu-id="a33a1-169">在 "**选择其他位置**" 页上，单击 "**更新**" 为保管人添加其他数据源。</span><span class="sxs-lookup"><span data-stu-id="a33a1-169">On the **Select additional locations** page, click **Update** to add additional data sources for a custodian.</span></span>
