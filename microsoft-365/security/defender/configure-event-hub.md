---
title: 配置事件中心
description: 了解如何配置事件中心
keywords: 事件中心， 配置， 见解
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.openlocfilehash: d28ad22721e22dfd0dc5962bd46bab2b45469781
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985529"
---
# <a name="configure-your-event-hub"></a><span data-ttu-id="04f6d-104">配置事件中心</span><span class="sxs-lookup"><span data-stu-id="04f6d-104">Configure your Event Hub</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="04f6d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="04f6d-105">**Applies to:**</span></span>
- [<span data-ttu-id="04f6d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04f6d-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="04f6d-107">了解如何配置事件中心，以便它可以从事件中心Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="04f6d-107">Learn how to configure your Event Hub so that it can ingest events from Microsoft 365 Defender.</span></span>


## <a name="setup-the-required-resource-provider-in-the-event-hub-subscription"></a><span data-ttu-id="04f6d-108">在事件中心订阅中设置必需的资源提供程序</span><span class="sxs-lookup"><span data-stu-id="04f6d-108">Setup the required Resource Provider in the Event Hub subscription</span></span>


1. <span data-ttu-id="04f6d-109">登录 [Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="04f6d-109">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
1. <span data-ttu-id="04f6d-110">选择 **订阅 \> {***选择事件中心将部署到***} \> 资源提供程序的订阅**。</span><span class="sxs-lookup"><span data-stu-id="04f6d-110">Select **Subscriptions \> {***Select the subscription the event hub will be deployed to***} \> Resource providers**.</span></span>
1. <span data-ttu-id="04f6d-111">验证 **Microsoft.Insights** 提供程序是否注册。</span><span class="sxs-lookup"><span data-stu-id="04f6d-111">Verify that the **Microsoft.Insights** Provider is registered.</span></span> <span data-ttu-id="04f6d-112">否则，请注册它。</span><span class="sxs-lookup"><span data-stu-id="04f6d-112">Otherwise, register it.</span></span>

![资源提供程序的图像Microsoft Azure](../../media/f893db7a7b1f7aa520e8b9257cc72562.png)

## <a name="setup-azure-active-directory-app-registration"></a><span data-ttu-id="04f6d-114">设置Azure Active Directory应用注册</span><span class="sxs-lookup"><span data-stu-id="04f6d-114">Setup Azure Active Directory App Registration</span></span>


><span data-ttu-id="04f6d-115">![注意]你必须具有管理员角色Azure Active Directory (AAD) 必须设置为允许非管理员注册应用。</span><span class="sxs-lookup"><span data-stu-id="04f6d-115">![NOTE] You must have Administrator role or Azure Active Directory (AAD) must be set to allow non-Administrators to register apps.</span></span> <span data-ttu-id="04f6d-116">还必须具有所有者或用户访问管理员角色才能为服务主体分配角色。</span><span class="sxs-lookup"><span data-stu-id="04f6d-116">You must also have an Owner or User Access Administrator role to assign the service principal a role.</span></span>  
><span data-ttu-id="04f6d-117">有关详细信息，请参阅 Microsoft Docs 门户中的创建[Azure AD &服务主体Microsoft 标识平台 \| Azure AD 应用](/azure/active-directory/develop/howto-create-service-principal-portal)。</span><span class="sxs-lookup"><span data-stu-id="04f6d-117">For more information, see [Create an Azure AD app & service principal in the portal - Microsoft identity platform \| Microsoft Docs](/azure/active-directory/develop/howto-create-service-principal-portal).</span></span>

1. <span data-ttu-id="04f6d-118">创建新的注册 (在应用注册新注册) 服务Azure Active Directory **\> 创建服务 \> 主体。**</span><span class="sxs-lookup"><span data-stu-id="04f6d-118">Create a new registration (which inherently creates a service principal) in **Azure Active Directory \> App registrations \> New registration.**</span></span>

1. <span data-ttu-id="04f6d-119">只需使用"名称" (填写表单，无需重定向 URI) 。</span><span class="sxs-lookup"><span data-stu-id="04f6d-119">Fill out the form with just the Name (no Redirect URI is required).</span></span>

    ![注册应用程序的图像](../../media/336bc84e6be23900c43232b4ef0c253c.png)

    ![概述信息的图像](../../media/06ac04c4ff713c2065cec2ef2f99a294.png)

1. <span data-ttu-id="04f6d-122">通过单击"证书""密码"**创建&密码 \> 新建客户端密码：**</span><span class="sxs-lookup"><span data-stu-id="04f6d-122">Create a secret by clicking on **Certificates & secrets \> New client secret**:</span></span>

    ![证书和密码的图像](../../media/d2ef88d3d2310d2c60c294b569cdf02e.png)

>[!WARNING]
><span data-ttu-id="04f6d-124">**你将无法再次访问客户端密码，因此请确保保存它**。</span><span class="sxs-lookup"><span data-stu-id="04f6d-124">**You won't be able to access the client secret again so make sure to save it**.</span></span>

## <a name="setup-event-hub-namespace"></a><span data-ttu-id="04f6d-125">设置事件中心命名空间</span><span class="sxs-lookup"><span data-stu-id="04f6d-125">Setup Event Hub namespace</span></span>


1. <span data-ttu-id="04f6d-126">创建事件中心命名空间：</span><span class="sxs-lookup"><span data-stu-id="04f6d-126">Create an Event Hub Namespace:</span></span>

    <span data-ttu-id="04f6d-127">转到 **事件 \>** 中心 添加并选择定价层、吞吐量单位和自动 (要求标准定价，且在功能下) 适合您预期负载的功能下。</span><span class="sxs-lookup"><span data-stu-id="04f6d-127">Go **to Event Hubs \> Add** and select the pricing tier, throughput units and Auto-Inflate (requires standard pricing and under features) appropriate for the load you are expecting.</span></span>  
    <span data-ttu-id="04f6d-128">有关详细信息，请参阅定价[- 事件 \| 中心Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="04f6d-128">For more information, see [Pricing - Event Hubs \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span></span>

    >[!NOTE]
    > <span data-ttu-id="04f6d-129">可以使用现有的事件中心，但吞吐量和缩放是在命名空间级别设置的，因此建议将事件中心放在其现有命名空间中。</span><span class="sxs-lookup"><span data-stu-id="04f6d-129">You can use an existing event hub, but the throughput and scaling are set at the namespace level so it is recommended to place an event hub in itsown namespace.</span></span>

   ![事件中心名称空间的图像](../../media/ebc4ca37c342ad1da75c4aee4018e51a.png)

1. <span data-ttu-id="04f6d-131">你还需要此事件中心命名空间的资源 ID。</span><span class="sxs-lookup"><span data-stu-id="04f6d-131">You will also need the Resource ID of this Event Hub Namespace.</span></span> <span data-ttu-id="04f6d-132">转到 Azure 事件中心命名空间页面 \> "属性"。</span><span class="sxs-lookup"><span data-stu-id="04f6d-132">Go to your Azure Event Hubs namespace page \> Properties.</span></span> <span data-ttu-id="04f6d-133">复制"资源 ID"下的文本，并记录它在下面的"M365 配置"部分使用。</span><span class="sxs-lookup"><span data-stu-id="04f6d-133">Copy the text under Resource ID and record it for use during the M365 Configuration section below.</span></span> 

    ![属性的图像](../../media/759498162a4e93cbf17c4130d704d164.png)

1. <span data-ttu-id="04f6d-135">创建事件中心命名空间后，你需要将应用注册服务主体添加为读者、Azure 事件中心数据接收器以及将登录到 Microsoft 365 Defender 的用户作为参与者 (这也可在资源组或订阅级别) 完成。</span><span class="sxs-lookup"><span data-stu-id="04f6d-135">Once the Event Hub Namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hubs Data Receiver, and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span>

    <span data-ttu-id="04f6d-136">此操作在 **IAM 事件中心命名空间 \> 访问控制 (添加) \> 角色** 分配下 **进行验证**：</span><span class="sxs-lookup"><span data-stu-id="04f6d-136">This is done in **Event Hubs Namespace \> Access Control (IAM) \> Add** and verify under **Role assignments**:</span></span>

    ![访问控制的图像](../../media/9c9c29137b90d5858920202d87680d16.png)

## <a name="setup-event-hub"></a><span data-ttu-id="04f6d-138">设置事件中心</span><span class="sxs-lookup"><span data-stu-id="04f6d-138">Setup Event Hub</span></span>


<span data-ttu-id="04f6d-139">**选项 1：**</span><span class="sxs-lookup"><span data-stu-id="04f6d-139">**Option 1:**</span></span>

<span data-ttu-id="04f6d-140">可以在命名空间内创建事件中心，选择要导出的所有 (表) 事件类型将写入此 **事件** 中心。</span><span class="sxs-lookup"><span data-stu-id="04f6d-140">You can create an Event Hub within your Namespace and **all** the Event Types (Tables) you select to export will be written into this **one** Event Hub.</span></span>

<span data-ttu-id="04f6d-141">**选项 2：**</span><span class="sxs-lookup"><span data-stu-id="04f6d-141">**Option 2:**</span></span>

<span data-ttu-id="04f6d-142">无需将所有事件类型 (Tables) 导出到一个事件中心，你可以将每个表导出到事件中心命名空间内的不同事件中心 (每个事件类型一个事件中心) 。</span><span class="sxs-lookup"><span data-stu-id="04f6d-142">Instead of exporting all the Event Types (Tables) into one Event Hub, you can export each table into a different Event Hub inside your Event Hub Namespace (one Event Hub per Event Type).</span></span>  

<span data-ttu-id="04f6d-143">在此选项中，Microsoft 365 Defender将创建事件中心。</span><span class="sxs-lookup"><span data-stu-id="04f6d-143">In this option, Microsoft 365 Defender will create Event Hubs for you.</span></span>  
>[!NOTE]
> <span data-ttu-id="04f6d-144">如果你使用的事件中心命名空间不是事件中心群集的一部分，你最多只能选择在定义的每个导出 设置 中导出最多 10 个事件类型 (表) ，因为每个事件中心命名空间的 Azure 限制是 10 个事件中心。</span><span class="sxs-lookup"><span data-stu-id="04f6d-144">If you are using an Event Hub Namespace that is **not** part of an Event Hub Cluster, you will only be able to choose up to 10 Event Types (Tables) to export in each Export Settings you define, due to an Azure limitation of 10 Event Hubs per Event Hub Namespace.</span></span>

<span data-ttu-id="04f6d-145">例如：</span><span class="sxs-lookup"><span data-stu-id="04f6d-145">For example:</span></span>

![示例事件中心的图像](../../media/005c1f6c10c34420d387f594987f9ffe.png)

<span data-ttu-id="04f6d-147">如果选择此选项，可以跳到"配置Microsoft 365 Defender[发送电子邮件表"](#configure-microsoft-365-defender-to-send-email-tables)部分。</span><span class="sxs-lookup"><span data-stu-id="04f6d-147">If you choose this option, you can skip to the [Configure Microsoft 365 Defender to send email tables](#configure-microsoft-365-defender-to-send-email-tables) section.</span></span>

<span data-ttu-id="04f6d-148">通过选择事件中心 + 事件中心 在命名空间 **\> 内创建事件中心**。</span><span class="sxs-lookup"><span data-stu-id="04f6d-148">Create an Event Hub within your Namespace by selecting **Event Hubs \> + Event Hub**.</span></span>

<span data-ttu-id="04f6d-149">分区计数允许通过并行处理实现额外的吞吐量，因此建议根据你期望的负载增加此数字。</span><span class="sxs-lookup"><span data-stu-id="04f6d-149">The Partition Count allows for additional throughput via parallelism, so it is recommended to increase this number based on the load you are expecting.</span></span>  
<span data-ttu-id="04f6d-150">建议使用默认邮件保留值和捕获值 1 和 Off。</span><span class="sxs-lookup"><span data-stu-id="04f6d-150">Default Message Retention and Capture values of 1 and Off are recommended.</span></span>

![创建事件中心的图像](../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png)

<span data-ttu-id="04f6d-152">对于此事件中心 (命名空间) 您需要使用发送、侦听声明配置共享访问策略。</span><span class="sxs-lookup"><span data-stu-id="04f6d-152">For this Event Hub (not namespace) you will need to configure a Shared Access Policy with Send, Listen Claims.</span></span> <span data-ttu-id="04f6d-153">单击事件中心 **共享访问 \> 策略 \> +** 添加，然后为它提供策略名称 (在任何其他位置) 并检查 **发送** 和 **侦听**。</span><span class="sxs-lookup"><span data-stu-id="04f6d-153">Click on your **Event Hub \> Shared access policies \> + Add** and then give it a Policy name (not used elsewhere) and check **Send** and **Listen**.</span></span>

![共享访问策略的图像](../../media/1867d13f46dc6a0f4cdae6cf00df24db.png)

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a><span data-ttu-id="04f6d-155">配置Microsoft 365 Defender发送电子邮件表</span><span class="sxs-lookup"><span data-stu-id="04f6d-155">Configure Microsoft 365 Defender to send email tables</span></span>


### <a name="setup-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a><span data-ttu-id="04f6d-156">安装程序Microsoft 365 Defender事件中心将电子邮件表格发送到 Splunk</span><span class="sxs-lookup"><span data-stu-id="04f6d-156">Setup Microsoft 365 Defender send Email tables to Splunk via Event Hub</span></span>


1. <span data-ttu-id="04f6d-157">使用Microsoft 365 Defender满足以下所有角色要求的帐户 <https://security.microsoft.com> 登录到 ：。</span><span class="sxs-lookup"><span data-stu-id="04f6d-157">Login to Microsoft 365 Defender at <https://security.microsoft.com> with an account that meets all the following role requirements:</span></span>

    - <span data-ttu-id="04f6d-158">要导出到的事件中心的 Event Hub *命名空间* 资源级别或更高级别的参与者角色。</span><span class="sxs-lookup"><span data-stu-id="04f6d-158">Contributor role at the Event Hub *Namespace* Resource level or higher for the Event Hub that you will be exporting to.</span></span> <span data-ttu-id="04f6d-159">如果没有此设置，在尝试保存设置时将看到导出错误。</span><span class="sxs-lookup"><span data-stu-id="04f6d-159">Without this you will get an export error when you try to save the settings.</span></span>

    - <span data-ttu-id="04f6d-160">绑定到 Azure 和 Azure 的租户上的全局管理员Microsoft 365 Defender管理员角色。</span><span class="sxs-lookup"><span data-stu-id="04f6d-160">Global Admin or Security Admin Role on the tenant tied to Microsoft 365 Defender and Azure.</span></span>

    ![安全门户图像](../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png)

1. <span data-ttu-id="04f6d-162">单击"**原始数据导出 \> +添加"。**</span><span class="sxs-lookup"><span data-stu-id="04f6d-162">Click on **Raw Data Export \> +Add**.</span></span>

    <span data-ttu-id="04f6d-163">现在，你将使用上面记录的数据。</span><span class="sxs-lookup"><span data-stu-id="04f6d-163">You will now use the data that your recorded above.</span></span>

    <span data-ttu-id="04f6d-164">**名称**：这是本地的，并且应该适用于你的环境。</span><span class="sxs-lookup"><span data-stu-id="04f6d-164">**Name**: This is local and should be whatever works in your environment.</span></span>

    <span data-ttu-id="04f6d-165">**将事件转发到事件中心**：选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="04f6d-165">**Forward events to event hub**: Select this checkbox.</span></span>

    <span data-ttu-id="04f6d-166">**Event-Hub 资源 ID：** 这是在设置事件中心时上面记录的事件中心命名空间资源 ID。</span><span class="sxs-lookup"><span data-stu-id="04f6d-166">**Event-Hub Resource ID**: This is the Event Hub Namespace Resource ID you  recorded above when you setup the Event Hub.</span></span>

    <span data-ttu-id="04f6d-167">**事件中心名称**：如果在事件中心命名空间内创建了事件中心，请粘贴上面记录的事件中心名称。</span><span class="sxs-lookup"><span data-stu-id="04f6d-167">**Event-Hub name**:  If you created an Event Hub inside your Event Hub Namespace, paste the Event Hub  name you recorded above.</span></span>

    <span data-ttu-id="04f6d-168">如果您选择允许Microsoft 365 Defender创建每个事件 (表) 事件中心，请保留此字段为空。</span><span class="sxs-lookup"><span data-stu-id="04f6d-168">If you choose to let Microsoft 365 Defender to create Event Hubs per Event Types  (Tables) for you, leave this field empty.</span></span>

    <span data-ttu-id="04f6d-169">**事件类型**：选择要转发到事件中心，然后转发到自定义应用的高级搜寻表。</span><span class="sxs-lookup"><span data-stu-id="04f6d-169">**Event Types**: Select the Advanced Hunting tables that you want to forward to the Event Hub and then on to your custom app.</span></span> <span data-ttu-id="04f6d-170">警报表来自Microsoft 365 Defender，设备表来自 Microsoft Defender for Endpoint (EDR) ，电子邮件表来自 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="04f6d-170">Alert tables are from Microsoft 365 Defender, Devices tables are from Microsoft Defender for Endpoint (EDR), and Email tables are from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="04f6d-171">电子邮件事件记录所有电子邮件事务。</span><span class="sxs-lookup"><span data-stu-id="04f6d-171">Email Events records all Email Transactions.</span></span> <span data-ttu-id="04f6d-172">还会记录 SafeLinks)  (、附件 (保险箱 附件) 和传递后事件 (ZAP) 的 URL，并可以加入到 NetworkMessageId 字段上的"电子邮件事件"中。</span><span class="sxs-lookup"><span data-stu-id="04f6d-172">The URL (SafeLinks), Attachment (Safe Attachments) and Post Delivery Events (ZAP) are also recorded and can be joined to the Email Events on the NetworkMessageId field.</span></span>

    ![流式 API 设置的图像](../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png)

1. <span data-ttu-id="04f6d-174">确保单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="04f6d-174">Make sure to click **Submit**.</span></span>

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a><span data-ttu-id="04f6d-175">验证事件是否导出到事件中心</span><span class="sxs-lookup"><span data-stu-id="04f6d-175">Verify that the events are being exported to the Event Hub</span></span>


<span data-ttu-id="04f6d-176">可以通过运行基本高级搜寻查询来验证事件是否正在发送到事件中心。</span><span class="sxs-lookup"><span data-stu-id="04f6d-176">You can verify that events are being sent to the Event Hub by running a basic Advanced Hunting query.</span></span> <span data-ttu-id="04f6d-177">选择 **搜寻 \> 高级 \> 搜寻查询** 并输入以下查询：</span><span class="sxs-lookup"><span data-stu-id="04f6d-177">Select **Hunting \> Advanced Hunting \> Query** and enter the following query:</span></span>

```
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

<span data-ttu-id="04f6d-178">这将显示在上一小时加入所有其他表时收到的电子邮件数。</span><span class="sxs-lookup"><span data-stu-id="04f6d-178">This will show you how many emails were received in the last hour joined across all the other tables.</span></span> <span data-ttu-id="04f6d-179">它还会显示是否看到可以导出到事件中心的事件。</span><span class="sxs-lookup"><span data-stu-id="04f6d-179">It will also show you if you are seeing events that could be exported to the event hub.</span></span> <span data-ttu-id="04f6d-180">如果此计数显示 0，则你将看不到进入事件中心的任何数据。</span><span class="sxs-lookup"><span data-stu-id="04f6d-180">If this count shows 0 then you won't see any data going out to the Event Hub.</span></span>

![高级搜寻的图像](../../media/c305e57dc6f72fa9eb035943f244738e.png)

<span data-ttu-id="04f6d-182">验证有要导出的数据后，可以查看事件中心以验证邮件是否传入。</span><span class="sxs-lookup"><span data-stu-id="04f6d-182">Once you have verified there is data to export, you can view the Event Hub to verify that messages are incoming.</span></span> <span data-ttu-id="04f6d-183">这最多可能需要一个小时。</span><span class="sxs-lookup"><span data-stu-id="04f6d-183">This can take up to one hour.</span></span> 
 
1. <span data-ttu-id="04f6d-184">在 Azure 中，转到 **事件中心 \> 单击命名空间 \> 事件中心 \> 单击事件中心**。</span><span class="sxs-lookup"><span data-stu-id="04f6d-184">In Azure, go to **Event Hubs \> Click on the Namespace \> Event Hubs \> Click on the Event Hub**.</span></span>  
1. <span data-ttu-id="04f6d-185">在 **"概述**"下，向下滚动，在"消息"图中，应看到"传入邮件"。</span><span class="sxs-lookup"><span data-stu-id="04f6d-185">Under **Overview**, scroll down and in the Messages graph you should see Incoming Messages.</span></span> <span data-ttu-id="04f6d-186">如果你未看到任何结果，则你的自定义应用将没有任何消息要接收。</span><span class="sxs-lookup"><span data-stu-id="04f6d-186">If you don't see any results, then there will be no messages for your custom app to ingest.</span></span>

    ![包含消息的"概述"选项卡的图像](../../media/e88060e315d76e74269a3fc866df047f.png)
