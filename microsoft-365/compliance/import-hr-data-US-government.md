---
title: 设置连接器以将 HR 数据导入美国政府云
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 美国政府云中的管理员可以设置数据连接器，以将员工数据从组织的人力资源部门 (HR) 系统导入到 Microsoft 365。 这样，你可以将 HR 数据用于内部风险管理策略，以帮助你检测特定用户可能对组织造成内部威胁的活动。
ms.openlocfilehash: 16d6d72d557744e30d41795d5f8c8a17db81c6a3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905924"
---
# <a name="set-up-a-connector-to-import-hr-data-in-us-government"></a><span data-ttu-id="01744-104">设置连接器以导入美国政府中的 HR 数据</span><span class="sxs-lookup"><span data-stu-id="01744-104">Set up a connector to import HR data in US Government</span></span>

<span data-ttu-id="01744-105">可以在 Microsoft 365 合规中心设置数据连接器，以将人力资源 () 数据导入美国政府组织。</span><span class="sxs-lookup"><span data-stu-id="01744-105">You can set up a data connector in the Microsoft 365 compliance center to import human resources (HR) data to your US Government organization.</span></span> <span data-ttu-id="01744-106">与 HR 相关的数据包括员工提交其期限的日期和员工最后一天的日期。</span><span class="sxs-lookup"><span data-stu-id="01744-106">HR-related data includes the date an employee submitted their resignation and date of the employee's last day.</span></span> <span data-ttu-id="01744-107">然后，Microsoft 信息保护解决方案（如内部风险管理解决方案）可以使用此[](insider-risk-management.md)HR 数据，帮助保护组织免受组织内部恶意活动或数据盗窃的攻击。</span><span class="sxs-lookup"><span data-stu-id="01744-107">This HR data can then be used by Microsoft information protection solutions, such as the [insider risk management solution](insider-risk-management.md), to help protect your organization from malicious activity or data theft inside your organization.</span></span> <span data-ttu-id="01744-108">设置 HR 连接器包括：在 Azure Active Directory 中创建用于连接器身份验证的应用，创建包含 HR 数据的 CSV 映射文件，在合规中心创建数据连接器，然后按计划运行脚本 () 该脚本将 CSV 文件的 HR 数据导入到 Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="01744-108">Setting up an HR connector consists of creating an app in Azure Active Directory that's used for authentication by connector, creating a CSV mapping files that contains your HR data, creating a data connector in the compliance center, and then running a script (on a scheduled basis) that ingests the HR data in the CSV file to the Microsoft cloud.</span></span> <span data-ttu-id="01744-109">然后，内部风险管理工具使用数据连接器访问导入到 Microsoft 365 美国政府版组织的 HR 数据。</span><span class="sxs-lookup"><span data-stu-id="01744-109">Then the data connector is used by the insider risk management tool to access the HR data that was imported to your Microsoft 365 US Government organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="01744-110">开始之前</span><span class="sxs-lookup"><span data-stu-id="01744-110">Before you begin</span></span>

- <span data-ttu-id="01744-111">必须在 Exchange Online 中为在步骤 3 中创建 HR 连接器的用户分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="01744-111">The user who creates the HR connector in Step 3 must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="01744-112">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="01744-112">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="01744-113">可以将"邮箱导入导出"角色添加到 Exchange Online 中的"组织管理"角色组。</span><span class="sxs-lookup"><span data-stu-id="01744-113">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="01744-114">也可以创建新的角色组，分配"邮箱导入导出"角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="01744-114">Or you can create a new role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="01744-115">有关详细信息，请参阅"在[](/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的创建角色组或修改角色组部分。</span><span class="sxs-lookup"><span data-stu-id="01744-115">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="01744-116">你需要确定如何定期从组织的 HR 系统 (检索或导出数据) 并将其添加到步骤 2 中介绍的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="01744-116">You'll need to determine how to retrieve or export the data from your organization's HR system (on a regular basis) and add it to the CSV file that's described in Step 2.</span></span> <span data-ttu-id="01744-117">在步骤 4 中运行的脚本将在 CSV 文件中将 HR 数据上载到 Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="01744-117">The script that you run in Step 4 will upload the HR data in the CSV file to the Microsoft cloud.</span></span>

- <span data-ttu-id="01744-118">在步骤 4 中运行的示例脚本将 HR 数据上载到 Microsoft 云，以便其他 Microsoft 工具（如内部风险管理解决方案）可以使用这些数据。</span><span class="sxs-lookup"><span data-stu-id="01744-118">The sample script that you run in Step 4 will upload HR data to the Microsoft cloud so that it can be used by other Microsoft tools, such as the insider risk management solution.</span></span> <span data-ttu-id="01744-119">本示例脚本在任何 Microsoft 标准支持计划或服务下都不受支持。</span><span class="sxs-lookup"><span data-stu-id="01744-119">This sample script isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="01744-120">示例脚本“原样”提供，不提供任何形式的保证。</span><span class="sxs-lookup"><span data-stu-id="01744-120">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="01744-121">Microsoft 进一步拒绝所有默示保证，包括但不限于针对特定用途的适销性或适用性的任何默示保证。</span><span class="sxs-lookup"><span data-stu-id="01744-121">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="01744-122">由于示例脚本及文档的使用或性能所引起的全部风险均由你承担。</span><span class="sxs-lookup"><span data-stu-id="01744-122">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="01744-123">在任何情况下，对于由于使用或者无法使用示例脚本或文档所引起的任何损失（包括但不限于商业利润损失、业务中断、商业信息丢失或者其他经济损失），Microsoft、其作者或者参与创建、制作或交付脚本的任何人概不负责，即使 Microsoft 已被告知可能会出现此类损失。</span><span class="sxs-lookup"><span data-stu-id="01744-123">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="01744-124">步骤 1：在 Azure Active Directory 中创建应用</span><span class="sxs-lookup"><span data-stu-id="01744-124">Step 1: Create an app in Azure Active Directory</span></span>

<span data-ttu-id="01744-125">第一步是在 Azure AD (Azure Active Directory) 。</span><span class="sxs-lookup"><span data-stu-id="01744-125">The first step is to create and register a new app in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="01744-126">该应用将对应于你在步骤 3 创建的 HR 连接器。</span><span class="sxs-lookup"><span data-stu-id="01744-126">The app will correspond to the HR connector that you create in Step 3.</span></span> <span data-ttu-id="01744-127">创建此应用将允许 Azure AD 在 HR 连接器运行时进行身份验证，并尝试访问你的组织。</span><span class="sxs-lookup"><span data-stu-id="01744-127">Creating this app will allow Azure AD to authenticate the HR connector when it runs and attempts to access your organization.</span></span> <span data-ttu-id="01744-128">此应用还将用于对在步骤 4 中运行的脚本进行身份验证，以将 HR 数据上传到 Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="01744-128">This app will also be used to authenticate the script that you run in Step 4 to upload your HR data to the Microsoft cloud.</span></span> <span data-ttu-id="01744-129">创建此 Azure AD 应用期间，请务必保存以下信息。</span><span class="sxs-lookup"><span data-stu-id="01744-129">During the creation of this Azure AD app, be sure to save the following information.</span></span> <span data-ttu-id="01744-130">这些值将在稍后的步骤中使用。</span><span class="sxs-lookup"><span data-stu-id="01744-130">These values will be used in later steps.</span></span>

- <span data-ttu-id="01744-131">Azure AD 应用程序 ID (也称为 *应用 ID* 或 *客户端 ID*) </span><span class="sxs-lookup"><span data-stu-id="01744-131">Azure AD application ID (also called the *app Id* or *client Id*)</span></span>

- <span data-ttu-id="01744-132">Azure AD 应用程序密码 (也称为 *客户端密码*) </span><span class="sxs-lookup"><span data-stu-id="01744-132">Azure AD application secret (also called the *client secret*)</span></span>

- <span data-ttu-id="01744-133">租户 ID (*也称为目录 ID*) </span><span class="sxs-lookup"><span data-stu-id="01744-133">Tenant Id (also called the *directory Id*)</span></span>

<span data-ttu-id="01744-134">有关在 Azure AD 中创建应用的分步说明，请参阅向 Microsoft 标识平台 [注册应用程序](/azure/active-directory/develop/quickstart-register-app)。</span><span class="sxs-lookup"><span data-stu-id="01744-134">For step-by-step instructions for creating an app in Azure AD, see [Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>

## <a name="step-2-prepare-a-csv-file-with-your-hr-data"></a><span data-ttu-id="01744-135">步骤 2：准备包含 HR 数据的 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="01744-135">Step 2: Prepare a CSV file with your HR data</span></span>

<span data-ttu-id="01744-136">下一步是创建一个 CSV 文件，其中包含有关已离开组织的员工的信息。</span><span class="sxs-lookup"><span data-stu-id="01744-136">The next step is to create a CSV file that contains information about employees who have left your organization.</span></span> <span data-ttu-id="01744-137">如开始之前部分所述，你需要确定如何从组织的 HR 系统生成此 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="01744-137">As explained in the Before You Begin section, you'll need to determine how to generate this CSV file from your organization's HR system.</span></span> <span data-ttu-id="01744-138">以下示例显示在记事 (打开的已完成 CSV 文件) 其中包含三个必需参数 (列) 。</span><span class="sxs-lookup"><span data-stu-id="01744-138">The following example shows a completed CSV file (opened in Note Pad) that contains the three required parameters (columns).</span></span> <span data-ttu-id="01744-139">在 Microsoft Excel 中编辑 CSV 文件要容易得多。</span><span class="sxs-lookup"><span data-stu-id="01744-139">It's much easier to edit the CSV file in Microsoft Excel.</span></span>

```text
EmailAddress,TerminationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

<span data-ttu-id="01744-140">CSV 文件的第一行（即标题行）列出了所需的列名称。</span><span class="sxs-lookup"><span data-stu-id="01744-140">The first row, or header row, of the CSV file lists the required column names.</span></span> <span data-ttu-id="01744-141">每个列标题中使用的名称由 (示例中的建议值决定) 。</span><span class="sxs-lookup"><span data-stu-id="01744-141">The name used in each column header is up to you (the ones in the previous example are suggestions).</span></span> <span data-ttu-id="01744-142">但是，在步骤 3 中创建 HR连接器时，必须指定 CSV 文件中使用的相同列名称。</span><span class="sxs-lookup"><span data-stu-id="01744-142">However, the same column names you use in the CSV file *must* be specified when you create the HR connector in Step 3.</span></span> <span data-ttu-id="01744-143">列名称中不要包含空格。</span><span class="sxs-lookup"><span data-stu-id="01744-143">Do not include spaces in the column names.</span></span>

<span data-ttu-id="01744-144">下表介绍了 CSV 文件的每一列：</span><span class="sxs-lookup"><span data-stu-id="01744-144">The following table describes each column in the CSV file:</span></span>

| <span data-ttu-id="01744-145">列名称</span><span class="sxs-lookup"><span data-stu-id="01744-145">Column name</span></span> | <span data-ttu-id="01744-146">说明</span><span class="sxs-lookup"><span data-stu-id="01744-146">Description</span></span> |
|:-----|:-----|
| <span data-ttu-id="01744-147">**EmailAddress**</span><span class="sxs-lookup"><span data-stu-id="01744-147">**EmailAddress**</span></span> <br/> |<span data-ttu-id="01744-148">指定已终止员工的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="01744-148">Specifies the email address of the terminated employee.</span></span>|
| <span data-ttu-id="01744-149">**TerminationDate**</span><span class="sxs-lookup"><span data-stu-id="01744-149">**TerminationDate**</span></span> <br/> |<span data-ttu-id="01744-150">指定在组织中正式终止其雇佣关系的日期。</span><span class="sxs-lookup"><span data-stu-id="01744-150">Specifies the date the person's employment was officially terminated in your organization.</span></span> <span data-ttu-id="01744-151">例如，这可能是员工通知你离开组织的日期。</span><span class="sxs-lookup"><span data-stu-id="01744-151">For example, this may be the date when the employee gave their notice about leaving your organization.</span></span> <span data-ttu-id="01744-152">此日期可能不同于人员最后一天的工作日期。</span><span class="sxs-lookup"><span data-stu-id="01744-152">This date may be the different than the date of the person's last day of work.</span></span> <span data-ttu-id="01744-153">使用以下日期格式 `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` ：，即 [ISO 8601 日期和时间格式](https://www.iso.org/iso-8601-date-and-time-format.html)。</span><span class="sxs-lookup"><span data-stu-id="01744-153">Use the following date format: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm`, which is the [ISO 8601 date and time format](https://www.iso.org/iso-8601-date-and-time-format.html).</span></span>|
|<span data-ttu-id="01744-154">**LastWorkingDate**</span><span class="sxs-lookup"><span data-stu-id="01744-154">**LastWorkingDate**</span></span>|<span data-ttu-id="01744-155">指定离职员工的最后一天工作。</span><span class="sxs-lookup"><span data-stu-id="01744-155">Specifies the last day of work for the terminated employee.</span></span> <span data-ttu-id="01744-156">使用以下日期格式 `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` ：，即 [ISO 8601 日期和时间格式](https://www.iso.org/iso-8601-date-and-time-format.html)。</span><span class="sxs-lookup"><span data-stu-id="01744-156">Use the following date format: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm`, which is the [ISO 8601 date and time format](https://www.iso.org/iso-8601-date-and-time-format.html).</span></span>|
|||

<span data-ttu-id="01744-157">创建包含所需 HR 数据的 CSV 文件后，请与在步骤 4 中运行的脚本存储在同一系统中。</span><span class="sxs-lookup"><span data-stu-id="01744-157">After you create the CSV file with the required HR data, store it on the same system as the script that you run in Step 4.</span></span> <span data-ttu-id="01744-158">请务必实现更新策略，以便 CSV 文件始终包含最新信息。</span><span class="sxs-lookup"><span data-stu-id="01744-158">Be sure to implement an update strategy so the CSV file always contains the most current information.</span></span> <span data-ttu-id="01744-159">这样做可确保无论运行脚本如何，最新的员工离职数据都会上传到 Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="01744-159">Doing so ensures that that whatever you run the script, the most current employee termination data is uploaded to the Microsoft cloud.</span></span>

## <a name="step-3-create-the-hr-connector"></a><span data-ttu-id="01744-160">步骤 3：创建 HR 连接器</span><span class="sxs-lookup"><span data-stu-id="01744-160">Step 3: Create the HR connector</span></span>

<span data-ttu-id="01744-161">下一步是在 Microsoft 365 合规中心创建 HR 连接器。</span><span class="sxs-lookup"><span data-stu-id="01744-161">The next step is to create an HR connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="01744-162">在步骤 4 中运行脚本后，您创建的 HR 连接器将导入 CSV 文件的 HR 数据到 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="01744-162">After you run the script in Step 4, the HR connector that you create will ingest the HR data from the CSV file to your Microsoft 365 organization.</span></span> <span data-ttu-id="01744-163">在此步骤中，请确保复制创建连接器时生成的作业 ID。</span><span class="sxs-lookup"><span data-stu-id="01744-163">In this step, be sure to copy the job ID that's generated when you create the connector.</span></span> <span data-ttu-id="01744-164">运行脚本时，将使用作业 ID。</span><span class="sxs-lookup"><span data-stu-id="01744-164">You'll use the job ID when you run the script.</span></span>

1. <span data-ttu-id="01744-165">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com) 然后单击左侧 **导航中的** "数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="01744-165">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="01744-166">在"**数据连接器"页上** 的 **"HR"下**，单击"查看 **"。**</span><span class="sxs-lookup"><span data-stu-id="01744-166">On the **Data connectors** page under **HR**, click **View**.</span></span>

3. <span data-ttu-id="01744-167">在 **"HR"** 页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="01744-167">On the **HR** page, click **Add connector**.</span></span>

4. <span data-ttu-id="01744-168">在"**身份验证凭据"** 页上，执行以下操作，然后单击"下一步 **"：**</span><span class="sxs-lookup"><span data-stu-id="01744-168">On the **Authentication credentials** page, do the following and then click **Next**:</span></span>

   1. <span data-ttu-id="01744-169">键入或粘贴你在步骤 1 中创建的 Azure 应用的 Azure AD 应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="01744-169">Type or paste the Azure AD application ID for the Azure app that you created in Step 1.</span></span>

   1. <span data-ttu-id="01744-170">键入 HR 连接器的名称。</span><span class="sxs-lookup"><span data-stu-id="01744-170">Type a name for the HR connector.</span></span>

5. <span data-ttu-id="01744-171">在"**文件映射**"页上，键入三列标题的名称 (在每个相应的框中键入在步骤 2 中创建的 CSV 文件) 也称为参数 *) 。*</span><span class="sxs-lookup"><span data-stu-id="01744-171">On the **File mapping** page, type the names of the three column headers (also called *parameters*) from the CSV file that you created in Step 2 in each of the appropriate boxes.</span></span> <span data-ttu-id="01744-172">名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="01744-172">The names are not case-sensitive.</span></span> <span data-ttu-id="01744-173">如前所述，在这些框中键入的名称必须与 CSV 文件中的参数名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="01744-173">As previously explained, the names that you type in these boxes must match the parameter names in your CSV file.</span></span> <span data-ttu-id="01744-174">例如，以下屏幕截图显示了步骤 2 中显示的示例 CSV 文件中的示例的参数名称。</span><span class="sxs-lookup"><span data-stu-id="01744-174">For example, the following screenshot shows the parameter names from the example in sample CSV file shown in Step 2.</span></span>

   ![列标题名称与 CSV 文件中的名称匹配](../media/HRConnectorWizard3.png)

6. <span data-ttu-id="01744-176">在" **审阅** "页上，查看设置，然后单击" **完成** "以创建连接器。</span><span class="sxs-lookup"><span data-stu-id="01744-176">On the **Review** page, review your settings and then click **Finish** to create the connector.</span></span>

   <span data-ttu-id="01744-177">将显示一个状态页，确认连接器已创建。</span><span class="sxs-lookup"><span data-stu-id="01744-177">A status page is displayed that confirms the connector was created.</span></span> <span data-ttu-id="01744-178">此页面包含两个重要内容，您需要完成下一步以运行示例脚本来上载 HR 数据。</span><span class="sxs-lookup"><span data-stu-id="01744-178">This page contains two important things that you need to complete the next step to run the sample script to upload your HR data.</span></span>

   ![查看包含作业 ID 的页面和指向 github 的链接，获取示例脚本](../media/HRConnector_Confirmation.png)

   1. <span data-ttu-id="01744-180">**作业 ID。**</span><span class="sxs-lookup"><span data-stu-id="01744-180">**Job ID.**</span></span> <span data-ttu-id="01744-181">您需要此作业 ID，以在下一步中运行脚本。</span><span class="sxs-lookup"><span data-stu-id="01744-181">You'll need this job ID to run the script in the next step.</span></span> <span data-ttu-id="01744-182">可以从此页面或连接器飞出页复制它。</span><span class="sxs-lookup"><span data-stu-id="01744-182">You can copy it from this page or from the connector flyout page.</span></span>
   
   1. <span data-ttu-id="01744-183">**指向示例脚本的链接。**</span><span class="sxs-lookup"><span data-stu-id="01744-183">**Link to sample script.**</span></span> <span data-ttu-id="01744-184">单击 **"此处** "链接以转到 GitHub 网站以访问示例脚本 (该链接将打开一个新的) 。</span><span class="sxs-lookup"><span data-stu-id="01744-184">Click the **here** link to go to the GitHub site to access the sample script (the link opens a new window).</span></span> <span data-ttu-id="01744-185">保持此窗口为打开状态，以便你可以复制步骤 4 中的脚本。</span><span class="sxs-lookup"><span data-stu-id="01744-185">Keep this window open so that you can copy the script in Step 4.</span></span> <span data-ttu-id="01744-186">或者，您可以为目标添加书签或复制 URL，以便可以在步骤 4 中再次访问它。</span><span class="sxs-lookup"><span data-stu-id="01744-186">Alternatively, you can bookmark the destination or copy the URL so you can access it again in Step 4.</span></span> <span data-ttu-id="01744-187">连接器飞出页面上也提供此链接。</span><span class="sxs-lookup"><span data-stu-id="01744-187">This link is also available on the connector flyout page.</span></span>

7. <span data-ttu-id="01744-188">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="01744-188">Click **Done**.</span></span>

   <span data-ttu-id="01744-189">新连接器显示在"连接器"选项卡 **上的** 列表中。</span><span class="sxs-lookup"><span data-stu-id="01744-189">The new connector is displayed in the list on the **Connectors** tab.</span></span> 

8. <span data-ttu-id="01744-190">单击刚创建的 HR 连接器以显示该飞出页，其中包含有关连接器的属性和其他信息。</span><span class="sxs-lookup"><span data-stu-id="01744-190">Click the HR connector that you just created to display the flyout page, which contains properties and other information about the connector.</span></span>

   ![新 HR 连接器的"飞出"页面](../media/HRConnectorWizard7.png)

   <span data-ttu-id="01744-192">如果你尚未这样做，你可以复制 **Azure 应用 ID** 和连接器作业 **ID 的值**。</span><span class="sxs-lookup"><span data-stu-id="01744-192">If you haven't already done so, you can copy the values for the **Azure App ID** and **Connector job ID**.</span></span> <span data-ttu-id="01744-193">下一步中，将需要使用这些脚本来运行脚本。</span><span class="sxs-lookup"><span data-stu-id="01744-193">You'll need these to run the script in the next step.</span></span> <span data-ttu-id="01744-194">您还可以从飞出页面下载脚本 (下一步中的链接下载脚本。) </span><span class="sxs-lookup"><span data-stu-id="01744-194">You can also download the script from the flyout page (or download it using the link in the next step.)</span></span>

   <span data-ttu-id="01744-195">还可以单击" **编辑"** 更改在"文件映射"页上定义的 Azure 应用 ID 或列 **标题** 名称。</span><span class="sxs-lookup"><span data-stu-id="01744-195">You can also click **Edit** to change the Azure App ID or the column header names that you defined on the **File mapping** page.</span></span>

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a><span data-ttu-id="01744-196">步骤 4：运行示例脚本以上载 HR 数据</span><span class="sxs-lookup"><span data-stu-id="01744-196">Step 4: Run the sample script to upload your HR data</span></span>

<span data-ttu-id="01744-197">设置 HR 连接器的最后一步是运行示例脚本，该脚本将在 CSV 文件 (（在步骤 2) 中创建）中将 HR 数据上载到 Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="01744-197">The last step in setting up an HR connector is to run a sample script that will upload the HR data in the CSV file (that you created in Step 2) to the Microsoft cloud.</span></span> <span data-ttu-id="01744-198">具体而言，脚本将数据上载到 HR 连接器。</span><span class="sxs-lookup"><span data-stu-id="01744-198">Specifically, the script uploads the data to the HR connector.</span></span> <span data-ttu-id="01744-199">运行脚本后，在步骤 3 中创建的 HR 连接器将 HR 数据导入到 Microsoft 365 组织，其他合规性工具（如预览体验成员风险管理解决方案）可以访问该组织。</span><span class="sxs-lookup"><span data-stu-id="01744-199">After you run the script, the HR connector that you created in Step 3 imports the HR data to your Microsoft 365 organization where it can accessed by other compliance tools, such as the Insider risk management solution.</span></span> <span data-ttu-id="01744-200">运行脚本后，请考虑安排一项任务，每天自动运行一次，以便将最新的员工离职数据上传到 Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="01744-200">After you run the script, consider scheduling a task to run it automatically on a daily basis so the most current employee termination data is uploaded to the Microsoft cloud.</span></span> <span data-ttu-id="01744-201">请参阅 [计划脚本自动运行](#optional-step-6-schedule-the-script-to-run-automatically)。</span><span class="sxs-lookup"><span data-stu-id="01744-201">See [Schedule the script to run automatically](#optional-step-6-schedule-the-script-to-run-automatically).</span></span>

1. <span data-ttu-id="01744-202">转到上一步中打开的窗口，以使用示例脚本访问 GitHub 网站。</span><span class="sxs-lookup"><span data-stu-id="01744-202">Go to window that you left open from the previous step to access the GitHub site with the sample script.</span></span> <span data-ttu-id="01744-203">或者，打开已添加书签的网站或使用您复制的 URL。</span><span class="sxs-lookup"><span data-stu-id="01744-203">Alternatively, open the bookmarked site or use the URL that you copied.</span></span>

2. <span data-ttu-id="01744-204">单击" **原始** "按钮以在文本视图中显示脚本。</span><span class="sxs-lookup"><span data-stu-id="01744-204">Click the **Raw** button to display the script in text view.</span></span>

3. <span data-ttu-id="01744-205">复制示例脚本中所有的行，然后将它们保存到文本文件。</span><span class="sxs-lookup"><span data-stu-id="01744-205">Copy all the lines in the sample script and then save them to a text file.</span></span>

4. <span data-ttu-id="01744-206">如有必要，修改组织的示例脚本。</span><span class="sxs-lookup"><span data-stu-id="01744-206">Modify the sample script for your organization, if necessary.</span></span>

5. <span data-ttu-id="01744-207">使用 文件名后缀 将文本文件另存为Windows PowerShell脚本文件 `.ps1` ;例如， `HRConnector.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="01744-207">Save the text file as a Windows PowerShell script file by using a filename suffix of `.ps1`; for example, `HRConnector.ps1`.</span></span>

6. <span data-ttu-id="01744-208">在本地计算机上打开命令提示符，然后转到保存脚本的目录。</span><span class="sxs-lookup"><span data-stu-id="01744-208">Open a Command Prompt on your local computer, and go to the directory where you saved the script.</span></span>

7. <span data-ttu-id="01744-209">运行以下命令，将 CSV 文件的 HR 数据上载到 Microsoft 云;例如：</span><span class="sxs-lookup"><span data-stu-id="01744-209">Run the following command to upload the HR data in the CSV file to the Microsoft cloud; for example:</span></span>

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   <span data-ttu-id="01744-210">下表介绍了要用于此脚本的参数及其所需值。</span><span class="sxs-lookup"><span data-stu-id="01744-210">The following table describes the parameters to use with this script and their required values.</span></span> <span data-ttu-id="01744-211">在之前步骤中获取的信息将使用这些参数的值。</span><span class="sxs-lookup"><span data-stu-id="01744-211">The information you obtained in the previous steps is used in the values for these parameters.</span></span>

   | <span data-ttu-id="01744-212">参数</span><span class="sxs-lookup"><span data-stu-id="01744-212">Parameter</span></span> | <span data-ttu-id="01744-213">说明</span><span class="sxs-lookup"><span data-stu-id="01744-213">Description</span></span> |
   |:-----|:-----|:-----|
   |`tenantId`|<span data-ttu-id="01744-214">在步骤 1 中获取的 Microsoft 365 组织的 ID。</span><span class="sxs-lookup"><span data-stu-id="01744-214">The Id for your Microsoft 365 organization that you obtained in Step 1.</span></span> <span data-ttu-id="01744-215">还可以在 Azure AD 管理中心的"概述"边栏选项卡上获取组织的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="01744-215">You can also obtain the tenant Id for your organization on the **Overview** blade in the Azure AD admin center.</span></span> <span data-ttu-id="01744-216">这用于标识您的组织。</span><span class="sxs-lookup"><span data-stu-id="01744-216">This is used to identify your organization.</span></span>|
   |`appId` |<span data-ttu-id="01744-217">步骤 1 中你在 Azure AD 中创建的应用的 Azure AD 应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="01744-217">The Azure AD application Id for the app that you created in Azure AD in Step 1.</span></span> <span data-ttu-id="01744-218">当脚本尝试访问你的 Microsoft 365 组织时，Azure AD 会使用此功能进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="01744-218">This is used by Azure AD for authentication when the script attempts to accesses your Microsoft 365 organization.</span></span> |
   |`appSecret`|<span data-ttu-id="01744-219">步骤 1 中你在 Azure AD 中创建的应用的 Azure AD 应用程序密码。</span><span class="sxs-lookup"><span data-stu-id="01744-219">The Azure AD application secret for the app that you created in Azure AD in Step 1.</span></span> <span data-ttu-id="01744-220">这还用于身份验证。</span><span class="sxs-lookup"><span data-stu-id="01744-220">This also used for authentication.</span></span>|
   |`jobId`|<span data-ttu-id="01744-221">在步骤 3 中创建的 HR 连接器的作业 ID。</span><span class="sxs-lookup"><span data-stu-id="01744-221">The job ID for the HR connector that you created in Step 3.</span></span> <span data-ttu-id="01744-222">这用于将上载到 Microsoft 云的 HR 数据与 HR 连接器关联。</span><span class="sxs-lookup"><span data-stu-id="01744-222">This is used to associate the HR data that is uploaded to the Microsoft cloud with the HR connector.</span></span>|
   |`csvFilePath`|<span data-ttu-id="01744-223">CSV 文件的文件路径 (步骤 2 中创建的脚本) 存储在同一系统中。</span><span class="sxs-lookup"><span data-stu-id="01744-223">The file path for the CSV file (stored on the same system as the script) that you created in Step 2.</span></span> <span data-ttu-id="01744-224">尝试避免文件路径中的空格;否则请使用单引号。</span><span class="sxs-lookup"><span data-stu-id="01744-224">Try to avoid spaces in the file path; otherwise use single quotation marks.</span></span>|
   |||
   
   <span data-ttu-id="01744-225">下面是使用每个参数的实际值的 HR 连接器脚本的语法示例：</span><span class="sxs-lookup"><span data-stu-id="01744-225">Here's an example of the syntax for the HR connector script using actual values for each parameter:</span></span>

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   <span data-ttu-id="01744-226">如果上传成功，脚本将显示" **上传成功"** 消息。</span><span class="sxs-lookup"><span data-stu-id="01744-226">If the upload is successful, the script displays the **Upload Successful** message.</span></span>

   > [!NOTE]
   > <span data-ttu-id="01744-227">如果由于执行策略而运行上一个命令时遇到问题，[](/powershell/module/microsoft.powershell.core/about/about_execution_policies)请参阅关于执行策略和[Set-ExecutionPolicy，](/powershell/module/microsoft.powershell.security/set-executionpolicy)了解设置执行策略的指南。</span><span class="sxs-lookup"><span data-stu-id="01744-227">If you have problems running the previous command because of execution policies, see [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies) and [Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy) for guidance about setting execution policies.</span></span>

## <a name="step-5-monitor-the-hr-connector"></a><span data-ttu-id="01744-228">步骤 5：监视 HR 连接器</span><span class="sxs-lookup"><span data-stu-id="01744-228">Step 5: Monitor the HR connector</span></span>

<span data-ttu-id="01744-229">创建 HR 连接器并运行脚本以上传 HR 数据后，可以在 Microsoft 365 合规中心查看连接器并上传状态。</span><span class="sxs-lookup"><span data-stu-id="01744-229">After you create the HR connector and run the script to upload your HR data, you can view the connector and upload status in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="01744-230">如果安排脚本定期自动运行，还可以在上次运行脚本后查看当前状态。</span><span class="sxs-lookup"><span data-stu-id="01744-230">If you schedule the script to run automatically on a regular basis, you can also view the current status after the last time the script ran.</span></span>

1. <span data-ttu-id="01744-231">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="01744-231">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="01744-232">单击 **"连接器"** 选项卡，然后选择 HR 连接器以显示飞出页面。</span><span class="sxs-lookup"><span data-stu-id="01744-232">Click the **Connectors** tab and then select the HR connector to display the flyout page.</span></span> <span data-ttu-id="01744-233">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="01744-233">This page contains the properties and information about the connector.</span></span>

   ![包含属性和状态的 HR 连接器飞出页](../media/HRConnectorFlyout1.png)

3. <span data-ttu-id="01744-235">在 **"进度\*\*\*\*"下，** 单击"下载日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="01744-235">Under **Progress**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="01744-236">此日志包含有关脚本每次运行以及将数据从 CSV 文件上载到 Microsoft 云时的信息。</span><span class="sxs-lookup"><span data-stu-id="01744-236">This log contains information about each time the script runs and uploads the data from the CSV file to the Microsoft cloud.</span></span> 

   ![HR 连接器日志文件 CSV 文件上传的行数](../media/HRConnectorLogFile.png)

   <span data-ttu-id="01744-238">`RecordsSaved`字段指示 CSV 文件中已上载的行数。</span><span class="sxs-lookup"><span data-stu-id="01744-238">The `RecordsSaved` field indicates the number of rows in the CSV file that uploaded.</span></span> <span data-ttu-id="01744-239">例如，如果 CSV 文件包含四行，则字段的值为 4（如果脚本成功上传 CSV 文件的所有 `RecordsSaved` 行）。</span><span class="sxs-lookup"><span data-stu-id="01744-239">For example, if the CSV file contains four rows, then the value of the `RecordsSaved` fields is 4, if the script successfully uploaded all the rows in the CSV file.</span></span>

<span data-ttu-id="01744-240">如果尚未在步骤 4 中运行脚本，则"上次导入"下将显示用于下载脚本 **的链接**。</span><span class="sxs-lookup"><span data-stu-id="01744-240">If you've haven't run the script in Step 4, a link to download the script is displayed under **Last import**.</span></span> <span data-ttu-id="01744-241">可以下载脚本，然后按照步骤 4 中的步骤运行它。</span><span class="sxs-lookup"><span data-stu-id="01744-241">You can download the script and then follow the steps in Step 4 to run it.</span></span>

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a><span data-ttu-id="01744-242"> (可选) 步骤 6：计划脚本自动运行</span><span class="sxs-lookup"><span data-stu-id="01744-242">(Optional) Step 6: Schedule the script to run automatically</span></span>

<span data-ttu-id="01744-243">若要确保组织的最新 HR 数据可用于内部风险管理解决方案等工具，建议安排脚本定期自动运行，如每天运行一次。</span><span class="sxs-lookup"><span data-stu-id="01744-243">To make sure the latest HR data from your organization is available to tools like the insider risk management solution, we recommend that you schedule the script to run automatically on a recurring basis, such as once a day.</span></span> <span data-ttu-id="01744-244">这还要求你在类似的 (（如果不是同一) 计划）上更新 CSV 文件的 HR 数据，以便其中包含有关离开组织的员工的最新信息。</span><span class="sxs-lookup"><span data-stu-id="01744-244">This also requires that you update the HR data in the CSV file on a similar (if not the same) schedule so that it contains the latest information about employees who leave your organization.</span></span> <span data-ttu-id="01744-245">目标是上载最新的 HR 数据，以便 HR 连接器能够将其提供给内部风险管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="01744-245">The goal is to upload the most current HR data so that the HR connector can make it available to the insider risk management solution.</span></span>

<span data-ttu-id="01744-246">You can user the Task Scheduler app in Windows to automatically run the script every day.</span><span class="sxs-lookup"><span data-stu-id="01744-246">You can user the Task Scheduler app in Windows to automatically run the script every day.</span></span>

1. <span data-ttu-id="01744-247">在本地计算机上，单击 **Windows"开始"** 按钮，然后键入 **"任务计划程序"。**</span><span class="sxs-lookup"><span data-stu-id="01744-247">On your local computer, click the Windows **Start** button and then type **Task Scheduler**.</span></span>

2. <span data-ttu-id="01744-248">单击任务 **计划程序** 应用以打开它。</span><span class="sxs-lookup"><span data-stu-id="01744-248">Click the **Task Scheduler** app to open it.</span></span>

3. <span data-ttu-id="01744-249">在"**操作"部分**，单击"**创建任务"。**</span><span class="sxs-lookup"><span data-stu-id="01744-249">In the **Actions** section, click **Create Task**.</span></span>

4. <span data-ttu-id="01744-250">在" **常规"** 选项卡上，键入计划任务的描述性名称;例如 **，HR 连接器脚本**。</span><span class="sxs-lookup"><span data-stu-id="01744-250">On the **General** tab, type a descriptive name for the scheduled task; for example, **HR Connector Script**.</span></span> <span data-ttu-id="01744-251">还可以添加可选说明。</span><span class="sxs-lookup"><span data-stu-id="01744-251">You can also add an optional description.</span></span>

5. <span data-ttu-id="01744-252">在 **"安全选项**"下，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="01744-252">Under **Security options**, do the following:</span></span>

   1. <span data-ttu-id="01744-253">确定是仅在您登录到计算机时运行脚本，还是在您登录时运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="01744-253">Determine whether to run the script only when you're logged on to the computer or run it when you're logged on or not.</span></span>
   
   1. <span data-ttu-id="01744-254">确保选中 **了"使用最高权限** 运行"复选框。</span><span class="sxs-lookup"><span data-stu-id="01744-254">Make sure that the **Run with the highest privileges** checkbox is selected.</span></span>

6. <span data-ttu-id="01744-255">选择 **"触发器"** 选项卡，单击 **"新建**"，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="01744-255">Select the **Triggers** tab, click **New**, and then do the following things:</span></span>

   1. <span data-ttu-id="01744-256">在 **"** 设置"下，选择" **每天** "选项，然后选择首次运行脚本的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="01744-256">Under **Settings**, select the **Daily** option, and then choose a date and time to run the script for the first time.</span></span> <span data-ttu-id="01744-257">脚本将每天在同一指定时间运行。</span><span class="sxs-lookup"><span data-stu-id="01744-257">The script will every day at the same specified time.</span></span>
   
   1. <span data-ttu-id="01744-258">在 **"高级设置**"下，确保 **选中"已启用** "复选框。</span><span class="sxs-lookup"><span data-stu-id="01744-258">Under **Advanced settings**, make sure the **Enabled** checkbox is selected.</span></span>
   
   1. <span data-ttu-id="01744-259">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="01744-259">Click **Ok**.</span></span>

7. <span data-ttu-id="01744-260">选择" **操作"** 选项卡，单击 **"新建**"，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="01744-260">Select the **Actions** tab, click **New**, and then do the following things:</span></span>

   ![为 HR 连接器脚本创建新的计划任务的操作设置](../media/HRConnectorScheduleTask1.png)

   1. <span data-ttu-id="01744-262">在 **"操作** "下拉列表中，确保已 **选择"启动程序** "。</span><span class="sxs-lookup"><span data-stu-id="01744-262">In the **Action** dropdown list, make sure that **Start a program** is selected.</span></span>

   1. <span data-ttu-id="01744-263">在"**程序/脚本**"框中，单击"浏览"，然后转到以下位置并选择它，以便路径显示在框中 `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` ：。</span><span class="sxs-lookup"><span data-stu-id="01744-263">In the **Program/script** box, click **Browse**, and go to the following location and select it so the path is displayed in the box: `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe`.</span></span>

   1. <span data-ttu-id="01744-264">在" **添加 (可选) "** 框中，粘贴在步骤 4 中运行相同的脚本命令。</span><span class="sxs-lookup"><span data-stu-id="01744-264">In the **Add arguments (optional)** box, paste the same script command that you ran in Step 4.</span></span> <span data-ttu-id="01744-265">例如，`.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`</span><span class="sxs-lookup"><span data-stu-id="01744-265">For example, `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`</span></span>

   1. <span data-ttu-id="01744-266">在 **" (可选**) "框中，粘贴在步骤 4 中运行脚本的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="01744-266">In the **Start in (optional)** box, paste the folder location of the script that you ran in Step 4.</span></span> <span data-ttu-id="01744-267">例如，`C:\Users\contosoadmin\Desktop\Scripts`。</span><span class="sxs-lookup"><span data-stu-id="01744-267">For example, `C:\Users\contosoadmin\Desktop\Scripts`.</span></span>

   1. <span data-ttu-id="01744-268">单击 **"** 确定"保存新操作的设置。</span><span class="sxs-lookup"><span data-stu-id="01744-268">Click **Ok** to save the settings for the new action.</span></span>

8. <span data-ttu-id="01744-269">在" **创建任务"** 窗口中，单击" **确定** "保存计划任务。</span><span class="sxs-lookup"><span data-stu-id="01744-269">In the **Create Task** window, click **Ok** to save the scheduled task.</span></span> <span data-ttu-id="01744-270">系统可能会提示你输入用户帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="01744-270">You might be prompted to enter your user account credentials.</span></span>

   <span data-ttu-id="01744-271">新任务将显示在任务计划程序库中。</span><span class="sxs-lookup"><span data-stu-id="01744-271">The new task is displayed in the Task Scheduler Library.</span></span>

   ![新任务显示在任务计划程序库中](../media/HRConnectorTaskSchedulerLibrary.png)

   <span data-ttu-id="01744-273">显示脚本上次运行的时间和计划运行的下一次。</span><span class="sxs-lookup"><span data-stu-id="01744-273">The last time the script ran and the next time it's scheduled to run is displayed.</span></span> <span data-ttu-id="01744-274">可以双击任务进行编辑。</span><span class="sxs-lookup"><span data-stu-id="01744-274">You can double-click the task to edit it.</span></span>

   <span data-ttu-id="01744-275">还可以验证脚本上次在合规中心中相应 HR 连接器的飞出页面上运行的时间。</span><span class="sxs-lookup"><span data-stu-id="01744-275">You can also verify the last time the script ran on the flyout page of the corresponding HR connector in the compliance center.</span></span>