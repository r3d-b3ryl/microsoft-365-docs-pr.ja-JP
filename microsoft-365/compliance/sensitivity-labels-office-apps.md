---
title: Office アプリにおける機密ラベルの機能
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 機密ラベルを使用すると、機密コンテンツの分類が可能になり、機密コンテンツの保護に役立ちます。このラベルを使用することで、共同作業の生産性や機能性が低下することはありません。機密ラベルは、ラベル付けされたコンテンツに暗号化や透かしなどの保護設定を強制適用するために使用できます。
ms.openlocfilehash: 1de7eadfcf95a54917c1d5e2cc0d42cc1ad486a5
ms.sourcegitcommit: c7f7ff463141f7d7f0970b64e5a04341db7e4fa8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "37378655"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a><span data-ttu-id="7c0d6-104">Office アプリにおける機密ラベルの機能</span><span class="sxs-lookup"><span data-stu-id="7c0d6-104">How sensitivity labels work in Office apps</span></span>

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a><span data-ttu-id="7c0d6-105">Office アプリケーションで機密ラベルを使用するための前提条件について</span><span class="sxs-lookup"><span data-stu-id="7c0d6-105">What prerequisites are there to use sensitivity labels in Office applications?</span></span>

### <a name="common-requirements"></a><span data-ttu-id="7c0d6-106">一般的な要件</span><span class="sxs-lookup"><span data-stu-id="7c0d6-106">Common requirements</span></span> 

- <span data-ttu-id="7c0d6-107">統合された機密ラベルは[セキュリティ/コンプライアンス センターで構成、公開されている](https://aka.ms/managemip)必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-107">Unified sensitivity labels must be [configured and published in the Security and Compliance Center](https://aka.ms/managemip)</span></span>
- <span data-ttu-id="7c0d6-108">ユーザーは業務用アカウントを使って Office にログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-108">Users must be signed in to Office with their work account.</span></span>
- <span data-ttu-id="7c0d6-109">ユーザーには Office 365 E3 以上のライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-109">Users must have an Office 365 E3 or above license assigned.</span></span>

### <a name="additional-requirements-for-office-for-windows"></a><span data-ttu-id="7c0d6-110">Office for Windows のその他の要件</span><span class="sxs-lookup"><span data-stu-id="7c0d6-110">Additional requirements for Office for Windows</span></span> 

- <span data-ttu-id="7c0d6-111">Azure Information Protection クライアントが Office で実行されていない必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-111">The Azure Information Protection client must not be running in Office.</span></span> <span data-ttu-id="7c0d6-112">「[機密ラベルは Office for Windows で Azure Information Protection クライアントと一緒に実行できますか?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-112">See also: [Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span></span>

### <a name="additional-requirements-for-outlook-on-all-platforms"></a><span data-ttu-id="7c0d6-113">すべてのプラットフォームの Outlook に関するその他の要件</span><span class="sxs-lookup"><span data-stu-id="7c0d6-113">Additional requirements for Outlook on all platforms</span></span> 

- <span data-ttu-id="7c0d6-114">ラベル構成で、コンテンツ マーキングを有効にした場合に、コンテンツ マーキングが転送中に挿入されるようにするには、Exchange Online を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-114">In your label configuration, if you turn on content marking, you must be using Exchange Online for that content marking to be inserted in transit.</span></span>

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a><span data-ttu-id="7c0d6-115">今日の Office でサポートされている機密ラベル機能について</span><span class="sxs-lookup"><span data-stu-id="7c0d6-115">What sensitivity label capabilities are supported in Office today?</span></span> 

<table border="1" cellspacing="0" cellpadding="0">
<th><span data-ttu-id="7c0d6-116"><font size="-1">機能</span><span class="sxs-lookup"><span data-stu-id="7c0d6-116"><font size="-1"></span></span><th><span data-ttu-id="7c0d6-117"><font size="-1">Windows</span><span class="sxs-lookup"><span data-stu-id="7c0d6-117"><font size="-1"></span></span><th><span data-ttu-id="7c0d6-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span><span class="sxs-lookup"><span data-stu-id="7c0d6-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span></span></tr>
<tr><td>

<td><span data-ttu-id="7c0d6-119"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="7c0d6-119"><font size="-1">Word</span></span><br>
<span data-ttu-id="7c0d6-120">Excel</span><span class="sxs-lookup"><span data-stu-id="7c0d6-120">Excel</span></span><br>
<span data-ttu-id="7c0d6-121">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7c0d6-121">PowerPoint</span></span><br>
<span data-ttu-id="7c0d6-122">Outlook</span><span class="sxs-lookup"><span data-stu-id="7c0d6-122">Outlook</span></span>


<td><span data-ttu-id="7c0d6-123"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="7c0d6-123"><font size="-1">Word</span></span><br>
<span data-ttu-id="7c0d6-124">Excel</span><span class="sxs-lookup"><span data-stu-id="7c0d6-124">Excel</span></span><br>
<span data-ttu-id="7c0d6-125">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7c0d6-125">PowerPoint</span></span><br>
<span data-ttu-id="7c0d6-126">Outlook</span><span class="sxs-lookup"><span data-stu-id="7c0d6-126">Outlook</span></span>

<td><span data-ttu-id="7c0d6-127"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="7c0d6-127"><font size="-1">Word</span></span><br>
<span data-ttu-id="7c0d6-128">Excel</span><span class="sxs-lookup"><span data-stu-id="7c0d6-128">Excel</span></span><br>
<span data-ttu-id="7c0d6-129">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7c0d6-129">PowerPoint</span></span>
<td><span data-ttu-id="7c0d6-130"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="7c0d6-130"><font size="-1">Outlook</span></span>

<td><span data-ttu-id="7c0d6-131"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="7c0d6-131"><font size="-1">Word</span></span><br>
<span data-ttu-id="7c0d6-132">Excel</span><span class="sxs-lookup"><span data-stu-id="7c0d6-132">Excel</span></span><br>
<span data-ttu-id="7c0d6-133">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7c0d6-133">PowerPoint</span></span>
<td><span data-ttu-id="7c0d6-134"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="7c0d6-134"><font size="-1">Outlook</span></span>

<td><span data-ttu-id="7c0d6-135"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="7c0d6-135"><font size="-1">Word</span></span><br>
<span data-ttu-id="7c0d6-136">Excel</span><span class="sxs-lookup"><span data-stu-id="7c0d6-136">Excel</span></span><br>
<span data-ttu-id="7c0d6-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7c0d6-137">PowerPoint</span></span>
<td><span data-ttu-id="7c0d6-138"><font size="-1"> Outlook </b>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-138">Outlook</span></span></tr>

<tr>
<td><span data-ttu-id="7c0d6-139"><font size="-1">ラベルを手動で適用、変更、または削除する</span><span class="sxs-lookup"><span data-stu-id="7c0d6-139"><font size="-1">Manually apply, change, or remove label</span></span><td><span data-ttu-id="7c0d6-140"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-140">Yes</span></span><br><span data-ttu-id="7c0d6-141"><font size="-1">1910以上</font>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-141"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="7c0d6-142"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-142">Yes</span></span><br><span data-ttu-id="7c0d6-143"><font size="-1">16.21.0以上</font>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-143"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="7c0d6-144"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-144">Yes</span></span><br><span data-ttu-id="7c0d6-145"><font size="-1">2.21以上</font>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-145"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="7c0d6-146"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-146"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-147"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-147">Yes</span></span><br><span data-ttu-id="7c0d6-148"><font size="-1">16.0.11231以上</font>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-148"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="7c0d6-149"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-149"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-150"><font size="-1">近日公開<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="7c0d6-150"><font size="-1">Coming soon<sup>3</sup></span></span><td><span data-ttu-id="7c0d6-151"><font size="-1">近日公開<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-151"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr>
<td><span data-ttu-id="7c0d6-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">既定のラベルを適用する</a>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Apply a default label</a>
</span></span><td><span data-ttu-id="7c0d6-153"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-153">Yes</span></span><br><span data-ttu-id="7c0d6-154"><font size="-1">1910以上</font>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-154"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="7c0d6-155"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-155">Yes</span></span><br><span data-ttu-id="7c0d6-156"><font size="-1">16.21.0以上</font>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-156"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="7c0d6-157"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-157">Yes</span></span><br><span data-ttu-id="7c0d6-158"><font size="-1">2.21以上</font>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-158"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="7c0d6-159"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-159"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-160"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-160">Yes</span></span><br><span data-ttu-id="7c0d6-161"><font size="-1">16.0.11231以上</font>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-161"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="7c0d6-162"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-162"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-163"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-163"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-164"><font size="-1">近日公開<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-164"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="7c0d6-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">ラベル変更の正当な理由を要求する</a><sup>1</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Require a justification for changing a label</a><sup>1</sup>
</span></span><td><span data-ttu-id="7c0d6-166"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-166">Yes</span></span><br><span data-ttu-id="7c0d6-167"><font size="-1">1910以上</font>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-167"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="7c0d6-168"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-168">Yes</span></span><br><span data-ttu-id="7c0d6-169"><font size="-1">16.21.0以上</font>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-169"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="7c0d6-170"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-170">Yes</span></span><br><span data-ttu-id="7c0d6-171"><font size="-1">2.21以上</font>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-171"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="7c0d6-172"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-172"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-173"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-173">Yes</span></span><br><span data-ttu-id="7c0d6-174"><font size="-1">16.0.11231以上</font>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-174"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="7c0d6-175"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-175"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-176"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-176"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-177"><font size="-1">近日公開<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-177"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="7c0d6-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">カスタム ヘルプ ページへのリンクを提供する</a>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Provide help link to a custom help page</a>
</span></span><td><span data-ttu-id="7c0d6-179"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-179">Yes</span></span><br><span data-ttu-id="7c0d6-180"><font size="-1">1910以上</font>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-180"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="7c0d6-181"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-181">Yes</span></span><br><span data-ttu-id="7c0d6-182"><font size="-1">16.21.0以上</font>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-182"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="7c0d6-183"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-183">Yes</span></span><br><span data-ttu-id="7c0d6-184"><font size="-1">2.21以上</font>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-184"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="7c0d6-185"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-185"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-186"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-186">Yes</span></span><br><span data-ttu-id="7c0d6-187"><font size="-1">16.0.11231以上</font>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-187"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="7c0d6-188"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-188"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-189"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-189"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-190"><font size="-1">近日公開<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-190"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="7c0d6-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">コンテンツをマークする</a>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Mark the content</a>
</span></span><td><span data-ttu-id="7c0d6-192"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-192">Yes</span></span><br><span data-ttu-id="7c0d6-193"><font size="-1">1910以上</font>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-193"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="7c0d6-194"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-194">Yes</span></span><br><span data-ttu-id="7c0d6-195"><font size="-1">16.21.0以上</font>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-195"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="7c0d6-196"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-196">Yes</span></span><br><span data-ttu-id="7c0d6-197"><font size="-1">2.21以上</font>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-197"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="7c0d6-198"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-198"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-199"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-199">Yes</span></span><br><span data-ttu-id="7c0d6-200"><font size="-1">16.0.11231以上</font
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-200"><font size="-1">16.0.11231+</font
</span></span>><td><span data-ttu-id="7c0d6-201"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-201"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-202"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-202"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-203"><font size="-1">近日公開<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="7c0d6-203"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="7c0d6-204"><font size="-1">定義済みのアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="7c0d6-204"><font size="-1">Assign pre-defined permissions</span></span>
<td><span data-ttu-id="7c0d6-205"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-205">Yes</span></span><br><span data-ttu-id="7c0d6-206"><font size="-1">1910以上</font>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-206"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="7c0d6-207"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-207">Yes</span></span><br><span data-ttu-id="7c0d6-208"><font size="-1">16.21.0以上</font>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-208"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="7c0d6-209"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-209">Yes</span></span><br><span data-ttu-id="7c0d6-210"><font size="-1">2.21以上</font>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-210"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="7c0d6-211"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-211"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-212"><font size="-1"><b>はい</b></span><span class="sxs-lookup"><span data-stu-id="7c0d6-212">Yes</span></span><br><span data-ttu-id="7c0d6-213"><font size="-1">16.0.11231以上</font>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-213"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="7c0d6-214"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-214"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-215"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-215"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-216"><font size="-1">近日公開<sup>3</sup>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-216"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="7c0d6-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">ユーザーがアクセス許可を割り当てる</a>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-217">Let users assign permissions</span></span><td><span data-ttu-id="7c0d6-218"><font size="-1"><b>はい</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7c0d6-218"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="7c0d6-219"><font size="-1">1910以上</font>

</span><span class="sxs-lookup"><span data-stu-id="7c0d6-219"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="7c0d6-220"><font size="-1"><b>はい</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7c0d6-220"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="7c0d6-221"><font size="-1">16.21.0以上</font></span><span class="sxs-lookup"><span data-stu-id="7c0d6-221"><font size="-1">16.21.0+</font></span></span>

<td><span data-ttu-id="7c0d6-222"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-222"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-223"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-223"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-224"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-224"><font size="-1">TBD</span></span><td
><span data-ttu-id="7c0d6-225"><font size="-1">近日公開<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-225"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="7c0d6-226"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-226"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-227"><font size="-1">近日公開<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="7c0d6-227"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="7c0d6-228"><font size="-1">管理者用に<a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">ラベルの分析</a>を送信する</span><span class="sxs-lookup"><span data-stu-id="7c0d6-228"><font size="-1">Send <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">label analytics</a> data for administrators</span></span>
<td><span data-ttu-id="7c0d6-229"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-229"><font size="-1">TBD</span></span>

<td><span data-ttu-id="7c0d6-230"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-230"><font size="-1">TBD</span></span>

<td><span data-ttu-id="7c0d6-231"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-231"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-232"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-232"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-233"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-233"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-234"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-234"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-235"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-235"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-236"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-236"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="7c0d6-237"><font size="-1">ユーザーがメールとドキュメントにラベルを適用することを必須にする</span><span class="sxs-lookup"><span data-stu-id="7c0d6-237"><font size="-1">Require users to apply a label to their email and documents</span></span>
<td><span data-ttu-id="7c0d6-238"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-238"><font size="-1">TBD</span></span>

<td><span data-ttu-id="7c0d6-239"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-239"><font size="-1">TBD</span></span>

<td><span data-ttu-id="7c0d6-240"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-240"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-241"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-241"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-242"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-242"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-243"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-243"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-244"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-244"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-245"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-245"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="7c0d6-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">機密ラベルをコンテンツに自動的に適用する</a>
</span><span class="sxs-lookup"><span data-stu-id="7c0d6-246">Apply a sensitivity label to content automatically</span></span><td><span data-ttu-id="7c0d6-247"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-247"><font size="-1">TBD</span></span>

<td><span data-ttu-id="7c0d6-248"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-248"><font size="-1">TBD</span></span>

<td><span data-ttu-id="7c0d6-249"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-249"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-250"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-250"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-251"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-251"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-252"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-252"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-253"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-253"><font size="-1">TBD</span></span>
<td><span data-ttu-id="7c0d6-254"><font size="-1">TBD</span><span class="sxs-lookup"><span data-stu-id="7c0d6-254"><font size="-1">TBD</span></span>
</table>

<br><span data-ttu-id="7c0d6-255"><sup>1</sup>構成されている場合、ユーザーはラベルのダウングレードを正当化するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-255"><sup>1</sup>If configured, users are prompted to justify label downgrades.</span></span> <span data-ttu-id="7c0d6-256">ただし、このような根拠のあるデータは、管理者はまだ使用できません。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-256">However, the justification data is not made available for administrators yet.</span></span> <span data-ttu-id="7c0d6-257">"管理者用にラベル分析データを送信する" 機能がサポートされている場合に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-257">It will become available when the “send label analytics data for administrators” capability is supported.</span></span>
<br><span data-ttu-id="7c0d6-258"><sup>2</sup> "ユーザーにアクセス許可を割り当てられるようにする" は、現在 Outlook for Windows と Outlook for Mac でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-258"><sup>2</sup>Let users assign permissions is currently only available in Outlook for Windows and Mac.</span></span> <span data-ttu-id="7c0d6-259">Word、Excel、PowerPoint の可用性は TBD です。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-259">Availability for Word, Excel, and PowerPoint is TBD.</span></span>
<br><span data-ttu-id="7c0d6-260"><sup>3</sup> 2019年の暦年第 4 四半期に予定されています。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-260"><sup>3</sup>Expected Q4 of calendar year 2019.</span></span>

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a><span data-ttu-id="7c0d6-261">コンテンツに機密ラベルが付与された後に、コンテンツ マークや暗号化が適用される時期</span><span class="sxs-lookup"><span data-stu-id="7c0d6-261">When do content marks or encryption get applied after content is given a sensitivity label?</span></span>

| <span data-ttu-id="7c0d6-262">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="7c0d6-262">Application</span></span> | <span data-ttu-id="7c0d6-263">コンテンツのマーケティング</span><span class="sxs-lookup"><span data-stu-id="7c0d6-263">Content marking</span></span> | <span data-ttu-id="7c0d6-264">暗号化</span><span class="sxs-lookup"><span data-stu-id="7c0d6-264">Encryption</span></span>
| --- | --- | --- |
| <span data-ttu-id="7c0d6-265">すべてのプラットフォームの Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7c0d6-265">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="7c0d6-266">直ちに</span><span class="sxs-lookup"><span data-stu-id="7c0d6-266">Immediately</span></span> | <span data-ttu-id="7c0d6-267">直ちに</span><span class="sxs-lookup"><span data-stu-id="7c0d6-267">Immediately</span></span> |
| <span data-ttu-id="7c0d6-268">Outlook for PC と Outlook for Mac</span><span class="sxs-lookup"><span data-stu-id="7c0d6-268">Outlook for PC and Mac</span></span> | <span data-ttu-id="7c0d6-269">Exchange Online でメールが送信された後</span><span class="sxs-lookup"><span data-stu-id="7c0d6-269">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="7c0d6-270">直ちに</span><span class="sxs-lookup"><span data-stu-id="7c0d6-270">Immediately</span></span> |
| <span data-ttu-id="7c0d6-271">すべてのプラットフォームの Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7c0d6-271">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="7c0d6-272">Exchange Online でメールが送信された後</span><span class="sxs-lookup"><span data-stu-id="7c0d6-272">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="7c0d6-273">Exchange Online でメールが送信された後</span><span class="sxs-lookup"><span data-stu-id="7c0d6-273">After the email is sent by Exchange Online</span></span> |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a><span data-ttu-id="7c0d6-274">機密ラベルは Office for Windows で Azure Information Protection クライアントと一緒に実行できますか?</span><span class="sxs-lookup"><span data-stu-id="7c0d6-274">Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?</span></span>

<span data-ttu-id="7c0d6-275">いいえ。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-275">No.</span></span> <span data-ttu-id="7c0d6-276">機密ラベルは、Azure Information Protection クライアントが Office for Windows で読み込まれた場合にオフになります。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-276">Sensitivity labels are turned off if the Azure Information Protection client is loaded in Office for Windows.</span></span>

<span data-ttu-id="7c0d6-277">Azure Information Protection クライアントがインストールされていても、代わりに機密ラベルを使用する場合は、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-277">If you have the Azure Information Protection client installed, but you want to use sensitivity labels instead, you can:</span></span>

1. <span data-ttu-id="7c0d6-278"> *\*Office の [秘密度] 機能を使用して秘密ラベルを適用して表示する*\*のグループポリシー設定を構成します。この設定は、*\*ユーザーの構成/管理用テンプレート/Microsoft Office 2016/セキュリティ設定*\*にあります。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-278">Configure the **Use the Sensitivity feature in Office to apply and view sensitivity labels** Group Policy setting, which can be found under **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings**.</span></span>

  ><span data-ttu-id="7c0d6-279">注: この設定は従来のグループ ポリシーの展開メカニズムか、[Office クラウド ポリシー サービス](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)から展開できます。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-279">Note: this setting can be deployed via traditional group policy deployment mechanisms, or by the [Office cloud policy service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span></span> 
 
  <span data-ttu-id="7c0d6-280">または、Azure Information Protection クライアントをアンインストール、または [無効](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d)にできます。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-280">Alternatively, you can uninstall or [disable](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) the Azure Information Protection client.</span></span> 

2. <span data-ttu-id="7c0d6-281">すべての Office アプリケーションを再起動します。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-281">Restart all Office applications.</span></span>

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a><span data-ttu-id="7c0d6-282">機密ラベルは、Office 2016 または Office 2019 のようなサブスクリプション以外 Office のバージョンでサポートされますか?</span><span class="sxs-lookup"><span data-stu-id="7c0d6-282">Will sensitivity labels be supported in non-subscription versions of Office like Office 2016 or Office 2019?</span></span>

<span data-ttu-id="7c0d6-283">いいえ。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-283">No.</span></span> <span data-ttu-id="7c0d6-284">機密ラベルは Office 365 サブスクリプションでのみサポートされ、サブスクリプション以外のいずれのバージョンでもサポートされません。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-284">Sensitivity labels will only be supported in the Office 365 subscription and will not be supported in any non-subscription version.</span></span> <span data-ttu-id="7c0d6-285">ただし、Azure Information Protection の統合されたラベル クライアントは、サブスクリプション以外の Office のバージョンで使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-285">However, the Azure Information Protection unified labeling client may be used in non-subscription versions of Office.</span></span> 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a><span data-ttu-id="7c0d6-286">以前は、保護テンプレートを展開してから機密ラベルを設定しました。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-286">I previously deployed protection templates before setting up sensitivity labels.</span></span> <span data-ttu-id="7c0d6-287">どうなりましたか?</span><span class="sxs-lookup"><span data-stu-id="7c0d6-287">Where did they go?</span></span>

<span data-ttu-id="7c0d6-288">機密ラベルが有効になっていると、管理者が定義した[保護テンプレート](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)は Office のユーザー環境から非表示になります。暗号化が有効になっている機密ラベルでは冗長であるためです。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-288">Administrator-defined [protection templates](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) are hidden from the Office user experience when sensitivity labels are enabled because they are redundant with sensitivity labels that have encryption enabled.</span></span> 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a><span data-ttu-id="7c0d6-289">ファイルまたはメールに複数の分類を含めることはできますか?</span><span class="sxs-lookup"><span data-stu-id="7c0d6-289">Can a file or email have more than one classification?</span></span>

<span data-ttu-id="7c0d6-290">ユーザーは、ドキュメントまたはメールごとに一度に 1 つずつラベルを選ぶことができます。多くの場合、分類は 1 つになります。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-290">Users can select just one label at a time for each document or email, which often results in just one classification.</span></span> <span data-ttu-id="7c0d6-291">ただし、ユーザーがサブラベルを選択すると、実際にプライマリ ラベルとセカンダリ ラベルの 2 つのラベルが同時に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-291">However, if users select a sublabel, this actually applies two labels at the same time; a primary label and a secondary label.</span></span> <span data-ttu-id="7c0d6-292">サブラベルを使用すると、ファイルには、追加の制御レベルに対して親子関係を表す 2 つの分類を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-292">By using sublabels, a file can have two classifications that denote a parent/child relationship for an additional level of control.</span></span> 

<span data-ttu-id="7c0d6-293">たとえば、 **秘密** ラベルは **法務** や **財務**などのサブラベルが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-293">For example, the label **Confidential** might contain sublabels such as **Legal** and **Finance**.</span></span> <span data-ttu-id="7c0d6-294">このサブラベルには、さまざまな分類の視覚的なマーキングと、多種多様な Rights Management テンプレートを適用できます。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-294">You can apply different classification visual markings and different Rights Management templates to these sublabels.</span></span> <span data-ttu-id="7c0d6-295">ユーザーは **秘密** ラベルを単独では選択できません (たとえば、 **法務**などのサブラベルのうちの 1 つのみなど)。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-295">A user cannot select the **Confidential** label by itself; only one of its sublabels, such as **Legal**.</span></span> <span data-ttu-id="7c0d6-296">結果として表示されるラベルは、 **秘密** / **法務**です。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-296">As a result, the label that they see set is **Confidential** / **Legal**.</span></span> <span data-ttu-id="7c0d6-297">ファイルのメタデータには、 **秘密**のカスタム テキスト プロパティ、 **法務**のカスタム テキスト プロパティ、両方の値 (**秘密ラベル**) を含む別のカスタム テキスト プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-297">The metadata for that file includes one custom text property for **Confidential**, one custom text property for **Legal**, and another that contains both values (**Confidential Legal**).</span></span> 

<span data-ttu-id="7c0d6-298">サブラベルを使用する場合は、プライマリ ラベルに視覚的なマーキング、保護、条件を構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-298">When you use sublabels, don't configure visual markings, protection, and conditions at the primary label.</span></span> <span data-ttu-id="7c0d6-299">サブレベルを使用する場合は、サブラベルでのみこれらの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-299">When you use sublevels, configure these setting on the sublabel only.</span></span> <span data-ttu-id="7c0d6-300">プライマリ ラベルとサブラベルでこれらの設定を構成すると、サブラベルの設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-300">If you configure these settings on the primary label and its sublabel, the settings at the sublabel take precedence.</span></span>

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a><span data-ttu-id="7c0d6-301">メールにラベルが付けられている場合は、添付ファイルに同じラベルを自動的に付けますか?</span><span class="sxs-lookup"><span data-stu-id="7c0d6-301">When an email is labeled, do any attachments automatically get the same labeling?</span></span>

<span data-ttu-id="7c0d6-302">いいえ。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-302">No.</span></span> <span data-ttu-id="7c0d6-303">添付ファイルのあるメール メッセージにラベルを付けると、この添付ファイルのラベルは同じラベルを継承しません。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-303">When you label an email message that has attachments, those attachments do not inherit the same label.</span></span> <span data-ttu-id="7c0d6-304">ラベルがない場合、または別々にラベルを適用していない場合、添付ファイルはそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-304">The attachments remain either without a label or retain a separately applied label.</span></span> <span data-ttu-id="7c0d6-305">ただし、メールのラベルが保護されている場合、その保護は Office の添付ファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7c0d6-305">However, if the label for the email applies protection, that protection is applied to Office attachments.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7c0d6-306">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="7c0d6-306">Additional resources</span></span>

[<span data-ttu-id="7c0d6-307">Azure Information Protection での分類とラベル付けについてよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="7c0d6-307">Frequently asked questions about classification and labeling in Azure Information Protection</span></span>](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[<span data-ttu-id="7c0d6-308">Office 内のドキュメントとメールに機密ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="7c0d6-308">Apply sensitivity labels to your documents and email within Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)