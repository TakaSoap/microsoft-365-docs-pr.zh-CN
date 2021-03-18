---
title: 创建安全的来宾共享环境
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-security-compliance
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: 了解可用于在 Microsoft 365 中创建安全来宾共享环境的选项，提供来宾访问以改进协作。
ms.openlocfilehash: 28b2efba9f0c4ba17811a9871b05ab9f5a7a4839
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838662"
---
# <a name="create-a-secure-guest-sharing-environment"></a><span data-ttu-id="1124e-103">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="1124e-103">Create a secure guest sharing environment</span></span>

<span data-ttu-id="1124e-104">在本文中，我们将介绍多种在 Microsoft 365 中创建安全来宾共享环境的选项。</span><span class="sxs-lookup"><span data-stu-id="1124e-104">In this article, we'll walk through a variety of options for creating a secure guest sharing environment in Microsoft 365.</span></span> <span data-ttu-id="1124e-105">这些示例可让你大致了解可用选项。</span><span class="sxs-lookup"><span data-stu-id="1124e-105">These are examples to give you an idea of the options available.</span></span> <span data-ttu-id="1124e-106">你可以在不同的组合中使用这些过程，以满足组织的安全性和合规性需求。</span><span class="sxs-lookup"><span data-stu-id="1124e-106">You can use these procedures in different combinations to meet the security and compliance needs of your organization.</span></span>

<span data-ttu-id="1124e-107">本文包括：</span><span class="sxs-lookup"><span data-stu-id="1124e-107">This article includes:</span></span>

- <span data-ttu-id="1124e-108">为来宾设置多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="1124e-108">Setting up multi-factor authentication for guests.</span></span>
- <span data-ttu-id="1124e-109">设置来宾的使用条款。</span><span class="sxs-lookup"><span data-stu-id="1124e-109">Setting up a terms of use for guests.</span></span>
- <span data-ttu-id="1124e-110">设置每季度来宾访问评审，以定期验证来宾是否继续需要团队和站点的权限。</span><span class="sxs-lookup"><span data-stu-id="1124e-110">Setting up quarterly guest access reviews to periodically validate whether guests continue to need permissions to teams and sites.</span></span>
- <span data-ttu-id="1124e-111">限制来宾仅对非托管设备进行仅 Web 访问。</span><span class="sxs-lookup"><span data-stu-id="1124e-111">Restricting guests to web-only access for unmanaged devices.</span></span>
- <span data-ttu-id="1124e-112">配置会话超时策略，确保来宾每天进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="1124e-112">Configuring a session timeout policy to ensure guests authenticate daily.</span></span>
- <span data-ttu-id="1124e-113">为高度敏感的项目创建敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="1124e-113">Creating a sensitive information type for a highly sensitive project.</span></span>
- <span data-ttu-id="1124e-114">自动为包含敏感信息类型的文档分配敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="1124e-114">Automatically assigning a sensitivity label to documents that contain a sensitive information type.</span></span>
- <span data-ttu-id="1124e-115">自动从带有敏感度标签的文件中删除来宾访问。</span><span class="sxs-lookup"><span data-stu-id="1124e-115">Automatically removing guest access from files with a sensitivity label.</span></span>

<span data-ttu-id="1124e-116">本文中所述的某些选项要求来宾在 Azure Active Directory 中具有帐户。</span><span class="sxs-lookup"><span data-stu-id="1124e-116">Some of the options discussed in this article require guests to have an account in Azure Active Directory.</span></span> <span data-ttu-id="1124e-117">若要确保在与来宾共享文件和文件夹时在目录中包含这些来宾，请使用[与 Azure AD B2B 预览版的 SharePoint 和 OneDrive 集成](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)。</span><span class="sxs-lookup"><span data-stu-id="1124e-117">To ensure that guests are included in the directory when you share files and folders with them, use the [SharePoint and OneDrive integration with Azure AD B2B Preview](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

<span data-ttu-id="1124e-118">请注意，我们不在本文中讨论如何启用来宾共享设置。</span><span class="sxs-lookup"><span data-stu-id="1124e-118">Note that we won't discuss enabling guest sharing settings in this article.</span></span> <span data-ttu-id="1124e-119">有关为不同方案启用来宾共享的详细信息，请参阅[与组织外部人员进行协作](collaborate-with-people-outside-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="1124e-119">See [Collaborating with people outside your organization](collaborate-with-people-outside-your-organization.md) for details about enabling guest sharing for different scenarios.</span></span>

## <a name="set-up-multi-factor-authentication-for-guests"></a><span data-ttu-id="1124e-120">为来宾设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="1124e-120">Set up multi-factor authentication for guests</span></span>

<span data-ttu-id="1124e-121">多重身份验证可显著降低帐户被盗的机率。</span><span class="sxs-lookup"><span data-stu-id="1124e-121">Multi-factor authentication greatly reduces the chances of an account being compromised.</span></span> <span data-ttu-id="1124e-122">由于来宾对个人电子邮件帐户的使用可能不符合任何管理策略或最佳做法，因此要求对来宾进行多重身份验证尤为重要。</span><span class="sxs-lookup"><span data-stu-id="1124e-122">Since guests may be using personal email accounts that don't adhere to any governance policies or best practices, it's especially important to require multi-factor authentication for guests.</span></span> <span data-ttu-id="1124e-123">如果来宾的用户名和密码被盗，则要求进行双重身份验证可大大降低未知方获得对网站和文件的访问权限的机率。</span><span class="sxs-lookup"><span data-stu-id="1124e-123">If a guest's username and password is stolen, requiring a second factor of authentication greatly reduces the chances of unknown parties gaining access to your sites and files.</span></span>

<span data-ttu-id="1124e-124">在此示例中，我们将使用 Azure Active Directory 中的条件访问策略为来宾设置多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="1124e-124">In this example, we'll set up multi-factor authentication for guests by using a conditional access policy in Azure Active Directory.</span></span>

<span data-ttu-id="1124e-125">为来宾设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="1124e-125">To set up multi-factor authentication for guests</span></span>

1. <span data-ttu-id="1124e-126">转到 “[ Azure 条件访问策略](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)”。</span><span class="sxs-lookup"><span data-stu-id="1124e-126">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="1124e-127">在“**条件访问 | 策略**”边栏选项卡上，单击“**新建策略**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-127">On the **Conditional Access | Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="1124e-128">在“**名称**”字段中，输入名称。</span><span class="sxs-lookup"><span data-stu-id="1124e-128">In the **Name** field, type a name.</span></span>
4. <span data-ttu-id="1124e-129">在“**分配**”下，单击“**用户和组**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-129">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="1124e-130">在“**用户和组**”边栏选项卡上，选择“**选择用户和组**”，然后选中“**所有来宾和外部用户**”复选框。</span><span class="sxs-lookup"><span data-stu-id="1124e-130">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="1124e-131">在“**分配**”下，单击“**云应用或操作**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-131">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="1124e-132">在“**云应用或操作**”边栏选项卡中，选择“**包含**”选项卡上的“**所有云应用**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-132">On the **Cloud apps or actions** blade, select **All cloud apps** on the **Include** tab.</span></span>
8. <span data-ttu-id="1124e-133">在“**访问控制**”下，单击“**授予**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-133">Under **Access controls**, click **Grant**.</span></span>
9. <span data-ttu-id="1124e-134">在“**授予**”边栏选项卡上，选中“**要求多重身份验证**”复选框，然后单击“**选择**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-134">On the **Grant** blade, select the **Require multi-factor authentication** check box, and then click **Select**.</span></span>
10. <span data-ttu-id="1124e-135">在“**新建**”边栏选项卡中的“**启用策略**”下面，单击“**打开**”，然后单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-135">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

<span data-ttu-id="1124e-136">现在，来宾需要在多重身份验证中进行注册，然后才能访问共享内容、网站或团队。</span><span class="sxs-lookup"><span data-stu-id="1124e-136">Now, guest will be required to enroll in multi-factor authentication before they can access shared content, sites, or teams.</span></span>

### <a name="more-information"></a><span data-ttu-id="1124e-137">更多信息</span><span class="sxs-lookup"><span data-stu-id="1124e-137">More information</span></span>

[<span data-ttu-id="1124e-138">规划 Azure Active Directory 多重身份验证部署</span><span class="sxs-lookup"><span data-stu-id="1124e-138">Planning an Azure AD Multi-Factor Authentication deployment</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)

## <a name="set-up-a-terms-of-use-for-guests"></a><span data-ttu-id="1124e-139">设置来宾的使用条款</span><span class="sxs-lookup"><span data-stu-id="1124e-139">Set up a terms of use for guests</span></span>

<span data-ttu-id="1124e-140">在某些情况中，来宾可能未与贵组织签署保密协议或其他法律协议。</span><span class="sxs-lookup"><span data-stu-id="1124e-140">In some situations guests may not have signed non-disclosure agreements or other legal agreements with your organization.</span></span> <span data-ttu-id="1124e-141">你可以要求来宾在访问与之共享的文件之前同意使用条款。</span><span class="sxs-lookup"><span data-stu-id="1124e-141">You can require guests to agree to a terms of use before accessing files that are shared with them.</span></span> <span data-ttu-id="1124e-142">可在他们首次尝试访问共享文件或网站时显示使用条款。</span><span class="sxs-lookup"><span data-stu-id="1124e-142">The terms of use can be displayed the first time they attempt to access a shared file or site.</span></span>

<span data-ttu-id="1124e-143">若要创建使用条款，首先需要在 Word 或其他创作程序中创建文档，然后将其另存为 pdf 文件。</span><span class="sxs-lookup"><span data-stu-id="1124e-143">To create a terms of use, you first need to create the document in Word or another authoring program, and then save it as a .pdf file.</span></span> <span data-ttu-id="1124e-144">然后，可将该文件上传到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="1124e-144">This file can then be uploaded to Azure AD.</span></span>

<span data-ttu-id="1124e-145">创建 Azure AD 使用条款</span><span class="sxs-lookup"><span data-stu-id="1124e-145">To create an Azure AD terms of use</span></span>

1. <span data-ttu-id="1124e-146">以全局管理员、安全管理员或条件访问管理员的身份登录到 Azure。</span><span class="sxs-lookup"><span data-stu-id="1124e-146">Sign in to Azure as a Global Administrator, Security Administrator, or Conditional Access Administrator.</span></span>
2. <span data-ttu-id="1124e-147">导航到“[使用条款](https://aka.ms/catou)”。</span><span class="sxs-lookup"><span data-stu-id="1124e-147">Navigate to [Terms of use](https://aka.ms/catou).</span></span>
3. <span data-ttu-id="1124e-148">单击“**新建条款**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-148">Click **New terms**.</span></span>

   ![Azure AD 新使用条款设置的屏幕截图](../media/azure-ad-guest-terms-of-use.png)

4. <span data-ttu-id="1124e-150">键入“**名称**”和“**显示名称**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-150">Type a **Name** and **Display name**.</span></span>
6. <span data-ttu-id="1124e-151">对于“**使用条款文档**”，浏览至你创建的 pdf 文件并选择它。</span><span class="sxs-lookup"><span data-stu-id="1124e-151">For **Terms of use document**, browse to the pdf file that you created and select it.</span></span>
7. <span data-ttu-id="1124e-152">选择使用条款文档的语言。</span><span class="sxs-lookup"><span data-stu-id="1124e-152">Select the language for your terms of use document.</span></span>
8. <span data-ttu-id="1124e-153">将“**要求用户展开使用条款**”设置为“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-153">Set **Require users to expand the terms of use** to **On**.</span></span>
9. <span data-ttu-id="1124e-154">在“**条件访问**”下的“**强制实施条件访问策略模板**”列表中，选择“**稍后创建条件访问策略**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-154">Under **Conditional Access**, in the **Enforce with Conditional Access policy template** list choose **Create conditional access policy later**.</span></span>
10. <span data-ttu-id="1124e-155">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-155">Click **Create**.</span></span>

<span data-ttu-id="1124e-156">创建使用条款后，下一步是创建对来宾显示使用条款的条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="1124e-156">Once you've created the terms of use, the next step is to create a conditional access policy that displays the terms of use to guests.</span></span>

<span data-ttu-id="1124e-157">创建条件访问策略</span><span class="sxs-lookup"><span data-stu-id="1124e-157">To create a conditional access policy</span></span>

1. <span data-ttu-id="1124e-158">转到 “[ Azure 条件访问策略](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)”。</span><span class="sxs-lookup"><span data-stu-id="1124e-158">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="1124e-159">在“**条件访问 | 策略**”边栏选项卡上，单击“**新建策略**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-159">On the **Conditional Access | Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="1124e-160">在“**名称**”框中，键入名称。</span><span class="sxs-lookup"><span data-stu-id="1124e-160">In the **Name** box, type a name.</span></span>
4. <span data-ttu-id="1124e-161">在“**分配**”下，单击“**用户和组**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-161">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="1124e-162">在“**用户和组**”边栏选项卡上，选择“**选择用户和组**”，然后选中“**所有来宾和外部用户**”复选框。</span><span class="sxs-lookup"><span data-stu-id="1124e-162">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="1124e-163">在“**分配**”下，单击“**云应用或操作**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-163">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="1124e-164">在“**包括**”选项卡上，选择“**选择应用**”，然后单击“**选择**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-164">On the **Include** tab, select **Select apps**, and then click **Select**.</span></span>
8. <span data-ttu-id="1124e-165">在“**选择**”边栏选项卡上，选择“**Microsoft Teams**”、“**Office 365 SharePoint Online**”和“**Outlook Groups**”，然后单击“**选择**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-165">On the **Select** blade, select **Microsoft Teams**, **Office 365 SharePoint Online**, and **Outlook Groups**, and then click **Select**.</span></span>
9. <span data-ttu-id="1124e-166">在“**访问控制**”下，单击“**授予**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-166">Under **Access controls**, click **Grant**.</span></span>
10. <span data-ttu-id="1124e-167">在“**授予**”边栏选项卡上，选择“**来宾使用条款**”，然后单击“**选择**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-167">On the **Grant** blade, select **Guest terms of use**, and then click **Select**.</span></span>
11. <span data-ttu-id="1124e-168">在“**新建**”边栏选项卡中的“**启用策略**”下面，单击“**打开**”，然后单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-168">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

<span data-ttu-id="1124e-169">现在，当来宾首次尝试访问组织中的内容、团队或网站时，必须接受使用条款。</span><span class="sxs-lookup"><span data-stu-id="1124e-169">Now, the first time a guest attempts to access content or a team or site in your organization, they will be required to accept the terms of use.</span></span>

> [!NOTE]
> <span data-ttu-id="1124e-170">使用条件访问需要 Azure AD Premium P1 许可证。</span><span class="sxs-lookup"><span data-stu-id="1124e-170">Using Conditional Access requires an Azure AD Premium P1 license.</span></span> <span data-ttu-id="1124e-171">有关详细信息，请参阅[什么是条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。</span><span class="sxs-lookup"><span data-stu-id="1124e-171">For more information, see [What is Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="more-information"></a><span data-ttu-id="1124e-172">更多信息</span><span class="sxs-lookup"><span data-stu-id="1124e-172">More information</span></span>

[<span data-ttu-id="1124e-173">Azure Active Directory 使用条款</span><span class="sxs-lookup"><span data-stu-id="1124e-173">Azure Active Directory terms of use</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)

## <a name="set-up-guest-access-reviews"></a><span data-ttu-id="1124e-174">设置来宾访问评审</span><span class="sxs-lookup"><span data-stu-id="1124e-174">Set up guest access reviews</span></span>

<span data-ttu-id="1124e-175">借助 Azure AD 中的访问评审功能，可以自动定期评审用户对各个团队和组的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1124e-175">With access reviews in Azure AD, you can automate a periodic review of user access to various teams and groups.</span></span> <span data-ttu-id="1124e-176">通过特别要求对来宾进行访问评审，可帮助确保来宾只在规定时间内拥有对组织敏感信息的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1124e-176">By requiring an access review for guests specifically, you can help ensure guests do not retain access to your organization's sensitive information for longer than is necessary.</span></span>

<span data-ttu-id="1124e-177">设置来宾访问评审</span><span class="sxs-lookup"><span data-stu-id="1124e-177">To set up a guest access review</span></span>

1. <span data-ttu-id="1124e-178">在 [Identity Governance](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade) 页面上的左侧菜单中，单击“**访问评审**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-178">On the [Identity Governance page](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade), in the left menu, click **Access reviews**.</span></span>
2. <span data-ttu-id="1124e-179">单击“**新建访问评审**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-179">Click **New access review**.</span></span>
3. <span data-ttu-id="1124e-180">选择 “**Microsoft Teams + Microsoft 365 组**” 选项。</span><span class="sxs-lookup"><span data-stu-id="1124e-180">Choose the **Teams + Groups** option.</span></span>
4. <span data-ttu-id="1124e-181">选择“**所有含来宾用户的Microsoft 365 组**”选项。</span><span class="sxs-lookup"><span data-stu-id="1124e-181">Choose the **All Microsoft 365 groups with guest users** option.</span></span> <span data-ttu-id="1124e-182">如果需要排除任何组，单击“**选择要排除的组**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-182">Click **Select group(s) to exclude** if you want to exclude any groups.</span></span>
5. <span data-ttu-id="1124e-183">选择“**仅来宾用户**”选项，然后单击“**下一步：审阅**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-183">Choose the **Guest users only** option, and then click **Next: Reviews**.</span></span>
6. <span data-ttu-id="1124e-184">在“**选择评审员**”下，选择“**组所有者**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-184">Under **Select reviewers**, choose **Group Owner(s)**.</span></span>
7. <span data-ttu-id="1124e-185">单击“**选择回退评审员**”，选择回退评审员，然后单击“**选择**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-185">Click **Select fallback reviewers**, choose who should be the fallback reviewers, and then click **Select**.</span></span>
8. <span data-ttu-id="1124e-186">在“**指定定期评审**”，选择“**每季**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-186">Under **Specify recurrence of review**, choose **Quarterly**.</span></span>
9. <span data-ttu-id="1124e-187">选择开始日期与持续时间。</span><span class="sxs-lookup"><span data-stu-id="1124e-187">Select a start date and duration.</span></span>
10. <span data-ttu-id="1124e-188">在“**结束**”处，选择“**从不**”，然后单击“**下一步：设置**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-188">For **End**, choose **Never**, and then click **Next: Settings**.</span></span>

    ![Azure AD 访问评审选项卡的屏幕截图](../media/azure-ad-create-access-review.png)

11. <span data-ttu-id="1124e-190">在“**设置**”选项卡中，查看设置是否符合你的商业规则。</span><span class="sxs-lookup"><span data-stu-id="1124e-190">On the **Settings** tab, review the settings for compliance with your business rules.</span></span>

    ![Azure AD 访问评审设置选项卡截图](../media/azure-ad-create-access-review-settings.png)

12. <span data-ttu-id="1124e-192">单击“**下一步: 评审+创建**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-192">Click **Next: Review + Create**.</span></span>
13. <span data-ttu-id="1124e-193">键入“**评审姓名**”然后查看设置。</span><span class="sxs-lookup"><span data-stu-id="1124e-193">Type a **Review name** and review the settings.</span></span>
14. <span data-ttu-id="1124e-194">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-194">Click **Create**.</span></span>

<span data-ttu-id="1124e-195">请务必注意，可以向来宾授予对团队或组的访问权限，也可以授予对各个文件和文件夹的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1124e-195">It's important to note that guests can be given access to teams or groups, or to individual files and folders.</span></span> <span data-ttu-id="1124e-196">授予对文件和文件夹的访问权限时，可能不会将来宾添加到任何特定组。</span><span class="sxs-lookup"><span data-stu-id="1124e-196">When given access to files and folders, guests may not be added to any particular group.</span></span> <span data-ttu-id="1124e-197">如果想要对不属于团队或组的来宾执行访问评审，可在 Azure AD 中创建一个动态组，以包含所有来宾并为该组创建访问评审。</span><span class="sxs-lookup"><span data-stu-id="1124e-197">If you want to do access reviews on guests who don't belong to a team or group, you can create a dynamic group in Azure AD to contain all guests and then create an access review for that group.</span></span> <span data-ttu-id="1124e-198">网站所有者还可以管理[网站来宾的到期时间](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea)</span><span class="sxs-lookup"><span data-stu-id="1124e-198">Site owners can also manage [guest expiration for the site](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea)</span></span>

### <a name="more-information"></a><span data-ttu-id="1124e-199">更多信息</span><span class="sxs-lookup"><span data-stu-id="1124e-199">More information</span></span>

[<span data-ttu-id="1124e-200">使用 Azure AD 访问评审管理来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="1124e-200">Manage guest access with Azure AD access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)

[<span data-ttu-id="1124e-201">在 Azure AD 访问评审中针对组或应用程序创建访问评审</span><span class="sxs-lookup"><span data-stu-id="1124e-201">Create an access review of groups or applications in Azure AD access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)

## <a name="set-up-web-only-access-for-guests"></a><span data-ttu-id="1124e-202">为来宾用户设置仅 Web 访问权限</span><span class="sxs-lookup"><span data-stu-id="1124e-202">Set up web-only access for guests</span></span>

<span data-ttu-id="1124e-203">通过要求来宾仅使用 Web 浏览器来访问团队、网站和文件，可以减少攻击面并简化管理。</span><span class="sxs-lookup"><span data-stu-id="1124e-203">You can reduce your attack surface and ease administration by requiring guests to access your teams, sites, and files by using a web browser only.</span></span>

<span data-ttu-id="1124e-204">对于 Microsoft 365 组和团队，这是通过 Azure AD 条件访问策略完成的。</span><span class="sxs-lookup"><span data-stu-id="1124e-204">For Microsoft 365 Groups and Teams, this is done with an Azure AD conditional access policy.</span></span> <span data-ttu-id="1124e-205">对于 SharePoint，这是在 SharePoint 管理中心中进行配置的。</span><span class="sxs-lookup"><span data-stu-id="1124e-205">For SharePoint, this is configured in the SharePoint admin center.</span></span> <span data-ttu-id="1124e-206">（还可[使用敏感度标签限制来宾进行仅限于 Web 的访问](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。）</span><span class="sxs-lookup"><span data-stu-id="1124e-206">(You can also [use sensitivity labels to restrict guests to web-only access](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).)</span></span>

<span data-ttu-id="1124e-207">限制来宾对团队和组进行仅 Web 访问：</span><span class="sxs-lookup"><span data-stu-id="1124e-207">To restrict guests to web-only access for Groups and Teams:</span></span>

1. <span data-ttu-id="1124e-208">转到 “[ Azure 条件访问策略](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)”。</span><span class="sxs-lookup"><span data-stu-id="1124e-208">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="1124e-209">在“**条件访问 - 策略**”边栏选项卡上，单击“**新建策略**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-209">On the **Conditional Access - Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="1124e-210">在“**名称**”框中，键入名称。</span><span class="sxs-lookup"><span data-stu-id="1124e-210">In the **Name** box, type a name.</span></span>
4. <span data-ttu-id="1124e-211">在“**分配**”下，单击“**用户和组**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-211">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="1124e-212">在“**用户和组**”边栏选项卡上，选择“**选择用户和组**”，然后选中“**所有来宾和外部用户**”复选框。</span><span class="sxs-lookup"><span data-stu-id="1124e-212">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="1124e-213">在“**分配**”下，单击“**云应用或操作**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-213">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="1124e-214">在“**包括**”选项卡上，选择“**选择应用**”，然后单击“**选择**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-214">On the **Include** tab, select **Select apps**, and then click **Select**.</span></span>
8. <span data-ttu-id="1124e-215">在“**选择**”边栏选项卡上，选择“**Microsoft Teams**”和“**Outlook Groups**”，然后单击“**选择**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-215">On the **Select** blade, select **Microsoft Teams** and **Outlook Groups**, and then click **Select**.</span></span>
9. <span data-ttu-id="1124e-216">在“**分配**”下，单击“**条件**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-216">Under **Assignments**, click **Conditions**.</span></span>
10. <span data-ttu-id="1124e-217">在“**条件**”边栏选项卡上，单击“**客户端应用**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-217">On the **Conditions** blade, click **Client apps**.</span></span>
11. <span data-ttu-id="1124e-218">在“**客户端应用**”边栏选项卡上，为“**配置**”单击“**是**”，然后选择“**移动应用和桌面客户端**”、“**Exchange ActiveSync 客户端**”和“**其他客户端**”设置。</span><span class="sxs-lookup"><span data-stu-id="1124e-218">On the **Client apps** blade, click **Yes** for **Configure**, and then select the **Mobile apps and desktop clients**, **Exchange ActiveSync clients**, and **Other clients** settings.</span></span> <span data-ttu-id="1124e-219">清除“**浏览器**”复选框。</span><span class="sxs-lookup"><span data-stu-id="1124e-219">Clear the **Browser** check box.</span></span>

    ![Azure AD 条件访问客户端应用设置的屏幕截图](../media/azure-ad-conditional-access-client-mobile.png)

12. <span data-ttu-id="1124e-221">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-221">Click **Done**.</span></span>
13. <span data-ttu-id="1124e-222">在“**访问控制**”下，单击“**授予**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-222">Under **Access controls**, click **Grant**.</span></span>
14. <span data-ttu-id="1124e-223">在“**授予**”边栏选项卡上，选择“**需要标记为兼容的设备**”和“**需要加入混合 Azure AD 的设备**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-223">On the **Grant** blade, select **Require device to be marked as compliant** and **Require Hybrid Azure AD joined device**.</span></span>
15. <span data-ttu-id="1124e-224">在“**对于多个控件**”，选择“**需要某一已选控件**”，然后单击“**选择**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-224">Under **For multiple controls**, select **Require one of the selected controls**, and then click **Select**.</span></span>
16. <span data-ttu-id="1124e-225">在“**新建**”边栏选项卡中的“**启用策略**”下面，单击“**打开**”，然后单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-225">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

<span data-ttu-id="1124e-226">限制来宾对 SharePoint 进行仅 Web 访问</span><span class="sxs-lookup"><span data-stu-id="1124e-226">To restrict guests to web-ony access for SharePoint</span></span>

1. <span data-ttu-id="1124e-227">在“[SharePoint 管理中心](https://admin.microsoft.com/sharepoint)”中，展开“**策略**”，然后单击“**访问控制**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-227">In the [SharePoint admin center](https://admin.microsoft.com/sharepoint), expand **Policies** and click **Access control**.</span></span>
2. <span data-ttu-id="1124e-228">单击“**未托管的设备**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-228">Click **Unmanaged devices**.</span></span>
3. <span data-ttu-id="1124e-229">选择“**允许仅限 web 的受限访问**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-229">Select the **Allow limited, web-only access** option, and then click **Save**.</span></span>

<span data-ttu-id="1124e-230">注意，SharePoint 管理中心中的此设置在 Azure AD 中创建了支持条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="1124e-230">Note that this setting in the SharePoint admin center creates a supporting conditional access policy in Azure AD.</span></span>

## <a name="configure-a-session-timeout-for-guests"></a><span data-ttu-id="1124e-231">为来宾配置会话超时策略</span><span class="sxs-lookup"><span data-stu-id="1124e-231">Configure a session timeout for guests</span></span>

<span data-ttu-id="1124e-232">如果来宾用户的设备不安全，则定期要求来宾进行身份验证可以降低未知用户访问组织内容的可能性。</span><span class="sxs-lookup"><span data-stu-id="1124e-232">Requiring guests to authenticate on a regular basis can reduce the possibility of unknown users accessing your organization's content if a guest's device isn't kept secure.</span></span> <span data-ttu-id="1124e-233">可以在 Azure AD 中为来宾配置会话超时条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="1124e-233">You can configure a session timeout conditional access policy for guests in Azure AD.</span></span>

<span data-ttu-id="1124e-234">配置来宾会话超时策略</span><span class="sxs-lookup"><span data-stu-id="1124e-234">To configure a guest session timeout policy</span></span>

1. <span data-ttu-id="1124e-235">转到 “[ Azure 条件访问策略](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)”。</span><span class="sxs-lookup"><span data-stu-id="1124e-235">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="1124e-236">在“**条件访问 - 策略**”边栏选项卡上，单击“**新建策略**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-236">On the **Conditional Access - Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="1124e-237">在“**名称**”框中，键入“*来宾会话超时*”。</span><span class="sxs-lookup"><span data-stu-id="1124e-237">In the **Name** box, type *Guest session timeout*.</span></span>
4. <span data-ttu-id="1124e-238">在“**分配**”下，单击“**用户和组**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-238">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="1124e-239">在“**用户和组**”边栏选项卡上，选择“**选择用户和组**”，然后选中“**所有来宾和外部用户**”复选框。</span><span class="sxs-lookup"><span data-stu-id="1124e-239">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="1124e-240">在“**分配**”下，单击“**云应用或操作**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-240">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="1124e-241">在“**包括**”选项卡上，选择“**选择应用**”，然后单击“**选择**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-241">On the **Include** tab, select **Select apps**, and then click **Select**.</span></span>
8. <span data-ttu-id="1124e-242">在“**选择**”边栏选项卡上，选择“**Microsoft Teams**”、“**Office 365 SharePoint Online**”和“**Outlook Groups**”，然后单击“**选择**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-242">On the **Select** blade, select **Microsoft Teams**, **Office 365 SharePoint Online**, and **Outlook Groups**, and then click **Select**.</span></span>
9. <span data-ttu-id="1124e-243">在“**访问控制**”下，单击“**会话**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-243">Under **Access controls**, click **Session**.</span></span>
10. <span data-ttu-id="1124e-244">在“**会话**”边栏选项卡上，选择“**登录频率**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-244">On the **Session** blade, select **Sign-in frequency**.</span></span>
11. <span data-ttu-id="1124e-245">为时间段选择 **1** 和“**天**”，然后单击“**选择**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-245">Select **1** and **Days** for the time period, and then click **Select**.</span></span>
12. <span data-ttu-id="1124e-246">在“**新建**”边栏选项卡中的“**启用策略**”下面，单击“**打开**”，然后单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-246">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

## <a name="create-a-sensitive-information-type-for-a-highly-sensitive-project"></a><span data-ttu-id="1124e-247">为高度敏感的项目创建敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="1124e-247">Create a sensitive information type for a highly sensitive project</span></span>

<span data-ttu-id="1124e-248">敏感信息类型是预定义的字符串，可以在策略工作流中使用这些字符串来强制执行合规性要求。</span><span class="sxs-lookup"><span data-stu-id="1124e-248">Sensitive information types are predefined strings that can be used in policy workflows to enforce compliance requirements.</span></span> <span data-ttu-id="1124e-249">Microsoft 365 合规中心提供一百多种敏感信息类型，包括驾驶执照号码、信用卡号、银行帐号等。</span><span class="sxs-lookup"><span data-stu-id="1124e-249">The Microsoft 365 Compliance Center comes with over one hundred sensitive information types, including driver's license numbers, credit card numbers, bank account numbers, etc.</span></span>

<span data-ttu-id="1124e-250">你可以创建自定义敏感信息类型，以帮助管理特定于组织的内容。</span><span class="sxs-lookup"><span data-stu-id="1124e-250">You can create custom sensitive information types to help manage content specific to your organization.</span></span> <span data-ttu-id="1124e-251">在此示例中，我们将为高度敏感项目创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="1124e-251">In this example, we'll create a custom sensitive information type for a highly sensitive project.</span></span> <span data-ttu-id="1124e-252">然后，可使用此敏感信息类型自动应用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="1124e-252">We can then use this sensitive information type to automatically apply a sensitivity label.</span></span>

<span data-ttu-id="1124e-253">创建敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="1124e-253">To create a sensitive information type</span></span>

1. <span data-ttu-id="1124e-254">在 [Microsoft 365 合规中心](https://compliance.microsoft.com)的左侧导航中，展开“**分类**”，然后单击“**敏感信息类型**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-254">In the [Microsoft 365 Compliance Center](https://compliance.microsoft.com), in the left navigation, expand **Classification**, and then click **Sensitive info types**.</span></span>
2. <span data-ttu-id="1124e-255">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-255">Click **Create**.</span></span>
3. <span data-ttu-id="1124e-256">对于“**名称**”和“**说明**”，键入“**土星项目**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-256">For **Name** and **Description**, type **Project Saturn**, and then click **Next**.</span></span>
4. <span data-ttu-id="1124e-257">单击“**添加元素**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-257">Click **Add an element**.</span></span>
5. <span data-ttu-id="1124e-258">在“**检测内容包含**”列表上，选择“**关键字**”，然后在“关键字”框中键入“*土星项目*”。</span><span class="sxs-lookup"><span data-stu-id="1124e-258">On the **Detect content containing** list, select **Keywords**, and then type *Project Saturn* in the keyword box.</span></span>
6. <span data-ttu-id="1124e-259">单击“**下一步**”，再单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-259">Click **Next**, and then click **Finish**.</span></span>
7. <span data-ttu-id="1124e-260">如果系统询问你是否要测试敏感信息类型，请单击“**否**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-260">If asked if you would like to test the sensitive information type, click **No**.</span></span>

### <a name="more-information"></a><span data-ttu-id="1124e-261">更多信息</span><span class="sxs-lookup"><span data-stu-id="1124e-261">More information</span></span>

[<span data-ttu-id="1124e-262">自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="1124e-262">Custom sensitive information types</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/custom-sensitive-info-types)

## <a name="create-an-auto-labeling-policy-to-assign-a-sensitivity-label-based-on-a-sensitive-information-type"></a><span data-ttu-id="1124e-263">创建自动标记策略以基于敏感信息类型分配敏感度标签</span><span class="sxs-lookup"><span data-stu-id="1124e-263">Create an auto-labeling policy to assign a sensitivity label based on a sensitive information type</span></span>

<span data-ttu-id="1124e-264">如果在组织中使用敏感度标签，则可以将标签自动应用于包含定义的敏感信息类型的文件。</span><span class="sxs-lookup"><span data-stu-id="1124e-264">If you are using sensitivity labels in your organization, you can automatically apply a label to files that contain defined sensitive information types.</span></span> 

<span data-ttu-id="1124e-265">创建自动标记策略</span><span class="sxs-lookup"><span data-stu-id="1124e-265">To create an auto-labeling policy</span></span>

1. <span data-ttu-id="1124e-266">打开 [Microsoft 365 合规管理中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="1124e-266">Open the [Microsoft 365 compliance admin center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="1124e-267">在左侧导航栏中，单击“**信息保护**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-267">In the left navigation, click **Information protection**.</span></span>
3. <span data-ttu-id="1124e-268">在“**自动标记**”标签上，单击“**创建自动标记策略**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-268">On the **Auto-labeling** tab, click **Create auto-labeling policy**.</span></span>
4. <span data-ttu-id="1124e-269">在“**选择要将此标签要应用于的信息**”页面上，选择“**自定义**”，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-269">On the **Choose info you want this label applied to** page, choose **Custom** and click **Next**.</span></span>
5. <span data-ttu-id="1124e-270">输入策略的名称和描述，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-270">Type a name and description for the policy and click **Next**.</span></span>
6. <span data-ttu-id="1124e-271">在”**选择要应用标签的位置**“页面上，打开“**SharePoint网站**”，然后单击“**选择网站**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-271">On the **Choose locations where you want to apply the label** page, turn on **SharePoint sites** and click **Choose sites**.</span></span>
7. <span data-ttu-id="1124e-272">添加要启用自动标记的网站 URL，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-272">Add the URLs for the sites where you want to turn on auto-labeling and click **Done**.</span></span>
8. <span data-ttu-id="1124e-273">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-273">Click **Next**.</span></span>
9. <span data-ttu-id="1124e-274">在“**设置通用或高级规则**”页面上，选择“**通用规则**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-274">On the **Set up common or advanced rules** page, choose **Common rules** and click **Next**.</span></span>
10. <span data-ttu-id="1124e-275">在“**定义所有位置的内容规则**”页面上，单击“**新建规则**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-275">On the **Define rules for content in all locations** page, click **New rule**.</span></span>
11. <span data-ttu-id="1124e-276">在“**新建规则**”页面上，为规则命名，单击“**添加条件**”，然后单击“**内容包含敏感信息类型**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-276">On the **New rule** page, give the rule a name, click **Add condition**, and then click **Content contains sensitive info types**.</span></span>
12. <span data-ttu-id="1124e-277">单击“**添加**”，单击“**敏感信息类型**”，选择要使用的敏感信息类型，单击“**添加**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-277">Click **Add**, click **Sensitive info types**, choose the sensitive info types that you want to use, click **Add**, and then click **Save**.</span></span>
13. <span data-ttu-id="1124e-278">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-278">Click **Next**.</span></span>
14. <span data-ttu-id="1124e-279">单击“**选择标签**”，选择要使用的标签，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-279">Click **Choose a label**, select the label you want to use, and then click **Add**.</span></span>
15. <span data-ttu-id="1124e-280">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-280">Click **Next**.</span></span>
16. <span data-ttu-id="1124e-281">将策略置于模拟模式，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-281">Leave the policy in simulation mode and click **Next**.</span></span>
17. <span data-ttu-id="1124e-282">单击“**创建策略**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-282">Click **Create policy**, and then click **Done**.</span></span>

<span data-ttu-id="1124e-283">实施策略后，当用户在文档中键入“Project Saturn”时，自动标记策略将在扫描文件时自动应用指定的标签。</span><span class="sxs-lookup"><span data-stu-id="1124e-283">With the policy in place, when a user types "Project Saturn" into a document, the auto-labeling policy will automatically apply the specified label when it scans the file.</span></span>

### <a name="more-information"></a><span data-ttu-id="1124e-284">更多信息</span><span class="sxs-lookup"><span data-stu-id="1124e-284">More information</span></span>

[<span data-ttu-id="1124e-285">将敏感度标签自动应用于内容</span><span class="sxs-lookup"><span data-stu-id="1124e-285">Apply a sensitivity label to content automatically</span></span>](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

## <a name="create-a-dlp-policy-to-remove-guest-access-to-highly-sensitive-files"></a><span data-ttu-id="1124e-286">创建 DLP 策略以删除来宾对高度敏感文件的访问</span><span class="sxs-lookup"><span data-stu-id="1124e-286">Create a DLP policy to remove guest access to highly sensitive files</span></span>

<span data-ttu-id="1124e-287">可使用 [数据丢失防护（DLP）](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) 阻止不需要的敏感内容访客共享。</span><span class="sxs-lookup"><span data-stu-id="1124e-287">You can use [data loss prevention (DLP)](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to prevent unwanted guest sharing of sensitive content.</span></span> <span data-ttu-id="1124e-288">数据丢失防护可以根据文件的敏感度标签采取措施并删除来宾访问权限。</span><span class="sxs-lookup"><span data-stu-id="1124e-288">Data loss prevention can take action based on a file's sensitivity label and remove guest access.</span></span>

<span data-ttu-id="1124e-289">创建 DLP 规则</span><span class="sxs-lookup"><span data-stu-id="1124e-289">To create a DLP rule</span></span>

1. <span data-ttu-id="1124e-290">在 Microsoft 365 合规性管理中心中，转到“[数据丢失防护页面](https://compliance.microsoft.com/datalossprevention)”。</span><span class="sxs-lookup"><span data-stu-id="1124e-290">In the Microsoft 365 compliance admin center, go to the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention).</span></span>
2. <span data-ttu-id="1124e-291">单击“**创建策略**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-291">Click **Create policy**.</span></span>
3. <span data-ttu-id="1124e-292">选择“**自定义**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-292">Choose **Custom** and click **Next**.</span></span>
4. <span data-ttu-id="1124e-293">键入策略名称，并单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-293">Type a name for the policy and click **Next**.</span></span>
5. <span data-ttu-id="1124e-294">在“**要应用该策略的位置**”页面上，关闭除 “**SharePoint 网站**”和 “**OneDrive 帐户**”之外的所有设置，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-294">On the **Locations to apply the policy** page turn off all settings except **SharePoint sites** and **OneDrive accounts**, and then click **Next**.</span></span>
6. <span data-ttu-id="1124e-295">在“**定义策略设置**”页面上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-295">On the **Define policy settings** page, click **Next**.</span></span>
7. <span data-ttu-id="1124e-296">在“**自定义高级 DLP 规则**”页面上，单击“**创建规则**”并输入规则名称。</span><span class="sxs-lookup"><span data-stu-id="1124e-296">On the **Customize advanced DLP rules** page, click **Create rule** and type a name for the rule.</span></span>
8. <span data-ttu-id="1124e-297">在“**条件**”下，单击“**添加条件**”，然后选择“**内容包含**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-297">Under **Conditions**, click **Add condition**, and choose **Content contains**.</span></span>
9. <span data-ttu-id="1124e-298">单击“**添加**”，选择“**敏感度标签**”，选择要使用的标签，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-298">Click **Add**, choose **Sensitivity labels**, choose the labels you want to use, and click **Add**.</span></span>

   ![条件选项、敏感信息类型、敏感度标签和保留标签的屏幕截图。](../media/limit-accidental-exposure-dlp-conditions.png)

10. <span data-ttu-id="1124e-300">在“**操作**”下，单击“**添加操作**”，然后选择“**限制访问或对 Microsoft 365 位置中的内容进行加密**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-300">Under **Actions** click **Add an action** and choose **Restrict access or encrypt the content in Microsoft 365 locations**.</span></span>
11. <span data-ttu-id="1124e-301">选中“**限制访问或对 Microsoft 365 位置中的内容进行加密**”复选框，然后选择“**仅限组织外部人员**”选项。</span><span class="sxs-lookup"><span data-stu-id="1124e-301">Select the **Restrict access or encrypt the content in Microsoft 365 locations** check box and then choose the **Only people outside your organization** option.</span></span>

      ![DLP 规则操作选项屏幕截图](../media/dlp-remove-guest-access-sensitive-files.png)

12. <span data-ttu-id="1124e-303">单击“**保存**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-303">Click **Save** and then click **Next**.</span></span>
13. <span data-ttu-id="1124e-304">选择测试选项，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-304">Choose your test options and click **Next**.</span></span>
14. <span data-ttu-id="1124e-305">单击“**提交**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="1124e-305">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="1124e-306">请务必注意，如果来宾是整个网站或团队的成员，则此策略不会删除访问权限。</span><span class="sxs-lookup"><span data-stu-id="1124e-306">It's important to note that this policy doesn't remove access if the guest is a member of the site or team as a whole.</span></span> <span data-ttu-id="1124e-307">如果计划将网站或团队中的高度机密文档与来宾成员进行共享，请考虑使用 [Teams 中的专用频道](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e)并仅允许组织成员在专用频道中共享。</span><span class="sxs-lookup"><span data-stu-id="1124e-307">If you plan to have highly sensitive documents in a site or team with guest members, consider using [private channels in Teams](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e) and only allowing members of your organization in the private channels.</span></span>

## <a name="additional-options"></a><span data-ttu-id="1124e-308">其他选项</span><span class="sxs-lookup"><span data-stu-id="1124e-308">Additional options</span></span>

<span data-ttu-id="1124e-309">Microsoft 365 和 Azure Active Directory 中提供部分选项，可帮助保护来宾共享环境的安全。</span><span class="sxs-lookup"><span data-stu-id="1124e-309">There are some additional options in Microsoft 365 and Azure Active Directory that can help secure your guest sharing environment.</span></span>

- <span data-ttu-id="1124e-310">可创建允许或拒绝的共享域的列表，限制用户可以与之共享的人员。</span><span class="sxs-lookup"><span data-stu-id="1124e-310">You can create a list of allowed or denied sharing domains to limit who users can share with.</span></span> <span data-ttu-id="1124e-311">有关详细信息，请参见“[按域限制共享 SharePoint 和 OneDrive 内容”](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)和“[允许或组织邀请指定组织的 B2B 用户](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)”。</span><span class="sxs-lookup"><span data-stu-id="1124e-311">See [Restrict sharing of SharePoint and OneDrive content by domain](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) and [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) for more information.</span></span>
- <span data-ttu-id="1124e-312">可限制用户连接至的其他 Azure Active Directory 租户。</span><span class="sxs-lookup"><span data-stu-id="1124e-312">You can limit which other Azure Active Directory tenants your users can connect to.</span></span> <span data-ttu-id="1124e-313">参见“[使用租户限制管理对 SaaS 云应用程序的访问权限](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)”了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="1124e-313">See [Use tenant restrictions to manage access to SaaS cloud applications](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions) for information.</span></span>
- <span data-ttu-id="1124e-314">可创建合作伙伴能够帮助管理访客用户的托管环境。</span><span class="sxs-lookup"><span data-stu-id="1124e-314">You can create a managed environment where partners can help manage guest accounts.</span></span> <span data-ttu-id="1124e-315">有关信息，请参见“[创建有访客用户的 B2B 外联网](https://docs.microsoft.com/Office365/Enterprise/b2b-extranet)”。</span><span class="sxs-lookup"><span data-stu-id="1124e-315">See [Create a B2B extranet with managed guests](https://docs.microsoft.com/Office365/Enterprise/b2b-extranet) for information.</span></span>

## <a name="see-also"></a><span data-ttu-id="1124e-316">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1124e-316">See Also</span></span>

[<span data-ttu-id="1124e-317">与来宾共享时限制文件意外曝光</span><span class="sxs-lookup"><span data-stu-id="1124e-317">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="1124e-318">有关与未经认证用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="1124e-318">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="1124e-319">创建托管有来宾的 B2B 外联网</span><span class="sxs-lookup"><span data-stu-id="1124e-319">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)
