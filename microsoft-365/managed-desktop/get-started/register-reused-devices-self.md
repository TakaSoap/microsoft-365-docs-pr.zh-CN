---
title: 自行注册现有设备
description: 注册重新使用的设备你可能已经有了你自己的设备，以便 Microsoft 托管桌面可以管理它们
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: e11b72228dceb5a4999e6b9398efde02a41ca163
ms.sourcegitcommit: 4612c270867c148818eaa4008f45ca793f5d2a2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2019
ms.locfileid: "38074734"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="01e1c-103">自行注册现有设备</span><span class="sxs-lookup"><span data-stu-id="01e1c-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="01e1c-104">本主题介绍了重新使用已拥有的设备的步骤，并将其注册到 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="01e1c-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="01e1c-105">如果您正在使用全新的设备，请按照在[Microsoft 托管桌面中注册新设备](register-devices-self.md)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="01e1c-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="01e1c-106">合作伙伴的过程记录在[合作伙伴注册设备的步骤](register-devices-partner.md)中。</span><span class="sxs-lookup"><span data-stu-id="01e1c-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="01e1c-107">Microsoft 托管桌面可以与全新设备配合使用，也可以重新使用可能已有的设备（这将需要您对其进行重新映像）。</span><span class="sxs-lookup"><span data-stu-id="01e1c-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="01e1c-108">您可以使用 Azure 门户上的 Microsoft 托管桌面注册设备。</span><span class="sxs-lookup"><span data-stu-id="01e1c-108">You can register devices by using Microsoft Managed Desktop on the Azure Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="01e1c-109">准备注册现有设备</span><span class="sxs-lookup"><span data-stu-id="01e1c-109">Prepare to register existing devices</span></span>


<span data-ttu-id="01e1c-110">若要注册现有设备，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="01e1c-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="01e1c-111">获取每个设备的硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="01e1c-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="01e1c-112">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="01e1c-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="01e1c-113">[在 Microsoft 托管桌面中注册设备](#register-devices)。</span><span class="sxs-lookup"><span data-stu-id="01e1c-113">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="01e1c-114">请仔细检查图像是否正确。</span><span class="sxs-lookup"><span data-stu-id="01e1c-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="01e1c-115">传递设备</span><span class="sxs-lookup"><span data-stu-id="01e1c-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="01e1c-116">获取硬件哈希</span><span class="sxs-lookup"><span data-stu-id="01e1c-116">Obtain the hardware hash</span></span>

<span data-ttu-id="01e1c-117">Microsoft 托管桌面通过引用其硬件哈希来唯一标识每个设备。</span><span class="sxs-lookup"><span data-stu-id="01e1c-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="01e1c-118">你可以通过四个选项从已在使用的设备中获取此信息：</span><span class="sxs-lookup"><span data-stu-id="01e1c-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="01e1c-119">向 OEM 提供商咨询 AutoPilot 注册文件，其中将包含硬件哈希值。</span><span class="sxs-lookup"><span data-stu-id="01e1c-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="01e1c-120">在[配置管理器](#configuration-manager)中创建自定义报表。</span><span class="sxs-lookup"><span data-stu-id="01e1c-120">Create a custom report in [Configuration Manager](#configuration-manager).</span></span>
- <span data-ttu-id="01e1c-121">在每台设备上使用[Active Directory](#active-directory-powershell-script-method)或[手动](#manual-powershell-script-method)运行 Windows PowerShell 脚本--并在文件中收集结果。</span><span class="sxs-lookup"><span data-stu-id="01e1c-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="01e1c-122">启动每个设备--但不完成 Windows 安装程序体验，并[收集可移动闪存驱动器上的哈希值](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="01e1c-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="configuration-manager"></a><span data-ttu-id="01e1c-123">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="01e1c-123">Configuration Manager</span></span>

<span data-ttu-id="01e1c-124">您可以使用 System Center Configuration Manager 收集要使用 Microsoft 托管桌面注册的现有设备的硬件哈希值。</span><span class="sxs-lookup"><span data-stu-id="01e1c-124">You can use System Center Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01e1c-125">要获取此信息的任何设备都必须运行 Windows 10 版本1703或更高版本。</span><span class="sxs-lookup"><span data-stu-id="01e1c-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> <span data-ttu-id="01e1c-126">此外，还需要一个作为连接到 System Center Current Branch 网站的 Configuration Manager 客户端的设备。</span><span class="sxs-lookup"><span data-stu-id="01e1c-126">You also need a device that is a Configuration Manager client connected to System Center Current Branch site.</span></span> <span data-ttu-id="01e1c-127">您还需要在启用了 SQL Server Reporting Services 的环境中设置报告点站点系统角色。</span><span class="sxs-lookup"><span data-stu-id="01e1c-127">You also need the Reporting Point Site System role set up in your environment with SQL Server Reporting Services enabled.</span></span> 

<span data-ttu-id="01e1c-128">如果你已满足所有这些先决条件，则可以按照以下步骤收集信息：</span><span class="sxs-lookup"><span data-stu-id="01e1c-128">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="01e1c-129">在 Configuration Manager 控制台中，选择 "**监控**"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-129">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="01e1c-130">在 "监控" 工作区中，展开 "**报告**"，然后选择 "**报告**"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-130">In the Monitoring workspace, expand **Reporting**, and then select **Reports**.</span></span> 
3. <span data-ttu-id="01e1c-131">在 "**开始**" 选项卡上的 "**创建**" 部分，选择 "**创建报告**" 以打开 "创建报告向导"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-131">On the **Home** tab, in the **Create** section, select **Create Report** to open the Create Report wizard.</span></span> 
4. <span data-ttu-id="01e1c-132">在 "**信息**" 页面上，设置以下设置：</span><span class="sxs-lookup"><span data-stu-id="01e1c-132">On the **Information** page, set these settings:</span></span> 
    - <span data-ttu-id="01e1c-133">**名称：** 指定报表的名称。</span><span class="sxs-lookup"><span data-stu-id="01e1c-133">**Name:** Specify a name for the report.</span></span> 
    - <span data-ttu-id="01e1c-134">**说明：** 指定报表的说明。</span><span class="sxs-lookup"><span data-stu-id="01e1c-134">**Description:** Specify a description for the report.</span></span> 
    - <span data-ttu-id="01e1c-135">**服务器：** 显示要在其上创建此报告的报表服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="01e1c-135">**Server:** Displays the name of the report server on which you are creating this report.</span></span> 
    - <span data-ttu-id="01e1c-136">**路径：** 选择 "**浏览**" 以指定要在其中存储报告的文件夹。</span><span class="sxs-lookup"><span data-stu-id="01e1c-136">**Path:** Select **Browse** to specify a folder in which you want to store the report.</span></span> 
5. <span data-ttu-id="01e1c-137">选择“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="01e1c-137">Select **Next**.</span></span> 
6. <span data-ttu-id="01e1c-138">在 "**摘要**" 页上，查看设置。</span><span class="sxs-lookup"><span data-stu-id="01e1c-138">On the **Summary** page, review the settings.</span></span> <span data-ttu-id="01e1c-139">选择 "**上一**步" 更改设置，或选择 "**下一步**" 在配置管理器中创建报表。</span><span class="sxs-lookup"><span data-stu-id="01e1c-139">Select **Previous** to change the settings or select **Next** to create the report in Configuration Manager.</span></span> 
7. <span data-ttu-id="01e1c-140">在 "**完成**" 页上，选择 "**关闭**" 退出向导，并打开 "**报告生成器**" 以输入报告设置。</span><span class="sxs-lookup"><span data-stu-id="01e1c-140">On the **Completion** page, select **Close** to exit the wizard and open **Report Builder** to enter the report settings.</span></span> <span data-ttu-id="01e1c-141">如果出现提示，请输入您的用户帐户和密码，然后选择 **"确定"。**</span><span class="sxs-lookup"><span data-stu-id="01e1c-141">Enter your user account and password if you are prompted, and then select **OK.**</span></span> <span data-ttu-id="01e1c-142">如果设备上未安装报表生成器，则系统会提示您安装它。</span><span class="sxs-lookup"><span data-stu-id="01e1c-142">If Report Builder is not installed on the device, you are prompted to install it.</span></span> <span data-ttu-id="01e1c-143">选择 "**运行" 以安装 "报告生成器**"，这是修改和创建报告所必需的。</span><span class="sxs-lookup"><span data-stu-id="01e1c-143">Select **Run to install Report Builder**, which is required to modify and create reports.</span></span> 


<span data-ttu-id="01e1c-144">**在 Microsoft Report Builder 中**，提供报表的 SQL 语句，并执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="01e1c-144">**In Microsoft Report Builder**, provide the SQL statement for the report and follow these steps:</span></span>

1. <span data-ttu-id="01e1c-145">在左窗格中，选择 "**数据集**"，然后右键单击以**添加数据集**。</span><span class="sxs-lookup"><span data-stu-id="01e1c-145">In the left pane, select **Datasets**, and then right-click to **Add Dataset**.</span></span>
2. <span data-ttu-id="01e1c-146">转到 "**查询**" 选项卡，然后输入名称为*DataSet0*。</span><span class="sxs-lookup"><span data-stu-id="01e1c-146">Go to the **Query** tab, and then enter the name as *DataSet0*.</span></span> 
3. <span data-ttu-id="01e1c-147">选择 **"使用嵌入到我的报表中的数据集"**;将打开 "报告生成器"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-147">Select **Use a dataset embedded in my report**; Report Builder opens.</span></span>
4. <span data-ttu-id="01e1c-148">在**报表生成器**中，选择 "**数据源：**"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-148">In **Report Builder**, select **Data source:**.</span></span> <span data-ttu-id="01e1c-149">选择应以 "AutoGen" 开头的默认数据源。</span><span class="sxs-lookup"><span data-stu-id="01e1c-149">Select the default data source, which should start with "AutoGen".</span></span> 
5. <span data-ttu-id="01e1c-150">选择 "**查询类型" 作为文本**，然后输入以下查询：</span><span class="sxs-lookup"><span data-stu-id="01e1c-150">Choose **Query type as Text**, and then enter this query:</span></span>




```sql
SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp

       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid
```




5. <span data-ttu-id="01e1c-151">导航到 "**字段**" 选项卡，应已填充**字段名称**和**字段源**的 wehre 值。</span><span class="sxs-lookup"><span data-stu-id="01e1c-151">Navigate to the **Field** tab, wehre values for **Field Name** and **Field Source** should already be populated.</span></span> <span data-ttu-id="01e1c-152">如果不是，请选择 "**添加**"，然后选择 "**查询字段**"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-152">If they aren't, then select **Add**, and then select **Query Field**.</span></span> <span data-ttu-id="01e1c-153">输入**字段名称**和**字段源**。</span><span class="sxs-lookup"><span data-stu-id="01e1c-153">Enter the **Field Name** and **Field Source**.</span></span>
6. <span data-ttu-id="01e1c-154">对以下每个值重复上述操作：</span><span class="sxs-lookup"><span data-stu-id="01e1c-154">Repeat for each of these values:</span></span> 
    - <span data-ttu-id="01e1c-155">负责</span><span class="sxs-lookup"><span data-stu-id="01e1c-155">Manufacturer</span></span> 
    - <span data-ttu-id="01e1c-156">模型</span><span class="sxs-lookup"><span data-stu-id="01e1c-156">Model</span></span> 
    - <span data-ttu-id="01e1c-157">Serial_Number</span><span class="sxs-lookup"><span data-stu-id="01e1c-157">Serial_Number</span></span> 
    - <span data-ttu-id="01e1c-158">HardwareHash</span><span class="sxs-lookup"><span data-stu-id="01e1c-158">HardwareHash</span></span>
7. <span data-ttu-id="01e1c-159">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="01e1c-159">Select **OK**.</span></span>

<span data-ttu-id="01e1c-160">接下来，通过执行以下步骤来**定义报告显示和创建报告**：</span><span class="sxs-lookup"><span data-stu-id="01e1c-160">**Next, define the report display and create the report** by following these steps:</span></span>

1. <span data-ttu-id="01e1c-161">选择**表或矩阵**;将打开一个新的向导。</span><span class="sxs-lookup"><span data-stu-id="01e1c-161">Select **Table or Matrix**; a new wizard will open.</span></span>
2. <span data-ttu-id="01e1c-162">在 "**选择数据集**" 中，选择 "**选择此报告中的现有数据集" 或 "共享数据集**"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-162">In **Choose a dataset**, select **Choose an existing dataset in this report or a shared dataset**.</span></span>  
3. <span data-ttu-id="01e1c-163">选择 " **DataSet0** " （默认值），然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-163">Select **DataSet0** (the default), and then select **Next**.</span></span>
4. <span data-ttu-id="01e1c-164">将 "**制造商**"、"**模型**" 和 "**序列号**" 拖到 "**行组**" 框中。</span><span class="sxs-lookup"><span data-stu-id="01e1c-164">Drag **Manufacturer**, **Model**, and **Serial Number** into the **Row Groups** box.</span></span> <span data-ttu-id="01e1c-165">将**HardwareHash**拖到 "**值**" 框中，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-165">Drag **HardwareHash** into the **Values** box and then select **Next**.</span></span>
5. <span data-ttu-id="01e1c-166">清除 "**显示分类汇总和**总计" 和 "**展开/折叠组**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="01e1c-166">Clear the checkboxes for **Show subtotals and grand totals** and **Expand/collapse groups**.</span></span> <span data-ttu-id="01e1c-167">选择“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="01e1c-167">Select **Next**.</span></span>
6. <span data-ttu-id="01e1c-168">选择“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="01e1c-168">Select **Finish**.</span></span>
7. <span data-ttu-id="01e1c-169">选择 "**运行**" 运行报告。</span><span class="sxs-lookup"><span data-stu-id="01e1c-169">Select **Run** to run your report.</span></span> <span data-ttu-id="01e1c-170">验证报告是否提供了您所需的信息。</span><span class="sxs-lookup"><span data-stu-id="01e1c-170">Verify that the report provides the information that you expect.</span></span> <span data-ttu-id="01e1c-171">如有必要，选择 "**设计**" 以返回到 "设计" 视图以修改报告。</span><span class="sxs-lookup"><span data-stu-id="01e1c-171">If necessary, select **Design** to return to the Design view to modify the report.</span></span>
8. <span data-ttu-id="01e1c-172">选择 "**保存**" 将报告保存到报告服务器。</span><span class="sxs-lookup"><span data-stu-id="01e1c-172">Select **Save** to save the report to the report server.</span></span> <span data-ttu-id="01e1c-173">您可以在 "监控" 工作区的 "报告" 节点中运行新报告。</span><span class="sxs-lookup"><span data-stu-id="01e1c-173">You can run the new report in the Reports node in the Monitoring workspace.</span></span> 

<span data-ttu-id="01e1c-174">**最后，按以下步骤导出报告并使用它来注册设备**。</span><span class="sxs-lookup"><span data-stu-id="01e1c-174">**Finally, export the report and use it to register devices** by following these steps.</span></span> <span data-ttu-id="01e1c-175">（如果您在前面的步骤中导航掉了，则只需遵循本节中的步骤1和步骤2。）：</span><span class="sxs-lookup"><span data-stu-id="01e1c-175">(You should only need to follow Steps 1 and 2 of this section if you have navigated away after the previous steps.):</span></span>

1. <span data-ttu-id="01e1c-176">在 Configuration Manager 控制台中，选择 "**监控**"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-176">In the Configuration Manager console, select **Monitoring**.</span></span>
2. <span data-ttu-id="01e1c-177">在 "**监视**" 中，展开 "**报告**"，然后选择 "**报告**"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-177">In **Monitoring**, expand **Reporting**, and then select **Reports**.</span></span>
3. <span data-ttu-id="01e1c-178">使用之前创建的名称查找报告。</span><span class="sxs-lookup"><span data-stu-id="01e1c-178">Find the report using the name you created earlier.</span></span>
4. <span data-ttu-id="01e1c-179">右键单击此报告，然后选择 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-179">Right-click this report, and select **Run**.</span></span>
5. <span data-ttu-id="01e1c-180">在打开的对话框中，选择 "**导出**"，然后选择 "**另存为 CSV**"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-180">In the dialog that opens, select **Export** and then select **Save as CSV**.</span></span>
6. <span data-ttu-id="01e1c-181">此版本的报告将从配置管理器与之通信的所有 Windows 10 设备中提取哈希。</span><span class="sxs-lookup"><span data-stu-id="01e1c-181">This version of report extracts hashes from all Windows 10 devices that Configuration Manager communicates with.</span></span> <span data-ttu-id="01e1c-182">你将需要筛选结果，使其仅包含计划注册到 Microsoft 托管桌面的那些设备。</span><span class="sxs-lookup"><span data-stu-id="01e1c-182">You will need to filter results to just those devices you plan to register with Microsoft Managed Desktop.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="01e1c-183">Configuration Manager 中的查询不允许导出的列名称中包含空格;这就是为什么这些步骤输入 "Serial_Number" 和 "HardwareHash" 的原因所在。</span><span class="sxs-lookup"><span data-stu-id="01e1c-183">The query in Configuration Manager doesn’t allow spaces in exported column names; that's why the steps had you enter "Serial_Number" and "HardwareHash."</span></span> <span data-ttu-id="01e1c-184">现在，您已导出了 CSV 文件，您必须编辑报告标头，以便阅读此处所示的*序列号*和*硬件哈希*，然后再继续执行设备注册。</span><span class="sxs-lookup"><span data-stu-id="01e1c-184">Now that you have the exported CSV file, you must edit the report headers to read *Serial Number* and *Hardware Hash* as shown here before you proceed with device registration.</span></span>

<span data-ttu-id="01e1c-185">现在，你可以继续[使用 Azure 门户注册设备](#register-devices-by-using-the-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="01e1c-185">Now you can proceed to [Register devices by using the Azure Portal](#register-devices-by-using-the-azure-portal).</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="01e1c-186">Active Directory PowerShell 脚本方法</span><span class="sxs-lookup"><span data-stu-id="01e1c-186">Active Directory PowerShell script method</span></span>

<span data-ttu-id="01e1c-187">在 Active Directory 环境中，您可以使用`Get-MMDRegistrationInfo` PowerShell Cmdlet 从 Active directory 组中的设备远程收集信息，方法是使用 WinRM。</span><span class="sxs-lookup"><span data-stu-id="01e1c-187">In an Active Directory environment, you can use the `Get-MMDRegistrationInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="01e1c-188">您还可以使用`Get-AD Computer` cmdlet 并获取目录中包含的特定硬件模型名称的筛选结果。</span><span class="sxs-lookup"><span data-stu-id="01e1c-188">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="01e1c-189">为此，请首先确认这些先决条件，然后继续执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="01e1c-189">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="01e1c-190">启用 WinRM。</span><span class="sxs-lookup"><span data-stu-id="01e1c-190">WinRM is enabled.</span></span>
- <span data-ttu-id="01e1c-191">要注册的设备在网络上是活动的（即，它们未断开连接或已关闭）。</span><span class="sxs-lookup"><span data-stu-id="01e1c-191">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="01e1c-192">请确保您有一个具有在设备上远程执行的权限的域凭据参数。</span><span class="sxs-lookup"><span data-stu-id="01e1c-192">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="01e1c-193">请确保 Windows 防火墙允许访问 WMI。</span><span class="sxs-lookup"><span data-stu-id="01e1c-193">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="01e1c-194">为此，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="01e1c-194">To do that, follow these steps:</span></span>
    1. <span data-ttu-id="01e1c-195">打开**Windows Defender 防火墙**控制面板，然后选择 "**允许通过 Windows defender 防火墙的应用程序或功能**"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-195">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    2. <span data-ttu-id="01e1c-196">在列表中查找**Windows Management Instrumentation （WMI）** ，启用 "**专用" 和 "公用**"，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="01e1c-196">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="01e1c-197">打开具有管理权限的 PowerShell 提示。</span><span class="sxs-lookup"><span data-stu-id="01e1c-197">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="01e1c-198">运行以下*任意一个*脚本：</span><span class="sxs-lookup"><span data-stu-id="01e1c-198">Run *either one* of these scripts:</span></span>
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. <span data-ttu-id="01e1c-199">访问可能包含设备条目的任何目录。</span><span class="sxs-lookup"><span data-stu-id="01e1c-199">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="01e1c-200">从*所有*目录中删除每个设备的条目，包括 Windows Server Active Directory 域服务和 Azure Active directory。</span><span class="sxs-lookup"><span data-stu-id="01e1c-200">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="01e1c-201">请注意，此删除操作可能需要几个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="01e1c-201">Be aware that this removal could take a few hours to completely process.</span></span>
4. <span data-ttu-id="01e1c-202">可能包含设备条目的 Access management services。</span><span class="sxs-lookup"><span data-stu-id="01e1c-202">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="01e1c-203">从*所有*管理服务中删除每个设备的条目，包括 System Center Configuration 管理器、Microsoft Intune 和 Windows Autopilot。</span><span class="sxs-lookup"><span data-stu-id="01e1c-203">Remove entries for each device from *all* management services, including System Center Configuration Manger, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="01e1c-204">请注意，此删除操作可能需要几个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="01e1c-204">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="01e1c-205">现在，你可以继续[注册设备](#register-devices)。</span><span class="sxs-lookup"><span data-stu-id="01e1c-205">Now you can proceed to [register devices](#register-devices).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="01e1c-206">手动 PowerShell 脚本方法</span><span class="sxs-lookup"><span data-stu-id="01e1c-206">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="01e1c-207">打开具有管理权限的 PowerShell 提示。</span><span class="sxs-lookup"><span data-stu-id="01e1c-207">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="01e1c-208">以`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="01e1c-208">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="01e1c-209">以`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="01e1c-209">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="01e1c-210">合并哈希数据。</span><span class="sxs-lookup"><span data-stu-id="01e1c-210">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="01e1c-211">闪存驱动器方法</span><span class="sxs-lookup"><span data-stu-id="01e1c-211">Flash drive method</span></span>

1. <span data-ttu-id="01e1c-212">在要注册的设备以外的其他设备上，插入 u 盘。</span><span class="sxs-lookup"><span data-stu-id="01e1c-212">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="01e1c-213">打开具有管理权限的 PowerShell 提示。</span><span class="sxs-lookup"><span data-stu-id="01e1c-213">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="01e1c-214">以`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="01e1c-214">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="01e1c-215">打开要注册的设备，但*不要启动安装程序体验*。</span><span class="sxs-lookup"><span data-stu-id="01e1c-215">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="01e1c-216">如果您意外启动了设置体验，则必须重置或重新映像设备。</span><span class="sxs-lookup"><span data-stu-id="01e1c-216">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="01e1c-217">插入 u 盘，然后按 SHIFT + F10。</span><span class="sxs-lookup"><span data-stu-id="01e1c-217">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="01e1c-218">打开具有管理权限的 PowerShell 提示符，然后运行`cd <pathToUsb>`。</span><span class="sxs-lookup"><span data-stu-id="01e1c-218">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="01e1c-219">以`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="01e1c-219">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="01e1c-220">以`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="01e1c-220">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="01e1c-221">删除 USB 驱动器，然后通过运行来关闭设备`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="01e1c-221">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="01e1c-222">合并哈希数据。</span><span class="sxs-lookup"><span data-stu-id="01e1c-222">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="01e1c-223">在完成注册后，请不要再打开要注册的设备。</span><span class="sxs-lookup"><span data-stu-id="01e1c-223">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="01e1c-224">合并哈希数据</span><span class="sxs-lookup"><span data-stu-id="01e1c-224">Merge hash data</span></span>

<span data-ttu-id="01e1c-225">如果您通过手动 PowerShell 或闪存驱动器方法收集了硬件哈希数据，则您现在需要将 CSV 文件中的数据组合到单个文件中才能完成注册。</span><span class="sxs-lookup"><span data-stu-id="01e1c-225">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="01e1c-226">下面是一个示例 PowerShell 脚本，可轻松实现此操作：</span><span class="sxs-lookup"><span data-stu-id="01e1c-226">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

<span data-ttu-id="01e1c-227">将哈希数据合并到一个 CSV 文件中，现在就可以继续[注册设备了](#register-devices)。</span><span class="sxs-lookup"><span data-stu-id="01e1c-227">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices).</span></span>

### <a name="register-devices"></a><span data-ttu-id="01e1c-228">注册设备</span><span class="sxs-lookup"><span data-stu-id="01e1c-228">Register devices</span></span>

<span data-ttu-id="01e1c-229">CSV 文件必须为注册的特定格式。</span><span class="sxs-lookup"><span data-stu-id="01e1c-229">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="01e1c-230">如果您在前面的步骤中收集数据，则该文件应具有正确的格式;如果从供应商获取文件，则可能需要调整格式。</span><span class="sxs-lookup"><span data-stu-id="01e1c-230">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="01e1c-231">为方便起见，可以下载此 CSV 文件的[模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="01e1c-231">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="01e1c-232">您的文件需要包含与示例1（制造商、模型等）**完全相同的列标题**，但您自己的数据用于其他行。</span><span class="sxs-lookup"><span data-stu-id="01e1c-232">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="01e1c-233">如果使用模板，请在文本编辑工具（如记事本）中打开它，并考虑仅保留第1行中的所有数据，仅在第2行和更低的行中输入数据。</span><span class="sxs-lookup"><span data-stu-id="01e1c-233">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="01e1c-234">如果您忘记更改任何示例数据，则注册将失败。</span><span class="sxs-lookup"><span data-stu-id="01e1c-234">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="01e1c-235">使用 Azure 门户注册设备</span><span class="sxs-lookup"><span data-stu-id="01e1c-235">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="01e1c-236">在 Microsoft 托管桌面[Azure 门户](https://aka.ms/mmdportal)中，在左侧导航窗格中选择 "**设备**"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-236">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="01e1c-237">选择 **+ 注册设备**;将打开 "飞入"：</span><span class="sxs-lookup"><span data-stu-id="01e1c-237">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="01e1c-238">[![选择注册设备后飞入](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="01e1c-238">[![Fly-in after selecting Register devices](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (遗憾的是这不成立。我们可以删除此注释-但现在将其保留，直到我们有机会聊天它。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="01e1c-240">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="01e1c-240">Follow these steps:</span></span>

1. <span data-ttu-id="01e1c-241">在 "**文件上载**" 中，提供以前创建的 CSV 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="01e1c-241">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="01e1c-242">（可选）可以出于自己的跟踪目的添加**订单 id**或**购买 ID** 。</span><span class="sxs-lookup"><span data-stu-id="01e1c-242">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="01e1c-243">这些值没有格式要求。</span><span class="sxs-lookup"><span data-stu-id="01e1c-243">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="01e1c-244">选择 "**注册设备**"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-244">Select **Register devices**.</span></span> <span data-ttu-id="01e1c-245">系统会将设备添加到**设备边栏**上的设备列表中，并标记为 "**注册挂起**"。</span><span class="sxs-lookup"><span data-stu-id="01e1c-245">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="01e1c-246">注册通常需要不到10分钟的时间，如果成功，设备将显示为 "已**准备就绪**，以供用户使用"，表示它已准备就绪，正在等待最终用户开始使用。</span><span class="sxs-lookup"><span data-stu-id="01e1c-246">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="01e1c-247">你可以在主**Microsoft 托管台式机-设备**页面上监视设备注册的进度。</span><span class="sxs-lookup"><span data-stu-id="01e1c-247">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="01e1c-248">可能报告的状态包括：</span><span class="sxs-lookup"><span data-stu-id="01e1c-248">Possible states reported there include:</span></span>

| <span data-ttu-id="01e1c-249">状态</span><span class="sxs-lookup"><span data-stu-id="01e1c-249">State</span></span> | <span data-ttu-id="01e1c-250">描述</span><span class="sxs-lookup"><span data-stu-id="01e1c-250">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="01e1c-251">注册挂起</span><span class="sxs-lookup"><span data-stu-id="01e1c-251">Registration pending</span></span> | <span data-ttu-id="01e1c-252">注册尚未完成。</span><span class="sxs-lookup"><span data-stu-id="01e1c-252">Registration is not done yet.</span></span> <span data-ttu-id="01e1c-253">稍后再次查看。</span><span class="sxs-lookup"><span data-stu-id="01e1c-253">Check back later.</span></span> |
| <span data-ttu-id="01e1c-254">注册失败</span><span class="sxs-lookup"><span data-stu-id="01e1c-254">Registration failed</span></span> | <span data-ttu-id="01e1c-255">无法完成注册。</span><span class="sxs-lookup"><span data-stu-id="01e1c-255">Registration could not be completed.</span></span> <span data-ttu-id="01e1c-256">有关详细信息，请参阅[设备注册故障排除](#troubleshooting-device-registration)。</span><span class="sxs-lookup"><span data-stu-id="01e1c-256">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="01e1c-257">为用户准备就绪</span><span class="sxs-lookup"><span data-stu-id="01e1c-257">Ready for user</span></span> | <span data-ttu-id="01e1c-258">注册成功，现在设备已准备好传递给最终用户。</span><span class="sxs-lookup"><span data-stu-id="01e1c-258">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="01e1c-259">Microsoft 托管桌面将在首次设置时引导他们，因此无需执行任何进一步的准备。</span><span class="sxs-lookup"><span data-stu-id="01e1c-259">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="01e1c-260">活动</span><span class="sxs-lookup"><span data-stu-id="01e1c-260">Active</span></span> | <span data-ttu-id="01e1c-261">设备已传递给最终用户，并且已向其注册了你的租户。</span><span class="sxs-lookup"><span data-stu-id="01e1c-261">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="01e1c-262">这也表明它们是定期使用设备的。</span><span class="sxs-lookup"><span data-stu-id="01e1c-262">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="01e1c-263">不再</span><span class="sxs-lookup"><span data-stu-id="01e1c-263">Inactive</span></span> | <span data-ttu-id="01e1c-264">设备已传递给最终用户，并且已向其注册了你的租户。</span><span class="sxs-lookup"><span data-stu-id="01e1c-264">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="01e1c-265">但是，他们最近未使用设备（最近7天）。</span><span class="sxs-lookup"><span data-stu-id="01e1c-265">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="01e1c-266">设备注册故障排除</span><span class="sxs-lookup"><span data-stu-id="01e1c-266">Troubleshooting device registration</span></span>

| <span data-ttu-id="01e1c-267">错误消息</span><span class="sxs-lookup"><span data-stu-id="01e1c-267">Error message</span></span> | <span data-ttu-id="01e1c-268">详细信息</span><span class="sxs-lookup"><span data-stu-id="01e1c-268">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="01e1c-269">找不到设备</span><span class="sxs-lookup"><span data-stu-id="01e1c-269">Device not found</span></span> | <span data-ttu-id="01e1c-270">无法注册此设备，因为我们找不到提供的制造商、型号或序列号的匹配项。</span><span class="sxs-lookup"><span data-stu-id="01e1c-270">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="01e1c-271">请与设备供应商确认这些值。</span><span class="sxs-lookup"><span data-stu-id="01e1c-271">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="01e1c-272">硬件哈希无效</span><span class="sxs-lookup"><span data-stu-id="01e1c-272">Hardware hash not valid</span></span> | <span data-ttu-id="01e1c-273">为此设备提供的硬件哈希格式不正确。</span><span class="sxs-lookup"><span data-stu-id="01e1c-273">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="01e1c-274">仔细检查硬件哈希，然后重新提交。</span><span class="sxs-lookup"><span data-stu-id="01e1c-274">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="01e1c-275">已注册设备</span><span class="sxs-lookup"><span data-stu-id="01e1c-275">Device already registered</span></span> | <span data-ttu-id="01e1c-276">此设备已注册到你的组织。</span><span class="sxs-lookup"><span data-stu-id="01e1c-276">This device is already registered to your organization.</span></span> <span data-ttu-id="01e1c-277">无需执行进一步操作。</span><span class="sxs-lookup"><span data-stu-id="01e1c-277">No further action required.</span></span> |
| <span data-ttu-id="01e1c-278">其他组织声明的设备</span><span class="sxs-lookup"><span data-stu-id="01e1c-278">Device claimed by another organization</span></span> | <span data-ttu-id="01e1c-279">此设备已由其他组织声明。</span><span class="sxs-lookup"><span data-stu-id="01e1c-279">This device has already been claimed by another organization.</span></span> <span data-ttu-id="01e1c-280">请与设备供应商联系。</span><span class="sxs-lookup"><span data-stu-id="01e1c-280">Check with your device supplier.</span></span> |
| <span data-ttu-id="01e1c-281">意外错误</span><span class="sxs-lookup"><span data-stu-id="01e1c-281">Unexpected error</span></span> | <span data-ttu-id="01e1c-282">无法自动处理你的请求。</span><span class="sxs-lookup"><span data-stu-id="01e1c-282">Your request could not be automatically processed.</span></span> <span data-ttu-id="01e1c-283">联系支持人员并提供请求 ID：<requestId></span><span class="sxs-lookup"><span data-stu-id="01e1c-283">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="01e1c-284">检查图像</span><span class="sxs-lookup"><span data-stu-id="01e1c-284">Check the image</span></span>

<span data-ttu-id="01e1c-285">如果你的设备来自 Microsoft 托管桌面合作伙伴提供商，则该映像应正确。</span><span class="sxs-lookup"><span data-stu-id="01e1c-285">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="01e1c-286">如果你愿意，也可以在自己自己应用图像。</span><span class="sxs-lookup"><span data-stu-id="01e1c-286">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="01e1c-287">若要开始，请联系你正在使用的 Microsoft 代表，他们将为你提供应用此图像的位置和步骤。</span><span class="sxs-lookup"><span data-stu-id="01e1c-287">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="01e1c-288">传递设备</span><span class="sxs-lookup"><span data-stu-id="01e1c-288">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01e1c-289">在将设备交给用户之前，请确保已为该用户获取并应用了[相应的许可证](../get-ready/prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="01e1c-289">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="01e1c-290">如果应用了所有许可证，则可以[让用户准备好使用设备](get-started-devices.md)，然后你的用户可以启动设备并继续执行 Windows 安装体验。</span><span class="sxs-lookup"><span data-stu-id="01e1c-290">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









