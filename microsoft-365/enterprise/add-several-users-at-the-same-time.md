---
title: 同时将多个用户添加到 Microsoft 365 - 管理员帮助
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_AddUsersCSV
- O365M_AddUsersCSV
- O365E_AddUsersCSV
search.appverid:
- MET150
- MOP150
- MOE150
- MED150
- GMA150
- MBS150
- GEA150
- BCS160
ms.assetid: 1f5767ed-e717-4f24-969c-6ea9d412ca88
description: '了解如何从电子表格或其他 CSV 格式文件的列表向 Microsoft 365 商业版添加多个用户。 观看 YouTube 上说明如何向 Microsoft 365 添加帐户的视频。 在此过程结束时，每个拥有帐户的用户都将拥有一个 Microsoft 365 邮箱。 '
ms.openlocfilehash: 71e1d1f9261fc58e9f49fac5050e07fd7b8839e3
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698263"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a><span data-ttu-id="298e9-105">同时将多个用户添加到 Microsoft 365 - 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="298e9-105">Add several users at the same time to Microsoft 365 - Admin Help</span></span>

<span data-ttu-id="298e9-106">团队中的每个人都需要一个用户帐户，然后才能登录和访问 Microsoft 365 服务，如电子邮件和 Office。</span><span class="sxs-lookup"><span data-stu-id="298e9-106">Each person on your team needs a user account before they can sign in and access Microsoft 365 services, such as email and Office.</span></span> <span data-ttu-id="298e9-107">如果您有很多用户，则可以通过 Excel 电子表格或其他以 CSV 格式保存的文件一次添加其帐户。</span><span class="sxs-lookup"><span data-stu-id="298e9-107">If you have a lot of people, you can add their accounts all at once from an Excel spreadsheet or other file saved in CSV format.</span></span> [<span data-ttu-id="298e9-108">不确定什么是 CSV 格式？</span><span class="sxs-lookup"><span data-stu-id="298e9-108">Not sure what CSV format is?</span></span>](add-several-users-at-the-same-time.md#__toc316652088)
  
> [!NOTE] 
> <span data-ttu-id="298e9-109">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="298e9-109">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a><span data-ttu-id="298e9-110">在 Microsoft 365 管理中心中添加多个用户</span><span class="sxs-lookup"><span data-stu-id="298e9-110">Add multiple users in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="298e9-111">使用工作或学校帐户登录 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="298e9-111">Sign in to Microsoft 365 with your work or school account.</span></span> 
    
2. <span data-ttu-id="298e9-112">在管理中心中，选择 **"用户** \> **活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="298e9-112">In the admin center, choose **Users** \> **Active users**.</span></span>

3. <span data-ttu-id="298e9-113">选择 **"添加多个用户"。**</span><span class="sxs-lookup"><span data-stu-id="298e9-113">Select **Add multiple users**.</span></span>

4. <span data-ttu-id="298e9-114">在" **导入多个用户** "面板上，可以选择下载包含或不填充示例数据的示例 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="298e9-114">On the **Import multiple users** panel, you can optionally download a sample CSV file with or without sample data filled in.</span></span> 
    
    <span data-ttu-id="298e9-115">电子表格需要包含与示例一完全相同的列标题 (用户名、名字等) 。</span><span class="sxs-lookup"><span data-stu-id="298e9-115">Your spreadsheet needs to include the **exact same column headings** as the sample one (User Name, First Name, and so on).</span></span> <span data-ttu-id="298e9-116">如果使用模板，在文本编辑工具（如记事本）中打开它，并考虑将第 1 行的所有数据都单独保留，并且仅输入行 2 和下面的数据。</span><span class="sxs-lookup"><span data-stu-id="298e9-116">If you use the template, open it in a text editing tool, like Notepad, and consider leaving all the data in row 1 alone, and only entering data in rows 2 and below.</span></span> 
    
    <span data-ttu-id="298e9-117">电子表格还需要包括用户名值，例如 (bob@contoso.com) 和 显示名称 (Bob Kelly) for each user。</span><span class="sxs-lookup"><span data-stu-id="298e9-117">Your spreadsheet also needs to include values for the user name (like bob@contoso.com) and a display name (like Bob Kelly) for each user.</span></span> 
    
  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. <span data-ttu-id="298e9-118">在框中输入文件路径，**或选择"** 浏览"浏览到 CSV 文件位置，然后选择"**验证"。**</span><span class="sxs-lookup"><span data-stu-id="298e9-118">Enter a file path into the box, or choose **Browse** to browse to the CSV file location, then choose **Verify**.</span></span>
  
    <span data-ttu-id="298e9-119">如果文件有问题，则问题将显示在面板中。</span><span class="sxs-lookup"><span data-stu-id="298e9-119">If there are problems with the file, the problem is displayed in the panel.</span></span> <span data-ttu-id="298e9-120">您还可以下载日志文件。</span><span class="sxs-lookup"><span data-stu-id="298e9-120">You can also download a log file.</span></span>
    
5. <span data-ttu-id="298e9-121">在 **"设置用户选项** "对话框中，可以设置登录状态并选择将分配给所有用户的产品许可证。</span><span class="sxs-lookup"><span data-stu-id="298e9-121">On the **Set user options** dialog you can set the sign-in status and choose the product license that will be assigned to all users.</span></span> 
    
6. <span data-ttu-id="298e9-122">在"查看结果"对话框中，可以选择将结果发送给您自己或其他用户 (密码将为纯文本) 并且可以查看已创建的用户数，以及是否需要购买更多许可证以分配给一些新用户。</span><span class="sxs-lookup"><span data-stu-id="298e9-122">On the **View your result** dialog you can choose to send the results to either yourself or other users (passwords will be in plain text) and you can see how many users were created, and if you need to purchase more licenses to assign to some of the new users.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="298e9-123">后续步骤</span><span class="sxs-lookup"><span data-stu-id="298e9-123">Next steps</span></span>
<span data-ttu-id="298e9-124"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="298e9-124"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="298e9-125">现在，这些用户拥有帐户，他们需要在电脑或 Mac 上下载并安装或重新安装[Microsoft 365 或 Office 2016。](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)</span><span class="sxs-lookup"><span data-stu-id="298e9-125">Now that these people have accounts, they need to [Download and install or reinstall Microsoft 365 or Office 2016 on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> <span data-ttu-id="298e9-126">团队中每个人都可以在最多 5 台电脑或 Mac 上安装 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="298e9-126">Each person on your team can install Microsoft 365 on up to 5 PCs or Macs.</span></span> 
    
- <span data-ttu-id="298e9-127">每个人还可以在最多 5 台平板电脑和 5 部手机上的移动设备上设置 [Office](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) 应用和电子邮件，如 iPhone、iPad 和 Android 手机和平板电脑。</span><span class="sxs-lookup"><span data-stu-id="298e9-127">Each person can also [Set up Office apps and email on a mobile device](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) on up to 5 tablets and 5 phones, such as iPhones, iPads, and Android phones and tablets.</span></span> <span data-ttu-id="298e9-128">这样，他们可以从任何位置编辑 Office 文件。</span><span class="sxs-lookup"><span data-stu-id="298e9-128">This way they can edit Office files from anywhere.</span></span> 
    
    <span data-ttu-id="298e9-129">有关安装步骤的端到端列表，请参阅"设置 [Microsoft 365](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) 商业版"。</span><span class="sxs-lookup"><span data-stu-id="298e9-129">See [Set up Microsoft 365 for business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) for an end-to-end list of the setup steps.</span></span> 
    
## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a><span data-ttu-id="298e9-130">有关如何将用户添加到 Microsoft 365 中详细信息</span><span class="sxs-lookup"><span data-stu-id="298e9-130">More information about how to add users to Microsoft 365</span></span>
<span data-ttu-id="298e9-131"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="298e9-131"><a name="bk_preview"> </a></span></span>

### <a name="not-sure-what-csv-format-is"></a><span data-ttu-id="298e9-132">不确定什么是 CSV 格式？</span><span class="sxs-lookup"><span data-stu-id="298e9-132">Not sure what CSV format is?</span></span>
<span data-ttu-id="298e9-133"><a name="__toc316652088"> </a></span><span class="sxs-lookup"><span data-stu-id="298e9-133"><a name="__toc316652088"> </a></span></span>

<span data-ttu-id="298e9-134">CSV 文件是包含逗号分隔值的文件。</span><span class="sxs-lookup"><span data-stu-id="298e9-134">A CSV file is a file with comma separated values.</span></span> <span data-ttu-id="298e9-135">可以使用任何文本编辑器或电子表格程序（如 Excel）创建或编辑此类文件。</span><span class="sxs-lookup"><span data-stu-id="298e9-135">You can create or edit a file like this with any text editor or spreadsheet program, such as Excel.</span></span>
  
<span data-ttu-id="298e9-136">您可以下载 [此示例电子表格](https://www.microsoft.com/download/details.aspx?id=45485) 作为起点。</span><span class="sxs-lookup"><span data-stu-id="298e9-136">You can download [this sample spreadsheet](https://www.microsoft.com/download/details.aspx?id=45485) as a starting point.</span></span> <span data-ttu-id="298e9-137">请记住，Microsoft 365 需要第一行中的列标题，因此不要将它们替换为其他标题。</span><span class="sxs-lookup"><span data-stu-id="298e9-137">Remember that Microsoft 365 requires column headings in the first row so don't replace them with something else.</span></span> 
  
<span data-ttu-id="298e9-138">使用新名称保存文件，并指定 CSV 格式。</span><span class="sxs-lookup"><span data-stu-id="298e9-138">Save the file with a new name, and specify CSV format.</span></span>
  
![如何以 CSV 格式将文件保存为 Excel 的图像](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
<span data-ttu-id="298e9-140">保存文件时，如果以 CSV 格式保存文件，则可能会提示工作簿中的某些功能将丢失。</span><span class="sxs-lookup"><span data-stu-id="298e9-140">When you save the file, you'll probably get a prompt that some features in your workbook will be lost if you save the file in CSV format.</span></span> <span data-ttu-id="298e9-141">这没有问题。</span><span class="sxs-lookup"><span data-stu-id="298e9-141">This is okay.</span></span> <span data-ttu-id="298e9-142">单击" **是**"即可继续。</span><span class="sxs-lookup"><span data-stu-id="298e9-142">Click **Yes** to continue.</span></span> 
  
![从 Excel 获取的提示图片，询问是否确实要将文件保存为 CSV 格式](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a><span data-ttu-id="298e9-144">设置电子表格格式的提示</span><span class="sxs-lookup"><span data-stu-id="298e9-144">Tips for formatting your spreadsheet</span></span>
<span data-ttu-id="298e9-145"><a name="__toc314595848"> </a></span><span class="sxs-lookup"><span data-stu-id="298e9-145"><a name="__toc314595848"> </a></span></span>

- <span data-ttu-id="298e9-146">**是否需要与示例电子表格中相同的列标题？**</span><span class="sxs-lookup"><span data-stu-id="298e9-146">**Do I need the same column headings as in the sample spreadsheet?**</span></span> <span data-ttu-id="298e9-147">是。</span><span class="sxs-lookup"><span data-stu-id="298e9-147">Yes.</span></span> <span data-ttu-id="298e9-148">示例电子表格包含第一行中的列标题。</span><span class="sxs-lookup"><span data-stu-id="298e9-148">The sample spreadsheet contains column headings in the first row.</span></span> <span data-ttu-id="298e9-149">这些标题是必需的。</span><span class="sxs-lookup"><span data-stu-id="298e9-149">These headings are required.</span></span> <span data-ttu-id="298e9-150">对于要添加到 Microsoft 365 的每个用户，在标题下创建一行。</span><span class="sxs-lookup"><span data-stu-id="298e9-150">For each user you want to add to Microsoft 365, create a row under the heading.</span></span> <span data-ttu-id="298e9-151">如果添加、更改或删除任何列标题，Microsoft 365 可能无法从文件中的信息创建用户。</span><span class="sxs-lookup"><span data-stu-id="298e9-151">If you add, change, or delete any of the column headings, Microsoft 365 might not be able to create users from the information in the file.</span></span> 
    
- <span data-ttu-id="298e9-152">**如果我没有每个用户所需的全部信息，应该如何操作？**</span><span class="sxs-lookup"><span data-stu-id="298e9-152">**What if I don't have all the information required for each user?**</span></span> <span data-ttu-id="298e9-153">用户名和显示名称是必需的，如果没有此信息，则不能添加新用户。</span><span class="sxs-lookup"><span data-stu-id="298e9-153">The user name and display name are required, and you cannot add a new user without this information.</span></span> <span data-ttu-id="298e9-154">如果没有其他一些信息（如传真），可以使用空格加逗号来指示字段应保留为空。</span><span class="sxs-lookup"><span data-stu-id="298e9-154">If you don't have some of the other information, such as the fax, you can use a space plus a comma to indicate that the field should remain blank.</span></span> 
    
- <span data-ttu-id="298e9-155">**电子表格可以小到大？**</span><span class="sxs-lookup"><span data-stu-id="298e9-155">**How small or large can the spreadsheet be?**</span></span> <span data-ttu-id="298e9-156">电子表格必须至少包含两行。</span><span class="sxs-lookup"><span data-stu-id="298e9-156">The spreadsheet must have at least two rows.</span></span> <span data-ttu-id="298e9-157">一个列标题用于 (数据列标签) 列标题，另一个列标题用于用户。</span><span class="sxs-lookup"><span data-stu-id="298e9-157">One is for the column headings (the user data column label) and one for the user.</span></span> <span data-ttu-id="298e9-158">行数不能超过 251。</span><span class="sxs-lookup"><span data-stu-id="298e9-158">You cannot have more than 251 rows.</span></span> <span data-ttu-id="298e9-159">如果需要导入 250 多个用户，可以创建多个电子表格。</span><span class="sxs-lookup"><span data-stu-id="298e9-159">If you need to import more than 250 users, you can create more than one spreadsheet.</span></span> 
    
- <span data-ttu-id="298e9-160">**我可以使用哪些语言？**</span><span class="sxs-lookup"><span data-stu-id="298e9-160">**What languages can I use?**</span></span> <span data-ttu-id="298e9-161">创建电子表格时，可以使用任何语言或字符输入用户数据列标签，但不得更改标签的顺序，如示例中所示。</span><span class="sxs-lookup"><span data-stu-id="298e9-161">When you create your spreadsheet, you can enter user data column labels in any language or characters, but you must not change the order of the labels, as shown in the sample.</span></span> <span data-ttu-id="298e9-162">然后，可以使用任何语言或字符将条目输入字段，以 Unicode 或 UTF-8 格式保存文件。</span><span class="sxs-lookup"><span data-stu-id="298e9-162">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span></span> 
    
- <span data-ttu-id="298e9-163">**如果我添加来自不同国家/地区的用户，该做什么？**</span><span class="sxs-lookup"><span data-stu-id="298e9-163">**What if I'm adding users from different countries or regions?**</span></span> <span data-ttu-id="298e9-164">为每个区域创建单独的电子表格。</span><span class="sxs-lookup"><span data-stu-id="298e9-164">Create a separate spreadsheet for each area.</span></span> <span data-ttu-id="298e9-165">你需要逐步完成批量添加用户向导，其中每个电子表格都提供一个包含于你正在处理的文件的所有用户的位置。</span><span class="sxs-lookup"><span data-stu-id="298e9-165">You'll need to step through the Bulk add users wizard which each spreadsheet, giving a single location of all users included in the file that you're working with.</span></span> 
    
- <span data-ttu-id="298e9-166">**我可以使用的字符数是否有限制？**</span><span class="sxs-lookup"><span data-stu-id="298e9-166">**Is there a limit to the number of characters I can use?**</span></span> <span data-ttu-id="298e9-167">下表显示了示例电子表格中的用户数据列标签和每个标签的最大字符长度。</span><span class="sxs-lookup"><span data-stu-id="298e9-167">The following table shows the user data column labels and the maximum character length for each in the sample spreadsheet.</span></span> 
    
|<span data-ttu-id="298e9-168">**用户数据列标签**</span><span class="sxs-lookup"><span data-stu-id="298e9-168">**User data column label**</span></span>|<span data-ttu-id="298e9-169">**最大字符长度**</span><span class="sxs-lookup"><span data-stu-id="298e9-169">**Maximum character length**</span></span>|
|:-----|:-----|
|<span data-ttu-id="298e9-170">用户名 (必需) </span><span class="sxs-lookup"><span data-stu-id="298e9-170">User Name (Required)</span></span>  <br/> |<span data-ttu-id="298e9-171">79，包括 at 符号 (@) ，格式为 \<extension\> name@domain。</span><span class="sxs-lookup"><span data-stu-id="298e9-171">79 including the at sign (@), in the format name@domain.\<extension\>.</span></span> <span data-ttu-id="298e9-172">用户的别名不能超过 50 个字符，并且域名不能超过 48 个字符。</span><span class="sxs-lookup"><span data-stu-id="298e9-172">The user's alias cannot exceed 50 characters, and the domain name cannot exceed 48 characters.</span></span>  <br/> |
|<span data-ttu-id="298e9-173">名字</span><span class="sxs-lookup"><span data-stu-id="298e9-173">First Name</span></span>  <br/> |<span data-ttu-id="298e9-174">64</span><span class="sxs-lookup"><span data-stu-id="298e9-174">64</span></span>  <br/> |
|<span data-ttu-id="298e9-175">姓氏</span><span class="sxs-lookup"><span data-stu-id="298e9-175">Last Name</span></span>  <br/> |<span data-ttu-id="298e9-176">64</span><span class="sxs-lookup"><span data-stu-id="298e9-176">64</span></span>  <br/> |
|<span data-ttu-id="298e9-177">显示名称 (是必需的) </span><span class="sxs-lookup"><span data-stu-id="298e9-177">Display Name (required)</span></span>  <br/> |<span data-ttu-id="298e9-178">256</span><span class="sxs-lookup"><span data-stu-id="298e9-178">256</span></span>  <br/> |
|<span data-ttu-id="298e9-179">职务</span><span class="sxs-lookup"><span data-stu-id="298e9-179">Job Title</span></span>  <br/> |<span data-ttu-id="298e9-180">64</span><span class="sxs-lookup"><span data-stu-id="298e9-180">64</span></span>  <br/> |
|<span data-ttu-id="298e9-181">Department</span><span class="sxs-lookup"><span data-stu-id="298e9-181">Department</span></span>  <br/> |<span data-ttu-id="298e9-182">64</span><span class="sxs-lookup"><span data-stu-id="298e9-182">64</span></span>  <br/> |
|<span data-ttu-id="298e9-183">Office 号码</span><span class="sxs-lookup"><span data-stu-id="298e9-183">Office Number</span></span>  <br/> |<span data-ttu-id="298e9-184">128</span><span class="sxs-lookup"><span data-stu-id="298e9-184">128</span></span>  <br/> |
|<span data-ttu-id="298e9-185">办公室电话</span><span class="sxs-lookup"><span data-stu-id="298e9-185">Office Phone</span></span>  <br/> |<span data-ttu-id="298e9-186">64</span><span class="sxs-lookup"><span data-stu-id="298e9-186">64</span></span>  <br/> |
|<span data-ttu-id="298e9-187">Mobile Phone － 移动电话</span><span class="sxs-lookup"><span data-stu-id="298e9-187">Mobile Phone</span></span>  <br/> |<span data-ttu-id="298e9-188">64</span><span class="sxs-lookup"><span data-stu-id="298e9-188">64</span></span>  <br/> |
|<span data-ttu-id="298e9-189">Fax</span><span class="sxs-lookup"><span data-stu-id="298e9-189">Fax</span></span>  <br/> |<span data-ttu-id="298e9-190">64</span><span class="sxs-lookup"><span data-stu-id="298e9-190">64</span></span>  <br/> |
|<span data-ttu-id="298e9-191">地址</span><span class="sxs-lookup"><span data-stu-id="298e9-191">Address</span></span>  <br/> |<span data-ttu-id="298e9-192">1023</span><span class="sxs-lookup"><span data-stu-id="298e9-192">1023</span></span>  <br/> |
|<span data-ttu-id="298e9-193">市/县</span><span class="sxs-lookup"><span data-stu-id="298e9-193">City</span></span>  <br/> |<span data-ttu-id="298e9-194">128</span><span class="sxs-lookup"><span data-stu-id="298e9-194">128</span></span>  <br/> |
|<span data-ttu-id="298e9-195">省/自治区/直辖市</span><span class="sxs-lookup"><span data-stu-id="298e9-195">State or Province</span></span>  <br/> |<span data-ttu-id="298e9-196">128</span><span class="sxs-lookup"><span data-stu-id="298e9-196">128</span></span>  <br/> |
|<span data-ttu-id="298e9-197">邮政编码</span><span class="sxs-lookup"><span data-stu-id="298e9-197">ZIP or Postal Code</span></span>  <br/> |<span data-ttu-id="298e9-198">40</span><span class="sxs-lookup"><span data-stu-id="298e9-198">40</span></span>  <br/> |
|<span data-ttu-id="298e9-199">国家或地区</span><span class="sxs-lookup"><span data-stu-id="298e9-199">Country or Region</span></span>  <br/> |<span data-ttu-id="298e9-200">128</span><span class="sxs-lookup"><span data-stu-id="298e9-200">128</span></span>  <br/> |
   
### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a><span data-ttu-id="298e9-201">向 Microsoft 365 添加用户时仍有问题？</span><span class="sxs-lookup"><span data-stu-id="298e9-201">Still having problems when adding users to Microsoft 365?</span></span>

- <span data-ttu-id="298e9-202">**仔细检查电子表格的格式是否正确。**</span><span class="sxs-lookup"><span data-stu-id="298e9-202">**Double-check that the spreadsheet is formatted correctly.**</span></span> <span data-ttu-id="298e9-203">检查列标题以确保它们与示例文件中的标题匹配。</span><span class="sxs-lookup"><span data-stu-id="298e9-203">Check the column headings to make sure they match the headings in the sample file.</span></span> <span data-ttu-id="298e9-204">确保遵循字符长度规则，并且每个字段用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="298e9-204">Make sure you're following the rules for character lengths and that each field is separated by a comma.</span></span> 
    
- <span data-ttu-id="298e9-205">**如果在 Microsoft 365 中看不到新用户，请等待几分钟。**</span><span class="sxs-lookup"><span data-stu-id="298e9-205">**If you don't see the new users in Microsoft 365 right away, wait a few minutes.**</span></span> <span data-ttu-id="298e9-206">可能需要一点时间更改才能在 Microsoft 365 中跨所有服务。</span><span class="sxs-lookup"><span data-stu-id="298e9-206">It can take a little while for changes to go across all the services in Microsoft 365.</span></span> 
    
## <a name="related-articles"></a><span data-ttu-id="298e9-207">相关文章</span><span class="sxs-lookup"><span data-stu-id="298e9-207">Related articles</span></span>

[<span data-ttu-id="298e9-208">将用户单独或批量添加到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="298e9-208">Add users individually or in bulk to Microsoft 365</span></span>](https://docs.microsoft.com/office365/admin/add-users/add-users)




