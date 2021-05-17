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
# <a name="localize-the-user-experience"></a><span data-ttu-id="8ad81-104">ユーザー エクスペリエンスをローカライズ</span><span class="sxs-lookup"><span data-stu-id="8ad81-104">Localize the user experience</span></span>

<span data-ttu-id="8ad81-105">デバイスのMicrosoft マネージド デスクトップは、セットアップ プロセス ("すぐに使用できる") または後で、選択した言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8ad81-105">Users of Microsoft Managed Desktop devices can select the language of their choice either during the setup process (the "out of box experience") or afterwards.</span></span>

## <a name="during-setup-the-out-of-box-experience"></a><span data-ttu-id="8ad81-106">セットアップ中 ("アウト オブ ボックス エクスペリエンス")</span><span class="sxs-lookup"><span data-stu-id="8ad81-106">During setup (the "out of box experience")</span></span>

<span data-ttu-id="8ad81-107">セットアップの完了プロセス中に、ユーザーは選択した言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8ad81-107">During the process of completing setup, users can select the language of their choice.</span></span> <span data-ttu-id="8ad81-108">この選択は、次の属性に影響します。</span><span class="sxs-lookup"><span data-stu-id="8ad81-108">This selection affects these attributes:</span></span>

- <span data-ttu-id="8ad81-109">Windows 10機能:</span><span class="sxs-lookup"><span data-stu-id="8ad81-109">Windows 10 language features:</span></span>
    - <span data-ttu-id="8ad81-110">表示言語</span><span class="sxs-lookup"><span data-stu-id="8ad81-110">Display language</span></span>
    - <span data-ttu-id="8ad81-111">キーボード言語</span><span class="sxs-lookup"><span data-stu-id="8ad81-111">Keyboard language</span></span>
    - <span data-ttu-id="8ad81-112">言語関連のオンデマンド機能</span><span class="sxs-lookup"><span data-stu-id="8ad81-112">Language-related Features on Demand</span></span>

- <span data-ttu-id="8ad81-113">Microsoft 365 Apps機能Enterprise次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ad81-113">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="8ad81-114">表示言語</span><span class="sxs-lookup"><span data-stu-id="8ad81-114">Display language</span></span>
    - <span data-ttu-id="8ad81-115">校正ツールとオーサリング ツール</span><span class="sxs-lookup"><span data-stu-id="8ad81-115">Proofing and authoring tools</span></span>

> [!NOTE]
> <span data-ttu-id="8ad81-116">ユーザーは、セットアップ プロセス中に言語を選択して、言語関連の機能オンデマンドのみを取得できます。</span><span class="sxs-lookup"><span data-stu-id="8ad81-116">Users can only get language-related Features On Demand by selecting the language during the setup process.</span></span>

## <a name="after-completing-setup"></a><span data-ttu-id="8ad81-117">セットアップが完了した後</span><span class="sxs-lookup"><span data-stu-id="8ad81-117">After completing setup</span></span>

<span data-ttu-id="8ad81-118">ユーザーは、セットアップ プロセスが完了した後Windows 10、Microsoft 365 AppsのEnterprise言語を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8ad81-118">Users can select the language of their choice for Windows 10 and Microsoft 365 Apps for Enterprise anytime after the setup process is complete.</span></span> <span data-ttu-id="8ad81-119">具体的には次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ad81-119">Specifically:</span></span>

- <span data-ttu-id="8ad81-120">Windows 10機能:</span><span class="sxs-lookup"><span data-stu-id="8ad81-120">Windows 10 language features:</span></span>
    - <span data-ttu-id="8ad81-121">表示言語</span><span class="sxs-lookup"><span data-stu-id="8ad81-121">Display language</span></span>
    - <span data-ttu-id="8ad81-122">キーボード言語</span><span class="sxs-lookup"><span data-stu-id="8ad81-122">Keyboard language</span></span>

- <span data-ttu-id="8ad81-123">Microsoft 365 Apps機能Enterprise次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ad81-123">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="8ad81-124">表示言語</span><span class="sxs-lookup"><span data-stu-id="8ad81-124">Display language</span></span>
    - <span data-ttu-id="8ad81-125">校正ツールとオーサリング ツール</span><span class="sxs-lookup"><span data-stu-id="8ad81-125">Proofing and authoring tools</span></span>

<span data-ttu-id="8ad81-126">ユーザーがインストール [できる](#supported-languages)Microsoft 365 Apps Microsoft 365 Apps Enterprise のサポートされている言語を使用するには、モダン **Workplace-Office-Language_Packs** グループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8ad81-126">To make the [Supported languages](#supported-languages) for Microsoft 365 Apps for Enterprise available for your users to install, add the users to the **Modern Workplace-Office-Language_Packs** group.</span></span> <span data-ttu-id="8ad81-127">言語は、次のIntune ポータル サイト。</span><span class="sxs-lookup"><span data-stu-id="8ad81-127">The languages will be available in the Intune Company Portal.</span></span>


## <a name="supported-languages"></a><span data-ttu-id="8ad81-128">サポートされている言語</span><span class="sxs-lookup"><span data-stu-id="8ad81-128">Supported languages</span></span>

<span data-ttu-id="8ad81-129">新しいデバイスの場合、製造元は必要な言語を含むデバイス イメージを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ad81-129">For new devices, your manufacturer must provide device images that include the languages you require.</span></span> <span data-ttu-id="8ad81-130">製造元のイメージに、サポートされている言語リストで提供されている言語以外の言語が含まれる場合は、サービスで引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8ad81-130">If your manufacturer's image includes languages other than those provided in the supported languages list it is still supported by the service.</span></span>

<span data-ttu-id="8ad81-131">既存のデバイスを再利用する場合は、適切なイメージを取得するために Microsoft アカウント担当者と作業する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ad81-131">If you are reusing existing devices, you might need to work with your Microsoft account representative to obtain appropriate images.</span></span> <span data-ttu-id="8ad81-132">詳細については、「デバイス イメージ [」を参照してください](../service-description/device-images.md)。</span><span class="sxs-lookup"><span data-stu-id="8ad81-132">For more information, see [Device images](../service-description/device-images.md).</span></span>

<span data-ttu-id="8ad81-133">ユーザー[が提供する](../service-description/device-images.md#universal-image)ユニバーサル Microsoft マネージド デスクトップには、次の言語と次のWindows 10。</span><span class="sxs-lookup"><span data-stu-id="8ad81-133">The [universal image](../service-description/device-images.md#universal-image) provided by Microsoft Managed Desktop includes these languages and for Windows 10:</span></span>

- <span data-ttu-id="8ad81-134">アラビア語</span><span class="sxs-lookup"><span data-stu-id="8ad81-134">Arabic</span></span>
- <span data-ttu-id="8ad81-135">ブルガリア語</span><span class="sxs-lookup"><span data-stu-id="8ad81-135">Bulgarian</span></span>
- <span data-ttu-id="8ad81-136">中国語 (簡体字)</span><span class="sxs-lookup"><span data-stu-id="8ad81-136">Chinese Simplified</span></span>
- <span data-ttu-id="8ad81-137">中国語 (繁体字)</span><span class="sxs-lookup"><span data-stu-id="8ad81-137">Chinese Traditional</span></span>
- <span data-ttu-id="8ad81-138">クロアチア語</span><span class="sxs-lookup"><span data-stu-id="8ad81-138">Croatian</span></span>
- <span data-ttu-id="8ad81-139">チェコ語</span><span class="sxs-lookup"><span data-stu-id="8ad81-139">Czech</span></span>
- <span data-ttu-id="8ad81-140">デンマーク語</span><span class="sxs-lookup"><span data-stu-id="8ad81-140">Danish</span></span>  
- <span data-ttu-id="8ad81-141">オランダ語</span><span class="sxs-lookup"><span data-stu-id="8ad81-141">Dutch</span></span>  
- <span data-ttu-id="8ad81-142">英語 (米国、GB、AU、CA、IN)</span><span class="sxs-lookup"><span data-stu-id="8ad81-142">English (US, GB, AU, CA, IN)</span></span>
- <span data-ttu-id="8ad81-143">エストニア語</span><span class="sxs-lookup"><span data-stu-id="8ad81-143">Estonian</span></span>
- <span data-ttu-id="8ad81-144">フィンランド語</span><span class="sxs-lookup"><span data-stu-id="8ad81-144">Finnish</span></span> 
- <span data-ttu-id="8ad81-145">フランス語 (フランス、カナダ)</span><span class="sxs-lookup"><span data-stu-id="8ad81-145">French (France, Canada)</span></span>
- <span data-ttu-id="8ad81-146">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="8ad81-146">German</span></span>
- <span data-ttu-id="8ad81-147">ギリシャ語</span><span class="sxs-lookup"><span data-stu-id="8ad81-147">Greek</span></span>
- <span data-ttu-id="8ad81-148">ヘブライ語</span><span class="sxs-lookup"><span data-stu-id="8ad81-148">Hebrew</span></span>
- <span data-ttu-id="8ad81-149">ハンガリー語</span><span class="sxs-lookup"><span data-stu-id="8ad81-149">Hungarian</span></span>
- <span data-ttu-id="8ad81-150">インドネシア語</span><span class="sxs-lookup"><span data-stu-id="8ad81-150">Indonesian</span></span>
- <span data-ttu-id="8ad81-151">イタリア語</span><span class="sxs-lookup"><span data-stu-id="8ad81-151">Italian</span></span>
- <span data-ttu-id="8ad81-152">日本語</span><span class="sxs-lookup"><span data-stu-id="8ad81-152">Japanese</span></span>
- <span data-ttu-id="8ad81-153">韓国語</span><span class="sxs-lookup"><span data-stu-id="8ad81-153">Korean</span></span>
- <span data-ttu-id="8ad81-154">ラトビア語</span><span class="sxs-lookup"><span data-stu-id="8ad81-154">Latvian</span></span>
- <span data-ttu-id="8ad81-155">リトアニア語</span><span class="sxs-lookup"><span data-stu-id="8ad81-155">Lithuanian</span></span>
- <span data-ttu-id="8ad81-156">ノルウェー語 (ブークモール)</span><span class="sxs-lookup"><span data-stu-id="8ad81-156">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="8ad81-157">ポーランド語</span><span class="sxs-lookup"><span data-stu-id="8ad81-157">Polish</span></span>
- <span data-ttu-id="8ad81-158">ポルトガル語 (ブラジル)</span><span class="sxs-lookup"><span data-stu-id="8ad81-158">Portuguese (Brazil)</span></span>
- <span data-ttu-id="8ad81-159">ポルトガル語 (ポルトガル)</span><span class="sxs-lookup"><span data-stu-id="8ad81-159">Portuguese (Portugal)</span></span>
- <span data-ttu-id="8ad81-160">ルーマニア語</span><span class="sxs-lookup"><span data-stu-id="8ad81-160">Romanian</span></span>
- <span data-ttu-id="8ad81-161">ロシア語</span><span class="sxs-lookup"><span data-stu-id="8ad81-161">Russian</span></span> 
- <span data-ttu-id="8ad81-162">セルビア語 (ラテン文字)</span><span class="sxs-lookup"><span data-stu-id="8ad81-162">Serbian (Latin alphabet)</span></span>
- <span data-ttu-id="8ad81-163">スロバキア語</span><span class="sxs-lookup"><span data-stu-id="8ad81-163">Slovak</span></span>
- <span data-ttu-id="8ad81-164">スロベニア語</span><span class="sxs-lookup"><span data-stu-id="8ad81-164">Slovenian</span></span>
- <span data-ttu-id="8ad81-165">スペイン語 (スペイン、メキシコ)</span><span class="sxs-lookup"><span data-stu-id="8ad81-165">Spanish (Spain, Mexico)</span></span>
- <span data-ttu-id="8ad81-166">スウェーデン語</span><span class="sxs-lookup"><span data-stu-id="8ad81-166">Swedish</span></span>
- <span data-ttu-id="8ad81-167">タイ語</span><span class="sxs-lookup"><span data-stu-id="8ad81-167">Thai</span></span>
- <span data-ttu-id="8ad81-168">トルコ語</span><span class="sxs-lookup"><span data-stu-id="8ad81-168">Turkish</span></span>
- <span data-ttu-id="8ad81-169">ウクライナ語</span><span class="sxs-lookup"><span data-stu-id="8ad81-169">Ukrainian</span></span>
- <span data-ttu-id="8ad81-170">ベトナム語</span><span class="sxs-lookup"><span data-stu-id="8ad81-170">Vietnamese</span></span>

<span data-ttu-id="8ad81-171">Microsoft 365 AppsのEnterprise、少し異なるリストをサポートしている場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ad81-171">Microsoft 365 Apps for Enterprise might support a slightly different list.</span></span>

<span data-ttu-id="8ad81-172">ユーザーがここに示す言語以外の言語が必要な場合は、管理ポータル[](../working-with-managed-desktop/admin-support.md)を使用してサポート要求を[送信します](access-admin-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="8ad81-172">If your users need a language other than the ones listed here, file a [support request](../working-with-managed-desktop/admin-support.md) by using the [Admin portal](access-admin-portal.md).</span></span>

## <a name="languages-for-support-and-operations"></a><span data-ttu-id="8ad81-173">サポートと操作の言語</span><span class="sxs-lookup"><span data-stu-id="8ad81-173">Languages for support and operations</span></span>

### <a name="user-support"></a><span data-ttu-id="8ad81-174">ユーザー サポート</span><span class="sxs-lookup"><span data-stu-id="8ad81-174">User support</span></span>
<span data-ttu-id="8ad81-175">Microsoft マネージド デスクトップは英語でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8ad81-175">Microsoft Managed Desktop provides support only in English.</span></span> <span data-ttu-id="8ad81-176">ユーザーがアプリで別の言語を問い合わせ場合、ユーザーは一般的な Microsoft サポート チャネルから直接サポートするのではなく、サポートを受Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="8ad81-176">If users choose another language in the Get Help app, they will get support from the general Microsoft support channels, rather than support directly from Microsoft Managed Desktop.</span></span> <span data-ttu-id="8ad81-177">詳細については [、「Getting help for users 」を参照してください](../working-with-managed-desktop/end-user-support.md)。</span><span class="sxs-lookup"><span data-stu-id="8ad81-177">For more information, see [Getting help for users](../working-with-managed-desktop/end-user-support.md).</span></span>

<span data-ttu-id="8ad81-178">ユーザーが他の言語でサポートを必要とする場合は、Microsoft 以外のサポート ソースまたは独自の組織からサポートを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ad81-178">If your users need support in other languages, you'll have to provide that through non-Microsoft support sources or from your own organization.</span></span>

### <a name="admin-support-and-operations"></a><span data-ttu-id="8ad81-179">管理者のサポートと操作</span><span class="sxs-lookup"><span data-stu-id="8ad81-179">Admin support and operations</span></span>
<span data-ttu-id="8ad81-180">Microsoft マネージド デスクトップは英語でのみ管理者サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="8ad81-180">Microsoft Managed Desktop provides admin support only in English.</span></span> <span data-ttu-id="8ad81-181">これには、管理ポータルと、管理操作との通信Microsoft マネージド デスクトップ含まれます。</span><span class="sxs-lookup"><span data-stu-id="8ad81-181">This includes the Admin portal and all communications with Microsoft Managed Desktop Operations.</span></span> <span data-ttu-id="8ad81-182">特に指定がない限り、すべての管理者関連の操作とインターフェイスは英語で行われます。</span><span class="sxs-lookup"><span data-stu-id="8ad81-182">You should assume that all admin-related interactions and interfaces will be in English, unless specified otherwise.</span></span>


