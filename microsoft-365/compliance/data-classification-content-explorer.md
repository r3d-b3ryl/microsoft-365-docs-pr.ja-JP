---
title: データ分類コンテンツ エクスプローラー (プレビュー)
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
ms.openlocfilehash: 9e9ad76d2bdd7f74368121346f7e04d1208803ff
ms.sourcegitcommit: 99d759d5c4e7d81266c3ebc087eaa37486cc0bc1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2019
ms.locfileid: "39818859"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="57a99-103">データ分類コンテンツ エクスプローラー (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="57a99-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="57a99-104">データ分類コンテンツ エクスプローラーにより、概要ページで要約されたアイテムをネイティブに表示することができます。</span><span class="sxs-lookup"><span data-stu-id="57a99-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="57a99-105">コンテンツ エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="57a99-105">Content explorer</span></span>

<span data-ttu-id="57a99-106">コンテンツ エクスプローラーは、機密ラベル、保持ラベルまたは組織で機密情報の種類として分類されているアイテムの現在のスナップショットです。</span><span class="sxs-lookup"><span data-stu-id="57a99-106">Content explorer is a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="57a99-107">機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="57a99-107">Sensitive information types</span></span>

<span data-ttu-id="57a99-108">[DLP ポリシー](data-loss-prevention-policies.md)は、**機密情報の種類**として定義されている機密情報を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="57a99-108">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="57a99-109">Microsoft 365 には、さまざまな地域にわたる[多くの一般的な機密情報の種類に対する定義](what-the-sensitive-information-types-look-for.md)が含まれていて、すぐに使用できる状態になっています。</span><span class="sxs-lookup"><span data-stu-id="57a99-109">Office 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> <span data-ttu-id="57a99-110">たとえば、クレジットカード番号、銀行口座番号、国民識別番号、Windows Live ID サービス番号などです。</span><span class="sxs-lookup"><span data-stu-id="57a99-110">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="57a99-111">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="57a99-111">Sensitivity labels</span></span>

<span data-ttu-id="57a99-112">[機密ラベル](sensitivity-labels.md)は、組織に対するアイテムの価値を示すタグです。</span><span class="sxs-lookup"><span data-stu-id="57a99-112">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="57a99-113">手動で、または自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="57a99-113">It can be applied manually, or automatically.</span></span> <span data-ttu-id="57a99-114">適用すると、ドキュメントに埋め込まれ、ドキュメントがどこへ移動されても機密ラベルは保持されます。</span><span class="sxs-lookup"><span data-stu-id="57a99-114">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="57a99-115">機密ラベルによって、必須のウォーターマークや暗号化など、さまざまな保護機能が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="57a99-115">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="57a99-116">エンド ポイントの保護を有効にすると、アイテムを組織の制御から離れさせないようにもできます。</span><span class="sxs-lookup"><span data-stu-id="57a99-116">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="57a99-117">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="57a99-117">Retention labels</span></span>

<span data-ttu-id="57a99-118">[保持ラベル](labels.md)を使用すると、ラベル付けされたアイテムの保持期間、およびアイテムを削除する前に行う手順を定義できます。</span><span class="sxs-lookup"><span data-stu-id="57a99-118">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="57a99-119">手動で、またはポリシーを使用して自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="57a99-119">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="57a99-120">組織が法的要件および規制要件を遵守するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="57a99-120">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![折りたたみ済みのコンテンツ エクスプローラーのスクリーンショット](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="57a99-122">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="57a99-122">Permissions</span></span>

<span data-ttu-id="57a99-123">コンテンツ エクスプローラーにアクセス権を付与するロールは 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="57a99-123">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="57a99-124">**コンテンツ エクスプローラーのリスト ビューアー**: このロールのメンバーシップにより、ユーザーは各アイテムおよびその場所を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="57a99-124">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="57a99-125">**コンテンツ エクスプローラーのコンテンツ ビューアー**: このロールのメンバーシップにより、ユーザーはリスト内の各アイテムのコンテンツを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="57a99-125">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="57a99-126">コンテンツ エクスプローラーにアクセスするために使用するアカウントには、1 つまたは両方のロールがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="57a99-126">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="57a99-127">独立した役割があり、累積ではありません。</span><span class="sxs-lookup"><span data-stu-id="57a99-127">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="57a99-128">たとえば、アイテムおよびそれらの場所のみ表示する機能をアカウントに付与する場合は、コンテンツ エクスプローラーのリスト ビューアーの権利を付与します。</span><span class="sxs-lookup"><span data-stu-id="57a99-128">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="57a99-129">その同じアカウントでリスト内のアイテムのコンテンツも表示できるようにするには、コンテンツ エクスプローラーのコンテンツ ビューアーの権利も付与します。</span><span class="sxs-lookup"><span data-stu-id="57a99-129">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="57a99-130">コンテンツ エクスプローラーの使用方法</span><span class="sxs-lookup"><span data-stu-id="57a99-130">How to use content explorer</span></span>

1. <span data-ttu-id="57a99-131">**Microsoft 365 コンプライアンス センター**  > **[データ分類]** > **[コンテンツ エクスプローラー]** の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="57a99-131">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="57a99-132">ラベルの名前または機密情報の種類が分かる場合は、それを検索ボックスに入力することができます。</span><span class="sxs-lookup"><span data-stu-id="57a99-132">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="57a99-133">交互に、ラベルの種類を展開してリストからラベルを選択し、アイテムを参照することができます。以下にリストの保持ラベルの部分を示します。</span><span class="sxs-lookup"><span data-stu-id="57a99-133">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="57a99-134">[**すべての場所**] の下で場所を選択して、アイテムのフォルダー構造をドリルダウンします。</span><span class="sxs-lookup"><span data-stu-id="57a99-134">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="57a99-135">ダブルクリックして、コンテンツ エクスプローラーでネイティブにアイテムを開きます。</span><span class="sxs-lookup"><span data-stu-id="57a99-135">Double click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="57a99-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="57a99-136">See also</span></span>

- [<span data-ttu-id="57a99-137">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="57a99-137">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="57a99-138">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="57a99-138">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="57a99-139">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="57a99-139">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="57a99-140">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="57a99-140">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="57a99-141">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="57a99-141">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
