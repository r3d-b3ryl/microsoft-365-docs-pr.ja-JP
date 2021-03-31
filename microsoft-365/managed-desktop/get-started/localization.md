---
title: ユーザー エクスペリエンスのローカライズ
description: ユーザーのデバイスをローカライズする方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
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
ms.openlocfilehash: 20456ce837be60b707569ae07d4fb00b695b3a98
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445983"
---
# <a name="localize-the-user-experience"></a><span data-ttu-id="08464-104">ユーザー エクスペリエンスのローカライズ</span><span class="sxs-lookup"><span data-stu-id="08464-104">Localize the user experience</span></span>

<span data-ttu-id="08464-105">Microsoft Managed Desktop デバイスのユーザーは、セットアップ プロセス ("すぐに使用できる") または後で、選択した言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="08464-105">Users of Microsoft Managed Desktop devices can select the language of their choice either during the setup process (the "out of box experience") or afterwards.</span></span>

## <a name="during-setup-the-out-of-box-experience"></a><span data-ttu-id="08464-106">セットアップ中 ("アウト オブ ボックス エクスペリエンス")</span><span class="sxs-lookup"><span data-stu-id="08464-106">During setup (the "out of box experience")</span></span>

<span data-ttu-id="08464-107">セットアップの完了プロセス中に、ユーザーは選択した言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="08464-107">During the process of completing setup, users can select the language of their choice.</span></span> <span data-ttu-id="08464-108">この選択は、次の属性に影響します。</span><span class="sxs-lookup"><span data-stu-id="08464-108">This selection affects these attributes:</span></span>

- <span data-ttu-id="08464-109">Windows 10 言語の機能:</span><span class="sxs-lookup"><span data-stu-id="08464-109">Windows 10 language features:</span></span>
    - <span data-ttu-id="08464-110">表示言語</span><span class="sxs-lookup"><span data-stu-id="08464-110">Display language</span></span>
    - <span data-ttu-id="08464-111">キーボード言語</span><span class="sxs-lookup"><span data-stu-id="08464-111">Keyboard language</span></span>
    - <span data-ttu-id="08464-112">言語関連のオンデマンド機能</span><span class="sxs-lookup"><span data-stu-id="08464-112">Language-related Features on Demand</span></span>

- <span data-ttu-id="08464-113">Microsoft 365 Apps for Enterprise 言語機能:</span><span class="sxs-lookup"><span data-stu-id="08464-113">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="08464-114">表示言語</span><span class="sxs-lookup"><span data-stu-id="08464-114">Display language</span></span>
    - <span data-ttu-id="08464-115">校正ツールとオーサリング ツール</span><span class="sxs-lookup"><span data-stu-id="08464-115">Proofing and authoring tools</span></span>

> [!NOTE]
> <span data-ttu-id="08464-116">ユーザーは、セットアップ プロセス中に言語を選択して、言語関連の機能オンデマンドのみを取得できます。</span><span class="sxs-lookup"><span data-stu-id="08464-116">Users can only get language-related Features On Demand by selecting the language during the setup process.</span></span>

## <a name="after-completing-setup"></a><span data-ttu-id="08464-117">セットアップが完了した後</span><span class="sxs-lookup"><span data-stu-id="08464-117">After completing setup</span></span>

<span data-ttu-id="08464-118">ユーザーは、セットアップ プロセスが完了した後、いつでも Windows 10 および Microsoft 365 Apps for Enterprise の言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="08464-118">Users can select the language of their choice for Windows 10 and Microsoft 365 Apps for Enterprise anytime after the setup process is complete.</span></span> <span data-ttu-id="08464-119">具体的には次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="08464-119">Specifically:</span></span>

- <span data-ttu-id="08464-120">Windows 10 言語の機能:</span><span class="sxs-lookup"><span data-stu-id="08464-120">Windows 10 language features:</span></span>
    - <span data-ttu-id="08464-121">表示言語</span><span class="sxs-lookup"><span data-stu-id="08464-121">Display language</span></span>
    - <span data-ttu-id="08464-122">キーボード言語</span><span class="sxs-lookup"><span data-stu-id="08464-122">Keyboard language</span></span>

- <span data-ttu-id="08464-123">Microsoft 365 Apps for Enterprise 言語機能:</span><span class="sxs-lookup"><span data-stu-id="08464-123">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="08464-124">表示言語</span><span class="sxs-lookup"><span data-stu-id="08464-124">Display language</span></span>
    - <span data-ttu-id="08464-125">校正ツールとオーサリング ツール</span><span class="sxs-lookup"><span data-stu-id="08464-125">Proofing and authoring tools</span></span>

<span data-ttu-id="08464-126">ユーザーがインストール [](#supported-languages)できる Microsoft 365 Apps for Enterprise のサポート言語を使用するには、モダン **Workplace-Office-Language_Packs** グループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="08464-126">To make the [Supported languages](#supported-languages) for Microsoft 365 Apps for Enterprise available for your users to install, add the users to the **Modern Workplace-Office-Language_Packs** group.</span></span> <span data-ttu-id="08464-127">言語は Intune ポータル サイトで使用できます。</span><span class="sxs-lookup"><span data-stu-id="08464-127">The languages will be available in the Intune Company Portal.</span></span>


## <a name="supported-languages"></a><span data-ttu-id="08464-128">サポートされている言語</span><span class="sxs-lookup"><span data-stu-id="08464-128">Supported languages</span></span>

<span data-ttu-id="08464-129">新しいデバイスの場合、製造元は必要な言語を含むデバイス イメージを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08464-129">For new devices, your manufacturer must provide device images that include the languages you require.</span></span> <span data-ttu-id="08464-130">製造元のイメージに、サポートされている言語リストで提供されている言語以外の言語が含まれる場合は、サービスで引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="08464-130">If your manufacturer's image includes languages other than those provided in the supported languages list it is still supported by the service.</span></span>

<span data-ttu-id="08464-131">既存のデバイスを再利用する場合は、適切なイメージを取得するために Microsoft アカウント担当者と作業する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="08464-131">If you are reusing existing devices, you might need to work with your Microsoft account representative to obtain appropriate images.</span></span> <span data-ttu-id="08464-132">詳細については、「デバイス イメージ [」を参照してください](../service-description/device-images.md)。</span><span class="sxs-lookup"><span data-stu-id="08464-132">For more information, see [Device images](../service-description/device-images.md).</span></span>

<span data-ttu-id="08464-133">Microsoft [Managed](../service-description/device-images.md#universal-image) Desktop によって提供されるユニバーサル イメージには、次の言語と Windows 10 用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="08464-133">The [universal image](../service-description/device-images.md#universal-image) provided by Microsoft Managed Desktop includes these languages and for Windows 10:</span></span>

- <span data-ttu-id="08464-134">英語 (米国、GB、AU、CA、IN)</span><span class="sxs-lookup"><span data-stu-id="08464-134">English (US, GB, AU, CA, IN)</span></span>
- <span data-ttu-id="08464-135">スペイン語 (スペイン、メキシコ)</span><span class="sxs-lookup"><span data-stu-id="08464-135">Spanish (Spain, Mexico)</span></span>
- <span data-ttu-id="08464-136">日本語</span><span class="sxs-lookup"><span data-stu-id="08464-136">Japanese</span></span>
- <span data-ttu-id="08464-137">フランス語 (フランス、カナダ)</span><span class="sxs-lookup"><span data-stu-id="08464-137">French (France, Canada)</span></span>
- <span data-ttu-id="08464-138">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="08464-138">German</span></span>
- <span data-ttu-id="08464-139">ポルトガル語 (ブラジル)</span><span class="sxs-lookup"><span data-stu-id="08464-139">Portuguese (Brazil)</span></span>
- <span data-ttu-id="08464-140">イタリア語</span><span class="sxs-lookup"><span data-stu-id="08464-140">Italian</span></span>
- <span data-ttu-id="08464-141">Chinese Simplified</span><span class="sxs-lookup"><span data-stu-id="08464-141">Chinese Simplified</span></span>
- <span data-ttu-id="08464-142">オランダ語</span><span class="sxs-lookup"><span data-stu-id="08464-142">Dutch</span></span>  
- <span data-ttu-id="08464-143">スウェーデン語</span><span class="sxs-lookup"><span data-stu-id="08464-143">Swedish</span></span>
- <span data-ttu-id="08464-144">デンマーク語</span><span class="sxs-lookup"><span data-stu-id="08464-144">Danish</span></span>  
- <span data-ttu-id="08464-145">フィンランド語</span><span class="sxs-lookup"><span data-stu-id="08464-145">Finnish</span></span> 
- <span data-ttu-id="08464-146">ロシア語</span><span class="sxs-lookup"><span data-stu-id="08464-146">Russian</span></span> 
- <span data-ttu-id="08464-147">ノルウェー語 (ブークモール)</span><span class="sxs-lookup"><span data-stu-id="08464-147">Norwegian (Bokmal)</span></span>
- <span data-ttu-id="08464-148">韓国語</span><span class="sxs-lookup"><span data-stu-id="08464-148">Korean</span></span>
- <span data-ttu-id="08464-149">Chinese Traditional</span><span class="sxs-lookup"><span data-stu-id="08464-149">Chinese Traditional</span></span>
- <span data-ttu-id="08464-150">ポーランド語</span><span class="sxs-lookup"><span data-stu-id="08464-150">Polish</span></span>
- <span data-ttu-id="08464-151">トルコ語</span><span class="sxs-lookup"><span data-stu-id="08464-151">Turkish</span></span>
- <span data-ttu-id="08464-152">アラビア語</span><span class="sxs-lookup"><span data-stu-id="08464-152">Arabic</span></span>
- <span data-ttu-id="08464-153">ヘブライ語</span><span class="sxs-lookup"><span data-stu-id="08464-153">Hebrew</span></span>
- <span data-ttu-id="08464-154">ポルトガル語 (ポルトガル)</span><span class="sxs-lookup"><span data-stu-id="08464-154">Portuguese (Portugal)</span></span>
- <span data-ttu-id="08464-155">チェコ語</span><span class="sxs-lookup"><span data-stu-id="08464-155">Czech</span></span>
- <span data-ttu-id="08464-156">ハンガリー語</span><span class="sxs-lookup"><span data-stu-id="08464-156">Hungarian</span></span>
- <span data-ttu-id="08464-157">タイ語</span><span class="sxs-lookup"><span data-stu-id="08464-157">Thai</span></span>
- <span data-ttu-id="08464-158">インドネシア語</span><span class="sxs-lookup"><span data-stu-id="08464-158">Indonesian</span></span>
- <span data-ttu-id="08464-159">ギリシャ語</span><span class="sxs-lookup"><span data-stu-id="08464-159">Greek</span></span>
- <span data-ttu-id="08464-160">スロバキア語</span><span class="sxs-lookup"><span data-stu-id="08464-160">Slovak</span></span>
- <span data-ttu-id="08464-161">ベトナム語</span><span class="sxs-lookup"><span data-stu-id="08464-161">Vietnamese</span></span>
- <span data-ttu-id="08464-162">スロベニア語</span><span class="sxs-lookup"><span data-stu-id="08464-162">Slovenian</span></span>
- <span data-ttu-id="08464-163">クロアチア語</span><span class="sxs-lookup"><span data-stu-id="08464-163">Croatian</span></span>
- <span data-ttu-id="08464-164">ルーマニア語</span><span class="sxs-lookup"><span data-stu-id="08464-164">Romanian</span></span>
- <span data-ttu-id="08464-165">リトアニア語</span><span class="sxs-lookup"><span data-stu-id="08464-165">Lithuanian</span></span>
- <span data-ttu-id="08464-166">ブルガリア語</span><span class="sxs-lookup"><span data-stu-id="08464-166">Bulgarian</span></span>
- <span data-ttu-id="08464-167">セルビア語 (ラテン文字)</span><span class="sxs-lookup"><span data-stu-id="08464-167">Serbian (Latin alphabet)</span></span>
- <span data-ttu-id="08464-168">ラトビア語</span><span class="sxs-lookup"><span data-stu-id="08464-168">Latvian</span></span>
- <span data-ttu-id="08464-169">ウクライナ語</span><span class="sxs-lookup"><span data-stu-id="08464-169">Ukrainian</span></span>
- <span data-ttu-id="08464-170">エストニア語</span><span class="sxs-lookup"><span data-stu-id="08464-170">Estonian</span></span>

<span data-ttu-id="08464-171">Microsoft 365 Apps for Enterprise では、若干異なるリストがサポートされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="08464-171">Microsoft 365 Apps for Enterprise might support a slightly different list.</span></span>

<span data-ttu-id="08464-172">ユーザーがここに示す言語以外の言語が必要な場合は、管理ポータル[](../working-with-managed-desktop/admin-support.md)を使用してサポート要求を[送信します](access-admin-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="08464-172">If your users need a language other than the ones listed here, file a [support request](../working-with-managed-desktop/admin-support.md) by using the [Admin portal](access-admin-portal.md).</span></span>

## <a name="languages-for-support-and-operations"></a><span data-ttu-id="08464-173">サポートと操作の言語</span><span class="sxs-lookup"><span data-stu-id="08464-173">Languages for support and operations</span></span>

### <a name="user-support"></a><span data-ttu-id="08464-174">ユーザー サポート</span><span class="sxs-lookup"><span data-stu-id="08464-174">User support</span></span>
<span data-ttu-id="08464-175">Microsoft Managed Desktop は英語でのみサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="08464-175">Microsoft Managed Desktop provides support only in English.</span></span> <span data-ttu-id="08464-176">ユーザーがヘルプ アプリで別の言語を選択した場合、Microsoft Managed Desktop から直接サポートするのではなく、一般的な Microsoft サポート チャネルからサポートを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="08464-176">If users choose another language in the Get Help app, they will get support from the general Microsoft support channels, rather than support directly from Microsoft Managed Desktop.</span></span> <span data-ttu-id="08464-177">詳細については [、「Getting help for users 」を参照してください](../working-with-managed-desktop/end-user-support.md)。</span><span class="sxs-lookup"><span data-stu-id="08464-177">For more information, see [Getting help for users](../working-with-managed-desktop/end-user-support.md).</span></span>

<span data-ttu-id="08464-178">ユーザーが他の言語でサポートを必要とする場合は、Microsoft 以外のサポート ソースまたは独自の組織からサポートを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08464-178">If your users need support in other languages, you'll have to provide that through non-Microsoft support sources or from your own organization.</span></span>

### <a name="admin-support-and-operations"></a><span data-ttu-id="08464-179">管理者のサポートと操作</span><span class="sxs-lookup"><span data-stu-id="08464-179">Admin support and operations</span></span>
<span data-ttu-id="08464-180">Microsoft Managed Desktop は、英語でのみ管理者サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="08464-180">Microsoft Managed Desktop provides admin support only in English.</span></span> <span data-ttu-id="08464-181">これには、管理ポータルと Microsoft Managed Desktop Operations とのすべての通信が含まれます。</span><span class="sxs-lookup"><span data-stu-id="08464-181">This includes the Admin portal and all communications with Microsoft Managed Desktop Operations.</span></span> <span data-ttu-id="08464-182">特に指定がない限り、すべての管理者関連の操作とインターフェイスは英語で行われます。</span><span class="sxs-lookup"><span data-stu-id="08464-182">You should assume that all admin-related interactions and interfaces will be in English, unless specified otherwise.</span></span>


