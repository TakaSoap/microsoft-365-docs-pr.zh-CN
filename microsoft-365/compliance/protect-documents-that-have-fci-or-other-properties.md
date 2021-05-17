---
title: 创建 DLP 策略来保护具有 FCI 或其他属性的文档
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何使用 DLP () 数据丢失防护策略来保护具有来自第三方系统的属性的文档。
ms.openlocfilehash: d3e635080ce05314adc8dd9599012e5f76bc0815
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113478"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a><span data-ttu-id="cf340-103">创建 DLP 策略来保护具有 FCI 或其他属性的文档</span><span class="sxs-lookup"><span data-stu-id="cf340-103">Create a DLP policy to protect documents with FCI or other properties</span></span>

<span data-ttu-id="cf340-104">Microsoft 365 DLP 策略 (数据丢失) 可以使用分类属性或项目属性来标识敏感项目。</span><span class="sxs-lookup"><span data-stu-id="cf340-104">Microsoft 365 data loss prevention (DLP) policies can use classification properties or item properties to identify sensitive items.</span></span> <span data-ttu-id="cf340-105">例如，可以使用：</span><span class="sxs-lookup"><span data-stu-id="cf340-105">For example you can use:</span></span>

- <span data-ttu-id="cf340-106">Windows服务器文件分类基础结构 (FCI) 属性</span><span class="sxs-lookup"><span data-stu-id="cf340-106">Windows Server File Classification infrastructure (FCI) properties</span></span>
- <span data-ttu-id="cf340-107">SharePoint文档属性</span><span class="sxs-lookup"><span data-stu-id="cf340-107">SharePoint document properties</span></span>
- <span data-ttu-id="cf340-108">第三方系统文档属性</span><span class="sxs-lookup"><span data-stu-id="cf340-108">third-party system document properties</span></span>

![显示 Office 365 和外部分类系统的图表](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

<span data-ttu-id="cf340-110">例如，您的组织可能使用 Windows Server FCI 来标识具有个人数据（如社会保险号）的项目，然后根据文档中找到的个人数据的类型和发生次数，将"个人身份信息"属性设置为"高、中等、**低**、公开"或"非 **PII"，** 对文档进行分类。 </span><span class="sxs-lookup"><span data-stu-id="cf340-110">For example, your organization might use Windows Server FCI to identify items with personal data such as social security numbers, and then classify the document by setting the **Personally Identifiable Information** property to **High**, **Moderate**, **Low**, **Public**, or **Not PII** based on the type and number of occurrences of personal data found in the document.</span></span>

<span data-ttu-id="cf340-111">在Microsoft 365中，您可以创建一个 DLP 策略，用于标识将该属性设置为特定值（如 **High** 和 **Medium）** 的文档，然后执行阻止访问这些文件等操作。</span><span class="sxs-lookup"><span data-stu-id="cf340-111">In Microsoft 365, you can create a DLP policy that identifies documents that have that property set to specific values, such as **High** and **Medium**, and then takes an action such as blocking access to those files.</span></span> <span data-ttu-id="cf340-112">如果将属性设置为“低”，则同一个策略可以使用其他规则来执行不同的操作，如发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="cf340-112">The same policy can have another rule that takes a different action if the property is set to **Low**, such as sending an email notification.</span></span> <span data-ttu-id="cf340-113">这样，DLP 与 Windows Server FCI 集成，并可帮助保护上载Office文档或从基于服务器Microsoft 365 Windows共享的文档。</span><span class="sxs-lookup"><span data-stu-id="cf340-113">In this way, DLP integrates with Windows Server FCI and can help protect Office documents uploaded or shared to Microsoft 365 from Windows Server-based file servers.</span></span>

<span data-ttu-id="cf340-114">DLP 策略只需查找特定的属性名称/值对。</span><span class="sxs-lookup"><span data-stu-id="cf340-114">A DLP policy simply looks for a specific property name/value pair.</span></span> <span data-ttu-id="cf340-115">可以使用任何文档属性，只要该属性具有 SharePoint 搜索的相应托管属性。</span><span class="sxs-lookup"><span data-stu-id="cf340-115">Any document property can be used, as long as the property has a corresponding managed property for SharePoint search.</span></span> <span data-ttu-id="cf340-116">例如，SharePoint 网站集可能使用名为“行程报告”的内容类型，包含名为“客户”的必填字段。</span><span class="sxs-lookup"><span data-stu-id="cf340-116">For example, a SharePoint site collection might use a content type named **Trip Report** with a required field named **Customer**.</span></span> <span data-ttu-id="cf340-117">只要有人创建行程报告，就必须输入客户名称。</span><span class="sxs-lookup"><span data-stu-id="cf340-117">Whenever a person creates a trip report, they must enter the customer name.</span></span> <span data-ttu-id="cf340-118">此属性名称/值对也可在 DLP 策略中使用，例如，如果您希望在"客户"字段包含 **Contoso** 时阻止来宾访问文档的规则。</span><span class="sxs-lookup"><span data-stu-id="cf340-118">This property name/value pair can also be used in a DLP policy—for example, if you want a rule that blocks access to the document for guests when the **Customer** field contains **Contoso**.</span></span>

<span data-ttu-id="cf340-119">如果要将 DLP 策略应用于具有特定标签Microsoft 365的内容，则不应按照此处的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="cf340-119">If you want to apply your DLP policy to content with specific Microsoft 365 labels, you should not follow the steps here.</span></span> <span data-ttu-id="cf340-120">相反，了解如何 [使用保留标签作为 DLP 策略中的条件](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="cf340-120">Instead, learn how to [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>

## <a name="before-you-create-the-dlp-policy"></a><span data-ttu-id="cf340-121">在创建 DLP 策略之前</span><span class="sxs-lookup"><span data-stu-id="cf340-121">Before you create the DLP policy</span></span>

<span data-ttu-id="cf340-122">您需要在 SharePoint 管理中心中创建托管属性，才能在 DLP 策略中使用 Windows Server FCI 属性或其他属性。</span><span class="sxs-lookup"><span data-stu-id="cf340-122">Before you can use a Windows Server FCI property or other property in a DLP policy, you need to create a managed property in the SharePoint admin center.</span></span> <span data-ttu-id="cf340-123">以下是原因。</span><span class="sxs-lookup"><span data-stu-id="cf340-123">Here's why.</span></span>

<span data-ttu-id="cf340-p106">示例</span><span class="sxs-lookup"><span data-stu-id="cf340-p106">In SharePoint Online and OneDrive for Business, the search index is built up by crawling the content on your sites. The crawler picks up content and metadata from the documents in the form of crawled properties. The search schema helps the crawler decide what content and metadata to pick up. Examples of metadata are the author and the title of a document. However, to get the content and metadata from the documents into the search index, the crawled properties must be mapped to managed properties. Only managed properties are kept in the index. For example, a crawled property related to author is mapped to a managed property related to author.</span></span>

> [!NOTE]
> <span data-ttu-id="cf340-131">在使用条件创建 DLP 规则时，请确保使用托管属性名称而不是已爬网属性 `ContentPropertyContainsWords` 名称。</span><span class="sxs-lookup"><span data-stu-id="cf340-131">Be sure to use a managed property name and not a crawled property name when creating DLP rules using the `ContentPropertyContainsWords` condition.</span></span>

<span data-ttu-id="cf340-132">这一点很重要，因为 DLP 使用搜索爬网程序来标识和分类您网站的敏感信息，然后将该敏感信息存储在搜索索引的安全部分。</span><span class="sxs-lookup"><span data-stu-id="cf340-132">This is important because DLP uses the search crawler to identify and classify sensitive information on your sites, and then store that sensitive information in a secure portion of the search index.</span></span> <span data-ttu-id="cf340-133">当您将文档上载到 Office 365 时，SharePoint 会自动创建基于文档属性的已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="cf340-133">When you upload a document to Office 365, SharePoint automatically creates crawled properties based on the document properties.</span></span> <span data-ttu-id="cf340-134">但是，要在 DLP 策略中使用 FCI 或其他属性，该已爬网属性需要映射到托管属性，以便将包含该属性的内容保留在索引中。</span><span class="sxs-lookup"><span data-stu-id="cf340-134">But to use an FCI or other property in a DLP policy, that crawled property needs to be mapped to a managed property so that content with that property is kept in the index.</span></span>

<span data-ttu-id="cf340-135">有关搜索和托管属性详细信息，请参阅管理[SharePoint Online 中的搜索架构](/sharepoint/manage-search-schema)。</span><span class="sxs-lookup"><span data-stu-id="cf340-135">For more information on search and managed properties, see [Manage the search schema in SharePoint Online](/sharepoint/manage-search-schema).</span></span>

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a><span data-ttu-id="cf340-136">步骤 1：将包含所需属性的文档上载到 Office 365</span><span class="sxs-lookup"><span data-stu-id="cf340-136">Step 1: Upload a document with the needed property to Office 365</span></span>

<span data-ttu-id="cf340-137">首先需要上载包含要在您的 DLP 策略中引用的属性的文档。</span><span class="sxs-lookup"><span data-stu-id="cf340-137">You first need to upload a document with the property that you want to reference in your DLP policy.</span></span> <span data-ttu-id="cf340-138">Microsoft 365将检测属性，并自动从该属性创建已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="cf340-138">Microsoft 365 will detect the property and automatically create a crawled property from it.</span></span> <span data-ttu-id="cf340-139">下一步，创建托管属性，然后将托管属性映射到此已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="cf340-139">In the next step, you'll create a managed property, and then map the managed property to this crawled property.</span></span>

### <a name="step-2-create-a-managed-property"></a><span data-ttu-id="cf340-140">步骤 2：创建托管属性</span><span class="sxs-lookup"><span data-stu-id="cf340-140">Step 2: Create a managed property</span></span>

1. <span data-ttu-id="cf340-141">登录 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="cf340-141">Sign in to the Microsoft 365 admin center.</span></span>

2. <span data-ttu-id="cf340-142">在左侧导航栏中，选择"管理 **中心** \> **SharePoint"。**</span><span class="sxs-lookup"><span data-stu-id="cf340-142">In the left navigation, choose **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="cf340-143">You're now in the SharePoint admin center.</span><span class="sxs-lookup"><span data-stu-id="cf340-143">You're now in the SharePoint admin center.</span></span>

3. <span data-ttu-id="cf340-144">在左侧导航栏中，在"**搜索管理"** \> 页上选择"搜索 **""** \> **管理搜索架构"。**</span><span class="sxs-lookup"><span data-stu-id="cf340-144">In the left navigation, choose **search** \> on the **search administration** page \> **Manage Search Schema**.</span></span>

   ![SharePoint 管理中心内的搜索管理页面](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. <span data-ttu-id="cf340-146">在" **托管属性"** 页上的 \> **"新建托管属性"上**。</span><span class="sxs-lookup"><span data-stu-id="cf340-146">On the **Managed Properties** page \> **New Managed Property**.</span></span>

   ![突出显示“新建托管属性”按钮的“托管属性”页面](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. <span data-ttu-id="cf340-p110">输入属性的名称和说明。此名称将显示在您的 DLP 策略中。</span><span class="sxs-lookup"><span data-stu-id="cf340-p110">Enter a name and description for the property. This name is what will appear in your DLP policies.</span></span>

6. <span data-ttu-id="cf340-150">对于“类型”，选择“文本”。</span><span class="sxs-lookup"><span data-stu-id="cf340-150">For **Type**, choose **Text**.</span></span>

7. <span data-ttu-id="cf340-151">在“主要特征”下，选择“可查询”和“可检索”。</span><span class="sxs-lookup"><span data-stu-id="cf340-151">Under **Main characteristics**, select **Queryable** and **Retrievable**.</span></span>

8. <span data-ttu-id="cf340-152">在 **"到已爬网属性的映射"** \> **下，添加映射**。</span><span class="sxs-lookup"><span data-stu-id="cf340-152">Under **Mappings to crawled properties** \> **Add a mapping**.</span></span>

9. <span data-ttu-id="cf340-153">在"**已爬网属性** 选择"对话框中，查找并选择与 Windows Server FCI 属性或将在 DLP 策略 OK 中使用的其他属性相对应的已爬网 \> \> **属性**。</span><span class="sxs-lookup"><span data-stu-id="cf340-153">In the **crawled property selection** dialog box \> find and select the crawled property that corresponds to the Windows Server FCI property or other property that you will use in your DLP policy \> **OK**.</span></span>

   ![已爬网属性选择对话框](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. <span data-ttu-id="cf340-155">在页面底部确定 \> 。</span><span class="sxs-lookup"><span data-stu-id="cf340-155">At the bottom of the page \> **OK**.</span></span>

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a><span data-ttu-id="cf340-156">创建使用 FCI 属性或其他属性的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="cf340-156">Create a DLP policy that uses an FCI property or other property</span></span>

<span data-ttu-id="cf340-157">本示例中，组织在其基于服务器Windows使用 FCI;具体来说，他们使用的是名为"个人身份信息"的 FCI 分类属性，其中可能的值为 **High、Moderate、Low、Public** 和 Not **PII。**   </span><span class="sxs-lookup"><span data-stu-id="cf340-157">In this example, an organization is using FCI on its Windows Server-based file servers; specifically, they're using the FCI classification property named **Personally Identifiable Information** with possible values of **High**, **Moderate**, **Low**, **Public**, and **Not PII**.</span></span> <span data-ttu-id="cf340-158">现在，他们希望在 OFFICE 365 中的 DLP 策略中使用其现有 FCI Office 365。</span><span class="sxs-lookup"><span data-stu-id="cf340-158">Now they want to use their existing FCI classification in their DLP policies in Office 365.</span></span>

<span data-ttu-id="cf340-159">首先，它们按照上述步骤在 SharePoint Online 中创建托管属性，该属性映射到从 FCI 属性自动创建的已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="cf340-159">First, they follow the steps above to create a managed property in SharePoint Online, which maps to the crawled property created automatically from the FCI property.</span></span>

<span data-ttu-id="cf340-160">接下来，它们使用两个规则创建 DLP 策略，这两个规则都使用条件 **"文档属性包含以下任一值"：**</span><span class="sxs-lookup"><span data-stu-id="cf340-160">Next, they create a DLP policy with two rules that both use the condition **Document properties contain any of these values**:</span></span>

- <span data-ttu-id="cf340-161">**FCI PII 内容 - 高、中等** 如果 FCI 分类属性"个人身份信息"等于"高"或"中等"，并且文档与组织外部人员共享，则第一个规则将限制对文档的访问。 </span><span class="sxs-lookup"><span data-stu-id="cf340-161">**FCI PII content - High, Moderate** The first rule restricts access to the document if the FCI classification property **Personally Identifiable Information** equals **High** or **Moderate** and the document is shared with people outside the organization.</span></span>

- <span data-ttu-id="cf340-162">**FCI PII 内容 - 低** 如果 FCI 分类属性"个人身份信息"等于 **"** 低"，并且文档与组织外部人员共享，则第二个规则会向文档所有者发送通知。</span><span class="sxs-lookup"><span data-stu-id="cf340-162">**FCI PII content - Low** The second rule sends a notification to the document owner if the FCI classification property **Personally Identifiable Information** equals **Low** and the document is shared with people outside the organization.</span></span>

### <a name="create-the-dlp-policy-by-using-powershell"></a><span data-ttu-id="cf340-163">使用 PowerShell 创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="cf340-163">Create the DLP policy by using PowerShell</span></span>

<span data-ttu-id="cf340-164">条件 **"文档** 属性包含这些值中的任意值"暂时在安全与合规中心的 UI 中不可用，但您仍可以使用 &amp; PowerShell 使用此条件。</span><span class="sxs-lookup"><span data-stu-id="cf340-164">The condition **Document properties contain any of these values** is temporarily not available in the UI of the Security &amp; Compliance Center, but you can still use this condition by using PowerShell.</span></span> <span data-ttu-id="cf340-165">您可以使用 cmdlet 处理 DLP 策略，并使用 cmdlet 和 参数添加条件  `New\Set\Get-DlpCompliancePolicy`  `New\Set\Get-DlpComplianceRule` 文档属性包含这些值  `ContentPropertyContainsWords` **中的任意值**。</span><span class="sxs-lookup"><span data-stu-id="cf340-165">You can use the  `New\Set\Get-DlpCompliancePolicy` cmdlets to work with a DLP policy, and use the  `New\Set\Get-DlpComplianceRule` cmdlets with the  `ContentPropertyContainsWords` parameter to add the condition **Document properties contain any of these values**.</span></span>

<span data-ttu-id="cf340-166">有关这些 cmdlet 详细信息，请参阅[安全 &amp; 与合规中心 cmdlet。](/powershell/exchange/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="cf340-166">For more information on these cmdlets, see [Security &amp; Compliance Center cmdlets](/powershell/exchange/exchange-online-powershell).</span></span>

1. [<span data-ttu-id="cf340-167">连接远程 &amp; PowerShell 访问安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="cf340-167">Connect to the Security &amp; Compliance Center using remote PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell)

2. <span data-ttu-id="cf340-168">使用 创建策略  `New-DlpCompliancePolicy` 。</span><span class="sxs-lookup"><span data-stu-id="cf340-168">Create the policy by using  `New-DlpCompliancePolicy`.</span></span>

<span data-ttu-id="cf340-169">此 PowerShell 创建适用于所有位置的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="cf340-169">This PowerShell creates a DLP policy that applies to all locations.</span></span>

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. <span data-ttu-id="cf340-170">使用 创建上述两个规则，其中一个规则用于"低"值，另一个规则用于"高"和"中等" `New-DlpComplianceRule` 值。   </span><span class="sxs-lookup"><span data-stu-id="cf340-170">Create the two rules described above by using  `New-DlpComplianceRule`, where one rule is for the **Low** value, and another rule is for the **High** and **Moderate** values.</span></span>

   <span data-ttu-id="cf340-171">下面是创建这两个规则的 PowerShell 示例。</span><span class="sxs-lookup"><span data-stu-id="cf340-171">Here is a PowerShell example that creates these two rules.</span></span> <span data-ttu-id="cf340-172">属性名/值对用引号括起来，而属性名可以指定用逗号分隔的多个值，中间没有空格，如  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span><span class="sxs-lookup"><span data-stu-id="cf340-172">The property name/value pairs are enclosed in quotation marks, and a property name may specify multiple values separated by commas with no spaces, like  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span></span>

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   <span data-ttu-id="cf340-173">Windows服务器 FCI 包括许多内置属性，包括此示例 **中使用的** 个人身份信息。</span><span class="sxs-lookup"><span data-stu-id="cf340-173">Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example.</span></span> <span data-ttu-id="cf340-174">每个属性的可能值对于每个组织可能不同。</span><span class="sxs-lookup"><span data-stu-id="cf340-174">The possible values for each property can be different for every organization.</span></span> <span data-ttu-id="cf340-175">此处 **使用的** **High、Moderate** 和 **Low** 值只是一个示例。</span><span class="sxs-lookup"><span data-stu-id="cf340-175">The **High**, **Moderate**, and **Low** values used here are only an example.</span></span> <span data-ttu-id="cf340-176">对于组织，可以在基于Windows服务器的文件服务器上查看服务器资源管理器中的 Windows Server FCI 分类属性及其可能值。</span><span class="sxs-lookup"><span data-stu-id="cf340-176">For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server.</span></span> <span data-ttu-id="cf340-177">有关详细信息，请参阅创建 [分类属性](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd759215(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="cf340-177">For more information, see [Create a classification property](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd759215(v=ws.11)).</span></span>

<span data-ttu-id="cf340-178">完成后，您的策略应具有两个新规则，这两个规则都使用 **Document 属性包含这些值中的任意一个** 条件。</span><span class="sxs-lookup"><span data-stu-id="cf340-178">When you finish, your policy should have two new rules that both use the **Document properties contain any of these values** condition.</span></span> <span data-ttu-id="cf340-179">此条件不会显示在 UI 中，但将显示其他条件、操作和设置。</span><span class="sxs-lookup"><span data-stu-id="cf340-179">This condition won't appear in the UI, though the other conditions, actions, and settings will appear.</span></span>

<span data-ttu-id="cf340-180">一个规则阻止访问其中“个人身份信息”属性等于“高”或“中等”的内容。</span><span class="sxs-lookup"><span data-stu-id="cf340-180">One rule blocks access to content where the **Personally Identifiable Information** property equals **High** or **Moderate**.</span></span> <span data-ttu-id="cf340-181">第二个规则会发送有关“个人身份信息”属性等于“低”的内容的通知。</span><span class="sxs-lookup"><span data-stu-id="cf340-181">A second rule sends a notification about content where the **Personally Identifiable Information** property equals **Low**.</span></span>

![显示刚创建的两条规则的“新建 DLP 策略”对话框](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a><span data-ttu-id="cf340-183">创建 DLP 策略之后</span><span class="sxs-lookup"><span data-stu-id="cf340-183">After you create the DLP policy</span></span>

<span data-ttu-id="cf340-184">执行前面部分中的步骤将创建一个 DLP 策略，该策略将快速检测具有该属性的内容，但只有在该内容是新上载的 (以便对内容编制索引) 时，或者如果该内容是旧内容但刚刚编辑过 (以便对内容重新编制索引) 。</span><span class="sxs-lookup"><span data-stu-id="cf340-184">Doing the steps in the previous sections will create a DLP policy that will quickly detect content with that property, but only if that content is newly uploaded (so that the content's indexed), or if that content is old but just edited (so that the content's re-indexed).</span></span>

<span data-ttu-id="cf340-p117">若要在任意位置检测包含该属性的内容，您可能需要手动请求对您的库、网站或网站集重新编制索引，以便 DLP 策略识别包含该属性的所有内容。在 SharePoint Online 中，内容基于已定义的爬网计划进行自动爬网。爬网程序选取自上次爬网以来已更改的内容，并更新索引。如果您需要在下一次计划的爬网之前，让您的 DLP 策略保护内容，您可以执行下列步骤。</span><span class="sxs-lookup"><span data-stu-id="cf340-p117">To detect content with that property everywhere, you may want to manually request that your library, site, or site collection be re-indexed, so that the DLP policy is aware of all the content with that property. In SharePoint Online, content is automatically crawled based on a defined crawl schedule. The crawler picks up content that has changed since the last crawl and updates the index. If you need your DLP policy to protect content before the next scheduled crawl, you can take these steps.</span></span>

> [!CAUTION]
> <span data-ttu-id="cf340-189">重新编制网站的索引可能会导致搜索系统上的负荷大量增加。</span><span class="sxs-lookup"><span data-stu-id="cf340-189">Re-indexing a site can cause a massive load on the search system.</span></span> <span data-ttu-id="cf340-190">除非方案绝对需要，否则不要重新编制网站的索引。</span><span class="sxs-lookup"><span data-stu-id="cf340-190">Don't re-index your site unless your scenario absolutely requires it.</span></span>

<span data-ttu-id="cf340-191">有关详细信息，请参阅[Manually request crawling and re-indexing of a site, a library or a list](/sharepoint/crawl-site-content)（手动请求对网站、库或列表进行爬网和重新编制索引）。</span><span class="sxs-lookup"><span data-stu-id="cf340-191">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](/sharepoint/crawl-site-content).</span></span>

### <a name="reindex-a-site-optional"></a><span data-ttu-id="cf340-192">为网站重新索引 (可选) </span><span class="sxs-lookup"><span data-stu-id="cf340-192">Reindex a site (optional)</span></span>

1. <span data-ttu-id="cf340-193">On the site， choose **设置** (gear icon in upper right) \> **Site 设置**.</span><span class="sxs-lookup"><span data-stu-id="cf340-193">On the site, choose **Settings** (gear icon in upper right) \> **Site Settings**.</span></span>

2. <span data-ttu-id="cf340-194">在 **"搜索"** 下，**选择"搜索和脱机可用性** \> **重新索引网站"。**</span><span class="sxs-lookup"><span data-stu-id="cf340-194">Under **Search**, choose **Search and offline availability** \> **Reindex site**.</span></span>

## <a name="more-information"></a><span data-ttu-id="cf340-195">更多信息</span><span class="sxs-lookup"><span data-stu-id="cf340-195">More information</span></span>

- [<span data-ttu-id="cf340-196">了解数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="cf340-196">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="cf340-197">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="cf340-197">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)

- [<span data-ttu-id="cf340-198">发送通知，并显示 DLP 策略的策略提示</span><span class="sxs-lookup"><span data-stu-id="cf340-198">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)

- [<span data-ttu-id="cf340-199">DLP 策略模板包含的内容</span><span class="sxs-lookup"><span data-stu-id="cf340-199">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)

- [<span data-ttu-id="cf340-200">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="cf340-200">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)