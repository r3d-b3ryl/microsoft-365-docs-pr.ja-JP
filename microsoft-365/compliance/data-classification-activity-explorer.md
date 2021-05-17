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
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: アクティビティ エクスプローラーでは、ラベル付きコンテンツを取り扱うユーザーの操作の確認およびフィルター処理を行い、データ分類機能の機能性を完全なものにします。
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114009"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="637cf-103">アクティビティ エクスプローラーの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="637cf-103">Get started with activity explorer</span></span>

<span data-ttu-id="637cf-104">データ[分類の概要と](data-classification-overview.md)[コンテンツ エクスプローラーの](data-classification-content-explorer.md)タブを使用すると、どのコンテンツが検出され、ラベル付けされ、そのコンテンツがどこに表示されるのかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="637cf-104">The [data classification overview](data-classification-overview.md) and [content explorer](data-classification-content-explorer.md) tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="637cf-105">アクティビティ エクスプローラーでは、ラベル付きコンテンツに対して実行される内容を監視できるようにすることで、こうした一連の機能性を完全なものにします。</span><span class="sxs-lookup"><span data-stu-id="637cf-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="637cf-106">アクティビティ エクスプローラーは、ラベル付きコンテンツのアクティビティの履歴ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="637cf-106">Activity explorer provides a historical view of activities on your labeled content.</span></span> <span data-ttu-id="637cf-107">アクティビティ情報は、統合監査ログMicrosoft 365収集され、アクティビティ エクスプローラー UI で変換され、使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="637cf-107">The activity information is collected from the Microsoft 365 unified audit logs, transformed and made available in the Activity explorer UI.</span></span> 

![アクティビティ エクスプローラーのプレースホルダー スクリーンショットの全体像](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="637cf-109">使用可能なフィルターは 30 種類以上あり、以下がその一例です。</span><span class="sxs-lookup"><span data-stu-id="637cf-109">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="637cf-110">日付の範囲</span><span class="sxs-lookup"><span data-stu-id="637cf-110">date range</span></span>
- <span data-ttu-id="637cf-111">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="637cf-111">activity type</span></span>
- <span data-ttu-id="637cf-112">場所</span><span class="sxs-lookup"><span data-stu-id="637cf-112">location</span></span>
- <span data-ttu-id="637cf-113">ユーザー</span><span class="sxs-lookup"><span data-stu-id="637cf-113">user</span></span>
- <span data-ttu-id="637cf-114">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="637cf-114">sensitivity label</span></span>
- <span data-ttu-id="637cf-115">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="637cf-115">retention label</span></span>
- <span data-ttu-id="637cf-116">ファイル パス</span><span class="sxs-lookup"><span data-stu-id="637cf-116">file path</span></span>
- <span data-ttu-id="637cf-117">DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="637cf-117">DLP policy</span></span>



## <a name="prerequisites"></a><span data-ttu-id="637cf-118">前提条件</span><span class="sxs-lookup"><span data-stu-id="637cf-118">Prerequisites</span></span>

<span data-ttu-id="637cf-119">データ分類にアクセスして使用するすべてのアカウントには、これらのいずれかのサブスクリプションのライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="637cf-119">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="637cf-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="637cf-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="637cf-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="637cf-121">Office 365 (E5)</span></span>
- <span data-ttu-id="637cf-122">高度なコンプライアンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="637cf-122">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="637cf-123">高度な脅威インテリジェンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="637cf-123">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="637cf-124">Microsoft 365 E5/A5 情報保護およびガバナンス</span><span class="sxs-lookup"><span data-stu-id="637cf-124">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="637cf-125">Microsoft 365 E5/A5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="637cf-125">Microsoft 365 E5/A5 Compliance</span></span>

### <a name="permissions"></a><span data-ttu-id="637cf-126">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="637cf-126">Permissions</span></span>

 <span data-ttu-id="637cf-127">[アクティビティ エクスプローラー] タブにアクセスするには、アカウントにこれらの役割グループのメンバーシップを明示的に割り当てるか、役割を明示的に付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="637cf-127">In order to get access to the activity explorer tab, an account must be explicitly assigned membership in any one of these role groups or explicitly granted the role.</span></span>

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

<span data-ttu-id="637cf-128">**Microsoft 365 の役割グループ**</span><span class="sxs-lookup"><span data-stu-id="637cf-128">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="637cf-129">全体管理者</span><span class="sxs-lookup"><span data-stu-id="637cf-129">Global administrator</span></span>
- <span data-ttu-id="637cf-130">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="637cf-130">Compliance administrator</span></span>
- <span data-ttu-id="637cf-131">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="637cf-131">Security administrator</span></span>
- <span data-ttu-id="637cf-132">コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="637cf-132">Compliance data administrator</span></span>

<span data-ttu-id="637cf-133">**Microsoft 365ロール**</span><span class="sxs-lookup"><span data-stu-id="637cf-133">**Microsoft 365 roles**</span></span>

- <span data-ttu-id="637cf-134">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="637cf-134">Compliance administrator</span></span>
- <span data-ttu-id="637cf-135">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="637cf-135">Security administrator</span></span>

## <a name="activity-types"></a><span data-ttu-id="637cf-136">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="637cf-136">Activity types</span></span>

<span data-ttu-id="637cf-137">アクティビティ エクスプローラーは、複数のアクティビティ ソースの監査ログからアクティビティ情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="637cf-137">Activity explorer gathers activity information from the audit logs on multiple sources of activities.</span></span> <span data-ttu-id="637cf-138">どのラベル付けアクティビティがアクティビティ エクスプローラーに表示されるかの詳細については、「アクティビティ エクスプローラーで利用可能なイベントのラベル付け [」を参照してください](data-classification-activity-explorer-available-events.md)。</span><span class="sxs-lookup"><span data-stu-id="637cf-138">For more detailed information on what labeling activity makes it to Activity explorer, see [Labeling events available in Activity explorer](data-classification-activity-explorer-available-events.md).</span></span>

<span data-ttu-id="637cf-139"> Office ネイティブ アプリケーション、Azure Information Protection アドイン、SharePoint Online、Exchange Online (感度ラベルのみ)、および OneDrive からの感度ラベル アクティビティと保持ラベル付けアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="637cf-139">**Sensitivity label activities** and **Retention labeling activities** from Office native applications, Azure Information Protection add-in, SharePoint Online, Exchange Online (sensitivity labels only) and OneDrive.</span></span> <span data-ttu-id="637cf-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="637cf-140">Some examples are:</span></span>

- <span data-ttu-id="637cf-141">ラベルの適用</span><span class="sxs-lookup"><span data-stu-id="637cf-141">label applied</span></span>
- <span data-ttu-id="637cf-142">ラベルの変更 (アップグレード、ダウングレード、または削除)</span><span class="sxs-lookup"><span data-stu-id="637cf-142">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="637cf-143">自動ラベル付けのシミュレーション</span><span class="sxs-lookup"><span data-stu-id="637cf-143">auto-labeling simulation</span></span>
- <span data-ttu-id="637cf-144">ファイルの読み取り</span><span class="sxs-lookup"><span data-stu-id="637cf-144">file read</span></span> 

<span data-ttu-id="637cf-145">**Azure Information Protection (AIP) スキャナーと AIP クライアント**</span><span class="sxs-lookup"><span data-stu-id="637cf-145">**Azure Information Protection (AIP) scanner and AIP clients**</span></span>

- <span data-ttu-id="637cf-146">適用される保護</span><span class="sxs-lookup"><span data-stu-id="637cf-146">protection applied</span></span>
- <span data-ttu-id="637cf-147">保護の変更</span><span class="sxs-lookup"><span data-stu-id="637cf-147">protection changed</span></span>
- <span data-ttu-id="637cf-148">保護が削除されました</span><span class="sxs-lookup"><span data-stu-id="637cf-148">protection removed</span></span>
- <span data-ttu-id="637cf-149">検出されたファイル</span><span class="sxs-lookup"><span data-stu-id="637cf-149">files discovered</span></span> 

<span data-ttu-id="637cf-150">また、アクティビティ エクスプローラーは、Exchange Online、SharePoint Online、OneDrive、Teams チャットとチャネル (プレビュー)、オンプレミスの SharePoint フォルダーとライブラリ、オンプレミスのファイル共有、およびエンドポイント データ損失防止 **(DLP)** を介して Windows 10 デバイスからのイベントに一致するイベントを収集します。</span><span class="sxs-lookup"><span data-stu-id="637cf-150">Activity explorer also gathers **DLP policy matches** events from Exchange Online, SharePoint Online, OneDrive, Teams Chat and Channel (preview), on-premises SharePoint folders and libraries, and on-premises file shares, and Windows 10 devices via **Endpoint data loss prevention (DLP)**.</span></span> <span data-ttu-id="637cf-151">デバイスからのイベントの例Windows 10ファイルです。</span><span class="sxs-lookup"><span data-stu-id="637cf-151">Some examples events from Windows 10 devices are file:</span></span>

- <span data-ttu-id="637cf-152">削除</span><span class="sxs-lookup"><span data-stu-id="637cf-152">deletions</span></span>
- <span data-ttu-id="637cf-153">creations</span><span class="sxs-lookup"><span data-stu-id="637cf-153">creations</span></span>
- <span data-ttu-id="637cf-154">クリップボードにコピー</span><span class="sxs-lookup"><span data-stu-id="637cf-154">copied to clipboard</span></span>
- <span data-ttu-id="637cf-155">更新日時</span><span class="sxs-lookup"><span data-stu-id="637cf-155">modified</span></span>
- <span data-ttu-id="637cf-156">read</span><span class="sxs-lookup"><span data-stu-id="637cf-156">read</span></span>
- <span data-ttu-id="637cf-157">印刷済み</span><span class="sxs-lookup"><span data-stu-id="637cf-157">printed</span></span>
- <span data-ttu-id="637cf-158">名前の変更</span><span class="sxs-lookup"><span data-stu-id="637cf-158">renamed</span></span>
- <span data-ttu-id="637cf-159">ネットワーク共有にコピーされる</span><span class="sxs-lookup"><span data-stu-id="637cf-159">copied to network share</span></span>
- <span data-ttu-id="637cf-160">許可されていないアプリによってアクセスされる</span><span class="sxs-lookup"><span data-stu-id="637cf-160">accessed by unallowed app</span></span> 

<span data-ttu-id="637cf-161">機密性の高いラベル付きコンテンツで実行されるアクションを理解する価値は、データ損失防止など、既に設定したコントロールが有効か、有効[](dlp-learn-about-dlp.md)ではないかを確認することです。</span><span class="sxs-lookup"><span data-stu-id="637cf-161">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention](dlp-learn-about-dlp.md) are effective or not.</span></span> <span data-ttu-id="637cf-162">そうでない場合、つまり、多数の `highly confidential` でラベル付けされたアイテムおよび `general` にダウングレードされたアイテムなどの予想しない何かが検出された場合は、各種ポリシーを管理して、望ましくない動作を制限するための新しい操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="637cf-162">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="637cf-163">アクティビティ エクスプローラーは現在、Exchange Online の保持アクティビティを監視していません。</span><span class="sxs-lookup"><span data-stu-id="637cf-163">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="637cf-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="637cf-164">See also</span></span>

- [<span data-ttu-id="637cf-165">秘密度ラベルの詳細</span><span class="sxs-lookup"><span data-stu-id="637cf-165">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="637cf-166">アイテム保持ポリシーと保持ラベルの詳細</span><span class="sxs-lookup"><span data-stu-id="637cf-166">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="637cf-167">機密情報の種類に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="637cf-167">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="637cf-168">データ分類について</span><span class="sxs-lookup"><span data-stu-id="637cf-168">Learn about data classification</span></span>](data-classification-overview.md)
