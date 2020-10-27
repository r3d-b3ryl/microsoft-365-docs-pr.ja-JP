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
ms.openlocfilehash: 71316d6c53862b80178d06726f7c249a2491d659
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769032"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="15e05-104">Microsoft セキュリティスコアの新機能</span><span class="sxs-lookup"><span data-stu-id="15e05-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="15e05-105">Microsoft のセキュリティの評価をより良いものにするには、いくつかの変更を行いました。</span><span class="sxs-lookup"><span data-stu-id="15e05-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="15e05-106">予定されている変更の詳細については、「 [Microsoft Secure Score の内容](microsoft-secure-score-whats-coming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15e05-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

## <a name="august-2020"></a><span data-ttu-id="15e05-107">2020 年 8 月</span><span class="sxs-lookup"><span data-stu-id="15e05-107">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="15e05-108">Azure Active Directory の改善アクションを更新しました</span><span class="sxs-lookup"><span data-stu-id="15e05-108">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="15e05-109">レガシ認証をブロックするポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="15e05-109">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="15e05-110">Id のセキュリティで保護されたスコアとグラフ API の非互換性</span><span class="sxs-lookup"><span data-stu-id="15e05-110">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="15e05-111">Microsoft Secure Score の最近のリリースでは、向上したスコアリングモデルがリリースされました。</span><span class="sxs-lookup"><span data-stu-id="15e05-111">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="15e05-112">これらの変更により、より柔軟かつ正確にセキュリティ状況を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="15e05-112">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="15e05-113">しかし、これらの更新プログラムにより、Microsoft セキュリティスコアが Id のセキュリティで保護されたスコアと Graph API とは一時的に互換性がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="15e05-113">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="15e05-114">時間では、Id のセキュリティスコアと Graph API が新しいスコアリングモデルを採用します。</span><span class="sxs-lookup"><span data-stu-id="15e05-114">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="15e05-115">その後、Microsoft のセキュリティで保護されたスコア、Id のセキュリティで保護されたスコア、Graph API によって報告されたスコアの違いがわかります。</span><span class="sxs-lookup"><span data-stu-id="15e05-115">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="15e05-116">ご不便をかけて申し訳ございません。今後、このようなエクスペリエンスの互換性を確保するために取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="15e05-116">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="15e05-117">更新された改善アクション</span><span class="sxs-lookup"><span data-stu-id="15e05-117">Updated improvement actions</span></span>

- <span data-ttu-id="15e05-118">Azure Active Directory の改善アクションを追加しました</span><span class="sxs-lookup"><span data-stu-id="15e05-118">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="15e05-119">Azure Advanced Threat Protection の向上アクションを追加しました</span><span class="sxs-lookup"><span data-stu-id="15e05-119">Added Azure Advanced Threat Protection improvement actions</span></span>
- <span data-ttu-id="15e05-120">Microsoft Defender ATP の [脅威 & 脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) のセキュリティに関する推奨事項のサポート</span><span class="sxs-lookup"><span data-stu-id="15e05-120">Support for Microsoft Defender ATP [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="15e05-121">リリースされた TVM で提供されるすべてのセキュリティの推奨事項を使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="15e05-121">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="15e05-122">更新されたインターフェイスと機能</span><span class="sxs-lookup"><span data-stu-id="15e05-122">Updated interface and functionality</span></span>

* <span data-ttu-id="15e05-123">CISO およびリード レベルのディスカッションのすべての新しい指標と傾向の表示</span><span class="sxs-lookup"><span data-stu-id="15e05-123">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="15e05-124">スコアを追跡して評価するための新しい方法</span><span class="sxs-lookup"><span data-stu-id="15e05-124">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="15e05-125">スコア回帰の追跡と理解の向上</span><span class="sxs-lookup"><span data-stu-id="15e05-125">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="15e05-126">改善のための処置のフィルタリング、タグ付け、検索、グループ化</span><span class="sxs-lookup"><span data-stu-id="15e05-126">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="15e05-127">スコア予測と計画されているアクションを使用して、将来の目標に向けて管理する</span><span class="sxs-lookup"><span data-stu-id="15e05-127">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="15e05-128">その他多数。</span><span class="sxs-lookup"><span data-stu-id="15e05-128">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="15e05-129">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="15e05-129">We want to hear from you</span></span>

<span data-ttu-id="15e05-130">問題がある場合は、「 [Security, Privacy & コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティ」に投稿してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="15e05-130">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="15e05-131">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="15e05-131">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="15e05-132">関連リソース</span><span class="sxs-lookup"><span data-stu-id="15e05-132">Related resources</span></span>

- [<span data-ttu-id="15e05-133">セキュリティ体制にアクセス</span><span class="sxs-lookup"><span data-stu-id="15e05-133">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="15e05-134">Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="15e05-134">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="15e05-135">今後の予定</span><span class="sxs-lookup"><span data-stu-id="15e05-135">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
