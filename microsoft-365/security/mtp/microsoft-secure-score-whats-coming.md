---
title: Microsoft セキュア スコアの新機能
description: Microsoft 365 セキュリティ センターの Microsoft セキュア スコアについて、詳細をどのように計算するか、セキュリティ管理者がどんなことを期待できるかについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュア スコア、セキュリティ センター、改善アクション
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
ms.openlocfilehash: 61f066b2fff2798e78e6379bbca46e48e93ff017
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895443"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="8eace-104">Microsoft セキュア スコアの新機能</span><span class="sxs-lookup"><span data-stu-id="8eace-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="8eace-105">お客様により優れたセキュリティ体制を提供し、使いやすさを向上させるために、Microsoft セキュア スコアは近日中に変化が加えられます。</span><span class="sxs-lookup"><span data-stu-id="8eace-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="8eace-106">お客様のスコアと最大可能スコアが新しくなります。</span><span class="sxs-lookup"><span data-stu-id="8eace-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="8eace-107">ただし、これによりセキュリティ体制が変わるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="8eace-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="8eace-108">最近の変更については、「[Microsoft セキュア スコアの新機能](microsoft-secure-score.md#whats-new)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8eace-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="8eace-109">2020年4月21日</span><span class="sxs-lookup"><span data-stu-id="8eace-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="8eace-110">改善アクションのうち、信頼できる測定としての条件を満たさないもの、またはセキュリティ体制の形として有用でないものは、削除しています。</span><span class="sxs-lookup"><span data-stu-id="8eace-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="8eace-111">Microsoft セキュリティ スコアが有意義であり、すべての改善アクションが測定可能かつ信頼性の高いものになるよう、次の改善アクションについては削除します。</span><span class="sxs-lookup"><span data-stu-id="8eace-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="8eace-112">過去30日間に使用されていないアカウントの削除/ブロック</span><span class="sxs-lookup"><span data-stu-id="8eace-112">Delete/block accounts not used in last 30 days</span></span>
- <span data-ttu-id="8eace-113">グローバル管理者を5名未満で指定する</span><span class="sxs-lookup"><span data-stu-id="8eace-113">Designate fewer than 5 global admins</span></span>
- <span data-ttu-id="8eace-114">ドキュメントへの IRM による保護の適用</span><span class="sxs-lookup"><span data-stu-id="8eace-114">Apply IRM protections to documents</span></span>
- <span data-ttu-id="8eace-115">データ損失防止ポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="8eace-115">Apply Data Loss Prevention policies</span></span>

### <a name="adding-additional-control-support-in-the-preview-version"></a><span data-ttu-id="8eace-116">プレビューバージョンでのコントロールサポートの追加</span><span class="sxs-lookup"><span data-stu-id="8eace-116">Adding additional control support in the preview version</span></span>
- <span data-ttu-id="8eace-117">ユーザーが管理されていないアプリケーションに同意を付与できないようにする (現時点でリリースされているバージョンで利用可能)</span><span class="sxs-lookup"><span data-stu-id="8eace-117">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

#### <a name="support-for-additional-microsoft-cloud-app-security-improvement-actions"></a><span data-ttu-id="8eace-118">その他の Microsoft Cloud App Security 向上アクションのサポート</span><span class="sxs-lookup"><span data-stu-id="8eace-118">Support for additional Microsoft Cloud App Security improvement actions</span></span>
- <span data-ttu-id="8eace-119">ドメインコントローラーで印刷スプーラーサービスを無効にする</span><span class="sxs-lookup"><span data-stu-id="8eace-119">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="8eace-120">セキュリティで保護されていない Kerberos 委任を変更して偽装を防止する</span><span class="sxs-lookup"><span data-stu-id="8eace-120">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="8eace-121">Microsoft LAPS を使用してローカル管理者パスワードを保護および管理する</span><span class="sxs-lookup"><span data-stu-id="8eace-121">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="8eace-122">機密性の高いエンティティに対して、重要な移動パスリスクを軽減する</span><span class="sxs-lookup"><span data-stu-id="8eace-122">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="8eace-123">機密グループからの休止アカウントの削除</span><span class="sxs-lookup"><span data-stu-id="8eace-123">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="8eace-124">セキュリティ保護のない SID 履歴属性をエンティティから削除する</span><span class="sxs-lookup"><span data-stu-id="8eace-124">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="8eace-125">安全でないアカウントの属性を解決する</span><span class="sxs-lookup"><span data-stu-id="8eace-125">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="8eace-126">クリアテキストの資格情報の公開を停止する</span><span class="sxs-lookup"><span data-stu-id="8eace-126">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="8eace-127">従来のプロトコル通信を停止する</span><span class="sxs-lookup"><span data-stu-id="8eace-127">Stop legacy protocols communication</span></span>
- <span data-ttu-id="8eace-128">暗号使用率の低い停止</span><span class="sxs-lookup"><span data-stu-id="8eace-128">Stop weak cipher usage</span></span>

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a><span data-ttu-id="8eace-129">Microsoft Defender ATP & 脆弱性管理 (TVM) のセキュリティに関する推奨事項のサポート</span><span class="sxs-lookup"><span data-stu-id="8eace-129">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations</span></span>
- <span data-ttu-id="8eace-130">リリースされた TVM で提供されるすべてのセキュリティの推奨事項は、Microsoft セキュリティスコアでも利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8eace-130">All released security recommendations supplied by TVM will now also be available in Microsoft Secure Score</span></span>
