---
title: Microsoft Defender for Endpoint 设备控制打印机保护
description: Microsoft Defender for Endpoint 设备控制打印机保护会阻止用户通过非公司打印机或未批准的 USB 打印机进行打印。
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 0f089efedef1e4fb6b146692da3f1a630f2bacac
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289687"
---
# <a name="device-control-printer-protection"></a><span data-ttu-id="ed3bc-103">设备控制打印机保护</span><span class="sxs-lookup"><span data-stu-id="ed3bc-103">Device Control Printer Protection</span></span>

<span data-ttu-id="ed3bc-104">Microsoft Defender for Endpoint 设备控制打印机保护会阻止用户通过非公司打印机或未批准的 USB 打印机进行打印。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-104">Microsoft Defender for Endpoint Device Control Printer Protection blocks people from printing via non-corporate printers or non-approved USB printer.</span></span>

## <a name="licensing"></a><span data-ttu-id="ed3bc-105">许可</span><span class="sxs-lookup"><span data-stu-id="ed3bc-105">Licensing</span></span>

<span data-ttu-id="ed3bc-106">在开始使用打印机保护之前，你应该[确认你的Microsoft 365订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-106">Before you get started with Printer Protection, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="ed3bc-107">若要访问和使用打印机保护，您必须具有以下权限：</span><span class="sxs-lookup"><span data-stu-id="ed3bc-107">To access and use Printer Protection, you must have the following:</span></span>

- <span data-ttu-id="ed3bc-108">Microsoft 365 E3/策略部署</span><span class="sxs-lookup"><span data-stu-id="ed3bc-108">Microsoft 365 E3 for functionality/policy deployment</span></span>
- <span data-ttu-id="ed3bc-109">Microsoft 365 E5报告功能</span><span class="sxs-lookup"><span data-stu-id="ed3bc-109">Microsoft 365 E5 for reporting</span></span>

## <a name="permission"></a><span data-ttu-id="ed3bc-110">权限</span><span class="sxs-lookup"><span data-stu-id="ed3bc-110">Permission</span></span>

<span data-ttu-id="ed3bc-111">对于 Intune 中的策略部署，若要通过 OMA-URI 部署策略，帐户必须具有创建、编辑、更新或删除设备配置文件的权限。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-111">For Policy deployment in Intune, to deploy policy via OMA-URI, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="ed3bc-112">可以创建自定义角色或使用具有以下权限的任何内置角色：</span><span class="sxs-lookup"><span data-stu-id="ed3bc-112">You can create custom roles or use any of the built-in roles with these permissions:</span></span>

- <span data-ttu-id="ed3bc-113">策略和配置文件管理器角色。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-113">Policy and profile Manager role.</span></span>
- <span data-ttu-id="ed3bc-114">或为设备配置文件启用创建/编辑/更新/读取/删除/查看报告权限的自定义角色</span><span class="sxs-lookup"><span data-stu-id="ed3bc-114">Or custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="ed3bc-115">或全局管理员</span><span class="sxs-lookup"><span data-stu-id="ed3bc-115">Or Global admin</span></span>

<span data-ttu-id="ed3bc-116">若要查看设备配置报告，该帐户必须具有查看报告权限。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-116">To see device configuration reports, the account must have view reports permissions.</span></span> <span data-ttu-id="ed3bc-117">你可以创建自定义角色或使用具有以下权限的内置角色：</span><span class="sxs-lookup"><span data-stu-id="ed3bc-117">You can create custom roles or use the built-in roles with these permissions:</span></span>

- <span data-ttu-id="ed3bc-118">全局安全管理员</span><span class="sxs-lookup"><span data-stu-id="ed3bc-118">Global security admin</span></span>
- <span data-ttu-id="ed3bc-119">安全管理员</span><span class="sxs-lookup"><span data-stu-id="ed3bc-119">Security admin</span></span>
- <span data-ttu-id="ed3bc-120">安全读取者</span><span class="sxs-lookup"><span data-stu-id="ed3bc-120">Security Reader</span></span>

## <a name="prepare-your-endpoints"></a><span data-ttu-id="ed3bc-121">准备终结点</span><span class="sxs-lookup"><span data-stu-id="ed3bc-121">Prepare your endpoints</span></span>

<span data-ttu-id="ed3bc-122">请确保计划Windows 10打印机保护的设备满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-122">Make sure that the Windows 10 devices that you plan on deploying Printer Protection to meet these requirements.</span></span>

1. <span data-ttu-id="ed3bc-123">加入预览体验计划。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-123">Join the Insider Program.</span></span>

1. <span data-ttu-id="ed3bc-124">已安装以下 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-124">The following Windows Updates are installed.</span></span>
    - <span data-ttu-id="ed3bc-125">For Windows 1809： install Windows Update [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span><span class="sxs-lookup"><span data-stu-id="ed3bc-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span></span>
    - <span data-ttu-id="ed3bc-126">For Windows 1909： install Windows Update [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span><span class="sxs-lookup"><span data-stu-id="ed3bc-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span></span>
    - <span data-ttu-id="ed3bc-127">For Windows 2004 or later</span><span class="sxs-lookup"><span data-stu-id="ed3bc-127">For Windows 2004 or later</span></span>

1. <span data-ttu-id="ed3bc-128">如果计划通过组策略部署策略，设备必须加入 MDATP;如果你计划通过 MEM 部署策略，设备必须加入 Intune。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-128">If you're planning to deploy policy via Group Policy, the device must be MDATP joined; if you're planning to deploy policy via MEM, the device must be Intune joined.</span></span>

## <a name="deploy-device-control-printer-protection-policy"></a><span data-ttu-id="ed3bc-129">部署设备控制打印机保护策略</span><span class="sxs-lookup"><span data-stu-id="ed3bc-129">Deploy Device Control Printer Protection policy</span></span>

<span data-ttu-id="ed3bc-130">可以通过组策略或 Intune 部署策略。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-130">You can deploy the policy via Group Policy or Intune.</span></span>

<br>

****

|<span data-ttu-id="ed3bc-131">Title</span><span class="sxs-lookup"><span data-stu-id="ed3bc-131">Title</span></span>|<span data-ttu-id="ed3bc-132">说明</span><span class="sxs-lookup"><span data-stu-id="ed3bc-132">Description</span></span>|<span data-ttu-id="ed3bc-133">云解决方案提供商支持</span><span class="sxs-lookup"><span data-stu-id="ed3bc-133">CSP Support</span></span> | <span data-ttu-id="ed3bc-134">GPO 支持</span><span class="sxs-lookup"><span data-stu-id="ed3bc-134">GPO Support</span></span> | <span data-ttu-id="ed3bc-135">基于用户的支持</span><span class="sxs-lookup"><span data-stu-id="ed3bc-135">User-based Support</span></span> | <span data-ttu-id="ed3bc-136">基于计算机的支持</span><span class="sxs-lookup"><span data-stu-id="ed3bc-136">Machine-based Support</span></span> |
|---|---|:---:|:---:|:---:|:---:|
|<span data-ttu-id="ed3bc-137">**启用设备控制打印限制**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-137">**Enable Device control Printing Restrictions**</span></span>|<span data-ttu-id="ed3bc-138">阻止用户通过非公司打印机打印</span><span class="sxs-lookup"><span data-stu-id="ed3bc-138">Block people from printing via non-corporate printer</span></span>|<span data-ttu-id="ed3bc-139">是</span><span class="sxs-lookup"><span data-stu-id="ed3bc-139">Yes</span></span>|<span data-ttu-id="ed3bc-140">是</span><span class="sxs-lookup"><span data-stu-id="ed3bc-140">Yes</span></span>|<span data-ttu-id="ed3bc-141">是</span><span class="sxs-lookup"><span data-stu-id="ed3bc-141">Yes</span></span>|<span data-ttu-id="ed3bc-142">是</span><span class="sxs-lookup"><span data-stu-id="ed3bc-142">Yes</span></span>|
|<span data-ttu-id="ed3bc-143">**已批准的 USB 连接打印设备列表**\*</span><span class="sxs-lookup"><span data-stu-id="ed3bc-143">**List of Approved USB-connected print devices**\*</span></span>|<span data-ttu-id="ed3bc-144">允许特定 USB 打印机</span><span class="sxs-lookup"><span data-stu-id="ed3bc-144">Allow specific USB printer</span></span>|<span data-ttu-id="ed3bc-145">是</span><span class="sxs-lookup"><span data-stu-id="ed3bc-145">Yes</span></span>|<span data-ttu-id="ed3bc-146">是</span><span class="sxs-lookup"><span data-stu-id="ed3bc-146">Yes</span></span>|<span data-ttu-id="ed3bc-147">是</span><span class="sxs-lookup"><span data-stu-id="ed3bc-147">Yes</span></span>|<span data-ttu-id="ed3bc-148">是</span><span class="sxs-lookup"><span data-stu-id="ed3bc-148">Yes</span></span>|
|

<span data-ttu-id="ed3bc-149">\* 此策略必须与启用设备控制 **打印限制一同使用**。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-149">\* This policy must be used together with **Enable Device control Printing Restrictions**.</span></span>

## <a name="deploy-policy-via-intune"></a><span data-ttu-id="ed3bc-150">通过 Intune 部署策略</span><span class="sxs-lookup"><span data-stu-id="ed3bc-150">Deploy policy via Intune</span></span>

<span data-ttu-id="ed3bc-151">对于 Intune，当前设备控制打印机保护仅支持 OMA-URI。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-151">For Intune, currently Device Control Printer Protection supports OMA-URI only.</span></span>

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a><span data-ttu-id="ed3bc-152">方案 1：使用 Intune 阻止用户通过任何非公司打印机打印</span><span class="sxs-lookup"><span data-stu-id="ed3bc-152">Scenario 1: Block people from printing via any non-corporate printer using Intune</span></span>

- <span data-ttu-id="ed3bc-153">在计算机上应用策略：</span><span class="sxs-lookup"><span data-stu-id="ed3bc-153">Apply policy over machine:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- <span data-ttu-id="ed3bc-154">对用户应用策略：</span><span class="sxs-lookup"><span data-stu-id="ed3bc-154">Apply policy over user:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

<span data-ttu-id="ed3bc-155">CSP 支持字符串，包含 `<enabled/>` ：</span><span class="sxs-lookup"><span data-stu-id="ed3bc-155">The CSP support string with `<enabled/>`:</span></span>

:::image type="content" source="../../media/customeditrow.png" alt-text="自定义编辑行":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a><span data-ttu-id="ed3bc-157">方案 2：允许使用 Intune 的特定批准的 USB 打印机</span><span class="sxs-lookup"><span data-stu-id="ed3bc-157">Scenario 2: Allow specific approved USB printers using Intune</span></span>

- <span data-ttu-id="ed3bc-158">在计算机上应用策略：</span><span class="sxs-lookup"><span data-stu-id="ed3bc-158">Apply policy over machine:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- <span data-ttu-id="ed3bc-159">对用户应用策略：</span><span class="sxs-lookup"><span data-stu-id="ed3bc-159">Apply policy over user:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

<span data-ttu-id="ed3bc-160">通过"ApprovedUsbPrintDevices"属性批准的 USB 打印机的云解决方案提供商支持字符串，示例 `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">` ：</span><span class="sxs-lookup"><span data-stu-id="ed3bc-160">The CSP support string with approved USB printers via 'ApprovedUsbPrintDevices' property, example `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">`:</span></span>

:::image type="content" source="../../media/editrow.png" alt-text="编辑行":::

## <a name="deploy-policy-via-group-policy"></a><span data-ttu-id="ed3bc-162">通过组策略部署策略</span><span class="sxs-lookup"><span data-stu-id="ed3bc-162">Deploy policy via Group Policy</span></span>

<span data-ttu-id="ed3bc-163">如果设备未加入 Intune，则还可以通过组策略部署策略。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-163">If the device isn't Intune joined, you can also deploy the policy via Group Policy.</span></span>

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a><span data-ttu-id="ed3bc-164">方案 1：使用组策略阻止用户通过任何非公司打印机打印</span><span class="sxs-lookup"><span data-stu-id="ed3bc-164">Scenario 1: Block people from printing via any non-corporate printer using Group Policy</span></span>

- <span data-ttu-id="ed3bc-165">在计算机上应用策略：</span><span class="sxs-lookup"><span data-stu-id="ed3bc-165">Apply policy over machine:</span></span>

  <span data-ttu-id="ed3bc-166">计算机配置 \> 管理模板 \> 打印机：启用设备控制打印限制</span><span class="sxs-lookup"><span data-stu-id="ed3bc-166">Computer Configuration \> Administrative Templates \> Printer: Enable Device control Printing Restrictions</span></span>

- <span data-ttu-id="ed3bc-167">对用户应用策略：</span><span class="sxs-lookup"><span data-stu-id="ed3bc-167">Apply policy over user:</span></span>

  <span data-ttu-id="ed3bc-168">用户配置 \> 管理模板 \> 控制面板 \> 打印机：启用设备控件打印限制</span><span class="sxs-lookup"><span data-stu-id="ed3bc-168">User Configuration \> Administrative Templates \> Control Panel \> Printers: Enable Device control Printing Restrictions</span></span>

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="启用设备打印限制":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a><span data-ttu-id="ed3bc-170">方案 2：允许使用组策略的特定批准的 USB 打印机</span><span class="sxs-lookup"><span data-stu-id="ed3bc-170">Scenario 2: Allow specific approved USB printers using Group Policy</span></span>

- <span data-ttu-id="ed3bc-171">在计算机上应用策略：</span><span class="sxs-lookup"><span data-stu-id="ed3bc-171">Apply policy over machine:</span></span>

  <span data-ttu-id="ed3bc-172">计算机配置 \> 管理模板 \> 打印机：已批准 USB 连接的打印设备列表</span><span class="sxs-lookup"><span data-stu-id="ed3bc-172">Computer Configuration \> Administrative Templates \> Printer:  List of Approved USB-connected print devices</span></span>

- <span data-ttu-id="ed3bc-173">对用户应用策略：</span><span class="sxs-lookup"><span data-stu-id="ed3bc-173">Apply policy over user:</span></span>

  <span data-ttu-id="ed3bc-174">用户配置 \> 管理模板 \> 控制面板 \> 打印机：已批准 USB 连接的打印设备列表</span><span class="sxs-lookup"><span data-stu-id="ed3bc-174">User Configuration \> Administrative Templates \> Control Panel \> Printers: List of Approved USB-connected print devices</span></span>

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="批准的 USB 连接打印设备列表":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a><span data-ttu-id="ed3bc-176">在 Microsoft Defender 终结点门户中查看设备控制打印机保护数据</span><span class="sxs-lookup"><span data-stu-id="ed3bc-176">View Device Control Printer Protection data in Microsoft Defender for Endpoint portal</span></span>

<span data-ttu-id="ed3bc-177">安全[Microsoft 365显示](https://security.microsoft.com)上面的设备控制打印机保护策略阻止的打印。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-177">The [Microsoft 365 security center](https://security.microsoft.com) shows printing blocked by the Device Control Printer Protection policy above.</span></span>

```sql
DeviceEvents

|where ActionType == 'PrintJobBlocked'

| extend parsed=parse_json(AdditionalFields)

| extend PrintedFile=tostring(parsed.JobOrDocumentName)

| extend PrintPortName=tostring(parsed.PortName)

| extend PrinterName=tostring(parsed.PrinterName)

| extend Policy=tostring(parsed.RestrictionReason) 

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields

| order by Timestamp desc
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="高级搜寻":::
