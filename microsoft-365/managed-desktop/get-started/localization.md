---
title: ユーザー エクスペリエンスをローカライズ
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
ms.openlocfilehash: 354f61284bbd95c1c7ca4cd50459a1644a89d090
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023263"
---
# <a name="localize-the-user-experience"></a><span data-ttu-id="419f0-104">ユーザー エクスペリエンスをローカライズ</span><span class="sxs-lookup"><span data-stu-id="419f0-104">Localize the user experience</span></span>

<span data-ttu-id="419f0-105">Microsoft Managed Desktop デバイスのユーザーは、セットアップ プロセス ("すぐに使用できる") または後で、選択した言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="419f0-105">Users of Microsoft Managed Desktop devices can select the language of their choice either during the setup process (the "out of box experience") or afterwards.</span></span>

## <a name="during-setup-the-out-of-box-experience"></a><span data-ttu-id="419f0-106">セットアップ中 ("アウト オブ ボックス エクスペリエンス")</span><span class="sxs-lookup"><span data-stu-id="419f0-106">During setup (the "out of box experience")</span></span>

<span data-ttu-id="419f0-107">セットアップの完了プロセス中に、ユーザーは選択した言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="419f0-107">During the process of completing setup, users can select the language of their choice.</span></span> <span data-ttu-id="419f0-108">この選択は、次の属性に影響します。</span><span class="sxs-lookup"><span data-stu-id="419f0-108">This selection affects these attributes:</span></span>

- <span data-ttu-id="419f0-109">Windows 10 言語の機能:</span><span class="sxs-lookup"><span data-stu-id="419f0-109">Windows 10 language features:</span></span>
    - <span data-ttu-id="419f0-110">表示言語</span><span class="sxs-lookup"><span data-stu-id="419f0-110">Display language</span></span>
    - <span data-ttu-id="419f0-111">キーボード言語</span><span class="sxs-lookup"><span data-stu-id="419f0-111">Keyboard language</span></span>
    - <span data-ttu-id="419f0-112">言語関連のオンデマンド機能</span><span class="sxs-lookup"><span data-stu-id="419f0-112">Language-related Features on Demand</span></span>

- <span data-ttu-id="419f0-113">Microsoft 365 Apps for Enterprise 言語機能:</span><span class="sxs-lookup"><span data-stu-id="419f0-113">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="419f0-114">表示言語</span><span class="sxs-lookup"><span data-stu-id="419f0-114">Display language</span></span>
    - <span data-ttu-id="419f0-115">校正ツールとオーサリング ツール</span><span class="sxs-lookup"><span data-stu-id="419f0-115">Proofing and authoring tools</span></span>

> [!NOTE]
> <span data-ttu-id="419f0-116">ユーザーは、セットアップ プロセス中に言語を選択して、言語関連の機能オンデマンドのみを取得できます。</span><span class="sxs-lookup"><span data-stu-id="419f0-116">Users can only get language-related Features On Demand by selecting the language during the setup process.</span></span>

## <a name="after-completing-setup"></a><span data-ttu-id="419f0-117">セットアップが完了した後</span><span class="sxs-lookup"><span data-stu-id="419f0-117">After completing setup</span></span>

<span data-ttu-id="419f0-118">ユーザーは、セットアップ プロセスが完了した後、いつでも Windows 10 および Microsoft 365 Apps for Enterprise の言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="419f0-118">Users can select the language of their choice for Windows 10 and Microsoft 365 Apps for Enterprise anytime after the setup process is complete.</span></span> <span data-ttu-id="419f0-119">具体的には次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="419f0-119">Specifically:</span></span>

- <span data-ttu-id="419f0-120">Windows 10 言語の機能:</span><span class="sxs-lookup"><span data-stu-id="419f0-120">Windows 10 language features:</span></span>
    - <span data-ttu-id="419f0-121">表示言語</span><span class="sxs-lookup"><span data-stu-id="419f0-121">Display language</span></span>
    - <span data-ttu-id="419f0-122">キーボード言語</span><span class="sxs-lookup"><span data-stu-id="419f0-122">Keyboard language</span></span>

- <span data-ttu-id="419f0-123">Microsoft 365 Apps for Enterprise 言語機能:</span><span class="sxs-lookup"><span data-stu-id="419f0-123">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="419f0-124">表示言語</span><span class="sxs-lookup"><span data-stu-id="419f0-124">Display language</span></span>
    - <span data-ttu-id="419f0-125">校正ツールとオーサリング ツール</span><span class="sxs-lookup"><span data-stu-id="419f0-125">Proofing and authoring tools</span></span>

<span data-ttu-id="419f0-126">ユーザーがインストール [](#supported-languages)できる Microsoft 365 Apps for Enterprise のサポート言語を使用するには、モダン **Workplace-Office-Language_Packs** グループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="419f0-126">To make the [Supported languages](#supported-languages) for Microsoft 365 Apps for Enterprise available for your users to install, add the users to the **Modern Workplace-Office-Language_Packs** group.</span></span> <span data-ttu-id="419f0-127">言語は Intune ポータル サイトで使用できます。</span><span class="sxs-lookup"><span data-stu-id="419f0-127">The languages will be available in the Intune Company Portal.</span></span>


## <a name="supported-languages"></a><span data-ttu-id="419f0-128">サポートされている言語</span><span class="sxs-lookup"><span data-stu-id="419f0-128">Supported languages</span></span>

<span data-ttu-id="419f0-129">新しいデバイスの場合、製造元は必要な言語を含むデバイス イメージを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="419f0-129">For new devices, your manufacturer must provide device images that include the languages you require.</span></span> <span data-ttu-id="419f0-130">製造元のイメージに、サポートされている言語リストで提供されている言語以外の言語が含まれる場合は、サービスで引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="419f0-130">If your manufacturer's image includes languages other than those provided in the supported languages list it is still supported by the service.</span></span>

<span data-ttu-id="419f0-131">既存のデバイスを再利用する場合は、適切なイメージを取得するために Microsoft アカウント担当者と作業する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="419f0-131">If you are reusing existing devices, you might need to work with your Microsoft account representative to obtain appropriate images.</span></span> <span data-ttu-id="419f0-132">詳細については、「デバイス イメージ [」を参照してください](../service-description/device-images.md)。</span><span class="sxs-lookup"><span data-stu-id="419f0-132">For more information, see [Device images](../service-description/device-images.md).</span></span>

<span data-ttu-id="419f0-133">Microsoft [Managed](../service-description/device-images.md#universal-image) Desktop によって提供されるユニバーサル イメージには、次の言語と Windows 10 用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="419f0-133">The [universal image](../service-description/device-images.md#universal-image) provided by Microsoft Managed Desktop includes these languages and for Windows 10:</span></span>

- <span data-ttu-id="419f0-134">アラビア語</span><span class="sxs-lookup"><span data-stu-id="419f0-134">Arabic</span></span>
- <span data-ttu-id="419f0-135">ブルガリア語</span><span class="sxs-lookup"><span data-stu-id="419f0-135">Bulgarian</span></span>
- <span data-ttu-id="419f0-136">中国語 (簡体字)</span><span class="sxs-lookup"><span data-stu-id="419f0-136">Chinese Simplified</span></span>
- <span data-ttu-id="419f0-137">中国語 (繁体字)</span><span class="sxs-lookup"><span data-stu-id="419f0-137">Chinese Traditional</span></span>
- <span data-ttu-id="419f0-138">クロアチア語</span><span class="sxs-lookup"><span data-stu-id="419f0-138">Croatian</span></span>
- <span data-ttu-id="419f0-139">チェコ語</span><span class="sxs-lookup"><span data-stu-id="419f0-139">Czech</span></span>
- <span data-ttu-id="419f0-140">デンマーク語</span><span class="sxs-lookup"><span data-stu-id="419f0-140">Danish</span></span>  
- <span data-ttu-id="419f0-141">オランダ語</span><span class="sxs-lookup"><span data-stu-id="419f0-141">Dutch</span></span>  
- <span data-ttu-id="419f0-142">英語 (米国、GB、AU、CA、IN)</span><span class="sxs-lookup"><span data-stu-id="419f0-142">English (US, GB, AU, CA, IN)</span></span>
- <span data-ttu-id="419f0-143">エストニア語</span><span class="sxs-lookup"><span data-stu-id="419f0-143">Estonian</span></span>
- <span data-ttu-id="419f0-144">フィンランド語</span><span class="sxs-lookup"><span data-stu-id="419f0-144">Finnish</span></span> 
- <span data-ttu-id="419f0-145">フランス語 (フランス、カナダ)</span><span class="sxs-lookup"><span data-stu-id="419f0-145">French (France, Canada)</span></span>
- <span data-ttu-id="419f0-146">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="419f0-146">German</span></span>
- <span data-ttu-id="419f0-147">ギリシャ語</span><span class="sxs-lookup"><span data-stu-id="419f0-147">Greek</span></span>
- <span data-ttu-id="419f0-148">ヘブライ語</span><span class="sxs-lookup"><span data-stu-id="419f0-148">Hebrew</span></span>
- <span data-ttu-id="419f0-149">ハンガリー語</span><span class="sxs-lookup"><span data-stu-id="419f0-149">Hungarian</span></span>
- <span data-ttu-id="419f0-150">インドネシア語</span><span class="sxs-lookup"><span data-stu-id="419f0-150">Indonesian</span></span>
- <span data-ttu-id="419f0-151">イタリア語</span><span class="sxs-lookup"><span data-stu-id="419f0-151">Italian</span></span>
- <span data-ttu-id="419f0-152">日本語</span><span class="sxs-lookup"><span data-stu-id="419f0-152">Japanese</span></span>
- <span data-ttu-id="419f0-153">韓国語</span><span class="sxs-lookup"><span data-stu-id="419f0-153">Korean</span></span>
- <span data-ttu-id="419f0-154">ラトビア語</span><span class="sxs-lookup"><span data-stu-id="419f0-154">Latvian</span></span>
- <span data-ttu-id="419f0-155">リトアニア語</span><span class="sxs-lookup"><span data-stu-id="419f0-155">Lithuanian</span></span>
- <span data-ttu-id="419f0-156">ノルウェー語 (ブークモール)</span><span class="sxs-lookup"><span data-stu-id="419f0-156">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="419f0-157">ポーランド語</span><span class="sxs-lookup"><span data-stu-id="419f0-157">Polish</span></span>
- <span data-ttu-id="419f0-158">ポルトガル語 (ブラジル)</span><span class="sxs-lookup"><span data-stu-id="419f0-158">Portuguese (Brazil)</span></span>
- <span data-ttu-id="419f0-159">ポルトガル語 (ポルトガル)</span><span class="sxs-lookup"><span data-stu-id="419f0-159">Portuguese (Portugal)</span></span>
- <span data-ttu-id="419f0-160">ルーマニア語</span><span class="sxs-lookup"><span data-stu-id="419f0-160">Romanian</span></span>
- <span data-ttu-id="419f0-161">ロシア語</span><span class="sxs-lookup"><span data-stu-id="419f0-161">Russian</span></span> 
- <span data-ttu-id="419f0-162">セルビア語 (ラテン文字)</span><span class="sxs-lookup"><span data-stu-id="419f0-162">Serbian (Latin alphabet)</span></span>
- <span data-ttu-id="419f0-163">スロバキア語</span><span class="sxs-lookup"><span data-stu-id="419f0-163">Slovak</span></span>
- <span data-ttu-id="419f0-164">スロベニア語</span><span class="sxs-lookup"><span data-stu-id="419f0-164">Slovenian</span></span>
- <span data-ttu-id="419f0-165">スペイン語 (スペイン、メキシコ)</span><span class="sxs-lookup"><span data-stu-id="419f0-165">Spanish (Spain, Mexico)</span></span>
- <span data-ttu-id="419f0-166">スウェーデン語</span><span class="sxs-lookup"><span data-stu-id="419f0-166">Swedish</span></span>
- <span data-ttu-id="419f0-167">タイ語</span><span class="sxs-lookup"><span data-stu-id="419f0-167">Thai</span></span>
- <span data-ttu-id="419f0-168">トルコ語</span><span class="sxs-lookup"><span data-stu-id="419f0-168">Turkish</span></span>
- <span data-ttu-id="419f0-169">ウクライナ語</span><span class="sxs-lookup"><span data-stu-id="419f0-169">Ukrainian</span></span>
- <span data-ttu-id="419f0-170">ベトナム語</span><span class="sxs-lookup"><span data-stu-id="419f0-170">Vietnamese</span></span>

<span data-ttu-id="419f0-171">Microsoft 365 Apps for Enterprise では、若干異なるリストがサポートされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="419f0-171">Microsoft 365 Apps for Enterprise might support a slightly different list.</span></span>

<span data-ttu-id="419f0-172">ユーザーがここに示す言語以外の言語が必要な場合は、管理ポータル[](../working-with-managed-desktop/admin-support.md)を使用してサポート要求を[送信します](access-admin-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="419f0-172">If your users need a language other than the ones listed here, file a [support request](../working-with-managed-desktop/admin-support.md) by using the [Admin portal](access-admin-portal.md).</span></span>

## <a name="languages-for-support-and-operations"></a><span data-ttu-id="419f0-173">サポートと操作の言語</span><span class="sxs-lookup"><span data-stu-id="419f0-173">Languages for support and operations</span></span>

### <a name="user-support"></a><span data-ttu-id="419f0-174">ユーザー サポート</span><span class="sxs-lookup"><span data-stu-id="419f0-174">User support</span></span>
<span data-ttu-id="419f0-175">Microsoft Managed Desktop は英語でのみサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="419f0-175">Microsoft Managed Desktop provides support only in English.</span></span> <span data-ttu-id="419f0-176">ユーザーがヘルプ アプリで別の言語を選択した場合、Microsoft Managed Desktop から直接サポートするのではなく、一般的な Microsoft サポート チャネルからサポートを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="419f0-176">If users choose another language in the Get Help app, they will get support from the general Microsoft support channels, rather than support directly from Microsoft Managed Desktop.</span></span> <span data-ttu-id="419f0-177">詳細については [、「Getting help for users 」を参照してください](../working-with-managed-desktop/end-user-support.md)。</span><span class="sxs-lookup"><span data-stu-id="419f0-177">For more information, see [Getting help for users](../working-with-managed-desktop/end-user-support.md).</span></span>

<span data-ttu-id="419f0-178">ユーザーが他の言語でサポートを必要とする場合は、Microsoft 以外のサポート ソースまたは独自の組織からサポートを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="419f0-178">If your users need support in other languages, you'll have to provide that through non-Microsoft support sources or from your own organization.</span></span>

### <a name="admin-support-and-operations"></a><span data-ttu-id="419f0-179">管理者のサポートと操作</span><span class="sxs-lookup"><span data-stu-id="419f0-179">Admin support and operations</span></span>
<span data-ttu-id="419f0-180">Microsoft Managed Desktop は、英語でのみ管理者サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="419f0-180">Microsoft Managed Desktop provides admin support only in English.</span></span> <span data-ttu-id="419f0-181">これには、管理ポータルと Microsoft Managed Desktop Operations とのすべての通信が含まれます。</span><span class="sxs-lookup"><span data-stu-id="419f0-181">This includes the Admin portal and all communications with Microsoft Managed Desktop Operations.</span></span> <span data-ttu-id="419f0-182">特に指定がない限り、すべての管理者関連の操作とインターフェイスは英語で行われます。</span><span class="sxs-lookup"><span data-stu-id="419f0-182">You should assume that all admin-related interactions and interfaces will be in English, unless specified otherwise.</span></span>


