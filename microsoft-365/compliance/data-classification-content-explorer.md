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
ms.openlocfilehash: 6f062901acbf149f6fc56c266d10b370ed0c1112
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "39268577"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="88edd-103">データ分類コンテンツ エクスプローラー (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="88edd-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="88edd-104">データ分類コンテンツ エクスプローラーにより、概要ページで要約されたアイテムをネイティブに表示することができます。</span><span class="sxs-lookup"><span data-stu-id="88edd-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="88edd-105">コンテンツ エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="88edd-105">Content explorer</span></span>

<span data-ttu-id="88edd-106">コンテンツ エクスプローラーは、機密ラベル、保持ラベルまたは組織で機密情報の種類として分類されているアイテムの現在のスナップショットです。</span><span class="sxs-lookup"><span data-stu-id="88edd-106">Content explorer is a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

![折りたたみ済みのコンテンツ エクスプローラーのスクリーンショット](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="88edd-108">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="88edd-108">Permissions</span></span>

<span data-ttu-id="88edd-109">コンテンツ エクスプローラーにアクセス権を付与するロールは 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="88edd-109">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="88edd-110">**コンテンツ エクスプローラーのリスト ビューアー**: このロールのメンバーシップにより、ユーザーは各アイテムおよびその場所を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="88edd-110">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="88edd-111">**コンテンツ エクスプローラーのコンテンツ ビューアー**: このロールのメンバーシップにより、ユーザーはリスト内の各アイテムのコンテンツを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="88edd-111">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="88edd-112">コンテンツ エクスプローラーにアクセスするために使用するアカウントには、1 つまたは両方のロールがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="88edd-112">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="88edd-113">独立した役割があり、累積ではありません。</span><span class="sxs-lookup"><span data-stu-id="88edd-113">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="88edd-114">たとえば、アイテムおよびそれらの場所のみ表示する機能をアカウントに付与する場合は、コンテンツ エクスプローラーのリスト ビューアーの権利を付与します。</span><span class="sxs-lookup"><span data-stu-id="88edd-114">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="88edd-115">その同じアカウントでリスト内のアイテムのコンテンツも表示できるようにするには、コンテンツ エクスプローラーのコンテンツ ビューアーの権利も付与します。</span><span class="sxs-lookup"><span data-stu-id="88edd-115">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="88edd-116">コンテンツ エクスプローラーの使用方法</span><span class="sxs-lookup"><span data-stu-id="88edd-116">How to use content explorer</span></span>

1. <span data-ttu-id="88edd-117">**Microsoft 365 コンプライアンス センター**  > **[データ分類]** > **[コンテンツ エクスプローラー]** の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="88edd-117">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="88edd-118">ラベルの名前または機密情報の種類が分かる場合は、それを検索ボックスに入力することができます。</span><span class="sxs-lookup"><span data-stu-id="88edd-118">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="88edd-119">交互に、ラベルの種類を展開してリストからラベルを選択し、アイテムを参照することができます。以下にリストの保持ラベルの部分を示します。</span><span class="sxs-lookup"><span data-stu-id="88edd-119">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="88edd-120">[**すべての場所**] の下で場所を選択して、アイテムのフォルダー構造をドリルダウンします。</span><span class="sxs-lookup"><span data-stu-id="88edd-120">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="88edd-121">ダブルクリックして、コンテンツ エクスプローラーでネイティブにアイテムを開きます。</span><span class="sxs-lookup"><span data-stu-id="88edd-121">Double click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="88edd-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="88edd-122">See also</span></span>

- [<span data-ttu-id="88edd-123">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="88edd-123">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="88edd-124">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="88edd-124">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="88edd-125">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="88edd-125">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="88edd-126">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="88edd-126">Overview of retention policies</span></span>](retention-policies.md)
