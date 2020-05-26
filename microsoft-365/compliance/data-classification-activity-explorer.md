---
title: アクティビティ エクスプローラーの使用を開始する
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
ms.openlocfilehash: 5cb6a8dbfa570b3b0e0d1ce39648d12050d2af81
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327843"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="69999-103">アクティビティ エクスプローラーの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="69999-103">Get started with activity explorer</span></span>

<span data-ttu-id="69999-104">データ分類の概要およびコンテンツ エクスプローラーのタブにより、どのコンテンツが検出されてラベルが付けられているか、およびそのコンテンツのある場所に対する可視性が与えられます。</span><span class="sxs-lookup"><span data-stu-id="69999-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="69999-105">アクティビティ エクスプローラーでは、ラベル付きコンテンツに対して実行される内容を監視できるようにすることで、こうした一連の機能性を完全なものにします。</span><span class="sxs-lookup"><span data-stu-id="69999-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="69999-106">アクティビティ エクスプローラーでは、履歴ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="69999-106">Activity explorer provides a historical view.</span></span>

![アクティビティ エクスプローラーのプレースホルダー スクリーンショットの全体像](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="69999-108">使用可能なフィルターは 30 種類以上あり、以下がその一例です。</span><span class="sxs-lookup"><span data-stu-id="69999-108">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="69999-109">日付の範囲</span><span class="sxs-lookup"><span data-stu-id="69999-109">date range</span></span>
- <span data-ttu-id="69999-110">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="69999-110">activity type</span></span>
- <span data-ttu-id="69999-111">場所</span><span class="sxs-lookup"><span data-stu-id="69999-111">location</span></span>
- <span data-ttu-id="69999-112">ユーザー</span><span class="sxs-lookup"><span data-stu-id="69999-112">user</span></span>
- <span data-ttu-id="69999-113">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="69999-113">sensitivity label</span></span>
- <span data-ttu-id="69999-114">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="69999-114">retention label</span></span>
- <span data-ttu-id="69999-115">ファイル パス</span><span class="sxs-lookup"><span data-stu-id="69999-115">file path</span></span>
- <span data-ttu-id="69999-116">DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="69999-116">DLP policy</span></span>


## <a name="prerequisites"></a><span data-ttu-id="69999-117">前提条件</span><span class="sxs-lookup"><span data-stu-id="69999-117">Prerequisites</span></span>

<span data-ttu-id="69999-118">データ分類にアクセスし、データ分類を使用するすべてのアカウントには、以下のサブスクリプションのいずれかからライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="69999-118">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="69999-119">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="69999-119">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="69999-120">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="69999-120">Office 365 (E5)</span></span>
- <span data-ttu-id="69999-121">高度なコンプライアンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="69999-121">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="69999-122">高度な脅威インテリジェンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="69999-122">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="69999-123">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="69999-123">Permissions</span></span>

 <span data-ttu-id="69999-124">[アクティビティ エクスプローラー] タブにアクセスするには、アカウントはこれらの役割または役割グループに割り当てられたメンバーシップであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="69999-124">In order to get access to the activity explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="69999-125">**Microsoft 365 の役割グループ**</span><span class="sxs-lookup"><span data-stu-id="69999-125">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="69999-126">全体管理者</span><span class="sxs-lookup"><span data-stu-id="69999-126">Global administrator</span></span>
- <span data-ttu-id="69999-127">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="69999-127">Compliance administrator</span></span>
- <span data-ttu-id="69999-128">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="69999-128">Security administrator</span></span>
- <span data-ttu-id="69999-129">コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="69999-129">Compliance data administrator</span></span>

## <a name="activity-type"></a><span data-ttu-id="69999-130">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="69999-130">Activity type</span></span>

<span data-ttu-id="69999-131">Microsoft 365 は、SharePoint Online、OneDrive 全体で以下のようなアクティビティの種類を監視し、レポートします。</span><span class="sxs-lookup"><span data-stu-id="69999-131">Microsoft 365 monitors and reports on types of activities across SharePoint Online, and OneDrive like:</span></span>

- <span data-ttu-id="69999-132">ラベルの適用</span><span class="sxs-lookup"><span data-stu-id="69999-132">label applied</span></span>
- <span data-ttu-id="69999-133">ラベルの変更 (アップグレード、ダウングレード、または削除)</span><span class="sxs-lookup"><span data-stu-id="69999-133">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="69999-134">自動ラベル付けのシミュレーション</span><span class="sxs-lookup"><span data-stu-id="69999-134">auto-labeling simulation</span></span>

<span data-ttu-id="69999-135">機密ラベル付きのコンテンツに対してどんな操作が行われたかを理解する価値は、[データ損失防止ポリシー](data-loss-prevention-policies.md) が有効かどうかなど、既定の環境の制限を確認できることです。</span><span class="sxs-lookup"><span data-stu-id="69999-135">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="69999-136">そうでない場合、つまり、多数の `highly confidential` でラベル付けされたアイテムおよび `general` にダウングレードされたアイテムなどの予想しない何かが検出された場合は、各種ポリシーを管理して、望ましくない動作を制限するための新しい操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="69999-136">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="69999-137">アクティビティ エクスプローラーは現在、Exchange Online の保持アクティビティを監視していません。</span><span class="sxs-lookup"><span data-stu-id="69999-137">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="69999-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="69999-138">See also</span></span>
- [<span data-ttu-id="69999-139">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="69999-139">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="69999-140">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="69999-140">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="69999-141">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="69999-141">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="69999-142">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="69999-142">Overview of retention policies</span></span>](retention-policies.md)
