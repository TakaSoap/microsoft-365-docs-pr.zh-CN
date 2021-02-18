---
title: 设计独立的 SharePoint Online 团队网站
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 设计独立的 SharePoint Online 团队网站，包括确定权限级别、向具有访问组的用户分配权限以及嵌套的 Azure AD 组。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0d53f3b45e3f406dfb0b38bcc910bd34876acb08
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288331"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>设计独立的 SharePoint Online 团队网站

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)


 **摘要：** 逐步完成独立 SharePoint Online 团队网站的设计过程。

本文将介绍创建独立 SharePoint Online 团队网站之前必须做出的关键设计决策。

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>第 1 阶段：确定 SharePoint 组和权限级别

默认情况下，每个 SharePoint Online 团队网站都是通过以下 SharePoint 组创建的：

- \<site name> 成员

- \<site name> 访问者

- \<site name> 所有者

这些组独立于 Microsoft 365 和 Azure Active Directory (AD) 组，是分配网站资源权限的基础。

确定 SharePoint 组的成员可在网站中执行哪些操作的特定权限集是权限级别。 默认情况下，SharePoint Online 团队网站有三个权限级别：编辑、读取和完全控制。 下表显示了 SharePoint 组和分配的权限级别的默认关联：

****

|SharePoint 组|权限级别|
|---|---|
|\<site name> 成员|编辑|
|\<site name> 访问者|读取|
|\<site name> 所有者|完全控制|
|

 **最佳做法：** 您可以创建其他 SharePoint 组和权限级别。 但是，我们建议对独立 SharePoint Online 网站使用默认 SharePoint 组和权限级别。

以下是默认的 SharePoint 组和权限级别。

![SharePoint Online 网站的默认 SharePoint 组和权限级别。](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>第 2 阶段：向具有访问组的用户分配权限

可以通过向 SharePoint 组添加用户帐户或用户帐户为一个成员的 Microsoft 365 或 Azure AD 组来向用户分配权限。 添加后，将直接或间接通过 Microsoft 365 或 Azure AD 组的成员身份为用户帐户分配与 SharePoint 组关联的权限级别。

使用默认 SharePoint 组作为示例：

- 成员 **\<site name> SharePoint** 组的成员（可同时包括用户帐户和组）分配有"编辑 **"** 权限级别

- 为 **\<site name> Visitors** SharePoint 组的成员分配了读取权限级别（可同时包括用户帐户和组）

- SharePoint **\<site name> 组的所有者**（可同时包括用户帐户和组）的成员分配有完全 **控制** 权限级别

 **最佳做法：** 尽管可以通过单个用户帐户管理权限，但我们建议改为使用单个 Azure AD 组（称为访问组）。 这简化了通过访问组成员身份管理权限，而不是管理每个 SharePoint 组的用户帐户列表。

Microsoft 365 的 Azure AD 组不同于 Microsoft 365 组。 Azure AD 组显示在 Microsoft 365 管理中心，其 **类型** 设置为 **"** 安全"，并且没有电子邮件地址。 可以在：

- Active Directory 域服务 (AD DS)

    这些组是在内部部署 AD DS 基础结构中创建并同步到 Microsoft 365 订阅的组。 在 Microsoft 365 管理中心中，这些组的状态为"已 **与 active directory 同步"。**

- Office 365

    这些是已使用 Microsoft 365 管理中心、Azure 门户或 Microsoft PowerShell 创建的组。 在 Microsoft 365 管理中心中，这些组具有 **云****状态**。

 **最佳做法：** 如果使用的是本地 AD DS，并且与 Microsoft 365 订阅同步，则使用 AD DS 执行用户和组管理。

对于独立的 SharePoint Online 团队网站，建议的组结构如下所示：

****

|SharePoint 组|基于 Azure AD 的访问组|权限级别|
|---|---|---|
|\<site name> 成员|\<site name> 成员|编辑|
|\<site name> 访问者|\<site name> 查看者|读取|
|\<site name> 所有者|\<site name> 管理员|完全控制|
|

 **最佳做法：** 虽然可以使用 Microsoft 365 或 Azure AD 组作为 SharePoint 组的成员，但我们建议你使用 Azure AD 组。 Azure AD 组通过 AD DS 或 Microsoft 365 进行管理，可让你更灵活地使用嵌套组分配权限。

下面是配置为使用基于 Azure AD 的访问组的默认 SharePoint 组。

![将访问组用作默认 SharePoint Online 网站组的成员。](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

设计三个访问组时，请记住以下几点：

- 管理员访问组中应该只有几个成员，与 **\<site name>** 管理团队网站的少量 SharePoint Online 管理员相对应。

- 大多数网站成员均在 **\<site name> "** 成员"或"**\<site name> 查看者"** 访问组中。 由于 Members 访问 **\<site name> 组的网站** 成员能够删除或修改网站中的资源，因此请仔细考虑其成员身份。 如果有疑问，将网站成员添加到 **\<site name> 查看者** 访问组。

下面是名为 ProjectX 的隔离网站的 SharePoint 组和访问组的示例。

![对名为 ProjectX 的 SharePoint Online 网站使用访问组的示例。](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a>阶段 3：使用嵌套的 Azure AD 组

对于仅限于少数人员的项目，添加到网站的 SharePoint 组的基于 Azure AD 的单个级别访问组适合大多数方案。 但是，如果你拥有大量人员，并且这些人员已经是已建立 Azure AD 组的成员，则通过使用嵌套组或包含其他组作为成员的组，可以更轻松地分配 SharePoint 权限。

例如，您希望创建独立的 SharePoint Online 团队网站，以在销售、市场营销、工程、法律和支持部门的主管人员以及那些已具有执行用户帐户成员身份的部门之间协作。 不要为新网站成员创建新组，并放入所有单独的行政用户帐户，而是将每个部门的现有执行组放在新组中。

 如果在多个组织之间共享 Microsoft 365 订阅，则组织独立网站的单个级别的组成员身份可能由于用户帐户数量而变得难以管理。 在这种情况下，你可以为包含其组织中组的每个组织使用嵌套的 Azure AD 组来管理权限。

若要使用嵌套的 Azure AD 组，

1. 标识或创建将包含用户帐户的 Azure AD 组，并添加相应的用户帐户作为成员。

2. 创建将包含其他 Azure AD 组的基于 Azure AD 的访问组容器，并添加这些组作为成员。

3. 对于容器访问组的相应访问级别，请标识 SharePoint 组和相应的权限级别。

> [!NOTE]
> 不能使用嵌套的 Microsoft 365 组。

下面是 ProjectX 成员访问组的嵌套 Azure AD 组的示例。

![对 ProjectX 网站的成员访问组使用嵌套访问组的示例。](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

由于研究、工程和项目领导团队中所有的用户帐户都是网站成员，因此将其 Azure AD 组添加到 ProjectX 成员访问组会更容易。

## <a name="next-step"></a>后续步骤

准备好在生产中创建和配置独立网站时，请参阅["部署独立的 SharePoint Online 团队网站"。](deploy-an-isolated-sharepoint-online-team-site.md)

## <a name="see-also"></a>另请参阅

[独立 SharePoint Online 团队网站](isolated-sharepoint-online-team-sites.md)

[管理独立 SharePoint Online 团队网站](manage-an-isolated-sharepoint-online-team-site.md)

[部署独立 SharePoint Online 团队网站](deploy-an-isolated-sharepoint-online-team-site.md)
