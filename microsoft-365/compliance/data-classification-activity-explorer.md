---
title: アクティビティ エクスプローラーの使用を開始する (プレビュー)
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
description: アクティビティ エクスプローラーでは、ラベル付きコンテンツを取り扱うユーザーの操作の確認およびフィルター処理を行い、データ分類機能の機能性を完全なものにします。
ms.openlocfilehash: 68304bc75d33c993db52895828ec49e3b5203a4c
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929461"
---
# <a name="get-started-with-activity-explorer-preview"></a><span data-ttu-id="1a7b5-103">アクティビティ エクスプローラーの使用を開始する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="1a7b5-103">Get started with activity explorer (preview)</span></span>

<span data-ttu-id="1a7b5-104">データ分類の概要およびコンテンツ エクスプローラーのタブにより、どのコンテンツが検出されてラベルが付けられているか、およびそのコンテンツのある場所に対する可視性が与えられます。</span><span class="sxs-lookup"><span data-stu-id="1a7b5-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="1a7b5-105">アクティビティ エクスプローラーでは、ラベル付きコンテンツに対して実行される内容を監視できるようにすることで、こうした一連の機能性を完全なものにします。</span><span class="sxs-lookup"><span data-stu-id="1a7b5-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="1a7b5-106">アクティビティ エクスプローラーでは、履歴ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="1a7b5-106">Activity explorer provides a historical view.</span></span>

![アクティビティ エクスプローラーのプレースホルダー スクリーンショットの全体像](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="1a7b5-108">次を使用し、データをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="1a7b5-108">You can filter the data by:</span></span>

- <span data-ttu-id="1a7b5-109">日付の範囲</span><span class="sxs-lookup"><span data-stu-id="1a7b5-109">date range</span></span>
- <span data-ttu-id="1a7b5-110">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="1a7b5-110">activity type</span></span>
- <span data-ttu-id="1a7b5-111">場所</span><span class="sxs-lookup"><span data-stu-id="1a7b5-111">location</span></span>
- <span data-ttu-id="1a7b5-112">ユーザー</span><span class="sxs-lookup"><span data-stu-id="1a7b5-112">user</span></span>
- <span data-ttu-id="1a7b5-113">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="1a7b5-113">sensitivity label</span></span>
- <span data-ttu-id="1a7b5-114">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="1a7b5-114">retention label</span></span>


<span data-ttu-id="1a7b5-115">リストまたは棒グラフとしてデータを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="1a7b5-115">You can view the data either as a list or a bar graph.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1a7b5-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="1a7b5-116">Prerequisites</span></span>

<span data-ttu-id="1a7b5-117">アクティビティ エクスプローラーにアクセスして使用するすべてのアカウントには、これらのいずれかのサブスクリプションのライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a7b5-117">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="1a7b5-118">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="1a7b5-118">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="1a7b5-119">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="1a7b5-119">Office 365 (E5)</span></span>
- <span data-ttu-id="1a7b5-120">高度なコンプライアンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="1a7b5-120">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="1a7b5-121">高度な脅威インテリジェンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="1a7b5-121">Advanced Threat Intelligence (E5) add-on</span></span>

## <a name="activity-type"></a><span data-ttu-id="1a7b5-122">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="1a7b5-122">Activity type</span></span>

<span data-ttu-id="1a7b5-123">Microsoft 365 では、SharePoint Online、OneDrive およびエンドポイントを横断して 12 種類のアクティビティを監視したり、レポートしたりします。</span><span class="sxs-lookup"><span data-stu-id="1a7b5-123">Microsoft 365 monitors and reports on 12 types of activities across SharePoint Online, OneDrive and endpoints.</span></span> <span data-ttu-id="1a7b5-124">エンドポイントとは、Windows 10 を実行しているユーザー デバイスです。</span><span class="sxs-lookup"><span data-stu-id="1a7b5-124">Endpoints are user devices running Windows 10.</span></span>

- <span data-ttu-id="1a7b5-125">ファイルが作成されました</span><span class="sxs-lookup"><span data-stu-id="1a7b5-125">File created</span></span>
- <span data-ttu-id="1a7b5-126">ファイルが変更されました</span><span class="sxs-lookup"><span data-stu-id="1a7b5-126">File modified</span></span>
- <span data-ttu-id="1a7b5-127">ファイルの名前が変更されました</span><span class="sxs-lookup"><span data-stu-id="1a7b5-127">File renamed</span></span>
- <span data-ttu-id="1a7b5-128">ファイルがクラウドにコピーされました</span><span class="sxs-lookup"><span data-stu-id="1a7b5-128">File copied to cloud</span></span>
- <span data-ttu-id="1a7b5-129">ファイルが許可されていないアプリによってアクセスされました</span><span class="sxs-lookup"><span data-stu-id="1a7b5-129">File accessed by unallowed app</span></span>
- <span data-ttu-id="1a7b5-130">ファイルが印刷されました</span><span class="sxs-lookup"><span data-stu-id="1a7b5-130">File printed</span></span>
- <span data-ttu-id="1a7b5-131">ファイルがリムーバブル メディアにコピーされました</span><span class="sxs-lookup"><span data-stu-id="1a7b5-131">File copied to removable media</span></span>
- <span data-ttu-id="1a7b5-132">ファイルがネットワーク共有にコピーされました</span><span class="sxs-lookup"><span data-stu-id="1a7b5-132">File copied to network share</span></span>
- <span data-ttu-id="1a7b5-133">ファイルの読み取り</span><span class="sxs-lookup"><span data-stu-id="1a7b5-133">File read</span></span>
- <span data-ttu-id="1a7b5-134">ファイルがクリップボードにコピーされました</span><span class="sxs-lookup"><span data-stu-id="1a7b5-134">file copied to clipboard</span></span>
- <span data-ttu-id="1a7b5-135">ラベルが適用されました</span><span class="sxs-lookup"><span data-stu-id="1a7b5-135">Label applied</span></span>
- <span data-ttu-id="1a7b5-136">ラベルが変更されました (アップグレード、ダウングレード、または削除されました)</span><span class="sxs-lookup"><span data-stu-id="1a7b5-136">Label changed (upgraded, downgraded, or removed)</span></span>

<span data-ttu-id="1a7b5-137">機密ラベル付きのコンテンツに対してどんな操作が行われたかを理解する価値は、[データ損失防止ポリシー](data-loss-prevention-policies.md) が有効かどうかなど、既定の環境の制限を確認できることです。</span><span class="sxs-lookup"><span data-stu-id="1a7b5-137">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="1a7b5-138">そうでない場合、つまり、多数の `highly confidential` でラベル付けされたアイテムおよび `general` にダウングレードされたアイテムなどの予想しない何かが検出された場合は、各種ポリシーを管理して、望ましくない動作を制限するための新しい操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1a7b5-138">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

<span data-ttu-id="1a7b5-139">フィルターを設定すると、次のことが実行できます。</span><span class="sxs-lookup"><span data-stu-id="1a7b5-139">Once your filters are set, you can:</span></span>

- <span data-ttu-id="1a7b5-140">横棒グラフのセグメントにマウス ポインターを置き、そのカテゴリに分類されたアイテムの数を確認できます ![アクティビティ エクスプローラーのマウスでのポイント](../media/data-classification-activity-explorer-hover-over-2.png)</span><span class="sxs-lookup"><span data-stu-id="1a7b5-140">hover over a segment of the bar chart to see the number of items that fall into that category ![activity explorer hover over](../media/data-classification-activity-explorer-hover-over-2.png)</span></span>
- <span data-ttu-id="1a7b5-141">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="1a7b5-141">export the data</span></span>
- <span data-ttu-id="1a7b5-142">リストから任意のアイテムを選択して、フライ アウトに操作の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="1a7b5-142">select any given item from the list and view the details of the action in the fly-out</span></span>

![アクティビティ エクスプローラーの詳細のフライ アウト](../media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a><span data-ttu-id="1a7b5-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a7b5-144">See also</span></span>
- [<span data-ttu-id="1a7b5-145">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="1a7b5-145">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="1a7b5-146">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="1a7b5-146">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="1a7b5-147">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="1a7b5-147">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="1a7b5-148">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="1a7b5-148">Overview of retention policies</span></span>](retention-policies.md)
