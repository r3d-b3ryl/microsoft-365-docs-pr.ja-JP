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
ms.openlocfilehash: ab80de0e1be3a164da8414ef3791fb9717bcc190
ms.sourcegitcommit: 48a45b0d2c60d4d79669174f462603a43f272875
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2020
ms.locfileid: "41233698"
---
# <a name="view-activity-on-your-labeled-content-preview"></a><span data-ttu-id="4c609-103">ラベル付きコンテンツのアクティビティを表示する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="4c609-103">View activity on your labeled content (preview)</span></span>

<span data-ttu-id="4c609-104">データ分類の概要およびコンテンツ エクスプローラーのタブにより、どのコンテンツが検出されてラベルが付けられているか、およびそのコンテンツのある場所に対する可視性が与えられます。</span><span class="sxs-lookup"><span data-stu-id="4c609-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="4c609-105">アクティビティ エクスプローラーでは、ラベル付きコンテンツに対して実行される内容を監視できるようにすることで、こうした一連の機能性を完全なものにします。</span><span class="sxs-lookup"><span data-stu-id="4c609-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="4c609-106">アクティビティ エクスプローラーでは、履歴ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="4c609-106">Activity explorer provides a historical view.</span></span>

![アクティビティ エクスプローラーのプレースホルダー スクリーンショットの全体像](media/data-classification-activity-explorer-1.png)

<span data-ttu-id="4c609-108">次を使用し、データをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="4c609-108">You can filter the data by:</span></span>

- <span data-ttu-id="4c609-109">日付の範囲</span><span class="sxs-lookup"><span data-stu-id="4c609-109">date range</span></span>
- <span data-ttu-id="4c609-110">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="4c609-110">activity type</span></span>
- <span data-ttu-id="4c609-111">場所</span><span class="sxs-lookup"><span data-stu-id="4c609-111">location</span></span>
- <span data-ttu-id="4c609-112">ユーザー</span><span class="sxs-lookup"><span data-stu-id="4c609-112">user</span></span>
- <span data-ttu-id="4c609-113">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="4c609-113">sensitivity label</span></span>
- <span data-ttu-id="4c609-114">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="4c609-114">retention label</span></span>


<span data-ttu-id="4c609-115">リストまたは棒グラフとしてデータを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="4c609-115">You can view the data either as a list or a bar graph.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4c609-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="4c609-116">Prerequisites</span></span>

<span data-ttu-id="4c609-117">アクティビティ エクスプローラーにアクセスして使用するすべてのアカウントには、これらのいずれかのサブスクリプションのライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c609-117">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="4c609-118">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="4c609-118">Microsoft 365 E5</span></span>
- <span data-ttu-id="4c609-119">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="4c609-119">Office 365 E5</span></span>
- <span data-ttu-id="4c609-120">高度なコンプライアンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="4c609-120">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="4c609-121">高度な脅威インテリジェンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="4c609-121">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="4c609-122">Advanced Threat Protection (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="4c609-122">Advanced Threat Protection (E5) add-on</span></span>

## <a name="activity-type"></a><span data-ttu-id="4c609-123">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="4c609-123">Activity type</span></span>

<span data-ttu-id="4c609-124">Microsoft 365 では、SharePoint Online、OneDrive およびエンドポイントを横断して 12 種類のアクティビティを監視したり、レポートしたりします。</span><span class="sxs-lookup"><span data-stu-id="4c609-124">Microsoft 365 monitors and reports on 12 types of activities across SharePoint Online, OneDrive and endpoints.</span></span> <span data-ttu-id="4c609-125">エンドポイントとは、Windows 10 を実行しているユーザー デバイスです。</span><span class="sxs-lookup"><span data-stu-id="4c609-125">Endpoints are user devices running Windows 10.</span></span>

- <span data-ttu-id="4c609-126">ファイルが作成されました</span><span class="sxs-lookup"><span data-stu-id="4c609-126">File created</span></span>
- <span data-ttu-id="4c609-127">ファイルが変更されました</span><span class="sxs-lookup"><span data-stu-id="4c609-127">File modified</span></span>
- <span data-ttu-id="4c609-128">ファイルの名前が変更されました</span><span class="sxs-lookup"><span data-stu-id="4c609-128">File renamed</span></span>
- <span data-ttu-id="4c609-129">ファイルがクラウドにコピーされました</span><span class="sxs-lookup"><span data-stu-id="4c609-129">File copied to cloud</span></span>
- <span data-ttu-id="4c609-130">ファイルが許可されていないアプリによってアクセスされました</span><span class="sxs-lookup"><span data-stu-id="4c609-130">File accessed by unallowed app</span></span>
- <span data-ttu-id="4c609-131">ファイルが印刷されました</span><span class="sxs-lookup"><span data-stu-id="4c609-131">File printed</span></span>
- <span data-ttu-id="4c609-132">ファイルがリムーバブル メディアにコピーされました</span><span class="sxs-lookup"><span data-stu-id="4c609-132">File copied to removable media</span></span>
- <span data-ttu-id="4c609-133">ファイルがネットワーク共有にコピーされました</span><span class="sxs-lookup"><span data-stu-id="4c609-133">File copied to network share</span></span>
- <span data-ttu-id="4c609-134">ファイルの読み取り</span><span class="sxs-lookup"><span data-stu-id="4c609-134">File read</span></span>
- <span data-ttu-id="4c609-135">ファイルがクリップボードにコピーされました</span><span class="sxs-lookup"><span data-stu-id="4c609-135">file copied to clipboard</span></span>
- <span data-ttu-id="4c609-136">ラベルが適用されました</span><span class="sxs-lookup"><span data-stu-id="4c609-136">Label applied</span></span>
- <span data-ttu-id="4c609-137">ラベルが変更されました (アップグレード、ダウングレード、または削除されました)</span><span class="sxs-lookup"><span data-stu-id="4c609-137">Label changed (upgraded, downgraded, or removed)</span></span>

<span data-ttu-id="4c609-138">機密ラベル付きのコンテンツに対してどんな操作が行われたかを理解する価値は、[データ損失防止ポリシー](data-loss-prevention-policies.md) が有効かどうかなど、既定の環境の制限を確認できることです。</span><span class="sxs-lookup"><span data-stu-id="4c609-138">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="4c609-139">そうでない場合、つまり、多数の `highly confidential` でラベル付けされたアイテムおよび `general` にダウングレードされたアイテムなどの予想しない何かが検出された場合は、各種ポリシーを管理して、望ましくない動作を制限するための新しい操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4c609-139">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

<span data-ttu-id="4c609-140">フィルターを設定すると、次のことが実行できます。</span><span class="sxs-lookup"><span data-stu-id="4c609-140">Once your filters are set, you can:</span></span>

- <span data-ttu-id="4c609-141">横棒グラフのセグメントにマウス ポインターを置き、そのカテゴリに分類されたアイテムの数を確認できます ![アクティビティ エクスプローラーのマウスでのポイント](media/data-classification-activity-explorer-hover-over-2.png)</span><span class="sxs-lookup"><span data-stu-id="4c609-141">hover over a segment of the bar chart to see the number of items that fall into that category ![activity explorer hover over](media/data-classification-activity-explorer-hover-over-2.png)</span></span>
- <span data-ttu-id="4c609-142">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="4c609-142">export the data</span></span>
- <span data-ttu-id="4c609-143">リストから任意のアイテムを選択して、フライ アウトに操作の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="4c609-143">select any given item from the list and view the details of the action in the fly-out</span></span>

![アクティビティ エクスプローラーの詳細のフライ アウト](media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a><span data-ttu-id="4c609-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c609-145">See also</span></span>
- [<span data-ttu-id="4c609-146">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="4c609-146">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="4c609-147">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="4c609-147">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="4c609-148">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="4c609-148">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="4c609-149">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="4c609-149">Overview of retention policies</span></span>](retention-policies.md)