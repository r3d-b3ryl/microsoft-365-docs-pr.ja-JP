---
title: データ分類アクティビティ エクスプローラーを使用する
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
description: アクティビティ エクスプローラーでは、ラベル付きコンテンツを取り扱うユーザーの操作の確認およびフィルター処理を行い、データ分類機能の機能性を完全なものにします。
ms.openlocfilehash: 272de0400e89f9829b3ead5d4523db27789c0c44
ms.sourcegitcommit: 9d0a025ea9e265d515a034de0102eabcf47d11f5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "39268971"
---
# <a name="view-activity-on-your-labeled-content-preview"></a><span data-ttu-id="e9e8d-103">ラベル付きコンテンツのアクティビティを表示する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e9e8d-103">View activity on your labeled content (preview)</span></span>

<span data-ttu-id="e9e8d-104">データ分類の概要およびコンテンツ エクスプローラーのタブにより、どのコンテンツが検出されてラベルが付けられているか、およびそのコンテンツのある場所に対する可視性が与えられます。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="e9e8d-105">アクティビティ エクスプローラーでは、ラベル付きコンテンツに対して実行される内容を監視できるようにすることで、こうした一連の機能性を完全なものにします。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="e9e8d-106">アクティビティ エクスプローラーでは、履歴ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-106">Activity explorer provides a historical view.</span></span>

![アクティビティ エクスプローラーのプレースホルダー スクリーンショットの全体像](media/data-classification-activity-explorer-1.png)

<span data-ttu-id="e9e8d-108">次を使用し、データをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-108">You can filter the data by:</span></span>

- <span data-ttu-id="e9e8d-109">日付の範囲</span><span class="sxs-lookup"><span data-stu-id="e9e8d-109">Date range</span></span>
- <span data-ttu-id="e9e8d-110">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="e9e8d-110">Activity type</span></span>
- <span data-ttu-id="e9e8d-111">場所</span><span class="sxs-lookup"><span data-stu-id="e9e8d-111">location</span></span>
- <span data-ttu-id="e9e8d-112">ユーザー</span><span class="sxs-lookup"><span data-stu-id="e9e8d-112">user</span></span>
- <span data-ttu-id="e9e8d-113">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="e9e8d-113">For sensitivity label usage:</span></span>
- <span data-ttu-id="e9e8d-114">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="e9e8d-114">Retention Label</span></span>


<span data-ttu-id="e9e8d-115">リストまたは棒グラフとしてデータを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-115">You can view the data either as a list or a bar graph.</span></span>

## <a name="activity-type"></a><span data-ttu-id="e9e8d-116">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="e9e8d-116">Activity type</span></span>

<span data-ttu-id="e9e8d-117">Microsoft 365 では、SharePoint Online、OneDrive およびエンドポイントを横断して 12 種類のアクティビティを監視したり、レポートしたりします。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-117">Microsoft 365 monitors and reports on 12 types of activities across SharePoint Online, OneDrive and endpoints.</span></span> <span data-ttu-id="e9e8d-118">エンドポイントとは、Windows 10 を実行しているユーザー デバイスです。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-118">Endpoints are user devices running Windows 10.</span></span>

- <span data-ttu-id="e9e8d-119">ファイルが作成されました</span><span class="sxs-lookup"><span data-stu-id="e9e8d-119">File is created</span></span>
- <span data-ttu-id="e9e8d-120">ファイルが変更されました</span><span class="sxs-lookup"><span data-stu-id="e9e8d-120">File modified</span></span>
- <span data-ttu-id="e9e8d-121">ファイルの名前が変更されました</span><span class="sxs-lookup"><span data-stu-id="e9e8d-121">File renamed</span></span>
- <span data-ttu-id="e9e8d-122">ファイルがクラウドにコピーされました</span><span class="sxs-lookup"><span data-stu-id="e9e8d-122">File copied to cloud</span></span>
- <span data-ttu-id="e9e8d-123">ファイルが許可されていないアプリによってアクセスされました</span><span class="sxs-lookup"><span data-stu-id="e9e8d-123">File accessed by unallowed app</span></span>
- <span data-ttu-id="e9e8d-124">ファイルが印刷されました</span><span class="sxs-lookup"><span data-stu-id="e9e8d-124">File printed</span></span>
- <span data-ttu-id="e9e8d-125">ファイルがリムーバブル メディアにコピーされました</span><span class="sxs-lookup"><span data-stu-id="e9e8d-125">File copied to removable media</span></span>
- <span data-ttu-id="e9e8d-126">ファイルがネットワーク共有にコピーされました</span><span class="sxs-lookup"><span data-stu-id="e9e8d-126">File copied to network share</span></span>
- <span data-ttu-id="e9e8d-127">ファイルの読み取り</span><span class="sxs-lookup"><span data-stu-id="e9e8d-127">File read</span></span>
- <span data-ttu-id="e9e8d-128">ファイルがクリップボードにコピーされました</span><span class="sxs-lookup"><span data-stu-id="e9e8d-128">file copied to clipboard</span></span>
- <span data-ttu-id="e9e8d-129">ラベルが適用されました</span><span class="sxs-lookup"><span data-stu-id="e9e8d-129">Label protection is applied</span></span>
- <span data-ttu-id="e9e8d-130">ラベルが変更されました (アップグレード、ダウングレード、または削除されました)</span><span class="sxs-lookup"><span data-stu-id="e9e8d-130">Label changed (upgraded, downgraded, or removed)</span></span>

<span data-ttu-id="e9e8d-131">機密ラベル付きのコンテンツに対してどんな操作が行われたかを理解する価値は、[データ損失防止ポリシー](data-loss-prevention-policies.md) が有効かどうかなど、既定の環境の制限を確認できることです。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-131">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="e9e8d-132">そうでない場合、つまり、多数の `highly confidential` でラベル付けされたアイテムおよび `general` にダウングレードされたアイテムなどの予想しない何かが検出された場合は、各種ポリシーを管理して、望ましくない動作を制限するための新しい操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-132">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

<span data-ttu-id="e9e8d-133">フィルターを設定すると、次のことが実行できます。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-133">Once your filters are set, you can:</span></span>

- <span data-ttu-id="e9e8d-134">横棒グラフのセグメントにマウス ポインターを置き、そのカテゴリに分類されたアイテムの数を確認できます ![アクティビティ エクスプローラーのマウスでのポイント](media/data-classification-activity-explorer-hover-over-2.png)</span><span class="sxs-lookup"><span data-stu-id="e9e8d-134">hover over a segment of the bar chart to see the number of items that fall into that category ![activity explorer hover over](media/data-classification-activity-explorer-hover-over-2.png)</span></span>
- <span data-ttu-id="e9e8d-135">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e9e8d-135">The variable to export  the data to.</span></span>
- <span data-ttu-id="e9e8d-136">リストから任意のアイテムを選択して、フライ アウトに操作の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="e9e8d-136">select any given item from the list and view the details of the action in the fly-out</span></span>

![アクティビティ エクスプローラーの詳細のフライ アウト](media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a><span data-ttu-id="e9e8d-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9e8d-138">See also</span></span>
- [<span data-ttu-id="e9e8d-139">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="e9e8d-139">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="e9e8d-140">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="e9e8d-140">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="e9e8d-141">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="e9e8d-141">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="e9e8d-142">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="e9e8d-142">Overview of retention policies</span></span>](retention-policies.md)