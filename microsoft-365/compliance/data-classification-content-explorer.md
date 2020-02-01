---
title: データ分類コンテンツ エクスプローラー (プレビュー)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: コンテンツ エクスプローラーにより、ラベル付きアイテムをネイティブに表示することができます。
ms.openlocfilehash: 71ec7b4e27a6f125754e693ecb5239c66404a9ad
ms.sourcegitcommit: a6686a68b068adec29b72f998ac9bc95992981df
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628082"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="08194-103">データ分類コンテンツ エクスプローラー (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="08194-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="08194-104">データ分類コンテンツ エクスプローラーにより、概要ページで要約されたアイテムをネイティブに表示することができます。</span><span class="sxs-lookup"><span data-stu-id="08194-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="08194-105">コンテンツ エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="08194-105">Content explorer</span></span>

<span data-ttu-id="08194-106">コンテンツ エクスプローラーは、機密ラベル、保持ラベルまたは組織で機密情報の種類として分類されているアイテムの現在のスナップショットです。</span><span class="sxs-lookup"><span data-stu-id="08194-106">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="08194-107">機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="08194-107">Sensitive information types</span></span>

<span data-ttu-id="08194-108">[DLP ポリシー](data-loss-prevention-policies.md)は、**機密情報の種類**として定義されている機密情報を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="08194-108">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="08194-109">Microsoft 365 には、さまざまな地域にわたる[多くの一般的な機密情報の種類に対する定義](what-the-sensitive-information-types-look-for.md)が含まれていて、すぐに使用できる状態になっています。</span><span class="sxs-lookup"><span data-stu-id="08194-109">Microsoft 365 includes [definitions for many common sensitive information types](what-the-sensitive-information-types-look-for.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="08194-110">たとえば、クレジットカード番号、銀行口座番号、国民識別番号、Windows Live ID サービス番号などです。</span><span class="sxs-lookup"><span data-stu-id="08194-110">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="08194-111">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="08194-111">Sensitivity labels</span></span>

<span data-ttu-id="08194-112">[機密ラベル](sensitivity-labels.md)は、組織に対するアイテムの価値を示すタグです。</span><span class="sxs-lookup"><span data-stu-id="08194-112">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="08194-113">手動で、または自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="08194-113">It can be applied manually, or automatically.</span></span> <span data-ttu-id="08194-114">適用すると、ドキュメントに埋め込まれ、ドキュメントがどこへ移動されても機密ラベルは保持されます。</span><span class="sxs-lookup"><span data-stu-id="08194-114">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="08194-115">機密ラベルによって、必須のウォーターマークや暗号化など、さまざまな保護機能が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="08194-115">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="08194-116">エンド ポイントの保護を有効にすると、アイテムを組織の制御から離れさせないようにもできます。</span><span class="sxs-lookup"><span data-stu-id="08194-116">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="08194-117">SharePoint および OneDrive にあるファイルに対応するデータがデータ分類ページに表示されるようにするには、機密度ラベルを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="08194-117">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="08194-118">詳細については、「[SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする (パブリック プレビュー)](sensitivity-labels-sharepoint-onedrive-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08194-118">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="08194-119">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="08194-119">Retention labels</span></span>

<span data-ttu-id="08194-120">[保持ラベル](labels.md)を使用すると、ラベル付けされたアイテムの保持期間、およびアイテムを削除する前に行う手順を定義できます。</span><span class="sxs-lookup"><span data-stu-id="08194-120">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="08194-121">手動で、またはポリシーを使用して自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="08194-121">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="08194-122">組織が法的要件および規制要件を遵守するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="08194-122">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![折りたたみ済みのコンテンツ エクスプローラーのスクリーンショット](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="08194-124">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="08194-124">Permissions</span></span>

<span data-ttu-id="08194-125">コンテンツ エクスプローラーにアクセス権を付与する役割は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="08194-125">There are two roles that grant access to content explorer:</span></span>

- <span data-ttu-id="08194-126">**コンテンツ エクスプローラーのリスト ビューアー**: この役割のグループのメンバーシップにより、ユーザーは各アイテムおよびその場所を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="08194-126">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location.</span></span>

- <span data-ttu-id="08194-127">**コンテンツ エクスプローラーのコンテンツ ビューアー**: この役割のグループのメンバーシップにより、ユーザーはリスト内の各アイテムのコンテンツを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="08194-127">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="08194-128">コンテンツ エクスプローラーにアクセスするために使用するアカウントには、1 つまたは両方の役割のグループがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="08194-128">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="08194-129">独立した役割のグループがあり、累積ではありません。</span><span class="sxs-lookup"><span data-stu-id="08194-129">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="08194-130">たとえば、アイテムおよびそれらの場所のみ表示する機能をアカウントに付与する場合は、コンテンツ エクスプローラーのリスト ビューアーの権利を付与します。</span><span class="sxs-lookup"><span data-stu-id="08194-130">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="08194-131">その同じアカウントでリスト内のアイテムのコンテンツも表示できるようにするには、コンテンツ エクスプローラーのコンテンツ ビューアーの権利も付与します。</span><span class="sxs-lookup"><span data-stu-id="08194-131">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="08194-132">コンテンツ エクスプローラーの使用方法</span><span class="sxs-lookup"><span data-stu-id="08194-132">How to use content explorer</span></span>

1. <span data-ttu-id="08194-133">**Microsoft 365 コンプライアンス センター**  > **[データ分類]** > **[コンテンツ エクスプローラー]** の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="08194-133">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="08194-134">ラベルの名前または機密情報の種類が分かる場合は、それを検索ボックスに入力することができます。</span><span class="sxs-lookup"><span data-stu-id="08194-134">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="08194-135">交互に、ラベルの種類を展開してリストからラベルを選択し、アイテムを参照することができます。以下にリストの保持ラベルの部分を示します。</span><span class="sxs-lookup"><span data-stu-id="08194-135">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="08194-136">[**すべての場所**] の下で場所を選択して、アイテムのフォルダー構造をドリルダウンします。</span><span class="sxs-lookup"><span data-stu-id="08194-136">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="08194-137">ダブルクリックして、コンテンツ エクスプローラーでネイティブにアイテムを開きます。</span><span class="sxs-lookup"><span data-stu-id="08194-137">Double-click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="08194-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="08194-138">See also</span></span>

- [<span data-ttu-id="08194-139">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="08194-139">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="08194-140">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="08194-140">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="08194-141">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="08194-141">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="08194-142">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="08194-142">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="08194-143">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="08194-143">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
