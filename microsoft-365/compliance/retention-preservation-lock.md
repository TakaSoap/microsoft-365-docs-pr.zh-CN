---
title: 使用保留锁定来限制对保留策略和保留标签策略的更改
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 使用带有保留策略和保留标签策略的保存锁来帮助满足监管要求，并防范恶意管理员。
ms.openlocfilehash: 6f6cfc5bef9b93af08fcc9b703b29facb9a7c576
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920690"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a><span data-ttu-id="4e5e5-103">使用保留锁定来限制对保留策略和保留标签策略的更改</span><span class="sxs-lookup"><span data-stu-id="4e5e5-103">Use Preservation Lock to restrict changes to retention policies and retention label policies</span></span>

><span data-ttu-id="4e5e5-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="4e5e5-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="4e5e5-105">保存锁可锁定保留策略或保留标签策略，因此任何人 - 包括全局管理员 - 都无法关闭该策略、删除该策略或降低其限制性。</span><span class="sxs-lookup"><span data-stu-id="4e5e5-105">Preservation Lock locks a retention policy or retention label policy so that no one—including a global admin—can turn off the policy, delete the policy, or make it less restrictive.</span></span> <span data-ttu-id="4e5e5-106">这种配置可能是监管要求所需要的，并且有助于防范恶意管理员。</span><span class="sxs-lookup"><span data-stu-id="4e5e5-106">This configuration might be needed for regulatory requirements and can help safeguard against rogue administrators.</span></span>

<span data-ttu-id="4e5e5-107">当锁定保留政策时：</span><span class="sxs-lookup"><span data-stu-id="4e5e5-107">When a policy for retention is locked:</span></span>

- <span data-ttu-id="4e5e5-108">任何人都无法关闭它</span><span class="sxs-lookup"><span data-stu-id="4e5e5-108">No one can turn it off</span></span>
- <span data-ttu-id="4e5e5-109">可以添加位置，但不能删除位置</span><span class="sxs-lookup"><span data-stu-id="4e5e5-109">Locations can be added but not removed</span></span>
- <span data-ttu-id="4e5e5-110">可以延长保留期，但不能缩短保留期</span><span class="sxs-lookup"><span data-stu-id="4e5e5-110">You can extend a retention period but not decrease it</span></span>

<span data-ttu-id="4e5e5-111">总之，锁定的策略可以增加或延长，但不能减少或关闭。</span><span class="sxs-lookup"><span data-stu-id="4e5e5-111">In summary, a locked policy can be increased or extended, but it can't be reduced or turned off.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4e5e5-112">在锁定保留策略或保留标签策略之前，请了解其影响并确认其是否是你的组织所需要的。</span><span class="sxs-lookup"><span data-stu-id="4e5e5-112">Before you lock a retention policy or retention label policy, it's critical that you understand the impact and confirm whether it's required for your organization.</span></span> <span data-ttu-id="4e5e5-113">例如，可能需要满足监管要求。</span><span class="sxs-lookup"><span data-stu-id="4e5e5-113">For example, it might be needed to meet regulatory requirements.</span></span> <span data-ttu-id="4e5e5-114">当应用了保留锁后，管理员将无法禁用或删除这些策略。</span><span class="sxs-lookup"><span data-stu-id="4e5e5-114">Administrators won't be able to disable or delete these policies after the preservation lock is applied.</span></span>

<span data-ttu-id="4e5e5-115">当你创建了一个 [保留策略](create-retention-policies.md)，或是 [发布](create-apply-retention-labels.md) 或 [自动应用](apply-retention-labels-automatically.md)的保留标签策略后，将配置保留锁。</span><span class="sxs-lookup"><span data-stu-id="4e5e5-115">Configure Preservation Lock after you've created a [retention policy](create-retention-policies.md), or a retention label policy that you [publish](create-apply-retention-labels.md) or [auto-apply](apply-retention-labels-automatically.md).</span></span> 

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a><span data-ttu-id="4e5e5-116">如何锁定保留策略或保留标签策略</span><span class="sxs-lookup"><span data-stu-id="4e5e5-116">How to lock a retention policy or retention label policy</span></span>

<span data-ttu-id="4e5e5-117">如果需要使用保存锁，则必须使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4e5e5-117">You must use PowerShell if you need to use Preservation Lock.</span></span> <span data-ttu-id="4e5e5-118">由于管理员在应用此锁后，无法禁用或删除保留策略，因此在 UI 中无法启用此功能，以防止意外配置。</span><span class="sxs-lookup"><span data-stu-id="4e5e5-118">Because administrators can't disable or delete a policy for retention after this lock is applied, enabling this feature is not available in the UI to safeguard against accidental configuration.</span></span>

<span data-ttu-id="4e5e5-119">所有保留策略及任何配置都支持保留锁。</span><span class="sxs-lookup"><span data-stu-id="4e5e5-119">All policies for retention and with any configuration support Preservation Lock.</span></span>

1. <span data-ttu-id="4e5e5-120">[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="4e5e5-120">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="4e5e5-121">通过运行 [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)，找到所需锁定的策略名称。</span><span class="sxs-lookup"><span data-stu-id="4e5e5-121">Find the name of the policy that you want to lock by running [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy).</span></span> <span data-ttu-id="4e5e5-122">例如：</span><span class="sxs-lookup"><span data-stu-id="4e5e5-122">For example:</span></span>
    
   ![PowerShell 中的保留策略列表](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. <span data-ttu-id="4e5e5-124">若要在策略上放置保存锁，请运行 [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet，并将策略的名称和 *RestrictiveRetention* 参数设置为 true：</span><span class="sxs-lookup"><span data-stu-id="4e5e5-124">To place a Preservation Lock on your policy, run the [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet with the name of the policy, and the *RestrictiveRetention* parameter set to true:</span></span>
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    <span data-ttu-id="4e5e5-125">例如：</span><span class="sxs-lookup"><span data-stu-id="4e5e5-125">For example:</span></span>
    
    ![PowerShell 中的 RestrictiveRetention 参数](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     <span data-ttu-id="4e5e5-127">出现提示时，请阅读并通过输入 **Y** 确认这个配置随附的限制：</span><span class="sxs-lookup"><span data-stu-id="4e5e5-127">When prompted, read and acknowledge the restrictions that come with this configuration by entering **Y** :</span></span>
    
   ![用于确认你要在 PowerShell 中锁定保留策略的提示](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="4e5e5-129">现在策略上已经有了保留锁定。</span><span class="sxs-lookup"><span data-stu-id="4e5e5-129">A Preservation Lock is now placed on the policy.</span></span> <span data-ttu-id="4e5e5-130">若要确认，请再次运行 `Get-RetentionCompliancePolicy`，但需指定保留策略名称并显示策略参数：</span><span class="sxs-lookup"><span data-stu-id="4e5e5-130">To confirm, run `Get-RetentionCompliancePolicy` again, but specify the policy name and display the policy parameters:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

<span data-ttu-id="4e5e5-131">应看到 **RestrictiveRetention** 设置为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="4e5e5-131">You should see **RestrictiveRetention** is set to **True**.</span></span> <span data-ttu-id="4e5e5-132">例如：</span><span class="sxs-lookup"><span data-stu-id="4e5e5-132">For example:</span></span>

![已在 PowerShell 中显示所有参数的锁定策略](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a><span data-ttu-id="4e5e5-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e5e5-134">See also</span></span>

[<span data-ttu-id="4e5e5-135">有助于你满足信息治理和记录管理监管要求的资源</span><span class="sxs-lookup"><span data-stu-id="4e5e5-135">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)
