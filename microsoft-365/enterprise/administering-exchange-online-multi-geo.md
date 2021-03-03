---
title: 在多地理位置环境中管理 Exchange Online 邮箱
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: 了解如何使用 PowerShell 在 Microsoft 365 环境中管理 Exchange Online 多地理位置设置。
ms.openlocfilehash: 83889b4582d2e305b2cb9f07a64307e85d30be77
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406038"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="1b9a5-103">在多地理位置环境中管理 Exchange Online 邮箱</span><span class="sxs-lookup"><span data-stu-id="1b9a5-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="1b9a5-104">在 Microsoft 365 环境中查看和配置多地理位置属性需要 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="1b9a5-105">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="1b9a5-106">你需要 [Microsoft Azure Active Directory PowerShell 模块](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 或 v1.x 中的更高版本才能查看用户对象的 **PreferredDataLocation** 属性。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="1b9a5-107">无法通过 AAD PowerShell 直接修改通过 AAD Connect 同步到 AAD 中的用户对象的 **PreferredDataLocation** 值。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="1b9a5-108">可以通过 AAD PowerShell 修改仅限云的用户对象。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="1b9a5-109">若要连接到 Azure AD PowerShell，请参阅[连接到 PowerShell](connect-to-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="1b9a5-110">在 Exchange Online 多地理位置环境中，无需执行任何手动步骤将地理位置添加到租户。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-110">In Exchange Online multi-geo environments, you don't need to do any manual steps to add geos to your tenant.</span></span> <span data-ttu-id="1b9a5-111">收到消息中心帖子，显示多地理位置已准备好用于 Exchange Online 后，所有可用的地理位置都可供你使用并配置。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-111">After you receive the Message Center post that says multi-geo is ready for Exchange Online, all available geos will be ready and configured for you to use.</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="1b9a5-112">使用 Exchange Online PowerShell 直接连接到某个地理位置</span><span class="sxs-lookup"><span data-stu-id="1b9a5-112">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="1b9a5-113">通常，Exchange Online PowerShell 将连接到中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-113">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="1b9a5-114">但你也可以直接连接到附属地理位置。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-114">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="1b9a5-115">由于性能有所改进，因此，当你仅管理附属地理位置中的用户时，我们建议直接连接到该位置。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-115">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="1b9a5-116">[安装和维护 EXO V2 模块](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)中介绍了安装和使用 EXO V2 模块的要求。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-116">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="1b9a5-117">若要将 Exchange Online PowerShell 连接到特定地理位置 *，ConnectionUri* 参数不同于常规连接说明。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-117">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="1b9a5-118">命令和值的其余部分是相同的。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-118">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="1b9a5-119">具体来说，需要将值添加到 `?email=<emailaddress>` _ConnectionUri_ 值的末尾。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-119">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="1b9a5-120">`<emailaddress>` 是目标地理位置 **中** 任何邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-120">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="1b9a5-121">您拥有该邮箱的权限或与凭据的关系不是因素;电子邮件地址只是告知 Exchange Online PowerShell 连接位置。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-121">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="1b9a5-122">Microsoft 365 或 Microsoft 365 GCC 客户通常不需要使用 _ConnectionUri_ 参数连接到 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-122">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="1b9a5-123">但是，若要连接到特定地理位置，您需要使用 _ConnectionUri_ 参数，以便可以在 `?email=<emailaddress>` 值中使用它。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-123">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a><span data-ttu-id="1b9a5-124">在 Exchange Online PowerShell 中连接到地理位置</span><span class="sxs-lookup"><span data-stu-id="1b9a5-124">Connect to a geo location in Exchange Online PowerShell</span></span>

<span data-ttu-id="1b9a5-125">以下连接说明适用于已配置或未配置为 MFA (多重身份验证) 。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-125">The following connection instructions work for accounts that are or aren't configured for multi-factor authentication (MFA).</span></span>

1. <span data-ttu-id="1b9a5-126">在 Windows PowerShell 窗口中，通过运行以下命令加载 EXO V2 模块：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-126">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="1b9a5-127">在下面的示例中，admin@contoso.onmicrosoft.com是管理员帐户，而目标地理位置是邮箱olga@contoso.onmicrosoft.com所在的位置。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-127">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. <span data-ttu-id="1b9a5-128">在出现的提示admin@contoso.onmicrosoft.com输入密码。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-128">Enter the password for the admin@contoso.onmicrosoft.com in the prompt that appears.</span></span> <span data-ttu-id="1b9a5-129">如果该帐户配置为 MFA，则还需要输入安全代码。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-129">If the account is configured for MFA, you also need to enter the security code.</span></span>

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="1b9a5-130">查看在 Exchange Online 组织中配置的可用地理位置</span><span class="sxs-lookup"><span data-stu-id="1b9a5-130">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="1b9a5-131">若要在 Microsoft 365 多地理位置中查看配置的地理位置的列表，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-131">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="1b9a5-132">查看 Exchange Online 组织的中心地理位置</span><span class="sxs-lookup"><span data-stu-id="1b9a5-132">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="1b9a5-133">若要查看租户的中心地理位置，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-133">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="1b9a5-134">查找邮箱的地理位置</span><span class="sxs-lookup"><span data-stu-id="1b9a5-134">Find the geo location of a mailbox</span></span>

<span data-ttu-id="1b9a5-135">Exchange Online PowerShell 中的 **Get-Mailbox** cmdlet 显示邮箱的以下多地理位置相关属性：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-135">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="1b9a5-136">**Database**：对地理位置代码对应的数据库名称的前 3 个字母，告知你邮箱当前位于何处。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-136">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="1b9a5-137">对于在线存档邮箱，应使用 **ArchiveDatabase** 属性。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-137">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="1b9a5-138">**MailboxRegion**：指定管理员设置的地理位置代码（从 Azure AD 中的 **PreferredDataLocation** 同步）。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-138">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="1b9a5-139">**MailboxRegionLastUpdateTime**：指明 MailboxRegion 的最后（自动或手动）更新时间。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-139">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="1b9a5-140">若要查看邮箱的这些属性，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-140">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="1b9a5-141">例如，若要查看邮箱 chris@contoso.onmicrosoft.com 的地理位置信息，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-141">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="1b9a5-142">此命令的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-142">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="1b9a5-143">如果数据库名称中的地理位置代码与 **MailboxRegion** 值不匹配，则邮箱将自动放入重定位队列中，并移动到 **MailboxRegion** 值 (Exchange Online 指定的地理位置，以查找这些属性值) 之间的不匹配。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-143">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="1b9a5-144">将现有的仅限云邮箱移动到特定地理位置</span><span class="sxs-lookup"><span data-stu-id="1b9a5-144">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="1b9a5-145">仅限云的用户是未通过 AAD Connect 同步到租户的用户。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-145">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="1b9a5-146">此用户是在 Azure AD 中直接创建的。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-146">This user was created directly in Azure AD.</span></span> <span data-ttu-id="1b9a5-147">使用用于 Windows PowerShell 的 Azure AD 模块中的 **Get-MsolUser** 和 **Set-MsolUser** cmdlet 来查看或指定将在其中存储仅限云的用户邮箱的地理位置。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-147">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="1b9a5-148">若要查看用户的 **PreferredDataLocation** 值，请在 Azure AD PowerShell 中使用此语法：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-148">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="1b9a5-149">例如，若要查看用户 michelle@contoso.onmicrosoft.com 的 **PreferredDataLocation** 值，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-149">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="1b9a5-150">若要修改仅限云的用户对象的 **PreferredDataLocation** 值，请在 Azure AD PowerShell 中使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-150">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="1b9a5-151">例如，若要为用户 michelle@contoso.onmicrosoft.com 将 **PreferredDataLocation** 值设置为欧盟 (EUR) 地理位置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-151">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="1b9a5-152">如前所述，您无法对本地 Active Directory 中的同步用户对象使用此过程。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-152">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="1b9a5-153">你需要在 Active Directory 中更改 **PreferredDataLocation** 值，并使用 AAD Connect 进行同步。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-153">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="1b9a5-154">有关详细信息，请参阅 [Azure Active Directory Connect 同步：为 Microsoft 365 资源配置首选数据位置](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-154">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="1b9a5-155">将邮箱重定位到新的地理位置所花费的时间取决于若干因素：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-155">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="1b9a5-156">邮箱的大小和类型。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-156">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="1b9a5-157">正在移动的邮箱数量。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-157">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="1b9a5-158">移动资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-158">The availability of move resources.</span></span>

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a><span data-ttu-id="1b9a5-159">将非活动邮箱移动到特定地理位置</span><span class="sxs-lookup"><span data-stu-id="1b9a5-159">Move an inactive mailbox to a specific geo</span></span>

<span data-ttu-id="1b9a5-160">不能移动出于合规性目的保留的非活动 (例如，通过更改其 **PreferredDataLocation**) 诉讼保留邮箱）。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-160">You can't move inactive mailboxes that are preserved for compliance purposes (for example, mailboxes on Litigation Hold) by changing their **PreferredDataLocation** value.</span></span> <span data-ttu-id="1b9a5-161">若要将非活动邮箱移动到其他地理位置，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-161">To move an inactive mailbox to a different geo, do the following steps:</span></span>

1. <span data-ttu-id="1b9a5-162">恢复非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-162">Recover the inactive mailbox.</span></span> <span data-ttu-id="1b9a5-163">有关说明，请参阅["恢复非活动邮箱"。](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox)</span><span class="sxs-lookup"><span data-stu-id="1b9a5-163">For instructions, see [Recover an inactive mailbox](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox).</span></span>

2. <span data-ttu-id="1b9a5-164">通过替换邮箱的名称、别名、帐户或电子邮件地址，并运行 Exchange Online PowerShell 中的以下命令，阻止托管文件夹助理处理恢复的 \<MailboxIdentity\> [邮箱](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-164">Prevent the Managed Folder Assistant from processing the recovered mailbox by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. <span data-ttu-id="1b9a5-165">将 **Exchange Online 计划 2** 许可证分配给恢复的邮箱。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-165">Assign an **Exchange Online Plan 2** license to the recovered mailbox.</span></span> <span data-ttu-id="1b9a5-166">需要此步骤才能将邮箱重新置于诉讼保留状态。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-166">This step is required to place the mailbox back on Litigation Hold.</span></span> <span data-ttu-id="1b9a5-167">有关说明，请参阅["向用户分配许可证"。](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="1b9a5-167">For instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

4. <span data-ttu-id="1b9a5-168">配置 **邮箱上的 PreferredDataLocation** 值，如上一节中所述。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-168">Configure the **PreferredDataLocation** value on the mailbox as described in the previous section.</span></span>

5. <span data-ttu-id="1b9a5-169">确认邮箱已移动到新地理位置后，将恢复的邮箱重新置于诉讼保留状态。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-169">After you've confirmed that the mailbox has moved to the new geo location, place the recovered mailbox back on Litigation Hold.</span></span> <span data-ttu-id="1b9a5-170">有关说明，请参阅["将邮箱置于诉讼保留"。](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold)</span><span class="sxs-lookup"><span data-stu-id="1b9a5-170">For instructions, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold).</span></span>

6. <span data-ttu-id="1b9a5-171">验证诉讼保留已就位后，允许托管文件夹助理再次处理邮箱，方法为替换为邮箱的名称、别名、帐户或电子邮件地址，并运行 \<MailboxIdentity\> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)中的以下命令：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-171">After verifying that the Litigation Hold is in place, allow the Managed Folder Assistant to process the mailbox again by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. <span data-ttu-id="1b9a5-172">通过删除与邮箱关联的用户帐户，使邮箱再次变为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-172">Make the mailbox inactive again by removing the user account that's associated with the mailbox.</span></span> <span data-ttu-id="1b9a5-173">有关说明，请参阅["从组织中删除用户"。](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="1b9a5-173">For instructions, see [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).</span></span> <span data-ttu-id="1b9a5-174">此步骤还会发布 Exchange Online 计划 2 许可证以用于其他用途。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-174">This step also releases the Exchange Online Plan 2 license for other uses.</span></span>

<span data-ttu-id="1b9a5-175">**注意**：将非活动邮箱移动到其他地理位置时，可能会影响内容搜索结果或从以前的地理位置搜索邮箱的能力。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-175">**Note**: When you move an inactive mailbox to a different geo location, you might affect content search results or the ability to search the mailbox from the former geo location.</span></span> <span data-ttu-id="1b9a5-176">有关详细信息，请参阅在多地理位置环境中搜索和 [导出内容](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments)。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-176">For more information, see [Searching and exporting content in Multi-Geo environments](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments).</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="1b9a5-177">在特定地理位置中创建新的云邮箱</span><span class="sxs-lookup"><span data-stu-id="1b9a5-177">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="1b9a5-178">若要在特定地理位置中创建新邮箱，你需要执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-178">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="1b9a5-179">配置 **PreferredDataLocation** 值，如前面的"[](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location)将现有仅云邮箱移动到特定地理位置"部分中所述，在Exchange Online 中创建邮箱之前。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-179">Configure the **PreferredDataLocation** value as described in the previous [Move an existing cloud-only mailbox to a specific geo location](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) section *before* you create the mailbox in Exchange Online.</span></span> <span data-ttu-id="1b9a5-180">例如，在分配许可证之前，在用户上配置 **PreferredDataLocation** 值。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-180">For example, configure the **PreferredDataLocation** value on a user before you assign a license.</span></span>

- <span data-ttu-id="1b9a5-181">在设置 **PreferredDataLocation** 值的同时分配许可证。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-181">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="1b9a5-182">若要在特定地理位置中创建新的仅限云许可用户（未通过 AAD Connect 同步），请在 Azure AD PowerShell 中使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-182">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="1b9a5-183">此示例使用下面的值为 Elizabeth Brunner 创建新用户帐户：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-183">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="1b9a5-184">用户主体名称：ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="1b9a5-184">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="1b9a5-185">名字：Elizabeth</span><span class="sxs-lookup"><span data-stu-id="1b9a5-185">First name: Elizabeth</span></span>
- <span data-ttu-id="1b9a5-186">姓氏：Brunner</span><span class="sxs-lookup"><span data-stu-id="1b9a5-186">Last name: Brunner</span></span>
- <span data-ttu-id="1b9a5-187">显示名称：Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="1b9a5-187">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="1b9a5-188">密码： 随机生成，并显示在命令的结果中（因为我们未使用 *Password* 参数）</span><span class="sxs-lookup"><span data-stu-id="1b9a5-188">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="1b9a5-189">许可证：`contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="1b9a5-189">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="1b9a5-190">位置：澳大利亚 (AUS)</span><span class="sxs-lookup"><span data-stu-id="1b9a5-190">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="1b9a5-191">有关创建新用户帐户和在 Azure AD PowerShell 中查找 LicenseAssignment 值的详细信息，请参阅[使用 PowerShell 创建用户帐户](create-user-accounts-with-microsoft-365-powershell.md)和[使用 PowerShell 查看许可证和服务](view-licenses-and-services-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-191">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1b9a5-192">如果使用 Exchange Online PowerShell 启用邮箱并需要在 **PreferredDataLocation** 中所指定的地理位置中直接创建邮箱，你需要直接针对云服务使用诸如 **Enable-Mailbox** 或 **New-Mailbox** 等 Exchange Online cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-192">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="1b9a5-193">如果在本地 Exchange PowerShell 中使用 **Enable-RemoteMailbox** cmdlet，则会在中心地理位置创建邮箱。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-193">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="1b9a5-194">在特定地理位置中载入现有本地邮箱</span><span class="sxs-lookup"><span data-stu-id="1b9a5-194">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="1b9a5-195">你可以使用标准载入工具和流程将邮箱从本地 Exchange 组织迁移到 Exchange Online，这些工具和流程包括 [EAC 中的“迁移”仪表板](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)，以及 Exchange Online PowerShell 中的 [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-195">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="1b9a5-196">第一步是验证用户对象对于要载入的每个邮箱是否存在，并验证是否在 Azure AD 中配置了正确的 **PreferredDataLocation** 值。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-196">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="1b9a5-197">载入工具将考虑 **PreferredDataLocation** 值，并将邮箱直接迁移到指定地理位置。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-197">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="1b9a5-198">或者，你可以使用以下步骤，通过 Exchange Online PowerShell 中 [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet 在特定地理位置中直接载入邮箱。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-198">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="1b9a5-199">验证用户对象对于要载入的每个邮箱是否存在，并且是否在 Azure AD 中将 **PreferredDataLocation** 设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-199">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="1b9a5-200">**PreferredDataLocation** 的值将同步到 Exchange Online 中对应邮件用户对象的 **MailboxRegion** 属性。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-200">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="1b9a5-201">使用本主题前面的连接说明直接连接到特定附属地理位置。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-201">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="1b9a5-202">在 Exchange Online PowerShell 中，通过运行以下命令，将用于执行邮箱迁移的本地管理员凭据存储在一个变量中：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-202">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="1b9a5-203">在 Exchange Online PowerShell 中，创建一个类似于以下示例的新 **New-MoveRequest**：</span><span class="sxs-lookup"><span data-stu-id="1b9a5-203">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="1b9a5-204">为需要从本地 Exchange 迁移到当前连接的附属地理位置的每个邮箱重复步骤 4。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-204">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="1b9a5-205">如果需要将其他邮箱迁移到不同的附属地理位置，请为每个特定位置重复步骤 2-4。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-205">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="1b9a5-206">多地理位置报告</span><span class="sxs-lookup"><span data-stu-id="1b9a5-206">Multi-geo reporting</span></span>

<span data-ttu-id="1b9a5-207">Microsoft 365 管理中心中的“**多地理位置使用情况报告**”按地理位置显示用户计数。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-207">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="1b9a5-208">该报告显示当前月份的用户分布，并提供过去 6 个月的历史数据。</span><span class="sxs-lookup"><span data-stu-id="1b9a5-208">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b9a5-209">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b9a5-209">See also</span></span>

[<span data-ttu-id="1b9a5-210">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1b9a5-210">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
