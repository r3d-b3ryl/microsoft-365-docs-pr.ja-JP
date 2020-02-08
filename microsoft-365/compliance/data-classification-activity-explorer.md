---
title: データ分類アクティビティ エクスプローラーを使用する
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
ms.openlocfilehash: 8af23cac590eb226890979719f938b8e79099bb3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595474"
---
# <a name="view-activity-on-your-labeled-content-preview"></a><span data-ttu-id="aeddf-103">ラベル付きコンテンツのアクティビティを表示する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="aeddf-103">View activity on your labeled content (preview)</span></span>

<span data-ttu-id="aeddf-104">データ分類の概要およびコンテンツ エクスプローラーのタブにより、どのコンテンツが検出されてラベルが付けられているか、およびそのコンテンツのある場所に対する可視性が与えられます。</span><span class="sxs-lookup"><span data-stu-id="aeddf-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="aeddf-105">アクティビティ エクスプローラーでは、ラベル付きコンテンツに対して実行される内容を監視できるようにすることで、こうした一連の機能性を完全なものにします。</span><span class="sxs-lookup"><span data-stu-id="aeddf-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="aeddf-106">アクティビティ エクスプローラーでは、履歴ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="aeddf-106">Activity explorer provides a historical view.</span></span>

![アクティビティ エクスプローラーのプレースホルダー スクリーンショットの全体像](media/data-classification-activity-explorer-1.png)

<span data-ttu-id="aeddf-108">次を使用し、データをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="aeddf-108">You can filter the data by:</span></span>

- <span data-ttu-id="aeddf-109">日付の範囲</span><span class="sxs-lookup"><span data-stu-id="aeddf-109">date range</span></span>
- <span data-ttu-id="aeddf-110">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="aeddf-110">activity type</span></span>
- <span data-ttu-id="aeddf-111">場所</span><span class="sxs-lookup"><span data-stu-id="aeddf-111">location</span></span>
- <span data-ttu-id="aeddf-112">ユーザー</span><span class="sxs-lookup"><span data-stu-id="aeddf-112">user</span></span>
- <span data-ttu-id="aeddf-113">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="aeddf-113">sensitivity label</span></span>
- <span data-ttu-id="aeddf-114">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="aeddf-114">retention label</span></span>


<span data-ttu-id="aeddf-115">リストまたは棒グラフとしてデータを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="aeddf-115">You can view the data either as a list or a bar graph.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aeddf-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="aeddf-116">Prerequisites</span></span>

<span data-ttu-id="aeddf-117">アクティビティ エクスプローラーにアクセスして使用するすべてのアカウントには、これらのいずれかのサブスクリプションのライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeddf-117">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="aeddf-118">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="aeddf-118">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="aeddf-119">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="aeddf-119">Office 365 (E5)</span></span>
- <span data-ttu-id="aeddf-120">高度なコンプライアンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="aeddf-120">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="aeddf-121">高度な脅威インテリジェンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="aeddf-121">Advanced Threat Intelligence (E5) add-on</span></span>

## <a name="activity-type"></a><span data-ttu-id="aeddf-122">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="aeddf-122">Activity type</span></span>

<span data-ttu-id="aeddf-123">Microsoft 365 では、SharePoint Online、OneDrive およびエンドポイントを横断して 12 種類のアクティビティを監視したり、レポートしたりします。</span><span class="sxs-lookup"><span data-stu-id="aeddf-123">Microsoft 365 monitors and reports on 12 types of activities across SharePoint Online, OneDrive and endpoints.</span></span> <span data-ttu-id="aeddf-124">エンドポイントとは、Windows 10 を実行しているユーザー デバイスです。</span><span class="sxs-lookup"><span data-stu-id="aeddf-124">Endpoints are user devices running Windows 10.</span></span>

- <span data-ttu-id="aeddf-125">ファイルが作成されました</span><span class="sxs-lookup"><span data-stu-id="aeddf-125">File created</span></span>
- <span data-ttu-id="aeddf-126">ファイルが変更されました</span><span class="sxs-lookup"><span data-stu-id="aeddf-126">File modified</span></span>
- <span data-ttu-id="aeddf-127">ファイルの名前が変更されました</span><span class="sxs-lookup"><span data-stu-id="aeddf-127">File renamed</span></span>
- <span data-ttu-id="aeddf-128">ファイルがクラウドにコピーされました</span><span class="sxs-lookup"><span data-stu-id="aeddf-128">File copied to cloud</span></span>
- <span data-ttu-id="aeddf-129">ファイルが許可されていないアプリによってアクセスされました</span><span class="sxs-lookup"><span data-stu-id="aeddf-129">File accessed by unallowed app</span></span>
- <span data-ttu-id="aeddf-130">ファイルが印刷されました</span><span class="sxs-lookup"><span data-stu-id="aeddf-130">File printed</span></span>
- <span data-ttu-id="aeddf-131">ファイルがリムーバブル メディアにコピーされました</span><span class="sxs-lookup"><span data-stu-id="aeddf-131">File copied to removable media</span></span>
- <span data-ttu-id="aeddf-132">ファイルがネットワーク共有にコピーされました</span><span class="sxs-lookup"><span data-stu-id="aeddf-132">File copied to network share</span></span>
- <span data-ttu-id="aeddf-133">ファイルの読み取り</span><span class="sxs-lookup"><span data-stu-id="aeddf-133">File read</span></span>
- <span data-ttu-id="aeddf-134">ファイルがクリップボードにコピーされました</span><span class="sxs-lookup"><span data-stu-id="aeddf-134">file copied to clipboard</span></span>
- <span data-ttu-id="aeddf-135">ラベルが適用されました</span><span class="sxs-lookup"><span data-stu-id="aeddf-135">Label applied</span></span>
- <span data-ttu-id="aeddf-136">ラベルが変更されました (アップグレード、ダウングレード、または削除されました)</span><span class="sxs-lookup"><span data-stu-id="aeddf-136">Label changed (upgraded, downgraded, or removed)</span></span>

<span data-ttu-id="aeddf-137">機密ラベル付きのコンテンツに対してどんな操作が行われたかを理解する価値は、[データ損失防止ポリシー](data-loss-prevention-policies.md) が有効かどうかなど、既定の環境の制限を確認できることです。</span><span class="sxs-lookup"><span data-stu-id="aeddf-137">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="aeddf-138">そうでない場合、つまり、多数の `highly confidential` でラベル付けされたアイテムおよび `general` にダウングレードされたアイテムなどの予想しない何かが検出された場合は、各種ポリシーを管理して、望ましくない動作を制限するための新しい操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="aeddf-138">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

<span data-ttu-id="aeddf-139">フィルターを設定すると、次のことが実行できます。</span><span class="sxs-lookup"><span data-stu-id="aeddf-139">Once your filters are set, you can:</span></span>

- <span data-ttu-id="aeddf-140">横棒グラフのセグメントにマウス ポインターを置き、そのカテゴリに分類されたアイテムの数を確認できます ![アクティビティ エクスプローラーのマウスでのポイント](media/data-classification-activity-explorer-hover-over-2.png)</span><span class="sxs-lookup"><span data-stu-id="aeddf-140">hover over a segment of the bar chart to see the number of items that fall into that category ![activity explorer hover over](media/data-classification-activity-explorer-hover-over-2.png)</span></span>
- <span data-ttu-id="aeddf-141">データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="aeddf-141">export the data</span></span>
- <span data-ttu-id="aeddf-142">リストから任意のアイテムを選択して、フライ アウトに操作の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="aeddf-142">select any given item from the list and view the details of the action in the fly-out</span></span>

![アクティビティ エクスプローラーの詳細のフライ アウト](media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a><span data-ttu-id="aeddf-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="aeddf-144">See also</span></span>
- [<span data-ttu-id="aeddf-145">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="aeddf-145">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="aeddf-146">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="aeddf-146">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="aeddf-147">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="aeddf-147">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="aeddf-148">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="aeddf-148">Overview of retention policies</span></span>](retention-policies.md)
