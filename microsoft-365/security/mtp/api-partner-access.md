---
title: 合作伙伴通过 Microsoft 365 Defender API 访问
description: 了解如何创建应用以代表用户以编程方式访问 Microsoft 365 Defender。
keywords: 合作伙伴， 访问， api， 多租户， 同意， 访问令牌， 应用
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 07afb0baf5c115f2029abfe03795b081a4f253a8
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929394"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a><span data-ttu-id="1671c-104">创建具有 Microsoft 365 Defender API 合作伙伴访问权限的应用</span><span class="sxs-lookup"><span data-stu-id="1671c-104">Create an app with partner access to Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1671c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1671c-105">**Applies to:**</span></span>

- <span data-ttu-id="1671c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1671c-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1671c-107">某些信息与预发布产品相关，该产品在商业发行之前可能会进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="1671c-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1671c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="1671c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="1671c-109">此页面介绍如何创建 Azure Active Directory 应用，该应用代表多个租户中的用户以编程方式访问 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="1671c-109">This page describes how to create an Azure Active Directory app that has programmatic access to Microsoft 365 Defender, on behalf of users across multiple tenants.</span></span> <span data-ttu-id="1671c-110">多租户应用可用于为大型用户组服务。</span><span class="sxs-lookup"><span data-stu-id="1671c-110">Multi-tenant apps are useful for serving large groups of users.</span></span>

<span data-ttu-id="1671c-111">如果你需要代表单个用户以编程方式访问 Microsoft 365 Defender，请参阅"创建应用以代表用户访问[Microsoft 365 Defender API"。](api-create-app-user-context.md)</span><span class="sxs-lookup"><span data-stu-id="1671c-111">If you need programmatic access to Microsoft 365 Defender on behalf of a single user, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md).</span></span> <span data-ttu-id="1671c-112">如果需要在没有用户明确定义的 (的情况下访问，例如，如果要编写后台应用或守护程序) ，请参阅"创建应用以在没有用户的情况下访问[Microsoft 365 Defender"。](api-create-app-web.md)</span><span class="sxs-lookup"><span data-stu-id="1671c-112">If you need access without a user explicitly defined (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="1671c-113">如果不确定需要哪种类型的访问，请参阅["入门"。](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="1671c-113">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="1671c-114">Microsoft 365 Defender 通过一组编程 API 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="1671c-114">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="1671c-115">这些 API 可帮助你自动化工作流并充分利用 Microsoft 365 Defender 的功能。</span><span class="sxs-lookup"><span data-stu-id="1671c-115">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="1671c-116">此 API 访问需要 OAuth2.0 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1671c-116">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="1671c-117">有关详细信息，请参阅 [OAuth 2.0 授权代码流](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="1671c-117">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="1671c-118">通常，你需要执行以下步骤才能使用这些 API：</span><span class="sxs-lookup"><span data-stu-id="1671c-118">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="1671c-119">创建 Azure Active Directory (Azure AD) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1671c-119">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="1671c-120">使用此应用程序获取访问令牌。</span><span class="sxs-lookup"><span data-stu-id="1671c-120">Get an access token using this application.</span></span>
- <span data-ttu-id="1671c-121">使用令牌访问 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="1671c-121">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="1671c-122">由于此应用是多租户，你还需要代表其用户从[](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant)每个租户获得管理员同意。</span><span class="sxs-lookup"><span data-stu-id="1671c-122">Since this app is multi-tenant, you'll also need [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) from each tenant on behalf of its users.</span></span>

<span data-ttu-id="1671c-123">本文介绍如何：</span><span class="sxs-lookup"><span data-stu-id="1671c-123">This article explains how to:</span></span>

- <span data-ttu-id="1671c-124">创建 **多租户** Azure AD 应用程序</span><span class="sxs-lookup"><span data-stu-id="1671c-124">Create a **multi-tenant** Azure AD application</span></span>
- <span data-ttu-id="1671c-125">获取应用程序的用户管理员授权，以访问 Microsoft 365 Defender 所需的资源。</span><span class="sxs-lookup"><span data-stu-id="1671c-125">Get authorized consent from your user administrator for your application to access the Microsoft 365 Defender that resources it needs.</span></span>
- <span data-ttu-id="1671c-126">获取 Microsoft 365 Defender 的访问令牌</span><span class="sxs-lookup"><span data-stu-id="1671c-126">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="1671c-127">验证令牌</span><span class="sxs-lookup"><span data-stu-id="1671c-127">Validate the token</span></span>

<span data-ttu-id="1671c-128">Microsoft 365 Defender 通过一组编程 API 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="1671c-128">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="1671c-129">这些 API 将帮助你自动化基于 Microsoft 365 Defender 功能的工作流和进行创新。</span><span class="sxs-lookup"><span data-stu-id="1671c-129">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="1671c-130">API 访问需要 OAuth2.0 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1671c-130">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="1671c-131">有关详细信息，请参阅 [OAuth 2.0 授权代码流](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="1671c-131">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="1671c-132">通常，你需要执行以下步骤才能使用 API：</span><span class="sxs-lookup"><span data-stu-id="1671c-132">In general, you’ll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="1671c-133">创建 **多租户** Azure AD 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1671c-133">Create a **multi-tenant** Azure AD application.</span></span>
- <span data-ttu-id="1671c-134">获取 (同意) 应用程序的用户管理员同意访问所需的 Microsoft 365 Defender 资源。</span><span class="sxs-lookup"><span data-stu-id="1671c-134">Get authorized (consent) by your user administrator for your application to access Microsoft 365 Defender resources it needs.</span></span>
- <span data-ttu-id="1671c-135">使用此应用程序获取访问令牌。</span><span class="sxs-lookup"><span data-stu-id="1671c-135">Get an access token using this application.</span></span>
- <span data-ttu-id="1671c-136">使用令牌访问 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="1671c-136">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="1671c-137">以下步骤将指导你如何创建多租户 Azure AD 应用程序、获取 Microsoft 365 Defender 的访问令牌并验证令牌。</span><span class="sxs-lookup"><span data-stu-id="1671c-137">The following steps with guide you how to create a multi-tenant Azure AD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="1671c-138">创建多租户应用</span><span class="sxs-lookup"><span data-stu-id="1671c-138">Create the multi-tenant app</span></span>

1. <span data-ttu-id="1671c-139">以具有 [全局管理员](https://portal.azure.com)角色的用户 **登录 Azure。**</span><span class="sxs-lookup"><span data-stu-id="1671c-139">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="1671c-140">导航到 **Azure Active Directory**  >  **应用注册**  >  **新注册**。</span><span class="sxs-lookup"><span data-stu-id="1671c-140">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Microsoft Azure 的图像和到应用程序注册的导航](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="1671c-142">在注册表单中：</span><span class="sxs-lookup"><span data-stu-id="1671c-142">In the registration form:</span></span>

   - <span data-ttu-id="1671c-143">为应用程序选择一个名称。</span><span class="sxs-lookup"><span data-stu-id="1671c-143">Choose a name for your application.</span></span>
   - <span data-ttu-id="1671c-144">从 **支持的帐户类型中**，选择任何组织目录中的帐户 **(任何 Azure AD) - 多租户**。</span><span class="sxs-lookup"><span data-stu-id="1671c-144">From **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory) - Multitenant**.</span></span>
   - <span data-ttu-id="1671c-145">填写" **重定向 URI"** 部分。</span><span class="sxs-lookup"><span data-stu-id="1671c-145">Fill out the **Redirect URI** section.</span></span> <span data-ttu-id="1671c-146">选择类型 **Web，** 将重定向 URI 作为 **https://portal.azure.com** 提供。</span><span class="sxs-lookup"><span data-stu-id="1671c-146">Select type **Web** and give the redirect URI as **https://portal.azure.com**.</span></span>

   <span data-ttu-id="1671c-147">填写完表单后，选择"注册 **"。**</span><span class="sxs-lookup"><span data-stu-id="1671c-147">After you're done filling out the form, select **Register**.</span></span>

   ![注册应用程序表单的图像](../..//media/atp-api-new-app-partner.png)

4. <span data-ttu-id="1671c-149">在应用程序页面上，选择 **"API** 权限添加我的组织使用> API，键入 Microsoft 威胁防护，然后选择  >    >  Microsoft **威胁防护**。 </span><span class="sxs-lookup"><span data-stu-id="1671c-149">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="1671c-150">你的应用现在可以访问 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="1671c-150">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="1671c-151">*Microsoft 威胁防护* 是 Microsoft 365 Defender 的以前名称，不会显示在原始列表中。</span><span class="sxs-lookup"><span data-stu-id="1671c-151">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="1671c-152">你需要开始在文本框中写入其名称，以查看其显示。</span><span class="sxs-lookup"><span data-stu-id="1671c-152">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 权限选择的图像](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="1671c-154">选择 **应用程序权限**。</span><span class="sxs-lookup"><span data-stu-id="1671c-154">Select **Application permissions**.</span></span> <span data-ttu-id="1671c-155">选择方案的相关权限，例如 (**Incident.Read.All**) ，然后选择"添加 **权限"。**</span><span class="sxs-lookup"><span data-stu-id="1671c-155">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![API 访问和 API 选择的图像](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="1671c-157">需要为方案选择相关权限。</span><span class="sxs-lookup"><span data-stu-id="1671c-157">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="1671c-158">*读取所有事件* 只是一个示例。</span><span class="sxs-lookup"><span data-stu-id="1671c-158">*Read all incidents* is just an example.</span></span> <span data-ttu-id="1671c-159">若要确定所需的权限，请查看要调用的 API中的"权限"部分。</span><span class="sxs-lookup"><span data-stu-id="1671c-159">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="1671c-160">例如，若要 [运行高级查询](api-advanced-hunting.md)，请选择"运行高级查询"权限;若要 [隔离设备，](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)请选择"隔离计算机"权限。</span><span class="sxs-lookup"><span data-stu-id="1671c-160">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="1671c-161">选择 **"授予管理员同意"。**</span><span class="sxs-lookup"><span data-stu-id="1671c-161">Select **Grant admin consent**.</span></span> <span data-ttu-id="1671c-162">每次添加权限时，都必须选择"授予 **管理员同意** "，它才能生效。</span><span class="sxs-lookup"><span data-stu-id="1671c-162">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![授予权限的图像](../../media/grant-consent.PNG)

7. <span data-ttu-id="1671c-164">若要向应用程序添加密码，请选择"证书&**密码，向** 密码添加说明，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="1671c-164">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="1671c-165">选择"添加 **"** 后， **选择复制生成的密码值**。</span><span class="sxs-lookup"><span data-stu-id="1671c-165">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="1671c-166">离开后将无法检索密码值。</span><span class="sxs-lookup"><span data-stu-id="1671c-166">You won't be able to retrieve the secret value after you leave.</span></span>

    ![创建应用密钥的图像](../../media/webapp-create-key2.png)

8. <span data-ttu-id="1671c-168">将应用程序 ID 和租户 ID 记录在安全位置。</span><span class="sxs-lookup"><span data-stu-id="1671c-168">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="1671c-169">它们列在应用程序 **页上的"** 概述"下。</span><span class="sxs-lookup"><span data-stu-id="1671c-169">They're listed under **Overview** on your application page.</span></span>

   ![已创建应用 ID 的图像](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="1671c-171">将应用程序添加到用户的租户。</span><span class="sxs-lookup"><span data-stu-id="1671c-171">Add the application to your user's tenant.</span></span>

   <span data-ttu-id="1671c-172">由于应用程序代表用户与 Microsoft 365 Defender 进行交互，因此需要针对要使用它的每一个租户批准它。</span><span class="sxs-lookup"><span data-stu-id="1671c-172">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

   <span data-ttu-id="1671c-173">**用户租户** 中的全局管理员需要查看同意链接并批准您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1671c-173">A **Global Administrator** from your user's tenant needs to view the consent link and approve your application.</span></span>

   <span data-ttu-id="1671c-174">同意链接的形式为：</span><span class="sxs-lookup"><span data-stu-id="1671c-174">Consent link is of the form:</span></span>

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   <span data-ttu-id="1671c-175">数字 `00000000-0000-0000-0000-000000000000` 应替换为应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="1671c-175">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>

   <span data-ttu-id="1671c-176">单击同意链接后，使用用户租户的全局管理员登录并许可应用程序。</span><span class="sxs-lookup"><span data-stu-id="1671c-176">After clicking on the consent link, sign in with the Global Administrator of the user's tenant and consent the application.</span></span>

   ![同意图像](../../media/app-consent-partner.png)

   <span data-ttu-id="1671c-178">你还需要向用户询问其租户 ID。</span><span class="sxs-lookup"><span data-stu-id="1671c-178">You'll also need to ask your user for their tenant ID.</span></span> <span data-ttu-id="1671c-179">租户 ID 是用于获取访问令牌的标识符之一。</span><span class="sxs-lookup"><span data-stu-id="1671c-179">The tenant ID is one of the identifiers used to acquire access tokens.</span></span>

- <span data-ttu-id="1671c-180">**完成！**</span><span class="sxs-lookup"><span data-stu-id="1671c-180">**Done!**</span></span> <span data-ttu-id="1671c-181">已成功注册应用程序！</span><span class="sxs-lookup"><span data-stu-id="1671c-181">You've successfully registered an application!</span></span>
- <span data-ttu-id="1671c-182">有关令牌获取和验证，请参阅以下示例。</span><span class="sxs-lookup"><span data-stu-id="1671c-182">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="1671c-183">获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="1671c-183">Get an access token</span></span>

<span data-ttu-id="1671c-184">有关 Azure AD 令牌详细信息，请参阅 [Azure AD 教程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。</span><span class="sxs-lookup"><span data-stu-id="1671c-184">For more information on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1671c-185">虽然本节中的示例鼓励您粘贴密码值以进行测试，但您永远不应将密码硬编码到生产中运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1671c-185">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="1671c-186">第三方可以使用你的密码访问资源。</span><span class="sxs-lookup"><span data-stu-id="1671c-186">A third party could use your secret to access resources.</span></span> <span data-ttu-id="1671c-187">通过使用 Azure 密钥保管库，可帮助保护 [应用密钥的安全](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)。</span><span class="sxs-lookup"><span data-stu-id="1671c-187">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="1671c-188">有关如何保护应用的实际示例，请参阅使用 Azure Key Vault 管理服务器 [应用中的密钥](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="1671c-188">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

> [!TIP]
> <span data-ttu-id="1671c-189">在下面的示例中，使用用户的租户 ID 测试脚本是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="1671c-189">In the following examples, use a user's tenant ID to test that the script is working.</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="1671c-190">使用 PowerShell 获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="1671c-190">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place!

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"

$authBody = [Ordered] @{
    resource = $resourceAppIdUri
    client_id = $clientId
    client_secret = $appSecret
    grant_type = 'client_credentials'
}

$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token

Out-File -FilePath "./Latest-token.txt" -InputObject $token

return $token
```

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="1671c-191">使用 C 获取访问令牌\#</span><span class="sxs-lookup"><span data-stu-id="1671c-191">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="1671c-192">以下代码已使用 Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 进行测试。</span><span class="sxs-lookup"><span data-stu-id="1671c-192">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="1671c-193">创建新的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="1671c-193">Create a new console application.</span></span>
1. <span data-ttu-id="1671c-194">安装 NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。</span><span class="sxs-lookup"><span data-stu-id="1671c-194">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="1671c-195">添加以下行：</span><span class="sxs-lookup"><span data-stu-id="1671c-195">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="1671c-196">将以下代码复制并粘贴到应用中 (请不要忘记更新三个变量 `tenantId` `clientId` `appSecret` ：、、) ：</span><span class="sxs-lookup"><span data-stu-id="1671c-196">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

    ```C#
    string tenantId = ""; // Paste your directory (tenant) ID here
    string clientId = ""; // Paste your application (client) ID here
    string appSecret = ""; // Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(clientId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="1671c-197">使用 Python 获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="1671c-197">Get an access token using Python</span></span>

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="1671c-198">使用令牌获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="1671c-198">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="1671c-199">在 Windows 10 版本 1803 及更高版本上预安装了百度。</span><span class="sxs-lookup"><span data-stu-id="1671c-199">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="1671c-200">对于其他版本的 Windows，请直接从官方网站下载 [并安装该工具](https://curl.haxx.se/windows/)。</span><span class="sxs-lookup"><span data-stu-id="1671c-200">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="1671c-201">打开命令提示符，CLIENT_ID Azure 应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="1671c-201">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="1671c-202">将CLIENT_SECRET Azure 应用程序密码。</span><span class="sxs-lookup"><span data-stu-id="1671c-202">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="1671c-203">将TENANT_ID Azure 租户 ID 设置为想要使用你的应用访问 Microsoft 365 Defender 的用户的 Azure 租户 ID。</span><span class="sxs-lookup"><span data-stu-id="1671c-203">Set TENANT_ID to the Azure tenant ID of the user that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="1671c-204">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1671c-204">Run the following command:</span></span>

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="1671c-205">成功的响应如下所示：</span><span class="sxs-lookup"><span data-stu-id="1671c-205">A successful response will look like this:</span></span>

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="1671c-206">验证令牌</span><span class="sxs-lookup"><span data-stu-id="1671c-206">Validate the token</span></span>

1. <span data-ttu-id="1671c-207">将令牌复制并粘贴到 [JSON Web 令牌验证程序网站 JWT 中](https://jwt.ms) ，以解码它。</span><span class="sxs-lookup"><span data-stu-id="1671c-207">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="1671c-208">确保解码 *令牌中* 的角色声明包含所需的权限。</span><span class="sxs-lookup"><span data-stu-id="1671c-208">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="1671c-209">在下图中，你可以看到从应用获取的已解码令牌，具有 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` 、 和 ```AdvancedHunting.Read.All``` 权限：</span><span class="sxs-lookup"><span data-stu-id="1671c-209">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![令牌验证的图像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="1671c-211">使用令牌访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="1671c-211">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="1671c-212">选择要用于事件或高级搜寻 (API) 。</span><span class="sxs-lookup"><span data-stu-id="1671c-212">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="1671c-213">有关详细信息，请参阅支持的[Microsoft 365 Defender API。](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="1671c-213">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="1671c-214">在即将发送的 http 请求中，将授权标头设置为 `"Bearer" <token>` *，Bearer* 是授权方案，令牌是经过验证的令牌。</span><span class="sxs-lookup"><span data-stu-id="1671c-214">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="1671c-215">令牌将在一小时内过期。</span><span class="sxs-lookup"><span data-stu-id="1671c-215">The token will expire within one hour.</span></span> <span data-ttu-id="1671c-216">在此期间，可以使用同一令牌发送多个请求。</span><span class="sxs-lookup"><span data-stu-id="1671c-216">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="1671c-217">以下示例演示如何发送请求，以使用 **C# 获取事件列表**。</span><span class="sxs-lookup"><span data-stu-id="1671c-217">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="1671c-218">相关文章</span><span class="sxs-lookup"><span data-stu-id="1671c-218">Related articles</span></span>

- [<span data-ttu-id="1671c-219">Microsoft 365 Defender API 概述</span><span class="sxs-lookup"><span data-stu-id="1671c-219">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="1671c-220">访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="1671c-220">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="1671c-221">创建"Hello world"应用程序</span><span class="sxs-lookup"><span data-stu-id="1671c-221">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="1671c-222">创建应用以在没有用户的情况下访问 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1671c-222">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="1671c-223">创建应用以代表用户访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="1671c-223">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="1671c-224">了解 API 限制和许可</span><span class="sxs-lookup"><span data-stu-id="1671c-224">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="1671c-225">了解错误代码</span><span class="sxs-lookup"><span data-stu-id="1671c-225">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="1671c-226">使用 Azure Key Vault 管理服务器应用中的密钥</span><span class="sxs-lookup"><span data-stu-id="1671c-226">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="1671c-227">用户登录和 API 访问的 OAuth 2.0 授权</span><span class="sxs-lookup"><span data-stu-id="1671c-227">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
