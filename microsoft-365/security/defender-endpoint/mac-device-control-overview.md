---
title: macOS 的设备控件
description: 了解如何在 Mac 上配置 Microsoft Defender for Endpoint 以减少来自可移动存储（如 USB 设备）的威胁。
keywords: microsoft， defender， atp， mac， 设备， 控件， usb， 可移动， 媒体
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 696bc45f7bb66313cc9353e252d76c2e9fd73259
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688677"
---
# <a name="device-control-for-macos"></a><span data-ttu-id="00438-104">macOS 的设备控件</span><span class="sxs-lookup"><span data-stu-id="00438-104">Device control for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="00438-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="00438-105">**Applies to:**</span></span>
- [<span data-ttu-id="00438-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="00438-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="00438-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="00438-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="00438-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="00438-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="00438-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="00438-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="requirements"></a><span data-ttu-id="00438-110">要求</span><span class="sxs-lookup"><span data-stu-id="00438-110">Requirements</span></span>

<span data-ttu-id="00438-111">macOS 的设备控件具有以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="00438-111">Device control for macOS has the following prerequisites:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="00438-112">Microsoft Defender for Endpoint (可以试用) </span><span class="sxs-lookup"><span data-stu-id="00438-112">Microsoft Defender for Endpoint entitlement (can be trial)</span></span>
> - <span data-ttu-id="00438-113">最低操作系统版本：macOS 10.15.4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="00438-113">Minimum OS version: macOS 10.15.4 or higher</span></span>
> - <span data-ttu-id="00438-114">最低产品版本：101.24.59</span><span class="sxs-lookup"><span data-stu-id="00438-114">Minimum product version: 101.24.59</span></span>
> - <span data-ttu-id="00438-115">设备必须使用系统扩展运行 (这是 macOS 11 Big Sur) 。</span><span class="sxs-lookup"><span data-stu-id="00438-115">Your device must be running with system extensions (this is the default on macOS 11 Big Sur).</span></span> 
> 
>   <span data-ttu-id="00438-116">可以通过运行以下命令来检查设备是否正在系统扩展上运行，并验证设备是否正在 `endpoint_security_extension` 打印到控制台：</span><span class="sxs-lookup"><span data-stu-id="00438-116">You can check if your device is running on system extensions by running the following command and verify that it is printing `endpoint_security_extension` to the console:</span></span> 
> 
>   ```bash
>   mdatp health --field real_time_protection_subsystem 
>   ```
> - <span data-ttu-id="00438-117">你的设备必须 (`Beta` Microsoft 自动更新) `InsiderFast` 频道中。</span><span class="sxs-lookup"><span data-stu-id="00438-117">Your device must be in `Beta` (previously called `InsiderFast`) Microsoft AutoUpdate update channel.</span></span> <span data-ttu-id="00438-118">有关详细信息，请参阅在 [Mac](mac-updates.md)上部署 Microsoft Defender for Endpoint 的更新。</span><span class="sxs-lookup"><span data-stu-id="00438-118">For more information, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span>
> 
>   <span data-ttu-id="00438-119">可以使用以下命令检查更新频道：</span><span class="sxs-lookup"><span data-stu-id="00438-119">You can check the update channel using the following command:</span></span> 
> 
>    ```bash
>    mdatp health --field release_ring 
>    ```
>
>    <span data-ttu-id="00438-120">如果上述命令未打印 或 `Beta` `InsiderFast` ，请从终端执行以下命令。</span><span class="sxs-lookup"><span data-stu-id="00438-120">If the above command does not print either `Beta` or `InsiderFast`, execute the following command from the Terminal.</span></span> <span data-ttu-id="00438-121">频道更新将在产品下次启动时生效 (安装下一个产品更新时或设备重启时) 。</span><span class="sxs-lookup"><span data-stu-id="00438-121">The channel update takes effect next time the product starts (when the next product update is installed or when the device is rebooted).</span></span> 
> 
>    ```bash
>    defaults write com.microsoft.autoupdate2 ChannelName -string Beta
>    ```
>
>    <span data-ttu-id="00438-122">或者，如果你使用 JAMF 或 Intune (托管) ，你可以远程配置更新通道。</span><span class="sxs-lookup"><span data-stu-id="00438-122">Alternatively, if you are in a managed environment (JAMF or Intune), you can configure the update channel remotely.</span></span> <span data-ttu-id="00438-123">有关详细信息，请参阅在 [Mac](mac-updates.md)上部署 Microsoft Defender for Endpoint 的更新。</span><span class="sxs-lookup"><span data-stu-id="00438-123">For more information, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span> 

## <a name="device-control-policy"></a><span data-ttu-id="00438-124">设备控制策略</span><span class="sxs-lookup"><span data-stu-id="00438-124">Device control policy</span></span>

<span data-ttu-id="00438-125">若要为 macOS 配置设备控制，必须创建一个策略，描述你想要在组织内部实施的限制。</span><span class="sxs-lookup"><span data-stu-id="00438-125">To configure device control for macOS, you must create a policy that describes the restrictions you want to put in place within your organization.</span></span>

<span data-ttu-id="00438-126">设备控制策略包含在用于配置所有其他产品设置的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="00438-126">The device control policy is included in the configuration profile used to configure all other product settings.</span></span> <span data-ttu-id="00438-127">有关详细信息，请参阅配置 [配置文件结构](mac-preferences.md#configuration-profile-structure)。</span><span class="sxs-lookup"><span data-stu-id="00438-127">For more information, see [Configuration profile structure](mac-preferences.md#configuration-profile-structure).</span></span>

<span data-ttu-id="00438-128">在配置文件中，设备控制策略在下一节中定义：</span><span class="sxs-lookup"><span data-stu-id="00438-128">Within the configuration profile, the device control policy is defined in the following section:</span></span>

|<span data-ttu-id="00438-129">节</span><span class="sxs-lookup"><span data-stu-id="00438-129">Section</span></span>|<span data-ttu-id="00438-130">值</span><span class="sxs-lookup"><span data-stu-id="00438-130">Value</span></span>|
|:---|:---|
| <span data-ttu-id="00438-131">**域**</span><span class="sxs-lookup"><span data-stu-id="00438-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="00438-132">**Key**</span><span class="sxs-lookup"><span data-stu-id="00438-132">**Key**</span></span> | <span data-ttu-id="00438-133">deviceControl</span><span class="sxs-lookup"><span data-stu-id="00438-133">deviceControl</span></span> |
| <span data-ttu-id="00438-134">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="00438-134">**Data type**</span></span> | <span data-ttu-id="00438-135">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="00438-135">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="00438-136">**备注**</span><span class="sxs-lookup"><span data-stu-id="00438-136">**Comments**</span></span> | <span data-ttu-id="00438-137">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="00438-137">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="00438-138">设备控制策略可用于：</span><span class="sxs-lookup"><span data-stu-id="00438-138">The device control policy can be used to:</span></span>

- [<span data-ttu-id="00438-139">自定义由设备控件引发通知的 URL 目标</span><span class="sxs-lookup"><span data-stu-id="00438-139">Customize the URL target for notifications raised by device control</span></span>](#customize-url-target-for-notifications-raised-by-device-control)
- [<span data-ttu-id="00438-140">允许或阻止可移动设备</span><span class="sxs-lookup"><span data-stu-id="00438-140">Allow or block removable devices</span></span>](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a><span data-ttu-id="00438-141">自定义由设备控件引发通知的 URL 目标</span><span class="sxs-lookup"><span data-stu-id="00438-141">Customize URL target for notifications raised by device control</span></span>

<span data-ttu-id="00438-142">例如，如果已就位的设备控制策略在设备上强制执行 (例如，对可移动媒体设备的访问权限受限) ，则向用户显示一条通知。</span><span class="sxs-lookup"><span data-stu-id="00438-142">When the device control policy that you have put in place is enforced on a device (for example, access to a removable media device is restricted), a notification is displayed to the user.</span></span>

![设备控制通知](images/mac-device-control-notification.png)

<span data-ttu-id="00438-144">最终用户单击此通知时，在默认浏览器中打开一个网页。</span><span class="sxs-lookup"><span data-stu-id="00438-144">When end users click this notification, a web page is opened in the default browser.</span></span> <span data-ttu-id="00438-145">您可以配置最终用户单击通知时打开的 URL。</span><span class="sxs-lookup"><span data-stu-id="00438-145">You can configure the URL that is opened when end users click the notification.</span></span>

|<span data-ttu-id="00438-146">节</span><span class="sxs-lookup"><span data-stu-id="00438-146">Section</span></span>|<span data-ttu-id="00438-147">值</span><span class="sxs-lookup"><span data-stu-id="00438-147">Value</span></span>|
|:---|:---|
| <span data-ttu-id="00438-148">**域**</span><span class="sxs-lookup"><span data-stu-id="00438-148">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="00438-149">**Key**</span><span class="sxs-lookup"><span data-stu-id="00438-149">**Key**</span></span> | <span data-ttu-id="00438-150">navigationTarget</span><span class="sxs-lookup"><span data-stu-id="00438-150">navigationTarget</span></span> |
| <span data-ttu-id="00438-151">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="00438-151">**Data type**</span></span> | <span data-ttu-id="00438-152">String</span><span class="sxs-lookup"><span data-stu-id="00438-152">String</span></span> |
| <span data-ttu-id="00438-153">**备注**</span><span class="sxs-lookup"><span data-stu-id="00438-153">**Comments**</span></span> | <span data-ttu-id="00438-154">如果未定义，产品将使用指向说明产品所采取操作的通用页面的默认 URL。</span><span class="sxs-lookup"><span data-stu-id="00438-154">If not defined, the product uses a default URL pointing to a generic page explaining the action taken by the product.</span></span> |

### <a name="allow-or-block-removable-devices"></a><span data-ttu-id="00438-155">允许或阻止可移动设备</span><span class="sxs-lookup"><span data-stu-id="00438-155">Allow or block removable devices</span></span>

<span data-ttu-id="00438-156">设备控制策略的可移动媒体部分用于限制对可移动媒体的访问。</span><span class="sxs-lookup"><span data-stu-id="00438-156">The removable media section of the device control policy is used to restrict access to removable media.</span></span> 

> [!NOTE]
> <span data-ttu-id="00438-157">当前支持以下类型的可移动媒体，并且可包含在策略中：USB 存储设备。</span><span class="sxs-lookup"><span data-stu-id="00438-157">The following types of removable media are currently supported and can be included in the policy: USB storage devices.</span></span>

|<span data-ttu-id="00438-158">节</span><span class="sxs-lookup"><span data-stu-id="00438-158">Section</span></span>|<span data-ttu-id="00438-159">值</span><span class="sxs-lookup"><span data-stu-id="00438-159">Value</span></span>|
|:---|:---|
| <span data-ttu-id="00438-160">**域**</span><span class="sxs-lookup"><span data-stu-id="00438-160">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="00438-161">**Key**</span><span class="sxs-lookup"><span data-stu-id="00438-161">**Key**</span></span> | <span data-ttu-id="00438-162">removableMediaPolicy</span><span class="sxs-lookup"><span data-stu-id="00438-162">removableMediaPolicy</span></span> |
| <span data-ttu-id="00438-163">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="00438-163">**Data type**</span></span> | <span data-ttu-id="00438-164">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="00438-164">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="00438-165">**备注**</span><span class="sxs-lookup"><span data-stu-id="00438-165">**Comments**</span></span> | <span data-ttu-id="00438-166">有关字典内容的说明，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="00438-166">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="00438-167">该策略的这一部分是分层的，允许实现最大灵活性并涵盖各种用例。</span><span class="sxs-lookup"><span data-stu-id="00438-167">This section of the policy is hierarchical, allowing for maximum flexibility and covering a wide range of use cases.</span></span> <span data-ttu-id="00438-168">顶级是供应商，由供应商 ID 标识。</span><span class="sxs-lookup"><span data-stu-id="00438-168">At the top level are vendors, identified by a vendor ID.</span></span> <span data-ttu-id="00438-169">对于每个供应商，都有由产品 ID 标识的产品。</span><span class="sxs-lookup"><span data-stu-id="00438-169">For each vendor, there are products, identified by a product ID.</span></span> <span data-ttu-id="00438-170">最后，对于每个产品，都有表示特定设备的序列号。</span><span class="sxs-lookup"><span data-stu-id="00438-170">Finally, for each product there are serial numbers denoting specific devices.</span></span>

```
|-- policy top level 
    |-- vendor 1 
        |-- product 1 
            |-- serial number 1 
            ...
            |-- serial number N 
        ...
        |-- product N 
    ...
    |-- vendor N
```

<span data-ttu-id="00438-171">若要了解如何查找设备标识符，请参阅查找 [设备标识符](#look-up-device-identifiers)。</span><span class="sxs-lookup"><span data-stu-id="00438-171">For information on how to find the device identifiers, see [Look up device identifiers](#look-up-device-identifiers).</span></span>

<span data-ttu-id="00438-172">策略从最具体的条目到最常规的条目进行评估。</span><span class="sxs-lookup"><span data-stu-id="00438-172">The policy is evaluated from the most specific entry to the most general one.</span></span> <span data-ttu-id="00438-173">这意味着，当插入设备时，产品会尝试在每个可移动媒体设备的策略中查找最具体的匹配项，并应用该级别的权限。</span><span class="sxs-lookup"><span data-stu-id="00438-173">Meaning, when a device is plugged in, the product tries to find the most specific match in the policy for each removable media device and apply the permissions at that level.</span></span> <span data-ttu-id="00438-174">如果没有匹配项，则应用下一个最佳匹配，一切都将应用到顶级指定的权限，当设备不匹配策略中的其他任何条目时，这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="00438-174">If there is no match, then the next best match is applied, all the way to the permission specified at the top level, which is the default when a device does not match any other entry in the policy.</span></span>

#### <a name="policy-enforcement-level"></a><span data-ttu-id="00438-175">策略执行级别</span><span class="sxs-lookup"><span data-stu-id="00438-175">Policy enforcement level</span></span>

<span data-ttu-id="00438-176">在可移动媒体部分下，有一个选项可以设置强制级别，它可以接受下列值之一：</span><span class="sxs-lookup"><span data-stu-id="00438-176">Under the removable media section, there is an option to set the enforcement level, which can take one of the following values:</span></span>

- <span data-ttu-id="00438-177">`audit` - 在此强制级别下，如果对设备的访问权限受到限制，则向用户显示一条通知，但该设备仍可使用。</span><span class="sxs-lookup"><span data-stu-id="00438-177">`audit` - Under this enforcement level, if access to a device is restricted, a notification is displayed to the user, however the device can still be used.</span></span> <span data-ttu-id="00438-178">此强制级别可用于评估策略的有效性。</span><span class="sxs-lookup"><span data-stu-id="00438-178">This enforcement level can be useful to evaluate the effectiveness of a policy.</span></span>
- <span data-ttu-id="00438-179">`block` - 在此强制级别下，用户可以在设备上执行的操作仅限于策略中定义的操作。</span><span class="sxs-lookup"><span data-stu-id="00438-179">`block` - Under this enforcement level, the operations that the user can perform on the device are limited to what is defined in the policy.</span></span> <span data-ttu-id="00438-180">此外，会向用户引发通知。</span><span class="sxs-lookup"><span data-stu-id="00438-180">Furthermore, a notification is raised to the user.</span></span> 

|<span data-ttu-id="00438-181">节</span><span class="sxs-lookup"><span data-stu-id="00438-181">Section</span></span>|<span data-ttu-id="00438-182">值</span><span class="sxs-lookup"><span data-stu-id="00438-182">Value</span></span>|
|:---|:---|
| <span data-ttu-id="00438-183">**域**</span><span class="sxs-lookup"><span data-stu-id="00438-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="00438-184">**Key**</span><span class="sxs-lookup"><span data-stu-id="00438-184">**Key**</span></span> | <span data-ttu-id="00438-185">enforcementLevel</span><span class="sxs-lookup"><span data-stu-id="00438-185">enforcementLevel</span></span> |
| <span data-ttu-id="00438-186">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="00438-186">**Data type**</span></span> | <span data-ttu-id="00438-187">String</span><span class="sxs-lookup"><span data-stu-id="00438-187">String</span></span> |
| <span data-ttu-id="00438-188">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="00438-188">**Possible values**</span></span> | <span data-ttu-id="00438-189">审核 (默认) </span><span class="sxs-lookup"><span data-stu-id="00438-189">audit (default)</span></span> <br/> <span data-ttu-id="00438-190">block</span><span class="sxs-lookup"><span data-stu-id="00438-190">block</span></span> |

#### <a name="default-permission-level"></a><span data-ttu-id="00438-191">默认权限级别</span><span class="sxs-lookup"><span data-stu-id="00438-191">Default permission level</span></span>

<span data-ttu-id="00438-192">在可移动媒体部分的顶部，你可以为与策略中任何其他内容不匹配的设备配置默认权限级别。</span><span class="sxs-lookup"><span data-stu-id="00438-192">At the top level of the removable media section, you can configure the default permission level for devices that do not match anything else in the policy.</span></span>

<span data-ttu-id="00438-193">此设置可以设置为：</span><span class="sxs-lookup"><span data-stu-id="00438-193">This setting can be set to:</span></span>

- <span data-ttu-id="00438-194">`none` - 无法对设备执行任何操作</span><span class="sxs-lookup"><span data-stu-id="00438-194">`none` - No operations can be performed on the device</span></span>
- <span data-ttu-id="00438-195">以下值的组合：</span><span class="sxs-lookup"><span data-stu-id="00438-195">A combination of the following values:</span></span>
    - <span data-ttu-id="00438-196">`read` - 允许对设备执行读取操作</span><span class="sxs-lookup"><span data-stu-id="00438-196">`read` - Read operations are permitted on the device</span></span>
    - <span data-ttu-id="00438-197">`write` - 允许对设备执行写入操作</span><span class="sxs-lookup"><span data-stu-id="00438-197">`write` - Write operations are permitted on the device</span></span>
    - <span data-ttu-id="00438-198">`execute` - 允许对设备执行操作</span><span class="sxs-lookup"><span data-stu-id="00438-198">`execute` - Execute operations are permitted on the device</span></span>

> [!NOTE]
> <span data-ttu-id="00438-199">如果 `none` 权限级别存在 ，则忽略其他 (、 或 `read` `write` `execute`) 权限。</span><span class="sxs-lookup"><span data-stu-id="00438-199">If `none` is present in the permission level, any other permissions (`read`, `write`, or `execute`) will be ignored.</span></span>

> [!NOTE]
> <span data-ttu-id="00438-200">权限 `execute` 仅指执行 Mach-O 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="00438-200">The `execute` permission only refers to execution of Mach-O binaries.</span></span> <span data-ttu-id="00438-201">它不包括脚本或其他类型的有效负载的执行。</span><span class="sxs-lookup"><span data-stu-id="00438-201">It does not include execution of scripts or other types of payloads.</span></span>

|<span data-ttu-id="00438-202">节</span><span class="sxs-lookup"><span data-stu-id="00438-202">Section</span></span>|<span data-ttu-id="00438-203">值</span><span class="sxs-lookup"><span data-stu-id="00438-203">Value</span></span>|
|:---|:---|
| <span data-ttu-id="00438-204">**域**</span><span class="sxs-lookup"><span data-stu-id="00438-204">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="00438-205">**Key**</span><span class="sxs-lookup"><span data-stu-id="00438-205">**Key**</span></span> | <span data-ttu-id="00438-206">permission</span><span class="sxs-lookup"><span data-stu-id="00438-206">permission</span></span> |
| <span data-ttu-id="00438-207">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="00438-207">**Data type**</span></span> | <span data-ttu-id="00438-208">字符串数组</span><span class="sxs-lookup"><span data-stu-id="00438-208">Array of strings</span></span> |
| <span data-ttu-id="00438-209">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="00438-209">**Possible values**</span></span> | <span data-ttu-id="00438-210">无</span><span class="sxs-lookup"><span data-stu-id="00438-210">none</span></span> <br/> <span data-ttu-id="00438-211">阅读</span><span class="sxs-lookup"><span data-stu-id="00438-211">read</span></span> <br/> <span data-ttu-id="00438-212">写入</span><span class="sxs-lookup"><span data-stu-id="00438-212">write</span></span> <br/> <span data-ttu-id="00438-213">execute</span><span class="sxs-lookup"><span data-stu-id="00438-213">execute</span></span> |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a><span data-ttu-id="00438-214">按供应商、产品和序列号限制可移动媒体</span><span class="sxs-lookup"><span data-stu-id="00438-214">Restrict removable media by vendor, product, and serial number</span></span>

<span data-ttu-id="00438-215">如允许 [或阻止可移动](#allow-or-block-removable-devices)设备中所述，USB 设备等可移动媒体可以通过供应商 ID、产品 ID 和序列号进行标识。</span><span class="sxs-lookup"><span data-stu-id="00438-215">As described in [Allow or block removable devices](#allow-or-block-removable-devices), removable media such as USB devices can be identified by the vendor ID, product ID, and serial number.</span></span>

<span data-ttu-id="00438-216">在可移动媒体策略的顶层，可以选择在供应商级别定义更精细的限制。</span><span class="sxs-lookup"><span data-stu-id="00438-216">At the top level of the removable media policy, you can optionally define more granular restrictions at the vendor level.</span></span> 

<span data-ttu-id="00438-217">字典 `vendors` 包含一个或多个条目，其中每个条目由供应商 ID 标识。</span><span class="sxs-lookup"><span data-stu-id="00438-217">The `vendors` dictionary contains one or more entries, with each entry being identified by the vendor ID.</span></span>

|<span data-ttu-id="00438-218">节</span><span class="sxs-lookup"><span data-stu-id="00438-218">Section</span></span>|<span data-ttu-id="00438-219">值</span><span class="sxs-lookup"><span data-stu-id="00438-219">Value</span></span>|
|:---|:---|
| <span data-ttu-id="00438-220">**域**</span><span class="sxs-lookup"><span data-stu-id="00438-220">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="00438-221">**Key**</span><span class="sxs-lookup"><span data-stu-id="00438-221">**Key**</span></span> | <span data-ttu-id="00438-222">供应商</span><span class="sxs-lookup"><span data-stu-id="00438-222">vendors</span></span> |
| <span data-ttu-id="00438-223">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="00438-223">**Data type**</span></span> | <span data-ttu-id="00438-224">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="00438-224">Dictionary (nested preference)</span></span> |

<span data-ttu-id="00438-225">对于每个供应商，你可以为来自该供应商的设备指定所需的权限级别。</span><span class="sxs-lookup"><span data-stu-id="00438-225">For each vendor, you can specify the desired permission level for devices from that vendor.</span></span>

|<span data-ttu-id="00438-226">节</span><span class="sxs-lookup"><span data-stu-id="00438-226">Section</span></span>|<span data-ttu-id="00438-227">值</span><span class="sxs-lookup"><span data-stu-id="00438-227">Value</span></span>|
|:---|:---|
| <span data-ttu-id="00438-228">**域**</span><span class="sxs-lookup"><span data-stu-id="00438-228">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="00438-229">**Key**</span><span class="sxs-lookup"><span data-stu-id="00438-229">**Key**</span></span> | <span data-ttu-id="00438-230">permission</span><span class="sxs-lookup"><span data-stu-id="00438-230">permission</span></span> |
| <span data-ttu-id="00438-231">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="00438-231">**Data type**</span></span> | <span data-ttu-id="00438-232">字符串数组</span><span class="sxs-lookup"><span data-stu-id="00438-232">Array of strings</span></span> |
| <span data-ttu-id="00438-233">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="00438-233">**Possible values**</span></span> | <span data-ttu-id="00438-234">与默认 [权限级别相同](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="00438-234">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="00438-235">此外，还可以选择指定属于已定义更精细权限的供应商的产品集。</span><span class="sxs-lookup"><span data-stu-id="00438-235">Furthermore, you can optionally specify the set of products belonging to that vendor for which more granular permissions are defined.</span></span> <span data-ttu-id="00438-236">字典 `products` 包含一个或多个条目，每个条目由产品 ID 标识。</span><span class="sxs-lookup"><span data-stu-id="00438-236">The `products` dictionary contains one or more entries, with each entry being identified by the product ID.</span></span> 

|<span data-ttu-id="00438-237">节</span><span class="sxs-lookup"><span data-stu-id="00438-237">Section</span></span>|<span data-ttu-id="00438-238">值</span><span class="sxs-lookup"><span data-stu-id="00438-238">Value</span></span>|
|:---|:---|
| <span data-ttu-id="00438-239">**域**</span><span class="sxs-lookup"><span data-stu-id="00438-239">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="00438-240">**Key**</span><span class="sxs-lookup"><span data-stu-id="00438-240">**Key**</span></span> | <span data-ttu-id="00438-241">products</span><span class="sxs-lookup"><span data-stu-id="00438-241">products</span></span> |
| <span data-ttu-id="00438-242">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="00438-242">**Data type**</span></span> | <span data-ttu-id="00438-243">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="00438-243">Dictionary (nested preference)</span></span> |

<span data-ttu-id="00438-244">对于每个产品，您可以为该产品指定所需的权限级别。</span><span class="sxs-lookup"><span data-stu-id="00438-244">For each product, you can specify the desired permission level for that product.</span></span>

|<span data-ttu-id="00438-245">节</span><span class="sxs-lookup"><span data-stu-id="00438-245">Section</span></span>|<span data-ttu-id="00438-246">值</span><span class="sxs-lookup"><span data-stu-id="00438-246">Value</span></span>|
|:---|:---|
| <span data-ttu-id="00438-247">**域**</span><span class="sxs-lookup"><span data-stu-id="00438-247">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="00438-248">**Key**</span><span class="sxs-lookup"><span data-stu-id="00438-248">**Key**</span></span> | <span data-ttu-id="00438-249">permission</span><span class="sxs-lookup"><span data-stu-id="00438-249">permission</span></span> |
| <span data-ttu-id="00438-250">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="00438-250">**Data type**</span></span> | <span data-ttu-id="00438-251">字符串数组</span><span class="sxs-lookup"><span data-stu-id="00438-251">Array of strings</span></span> |
| <span data-ttu-id="00438-252">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="00438-252">**Possible values**</span></span> | <span data-ttu-id="00438-253">与默认 [权限级别相同](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="00438-253">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="00438-254">此外，还可以指定一组可选的序列号，为这些序列号定义更精细的权限。</span><span class="sxs-lookup"><span data-stu-id="00438-254">Furthermore, you can specify an optional set of serial numbers for which more granular permissions are defined.</span></span>

<span data-ttu-id="00438-255">词典 `serialNumbers` 包含一个或多个条目，每个条目由序列号标识。</span><span class="sxs-lookup"><span data-stu-id="00438-255">The `serialNumbers` dictionary contains one or more entries, with each entry being identified by the serial number.</span></span>

|<span data-ttu-id="00438-256">节</span><span class="sxs-lookup"><span data-stu-id="00438-256">Section</span></span>|<span data-ttu-id="00438-257">值</span><span class="sxs-lookup"><span data-stu-id="00438-257">Value</span></span>|
|:---|:---|
| <span data-ttu-id="00438-258">**域**</span><span class="sxs-lookup"><span data-stu-id="00438-258">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="00438-259">**Key**</span><span class="sxs-lookup"><span data-stu-id="00438-259">**Key**</span></span> | <span data-ttu-id="00438-260">serialNumbers</span><span class="sxs-lookup"><span data-stu-id="00438-260">serialNumbers</span></span> |
| <span data-ttu-id="00438-261">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="00438-261">**Data type**</span></span> | <span data-ttu-id="00438-262">字典 (嵌套首选项) </span><span class="sxs-lookup"><span data-stu-id="00438-262">Dictionary (nested preference)</span></span> |

<span data-ttu-id="00438-263">对于每个序列号，您可以指定所需的权限级别。</span><span class="sxs-lookup"><span data-stu-id="00438-263">For each serial number, you can specify the desired permission level.</span></span>

|<span data-ttu-id="00438-264">节</span><span class="sxs-lookup"><span data-stu-id="00438-264">Section</span></span>|<span data-ttu-id="00438-265">值</span><span class="sxs-lookup"><span data-stu-id="00438-265">Value</span></span>|
|:---|:---|
| <span data-ttu-id="00438-266">**域**</span><span class="sxs-lookup"><span data-stu-id="00438-266">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="00438-267">**Key**</span><span class="sxs-lookup"><span data-stu-id="00438-267">**Key**</span></span> | <span data-ttu-id="00438-268">permission</span><span class="sxs-lookup"><span data-stu-id="00438-268">permission</span></span> |
| <span data-ttu-id="00438-269">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="00438-269">**Data type**</span></span> | <span data-ttu-id="00438-270">字符串数组</span><span class="sxs-lookup"><span data-stu-id="00438-270">Array of strings</span></span> |
| <span data-ttu-id="00438-271">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="00438-271">**Possible values**</span></span> | <span data-ttu-id="00438-272">与默认 [权限级别相同](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="00438-272">Same as [Default permission level](#default-permission-level)</span></span> |

#### <a name="example-device-control-policy"></a><span data-ttu-id="00438-273">示例设备控制策略</span><span class="sxs-lookup"><span data-stu-id="00438-273">Example device control policy</span></span>

<span data-ttu-id="00438-274">以下示例演示如何将上述所有概念组合到设备控制策略中。</span><span class="sxs-lookup"><span data-stu-id="00438-274">The following example shows how all of the above concepts can be combined into a device control policy.</span></span> <span data-ttu-id="00438-275">在下面的示例中，请注意可移动媒体策略的层次结构特性。</span><span class="sxs-lookup"><span data-stu-id="00438-275">In the following example, note the hierarchical nature of the removable media policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>navigationTarget</key> 
        <string>[custom URL for notifications]</string> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>[enforcement level]</string> <!-- audit / block --> 
            <key>permission</key> 
            <array> 
                <string>[permission]</string> <!-- none / read / write / execute --> 
                <!-- other permissions -->
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>[vendor id]</key> 
                <dict>
                    <key>permission</key> 
                    <array> 
                        <string>[permission]</string> <!-- none / read / write / execute --> 
                        <!-- other permissions -->
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>[product id]</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>[permission]</string> <!-- none / read / write / execute --> 
                                <!-- other permissions -->
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>[serial-number]</key> 
                                <array> 
                                    <string>[permission]</string> <!-- none / read / write / execute --> 
                                    <!-- other permissions -->
                                </array> 
                                <!-- other serial numbers --> 
                            </dict> 
                        </dict> 
                        <!-- other products --> 
                    </dict> 
                </dict> 
                <!-- other vendors --> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

<span data-ttu-id="00438-276">我们在以下文档中包含了更多设备控制策略示例：</span><span class="sxs-lookup"><span data-stu-id="00438-276">We have included more examples of device control policies in the following documents:</span></span>

- [<span data-ttu-id="00438-277">Intune 的设备控制策略示例</span><span class="sxs-lookup"><span data-stu-id="00438-277">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="00438-278">JAMF 的设备控制策略示例</span><span class="sxs-lookup"><span data-stu-id="00438-278">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a><span data-ttu-id="00438-279">查找设备标识符</span><span class="sxs-lookup"><span data-stu-id="00438-279">Look up device identifiers</span></span>

<span data-ttu-id="00438-280">若要查找 USB 设备的供应商 ID、产品 ID 和序列号，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="00438-280">To find the vendor ID, product ID, and serial number of a USB device:</span></span>

1. <span data-ttu-id="00438-281">登录到 Mac 设备。</span><span class="sxs-lookup"><span data-stu-id="00438-281">Log into a Mac device.</span></span>
1. <span data-ttu-id="00438-282">插入要查找其标识符的 USB 设备。</span><span class="sxs-lookup"><span data-stu-id="00438-282">Plug in the USB device for which you want to look up the identifiers.</span></span>
1. <span data-ttu-id="00438-283">在 macOS 的顶级菜单中，选择"**关于此 Mac"。**</span><span class="sxs-lookup"><span data-stu-id="00438-283">In the top-level menu of macOS, select **About This Mac**.</span></span>

    ![关于此 Mac](images/mac-device-control-lookup-1.png)

1. <span data-ttu-id="00438-285">选择 **"系统报告"。**</span><span class="sxs-lookup"><span data-stu-id="00438-285">Select **System Report**.</span></span>

    ![系统报告](images/mac-device-control-lookup-2.png)

1. <span data-ttu-id="00438-287">从左侧列中，选择 **USB**。</span><span class="sxs-lookup"><span data-stu-id="00438-287">From the left column, select **USB**.</span></span>

    ![所有 USB 设备的视图](images/mac-device-control-lookup-3.png)

1. <span data-ttu-id="00438-289">在 **"USB 设备树**"下，导航到插入的 USB 设备。</span><span class="sxs-lookup"><span data-stu-id="00438-289">Under **USB Device Tree**, navigate to the USB device that you plugged in.</span></span>

    ![USB 设备的详细信息](images/mac-device-control-lookup-4.png)

1. <span data-ttu-id="00438-291">将显示供应商 ID、产品 ID 和序列号。</span><span class="sxs-lookup"><span data-stu-id="00438-291">The vendor ID, product ID, and serial number are displayed.</span></span> <span data-ttu-id="00438-292">将供应商 ID 和产品 ID 添加到可移动媒体策略时，必须仅在 之后添加部件 `0x` 。</span><span class="sxs-lookup"><span data-stu-id="00438-292">When adding the vendor ID and product ID to the removable media policy, you must only add the part after `0x`.</span></span> <span data-ttu-id="00438-293">例如，在下图中，供应商 ID 为 ， `1000` 产品 ID 为 `090c` 。</span><span class="sxs-lookup"><span data-stu-id="00438-293">For example, in the below image, vendor ID is `1000` and product ID is `090c`.</span></span>

#### <a name="discover-usb-devices-in-your-organization"></a><span data-ttu-id="00438-294">发现你的组织的 USB 设备</span><span class="sxs-lookup"><span data-stu-id="00438-294">Discover USB devices in your organization</span></span>

<span data-ttu-id="00438-295">你可以查看源自 Microsoft Defender for Endpoint 高级搜寻中的 USB 设备的装入、卸载和卷更改事件。</span><span class="sxs-lookup"><span data-stu-id="00438-295">You can view mount, unmount, and volume change events originating from USB devices in Microsoft Defender for Endpoint advanced hunting.</span></span> <span data-ttu-id="00438-296">这些事件有助于识别可疑的使用活动或执行内部调查。</span><span class="sxs-lookup"><span data-stu-id="00438-296">These events can be helpful to identify suspicious usage activity or perform internal investigations.</span></span>

```
DeviceEvents 
    | where ActionType == "UsbDriveMount" or ActionType == "UsbDriveUnmount" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a><span data-ttu-id="00438-297">设备控制策略部署</span><span class="sxs-lookup"><span data-stu-id="00438-297">Device control policy deployment</span></span>

<span data-ttu-id="00438-298">设备控制策略必须包含在其他产品设置旁边，如在 macOS 上设置 [Microsoft Defender for Endpoint 的首选项中所述](mac-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="00438-298">The device control policy must be included next to the other product settings, as described in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="00438-299">可以使用配置文件部署 中列出的说明部署 [此配置文件](mac-preferences.md#configuration-profile-deployment)。</span><span class="sxs-lookup"><span data-stu-id="00438-299">This profile can be deployed using the instructions listed in [Configuration profile deployment](mac-preferences.md#configuration-profile-deployment).</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="00438-300">疑难解答提示</span><span class="sxs-lookup"><span data-stu-id="00438-300">Troubleshooting tips</span></span>

<span data-ttu-id="00438-301">在通过 Intune 或 JAMF 推送配置文件后，可以通过从终端运行以下命令来检查产品是否成功选取配置文件：</span><span class="sxs-lookup"><span data-stu-id="00438-301">After pushing the configuration profile through Intune or JAMF, you can check if it was successfully picked up by the product by running the following command from the Terminal:</span></span>

```bash
mdatp device-control removable-media policy list
```

<span data-ttu-id="00438-302">此命令将输出到产品使用的设备控制策略的标准输出。</span><span class="sxs-lookup"><span data-stu-id="00438-302">This command will print to standard output the device control policy that the product is using.</span></span> <span data-ttu-id="00438-303">如果打印，请确保 (配置文件) 配置文件确实已从管理控制台推送到设备， (b) 它是一个有效的设备控制策略，如本文档中所述。 `Policy is empty`</span><span class="sxs-lookup"><span data-stu-id="00438-303">In case this prints `Policy is empty`, make sure that (a) the configuration profile has indeed been pushed to your device from the management console, and (b) it is a valid device control policy, as described in this document.</span></span>

<span data-ttu-id="00438-304">在策略已成功传递且插入了一个或多个设备的设备上，可以运行以下命令列出所有设备以及应用于它们的有效权限。</span><span class="sxs-lookup"><span data-stu-id="00438-304">On a device where the policy has been delivered successfully and where there are one or more devices plugged in, you can run the following command to list all devices and the effective permissions applied to them.</span></span>

```bash
mdatp device-control removable-media devices list
```

<span data-ttu-id="00438-305">输出示例：</span><span class="sxs-lookup"><span data-stu-id="00438-305">Example of output:</span></span>

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

<span data-ttu-id="00438-306">在以上示例中，根据已传递到设备的设备控制策略，只有一个插入的可移动媒体设备，并且具有 `read` `execute` 和 权限。</span><span class="sxs-lookup"><span data-stu-id="00438-306">In the above example, there is only one removable media device plugged in and it has `read` and `execute` permissions, according to the device control policy that was delivered to the device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="00438-307">相关主题</span><span class="sxs-lookup"><span data-stu-id="00438-307">Related topics</span></span>

- [<span data-ttu-id="00438-308">Intune 的设备控制策略示例</span><span class="sxs-lookup"><span data-stu-id="00438-308">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="00438-309">JAMF 的设备控制策略示例</span><span class="sxs-lookup"><span data-stu-id="00438-309">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)
