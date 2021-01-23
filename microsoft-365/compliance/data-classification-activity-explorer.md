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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: アクティビティ エクスプローラーでは、ラベル付きコンテンツを取り扱うユーザーの操作の確認およびフィルター処理を行い、データ分類機能の機能性を完全なものにします。
ms.openlocfilehash: 6825c00373617011db28fa484f272086f887ea40
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921635"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="77847-103">アクティビティ エクスプローラーの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="77847-103">Get started with activity explorer</span></span>

<span data-ttu-id="77847-104">データ分類の概要およびコンテンツ エクスプローラーのタブにより、どのコンテンツが検出されてラベルが付けられているか、およびそのコンテンツのある場所に対する可視性が与えられます。</span><span class="sxs-lookup"><span data-stu-id="77847-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="77847-105">アクティビティ エクスプローラーでは、ラベル付きコンテンツに対して実行される内容を監視できるようにすることで、こうした一連の機能性を完全なものにします。</span><span class="sxs-lookup"><span data-stu-id="77847-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="77847-106">アクティビティ エクスプローラーでは、履歴ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="77847-106">Activity explorer provides a historical view.</span></span>

![アクティビティ エクスプローラーのプレースホルダー スクリーンショットの全体像](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="77847-108">使用可能なフィルターは 30 種類以上あり、以下がその一例です。</span><span class="sxs-lookup"><span data-stu-id="77847-108">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="77847-109">日付の範囲</span><span class="sxs-lookup"><span data-stu-id="77847-109">date range</span></span>
- <span data-ttu-id="77847-110">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="77847-110">activity type</span></span>
- <span data-ttu-id="77847-111">場所</span><span class="sxs-lookup"><span data-stu-id="77847-111">location</span></span>
- <span data-ttu-id="77847-112">ユーザー</span><span class="sxs-lookup"><span data-stu-id="77847-112">user</span></span>
- <span data-ttu-id="77847-113">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="77847-113">sensitivity label</span></span>
- <span data-ttu-id="77847-114">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="77847-114">retention label</span></span>
- <span data-ttu-id="77847-115">ファイル パス</span><span class="sxs-lookup"><span data-stu-id="77847-115">file path</span></span>
- <span data-ttu-id="77847-116">DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="77847-116">DLP policy</span></span>


## <a name="prerequisites"></a><span data-ttu-id="77847-117">前提条件</span><span class="sxs-lookup"><span data-stu-id="77847-117">Prerequisites</span></span>

<span data-ttu-id="77847-118">データ分類にアクセスし、データ分類を使用するすべてのアカウントには、以下のサブスクリプションのいずれかからライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="77847-118">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="77847-119">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="77847-119">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="77847-120">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="77847-120">Office 365 (E5)</span></span>
- <span data-ttu-id="77847-121">高度なコンプライアンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="77847-121">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="77847-122">高度な脅威インテリジェンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="77847-122">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="77847-123">Microsoft 365 E5/A5 情報保護およびガバナンス</span><span class="sxs-lookup"><span data-stu-id="77847-123">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="77847-124">Microsoft 365 E5/A5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="77847-124">Microsoft 365 E5/A5 Compliance</span></span>

### <a name="permissions"></a><span data-ttu-id="77847-125">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="77847-125">Permissions</span></span>

 <span data-ttu-id="77847-126">[アクティビティ エクスプローラー] タブにアクセスするには、アカウントはこれらの役割または役割グループに割り当てられたメンバーシップであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="77847-126">In order to get access to the activity explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="77847-127">**Microsoft 365 の役割グループ**</span><span class="sxs-lookup"><span data-stu-id="77847-127">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="77847-128">全体管理者</span><span class="sxs-lookup"><span data-stu-id="77847-128">Global administrator</span></span>
- <span data-ttu-id="77847-129">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="77847-129">Compliance administrator</span></span>
- <span data-ttu-id="77847-130">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="77847-130">Security administrator</span></span>
- <span data-ttu-id="77847-131">コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="77847-131">Compliance data administrator</span></span>

## <a name="activity-type"></a><span data-ttu-id="77847-132">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="77847-132">Activity type</span></span>

<span data-ttu-id="77847-133">Microsoft 365 は、SharePoint Online、OneDrive 全体で以下のようなアクティビティの種類を監視し、レポートします。</span><span class="sxs-lookup"><span data-stu-id="77847-133">Microsoft 365 monitors and reports on types of activities across SharePoint Online, and OneDrive like:</span></span>

- <span data-ttu-id="77847-134">ラベルの適用</span><span class="sxs-lookup"><span data-stu-id="77847-134">label applied</span></span>
- <span data-ttu-id="77847-135">ラベルの変更 (アップグレード、ダウングレード、または削除)</span><span class="sxs-lookup"><span data-stu-id="77847-135">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="77847-136">自動ラベル付けのシミュレーション</span><span class="sxs-lookup"><span data-stu-id="77847-136">auto-labeling simulation</span></span>

<span data-ttu-id="77847-137">機密ラベル付きのコンテンツに対してどんな操作が行われたかを理解する価値は、[データ損失防止ポリシー](data-loss-prevention-policies.md) が有効かどうかなど、既定の環境の制限を確認できることです。</span><span class="sxs-lookup"><span data-stu-id="77847-137">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="77847-138">そうでない場合、つまり、多数の `highly confidential` でラベル付けされたアイテムおよび `general` にダウングレードされたアイテムなどの予想しない何かが検出された場合は、各種ポリシーを管理して、望ましくない動作を制限するための新しい操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="77847-138">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="77847-139">アクティビティ エクスプローラーは現在、Exchange Online の保持アクティビティを監視していません。</span><span class="sxs-lookup"><span data-stu-id="77847-139">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="77847-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="77847-140">See also</span></span>
- [<span data-ttu-id="77847-141">秘密度ラベルの詳細</span><span class="sxs-lookup"><span data-stu-id="77847-141">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="77847-142">アイテム保持ポリシーと保持ラベルの詳細</span><span class="sxs-lookup"><span data-stu-id="77847-142">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="77847-143">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="77847-143">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

