---
title: Microsoft セキュリティスコアの新機能
description: Microsoft 365 セキュリティセンターの Microsoft セキュリティスコアに対して発生した新しい変更点について説明します。
keywords: microsoft secure score、セキュリティスコア、office 365 のセキュリティスコア、microsoft セキュリティスコア、microsoft 365 セキュリティセンター
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 0ba3d7a5e46f7e0f8677ce2844c5551bf70739e3
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367115"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="2dd8c-104">Microsoft セキュリティスコアの新機能</span><span class="sxs-lookup"><span data-stu-id="2dd8c-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2dd8c-105">Microsoft のセキュリティの評価をより良いものにするには、いくつかの変更を行いました。</span><span class="sxs-lookup"><span data-stu-id="2dd8c-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="2dd8c-106">予定されている変更の詳細については、「 [Microsoft Secure Score の内容](microsoft-secure-score-whats-coming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dd8c-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

## <a name="november-2020"></a><span data-ttu-id="2dd8c-107">2020 年 11 月</span><span class="sxs-lookup"><span data-stu-id="2dd8c-107">November 2020</span></span>

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="2dd8c-108">エンドポイント (以前の Microsoft Defender ATP) に関する Microsoft Defender のサービス関連の改善アクションを3つ追加しました。</span><span class="sxs-lookup"><span data-stu-id="2dd8c-108">Added 3 services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="2dd8c-109">Windows サービスの引用符で囲まれるサービスパスを修正する</span><span class="sxs-lookup"><span data-stu-id="2dd8c-109">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="2dd8c-110">サービスの実行可能パスを共通の保護された場所に変更する</span><span class="sxs-lookup"><span data-stu-id="2dd8c-110">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="2dd8c-111">Windows レジストリでパスワードがキャッシュされないようにサービスアカウントを変更する</span><span class="sxs-lookup"><span data-stu-id="2dd8c-111">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="2dd8c-112">2020 年 10 月</span><span class="sxs-lookup"><span data-stu-id="2dd8c-112">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="2dd8c-113">エンドポイントの Microsoft Defender に関連する向上アクションを削除する</span><span class="sxs-lookup"><span data-stu-id="2dd8c-113">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="2dd8c-114">Microsoft Defender SmartScreen Windows ストアアプリの web コンテンツチェックを設定して警告を発する</span><span class="sxs-lookup"><span data-stu-id="2dd8c-114">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="2dd8c-115">2020 年 8 月</span><span class="sxs-lookup"><span data-stu-id="2dd8c-115">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="2dd8c-116">Azure Active Directory の改善アクションを更新しました</span><span class="sxs-lookup"><span data-stu-id="2dd8c-116">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="2dd8c-117">レガシ認証をブロックするポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="2dd8c-117">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="2dd8c-118">Id のセキュリティで保護されたスコアとグラフ API の非互換性</span><span class="sxs-lookup"><span data-stu-id="2dd8c-118">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="2dd8c-119">Microsoft Secure Score の最近のリリースでは、向上したスコアリングモデルがリリースされました。</span><span class="sxs-lookup"><span data-stu-id="2dd8c-119">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="2dd8c-120">これらの変更により、より柔軟かつ正確にセキュリティ状況を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="2dd8c-120">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="2dd8c-121">しかし、これらの更新プログラムにより、Microsoft セキュリティスコアが Id のセキュリティで保護されたスコアと Graph API とは一時的に互換性がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2dd8c-121">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="2dd8c-122">時間では、Id のセキュリティスコアと Graph API が新しいスコアリングモデルを採用します。</span><span class="sxs-lookup"><span data-stu-id="2dd8c-122">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="2dd8c-123">その後、Microsoft のセキュリティで保護されたスコア、Id のセキュリティで保護されたスコア、Graph API によって報告されたスコアの違いがわかります。</span><span class="sxs-lookup"><span data-stu-id="2dd8c-123">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="2dd8c-124">ご不便をかけて申し訳ございません。今後、このようなエクスペリエンスの互換性を確保するために取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="2dd8c-124">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="2dd8c-125">更新された改善アクション</span><span class="sxs-lookup"><span data-stu-id="2dd8c-125">Updated improvement actions</span></span>

- <span data-ttu-id="2dd8c-126">Azure Active Directory の改善アクションを追加しました</span><span class="sxs-lookup"><span data-stu-id="2dd8c-126">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="2dd8c-127">Id の改善アクションのために Microsoft Defender を追加しました</span><span class="sxs-lookup"><span data-stu-id="2dd8c-127">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="2dd8c-128">エンドポイントの脅威に対する Microsoft Defender のサポート [& 脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="2dd8c-128">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="2dd8c-129">リリースされた TVM で提供されるすべてのセキュリティの推奨事項を使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2dd8c-129">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="2dd8c-130">更新されたインターフェイスと機能</span><span class="sxs-lookup"><span data-stu-id="2dd8c-130">Updated interface and functionality</span></span>

* <span data-ttu-id="2dd8c-131">CISO およびリード レベルのディスカッションのすべての新しい指標と傾向の表示</span><span class="sxs-lookup"><span data-stu-id="2dd8c-131">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="2dd8c-132">スコアを追跡して評価するための新しい方法</span><span class="sxs-lookup"><span data-stu-id="2dd8c-132">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="2dd8c-133">スコア回帰の追跡と理解の向上</span><span class="sxs-lookup"><span data-stu-id="2dd8c-133">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="2dd8c-134">改善のための処置のフィルタリング、タグ付け、検索、グループ化</span><span class="sxs-lookup"><span data-stu-id="2dd8c-134">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="2dd8c-135">スコア予測と計画されているアクションを使用して、将来の目標に向けて管理する</span><span class="sxs-lookup"><span data-stu-id="2dd8c-135">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="2dd8c-136">その他多数。</span><span class="sxs-lookup"><span data-stu-id="2dd8c-136">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="2dd8c-137">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="2dd8c-137">We want to hear from you</span></span>

<span data-ttu-id="2dd8c-138">問題がある場合は、「 [Security, Privacy & コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティ」に投稿してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="2dd8c-138">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="2dd8c-139">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="2dd8c-139">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="2dd8c-140">関連リソース</span><span class="sxs-lookup"><span data-stu-id="2dd8c-140">Related resources</span></span>

- [<span data-ttu-id="2dd8c-141">セキュリティ体制にアクセス</span><span class="sxs-lookup"><span data-stu-id="2dd8c-141">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="2dd8c-142">Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="2dd8c-142">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="2dd8c-143">今後の予定</span><span class="sxs-lookup"><span data-stu-id="2dd8c-143">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
