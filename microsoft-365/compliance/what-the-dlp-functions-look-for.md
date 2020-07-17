---
title: DLP 函数查找的内容
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解数据丢失防护（DLP）函数的外观，以帮助您了解预定义的敏感信息类型的工作方式。
ms.openlocfilehash: 838277b2e30696cd00cfc30df49c1d5a29149d92
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819272"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="8f918-103">DLP 函数查找的内容</span><span class="sxs-lookup"><span data-stu-id="8f918-103">What the DLP functions look for</span></span>

<span data-ttu-id="8f918-104">数据丢失防护（DLP）包括敏感信息类型，如信用卡号和欧盟借记卡号，可供您在 DLP 策略中使用。</span><span class="sxs-lookup"><span data-stu-id="8f918-104">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="8f918-105">这些敏感信息类型查找特定模式，并通过确保正确的格式设置、强制校验和来查找相关的关键字或其他信息来 corroborate。</span><span class="sxs-lookup"><span data-stu-id="8f918-105">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="8f918-106">其中一些功能是由内部函数执行的。</span><span class="sxs-lookup"><span data-stu-id="8f918-106">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="8f918-107">例如，信用卡号敏感信息类型使用函数查找类似于到期日期的日期，以帮助 corroborate 号码是信用卡号。</span><span class="sxs-lookup"><span data-stu-id="8f918-107">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="8f918-108">本主题说明这些函数查找的内容，以帮助您了解预定义的敏感信息类型的工作原理。</span><span class="sxs-lookup"><span data-stu-id="8f918-108">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="8f918-109">有关详细信息，请参阅[敏感信息类型实体定义](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="8f918-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="8f918-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="8f918-110">Func_us_date</span></span>

<span data-ttu-id="8f918-111">此函数以美国常用格式查找日期这包括格式 "月/日/年"、"月-日-年" 和 "年月日"。</span><span class="sxs-lookup"><span data-stu-id="8f918-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="8f918-112">月份的名称或缩写不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="8f918-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="8f918-113">示例：</span><span class="sxs-lookup"><span data-stu-id="8f918-113">Examples:</span></span>
  
- <span data-ttu-id="8f918-114">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="8f918-114">December 2, 2016</span></span>
    
- <span data-ttu-id="8f918-115">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="8f918-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="8f918-116">dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="8f918-116">dec 02 2016</span></span>
    
- <span data-ttu-id="8f918-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="8f918-117">12/2/2016</span></span>
    
- <span data-ttu-id="8f918-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="8f918-118">12/02/16</span></span>
    
- <span data-ttu-id="8f918-119">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="8f918-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="8f918-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="8f918-120">12-2-16</span></span>
    
<span data-ttu-id="8f918-121">接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="8f918-121">Accepted month names:</span></span>
  
- <span data-ttu-id="8f918-122">English</span><span class="sxs-lookup"><span data-stu-id="8f918-122">English</span></span>
    
  - <span data-ttu-id="8f918-123">一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="8f918-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="8f918-124">2003年4月4日. 5 月4月6月11月11月11月4日。</span><span class="sxs-lookup"><span data-stu-id="8f918-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="8f918-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="8f918-125">Func_eu_date</span></span>

<span data-ttu-id="8f918-126">此函数查找欧盟常用格式的日期</span><span class="sxs-lookup"><span data-stu-id="8f918-126">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="8f918-127">（以及美国以外的大多数位置）。</span><span class="sxs-lookup"><span data-stu-id="8f918-127">(and most places outside the U.S.).</span></span> <span data-ttu-id="8f918-128">这包括格式 "日/月/年"、"日-月-年" 和 "年月日"。</span><span class="sxs-lookup"><span data-stu-id="8f918-128">This includes the formats "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="8f918-129">月份的名称或缩写不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="8f918-129">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="8f918-130">示例：</span><span class="sxs-lookup"><span data-stu-id="8f918-130">Examples:</span></span>
  
- <span data-ttu-id="8f918-131">2 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="8f918-131">2 Dec 2016</span></span>
    
- <span data-ttu-id="8f918-132">02年12月2016</span><span class="sxs-lookup"><span data-stu-id="8f918-132">02 dec 2016</span></span>
    
- <span data-ttu-id="8f918-133">2 Dec 16</span><span class="sxs-lookup"><span data-stu-id="8f918-133">2 Dec 16</span></span>
    
- <span data-ttu-id="8f918-134">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="8f918-134">2/12/2016</span></span>
    
- <span data-ttu-id="8f918-135">02/12/16</span><span class="sxs-lookup"><span data-stu-id="8f918-135">02/12/16</span></span>
    
- <span data-ttu-id="8f918-136">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="8f918-136">2-Dec-2016</span></span>
    
- <span data-ttu-id="8f918-137">2-12-16</span><span class="sxs-lookup"><span data-stu-id="8f918-137">2-12-16</span></span>
    
<span data-ttu-id="8f918-138">接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="8f918-138">Accepted month names:</span></span>
  
- <span data-ttu-id="8f918-139">English</span><span class="sxs-lookup"><span data-stu-id="8f918-139">English</span></span>
    
  - <span data-ttu-id="8f918-140">一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="8f918-140">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="8f918-141">2003年4月4日. 5 月4月6月11月11月11月4日。</span><span class="sxs-lookup"><span data-stu-id="8f918-141">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="8f918-142">荷兰语</span><span class="sxs-lookup"><span data-stu-id="8f918-142">Dutch</span></span>
    
  - <span data-ttu-id="8f918-143">januari、februari、maart、四月、mei、juni、juli、augustus、九月、ocktober、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="8f918-143">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="8f918-144">2004年1月1月 maart 日 mei 年9月8日9月9日 okt 年11月</span><span class="sxs-lookup"><span data-stu-id="8f918-144">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="8f918-145">法语</span><span class="sxs-lookup"><span data-stu-id="8f918-145">French</span></span>
    
  - <span data-ttu-id="8f918-146">janvier、février、mars、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre</span><span class="sxs-lookup"><span data-stu-id="8f918-146">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="8f918-147">janv.</span><span class="sxs-lookup"><span data-stu-id="8f918-147">janv.</span></span> <span data-ttu-id="8f918-148">févr.</span><span class="sxs-lookup"><span data-stu-id="8f918-148">févr.</span></span> <span data-ttu-id="8f918-149">火星 avril mai juin juil。</span><span class="sxs-lookup"><span data-stu-id="8f918-149">mars avril mai juin juil.</span></span> <span data-ttu-id="8f918-150">août 9 月。</span><span class="sxs-lookup"><span data-stu-id="8f918-150">août sept.</span></span> <span data-ttu-id="8f918-151">2008.</span><span class="sxs-lookup"><span data-stu-id="8f918-151">oct.</span></span> <span data-ttu-id="8f918-152">年11月.</span><span class="sxs-lookup"><span data-stu-id="8f918-152">nov.</span></span> <span data-ttu-id="8f918-153">déc.</span><span class="sxs-lookup"><span data-stu-id="8f918-153">déc.</span></span>
    
- <span data-ttu-id="8f918-154">德语</span><span class="sxs-lookup"><span data-stu-id="8f918-154">German</span></span>
    
  - <span data-ttu-id="8f918-155">jänuar、februar、märz、四月、mai、juni juli、八月、九月、oktober、十一月、dezember</span><span class="sxs-lookup"><span data-stu-id="8f918-155">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="8f918-156">Jan./Jän。</span><span class="sxs-lookup"><span data-stu-id="8f918-156">Jan./Jän.</span></span> <span data-ttu-id="8f918-157">2003年 März 年4月 Juni Juli，Okt。</span><span class="sxs-lookup"><span data-stu-id="8f918-157">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="8f918-158">Dez 年11月。</span><span class="sxs-lookup"><span data-stu-id="8f918-158">Nov. Dez.</span></span>
    
- <span data-ttu-id="8f918-159">意大利语</span><span class="sxs-lookup"><span data-stu-id="8f918-159">Italian</span></span>
    
  - <span data-ttu-id="8f918-160">gennaio、febbraio、marzo、aprile、maggio、giugno、luglio、agosto、settembre、ottobre、novembre、dicembre</span><span class="sxs-lookup"><span data-stu-id="8f918-160">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="8f918-161">genn.</span><span class="sxs-lookup"><span data-stu-id="8f918-161">genn.</span></span> <span data-ttu-id="8f918-162">febbr.</span><span class="sxs-lookup"><span data-stu-id="8f918-162">febbr.</span></span> <span data-ttu-id="8f918-163">mar.</span><span class="sxs-lookup"><span data-stu-id="8f918-163">mar.</span></span> <span data-ttu-id="8f918-164">四月.</span><span class="sxs-lookup"><span data-stu-id="8f918-164">apr.</span></span> <span data-ttu-id="8f918-165">magg.</span><span class="sxs-lookup"><span data-stu-id="8f918-165">magg.</span></span> <span data-ttu-id="8f918-166">giugno luglio ag。</span><span class="sxs-lookup"><span data-stu-id="8f918-166">giugno luglio ag.</span></span> <span data-ttu-id="8f918-167">设置.</span><span class="sxs-lookup"><span data-stu-id="8f918-167">sett.</span></span> <span data-ttu-id="8f918-168">ott.</span><span class="sxs-lookup"><span data-stu-id="8f918-168">ott.</span></span> <span data-ttu-id="8f918-169">年11月.</span><span class="sxs-lookup"><span data-stu-id="8f918-169">nov.</span></span> <span data-ttu-id="8f918-170">home.dic.</span><span class="sxs-lookup"><span data-stu-id="8f918-170">dic.</span></span>
    
- <span data-ttu-id="8f918-171">葡萄牙语</span><span class="sxs-lookup"><span data-stu-id="8f918-171">Portuguese</span></span>
    
  - <span data-ttu-id="8f918-172">里约热内卢、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="8f918-172">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="8f918-173">jan fev mar abr mai 06 年6月前设置11月 dez</span><span class="sxs-lookup"><span data-stu-id="8f918-173">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="8f918-174">西班牙语</span><span class="sxs-lookup"><span data-stu-id="8f918-174">Spanish</span></span>
    
  - <span data-ttu-id="8f918-175">enero、febrero、marzo、abril、mayo、junio、julio、agosto、septiembre、octubre、noviembre、diciembre</span><span class="sxs-lookup"><span data-stu-id="8f918-175">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="8f918-176">enero 2003 年2月。</span><span class="sxs-lookup"><span data-stu-id="8f918-176">enero feb.</span></span> <span data-ttu-id="8f918-177">marzo abr。</span><span class="sxs-lookup"><span data-stu-id="8f918-177">marzo abr.</span></span> <span data-ttu-id="8f918-178">mayo 06。</span><span class="sxs-lookup"><span data-stu-id="8f918-178">mayo jun.</span></span> <span data-ttu-id="8f918-179">年7月.</span><span class="sxs-lookup"><span data-stu-id="8f918-179">jul.</span></span> <span data-ttu-id="8f918-180">agosto/set。</span><span class="sxs-lookup"><span data-stu-id="8f918-180">agosto sept./set.</span></span> <span data-ttu-id="8f918-181">2008.</span><span class="sxs-lookup"><span data-stu-id="8f918-181">oct.</span></span> <span data-ttu-id="8f918-182">年11月.</span><span class="sxs-lookup"><span data-stu-id="8f918-182">nov.</span></span> <span data-ttu-id="8f918-183">home.dic.</span><span class="sxs-lookup"><span data-stu-id="8f918-183">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="8f918-184">Func_eu_date1 （已弃用）</span><span class="sxs-lookup"><span data-stu-id="8f918-184">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="8f918-185">此函数已被弃用，因为它仅支持包含在上述函数中的葡萄牙月名称 `Func_eu_date` 。</span><span class="sxs-lookup"><span data-stu-id="8f918-185">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="8f918-186">此函数使用葡萄牙语中常用的格式查找日期。</span><span class="sxs-lookup"><span data-stu-id="8f918-186">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="8f918-187">此函数的格式与 `Func_eu_date` 使用的语言不同。</span><span class="sxs-lookup"><span data-stu-id="8f918-187">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="8f918-188">示例：</span><span class="sxs-lookup"><span data-stu-id="8f918-188">Examples:</span></span>
  
- <span data-ttu-id="8f918-189">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="8f918-189">2 Dez 2016</span></span>
    
- <span data-ttu-id="8f918-190">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="8f918-190">02 dez 2016</span></span>
    
- <span data-ttu-id="8f918-191">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="8f918-191">2 Dez 16</span></span>
    
- <span data-ttu-id="8f918-192">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="8f918-192">2/12/2016</span></span>
    
- <span data-ttu-id="8f918-193">02/12/16</span><span class="sxs-lookup"><span data-stu-id="8f918-193">02/12/16</span></span>
    
- <span data-ttu-id="8f918-194">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="8f918-194">2-Dez-2016</span></span>
    
- <span data-ttu-id="8f918-195">2-12-16</span><span class="sxs-lookup"><span data-stu-id="8f918-195">2-12-16</span></span>
    
<span data-ttu-id="8f918-196">接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="8f918-196">Accepted month names:</span></span>
  
- <span data-ttu-id="8f918-197">葡萄牙语</span><span class="sxs-lookup"><span data-stu-id="8f918-197">Portuguese</span></span>
    
  - <span data-ttu-id="8f918-198">里约热内卢、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="8f918-198">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="8f918-199">jan fev mar abr mai 06 年6月前设置11月 dez</span><span class="sxs-lookup"><span data-stu-id="8f918-199">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="8f918-200">Func_eu_date2 （已弃用）</span><span class="sxs-lookup"><span data-stu-id="8f918-200">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="8f918-201">此函数已被弃用，因为它仅支持荷兰月份名称，这些名称现在包含在 `Func_eu_date` 上述函数中。</span><span class="sxs-lookup"><span data-stu-id="8f918-201">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="8f918-202">此函数查找在荷兰语中常用的格式的日期。</span><span class="sxs-lookup"><span data-stu-id="8f918-202">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="8f918-203">此函数的格式与 `Func_eu_date` 使用的语言不同。</span><span class="sxs-lookup"><span data-stu-id="8f918-203">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="8f918-204">示例：</span><span class="sxs-lookup"><span data-stu-id="8f918-204">Examples:</span></span>
  
- <span data-ttu-id="8f918-205">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="8f918-205">2 Mei 2016</span></span>
    
- <span data-ttu-id="8f918-206">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="8f918-206">02 mei 2016</span></span>
    
- <span data-ttu-id="8f918-207">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="8f918-207">2 Mei 16</span></span>
    
- <span data-ttu-id="8f918-208">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="8f918-208">2/12/2016</span></span>
    
- <span data-ttu-id="8f918-209">02/12/16</span><span class="sxs-lookup"><span data-stu-id="8f918-209">02/12/16</span></span>
    
- <span data-ttu-id="8f918-210">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="8f918-210">2-Mei-2016</span></span>
    
- <span data-ttu-id="8f918-211">2-12-16</span><span class="sxs-lookup"><span data-stu-id="8f918-211">2-12-16</span></span>
    
<span data-ttu-id="8f918-212">接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="8f918-212">Accepted month names:</span></span>
  
- <span data-ttu-id="8f918-213">荷兰语</span><span class="sxs-lookup"><span data-stu-id="8f918-213">Dutch</span></span>
    
  - <span data-ttu-id="8f918-214">januari、februari、maart、四月、mei、juni、juli、augustus、九月、ocktober、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="8f918-214">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="8f918-215">2004年1月1月 maart 日 mei 年9月8日9月9日 okt 年11月</span><span class="sxs-lookup"><span data-stu-id="8f918-215">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="8f918-216">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="8f918-216">Func_expiration_date</span></span>

<span data-ttu-id="8f918-217">此函数查找信用卡和借记卡常用格式的日期，其中不包括月份的天数。</span><span class="sxs-lookup"><span data-stu-id="8f918-217">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="8f918-218">此函数将以 "月/年"、"月-年"、"[月 name] year" 和 "[月缩写] 年" 的格式匹配日期。</span><span class="sxs-lookup"><span data-stu-id="8f918-218">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="8f918-219">月份的名称或缩写不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="8f918-219">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="8f918-220">示例：</span><span class="sxs-lookup"><span data-stu-id="8f918-220">Examples:</span></span>
  
- <span data-ttu-id="8f918-221">MM/YY--例如，01/11 或1/11</span><span class="sxs-lookup"><span data-stu-id="8f918-221">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="8f918-222">MM/YYYY--例如，01/2011 或1/2011</span><span class="sxs-lookup"><span data-stu-id="8f918-222">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="8f918-223">MM-YY--例如，01-22 或1-11</span><span class="sxs-lookup"><span data-stu-id="8f918-223">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="8f918-224">MM--例如，01-2000 或1-2000</span><span class="sxs-lookup"><span data-stu-id="8f918-224">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="8f918-225">以下格式支持 YY 或 YYYY：</span><span class="sxs-lookup"><span data-stu-id="8f918-225">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="8f918-226">年月日-例如，。Jan-2010 或一月-2010 或 Jan-10 或一月-10</span><span class="sxs-lookup"><span data-stu-id="8f918-226">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="8f918-227">年月日-例如，"一月 2010" 或 "Jan 2010" 或 "Jan 10" 或 "Jan 10"</span><span class="sxs-lookup"><span data-stu-id="8f918-227">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="8f918-228">MonthYYYY-例如，"january2010" 或 "Jan2010" 或 "january10" 或 "Jan10"</span><span class="sxs-lookup"><span data-stu-id="8f918-228">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="8f918-229">Month/YYYY-例如，"一月/2010" 或 "Jan/2010" 或 "一月/10" 或 "Jan/10"</span><span class="sxs-lookup"><span data-stu-id="8f918-229">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="8f918-230">接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="8f918-230">Accepted month names:</span></span>
  
- <span data-ttu-id="8f918-231">English</span><span class="sxs-lookup"><span data-stu-id="8f918-231">English</span></span>
    
  - <span data-ttu-id="8f918-232">一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="8f918-232">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="8f918-233">2004年2月3月4月5月8日12月8月8日</span><span class="sxs-lookup"><span data-stu-id="8f918-233">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="8f918-234">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="8f918-234">Func_us_address</span></span>

<span data-ttu-id="8f918-235">此函数查找美国的状态名称或邮政缩写，后跟有效的邮政编码，就像在邮政地址中使用一样。</span><span class="sxs-lookup"><span data-stu-id="8f918-235">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses.</span></span> <span data-ttu-id="8f918-236">邮政编码必须是与美国省/市/自治区名称或缩写相关联的正确邮政编码之一。</span><span class="sxs-lookup"><span data-stu-id="8f918-236">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="8f918-237">美国省/市/自治区名称和邮政编码不能由标点符号或字母分隔。</span><span class="sxs-lookup"><span data-stu-id="8f918-237">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="8f918-238">示例：</span><span class="sxs-lookup"><span data-stu-id="8f918-238">Examples:</span></span>
  
- <span data-ttu-id="8f918-239">华盛顿98052</span><span class="sxs-lookup"><span data-stu-id="8f918-239">Washington 98052</span></span>
    
- <span data-ttu-id="8f918-240">华盛顿98052-9998</span><span class="sxs-lookup"><span data-stu-id="8f918-240">Washington 98052-9998</span></span>
    
- <span data-ttu-id="8f918-241">WA 98052</span><span class="sxs-lookup"><span data-stu-id="8f918-241">WA 98052</span></span>
    
- <span data-ttu-id="8f918-242">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="8f918-242">WA 98052-9998</span></span>
    

