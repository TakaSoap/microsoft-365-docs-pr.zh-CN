---
title: 删除设备
description: 从管理中删除Microsoft 托管桌面设备
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893697"
---
# <a name="remove-devices"></a><span data-ttu-id="bee92-103">删除设备</span><span class="sxs-lookup"><span data-stu-id="bee92-103">Remove devices</span></span>

<span data-ttu-id="bee92-104">可以使用管理门户Microsoft 托管桌面管理中删除设备。</span><span class="sxs-lookup"><span data-stu-id="bee92-104">You can remove devices from Microsoft Managed Desktop management by using the Admin portal.</span></span> <span data-ttu-id="bee92-105">此操作是永久性的，但你可以按照注册步骤Microsoft 托管桌面注册[它们。](../get-started/register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="bee92-105">This action is permanent, but you can register them with Microsoft Managed Desktop again by following the [registration steps](../get-started/register-devices-self.md).</span></span>

<span data-ttu-id="bee92-106">删除设备时，将发生以下所有情况：</span><span class="sxs-lookup"><span data-stu-id="bee92-106">When you remove a device, all of the following occur:</span></span>

- <span data-ttu-id="bee92-107">我们将设备从 Autopilot 中删除。</span><span class="sxs-lookup"><span data-stu-id="bee92-107">We remove the device from Autopilot.</span></span>
- <span data-ttu-id="bee92-108">我们将设备从所有"现代工作区"设备组中删除。</span><span class="sxs-lookup"><span data-stu-id="bee92-108">We remove the device from  all "Modern Workplace" device groups.</span></span>
- <span data-ttu-id="bee92-109">我们将设备从管理门户 **的"设备** "边栏选项卡中删除。</span><span class="sxs-lookup"><span data-stu-id="bee92-109">We remove the device from the **Devices** blade in the Admin portal.</span></span>

<span data-ttu-id="bee92-110">删除设备时，还可以选择将其从 Azure AD Azure Active Directory (中删除) Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="bee92-110">When you remove a device, you have the option to also remove it from Azure Active Directory (Azure AD) and Microsoft Intune.</span></span>
 
> [!CAUTION]
> <span data-ttu-id="bee92-111">从 Azure AD 中删除与设备相关的对象Microsoft Intune永久。</span><span class="sxs-lookup"><span data-stu-id="bee92-111">Removing the objects related to a device from Azure AD and Microsoft Intune is permanent.</span></span> <span data-ttu-id="bee92-112">如果删除对象，将无法从 Intune 和 Azure 门户查看或管理设备。</span><span class="sxs-lookup"><span data-stu-id="bee92-112">If you remove the objects, you won't be able to view or manage the devices from the Intune and Azure portals.</span></span> <span data-ttu-id="bee92-113">设备无法访问其公司的公司资源。</span><span class="sxs-lookup"><span data-stu-id="bee92-113">The devices won't be able to access their company's corporate resources.</span></span> <span data-ttu-id="bee92-114">如果设备在删除后尝试登录，公司数据可能会被删除。</span><span class="sxs-lookup"><span data-stu-id="bee92-114">Company data might be deleted from them if the devices try to sign in after they're deleted.</span></span>

1. <span data-ttu-id="bee92-115">在 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)**中，选择** 左侧导航窗格中的"设备"。</span><span class="sxs-lookup"><span data-stu-id="bee92-115">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span>
2. <span data-ttu-id="bee92-116">查找菜单 **Microsoft 托管桌面** 部分 **并选择设备。**</span><span class="sxs-lookup"><span data-stu-id="bee92-116">Look for the **Microsoft Managed Desktop** section of the menu and select **Devices**.</span></span>
3. <span data-ttu-id="bee92-117">在Microsoft 托管桌面设备"工作区中，选择要删除的设备。</span><span class="sxs-lookup"><span data-stu-id="bee92-117">In the Microsoft Managed Desktop Devices workspace, select the devices you want to delete.</span></span>
4. <span data-ttu-id="bee92-118">选择 **"设备** 操作"，然后选择" **删除** 设备"，这将打开一个飞入以删除设备。</span><span class="sxs-lookup"><span data-stu-id="bee92-118">Select **Device actions**, and then select **Delete Device** which opens a fly-in to remove the devices.</span></span>
5. <span data-ttu-id="bee92-119">In the fly-in， review the selected devices and then select **Remove devices**.</span><span class="sxs-lookup"><span data-stu-id="bee92-119">In the fly-in, review the selected devices and then select **Remove devices**.</span></span> <span data-ttu-id="bee92-120">如果要同时删除 Azure AD 和 Intune 对象，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="bee92-120">If you want to also remove the Azure AD and Intune objects at the same time, select the check box.</span></span> <span data-ttu-id="bee92-121">设备删除可能需要几分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="bee92-121">Device removal can take a few minutes to complete.</span></span>

> [!NOTE]
> <span data-ttu-id="bee92-122">你无法删除正等待注册 **状态** 的设备。</span><span class="sxs-lookup"><span data-stu-id="bee92-122">You can't remove devices that are in a **pending** registration state.</span></span>