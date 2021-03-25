---
title: JAMF 的设备控制策略示例
description: 了解如何使用可以使用 JAMF 的示例使用设备控制策略。
keywords: microsoft， defender， 终结点， atp， mac， 设备， 控件， usb， 可移动， 媒体， jamf
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
ms.openlocfilehash: 8990979024c033d4142b595d6fef94f7b872e7c9
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187671"
---
# <a name="examples-of-device-control-policies-for-jamf"></a><span data-ttu-id="6b7a6-104">JAMF 的设备控制策略示例</span><span class="sxs-lookup"><span data-stu-id="6b7a6-104">Examples of device control policies for JAMF</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6b7a6-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6b7a6-105">**Applies to:**</span></span>
- [<span data-ttu-id="6b7a6-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6b7a6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6b7a6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b7a6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6b7a6-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="6b7a6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6b7a6-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6b7a6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="6b7a6-110">本文档包含您可以为你自己的组织自定义的设备控制策略的示例。</span><span class="sxs-lookup"><span data-stu-id="6b7a6-110">This document contains examples of device control policies that you can customize for your own organization.</span></span> <span data-ttu-id="6b7a6-111">如果你使用 JAMF 管理企业中的设备，则这些示例适用。</span><span class="sxs-lookup"><span data-stu-id="6b7a6-111">These examples are applicable if you are using JAMF to manage devices in your enterprise.</span></span>

## <a name="restrict-access-to-all-removable-media"></a><span data-ttu-id="6b7a6-112">限制访问所有可移动媒体</span><span class="sxs-lookup"><span data-stu-id="6b7a6-112">Restrict access to all removable media</span></span>

<span data-ttu-id="6b7a6-113">以下示例限制访问所有可移动媒体。</span><span class="sxs-lookup"><span data-stu-id="6b7a6-113">The following example restricts access to all removable media.</span></span> <span data-ttu-id="6b7a6-114">请注意 `none` 在策略的顶层应用的权限，这意味着将禁止所有文件操作。</span><span class="sxs-lookup"><span data-stu-id="6b7a6-114">Note the `none` permission that is applied at the top level of the policy, meaning that all file operations will be prohibited.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>none</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="set-all-removable-media-to-be-read-only"></a><span data-ttu-id="6b7a6-115">将所有可移动媒体设置为只读</span><span class="sxs-lookup"><span data-stu-id="6b7a6-115">Set all removable media to be read-only</span></span>

<span data-ttu-id="6b7a6-116">以下示例将所有可移动媒体配置为只读。</span><span class="sxs-lookup"><span data-stu-id="6b7a6-116">The following example configures all removable media to be read-only.</span></span> <span data-ttu-id="6b7a6-117">请注意在策略的顶层应用的权限，这意味着将不允许执行所有 `read` 写入和执行操作。</span><span class="sxs-lookup"><span data-stu-id="6b7a6-117">Note the `read` permission that is applied at the top level of the policy, meaning that all write and execute operations will be disallowed.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="disallow-program-execution-from-removable-media"></a><span data-ttu-id="6b7a6-118">禁止从可移动媒体执行程序</span><span class="sxs-lookup"><span data-stu-id="6b7a6-118">Disallow program execution from removable media</span></span>

<span data-ttu-id="6b7a6-119">以下示例演示如何禁止从可移动媒体执行程序。</span><span class="sxs-lookup"><span data-stu-id="6b7a6-119">The following example shows how program execution from removable media can be disallowed.</span></span> <span data-ttu-id="6b7a6-120">记下 `read` `write` 在策略的顶级应用的 和 权限。</span><span class="sxs-lookup"><span data-stu-id="6b7a6-120">Note the `read` and `write` permissions that are applied at the top level of the policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="restrict-all-devices-from-specific-vendors"></a><span data-ttu-id="6b7a6-121">限制来自特定供应商的所有设备</span><span class="sxs-lookup"><span data-stu-id="6b7a6-121">Restrict all devices from specific vendors</span></span>

<span data-ttu-id="6b7a6-122">以下示例限制来自特定供应商的所有设备， (标识和 `fff0` `4525`) 。</span><span class="sxs-lookup"><span data-stu-id="6b7a6-122">The following example restricts all devices from specific vendors (in this case identified by `fff0` and `4525`).</span></span> <span data-ttu-id="6b7a6-123">所有其他设备将不受限制，因为策略顶级定义的权限列出了所有可能的权限 (读取、写入和执行) 。</span><span class="sxs-lookup"><span data-stu-id="6b7a6-123">All other devices will be unrestricted, since the permission defined at the top level of the policy lists all possible permissions (read, write, and execute).</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string>
                <string>execute</string> 
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>fff0</key> 
                <dict> 
                    <key>permission</key> 
                    <array> 
                        <string>none</string> 
                    </array> 
                </dict> 
                <key>4525</key> 
                <dict> 
                    <key>permission</key> 
                    <array>                         
                        <string>none</string> 
                    </array> 
                </dict> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a><span data-ttu-id="6b7a6-124">限制由供应商 ID、产品 ID 和序列号标识的特定设备</span><span class="sxs-lookup"><span data-stu-id="6b7a6-124">Restrict specific devices identified by vendor ID, product ID, and serial number</span></span>

<span data-ttu-id="6b7a6-125">以下示例限制由供应商 ID、产品 ID 和序列号标识的两个 `fff0` `1000` 特定 `04ZSSMHI2O7WBVOA` 设备 `04ZSSMHI2O7WBVOB` 。</span><span class="sxs-lookup"><span data-stu-id="6b7a6-125">The following example restricts two specific devices, identified by vendor ID `fff0`, product ID `1000`, and serial numbers `04ZSSMHI2O7WBVOA` and `04ZSSMHI2O7WBVOB`.</span></span> <span data-ttu-id="6b7a6-126">在策略的所有其他级别，权限包括所有可能的值 (读取、写入和执行) ，这意味着所有其他设备将不受限制。</span><span class="sxs-lookup"><span data-stu-id="6b7a6-126">At all other levels of the policy the permissions include all possible values (read, write, and execute), meaning that all other devices will be unrestricted.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string>
                <string>execute</string>
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>fff0</key> 
                <dict> 
                    <key>permission</key> 
                    <array> 
                        <string>read</string> 
                        <string>write</string>
                        <string>execute</string> 
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>1000</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>read</string> 
                                <string>write</string>
                                <string>execute</string>
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>04ZSSMHI2O7WBVOA</key> 
                                <array> 
                                  <string>none</string> 
                                </array> 
                                <key>04ZSSMHI2O7WBVOB</key>
                                <array> 
                                  <string>none</string> 
                                </array> 
                            </dict> 
                        </dict> 
                    </dict> 
                </dict>
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

## <a name="related-topics"></a><span data-ttu-id="6b7a6-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="6b7a6-127">Related topics</span></span>

- [<span data-ttu-id="6b7a6-128">macOS 的设备控制概述</span><span class="sxs-lookup"><span data-stu-id="6b7a6-128">Overview of device control for macOS</span></span>](mac-device-control-overview.md)
