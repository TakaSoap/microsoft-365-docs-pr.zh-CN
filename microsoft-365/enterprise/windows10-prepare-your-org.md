---
title: 准备您的组织 Windows 10 Enterprise
description: 在 Microsoft 365 Enterprise 的一部分部署 Pc 上的 Windows 10 Enterprise 所需的步骤提供高级指导。
keywords: Microsoft 365 Microsoft 365 企业版，Microsoft 365 文档，Windows 10 企业部署
author: JoeDavies-MSFT
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: josephd
ms.openlocfilehash: 21a4198c688e1865a029f18ff3ceeb2155d419e4
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865933"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a><span data-ttu-id="b9d61-104">步骤 1： 准备您的组织 Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b9d61-104">Step 1: Prepare your organization for Windows 10 Enterprise</span></span>

<span data-ttu-id="b9d61-105">*本文适用于 Microsoft 365 企业版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="b9d61-105">*This article applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="b9d61-106">之前升级到 Windows 10 Enterprise 设备，请考虑以下方面：</span><span class="sxs-lookup"><span data-stu-id="b9d61-106">Before upgrading your devices to Windows 10 Enterprise, consider the following:</span></span>

- <span data-ttu-id="b9d61-107">**必须添加并验证您的域**</span><span class="sxs-lookup"><span data-stu-id="b9d61-107">**Your domains must be added and verified**</span></span> <br><span data-ttu-id="b9d61-p101">使用 Microsoft 365 订阅，您可以获取结束 onmicrosoft.com (例如，contoso.onmicrosoft.com) 在默认域的名称。大多数组织都喜欢使用一个或多个他们所拥有以便其电子邮件地址结尾自己的域名 （如 username@contoso.com) 中的域。若要使用您自己的域，您需要将其添加到 Microsoft 365 并确认您拥有。我们建议您将添加并立即验证您的域，以便它们准备好转每当您安装了 Microsoft 365 服务，如电子邮件和 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="b9d61-p101"> With a Microsoft 365 subscription, you get a default domain name that ends in onmicrosoft.com (for example, contoso.onmicrosoft.com). Most organizations prefer to use one or more of the domains they own so their email addresses end in their own domain name (like username@contoso.com). To use your own domain, you need to add it to Microsoft 365 and verify that you own it. We recommend that you add and verify your domains now so they're ready to go whenever you set up Microsoft 365 services, like email and Skype for Business.</span></span>
- <span data-ttu-id="b9d61-112">**您无需在这里添加用户**</span><span class="sxs-lookup"><span data-stu-id="b9d61-112">**You don't need to add users at this time**</span></span> <br><span data-ttu-id="b9d61-p102">若要使用 Microsoft 365 服务或安装 Microsoft 365 产品，用户需要 Microsoft 365 中的帐户和所需产品许可证。如何将用户添加到 Microsoft 365 取决于用户和当前具有 Active Directory 本地是否的数量。如果您没有 Active Directory （或具有 Active Directory 但不希望同步到 Microsoft 365），您可以直接向 Microsoft 365 添加用户并单独或批量分配许可证。</span><span class="sxs-lookup"><span data-stu-id="b9d61-p102"> To use Microsoft 365 services or install Microsoft 365 products, users need accounts in Microsoft 365 and they need product licenses. How you add users to Microsoft 365 depends on the number of users and whether you currently have Active Directory on-premises. If you don’t have Active Directory (or you have Active Directory but don’t want to synchronize it to Microsoft 365), you can add users directly to Microsoft 365 and assign licenses, either individually or in bulk. </span></span><br><span data-ttu-id="b9d61-p103">如果您有 Active Directory 部署，您可以[将其与 Microsoft 365 同步](identity-azure-ad-connect-health.md)在 Azure AD，由 Microsoft 365 云目录中创建用户帐户。使用此方法时，您可以创建用于管理 （如 SharePoint Online 网站集或文档） 的资源的权限的帐户的用户和安全组。将您的 Active Directory 与 Microsoft 365 同步时，不会将许可证分配给用户。</span><span class="sxs-lookup"><span data-stu-id="b9d61-p103"> If you have Active Directory on-premises, you can [sync it with Microsoft 365](identity-azure-ad-connect-health.md) to create user accounts in Azure AD, the cloud directory used by Microsoft 365. With this method, you can create accounts for users and for security groups you use to manage permissions to resources (like SharePoint Online site collections or documents). Synchronizing your Active Directory with Microsoft 365 won’t assign licenses to the users.</span></span>
- <span data-ttu-id="b9d61-119">**此时您无需对许可用户**</span><span class="sxs-lookup"><span data-stu-id="b9d61-119">**You don't need to license users at this time**</span></span> <br><span data-ttu-id="b9d61-p104">用户可以使用 Microsoft 365 服务或从 Microsoft 365 门户安装软件之前，需产品许可证。作为全局或用户管理管理员，您可以单独或批量直接分配 Microsoft 365 中的产品许可证。您可以使用[基于组的授权](identity-group-based-licensing.md)用户添加到特定组时自动分配许可证。</span><span class="sxs-lookup"><span data-stu-id="b9d61-p104"> Before users can use Microsoft 365 services or install software from the Microsoft 365 portal, they need product licenses. As a global or user management admin, you can directly assign products licenses in Microsoft 365 either individually or in bulk. You can also use [group-based licensing](identity-group-based-licensing.md) to automatically assign licenses when users are added to a particular group.</span></span> 
- <span data-ttu-id="b9d61-123">**您单独安装 Office 365 ProPlus**</span><span class="sxs-lookup"><span data-stu-id="b9d61-123">**You install Office 365 ProPlus separately**</span></span> <br><span data-ttu-id="b9d61-p105">获取 Microsoft 365 许可证不自动安装 Office 365 ProPlus 客户端计算机上。请参阅[第 4 阶段： Office 365 ProPlus](office365proplus-infrastructure.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b9d61-p105"> Obtaining a Microsoft 365 license does not automatically install Office 365 ProPlus on your client computers. See [Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md) for more information.</span></span> 

## <a name="set-windows-diagnostics-data-level"></a><span data-ttu-id="b9d61-126">设置 Windows 诊断数据级别</span><span class="sxs-lookup"><span data-stu-id="b9d61-126">Set Windows diagnostics data level</span></span>

<span data-ttu-id="b9d61-p106">Microsoft 使用诊断数据来帮助保持的 Windows 设备安全通过识别恶意软件趋势和其他威胁和帮助我们改善 Windows 和 Microsoft 服务的质量。您必须确保最低级别的基本您的组织中的所有终结点上启用诊断服务。*默认情况下，此服务并将其设置为增强型级别。* 但是，最好以检查，并确保它们接收传感器数据。设置通过策略级别将覆盖设备级设置。</span><span class="sxs-lookup"><span data-stu-id="b9d61-p106">Microsoft uses diagnostic data to help keep Windows devices secure by identifying malware trends and other threats and to help us improve the quality of Windows and Microsoft services. You must ensure that the diagnostics service is enabled at a minimum level of Basic on all endpoints in your organization. *By default, this service is enabled and set to the Enhanced level.* However, it’s good practice to check and ensure that they are receiving sensor data. Setting levels through policies overrides device-level settings.</span></span> 

<span data-ttu-id="b9d61-132">**Windows 10 操作系统诊断数据级别**</span><span class="sxs-lookup"><span data-stu-id="b9d61-132">**Windows 10 operating system diagnostic data levels**</span></span>

<span data-ttu-id="b9d61-p107">您可以配置操作系统诊断数据设置使用您已使用，如组策略、 MDM，或 Windows 设置的管理工具。您可以手动更改设置使用注册表编辑器。设置您的诊断数据级别通过管理策略将覆盖任何设备级别的设置。</span><span class="sxs-lookup"><span data-stu-id="b9d61-p107">You can configure your operating system diagnostic data settings using the management tools you’re already using, such as Group Policy, MDM, or Windows Provisioning. You can also manually change your settings using Registry Editor. Setting your diagnostic data levels through a management policy overrides any device level settings.</span></span>

<span data-ttu-id="b9d61-136">当您配置的管理策略下表中使用适当的值。</span><span class="sxs-lookup"><span data-stu-id="b9d61-136">Use the appropriate value in the table below when you configure the management policy.</span></span>

| <span data-ttu-id="b9d61-137">级别</span><span class="sxs-lookup"><span data-stu-id="b9d61-137">Level</span></span> | <span data-ttu-id="b9d61-138">数据收集</span><span class="sxs-lookup"><span data-stu-id="b9d61-138">Data gathered</span></span> | <span data-ttu-id="b9d61-139">值</span><span class="sxs-lookup"><span data-stu-id="b9d61-139">Value</span></span> |
|:--- |:--- |:--- |
| <span data-ttu-id="b9d61-140">安全性</span><span class="sxs-lookup"><span data-stu-id="b9d61-140">Security</span></span> | <span data-ttu-id="b9d61-141">仅安全数据。</span><span class="sxs-lookup"><span data-stu-id="b9d61-141">Security data only.</span></span> | <span data-ttu-id="b9d61-142">0</span><span class="sxs-lookup"><span data-stu-id="b9d61-142">0</span></span> |
| <span data-ttu-id="b9d61-143">Basic</span><span class="sxs-lookup"><span data-stu-id="b9d61-143">Basic</span></span> | <span data-ttu-id="b9d61-144">安全数据基本系统和质量数据。</span><span class="sxs-lookup"><span data-stu-id="b9d61-144">Security data, and basic system and quality data.</span></span> | <span data-ttu-id="b9d61-145">1 </span><span class="sxs-lookup"><span data-stu-id="b9d61-145">1</span></span> |
| <span data-ttu-id="b9d61-146">增强</span><span class="sxs-lookup"><span data-stu-id="b9d61-146">Enhanced</span></span> | <span data-ttu-id="b9d61-147">安全数据、 基本系统和质量数据和增强的见解和高级的可靠性数据。</span><span class="sxs-lookup"><span data-stu-id="b9d61-147">Security data, basic system and quality data, and enhanced insights and advanced reliability data.</span></span> | <span data-ttu-id="b9d61-148">2 </span><span class="sxs-lookup"><span data-stu-id="b9d61-148">2</span></span> |
| <span data-ttu-id="b9d61-149">完整</span><span class="sxs-lookup"><span data-stu-id="b9d61-149">Full</span></span> | <span data-ttu-id="b9d61-150">安全数据、 基本系统和质量数据、 增强的见解和高级的可靠性数据和完整的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="b9d61-150">Security data, basic system and quality data, enhanced insights and advanced reliability data, and full diagnostics data.</span></span> | <span data-ttu-id="b9d61-151">3 </span><span class="sxs-lookup"><span data-stu-id="b9d61-151">3</span></span> |

<span data-ttu-id="b9d61-152">您可以通过这些方法启用诊断数据：</span><span class="sxs-lookup"><span data-stu-id="b9d61-152">You can enable diagnostics data through any of these methods:</span></span>

* <span data-ttu-id="b9d61-p108">**Microsoft Intune** -如果您打算使用 Intune 管理您的设备，您可以创建配置策略，以通过配置<a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a>系统策略来启用诊断数据。配置策略设置的详细信息，请参阅[管理设置和您与 Microsoft Intune 策略的设备上的功能](https://aka.ms/intuneconfigpolicies)。</span><span class="sxs-lookup"><span data-stu-id="b9d61-p108">**Microsoft Intune** - If you plan to use Intune to manage your devices, you can create a configuration policy to enable diagnostic data by configuring the <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> system policy. For more info on setting up configuration policies, see [Manage settings and features on your devices with Microsoft Intune policies](https://aka.ms/intuneconfigpolicies).</span></span>
* <span data-ttu-id="b9d61-p109">**注册表编辑器**-您可以使用注册表编辑器手动启用您的组织中的每个设备上的诊断数据。另外，您可以编写脚本以编辑注册表。如果管理策略已存在，如组策略或 MDM，它将覆盖此注册表设置。</span><span class="sxs-lookup"><span data-stu-id="b9d61-p109">**Registry Editor** - You can use the Registry Editor to manually enable diagnostic data on each device in your organization. Alternately, you can write a script to edit the registry. If a management policy already exists, such as Group Policy or MDM, it will override this registry setting.</span></span>
* <span data-ttu-id="b9d61-158">**组策略**-如果您不打算注册 Intune 中的设备，可以使用组策略对象，设置您的组织的诊断数据级别。</span><span class="sxs-lookup"><span data-stu-id="b9d61-158">**Group Policy** - If you do not plan to enroll devices in Intune, you can use a Group Policy object to set your organization’s diagnostic data level.</span></span>
* <span data-ttu-id="b9d61-p110">**命令提示符处**-您可以设置 Windows 10 诊断数据和服务自动启动命令提示符下使用。如果您要测试仅几个设备上的服务最佳此方法。启用服务为自动启动，使用此命令将不配置的诊断数据级别。如果您未配置使用管理工具的诊断数据级别，则服务增强级别都将使用默认操作。</span><span class="sxs-lookup"><span data-stu-id="b9d61-p110">**Command prompt** - You can set Windows 10 diagnostics data and service to automatically start with the command prompt. This method is best if you are testing the service on only a few devices. Enabling the service to start automatically with this command will not configure the diagnostic data level. If you have not configured a diagnostic data level using management tools, the service will operate with the default Enhanced level.</span></span>

<span data-ttu-id="b9d61-163">请参阅[您的组织中配置 Windows 诊断数据](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization)以了解更多有关 Windows 诊断数据和如何启用它根据您选择的方法。</span><span class="sxs-lookup"><span data-stu-id="b9d61-163">See [Configure Windows diagnostic data in your organization](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) to learn more about Windows diagnostic data and how you can enable it based on the method that you choose.</span></span>

<span data-ttu-id="b9d61-164">作为临时检查点，请查看对应于此步骤的[退出条件](windows10-exit-criteria.md#crit-windows10-step1)。</span><span class="sxs-lookup"><span data-stu-id="b9d61-164">As an interim checkpoint, you can see the [exit criteria](windows10-exit-criteria.md#crit-windows10-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="b9d61-165">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b9d61-165">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="b9d61-166">为就地升级的现有设备部署 Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b9d61-166">Deploy Windows 10 Enterprise for existing devices as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) |






